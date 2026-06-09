# GetTokenHandle

- ea: `0x140059a6c`
- end: `0x140059b3a`
- name: `GetTokenHandle`
- size: `206`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14005be08`

## callees

- `0x140014fc4`
- `0x140059114`
- `0x1400599f4`
- `0x140059a6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059ae3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059af0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059af0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059ab3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059adb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059ab3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059adb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140059aa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140059aca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140059aa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140059aca`
- `ADVAPI32!OpenProcessToken` at `0x140059afe`
- `ADVAPI32!OpenProcessToken` at `0x140059afe`

## pseudocode

```c
__int64 __fastcall GetTokenHandle(PHANDLE TokenHandle)
{
  unsigned int v2; // ebx
  DWORD v3; // esi
  HANDLE CurrentThread; // rax
  HANDLE v5; // rax
  HANDLE CurrentProcess; // rax
  int v8; // eax

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    v2 = 1;
    v3 = (unsigned int)IsWindowsProtectedPrintSpoolerWorkerEnabled() != 0 ? 8 : 40;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, v3, 0, TokenHandle) && GetLastError() != 1008 )
    {
      v5 = GetCurrentThread();
      v2 = OpenThreadToken(v5, v3, 1, TokenHandle);
    }
    if ( GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      return OpenProcessToken(CurrentProcess, v3, TokenHandle);
    }
    return v2;
  }
  else
  {
    v8 = IsWindowsProtectedPrintSpoolerWorkerEnabled();
    return GetTokenHandleInternal(TokenHandle, v8 != 0 ? 8 : 40, v8 == 0);
  }
}

```

## disassembly

```asm
0x140059a6c  mov     [rsp+arg_0], rbx
0x140059a71  mov     [rsp+arg_8], rsi
0x140059a76  push    rdi
0x140059a77  sub     rsp, 20h
0x140059a7b  mov     rdi, rcx
0x140059a7e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140059a85  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140059a8a  test    al, al
0x140059a8c  jz      short loc_140059B0A
0x140059a8e  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x140059a93  neg     eax
0x140059a95  mov     ebx, 1
0x140059a9a  sbb     esi, esi
0x140059a9c  and     esi, 0FFFFFFE0h
0x140059a9f  add     esi, 28h ; '('
0x140059aa2  call    cs:__imp_GetCurrentThread
0x140059aa8  mov     r9, rdi; TokenHandle
0x140059aab  xor     r8d, r8d; OpenAsSelf
0x140059aae  mov     rcx, rax; ThreadHandle
0x140059ab1  mov     edx, esi; DesiredAccess
0x140059ab3  call    cs:__imp_OpenThreadToken
0x140059ab9  test    eax, eax
0x140059abb  jnz     short loc_140059AE3
0x140059abd  call    cs:__imp_GetLastError
0x140059ac3  cmp     eax, 3F0h
0x140059ac8  jz      short loc_140059AE3
0x140059aca  call    cs:__imp_GetCurrentThread
0x140059ad0  mov     r9, rdi; TokenHandle
0x140059ad3  mov     r8d, ebx; OpenAsSelf
0x140059ad6  mov     rcx, rax; ThreadHandle
0x140059ad9  mov     edx, esi; DesiredAccess
0x140059adb  call    cs:__imp_OpenThreadToken
0x140059ae1  mov     ebx, eax
0x140059ae3  call    cs:__imp_GetLastError
0x140059ae9  cmp     eax, 3F0h
0x140059aee  jnz     short loc_140059B06
0x140059af0  call    cs:__imp_GetCurrentProcess
0x140059af6  mov     r8, rdi; TokenHandle
0x140059af9  mov     edx, esi; DesiredAccess
0x140059afb  mov     rcx, rax; ProcessHandle
0x140059afe  call    cs:__imp_OpenProcessToken
0x140059b04  mov     ebx, eax
0x140059b06  mov     eax, ebx
0x140059b08  jmp     short loc_140059B2A
0x140059b0a  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x140059b0f  xor     r8d, r8d
0x140059b12  mov     rcx, rdi; TokenHandle
0x140059b15  test    eax, eax
0x140059b17  setz    r8b; int
0x140059b1b  neg     eax
0x140059b1d  sbb     edx, edx
0x140059b1f  and     edx, 0FFFFFFE0h
0x140059b22  add     edx, 28h ; '('; DesiredAccess
0x140059b25  call    ?GetTokenHandleInternal@@YAHPEAPEAXKH@Z; GetTokenHandleInternal(void * *,ulong,int)
0x140059b2a  mov     rbx, [rsp+28h+arg_0]
0x140059b2f  mov     rsi, [rsp+28h+arg_8]
0x140059b34  add     rsp, 20h
0x140059b38  pop     rdi
0x140059b39  retn
```
