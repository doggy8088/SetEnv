# SetEnv

A free tool allows you to set/update/delete `User` or `System` Environment Variables, e.g. `PATH`.

> For Windows 9x/NT/2000/XP/S2K3/Vista/7/8/10/11.

## Usage

```txt
Usage: SetEnv -<options> <name> <value>

Options (Default is System variable, add -u for User):

    SetEnv -a name value      Set the SYSTEM environment variable to the specified value
    SetEnv -a name %value     Add a value to an expanded SYSTEM environment variable
    SetEnv -ua name           Add a value to an expanded USER environment variable
    SetEnv -ap name %value    Prepend a value to an expanded SYSTEM environment variable
    SetEnv -uap name %value   Prepend a value to an expanded USER environment variable

    SetEnv -d name            Delete the SYSTEM environment variable
    SetEnv -ud name           Deletes a USER environment variable
    SetEnv -d name %value     Delete the value from the expanded SYSTEM environment variable
    SetEnv -ud name %value    Deletes the value from the expanded USER environment variable

    SetEnv -e                 Show examples of using SetEnv

Return Values:

    0                         Success
    5                         Access Denied
    1                         Other Error (Error messages go to stderr)

Notes:

    If you want to create an expanded variable with multiple values, e.g. PATH

    specify the value with a preceeding '%' character, e.g. SetEnv PATH %d:\\Bin

    Use double quotes around any value which contains spaces.
```

## Examples

- 從 `SYSTEM` 環境變數加入一個 `PATH` 路徑 (加在路徑最前面，優先權最高)

    ```bat
    setenv -ap PATH %%C:\AngularDev\Code\bin
    ```

    > 寫在 `*.bat` 中要將 `%` 寫成 `%%` 才行

- 從 `USER` 環境變數加入一個 `PATH` 路徑 (加在路徑最前面，優先權最高)

    ```bat
    setenv -uap PATH %%C:\AngularDev\Code\bin
    ```

    > 寫在 `*.bat` 中要將 `%` 寫成 `%%` 才行

- 從 `SYSTEM` 環境變數刪除一個 `PATH` 路徑

    ```bat
    setenv -d PATH %%C:\AngularDev\Code\bin
    ```

    > 寫在 `*.bat` 中要將 `%` 寫成 `%%` 才行


- 從 `USER` 環境變數刪除一個 `PATH` 路徑

    ```bat
    setenv -ud PATH %%C:\AngularDev\Code\bin
    ```

    > 寫在 `*.bat` 中要將 `%` 寫成 `%%` 才行
