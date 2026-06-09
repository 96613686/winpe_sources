# WslLaunch

- ea: `0x180007d90`
- end: `0x180007e4b`
- name: `WslLaunch`
- size: `187`
- prototype: `HRESULT __stdcall(PCWSTR distributionName, PCWSTR command, BOOL useCurrentWorkingDirectory, HANDLE stdIn, HANDLE stdOut, HANDLE stdErr, HANDLE *process)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180006968`
- `0x180007850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007e21`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007e21`

## pseudocode

```c
HRESULT __stdcall WslLaunch(
        PCWSTR distributionName,
        PCWSTR command,
        BOOL useCurrentWorkingDirectory,
        HANDLE stdIn,
        HANDLE stdOut,
        HANDLE stdErr,
        HANDLE *process)
{
  HRESULT v7; // ebx
  HANDLE hHandle; // [rsp+28h] [rbp-31h] BYREF
  __int128 v10; // [rsp+30h] [rbp-29h] BYREF
  PCWSTR *v11; // [rsp+40h] [rbp-19h]
  BOOL *v12; // [rsp+48h] [rbp-11h]
  HANDLE *v13; // [rsp+50h] [rbp-9h]
  HANDLE *p_stdOut; // [rsp+58h] [rbp-1h]
  HANDLE *p_stdErr; // [rsp+60h] [rbp+7h]
  HANDLE **p_process; // [rsp+68h] [rbp+Fh]
  int v17; // [rsp+70h] [rbp+17h] BYREF
  PCWSTR v18; // [rsp+A8h] [rbp+4Fh] BYREF
  PCWSTR v19; // [rsp+B0h] [rbp+57h] BYREF
  BOOL v20; // [rsp+B8h] [rbp+5Fh] BYREF
  HANDLE v21; // [rsp+C0h] [rbp+67h] BYREF

  v21 = stdIn;
  v20 = useCurrentWorkingDirectory;
  v19 = command;
  v18 = distributionName;
  v17 = -2147467259;
  *(_QWORD *)&v10 = &v17;
  hHandle = 0;
  *((_QWORD *)&v10 + 1) = &v18;
  v11 = &v19;
  v12 = &v20;
  v13 = &v21;
  p_stdOut = &stdOut;
  p_stdErr = &stdErr;
  p_process = &process;
  CreateThreadFromLambda__lambda_d4251f4926f6295bfcc87f753188dddd_(&hHandle, &v10);
  WaitForSingleObject(hHandle, 0xFFFFFFFF);
  v7 = v17;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
  return v7;
}

```

## disassembly

```asm
0x180007d90  mov     rax, rsp
0x180007d93  mov     [rax+20h], r9
0x180007d97  mov     [rax+18h], r8d
0x180007d9b  mov     [rax+10h], rdx
0x180007d9f  mov     [rax+8], rcx
0x180007da3  push    rbp
0x180007da4  push    rbx
0x180007da5  lea     rbp, [rax-47h]
0x180007da9  sub     rsp, 88h
0x180007db0  mov     rax, cs:__security_cookie
0x180007db7  xor     rax, rsp
0x180007dba  mov     [rbp+3Fh+var_20], rax
0x180007dbe  lea     rax, [rbp+3Fh+var_28]
0x180007dc2  mov     [rbp+3Fh+var_28], 80004005h
0x180007dc9  mov     [rbp+3Fh+var_68], rax
0x180007dcd  lea     rdx, [rbp+3Fh+var_68]
0x180007dd1  lea     rax, [rbp+3Fh+arg_0]
0x180007dd5  mov     [rbp+3Fh+hHandle], 0
0x180007ddd  mov     [rbp+3Fh+var_60], rax
0x180007de1  lea     rcx, [rbp+3Fh+hHandle]
0x180007de5  lea     rax, [rbp+3Fh+arg_8]
0x180007de9  mov     [rbp+3Fh+var_58], rax
0x180007ded  lea     rax, [rbp+3Fh+arg_10]
0x180007df1  mov     [rbp+3Fh+var_50], rax
0x180007df5  lea     rax, [rbp+3Fh+arg_18]
0x180007df9  mov     [rbp+3Fh+var_48], rax
0x180007dfd  lea     rax, [rbp+3Fh+stdOut]
0x180007e01  mov     [rbp+3Fh+var_40], rax
0x180007e05  lea     rax, [rbp+3Fh+stdErr]
0x180007e09  mov     [rbp+3Fh+var_38], rax
0x180007e0d  lea     rax, [rbp+3Fh+process]
0x180007e11  mov     [rbp+3Fh+var_30], rax
0x180007e15  call    CreateThreadFromLambda__lambda_d4251f4926f6295bfcc87f753188dddd___; CreateThreadFromLambda__lambda_d4251f4926f6295bfcc87f753188dddd_
0x180007e1a  mov     rcx, [rbp+3Fh+hHandle]; hHandle
0x180007e1e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007e21  call    cs:__imp_WaitForSingleObject
0x180007e27  mov     ebx, [rbp+3Fh+var_28]
0x180007e2a  lea     rcx, [rbp+3Fh+hHandle]
0x180007e2e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007e33  mov     eax, ebx
0x180007e35  mov     rcx, [rbp+3Fh+var_20]
0x180007e39  xor     rcx, rsp; StackCookie
0x180007e3c  call    __security_check_cookie
0x180007e41  add     rsp, 88h
0x180007e48  pop     rbx
0x180007e49  pop     rbp
0x180007e4a  retn
```
