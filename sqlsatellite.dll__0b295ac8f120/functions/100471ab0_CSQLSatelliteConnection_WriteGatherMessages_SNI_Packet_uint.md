# CSQLSatelliteConnection::WriteGatherMessages(SNI_Packet *,uint)

- ea: `0x100471ab0`
- end: `0x100471d77`
- name: `?WriteGatherMessages@CSQLSatelliteConnection@@AEAAKPEAVSNI_Packet@@I@Z`
- size: `711`
- prototype: `__int64 __fastcall(CSQLSatelliteConnection *this, struct SNI_Packet *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x100414a30`
- `0x1004152f0`
- `0x100478d40`

## callees

- `0x10040bbb0`
- `0x10041d750`
- `0x10041f180`
- `0x100423130`
- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x100471ab0`
- `0x100472490`
- `0x1004737e0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100471c29`
- `KERNEL32!QueryPerformanceCounter` at `0x100471c29`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100471cca`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100471cca`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100471c0a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100471c16`

## string_xrefs

- `0x100471b4f`: `sql\common\dk\sni\src\sni.cpp`
- `0x100471ba0`: `sql\common\dk\sni\src\sni.cpp`
- `0x100471c86`: `sql\common\dk\sni\src\sni.cpp`
- `0x100471ca9`: `sql\common\dk\sni\src\sni.cpp`
- `0x100471b5b`: `SNIGatherWriteAsync`
- `0x100471ba7`: `SNIGatherWriteAsync`
- `0x100471c7f`: `SNIGatherWriteAsync`
- `0x100471ca2`: `SNIGatherWriteAsync`
- `0x100471d23`: `SNI Gather Write Error for error %d, at CSQLSatelliteConnection::WriteGatherMessages`

## pseudocode

```c
__int64 __fastcall CSQLSatelliteConnection::WriteGatherMessages(
        CSQLSatelliteConnection *this,
        struct SNI_Packet *a2,
        unsigned int a3)
{
  struct SNI_Packet *v4; // rsi
  struct SNI_Packet *i; // rax
  unsigned int v7; // ebp
  char *v8; // r12
  unsigned int v9; // r14d
  const wchar_t *v10; // r9
  __int64 v11; // rbx
  unsigned int v12; // eax
  const wchar_t *v13; // r9
  LARGE_INTEGER v14; // rax
  struct SNI_Packet *v15; // rbx
  __int64 v17; // [rsp+20h] [rbp-88h]
  char *v18; // [rsp+48h] [rbp-60h]
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp+8h] BYREF
  char v20; // [rsp+C0h] [rbp+18h] BYREF

  v4 = a2;
  _InterlockedExchangeAdd((volatile signed __int32 *)this + 38, a3);
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  for ( i = a2; i; i = (struct SNI_Packet *)*((_QWORD *)i + 26) )
    *((_QWORD *)i + 25) = this;
  v7 = 13;
  v8 = (char *)this + 192;
  v18 = (char *)this + 192;
  v9 = 0;
  if ( !(unsigned int)SOS_RWLock::GetLock((char *)this + 192, 2, 0xFFFFFFFFLL, (char *)this + 224) )
  {
    v9 = 2;
    v11 = *((_QWORD *)this + 8);
    if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
      SNIXE_SNI_ENTER_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNIGatherWriteAsync",
        4623,
        L"API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Conn*}, pPacket: %p{SNI_Packet*}, pProvInfo: %p{SNI_ProvInfo*}\n",
        *(_DWORD *)(v11 + 76),
        v11,
        v4,
        0,
        -2);
    if ( g_fSNIKillSwitch )
    {
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIGatherWriteAsync", 4623, v10);
      v7 = 5023;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12856));
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12832));
      v12 = (*(__int64 (__fastcall **)(_QWORD, struct SNI_Packet *, _QWORD))(**(_QWORD **)(v11 + 12616) + 48LL))(
              *(_QWORD *)(v11 + 12616),
              v4,
              0);
      v7 = v12;
      if ( v12 != 997 )
      {
        if ( !v12 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v11 + 12744));
          if ( CommonGlobalState::m_CollectingStatistics != (_BYTE)v12 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable == v12 )
            {
              v14.QuadPart = MEMORY[0x7FFE0008];
            }
            else
            {
              QueryPerformanceCounter(&PerformanceCount);
              v14 = PerformanceCount;
            }
            *(LARGE_INTEGER *)(v11 + 12792) = v14;
          }
        }
        v20 = 0;
        SNI_Conn::ReleaseUnderForceCloseLock(v11, 5, &v20);
      }
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v17) = v7;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "SNIGatherWriteAsync",
          4655,
          L"RET|SNI%d{WINERR}\n",
          v17);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIGatherWriteAsync", 4623, v13);
      v9 = 2;
      v8 = v18;
    }
  }
  if ( v9 )
    SOS_RWLock::ReleaseLock(v8, v9);
  if ( v7 )
  {
    if ( v7 != 997 )
    {
      _InterlockedExchangeAdd((volatile signed __int32 *)this + 38, -a3);
      if ( v4 )
      {
        do
        {
          v15 = (struct SNI_Packet *)*((_QWORD *)v4 + 26);
          *((_QWORD *)v4 + 26) = 0;
          SNIPacketRelease(v4);
          v4 = v15;
        }
        while ( v15 );
      }
      CSQLSatelliteConnection::AbortConnection(
        this,
        L"SNI Gather Write Error for error %d, at CSQLSatelliteConnection::WriteGatherMessages",
        v7);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 8, 0xFFFFFFFF) == 1 )
      {
        if ( *((_QWORD *)this + 2) )
          TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(
            *((_QWORD *)this + 3),
            this);
        (*(void (__fastcall **)(CSQLSatelliteConnection *))(*(_QWORD *)this + 24LL))(this);
      }
    }
  }
  else
  {
    CSQLSatelliteConnection::WriteCallBack(this, v4, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x100471ab0  push    rbp
0x100471ab2  push    rsi
0x100471ab3  push    rdi
0x100471ab4  push    r12
0x100471ab6  push    r13
0x100471ab8  push    r14
0x100471aba  push    r15
0x100471abc  sub     rsp, 70h
0x100471ac0  mov     [rsp+0A8h+var_68], 0FFFFFFFFFFFFFFFEh
0x100471ac9  mov     [rsp+0A8h+arg_8], rbx
0x100471ad1  mov     r15d, r8d
0x100471ad4  mov     rsi, rdx
0x100471ad7  mov     rdi, rcx
0x100471ada  mov     eax, r8d
0x100471add  lock xadd [rcx+98h], eax
0x100471ae5  lock inc dword ptr [rcx+20h]
0x100471ae9  mov     rax, rdx
0x100471aec  test    rdx, rdx
0x100471aef  jz      short loc_100471B04
0x100471af1  mov     [rax+0C8h], rdi
0x100471af8  mov     rax, [rax+0D0h]
0x100471aff  test    rax, rax
0x100471b02  jnz     short loc_100471AF1
0x100471b04  mov     ebp, 0Dh
0x100471b09  lea     r12, [rcx+0C0h]
0x100471b10  mov     [rsp+0A8h+var_60], r12
0x100471b15  xor     r13d, r13d
0x100471b18  mov     r14d, r13d
0x100471b1b  mov     [rsp+0A8h+var_58], r13d
0x100471b20  lea     r9, [rcx+0E0h]
0x100471b27  lea     edx, [rbp-0Bh]
0x100471b2a  mov     r8d, 0FFFFFFFFh
0x100471b30  mov     rcx, r12
0x100471b33  call    ?GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLock(RWLockMode,ulong,SOS_WaitInfo const *)
0x100471b38  test    eax, eax
0x100471b3a  jnz     loc_100471CBF
0x100471b40  mov     r14d, 2
0x100471b46  mov     [rsp+0A8h+var_58], r14d
0x100471b4b  mov     rbx, [rdi+40h]
0x100471b4f  lea     rcx, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100471b56  mov     [rsp+0A8h+var_50], rcx
0x100471b5b  lea     rdx, aSnigatherwrite; "SNIGatherWriteAsync"
0x100471b62  mov     [rsp+0A8h+var_48], rdx
0x100471b67  mov     [rsp+0A8h+var_40], 120Fh
0x100471b6f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100471b76  jz      short loc_100471BAE
0x100471b78  mov     [rsp+0A8h+var_70], r13
0x100471b7d  mov     [rsp+0A8h+var_78], rsi
0x100471b82  mov     [rsp+0A8h+var_80], rbx
0x100471b87  mov     eax, [rbx+4Ch]
0x100471b8a  mov     dword ptr [rsp+0A8h+var_88], eax
0x100471b8e  lea     r9, aApiSniUSniConn; "API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Con"...
0x100471b95  mov     r8d, 120Fh; int
0x100471b9b  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100471ba0  lea     rcx, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100471ba7  lea     rdx, aSnigatherwrite; "SNIGatherWriteAsync"
0x100471bae  cmp     cs:?g_fSNIKillSwitch@@3HA, 0; int g_fSNIKillSwitch
0x100471bb5  jz      short loc_100471BD5
0x100471bb7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100471bbe  jz      short loc_100471BCB
0x100471bc0  mov     r8d, 120Fh; int
0x100471bc6  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100471bcb  mov     ebp, 139Fh
0x100471bd0  jmp     loc_100471CBF
0x100471bd5  lock inc dword ptr [rbx+3238h]
0x100471bdc  lock inc dword ptr [rbx+3220h]
0x100471be3  mov     rcx, [rbx+3148h]
0x100471bea  mov     rax, [rcx]
0x100471bed  xor     r8d, r8d
0x100471bf0  mov     rdx, rsi
0x100471bf3  call    qword ptr [rax+30h]
0x100471bf6  mov     ebp, eax
0x100471bf8  cmp     eax, 3E5h
0x100471bfd  jz      short loc_100471C65
0x100471bff  test    eax, eax
0x100471c01  jnz     short loc_100471C48
0x100471c03  lock inc dword ptr [rbx+31C8h]
0x100471c0a  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100471c11  cmp     [rax], bpl
0x100471c14  jz      short loc_100471C48
0x100471c16  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100471c1d  cmp     [rax], ebp
0x100471c1f  jz      short loc_100471C39
0x100471c21  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x100471c29  call    cs:__imp_QueryPerformanceCounter
0x100471c2f  mov     rax, qword ptr [rsp+0A8h+PerformanceCount]
0x100471c37  jmp     short loc_100471C41
0x100471c39  mov     rax, ds:7FFE0008h
0x100471c41  mov     [rbx+31F8h], rax
0x100471c48  mov     [rsp+0A8h+arg_10], 0
0x100471c50  lea     r8, [rsp+0A8h+arg_10]
0x100471c58  mov     edx, 5
0x100471c5d  mov     rcx, rbx
0x100471c60  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x100471c65  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100471c6c  jz      short loc_100471C93
0x100471c6e  mov     dword ptr [rsp+0A8h+var_88], ebp
0x100471c72  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100471c79  mov     r8d, 122Fh; int
0x100471c7f  lea     rdx, aSnigatherwrite; "SNIGatherWriteAsync"
0x100471c86  lea     rcx, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100471c8d  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100471c92  nop
0x100471c93  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100471c9a  jz      short loc_100471CB5
0x100471c9c  mov     r8d, 120Fh; int
0x100471ca2  lea     rdx, aSnigatherwrite; "SNIGatherWriteAsync"
0x100471ca9  lea     rcx, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100471cb0  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100471cb5  mov     r14d, [rsp+0A8h+var_58]
0x100471cba  mov     r12, [rsp+0A8h+var_60]
0x100471cbf  test    r14d, r14d
0x100471cc2  jz      short loc_100471CD5
0x100471cc4  mov     edx, r14d
0x100471cc7  mov     rcx, r12
0x100471cca  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x100471cd0  mov     [rsp+0A8h+var_58], r13d
0x100471cd5  test    ebp, ebp
0x100471cd7  jnz     short loc_100471CE9
0x100471cd9  xor     r8d, r8d; unsigned int
0x100471cdc  mov     rdx, rsi; struct SNI_Packet *
0x100471cdf  mov     rcx, rdi; void *
0x100471ce2  call    ?WriteCallBack@CSQLSatelliteConnection@@SAXPEAXPEAVSNI_Packet@@K@Z; CSQLSatelliteConnection::WriteCallBack(void *,SNI_Packet *,ulong)
0x100471ce7  jmp     short loc_100471D5D
0x100471ce9  cmp     ebp, 3E5h
0x100471cef  jz      short loc_100471D5D
0x100471cf1  neg     r15d
0x100471cf4  lock xadd [rdi+98h], r15d
0x100471cfd  test    rsi, rsi
0x100471d00  jz      short loc_100471D20
0x100471d02  mov     rbx, [rsi+0D0h]
0x100471d09  mov     [rsi+0D0h], r13
0x100471d10  mov     rcx, rsi; struct SNI_Packet *
0x100471d13  call    SNIPacketRelease
0x100471d18  mov     rsi, rbx
0x100471d1b  test    rbx, rbx
0x100471d1e  jnz     short loc_100471D02
0x100471d20  mov     r8d, ebp
0x100471d23  lea     rdx, aSniGatherWrite; "SNI Gather Write Error for error %d, at"...
0x100471d2a  mov     rcx, rdi; this
0x100471d2d  call    ?AbortConnection@CSQLSatelliteConnection@@QEAAXPEB_WZZ; CSQLSatelliteConnection::AbortConnection(wchar_t const *,...)
0x100471d32  mov     eax, 0FFFFFFFFh
0x100471d37  lock xadd [rdi+20h], eax
0x100471d3c  cmp     eax, 1
0x100471d3f  jnz     short loc_100471D5D
0x100471d41  cmp     qword ptr [rdi+10h], 0
0x100471d46  jz      short loc_100471D54
0x100471d48  mov     rdx, rdi
0x100471d4b  mov     rcx, [rdi+18h]
0x100471d4f  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x100471d54  mov     rax, [rdi]
0x100471d57  mov     rcx, rdi
0x100471d5a  call    qword ptr [rax+18h]
0x100471d5d  mov     eax, ebp
0x100471d5f  mov     rbx, [rsp+0A8h+arg_8]
0x100471d67  add     rsp, 70h
0x100471d6b  pop     r15
0x100471d6d  pop     r14
0x100471d6f  pop     r13
0x100471d71  pop     r12
0x100471d73  pop     rdi
0x100471d74  pop     rsi
0x100471d75  pop     rbp
0x100471d76  retn
```
