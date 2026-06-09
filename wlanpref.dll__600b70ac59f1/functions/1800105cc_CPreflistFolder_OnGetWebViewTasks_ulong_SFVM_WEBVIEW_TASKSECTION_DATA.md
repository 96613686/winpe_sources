# CPreflistFolder::OnGetWebViewTasks(ulong,SFVM_WEBVIEW_TASKSECTION_DATA *)

- ea: `0x1800105cc`
- end: `0x180010be5`
- name: `?OnGetWebViewTasks@CPreflistFolder@@AEAAJKPEAUSFVM_WEBVIEW_TASKSECTION_DATA@@@Z`
- size: `1561`
- prototype: `__int64 __fastcall(CPreflistFolder *__hidden this, unsigned int, struct SFVM_WEBVIEW_TASKSECTION_DATA *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010300`

## callees

- `0x180001e2c`
- `0x180001e9c`
- `0x180003458`
- `0x1800036ac`
- `0x180008484`
- `0x18000cd90`
- `0x18000cfa4`
- `0x18000cfd4`
- `0x18000d0d0`
- `0x18000d23c`
- `0x18000d264`
- `0x18000d578`
- `0x18000db34`
- `0x18000dc28`
- `0x18000f130`
- `0x18000f36c`
- `0x18000fc60`
- `0x18000fc8c`
- `0x1800105cc`
- `0x180011418`
- `0x180014840`
- `0x180014880`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010617`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001068c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001068c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180010648`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180010648`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x180010663`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x180010663`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CPreflistFolder::OnGetWebViewTasks(
        CPreflistFolder *this,
        __int64 a2,
        struct SFVM_WEBVIEW_TASKSECTION_DATA *a3)
{
  unsigned __int64 v5; // rcx
  unsigned int i; // ebx
  UINT *v7; // rdi
  int v8; // esi
  struct IUnknown *v9; // rdi
  struct IUnknown **v10; // rax
  unsigned __int64 v12; // rsi
  unsigned int j; // edi
  const struct CAdapter *v14; // rax
  int v15; // ebx
  __int64 Name; // rbx
  int FriendlyName; // eax
  struct IUnknown *v18; // rbx
  struct IUnknown **v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rdx
  struct IUnknown *v22; // rbx
  __int64 v23; // [rsp+20h] [rbp-A9h]
  int v24; // [rsp+28h] [rbp-A1h]
  void *ppvOut; // [rsp+40h] [rbp-89h] BYREF
  struct IUnknown *v26; // [rsp+48h] [rbp-81h] BYREF
  const unsigned __int16 *v27; // [rsp+50h] [rbp-79h] BYREF
  const unsigned __int16 *v28; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int64 v29; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v30[3]; // [rsp+68h] [rbp-61h] BYREF
  int v31; // [rsp+80h] [rbp-49h]
  _QWORD v32[3]; // [rsp+88h] [rbp-41h] BYREF
  int v33; // [rsp+A0h] [rbp-29h]
  __int64 v34; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int64 v35; // [rsp+B0h] [rbp-19h]
  __int64 v36; // [rsp+B8h] [rbp-11h]
  int v37; // [rsp+C0h] [rbp-9h]
  void **v38; // [rsp+C8h] [rbp-1h] BYREF
  __int128 v39; // [rsp+D0h] [rbp+7h]
  _BYTE v40[8]; // [rsp+E0h] [rbp+17h] BYREF
  __int128 v41; // [rsp+E8h] [rbp+1Fh] BYREF

  v5 = ((unsigned __int64)this + 64) & -(__int64)(this != 0);
  v29 = v5;
  if ( v5 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v5 + 8LL))(v5);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( !*((_DWORD *)this + 36) )
  {
    ppvOut = 0;
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 17),
           (const GUID *const)&SID_PerLayoutPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut) >= 0 )
    {
      if ( PSPropertyBag_WriteBOOL((IPropertyBag *)ppvOut, L"ListViewHiddenState", 1) >= 0 )
        *((_DWORD *)this + 36) = 1;
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  CPreflistFolder::InitializeDataSource(this);
  if ( dword_1800407B0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800407B0);
    if ( dword_1800407B0 == -1 )
    {
      xmmword_180040410 = xmmword_1800353F8;
      dword_180040420 = 20035;
      dword_180040424 = 20050;
      dword_180040428 = 20036;
      xmmword_18004042C = xmmword_1800353E8;
      dword_18004043C = 20037;
      dword_180040440 = 20051;
      dword_180040444 = 20038;
      xmmword_180040448 = xmmword_1800353D8;
      dword_180040458 = 20045;
      dword_18004045C = 20052;
      dword_180040460 = 20046;
      xmmword_180040464 = xmmword_1800353C8;
      dword_180040474 = 20047;
      dword_180040478 = 20053;
      dword_18004047C = 20048;
      xmmword_180040480 = xmmword_1800353B8;
      dword_180040490 = 20039;
      dword_180040494 = 20054;
      dword_180040498 = 20040;
      xmmword_18004049C = xmmword_1800353A8;
      dword_1800404AC = 20041;
      dword_1800404B0 = 20056;
      dword_1800404B4 = 20042;
      xmmword_1800404B8 = xmmword_180035398;
      dword_1800404C8 = 20065;
      dword_1800404CC = 20067;
      dword_1800404D0 = 20066;
      xmmword_1800404D4 = xmmword_180035388;
      dword_1800404E4 = 20043;
      dword_1800404E8 = 20057;
      dword_1800404EC = 20044;
      Init_thread_footer(&dword_1800407B0);
    }
  }
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(v30, 8);
  for ( i = 0; i < 8; ++i )
  {
    v7 = (UINT *)&xmmword_180040410 + 7 * i;
    ppvOut = (void *)WTL::_atltmpPchNil;
    v28 = WTL::_atltmpPchNil;
    v27 = WTL::_atltmpPchNil;
    WTL::CString::LoadStringW((WTL::CString *)&ppvOut, v7[4]);
    WTL::CString::LoadStringW((WTL::CString *)&v28, v7[6]);
    WTL::CString::LoadStringW((WTL::CString *)&v27, v7[5]);
    v26 = 0;
    v8 = ATL::CComObject<CUICommand>::CreateInstance(&v26);
    if ( v8 < 0 )
    {
      WTL::CString::~CString((WTL::CString *)&v27);
      WTL::CString::~CString((WTL::CString *)&v28);
      WTL::CString::~CString((WTL::CString *)&ppvOut);
      ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(v30);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      return (unsigned int)v8;
    }
    v9 = v26;
    CUICommand::Set(
      (_DWORD)v26,
      (unsigned int)&xmmword_180040410 + 28 * i,
      (unsigned int)&ppvOut,
      (unsigned int)&v27,
      (__int64)&v28,
      v24,
      (__int64)&v29);
    v10 = (struct IUnknown **)ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::operator[](
                                v30,
                                i);
    if ( *v10 != v9 )
      ATL::AtlComPtrAssign(v10, v9);
    WTL::CString::~CString((WTL::CString *)&v27);
    WTL::CString::~CString((WTL::CString *)&v28);
    WTL::CString::~CString((WTL::CString *)&ppvOut);
  }
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 72LL))(
    CSingletonPtr<CWlanProfileStore>::s_pInstance,
    &v34);
  v12 = v35;
  if ( v35 > 1 )
  {
    memset(v32, 0, sizeof(v32));
    v33 = 0;
    ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(v32, v35);
    for ( j = 0; j < v12; ++j )
    {
      v14 = (const struct CAdapter *)ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(&v34, j);
      CAdapter::CAdapter((CAdapter *)&v38, v14);
      v26 = 0;
      v15 = ATL::CComObject<CUICommand>::CreateInstance(&v26);
      if ( v15 < 0 )
      {
        v38 = &CAdapter::`vftable';
        WTL::CString::~CString((WTL::CString *)v40);
        ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(v32);
        goto LABEL_31;
      }
      ppvOut = (void *)WTL::_atltmpPchNil;
      WTL::CString::LoadStringW((WTL::CString *)&ppvOut, 0x4E57u);
      Name = CAdapter::GetName(&v38, &v27);
      FriendlyName = CAdapter::GetFriendlyName(&v38, &v28);
      v41 = v39;
      v23 = Name;
      v18 = v26;
      CUICommand::Set((_DWORD)v26, (unsigned int)&v41, FriendlyName, (unsigned int)&ppvOut, v23, v24, (__int64)&v29);
      WTL::CString::~CString((WTL::CString *)&v28);
      WTL::CString::~CString((WTL::CString *)&v27);
      v19 = (struct IUnknown **)ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::operator[](
                                  v32,
                                  j);
      if ( *v19 != v18 )
        ATL::AtlComPtrAssign(v19, v18);
      WTL::CString::~CString((WTL::CString *)&ppvOut);
      v38 = &CAdapter::`vftable';
      WTL::CString::~CString((WTL::CString *)v40);
    }
    v20 = *(_QWORD *)ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::operator[](
                       v30,
                       4);
    v26 = (struct IUnknown *)v20;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
    *(_DWORD *)(v20 + 144) = 1;
    ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(v20 + 72, 0);
    ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::InsertArrayAt(
      v20 + 72,
      v21,
      v32);
    ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(&v26);
    ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(v32);
  }
  v26 = 0;
  v15 = ATL::CComObject<CEnumUICommand>::CreateInstance(&v26);
  if ( v15 >= 0 )
  {
    v22 = v26;
    CEnumUICommand::Set(v26, v30);
    *(_OWORD *)a3 = 0;
    *((_QWORD *)a3 + 2) = 0;
    *((_DWORD *)a3 + 4) = 1;
    v15 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct SFVM_WEBVIEW_TASKSECTION_DATA *))v22->lpVtbl->QueryInterface)(
            v22,
            &GUID_869447da_9f84_4e2a_b92d_00642dc8a911,
            a3);
  }
LABEL_31:
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v34);
  ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800105cc  mov     [rsp-8+arg_8], rbx
0x1800105d1  mov     [rsp-8+arg_18], rsi
0x1800105d6  push    rbp
0x1800105d7  push    rdi
0x1800105d8  push    r12
0x1800105da  push    r14
0x1800105dc  push    r15
0x1800105de  lea     rbp, [rsp-37h]
0x1800105e3  sub     rsp, 100h
0x1800105ea  mov     r15, r8
0x1800105ed  mov     rbx, rcx
0x1800105f0  mov     rax, rcx
0x1800105f3  lea     rdx, [rcx+40h]
0x1800105f7  neg     rax
0x1800105fa  sbb     rcx, rcx
0x1800105fd  and     rcx, rdx
0x180010600  mov     [rbp+57h+var_C0], rcx
0x180010604  jz      short loc_180010613
0x180010606  mov     rax, [rcx]
0x180010609  mov     rax, [rax+8]
0x18001060d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010612  nop
0x180010613  lea     rcx, [rbx+58h]; lpCriticalSection
0x180010617  call    cs:__imp_EnterCriticalSection
0x18001061d  xor     r12d, r12d
0x180010620  cmp     [rbx+90h], r12d
0x180010627  jnz     short loc_180010688
0x180010629  mov     [rsp+120h+ppvOut], r12
0x18001062e  lea     r9, [rsp+120h+ppvOut]; ppvOut
0x180010633  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001063a  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x180010641  mov     rcx, [rbx+88h]; punk
0x180010648  call    cs:__imp_IUnknown_QueryService
0x18001064e  test    eax, eax
0x180010650  js      short loc_180010688
0x180010652  lea     r8d, [r12+1]; value
0x180010657  lea     rdx, propName; "ListViewHiddenState"
0x18001065e  mov     rcx, [rsp+120h+ppvOut]; propBag
0x180010663  call    cs:__imp_PSPropertyBag_WriteBOOL
0x180010669  test    eax, eax
0x18001066b  js      short loc_180010677
0x18001066d  mov     dword ptr [rbx+90h], 1
0x180010677  mov     rcx, [rsp+120h+ppvOut]
0x18001067c  mov     rax, [rcx]
0x18001067f  mov     rax, [rax+10h]
0x180010683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010688  lea     rcx, [rbx+58h]; lpCriticalSection
0x18001068c  call    cs:__imp_LeaveCriticalSection
0x180010692  mov     rcx, rbx; this
0x180010695  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18001069a  mov     ecx, cs:_tls_index
0x1800106a0  mov     rax, gs:58h
0x1800106a9  mov     edx, 4
0x1800106ae  mov     rax, [rax+rcx*8]
0x1800106b2  mov     ecx, [rdx+rax]
0x1800106b5  cmp     cs:dword_1800407B0, ecx
0x1800106bb  jle     loc_18001084E
0x1800106c1  lea     rcx, dword_1800407B0
0x1800106c8  call    _Init_thread_header
0x1800106cd  cmp     cs:dword_1800407B0, 0FFFFFFFFh
0x1800106d4  jnz     loc_18001084E
0x1800106da  movups  xmm0, cs:xmmword_1800353F8
0x1800106e1  movdqu  cs:xmmword_180040410, xmm0
0x1800106e9  mov     cs:dword_180040420, 4E43h
0x1800106f3  mov     cs:dword_180040424, 4E52h
0x1800106fd  mov     cs:dword_180040428, 4E44h
0x180010707  movups  xmm0, cs:xmmword_1800353E8
0x18001070e  movdqu  cs:xmmword_18004042C, xmm0
0x180010716  mov     cs:dword_18004043C, 4E45h
0x180010720  mov     cs:dword_180040440, 4E53h
0x18001072a  mov     cs:dword_180040444, 4E46h
0x180010734  movups  xmm0, cs:xmmword_1800353D8
0x18001073b  movdqu  cs:xmmword_180040448, xmm0
0x180010743  mov     cs:dword_180040458, 4E4Dh
0x18001074d  mov     cs:dword_18004045C, 4E54h
0x180010757  mov     cs:dword_180040460, 4E4Eh
0x180010761  movups  xmm0, cs:xmmword_1800353C8
0x180010768  movdqu  cs:xmmword_180040464, xmm0
0x180010770  mov     cs:dword_180040474, 4E4Fh
0x18001077a  mov     cs:dword_180040478, 4E55h
0x180010784  mov     cs:dword_18004047C, 4E50h
0x18001078e  movups  xmm0, cs:xmmword_1800353B8
0x180010795  movdqu  cs:xmmword_180040480, xmm0
0x18001079d  mov     cs:dword_180040490, 4E47h
0x1800107a7  mov     cs:dword_180040494, 4E56h
0x1800107b1  mov     cs:dword_180040498, 4E48h
0x1800107bb  movups  xmm0, cs:xmmword_1800353A8
0x1800107c2  movdqu  cs:xmmword_18004049C, xmm0
0x1800107ca  mov     cs:dword_1800404AC, 4E49h
0x1800107d4  mov     cs:dword_1800404B0, 4E58h
0x1800107de  mov     cs:dword_1800404B4, 4E4Ah
0x1800107e8  movups  xmm0, cs:xmmword_180035398
0x1800107ef  movdqu  cs:xmmword_1800404B8, xmm0
0x1800107f7  mov     cs:dword_1800404C8, 4E61h
0x180010801  mov     cs:dword_1800404CC, 4E63h
0x18001080b  mov     cs:dword_1800404D0, 4E62h
0x180010815  movups  xmm0, cs:xmmword_180035388
0x18001081c  movdqu  cs:xmmword_1800404D4, xmm0
0x180010824  mov     cs:dword_1800404E4, 4E4Bh
0x18001082e  mov     cs:dword_1800404E8, 4E59h
0x180010838  mov     cs:dword_1800404EC, 4E4Ch
0x180010842  lea     rcx, dword_1800407B0
0x180010849  call    _Init_thread_footer
0x18001084e  mov     [rbp+57h+var_B8], r12
0x180010852  mov     [rbp+57h+var_B0], r12
0x180010856  mov     [rbp+57h+var_A8], r12
0x18001085a  mov     [rbp+57h+var_A0], r12d
0x18001085e  mov     edx, 8
0x180010863  lea     rcx, [rbp+57h+var_B8]
0x180010867  call    ?SetCount@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(unsigned __int64,int)
0x18001086c  mov     ebx, r12d
0x18001086f  cmp     ebx, 8
0x180010872  jnb     loc_18001097D
0x180010878  mov     r14d, ebx
0x18001087b  imul    rdi, r14, 1Ch
0x18001087f  lea     rcx, xmmword_180040410
0x180010886  add     rdi, rcx
0x180010889  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180010890  mov     [rsp+120h+ppvOut], rax
0x180010895  mov     [rbp+57h+var_C8], rax
0x180010899  mov     [rbp+57h+var_D0], rax
0x18001089d  mov     edx, [rdi+10h]; uID
0x1800108a0  lea     rcx, [rsp+120h+ppvOut]; this
0x1800108a5  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x1800108aa  mov     edx, [rdi+18h]; uID
0x1800108ad  lea     rcx, [rbp+57h+var_C8]; this
0x1800108b1  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x1800108b6  mov     edx, [rdi+14h]; uID
0x1800108b9  lea     rcx, [rbp+57h+var_D0]; this
0x1800108bd  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x1800108c2  mov     [rsp+120h+var_D8], r12
0x1800108c7  lea     rcx, [rsp+120h+var_D8]
0x1800108cc  call    ?CreateInstance@?$CComObject@VCUICommand@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUICommand>::CreateInstance(ATL::CComObject<CUICommand> * *)
0x1800108d1  mov     esi, eax
0x1800108d3  test    eax, eax
0x1800108d5  js      short loc_180010944
0x1800108d7  lea     rax, [rbp+57h+var_C0]
0x1800108db  mov     [rsp+120h+var_F0], rax
0x1800108e0  lea     rax, [rbp+57h+var_C8]
0x1800108e4  mov     [rsp+120h+var_100], rax
0x1800108e9  lea     r9, [rbp+57h+var_D0]
0x1800108ed  lea     r8, [rsp+120h+ppvOut]
0x1800108f2  mov     rdx, rdi
0x1800108f5  mov     rdi, [rsp+120h+var_D8]
0x1800108fa  mov     rcx, rdi
0x1800108fd  call    ?Set@CUICommand@@QEAAXAEBU_GUID@@AEBVCString@WTL@@11HAEAV?$CComPtr@VIUICommandHelper@@@ATL@@@Z; CUICommand::Set(_GUID const &,WTL::CString const &,WTL::CString const &,WTL::CString const &,int,ATL::CComPtr<IUICommandHelper> &)
0x180010902  mov     edx, r14d
0x180010905  lea     rcx, [rbp+57h+var_B8]
0x180010909  call    ??A?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAAAEAV?$CComPtr@VCUICommand@@@1@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::operator[](unsigned __int64)
0x18001090e  cmp     [rax], rdi
0x180010911  jz      short loc_18001091F
0x180010913  mov     rdx, rdi; struct IUnknown *
0x180010916  mov     rcx, rax; struct IUnknown **
0x180010919  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001091e  nop
0x18001091f  lea     rcx, [rbp+57h+var_D0]; this
0x180010923  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010928  nop
0x180010929  lea     rcx, [rbp+57h+var_C8]; this
0x18001092d  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010932  nop
0x180010933  lea     rcx, [rsp+120h+ppvOut]; this
0x180010938  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18001093d  inc     ebx
0x18001093f  jmp     loc_18001086F
0x180010944  lea     rcx, [rbp+57h+var_D0]; this
0x180010948  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18001094d  nop
0x18001094e  lea     rcx, [rbp+57h+var_C8]; this
0x180010952  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010957  nop
0x180010958  lea     rcx, [rsp+120h+ppvOut]; this
0x18001095d  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010962  nop
0x180010963  lea     rcx, [rbp+57h+var_B8]
0x180010967  call    ??1?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(void)
0x18001096c  nop
0x18001096d  lea     rcx, [rbp+57h+var_C0]
0x180010971  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010976  mov     eax, esi
0x180010978  jmp     loc_180010BC9
0x18001097d  mov     [rbp+57h+var_78], r12
0x180010981  mov     [rbp+57h+var_70], r12
0x180010985  mov     [rbp+57h+var_68], r12
0x180010989  mov     [rbp+57h+var_60], r12d
0x18001098d  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180010994  mov     rax, [rcx]
0x180010997  lea     rdx, [rbp+57h+var_78]
0x18001099b  mov     rax, [rax+48h]
0x18001099f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a4  mov     rsi, [rbp+57h+var_70]
0x1800109a8  cmp     rsi, 1
0x1800109ac  jbe     loc_180010B55
0x1800109b2  mov     [rbp+57h+var_98], r12
0x1800109b6  mov     [rbp+57h+var_90], r12
0x1800109ba  mov     [rbp+57h+var_88], r12
0x1800109be  mov     [rbp+57h+var_80], r12d
0x1800109c2  mov     rdx, rsi
0x1800109c5  lea     rcx, [rbp+57h+var_98]
0x1800109c9  call    ?SetCount@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(unsigned __int64,int)
0x1800109ce  mov     edi, r12d
0x1800109d1  mov     r14d, edi
0x1800109d4  cmp     r14, rsi
0x1800109d7  jnb     loc_180010AF2
0x1800109dd  mov     edx, r14d
0x1800109e0  lea     rcx, [rbp+57h+var_78]
0x1800109e4  call    ?GetAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEBAAEBVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(unsigned __int64)
0x1800109e9  mov     rdx, rax; struct CAdapter *
0x1800109ec  lea     rcx, [rbp+57h+var_58]; this
0x1800109f0  call    ??0CAdapter@@QEAA@AEBV0@@Z; CAdapter::CAdapter(CAdapter const &)
0x1800109f5  nop
0x1800109f6  mov     [rsp+120h+var_D8], r12
0x1800109fb  lea     rcx, [rsp+120h+var_D8]
0x180010a00  call    ?CreateInstance@?$CComObject@VCUICommand@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUICommand>::CreateInstance(ATL::CComObject<CUICommand> * *)
0x180010a05  mov     ebx, eax
0x180010a07  test    eax, eax
0x180010a09  js      loc_180010ACF
0x180010a0f  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180010a16  mov     [rsp+120h+ppvOut], rax
0x180010a1b  mov     edx, 4E57h; uID
0x180010a20  lea     rcx, [rsp+120h+ppvOut]; this
0x180010a25  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180010a2a  lea     rdx, [rbp+57h+var_D0]
0x180010a2e  lea     rcx, [rbp+57h+var_58]
0x180010a32  call    ?GetName@CAdapter@@QEBA?AVCString@WTL@@XZ; CAdapter::GetName(void)
0x180010a37  mov     rbx, rax
0x180010a3a  lea     rdx, [rbp+57h+var_C8]
0x180010a3e  lea     rcx, [rbp+57h+var_58]
0x180010a42  call    ?GetFriendlyName@CAdapter@@QEBA?AVCString@WTL@@XZ; CAdapter::GetFriendlyName(void)
0x180010a47  nop
0x180010a48  movups  xmm0, [rbp+57h+var_50]
0x180010a4c  movdqu  [rbp+57h+var_38], xmm0
0x180010a51  lea     rcx, [rbp+57h+var_C0]
0x180010a55  mov     [rsp+120h+var_F0], rcx
0x180010a5a  mov     [rsp+120h+var_100], rbx
0x180010a5f  lea     r9, [rsp+120h+ppvOut]
0x180010a64  mov     r8, rax
0x180010a67  lea     rdx, [rbp+57h+var_38]
0x180010a6b  mov     rbx, [rsp+120h+var_D8]
0x180010a70  mov     rcx, rbx
0x180010a73  call    ?Set@CUICommand@@QEAAXAEBU_GUID@@AEBVCString@WTL@@11HAEAV?$CComPtr@VIUICommandHelper@@@ATL@@@Z; CUICommand::Set(_GUID const &,WTL::CString const &,WTL::CString const &,WTL::CString const &,int,ATL::CComPtr<IUICommandHelper> &)
0x180010a78  nop
0x180010a79  lea     rcx, [rbp+57h+var_C8]; this
0x180010a7d  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010a82  nop
0x180010a83  lea     rcx, [rbp+57h+var_D0]; this
0x180010a87  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010a8c  mov     edx, r14d
0x180010a8f  lea     rcx, [rbp+57h+var_98]
0x180010a93  call    ??A?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAAAEAV?$CComPtr@VCUICommand@@@1@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::operator[](unsigned __int64)
0x180010a98  cmp     [rax], rbx
0x180010a9b  jz      short loc_180010AA9
0x180010a9d  mov     rdx, rbx; struct IUnknown *
0x180010aa0  mov     rcx, rax; struct IUnknown **
0x180010aa3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180010aa8  nop
0x180010aa9  lea     rcx, [rsp+120h+ppvOut]; this
0x180010aae  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ab3  nop
0x180010ab4  lea     rax, ??_7CAdapter@@6B@; const CAdapter::`vftable'
0x180010abb  mov     [rbp+57h+var_58], rax
0x180010abf  lea     rcx, [rbp+57h+var_40]; this
0x180010ac3  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ac8  inc     edi
0x180010aca  jmp     loc_1800109D1
0x180010acf  lea     rax, ??_7CAdapter@@6B@; const CAdapter::`vftable'
0x180010ad6  mov     [rbp+57h+var_58], rax
0x180010ada  lea     rcx, [rbp+57h+var_40]; this
0x180010ade  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ae3  nop
0x180010ae4  lea     rcx, [rbp+57h+var_98]
0x180010ae8  call    ??1?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(void)
0x180010aed  jmp     loc_180010BAA
0x180010af2  mov     edx, 4
0x180010af7  lea     rcx, [rbp+57h+var_B8]
0x180010afb  call    ??A?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAAAEAV?$CComPtr@VCUICommand@@@1@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::operator[](unsigned __int64)
0x180010b00  mov     rbx, [rax]
0x180010b03  mov     [rsp+120h+var_D8], rbx
0x180010b08  test    rbx, rbx
0x180010b0b  jz      short loc_180010B1D
0x180010b0d  mov     rax, [rbx]
0x180010b10  mov     rcx, rbx
0x180010b13  mov     rax, [rax+8]
0x180010b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b1c  nop
0x180010b1d  mov     dword ptr [rbx+90h], 1
0x180010b27  xor     edx, edx
0x180010b29  lea     rcx, [rbx+48h]
0x180010b2d  call    ?SetCount@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::SetCount(unsigned __int64,int)
0x180010b32  nop
0x180010b33  lea     r8, [rbp+57h+var_98]
0x180010b37  lea     rcx, [rbx+48h]
0x180010b3b  call    ?InsertArrayAt@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAAX_KPEBV12@@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::InsertArrayAt(unsigned __int64,ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>> const *)
0x180010b40  nop
0x180010b41  lea     rcx, [rsp+120h+var_D8]
0x180010b46  call    ??1?$CComPtrBase@VCUICommand@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(void)
0x180010b4b  nop
0x180010b4c  lea     rcx, [rbp+57h+var_98]
0x180010b50  call    ??1?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(void)
0x180010b55  mov     [rsp+120h+var_D8], r12
  ... truncated ...
```
