# GetTokenHandle

- ea: `0x14005f274`
- end: `0x14005f377`
- name: `GetTokenHandle`
- size: `259`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400618f8`

## callees

- `0x140016314`
- `0x14005e8c0`
- `0x14005f1dc`
- `0x14005f274`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f2d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f30d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f2d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f30d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005f320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005f320`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005f2c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005f2ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005f2c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005f2ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005f2ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005f2e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005f2ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005f2e8`
- `ADVAPI32!OpenProcessToken` at `0x14005f334`
- `ADVAPI32!OpenProcessToken` at `0x14005f334`

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
0x14005f274  mov     [rsp+arg_0], rbx
0x14005f279  mov     [rsp+arg_8], rsi
0x14005f27e  push    rdi
0x14005f27f  sub     rsp, 20h
0x14005f283  mov     rdi, rcx
0x14005f286  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14005f28d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14005f292  test    al, al
0x14005f294  jz      loc_14005F346
0x14005f29a  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x14005f29f  neg     eax
0x14005f2a1  mov     ebx, 1
0x14005f2a6  sbb     esi, esi
0x14005f2a8  and     esi, 0FFFFFFE0h
0x14005f2ab  add     esi, 28h ; '('
0x14005f2ae  call    cs:__imp_GetCurrentThread
0x14005f2b5  nop     dword ptr [rax+rax+00h]
0x14005f2ba  mov     r9, rdi; TokenHandle
0x14005f2bd  xor     r8d, r8d; OpenAsSelf
0x14005f2c0  mov     rcx, rax; ThreadHandle
0x14005f2c3  mov     edx, esi; DesiredAccess
0x14005f2c5  call    cs:__imp_OpenThreadToken
0x14005f2cc  nop     dword ptr [rax+rax+00h]
0x14005f2d1  test    eax, eax
0x14005f2d3  jnz     short loc_14005F30D
0x14005f2d5  call    cs:__imp_GetLastError
0x14005f2dc  nop     dword ptr [rax+rax+00h]
0x14005f2e1  cmp     eax, 3F0h
0x14005f2e6  jz      short loc_14005F30D
0x14005f2e8  call    cs:__imp_GetCurrentThread
0x14005f2ef  nop     dword ptr [rax+rax+00h]
0x14005f2f4  mov     r9, rdi; TokenHandle
0x14005f2f7  mov     r8d, ebx; OpenAsSelf
0x14005f2fa  mov     rcx, rax; ThreadHandle
0x14005f2fd  mov     edx, esi; DesiredAccess
0x14005f2ff  call    cs:__imp_OpenThreadToken
0x14005f306  nop     dword ptr [rax+rax+00h]
0x14005f30b  mov     ebx, eax
0x14005f30d  call    cs:__imp_GetLastError
0x14005f314  nop     dword ptr [rax+rax+00h]
0x14005f319  cmp     eax, 3F0h
0x14005f31e  jnz     short loc_14005F342
0x14005f320  call    cs:__imp_GetCurrentProcess
0x14005f327  nop     dword ptr [rax+rax+00h]
0x14005f32c  mov     r8, rdi; TokenHandle
0x14005f32f  mov     edx, esi; DesiredAccess
0x14005f331  mov     rcx, rax; ProcessHandle
0x14005f334  call    cs:__imp_OpenProcessToken
0x14005f33b  nop     dword ptr [rax+rax+00h]
0x14005f340  mov     ebx, eax
0x14005f342  mov     eax, ebx
0x14005f344  jmp     short loc_14005F366
0x14005f346  call    ?IsWindowsProtectedPrintSpoolerWorkerEnabled@@YAHXZ; IsWindowsProtectedPrintSpoolerWorkerEnabled(void)
0x14005f34b  xor     r8d, r8d
0x14005f34e  mov     rcx, rdi; TokenHandle
0x14005f351  test    eax, eax
0x14005f353  setz    r8b; int
0x14005f357  neg     eax
0x14005f359  sbb     edx, edx
0x14005f35b  and     edx, 0FFFFFFE0h
0x14005f35e  add     edx, 28h ; '('; DesiredAccess
0x14005f361  call    ?GetTokenHandleInternal@@YAHPEAPEAXKH@Z; GetTokenHandleInternal(void * *,ulong,int)
0x14005f366  mov     rbx, [rsp+28h+arg_0]
0x14005f36b  mov     rsi, [rsp+28h+arg_8]
0x14005f370  add     rsp, 20h
0x14005f374  pop     rdi
0x14005f375  retn
```
