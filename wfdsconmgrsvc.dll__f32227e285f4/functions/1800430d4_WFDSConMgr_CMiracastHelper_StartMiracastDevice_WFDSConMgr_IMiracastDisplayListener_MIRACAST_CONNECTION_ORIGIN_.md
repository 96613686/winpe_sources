# WFDSConMgr::CMiracastHelper::StartMiracastDevice(WFDSConMgr::IMiracastDisplayListener *,MIRACAST_CONNECTION_ORIGIN,_GUID const &,WFDSConMgr::IImpersonationProvider const &,WFDSConMgr::IConfigHelper const &,bool &)

- ea: `0x1800430d4`
- end: `0x1800436fe`
- name: `?StartMiracastDevice@CMiracastHelper@WFDSConMgr@@QEAAXPEAVIMiracastDisplayListener@2@W4MIRACAST_CONNECTION_ORIGIN@@AEBU_GUID@@AEBVIImpersonationProvider@2@AEBVIConfigHelper@2@AEA_N@Z`
- size: `1578`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180056344`

## callees

- `0x180004cdc`
- `0x1800059c0`
- `0x18000665c`
- `0x180006740`
- `0x180006780`
- `0x1800426a4`
- `0x180042934`
- `0x180042d20`
- `0x1800430d4`
- `0x18004374c`
- `0x180043a9c`
- `0x180043f64`
- `0x18005c888`
- `0x18005dca0`
- `0x18005df7c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004323c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004344f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043635`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004323c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004344f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043635`

## string_xrefs

- `0x1800436d3`: `Attempt to start Miracast device multiple times`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CMiracastHelper::StartMiracastDevice(
        __int64 a1,
        _BOOL8 a2,
        unsigned int a3,
        __int64 a4,
        struct WFDSConMgr::IImpersonationProvider *a5,
        struct WFDSConMgr::IConfigHelper *a6,
        bool *a7)
{
  bool *v11; // r15
  PVOID *v12; // r10
  __int64 v13; // rax
  __int64 v14; // r10
  __int64 v15; // rax
  __int64 v16; // r11
  char v17; // al
  __int64 v18; // rax
  _DWORD *v19; // rsi
  __int64 v20; // r10
  unsigned int v21; // eax
  char v22; // al
  __int64 v23; // rax
  __int64 v24; // r10
  unsigned int v25; // eax
  char v26; // al
  char v27; // si
  WFDSConMgr::CMiracastHelper *v28; // rbx
  LPCRITICAL_SECTION lpCriticalSection[9]; // [rsp+30h] [rbp-48h] BYREF
  LPCRITICAL_SECTION v30; // [rsp+80h] [rbp+8h] BYREF

  v30 = (LPCRITICAL_SECTION)a1;
  v11 = a7;
  *a7 = 0;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, a1);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 25) >= 4u && (*((_BYTE *)v12 + 28) & 1) != 0 )
    {
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 160);
      WPP_SF_qS_guid_(*(_QWORD *)(v14 + 16), v13, a4);
    }
  }
  WFDSConMgr::CAutoResetEvent::CAutoResetEvent((WFDSConMgr::CAutoResetEvent *)&a7, a2);
  WFDSConMgr::CriticalSection::Lock(a1 + 104, lpCriticalSection);
  if ( *(_BYTE *)(a1 + 144) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      172,
      L"Operation was canceled before starting",
      (const void *)a1);
  if ( *(_BYTE *)(a1 + 257) || *(_BYTE *)(a1 + 258) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      176,
      L"Attempt to start Miracast device multiple times",
      (const void *)a1);
  *(_QWORD *)(a1 + 304) = a2;
  v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 160);
  *(_DWORD *)(a1 + 260) = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, bool *, __int64))(*(_QWORD *)v16 + 8LL))(
                            v16,
                            v15,
                            a3,
                            a7,
                            a4);
  *(_BYTE *)(a1 + 256) = 1;
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  if ( *(_DWORD *)(a1 + 260) > 2u )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids,
        a1,
        *(_DWORD *)(a1 + 260));
    }
    v17 = WFDSConMgr::MiracastDeviceStatusToWin32Error(*(unsigned int *)(a1 + 260));
    WFDSConMgr::CException::Throw(
      v17,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      192,
      L"StartMiracastDisplayDeviceWithActivityId failed",
      (const void *)a1);
  }
  v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 160);
  v19 = (_DWORD *)(a1 + 264);
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v20 + 32LL))(v20, v18, a1 + 264);
  *(_DWORD *)(a1 + 260) = v21;
  if ( v21 > 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, a1, v21);
    }
    v22 = WFDSConMgr::MiracastDeviceStatusToWin32Error(*(unsigned int *)(a1 + 260));
    WFDSConMgr::CException::Throw(
      v22,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      202,
      L"Bad status after StartMiracastDisplayDeviceWithActivityId",
      (const void *)a1);
  }
  if ( (unsigned int)(*v19 - 1) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, a1, *v19);
    }
    WFDSConMgr::CException::Throw(
      6,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      213,
      L"Bad display status state after StartMiracastDisplayDeviceWithActivityId",
      (const void *)a1);
  }
  if ( v21 == 2 )
  {
    WFDSConMgr::WaitMultipleEvents(lpCriticalSection, 120000, &a7, a1 + 152);
    if ( HIDWORD(lpCriticalSection[0]) == 1 )
    {
      WFDSConMgr::CriticalSection::Lock(a1 + 104, &v30);
      *(_BYTE *)(a1 + 257) = 1;
      if ( v30 )
        LeaveCriticalSection(v30);
      WFDSConMgr::CMiracastHelper::StopMiracastDeviceNoThrow((WFDSConMgr::CMiracastHelper *)a1);
      WFDSConMgr::CException::Throw(
        199,
        "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
        234,
        L"StartMiracastDisplayDevice operation canceled",
        (const void *)a1);
    }
  }
  v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 160);
  v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 32LL))(v24, v23, a1 + 264);
  *(_DWORD *)(a1 + 260) = v25;
  if ( v25 > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, a1, v25);
    }
    v26 = WFDSConMgr::MiracastDeviceStatusToWin32Error(*(unsigned int *)(a1 + 260));
    WFDSConMgr::CException::Throw(
      v26,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      244,
      L"Bad status after StartMiracastDisplayDeviceWithActivityId event signaled",
      (const void *)a1);
  }
  if ( *v19 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, a1, *v19);
    }
    WFDSConMgr::CException::Throw(
      6,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      254,
      L"Bad display status state after StartMiracastDisplayDeviceWithActivityId event signaled",
      (const void *)a1);
  }
  v27 = 0;
  WFDSConMgr::CMiracastHelper::EnableUibcSettingsOnStart((WFDSConMgr::CMiracastHelper *)a1, a5, a6, v11);
  WFDSConMgr::CriticalSection::Lock(a1 + 104, lpCriticalSection);
  if ( *(_BYTE *)(a1 + 144) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, a1);
    }
    v27 = 1;
  }
  *(_BYTE *)(a1 + 257) = 1;
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  if ( v27 )
  {
    WFDSConMgr::CMiracastHelper::StopMiracastDevice((WFDSConMgr::CMiracastHelper *)a1);
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMiracastHelper::StartMiracastDevice",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      38,
      L"StartMiracastDisplayDevice operation canceled",
      (const void *)a1);
  }
  try
  {
    WFDSConMgr::CMiracastHelper::RegisterDisplayStateChangeUpdates((WFDSConMgr::CMiracastHelper *)a1);
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v28 = (WFDSConMgr::CMiracastHelper *)v30;
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, v30);
    }
    else
    {
      v28 = (WFDSConMgr::CMiracastHelper *)v30;
    }
    WFDSConMgr::CMiracastHelper::StopMiracastDevice(v28);
    throw;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, a1);
  }
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)&a7);
}

```

## disassembly

```asm
0x1800430d4  mov     [rsp+arg_0], rcx
0x1800430d9  push    rbx
0x1800430da  push    rsi
0x1800430db  push    r12
0x1800430dd  push    r13
0x1800430df  push    r14
0x1800430e1  push    r15
0x1800430e3  sub     rsp, 48h
0x1800430e7  mov     rsi, r9
0x1800430ea  mov     r13d, r8d
0x1800430ed  mov     r12, rdx
0x1800430f0  mov     rbx, rcx
0x1800430f3  mov     r15, [rsp+78h+arg_30]
0x1800430fb  mov     byte ptr [r15], 0
0x1800430ff  lea     r14, WPP_GLOBAL_Control
0x180043106  mov     r10, cs:WPP_GLOBAL_Control
0x18004310d  cmp     r10, r14
0x180043110  jz      short loc_180043174
0x180043112  cmp     byte ptr [r10+19h], 4
0x180043117  jb      short loc_18004313F
0x180043119  test    byte ptr [r10+1Ch], 1
0x18004311e  jz      short loc_18004313F
0x180043120  mov     edx, 0Bh
0x180043125  mov     r9, rcx
0x180043128  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x18004312f  mov     rcx, [r10+10h]
0x180043133  call    WPP_SF_q
0x180043138  mov     r10, cs:WPP_GLOBAL_Control
0x18004313f  cmp     r10, r14
0x180043142  jz      short loc_180043174
0x180043144  cmp     byte ptr [r10+19h], 4
0x180043149  jb      short loc_180043174
0x18004314b  test    byte ptr [r10+1Ch], 1
0x180043150  jz      short loc_180043174
0x180043152  lea     rcx, [rbx+0A0h]
0x180043159  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004315e  mov     [rsp+78h+var_50], rsi; __int64
0x180043163  mov     [rsp+78h+var_58], rax; __int64
0x180043168  mov     r9, rbx
0x18004316b  mov     rcx, [r10+10h]; LoggerHandle
0x18004316f  call    WPP_SF_qS_guid_
0x180043174  lea     rcx, [rsp+78h+arg_30]; this
0x18004317c  call    ??0CAutoResetEvent@WFDSConMgr@@QEAA@_N@Z; WFDSConMgr::CAutoResetEvent::CAutoResetEvent(bool)
0x180043181  nop
0x180043182  lea     r14, [rbx+68h]
0x180043186  lea     rdx, [rsp+78h+lpCriticalSection]
0x18004318b  mov     rcx, r14
0x18004318e  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180043193  nop
0x180043194  xor     eax, eax
0x180043196  cmp     [rbx+90h], al
0x18004319c  jz      short loc_1800431CE
0x18004319e  mov     [rsp+78h+var_50], rbx; void *
0x1800431a3  lea     rax, aOperationWasCa; "Operation was canceled before starting"
0x1800431aa  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1800431af  mov     r9d, 0ACh; char
0x1800431b5  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800431bc  lea     rdx, aWfdsconmgrCmir_5; "WFDSConMgr::CMiracastHelper::StartMirac"...
0x1800431c3  mov     ecx, 800704C7h; char
0x1800431c8  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800431ce  cmp     [rbx+101h], al
0x1800431d4  jnz     loc_1800436CE
0x1800431da  cmp     [rbx+102h], al
0x1800431e0  jnz     loc_1800436CE
0x1800431e6  mov     [rbx+130h], r12
0x1800431ed  mov     r11, [rbx+18h]
0x1800431f1  lea     r12, [rbx+0A0h]
0x1800431f8  mov     rcx, r12
0x1800431fb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043200  mov     r10, rax
0x180043203  mov     rdx, [r11]
0x180043206  mov     rax, [rdx+8]
0x18004320a  mov     [rsp+78h+var_58], rsi
0x18004320f  mov     r9, [rsp+78h+arg_30]
0x180043217  mov     r8d, r13d
0x18004321a  mov     rdx, r10
0x18004321d  mov     rcx, r11
0x180043220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043225  mov     [rbx+104h], eax
0x18004322b  mov     byte ptr [rbx+100h], 1
0x180043232  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x180043237  test    rcx, rcx
0x18004323a  jz      short loc_180043242
0x18004323c  call    cs:__imp_LeaveCriticalSection
0x180043242  mov     eax, [rbx+104h]
0x180043248  cmp     eax, 2
0x18004324b  jbe     short loc_1800432CC
0x18004324d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043254  lea     r14, WPP_GLOBAL_Control
0x18004325b  cmp     rcx, r14
0x18004325e  jz      short loc_180043288
0x180043260  cmp     byte ptr [rcx+19h], 1
0x180043264  jb      short loc_180043288
0x180043266  test    byte ptr [rcx+1Ch], 1
0x18004326a  jz      short loc_180043288
0x18004326c  mov     edx, 0Dh
0x180043271  mov     dword ptr [rsp+78h+var_58], eax
0x180043275  mov     r9, rbx
0x180043278  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x18004327f  mov     rcx, [rcx+10h]
0x180043283  call    WPP_SF_qD
0x180043288  mov     ecx, [rbx+104h]
0x18004328e  call    ?MiracastDeviceStatusToWin32Error@WFDSConMgr@@YAKW4MIRACAST_DEVICE_STATUS@@@Z; WFDSConMgr::MiracastDeviceStatusToWin32Error(MIRACAST_DEVICE_STATUS)
0x180043293  test    eax, eax
0x180043295  jle     short loc_18004329F
0x180043297  movzx   eax, ax
0x18004329a  or      eax, 80070000h
0x18004329f  mov     [rsp+78h+var_50], rbx; void *
0x1800432a4  lea     rcx, aStartmiracastd; "StartMiracastDisplayDeviceWithActivityI"...
0x1800432ab  mov     [rsp+78h+var_58], rcx; unsigned __int16 *
0x1800432b0  mov     r9d, 0C0h; char
0x1800432b6  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800432bd  lea     rdx, aWfdsconmgrCmir_5; "WFDSConMgr::CMiracastHelper::StartMirac"...
0x1800432c4  mov     ecx, eax; char
0x1800432c6  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800432cc  mov     r10, [rbx+18h]
0x1800432d0  mov     rcx, r12
0x1800432d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800432d8  mov     r9, rax
0x1800432db  lea     rsi, [rbx+108h]
0x1800432e2  mov     rdx, [r10]
0x1800432e5  mov     rax, [rdx+20h]
0x1800432e9  mov     r8, rsi
0x1800432ec  mov     rdx, r9
0x1800432ef  mov     rcx, r10
0x1800432f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432f7  mov     r8d, eax
0x1800432fa  mov     [rbx+104h], eax
0x180043300  cmp     eax, 2
0x180043303  jbe     short loc_180043384
0x180043305  mov     rcx, cs:WPP_GLOBAL_Control
0x18004330c  lea     r14, WPP_GLOBAL_Control
0x180043313  cmp     rcx, r14
0x180043316  jz      short loc_180043340
0x180043318  cmp     byte ptr [rcx+19h], 1
0x18004331c  jb      short loc_180043340
0x18004331e  test    byte ptr [rcx+1Ch], 1
0x180043322  jz      short loc_180043340
0x180043324  mov     edx, 0Eh
0x180043329  mov     dword ptr [rsp+78h+var_58], eax
0x18004332d  mov     r9, rbx
0x180043330  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x180043337  mov     rcx, [rcx+10h]
0x18004333b  call    WPP_SF_qD
0x180043340  mov     ecx, [rbx+104h]
0x180043346  call    ?MiracastDeviceStatusToWin32Error@WFDSConMgr@@YAKW4MIRACAST_DEVICE_STATUS@@@Z; WFDSConMgr::MiracastDeviceStatusToWin32Error(MIRACAST_DEVICE_STATUS)
0x18004334b  test    eax, eax
0x18004334d  jle     short loc_180043357
0x18004334f  movzx   eax, ax
0x180043352  or      eax, 80070000h
0x180043357  mov     [rsp+78h+var_50], rbx; void *
0x18004335c  lea     rcx, aBadStatusAfter_0; "Bad status after StartMiracastDisplayDe"...
0x180043363  mov     [rsp+78h+var_58], rcx; unsigned __int16 *
0x180043368  mov     r9d, 0CAh; char
0x18004336e  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180043375  lea     rdx, aWfdsconmgrCmir_5; "WFDSConMgr::CMiracastHelper::StartMirac"...
0x18004337c  mov     ecx, eax; char
0x18004337e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180043384  mov     r9d, [rsi]
0x180043387  lea     eax, [r9-1]
0x18004338b  cmp     eax, 1
0x18004338e  jbe     short loc_1800433FC
0x180043390  mov     rcx, cs:WPP_GLOBAL_Control
0x180043397  lea     r14, WPP_GLOBAL_Control
0x18004339e  cmp     rcx, r14
0x1800433a1  jz      short loc_1800433CC
0x1800433a3  cmp     byte ptr [rcx+19h], 1
0x1800433a7  jb      short loc_1800433CC
0x1800433a9  test    byte ptr [rcx+1Ch], 1
0x1800433ad  jz      short loc_1800433CC
0x1800433af  mov     edx, 0Fh
0x1800433b4  mov     dword ptr [rsp+78h+var_58], r9d
0x1800433b9  mov     r9, rbx
0x1800433bc  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x1800433c3  mov     rcx, [rcx+10h]
0x1800433c7  call    WPP_SF_qD
0x1800433cc  mov     [rsp+78h+var_50], rbx; void *
0x1800433d1  lea     rax, aBadDisplayStat_1; "Bad display status state after StartMir"...
0x1800433d8  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1800433dd  mov     r9d, 0D5h; char
0x1800433e3  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800433ea  lea     rdx, aWfdsconmgrCmir_5; "WFDSConMgr::CMiracastHelper::StartMirac"...
0x1800433f1  mov     ecx, 80070306h; char
0x1800433f6  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800433fc  cmp     r8d, 2
0x180043400  jnz     loc_18004348D
0x180043406  lea     r9, [rbx+98h]
0x18004340d  lea     r8, [rsp+78h+arg_30]
0x180043415  mov     edx, 1D4C0h
0x18004341a  lea     rcx, [rsp+78h+lpCriticalSection]
0x18004341f  call    ?WaitMultipleEvents@WFDSConMgr@@YA?AVCWaitResult@1@KAEBVCEventWrapper@1@0@Z; WFDSConMgr::WaitMultipleEvents(ulong,WFDSConMgr::CEventWrapper const &,WFDSConMgr::CEventWrapper const &)
0x180043424  cmp     dword ptr [rsp+78h+lpCriticalSection+4], 1
0x180043429  jnz     short loc_18004348D
0x18004342b  lea     rdx, [rsp+78h+arg_0]
0x180043433  mov     rcx, r14
0x180043436  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004343b  mov     byte ptr [rbx+101h], 1
0x180043442  mov     rcx, [rsp+78h+arg_0]; lpCriticalSection
0x18004344a  test    rcx, rcx
0x18004344d  jz      short loc_180043455
0x18004344f  call    cs:__imp_LeaveCriticalSection
0x180043455  mov     rcx, rbx; this
0x180043458  call    ?StopMiracastDeviceNoThrow@CMiracastHelper@WFDSConMgr@@QEAAKXZ; WFDSConMgr::CMiracastHelper::StopMiracastDeviceNoThrow(void)
0x18004345d  mov     [rsp+78h+var_50], rbx; void *
0x180043462  lea     rax, aStartmiracastd_0; "StartMiracastDisplayDevice operation ca"...
0x180043469  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004346e  mov     r9d, 0EAh; char
0x180043474  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004347b  lea     rdx, aWfdsconmgrCmir_5; "WFDSConMgr::CMiracastHelper::StartMirac"...
0x180043482  mov     ecx, 800704C7h; char
0x180043487  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004348d  mov     r10, [rbx+18h]
0x180043491  mov     rcx, r12
0x180043494  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043499  mov     rdx, [r10]
0x18004349c  mov     r9, [rdx+20h]
0x1800434a0  mov     r8, rsi
0x1800434a3  mov     rdx, rax
0x1800434a6  mov     rcx, r10
0x1800434a9  mov     rax, r9
0x1800434ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434b1  mov     [rbx+104h], eax
0x1800434b7  cmp     eax, 1
0x1800434ba  jbe     short loc_18004353B
0x1800434bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800434c3  lea     r14, WPP_GLOBAL_Control
0x1800434ca  cmp     rcx, r14
0x1800434cd  jz      short loc_1800434F7
0x1800434cf  cmp     byte ptr [rcx+19h], 1
0x1800434d3  jb      short loc_1800434F7
0x1800434d5  test    byte ptr [rcx+1Ch], 1
0x1800434d9  jz      short loc_1800434F7
0x1800434db  mov     edx, 10h
0x1800434e0  mov     dword ptr [rsp+78h+var_58], eax
0x1800434e4  mov     r9, rbx
0x1800434e7  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x1800434ee  mov     rcx, [rcx+10h]
0x1800434f2  call    WPP_SF_qD
0x1800434f7  mov     ecx, [rbx+104h]
0x1800434fd  call    ?MiracastDeviceStatusToWin32Error@WFDSConMgr@@YAKW4MIRACAST_DEVICE_STATUS@@@Z; WFDSConMgr::MiracastDeviceStatusToWin32Error(MIRACAST_DEVICE_STATUS)
0x180043502  test    eax, eax
0x180043504  jle     short loc_18004350E
0x180043506  movzx   eax, ax
0x180043509  or      eax, 80070000h
0x18004350e  mov     [rsp+78h+var_50], rbx; void *
0x180043513  lea     rcx, aBadStatusAfter_1; "Bad status after StartMiracastDisplayDe"...
0x18004351a  mov     [rsp+78h+var_58], rcx; unsigned __int16 *
0x18004351f  mov     r9d, 0F4h; char
0x180043525  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004352c  lea     rdx, aWfdsconmgrCmir_5; "WFDSConMgr::CMiracastHelper::StartMirac"...
0x180043533  mov     ecx, eax; char
0x180043535  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004353b  mov     eax, [rsi]
0x18004353d  cmp     eax, 2
0x180043540  jz      short loc_1800435AD
0x180043542  mov     rcx, cs:WPP_GLOBAL_Control
0x180043549  lea     r14, WPP_GLOBAL_Control
0x180043550  cmp     rcx, r14
0x180043553  jz      short loc_18004357D
0x180043555  cmp     byte ptr [rcx+19h], 1
0x180043559  jb      short loc_18004357D
0x18004355b  test    byte ptr [rcx+1Ch], 1
0x18004355f  jz      short loc_18004357D
0x180043561  mov     edx, 11h
0x180043566  mov     dword ptr [rsp+78h+var_58], eax
0x18004356a  mov     r9, rbx
0x18004356d  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x180043574  mov     rcx, [rcx+10h]
0x180043578  call    WPP_SF_qD
0x18004357d  mov     [rsp+78h+var_50], rbx; void *
0x180043582  lea     rax, aBadDisplayStat; "Bad display status state after StartMir"...
0x180043589  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004358e  mov     r9d, 0FEh; char
0x180043594  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004359b  lea     rdx, aWfdsconmgrCmir_5; "WFDSConMgr::CMiracastHelper::StartMirac"...
0x1800435a2  mov     ecx, 80070306h; char
0x1800435a7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800435ad  xor     sil, sil
0x1800435b0  mov     r9, r15; bool *
0x1800435b3  mov     r8, [rsp+78h+arg_28]; struct WFDSConMgr::IConfigHelper *
0x1800435bb  mov     rdx, [rsp+78h+arg_20]; struct WFDSConMgr::IImpersonationProvider *
0x1800435c3  mov     rcx, rbx; this
0x1800435c6  call    ?EnableUibcSettingsOnStart@CMiracastHelper@WFDSConMgr@@AEAAXAEBVIImpersonationProvider@2@AEBVIConfigHelper@2@AEA_N@Z; WFDSConMgr::CMiracastHelper::EnableUibcSettingsOnStart(WFDSConMgr::IImpersonationProvider const &,WFDSConMgr::IConfigHelper const &,bool &)
0x1800435cb  lea     rdx, [rsp+78h+lpCriticalSection]
0x1800435d0  mov     rcx, r14
0x1800435d3  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x1800435d8  cmp     [rbx+90h], sil
0x1800435df  jz      short loc_18004361D
0x1800435e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800435e8  lea     r14, WPP_GLOBAL_Control
0x1800435ef  cmp     rcx, r14
0x1800435f2  jz      short loc_180043618
0x1800435f4  cmp     byte ptr [rcx+19h], 1
0x1800435f8  jb      short loc_180043618
0x1800435fa  test    byte ptr [rcx+1Ch], 1
0x1800435fe  jz      short loc_180043618
0x180043600  mov     edx, 12h
0x180043605  mov     r9, rbx
0x180043608  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x18004360f  mov     rcx, [rcx+10h]
  ... truncated ...
```
