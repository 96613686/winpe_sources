# DataStoreReader::LoadRecentResultsFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,WinSATData &,IXMLDOMDocument2 * *)

- ea: `0x180006580`
- end: `0x180006967`
- name: `?LoadRecentResultsFromFile@DataStoreReader@@KAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAUWinSATData@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `999`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004e00`

## callees

- `0x180001a34`
- `0x1800049bc`
- `0x180006580`
- `0x18000782c`
- `0x180007930`
- `0x180013e58`
- `0x180013ec8`
- `0x1800151bb`
- `0x1800171e0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800066fa`
- `OLEAUT32!__imp_SysAllocString` at `0x1800066fa`
- `OLEAUT32!__imp_VariantInit` at `0x1800066d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800066d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800066e7`
- `OLEAUT32!__imp_VariantClear` at `0x1800067ab`
- `OLEAUT32!__imp_VariantClear` at `0x180006825`
- `OLEAUT32!__imp_VariantClear` at `0x180006895`
- `OLEAUT32!__imp_VariantClear` at `0x1800068e7`
- `OLEAUT32!__imp_VariantClear` at `0x1800066e7`
- `OLEAUT32!__imp_VariantClear` at `0x1800067ab`
- `OLEAUT32!__imp_VariantClear` at `0x180006825`
- `OLEAUT32!__imp_VariantClear` at `0x180006895`
- `OLEAUT32!__imp_VariantClear` at `0x1800068e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006688`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006688`

## string_xrefs

- `0x180006797`: `base\winsat\mlib\mxmldom.cpp`
- `0x180006811`: `base\winsat\mlib\mxmldom.cpp`
- `0x180006881`: `base\winsat\mlib\mxmldom.cpp`
- `0x180006776`: `cannot create an IXMLDOMDocument2 document`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DataStoreReader::LoadRecentResultsFromFile(__int64 a1, void *a2, struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMDocument2 *v6; // rbx
  int v7; // r15d
  const OLECHAR *v8; // r12
  int v9; // eax
  int v10; // eax
  int ResultsFromXmlDoc; // esi
  struct IXMLDOMDocument2 *v13; // rcx
  struct IXMLDOMDocument2 *v14; // [rsp+40h] [rbp-98h] BYREF
  __int64 v15; // [rsp+48h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-88h] BYREF
  VARIANTARG v17; // [rsp+70h] [rbp-68h] BYREF
  __int16 v18; // [rsp+E0h] [rbp+8h] BYREF
  void *v19; // [rsp+E8h] [rbp+10h]
  struct IXMLDOMDocument2 **v20; // [rsp+F0h] [rbp+18h]
  LPVOID ppv; // [rsp+F8h] [rbp+20h] BYREF

  v20 = a3;
  v19 = a2;
  v15 = -2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  memset_0(a2, 0, 0x1A0u);
  ppv = 0;
  v18 = 0;
  if ( dword_18004E6A4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18004E6A4);
    if ( dword_18004E6A4 == -1 )
    {
      byte_18004E6A0 = 0;
      Init_thread_footer(&dword_18004E6A4);
    }
  }
  v6 = 0;
  v14 = 0;
  if ( !mlib::XmlDOM::fInitialized )
  {
    mlib::XmlDOM::clsIDDocument = 0;
    mlib::XmlDOM::clsIDSchema = 0;
    if ( !mlib::XmlDOM::CheckMSXMLVersion() )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      v7 = -2147467259;
      goto LABEL_26;
    }
    mlib::XmlDOM::fInitialized = 1;
  }
  if ( CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv) < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    v7 = -2147467259;
LABEL_26:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
    return (unsigned int)v7;
  }
  VariantInit(&pvarg);
  v8 = *(const OLECHAR **)(*(_QWORD *)a1 + 24LL);
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v8);
  if ( !pvarg.llVal && v8 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v17 = pvarg;
  v9 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)ppv + 464LL))(ppv, &v17, &v18);
  if ( v9 < 0 )
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           230,
           v9,
           0,
           (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           0,
           (__int64)L"cannot create an IXMLDOMDocument2 document");
    VariantClear(&pvarg);
    if ( !ppv )
      goto LABEL_25;
LABEL_24:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_25:
    if ( v7 < 0 )
      goto LABEL_26;
    goto LABEL_28;
  }
  if ( !v18 )
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           235,
           -2147467259,
           (_DWORD)ppv,
           (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           0,
           (__int64)L"cannot load document from file '%s'",
           *(_QWORD *)(*(_QWORD *)a1 + 24LL),
           v14,
           v15);
    VariantClear(&pvarg);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    goto LABEL_25;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
  if ( v10 < 0 )
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           246,
           v10,
           (_DWORD)ppv,
           (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           0,
           (__int64)L"cannot set the 'preserve white space' flag");
    VariantClear(&pvarg);
    if ( !ppv )
      goto LABEL_25;
    goto LABEL_24;
  }
  v6 = (struct IXMLDOMDocument2 *)ppv;
  ppv = 0;
  v14 = v6;
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
LABEL_28:
  ResultsFromXmlDoc = WinSATData::LoadResultsFromXmlDoc((WinSATData *)a2, v6);
  if ( ResultsFromXmlDoc >= 0 && a3 )
  {
    v13 = v6;
    v6 = 0;
    *a3 = v13;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
  return (unsigned int)ResultsFromXmlDoc;
}

```

## disassembly

```asm
0x180006580  mov     [rsp+arg_10], r8
0x180006585  mov     [rsp+arg_8], rdx
0x18000658a  push    rbx
0x18000658b  push    rsi
0x18000658c  push    rdi
0x18000658d  push    r12
0x18000658f  push    r13
0x180006591  push    r14
0x180006593  push    r15
0x180006595  sub     rsp, 0A0h
0x18000659c  mov     [rsp+0D8h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800065a5  mov     r14, r8
0x1800065a8  mov     rsi, rdx
0x1800065ab  mov     r15, rcx
0x1800065ae  test    rcx, rcx
0x1800065b1  jz      loc_18000694F
0x1800065b7  test    rdx, rdx
0x1800065ba  jz      loc_18000694F
0x1800065c0  xor     edx, edx; Val
0x1800065c2  mov     r8d, 1A0h; Size
0x1800065c8  mov     rcx, rsi; void *
0x1800065cb  call    memset_0
0x1800065d0  nop
0x1800065d1  xor     edi, edi
0x1800065d3  mov     [rsp+0D8h+arg_18], rdi
0x1800065db  mov     [rsp+0D8h+arg_0], di
0x1800065e3  mov     ecx, cs:_tls_index
0x1800065e9  mov     rax, gs:58h
0x1800065f2  mov     edx, 4
0x1800065f7  mov     rax, [rax+rcx*8]
0x1800065fb  mov     eax, [rdx+rax]
0x1800065fe  cmp     cs:dword_18004E6A4, eax
0x180006604  jle     short loc_18000662E
0x180006606  lea     rcx, dword_18004E6A4
0x18000660d  call    _Init_thread_header
0x180006612  cmp     cs:dword_18004E6A4, 0FFFFFFFFh
0x180006619  jnz     short loc_18000662E
0x18000661b  mov     cs:byte_18004E6A0, dil
0x180006622  lea     rcx, dword_18004E6A4
0x180006629  call    _Init_thread_footer
0x18000662e  mov     rbx, rdi
0x180006631  mov     [rsp+0D8h+var_98], rbx
0x180006636  cmp     cs:?fInitialized@XmlDOM@mlib@@0_NA, bl; bool mlib::XmlDOM::fInitialized
0x18000663c  jnz     short loc_180006662
0x18000663e  xorps   xmm0, xmm0
0x180006641  movups  xmmword ptr cs:?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm0; _GUID mlib::XmlDOM::clsIDDocument ...
0x180006648  xorps   xmm1, xmm1
0x18000664b  movups  xmmword ptr cs:?clsIDSchema@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm1; _GUID mlib::XmlDOM::clsIDSchema ...
0x180006652  call    ?CheckMSXMLVersion@XmlDOM@mlib@@SA_NXZ; mlib::XmlDOM::CheckMSXMLVersion(void)
0x180006657  test    al, al
0x180006659  jz      short loc_1800066AA
0x18000665b  mov     cs:?fInitialized@XmlDOM@mlib@@0_NA, 1; bool mlib::XmlDOM::fInitialized
0x180006662  lea     rax, [rsp+0D8h+arg_18]
0x18000666a  mov     [rsp+0D8h+ppv], rax; ppv
0x18000666f  lea     r13, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x180006676  mov     r9, r13; riid
0x180006679  xor     edx, edx; pUnkOuter
0x18000667b  mov     r8d, 1; dwClsContext
0x180006681  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x180006688  call    cs:__imp_CoCreateInstance
0x18000668e  test    eax, eax
0x180006690  jns     short loc_1800066CF
0x180006692  lea     rcx, [rsp+0D8h+arg_18]
0x18000669a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000669f  mov     r15d, 80004005h
0x1800066a5  jmp     loc_1800068BB
0x1800066aa  mov     rcx, [rsp+0D8h+arg_18]
0x1800066b2  test    rcx, rcx
0x1800066b5  jz      short loc_1800066C4
0x1800066b7  mov     rax, [rcx]
0x1800066ba  mov     rax, [rax+10h]
0x1800066be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c3  nop
0x1800066c4  mov     r15d, 80004005h
0x1800066ca  jmp     loc_1800068BB
0x1800066cf  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x1800066d4  call    cs:__imp_VariantInit
0x1800066da  nop
0x1800066db  mov     rax, [r15]
0x1800066de  mov     r12, [rax+18h]
0x1800066e2  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x1800066e7  call    cs:__imp_VariantClear
0x1800066ed  mov     eax, 8
0x1800066f2  mov     word ptr [rsp+0D8h+pvarg], ax
0x1800066f7  mov     rcx, r12; psz
0x1800066fa  call    cs:__imp_SysAllocString
0x180006700  mov     dword ptr [rsp+0D8h+pvarg+8], eax
0x180006704  mov     rcx, rax
0x180006707  sar     rcx, 20h
0x18000670b  mov     dword ptr [rsp+0D8h+pvarg+0Ch], ecx
0x18000670f  test    rax, rax
0x180006712  jnz     short loc_180006735
0x180006714  test    r12, r12
0x180006717  jz      short loc_180006735
0x180006719  mov     eax, 0Ah
0x18000671e  mov     word ptr [rsp+0D8h+pvarg], ax
0x180006723  mov     dword ptr [rsp+0D8h+pvarg+8], 8007000Eh
0x18000672b  mov     ecx, 8007000Eh; int
0x180006730  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006735  mov     rcx, [rsp+0D8h+arg_18]
0x18000673d  movups  xmm0, xmmword ptr [rsp+0D8h+pvarg]
0x180006742  movaps  [rsp+0D8h+var_68], xmm0
0x180006747  movsd   xmm1, qword ptr [rsp+0D8h+pvarg+10h]
0x18000674d  movsd   [rsp+0D8h+var_58], xmm1
0x180006756  mov     rax, [rcx]
0x180006759  lea     r8, [rsp+0D8h+arg_0]
0x180006761  lea     rdx, [rsp+0D8h+var_68]
0x180006766  mov     rax, [rax+1D0h]
0x18000676d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006772  test    eax, eax
0x180006774  jns     short loc_1800067D1
0x180006776  lea     rcx, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x18000677d  mov     [rsp+0D8h+var_A8], rcx
0x180006782  mov     [rsp+0D8h+var_B0], rdi
0x180006787  mov     [rsp+0D8h+ppv], r13
0x18000678c  xor     r9d, r9d
0x18000678f  mov     r8d, eax
0x180006792  mov     edx, 0E6h
0x180006797  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18000679e  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1800067a3  mov     r15d, eax
0x1800067a6  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x1800067ab  call    cs:__imp_VariantClear
0x1800067b1  nop
0x1800067b2  mov     rcx, [rsp+0D8h+arg_18]
0x1800067ba  test    rcx, rcx
0x1800067bd  jz      short loc_1800067CC
0x1800067bf  mov     rax, [rcx]
0x1800067c2  mov     rax, [rax+10h]
0x1800067c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067cb  nop
0x1800067cc  jmp     loc_1800068B6
0x1800067d1  cmp     [rsp+0D8h+arg_0], 0
0x1800067da  jnz     short loc_18000683B
0x1800067dc  mov     rax, [r15]
0x1800067df  mov     rcx, [rax+18h]
0x1800067e3  mov     [rsp+0D8h+var_A0], rcx
0x1800067e8  lea     rax, aCannotLoadDocu; "cannot load document from file '%s'"
0x1800067ef  mov     [rsp+0D8h+var_A8], rax
0x1800067f4  mov     [rsp+0D8h+var_B0], rdi
0x1800067f9  mov     [rsp+0D8h+ppv], r13
0x1800067fe  mov     r9, [rsp+0D8h+arg_18]
0x180006806  mov     edx, 0EBh
0x18000680b  mov     r8d, 80004005h
0x180006811  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180006818  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18000681d  mov     r15d, eax
0x180006820  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180006825  call    cs:__imp_VariantClear
0x18000682b  nop
0x18000682c  lea     rcx, [rsp+0D8h+arg_18]
0x180006834  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006839  jmp     short loc_1800068B6
0x18000683b  mov     rcx, [rsp+0D8h+arg_18]
0x180006843  mov     rax, [rcx]
0x180006846  mov     edx, 0FFFFFFFFh
0x18000684b  mov     rax, [rax+240h]
0x180006852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006857  test    eax, eax
0x180006859  jns     short loc_1800068CD
0x18000685b  lea     rcx, aCannotSetThePr; "cannot set the 'preserve white space' f"...
0x180006862  mov     [rsp+0D8h+var_A8], rcx
0x180006867  mov     [rsp+0D8h+var_B0], rdi
0x18000686c  mov     [rsp+0D8h+ppv], r13
0x180006871  mov     r9, [rsp+0D8h+arg_18]
0x180006879  mov     r8d, eax
0x18000687c  mov     edx, 0F6h
0x180006881  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180006888  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18000688d  mov     r15d, eax
0x180006890  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180006895  call    cs:__imp_VariantClear
0x18000689b  nop
0x18000689c  mov     rcx, [rsp+0D8h+arg_18]
0x1800068a4  test    rcx, rcx
0x1800068a7  jz      short loc_1800068B6
0x1800068a9  mov     rax, [rcx]
0x1800068ac  mov     rax, [rax+10h]
0x1800068b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b5  nop
0x1800068b6  test    r15d, r15d
0x1800068b9  jns     short loc_1800068FC
0x1800068bb  lea     rcx, [rsp+0D8h+var_98]
0x1800068c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800068c5  mov     eax, r15d
0x1800068c8  jmp     loc_180006954
0x1800068cd  mov     rbx, [rsp+0D8h+arg_18]
0x1800068d5  mov     [rsp+0D8h+arg_18], rdi
0x1800068dd  mov     [rsp+0D8h+var_98], rbx
0x1800068e2  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x1800068e7  call    cs:__imp_VariantClear
0x1800068ed  nop
0x1800068ee  lea     rcx, [rsp+0D8h+arg_18]
0x1800068f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800068fb  nop
0x1800068fc  jmp     short loc_180006917
0x1800068fe  jmp     short $+2
0x180006900  mov     rbx, [rsp+0D8h+var_98]
0x180006905  mov     rsi, [rsp+0D8h+arg_8]
0x18000690d  mov     r14, [rsp+0D8h+arg_10]
0x180006915  xor     edi, edi
0x180006917  mov     rdx, rbx; struct IXMLDOMDocument2 *
0x18000691a  mov     rcx, rsi; this
0x18000691d  call    ?LoadResultsFromXmlDoc@WinSATData@@QEAAJPEAUIXMLDOMDocument2@@@Z; WinSATData::LoadResultsFromXmlDoc(IXMLDOMDocument2 *)
0x180006922  mov     esi, eax
0x180006924  test    eax, eax
0x180006926  js      short loc_180006936
0x180006928  test    r14, r14
0x18000692b  jz      short loc_180006936
0x18000692d  mov     rcx, rbx
0x180006930  mov     rbx, rdi
0x180006933  mov     [r14], rcx
0x180006936  test    rbx, rbx
0x180006939  jz      short loc_18000694B
0x18000693b  mov     rax, [rbx]
0x18000693e  mov     rcx, rbx
0x180006941  mov     rax, [rax+10h]
0x180006945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694a  nop
0x18000694b  mov     eax, esi
0x18000694d  jmp     short loc_180006954
0x18000694f  mov     eax, 80070057h
0x180006954  add     rsp, 0A0h
0x18000695b  pop     r15
0x18000695d  pop     r14
0x18000695f  pop     r13
0x180006961  pop     r12
0x180006963  pop     rdi
0x180006964  pop     rsi
0x180006965  pop     rbx
0x180006966  retn
```
