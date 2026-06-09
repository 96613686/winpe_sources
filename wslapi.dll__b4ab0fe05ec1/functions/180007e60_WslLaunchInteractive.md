# WslLaunchInteractive

- ea: `0x180007e60`
- end: `0x180007efc`
- name: `WslLaunchInteractive`
- size: `156`
- prototype: `HRESULT __stdcall(PCWSTR distributionName, PCWSTR command, BOOL useCurrentWorkingDirectory, DWORD *exitCode)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180006968`
- `0x1800077a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007ed5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007ed5`

## pseudocode

```c
HRESULT __stdcall WslLaunchInteractive(
        PCWSTR distributionName,
        PCWSTR command,
        BOOL useCurrentWorkingDirectory,
        DWORD *exitCode)
{
  HRESULT v4; // ebx
  HANDLE hHandle; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v7[5]; // [rsp+28h] [rbp-40h] BYREF
  int v8; // [rsp+50h] [rbp-18h] BYREF
  PCWSTR v9; // [rsp+80h] [rbp+18h] BYREF
  PCWSTR v10; // [rsp+88h] [rbp+20h] BYREF
  BOOL v11; // [rsp+90h] [rbp+28h] BYREF
  DWORD *v12; // [rsp+98h] [rbp+30h] BYREF

  v12 = exitCode;
  v11 = useCurrentWorkingDirectory;
  v10 = command;
  v9 = distributionName;
  v8 = -2147467259;
  v7[0] = &v8;
  hHandle = 0;
  v7[1] = &v9;
  v7[2] = &v10;
  v7[3] = &v11;
  v7[4] = &v12;
  CreateThreadFromLambda__lambda_3f888ffeeb51c4c77808cd545df17201_(&hHandle, (__int64)v7);
  WaitForSingleObject(hHandle, 0xFFFFFFFF);
  v4 = v8;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
  return v4;
}

```

## disassembly

```asm
0x180007e60  mov     rax, rsp
0x180007e63  mov     [rax+20h], r9
0x180007e67  mov     [rax+18h], r8d
0x180007e6b  mov     [rax+10h], rdx
0x180007e6f  mov     [rax+8], rcx
0x180007e73  push    rbp
0x180007e74  push    rbx
0x180007e75  mov     rbp, rsp
0x180007e78  sub     rsp, 68h
0x180007e7c  mov     rax, cs:__security_cookie
0x180007e83  xor     rax, rsp
0x180007e86  mov     [rbp+var_10], rax
0x180007e8a  lea     rax, [rbp+var_18]
0x180007e8e  mov     [rbp+var_18], 80004005h
0x180007e95  mov     [rbp+var_40], rax
0x180007e99  lea     rdx, [rbp+var_40]
0x180007e9d  lea     rax, [rbp+arg_0]
0x180007ea1  mov     [rbp+hHandle], 0
0x180007ea9  mov     [rbp+var_38], rax
0x180007ead  lea     rcx, [rbp+hHandle]
0x180007eb1  lea     rax, [rbp+arg_8]
0x180007eb5  mov     [rbp+var_30], rax
0x180007eb9  lea     rax, [rbp+arg_10]
0x180007ebd  mov     [rbp+var_28], rax
0x180007ec1  lea     rax, [rbp+arg_18]
0x180007ec5  mov     [rbp+var_20], rax
0x180007ec9  call    CreateThreadFromLambda__lambda_3f888ffeeb51c4c77808cd545df17201___; CreateThreadFromLambda__lambda_3f888ffeeb51c4c77808cd545df17201_
0x180007ece  mov     rcx, [rbp+hHandle]; hHandle
0x180007ed2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007ed5  call    cs:__imp_WaitForSingleObject
0x180007edb  mov     ebx, [rbp+var_18]
0x180007ede  lea     rcx, [rbp+hHandle]
0x180007ee2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007ee7  mov     eax, ebx
0x180007ee9  mov     rcx, [rbp+var_10]
0x180007eed  xor     rcx, rsp; StackCookie
0x180007ef0  call    __security_check_cookie
0x180007ef5  add     rsp, 68h
0x180007ef9  pop     rbx
0x180007efa  pop     rbp
0x180007efb  retn
```
