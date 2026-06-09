# SpoolerInit

- ea: `0x140071760`
- end: `0x1400718c7`
- name: `SpoolerInit`
- size: `359`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14006c574`

## callees

- `0x140004790`
- `0x140004800`
- `0x140016314`
- `0x140018a8c`
- `0x14005d4e0`
- `0x140071470`
- `0x140071760`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140071818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007189e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140071818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14007189e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400717f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400717f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400717b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400717d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400717b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400717d9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140071853`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140071853`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140071867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007187d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140071867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007187d`

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
0x140071760  mov     [rsp+arg_8], rbx
0x140071765  mov     [rsp+arg_10], rsi
0x14007176a  push    rdi
0x14007176b  sub     rsp, 30h
0x14007176f  mov     ecx, 440h; dwBytes
0x140071774  mov     [rsp+38h+ThreadId], 0
0x14007177c  call    DllAllocSplMem
0x140071781  mov     rbx, rax
0x140071784  test    rax, rax
0x140071787  jz      loc_1400718AC
0x14007178d  mov     ecx, 2001Fh
0x140071792  xor     edi, edi
0x140071794  call    SplGetClientUserHandle
0x140071799  lea     rsi, [rbx+8]
0x14007179d  mov     [rsi], rax
0x1400717a0  test    rax, rax
0x1400717a3  jz      loc_140071892
0x1400717a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1400717b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1400717b5  test    al, al
0x1400717b7  jz      short loc_1400717D9
0x1400717b9  call    cs:__imp_GetCurrentThread
0x1400717c0  nop     dword ptr [rax+rax+00h]
0x1400717c5  mov     r8, rbx; TokenHandle
0x1400717c8  lea     edx, [rdi+0Eh]; DesiredAccess
0x1400717cb  mov     rcx, rax; ThreadHandle
0x1400717ce  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x1400717d3  test    eax, eax
0x1400717d5  jz      short loc_140071826
0x1400717d7  jmp     short loc_140071804
0x1400717d9  call    cs:__imp_GetCurrentThread
0x1400717e0  nop     dword ptr [rax+rax+00h]
0x1400717e5  mov     edx, 0Eh; DesiredAccess
0x1400717ea  mov     r9, rbx; TokenHandle
0x1400717ed  mov     rcx, rax; ThreadHandle
0x1400717f0  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1400717f4  call    cs:__imp_OpenThreadToken
0x1400717fb  nop     dword ptr [rax+rax+00h]
0x140071800  test    eax, eax
0x140071802  jnz     short loc_140071826
0x140071804  mov     rcx, rsi; struct INIT_REG_USER *
0x140071807  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x14007180c  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140071813  mov     r8, rbx; lpMem
0x140071816  xor     edx, edx; dwFlags
0x140071818  call    cs:__imp_HeapFree
0x14007181f  nop     dword ptr [rax+rax+00h]
0x140071824  xor     ebx, ebx
0x140071826  test    rbx, rbx
0x140071829  jz      short loc_1400718AA
0x14007182b  cmp     cs:?Initialized@@3HA, edi; int Initialized
0x140071831  jnz     loc_1400718BD
0x140071837  lea     rax, [rsp+38h+ThreadId]
0x14007183c  mov     r9, rbx; lpParameter
0x14007183f  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140071844  lea     r8, ?SpoolerUserInit@@YAXPEAUUSER_INFO@@@Z; lpStartAddress
0x14007184b  xor     edx, edx; dwStackSize
0x14007184d  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x140071851  xor     ecx, ecx; lpThreadAttributes
0x140071853  call    cs:__imp_CreateThread
0x14007185a  nop     dword ptr [rax+rax+00h]
0x14007185f  test    rax, rax
0x140071862  jz      short loc_14007187A
0x140071864  mov     rcx, rax; hObject
0x140071867  call    cs:__imp_CloseHandle
0x14007186e  nop     dword ptr [rax+rax+00h]
0x140071873  mov     edi, 1
0x140071878  jmp     short loc_1400718AA
0x14007187a  mov     rcx, [rbx]; hObject
0x14007187d  call    cs:__imp_CloseHandle
0x140071884  nop     dword ptr [rax+rax+00h]
0x140071889  lea     rcx, [rbx+8]; struct INIT_REG_USER *
0x14007188d  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x140071892  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140071899  mov     r8, rbx; lpMem
0x14007189c  xor     edx, edx; dwFlags
0x14007189e  call    cs:__imp_HeapFree
0x1400718a5  nop     dword ptr [rax+rax+00h]
0x1400718aa  mov     eax, edi
0x1400718ac  mov     rbx, [rsp+38h+arg_8]
0x1400718b1  mov     rsi, [rsp+38h+arg_10]
0x1400718b6  add     rsp, 30h
0x1400718ba  pop     rdi
0x1400718bb  retn
0x1400718bd  mov     rcx, rbx; Parameter
0x1400718c0  call    ?SpoolerUserInit@@YAXPEAUUSER_INFO@@@Z; SpoolerUserInit(USER_INFO *)
0x1400718c5  jmp     short loc_140071873
```
