# UART Communications


## Peripheral Setup

* Asynchronous
* 115200 baudrate


## Code Snippets

**print off some data**

```c
char msg[256];

// print version of the code to debug log
sprintf(msg, "%s\n--------------\nAuthor: Malcolm Boyes\nCompiler Version: %s\nCompiled On: %s at %s\n--------------\n", logo, __VERSION__, __DATE__, __TIME__);
HAL_UART_Transmit(&huart2, (uint8_t *) msg, strlen(msg), HAL_MAX_DELAY);
```


**print off anything**

```c
char msg[256];

// print version of the code to debug log
sprintf(msg, "this is my message");
HAL_UART_Transmit(&huart2, (uint8_t *) msg, strlen(msg), HAL_MAX_DELAY);
```