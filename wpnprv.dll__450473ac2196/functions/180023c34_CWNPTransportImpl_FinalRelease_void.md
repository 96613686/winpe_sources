# CWNPTransportImpl::FinalRelease(void)

- ea: `0x180023c34`
- end: `0x180023e9b`
- name: `?FinalRelease@CWNPTransportImpl@@IEAAXXZ`
- size: `615`
- prototype: `void __fastcall(CWNPTransportImpl *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800211ec`

## callees

- `0x18000865c`
- `0x18000ba54`
- `0x18000c3b4`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180021614`
- `0x180021640`
- `0x180021b0c`
- `0x180022dcc`
- `0x180023c34`
- `0x18002aa30`
- `0x18002b200`
- `0x180030d10`
- `0x1800317d4`
- `0x180031b64`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSUnRegisterSessionNotification` at `0x180023e38`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSUnRegisterSessionNotification` at `0x180023e38`
- `WS2_32!__imp_WSAGetLastError` at `0x180023dab`
- `WS2_32!__imp_WSAGetLastError` at `0x180023dab`
- `WS2_32!__imp_WSACleanup` at `0x180023da1`
- `WS2_32!__imp_WSACleanup` at `0x180023da1`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180023e02`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180023e02`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall CWNPTransportImpl::FinalRelease(CWNPTransportImpl *this)
{
  CWNPTransportImpl *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int Error; // eax
  bool v15; // sf
  void *v16; // rcx
  DWORD v17; // eax
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (CWNPTransportImpl *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids);
  }
  if ( (*((_BYTE *)this + 216) & 1) == 0 )
    CWNPTransportImpl::CleanupLongRunningTransport(this);
  CWNPTransportImpl::DeleteWakeTimer(v2, (void **)this + 26);
  CWNPTransportImpl::ReleaseConnectionContext(this);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 224, v3, v4, v5);
  v8 = *((_QWORD *)this + 46);
  *((_QWORD *)this + 46) = 0;
  if ( v8 )
    std::default_delete<SleepStudyManager>::operator()();
  v9 = *((_QWORD *)this + 43);
  *((_QWORD *)this + 43) = 0;
  if ( v9 )
    std::default_delete<CWNPBaseInterfaceSelector>::operator()();
  v10 = *((_QWORD *)this + 14);
  if ( v10 )
    *(_QWORD *)(v10 + 200) = 0;
  v11 = *((_QWORD *)this + 16);
  if ( v11 )
  {
    LOBYTE(v6) = (*((_BYTE *)this + 216) & 1) == 0;
    v12 = PdcDeactivateNetwork(v11, 6, v6, v7);
    if ( v12 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids,
        (unsigned int)v12);
    }
    *((_QWORD *)this + 16) = 0;
  }
  if ( *((_BYTE *)this + 161) )
  {
    v13 = PdcUninitialize();
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids,
        (unsigned int)v13);
    }
  }
  if ( *((_BYTE *)this + 160) && WSACleanup() )
  {
    Error = WSAGetLastError();
    v15 = Error < 0;
    if ( Error > 0 )
    {
      Error = (unsigned __int16)Error | 0x80070000;
      v15 = Error < 0;
    }
    if ( v15
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids,
        (unsigned int)Error);
    }
  }
  if ( (*((_BYTE *)this + 216) & 1) == 0 )
  {
    v16 = (void *)*((_QWORD *)this + 55);
    if ( v16 )
    {
      v17 = PowerSettingUnregisterNotification(v16);
      if ( v17 )
      {
        wil::details::in1diag3::Return_Win32(retaddr, (void *)0xE30, v18, (const char *)v17, v20);
        goto LABEL_43;
      }
      *((_QWORD *)this + 55) = 0;
    }
    if ( (unsigned __int8)IsWTSRegisterSessionNotificationPresent()
      && !WTSUnRegisterSessionNotification(*((HWND *)this + 8)) )
    {
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0xE35,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnptransimpl.cpp",
        v19);
    }
  }
LABEL_43:
  CMsgrWndBase::DestroyMsgrWindow((CWNPTransportImpl *)((char *)this + 40));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids);
  }
}

```

## disassembly

```asm
0x180023c34  mov     [rsp+arg_0], rbx
0x180023c39  mov     [rsp+arg_8], rbp
0x180023c3e  push    r15; unsigned int
0x180023c40  sub     rsp, 20h
0x180023c44  mov     rbx, rcx
0x180023c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c4e  lea     rbp, WPP_GLOBAL_Control
0x180023c55  lea     r15, WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids
0x180023c5c  cmp     rcx, rbp
0x180023c5f  jz      short loc_180023C7E
0x180023c61  test    byte ptr [rcx+1Ch], 4
0x180023c65  jz      short loc_180023C7E
0x180023c67  cmp     byte ptr [rcx+19h], 6
0x180023c6b  jb      short loc_180023C7E
0x180023c6d  mov     rcx, [rcx+10h]
0x180023c71  mov     edx, 20h ; ' '
0x180023c76  mov     r8, r15
0x180023c79  call    WPP_SF_
0x180023c7e  test    byte ptr [rbx+0D8h], 1
0x180023c85  jnz     short loc_180023C8F
0x180023c87  mov     rcx, rbx; this
0x180023c8a  call    ?CleanupLongRunningTransport@CWNPTransportImpl@@AEAAXXZ; CWNPTransportImpl::CleanupLongRunningTransport(void)
0x180023c8f  lea     rdx, [rbx+0D0h]; void **
0x180023c96  call    ?DeleteWakeTimer@CWNPTransportImpl@@AEAAXPEAPEAX@Z; CWNPTransportImpl::DeleteWakeTimer(void * *)
0x180023c9b  mov     rcx, rbx; this
0x180023c9e  call    ?ReleaseConnectionContext@CWNPTransportImpl@@AEAAXXZ; CWNPTransportImpl::ReleaseConnectionContext(void)
0x180023ca3  lea     rcx, [rbx+0E0h]
0x180023caa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023caf  mov     rdx, [rbx+170h]
0x180023cb6  mov     qword ptr [rbx+170h], 0
0x180023cc1  test    rdx, rdx
0x180023cc4  jz      short loc_180023CCB
0x180023cc6  call    ??R?$default_delete@VSleepStudyManager@@@std@@QEBAXPEAVSleepStudyManager@@@Z; std::default_delete<SleepStudyManager>::operator()(SleepStudyManager *)
0x180023ccb  mov     rdx, [rbx+158h]
0x180023cd2  mov     qword ptr [rbx+158h], 0
0x180023cdd  test    rdx, rdx
0x180023ce0  jz      short loc_180023CE7
0x180023ce2  call    ??R?$default_delete@VCWNPBaseInterfaceSelector@@@std@@QEBAXPEAVCWNPBaseInterfaceSelector@@@Z; std::default_delete<CWNPBaseInterfaceSelector>::operator()(CWNPBaseInterfaceSelector *)
0x180023ce7  mov     rax, [rbx+70h]
0x180023ceb  test    rax, rax
0x180023cee  jz      short loc_180023CFB
0x180023cf0  mov     qword ptr [rax+0C8h], 0
0x180023cfb  mov     rcx, [rbx+80h]
0x180023d02  test    rcx, rcx
0x180023d05  jz      short loc_180023D5A
0x180023d07  mov     r8b, [rbx+0D8h]
0x180023d0e  mov     edx, 6
0x180023d13  not     r8b
0x180023d16  and     r8b, 1
0x180023d1a  call    ?PdcDeactivateNetwork@@YAJPEAXW4_PDC_REAOSN@@_N@Z; PdcDeactivateNetwork(void *,_PDC_REAOSN,bool)
0x180023d1f  test    eax, eax
0x180023d21  jns     short loc_180023D4F
0x180023d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d2a  cmp     rcx, rbp
0x180023d2d  jz      short loc_180023D4F
0x180023d2f  test    byte ptr [rcx+1Ch], 4
0x180023d33  jz      short loc_180023D4F
0x180023d35  cmp     byte ptr [rcx+19h], 2
0x180023d39  jb      short loc_180023D4F
0x180023d3b  mov     rcx, [rcx+10h]
0x180023d3f  mov     edx, 21h ; '!'
0x180023d44  mov     r9d, eax
0x180023d47  mov     r8, r15
0x180023d4a  call    WPP_SF_d
0x180023d4f  mov     qword ptr [rbx+80h], 0
0x180023d5a  cmp     byte ptr [rbx+0A1h], 0
0x180023d61  jz      short loc_180023D98
0x180023d63  call    ?PdcUninitialize@@YAJXZ; PdcUninitialize(void)
0x180023d68  test    eax, eax
0x180023d6a  jns     short loc_180023D98
0x180023d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d73  cmp     rcx, rbp
0x180023d76  jz      short loc_180023D98
0x180023d78  test    byte ptr [rcx+1Ch], 4
0x180023d7c  jz      short loc_180023D98
0x180023d7e  cmp     byte ptr [rcx+19h], 2
0x180023d82  jb      short loc_180023D98
0x180023d84  mov     rcx, [rcx+10h]
0x180023d88  mov     edx, 23h ; '#'
0x180023d8d  mov     r9d, eax
0x180023d90  mov     r8, r15
0x180023d93  call    WPP_SF_d
0x180023d98  cmp     byte ptr [rbx+0A0h], 0
0x180023d9f  jz      short loc_180023DED
0x180023da1  call    cs:__imp_WSACleanup
0x180023da7  test    eax, eax
0x180023da9  jz      short loc_180023DED
0x180023dab  call    cs:__imp_WSAGetLastError
0x180023db1  test    eax, eax
0x180023db3  jle     short loc_180023DBF
0x180023db5  movzx   eax, ax
0x180023db8  or      eax, 80070000h
0x180023dbd  test    eax, eax
0x180023dbf  jns     short loc_180023DED
0x180023dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023dc8  cmp     rcx, rbp
0x180023dcb  jz      short loc_180023DED
0x180023dcd  test    byte ptr [rcx+1Ch], 4
0x180023dd1  jz      short loc_180023DED
0x180023dd3  cmp     byte ptr [rcx+19h], 2
0x180023dd7  jb      short loc_180023DED
0x180023dd9  mov     rcx, [rcx+10h]
0x180023ddd  mov     edx, 25h ; '%'
0x180023de2  mov     r9d, eax
0x180023de5  mov     r8, r15
0x180023de8  call    WPP_SF_d
0x180023ded  test    byte ptr [rbx+0D8h], 1
0x180023df4  jnz     short loc_180023E58
0x180023df6  mov     rcx, [rbx+1B8h]; RegistrationHandle
0x180023dfd  test    rcx, rcx
0x180023e00  jz      short loc_180023E2B
0x180023e02  call    cs:__imp_PowerSettingUnregisterNotification
0x180023e08  test    eax, eax
0x180023e0a  jz      short loc_180023E20
0x180023e0c  mov     rcx, [rsp+28h]; this
0x180023e11  mov     r9d, eax; char *
0x180023e14  mov     edx, 0E30h; void *
0x180023e19  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023e1e  jmp     short loc_180023E58
0x180023e20  mov     qword ptr [rbx+1B8h], 0
0x180023e2b  call    IsWTSRegisterSessionNotificationPresent
0x180023e30  test    al, al
0x180023e32  jz      short loc_180023E58
0x180023e34  mov     rcx, [rbx+40h]; hWnd
0x180023e38  call    cs:__imp_WTSUnRegisterSessionNotification
0x180023e3e  test    eax, eax
0x180023e40  jnz     short loc_180023E58
0x180023e42  mov     rcx, [rsp+28h]; this
0x180023e47  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023e4e  mov     edx, 0E35h; void *
0x180023e53  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023e58  lea     rcx, [rbx+28h]; this
0x180023e5c  call    ?DestroyMsgrWindow@CMsgrWndBase@@UEAAHXZ; CMsgrWndBase::DestroyMsgrWindow(void)
0x180023e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e68  cmp     rcx, rbp
0x180023e6b  jz      short loc_180023E8A
0x180023e6d  test    byte ptr [rcx+1Ch], 4
0x180023e71  jz      short loc_180023E8A
0x180023e73  cmp     byte ptr [rcx+19h], 6
0x180023e77  jb      short loc_180023E8A
0x180023e79  mov     rcx, [rcx+10h]
0x180023e7d  mov     edx, 27h ; '''
0x180023e82  mov     r8, r15
0x180023e85  call    WPP_SF_
0x180023e8a  mov     rbx, [rsp+28h+arg_0]
0x180023e8f  mov     rbp, [rsp+28h+arg_8]
0x180023e94  add     rsp, 20h
0x180023e98  pop     r15
0x180023e9a  retn
```
