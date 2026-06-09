# SpoolerInit

- ea: `0x14006abd0`
- end: `0x14006ad02`
- name: `SpoolerInit`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140066058`

## callees

- `0x140003c70`
- `0x1400041c0`
- `0x140014fc4`
- `0x140017604`
- `0x140057e2c`
- `0x14006a910`
- `0x14006abd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ac76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ace0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ac76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ace0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14006ac58`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14006ac58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14006ac29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14006ac43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14006ac29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14006ac43`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14006aca7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14006aca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006acb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006acc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006acb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006acc5`

## pseudocode

```c
__int64 SpoolerInit()
{
  __int64 result; // rax
  __int64 v1; // rbx
  unsigned int v2; // edi
  __int64 ClientUserHandle; // rax
  HANDLE CurrentThread; // rax
  void **v5; // r9
  HANDLE v6; // rax
  HANDLE v7; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  result = DllAllocSplMem(0x440u);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    ClientUserHandle = SplGetClientUserHandle(131103);
    *(_QWORD *)(v1 + 8) = ClientUserHandle;
    if ( !ClientUserHandle )
      goto LABEL_14;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    {
      CurrentThread = GetCurrentThread();
      if ( SecurityHelper::OpenThreadToken(CurrentThread, 0xEu, (PHANDLE)v1, v5) )
        goto LABEL_7;
    }
    else
    {
      v6 = GetCurrentThread();
      if ( !OpenThreadToken(v6, 0xEu, 1, (PHANDLE)v1) )
      {
LABEL_7:
        FreeRegUser((struct INIT_REG_USER *)(v1 + 8));
        HeapFree(g_hSpoolssHeap, 0, (LPVOID)v1);
        v1 = 0;
      }
    }
    if ( !v1 )
      return v2;
    if ( Initialized )
    {
      SpoolerUserInit((_QWORD *)v1);
      return 1;
    }
    v7 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SpoolerUserInit, (LPVOID)v1, 0, &ThreadId);
    if ( v7 )
    {
      CloseHandle(v7);
      return 1;
    }
    CloseHandle(*(HANDLE *)v1);
    FreeRegUser((struct INIT_REG_USER *)(v1 + 8));
LABEL_14:
    HeapFree(g_hSpoolssHeap, 0, (LPVOID)v1);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x14006abd0  mov     [rsp+arg_8], rbx
0x14006abd5  mov     [rsp+arg_10], rsi
0x14006abda  push    rdi
0x14006abdb  sub     rsp, 30h
0x14006abdf  mov     ecx, 440h; dwBytes
0x14006abe4  mov     [rsp+38h+ThreadId], 0
0x14006abec  call    DllAllocSplMem
0x14006abf1  mov     rbx, rax
0x14006abf4  test    rax, rax
0x14006abf7  jz      loc_14006ACE8
0x14006abfd  mov     ecx, 2001Fh
0x14006ac02  xor     edi, edi
0x14006ac04  call    SplGetClientUserHandle
0x14006ac09  lea     rsi, [rbx+8]
0x14006ac0d  mov     [rsi], rax
0x14006ac10  test    rax, rax
0x14006ac13  jz      loc_14006ACD4
0x14006ac19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14006ac20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14006ac25  test    al, al
0x14006ac27  jz      short loc_14006AC43
0x14006ac29  call    cs:__imp_GetCurrentThread
0x14006ac2f  mov     r8, rbx; TokenHandle
0x14006ac32  lea     edx, [rdi+0Eh]; DesiredAccess
0x14006ac35  mov     rcx, rax; ThreadHandle
0x14006ac38  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14006ac3d  test    eax, eax
0x14006ac3f  jz      short loc_14006AC7E
0x14006ac41  jmp     short loc_14006AC62
0x14006ac43  call    cs:__imp_GetCurrentThread
0x14006ac49  mov     edx, 0Eh; DesiredAccess
0x14006ac4e  mov     r9, rbx; TokenHandle
0x14006ac51  mov     rcx, rax; ThreadHandle
0x14006ac54  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x14006ac58  call    cs:__imp_OpenThreadToken
0x14006ac5e  test    eax, eax
0x14006ac60  jnz     short loc_14006AC7E
0x14006ac62  mov     rcx, rsi; struct INIT_REG_USER *
0x14006ac65  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x14006ac6a  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006ac71  mov     r8, rbx; lpMem
0x14006ac74  xor     edx, edx; dwFlags
0x14006ac76  call    cs:__imp_HeapFree
0x14006ac7c  xor     ebx, ebx
0x14006ac7e  test    rbx, rbx
0x14006ac81  jz      short loc_14006ACE6
0x14006ac83  cmp     cs:?Initialized@@3HA, edi; int Initialized
0x14006ac89  jnz     short loc_14006ACF8
0x14006ac8b  lea     rax, [rsp+38h+ThreadId]
0x14006ac90  mov     r9, rbx; lpParameter
0x14006ac93  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14006ac98  lea     r8, ?SpoolerUserInit@@YAXPEAUUSER_INFO@@@Z; lpStartAddress
0x14006ac9f  xor     edx, edx; dwStackSize
0x14006aca1  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x14006aca5  xor     ecx, ecx; lpThreadAttributes
0x14006aca7  call    cs:__imp_CreateThread
0x14006acad  test    rax, rax
0x14006acb0  jz      short loc_14006ACC2
0x14006acb2  mov     rcx, rax; hObject
0x14006acb5  call    cs:__imp_CloseHandle
0x14006acbb  mov     edi, 1
0x14006acc0  jmp     short loc_14006ACE6
0x14006acc2  mov     rcx, [rbx]; hObject
0x14006acc5  call    cs:__imp_CloseHandle
0x14006accb  lea     rcx, [rbx+8]; struct INIT_REG_USER *
0x14006accf  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x14006acd4  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006acdb  mov     r8, rbx; lpMem
0x14006acde  xor     edx, edx; dwFlags
0x14006ace0  call    cs:__imp_HeapFree
0x14006ace6  mov     eax, edi
0x14006ace8  mov     rbx, [rsp+38h+arg_8]
0x14006aced  mov     rsi, [rsp+38h+arg_10]
0x14006acf2  add     rsp, 30h
0x14006acf6  pop     rdi
0x14006acf7  retn
0x14006acf8  mov     rcx, rbx; Parameter
0x14006acfb  call    ?SpoolerUserInit@@YAXPEAUUSER_INFO@@@Z; SpoolerUserInit(USER_INFO *)
0x14006ad00  jmp     short loc_14006ACBB
```
