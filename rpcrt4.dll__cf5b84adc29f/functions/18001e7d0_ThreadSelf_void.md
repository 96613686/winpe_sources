# ThreadSelf(void)

- ea: `0x18001e7d0`
- end: `0x18001ee07`
- name: `?ThreadSelf@@YAPEAVTHREAD@@XZ`
- size: `1591`
- prototype: `struct THREAD *(void)`
- caller_count: `89`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001050`
- `0x180001cc0`
- `0x180002130`
- `0x180002f84`
- `0x180004f40`
- `0x180005510`
- `0x1800062f8`
- `0x180006550`
- `0x180007820`
- `0x180008190`
- `0x180009b90`
- `0x180009eb0`
- `0x18000b1d0`
- `0x18000b760`
- `0x18000c110`
- `0x18000cc28`
- `0x18001c6e0`
- `0x18001cf10`
- `0x18001cfb0`
- `0x18001d11c`
- `0x18001d150`
- `0x18001d170`
- `0x18001dbe0`
- `0x18001df70`
- `0x18001dfa0`
- `0x18001e3e0`
- `0x18001ee10`
- `0x18001f910`
- `0x18001f9e0`
- `0x18001fc50`
- `0x18001fca0`
- `0x18001fcd0`
- `0x180023b80`
- `0x180028f44`
- `0x180029de0`
- `0x180029ea0`
- `0x18002e4f0`
- `0x180034230`
- `0x1800465b0`
- `0x180059320`
- `0x180059610`
- `0x180068338`
- `0x180074de0`
- `0x180075750`
- `0x180079650`
- `0x1800799e0`
- `0x18007d010`
- `0x18007ea80`
- `0x1800823d0`
- `0x180082e00`

## callees

- `0x18001e6d0`
- `0x18001e7d0`
- `0x180022e80`
- `0x180022fb8`
- `0x180026df0`
- `0x18009bb8c`
- `0x1800b675c`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001ea57`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ebfa`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ea57`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ebfa`
- `ntdll!RtlEnterCriticalSection` at `0x18001e97d`
- `ntdll!RtlEnterCriticalSection` at `0x18001ebb2`
- `ntdll!RtlEnterCriticalSection` at `0x18001e97d`
- `ntdll!RtlEnterCriticalSection` at `0x18001ebb2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001eab4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001eab4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eda0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eda0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eb82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ec4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eb82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ec4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ece1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ece1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ea77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ea77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ea86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ea86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e8cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e8cb`

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
  __int64 v12; // r8
  __int64 v13; // r9
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // rax
  void *v16; // rdx
  void *v17; // rcx
  _QWORD *v18; // rcx
  void *v19; // rbx
  _QWORD *v20; // rbx
  OsfCCallSequence *v21; // rcx
  struct _LIST_ENTRY *v22; // rcx
  struct _LIST_ENTRY **v23; // rax
  struct _RTL_CRITICAL_SECTION *v24; // rcx
  void *v25; // rcx
  _QWORD *v26; // rbx
  _QWORD *v27; // rcx
  LPVOID v28; // rax
  int v29; // r8d
  unsigned int i; // ecx
  _QWORD *v31; // rax
  _QWORD *v32; // r8
  _QWORD *v33; // rcx
  BOOL bInheritHandle; // [rsp+28h] [rbp-81h]
  DWORD dwOptions; // [rsp+30h] [rbp-79h]
  char v36; // [rsp+40h] [rbp-69h] BYREF
  char v37; // [rsp+48h] [rbp-61h] BYREF
  LPVOID v38; // [rsp+50h] [rbp-59h] BYREF
  HANDLE v39; // [rsp+58h] [rbp-51h] BYREF
  __int64 v40; // [rsp+60h] [rbp-49h] BYREF
  char v41[16]; // [rsp+70h] [rbp-39h] BYREF
  char *v42; // [rsp+80h] [rbp-29h]
  __int64 v43; // [rsp+88h] [rbp-21h]
  char *v44; // [rsp+90h] [rbp-19h]
  __int64 v45; // [rsp+98h] [rbp-11h]
  LPVOID *v46; // [rsp+A0h] [rbp-9h]
  __int64 v47; // [rsp+A8h] [rbp-1h]
  HANDLE *v48; // [rsp+B0h] [rbp+7h]
  __int64 v49; // [rsp+B8h] [rbp+Fh]
  __int64 *v50; // [rsp+C0h] [rbp+17h]
  __int64 v51; // [rsp+C8h] [rbp+1Fh]

  ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
  if ( !ReservedForNtRpc )
  {
    if ( LsaAlloc )
      v28 = LsaAlloc(0xE8u);
    else
      v28 = HeapAlloc(hRpcHeap, 0, 0xE8u);
    v2 = (unsigned __int64)v28;
    if ( dword_1800FE624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 72 )
          goto LABEL_6;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v39 = hRpcHeap;
        v40 = 232;
        v42 = &v36;
        v38 = v28;
        v44 = &v37;
        v46 = &v38;
        v48 = &v39;
        v50 = &v40;
        v37 = 67;
        v36 = 72;
        v43 = 1;
        v45 = 1;
        v47 = 8;
        v49 = 8;
        v51 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v29,
          6,
          (__int64)v41);
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
    v16 = *(void **)(v2 + 64);
    if ( v16 )
      CellHeap::FreeCell(v11, v16, (int *)(v2 + 56));
    if ( gfRPCVerifierEnabled && *((_DWORD *)pRpcVerifierSettings + 24) && *(_QWORD *)(v2 + 8) )
      (*((void (**)(void))pRpcVerifierSettings + 26))();
    v17 = *(void **)(v2 + 8);
    if ( v17 )
    {
      CloseHandle(v17);
      *(_QWORD *)(v2 + 8) = 3131947693LL;
    }
    v18 = *(_QWORD **)(v2 + 80);
    if ( v18 )
    {
      do
      {
        v26 = (_QWORD *)*v18;
        FreeEEInfoRecord(v18);
        v18 = v26;
      }
      while ( v26 );
      *(_QWORD *)(v2 + 80) = 0;
    }
    v19 = *(void **)(v2 + 136);
    if ( v19 )
    {
      LogEvent(0x48u, 0x44u, *(void **)(v2 + 136), hRpcHeap, 0, bInheritHandle, dwOptions);
      if ( LsaFree )
        LsaFree(v19);
      else
        HeapFree(hRpcHeap, 0, v19);
    }
    v20 = (_QWORD *)*v4;
    while ( v20 != v4 )
    {
      v27 = (_QWORD *)v20[1];
      if ( (_QWORD *)*v27 != v20 || (v31 = (_QWORD *)*v20, *(_QWORD **)(*v20 + 8LL) != v20) )
      {
        RpcpReportFatalError(21, v20, v12, v13);
        __debugbreak();
      }
      v32 = v20;
      if ( v31 )
      {
        *v27 = v31;
        v31[1] = v27;
      }
      v33 = v20 - 8;
      v20[1] = 0;
      v20 = v31;
      *v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v33 + 32LL))(v33);
    }
    v21 = *(OsfCCallSequence **)(v2 + 152);
    if ( v21 )
      OsfCCallSequence::ThreadFreed(v21);
    RtlEnterCriticalSection(ThreadListMutex);
    v22 = v6->Flink;
    if ( v6->Flink )
    {
      v23 = *(struct _LIST_ENTRY ***)(v2 + 184);
      if ( v23 )
      {
        if ( v22->Blink != v6 || *v23 != v6 )
          goto LABEL_13;
        *v23 = v22;
        v22->Blink = (struct _LIST_ENTRY *)v23;
      }
    }
    v24 = ThreadListMutex;
    v6->Flink = 0;
    *(_QWORD *)(v2 + 184) = 0;
    RtlLeaveCriticalSection(v24);
    v25 = *(void **)(v2 + 24);
    if ( v25 )
      CloseHandle(v25);
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
0x18001e7d0  push    rbp
0x18001e7d2  lea     rbp, [rsp-57h]
0x18001e7d7  sub     rsp, 100h
0x18001e7de  mov     rax, cs:__security_cookie
0x18001e7e5  xor     rax, rsp
0x18001e7e8  mov     [rbp+57h+var_30], rax
0x18001e7ec  mov     rax, gs:30h
0x18001e7f5  mov     rax, [rax+1698h]
0x18001e7fc  test    rax, rax
0x18001e7ff  jz      loc_18001ECB6
0x18001e805  mov     rcx, gs:30h
0x18001e80e  mov     rdx, 0ABABABABDEDEDEDEh
0x18001e818  xor     rax, rdx
0x18001e81b  mov     rdx, [rcx+48h]
0x18001e81f  cmp     [rax+10h], rdx
0x18001e823  jz      short loc_18001E8A4
0x18001e825  mov     ecx, 1Eh
0x18001e82a  int     29h; Win8: RtlFailFast(ecx)
0x18001e82c  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001e833  jnz     loc_18001E9A8
0x18001e839  mov     [rsp+100h+arg_0], rbx
0x18001e841  mov     [rsp+100h+arg_8], rsi
0x18001e849  mov     [rsp+100h+var_8], r12
0x18001e851  mov     [rsp+100h+var_10], r13
0x18001e859  mov     [rsp+100h+var_20], r15
0x18001e861  test    rdi, rdi
0x18001e864  jnz     short loc_18001E8BA
0x18001e866  mov     rdi, r14
0x18001e869  mov     rbx, [rsp+100h+arg_0]
0x18001e871  mov     rax, rdi
0x18001e874  mov     rdi, [rsp+100h+arg_10]
0x18001e87c  mov     r13, [rsp+100h+var_10]
0x18001e884  mov     r12, [rsp+100h+var_8]
0x18001e88c  mov     rsi, [rsp+100h+arg_8]
0x18001e894  mov     r15, [rsp+100h+var_20]
0x18001e89c  mov     r14, [rsp+100h+var_18]
0x18001e8a4  mov     rcx, [rbp+57h+var_30]
0x18001e8a8  xor     rcx, rsp; StackCookie
0x18001e8ab  call    __security_check_cookie
0x18001e8b0  add     rsp, 100h
0x18001e8b7  pop     rbp
0x18001e8b8  retn
0x18001e8ba  xor     r9d, r9d; lpName
0x18001e8bd  mov     [rdi+18h], r14
0x18001e8c1  xor     r8d, r8d; bInitialState
0x18001e8c4  mov     edx, 1; bManualReset
0x18001e8c9  xor     ecx, ecx; lpEventAttributes
0x18001e8cb  call    cs:__imp_CreateEventW
0x18001e8d2  nop     dword ptr [rax+rax+00h]
0x18001e8d7  mov     [rdi+18h], rax
0x18001e8db  lea     r12, [rdi+0A0h]
0x18001e8e2  mov     [rdi+60h], r14d
0x18001e8e6  mov     r13d, r14d
0x18001e8e9  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x18001e8f0  lea     rsi, [rdi+0B0h]
0x18001e8f7  mov     [rdi+20h], r14
0x18001e8fb  test    rax, rax
0x18001e8fe  mov     [rdi+28h], r14
0x18001e902  mov     rbx, rax
0x18001e905  mov     [rdi+78h], r14d
0x18001e909  mov     r15d, 0Eh
0x18001e90f  mov     [rdi], r14d
0x18001e912  cmovz   r13d, r15d
0x18001e916  mov     [rdi+34h], r14d
0x18001e91a  mov     [rdi+40h], r14
0x18001e91e  mov     [rdi+50h], r14
0x18001e922  mov     [rdi+58h], r14
0x18001e926  mov     [rdi+68h], r14
0x18001e92a  mov     [rdi+70h], r14
0x18001e92e  mov     [rdi+80h], r14
0x18001e935  mov     [rdi+88h], r14
0x18001e93c  mov     [rdi+90h], r14d
0x18001e943  mov     [r12+8], r12
0x18001e948  mov     [r12], r12
0x18001e94c  mov     [rsi], r14
0x18001e94f  mov     [rdi+0B8h], r14
0x18001e956  mov     [rdi+48h], r14
0x18001e95a  mov     [rdi+98h], r14
0x18001e961  mov     [rdi+30h], r14b
0x18001e965  mov     rax, gs:30h
0x18001e96e  mov     rcx, [rax+48h]
0x18001e972  mov     [rdi+10h], rcx
0x18001e976  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001e97d  call    cs:__imp_RtlEnterCriticalSection
0x18001e984  nop     dword ptr [rax+rax+00h]
0x18001e989  mov     rax, cs:?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x18001e990  lea     rcx, ?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x18001e997  cmp     [rax+8], rcx
0x18001e99b  jz      loc_18001EA3E
0x18001e9a1  mov     ecx, 3
0x18001e9a6  int     29h; Win8: RtlFailFast(ecx)
0x18001e9a8  mov     rax, cs:?hRpcHeap@@3PEAXEA; void * hRpcHeap
0x18001e9af  lea     rdx, RPCLogEvent
0x18001e9b6  mov     [rbp+57h+var_A8], rax
0x18001e9ba  lea     rcx, RpcEtwGuid_Context
0x18001e9c1  lea     rax, [rbp+57h+var_C0]
0x18001e9c5  mov     [rbp+57h+var_A0], 0E8h
0x18001e9cd  mov     [rbp+57h+var_80], rax
0x18001e9d1  mov     r9d, 6
0x18001e9d7  lea     rax, [rbp+57h+var_B8]
0x18001e9db  mov     [rbp+57h+var_B0], rdi
0x18001e9df  mov     [rbp+57h+var_70], rax
0x18001e9e3  lea     rax, [rbp+57h+var_B0]
0x18001e9e7  mov     [rbp+57h+var_60], rax
0x18001e9eb  lea     rax, [rbp+57h+var_A8]
0x18001e9ef  mov     [rbp+57h+var_50], rax
0x18001e9f3  lea     rax, [rbp+57h+var_A0]
0x18001e9f7  mov     [rbp+57h+var_40], rax
0x18001e9fb  lea     rax, [rbp+57h+var_90]
0x18001e9ff  mov     qword ptr [rsp+100h+dwDesiredAccess], rax
0x18001ea04  mov     [rbp+57h+var_B8], 43h ; 'C'
0x18001ea08  mov     [rbp+57h+var_C0], 48h ; 'H'
0x18001ea0c  mov     [rbp+57h+var_78], 1
0x18001ea14  mov     [rbp+57h+var_68], 1
0x18001ea1c  mov     [rbp+57h+var_58], 8
0x18001ea24  mov     [rbp+57h+var_48], 8
0x18001ea2c  mov     [rbp+57h+var_38], 8
0x18001ea34  call    McGenEventWrite_EtwEventWriteTransfer
0x18001ea39  jmp     loc_18001E839
0x18001ea3e  mov     [rsi+8], rcx
0x18001ea42  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001ea49  mov     [rsi], rax
0x18001ea4c  mov     [rax+8], rsi
0x18001ea50  mov     cs:?ThreadListHead@@3U_LIST_ENTRY@@A, rsi; _LIST_ENTRY ThreadListHead
0x18001ea57  call    cs:__imp_RtlLeaveCriticalSection
0x18001ea5e  nop     dword ptr [rax+rax+00h]
0x18001ea63  mov     [rdi+0C0h], r14
0x18001ea6a  mov     [rdi+8], r14
0x18001ea6e  test    rbx, rbx
0x18001ea71  jz      loc_18001EDB5
0x18001ea77  call    cs:__imp_GetCurrentProcess
0x18001ea7e  nop     dword ptr [rax+rax+00h]
0x18001ea83  mov     rbx, rax
0x18001ea86  call    cs:__imp_GetCurrentThread
0x18001ea8d  nop     dword ptr [rax+rax+00h]
0x18001ea92  xor     r13d, r13d
0x18001ea95  mov     [rsp+100h+dwOptions], 2; int
0x18001ea9d  mov     rdx, rax; hSourceHandle
0x18001eaa0  mov     [rsp+100h+bInheritHandle], r13d; int
0x18001eaa5  lea     r9, [rdi+8]; lpTargetHandle
0x18001eaa9  mov     [rsp+100h+dwDesiredAccess], r13d; dwDesiredAccess
0x18001eaae  mov     r8, rbx; hTargetProcessHandle
0x18001eab1  mov     rcx, rbx; hSourceProcessHandle
0x18001eab4  call    cs:__imp_DuplicateHandle
0x18001eabb  nop     dword ptr [rax+rax+00h]
0x18001eac0  test    eax, eax
0x18001eac2  jz      short loc_18001EAF4
0x18001eac4  cmp     cs:?gfRPCVerifierEnabled@@3HA, r13d; int gfRPCVerifierEnabled
0x18001eacb  jnz     loc_18001ED73
0x18001ead1  mov     rax, gs:30h
0x18001eada  mov     rdx, 0ABABABABDEDEDEDEh
0x18001eae4  mov     rcx, rdi
0x18001eae7  mov     r15d, r13d
0x18001eaea  xor     rcx, rdx; this
0x18001eaed  mov     [rax+1698h], rcx
0x18001eaf4  test    r15d, r15d
0x18001eaf7  jz      loc_18001E869
0x18001eafd  mov     rdx, [rdi+40h]; void *
0x18001eb01  test    rdx, rdx
0x18001eb04  jnz     loc_18001EDC0
0x18001eb0a  cmp     cs:?gfRPCVerifierEnabled@@3HA, r14d; int gfRPCVerifierEnabled
0x18001eb11  jnz     loc_18001EDCE
0x18001eb17  mov     rcx, [rdi+8]; hObject
0x18001eb1b  test    rcx, rcx
0x18001eb1e  jz      short loc_18001EB35
0x18001eb20  call    cs:__imp_CloseHandle
0x18001eb27  nop     dword ptr [rax+rax+00h]
0x18001eb2c  mov     eax, 0BAADBAADh
0x18001eb31  mov     [rdi+8], rax
0x18001eb35  mov     rcx, [rdi+50h]; lpMem
0x18001eb39  test    rcx, rcx
0x18001eb3c  jnz     loc_18001EC60
0x18001eb42  mov     rbx, [rdi+88h]
0x18001eb49  test    rbx, rbx
0x18001eb4c  jz      short loc_18001EB8E
0x18001eb4e  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x18001eb55  mov     r8, rbx; void *
0x18001eb58  mov     dl, 44h ; 'D'; unsigned __int8
0x18001eb5a  mov     qword ptr [rsp+100h+dwDesiredAccess], r13; unsigned __int64
0x18001eb5f  mov     cl, 48h ; 'H'; unsigned __int8
0x18001eb61  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18001eb66  mov     rax, cs:?LsaFree@@3P6AXPEAX@ZEA; void (*LsaFree)(void *)
0x18001eb6d  test    rax, rax
0x18001eb70  jnz     loc_18001ECA9
0x18001eb76  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x18001eb7d  mov     r8, rbx; lpMem
0x18001eb80  xor     edx, edx; dwFlags
0x18001eb82  call    cs:__imp_HeapFree
0x18001eb89  nop     dword ptr [rax+rax+00h]
0x18001eb8e  mov     rbx, [r12]
0x18001eb92  cmp     rbx, r12
0x18001eb95  jnz     loc_18001EC80
0x18001eb9b  mov     rcx, [rdi+98h]; this
0x18001eba2  test    rcx, rcx
0x18001eba5  jnz     loc_18001EDFD
0x18001ebab  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001ebb2  call    cs:__imp_RtlEnterCriticalSection
0x18001ebb9  nop     dword ptr [rax+rax+00h]
0x18001ebbe  mov     rcx, [rsi]
0x18001ebc1  test    rcx, rcx
0x18001ebc4  jz      short loc_18001EBE9
0x18001ebc6  mov     rax, [rsi+8]
0x18001ebca  test    rax, rax
0x18001ebcd  jz      short loc_18001EBE9
0x18001ebcf  cmp     [rcx+8], rsi
0x18001ebd3  jnz     loc_18001E9A1
0x18001ebd9  cmp     [rax], rsi
0x18001ebdc  jnz     loc_18001E9A1
0x18001ebe2  mov     [rax], rcx
0x18001ebe5  mov     [rcx+8], rax
0x18001ebe9  mov     rcx, cs:?ThreadListMutex@@3PEAVMUTEX@@EA; CriticalSection
0x18001ebf0  mov     [rsi], r13
0x18001ebf3  mov     [rdi+0B8h], r13
0x18001ebfa  call    cs:__imp_RtlLeaveCriticalSection
0x18001ec01  nop     dword ptr [rax+rax+00h]
0x18001ec06  mov     rcx, [rdi+18h]; hObject
0x18001ec0a  test    rcx, rcx
0x18001ec0d  jz      short loc_18001EC1B
0x18001ec0f  call    cs:__imp_CloseHandle
0x18001ec16  nop     dword ptr [rax+rax+00h]
0x18001ec1b  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x18001ec22  mov     r8, rdi; void *
0x18001ec25  mov     dl, 44h ; 'D'; unsigned __int8
0x18001ec27  mov     qword ptr [rsp+100h+dwDesiredAccess], r13; unsigned __int64
0x18001ec2c  mov     cl, 48h ; 'H'; unsigned __int8
0x18001ec2e  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18001ec33  mov     rax, cs:?LsaFree@@3P6AXPEAX@ZEA; void (*LsaFree)(void *)
0x18001ec3a  test    rax, rax
0x18001ec3d  jnz     short loc_18001EC9F
0x18001ec3f  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x18001ec46  mov     r8, rdi; lpMem
0x18001ec49  xor     edx, edx; dwFlags
0x18001ec4b  call    cs:__imp_HeapFree
0x18001ec52  nop     dword ptr [rax+rax+00h]
0x18001ec57  mov     rdi, r13
0x18001ec5a  jmp     loc_18001E869
0x18001ec60  mov     rbx, [rcx]
0x18001ec63  call    FreeEEInfoRecord
0x18001ec68  mov     rcx, rbx
0x18001ec6b  test    rbx, rbx
0x18001ec6e  jnz     short loc_18001EC60
0x18001ec70  mov     [rdi+50h], r13
0x18001ec74  jmp     loc_18001EB42
0x18001ec80  mov     rcx, [rbx+8]
0x18001ec84  lea     rdx, [rbx+8]
0x18001ec88  cmp     [rcx], rbx
0x18001ec8b  jz      loc_18001ED30
0x18001ec91  mov     rdx, rbx
0x18001ec94  mov     ecx, 15h
0x18001ec99  call    RpcpReportFatalError
0x18001ec9e  int     3; Trap to Debugger
0x18001ec9f  mov     rcx, rdi
0x18001eca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eca7  jmp     short loc_18001EC57
0x18001eca9  mov     rcx, rbx
0x18001ecac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecb1  jmp     loc_18001EB8E
0x18001ecb6  mov     rax, cs:?LsaAlloc@@3P6APEAX_K@ZEA; void * (*LsaAlloc)(unsigned __int64)
0x18001ecbd  mov     [rsp+100h+arg_10], rdi
0x18001ecc5  mov     [rsp+100h+var_18], r14
0x18001eccd  test    rax, rax
0x18001ecd0  jnz     short loc_18001ED24
0x18001ecd2  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x18001ecd9  xor     edx, edx; dwFlags
0x18001ecdb  mov     r8d, 0E8h; dwBytes
0x18001ece1  call    cs:__imp_HeapAlloc
0x18001ece8  nop     dword ptr [rax+rax+00h]
0x18001eced  xor     r14d, r14d
0x18001ecf0  mov     rdi, rax
0x18001ecf3  cmp     cs:dword_1800FE624, r14d
0x18001ecfa  jz      loc_18001E839
0x18001ed00  mov     ecx, r14d
0x18001ed03  lea     rdx, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001ed0a  cmp     ecx, 4
0x18001ed0d  jnb     loc_18001E82C
0x18001ed13  movsxd  rax, ecx
0x18001ed16  cmp     byte ptr [rax+rdx], 48h ; 'H'
0x18001ed1a  jz      loc_18001E839
0x18001ed20  inc     ecx
0x18001ed22  jmp     short loc_18001ED0A
0x18001ed24  mov     ecx, 0E8h
0x18001ed29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed2e  jmp     short loc_18001ECED
0x18001ed30  mov     rax, [rbx]
0x18001ed33  cmp     [rax+8], rbx
0x18001ed37  jnz     loc_18001EC91
0x18001ed3d  mov     r8, rbx
0x18001ed40  test    rax, rax
0x18001ed43  jz      short loc_18001ED4C
0x18001ed45  mov     [rcx], rax
0x18001ed48  mov     [rax+8], rcx
0x18001ed4c  lea     rcx, [rbx-40h]
0x18001ed50  mov     [rdx], r13
0x18001ed53  mov     rbx, rax
0x18001ed56  mov     [r8], r13
0x18001ed59  mov     rax, [rcx]
0x18001ed5c  mov     rax, [rax+20h]
0x18001ed60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed65  cmp     rbx, r12
0x18001ed68  jz      loc_18001EB9B
  ... truncated ...
```
