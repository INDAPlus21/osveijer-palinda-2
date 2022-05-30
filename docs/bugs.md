# Buggy code

## bug01.go

Does not work because messages aren't received in the goroutine they are sent from. My fix moves the send to an other goroutine so it can be received in the main goroutine.

## bug02.go

Does not work because the channel is closed before the goroutine that is doing the printing is done. My fix adds a waitgroup and then waits for all goroutines to be done before moving on to closing the channel.