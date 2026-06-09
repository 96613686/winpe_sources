# CSqmSessionMgr::GetContext(ushort const *,__POSITION * *,int *)

- ea: `0x1800154d4`
- end: `0x1800159f0`
- name: `?GetContext@CSqmSessionMgr@@QEAAXPEBGPEAPEAU__POSITION@@PEAH@Z`
- size: `1308`
- prototype: `void __fastcall(CSqmSessionMgr *__hidden this, const unsigned __int16 *, struct __POSITION **, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180007c34`

## callees

- `0x180001914`
- `0x180001954`
- `0x180003860`
- `0x180003888`
- `0x1800144c4`
- `0x180014564`
- `0x1800147c8`
- `0x1800147f0`
- `0x180014cdc`
- `0x180014eac`
- `0x180015024`
- `0x180015214`
- `0x1800154d4`
- `0x1800159f8`
- `0x180015d70`
- `0x180016108`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800158f6`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800158f6`
- `KERNEL32!LeaveCriticalSection` at `0x180015642`
- `KERNEL32!LeaveCriticalSection` at `0x180015802`
- `KERNEL32!LeaveCriticalSection` at `0x180015642`
- `KERNEL32!LeaveCriticalSection` at `0x180015802`
- `KERNEL32!LeaveCriticalSection` at `0x1800159d6`
- `KERNEL32!EnterCriticalSection` at `0x1800154f2`
- `KERNEL32!EnterCriticalSection` at `0x18001569c`
- `KERNEL32!EnterCriticalSection` at `0x1800157c0`
- `KERNEL32!EnterCriticalSection` at `0x1800154f2`
- `KERNEL32!EnterCriticalSection` at `0x18001569c`
- `KERNEL32!EnterCriticalSection` at `0x1800157c0`
- `KERNEL32!SetLastError` at `0x1800157eb`
- `KERNEL32!SetLastError` at `0x1800158fe`
- `KERNEL32!SetLastError` at `0x1800157eb`
- `KERNEL32!SetLastError` at `0x1800158fe`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180015653`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180015653`
- `KERNEL32!GetLastError` at `0x18001565d`
- `KERNEL32!GetLastError` at `0x18001565d`
- `ole32!CoTaskMemAlloc` at `0x1800157d1`
- `ole32!CoTaskMemAlloc` at `0x1800157d1`

## pseudocode

```c
void __fastcall CSqmSessionMgr::GetContext(
        CSqmSessionMgr *this,
        const unsigned __int16 *a2,
        struct __POSITION **a3,
        int *a4)
{
  LPCRITICAL_SECTION v4; // r13
  unsigned int v6; // ebx
  __int64 v7; // r8
  HANDLE *p_OwningThread; // r14
  _QWORD *OwningThread; // rsi
  ULONG_PTR *p_SpinCount; // rdi
  __int64 i; // rsi
  _DWORD *v12; // rax
  _DWORD *v13; // rsi
  unsigned int v14; // ebp
  __int64 j; // rax
  void *v16; // rbx
  _QWORD *v17; // rcx
  signed int LastError; // eax
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  int v20; // eax
  __int64 v21; // r8
  struct _RTL_CRITICAL_SECTION_DEBUG *v22; // rax
  unsigned int v23; // edi
  __int64 v24; // r8
  int v25; // edi
  __int64 v26; // rax
  _QWORD *v27; // rcx
  unsigned int started; // eax
  unsigned int v29; // edx

  v4 = _pSqmSessionMgr;
  EnterCriticalSection(_pSqmSessionMgr);
  v6 = WmcHashStringToDWORD(L"ShareMediaCPLSQM");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids, v6);
  p_OwningThread = &v4[1].OwningThread;
  OwningThread = v4[1].OwningThread;
  p_SpinCount = &v4[1].SpinCount;
  if ( OwningThread )
  {
    for ( i = OwningThread[v6 % *(_DWORD *)p_SpinCount]; i; i = *(_QWORD *)(i + 16) )
    {
      if ( *(_DWORD *)(i + 24) == v6 && *(_DWORD *)i == v6 )
      {
        *a3 = (struct __POSITION *)i;
        v13 = *(_DWORD **)(i + 8);
        goto LABEL_20;
      }
    }
  }
  *a3 = 0;
  v12 = operator new(0x28u);
  v13 = v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = v4;
    v12[2] = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 4) = 0;
    v14 = v6 % *(_DWORD *)p_SpinCount;
    if ( *p_OwningThread )
    {
      for ( j = *((_QWORD *)*p_OwningThread + v6 % *(_DWORD *)p_SpinCount); j; j = *(_QWORD *)(j + 16) )
      {
        if ( *(_DWORD *)(j + 24) == v6 && *(_DWORD *)j == v6 )
          goto LABEL_19;
      }
    }
    else
    {
      LOBYTE(v7) = 1;
      if ( !(unsigned __int8)ATL::CAtlMap<unsigned long,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::InitHashTable(
                               &v4[1].OwningThread,
                               *(unsigned int *)p_SpinCount,
                               v7) )
        ATL::AtlThrowImpl(-2147024882);
    }
    j = ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::NewNode(
          &v4[1].OwningThread,
          v6,
          v14,
          v6);
LABEL_19:
    *(_QWORD *)(j + 8) = v13;
    *a3 = (struct __POSITION *)j;
LABEL_20:
    if ( v13[2] )
      goto LABEL_76;
    v16 = (void *)*((_QWORD *)v13 + 2);
    if ( v16 )
    {
      *((_QWORD *)v13 + 2) = 0;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v7, *((_QWORD *)v13 + 3));
        v17 = WPP_GLOBAL_Control;
      }
      if ( *(_QWORD *)&v4[1].LockCount )
      {
        LeaveCriticalSection(v4);
        if ( !DeleteTimerQueueTimer(*(HANDLE *)&v4[1].LockCount, v16, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids,
              (unsigned int)LastError);
        }
        EnterCriticalSection(v4);
      }
      else
      {
        if ( v17 == &WPP_GLOBAL_Control || (*((_BYTE *)v17 + 28) & 8) == 0 )
        {
LABEL_39:
          if ( *((_QWORD *)v13 + 3) )
            goto LABEL_77;
          if ( v4[3].LockSemaphore )
          {
            v26 = ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveHead();
            v19 = (struct _RTL_CRITICAL_SECTION *)v26;
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
LABEL_65:
              started = CSqmSession::StartSession(v19, (unsigned int)v4[4].OwningThread);
              v25 = started;
              if ( !started )
              {
                CSqmSession::StartTimer((CSqmSession *)v19, v29);
                if ( *((_QWORD *)v13 + 4) )
                {
                  _time64(0);
                  SetLastError(0);
                }
                *((_QWORD *)v13 + 3) = v19;
LABEL_76:
                v17 = WPP_GLOBAL_Control;
LABEL_77:
                if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
                  WPP_SF_(v17[2], 30, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids);
                ++v13[2];
                goto LABEL_84;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  29,
                  &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids,
                  started);
              }
              if ( v19 )
                goto LABEL_73;
LABEL_75:
              *a3 = 0;
              if ( v25 )
                goto LABEL_84;
              goto LABEL_76;
            }
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            {
LABEL_62:
              if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 8) != 0 )
                WPP_SF_q(v27[2], 28, v24, v19);
              goto LABEL_65;
            }
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v24, v26);
          }
          else
          {
            v19 = (struct _RTL_CRITICAL_SECTION *)operator new(0x88u);
            if ( !v19 )
            {
              v25 = -2147024882;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids,
                  2147942414LL);
LABEL_74:
                *a3 = 0;
                goto LABEL_84;
              }
              goto LABEL_75;
            }
            *(_OWORD *)&v19->DebugInfo = 0;
            *(_OWORD *)&v19->OwningThread = 0;
            v19->SpinCount = 0;
            v20 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v19);
            if ( v20 < 0 )
              ATL::AtlThrowImpl(v20);
            v19[1].DebugInfo = 0;
            *(_QWORD *)&v19[1].LockCount = 0;
            v19[1].OwningThread = 0;
            LODWORD(v19[1].LockSemaphore) = 17;
            v19[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)0xFFFFFFFFLL;
            *(_QWORD *)&v19[2].LockCount = 0;
            LODWORD(v19[2].OwningThread) = 0;
            HIDWORD(v19[2].OwningThread) = 10;
            v19[2].LockSemaphore = 0;
            v19[2].SpinCount = 0;
            HIDWORD(v19[1].LockSemaphore) = 1061158912;
            LODWORD(v19[1].SpinCount) = 1048576000;
            HIDWORD(v19[1].SpinCount) = 1074790400;
            ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::UpdateRehashThresholds();
            v19[3].DebugInfo = 0;
            *(_QWORD *)&v19[3].LockCount = 0;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v21, v19);
            EnterCriticalSection(v19);
            if ( v19[3].DebugInfo )
            {
              v23 = -2147467259;
            }
            else
            {
              v22 = (struct _RTL_CRITICAL_SECTION_DEBUG *)CoTaskMemAlloc(0x10u);
              v19[3].DebugInfo = v22;
              if ( v22 )
              {
                *(_OWORD *)&v22->Type = 0;
                v23 = 0;
                SetLastError(0);
              }
              else
              {
                v23 = -2147024882;
              }
            }
            LeaveCriticalSection(v19);
            if ( v23 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids, v23);
              }
LABEL_73:
              CSqmSession::~CSqmSession((CSqmSession *)v19);
              operator delete(v19);
              goto LABEL_74;
            }
          }
          v27 = WPP_GLOBAL_Control;
          goto LABEL_62;
        }
        WPP_SF_(v17[2], 21, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids);
      }
    }
    v17 = WPP_GLOBAL_Control;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_ea0197bca44a35f25f9875116037e43b_Traceguids, 2147942414LL);
LABEL_84:
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x1800154d4  push    rbx
0x1800154d6  push    rbp
0x1800154d7  push    rsi
0x1800154d8  push    rdi
0x1800154d9  push    r12
0x1800154db  push    r13
0x1800154dd  push    r14
0x1800154df  push    r15
0x1800154e1  sub     rsp, 28h
0x1800154e5  mov     r13, cs:?_pSqmSessionMgr@@3PEAVCSqmSessionMgr@@EA; CSqmSessionMgr * _pSqmSessionMgr
0x1800154ec  mov     r15, r8
0x1800154ef  mov     rcx, r13; lpCriticalSection
0x1800154f2  call    cs:__imp_EnterCriticalSection
0x1800154f8  lea     rcx, aSharemediacpls; "ShareMediaCPLSQM"
0x1800154ff  call    ?WmcHashStringToDWORD@@YAKPEBG@Z; WmcHashStringToDWORD(ushort const *)
0x180015504  mov     ebx, eax
0x180015506  mov     rcx, cs:WPP_GLOBAL_Control
0x18001550d  lea     rax, WPP_GLOBAL_Control
0x180015514  mov     bpl, 8
0x180015517  cmp     rcx, rax
0x18001551a  jz      short loc_18001553A
0x18001551c  test    [rcx+1Ch], bpl
0x180015520  jz      short loc_18001553A
0x180015522  mov     rcx, [rcx+10h]
0x180015526  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x18001552d  mov     edx, 0Fh
0x180015532  mov     r9d, ebx
0x180015535  call    WPP_SF_d
0x18001553a  lea     r14, [r13+38h]
0x18001553e  xor     r12d, r12d
0x180015541  mov     rsi, [r14]
0x180015544  lea     rdi, [r14+10h]
0x180015548  test    rsi, rsi
0x18001554b  jz      short loc_18001556B
0x18001554d  xor     edx, edx
0x18001554f  mov     eax, ebx
0x180015551  div     dword ptr [rdi]
0x180015553  mov     rsi, [rsi+rdx*8]
0x180015557  jmp     short loc_180015566
0x180015559  cmp     [rsi+18h], ebx
0x18001555c  jnz     short loc_180015562
0x18001555e  cmp     [rsi], ebx
0x180015560  jz      short loc_1800155B7
0x180015562  mov     rsi, [rsi+10h]
0x180015566  test    rsi, rsi
0x180015569  jnz     short loc_180015559
0x18001556b  mov     rcx, r15
0x18001556e  mov     rax, r12
0x180015571  mov     [rcx], rax
0x180015574  mov     ecx, 28h ; '('; Size
0x180015579  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001557e  mov     rsi, rax
0x180015581  test    rax, rax
0x180015584  jz      loc_18001598F
0x18001558a  mov     [rax], r13
0x18001558d  xor     edx, edx
0x18001558f  mov     [rax+8], r12d
0x180015593  mov     [rax+10h], r12
0x180015597  mov     [rax+18h], r12
0x18001559b  mov     [rax+20h], r12
0x18001559f  mov     eax, ebx
0x1800155a1  div     dword ptr [rdi]
0x1800155a3  mov     rcx, [r14]
0x1800155a6  mov     ebp, edx
0x1800155a8  test    rcx, rcx
0x1800155ab  jz      loc_1800156A4
0x1800155b1  mov     rax, [rcx+rdx*8]
0x1800155b5  jmp     short loc_1800155CD
0x1800155b7  mov     [r15], rsi
0x1800155ba  mov     rsi, [rsi+8]
0x1800155be  jmp     short loc_1800155EC
0x1800155c0  cmp     [rax+18h], ebx
0x1800155c3  jnz     short loc_1800155C9
0x1800155c5  cmp     [rax], ebx
0x1800155c7  jz      short loc_1800155E2
0x1800155c9  mov     rax, [rax+10h]
0x1800155cd  test    rax, rax
0x1800155d0  jnz     short loc_1800155C0
0x1800155d2  mov     r9d, ebx
0x1800155d5  mov     r8d, ebp
0x1800155d8  mov     edx, ebx
0x1800155da  mov     rcx, r14
0x1800155dd  call    ?NewNode@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@AEAAPEAVCNode@12@KII@Z; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::NewNode(ulong,uint,uint)
0x1800155e2  mov     [rax+8], rsi
0x1800155e6  mov     bpl, 8
0x1800155e9  mov     [r15], rax
0x1800155ec  cmp     [rsi+8], r12d
0x1800155f0  jnz     loc_18001595C
0x1800155f6  mov     rbx, [rsi+10h]
0x1800155fa  test    rbx, rbx
0x1800155fd  jz      loc_1800156E0
0x180015603  mov     [rsi+10h], r12
0x180015607  mov     rcx, cs:WPP_GLOBAL_Control
0x18001560e  lea     r14, WPP_GLOBAL_Control
0x180015615  cmp     rcx, r14
0x180015618  jz      short loc_180015639
0x18001561a  test    [rcx+1Ch], bpl
0x18001561e  jz      short loc_180015639
0x180015620  mov     r9, [rsi+18h]
0x180015624  mov     edx, 13h
0x180015629  mov     rcx, [rcx+10h]
0x18001562d  call    WPP_SF_q
0x180015632  mov     rcx, cs:WPP_GLOBAL_Control
0x180015639  cmp     [r13+30h], r12
0x18001563d  jz      short loc_1800156BE
0x18001563f  mov     rcx, r13; lpCriticalSection
0x180015642  call    cs:__imp_LeaveCriticalSection
0x180015648  mov     rcx, [r13+30h]; TimerQueue
0x18001564c  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180015650  mov     rdx, rbx; Timer
0x180015653  call    cs:__imp_DeleteTimerQueueTimer
0x180015659  test    eax, eax
0x18001565b  jnz     short loc_180015699
0x18001565d  call    cs:__imp_GetLastError
0x180015663  test    eax, eax
0x180015665  jle     short loc_18001566F
0x180015667  movzx   eax, ax
0x18001566a  or      eax, 80070000h
0x18001566f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015676  cmp     rcx, r14
0x180015679  jz      short loc_180015699
0x18001567b  test    [rcx+1Ch], bpl
0x18001567f  jz      short loc_180015699
0x180015681  mov     rcx, [rcx+10h]
0x180015685  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x18001568c  mov     edx, 14h
0x180015691  mov     r9d, eax
0x180015694  call    WPP_SF_d
0x180015699  mov     rcx, r13; lpCriticalSection
0x18001569c  call    cs:__imp_EnterCriticalSection
0x1800156a2  jmp     short loc_1800156E7
0x1800156a4  mov     edx, [rdi]
0x1800156a6  mov     r8b, 1
0x1800156a9  mov     rcx, r14
0x1800156ac  call    ?InitHashTable@?$CAtlMap@KPEAVSqmTimerEntry@CSqmSession@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmTimerEntry@CSqmSession@@@4@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::InitHashTable(uint,bool)
0x1800156b1  test    al, al
0x1800156b3  jz      loc_1800159E5
0x1800156b9  jmp     loc_1800155D2
0x1800156be  cmp     rcx, r14
0x1800156c1  jz      short loc_1800156EE
0x1800156c3  test    [rcx+1Ch], bpl
0x1800156c7  jz      short loc_1800156EE
0x1800156c9  mov     rcx, [rcx+10h]
0x1800156cd  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x1800156d4  mov     edx, 15h
0x1800156d9  call    WPP_SF_
0x1800156de  jmp     short loc_1800156E7
0x1800156e0  lea     r14, WPP_GLOBAL_Control
0x1800156e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156ee  cmp     [rsi+18h], r12
0x1800156f2  jnz     loc_18001596A
0x1800156f8  lea     rcx, [r13+80h]
0x1800156ff  cmp     [rcx+10h], r12
0x180015703  jnz     loc_180015883
0x180015709  mov     ecx, 88h; Size
0x18001570e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015713  mov     rbx, rax
0x180015716  test    rax, rax
0x180015719  jz      loc_180015847
0x18001571f  xorps   xmm0, xmm0
0x180015722  xor     eax, eax
0x180015724  movups  xmmword ptr [rbx], xmm0
0x180015727  mov     rcx, rbx; this
0x18001572a  movups  xmmword ptr [rbx+10h], xmm0
0x18001572e  mov     [rbx+20h], rax
0x180015732  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180015737  test    eax, eax
0x180015739  js      loc_1800159DD
0x18001573f  lea     rcx, [rbx+30h]
0x180015743  mov     [rbx+28h], r12
0x180015747  mov     eax, 0FFFFFFFFh
0x18001574c  mov     [rcx], r12
0x18001574f  mov     [rcx+8], r12
0x180015753  mov     dword ptr [rcx+10h], 11h
0x18001575a  mov     [rcx+20h], rax
0x18001575e  mov     [rcx+28h], r12
0x180015762  mov     [rcx+30h], r12d
0x180015766  mov     dword ptr [rcx+34h], 0Ah
0x18001576d  mov     [rcx+38h], r12
0x180015771  mov     [rcx+40h], r12
0x180015775  mov     dword ptr [rcx+14h], 3F400000h
0x18001577c  mov     dword ptr [rcx+18h], 3E800000h
0x180015783  mov     dword ptr [rcx+1Ch], 40100000h
0x18001578a  call    ?UpdateRehashThresholds@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@AEAAXXZ; ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::UpdateRehashThresholds(void)
0x18001578f  mov     [rbx+78h], r12
0x180015793  mov     [rbx+80h], r12
0x18001579a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157a1  cmp     rcx, r14
0x1800157a4  jz      short loc_1800157BD
0x1800157a6  test    [rcx+1Ch], bpl
0x1800157aa  jz      short loc_1800157BD
0x1800157ac  mov     rcx, [rcx+10h]
0x1800157b0  mov     edx, 16h
0x1800157b5  mov     r9, rbx
0x1800157b8  call    WPP_SF_q
0x1800157bd  mov     rcx, rbx; lpCriticalSection
0x1800157c0  call    cs:__imp_EnterCriticalSection
0x1800157c6  cmp     [rbx+78h], r12
0x1800157ca  jnz     short loc_1800157FA
0x1800157cc  mov     ecx, 10h; cb
0x1800157d1  call    cs:__imp_CoTaskMemAlloc
0x1800157d7  mov     [rbx+78h], rax
0x1800157db  test    rax, rax
0x1800157de  jz      short loc_1800157F3
0x1800157e0  xorps   xmm0, xmm0
0x1800157e3  xor     ecx, ecx; dwErrCode
0x1800157e5  movups  xmmword ptr [rax], xmm0
0x1800157e8  mov     edi, r12d
0x1800157eb  call    cs:__imp_SetLastError
0x1800157f1  jmp     short loc_1800157FF
0x1800157f3  mov     edi, 8007000Eh
0x1800157f8  jmp     short loc_1800157FF
0x1800157fa  mov     edi, 80004005h
0x1800157ff  mov     rcx, rbx; lpCriticalSection
0x180015802  call    cs:__imp_LeaveCriticalSection
0x180015808  test    edi, edi
0x18001580a  jz      loc_1800158AE
0x180015810  mov     rcx, cs:WPP_GLOBAL_Control
0x180015817  cmp     rcx, r14
0x18001581a  jz      loc_180015939
0x180015820  test    [rcx+1Ch], bpl
0x180015824  jz      loc_180015939
0x18001582a  mov     rcx, [rcx+10h]
0x18001582e  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015835  mov     edx, 17h
0x18001583a  mov     r9d, edi
0x18001583d  call    WPP_SF_d
0x180015842  jmp     loc_180015939
0x180015847  mov     edi, 8007000Eh
0x18001584c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015853  cmp     rcx, r14
0x180015856  jz      loc_180015953
0x18001585c  test    [rcx+1Ch], bpl
0x180015860  jz      loc_180015953
0x180015866  mov     rcx, [rcx+10h]
0x18001586a  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015871  mov     edx, 18h
0x180015876  mov     r9d, edi
0x180015879  call    WPP_SF_d
0x18001587e  jmp     loc_18001594E
0x180015883  call    ?RemoveHead@?$CAtlList@PEAVCSqmSession@@V?$CElementTraits@PEAVCSqmSession@@@ATL@@@ATL@@QEAAPEAVCSqmSession@@XZ; ATL::CAtlList<CSqmSession *,ATL::CElementTraits<CSqmSession *>>::RemoveHead(void)
0x180015888  mov     rbx, rax
0x18001588b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015892  cmp     rcx, r14
0x180015895  jz      short loc_1800158D1
0x180015897  test    [rcx+1Ch], bpl
0x18001589b  jz      short loc_1800158B5
0x18001589d  mov     rcx, [rcx+10h]
0x1800158a1  mov     edx, 1Ah
0x1800158a6  mov     r9, rax
0x1800158a9  call    WPP_SF_q
0x1800158ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158b5  cmp     rcx, r14
0x1800158b8  jz      short loc_1800158D1
0x1800158ba  test    [rcx+1Ch], bpl
0x1800158be  jz      short loc_1800158D1
0x1800158c0  mov     rcx, [rcx+10h]
0x1800158c4  mov     edx, 1Ch
0x1800158c9  mov     r9, rbx
0x1800158cc  call    WPP_SF_q
0x1800158d1  mov     edx, [r13+0B0h]; unsigned int
0x1800158d8  mov     rcx, rbx; lpCriticalSection
0x1800158db  call    ?StartSession@CSqmSession@@QEAAJK@Z; CSqmSession::StartSession(ulong)
0x1800158e0  mov     edi, eax
0x1800158e2  test    eax, eax
0x1800158e4  jnz     short loc_18001590A
0x1800158e6  mov     rcx, rbx; this
0x1800158e9  call    ?StartTimer@CSqmSession@@QEAAXK@Z; CSqmSession::StartTimer(ulong)
0x1800158ee  cmp     [rsi+20h], r12
0x1800158f2  jz      short loc_180015904
0x1800158f4  xor     ecx, ecx; Time
0x1800158f6  call    cs:__imp__time64
0x1800158fc  xor     ecx, ecx; dwErrCode
0x1800158fe  call    cs:__imp_SetLastError
0x180015904  mov     [rsi+18h], rbx
0x180015908  jmp     short loc_180015963
0x18001590a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015911  cmp     rcx, r14
0x180015914  jz      short loc_180015934
0x180015916  test    [rcx+1Ch], bpl
0x18001591a  jz      short loc_180015934
0x18001591c  mov     rcx, [rcx+10h]
0x180015920  lea     r8, WPP_ea0197bca44a35f25f9875116037e43b_Traceguids
0x180015927  mov     edx, 1Dh
0x18001592c  mov     r9d, eax
0x18001592f  call    WPP_SF_d
0x180015934  test    rbx, rbx
0x180015937  jz      short loc_180015953
0x180015939  mov     rcx, rbx; this
0x18001593c  call    ??1CSqmSession@@QEAA@XZ; CSqmSession::~CSqmSession(void)
0x180015941  mov     edx, 88h
0x180015946  mov     rcx, rbx; Block
0x180015949  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001594e  mov     [r15], r12
0x180015951  jmp     short loc_1800159C3
0x180015953  mov     [r15], r12
0x180015956  test    edi, edi
0x180015958  jnz     short loc_1800159C3
0x18001595a  jmp     short loc_180015963
0x18001595c  lea     r14, WPP_GLOBAL_Control
  ... truncated ...
```
