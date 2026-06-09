# TetheringService::AddPeer(uchar (*)[6])

- ea: `0x180015430`
- end: `0x180015769`
- name: `?AddPeer@TetheringService@@QEAAXPEAY05E@Z`
- size: `825`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned __int8 (*)[6])`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x18001379c`
- `0x180014c8c`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ee14`
- `0x180015430`
- `0x1800200d0`
- `0x18002035c`
- `0x180020f4c`
- `0x180027130`
- `0x1800272c0`
- `0x180027394`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015506`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015506`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800156bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800156bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154ae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800154f0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800154f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TetheringService::AddPeer(struct _RTL_CRITICAL_SECTION *this, unsigned __int8 (*a2)[6])
{
  int Session; // edi
  RTL_SRWLOCK *v5; // rbx
  PRTL_CRITICAL_SECTION_DEBUG i; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v7; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v8; // r14
  TetheringServiceTelemetry *v9; // rcx
  __int64 v10; // rdx
  TetheringServiceTelemetry *v11; // rcx
  TetheringServiceTelemetry *v12; // rcx
  TetheringServiceTelemetry *v13; // rcx
  struct TetheringSessionTelemetry *v14; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v15[24]; // [rsp+60h] [rbp-79h] BYREF
  _DWORD *v16; // [rsp+78h] [rbp-61h]
  _DWORD *v17; // [rsp+80h] [rbp-59h]
  int v18; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v19; // [rsp+B4h] [rbp-25h]
  LONG LockCount; // [rsp+C4h] [rbp-15h]
  char v21[16]; // [rsp+C8h] [rbp-11h] BYREF
  __int16 v22; // [rsp+D8h] [rbp-1h]

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 285, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  Session = 0;
  memset_0(v15, 0, 0x50u);
  v5 = 0;
  v14 = 0;
  EnterCriticalSection(this + 34);
  for ( i = this[35].DebugInfo; i; i = *(PRTL_CRITICAL_SECTION_DEBUG *)&i[4].Flags )
  {
    if ( *(_DWORD *)&i->Type == *(_DWORD *)a2 && *(&i->CreatorBackTraceIndex + 1) == *(_WORD *)&(*a2)[4] )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v10 = 286;
        goto LABEL_18;
      }
      goto LABEL_32;
    }
  }
  if ( ChangeTimerQueueTimer(this[39].LockSemaphore, this[39].OwningThread, 0xFFFFFFFF, 0xFFFFFFFF) )
    BYTE4(this[39].SpinCount) = 0;
  v7 = (struct _RTL_CRITICAL_SECTION_DEBUG *)malloc(0xF0u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(&v7->CreatorBackTraceIndex + 2, 0, 0xE2u);
    *(_DWORD *)&v8->Type = *(_DWORD *)a2;
    *(&v8->CreatorBackTraceIndex + 1) = *(_WORD *)&(*a2)[4];
    *(_QWORD *)&v8[4].Flags = this[35].DebugInfo;
    this[35].DebugInfo = v8;
    ++HIDWORD(this[41].OwningThread);
    *(_OWORD *)v21 = 0;
    v22 = 0;
    StringCchPrintfA(
      v21,
      0x12u,
      "%02x:%02x:%02x:%02x:%02x:%02x",
      LOBYTE(v8->Type),
      HIBYTE(v8->Type),
      LOBYTE(v8->CreatorBackTraceIndex),
      HIBYTE(v8->CreatorBackTraceIndex),
      *((unsigned __int8 *)&v8->CreatorBackTraceIndex + 2),
      *((unsigned __int8 *)&v8->CreatorBackTraceIndex + 3));
    v18 = 25;
    v19 = *(_OWORD *)&this[10].SpinCount;
    LockCount = this[11].LockCount;
    NetworkingTriageScenario::MobileHotspot::TetheringPeerAdded(
      (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)&v18,
      v21);
    if ( g_lTraceLoggingRegistered < 0 )
      goto LABEL_32;
    if ( !*(_QWORD *)&g_pTetheringSessionId.Data1 )
    {
      Session = -2147418113;
      goto LABEL_32;
    }
    Session = TetheringServiceTelemetry::GetSession(v11, *(struct _GUID **)&g_pTetheringSessionId.Data1, &v14);
    v5 = (RTL_SRWLOCK *)v14;
    if ( Session < 0 )
      goto LABEL_27;
    if ( !v14 )
    {
      Session = -2147467261;
      goto LABEL_32;
    }
    if ( (unsigned int)TetheringSessionTelemetry::Initialized(v14) )
    {
LABEL_27:
      if ( Session >= 0 )
      {
        if ( !v5 )
          ATL::AtlThrowImpl(-2147467259);
        TetheringServiceTelemetry::AcquireSessionData(v12, v5, (struct TetheringServiceTelemetry::SESSION_DATA *)v15);
        ++*v17;
        if ( HIDWORD(this[41].OwningThread) > *v16 )
          *v16 = HIDWORD(this[41].OwningThread);
        ReleaseSRWLockExclusive(v5 + 2);
      }
    }
    else
    {
      Session = -2147467259;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 287;
LABEL_18:
      WPP_SF_(*((_QWORD *)v9 + 2), v10, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
  }
LABEL_32:
  LeaveCriticalSection(this + 34);
  TetheringService::UpdatePeerListWorker((TetheringService *)this);
  if ( Session >= 0 )
    goto LABEL_36;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_40;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      288,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)Session);
LABEL_36:
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v13 + 2), 289, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
LABEL_40:
  if ( v5 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v5->Ptr + 2))(v5);
}

```

## disassembly

```asm
0x180015430  push    rbp
0x180015432  push    rbx
0x180015433  push    rsi
0x180015434  push    rdi
0x180015435  push    r12
0x180015437  push    r13
0x180015439  push    r14
0x18001543b  push    r15
0x18001543d  lea     rbp, [rsp-1Fh]
0x180015442  sub     rsp, 0F8h
0x180015449  mov     rax, cs:__security_cookie
0x180015450  xor     rax, rsp
0x180015453  mov     [rbp+57h+var_50], rax
0x180015457  mov     r15, rdx
0x18001545a  mov     rsi, rcx
0x18001545d  lea     r13, WPP_GLOBAL_Control
0x180015464  mov     rcx, cs:WPP_GLOBAL_Control
0x18001546b  cmp     rcx, r13
0x18001546e  jz      short loc_18001548B
0x180015470  test    byte ptr [rcx+1Ch], 8
0x180015474  jz      short loc_18001548B
0x180015476  mov     edx, 11Dh
0x18001547b  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015482  mov     rcx, [rcx+10h]
0x180015486  call    WPP_SF_
0x18001548b  xor     edi, edi
0x18001548d  xor     edx, edx; Val
0x18001548f  lea     r8d, [rdi+50h]; Size
0x180015493  lea     rcx, [rbp+57h+var_D0]; void *
0x180015497  call    memset_0
0x18001549c  nop
0x18001549d  xor     ebx, ebx
0x18001549f  mov     [rsp+130h+var_E0], rbx
0x1800154a4  lea     r12, [rsi+550h]
0x1800154ab  mov     rcx, r12; lpCriticalSection
0x1800154ae  call    cs:__imp_EnterCriticalSection
0x1800154b4  mov     rcx, [rsi+578h]
0x1800154bb  jmp     short loc_1800154D6
0x1800154bd  mov     eax, [rcx]
0x1800154bf  cmp     eax, [r15]
0x1800154c2  jnz     short loc_1800154CF
0x1800154c4  movzx   eax, word ptr [rcx+4]
0x1800154c8  cmp     ax, [r15+4]
0x1800154cd  jz      short loc_180015535
0x1800154cf  mov     rcx, [rcx+0E8h]
0x1800154d6  test    rcx, rcx
0x1800154d9  jnz     short loc_1800154BD
0x1800154db  or      r8d, 0FFFFFFFFh; DueTime
0x1800154df  mov     r9d, r8d; Period
0x1800154e2  mov     rdx, [rsi+628h]; Timer
0x1800154e9  mov     rcx, [rsi+630h]; TimerQueue
0x1800154f0  call    cs:__imp_ChangeTimerQueueTimer
0x1800154f6  test    eax, eax
0x1800154f8  jz      short loc_180015501
0x1800154fa  mov     byte ptr [rsi+63Ch], 0
0x180015501  mov     ecx, 0F0h; Size
0x180015506  call    cs:__imp_malloc
0x18001550c  mov     r14, rax
0x18001550f  test    rax, rax
0x180015512  jnz     short loc_180015569
0x180015514  mov     rcx, cs:WPP_GLOBAL_Control
0x18001551b  cmp     rcx, r13
0x18001551e  jz      loc_1800156C2
0x180015524  test    byte ptr [rcx+1Ch], 1
0x180015528  jz      loc_1800156C2
0x18001552e  mov     edx, 11Fh
0x180015533  jmp     short loc_180015554
0x180015535  mov     rcx, cs:WPP_GLOBAL_Control
0x18001553c  cmp     rcx, r13
0x18001553f  jz      loc_1800156C2
0x180015545  test    byte ptr [rcx+1Ch], 4
0x180015549  jz      loc_1800156C2
0x18001554f  mov     edx, 11Eh
0x180015554  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001555b  mov     rcx, [rcx+10h]
0x18001555f  call    WPP_SF_
0x180015564  jmp     loc_1800156C2
0x180015569  lea     rcx, [rax+6]; void *
0x18001556d  xor     edx, edx; Val
0x18001556f  mov     r8d, 0E2h; Size
0x180015575  call    memset_0
0x18001557a  mov     eax, [r15]
0x18001557d  mov     [r14], eax
0x180015580  movzx   eax, word ptr [r15+4]
0x180015585  mov     [r14+4], ax
0x18001558a  mov     rax, [rsi+578h]
0x180015591  mov     [r14+0E8h], rax
0x180015598  mov     [rsi+578h], r14
0x18001559f  mov     eax, [rsi+67Ch]
0x1800155a5  inc     eax
0x1800155a7  mov     [rsi+67Ch], eax
0x1800155ad  xorps   xmm0, xmm0
0x1800155b0  xor     eax, eax
0x1800155b2  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800155b6  mov     [rbp+57h+var_58], ax
0x1800155ba  movzx   eax, byte ptr [r14+5]
0x1800155bf  movzx   ecx, byte ptr [r14+4]
0x1800155c4  movzx   edx, byte ptr [r14+3]
0x1800155c9  movzx   r8d, byte ptr [r14+2]
0x1800155ce  movzx   r10d, byte ptr [r14+1]
0x1800155d3  movzx   r9d, byte ptr [r14]
0x1800155d7  mov     [rsp+130h+var_F0], eax
0x1800155db  mov     [rsp+130h+var_F8], ecx
0x1800155df  mov     [rsp+130h+var_100], edx
0x1800155e3  mov     [rsp+130h+var_108], r8d
0x1800155e8  mov     [rsp+130h+var_110], r10d
0x1800155ed  lea     r8, a02x02x02x02x02; "%02x:%02x:%02x:%02x:%02x:%02x"
0x1800155f4  mov     edx, 12h; unsigned __int64
0x1800155f9  lea     rcx, [rbp+57h+var_68]; char *
0x1800155fd  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015602  mov     [rbp+57h+var_80], 19h
0x180015609  movups  xmm0, xmmword ptr [rsi+1B0h]
0x180015610  movdqu  [rbp+57h+var_7C], xmm0
0x180015615  mov     eax, [rsi+1C0h]
0x18001561b  mov     [rbp+57h+var_6C], eax
0x18001561e  lea     rdx, [rbp+57h+var_68]; char *
0x180015622  lea     rcx, [rbp+57h+var_80]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x180015626  call    ?TetheringPeerAdded@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBD@Z; NetworkingTriageScenario::MobileHotspot::TetheringPeerAdded(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,char const *)
0x18001562b  cmp     cs:?g_lTraceLoggingRegistered@@3JA, 0; long g_lTraceLoggingRegistered
0x180015632  jl      loc_1800156C2
0x180015638  mov     rdx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data1; struct _GUID *
0x18001563f  test    rdx, rdx
0x180015642  jnz     short loc_18001564B
0x180015644  mov     edi, 8000FFFFh
0x180015649  jmp     short loc_1800156C2
0x18001564b  lea     r8, [rsp+130h+var_E0]; struct TetheringSessionTelemetry **
0x180015650  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x180015655  mov     edi, eax
0x180015657  mov     rbx, [rsp+130h+var_E0]
0x18001565c  test    eax, eax
0x18001565e  js      short loc_18001567F
0x180015660  test    rbx, rbx
0x180015663  jnz     short loc_18001566C
0x180015665  mov     edi, 80004003h
0x18001566a  jmp     short loc_1800156C2
0x18001566c  mov     rcx, rbx; this
0x18001566f  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x180015674  test    eax, eax
0x180015676  jnz     short loc_18001567F
0x180015678  mov     edi, 80004005h
0x18001567d  jmp     short loc_1800156C2
0x18001567f  test    edi, edi
0x180015681  js      short loc_1800156C2
0x180015683  test    rbx, rbx
0x180015686  jz      loc_18001575E
0x18001568c  lea     r8, [rbp+57h+var_D0]; struct TetheringServiceTelemetry::SESSION_DATA *
0x180015690  mov     rdx, rbx; struct TetheringSessionTelemetry *
0x180015693  call    ?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z; TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)
0x180015698  mov     rax, [rbp+57h+var_B0]
0x18001569c  inc     dword ptr [rax]
0x18001569e  mov     r8, [rbp+57h+var_B8]
0x1800156a2  mov     edx, [r8]
0x1800156a5  mov     eax, [rsi+67Ch]
0x1800156ab  cmp     eax, edx
0x1800156ad  jbe     short loc_1800156B8
0x1800156af  mov     eax, [rsi+67Ch]
0x1800156b5  mov     [r8], eax
0x1800156b8  lea     rcx, [rbx+10h]; SRWLock
0x1800156bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800156c2  mov     rcx, r12; lpCriticalSection
0x1800156c5  call    cs:__imp_LeaveCriticalSection
0x1800156cb  mov     rcx, rsi; this
0x1800156ce  call    ?UpdatePeerListWorker@TetheringService@@AEAAXXZ; TetheringService::UpdatePeerListWorker(void)
0x1800156d3  test    edi, edi
0x1800156d5  jns     short loc_180015701
0x1800156d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156de  cmp     rcx, r13
0x1800156e1  jz      short loc_180015729
0x1800156e3  test    byte ptr [rcx+1Ch], 8
0x1800156e7  jz      short loc_180015708
0x1800156e9  mov     edx, 120h
0x1800156ee  mov     r9d, edi
0x1800156f1  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800156f8  mov     rcx, [rcx+10h]
0x1800156fc  call    WPP_SF_d
0x180015701  mov     rcx, cs:WPP_GLOBAL_Control
0x180015708  cmp     rcx, r13
0x18001570b  jz      short loc_180015729
0x18001570d  test    byte ptr [rcx+1Ch], 8
0x180015711  jz      short loc_180015729
0x180015713  mov     edx, 121h
0x180015718  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001571f  mov     rcx, [rcx+10h]
0x180015723  call    WPP_SF_
0x180015728  nop
0x180015729  test    rbx, rbx
0x18001572c  jz      short loc_18001573E
0x18001572e  mov     rax, [rbx]
0x180015731  mov     rcx, rbx
0x180015734  mov     rax, [rax+10h]
0x180015738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001573d  nop
0x18001573e  mov     rcx, [rbp+57h+var_50]
0x180015742  xor     rcx, rsp; StackCookie
0x180015745  call    __security_check_cookie
0x18001574a  add     rsp, 0F8h
0x180015751  pop     r15
0x180015753  pop     r14
0x180015755  pop     r13
0x180015757  pop     r12
0x180015759  pop     rdi
0x18001575a  pop     rsi
0x18001575b  pop     rbx
0x18001575c  pop     rbp
0x18001575d  retn
0x18001575e  mov     ecx, 80004005h; int
0x180015763  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
