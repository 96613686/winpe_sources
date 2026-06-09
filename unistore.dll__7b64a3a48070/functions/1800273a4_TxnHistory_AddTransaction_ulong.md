# TxnHistory::AddTransaction(ulong *)

- ea: `0x1800273a4`
- end: `0x18002753a`
- name: `?AddTransaction@TxnHistory@@YAJPEAK@Z`
- size: `406`
- prototype: `__int64 __fastcall(TxnHistory *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800270ac`

## callees

- `0x1800068f0`
- `0x1800273a4`
- `0x180027db0`
- `0x1800289f4`
- `0x1800728bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800273df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800273df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002740c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002740c`

## string_xrefs

- `0x1800274f5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`

## pseudocode

```c
__int64 __fastcall TxnHistory::AddTransaction(TxnHistory *this, unsigned int *a2)
{
  __int64 v3; // rcx
  __int64 CallerClientId; // rax
  RundownProtectionList *v5; // rcx
  unsigned int CurrentProcessId; // eax
  ULONGLONG TickCount64; // rax
  unsigned int v8; // r11d
  unsigned int v9; // r9d
  __int64 v10; // r8
  __int64 v11; // rcx
  unsigned int v12; // r10d
  unsigned int v13; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int128 v17; // [rsp+30h] [rbp-30h]
  __int128 v18; // [rsp+40h] [rbp-20h]
  __int128 v19; // [rsp+50h] [rbp-10h]
  unsigned int v20; // [rsp+78h] [rbp+18h] BYREF
  __int64 v21; // [rsp+80h] [rbp+20h]

  EnterCriticalSection(&TxnHistory::g_txnHistoryLock);
  CallerClientId = GetCallerClientId(v3);
  v21 = CallerClientId;
  v20 = 0;
  if ( (unsigned int)CallerClientId <= 0xFFFFFFFD )
  {
    if ( !(unsigned int)RundownProtectionList::GetProcessIdFromRundownProtectionId(v5, CallerClientId, &v20) )
    {
      v13 = -2147483622;
      Log_UnistoreHREvent_0(
        2147483674LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
        1181);
      Log_UnistoreHREvent_22(2147483674LL, v15, v16, 71);
      goto LABEL_8;
    }
    CurrentProcessId = v20;
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
  }
  HIDWORD(v17) = CurrentProcessId;
  *(_QWORD *)&v18 = HIDWORD(v21);
  *(_QWORD *)&v17 = 0;
  DWORD2(v17) = 0;
  *(_QWORD *)&v19 = 0;
  TickCount64 = GetTickCount64();
  v8 = TxnHistory::g_nextTxnHistoryIndex;
  v9 = TxnHistory::g_txnId;
  LODWORD(v10) = TxnHistory::g_nextTxnHistoryIndex;
  *((_QWORD *)&v18 + 1) = TickCount64;
  DWORD2(v19) = 0;
  v11 = 6LL * TxnHistory::g_nextTxnHistoryIndex;
  HIDWORD(v19) = TxnHistory::g_txnId;
  v12 = 0;
  *(_OWORD *)(&TxnHistory::g_transactionHistoryArray + v11) = v17;
  *(_OWORD *)(&TxnHistory::g_transactionHistoryArray + v11 + 2) = v18;
  *(_OWORD *)(&TxnHistory::g_transactionHistoryArray + v11 + 4) = v19;
  do
  {
    v10 = ((int)v10 + 1) % 0x19u;
    TxnHistory::g_nextTxnHistoryIndex = v10;
    if ( *(&TxnHistory::g_transactionHistoryArray + 6 * v10 + 4) )
      break;
    if ( !*(&TxnHistory::g_transactionHistoryArray + 6 * v10 + 3) )
      break;
    ++v12;
  }
  while ( v12 < 0x19 );
  if ( (_DWORD)v10 == v8 )
    TxnHistory::g_nextTxnHistoryIndex = ((int)v10 + 1) % 0x19u;
  *(_DWORD *)this = v9;
  TxnHistory::g_txnId = v9 + 1;
  v13 = 0;
LABEL_8:
  LeaveCriticalSection(&TxnHistory::g_txnHistoryLock);
  return v13;
}

```

## disassembly

```asm
0x1800273a4  mov     [rsp-8+arg_0], rbx
0x1800273a9  mov     [rsp-8+arg_18], rsi
0x1800273ae  push    rbp
0x1800273af  mov     rbp, rsp
0x1800273b2  sub     rsp, 60h
0x1800273b6  mov     rbx, rcx
0x1800273b9  lea     rcx, ?g_txnHistoryLock@TxnHistory@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800273c0  call    cs:__imp_EnterCriticalSection
0x1800273c6  call    ?GetCallerClientId@@YA?AUCallerId@@XZ; GetCallerClientId(void)
0x1800273cb  mov     [rbp+arg_10], rax
0x1800273cf  mov     [rbp+arg_8], 0
0x1800273d6  cmp     eax, 0FFFFFFFDh
0x1800273d9  jbe     loc_1800274C2
0x1800273df  call    cs:__imp_GetCurrentProcessId
0x1800273e5  mov     dword ptr [rbp+var_30+0Ch], eax
0x1800273e8  mov     eax, dword ptr [rbp+arg_10+4]
0x1800273eb  mov     dword ptr [rbp+var_20], eax
0x1800273ee  mov     qword ptr [rbp+var_30], 0
0x1800273f6  mov     dword ptr [rbp+var_30+8], 0
0x1800273fd  mov     dword ptr [rbp+var_20+4], 0
0x180027404  mov     qword ptr [rbp+var_10], 0
0x18002740c  call    cs:__imp_GetTickCount64
0x180027412  mov     r11d, cs:?g_nextTxnHistoryIndex@TxnHistory@@3KA; ulong TxnHistory::g_nextTxnHistoryIndex
0x180027419  lea     rsi, ?g_transactionHistoryArray@TxnHistory@@3PAUTxnHistoryEntry@1@A; TxnHistory::TxnHistoryEntry near * TxnHistory::g_transactionHistoryArray
0x180027420  movups  xmm0, [rbp+var_30]
0x180027424  mov     r9d, cs:?g_txnId@TxnHistory@@3KA; ulong TxnHistory::g_txnId
0x18002742b  mov     r8d, r11d
0x18002742e  mov     qword ptr [rbp+var_20+8], rax
0x180027432  movups  xmm1, [rbp+var_20]
0x180027436  lea     rcx, [r11+r11*2]
0x18002743a  mov     dword ptr [rbp+var_10+8], 0
0x180027441  add     rcx, rcx
0x180027444  mov     dword ptr [rbp+var_10+0Ch], r9d
0x180027448  xor     r10d, r10d
0x18002744b  movups  xmmword ptr [rsi+rcx*8], xmm0
0x18002744f  movups  xmm0, [rbp+var_10]
0x180027453  movups  xmmword ptr [rsi+rcx*8+10h], xmm1
0x180027458  movups  xmmword ptr [rsi+rcx*8+20h], xmm0
0x18002745d  lea     ecx, [r8+1]
0x180027461  mov     eax, 51EB851Fh
0x180027466  mul     ecx
0x180027468  shr     edx, 3
0x18002746b  imul    eax, edx, 19h
0x18002746e  sub     ecx, eax
0x180027470  mov     r8d, ecx
0x180027473  mov     cs:?g_nextTxnHistoryIndex@TxnHistory@@3KA, r8d; ulong TxnHistory::g_nextTxnHistoryIndex
0x18002747a  lea     rcx, [rcx+rcx*2]
0x18002747e  add     rcx, rcx
0x180027481  cmp     qword ptr [rsi+rcx*8+20h], 0
0x180027487  jz      short loc_1800274D9
0x180027489  cmp     r8d, r11d
0x18002748c  jz      loc_18002751A
0x180027492  mov     [rbx], r9d
0x180027495  inc     r9d
0x180027498  mov     cs:?g_txnId@TxnHistory@@3KA, r9d; ulong TxnHistory::g_txnId
0x18002749f  xor     ebx, ebx
0x1800274a1  lea     rcx, ?g_txnHistoryLock@TxnHistory@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800274a8  call    cs:__imp_LeaveCriticalSection
0x1800274ae  lea     r11, [rsp+60h+var_s0]
0x1800274b3  mov     eax, ebx
0x1800274b5  mov     rbx, [r11+10h]
0x1800274b9  mov     rsi, [r11+28h]
0x1800274bd  mov     rsp, r11
0x1800274c0  pop     rbp
0x1800274c1  retn
0x1800274c2  lea     r8, [rbp+arg_8]; unsigned int *
0x1800274c6  mov     edx, eax; unsigned int
0x1800274c8  call    ?GetProcessIdFromRundownProtectionId@RundownProtectionList@@QEAAHKPEAK@Z; RundownProtectionList::GetProcessIdFromRundownProtectionId(ulong,ulong *)
0x1800274cd  test    eax, eax
0x1800274cf  jz      short loc_1800274F0
0x1800274d1  mov     eax, [rbp+arg_8]
0x1800274d4  jmp     loc_1800273E5
0x1800274d9  cmp     qword ptr [rsi+rcx*8+18h], 0
0x1800274df  jz      short loc_180027489
0x1800274e1  inc     r10d
0x1800274e4  cmp     r10d, 19h
0x1800274e8  jb      loc_18002745D
0x1800274ee  jmp     short loc_180027489
0x1800274f0  mov     ebx, 8000001Ah
0x1800274f5  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800274fc  mov     ecx, ebx
0x1800274fe  mov     r9d, 49Dh
0x180027504  xor     edx, edx
0x180027506  call    Log_UnistoreHREvent_0
0x18002750b  mov     r9d, 47h ; 'G'
0x180027511  mov     ecx, ebx
0x180027513  call    Log_UnistoreHREvent_22
0x180027518  jmp     short loc_1800274A1
0x18002751a  inc     r8d
0x18002751d  mov     eax, 51EB851Fh
0x180027522  mul     r8d
0x180027525  shr     edx, 3
0x180027528  imul    eax, edx, 19h
0x18002752b  sub     r8d, eax
0x18002752e  mov     cs:?g_nextTxnHistoryIndex@TxnHistory@@3KA, r8d; ulong TxnHistory::g_nextTxnHistoryIndex
0x180027535  jmp     loc_180027492
```
