# WFDSConMgr::CSessionManager::QueryStatus(void *,ulong *,_WFDSConMgrSessionStatus * *)

- ea: `0x180034248`
- end: `0x180034792`
- name: `?QueryStatus@CSessionManager@WFDSConMgr@@QEBAXPEAXPEAKPEAPEAU_WFDSConMgrSessionStatus@@@Z`
- size: `1354`
- prototype: `void __fastcall(WFDSConMgr::CSessionManager *__hidden this, void *, unsigned int *, struct _WFDSConMgrSessionStatus **)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18001c8b4`

## callees

- `0x180002600`
- `0x18000444e`
- `0x18000475c`
- `0x180004c7c`
- `0x18000665c`
- `0x180006740`
- `0x18000a010`
- `0x18000f120`
- `0x18001a21c`
- `0x180032038`
- `0x1800321c8`
- `0x180033428`
- `0x180034248`
- `0x18003588c`
- `0x18003595c`
- `0x18003a100`
- `0x18003a14c`
- `0x18003a274`
- `0x18003a684`
- `0x18003e4f4`
- `0x18003e580`
- `0x18005c888`
- `0x18005f95c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800346dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800346dc`

## string_xrefs

- `0x180034419`: `Overflow in computing WFDSConMgrSessionStatus size`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WFDSConMgr::CSessionManager::QueryStatus(
        RTL_SRWLOCK *this,
        void *a2,
        unsigned int *a3,
        struct _WFDSConMgrSessionStatus **a4)
{
  struct _WFDSConMgrSessionStatus **v4; // rdi
  unsigned int *v5; // rbx
  WFDSConMgr::CRemoteDevice *v8; // r15
  struct WFDSConMgr::CMiracastHelper *MiracastHelper; // rax
  struct WFDSConMgr::CMaUsbHelper *MaUsbHelper; // rax
  unsigned __int64 v11; // r13
  unsigned int v12; // eax
  unsigned __int64 v13; // r12
  unsigned int v14; // ecx
  _DWORD *v15; // rsi
  struct WFDSConMgr::CSessionStateMachine *StateMachine; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  _QWORD *DevQueryShim; // rax
  int v20; // edi
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  struct WFDSConMgr::CSessionStateMachine *v25; // rax
  const void *v26; // rax
  size_t v27; // r8
  __int64 v28; // rax
  __int64 v29; // r8
  unsigned int v30; // r13d
  struct WFDSConMgr::CSessionStateMachine *v31; // rax
  void *v32; // rdx
  const void *v33; // rax
  size_t v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  struct WFDSConMgr::CPairContext *Context; // [rsp+50h] [rbp-89h]
  int RemoteInputState; // [rsp+50h] [rbp-89h]
  int v39; // [rsp+58h] [rbp-81h]
  unsigned int v40; // [rsp+5Ch] [rbp-7Dh]
  WFDSConMgr::Common *v41; // [rsp+60h] [rbp-79h] BYREF
  unsigned int *v42; // [rsp+68h] [rbp-71h]
  struct _WFDSConMgrSessionStatus **v43; // [rsp+70h] [rbp-69h]
  _BYTE v44[16]; // [rsp+78h] [rbp-61h] BYREF
  WFDSConMgr::CRemoteDevice *v45; // [rsp+88h] [rbp-51h] BYREF
  std::_Ref_count_base *v46; // [rsp+90h] [rbp-49h]
  PSRWLOCK SRWLock; // [rsp+98h] [rbp-41h] BYREF
  char v48; // [rsp+A0h] [rbp-39h]
  _BYTE v49[16]; // [rsp+A8h] [rbp-31h] BYREF
  unsigned int v50; // [rsp+B8h] [rbp-21h]
  _BYTE v51[16]; // [rsp+C8h] [rbp-11h] BYREF
  unsigned int v52; // [rsp+D8h] [rbp-1h]

  v4 = a4;
  v43 = a4;
  v5 = a3;
  v42 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids, this);
  }
  if ( !v5 || !v4 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CSessionManager::QueryStatus",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      72,
      L"Missing required parameter to query status",
      this);
  *v5 = 0;
  *v4 = 0;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    this + 2);
  Context = WFDSConMgr::CSessionManager::GetContext((WFDSConMgr::CSessionManager *)this, a2);
  WFDSConMgr::CPairContext::GetRemoteDevice(Context, &v45);
  v8 = v45;
  if ( !v45 )
    WFDSConMgr::CException::Throw(
      6,
      "WFDSConMgr::CSessionManager::QueryStatus",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      98,
      L"Can't query status with unassociated handle",
      this);
  MiracastHelper = WFDSConMgr::CRemoteDevice::GetMiracastHelper(v45);
  std::wstring::wstring(v51, (char *)MiracastHelper + 224);
  MaUsbHelper = WFDSConMgr::CRemoteDevice::GetMaUsbHelper(v8);
  std::wstring::wstring(v49, (char *)MaUsbHelper + 280);
  v11 = 2LL * v52;
  if ( v11 > 0xFFFFFFFF )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CSessionManager::QueryStatus",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      113,
      L"Overflow in calculating cbMiracastDisplayDeviceInterfaceId",
      this);
  v12 = v11 + 32;
  if ( (unsigned int)v11 >= 0xFFFFFFE0 )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CSessionManager::QueryStatus",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      116,
      L"Overflow in calculating cbTransportStatusListSize+cbMiracastDisplayDeviceInterfaceId",
      this);
  v13 = 2LL * v50;
  if ( v13 > 0xFFFFFFFF )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CSessionManager::QueryStatus",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      119,
      L"Overflow in calculating cbMiracastDisplayDeviceInterfaceId",
      this);
  v14 = v13 + v12;
  v39 = v13 + v12;
  if ( (unsigned int)v13 + v12 < v12 )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CSessionManager::QueryStatus",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      122,
      L"Overflow in calculating cbTransportStatusListSize+cbMaUsbDeviceInterfaceId",
      this);
  v40 = v14 + 20;
  if ( v14 >= 0xFFFFFFEC )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CSessionManager::QueryStatus",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\sessionmanager.cpp",
      125,
      L"Overflow in computing WFDSConMgrSessionStatus size",
      this);
  v15 = WFDSConMgr::Common::AllocExternalMemory((WFDSConMgr::Common *)(v14 + 20));
  v41 = (WFDSConMgr::Common *)v15;
  StateMachine = WFDSConMgr::CRemoteDevice::GetStateMachine(v8);
  *v15 = WFDSConMgr::CSessionStateMachine::GetWFDState(StateMachine);
  DevQueryShim = (_QWORD *)WFDSConMgr::CConnectManager::GetDevQueryShim(Context, v44, v17, v18);
  RemoteInputState = WFDSConMgr::CRemoteDevice::GetRemoteInputState((char *)v8, 1, DevQueryShim);
  v15[1] = RemoteInputState;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v20 = *v15;
    v21 = (*(__int64 (__fastcall **)(WFDSConMgr::CRemoteDevice *))(*(_QWORD *)v8 + 40LL))(v8);
    v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    v23 = (*(__int64 (__fastcall **)(WFDSConMgr::CRemoteDevice *))(*(_QWORD *)v8 + 32LL))(v8);
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    WPP_SF_qqSSLL(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)v8, v24, v22, v20, RemoteInputState);
    v5 = v42;
    v4 = v43;
  }
  v15[3] = 2;
  v15[2] = 20;
  v15[4] = v39;
  v15[5] = 1;
  v25 = WFDSConMgr::CRemoteDevice::GetStateMachine(v8);
  v15[6] = WFDSConMgr::CSessionStateMachine::GetStackState(v25, 1);
  v15[7] = 52;
  v15[8] = v11;
  if ( (_DWORD)v11 )
  {
    v26 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
    memcpy_0(v15 + 13, v26, v27);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
    WPP_SF_qqLLS(*(_QWORD *)(v29 + 16), 42, v29, (_DWORD)this, (char)v8, v15[5], v15[6], v28);
  }
  v30 = v11 + 52;
  v15[9] = 2;
  v31 = WFDSConMgr::CRemoteDevice::GetStateMachine(v8);
  v15[10] = WFDSConMgr::CSessionStateMachine::GetStackState(v31, 2);
  v15[11] = v30;
  v15[12] = v13;
  if ( (_DWORD)v13 )
  {
    v33 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
    memcpy_0((char *)v15 + v30, v33, v34);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
    WPP_SF_qqLLS(*(_QWORD *)(v36 + 16), 43, v36, (_DWORD)this, (char)v8, v15[9], v15[10], v35);
  }
  *v5 = v40;
  v41 = 0;
  *v4 = (struct _WFDSConMgrSessionStatus *)v15;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids, this);
  }
  std::unique_ptr<unsigned char [0],WFDSConMgr::Common::FreeDeleter>::~unique_ptr<unsigned char [0],WFDSConMgr::Common::FreeDeleter>(
    &v41,
    v32);
  std::wstring::_Tidy_deallocate(v49);
  std::wstring::_Tidy_deallocate(v51);
  if ( v46 )
    std::_Ref_count_base::_Decref(v46);
  if ( v48 )
  {
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
  }
}

```

## disassembly

```asm
0x180034248  push    rbp
0x18003424a  push    rbx
0x18003424b  push    rsi
0x18003424c  push    rdi
0x18003424d  push    r12
0x18003424f  push    r13
0x180034251  push    r14
0x180034253  push    r15
0x180034255  lea     rbp, [rsp-1Fh]
0x18003425a  sub     rsp, 0F8h
0x180034261  mov     rax, cs:__security_cookie
0x180034268  xor     rax, rsp
0x18003426b  mov     [rbp+57h+var_48], rax
0x18003426f  mov     rdi, r9
0x180034272  mov     [rbp+57h+var_C0], r9
0x180034276  mov     rbx, r8
0x180034279  mov     [rbp+57h+var_C8], rbx
0x18003427d  mov     rsi, rdx
0x180034280  mov     r14, rcx
0x180034283  lea     rax, WPP_GLOBAL_Control
0x18003428a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034291  cmp     rcx, rax
0x180034294  jz      short loc_1800342BA
0x180034296  cmp     byte ptr [rcx+19h], 4
0x18003429a  jb      short loc_1800342BA
0x18003429c  test    byte ptr [rcx+1Ch], 1
0x1800342a0  jz      short loc_1800342BA
0x1800342a2  mov     edx, 28h ; '('
0x1800342a7  mov     r9, r14
0x1800342aa  lea     r8, WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids
0x1800342b1  mov     rcx, [rcx+10h]
0x1800342b5  call    WPP_SF_q
0x1800342ba  test    rbx, rbx
0x1800342bd  jz      loc_180034762
0x1800342c3  test    rdi, rdi
0x1800342c6  jz      loc_180034762
0x1800342cc  mov     dword ptr [rbx], 0
0x1800342d2  mov     qword ptr [rdi], 0
0x1800342d9  lea     rdx, [r14+10h]
0x1800342dd  lea     rcx, [rbp+57h+SRWLock]
0x1800342e1  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x1800342e6  nop
0x1800342e7  mov     rdx, rsi; void *
0x1800342ea  mov     rcx, r14; this
0x1800342ed  call    ?GetContext@CSessionManager@WFDSConMgr@@AEBAPEAVCPairContext@2@PEAX@Z; WFDSConMgr::CSessionManager::GetContext(void *)
0x1800342f2  mov     qword ptr [rsp+130h+var_E0], rax
0x1800342f7  lea     rdx, [rbp+57h+var_A8]
0x1800342fb  mov     rcx, rax
0x1800342fe  call    ?GetRemoteDevice@CPairContext@WFDSConMgr@@QEAA?AV?$shared_ptr@VCRemoteDevice@WFDSConMgr@@@std@@XZ; WFDSConMgr::CPairContext::GetRemoteDevice(void)
0x180034303  nop
0x180034304  mov     r15, [rbp+57h+var_A8]
0x180034308  test    r15, r15
0x18003430b  jnz     short loc_18003433D
0x18003430d  mov     [rsp+130h+var_108], r14; void *
0x180034312  lea     rax, aCanTQueryStatu; "Can't query status with unassociated ha"...
0x180034319  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18003431e  mov     r9d, 362h; char
0x180034324  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18003432b  lea     rdx, aWfdsconmgrCses_39; "WFDSConMgr::CSessionManager::QueryStatu"...
0x180034332  mov     ecx, 80070006h; char
0x180034337  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003433d  mov     rcx, r15; this
0x180034340  call    ?GetMiracastHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMiracastHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastHelper(void)
0x180034345  lea     rdx, [rax+0E0h]
0x18003434c  lea     rcx, [rbp+57h+var_68]
0x180034350  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034355  nop
0x180034356  mov     rcx, r15; this
0x180034359  call    ?GetMaUsbHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMaUsbHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMaUsbHelper(void)
0x18003435e  lea     rdx, [rax+118h]
0x180034365  lea     rcx, [rbp+57h+var_88]
0x180034369  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003436e  nop
0x18003436f  mov     r13d, [rbp+57h+var_58]
0x180034373  add     r13, r13
0x180034376  mov     ecx, 0FFFFFFFFh
0x18003437b  cmp     r13, rcx
0x18003437e  ja      loc_180034732
0x180034384  lea     eax, [r13+20h]
0x180034388  cmp     eax, 20h ; ' '
0x18003438b  jnb     short loc_1800343BD
0x18003438d  mov     [rsp+130h+var_108], r14; void *
0x180034392  lea     rax, aOverflowInCalc_6; "Overflow in calculating cbTransportStat"...
0x180034399  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18003439e  mov     r9d, 374h; char
0x1800343a4  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800343ab  lea     rdx, aWfdsconmgrCses_39; "WFDSConMgr::CSessionManager::QueryStatu"...
0x1800343b2  mov     ecx, 80070216h; char
0x1800343b7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800343bd  mov     r12d, [rbp+57h+var_78]
0x1800343c1  add     r12, r12
0x1800343c4  cmp     r12, rcx
0x1800343c7  ja      loc_180034702
0x1800343cd  lea     ecx, [r12+rax]
0x1800343d1  mov     [rsp+130h+var_D8], ecx
0x1800343d5  cmp     ecx, eax
0x1800343d7  jnb     short loc_180034409
0x1800343d9  mov     [rsp+130h+var_108], r14; void *
0x1800343de  lea     rax, aOverflowInCalc_2; "Overflow in calculating cbTransportStat"...
0x1800343e5  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1800343ea  mov     r9d, 37Ah; char
0x1800343f0  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800343f7  lea     rdx, aWfdsconmgrCses_39; "WFDSConMgr::CSessionManager::QueryStatu"...
0x1800343fe  mov     ecx, 80070216h; char
0x180034403  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180034409  lea     eax, [rcx+14h]
0x18003440c  mov     [rbp+57h+var_D4], eax
0x18003440f  cmp     eax, 14h
0x180034412  jnb     short loc_180034444
0x180034414  mov     [rsp+130h+var_108], r14; void *
0x180034419  lea     rax, aOverflowInComp; "Overflow in computing WFDSConMgrSession"...
0x180034420  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x180034425  mov     r9d, 37Dh; char
0x18003442b  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180034432  lea     rdx, aWfdsconmgrCses_39; "WFDSConMgr::CSessionManager::QueryStatu"...
0x180034439  mov     ecx, 80070216h; char
0x18003443e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180034444  mov     ecx, eax; this
0x180034446  call    ?AllocExternalMemory@Common@WFDSConMgr@@YAPEAX_K@Z; WFDSConMgr::Common::AllocExternalMemory(unsigned __int64)
0x18003444b  mov     rsi, rax
0x18003444e  mov     [rbp+57h+var_D0], rax
0x180034452  mov     rcx, r15; this
0x180034455  call    ?GetStateMachine@CRemoteDevice@WFDSConMgr@@QEAAAEAVCSessionStateMachine@2@XZ; WFDSConMgr::CRemoteDevice::GetStateMachine(void)
0x18003445a  mov     rcx, rax
0x18003445d  call    ?GetWFDState@CSessionStateMachine@WFDSConMgr@@QEBA?AW4_WFDSConMgrWFDStatus@@XZ; WFDSConMgr::CSessionStateMachine::GetWFDState(void)
0x180034462  mov     [rsi], eax
0x180034464  lea     rdx, [rbp+57h+var_B8]
0x180034468  mov     rcx, qword ptr [rsp+130h+var_E0]
0x18003446d  call    ?GetDevQueryShim@CConnectManager@WFDSConMgr@@QEAA?AV?$shared_ptr@VCDevQueryShim@WFDSConMgr@@@std@@XZ; WFDSConMgr::CConnectManager::GetDevQueryShim(void)
0x180034472  mov     r8, rax
0x180034475  mov     dl, 1
0x180034477  mov     rcx, r15; void *
0x18003447a  call    ?GetRemoteInputState@CRemoteDevice@WFDSConMgr@@QEAA?AW4_WFDSConMgrRemoteInputState@@_NV?$shared_ptr@VIImpersonationProvider@WFDSConMgr@@@std@@@Z; WFDSConMgr::CRemoteDevice::GetRemoteInputState(bool,std::shared_ptr<WFDSConMgr::IImpersonationProvider>)
0x18003447f  mov     dword ptr [rsp+130h+var_E0], eax
0x180034483  mov     [rsi+4], eax
0x180034486  mov     rcx, cs:WPP_GLOBAL_Control
0x18003448d  lea     rax, WPP_GLOBAL_Control
0x180034494  cmp     rcx, rax
0x180034497  jz      short loc_180034513
0x180034499  cmp     byte ptr [rcx+19h], 3
0x18003449d  jb      short loc_180034513
0x18003449f  test    byte ptr [rcx+1Ch], 1
0x1800344a3  jz      short loc_180034513
0x1800344a5  mov     edi, [rsi]
0x1800344a7  mov     rax, [r15]
0x1800344aa  mov     rcx, r15
0x1800344ad  mov     rax, [rax+28h]
0x1800344b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344b6  mov     rcx, rax
0x1800344b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800344be  mov     rbx, rax
0x1800344c1  mov     rcx, [r15]
0x1800344c4  mov     rax, [rcx+20h]
0x1800344c8  mov     rcx, r15
0x1800344cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344d0  mov     rcx, rax
0x1800344d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800344d8  mov     edx, 29h ; ')'
0x1800344dd  mov     ecx, dword ptr [rsp+130h+var_E0]
0x1800344e1  mov     dword ptr [rsp+130h+var_F0], ecx; char
0x1800344e5  mov     dword ptr [rsp+130h+var_F8], edi; char
0x1800344e9  mov     [rsp+130h+var_100], rbx; __int64
0x1800344ee  mov     [rsp+130h+var_108], rax; __int64
0x1800344f3  mov     [rsp+130h+var_110], r15; char
0x1800344f8  mov     r9, r14
0x1800344fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180034502  mov     rcx, [rcx+10h]; LoggerHandle
0x180034506  call    WPP_SF_qqSSLL
0x18003450b  mov     rbx, [rbp+57h+var_C8]
0x18003450f  mov     rdi, [rbp+57h+var_C0]
0x180034513  mov     dword ptr [rsi+0Ch], 2
0x18003451a  mov     dword ptr [rsi+8], 14h
0x180034521  mov     eax, [rsp+130h+var_D8]
0x180034525  mov     [rsi+10h], eax
0x180034528  mov     dword ptr [rsi+14h], 1
0x18003452f  mov     rcx, r15; this
0x180034532  call    ?GetStateMachine@CRemoteDevice@WFDSConMgr@@QEAAAEAVCSessionStateMachine@2@XZ; WFDSConMgr::CRemoteDevice::GetStateMachine(void)
0x180034537  mov     edx, 1
0x18003453c  mov     rcx, rax
0x18003453f  call    ?GetStackState@CSessionStateMachine@WFDSConMgr@@QEBA?AW4_WFDSConMgrTransportStatus@@W4StackType@Context@2@@Z; WFDSConMgr::CSessionStateMachine::GetStackState(WFDSConMgr::Context::StackType)
0x180034544  mov     [rsi+18h], eax
0x180034547  mov     dword ptr [rsi+1Ch], 34h ; '4'
0x18003454e  mov     [rsi+20h], r13d
0x180034552  test    r13d, r13d
0x180034555  jz      short loc_18003456F
0x180034557  mov     r8d, r13d
0x18003455a  lea     rcx, [rbp+57h+var_68]
0x18003455e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034563  mov     rdx, rax; Src
0x180034566  lea     rcx, [rsi+34h]; void *
0x18003456a  call    memcpy_0
0x18003456f  mov     r8, cs:WPP_GLOBAL_Control
0x180034576  lea     rax, WPP_GLOBAL_Control
0x18003457d  cmp     r8, rax
0x180034580  jz      short loc_1800345C2
0x180034582  cmp     byte ptr [r8+19h], 4
0x180034587  jb      short loc_1800345C2
0x180034589  test    byte ptr [r8+1Ch], 1
0x18003458e  jz      short loc_1800345C2
0x180034590  lea     rcx, [rbp+57h+var_68]
0x180034594  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034599  mov     edx, 2Ah ; '*'
0x18003459e  mov     qword ptr [rsp+130h+var_F8], rax
0x1800345a3  mov     eax, [rsi+18h]
0x1800345a6  mov     dword ptr [rsp+130h+var_100], eax
0x1800345aa  mov     eax, [rsi+14h]
0x1800345ad  mov     dword ptr [rsp+130h+var_108], eax
0x1800345b1  mov     [rsp+130h+var_110], r15
0x1800345b6  mov     r9, r14
0x1800345b9  mov     rcx, [r8+10h]
0x1800345bd  call    WPP_SF_qqLLS
0x1800345c2  add     r13d, 34h ; '4'
0x1800345c6  mov     dword ptr [rsi+24h], 2
0x1800345cd  mov     rcx, r15; this
0x1800345d0  call    ?GetStateMachine@CRemoteDevice@WFDSConMgr@@QEAAAEAVCSessionStateMachine@2@XZ; WFDSConMgr::CRemoteDevice::GetStateMachine(void)
0x1800345d5  mov     edx, 2
0x1800345da  mov     rcx, rax
0x1800345dd  call    ?GetStackState@CSessionStateMachine@WFDSConMgr@@QEBA?AW4_WFDSConMgrTransportStatus@@W4StackType@Context@2@@Z; WFDSConMgr::CSessionStateMachine::GetStackState(WFDSConMgr::Context::StackType)
0x1800345e2  mov     [rsi+28h], eax
0x1800345e5  mov     [rsi+2Ch], r13d
0x1800345e9  mov     [rsi+30h], r12d
0x1800345ed  test    r12d, r12d
0x1800345f0  jz      short loc_18003460C
0x1800345f2  mov     r8d, r12d
0x1800345f5  lea     rcx, [rbp+57h+var_88]
0x1800345f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800345fe  mov     rdx, rax; Src
0x180034601  mov     ecx, r13d
0x180034604  add     rcx, rsi; void *
0x180034607  call    memcpy_0
0x18003460c  mov     r8, cs:WPP_GLOBAL_Control
0x180034613  lea     r12, WPP_GLOBAL_Control
0x18003461a  cmp     r8, r12
0x18003461d  jz      short loc_18003465F
0x18003461f  cmp     byte ptr [r8+19h], 4
0x180034624  jb      short loc_18003465F
0x180034626  test    byte ptr [r8+1Ch], 1
0x18003462b  jz      short loc_18003465F
0x18003462d  lea     rcx, [rbp+57h+var_88]
0x180034631  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034636  mov     edx, 2Bh ; '+'
0x18003463b  mov     qword ptr [rsp+130h+var_F8], rax
0x180034640  mov     eax, [rsi+28h]
0x180034643  mov     dword ptr [rsp+130h+var_100], eax
0x180034647  mov     eax, [rsi+24h]
0x18003464a  mov     dword ptr [rsp+130h+var_108], eax
0x18003464e  mov     [rsp+130h+var_110], r15
0x180034653  mov     r9, r14
0x180034656  mov     rcx, [r8+10h]
0x18003465a  call    WPP_SF_qqLLS
0x18003465f  mov     eax, [rbp+57h+var_D4]
0x180034662  mov     [rbx], eax
0x180034664  mov     [rbp+57h+var_D0], 0
0x18003466c  mov     [rdi], rsi
0x18003466f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034676  cmp     rcx, r12
0x180034679  jz      short loc_1800346A0
0x18003467b  cmp     byte ptr [rcx+19h], 4
0x18003467f  jb      short loc_1800346A0
0x180034681  test    byte ptr [rcx+1Ch], 1
0x180034685  jz      short loc_1800346A0
0x180034687  mov     edx, 2Ch ; ','
0x18003468c  mov     r9, r14
0x18003468f  lea     r8, WPP_1ed754397b2a39d314f3beddc0f07fb6_Traceguids
0x180034696  mov     rcx, [rcx+10h]
0x18003469a  call    WPP_SF_q
0x18003469f  nop
0x1800346a0  lea     rcx, [rbp+57h+var_D0]
0x1800346a4  call    ??1?$unique_ptr@$$BY0A@EUFreeDeleter@Common@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<uchar [0],WFDSConMgr::Common::FreeDeleter>::~unique_ptr<uchar [0],WFDSConMgr::Common::FreeDeleter>(void)
0x1800346a9  nop
0x1800346aa  lea     rcx, [rbp+57h+var_88]
0x1800346ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800346b3  nop
0x1800346b4  lea     rcx, [rbp+57h+var_68]
0x1800346b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800346bd  nop
0x1800346be  mov     rcx, [rbp+57h+var_A0]; this
0x1800346c2  test    rcx, rcx
0x1800346c5  jz      short loc_1800346CD
0x1800346c7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800346cc  nop
0x1800346cd  cmp     [rbp+57h+var_90], 0
0x1800346d1  jz      short loc_1800346E2
0x1800346d3  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800346d7  test    rcx, rcx
0x1800346da  jz      short loc_1800346E2
0x1800346dc  call    cs:__imp_ReleaseSRWLockShared
0x1800346e2  mov     rcx, [rbp+57h+var_48]
0x1800346e6  xor     rcx, rsp; StackCookie
0x1800346e9  call    __security_check_cookie
0x1800346ee  add     rsp, 0F8h
0x1800346f5  pop     r15
0x1800346f7  pop     r14
0x1800346f9  pop     r13
0x1800346fb  pop     r12
0x1800346fd  pop     rdi
0x1800346fe  pop     rsi
0x1800346ff  pop     rbx
0x180034700  pop     rbp
0x180034701  retn
  ... truncated ...
```
