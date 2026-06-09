# WslConfigureDistribution

- ea: `0x180006c10`
- end: `0x180006ca9`
- name: `WslConfigureDistribution`
- size: `153`
- prototype: `HRESULT __stdcall(PCWSTR distributionName, ULONG defaultUID, WSL_DISTRIBUTION_FLAGS wslDistributionFlags)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001dc0`
- `0x1800066dc`
- `0x180006968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006c7b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006c7b`

## pseudocode

```c
HRESULT __stdcall WslConfigureDistribution(
        PCWSTR distributionName,
        ULONG defaultUID,
        WSL_DISTRIBUTION_FLAGS wslDistributionFlags)
{
  HRESULT v3; // ebx
  HANDLE hHandle; // [rsp+20h] [rbp-40h] BYREF
  __int128 v6; // [rsp+28h] [rbp-38h] BYREF
  ULONG *v7; // [rsp+38h] [rbp-28h]
  WSL_DISTRIBUTION_FLAGS *v8; // [rsp+40h] [rbp-20h]
  int v9; // [rsp+48h] [rbp-18h] BYREF
  PCWSTR v10; // [rsp+70h] [rbp+10h] BYREF
  ULONG v11; // [rsp+78h] [rbp+18h] BYREF
  WSL_DISTRIBUTION_FLAGS v12; // [rsp+80h] [rbp+20h] BYREF

  v12 = wslDistributionFlags;
  v11 = defaultUID;
  v10 = distributionName;
  v9 = -2147467259;
  *(_QWORD *)&v6 = &v9;
  hHandle = 0;
  *((_QWORD *)&v6 + 1) = &v10;
  v7 = &v11;
  v8 = &v12;
  CreateThreadFromLambda__lambda_30c9907fbca49ad387fb0dd3a4426001_(&hHandle, &v6);
  WaitForSingleObject(hHandle, 0xFFFFFFFF);
  v3 = v9;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
  return v3;
}

```

## disassembly

```asm
0x180006c10  mov     rax, rsp
0x180006c13  mov     [rax+20h], rbx
0x180006c17  mov     [rax+18h], r8d
0x180006c1b  mov     [rax+10h], edx
0x180006c1e  mov     [rax+8], rcx
0x180006c22  push    rbp
0x180006c23  mov     rbp, rsp
0x180006c26  sub     rsp, 60h
0x180006c2a  mov     rax, cs:__security_cookie
0x180006c31  xor     rax, rsp
0x180006c34  mov     [rbp+var_10], rax
0x180006c38  lea     rax, [rbp+var_18]
0x180006c3c  mov     [rbp+var_18], 80004005h
0x180006c43  mov     [rbp+var_38], rax
0x180006c47  lea     rdx, [rbp+var_38]
0x180006c4b  lea     rax, [rbp+arg_0]
0x180006c4f  mov     [rbp+hHandle], 0
0x180006c57  mov     [rbp+var_30], rax
0x180006c5b  lea     rcx, [rbp+hHandle]
0x180006c5f  lea     rax, [rbp+arg_8]
0x180006c63  mov     [rbp+var_28], rax
0x180006c67  lea     rax, [rbp+arg_10]
0x180006c6b  mov     [rbp+var_20], rax
0x180006c6f  call    CreateThreadFromLambda__lambda_30c9907fbca49ad387fb0dd3a4426001___; CreateThreadFromLambda__lambda_30c9907fbca49ad387fb0dd3a4426001_
0x180006c74  mov     rcx, [rbp+hHandle]; hHandle
0x180006c78  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006c7b  call    cs:__imp_WaitForSingleObject
0x180006c81  mov     ebx, [rbp+var_18]
0x180006c84  lea     rcx, [rbp+hHandle]
0x180006c88  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006c8d  mov     eax, ebx
0x180006c8f  mov     rcx, [rbp+var_10]
0x180006c93  xor     rcx, rsp; StackCookie
0x180006c96  call    __security_check_cookie
0x180006c9b  mov     rbx, [rsp+60h+arg_18]
0x180006ca3  add     rsp, 60h
0x180006ca7  pop     rbp
0x180006ca8  retn
```
