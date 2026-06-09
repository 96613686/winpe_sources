# WslGetDistributionConfiguration

- ea: `0x180006cb0`
- end: `0x180006d5c`
- name: `WslGetDistributionConfiguration`
- size: `172`
- prototype: `HRESULT __stdcall(PCWSTR distributionName, ULONG *distributionVersion, ULONG *defaultUID, WSL_DISTRIBUTION_FLAGS *wslDistributionFlags, PSTR **defaultEnvironmentVariables, ULONG *defaultEnvironmentVariableCount)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001dc0`
- `0x18000677c`
- `0x180006968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006d35`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006d35`

## pseudocode

```c
HRESULT __stdcall WslGetDistributionConfiguration(
        PCWSTR distributionName,
        ULONG *distributionVersion,
        ULONG *defaultUID,
        WSL_DISTRIBUTION_FLAGS *wslDistributionFlags,
        PSTR **defaultEnvironmentVariables,
        ULONG *defaultEnvironmentVariableCount)
{
  HRESULT v6; // ebx
  HANDLE hHandle; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v9[7]; // [rsp+28h] [rbp-50h] BYREF
  int v10; // [rsp+60h] [rbp-18h] BYREF
  PCWSTR v11; // [rsp+90h] [rbp+18h] BYREF
  ULONG *v12; // [rsp+98h] [rbp+20h] BYREF
  ULONG *v13; // [rsp+A0h] [rbp+28h] BYREF
  WSL_DISTRIBUTION_FLAGS *v14; // [rsp+A8h] [rbp+30h] BYREF

  v14 = wslDistributionFlags;
  v13 = defaultUID;
  v12 = distributionVersion;
  v11 = distributionName;
  v10 = -2147467259;
  v9[0] = &v10;
  hHandle = 0;
  v9[1] = &v11;
  v9[2] = &v12;
  v9[3] = &v13;
  v9[4] = &v14;
  v9[5] = &defaultEnvironmentVariables;
  v9[6] = &defaultEnvironmentVariableCount;
  CreateThreadFromLambda__lambda_a36406807b7b7f438664203591e8456f_(&hHandle, (__int64)v9);
  WaitForSingleObject(hHandle, 0xFFFFFFFF);
  v6 = v10;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
  return v6;
}

```

## disassembly

```asm
0x180006cb0  mov     rax, rsp
0x180006cb3  mov     [rax+20h], r9
0x180006cb7  mov     [rax+18h], r8
0x180006cbb  mov     [rax+10h], rdx
0x180006cbf  mov     [rax+8], rcx
0x180006cc3  push    rbp
0x180006cc4  push    rbx
0x180006cc5  mov     rbp, rsp
0x180006cc8  sub     rsp, 78h
0x180006ccc  mov     rax, cs:__security_cookie
0x180006cd3  xor     rax, rsp
0x180006cd6  mov     [rbp+var_10], rax
0x180006cda  lea     rax, [rbp+var_18]
0x180006cde  mov     [rbp+var_18], 80004005h
0x180006ce5  mov     [rbp+var_50], rax
0x180006ce9  lea     rdx, [rbp+var_50]
0x180006ced  lea     rax, [rbp+arg_0]
0x180006cf1  mov     [rbp+hHandle], 0
0x180006cf9  mov     [rbp+var_48], rax
0x180006cfd  lea     rcx, [rbp+hHandle]
0x180006d01  lea     rax, [rbp+arg_8]
0x180006d05  mov     [rbp+var_40], rax
0x180006d09  lea     rax, [rbp+arg_10]
0x180006d0d  mov     [rbp+var_38], rax
0x180006d11  lea     rax, [rbp+arg_18]
0x180006d15  mov     [rbp+var_30], rax
0x180006d19  lea     rax, [rbp+defaultEnvironmentVariables]
0x180006d1d  mov     [rbp+var_28], rax
0x180006d21  lea     rax, [rbp+defaultEnvironmentVariableCount]
0x180006d25  mov     [rbp+var_20], rax
0x180006d29  call    CreateThreadFromLambda__lambda_a36406807b7b7f438664203591e8456f___; CreateThreadFromLambda__lambda_a36406807b7b7f438664203591e8456f_
0x180006d2e  mov     rcx, [rbp+hHandle]; hHandle
0x180006d32  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006d35  call    cs:__imp_WaitForSingleObject
0x180006d3b  mov     ebx, [rbp+var_18]
0x180006d3e  lea     rcx, [rbp+hHandle]
0x180006d42  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006d47  mov     eax, ebx
0x180006d49  mov     rcx, [rbp+var_10]
0x180006d4d  xor     rcx, rsp; StackCookie
0x180006d50  call    __security_check_cookie
0x180006d55  add     rsp, 78h
0x180006d59  pop     rbx
0x180006d5a  pop     rbp
0x180006d5b  retn
```
