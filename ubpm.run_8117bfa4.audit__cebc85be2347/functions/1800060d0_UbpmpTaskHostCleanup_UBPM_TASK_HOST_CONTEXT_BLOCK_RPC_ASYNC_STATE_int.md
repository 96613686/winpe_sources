# UbpmpTaskHostCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,_RPC_ASYNC_STATE * *,int *)

- ea: `0x1800060d0`
- end: `0x18000680d`
- name: `?UbpmpTaskHostCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_RPC_ASYNC_STATE@@PEAH@Z`
- size: `1853`
- prototype: `void __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *, struct _RPC_ASYNC_STATE **, int *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005190`
- `0x180010220`

## callees

- `0x180003da0`
- `0x180004768`
- `0x1800053a0`
- `0x180005614`
- `0x1800060d0`
- `0x180007e9c`
- `0x18000fbf0`
- `0x180012b1c`
- `0x18001bb54`
- `0x18001c87c`
- `0x18001cbe0`
- `0x180024740`
- `0x1800351ec`
- `0x180036cf8`
- `0x18003819c`
- `0x18003e8b0`
- `0x18003edd8`
- `0x18003f3d8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000629c`
- `ntdll!RtlFreeHeap` at `0x18000629c`
- `ntdll!RtlAllocateHeap` at `0x1800062ce`
- `ntdll!RtlAllocateHeap` at `0x1800062ce`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800063a0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800063a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000644b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000644b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000635f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000635f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000643b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000643b`
- `profapi!__imp_UnloadProfileBasic` at `0x180006622`
- `profapi!__imp_UnloadProfileBasic` at `0x180006622`

## string_xrefs

- `0x1800061e7`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x180006279`: `ReportTaskEvent(0x%x) --> ret=%d`

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
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  void *v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  __int64 *i; // rdi
  struct _LIST_ENTRY *j; // rcx
  DWORD LastError; // eax
  unsigned __int16 v34; // r10
  unsigned __int16 *v35; // rcx
  DWORD v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  void *v39; // rdx
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
          v34 = *((_WORD *)i + 45);
          if ( v34 )
          {
            LODWORD(Size) = *((_DWORD *)i + 33);
            UbpmRunNextSerializedAction(
              (__int128 *)((char *)i + 44),
              v34,
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
          v35 = L"NULL";
          if ( i[9] )
            v35 = (unsigned __int16 *)i[9];
          ReportTaskEvent(
            (char *)g_hTaskEventManager,
            &ACTION_FAILURE,
            (unsigned __int16 *)i[8],
            (const struct _GUID *)((char *)i + 92),
            v35,
            v9,
            *((_DWORD *)a1 + 8));
          if ( *((_WORD *)a1 + 138) <= 1u )
          {
            v36 = ExitCode;
            if ( (int)ExitCode > 0 )
              v36 = (unsigned __int16)ExitCode | 0x80070000;
            ReportTaskEvent(
              (char *)g_hTaskEventManager,
              &JOB_FAILURE,
              (const unsigned __int16 *)i[8],
              (const struct _GUID *)((char *)i + 92),
              0,
              v36);
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
          UBPM_MIDL_user_free(v22, v25, v26, v27);
        }
      }
      else
      {
        SetLastError(8u);
      }
    }
    v28 = (void *)*((_QWORD *)a1 + 5);
    if ( v28 )
    {
      if ( !UnregisterWaitEx(v28, 0) )
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
      v39 = (void *)*((_QWORD *)a1 + 32);
      if ( !v39 )
        v39 = (void *)*((_QWORD *)a1 + 31);
      UbpmpDecrementAppContainerRefAndDelete((__int64)a1 + 424, v39);
      *((_QWORD *)a1 + 53) = 0;
    }
    if ( *((_QWORD *)a1 + 30) )
    {
      v37 = *((_QWORD *)a1 + 31);
      if ( v37 )
      {
        v38 = UnloadProfileBasic(v37);
        if ( v38 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_L(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            194,
            WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            (unsigned int)v38);
      }
    }
    v29 = (void *)*((_QWORD *)a1 + 31);
    if ( v29 )
      CloseHandle(v29);
    v30 = (void *)*((_QWORD *)a1 + 51);
    *((_QWORD *)a1 + 31) = 0;
    *((_QWORD *)a1 + 30) = 0;
    if ( v30 )
    {
      UbpmUtilsSystemPowerOff(v30);
      *((_QWORD *)a1 + 51) = 0;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, a1);
  }
}

```

## disassembly

```asm
0x1800060d0  mov     rax, rsp
0x1800060d3  push    rbx
0x1800060d4  push    rbp
0x1800060d5  push    rsi
0x1800060d6  push    rdi
0x1800060d7  push    r12
0x1800060d9  sub     rsp, 80h
0x1800060e0  xor     r12d, r12d
0x1800060e3  mov     rdi, r8
0x1800060e6  test    byte ptr [rcx+68h], 4
0x1800060ea  mov     rsi, rdx
0x1800060ed  mov     rbx, rcx
0x1800060f0  mov     [rax+8], r12d
0x1800060f4  mov     [rdx], r12
0x1800060f7  mov     [r8], r12d
0x1800060fa  mov     [rax+10h], r12
0x1800060fe  jnz     loc_1800063FB
0x180006104  mov     rcx, cs:WPP_GLOBAL_Control
0x18000610b  lea     rbp, WPP_GLOBAL_Control
0x180006112  cmp     rcx, rbp
0x180006115  jz      short loc_180006121
0x180006117  test    byte ptr [rcx+1Ch], 80h
0x18000611b  jnz     loc_180006694
0x180006121  or      byte ptr [rbx+68h], 4
0x180006125  mov     rax, [rbx+38h]
0x180006129  mov     dword ptr [rdi], 1
0x18000612f  test    rax, rax
0x180006132  jnz     loc_180006688
0x180006138  mov     rcx, [rbx+18h]; hProcess
0x18000613c  test    rcx, rcx
0x18000613f  jnz     loc_180006398
0x180006145  mov     edx, 50Bh
0x18000614a  mov     [rsp+0A8h+ExitCode], edx
0x180006151  test    byte ptr [rbx+68h], 10h
0x180006155  mov     [rsp+0A8h+arg_10], r14
0x18000615d  mov     [rsp+0A8h+arg_18], r15
0x180006165  jnz     loc_1800063B8
0x18000616b  movzx   r10d, word ptr [rbx+114h]
0x180006173  test    r10w, r10w
0x180006177  jnz     loc_180006487
0x18000617d  mov     ecx, [rbx+20h]
0x180006180  test    edx, edx
0x180006182  jg      loc_18000646B
0x180006188  mov     rax, [rbx+0A0h]
0x18000618f  lea     r14, aNull_0; "NULL"
0x180006196  test    rax, rax
0x180006199  cmovnz  r14, rax
0x18000619d  test    edx, edx
0x18000619f  jg      loc_180006479
0x1800061a5  mov     r8, [rbx+90h]; unsigned __int16 *
0x1800061ac  lea     rsi, [rbx+118h]
0x1800061b3  mov     dword ptr [rsp+0A8h+pSid], ecx; struct _GUID *
0x1800061b7  mov     r9, rsi; struct _GUID *
0x1800061ba  mov     rcx, cs:g_hTaskEventManager; this
0x1800061c1  mov     dword ptr [rsp+0A8h+var_80], edx; void *
0x1800061c5  lea     rdx, ACTION_SUCCESS; struct _EVENT_DESCRIPTOR *
0x1800061cc  mov     [rsp+0A8h+var_88], r14; unsigned __int16 *
0x1800061d1  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1KKPEAX2@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x1800061d6  test    eax, eax
0x1800061d8  movzx   r8d, ax
0x1800061dc  lea     rdx, ACTION_SUCCESS
0x1800061e3  cmovns  r8d, r12d
0x1800061e7  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x1800061ee  call    TaskEventTrace
0x1800061f3  cmp     word ptr [rbx+114h], 1
0x1800061fb  ja      loc_1800062A8
0x180006201  mov     rax, [rbx+0B8h]
0x180006208  mov     edx, 1
0x18000620d  mov     rcx, cs:pSid
0x180006214  test    rax, rax
0x180006217  cmovnz  rcx, rax
0x18000621b  lea     rax, [rsp+0A8h+P]
0x180006223  xor     r9d, r9d
0x180006226  mov     [rsp+0A8h+var_88], rax
0x18000622b  xor     r8d, r8d
0x18000622e  call    UbpmUtilsGetAccountNamesFromSid
0x180006233  mov     rdi, [rsp+0A8h+P]
0x18000623b  lea     r9, aNone; "(NONE)"
0x180006242  mov     r8, [rbx+90h]; unsigned __int16 *
0x180006249  lea     rdx, JOB_SUCCESS; struct _EVENT_DESCRIPTOR *
0x180006250  mov     rcx, cs:g_hTaskEventManager; this
0x180006257  test    rdi, rdi
0x18000625a  mov     [rsp+0A8h+var_88], rsi; struct _GUID *
0x18000625f  cmovnz  r9, rdi; unsigned __int16 *
0x180006263  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEBU_GUID@@PEAX2@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *,void *,_GUID const *)
0x180006268  test    eax, eax
0x18000626a  movzx   r8d, ax
0x18000626e  lea     rdx, JOB_SUCCESS
0x180006275  cmovns  r8d, r12d
0x180006279  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x180006280  call    TaskEventTrace
0x180006285  test    rdi, rdi
0x180006288  jz      short loc_1800062A8
0x18000628a  mov     rcx, gs:60h
0x180006293  mov     r8, rdi; P
0x180006296  xor     edx, edx; Flags
0x180006298  mov     rcx, [rcx+30h]; HeapHandle
0x18000629c  call    cs:__imp_RtlFreeHeap
0x1800062a3  nop     dword ptr [rax+rax+00h]
0x1800062a8  mov     rcx, gs:60h
0x1800062b1  mov     edx, 8; Flags
0x1800062b6  mov     esi, [rsp+0A8h+ExitCode]
0x1800062bd  mov     r8d, 18h; Size
0x1800062c3  mov     r14d, [rbx+128h]
0x1800062ca  mov     rcx, [rcx+30h]; HeapHandle
0x1800062ce  call    cs:__imp_RtlAllocateHeap
0x1800062d5  nop     dword ptr [rax+rax+00h]
0x1800062da  mov     rdi, rax
0x1800062dd  test    rax, rax
0x1800062e0  jz      loc_1800066B0
0x1800062e6  movups  xmm0, xmmword ptr [rbx+70h]
0x1800062ea  xor     r9d, r9d; struct _TP_CALLBACK_ENVIRON_V3 *
0x1800062ed  mov     [rax+14h], r14d
0x1800062f1  mov     r8d, 1; int
0x1800062f7  mov     [rax+10h], esi
0x1800062fa  mov     rdx, rax; void *
0x1800062fd  mov     [rsp+0A8h+var_88], r12; struct _UBPM_SRWLOCK *
0x180006302  lea     rcx, UbpmpPostTaskHostDeadCallback; void (*)(void *, unsigned __int8, void *)
0x180006309  movups  xmmword ptr [rax], xmm0
0x18000630c  call    ?UbpmUtilsSubmitThreadPoolWork@@YAKP6AXPEAXE0@Z0HPEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z; UbpmUtilsSubmitThreadPoolWork(void (*)(void *,uchar,void *),void *,int,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)
0x180006311  test    eax, eax
0x180006313  jnz     loc_1800066C6
0x180006319  mov     rcx, [rbx+28h]; WaitHandle
0x18000631d  mov     r15, [rsp+0A8h+arg_18]
0x180006325  mov     r14, [rsp+0A8h+arg_10]
0x18000632d  test    rcx, rcx
0x180006330  jnz     loc_180006439
0x180006336  cmp     [rbx+1A8h], r12
0x18000633d  jnz     loc_1800067E2
0x180006343  mov     rdx, [rbx+0F0h]
0x18000634a  test    rdx, rdx
0x18000634d  jnz     loc_180006612
0x180006353  mov     rcx, [rbx+0F8h]; hObject
0x18000635a  test    rcx, rcx
0x18000635d  jz      short loc_18000636B
0x18000635f  call    cs:__imp_CloseHandle
0x180006366  nop     dword ptr [rax+rax+00h]
0x18000636b  mov     rcx, [rbx+198h]; hObject
0x180006372  mov     [rbx+0F8h], r12
0x180006379  mov     [rbx+0F0h], r12
0x180006380  test    rcx, rcx
0x180006383  jnz     loc_18000654F
0x180006389  add     rsp, 80h
0x180006390  pop     r12
0x180006392  pop     rdi
0x180006393  pop     rsi
0x180006394  pop     rbp
0x180006395  pop     rbx
0x180006396  retn
0x180006398  lea     rdx, [rsp+0A8h+ExitCode]; lpExitCode
0x1800063a0  call    cs:__imp_GetExitCodeProcess
0x1800063a7  nop     dword ptr [rax+rax+00h]
0x1800063ac  mov     edx, [rsp+0A8h+ExitCode]
0x1800063b3  jmp     loc_180006151
0x1800063b8  lea     rsi, [rbx+0C8h]
0x1800063bf  mov     rdi, [rsi]
0x1800063c2  cmp     rdi, rsi
0x1800063c5  jnz     loc_180006534
0x1800063cb  mov     rcx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x1800063d2  lea     rdx, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x1800063d9  cmp     rcx, rdx
0x1800063dc  jz      loc_180006319
0x1800063e2  mov     eax, [rbx+20h]
0x1800063e5  cmp     [rcx+38h], eax
0x1800063e8  jz      loc_1800067A2
0x1800063ee  mov     rcx, [rcx]
0x1800063f1  cmp     rcx, rdx
0x1800063f4  jnz     short loc_1800063E2
0x1800063f6  jmp     loc_180006319
0x1800063fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006402  lea     rbp, WPP_GLOBAL_Control
0x180006409  cmp     rcx, rbp
0x18000640c  jz      loc_180006389
0x180006412  test    byte ptr [rcx+1Ch], 80h
0x180006416  jz      loc_180006389
0x18000641c  mov     rcx, [rcx+10h]
0x180006420  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180006427  mov     edx, 0BFh
0x18000642c  mov     r9, rbx
0x18000642f  call    WPP_SF_q
0x180006434  jmp     loc_180006389
0x180006439  xor     edx, edx; CompletionEvent
0x18000643b  call    cs:__imp_UnregisterWaitEx
0x180006442  nop     dword ptr [rax+rax+00h]
0x180006447  test    eax, eax
0x180006449  jnz     short loc_180006462
0x18000644b  call    cs:__imp_GetLastError
0x180006452  nop     dword ptr [rax+rax+00h]
0x180006457  cmp     eax, 3E5h
0x18000645c  jnz     loc_1800067AB
0x180006462  mov     [rbx+28h], r12
0x180006466  jmp     loc_180006336
0x18000646b  movzx   edx, dx
0x18000646e  or      edx, 80070000h
0x180006474  jmp     loc_180006188
0x180006479  movzx   edx, dx
0x18000647c  or      edx, 80070000h
0x180006482  jmp     loc_1800061A5
0x180006487  mov     rax, [rbx+178h]
0x18000648e  lea     r8, [rbx+118h]; int
0x180006495  mov     r9d, [rbx+128h]; int
0x18000649c  lea     rcx, [rbx+70h]; int
0x1800064a0  mov     [rsp+0A8h+var_30], rax; unsigned __int16 **
0x1800064a5  movzx   edx, r10w; int
0x1800064a9  movzx   eax, byte ptr [rbx+174h]
0x1800064b0  mov     [rsp+0A8h+var_38], al; unsigned __int8
0x1800064b4  mov     eax, [rbx+170h]
0x1800064ba  mov     [rsp+0A8h+var_40], eax; int
0x1800064be  mov     rax, [rbx+168h]
0x1800064c5  mov     [rsp+0A8h+var_48], rax; unsigned __int16 **
0x1800064ca  movzx   eax, byte ptr [rbx+160h]
0x1800064d1  mov     [rsp+0A8h+var_50], al; unsigned __int8
0x1800064d5  mov     rax, [rbx+158h]
0x1800064dc  mov     [rsp+0A8h+Src], rax; Src
0x1800064e1  mov     eax, [rbx+150h]
0x1800064e7  mov     dword ptr [rsp+0A8h+Size], eax; Size
0x1800064eb  mov     eax, [rbx+14Ch]
0x1800064f1  mov     [rsp+0A8h+var_68], eax; int
0x1800064f5  mov     rax, [rbx+138h]
0x1800064fc  mov     [rsp+0A8h+var_70], rax; __int64
0x180006501  mov     rax, [rbx+0B8h]
0x180006508  mov     [rsp+0A8h+pSid], rax; pSid
0x18000650d  mov     eax, [rbx+0C0h]
0x180006513  mov     dword ptr [rsp+0A8h+var_80], eax; int
0x180006517  mov     rax, [rbx+130h]
0x18000651e  mov     [rsp+0A8h+var_88], rax; __int64
0x180006523  call    UbpmRunNextSerializedAction
0x180006528  mov     edx, [rsp+0A8h+ExitCode]
0x18000652f  jmp     loc_18000617D
0x180006534  lea     r14, aNull_0; "NULL"
0x18000653b  test    byte ptr [rdi+58h], 1
0x18000653f  jz      short loc_180006560
0x180006541  mov     rdi, [rdi]
0x180006544  cmp     rdi, rsi
0x180006547  jz      loc_1800063CB
0x18000654d  jmp     short loc_18000653B
0x18000654f  call    ?UbpmUtilsSystemPowerOff@@YAKPEAX@Z; UbpmUtilsSystemPowerOff(void *)
0x180006554  mov     [rbx+198h], r12
0x18000655b  jmp     loc_180006389
0x180006560  movzx   r10d, word ptr [rdi+5Ah]
0x180006565  lea     r15, [rdi+5Ch]
0x180006569  test    r10w, r10w
0x18000656d  jnz     loc_180006702
0x180006573  mov     r8d, [rbx+20h]
0x180006577  test    edx, edx
0x180006579  jg      loc_18000666D
0x18000657f  mov     rax, [rdi+48h]
0x180006583  mov     rcx, r14
0x180006586  mov     dword ptr [rsp+0A8h+pSid], r8d; unsigned int
0x18000658b  test    rax, rax
0x18000658e  mov     r8, [rdi+40h]; unsigned __int16 *
0x180006592  mov     r9, r15; struct _GUID *
0x180006595  cmovnz  rcx, rax
0x180006599  mov     dword ptr [rsp+0A8h+var_80], edx; unsigned int
0x18000659d  mov     [rsp+0A8h+var_88], rcx; unsigned __int16 *
0x1800065a2  lea     rdx, ACTION_FAILURE; struct _EVENT_DESCRIPTOR *
0x1800065a9  mov     rcx, cs:g_hTaskEventManager; void *
0x1800065b0  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2KK@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong)
0x1800065b5  cmp     word ptr [rbx+114h], 1
0x1800065bd  ja      short loc_1800065F2
0x1800065bf  mov     eax, [rsp+0A8h+ExitCode]
0x1800065c6  test    eax, eax
0x1800065c8  jg      loc_18000667B
0x1800065ce  mov     r8, [rdi+40h]; unsigned __int16 *
0x1800065d2  lea     r9, [rdi+5Ch]; struct _GUID *
0x1800065d6  mov     rcx, cs:g_hTaskEventManager; void *
0x1800065dd  lea     rdx, JOB_FAILURE; struct _EVENT_DESCRIPTOR *
0x1800065e4  mov     dword ptr [rsp+0A8h+var_80], eax; unsigned int
0x1800065e8  mov     [rsp+0A8h+var_88], r12; unsigned __int16 *
0x1800065ed  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2K@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong)
0x1800065f2  mov     r8d, [rsp+0A8h+ExitCode]; unsigned int
0x1800065fa  lea     rcx, [rdi+2Ch]; struct _GUID *
0x1800065fe  mov     edx, [rdi+6Ch]; unsigned int
0x180006601  call    ?SubmitPostTaskHostDeadCallback@@YAXPEBU_GUID@@KK@Z; SubmitPostTaskHostDeadCallback(_GUID const *,ulong,ulong)
0x180006606  mov     edx, [rsp+0A8h+ExitCode]
0x18000660d  jmp     loc_180006541
0x180006612  mov     rcx, [rbx+0F8h]
0x180006619  test    rcx, rcx
0x18000661c  jz      loc_180006353
0x180006622  call    cs:__imp_UnloadProfileBasic
0x180006629  nop     dword ptr [rax+rax+00h]
0x18000662e  test    eax, eax
0x180006630  jns     loc_180006353
0x180006636  mov     rcx, cs:WPP_GLOBAL_Control
0x18000663d  cmp     rcx, rbp
0x180006640  jz      loc_180006353
0x180006646  test    byte ptr [rcx+1Ch], 1
0x18000664a  jz      loc_180006353
0x180006650  mov     rcx, [rcx+10h]
0x180006654  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000665b  mov     edx, 0C2h
0x180006660  mov     r9d, eax
0x180006663  call    WPP_SF_L
0x180006668  jmp     loc_180006353
0x18000666d  movzx   edx, dx
0x180006670  or      edx, 80070000h
0x180006676  jmp     loc_18000657F
0x18000667b  movzx   eax, ax
0x18000667e  or      eax, 80070000h
0x180006683  jmp     loc_1800065CE
  ... truncated ...
```
