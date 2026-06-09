# WFDSConMgr::CConnectInfraIssueChallengeSessionWork::DoActionInternal(void)

- ea: `0x18005b880`
- end: `0x18005bc2a`
- name: `?DoActionInternal@CConnectInfraIssueChallengeSessionWork@WFDSConMgr@@EEAAXXZ`
- size: `938`
- prototype: `void __fastcall(WFDSConMgr::CConnectInfraIssueChallengeSessionWork *__hidden this)`
- caller_count: `0`
- callee_count: `33`
- tags: `broker_com_uri`

## callees

- `0x180002600`
- `0x18000475c`
- `0x1800059c0`
- `0x180006740`
- `0x180006c60`
- `0x180006e6c`
- `0x180008a10`
- `0x18001a21c`
- `0x18001d18c`
- `0x180024af0`
- `0x180025708`
- `0x1800258b4`
- `0x1800259a4`
- `0x180025b08`
- `0x180025e80`
- `0x1800275bc`
- `0x1800321c8`
- `0x180039fec`
- `0x18003a228`
- `0x18003b6bc`
- `0x18003bfb4`
- `0x18004a298`
- `0x180053714`
- `0x180057cac`
- `0x180058034`
- `0x1800582b8`
- `0x180058964`
- `0x180058f70`
- `0x180059098`
- `0x180059180`
- `0x18005b880`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ba9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ba9a`

## string_xrefs

- `0x18005b8fc`: `Attempted to do infrastructure challenge for WFD`
- `0x18005bac2`: `Challenge completed, devnode is offline`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WFDSConMgr::CConnectInfraIssueChallengeSessionWork::DoActionInternal(
        WFDSConMgr::CConnectInfraIssueChallengeSessionWork *this)
{
  _QWORD *v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rsi
  __int64 RemoteAddress; // rax
  __int64 *v7; // rax
  __int64 v8; // rax
  int *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 DevQueryShim; // rax
  __int64 v14; // r9
  __int64 v15; // rax
  WFDSConMgr::CDevQueryHelper **v16; // rbx
  bool StreamSecuritySupportedForInfraDevice; // di
  bool PinSupportedForInfraDevice; // si
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  _QWORD *v23; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-49h] BYREF
  __int64 v25; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v26[8]; // [rsp+60h] [rbp-39h] BYREF
  std::_Ref_count_base *v27; // [rsp+68h] [rbp-31h]
  __int64 v28; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v29[16]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v30[16]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v31; // [rsp+A0h] [rbp+7h]
  _BYTE v32[16]; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v33; // [rsp+C0h] [rbp+27h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids, this);
  }
  if ( (unsigned int)WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(*(_QWORD *)(*((_QWORD *)this + 1) + 128LL)) != 2 )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CConnectInfraIssueChallengeSessionWork::DoActionInternal",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectwork.cpp",
      45,
      L"Attempted to do infrastructure challenge for WFD",
      this);
  v2 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
         &lpCriticalSection,
         (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_7469569e7aaf0bdc27a61784de0eddb7___(v2);
  v3 = 0;
  v25 = 0;
  v4 = *((_QWORD *)this + 1);
  v5 = *(_QWORD *)(v4 + 128);
  if ( *(_DWORD *)(v5 + 112) == 1 )
  {
    RemoteAddress = WFDSConMgr::CRemoteDevice::GetRemoteAddress(*(void **)(v4 + 128));
    v7 = std::make_unique<WFDSConMgr::InfracastDafAssociationParameters,unsigned char const (&)[6],_GUID const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,bool const &,bool const &,std::vector<std::wstring> const &,0>(
           &lpCriticalSection,
           RemoteAddress,
           (_OWORD *)(v5 + 220),
           v5 + 240,
           v5 + 272,
           v5 + 304,
           v5 + 336,
           (char *)(v5 + 392),
           (char *)(v5 + 393),
           v5 + 368);
    std::unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>::operator=<std::default_delete<WFDSConMgr::InfracastDafAssociationParameters>,0>(
      &v25,
      v7);
    std::unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>::~unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>(&lpCriticalSection);
    v3 = v25;
  }
  v8 = *((_QWORD *)this + 1);
  v9 = *(int **)(v8 + 88);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 128) + 40LL))(*(_QWORD *)(v8 + 128));
  WFDSConMgr::CDafAssociationHelper::IssueInfraChallenge(v9, v10, v3);
  WFDSConMgr::CriticalSection::Lock((char *)this + 48, &lpCriticalSection);
  if ( *((_BYTE *)this + 88) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CConnectInfraIssueChallengeSessionWork::DoActionInternal",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectwork.cpp",
      84,
      L"Query operation was canceled before starting",
      this);
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 128LL) + 40LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 128LL));
  DevQueryShim = WFDSConMgr::CConnectManager::GetDevQueryShim(*((_QWORD *)this + 1), v29, v12, v11);
  v15 = WFDSConMgr::CDevNodeQueryHelper::Create(v26, DevQueryShim, v14);
  v16 = (WFDSConMgr::CDevQueryHelper **)((char *)this + 32);
  std::shared_ptr<WFDSConMgr::CDevQueryHelper>::operator=((char *)this + 32, v15);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  WFDSConMgr::CDevQueryHelper::DoQuery(*v16, 1, 1, 0);
  if ( !WFDSConMgr::CDevQueryHelper::GetDevNodePropertyIsOnline(*v16) )
    WFDSConMgr::CException::Throw(
      144,
      "WFDSConMgr::CConnectInfraIssueChallengeSessionWork::DoActionInternal",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\connectwork.cpp",
      100,
      L"Challenge completed, devnode is offline",
      this);
  WFDSConMgr::CDevQueryHelper::GetHostNameResolutionModeForInfraDevice(*v16, v32);
  WFDSConMgr::CDevQueryHelper::GetIpAddressForInfraDevice(*v16, v30);
  StreamSecuritySupportedForInfraDevice = WFDSConMgr::CDevQueryHelper::GetStreamSecuritySupportedForInfraDevice(*v16);
  PinSupportedForInfraDevice = WFDSConMgr::CDevQueryHelper::GetPinSupportedForInfraDevice(*v16);
  v19 = *(_QWORD *)(*((_QWORD *)this + 1) + 128LL);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)v26,
    (RTL_SRWLOCK *)(v19 + 48));
  *(_BYTE *)(v19 + 392) = StreamSecuritySupportedForInfraDevice;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v26);
  v20 = *(_QWORD *)(*((_QWORD *)this + 1) + 128LL);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)v26,
    (RTL_SRWLOCK *)(v20 + 48));
  *(_BYTE *)(v20 + 393) = PinSupportedForInfraDevice;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v26);
  v21 = v31;
  if ( v31 )
  {
    WFDSConMgr::CRemoteDevice::SetInfraIpAddress(*(_QWORD *)(*((_QWORD *)this + 1) + 128LL), v30);
    v21 = v31;
  }
  if ( v33 || v21 )
  {
    v22 = lambda_69ca09668d1fc59e8b926ce773025052_::_lambda_69ca09668d1fc59e8b926ce773025052_(v26, v32, v30, this);
    WFDSConMgr::TryCatchTelemetry__lambda_69ca09668d1fc59e8b926ce773025052___(v22);
  }
  WFDSConMgr::CRemoteDevice::OnInfraConnectedStartDevnodeManagement(*(WFDSConMgr::CRemoteDevice **)(*((_QWORD *)this + 1)
                                                                                                  + 128LL));
  v23 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          &v28,
          (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_b3e34dd1aff94dcafa37f24a4e021654___(v23);
  WFDSConMgr::CConnectManager::GoToNextState(*((_QWORD *)this + 1), 13);
  std::wstring::_Tidy_deallocate(v30);
  std::wstring::_Tidy_deallocate(v32);
  std::unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>::~unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>(&v25);
}

```

## disassembly

```asm
0x18005b880  mov     [rsp-8+arg_8], rbx
0x18005b885  mov     [rsp-8+arg_10], rsi
0x18005b88a  push    rbp
0x18005b88b  push    rdi
0x18005b88c  push    r14
0x18005b88e  lea     rbp, [rsp-47h]
0x18005b893  sub     rsp, 0E0h
0x18005b89a  mov     rax, cs:__security_cookie
0x18005b8a1  xor     rax, rsp
0x18005b8a4  mov     [rbp+57h+var_20], rax
0x18005b8a8  mov     r14, rcx
0x18005b8ab  lea     rax, WPP_GLOBAL_Control
0x18005b8b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b8b9  cmp     rcx, rax
0x18005b8bc  jz      short loc_18005B8E2
0x18005b8be  cmp     byte ptr [rcx+19h], 4
0x18005b8c2  jb      short loc_18005B8E2
0x18005b8c4  test    byte ptr [rcx+1Ch], 1
0x18005b8c8  jz      short loc_18005B8E2
0x18005b8ca  mov     edx, 40h ; '@'
0x18005b8cf  mov     r9, r14
0x18005b8d2  lea     r8, WPP_3a65b95a777438214dc7765bc6ade9f9_Traceguids
0x18005b8d9  mov     rcx, [rcx+10h]
0x18005b8dd  call    WPP_SF_q
0x18005b8e2  mov     rcx, [r14+8]
0x18005b8e6  mov     rcx, [rcx+80h]
0x18005b8ed  call    ?GetDafProviderTypeForConnection@CRemoteDevice@WFDSConMgr@@QEBA?AW4DafProvider@2@XZ; WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(void)
0x18005b8f2  cmp     eax, 2
0x18005b8f5  jz      short loc_18005B927
0x18005b8f7  mov     [rsp+0F0h+var_C8], r14; void *
0x18005b8fc  lea     rax, aAttemptedToDoI; "Attempted to do infrastructure challeng"...
0x18005b903  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x18005b908  mov     r9d, 52Dh; char
0x18005b90e  lea     r8, aOnecoreuapNetW_9; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005b915  lea     rdx, aWfdsconmgrCcon_14; "WFDSConMgr::CConnectInfraIssueChallenge"...
0x18005b91c  mov     ecx, 8007139Fh; char
0x18005b921  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005b927  mov     rdx, r14
0x18005b92a  lea     rcx, [rbp+57h+lpCriticalSection]
0x18005b92e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18005b933  mov     rcx, rax
0x18005b936  call    WFDSConMgr__TryCatchTelemetry__lambda_7469569e7aaf0bdc27a61784de0eddb7___
0x18005b93b  xor     ebx, ebx
0x18005b93d  mov     [rbp+57h+var_98], rbx
0x18005b941  mov     rax, [r14+8]
0x18005b945  mov     rsi, [rax+80h]
0x18005b94c  cmp     dword ptr [rsi+70h], 1
0x18005b950  jnz     short loc_18005B9CF
0x18005b952  lea     rdi, [rsi+170h]
0x18005b959  mov     rcx, rsi; void *
0x18005b95c  call    ?GetRemoteAddress@CRemoteDevice@WFDSConMgr@@QEBAAEAY05$$CBEXZ; WFDSConMgr::CRemoteDevice::GetRemoteAddress(void)
0x18005b961  lea     rcx, [rdi+19h]
0x18005b965  lea     rdx, [rdi+18h]
0x18005b969  lea     r10, [rsi+150h]
0x18005b970  lea     r11, [rsi+130h]
0x18005b977  lea     rbx, [rsi+110h]
0x18005b97e  lea     r9, [rsi+0F0h]
0x18005b985  lea     r8, [rsi+0DCh]
0x18005b98c  mov     [rsp+0F0h+var_A8], rdi
0x18005b991  mov     [rsp+0F0h+var_B0], rcx
0x18005b996  mov     [rsp+0F0h+var_B8], rdx
0x18005b99b  mov     [rsp+0F0h+var_C0], r10
0x18005b9a0  mov     [rsp+0F0h+var_C8], r11
0x18005b9a5  mov     [rsp+0F0h+var_D0], rbx
0x18005b9aa  mov     rdx, rax
0x18005b9ad  lea     rcx, [rbp+57h+lpCriticalSection]
0x18005b9b1  call    ??$make_unique@UInfracastDafAssociationParameters@WFDSConMgr@@AEAY05$$CBEAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@AEBV45@AEBV45@AEB_NAEB_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@$0A@@std@@YA?AV?$unique_ptr@UInfracastDafAssociationParameters@WFDSConMgr@@U?$default_delete@UInfracastDafAssociationParameters@WFDSConMgr@@@std@@@0@AEAY05$$CBEAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@222AEB_N3AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@0@@Z; std::make_unique<WFDSConMgr::InfracastDafAssociationParameters,uchar const (&)[6],_GUID const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,bool const &,bool const &,std::vector<std::wstring> const &,0>(uchar const (&)[6],_GUID const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,bool const &,bool const &,std::vector<std::wstring> const &)
0x18005b9b6  mov     rdx, rax
0x18005b9b9  lea     rcx, [rbp+57h+var_98]
0x18005b9bd  call    ??$?4U?$default_delete@UInfracastDafAssociationParameters@WFDSConMgr@@@std@@$0A@@?$unique_ptr@UInfracastDafAssociationParameters@WFDSConMgr@@U?$default_delete@UInfracastDafAssociationParameters@WFDSConMgr@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>::operator=<std::default_delete<WFDSConMgr::InfracastDafAssociationParameters>,0>(std::unique_ptr<WFDSConMgr::InfracastDafAssociationParameters> &&)
0x18005b9c2  lea     rcx, [rbp+57h+lpCriticalSection]
0x18005b9c6  call    ??1?$unique_ptr@UInfracastDafAssociationParameters@WFDSConMgr@@U?$default_delete@UInfracastDafAssociationParameters@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>::~unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>(void)
0x18005b9cb  mov     rbx, [rbp+57h+var_98]
0x18005b9cf  mov     rax, [r14+8]
0x18005b9d3  mov     rdi, [rax+58h]
0x18005b9d7  mov     rcx, [rax+80h]
0x18005b9de  mov     rax, [rcx]
0x18005b9e1  mov     rax, [rax+28h]
0x18005b9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9ea  mov     r8, rbx
0x18005b9ed  mov     rdx, rax
0x18005b9f0  mov     rcx, rdi; void *
0x18005b9f3  call    ?IssueInfraChallenge@CDafAssociationHelper@WFDSConMgr@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBUInfracastDafAssociationParameters@2@@Z; WFDSConMgr::CDafAssociationHelper::IssueInfraChallenge(std::wstring const &,WFDSConMgr::InfracastDafAssociationParameters const *)
0x18005b9f8  lea     rcx, [r14+30h]
0x18005b9fc  lea     rdx, [rbp+57h+lpCriticalSection]
0x18005ba00  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18005ba05  nop
0x18005ba06  cmp     byte ptr [r14+58h], 0
0x18005ba0b  jz      short loc_18005BA3D
0x18005ba0d  mov     [rsp+0F0h+var_C8], r14; void *
0x18005ba12  lea     rax, aQueryOperation_0; "Query operation was canceled before sta"...
0x18005ba19  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x18005ba1e  mov     r9d, 554h; char
0x18005ba24  lea     r8, aOnecoreuapNetW_9; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005ba2b  lea     rdx, aWfdsconmgrCcon_14; "WFDSConMgr::CConnectInfraIssueChallenge"...
0x18005ba32  mov     ecx, 800704C7h; char
0x18005ba37  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005ba3d  mov     rax, [r14+8]
0x18005ba41  mov     rcx, [rax+80h]
0x18005ba48  mov     rax, [rcx]
0x18005ba4b  mov     rax, [rax+28h]
0x18005ba4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba54  mov     r9, rax
0x18005ba57  lea     rdx, [rbp+57h+var_70]
0x18005ba5b  mov     rcx, [r14+8]
0x18005ba5f  call    ?GetDevQueryShim@CConnectManager@WFDSConMgr@@QEAA?AV?$shared_ptr@VCDevQueryShim@WFDSConMgr@@@std@@XZ; WFDSConMgr::CConnectManager::GetDevQueryShim(void)
0x18005ba64  mov     r8, r9
0x18005ba67  mov     rdx, rax
0x18005ba6a  lea     rcx, [rbp+57h+var_90]
0x18005ba6e  call    ?Create@CDevNodeQueryHelper@WFDSConMgr@@SA?AV?$shared_ptr@VCDevQueryHelper@WFDSConMgr@@@std@@V?$shared_ptr@VCDevQueryShim@WFDSConMgr@@@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; WFDSConMgr::CDevNodeQueryHelper::Create(std::shared_ptr<WFDSConMgr::CDevQueryShim>,std::wstring const &)
0x18005ba73  lea     rbx, [r14+20h]
0x18005ba77  mov     rdx, rax
0x18005ba7a  mov     rcx, rbx
0x18005ba7d  call    ??4?$shared_ptr@VCDevQueryHelper@WFDSConMgr@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WFDSConMgr::CDevQueryHelper>::operator=(std::shared_ptr<WFDSConMgr::CDevQueryHelper> &&)
0x18005ba82  mov     rcx, [rbp+57h+var_88]; this
0x18005ba86  test    rcx, rcx
0x18005ba89  jz      short loc_18005BA91
0x18005ba8b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ba90  nop
0x18005ba91  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18005ba95  test    rcx, rcx
0x18005ba98  jz      short loc_18005BAA0
0x18005ba9a  call    cs:__imp_LeaveCriticalSection
0x18005baa0  xor     r9d, r9d; unsigned int
0x18005baa3  mov     r8b, 1; bool
0x18005baa6  mov     dl, r8b; bool
0x18005baa9  mov     rcx, [rbx]; this
0x18005baac  call    ?DoQuery@CDevQueryHelper@WFDSConMgr@@QEAA_N_N0K@Z; WFDSConMgr::CDevQueryHelper::DoQuery(bool,bool,ulong)
0x18005bab1  mov     rcx, [rbx]; this
0x18005bab4  call    ?GetDevNodePropertyIsOnline@CDevQueryHelper@WFDSConMgr@@QEAA_NXZ; WFDSConMgr::CDevQueryHelper::GetDevNodePropertyIsOnline(void)
0x18005bab9  test    al, al
0x18005babb  jnz     short loc_18005BAED
0x18005babd  mov     [rsp+0F0h+var_C8], r14; void *
0x18005bac2  lea     rax, aChallengeCompl; "Challenge completed, devnode is offline"
0x18005bac9  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x18005bace  mov     r9d, 564h; char
0x18005bad4  lea     r8, aOnecoreuapNetW_9; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18005badb  lea     rdx, aWfdsconmgrCcon_14; "WFDSConMgr::CConnectInfraIssueChallenge"...
0x18005bae2  mov     ecx, 80070490h; char
0x18005bae7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005baed  lea     rdx, [rbp+57h+var_40]
0x18005baf1  mov     rcx, [rbx]
0x18005baf4  call    ?GetHostNameResolutionModeForInfraDevice@CDevQueryHelper@WFDSConMgr@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WFDSConMgr::CDevQueryHelper::GetHostNameResolutionModeForInfraDevice(void)
0x18005baf9  nop
0x18005bafa  lea     rdx, [rbp+57h+var_60]
0x18005bafe  mov     rcx, [rbx]
0x18005bb01  call    ?GetIpAddressForInfraDevice@CDevQueryHelper@WFDSConMgr@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WFDSConMgr::CDevQueryHelper::GetIpAddressForInfraDevice(void)
0x18005bb06  nop
0x18005bb07  mov     rcx, [rbx]; this
0x18005bb0a  call    ?GetStreamSecuritySupportedForInfraDevice@CDevQueryHelper@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CDevQueryHelper::GetStreamSecuritySupportedForInfraDevice(void)
0x18005bb0f  mov     dil, al
0x18005bb12  mov     rcx, [rbx]; this
0x18005bb15  call    ?GetPinSupportedForInfraDevice@CDevQueryHelper@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CDevQueryHelper::GetPinSupportedForInfraDevice(void)
0x18005bb1a  mov     sil, al
0x18005bb1d  mov     rcx, [r14+8]
0x18005bb21  mov     rbx, [rcx+80h]
0x18005bb28  lea     rdx, [rbx+30h]
0x18005bb2c  lea     rcx, [rbp+57h+var_90]
0x18005bb30  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x18005bb35  mov     [rbx+188h], dil
0x18005bb3c  lea     rcx, [rbp+57h+var_90]
0x18005bb40  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x18005bb45  mov     rcx, [r14+8]
0x18005bb49  mov     rbx, [rcx+80h]
0x18005bb50  lea     rdx, [rbx+30h]
0x18005bb54  lea     rcx, [rbp+57h+var_90]
0x18005bb58  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x18005bb5d  mov     [rbx+189h], sil
0x18005bb64  lea     rcx, [rbp+57h+var_90]
0x18005bb68  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x18005bb6d  mov     rax, [rbp+57h+var_50]
0x18005bb71  test    rax, rax
0x18005bb74  jz      short loc_18005BB8E
0x18005bb76  mov     rcx, [r14+8]
0x18005bb7a  lea     rdx, [rbp+57h+var_60]
0x18005bb7e  mov     rcx, [rcx+80h]
0x18005bb85  call    ?SetInfraIpAddress@CRemoteDevice@WFDSConMgr@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WFDSConMgr::CRemoteDevice::SetInfraIpAddress(std::wstring const &)
0x18005bb8a  mov     rax, [rbp+57h+var_50]
0x18005bb8e  cmp     [rbp+57h+var_30], 0
0x18005bb93  jnz     short loc_18005BB9A
0x18005bb95  test    rax, rax
0x18005bb98  jz      short loc_18005BBB6
0x18005bb9a  mov     r9, r14
0x18005bb9d  lea     r8, [rbp+57h+var_60]
0x18005bba1  lea     rdx, [rbp+57h+var_40]
0x18005bba5  lea     rcx, [rbp+57h+var_90]
0x18005bba9  call    _lambda_69ca09668d1fc59e8b926ce773025052____lambda_69ca09668d1fc59e8b926ce773025052_
0x18005bbae  mov     rcx, rax
0x18005bbb1  call    WFDSConMgr__TryCatchTelemetry__lambda_69ca09668d1fc59e8b926ce773025052___
0x18005bbb6  mov     rcx, [r14+8]
0x18005bbba  mov     rcx, [rcx+80h]; this
0x18005bbc1  call    ?OnInfraConnectedStartDevnodeManagement@CRemoteDevice@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CRemoteDevice::OnInfraConnectedStartDevnodeManagement(void)
0x18005bbc6  mov     rdx, r14
0x18005bbc9  lea     rcx, [rbp+57h+var_78]
0x18005bbcd  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18005bbd2  mov     rcx, rax
0x18005bbd5  call    WFDSConMgr__TryCatchTelemetry__lambda_b3e34dd1aff94dcafa37f24a4e021654___
0x18005bbda  mov     edx, 0Dh
0x18005bbdf  mov     rcx, [r14+8]
0x18005bbe3  call    ?GoToNextState@CConnectManager@WFDSConMgr@@QEAAXW4ConnectionState@2@@Z; WFDSConMgr::CConnectManager::GoToNextState(WFDSConMgr::ConnectionState)
0x18005bbe8  nop
0x18005bbe9  lea     rcx, [rbp+57h+var_60]
0x18005bbed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bbf2  nop
0x18005bbf3  lea     rcx, [rbp+57h+var_40]
0x18005bbf7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bbfc  nop
0x18005bbfd  lea     rcx, [rbp+57h+var_98]
0x18005bc01  call    ??1?$unique_ptr@UInfracastDafAssociationParameters@WFDSConMgr@@U?$default_delete@UInfracastDafAssociationParameters@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>::~unique_ptr<WFDSConMgr::InfracastDafAssociationParameters>(void)
0x18005bc06  mov     rcx, [rbp+57h+var_20]
0x18005bc0a  xor     rcx, rsp; StackCookie
0x18005bc0d  call    __security_check_cookie
0x18005bc12  lea     r11, [rsp+0F0h+var_10]
0x18005bc1a  mov     rbx, [r11+28h]
0x18005bc1e  mov     rsi, [r11+30h]
0x18005bc22  mov     rsp, r11
0x18005bc25  pop     r14
0x18005bc27  pop     rdi
0x18005bc28  pop     rbp
0x18005bc29  retn
```
