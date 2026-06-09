# WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal(void)

- ea: `0x18005be40`
- end: `0x18005c239`
- name: `?DoActionInternal@CConnectWFDOpenSessionWork@WFDSConMgr@@EEAAXXZ`
- size: `1017`
- prototype: `void __fastcall(WFDSConMgr::CConnectWFDOpenSessionWork *__hidden this)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, installer_update`

## callees

- `0x180002600`
- `0x180006740`
- `0x18002bdc0`
- `0x18002c1c4`
- `0x18002d768`
- `0x18002e078`
- `0x18002e48c`
- `0x180039ec4`
- `0x180039fec`
- `0x18003a228`
- `0x18003a684`
- `0x18003a9d0`
- `0x18003aaa8`
- `0x18003b9a8`
- `0x18003c080`
- `0x180053494`
- `0x180053714`
- `0x180057f54`
- `0x180058334`
- `0x180058458`
- `0x1800593b4`
- `0x18005be40`
- `0x18005c888`
- `0x18005dec4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bf67`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bf67`

## string_xrefs

- `0x18005c1f7`: `WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal`
- `0x18005c227`: `WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal`
- `0x18005c1de`: `Attempted to do WFD Open Session for infrastructure`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal(WFDSConMgr::CConnectWFDOpenSessionWork *this)
{
  WFDSConMgr::CConnectWFDOpenSessionWork *v1; // rbx
  WFDSConMgr::CConnectManager **v2; // rsi
  bool HasWsbAspHandle; // r15
  struct WFDSConMgr::IConfigHelper *ConfigHelper; // rax
  char v5; // al
  char v6; // r15
  WFDSConMgr::CWFDConnectHelper *v7; // r12
  struct WFDSConMgr::IWFDDisconnectListener *StateMachine; // r13
  const unsigned __int8 *RemoteAddress; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  WFDSConMgr::CConnectWFDOpenSessionWork **v12; // rax
  WFDSConMgr::CConnectWFDOpenSessionWork *v13; // rbx
  int Error; // eax
  __int64 v15; // r10
  int v16; // eax
  __int64 v17; // r10
  ULONGLONG v18; // r9
  unsigned int v19; // edi
  WFDSConMgr::CConnectManager **v20; // rbx
  __int64 v21; // rax
  unsigned int v22; // r14d
  unsigned int v23; // esi
  PVOID *v24; // r10
  const WFDSConMgr::CException *v25; // rsi
  int v26; // ecx
  int v27; // eax
  __int64 v28; // r10
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r11
  struct WFDSConMgr::CSessionStateMachine *v32; // rax
  WFDSConMgr::CWFDConnectHelper *v33; // rax
  bool v34; // al
  __int64 v35; // r9
  __int64 v36; // r11
  __int64 v37; // r10
  __int64 v38; // r8
  int v39; // eax
  __int64 v40; // r10
  __int64 v41; // rdx
  char v42; // [rsp+50h] [rbp-118h] BYREF
  char v43; // [rsp+51h] [rbp-117h]
  char v44; // [rsp+52h] [rbp-116h]
  bool v45; // [rsp+53h] [rbp-115h]
  char v46[4]; // [rsp+54h] [rbp-114h] BYREF
  void *v47; // [rsp+58h] [rbp-110h] BYREF
  WFDSConMgr::CConnectWFDOpenSessionWork *v48; // [rsp+60h] [rbp-108h]
  unsigned int v49; // [rsp+68h] [rbp-100h] BYREF
  unsigned int v50; // [rsp+6Ch] [rbp-FCh]
  unsigned int v51; // [rsp+70h] [rbp-F8h] BYREF
  unsigned int v52; // [rsp+74h] [rbp-F4h] BYREF
  const WFDSConMgr::CException *v53; // [rsp+78h] [rbp-F0h] BYREF
  WFDSConMgr::CConnectWFDOpenSessionWork *v54; // [rsp+80h] [rbp-E8h] BYREF
  int v55; // [rsp+88h] [rbp-E0h] BYREF
  WFDSConMgr::CConnectManager **v56; // [rsp+90h] [rbp-D8h]
  ULONGLONG TickCount64; // [rsp+98h] [rbp-D0h]
  _DWORD v58[2]; // [rsp+A0h] [rbp-C8h] BYREF
  const WFDSConMgr::CException *v59; // [rsp+A8h] [rbp-C0h] BYREF
  _BYTE v60[128]; // [rsp+B0h] [rbp-B8h] BYREF

  v1 = this;
  v48 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, this);
  }
  v2 = (WFDSConMgr::CConnectManager **)((char *)v1 + 8);
  if ( (unsigned int)WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(*(_QWORD *)(*((_QWORD *)v1 + 1) + 128LL)) != 1 )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectwork.cpp",
      232,
      L"Attempted to do WFD Open Session for infrastructure",
      v1);
  v56 = (WFDSConMgr::CConnectManager **)((char *)v1 + 8);
  v44 = 0;
  v54 = v1;
  WFDSConMgr::TryCatchTelemetry__lambda_8446f853dd909dc8f92a6b3d2dee06bc___(&v54);
  HasWsbAspHandle = WFDSConMgr::CRemoteDevice::HasWsbAspHandle(*((WFDSConMgr::CRemoteDevice **)*v2 + 16));
  v45 = HasWsbAspHandle;
  v46[0] = 0;
  v49 = 0;
  v52 = 0;
  v55 = 0;
  v51 = 0;
  ConfigHelper = WFDSConMgr::CRemoteDevice::GetConfigHelper(*((WFDSConMgr::CRemoteDevice **)*v2 + 16));
  (*(void (__fastcall **)(struct WFDSConMgr::IConfigHelper *, char *, unsigned int *, unsigned int *, int *, unsigned int *))(*(_QWORD *)ConfigHelper + 152LL))(
    ConfigHelper,
    v46,
    &v49,
    &v52,
    &v55,
    &v51);
  v50 = 0;
  TickCount64 = GetTickCount64();
  v5 = 0;
  v43 = 0;
  v42 = 0;
  v54 = v1;
  while ( 2 )
  {
    try
    {
      if ( v5 )
        lambda_618646fc743ab71dd0f0413086fb56ef_::operator()(&v54, &v42);
      v43 = 0;
      if ( HasWsbAspHandle )
      {
        v6 = 0;
      }
      else
      {
        v6 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v1);
        }
      }
      v7 = (WFDSConMgr::CWFDConnectHelper *)*((_QWORD *)*v2 + 13);
      StateMachine = WFDSConMgr::CRemoteDevice::GetStateMachine(*((WFDSConMgr::CRemoteDevice **)*v2 + 16));
      RemoteAddress = (const unsigned __int8 *)WFDSConMgr::CRemoteDevice::GetRemoteAddress(*((void **)*v2 + 16));
      WFDSConMgr::CWFDConnectHelper::OpenSession(v7, (const unsigned __int8 (*)[6])RemoteAddress, StateMachine, v6);
      if ( v6 )
        *((_BYTE *)*v2 + 160) = 1;
    }
    catch ( const WFDSConMgr::CException *v53 )
    {
      if ( v45 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          Error = WFDSConMgr::CException::GetError(v53);
          WPP_SF_qD(*(_QWORD *)(v15 + 16), 51, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v48, Error);
        }
        throw;
      }
      if ( v43 && !v42 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = WFDSConMgr::CException::GetError(v53);
          WPP_SF_qD(*(_QWORD *)(v17 + 16), 52, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v48, v16);
        }
        throw;
      }
      v18 = GetTickCount64();
      v19 = ++v50;
      v20 = (WFDSConMgr::CConnectManager **)v48;
      v21 = *(_QWORD *)(*((_QWORD *)v48 + 1) + 104LL);
      if ( *(_BYTE *)(v21 + 80) && *(_DWORD *)(v21 + 136) == 163852 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids,
            v48,
            *(_DWORD *)v53);
        }
        goto LABEL_83;
      }
      v22 = v49;
      if ( v19 >= v49 )
      {
        v23 = v51;
LABEL_77:
        if ( !v46[0]
          || WFDSConMgr::CWFDConnectHelper::DeviceNotFound(*(WFDSConMgr::CWFDConnectHelper **)(*((_QWORD *)v48 + 1)
                                                                                             + 104LL)) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25)
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WFDSConMgr::CException::GetError(v53);
            v33 = WFDSConMgr::CConnectManager::WFDHelper(v20[1]);
            v34 = WFDSConMgr::CWFDConnectHelper::DeviceNotFound(v33);
            WPP_SF_qdDDIDl(*(_QWORD *)(v37 + 16), v34, v38, v20, v38, v19, v22, v35 - v36, v23, v34);
          }
          throw;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qdDDID(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(unsigned int *)v53,
            v29,
            v20,
            *(_DWORD *)v53,
            v19,
            v22,
            v30 - v31,
            v23);
        }
LABEL_83:
        v44 = 1;
        WFDSConMgr::CWFDConnectHelper::Reset(*((WFDSConMgr::CWFDConnectHelper **)v20[1] + 13));
        v32 = WFDSConMgr::CRemoteDevice::GetStateMachine(*((WFDSConMgr::CRemoteDevice **)v20[1] + 16));
        WFDSConMgr::CSessionStateMachine::UpdateWFDState(v32, 2);
        v1 = v48;
        v2 = v56;
        break;
      }
      v23 = v51;
      if ( v18 - TickCount64 > v51 )
        goto LABEL_77;
      if ( WFDSConMgr::CWFDConnectHelper::DeviceNotFound(*(WFDSConMgr::CWFDConnectHelper **)(*((_QWORD *)v48 + 1) + 104LL)) )
      {
        v24 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v25 = v53;
        }
        else
        {
          v25 = v53;
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids,
            v20,
            *(_DWORD *)v53);
          v24 = (PVOID *)WPP_GLOBAL_Control;
        }
        v43 = 1;
        v42 = 0;
      }
      else
      {
        v25 = v53;
        v24 = (PVOID *)WPP_GLOBAL_Control;
      }
      v26 = *(_DWORD *)v25;
      if ( (*(_DWORD *)v25 & 0x1FFF0000) == 0x70000 )
        v26 = (unsigned __int16)v26;
      if ( v26 == 1223 )
      {
        if ( v24 != &WPP_GLOBAL_Control && *((_BYTE *)v24 + 25) && (*((_BYTE *)v24 + 28) & 1) != 0 )
        {
          v27 = WFDSConMgr::CException::GetError(v25);
          WPP_SF_qD(*(_QWORD *)(v28 + 16), 57, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v20, v27);
        }
        throw;
      }
      if ( v24 != &WPP_GLOBAL_Control && *((_BYTE *)v24 + 25) >= 3u && (*((_BYTE *)v24 + 28) & 1) != 0 )
        WPP_SF_qDD(v24[2], 58, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v20, *(_DWORD *)v25, v19);
      WFDSConMgr::CWFDConnectHelper::Reset(*((WFDSConMgr::CWFDConnectHelper **)v20[1] + 13));
      WFDSConMgr::CEventWrapper::WaitAllowTimeout(v20 + 12, v58, v52 + v55 * (v19 - 1));
      if ( !v58[1] )
        WFDSConMgr::CException::Throw(
          199,
          "WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal",
          "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectwork.cpp",
          195,
          L"Connect canceled between reconnect retries",
          v20);
      v47 = v20;
      WFDSConMgr::TryCatchTelemetry__lambda_2afaf7eeead46479cc35188dddeb75ee___(&v47);
      v1 = v48;
      v2 = v56;
      if ( v50 >= v49 )
        break;
      HasWsbAspHandle = v45;
      v5 = v43;
      continue;
    }
    break;
  }
  v47 = v1;
  WFDSConMgr::TryCatchTelemetry__lambda_78d2801d00252623a192c2dea2d50cf5___(&v47);
  if ( v44 )
  {
    WFDSConMgr::CEventWrapper::WaitAllowTimeout((char *)v1 + 96, &v47, v52);
    if ( !HIDWORD(v47) )
      WFDSConMgr::CException::Throw(
        199,
        "WFDSConMgr::CConnectWFDOpenSessionWork::DoActionInternal",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectwork.cpp",
        228,
        L"Connect canceled before re-pair",
        v1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v1);
    }
    v47 = v1;
    WFDSConMgr::TryCatchTelemetry__lambda_42202b07dc32095212ff6c16076b80a4___(&v47);
    try
    {
      v42 = 0;
      lambda_618646fc743ab71dd0f0413086fb56ef_::operator()(&v54, &v42);
    }
    catch ( const WFDSConMgr::CException *v59 )
    {
      if ( v42 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v39 = WFDSConMgr::CException::GetError(v59);
          v41 = 62;
          goto LABEL_98;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25)
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v39 = WFDSConMgr::CException::GetError(v59);
        v41 = 61;
LABEL_98:
        WPP_SF_qD(*(_QWORD *)(v40 + 16), v41, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, v48, v39);
      }
      throw;
    }
    WFDSConMgr::CConnectManager::GoToNextState(*v2, 2);
  }
  else
  {
    v10 = *((_QWORD *)*v2 + 16);
    v11 = WFDSConMgr::CWFDConnectHelper::ReleaseWFDHandle(*((_QWORD *)*v2 + 13), v60);
    WFDSConMgr::CRemoteDevice::SetMiracastWFDHandle(v10, v11);
    WFDSConMgr::CWFDSessionHandle::~CWFDSessionHandle((WFDSConMgr::CWFDSessionHandle *)v60);
    if ( !WFDSConMgr::CRemoteDevice::HasSetMediaStreamingMode(*((WFDSConMgr::CRemoteDevice **)*v2 + 16)) )
    {
      v12 = (WFDSConMgr::CConnectWFDOpenSessionWork **)WFDSConMgr::CWFDConnectHelper::SetMediaStreamingModeOn(
                                                         *((_QWORD *)*v2 + 13),
                                                         &v47);
      v13 = *v12;
      *v12 = 0;
      std::unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>::~unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>(&v47);
      v47 = 0;
      v54 = v13;
      WFDSConMgr::CRemoteDevice::OnSetMediaStreamingMode(*((_QWORD *)*v2 + 16), &v54);
      std::unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>::~unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>(&v47);
    }
    WFDSConMgr::CConnectManager::GoToFinalState(*v2);
  }
}

```

## disassembly

```asm
0x18005be40  mov     [rsp+arg_8], rbx
0x18005be45  mov     [rsp+arg_10], rsi
0x18005be4a  push    rdi
0x18005be4b  push    r12
0x18005be4d  push    r13
0x18005be4f  push    r14
0x18005be51  push    r15
0x18005be53  sub     rsp, 140h
0x18005be5a  mov     rax, cs:__security_cookie
0x18005be61  xor     rax, rsp
0x18005be64  mov     [rsp+168h+var_38], rax
0x18005be6c  mov     rbx, rcx
0x18005be6f  mov     [rsp+168h+var_108], rcx
0x18005be74  lea     r14, WPP_GLOBAL_Control
0x18005be7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be82  cmp     rcx, r14
0x18005be85  jz      short loc_18005BEAB
0x18005be87  cmp     byte ptr [rcx+19h], 4
0x18005be8b  jb      short loc_18005BEAB
0x18005be8d  test    byte ptr [rcx+1Ch], 1
0x18005be91  jz      short loc_18005BEAB
0x18005be93  mov     edx, 30h ; '0'
0x18005be98  mov     r9, rbx
0x18005be9b  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18005bea2  mov     rcx, [rcx+10h]
0x18005bea6  call    WPP_SF_q
0x18005beab  lea     rsi, [rbx+8]
0x18005beaf  mov     rcx, [rsi]
0x18005beb2  mov     rcx, [rcx+80h]
0x18005beb9  call    ?GetDafProviderTypeForConnection@CRemoteDevice@WFDSConMgr@@QEBA?AW4DafProvider@2@XZ; WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(void)
0x18005bebe  cmp     eax, 1
0x18005bec1  jnz     loc_18005C1D9
0x18005bec7  mov     [rsp+168h+var_D8], rsi
0x18005becf  xor     edi, edi
0x18005bed1  mov     [rsp+168h+var_116], dil
0x18005bed6  mov     [rsp+168h+var_E8], rbx
0x18005bede  lea     rcx, [rsp+168h+var_E8]
0x18005bee6  call    WFDSConMgr__TryCatchTelemetry__lambda_8446f853dd909dc8f92a6b3d2dee06bc___
0x18005beeb  mov     rcx, [rsi]
0x18005beee  mov     rcx, [rcx+80h]; this
0x18005bef5  call    ?HasWsbAspHandle@CRemoteDevice@WFDSConMgr@@QEAA_NXZ; WFDSConMgr::CRemoteDevice::HasWsbAspHandle(void)
0x18005befa  mov     r15b, al
0x18005befd  mov     [rsp+168h+var_115], al
0x18005bf01  mov     [rsp+168h+var_114], dil
0x18005bf06  mov     [rsp+168h+var_100], edi
0x18005bf0a  mov     [rsp+168h+var_F4], edi
0x18005bf0e  mov     [rsp+168h+var_E0], edi
0x18005bf15  mov     [rsp+168h+var_F8], edi
0x18005bf19  mov     rcx, [rsi]
0x18005bf1c  mov     rcx, [rcx+80h]; this
0x18005bf23  call    ?GetConfigHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVIConfigHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetConfigHelper(void)
0x18005bf28  mov     r10, rax
0x18005bf2b  mov     rcx, [rax]
0x18005bf2e  mov     rax, [rcx+98h]
0x18005bf35  lea     rcx, [rsp+168h+var_F8]
0x18005bf3a  mov     [rsp+168h+var_140], rcx
0x18005bf3f  lea     rcx, [rsp+168h+var_E0]
0x18005bf47  mov     [rsp+168h+var_148], rcx
0x18005bf4c  lea     r9, [rsp+168h+var_F4]
0x18005bf51  lea     r8, [rsp+168h+var_100]
0x18005bf56  lea     rdx, [rsp+168h+var_114]
0x18005bf5b  mov     rcx, r10
0x18005bf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf63  mov     [rsp+168h+var_FC], edi
0x18005bf67  call    cs:__imp_GetTickCount64
0x18005bf6d  mov     [rsp+168h+var_D0], rax
0x18005bf75  mov     al, dil
0x18005bf78  mov     [rsp+168h+var_117], al
0x18005bf7c  mov     [rsp+168h+var_118], dil
0x18005bf81  mov     [rsp+168h+var_E8], rbx
0x18005bf89  test    al, al
0x18005bf8b  jz      short loc_18005BF9F
0x18005bf8d  lea     rdx, [rsp+168h+var_118]
0x18005bf92  lea     rcx, [rsp+168h+var_E8]
0x18005bf9a  call    _lambda_618646fc743ab71dd0f0413086fb56ef___operator__
0x18005bf9f  mov     [rsp+168h+var_117], dil
0x18005bfa4  test    r15b, r15b
0x18005bfa7  jnz     short loc_18005BFDE
0x18005bfa9  mov     r15b, 1
0x18005bfac  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bfb3  cmp     rcx, r14
0x18005bfb6  jz      short loc_18005BFE1
0x18005bfb8  cmp     byte ptr [rcx+19h], 3
0x18005bfbc  jb      short loc_18005BFE1
0x18005bfbe  test    [rcx+1Ch], r15b
0x18005bfc2  jz      short loc_18005BFE1
0x18005bfc4  mov     edx, 32h ; '2'
0x18005bfc9  mov     r9, rbx
0x18005bfcc  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18005bfd3  mov     rcx, [rcx+10h]
0x18005bfd7  call    WPP_SF_q
0x18005bfdc  jmp     short loc_18005BFE1
0x18005bfde  mov     r15b, dil
0x18005bfe1  mov     rcx, [rsi]
0x18005bfe4  mov     r12, [rcx+68h]
0x18005bfe8  mov     rcx, [rcx+80h]; this
0x18005bfef  call    ?GetStateMachine@CRemoteDevice@WFDSConMgr@@QEAAAEAVCSessionStateMachine@2@XZ; WFDSConMgr::CRemoteDevice::GetStateMachine(void)
0x18005bff4  mov     r13, rax
0x18005bff7  mov     rcx, [rsi]
0x18005bffa  mov     rcx, [rcx+80h]; void *
0x18005c001  call    ?GetRemoteAddress@CRemoteDevice@WFDSConMgr@@QEBAAEAY05$$CBEXZ; WFDSConMgr::CRemoteDevice::GetRemoteAddress(void)
0x18005c006  mov     r9b, r15b; bool
0x18005c009  mov     r8, r13; struct WFDSConMgr::IWFDDisconnectListener *
0x18005c00c  mov     rdx, rax; unsigned __int8 (*)[6]
0x18005c00f  mov     rcx, r12; this
0x18005c012  call    ?OpenSession@CWFDConnectHelper@WFDSConMgr@@QEAAXAEAY05$$CBEPEAVIWFDDisconnectListener@2@_N@Z; WFDSConMgr::CWFDConnectHelper::OpenSession(uchar const (&)[6],WFDSConMgr::IWFDDisconnectListener *,bool)
0x18005c017  test    r15b, r15b
0x18005c01a  jz      short loc_18005C026
0x18005c01c  mov     rax, [rsi]
0x18005c01f  mov     byte ptr [rax+0A0h], 1
0x18005c026  jmp     short loc_18005C06C
0x18005c028  mov     eax, [rsp+168h+var_100]
0x18005c02c  lea     r14, WPP_GLOBAL_Control
0x18005c033  xor     edi, edi
0x18005c035  mov     rbx, [rsp+168h+var_108]
0x18005c03a  mov     rsi, [rsp+168h+var_D8]
0x18005c042  cmp     [rsp+168h+var_FC], eax
0x18005c046  jnb     short loc_18005C06C
0x18005c048  mov     r15b, [rsp+168h+var_115]
0x18005c04d  mov     al, [rsp+168h+var_117]
0x18005c051  jmp     loc_18005BF89
0x18005c056  lea     r14, WPP_GLOBAL_Control
0x18005c05d  xor     edi, edi
0x18005c05f  mov     rbx, [rsp+168h+var_108]
0x18005c064  mov     rsi, [rsp+168h+var_D8]
0x18005c06c  mov     [rsp+168h+var_110], rbx
0x18005c071  lea     rcx, [rsp+168h+var_110]
0x18005c076  call    WFDSConMgr__TryCatchTelemetry__lambda_78d2801d00252623a192c2dea2d50cf5___
0x18005c07b  cmp     [rsp+168h+var_116], dil
0x18005c080  jz      loc_18005C135
0x18005c086  lea     rcx, [rbx+60h]
0x18005c08a  mov     r8d, [rsp+168h+var_F4]
0x18005c08f  lea     rdx, [rsp+168h+var_110]
0x18005c094  call    ?WaitAllowTimeout@CEventWrapper@WFDSConMgr@@QEBA?AVCWaitResult@2@K@Z; WFDSConMgr::CEventWrapper::WaitAllowTimeout(ulong)
0x18005c099  cmp     dword ptr [rsp+168h+var_110+4], edi
0x18005c09d  jz      loc_18005C209
0x18005c0a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c0aa  cmp     rcx, r14
0x18005c0ad  jz      short loc_18005C0D3
0x18005c0af  cmp     byte ptr [rcx+19h], 2
0x18005c0b3  jb      short loc_18005C0D3
0x18005c0b5  test    byte ptr [rcx+1Ch], 1
0x18005c0b9  jz      short loc_18005C0D3
0x18005c0bb  mov     edx, 3Ch ; '<'
0x18005c0c0  mov     r9, rbx
0x18005c0c3  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18005c0ca  mov     rcx, [rcx+10h]
0x18005c0ce  call    WPP_SF_q
0x18005c0d3  mov     [rsp+168h+var_110], rbx
0x18005c0d8  lea     rcx, [rsp+168h+var_110]
0x18005c0dd  call    WFDSConMgr__TryCatchTelemetry__lambda_42202b07dc32095212ff6c16076b80a4___
0x18005c0e2  nop
0x18005c0e3  mov     [rsp+168h+var_118], dil
0x18005c0e8  lea     rdx, [rsp+168h+var_118]
0x18005c0ed  lea     rcx, [rsp+168h+var_E8]
0x18005c0f5  call    _lambda_618646fc743ab71dd0f0413086fb56ef___operator__
0x18005c0fa  nop
0x18005c0fb  mov     edx, 2
0x18005c100  mov     rcx, [rsi]
0x18005c103  call    ?GoToNextState@CConnectManager@WFDSConMgr@@QEAAXW4ConnectionState@2@@Z; WFDSConMgr::CConnectManager::GoToNextState(WFDSConMgr::ConnectionState)
0x18005c108  mov     rcx, [rsp+168h+var_38]
0x18005c110  xor     rcx, rsp; StackCookie
0x18005c113  call    __security_check_cookie
0x18005c118  lea     r11, [rsp+168h+var_28]
0x18005c120  mov     rbx, [r11+38h]
0x18005c124  mov     rsi, [r11+40h]
0x18005c128  mov     rsp, r11
0x18005c12b  pop     r15
0x18005c12d  pop     r14
0x18005c12f  pop     r13
0x18005c131  pop     r12
0x18005c133  pop     rdi
0x18005c134  retn
0x18005c135  mov     rcx, [rsi]
0x18005c138  mov     rbx, [rcx+80h]
0x18005c13f  lea     rdx, [rsp+168h+var_B8]
0x18005c147  mov     rcx, [rcx+68h]
0x18005c14b  call    ?ReleaseWFDHandle@CWFDConnectHelper@WFDSConMgr@@QEAA?AVCWFDSessionHandle@2@XZ; WFDSConMgr::CWFDConnectHelper::ReleaseWFDHandle(void)
0x18005c150  nop
0x18005c151  mov     rdx, rax
0x18005c154  mov     rcx, rbx
0x18005c157  call    ?SetMiracastWFDHandle@CRemoteDevice@WFDSConMgr@@QEAAX$$QEAVCWFDSessionHandle@2@@Z; WFDSConMgr::CRemoteDevice::SetMiracastWFDHandle(WFDSConMgr::CWFDSessionHandle &&)
0x18005c15c  nop
0x18005c15d  lea     rcx, [rsp+168h+var_B8]; this
0x18005c165  call    ??1CWFDSessionHandle@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CWFDSessionHandle::~CWFDSessionHandle(void)
0x18005c16a  mov     rcx, [rsi]
0x18005c16d  mov     rcx, [rcx+80h]; this
0x18005c174  call    ?HasSetMediaStreamingMode@CRemoteDevice@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CRemoteDevice::HasSetMediaStreamingMode(void)
0x18005c179  test    al, al
0x18005c17b  jnz     short loc_18005C1CC
0x18005c17d  mov     rcx, [rsi]
0x18005c180  lea     rdx, [rsp+168h+var_110]
0x18005c185  mov     rcx, [rcx+68h]
0x18005c189  call    ?SetMediaStreamingModeOn@CWFDConnectHelper@WFDSConMgr@@QEAA?AV?$unique_ptr@VCWFDMediaStreamingModeHelper@WFDSConMgr@@U?$default_delete@VCWFDMediaStreamingModeHelper@WFDSConMgr@@@std@@@std@@XZ; WFDSConMgr::CWFDConnectHelper::SetMediaStreamingModeOn(void)
0x18005c18e  mov     rbx, [rax]
0x18005c191  mov     [rax], rdi
0x18005c194  lea     rcx, [rsp+168h+var_110]
0x18005c199  call    ??1?$unique_ptr@VCWFDMediaStreamingModeHelper@WFDSConMgr@@U?$default_delete@VCWFDMediaStreamingModeHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>::~unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>(void)
0x18005c19e  mov     [rsp+168h+var_110], rdi
0x18005c1a3  mov     [rsp+168h+var_E8], rbx
0x18005c1ab  mov     rcx, [rsi]
0x18005c1ae  lea     rdx, [rsp+168h+var_E8]
0x18005c1b6  mov     rcx, [rcx+80h]
0x18005c1bd  call    ?OnSetMediaStreamingMode@CRemoteDevice@WFDSConMgr@@QEAAXV?$unique_ptr@VCWFDMediaStreamingModeHelper@WFDSConMgr@@U?$default_delete@VCWFDMediaStreamingModeHelper@WFDSConMgr@@@std@@@std@@@Z; WFDSConMgr::CRemoteDevice::OnSetMediaStreamingMode(std::unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>)
0x18005c1c2  lea     rcx, [rsp+168h+var_110]
0x18005c1c7  call    ??1?$unique_ptr@VCWFDMediaStreamingModeHelper@WFDSConMgr@@U?$default_delete@VCWFDMediaStreamingModeHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>::~unique_ptr<WFDSConMgr::CWFDMediaStreamingModeHelper>(void)
0x18005c1cc  mov     rcx, [rsi]; this
0x18005c1cf  call    ?GoToFinalState@CConnectManager@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CConnectManager::GoToFinalState(void)
0x18005c1d4  jmp     loc_18005C108
0x18005c1d9  mov     [rsp+168h+var_140], rbx; void *
0x18005c1de  lea     rax, aAttemptedToDoW; "Attempted to do WFD Open Session for in"...
0x18005c1e5  mov     [rsp+168h+var_148], rax; unsigned __int16 *
0x18005c1ea  mov     r9d, 3E8h; char
0x18005c1f0  lea     r8, aOnecoreuapNetW_9; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005c1f7  lea     rdx, aWfdsconmgrCcon_12; "WFDSConMgr::CConnectWFDOpenSessionWork:"...
0x18005c1fe  mov     ecx, 8007139Fh; char
0x18005c203  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005c209  mov     [rsp+168h+var_140], rbx; void *
0x18005c20e  lea     rax, aConnectCancele_0; "Connect canceled before re-pair"
0x18005c215  mov     [rsp+168h+var_148], rax; unsigned __int16 *
0x18005c21a  mov     r9d, 4E4h; char
0x18005c220  lea     r8, aOnecoreuapNetW_9; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005c227  lea     rdx, aWfdsconmgrCcon_12; "WFDSConMgr::CConnectWFDOpenSessionWork:"...
0x18005c22e  mov     ecx, 800704C7h; char
0x18005c233  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
