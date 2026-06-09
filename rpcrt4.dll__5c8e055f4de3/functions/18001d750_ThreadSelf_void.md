# ThreadSelf(void)

- ea: `0x18001d750`
- end: `0x18001dd2b`
- name: `?ThreadSelf@@YAPEAVTHREAD@@XZ`
- size: `1499`
- prototype: `struct THREAD *(void)`
- caller_count: `90`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001050`
- `0x180001c90`
- `0x180002100`
- `0x180002f34`
- `0x180014020`
- `0x180015de0`
- `0x1800160d0`
- `0x18001b6c0`
- `0x18001bee0`
- `0x18001bf80`
- `0x18001c0e4`
- `0x18001c118`
- `0x18001c140`
- `0x18001cb80`
- `0x18001cf10`
- `0x18001cf40`
- `0x18001d380`
- `0x18001dd40`
- `0x18001e860`
- `0x18001e930`
- `0x18001eba0`
- `0x18001ebf0`
- `0x18001ec20`
- `0x1800229b0`
- `0x1800252a0`
- `0x180027d50`
- `0x180028ba0`
- `0x180028c60`
- `0x18002d1c0`
- `0x180032d50`
- `0x180046de0`
- `0x180046ecc`
- `0x1800634b8`
- `0x180064c90`
- `0x180065260`
- `0x180066038`
- `0x180066290`
- `0x1800674d0`
- `0x180067e00`
- `0x180069920`
- `0x180069c10`
- `0x18006af00`
- `0x18006b420`
- `0x18006bd90`
- `0x18006c1cc`
- `0x18006c980`
- `0x18006d1e4`
- `0x18006e090`
- `0x18006e120`
- `0x180075290`

## callees

- `0x18001d65c`
- `0x18001d750`
- `0x180021ce0`
- `0x180021e18`
- `0x180025c00`
- `0x1800981b8`
- `0x1800b28d4`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001d9ca`
- `ntdll!RtlLeaveCriticalSection` at `0x18001db43`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d9ca`
- `ntdll!RtlLeaveCriticalSection` at `0x18001db43`
- `ntdll!RtlEnterCriticalSection` at `0x18001d8f6`
- `ntdll!RtlEnterCriticalSection` at `0x18001db01`
- `ntdll!RtlEnterCriticalSection` at `0x18001d8f6`
- `ntdll!RtlEnterCriticalSection` at `0x18001db01`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001da15`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001da15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dcca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001db88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001db88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d9ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d9ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d84a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d84a`

## pseudocode

```c
struct THREAD *ThreadSelf(void)
{
  unsigned __int64 ReservedForNtRpc; // rax
  struct THREAD *result; // rax
  unsigned __int64 v2; // rdi
  HANDLE EventW; // rax
  _QWORD *v4; // r12
  int v5; // r13d
  struct _LIST_ENTRY *v6; // rsi
  HANDLE v7; // rbx
  int v8; // r15d
  struct _LIST_ENTRY *Flink; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  CellHeap *v11; // rcx
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // rax
  void *v14; // rdx
  void *v15; // rcx
  _QWORD *v16; // rcx
  void *v17; // rbx
  _QWORD *v18; // rbx
  OsfCCallSequence *v19; // rcx
  struct _LIST_ENTRY *v20; // rcx
  struct _LIST_ENTRY **v21; // rax
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  void *v23; // rcx
  _QWORD *v24; // rbx
  _QWORD *v25; // rcx
  LPVOID v26; // rax
  int v27; // r8d
  unsigned int i; // ecx
  _QWORD *v29; // rax
  _QWORD *v30; // r8
  _QWORD *v31; // rcx
  BOOL bInheritHandle; // [rsp+28h] [rbp-81h]
  DWORD dwOptions; // [rsp+30h] [rbp-79h]
  char v34; // [rsp+40h] [rbp-69h] BYREF
  char v35; // [rsp+48h] [rbp-61h] BYREF
  LPVOID v36; // [rsp+50h] [rbp-59h] BYREF
  HANDLE v37; // [rsp+58h] [rbp-51h] BYREF
  __int64 v38; // [rsp+60h] [rbp-49h] BYREF
  char v39[16]; // [rsp+70h] [rbp-39h] BYREF
  char *v40; // [rsp+80h] [rbp-29h]
  __int64 v41; // [rsp+88h] [rbp-21h]
  char *v42; // [rsp+90h] [rbp-19h]
  __int64 v43; // [rsp+98h] [rbp-11h]
  LPVOID *v44; // [rsp+A0h] [rbp-9h]
  __int64 v45; // [rsp+A8h] [rbp-1h]
  HANDLE *v46; // [rsp+B0h] [rbp+7h]
  __int64 v47; // [rsp+B8h] [rbp+Fh]
  __int64 *v48; // [rsp+C0h] [rbp+17h]
  __int64 v49; // [rsp+C8h] [rbp+1Fh]

  ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
  if ( !ReservedForNtRpc )
  {
    if ( LsaAlloc )
      v26 = LsaAlloc(0xE8u);
    else
      v26 = HeapAlloc(hRpcHeap, 0, 0xE8u);
    v2 = (unsigned __int64)v26;
    if ( dword_1800F9624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 72 )
          goto LABEL_6;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v37 = hRpcHeap;
        v38 = 232;
        v40 = &v34;
        v36 = v26;
        v42 = &v35;
        v44 = &v36;
        v46 = &v37;
        v48 = &v38;
        v35 = 67;
        v34 = 72;
        v41 = 1;
        v43 = 1;
        v45 = 8;
        v47 = 8;
        v49 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v27,
          6,
          (__int64)v39);
      }
    }
LABEL_6:
    if ( !v2 )
      return 0;
    *(_QWORD *)(v2 + 24) = 0;
    EventW = CreateEventW(0, 1, 0, 0);
    *(_QWORD *)(v2 + 24) = EventW;
    v4 = (_QWORD *)(v2 + 160);
    *(_DWORD *)(v2 + 96) = 0;
    v5 = 0;
    *(_DWORD *)(v2 + 4) = -1;
    v6 = (struct _LIST_ENTRY *)(v2 + 176);
    *(_QWORD *)(v2 + 32) = 0;
    *(_QWORD *)(v2 + 40) = 0;
    v7 = EventW;
    *(_DWORD *)(v2 + 120) = 0;
    v8 = 14;
    *(_DWORD *)v2 = 0;
    if ( !EventW )
      v5 = 14;
    *(_DWORD *)(v2 + 52) = 0;
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 80) = 0;
    *(_QWORD *)(v2 + 88) = 0;
    *(_QWORD *)(v2 + 104) = 0;
    *(_QWORD *)(v2 + 112) = 0;
    *(_QWORD *)(v2 + 128) = 0;
    *(_QWORD *)(v2 + 136) = 0;
    *(_DWORD *)(v2 + 144) = 0;
    *(_QWORD *)(v2 + 168) = v2 + 160;
    *v4 = v4;
    v6->Flink = 0;
    *(_QWORD *)(v2 + 184) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    *(_QWORD *)(v2 + 152) = 0;
    *(_BYTE *)(v2 + 48) = 0;
    *(_QWORD *)(v2 + 16) = NtCurrentTeb()->ClientId.UniqueThread;
    RtlEnterCriticalSection(ThreadListMutex);
    Flink = ThreadListHead.Flink;
    if ( ThreadListHead.Flink->Blink != &ThreadListHead )
LABEL_13:
      __fastfail(3u);
    *(_QWORD *)(v2 + 184) = &ThreadListHead;
    v10 = ThreadListMutex;
    v6->Flink = Flink;
    Flink->Blink = v6;
    ThreadListHead.Flink = (struct _LIST_ENTRY *)(v2 + 176);
    RtlLeaveCriticalSection(v10);
    *(_QWORD *)(v2 + 192) = 0;
    *(_QWORD *)(v2 + 8) = 0;
    if ( v7 )
    {
      CurrentProcess = GetCurrentProcess();
      CurrentThread = GetCurrentThread();
      if ( DuplicateHandle(CurrentProcess, CurrentThread, CurrentProcess, (LPHANDLE)(v2 + 8), 0, 0, 2u) )
      {
        if ( gfRPCVerifierEnabled
          && *((_DWORD *)pRpcVerifierSettings + 24)
          && !(*((unsigned int (__fastcall **)(_QWORD))pRpcVerifierSettings + 25))(*(_QWORD *)(v2 + 8)) )
        {
          CloseHandle(*(HANDLE *)(v2 + 8));
          *(_QWORD *)(v2 + 8) = 0;
        }
        else
        {
          v8 = 0;
          v11 = (CellHeap *)(v2 ^ 0xABABABABDEDEDEDEuLL);
          NtCurrentTeb()->ReservedForNtRpc = (PVOID)(v2 ^ 0xABABABABDEDEDEDEuLL);
        }
      }
    }
    else
    {
      v8 = v5;
    }
    if ( !v8 )
      return (struct THREAD *)v2;
    v14 = *(void **)(v2 + 64);
    if ( v14 )
      CellHeap::FreeCell(v11, v14, (int *)(v2 + 56));
    if ( gfRPCVerifierEnabled && *((_DWORD *)pRpcVerifierSettings + 24) && *(_QWORD *)(v2 + 8) )
      (*((void (**)(void))pRpcVerifierSettings + 26))();
    v15 = *(void **)(v2 + 8);
    if ( v15 )
    {
      CloseHandle(v15);
      *(_QWORD *)(v2 + 8) = 3131947693LL;
    }
    v16 = *(_QWORD **)(v2 + 80);
    if ( v16 )
    {
      do
      {
        v24 = (_QWORD *)*v16;
        FreeEEInfoRecord(v16);
        v16 = v24;
      }
      while ( v24 );
      *(_QWORD *)(v2 + 80) = 0;
    }
    v17 = *(void **)(v2 + 136);
    if ( v17 )
    {
      LogEvent(0x48u, 0x44u, *(void **)(v2 + 136), hRpcHeap, 0, bInheritHandle, dwOptions);
      if ( LsaFree )
        LsaFree(v17);
      else
        HeapFree(hRpcHeap, 0, v17);
    }
    v18 = (_QWORD *)*v4;
    while ( v18 != v4 )
    {
      v25 = (_QWORD *)v18[1];
      if ( (_QWORD *)*v25 != v18 || (v29 = (_QWORD *)*v18, *(_QWORD **)(*v18 + 8LL) != v18) )
      {
        RpcpReportFatalError(21, v18);
        __debugbreak();
      }
      v30 = v18;
      if ( v29 )
      {
        *v25 = v29;
        v29[1] = v25;
      }
      v31 = v18 - 8;
      v18[1] = 0;
      v18 = v29;
      *v30 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v31 + 32LL))(v31);
    }
    v19 = *(OsfCCallSequence **)(v2 + 152);
    if ( v19 )
      OsfCCallSequence::ThreadFreed(v19);
    RtlEnterCriticalSection(ThreadListMutex);
    v20 = v6->Flink;
    if ( v6->Flink )
    {
      v21 = *(struct _LIST_ENTRY ***)(v2 + 184);
      if ( v21 )
      {
        if ( v20->Blink != v6 || *v21 != v6 )
          goto LABEL_13;
        *v21 = v20;
        v20->Blink = (struct _LIST_ENTRY *)v21;
      }
    }
    v22 = ThreadListMutex;
    v6->Flink = 0;
    *(_QWORD *)(v2 + 184) = 0;
    RtlLeaveCriticalSection(v22);
    v23 = *(void **)(v2 + 24);
    if ( v23 )
      CloseHandle(v23);
    LogEvent(0x48u, 0x44u, (void *)v2, hRpcHeap, 0, bInheritHandle, dwOptions);
    if ( LsaFree )
      LsaFree((void *)v2);
    else
      HeapFree(hRpcHeap, 0, (LPVOID)v2);
    return 0;
  }
  result = (struct THREAD *)(ReservedForNtRpc ^ 0xABABABABDEDEDEDEuLL);
  if ( (HANDLE)*((_QWORD *)result + 2) != NtCurrentTeb()->ClientId.UniqueThread )
    __fastfail(0x1Eu);
  return result;
}

```

## disassembly

```asm
0x18001d750  push    rbp
0x18001d752  lea     rbp, [rsp-57h]
0x18001d757  sub     rsp, 100h
0x18001d75e  mov     rax, cs:__security_cookie
0x18001d765  xor     rax, rsp
0x18001d768  mov     [rbp+57h+var_30], rax
0x18001d76c  mov     rax, gs:30h
0x18001d775  mov     rax, [rax+1698h]
0x18001d77c  test    rax, rax
0x18001d77f  jz      loc_18001DBE6
0x18001d785  mov     rcx, gs:30h
0x18001d78e  mov     rdx, 0ABABABABDEDEDEDEh
0x18001d798  xor     rax, rdx
0x18001d79b  mov     rdx, [rcx+48h]
0x18001d79f  cmp     [rax+10h], rdx
0x18001d7a3  jz      short loc_18001D824
0x18001d7a5  mov     ecx, 1Eh
0x18001d7aa  int     29h; Win8: RtlFailFast(ecx)
0x18001d7ac  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001d7b3  jnz     loc_18001D91B
0x18001d7b9  mov     [rsp+100h+arg_0], rbx
0x18001d7c1  mov     [rsp+100h+arg_8], rsi
0x18001d7c9  mov     [rsp+100h+var_8], r12
0x18001d7d1  mov     [rsp+100h+var_10], r13
0x18001d7d9  mov     [rsp+100h+var_20], r15
0x18001d7e1  test    rdi, rdi
0x18001d7e4  jnz     short loc_18001D839
0x18001d7e6  mov     rdi, r14
0x18001d7e9  mov     rbx, [rsp+100h+arg_0]
0x18001d7f1  mov     rax, rdi
0x18001d7f4  mov     rdi, [rsp+100h+arg_10]
0x18001d7fc  mov     r13, [rsp+100h+var_10]
0x18001d804  mov     r12, [rsp+100h+var_8]
0x18001d80c  mov     rsi, [rsp+100h+arg_8]
0x18001d814  mov     r15, [rsp+100h+var_20]
0x18001d81c  mov     r14, [rsp+100h+var_18]
0x18001d824  mov     rcx, [rbp+57h+var_30]
0x18001d828  xor     rcx, rsp; StackCookie
0x18001d82b  call    __security_check_cookie
0x18001d830  add     rsp, 100h
0x18001d837  pop     rbp
0x18001d838  retn
0x18001d839  xor     r9d, r9d; lpName
0x18001d83c  mov     [rdi+18h], r14
0x18001d840  xor     r8d, r8d; bInitialState
0x18001d843  mov     edx, 1; bManualReset
0x18001d848  xor     ecx, ecx; lpEventAttributes
0x18001d84a  call    cs:__imp_CreateEventW
0x18001d850  mov     [rdi+18h], rax
0x18001d854  lea     r12, [rdi+0A0h]
0x18001d85b  mov     [rdi+60h], r14d
0x18001d85f  mov     r13d, r14d
0x18001d862  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x18001d869  lea     rsi, [rdi+0B0h]
0x18001d870  mov     [rdi+20h], r14
0x18001d874  test    rax, rax
0x18001d877  mov     [rdi+28h], r14
0x18001d87b  mov     rbx, rax
0x18001d87e  mov     [rdi+78h], r14d
0x18001d882  mov     r15d, 0Eh
0x18001d888  mov     [rdi], r14d
0x18001d88b  cmovz   r13d, r15d
0x18001d88f  mov     [rdi+34h], r14d
0x18001d893  mov     [rdi+40h], r14
0x18001d897  mov     [rdi+50h], r14
0x18001d89b  mov     [rdi+58h], r14
0x18001d89f  mov     [rdi+68h], r14
0x18001d8a3  mov     [rdi+70h], r14
0x18001d8a7  mov     [rdi+80h], r14
0x18001d8ae  mov     [rdi+88h], r14
0x18001d8b5  mov     [rdi+90h], r14d
0x18001d8bc  mov     [r12+8], r12
0x18001d8c1  mov     [r12], r12
0x18001d8c5  mov     [rsi], r14
0x18001d8c8  mov     [rdi+0B8h], r14
0x18001d8cf  mov     [rdi+48h], r14
0x18001d8d3  mov     [rdi+98h], r14
0x18001d8da  mov     [rdi+30h], r14b
0x18001d8de  mov     rax, gs:30h
0x18001d8e7  mov     rcx, [rax+48h]
0x18001d8eb  mov     [rdi+10h], rcx
0x18001d8ef  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001d8f6  call    cs:__imp_RtlEnterCriticalSection
0x18001d8fc  mov     rax, cs:?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x18001d903  lea     rcx, ?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x18001d90a  cmp     [rax+8], rcx
0x18001d90e  jz      loc_18001D9B1
0x18001d914  mov     ecx, 3
0x18001d919  int     29h; Win8: RtlFailFast(ecx)
0x18001d91b  mov     rax, cs:?hRpcHeap@@3PEAXEA; void * hRpcHeap
0x18001d922  lea     rdx, RPCLogEvent
0x18001d929  mov     [rbp+57h+var_A8], rax
0x18001d92d  lea     rcx, RpcEtwGuid_Context
0x18001d934  lea     rax, [rbp+57h+var_C0]
0x18001d938  mov     [rbp+57h+var_A0], 0E8h
0x18001d940  mov     [rbp+57h+var_80], rax
0x18001d944  mov     r9d, 6
0x18001d94a  lea     rax, [rbp+57h+var_B8]
0x18001d94e  mov     [rbp+57h+var_B0], rdi
0x18001d952  mov     [rbp+57h+var_70], rax
0x18001d956  lea     rax, [rbp+57h+var_B0]
0x18001d95a  mov     [rbp+57h+var_60], rax
0x18001d95e  lea     rax, [rbp+57h+var_A8]
0x18001d962  mov     [rbp+57h+var_50], rax
0x18001d966  lea     rax, [rbp+57h+var_A0]
0x18001d96a  mov     [rbp+57h+var_40], rax
0x18001d96e  lea     rax, [rbp+57h+var_90]
0x18001d972  mov     qword ptr [rsp+100h+dwDesiredAccess], rax
0x18001d977  mov     [rbp+57h+var_B8], 43h ; 'C'
0x18001d97b  mov     [rbp+57h+var_C0], 48h ; 'H'
0x18001d97f  mov     [rbp+57h+var_78], 1
0x18001d987  mov     [rbp+57h+var_68], 1
0x18001d98f  mov     [rbp+57h+var_58], 8
0x18001d997  mov     [rbp+57h+var_48], 8
0x18001d99f  mov     [rbp+57h+var_38], 8
0x18001d9a7  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d9ac  jmp     loc_18001D7B9
0x18001d9b1  mov     [rsi+8], rcx
0x18001d9b5  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001d9bc  mov     [rsi], rax
0x18001d9bf  mov     [rax+8], rsi
0x18001d9c3  mov     cs:?ThreadListHead@@3U_LIST_ENTRY@@A, rsi; _LIST_ENTRY ThreadListHead
0x18001d9ca  call    cs:__imp_RtlLeaveCriticalSection
0x18001d9d0  mov     [rdi+0C0h], r14
0x18001d9d7  mov     [rdi+8], r14
0x18001d9db  test    rbx, rbx
0x18001d9de  jz      loc_18001DCD9
0x18001d9e4  call    cs:__imp_GetCurrentProcess
0x18001d9ea  mov     rbx, rax
0x18001d9ed  call    cs:__imp_GetCurrentThread
0x18001d9f3  xor     r13d, r13d
0x18001d9f6  mov     [rsp+100h+dwOptions], 2; int
0x18001d9fe  mov     rdx, rax; hSourceHandle
0x18001da01  mov     [rsp+100h+bInheritHandle], r13d; int
0x18001da06  lea     r9, [rdi+8]; lpTargetHandle
0x18001da0a  mov     [rsp+100h+dwDesiredAccess], r13d; dwDesiredAccess
0x18001da0f  mov     r8, rbx; hTargetProcessHandle
0x18001da12  mov     rcx, rbx; hSourceProcessHandle
0x18001da15  call    cs:__imp_DuplicateHandle
0x18001da1b  test    eax, eax
0x18001da1d  jz      short loc_18001DA4F
0x18001da1f  cmp     cs:?gfRPCVerifierEnabled@@3HA, r13d; int gfRPCVerifierEnabled
0x18001da26  jnz     loc_18001DC9D
0x18001da2c  mov     rax, gs:30h
0x18001da35  mov     rdx, 0ABABABABDEDEDEDEh
0x18001da3f  mov     rcx, rdi
0x18001da42  mov     r15d, r13d
0x18001da45  xor     rcx, rdx; this
0x18001da48  mov     [rax+1698h], rcx
0x18001da4f  test    r15d, r15d
0x18001da52  jz      loc_18001D7E9
0x18001da58  mov     rdx, [rdi+40h]; void *
0x18001da5c  test    rdx, rdx
0x18001da5f  jnz     loc_18001DCE4
0x18001da65  cmp     cs:?gfRPCVerifierEnabled@@3HA, r14d; int gfRPCVerifierEnabled
0x18001da6c  jnz     loc_18001DCF2
0x18001da72  mov     rcx, [rdi+8]; hObject
0x18001da76  test    rcx, rcx
0x18001da79  jz      short loc_18001DA8A
0x18001da7b  call    cs:__imp_CloseHandle
0x18001da81  mov     eax, 0BAADBAADh
0x18001da86  mov     [rdi+8], rax
0x18001da8a  mov     rcx, [rdi+50h]; lpMem
0x18001da8e  test    rcx, rcx
0x18001da91  jnz     loc_18001DB96
0x18001da97  mov     rbx, [rdi+88h]
0x18001da9e  test    rbx, rbx
0x18001daa1  jz      short loc_18001DADD
0x18001daa3  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x18001daaa  mov     r8, rbx; void *
0x18001daad  mov     dl, 44h ; 'D'; unsigned __int8
0x18001daaf  mov     qword ptr [rsp+100h+dwDesiredAccess], r13; unsigned __int64
0x18001dab4  mov     cl, 48h ; 'H'; unsigned __int8
0x18001dab6  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18001dabb  mov     rax, cs:?LsaFree@@3P6AXPEAX@ZEA; void (*LsaFree)(void *)
0x18001dac2  test    rax, rax
0x18001dac5  jnz     loc_18001DBD9
0x18001dacb  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x18001dad2  mov     r8, rbx; lpMem
0x18001dad5  xor     edx, edx; dwFlags
0x18001dad7  call    cs:__imp_HeapFree
0x18001dadd  mov     rbx, [r12]
0x18001dae1  cmp     rbx, r12
0x18001dae4  jnz     loc_18001DBB0
0x18001daea  mov     rcx, [rdi+98h]; this
0x18001daf1  test    rcx, rcx
0x18001daf4  jnz     loc_18001DD21
0x18001dafa  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001db01  call    cs:__imp_RtlEnterCriticalSection
0x18001db07  mov     rcx, [rsi]
0x18001db0a  test    rcx, rcx
0x18001db0d  jz      short loc_18001DB32
0x18001db0f  mov     rax, [rsi+8]
0x18001db13  test    rax, rax
0x18001db16  jz      short loc_18001DB32
0x18001db18  cmp     [rcx+8], rsi
0x18001db1c  jnz     loc_18001D914
0x18001db22  cmp     [rax], rsi
0x18001db25  jnz     loc_18001D914
0x18001db2b  mov     [rax], rcx
0x18001db2e  mov     [rcx+8], rax
0x18001db32  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001db39  mov     [rsi], r13
0x18001db3c  mov     [rdi+0B8h], r13
0x18001db43  call    cs:__imp_RtlLeaveCriticalSection
0x18001db49  mov     rcx, [rdi+18h]; hObject
0x18001db4d  test    rcx, rcx
0x18001db50  jz      short loc_18001DB58
0x18001db52  call    cs:__imp_CloseHandle
0x18001db58  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x18001db5f  mov     r8, rdi; void *
0x18001db62  mov     dl, 44h ; 'D'; unsigned __int8
0x18001db64  mov     qword ptr [rsp+100h+dwDesiredAccess], r13; unsigned __int64
0x18001db69  mov     cl, 48h ; 'H'; unsigned __int8
0x18001db6b  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18001db70  mov     rax, cs:?LsaFree@@3P6AXPEAX@ZEA; void (*LsaFree)(void *)
0x18001db77  test    rax, rax
0x18001db7a  jnz     short loc_18001DBCF
0x18001db7c  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x18001db83  mov     r8, rdi; lpMem
0x18001db86  xor     edx, edx; dwFlags
0x18001db88  call    cs:__imp_HeapFree
0x18001db8e  mov     rdi, r13
0x18001db91  jmp     loc_18001D7E9
0x18001db96  mov     rbx, [rcx]
0x18001db99  call    FreeEEInfoRecord
0x18001db9e  mov     rcx, rbx
0x18001dba1  test    rbx, rbx
0x18001dba4  jnz     short loc_18001DB96
0x18001dba6  mov     [rdi+50h], r13
0x18001dbaa  jmp     loc_18001DA97
0x18001dbb0  mov     rcx, [rbx+8]
0x18001dbb4  lea     rdx, [rbx+8]
0x18001dbb8  cmp     [rcx], rbx
0x18001dbbb  jz      loc_18001DC5A
0x18001dbc1  mov     rdx, rbx
0x18001dbc4  mov     ecx, 15h
0x18001dbc9  call    RpcpReportFatalError
0x18001dbce  int     3; Trap to Debugger
0x18001dbcf  mov     rcx, rdi
0x18001dbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbd7  jmp     short loc_18001DB8E
0x18001dbd9  mov     rcx, rbx
0x18001dbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe1  jmp     loc_18001DADD
0x18001dbe6  mov     rax, cs:?LsaAlloc@@3P6APEAX_K@ZEA; void * (*LsaAlloc)(unsigned __int64)
0x18001dbed  mov     [rsp+100h+arg_10], rdi
0x18001dbf5  mov     [rsp+100h+var_18], r14
0x18001dbfd  test    rax, rax
0x18001dc00  jnz     short loc_18001DC4E
0x18001dc02  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x18001dc09  xor     edx, edx; dwFlags
0x18001dc0b  mov     r8d, 0E8h; dwBytes
0x18001dc11  call    cs:__imp_HeapAlloc
0x18001dc17  xor     r14d, r14d
0x18001dc1a  mov     rdi, rax
0x18001dc1d  cmp     cs:dword_1800F9624, r14d
0x18001dc24  jz      loc_18001D7B9
0x18001dc2a  mov     ecx, r14d
0x18001dc2d  lea     rdx, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001dc34  cmp     ecx, 4
0x18001dc37  jnb     loc_18001D7AC
0x18001dc3d  movsxd  rax, ecx
0x18001dc40  cmp     byte ptr [rax+rdx], 48h ; 'H'
0x18001dc44  jz      loc_18001D7B9
0x18001dc4a  inc     ecx
0x18001dc4c  jmp     short loc_18001DC34
0x18001dc4e  mov     ecx, 0E8h
0x18001dc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc58  jmp     short loc_18001DC17
0x18001dc5a  mov     rax, [rbx]
0x18001dc5d  cmp     [rax+8], rbx
0x18001dc61  jnz     loc_18001DBC1
0x18001dc67  mov     r8, rbx
0x18001dc6a  test    rax, rax
0x18001dc6d  jz      short loc_18001DC76
0x18001dc6f  mov     [rcx], rax
0x18001dc72  mov     [rax+8], rcx
0x18001dc76  lea     rcx, [rbx-40h]
0x18001dc7a  mov     [rdx], r13
0x18001dc7d  mov     rbx, rax
0x18001dc80  mov     [r8], r13
0x18001dc83  mov     rax, [rcx]
0x18001dc86  mov     rax, [rax+20h]
0x18001dc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc8f  cmp     rbx, r12
0x18001dc92  jz      loc_18001DAEA
0x18001dc98  jmp     loc_18001DBB0
0x18001dc9d  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x18001dca4  cmp     [rax+60h], r13d
0x18001dca8  jz      loc_18001DA2C
0x18001dcae  mov     rcx, [rdi+8]
0x18001dcb2  mov     rax, [rax+0C8h]
0x18001dcb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcbe  test    eax, eax
0x18001dcc0  jnz     loc_18001DA2C
0x18001dcc6  mov     rcx, [rdi+8]; hObject
0x18001dcca  call    cs:__imp_CloseHandle
0x18001dcd0  mov     [rdi+8], r13
0x18001dcd4  jmp     loc_18001DA4F
  ... truncated ...
```
