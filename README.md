Identify record-breaking highs and lows in 2015
record_breaking_highs = df_2015_pivot['TMAX'] > record_high
record_breaking_lows = df_2015_pivot['TMIN'] < record_low

# Plotting with 2015 overlay
plt.figure(figsize=(10, 5))
plt.plot(record_high, label='Record High (2005-2014)', color='red')
plt.plot(record_low, label='Record Low (2005-2014)', color='blue')
plt.fill_between(record_high.index, record_high, record_low, color='gray', alpha=0.1)
plt.scatter(df_2015_pivot.index[record_breaking_highs], df_2015_pivot['TMAX'][record_breaking_highs], color='orange', label='Record Breaking High (2015)')
plt.scatter(df_2015_pivot.index[record_breaking_lows], df_2015_pivot['TMIN'][record_breaking_lows], color='purple', label='Record Breaking Low (2015)')
plt.xlabel('Day of the Year')
plt.ylabel('Temperature (Tenths of Degrees C)')
plt.title('Record High and Low Temperatures (2005-2014) with 2015 Record Breakers')
plt.legend()
plt.show()
