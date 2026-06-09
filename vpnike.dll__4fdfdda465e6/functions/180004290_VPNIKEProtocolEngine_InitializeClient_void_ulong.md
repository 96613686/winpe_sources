# VPNIKEProtocolEngine::InitializeClient(void *,ulong)

- ea: `0x180004290`
- end: `0x180004634`
- name: `?InitializeClient@VPNIKEProtocolEngine@@UEAAKPEAXK@Z`
- size: `932`
- prototype: `__int64 __fastcall(VPNIKEProtocolEngine *this, void *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001514`
- `0x180004290`
- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x180007e74`
- `0x18000aefc`
- `0x18002d860`
- `0x18004b4c8`
- `0x180058978`
- `0x18005e148`
- `0x18006ba70`
- `0x18006bb4c`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `rasman!RasSendProtocolResultToRasman` at `0x18000440e`
- `rasman!RasDeviceGetInfo` at `0x180004382`
- `rasman!RasSetTunnelEndPoints` at `0x180004400`
- `rasman!RasPortGetStatisticsEx` at `0x180004390`
- `rasman!RasDeAllocateRoute` at `0x18000441c`
- `rasman!RasGetKey` at `0x1800043ac`
- `rasman!RasUpdateDefaultRouteSettings` at `0x180004438`
- `rasman!RasAllocateRoute` at `0x18000439e`
- `rasman!RasPortGetBundle` at `0x1800043c8`
- `rasman!RasProtocolStarted` at `0x1800043e4`
- `rasman!RasSetConnectionUserData` at `0x1800043d6`
- `rasman!RasActivateRoute` at `0x18000442a`
- `rasman!RasGetTimeSinceLastActivity` at `0x1800043f2`
- `rasman!RasGetPortUserData` at `0x1800043ba`

## string_xrefs

- `0x18000434a`: `VPNIKEProtocolEngine::InitializeClient`
- `0x180004466`: `BaseProtocolEngine::Initialize failed`

## pseudocode

```c
__int64 __fastcall VPNIKEProtocolEngine::InitializeClient(VPNIKEProtocolEngine *this, void *a2)
{
  VPNIKEProtocolEngine *v3; // rdi
  const wchar_t *v4; // r8
  struct BaseConnectionFactory *Instance; // rax
  struct VPNIKEIOCTLHelper *v6; // rax
  unsigned int v7; // eax
  SynchronizationEventManager *v8; // rax
  SynchronizationEventManager *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v13; // [rsp+20h] [rbp-878h] BYREF
  SynchronizationEventManager *v14; // [rsp+28h] [rbp-870h] BYREF
  VPNIKEProtocolEngine *v15; // [rsp+30h] [rbp-868h]
  __int64 v16; // [rsp+38h] [rbp-860h] BYREF
  __int128 v17; // [rsp+40h] [rbp-858h]
  __int128 v18; // [rsp+50h] [rbp-848h]
  __int64 v19; // [rsp+60h] [rbp-838h]
  int v20; // [rsp+68h] [rbp-830h]
  int v21; // [rsp+6Ch] [rbp-82Ch]
  int v22; // [rsp+70h] [rbp-828h] BYREF
  _BYTE v23[2044]; // [rsp+74h] [rbp-824h] BYREF

  v3 = this;
  v15 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  }
  v13 = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = -1;
  v21 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"VPNIKEProtocolEngine::InitializeClient",
      &v13,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  LODWORD(v14) = 0;
  GetProcessLowBoxStatus(&v14);
  if ( !(_DWORD)v14 )
    DebugInitEx("VPNIKE");
  *(&VPNIKEProtocolEngine::PEHelperFunctions + 1) = RasDeviceGetInfo;
  *(_QWORD *)&xmmword_1800AA960 = RasPortGetStatisticsEx;
  *((_QWORD *)&xmmword_1800AA960 + 1) = RasAllocateRoute;
  *(_QWORD *)&xmmword_1800AA970 = RasGetKey;
  *((_QWORD *)&xmmword_1800AA970 + 1) = RasGetPortUserData;
  *(_QWORD *)&xmmword_1800AA980 = RasPortGetBundle;
  *((_QWORD *)&xmmword_1800AA980 + 1) = RasSetConnectionUserData;
  *(_QWORD *)&xmmword_1800AA990 = RasProtocolStarted;
  *((_QWORD *)&xmmword_1800AA990 + 1) = RasGetTimeSinceLastActivity;
  *(_QWORD *)&xmmword_1800AA9A0 = RasSetTunnelEndPoints;
  *((_QWORD *)&xmmword_1800AA9A0 + 1) = RasSendProtocolResultToRasman;
  *(_QWORD *)&xmmword_1800AA9B0 = RasDeAllocateRoute;
  *((_QWORD *)&xmmword_1800AA9B0 + 1) = RasActivateRoute;
  *(_QWORD *)&xmmword_1800AA9C0 = RasUpdateDefaultRouteSettings;
  v13 = BaseProtocolEngine::Initialize(v3, a2);
  if ( v13 )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_33;
    v4 = L"BaseProtocolEngine::Initialize failed";
    goto LABEL_12;
  }
  Instance = VPNIKEConnectionFactory::GetInstance();
  *((_QWORD *)v3 + 1) = Instance;
  if ( !Instance )
  {
    v13 = 14;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v4 = L"VPNIKEConnectionFactory::GetInstance failed";
LABEL_12:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, v4);
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  v6 = VPNIKEIOCTLHelper::GetInstance();
  *((_QWORD *)v3 + 13) = v6;
  if ( !v6 )
  {
    v13 = 20;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v4 = L"VPNIKEIOCTLHelper::GetInstance failed";
      goto LABEL_12;
    }
LABEL_34:
    (*(void (__fastcall **)(VPNIKEProtocolEngine *))(*(_QWORD *)v3 + 24LL))(v3);
    goto LABEL_35;
  }
  v7 = IPv4Helper::InitializeHelper(1u);
  v13 = v7;
  if ( v7 )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v22, L"IPv4Helper::InitializeHelper failed %d", v7);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v4 = (const wchar_t *)&v22;
        goto LABEL_12;
      }
    }
  }
  else
  {
    try
    {
      v8 = (SynchronizationEventManager *)operator new(0x9E8u);
      v14 = v8;
      if ( v8 )
        v9 = SynchronizationEventManager::SynchronizationEventManager(v8);
      else
        v9 = 0;
      *((_QWORD *)v3 + 5) = v9;
    }
    catch ( ... )
    {
      v13 = 14;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v22) = 0;
        FormatRRASErrorString(&v22, L"SynchronizationEventManager creation failed %d", 14);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v22);
      }
      v3 = v15;
      goto LABEL_33;
    }
    v10 = BFEHandler::EnableIPsecConnectionMonitoring();
    v13 = v10;
    if ( v10 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v22) = 0;
        FormatRRASErrorString(&v22, L"EnableIPsecConnectionMonitoring failed with %d.", v10);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v22);
      }
      v13 = 0;
    }
    *((_DWORD *)v3 + 32) |= 1u;
  }
LABEL_33:
  if ( v13 )
    goto LABEL_34;
LABEL_35:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v13);
  }
  v11 = v13;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v11;
}

```

## disassembly

```asm
0x180004290  mov     [rsp+arg_10], rbx
0x180004295  push    rsi
0x180004296  push    rdi
0x180004297  push    r14
0x180004299  sub     rsp, 880h
0x1800042a0  mov     rax, cs:__security_cookie
0x1800042a7  xor     rax, rsp
0x1800042aa  mov     [rsp+898h+var_28], rax
0x1800042b2  mov     r14, rdx
0x1800042b5  mov     rdi, rcx
0x1800042b8  mov     [rsp+898h+var_868], rcx
0x1800042bd  lea     rsi, WPP_GLOBAL_Control
0x1800042c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042cb  cmp     rcx, rsi
0x1800042ce  jz      short loc_1800042F1
0x1800042d0  test    byte ptr [rcx+1Ch], 1
0x1800042d4  jz      short loc_1800042F1
0x1800042d6  cmp     byte ptr [rcx+19h], 6
0x1800042da  jb      short loc_1800042F1
0x1800042dc  mov     edx, 0Fh
0x1800042e1  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x1800042e8  mov     rcx, [rcx+10h]
0x1800042ec  call    WPP_SF_
0x1800042f1  xor     ebx, ebx
0x1800042f3  mov     [rsp+898h+var_878], ebx
0x1800042f7  mov     [rsp+898h+var_828], ebx
0x1800042fb  xor     edx, edx; Val
0x1800042fd  mov     r8d, 7FCh; Size
0x180004303  lea     rcx, [rsp+898h+var_824]; void *
0x180004308  call    memset_0
0x18000430d  xorps   xmm0, xmm0
0x180004310  movdqu  [rsp+898h+var_858], xmm0
0x180004316  mov     [rsp+898h+var_860], rbx
0x18000431b  xorps   xmm1, xmm1
0x18000431e  movdqu  [rsp+898h+var_848], xmm1
0x180004324  mov     [rsp+898h+var_838], rbx
0x180004329  mov     [rsp+898h+var_830], 0FFFFFFFFh
0x180004331  mov     [rsp+898h+var_82C], ebx
0x180004335  test    cs:byte_1800AA941, 8
0x18000433c  jz      short loc_18000435B
0x18000433e  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180004345  lea     r8, [rsp+898h+var_878]; unsigned int *
0x18000434a  lea     rdx, aVpnikeprotocol_4; "VPNIKEProtocolEngine::InitializeClient"
0x180004351  lea     rcx, [rsp+898h+var_860]; this
0x180004356  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18000435b  mov     dword ptr [rsp+898h+var_870], ebx
0x18000435f  lea     rcx, [rsp+898h+var_870]
0x180004364  call    GetProcessLowBoxStatus
0x180004369  cmp     dword ptr [rsp+898h+var_870], ebx
0x18000436d  jnz     short loc_180004382
0x18000436f  lea     r8, g_dwTraceId
0x180004376  lea     rcx, aVpnike; "VPNIKE"
0x18000437d  call    DebugInitEx
0x180004382  mov     rax, cs:__imp_RasDeviceGetInfo
0x180004389  mov     qword ptr cs:?PEHelperFunctions@VPNIKEProtocolEngine@@2U_PROTOCOL_ENGINE_HELPER_FUNCTIONS@@A+8, rax; _PROTOCOL_ENGINE_HELPER_FUNCTIONS VPNIKEProtocolEngine::PEHelperFunctions
0x180004390  mov     rax, cs:__imp_RasPortGetStatisticsEx
0x180004397  mov     qword ptr cs:xmmword_1800AA960, rax
0x18000439e  mov     rax, cs:__imp_RasAllocateRoute
0x1800043a5  mov     qword ptr cs:xmmword_1800AA960+8, rax
0x1800043ac  mov     rax, cs:__imp_RasGetKey
0x1800043b3  mov     qword ptr cs:xmmword_1800AA970, rax
0x1800043ba  mov     rax, cs:__imp_RasGetPortUserData
0x1800043c1  mov     qword ptr cs:xmmword_1800AA970+8, rax
0x1800043c8  mov     rax, cs:__imp_RasPortGetBundle
0x1800043cf  mov     qword ptr cs:xmmword_1800AA980, rax
0x1800043d6  mov     rax, cs:__imp_RasSetConnectionUserData
0x1800043dd  mov     qword ptr cs:xmmword_1800AA980+8, rax
0x1800043e4  mov     rax, cs:__imp_RasProtocolStarted
0x1800043eb  mov     qword ptr cs:xmmword_1800AA990, rax
0x1800043f2  mov     rax, cs:__imp_RasGetTimeSinceLastActivity
0x1800043f9  mov     qword ptr cs:xmmword_1800AA990+8, rax
0x180004400  mov     rax, cs:__imp_RasSetTunnelEndPoints
0x180004407  mov     qword ptr cs:xmmword_1800AA9A0, rax
0x18000440e  mov     rax, cs:__imp_RasSendProtocolResultToRasman
0x180004415  mov     qword ptr cs:xmmword_1800AA9A0+8, rax
0x18000441c  mov     rax, cs:__imp_RasDeAllocateRoute
0x180004423  mov     qword ptr cs:xmmword_1800AA9B0, rax
0x18000442a  mov     rax, cs:__imp_RasActivateRoute
0x180004431  mov     qword ptr cs:xmmword_1800AA9B0+8, rax
0x180004438  mov     rax, cs:__imp_RasUpdateDefaultRouteSettings
0x18000443f  mov     qword ptr cs:xmmword_1800AA9C0, rax
0x180004446  mov     rdx, r14; void *
0x180004449  mov     rcx, rdi; this
0x18000444c  call    ?Initialize@BaseProtocolEngine@@QEAAKPEAXK@Z; BaseProtocolEngine::Initialize(void *,ulong)
0x180004451  mov     [rsp+898h+var_878], eax
0x180004455  test    eax, eax
0x180004457  jz      short loc_180004485
0x180004459  test    cs:byte_1800AA941, 4
0x180004460  jz      loc_1800045B9
0x180004466  lea     r8, aBaseprotocolen_3; "BaseProtocolEngine::Initialize failed"
0x18000446d  lea     rdx, RasVpnIkeTraceError
0x180004474  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000447b  call    McTemplateU0z_EventWriteTransfer
0x180004480  jmp     loc_1800045B9
0x180004485  call    ?GetInstance@VPNIKEConnectionFactory@@SAPEAVBaseConnectionFactory@@XZ; VPNIKEConnectionFactory::GetInstance(void)
0x18000448a  mov     [rdi+8], rax
0x18000448e  test    rax, rax
0x180004491  jnz     short loc_1800044B1
0x180004493  mov     [rsp+898h+var_878], 0Eh
0x18000449b  test    cs:byte_1800AA941, 4
0x1800044a2  jz      loc_1800045BF
0x1800044a8  lea     r8, aVpnikeconnecti_15; "VPNIKEConnectionFactory::GetInstance fa"...
0x1800044af  jmp     short loc_18000446D
0x1800044b1  call    ?GetInstance@VPNIKEIOCTLHelper@@SAPEAV1@XZ; VPNIKEIOCTLHelper::GetInstance(void)
0x1800044b6  mov     [rdi+68h], rax
0x1800044ba  test    rax, rax
0x1800044bd  jnz     short loc_1800044DD
0x1800044bf  mov     [rsp+898h+var_878], 14h
0x1800044c7  test    cs:byte_1800AA941, 4
0x1800044ce  jz      loc_1800045BF
0x1800044d4  lea     r8, aVpnikeioctlhel_2; "VPNIKEIOCTLHelper::GetInstance failed"
0x1800044db  jmp     short loc_18000446D
0x1800044dd  mov     cl, 1; unsigned __int8
0x1800044df  call    ?InitializeHelper@IPv4Helper@@SAKE@Z; IPv4Helper::InitializeHelper(uchar)
0x1800044e4  mov     [rsp+898h+var_878], eax
0x1800044e8  test    eax, eax
0x1800044ea  jz      short loc_180004529
0x1800044ec  test    cs:byte_1800AA941, 4
0x1800044f3  jz      loc_1800045B9
0x1800044f9  mov     word ptr [rsp+898h+var_828], bx
0x1800044fe  mov     r8d, eax
0x180004501  lea     rdx, aIpv4helperInit; "IPv4Helper::InitializeHelper failed %d"
0x180004508  lea     rcx, [rsp+898h+var_828]
0x18000450d  call    FormatRRASErrorString
0x180004512  test    cs:byte_1800AA941, 4
0x180004519  jz      loc_1800045B9
0x18000451f  lea     r8, [rsp+898h+var_828]
0x180004524  jmp     loc_18000446D
0x180004529  mov     ecx, 9E8h; Size
0x18000452e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004533  mov     [rsp+898h+var_870], rax
0x180004538  test    rax, rax
0x18000453b  jz      short loc_180004547
0x18000453d  mov     rcx, rax; this
0x180004540  call    ??0SynchronizationEventManager@@QEAA@XZ; SynchronizationEventManager::SynchronizationEventManager(void)
0x180004545  jmp     short loc_18000454A
0x180004547  mov     rax, rbx
0x18000454a  mov     [rdi+28h], rax
0x18000454e  call    ?EnableIPsecConnectionMonitoring@BFEHandler@@SAKXZ; BFEHandler::EnableIPsecConnectionMonitoring(void)
0x180004553  mov     [rsp+898h+var_878], eax
0x180004557  test    eax, eax
0x180004559  jz      short loc_1800045A2
0x18000455b  test    cs:byte_1800AA941, 4
0x180004562  jz      short loc_18000459E
0x180004564  mov     word ptr [rsp+898h+var_828], bx
0x180004569  mov     r8d, eax
0x18000456c  lea     rdx, aEnableipseccon; "EnableIPsecConnectionMonitoring failed "...
0x180004573  lea     rcx, [rsp+898h+var_828]
0x180004578  call    FormatRRASErrorString
0x18000457d  test    cs:byte_1800AA941, 4
0x180004584  jz      short loc_18000459E
0x180004586  lea     r8, [rsp+898h+var_828]
0x18000458b  lea     rdx, RasVpnIkeTraceError
0x180004592  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004599  call    McTemplateU0z_EventWriteTransfer
0x18000459e  mov     [rsp+898h+var_878], ebx
0x1800045a2  or      dword ptr [rdi+80h], 1
0x1800045a9  jmp     short loc_1800045B9
0x1800045ab  lea     rsi, WPP_GLOBAL_Control
0x1800045b2  xor     ebx, ebx
0x1800045b4  mov     rdi, [rsp+898h+var_868]
0x1800045b9  cmp     [rsp+898h+var_878], ebx
0x1800045bd  jz      short loc_1800045CE
0x1800045bf  mov     rax, [rdi]
0x1800045c2  mov     rcx, rdi
0x1800045c5  mov     rax, [rax+18h]
0x1800045c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045d5  cmp     rcx, rsi
0x1800045d8  jz      short loc_180004600
0x1800045da  test    byte ptr [rcx+1Ch], 1
0x1800045de  jz      short loc_180004600
0x1800045e0  cmp     byte ptr [rcx+19h], 6
0x1800045e4  jb      short loc_180004600
0x1800045e6  mov     edx, 10h
0x1800045eb  mov     r9d, [rsp+898h+var_878]
0x1800045f0  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x1800045f7  mov     rcx, [rcx+10h]
0x1800045fb  call    WPP_SF_d
0x180004600  mov     ebx, [rsp+898h+var_878]
0x180004604  lea     rcx, [rsp+898h+var_860]; this
0x180004609  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18000460e  mov     eax, ebx
0x180004610  mov     rcx, [rsp+898h+var_28]
0x180004618  xor     rcx, rsp; StackCookie
0x18000461b  call    __security_check_cookie
0x180004620  mov     rbx, [rsp+898h+arg_10]
0x180004628  add     rsp, 880h
0x18000462f  pop     r14
0x180004631  pop     rdi
0x180004632  pop     rsi
0x180004633  retn
```
