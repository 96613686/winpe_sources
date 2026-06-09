# UbpmpTaskHostCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,_RPC_ASYNC_STATE * *,int *)

- ea: `0x1800057b0`
- end: `0x180005ec3`
- name: `?UbpmpTaskHostCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_RPC_ASYNC_STATE@@PEAH@Z`
- size: `1811`
- prototype: `void __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *, struct _RPC_ASYNC_STATE **, int *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004860`
- `0x18000a570`

## callees

- `0x180004194`
- `0x180004240`
- `0x1800046c0`
- `0x180004a30`
- `0x180004c6c`
- `0x1800057b0`
- `0x180007460`
- `0x18000ae40`
- `0x18000d578`
- `0x180019d90`
- `0x18001f600`
- `0x180020144`
- `0x180032e38`
- `0x180034844`
- `0x180035c10`
- `0x18003bfac`
- `0x18003c454`
- `0x18003ca00`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000597c`
- `ntdll!RtlFreeHeap` at `0x18000597c`
- `ntdll!RtlAllocateHeap` at `0x1800059a8`
- `ntdll!RtlAllocateHeap` at `0x1800059a8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180005a6d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180005a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a33`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005b09`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005b09`
- `profapi!__imp_UnloadProfileBasic` at `0x180005ce4`
- `profapi!__imp_UnloadProfileBasic` at `0x180005ce4`

## string_xrefs

- `0x1800058c7`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x180005959`: `ReportTaskEvent(0x%x) --> ret=%d`

## pseudocode

```c
void __fastcall UbpmpTaskHostCleanup(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1, struct _RPC_ASYNC_STATE **a2, int *a3)
{
  bool v4; // zf
  struct _RPC_ASYNC_STATE *v7; // rax
  void *v8; // rcx
  signed int v9; // edx
  unsigned __int16 v10; // r10
  unsigned __int16 *v11; // r14
  int v12; // eax
  __int64 v13; // r8
  PSID v14; // rcx
  PVOID v15; // rdi
  unsigned __int16 *v16; // r9
  int v17; // eax
  __int64 v18; // r8
  DWORD v19; // esi
  int v20; // r14d
  _DWORD *Heap; // rax
  _DWORD *v22; // rdi
  __int128 v23; // xmm0
  int v24; // eax
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  __int64 *i; // rdi
  struct _LIST_ENTRY *j; // rcx
  DWORD LastError; // eax
  unsigned __int16 v31; // r10
  unsigned __int16 *v32; // rcx
  DWORD v33; // eax
  int v34; // eax
  void *v35; // rdx
  size_t Size; // [rsp+48h] [rbp-60h]
  DWORD ExitCode; // [rsp+B0h] [rbp+8h] BYREF
  PVOID P; // [rsp+B8h] [rbp+10h] BYREF

  v4 = (*((_BYTE *)a1 + 104) & 4) == 0;
  ExitCode = 0;
  *a2 = 0;
  *a3 = 0;
  P = 0;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, a3, *((unsigned int *)a1 + 8), a1);
    *((_BYTE *)a1 + 104) |= 4u;
    v7 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a1 + 7);
    *a3 = 1;
    if ( v7 )
    {
      *a2 = v7;
      *((_QWORD *)a1 + 7) = 0;
    }
    v8 = (void *)*((_QWORD *)a1 + 3);
    if ( v8 )
    {
      GetExitCodeProcess(v8, &ExitCode);
      v9 = ExitCode;
    }
    else
    {
      v9 = 1291;
      ExitCode = 1291;
    }
    if ( (*((_BYTE *)a1 + 104) & 0x10) != 0 )
    {
      for ( i = (__int64 *)*((_QWORD *)a1 + 25); i != (__int64 *)((char *)a1 + 200); i = (__int64 *)*i )
      {
        if ( (i[11] & 1) == 0 )
        {
          v31 = *((_WORD *)i + 45);
          if ( v31 )
          {
            LODWORD(Size) = *((_DWORD *)i + 33);
            UbpmRunNextSerializedAction(
              (__int128 *)((char *)i + 44),
              v31,
              (UUID *)((char *)i + 92),
              *((_DWORD *)i + 27),
              i[14],
              *((_DWORD *)a1 + 48),
              *((PSID *)a1 + 23),
              i[15],
              *((_DWORD *)i + 32),
              Size,
              (void *)i[17],
              *((_BYTE *)i + 144),
              (unsigned __int16 **)i[19],
              *((_DWORD *)i + 40),
              *((_BYTE *)i + 164),
              (unsigned __int16 **)i[21]);
            v9 = ExitCode;
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          v32 = L"NULL";
          if ( i[9] )
            v32 = (unsigned __int16 *)i[9];
          ReportTaskEvent(
            (char *)g_hTaskEventManager,
            &ACTION_FAILURE,
            (unsigned __int16 *)i[8],
            (const struct _GUID *)((char *)i + 92),
            v32,
            v9,
            *((_DWORD *)a1 + 8));
          if ( *((_WORD *)a1 + 138) <= 1u )
          {
            v33 = ExitCode;
            if ( (int)ExitCode > 0 )
              v33 = (unsigned __int16)ExitCode | 0x80070000;
            ReportTaskEvent(
              (char *)g_hTaskEventManager,
              &JOB_FAILURE,
              (const unsigned __int16 *)i[8],
              (const struct _GUID *)((char *)i + 92),
              0,
              v33);
          }
          SubmitPostTaskHostDeadCallback((const struct _GUID *)((char *)i + 44), *((_DWORD *)i + 27), ExitCode);
          v9 = ExitCode;
        }
      }
      for ( j = g_leTaskHostHardeningListHead.Flink; j != &g_leTaskHostHardeningListHead; j = j->Flink )
      {
        if ( LODWORD(j[3].Blink) == *((_DWORD *)a1 + 8) )
          LODWORD(j[3].Blink) = 0;
      }
    }
    else
    {
      v10 = *((_WORD *)a1 + 138);
      if ( v10 )
      {
        LODWORD(Size) = *((_DWORD *)a1 + 84);
        UbpmRunNextSerializedAction(
          (__int128 *)a1 + 7,
          v10,
          (UUID *)((char *)a1 + 280),
          *((_DWORD *)a1 + 74),
          *((_QWORD *)a1 + 38),
          *((_DWORD *)a1 + 48),
          *((PSID *)a1 + 23),
          *((_QWORD *)a1 + 39),
          *((_DWORD *)a1 + 83),
          Size,
          *((void **)a1 + 43),
          *((_BYTE *)a1 + 352),
          *((unsigned __int16 ***)a1 + 45),
          *((_DWORD *)a1 + 92),
          *((_BYTE *)a1 + 372),
          *((unsigned __int16 ***)a1 + 47));
        LOBYTE(v9) = ExitCode;
      }
      v11 = L"NULL";
      if ( *((_QWORD *)a1 + 20) )
        v11 = (unsigned __int16 *)*((_QWORD *)a1 + 20);
      v12 = EventManager::EvtReport(
              g_hTaskEventManager,
              &ACTION_SUCCESS,
              *((unsigned __int16 **)a1 + 18),
              (const struct _GUID *)((char *)a1 + 280),
              v11,
              v9,
              *((_DWORD *)a1 + 8));
      v13 = (unsigned __int16)v12;
      if ( v12 >= 0 )
        v13 = 0;
      TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &ACTION_SUCCESS, v13);
      if ( *((_WORD *)a1 + 138) <= 1u )
      {
        v14 = pSid;
        if ( *((_QWORD *)a1 + 23) )
          v14 = (PSID)*((_QWORD *)a1 + 23);
        UbpmUtilsGetAccountNamesFromSid(v14, 1, 0, 0, &P);
        v15 = P;
        v16 = L"(NONE)";
        if ( P )
          v16 = (unsigned __int16 *)P;
        v17 = EventManager::EvtReport(
                g_hTaskEventManager,
                &JOB_SUCCESS,
                *((unsigned __int16 **)a1 + 18),
                v16,
                (const struct _GUID *)((char *)a1 + 280));
        v18 = (unsigned __int16)v17;
        if ( v17 >= 0 )
          v18 = 0;
        TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &JOB_SUCCESS, v18);
        if ( v15 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      }
      v19 = ExitCode;
      v20 = *((_DWORD *)a1 + 74);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x18u);
      v22 = Heap;
      if ( Heap )
      {
        v23 = *((_OWORD *)a1 + 7);
        Heap[5] = v20;
        Heap[4] = v19;
        *(_OWORD *)Heap = v23;
        v24 = UbpmUtilsSubmitThreadPoolWork(
                (void (*)(void *, unsigned __int8, void *))UbpmpPostTaskHostDeadCallback,
                Heap,
                1,
                0,
                0);
        if ( v24 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF__guid_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              190,
              WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
              (char *)a1 + 112,
              v24);
          UBPM_MIDL_user_free(v22);
        }
      }
      else
      {
        SetLastError(8u);
      }
    }
    v25 = (void *)*((_QWORD *)a1 + 5);
    if ( v25 )
    {
      if ( !UnregisterWaitEx(v25, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 997
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
        }
      }
      *((_QWORD *)a1 + 5) = 0;
    }
    if ( *((_QWORD *)a1 + 53) )
    {
      v35 = (void *)*((_QWORD *)a1 + 32);
      if ( !v35 )
        v35 = (void *)*((_QWORD *)a1 + 31);
      UbpmpDecrementAppContainerRefAndDelete((__int64)a1 + 424, v35);
      *((_QWORD *)a1 + 53) = 0;
    }
    if ( *((_QWORD *)a1 + 30) )
    {
      if ( *((_QWORD *)a1 + 31) )
      {
        v34 = UnloadProfileBasic();
        if ( v34 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_L(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            194,
            WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            (unsigned int)v34);
      }
    }
    v26 = (void *)*((_QWORD *)a1 + 31);
    if ( v26 )
      CloseHandle(v26);
    v27 = (void *)*((_QWORD *)a1 + 51);
    *((_QWORD *)a1 + 31) = 0;
    *((_QWORD *)a1 + 30) = 0;
    if ( v27 )
    {
      UbpmUtilsSystemPowerOff(v27);
      *((_QWORD *)a1 + 51) = 0;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids);
  }
}

```

## disassembly

```asm
0x1800057b0  mov     rax, rsp
0x1800057b3  push    rbx
0x1800057b4  push    rbp
0x1800057b5  push    rsi
0x1800057b6  push    rdi
0x1800057b7  push    r12
0x1800057b9  sub     rsp, 80h
0x1800057c0  xor     r12d, r12d
0x1800057c3  mov     rdi, r8
0x1800057c6  test    byte ptr [rcx+68h], 4
0x1800057ca  mov     rsi, rdx
0x1800057cd  mov     rbx, rcx
0x1800057d0  mov     [rax+8], r12d
0x1800057d4  mov     [rdx], r12
0x1800057d7  mov     [r8], r12d
0x1800057da  mov     [rax+10h], r12
0x1800057de  jnz     loc_180005AC9
0x1800057e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057eb  lea     rbp, WPP_GLOBAL_Control
0x1800057f2  cmp     rcx, rbp
0x1800057f5  jz      short loc_180005801
0x1800057f7  test    byte ptr [rcx+1Ch], 80h
0x1800057fb  jnz     loc_180005D50
0x180005801  or      byte ptr [rbx+68h], 4
0x180005805  mov     rax, [rbx+38h]
0x180005809  mov     dword ptr [rdi], 1
0x18000580f  test    rax, rax
0x180005812  jnz     loc_180005D44
0x180005818  mov     rcx, [rbx+18h]; hProcess
0x18000581c  test    rcx, rcx
0x18000581f  jnz     loc_180005A65
0x180005825  mov     edx, 50Bh
0x18000582a  mov     [rsp+0A8h+ExitCode], edx
0x180005831  test    byte ptr [rbx+68h], 10h
0x180005835  mov     [rsp+0A8h+arg_10], r14
0x18000583d  mov     [rsp+0A8h+arg_18], r15
0x180005845  jnz     loc_180005A7F
0x18000584b  movzx   r10d, word ptr [rbx+114h]
0x180005853  test    r10w, r10w
0x180005857  jnz     loc_180005B49
0x18000585d  mov     ecx, [rbx+20h]
0x180005860  test    edx, edx
0x180005862  jg      loc_180005B2D
0x180005868  mov     rax, [rbx+0A0h]
0x18000586f  lea     r14, aNull_0; "NULL"
0x180005876  test    rax, rax
0x180005879  cmovnz  r14, rax
0x18000587d  test    edx, edx
0x18000587f  jg      loc_180005B3B
0x180005885  mov     r8, [rbx+90h]; unsigned __int16 *
0x18000588c  lea     rsi, [rbx+118h]
0x180005893  mov     dword ptr [rsp+0A8h+pSid], ecx; struct _GUID *
0x180005897  mov     r9, rsi; struct _GUID *
0x18000589a  mov     rcx, cs:g_hTaskEventManager; this
0x1800058a1  mov     dword ptr [rsp+0A8h+var_80], edx; void *
0x1800058a5  lea     rdx, ACTION_SUCCESS; struct _EVENT_DESCRIPTOR *
0x1800058ac  mov     [rsp+0A8h+var_88], r14; unsigned __int16 *
0x1800058b1  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1KKPEAX2@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x1800058b6  test    eax, eax
0x1800058b8  movzx   r8d, ax
0x1800058bc  lea     rdx, ACTION_SUCCESS
0x1800058c3  cmovns  r8d, r12d
0x1800058c7  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x1800058ce  call    TaskEventTrace
0x1800058d3  cmp     word ptr [rbx+114h], 1
0x1800058db  ja      loc_180005982
0x1800058e1  mov     rax, [rbx+0B8h]
0x1800058e8  mov     edx, 1
0x1800058ed  mov     rcx, cs:pSid
0x1800058f4  test    rax, rax
0x1800058f7  cmovnz  rcx, rax
0x1800058fb  lea     rax, [rsp+0A8h+P]
0x180005903  xor     r9d, r9d
0x180005906  mov     [rsp+0A8h+var_88], rax
0x18000590b  xor     r8d, r8d
0x18000590e  call    UbpmUtilsGetAccountNamesFromSid
0x180005913  mov     rdi, [rsp+0A8h+P]
0x18000591b  lea     r9, aNone; "(NONE)"
0x180005922  mov     r8, [rbx+90h]; unsigned __int16 *
0x180005929  lea     rdx, JOB_SUCCESS; struct _EVENT_DESCRIPTOR *
0x180005930  mov     rcx, cs:g_hTaskEventManager; this
0x180005937  test    rdi, rdi
0x18000593a  mov     [rsp+0A8h+var_88], rsi; struct _GUID *
0x18000593f  cmovnz  r9, rdi; unsigned __int16 *
0x180005943  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEBU_GUID@@PEAX2@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *,void *,_GUID const *)
0x180005948  test    eax, eax
0x18000594a  movzx   r8d, ax
0x18000594e  lea     rdx, JOB_SUCCESS
0x180005955  cmovns  r8d, r12d
0x180005959  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x180005960  call    TaskEventTrace
0x180005965  test    rdi, rdi
0x180005968  jz      short loc_180005982
0x18000596a  mov     rcx, gs:60h
0x180005973  mov     r8, rdi; P
0x180005976  xor     edx, edx; Flags
0x180005978  mov     rcx, [rcx+30h]; HeapHandle
0x18000597c  call    cs:__imp_RtlFreeHeap
0x180005982  mov     rcx, gs:60h
0x18000598b  mov     edx, 8; Flags
0x180005990  mov     esi, [rsp+0A8h+ExitCode]
0x180005997  mov     r8d, 18h; Size
0x18000599d  mov     r14d, [rbx+128h]
0x1800059a4  mov     rcx, [rcx+30h]; HeapHandle
0x1800059a8  call    cs:__imp_RtlAllocateHeap
0x1800059ae  mov     rdi, rax
0x1800059b1  test    rax, rax
0x1800059b4  jz      loc_180005D6C
0x1800059ba  movups  xmm0, xmmword ptr [rbx+70h]
0x1800059be  xor     r9d, r9d; struct _TP_CALLBACK_ENVIRON_V3 *
0x1800059c1  mov     [rax+14h], r14d
0x1800059c5  mov     r8d, 1; int
0x1800059cb  mov     [rax+10h], esi
0x1800059ce  mov     rdx, rax; void *
0x1800059d1  mov     [rsp+0A8h+var_88], r12; struct _UBPM_SRWLOCK *
0x1800059d6  lea     rcx, UbpmpPostTaskHostDeadCallback; void (*)(void *, unsigned __int8, void *)
0x1800059dd  movups  xmmword ptr [rax], xmm0
0x1800059e0  call    ?UbpmUtilsSubmitThreadPoolWork@@YAKP6AXPEAXE0@Z0HPEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z; UbpmUtilsSubmitThreadPoolWork(void (*)(void *,uchar,void *),void *,int,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)
0x1800059e5  test    eax, eax
0x1800059e7  jnz     loc_180005D7C
0x1800059ed  mov     rcx, [rbx+28h]; WaitHandle
0x1800059f1  mov     r15, [rsp+0A8h+arg_18]
0x1800059f9  mov     r14, [rsp+0A8h+arg_10]
0x180005a01  test    rcx, rcx
0x180005a04  jnz     loc_180005B07
0x180005a0a  cmp     [rbx+1A8h], r12
0x180005a11  jnz     loc_180005E98
0x180005a17  mov     rdx, [rbx+0F0h]
0x180005a1e  test    rdx, rdx
0x180005a21  jnz     loc_180005CD4
0x180005a27  mov     rcx, [rbx+0F8h]; hObject
0x180005a2e  test    rcx, rcx
0x180005a31  jz      short loc_180005A39
0x180005a33  call    cs:__imp_CloseHandle
0x180005a39  mov     rcx, [rbx+198h]; hObject
0x180005a40  mov     [rbx+0F8h], r12
0x180005a47  mov     [rbx+0F0h], r12
0x180005a4e  test    rcx, rcx
0x180005a51  jnz     loc_180005C11
0x180005a57  add     rsp, 80h
0x180005a5e  pop     r12
0x180005a60  pop     rdi
0x180005a61  pop     rsi
0x180005a62  pop     rbp
0x180005a63  pop     rbx
0x180005a64  retn
0x180005a65  lea     rdx, [rsp+0A8h+ExitCode]; lpExitCode
0x180005a6d  call    cs:__imp_GetExitCodeProcess
0x180005a73  mov     edx, [rsp+0A8h+ExitCode]
0x180005a7a  jmp     loc_180005831
0x180005a7f  lea     rsi, [rbx+0C8h]
0x180005a86  mov     rdi, [rsi]
0x180005a89  cmp     rdi, rsi
0x180005a8c  jnz     loc_180005BF6
0x180005a92  mov     rcx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180005a99  lea     rdx, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180005aa0  cmp     rcx, rdx
0x180005aa3  jz      loc_1800059ED
0x180005aa9  nop     dword ptr [rax+00000000h]
0x180005ab0  mov     eax, [rbx+20h]
0x180005ab3  cmp     [rcx+38h], eax
0x180005ab6  jz      loc_180005E58
0x180005abc  mov     rcx, [rcx]
0x180005abf  cmp     rcx, rdx
0x180005ac2  jnz     short loc_180005AB0
0x180005ac4  jmp     loc_1800059ED
0x180005ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ad0  lea     rbp, WPP_GLOBAL_Control
0x180005ad7  cmp     rcx, rbp
0x180005ada  jz      loc_180005A57
0x180005ae0  test    byte ptr [rcx+1Ch], 80h
0x180005ae4  jz      loc_180005A57
0x180005aea  mov     rcx, [rcx+10h]
0x180005aee  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180005af5  mov     edx, 0BFh
0x180005afa  mov     r9, rbx
0x180005afd  call    WPP_SF_q
0x180005b02  jmp     loc_180005A57
0x180005b07  xor     edx, edx; CompletionEvent
0x180005b09  call    cs:__imp_UnregisterWaitEx
0x180005b0f  test    eax, eax
0x180005b11  jnz     short loc_180005B24
0x180005b13  call    cs:__imp_GetLastError
0x180005b19  cmp     eax, 3E5h
0x180005b1e  jnz     loc_180005E61
0x180005b24  mov     [rbx+28h], r12
0x180005b28  jmp     loc_180005A0A
0x180005b2d  movzx   edx, dx
0x180005b30  or      edx, 80070000h
0x180005b36  jmp     loc_180005868
0x180005b3b  movzx   edx, dx
0x180005b3e  or      edx, 80070000h
0x180005b44  jmp     loc_180005885
0x180005b49  mov     rax, [rbx+178h]
0x180005b50  lea     r8, [rbx+118h]; int
0x180005b57  mov     r9d, [rbx+128h]; int
0x180005b5e  lea     rcx, [rbx+70h]; int
0x180005b62  mov     [rsp+0A8h+var_30], rax; unsigned __int16 **
0x180005b67  movzx   edx, r10w; int
0x180005b6b  movzx   eax, byte ptr [rbx+174h]
0x180005b72  mov     [rsp+0A8h+var_38], al; unsigned __int8
0x180005b76  mov     eax, [rbx+170h]
0x180005b7c  mov     [rsp+0A8h+var_40], eax; int
0x180005b80  mov     rax, [rbx+168h]
0x180005b87  mov     [rsp+0A8h+var_48], rax; unsigned __int16 **
0x180005b8c  movzx   eax, byte ptr [rbx+160h]
0x180005b93  mov     [rsp+0A8h+var_50], al; unsigned __int8
0x180005b97  mov     rax, [rbx+158h]
0x180005b9e  mov     [rsp+0A8h+Src], rax; Src
0x180005ba3  mov     eax, [rbx+150h]
0x180005ba9  mov     dword ptr [rsp+0A8h+Size], eax; Size
0x180005bad  mov     eax, [rbx+14Ch]
0x180005bb3  mov     [rsp+0A8h+var_68], eax; int
0x180005bb7  mov     rax, [rbx+138h]
0x180005bbe  mov     [rsp+0A8h+var_70], rax; __int64
0x180005bc3  mov     rax, [rbx+0B8h]
0x180005bca  mov     [rsp+0A8h+pSid], rax; pSid
0x180005bcf  mov     eax, [rbx+0C0h]
0x180005bd5  mov     dword ptr [rsp+0A8h+var_80], eax; int
0x180005bd9  mov     rax, [rbx+130h]
0x180005be0  mov     [rsp+0A8h+var_88], rax; __int64
0x180005be5  call    UbpmRunNextSerializedAction
0x180005bea  mov     edx, [rsp+0A8h+ExitCode]
0x180005bf1  jmp     loc_18000585D
0x180005bf6  lea     r14, aNull_0; "NULL"
0x180005bfd  test    byte ptr [rdi+58h], 1
0x180005c01  jz      short loc_180005C22
0x180005c03  mov     rdi, [rdi]
0x180005c06  cmp     rdi, rsi
0x180005c09  jz      loc_180005A92
0x180005c0f  jmp     short loc_180005BFD
0x180005c11  call    ?UbpmUtilsSystemPowerOff@@YAKPEAX@Z; UbpmUtilsSystemPowerOff(void *)
0x180005c16  mov     [rbx+198h], r12
0x180005c1d  jmp     loc_180005A57
0x180005c22  movzx   r10d, word ptr [rdi+5Ah]
0x180005c27  lea     r15, [rdi+5Ch]
0x180005c2b  test    r10w, r10w
0x180005c2f  jnz     loc_180005DB8
0x180005c35  mov     r8d, [rbx+20h]
0x180005c39  test    edx, edx
0x180005c3b  jg      loc_180005D29
0x180005c41  mov     rax, [rdi+48h]
0x180005c45  mov     rcx, r14
0x180005c48  mov     dword ptr [rsp+0A8h+pSid], r8d; unsigned int
0x180005c4d  test    rax, rax
0x180005c50  mov     r8, [rdi+40h]; unsigned __int16 *
0x180005c54  mov     r9, r15; struct _GUID *
0x180005c57  cmovnz  rcx, rax
0x180005c5b  mov     dword ptr [rsp+0A8h+var_80], edx; unsigned int
0x180005c5f  mov     [rsp+0A8h+var_88], rcx; unsigned __int16 *
0x180005c64  lea     rdx, ACTION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180005c6b  mov     rcx, cs:g_hTaskEventManager; void *
0x180005c72  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2KK@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong)
0x180005c77  cmp     word ptr [rbx+114h], 1
0x180005c7f  ja      short loc_180005CB4
0x180005c81  mov     eax, [rsp+0A8h+ExitCode]
0x180005c88  test    eax, eax
0x180005c8a  jg      loc_180005D37
0x180005c90  mov     r8, [rdi+40h]; unsigned __int16 *
0x180005c94  lea     r9, [rdi+5Ch]; struct _GUID *
0x180005c98  mov     rcx, cs:g_hTaskEventManager; void *
0x180005c9f  lea     rdx, JOB_FAILURE; struct _EVENT_DESCRIPTOR *
0x180005ca6  mov     dword ptr [rsp+0A8h+var_80], eax; unsigned int
0x180005caa  mov     [rsp+0A8h+var_88], r12; unsigned __int16 *
0x180005caf  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2K@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong)
0x180005cb4  mov     r8d, [rsp+0A8h+ExitCode]; unsigned int
0x180005cbc  lea     rcx, [rdi+2Ch]; struct _GUID *
0x180005cc0  mov     edx, [rdi+6Ch]; unsigned int
0x180005cc3  call    ?SubmitPostTaskHostDeadCallback@@YAXPEBU_GUID@@KK@Z; SubmitPostTaskHostDeadCallback(_GUID const *,ulong,ulong)
0x180005cc8  mov     edx, [rsp+0A8h+ExitCode]
0x180005ccf  jmp     loc_180005C03
0x180005cd4  mov     rcx, [rbx+0F8h]
0x180005cdb  test    rcx, rcx
0x180005cde  jz      loc_180005A27
0x180005ce4  call    cs:__imp_UnloadProfileBasic
0x180005cea  test    eax, eax
0x180005cec  jns     loc_180005A27
0x180005cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cf9  cmp     rcx, rbp
0x180005cfc  jz      loc_180005A27
0x180005d02  test    byte ptr [rcx+1Ch], 1
0x180005d06  jz      loc_180005A27
0x180005d0c  mov     rcx, [rcx+10h]
0x180005d10  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180005d17  mov     edx, 0C2h
0x180005d1c  mov     r9d, eax
0x180005d1f  call    WPP_SF_L
0x180005d24  jmp     loc_180005A27
0x180005d29  movzx   edx, dx
0x180005d2c  or      edx, 80070000h
0x180005d32  jmp     loc_180005C41
0x180005d37  movzx   eax, ax
0x180005d3a  or      eax, 80070000h
0x180005d3f  jmp     loc_180005C90
0x180005d44  mov     [rsi], rax
0x180005d47  mov     [rbx+38h], r12
0x180005d4b  jmp     loc_180005818
0x180005d50  mov     r9d, [rbx+20h]
0x180005d54  mov     edx, 0C0h
0x180005d59  mov     rcx, [rcx+10h]
  ... truncated ...
```
