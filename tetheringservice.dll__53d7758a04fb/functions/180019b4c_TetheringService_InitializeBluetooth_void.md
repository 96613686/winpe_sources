# TetheringService::InitializeBluetooth(void)

- ea: `0x180019b4c`
- end: `0x180019eb9`
- name: `?InitializeBluetooth@TetheringService@@QEAAJXZ`
- size: `877`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task`

## callers

- `0x18000b888`

## callees

- `0x1800010a8`
- `0x180002590`
- `0x18000299c`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ee14`
- `0x180012a90`
- `0x180015cdc`
- `0x180019b4c`
- `0x18001e4a4`
- `0x180021be8`
- `0x180026b10`
- `0x180027130`
- `0x180027288`
- `0x180027394`
- `0x180027424`
- `0x1800274c0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019d4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019d4b`

## pseudocode

```c
__int64 __fastcall TetheringService::InitializeBluetooth(TetheringService *this)
{
  RTL_SRWLOCK *v2; // rbx
  int DefaultInterface; // edi
  WCHAR *v4; // rax
  int started; // eax
  int v6; // r8d
  char v7; // di
  TetheringServiceTelemetry *v8; // rcx
  int v9; // eax
  bool v10; // zf
  const char *v11; // rax
  struct _GUID *Id; // rax
  TetheringServiceTelemetry *v13; // rcx
  TetheringServiceTelemetry *v14; // rcx
  _DWORD *v15; // rdx
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  TetheringServiceTelemetry *v19; // rcx
  RTL_SRWLOCK *v21; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v22; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID *v23; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID *v24; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v25[10]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[56]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v27; // [rsp+E8h] [rbp-18h]
  struct _GUID v28; // [rsp+100h] [rbp+0h] BYREF
  struct _GUID v29; // [rsp+110h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  memset_0(v26, 0, 0x50u);
  v2 = 0;
  v21 = 0;
  *((_DWORD *)this + 414) = TetheringService::ChangeConnectionType(this, 1u, 4);
  v28 = 0;
  if ( *((_QWORD *)this + 161) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)this + 162) == *(_QWORD *)GUID_NULL.Data4 )
  {
    DefaultInterface = InterfaceMgr::GetDefaultInterface(1, 2, &v28);
    if ( DefaultInterface < 0 )
      goto LABEL_31;
  }
  else
  {
    v28 = *(struct _GUID *)((char *)this + 1288);
  }
  v29 = 0;
  DefaultInterface = InterfaceMgr::GetDefaultInterface(2, 4, &v29);
  if ( DefaultInterface < 0 )
  {
LABEL_31:
    v19 = WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  v4 = (WCHAR *)operator new(0x220u, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v4;
  if ( v4 )
    v2 = (RTL_SRWLOCK *)TetheringSessionTelemetry::TetheringSessionTelemetry((TetheringSessionTelemetry *)v4, 4);
  else
    v2 = 0;
  v21 = v2;
  started = StartGlobalTelemetrySession((struct TetheringSessionTelemetry *)v2);
  v7 = started;
  if ( started >= 0 )
  {
    memset_0(v25, 0, sizeof(v25));
    v25[0] = &v28;
    v25[1] = &v29;
    Id = TetheringSessionTelemetry::GetId((TetheringSessionTelemetry *)v2);
    TetheringServiceTelemetry::SetSessionData(v13, Id, (const struct TetheringServiceTelemetry::SESSION_DATA *)v25);
    if ( !v2 )
      ATL::AtlThrowImpl(-2147467259);
    TetheringServiceTelemetry::AcquireSessionData(v14, v2, (struct TetheringServiceTelemetry::SESSION_DATA *)v26);
    v15 = v27;
    v27[2] = 0;
    v15[1] = *((_DWORD *)this + 414);
    *v15 = *((_DWORD *)this + 414);
    ReleaseSRWLockExclusive(v2 + 2);
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      if ( !v2
        || (v9 = TetheringSessionTelemetry::Initialized((TetheringSessionTelemetry *)v2),
            v8 = WPP_GLOBAL_Control,
            v10 = v9 == 0,
            v11 = "true",
            v10) )
      {
        v11 = "false";
      }
      WPP_SF_lsd(*((_QWORD *)v8 + 2), 261, v6, (_DWORD)v2, (__int64)v11, v7);
    }
  }
  v16 = TetheringService::StartSharingInternal(this, &v28, &v29, 0, 1u, 0);
  DefaultInterface = v16;
  if ( v16 >= 0 )
  {
    if ( g_lTraceLoggingRegistered >= 0
      && (unsigned int)dword_180041008 > 5
      && (qword_180041018 & 0x400000000000LL) != 0
      && (qword_180041020 & 0x400000000000LL) == qword_180041020 )
    {
      LODWORD(v21) = v16;
      v23 = &v29;
      v24 = &v28;
      v22 = (WCHAR *)&sourceString;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        qword_180041020,
        (__int64)byte_180039ADB,
        v17,
        v18,
        (const WCHAR **)&v22,
        (__int64 *)&v24,
        (__int64 *)&v23,
        (__int64)&v21);
    }
    goto LABEL_31;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_35;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      262,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)v16);
    goto LABEL_31;
  }
LABEL_32:
  if ( v19 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)v19 + 2),
      263,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)DefaultInterface);
LABEL_35:
  if ( v2 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v2->Ptr + 2))(v2);
  return (unsigned int)DefaultInterface;
}

```

## disassembly

```asm
0x180019b4c  mov     [rsp-8+arg_8], rbx
0x180019b51  mov     [rsp-8+arg_10], rsi
0x180019b56  push    rbp
0x180019b57  push    rdi
0x180019b58  push    r15
0x180019b5a  lea     rbp, [rsp-30h]
0x180019b5f  sub     rsp, 130h
0x180019b66  mov     rax, cs:__security_cookie
0x180019b6d  xor     rax, rsp
0x180019b70  mov     [rbp+40h+var_20], rax
0x180019b74  mov     rsi, rcx
0x180019b77  lea     r15, WPP_GLOBAL_Control
0x180019b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b85  cmp     rcx, r15
0x180019b88  jz      short loc_180019BA5
0x180019b8a  test    byte ptr [rcx+1Ch], 8
0x180019b8e  jz      short loc_180019BA5
0x180019b90  mov     edx, 104h
0x180019b95  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019b9c  mov     rcx, [rcx+10h]
0x180019ba0  call    WPP_SF_
0x180019ba5  xor     edx, edx; Val
0x180019ba7  lea     r8d, [rdx+50h]; Size
0x180019bab  lea     rcx, [rbp+40h+var_90]; void *
0x180019baf  call    memset_0
0x180019bb4  nop
0x180019bb5  xor     ebx, ebx
0x180019bb7  mov     [rsp+140h+var_100], rbx
0x180019bbc  lea     edi, [rbx+1]
0x180019bbf  lea     r8d, [rbx+4]
0x180019bc3  mov     edx, edi
0x180019bc5  mov     rcx, rsi
0x180019bc8  call    ?ChangeConnectionType@TetheringService@@AEAAHW4_TETHERING_CONNECTION_TYPE@@0@Z; TetheringService::ChangeConnectionType(_TETHERING_CONNECTION_TYPE,_TETHERING_CONNECTION_TYPE)
0x180019bcd  mov     [rsi+678h], eax
0x180019bd3  xorps   xmm0, xmm0
0x180019bd6  movups  xmmword ptr [rbp+40h+var_40.Data1], xmm0
0x180019bda  mov     rax, [rsi+508h]
0x180019be1  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180019be8  jnz     short loc_180019C13
0x180019bea  mov     rax, [rsi+510h]
0x180019bf1  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180019bf8  jnz     short loc_180019C13
0x180019bfa  lea     r8, [rbp+40h+var_40]
0x180019bfe  lea     edx, [rbx+2]
0x180019c01  mov     ecx, edi
0x180019c03  call    ?GetDefaultInterface@InterfaceMgr@@SAJW4_TETHERING_INTERFACE_TYPE@@W4_TETHERING_CONNECTION_TYPE@@PEAU_GUID@@@Z; InterfaceMgr::GetDefaultInterface(_TETHERING_INTERFACE_TYPE,_TETHERING_CONNECTION_TYPE,_GUID *)
0x180019c08  mov     edi, eax
0x180019c0a  test    eax, eax
0x180019c0c  jns     short loc_180019C1F
0x180019c0e  jmp     loc_180019E48
0x180019c13  movups  xmm0, xmmword ptr [rsi+508h]
0x180019c1a  movdqu  xmmword ptr [rbp+40h+var_40.Data1], xmm0
0x180019c1f  xorps   xmm0, xmm0
0x180019c22  movups  xmmword ptr [rbp+40h+var_30.Data1], xmm0
0x180019c26  lea     r8, [rbp+40h+var_30]
0x180019c2a  mov     edx, 4
0x180019c2f  lea     ecx, [rdx-2]
0x180019c32  call    ?GetDefaultInterface@InterfaceMgr@@SAJW4_TETHERING_INTERFACE_TYPE@@W4_TETHERING_CONNECTION_TYPE@@PEAU_GUID@@@Z; InterfaceMgr::GetDefaultInterface(_TETHERING_INTERFACE_TYPE,_TETHERING_CONNECTION_TYPE,_GUID *)
0x180019c37  mov     edi, eax
0x180019c39  test    eax, eax
0x180019c3b  js      loc_180019E48
0x180019c41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019c48  mov     ecx, 220h; unsigned __int64
0x180019c4d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019c52  mov     [rsp+140h+var_F8], rax
0x180019c57  test    rax, rax
0x180019c5a  jz      short loc_180019C6E
0x180019c5c  mov     edx, 4; unsigned int
0x180019c61  mov     rcx, rax; this
0x180019c64  call    ??0TetheringSessionTelemetry@@QEAA@K@Z; TetheringSessionTelemetry::TetheringSessionTelemetry(ulong)
0x180019c69  mov     rbx, rax
0x180019c6c  jmp     short loc_180019C70
0x180019c6e  xor     ebx, ebx
0x180019c70  mov     [rsp+140h+var_100], rbx
0x180019c75  mov     rcx, rbx; struct TetheringSessionTelemetry *
0x180019c78  call    ?StartGlobalTelemetrySession@@YAJPEAVTetheringSessionTelemetry@@@Z; StartGlobalTelemetrySession(TetheringSessionTelemetry *)
0x180019c7d  mov     edi, eax
0x180019c7f  test    eax, eax
0x180019c81  jns     short loc_180019CDF
0x180019c83  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c8a  cmp     rcx, r15
0x180019c8d  jz      loc_180019D51
0x180019c93  test    byte ptr [rcx+1Ch], 8
0x180019c97  jz      loc_180019D51
0x180019c9d  test    rbx, rbx
0x180019ca0  jz      short loc_180019CBC
0x180019ca2  mov     rcx, rbx; this
0x180019ca5  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x180019caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019cb1  test    eax, eax
0x180019cb3  lea     rax, aTrue_0; "true"
0x180019cba  jnz     short loc_180019CC3
0x180019cbc  lea     rax, aFalse; "false"
0x180019cc3  mov     r9d, ebx
0x180019cc6  mov     edx, 105h
0x180019ccb  mov     dword ptr [rsp+140h+var_118], edi
0x180019ccf  mov     qword ptr [rsp+140h+var_120], rax
0x180019cd4  mov     rcx, [rcx+10h]
0x180019cd8  call    WPP_SF_lsd
0x180019cdd  jmp     short loc_180019D51
0x180019cdf  xor     edx, edx; Val
0x180019ce1  lea     r8d, [rdx+50h]; Size
0x180019ce5  lea     rcx, [rsp+140h+var_E0]; void *
0x180019cea  call    memset_0
0x180019cef  lea     rax, [rbp+40h+var_40]
0x180019cf3  mov     [rsp+140h+var_E0], rax
0x180019cf8  lea     rax, [rbp+40h+var_30]
0x180019cfc  mov     [rsp+140h+var_D8], rax
0x180019d01  mov     rcx, rbx; this
0x180019d04  call    ?GetId@TetheringSessionTelemetry@@QEAAPEAU_GUID@@XZ; TetheringSessionTelemetry::GetId(void)
0x180019d09  mov     rdx, rax; struct _GUID *
0x180019d0c  lea     r8, [rsp+140h+var_E0]; struct TetheringServiceTelemetry::SESSION_DATA *
0x180019d11  call    ?SetSessionData@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@AEBUSESSION_DATA@1@@Z; TetheringServiceTelemetry::SetSessionData(_GUID *,TetheringServiceTelemetry::SESSION_DATA const &)
0x180019d16  test    rbx, rbx
0x180019d19  jz      loc_180019EAE
0x180019d1f  lea     r8, [rbp+40h+var_90]; struct TetheringServiceTelemetry::SESSION_DATA *
0x180019d23  mov     rdx, rbx; struct TetheringSessionTelemetry *
0x180019d26  call    ?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z; TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)
0x180019d2b  mov     rdx, [rbp+40h+var_58]
0x180019d2f  mov     dword ptr [rdx+8], 0
0x180019d36  mov     eax, [rsi+678h]
0x180019d3c  mov     [rdx+4], eax
0x180019d3f  mov     eax, [rsi+678h]
0x180019d45  mov     [rdx], eax
0x180019d47  lea     rcx, [rbx+10h]; SRWLock
0x180019d4b  call    cs:__imp_ReleaseSRWLockExclusive
0x180019d51  mov     [rsp+140h+var_118], 0; unsigned __int16 *
0x180019d5a  mov     [rsp+140h+var_120], 1; unsigned int
0x180019d62  xor     r9d, r9d; struct _TETHERING_SESSION_CONNECTION_SETTINGS *
0x180019d65  lea     r8, [rbp+40h+var_30]; struct _GUID *
0x180019d69  lea     rdx, [rbp+40h+var_40]; struct _GUID *
0x180019d6d  mov     rcx, rsi; this
0x180019d70  call    ?StartSharingInternal@TetheringService@@AEAAJPEBU_GUID@@0QEAU_TETHERING_SESSION_CONNECTION_SETTINGS@@KPEBG@Z; TetheringService::StartSharingInternal(_GUID const *,_GUID const *,_TETHERING_SESSION_CONNECTION_SETTINGS * const,ulong,ushort const *)
0x180019d75  mov     edi, eax
0x180019d77  test    eax, eax
0x180019d79  jns     short loc_180019DB2
0x180019d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d82  cmp     rcx, r15
0x180019d85  jz      loc_180019E73
0x180019d8b  test    byte ptr [rcx+1Ch], 1
0x180019d8f  jz      loc_180019E4F
0x180019d95  mov     edx, 106h
0x180019d9a  mov     r9d, eax
0x180019d9d  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019da4  mov     rcx, [rcx+10h]
0x180019da8  call    WPP_SF_d
0x180019dad  jmp     loc_180019E48
0x180019db2  cmp     cs:?g_lTraceLoggingRegistered@@3JA, 0; long g_lTraceLoggingRegistered
0x180019db9  jl      loc_180019E48
0x180019dbf  mov     eax, cs:dword_180041008
0x180019dc5  cmp     eax, 5
0x180019dc8  jbe     short loc_180019E48
0x180019dca  mov     rcx, cs:qword_180041020
0x180019dd1  mov     rax, cs:qword_180041018
0x180019dd8  mov     rdx, 400000000000h
0x180019de2  test    rdx, rax
0x180019de5  jz      short loc_180019E48
0x180019de7  mov     rax, rcx
0x180019dea  and     rax, rdx
0x180019ded  cmp     rax, rcx
0x180019df0  jnz     short loc_180019E48
0x180019df2  mov     dword ptr [rsp+140h+var_100], edi
0x180019df6  lea     rax, [rbp+40h+var_30]
0x180019dfa  mov     [rsp+140h+var_F0], rax
0x180019dff  lea     rax, [rbp+40h+var_40]
0x180019e03  mov     [rsp+140h+var_E8], rax
0x180019e08  lea     rax, sourceString
0x180019e0f  mov     [rsp+140h+var_F8], rax
0x180019e14  lea     rax, [rsp+140h+var_100]
0x180019e19  mov     [rsp+140h+var_108], rax
0x180019e1e  lea     rax, [rsp+140h+var_F0]
0x180019e23  mov     [rsp+140h+var_110], rax
0x180019e28  lea     rax, [rsp+140h+var_E8]
0x180019e2d  mov     [rsp+140h+var_118], rax
0x180019e32  lea     rax, [rsp+140h+var_F8]
0x180019e37  mov     qword ptr [rsp+140h+var_120], rax
0x180019e3c  lea     rdx, byte_180039ADB
0x180019e43  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180019e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e4f  cmp     rcx, r15
0x180019e52  jz      short loc_180019E73
0x180019e54  test    byte ptr [rcx+1Ch], 8
0x180019e58  jz      short loc_180019E73
0x180019e5a  mov     edx, 107h
0x180019e5f  mov     r9d, edi
0x180019e62  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019e69  mov     rcx, [rcx+10h]
0x180019e6d  call    WPP_SF_d
0x180019e72  nop
0x180019e73  test    rbx, rbx
0x180019e76  jz      short loc_180019E88
0x180019e78  mov     rax, [rbx]
0x180019e7b  mov     rcx, rbx
0x180019e7e  mov     rax, [rax+10h]
0x180019e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e87  nop
0x180019e88  mov     eax, edi
0x180019e8a  mov     rcx, [rbp+40h+var_20]
0x180019e8e  xor     rcx, rsp; StackCookie
0x180019e91  call    __security_check_cookie
0x180019e96  lea     r11, [rsp+140h+var_10]
0x180019e9e  mov     rbx, [r11+28h]
0x180019ea2  mov     rsi, [r11+30h]
0x180019ea6  mov     rsp, r11
0x180019ea9  pop     r15
0x180019eab  pop     rdi
0x180019eac  pop     rbp
0x180019ead  retn
0x180019eae  mov     ecx, 80004005h; int
0x180019eb3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
