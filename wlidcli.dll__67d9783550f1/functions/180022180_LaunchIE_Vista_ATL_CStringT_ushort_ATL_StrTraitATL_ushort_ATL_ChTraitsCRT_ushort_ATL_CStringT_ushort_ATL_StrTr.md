# LaunchIE_Vista(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180022180`
- end: `0x1800223be`
- name: `?LaunchIE_Vista@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002204c`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x18000a844`
- `0x18000cc9c`
- `0x18000e870`
- `0x18000fa9c`
- `0x180013638`
- `0x18001e32c`
- `0x180021c38`
- `0x180022180`
- `0x1800224dc`
- `0x1800530e4`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022341`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022341`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800222c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800222c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002227a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002227a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022399`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022399`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800222a5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800222a5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180022293`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180022293`

## string_xrefs

- `0x18002224e`: `Could not initialize COM with COINIT_APARTMENTTHREADED. 0x%x`
- `0x180022288`: `ieframe.dll`
- `0x180022352`: `Could not get system directory or load ieframe.dll. 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LaunchIE_Vista(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  HMODULE LibraryW; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rax
  signed int Error; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+20h] [rbp-E0h]
  int IWebBrowser2ForNewBrowserProcess; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  IUnknown *pUnk; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v17[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v21[2]; // [rsp+70h] [rbp-90h]
  _QWORD v22[7]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  IWebBrowser2ForNewBrowserProcess = 0;
  CAutoCoInitialize::Initialize((CAutoCoInitialize *)v17, 2u);
  pUnk = 0;
  v20 = 0;
  *(_QWORD *)v21 = 0;
  v15 = 0;
  memset_0(Buffer, 0, 0x20Au);
  v22[0] = "LaunchIE_Vista";
  v22[1] = &IWebBrowser2ForNewBrowserProcess;
  v22[2] = 0;
  v22[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
    "LaunchIE_Vista",
    (const char *)0x121,
    0,
    v12);
  v15 = 8;
  if ( v17[1] )
  {
    IWebBrowser2ForNewBrowserProcess = -2147417850;
    LODWORD(v13) = -2147417850;
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
      0x12Cu,
      L"Could not initialize COM with COINIT_APARTMENTTHREADED. 0x%x",
      v13);
    goto LABEL_14;
  }
  if ( GetSystemDirectoryW(Buffer, 0x105u) )
  {
    if ( PathAppendW(Buffer, L"ieframe.dll") )
    {
      LibraryW = LoadLibraryW(Buffer);
      v7 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "IELaunchURL");
        if ( ProcAddress )
        {
          IWebBrowser2ForNewBrowserProcess = ((__int64 (__fastcall *)(_QWORD, __int128 *, __int64 *))ProcAddress)(
                                               *a1,
                                               &v20,
                                               &v15);
          if ( IWebBrowser2ForNewBrowserProcess < 0 )
            goto LABEL_12;
          IWebBrowser2ForNewBrowserProcess = GetIWebBrowser2ForNewBrowserProcess(v21[0], (struct IWebBrowser2 **)&pUnk);
          if ( IWebBrowser2ForNewBrowserProcess < 0 )
            goto LABEL_12;
          v22[4] = &v18;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v18,
            a3);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v19,
            a2);
          Error = PostDataInIE(pUnk);
        }
        else
        {
          Error = ATL::AtlHresultFromLastError();
        }
        IWebBrowser2ForNewBrowserProcess = Error;
LABEL_12:
        FreeLibrary(v7);
        goto LABEL_14;
      }
    }
  }
  LODWORD(v13) = ATL::AtlHresultFromLastError();
  TracePrintW(
    2u,
    "clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
    0x139u,
    L"Could not get system directory or load ieframe.dll. 0x%x",
    v13);
  IWebBrowser2ForNewBrowserProcess = -2147186534;
LABEL_14:
  v10 = IWebBrowser2ForNewBrowserProcess;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pUnk);
  if ( v17[0] )
    CoUninitialize();
  return v10;
}

```

## disassembly

```asm
0x180022180  push    rbp
0x180022182  push    rbx
0x180022183  push    rsi
0x180022184  push    rdi
0x180022185  push    r14
0x180022187  lea     rbp, [rsp-1D0h]
0x18002218f  sub     rsp, 2D0h
0x180022196  mov     rax, cs:__security_cookie
0x18002219d  xor     rax, rsp
0x1800221a0  mov     [rbp+1F0h+var_30], rax
0x1800221a7  mov     r14, r8
0x1800221aa  mov     rsi, rdx
0x1800221ad  mov     rbx, rcx
0x1800221b0  mov     [rsp+2F0h+var_2C0], 0
0x1800221b8  mov     edx, 2; unsigned int
0x1800221bd  lea     rcx, [rsp+2F0h+var_2A8]; this
0x1800221c2  call    ?Initialize@CAutoCoInitialize@@AEAAXK@Z; CAutoCoInitialize::Initialize(ulong)
0x1800221c7  nop
0x1800221c8  mov     [rsp+2F0h+pUnk], 0
0x1800221d1  xorps   xmm0, xmm0
0x1800221d4  xor     eax, eax
0x1800221d6  movups  [rsp+2F0h+var_290], xmm0
0x1800221db  mov     qword ptr [rsp+2F0h+var_280], rax
0x1800221e0  mov     [rsp+2F0h+var_2B8], rax
0x1800221e5  xor     edx, edx; Val
0x1800221e7  mov     r8d, 20Ah; Size
0x1800221ed  lea     rcx, [rbp+1F0h+Buffer]; void *
0x1800221f1  call    memset_0
0x1800221f6  lea     rdx, aLaunchieVista; "LaunchIE_Vista"
0x1800221fd  mov     [rsp+2F0h+var_278], rdx
0x180022202  lea     rax, [rsp+2F0h+var_2C0]
0x180022207  mov     [rbp+1F0h+var_270], rax
0x18002220b  mov     [rbp+1F0h+var_268], 0
0x180022213  mov     [rbp+1F0h+var_260], 0
0x18002221b  xor     r9d, r9d; unsigned int
0x18002221e  mov     r8d, 121h; char *
0x180022224  lea     rcx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002222b  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180022230  nop
0x180022231  mov     [rsp+2F0h+var_2B8], 8
0x18002223a  cmp     [rsp+2F0h+var_2A4], 0
0x18002223f  jz      short loc_180022271
0x180022241  mov     eax, 80010106h
0x180022246  mov     [rsp+2F0h+var_2C0], eax
0x18002224a  mov     [rsp+2F0h+var_2D0], eax
0x18002224e  lea     r9, aCouldNotInitia; "Could not initialize COM with COINIT_AP"...
0x180022255  mov     r8d, 12Ch; unsigned int
0x18002225b  lea     rdx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180022262  mov     ecx, 2; unsigned __int8
0x180022267  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002226c  jmp     loc_180022378
0x180022271  mov     edx, 105h; uSize
0x180022276  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x18002227a  call    cs:__imp_GetSystemDirectoryW
0x180022280  test    eax, eax
0x180022282  jz      loc_180022349
0x180022288  lea     rdx, pszMore; "ieframe.dll"
0x18002228f  lea     rcx, [rbp+1F0h+Buffer]; pszPath
0x180022293  call    cs:__imp_PathAppendW
0x180022299  test    eax, eax
0x18002229b  jz      loc_180022349
0x1800222a1  lea     rcx, [rbp+1F0h+Buffer]; lpLibFileName
0x1800222a5  call    cs:__imp_LoadLibraryW
0x1800222ab  mov     rdi, rax
0x1800222ae  test    rax, rax
0x1800222b1  jz      loc_180022349
0x1800222b7  lea     rdx, aIelaunchurl; "IELaunchURL"
0x1800222be  mov     rcx, rax; hModule
0x1800222c1  call    cs:__imp_GetProcAddress
0x1800222c7  test    rax, rax
0x1800222ca  jnz     short loc_1800222D3
0x1800222cc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800222d1  jmp     short loc_18002233A
0x1800222d3  lea     r8, [rsp+2F0h+var_2B8]
0x1800222d8  lea     rdx, [rsp+2F0h+var_290]
0x1800222dd  mov     rcx, [rbx]
0x1800222e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222e5  mov     [rsp+2F0h+var_2C0], eax
0x1800222e9  test    eax, eax
0x1800222eb  js      short loc_18002233E
0x1800222ed  lea     rdx, [rsp+2F0h+pUnk]; struct IWebBrowser2 **
0x1800222f2  mov     ecx, [rsp+2F0h+var_280]; unsigned int
0x1800222f6  call    ?GetIWebBrowser2ForNewBrowserProcess@@YAJKPEAPEAUIWebBrowser2@@@Z; GetIWebBrowser2ForNewBrowserProcess(ulong,IWebBrowser2 * *)
0x1800222fb  mov     [rsp+2F0h+var_2C0], eax
0x1800222ff  test    eax, eax
0x180022301  js      short loc_18002233E
0x180022303  lea     rax, [rsp+2F0h+var_2A0]
0x180022308  mov     [rbp+1F0h+var_258], rax
0x18002230c  mov     rdx, r14
0x18002230f  lea     rcx, [rsp+2F0h+var_2A0]
0x180022314  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180022319  mov     rbx, rax
0x18002231c  mov     rdx, rsi
0x18002231f  lea     rcx, [rsp+2F0h+var_298]
0x180022324  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180022329  nop
0x18002232a  mov     r8, rbx
0x18002232d  mov     rdx, rax
0x180022330  mov     rcx, [rsp+2F0h+pUnk]; pUnk
0x180022335  call    ?PostDataInIE@@YAJPEAUIWebBrowser2@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; PostDataInIE(IWebBrowser2 *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18002233a  mov     [rsp+2F0h+var_2C0], eax
0x18002233e  mov     rcx, rdi; hLibModule
0x180022341  call    cs:__imp_FreeLibrary
0x180022347  jmp     short loc_180022378
0x180022349  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002234e  mov     [rsp+2F0h+var_2D0], eax
0x180022352  lea     r9, aCouldNotGetSys; "Could not get system directory or load "...
0x180022359  mov     r8d, 139h; unsigned int
0x18002235f  lea     rdx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180022366  mov     ecx, 2; unsigned __int8
0x18002236b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022370  mov     [rsp+2F0h+var_2C0], 8004889Ah
0x180022378  mov     ebx, [rsp+2F0h+var_2C0]
0x18002237c  lea     rcx, [rsp+2F0h+var_278]
0x180022381  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180022386  nop
0x180022387  lea     rcx, [rsp+2F0h+pUnk]
0x18002238c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180022391  nop
0x180022392  cmp     [rsp+2F0h+var_2A8], 0
0x180022397  jz      short loc_18002239F
0x180022399  call    cs:__imp_CoUninitialize
0x18002239f  mov     eax, ebx
0x1800223a1  mov     rcx, [rbp+1F0h+var_30]
0x1800223a8  xor     rcx, rsp; StackCookie
0x1800223ab  call    __security_check_cookie
0x1800223b0  add     rsp, 2D0h
0x1800223b7  pop     r14
0x1800223b9  pop     rdi
0x1800223ba  pop     rsi
0x1800223bb  pop     rbx
0x1800223bc  pop     rbp
0x1800223bd  retn
```
