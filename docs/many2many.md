# many2many

If the order is switched the channel will be closed before all messages are sent.

If the `close(ch)` is moved to the end of `Produce()` the channel will be closed when one instance of the produce is done sending. The other instances will still have messages to send.

If the `close(ch)` is removed completely the conumers are never closed since their loop continues until the channel is closed.

If the number of consumers is increased the number of strings being printed is also increased on average, it is still random.

All strings are most likely not printed.