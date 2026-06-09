# CReportManager::UploadReport(void)

- ea: `0x180006ea8`
- end: `0x18000750c`
- name: `?UploadReport@CReportManager@@AEAAJXZ`
- size: `1636`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180034288`

## callees

- `0x180004c64`
- `0x180006cb0`
- `0x180006d48`
- `0x180006e1c`
- `0x180006e5c`
- `0x180006ea8`
- `0x180007fd8`
- `0x180009074`
- `0x180009464`
- `0x180009490`
- `0x18000ad98`
- `0x18000cf50`
- `0x18000db80`
- `0x18001c368`
- `0x18001f458`
- `0x180020680`
- `0x18002dea4`
- `0x180036c60`
- `0x18003cef0`
- `0x18003de9c`
- `0x180048c40`
- `0x18004c36c`
- `0x18004dfbc`
- `0x180054514`
- `0x18006cb20`
- `0x18007543c`
- `0x180075fcc`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000717a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000717a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006f84`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006f84`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180007156`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180007156`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CReportManager::UploadReport(CReportManager *this)
{
  __int64 v2; // rbx
  int v3; // r14d
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // edx
  DWORD LastError; // eax
  int v8; // eax
  signed int v9; // ebx
  unsigned int v10; // r14d
  CReport *v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // edx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // r9d
  unsigned int v21; // ebx
  wchar_t *v22; // rcx
  wchar_t *v24; // rcx
  __int64 v25; // r9
  int v26; // r14d
  CReport *v27; // rcx
  __int64 v28; // rcx
  int WatsonCab; // eax
  wchar_t *v30; // rcx
  __int64 v31; // rdx
  CReport *v32; // rcx
  int v33; // eax
  int StorePath; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  wchar_t *v38; // rbx
  int v39; // eax
  CReportManager *v40; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v41[2]; // [rsp+38h] [rbp-51h] BYREF
  void *v42[2]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v43[4]; // [rsp+58h] [rbp-31h] BYREF
  char v44; // [rsp+78h] [rbp-11h]
  __int128 v45; // [rsp+80h] [rbp-9h] BYREF
  __int64 v46; // [rsp+90h] [rbp+7h]
  _BYTE v47[32]; // [rsp+98h] [rbp+Fh] BYREF
  int v48; // [rsp+B8h] [rbp+2Fh]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+F0h] [rbp+67h] BYREF
  wchar_t *v50; // [rsp+F8h] [rbp+6Fh] BYREF

  *(_OWORD *)v42 = 0;
  SystemTimeAsFileTime = 0;
  v2 = *((_QWORD *)this + 1);
  v3 = *(_DWORD *)(v2 + 6616);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
  v45 = 0;
  v46 = 0;
  v48 = 0;
  v50 = 0;
  if ( v2 && (v4 = *((_QWORD *)this + 33)) != 0 )
  {
    *(_QWORD *)&v45 = v2;
    *((_QWORD *)&v45 + 1) = *(_QWORD *)this;
    v46 = v4;
    CDataCollection::AddReportMetadata((CDataCollection *)&v45);
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
  }
  v40 = 0;
  v41[1] = 0;
  v41[0] = CreateEventW(0, 0, 0, 0);
  tlx::file_handle_traits::operator()(v5, 0);
  if ( (unsigned __int64)(v41[0] + 1LL) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_12;
  }
  v10 = v3 & 0x2000000;
  v40 = this;
  v11 = (CReport *)*((_QWORD *)this + 1);
  if ( v10 )
  {
    if ( (unsigned int)CReport::GetUploadShouldBypassPowerThrottling(v11) || !(unsigned int)WerpIsOnBattery() )
    {
      if ( (unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 1))
        || !(unsigned int)UtilIsNetworkRestricted() )
      {
        v13 = 1;
        goto LABEL_29;
      }
      *((_DWORD *)this + 34) = 3;
      *(_DWORD *)(*((_QWORD *)this + 1) + 5960LL) |= 0x8000u;
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 46680LL) != 1 )
        goto LABEL_22;
    }
    else
    {
      *((_DWORD *)this + 34) = 3;
      *(_DWORD *)(*((_QWORD *)this + 1) + 5960LL) |= 0x4000u;
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 46680LL) != 1 )
LABEL_22:
        MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v16);
    }
    v9 = 1769476;
    goto LABEL_52;
  }
  v12 = CReport::RemoveFilesByFlagMask(v11, v6);
  if ( v12 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
      (unsigned int)v12);
  v13 = 0;
LABEL_29:
  *((_DWORD *)this + 34) = v13;
  v17 = 120;
  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) != 4 )
    v17 = 60;
  PdcNetworkActivation::PdcNetworkActivation((PdcNetworkActivation *)v43, v17);
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 (__fastcall *)(struct TRANSPORT_CALLBACK_PARAM *, void *), CReportManager **))(**((_QWORD **)this + 2) + 16LL))(
          *((_QWORD *)this + 2),
          *((_QWORD *)this + 1),
          CReportManager::Static_TransportCallback,
          &v40);
  v9 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
        (unsigned int)v18);
    if ( v43[0] )
    {
      if ( v44 )
        PdcNetworkActivation::Deactivate((PdcNetworkActivation *)v43);
      Pdcv2ActivationClientUnregister();
    }
    goto LABEL_52;
  }
  *(_DWORD *)(*((_QWORD *)this + 1) + 6624LL) = 2;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v19 = *((_QWORD *)this + 1);
  *(struct _FILETIME *)(v19 + 600) = SystemTimeAsFileTime;
  v42[0] = *((void **)this + 33);
  v42[1] = (void *)v41[0];
  v21 = UtilMsgWaitForMultipleObjects((const wchar_t *)v19, 2u, v42, v20, v10);
  if ( v21 == -1 )
    GetLastError();
  PdcNetworkActivation::~PdcNetworkActivation((PdcNetworkActivation *)v43);
  if ( !v21 )
    goto LABEL_46;
  if ( v21 != 1 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
    {
LABEL_50:
      CReportManager::HandleCancellation(this);
      v9 = -2145681407;
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3)) == 5 )
        v9 = 1769472;
      goto LABEL_52;
    }
    if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
    {
LABEL_47:
      if ( v22 != (wchar_t *)&WPP_GLOBAL_Control && (v22[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)v22 + 2), 23, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
      goto LABEL_50;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v21);
LABEL_46:
    v22 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    v24 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 34) == 3 || (v25 = *((unsigned int *)this + 28), (_DWORD)v25 == 1769476) )
  {
    v26 = 0;
    *((_DWORD *)this + 58) = 5;
    v27 = (CReport *)*((_QWORD *)this + 1);
    if ( !*((_DWORD *)v27 + 11670) && (unsigned int)CReport::ContainsConfidentialFiles(v27)
      || (unsigned __int8)IsXerTransportEventUploadCompletePresent(v27)
      && (v28 = *((_QWORD *)this + 1), *(_DWORD *)(v28 + 6024))
      && CRegSetting::GetDwordData((CRegSetting *)(v28 + 51680))
      || (WatsonCab = CReportManager::CreateWatsonCab(this, 0), WatsonCab >= 0) )
    {
      WatsonCab = CReportManager::SubmitReportToQueue(this, 0);
      if ( WatsonCab == 1769477 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, 1769477);
        goto LABEL_79;
      }
      if ( WatsonCab >= 0 )
        goto LABEL_104;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_88:
        v32 = (CReport *)*((_QWORD *)this + 1);
        if ( *((_DWORD *)v32 + 11670) )
        {
          StorePath = CReport::GetStorePath(v32, (const wchar_t **)&v50);
          v38 = v50;
          if ( StorePath < 0 || !v50 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v36, v35, v37);
          v39 = CReport::SaveTemporaryAttachedFiles(*((CReport **)this + 1), v38);
          if ( v39 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
              (unsigned int)v39);
          goto LABEL_104;
        }
        v33 = CReportManager::SubmitReportToQueue(this, 2u);
        v9 = v33;
        if ( v33 != 1769477 )
        {
          if ( v33 < 0 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
                (unsigned int)v33);
            goto LABEL_52;
          }
LABEL_104:
          v9 = v26 + 1769476;
          goto LABEL_52;
        }
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
LABEL_79:
        v26 = 1;
        goto LABEL_104;
      }
      v31 = 26;
    }
    else
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_88;
      v31 = 27;
    }
    WPP_SF_d(*((_QWORD *)v30 + 2), v31, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, (unsigned int)WatsonCab);
    goto LABEL_88;
  }
  v8 = 1769483;
  if ( (_DWORD)v25 == 1769483 || (v9 = *((_DWORD *)this + 29), v9 == 1769483) )
  {
LABEL_12:
    v9 = v8;
    goto LABEL_52;
  }
  if ( (int)v25 < 0 )
  {
    v9 = -2145681407;
    if ( (_DWORD)v25 != -2145681407 )
    {
      if ( v24 != (wchar_t *)&WPP_GLOBAL_Control && (v24[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v24 + 2), 31, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v25);
      v9 = -2145681406;
    }
  }
  else if ( v9 != -2147024323 && v9 != -2147024865 )
  {
    v9 = ((v9 >> 31) & 0xFFFFFFF5) + 1769484;
  }
LABEL_52:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(v41);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006ea8  mov     [rsp-8+arg_10], rbx
0x180006ead  mov     [rsp-8+arg_18], rsi
0x180006eb2  push    rbp
0x180006eb3  push    rdi
0x180006eb4  push    r12
0x180006eb6  push    r13
0x180006eb8  push    r14
0x180006eba  lea     rbp, [rsp-37h]
0x180006ebf  sub     rsp, 0C0h
0x180006ec6  mov     rdi, rcx
0x180006ec9  xorps   xmm0, xmm0
0x180006ecc  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180006ed0  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180006ed8  mov     rbx, [rcx+8]
0x180006edc  mov     r14d, [rbx+19D8h]
0x180006ee3  lea     rcx, [rbp+57h+var_48]; void *
0x180006ee7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180006eec  xorps   xmm0, xmm0
0x180006eef  movdqa  [rbp+57h+var_60], xmm0
0x180006ef4  mov     [rbp+57h+var_50], 0
0x180006efc  mov     [rbp+57h+var_28], 0
0x180006f03  mov     [rbp+57h+arg_8], 0
0x180006f0b  mov     r12d, 1
0x180006f11  lea     r13, WPP_GLOBAL_Control
0x180006f18  test    rbx, rbx
0x180006f1b  jz      short loc_180006F43
0x180006f1d  mov     rcx, [rdi+108h]
0x180006f24  test    rcx, rcx
0x180006f27  jz      short loc_180006F43
0x180006f29  mov     qword ptr [rbp+57h+var_60], rbx
0x180006f2d  mov     rax, [rdi]
0x180006f30  mov     qword ptr [rbp+57h+var_60+8], rax
0x180006f34  mov     [rbp+57h+var_50], rcx
0x180006f38  lea     rcx, [rbp+57h+var_60]; this
0x180006f3c  call    ?AddReportMetadata@CDataCollection@@QEAAJXZ; CDataCollection::AddReportMetadata(void)
0x180006f41  jmp     short loc_180006F6A
0x180006f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f4a  cmp     rcx, r13
0x180006f4d  jz      short loc_180006F6A
0x180006f4f  test    [rcx+1Ch], r12b
0x180006f53  jz      short loc_180006F6A
0x180006f55  mov     edx, 83h
0x180006f5a  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180006f61  mov     rcx, [rcx+10h]
0x180006f65  call    WPP_SF_
0x180006f6a  xorps   xmm0, xmm0
0x180006f6d  movdqu  [rbp+57h+var_B0], xmm0
0x180006f72  mov     [rbp+57h+var_A0], 0
0x180006f7a  xor     r9d, r9d; lpName
0x180006f7d  xor     r8d, r8d; bInitialState
0x180006f80  xor     edx, edx; bManualReset
0x180006f82  xor     ecx, ecx; lpEventAttributes
0x180006f84  call    cs:__imp_CreateEventW
0x180006f8b  nop     dword ptr [rax+rax+00h]
0x180006f90  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x180006f94  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180006f98  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180006f9d  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x180006fa1  inc     rax
0x180006fa4  cmp     rax, r12
0x180006fa7  ja      short loc_180006FEA
0x180006fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fb0  cmp     rcx, r13
0x180006fb3  jz      short loc_180006FD0
0x180006fb5  test    [rcx+1Ch], r12b
0x180006fb9  jz      short loc_180006FD0
0x180006fbb  mov     edx, 13h
0x180006fc0  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180006fc7  mov     rcx, [rcx+10h]
0x180006fcb  call    WPP_SF_
0x180006fd0  call    cs:__imp_GetLastError
0x180006fd7  nop     dword ptr [rax+rax+00h]
0x180006fdc  mov     ecx, eax; unsigned int
0x180006fde  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180006fe3  mov     ebx, eax
0x180006fe5  jmp     loc_180007255
0x180006fea  lea     rsi, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180006ff1  and     r14d, 2000000h
0x180006ff8  mov     qword ptr [rbp+57h+var_B0], rdi
0x180006ffc  mov     rcx, [rdi+8]; this
0x180007000  jnz     short loc_180007038
0x180007002  call    ?RemoveFilesByFlagMask@CReport@@QEAAJK@Z; CReport::RemoveFilesByFlagMask(ulong)
0x180007007  test    eax, eax
0x180007009  jns     short loc_180007031
0x18000700b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007012  cmp     rcx, r13
0x180007015  jz      short loc_180007031
0x180007017  test    [rcx+1Ch], r12b
0x18000701b  jz      short loc_180007031
0x18000701d  mov     edx, 14h
0x180007022  mov     r9d, eax
0x180007025  mov     r8, rsi
0x180007028  mov     rcx, [rcx+10h]
0x18000702c  call    WPP_SF_d
0x180007031  xor     eax, eax
0x180007033  jmp     loc_1800070BF
0x180007038  call    ?GetUploadShouldBypassPowerThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassPowerThrottling(void)
0x18000703d  test    eax, eax
0x18000703f  jnz     short loc_18000707C
0x180007041  call    WerpIsOnBattery
0x180007046  test    eax, eax
0x180007048  jz      short loc_18000707C
0x18000704a  mov     dword ptr [rdi+88h], 3
0x180007054  mov     rax, [rdi+8]
0x180007058  bts     dword ptr [rax+1748h], 0Eh
0x180007060  mov     rax, [rdi+8]
0x180007064  cmp     [rax+0B658h], r12d
0x18000706b  jz      short loc_180007072
0x18000706d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007072  mov     ebx, 1B0004h
0x180007077  jmp     loc_180007255
0x18000707c  mov     rcx, [rdi+8]; this
0x180007080  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x180007085  test    eax, eax
0x180007087  jnz     short loc_1800070BC
0x180007089  call    ?UtilIsNetworkRestricted@@YAHXZ; UtilIsNetworkRestricted(void)
0x18000708e  test    eax, eax
0x180007090  jz      short loc_1800070BC
0x180007092  mov     dword ptr [rdi+88h], 3
0x18000709c  mov     rax, [rdi+8]
0x1800070a0  bts     dword ptr [rax+1748h], 0Fh
0x1800070a8  mov     rax, [rdi+8]
0x1800070ac  cmp     [rax+0B658h], r12d
0x1800070b3  jz      short loc_180007072
0x1800070b5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800070ba  jmp     short loc_180007072
0x1800070bc  mov     eax, r12d
0x1800070bf  mov     [rdi+88h], eax
0x1800070c5  mov     rax, [rdi+8]
0x1800070c9  mov     edx, 78h ; 'x'
0x1800070ce  lea     ecx, [rdx-3Ch]
0x1800070d1  cmp     dword ptr [rax+16F0h], 4
0x1800070d8  cmovnz  edx, ecx; unsigned int
0x1800070db  lea     rcx, [rbp+57h+var_88]; this
0x1800070df  call    ??0PdcNetworkActivation@@QEAA@K@Z; PdcNetworkActivation::PdcNetworkActivation(ulong)
0x1800070e4  nop
0x1800070e5  mov     rcx, [rdi+10h]
0x1800070e9  mov     rax, [rcx]
0x1800070ec  mov     [rsp+0E0h+var_C0], r14d; unsigned int
0x1800070f1  lea     r9, [rbp+57h+var_B0]
0x1800070f5  lea     r8, ?Static_TransportCallback@CReportManager@@SAJPEAUTRANSPORT_CALLBACK_PARAM@@PEAX@Z; CReportManager::Static_TransportCallback(TRANSPORT_CALLBACK_PARAM *,void *)
0x1800070fc  mov     rdx, [rdi+8]
0x180007100  mov     rax, [rax+10h]
0x180007104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007109  mov     ebx, eax
0x18000710b  test    eax, eax
0x18000710d  jns     short loc_180007167
0x18000710f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007116  cmp     rcx, r13
0x180007119  jz      short loc_180007136
0x18000711b  test    [rcx+1Ch], r12b
0x18000711f  jz      short loc_180007136
0x180007121  mov     edx, 15h
0x180007126  mov     r9d, eax
0x180007129  mov     r8, rsi
0x18000712c  mov     rcx, [rcx+10h]
0x180007130  call    WPP_SF_d
0x180007135  nop
0x180007136  mov     rcx, [rbp+57h+var_88]
0x18000713a  test    rcx, rcx
0x18000713d  jz      loc_180007255
0x180007143  cmp     [rbp+57h+var_68], 0
0x180007147  jz      short loc_180007156
0x180007149  lea     rcx, [rbp+57h+var_88]; this
0x18000714d  call    ?Deactivate@PdcNetworkActivation@@QEAAXXZ; PdcNetworkActivation::Deactivate(void)
0x180007152  mov     rcx, [rbp+57h+var_88]
0x180007156  call    cs:__imp_Pdcv2ActivationClientUnregister
0x18000715d  nop     dword ptr [rax+rax+00h]
0x180007162  jmp     loc_180007255
0x180007167  mov     rax, [rdi+8]
0x18000716b  mov     ebx, 2
0x180007170  mov     [rax+19E0h], ebx
0x180007176  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000717a  call    cs:__imp_GetSystemTimeAsFileTime
0x180007181  nop     dword ptr [rax+rax+00h]
0x180007186  mov     rcx, [rdi+8]; wchar_t *
0x18000718a  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x18000718d  mov     [rcx+25Ch], eax
0x180007193  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180007196  mov     [rcx+258h], eax
0x18000719c  mov     rax, [rdi+108h]
0x1800071a3  mov     [rbp+57h+var_98], rax
0x1800071a7  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x1800071ab  mov     [rbp+57h+var_98+8], rax
0x1800071af  lea     r8, [rbp+57h+var_98]; void **
0x1800071b3  mov     edx, ebx; unsigned int
0x1800071b5  call    ?UtilMsgWaitForMultipleObjects@@YAKPEB_WKQEAPEAXHK@Z; UtilMsgWaitForMultipleObjects(wchar_t const *,ulong,void * * const,int,ulong)
0x1800071ba  mov     ebx, eax
0x1800071bc  cmp     eax, 0FFFFFFFFh
0x1800071bf  jnz     short loc_1800071CE
0x1800071c1  call    cs:__imp_GetLastError
0x1800071c8  nop     dword ptr [rax+rax+00h]
0x1800071cd  nop
0x1800071ce  lea     rcx, [rbp+57h+var_88]; this
0x1800071d2  call    ??1PdcNetworkActivation@@QEAA@XZ; PdcNetworkActivation::~PdcNetworkActivation(void)
0x1800071d7  test    ebx, ebx
0x1800071d9  jz      short loc_18000720A
0x1800071db  cmp     ebx, 1
0x1800071de  jz      loc_180007287
0x1800071e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071eb  cmp     rcx, r13
0x1800071ee  jz      short loc_18000722D
0x1800071f0  test    byte ptr [rcx+1Ch], 4
0x1800071f4  jz      short loc_180007211
0x1800071f6  mov     edx, 16h
0x1800071fb  mov     r9d, ebx
0x1800071fe  mov     r8, rsi
0x180007201  mov     rcx, [rcx+10h]
0x180007205  call    WPP_SF_d
0x18000720a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007211  cmp     rcx, r13
0x180007214  jz      short loc_18000722D
0x180007216  test    byte ptr [rcx+1Ch], 4
0x18000721a  jz      short loc_18000722D
0x18000721c  mov     edx, 17h
0x180007221  mov     r8, rsi
0x180007224  mov     rcx, [rcx+10h]
0x180007228  call    WPP_SF_
0x18000722d  mov     rcx, rdi; this
0x180007230  call    ?HandleCancellation@CReportManager@@AEAAJXZ; CReportManager::HandleCancellation(void)
0x180007235  mov     rcx, [rdi+18h]
0x180007239  mov     rax, [rcx]
0x18000723c  mov     rax, [rax+38h]
0x180007240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007245  mov     ebx, 801B8001h
0x18000724a  mov     ecx, 1B0000h
0x18000724f  cmp     eax, 5
0x180007252  cmovz   ebx, ecx
0x180007255  lea     rcx, [rbp+57h+var_B0+8]
0x180007259  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18000725e  nop
0x18000725f  lea     rcx, [rbp+57h+var_48]; void *
0x180007263  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007268  mov     eax, ebx
0x18000726a  lea     r11, [rsp+0E0h+var_20]
0x180007272  mov     rbx, [r11+40h]
0x180007276  mov     rsi, [r11+48h]
0x18000727a  mov     rsp, r11
0x18000727d  pop     r14
0x18000727f  pop     r13
0x180007281  pop     r12
0x180007283  pop     rdi
0x180007284  pop     rbp
0x180007285  retn
0x180007287  mov     rcx, cs:WPP_GLOBAL_Control
0x18000728e  cmp     rcx, r13
0x180007291  jz      short loc_1800072B1
0x180007293  test    byte ptr [rcx+1Ch], 4
0x180007297  jz      short loc_1800072B1
0x180007299  mov     edx, 18h
0x18000729e  mov     r8, rsi
0x1800072a1  mov     rcx, [rcx+10h]
0x1800072a5  call    WPP_SF_
0x1800072aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072b1  cmp     dword ptr [rdi+88h], 3
0x1800072b8  jz      loc_180007345
0x1800072be  mov     r9d, [rdi+70h]
0x1800072c2  mov     ebx, 1B0004h
0x1800072c7  cmp     r9d, ebx
0x1800072ca  jz      short loc_180007345
0x1800072cc  lea     eax, [rbx+7]
0x1800072cf  cmp     r9d, eax
0x1800072d2  jz      loc_180006FE3
0x1800072d8  mov     ebx, [rdi+74h]
0x1800072db  cmp     ebx, eax
0x1800072dd  jz      loc_180006FE3
0x1800072e3  test    r9d, r9d
0x1800072e6  js      short loc_180007311
0x1800072e8  cmp     ebx, 8007023Dh
0x1800072ee  jz      loc_180007255
0x1800072f4  cmp     ebx, 8007001Fh
0x1800072fa  jz      loc_180007255
0x180007300  sar     ebx, 1Fh
0x180007303  and     ebx, 0FFFFFFF5h
0x180007306  add     ebx, 1B000Ch
0x18000730c  jmp     loc_180007255
0x180007311  mov     ebx, 801B8001h
0x180007316  cmp     r9d, ebx
0x180007319  jz      loc_180007255
0x18000731f  cmp     rcx, r13
0x180007322  jz      short loc_18000733B
0x180007324  test    [rcx+1Ch], r12b
0x180007328  jz      short loc_18000733B
0x18000732a  mov     edx, 1Fh
0x18000732f  mov     r8, rsi
0x180007332  mov     rcx, [rcx+10h]
0x180007336  call    WPP_SF_d
0x18000733b  mov     ebx, 801B8002h
0x180007340  jmp     loc_180007255
0x180007345  xor     r14d, r14d
0x180007348  mov     dword ptr [rdi+0E8h], 5
0x180007352  mov     rcx, [rdi+8]; this
0x180007356  mov     ebx, 1B0005h
0x18000735b  cmp     [rcx+0B658h], r14d
0x180007362  jnz     short loc_18000736D
0x180007364  call    ?ContainsConfidentialFiles@CReport@@QEAAHXZ; CReport::ContainsConfidentialFiles(void)
0x180007369  test    eax, eax
0x18000736b  jnz     short loc_1800073A1
0x18000736d  call    IsXerTransportEventUploadCompletePresent
0x180007372  test    al, al
  ... truncated ...
```
