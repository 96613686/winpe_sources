# HlinkSimpleNavigateToMoniker

- ea: `0x1800fac90`
- end: `0x1800fb316`
- name: `HlinkSimpleNavigateToMoniker`
- size: `1670`
- prototype: `HRESULT __stdcall(IMoniker *pmkTarget, LPCWSTR szLocation, LPCWSTR szTargetFrameName, IUnknown *pUnk, IBindCtx *pbc, IBindStatusCallback *, DWORD grfHLNF, DWORD dwReserved)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fab70`
- `0x1800fb320`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x180033980`
- `0x1800a5d70`
- `0x1800f961c`
- `0x1800f9644`
- `0x1800f9dac`
- `0x1800f9fc0`
- `0x1800fa748`
- `0x1800fa834`
- `0x1800fac90`
- `0x1800fb408`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800faeaa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800fb1eb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800faeaa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800fb1eb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800facef`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800facef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fb257`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fb257`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800fb243`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800fb243`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlA` at `0x1800fb20e`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlA` at `0x1800fb20e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb122`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb2db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb122`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb2db`

## pseudocode

```c
HRESULT __stdcall HlinkSimpleNavigateToMoniker(
        IMoniker *pmkTarget,
        LPCWSTR szLocation,
        LPCWSTR szTargetFrameName,
        IUnknown *pUnk,
        IBindCtx *pbc,
        IBindStatusCallback *a6,
        DWORD grfHLNF,
        DWORD dwReserved)
{
  const char *v12; // rdx
  __int64 (**v13)(void); // r8
  __int64 v14; // r9
  struct IHlinkFrame *v16; // rdi
  DWORD v17; // ebx
  HRESULT PopupManager; // ebx
  struct IMonikerVtbl *lpVtbl; // rax
  __int64 v20; // rdx
  unsigned __int16 *v21; // rcx
  GUID *v22; // rcx
  __int64 v23; // rax
  int cbMultiByte; // eax
  __int64 v25; // r9
  unsigned int v26; // r14d
  int AnInterface; // eax
  LPVOID v28; // rcx
  int v29; // eax
  int v30; // r14d
  __int64 v31; // rcx
  struct IMonikerVtbl *v32; // rax
  struct IMonikerVtbl *v33; // rax
  __int64 v34; // rax
  int v35; // r14d
  size_t v36; // r15
  CHAR *lpMultiByteStr; // rsi
  HANDLE FileA; // rax
  CHAR *v39; // rcx
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  LPCWCH lpWideCharStr; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcchPath[2]; // [rsp+68h] [rbp-98h] BYREF
  int v44; // [rsp+70h] [rbp-90h] BYREF
  struct ITargetFrame *v45; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  IBindStatusCallback *v48; // [rsp+90h] [rbp-70h]
  HMODULE v49; // [rsp+98h] [rbp-68h] BYREF
  int v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  CHAR MultiByteStr[32]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR pszPath[272]; // [rsp+D0h] [rbp-30h] BYREF

  v48 = a6;
  InitOnceExecuteOnce(&stru_18016BB00, (PINIT_ONCE_FN)InitOnceDeviceFamily, 0, 0);
  if ( byte_18016AF34 )
    return -2147467263;
  v41 = 0;
  v16 = 0;
  pv = 0;
  v45 = 0;
  v50 = 0;
  v51 = 0;
  v46 = 0;
  if ( pmkTarget )
  {
    lpVtbl = pmkTarget->lpVtbl;
    v44 = 0;
    if ( ((int (__fastcall *)(IMoniker *, int *))lpVtbl->IsSystemMoniker)(pmkTarget, &v44) >= 0
      && v44 == 6
      && ((int (__fastcall *)(IMoniker *, _QWORD, _QWORD, unsigned __int16 **))pmkTarget->lpVtbl->GetDisplayName)(
           pmkTarget,
           0,
           0,
           &v46) >= 0 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v46[v20] );
      PopupManager = WrapSpecialUrlFlat(v46, (int)v20 + 1);
      if ( PopupManager < 0 )
      {
        v21 = v46;
LABEL_82:
        CoTaskMemFree(v21);
        goto LABEL_83;
      }
    }
    v17 = grfHLNF;
LABEL_16:
    v22 = &IID_IHlinkFrame;
    if ( pUnk )
    {
      GetAnInterface(pUnk, &IID_IWebBrowserApp, &v41, v14, (__int64)&IID_IHlinkFrame, (__int64)&IID_IHlinkFrame, &pv);
      v16 = (struct IHlinkFrame *)pv;
    }
    v47 = 0;
    if ( (unsigned int)HLinkDll::LoadFunc((HLinkDll *)v22, v12, v13)
      && (int)((__int64 (__fastcall *)(IMoniker *, LPCWSTR, const wchar_t *, _QWORD, _DWORD, _QWORD, GUID *, __int64 *))qword_180169478)(
                pmkTarget,
                szLocation,
                L"TheName",
                0,
                0,
                0,
                &IID_IHlink,
                &v47) >= 0
      && v16 )
    {
      if ( szTargetFrameName && *szTargetFrameName )
      {
        v23 = -1;
        do
          ++v23;
        while ( szTargetFrameName[v23] );
        cbMultiByte = v23 + 1;
        if ( cbMultiByte > 20 )
          cbMultiByte = 20;
        WideCharToMultiByte(0, 0, szTargetFrameName, -1, MultiByteStr, cbMultiByte, 0, 0);
        if ( (unsigned int)StrCmpIIA(MultiByteStr, "_blank") )
        {
          AnInterface = GetAnInterface(
                          pUnk,
                          &IID_ITargetFrame,
                          &v45,
                          v25,
                          (__int64)&IID_ITargetFrame,
                          (__int64)&IID_ITargetFrame,
                          0);
          v28 = 0;
          pv = 0;
          if ( AnInterface >= 0 )
          {
            ((void (__fastcall *)(struct ITargetFrame *, LPCWSTR, struct IHlinkFrame *, __int64, LPVOID *))v45->lpVtbl->FindFrame)(
              v45,
              szTargetFrameName,
              v16,
              1,
              &pv);
            v28 = pv;
          }
          *(_QWORD *)pcchPath = 0;
          if ( v28 )
          {
            lpWideCharStr = 0;
            (**(void (__fastcall ***)(LPVOID, GUID *, LPCWCH *))v28)(v28, &IID_IServiceProvider, &lpWideCharStr);
            if ( lpWideCharStr )
            {
              (*(void (__fastcall **)(LPCWCH, GUID *, GUID *, DWORD *))(*(_QWORD *)lpWideCharStr + 24LL))(
                lpWideCharStr,
                &IID_IWebBrowserApp,
                &IID_IHlinkFrame,
                pcchPath);
              (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)lpWideCharStr + 16LL))(lpWideCharStr);
            }
            v29 = AccessAllowed(v45, *(struct IHlinkFrame **)pcchPath);
            v28 = pv;
            v30 = v29;
          }
          else
          {
            v30 = 1;
            v17 |= 0x80000002;
          }
          if ( v28 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v45 )
            ((void (__fastcall *)(struct ITargetFrame *))v45->lpVtbl->Release)(v45);
          if ( *(_QWORD *)pcchPath )
          {
            ((void (__fastcall *)(struct IHlinkFrame *))v16->lpVtbl->Release)(v16);
            v16 = *(struct IHlinkFrame **)pcchPath;
          }
          if ( !v30 )
          {
            PopupManager = -2147024891;
            goto LABEL_75;
          }
        }
        else
        {
          v17 |= 0x80000002;
        }
      }
      v26 = v17 | 0x200000;
      if ( CoInternetIsFeatureEnabled(FEATURE_RESTRICT_FILEDOWNLOAD, 2u) == 1 )
        v26 = v17;
      if ( (v26 & 2) != 0 )
      {
        PopupManager = QueryPopupManager(pUnk, (__int64 *)pmkTarget, (__int64)szTargetFrameName);
        if ( PopupManager < 0 )
          goto LABEL_75;
      }
      PopupManager = ((__int64 (__fastcall *)(struct IHlinkFrame *, _QWORD, IBindCtx *, IBindStatusCallback *, __int64))v16->lpVtbl->Navigate)(
                       v16,
                       v26,
                       pbc,
                       v48,
                       v47);
      if ( PopupManager >= 0 )
        goto LABEL_75;
    }
    else
    {
      PopupManager = -2147467259;
    }
    if ( v16 )
    {
      if ( v41 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        v41 = 0;
      }
      ((void (__fastcall *)(struct IHlinkFrame *, GUID *, __int64 *))v16->lpVtbl->QueryInterface)(
        v16,
        &IID_IWebBrowserApp,
        &v41);
    }
    v31 = v41;
    if ( v41 )
    {
      if ( pmkTarget )
      {
        v32 = pmkTarget->lpVtbl;
        pv = 0;
        PopupManager = ((__int64 (__fastcall *)(IMoniker *, IBindCtx *, _QWORD, LPVOID *))v32->GetDisplayName)(
                         pmkTarget,
                         pbc,
                         0,
                         &pv);
        if ( PopupManager >= 0 )
        {
          PopupManager = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v41 + 88LL))(
                           v41,
                           pv,
                           0,
                           0,
                           0,
                           0);
          CoTaskMemFree(pv);
          if ( PopupManager >= 0 )
            goto LABEL_75;
        }
        v31 = v41;
      }
      if ( v31 )
      {
LABEL_76:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
LABEL_77:
        if ( v16 )
          ((void (__fastcall *)(struct IHlinkFrame *))v16->lpVtbl->Release)(v16);
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        v21 = v46;
        if ( !v46 )
          goto LABEL_83;
        goto LABEL_82;
      }
    }
    if ( !pmkTarget )
      goto LABEL_77;
    PopupManager = QueryPopupManager(pUnk, (__int64 *)pmkTarget, (__int64)szTargetFrameName);
    if ( PopupManager >= 0 )
    {
      v33 = pmkTarget->lpVtbl;
      pcchPath[0] = 260;
      lpWideCharStr = 0;
      if ( ((int (__fastcall *)(IMoniker *, IBindCtx *, _QWORD, LPCWCH *))v33->GetDisplayName)(
             pmkTarget,
             pbc,
             0,
             &lpWideCharStr) >= 0 )
      {
        v34 = -1;
        do
          ++v34;
        while ( lpWideCharStr[v34 + 1] );
        v35 = 2 * v34;
        v36 = 2 * (int)v34;
        lpMultiByteStr = (CHAR *)operator new(v36);
        if ( !lpMultiByteStr )
          goto LABEL_74;
        WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, v35, 0, 0);
        lpMultiByteStr[v36 - 1] = 0;
        if ( PathCreateFromUrlA(lpMultiByteStr, pszPath, pcchPath, 0) < 0 )
        {
          v39 = lpMultiByteStr;
        }
        else
        {
          FileA = CreateFileA(pszPath, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( FileA == (HANDLE)-1LL )
          {
            PopupManager = -2147467259;
LABEL_73:
            operator delete(lpMultiByteStr);
LABEL_74:
            CoTaskMemFree((LPVOID)lpWideCharStr);
            goto LABEL_75;
          }
          CloseHandle(FileA);
          v39 = pszPath;
        }
        PopupManager = DoUrlShellExecuteA(v39);
        goto LABEL_73;
      }
    }
LABEL_75:
    v31 = v41;
    if ( !v41 )
      goto LABEL_77;
    goto LABEL_76;
  }
  if ( szLocation && *szLocation )
  {
    v17 = grfHLNF | 1;
    goto LABEL_16;
  }
  PopupManager = -2147024809;
LABEL_83:
  CShellDll::~CShellDll(&v49);
  return PopupManager;
}

```

## disassembly

```asm
0x1800fac90  push    rbp
0x1800fac92  push    rbx
0x1800fac93  push    rsi
0x1800fac94  push    rdi
0x1800fac95  push    r12
0x1800fac97  push    r13
0x1800fac99  push    r14
0x1800fac9b  push    r15
0x1800fac9d  lea     rbp, [rsp-0F8h]
0x1800faca5  sub     rsp, 1F8h
0x1800facac  mov     rax, cs:__security_cookie
0x1800facb3  xor     rax, rsp
0x1800facb6  mov     [rbp+130h+var_50], rax
0x1800facbd  mov     rax, [rbp+130h+arg_28]
0x1800facc4  mov     r12, r9
0x1800facc7  mov     r13, [rbp+130h+pbc]
0x1800facce  mov     r15, r8
0x1800facd1  mov     r14, rdx
0x1800facd4  mov     [rbp+130h+var_1A0], rax
0x1800facd8  mov     rsi, rcx
0x1800facdb  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800face2  xor     r9d, r9d; Context
0x1800face5  lea     rcx, stru_18016BB00; InitOnce
0x1800facec  xor     r8d, r8d; Parameter
0x1800facef  call    cs:__imp_InitOnceExecuteOnce
0x1800facf6  nop     dword ptr [rax+rax+00h]
0x1800facfb  xor     ebx, ebx
0x1800facfd  cmp     cs:byte_18016AF34, bl
0x1800fad03  jz      short loc_1800FAD0F
0x1800fad05  mov     eax, 80004001h
0x1800fad0a  jmp     loc_1800FB2F2
0x1800fad0f  mov     [rsp+230h+var_1D8], rbx
0x1800fad14  mov     rdi, rbx
0x1800fad17  mov     [rsp+230h+pv], rbx
0x1800fad1c  mov     [rsp+230h+var_1B8], rbx
0x1800fad21  mov     [rbp+130h+var_190], ebx
0x1800fad24  mov     [rbp+130h+var_188], rbx
0x1800fad28  mov     [rbp+130h+var_1B0], rbx
0x1800fad2c  test    rsi, rsi
0x1800fad2f  jnz     short loc_1800FAD51
0x1800fad31  test    r14, r14
0x1800fad34  jz      short loc_1800FAD47
0x1800fad36  cmp     [r14], bx
0x1800fad3a  jz      short loc_1800FAD47
0x1800fad3c  mov     ebx, [rbp+130h+grfHLNF]
0x1800fad42  or      ebx, 1
0x1800fad45  jmp     short loc_1800FADC3
0x1800fad47  mov     ebx, 80070057h
0x1800fad4c  jmp     loc_1800FB2E7
0x1800fad51  mov     rax, [rsi]
0x1800fad54  lea     rdx, [rsp+230h+var_1C0]
0x1800fad59  mov     rcx, rsi
0x1800fad5c  mov     [rsp+230h+var_1C0], ebx
0x1800fad60  mov     rax, [rax+0B0h]
0x1800fad67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fad6c  test    eax, eax
0x1800fad6e  js      short loc_1800FADBD
0x1800fad70  cmp     [rsp+230h+var_1C0], 6
0x1800fad75  jnz     short loc_1800FADBD
0x1800fad77  mov     rax, [rsi]
0x1800fad7a  lea     r9, [rbp+130h+var_1B0]
0x1800fad7e  xor     r8d, r8d
0x1800fad81  xor     edx, edx
0x1800fad83  mov     rcx, rsi
0x1800fad86  mov     rax, [rax+0A0h]
0x1800fad8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fad92  test    eax, eax
0x1800fad94  js      short loc_1800FADBD
0x1800fad96  mov     rcx, [rbp+130h+var_1B0]; unsigned __int16 *
0x1800fad9a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800fad9e  inc     rdx
0x1800fada1  cmp     [rcx+rdx*2], bx
0x1800fada5  jnz     short loc_1800FAD9E
0x1800fada7  inc     edx; unsigned int
0x1800fada9  call    ?WrapSpecialUrlFlat@@YAJPEAGK@Z; WrapSpecialUrlFlat(ushort *,ulong)
0x1800fadae  mov     ebx, eax
0x1800fadb0  test    eax, eax
0x1800fadb2  jns     short loc_1800FADBD
0x1800fadb4  mov     rcx, [rbp+130h+var_1B0]
0x1800fadb8  jmp     loc_1800FB2DB
0x1800fadbd  mov     ebx, [rbp+130h+grfHLNF]
0x1800fadc3  lea     rcx, IID_IHlinkFrame
0x1800fadca  test    r12, r12
0x1800fadcd  jz      short loc_1800FADFC
0x1800fadcf  lea     rax, [rsp+230h+pv]
0x1800fadd4  mov     [rsp+230h+lpDefaultChar], rax
0x1800fadd9  lea     r8, [rsp+230h+var_1D8]
0x1800fadde  mov     qword ptr [rsp+230h+cbMultiByte], rcx
0x1800fade3  lea     rdx, IID_IWebBrowserApp
0x1800fadea  mov     [rsp+230h+lpMultiByteStr], rcx
0x1800fadef  mov     rcx, r12
0x1800fadf2  call    GetAnInterface
0x1800fadf7  mov     rdi, [rsp+230h+pv]
0x1800fadfc  mov     [rbp+130h+var_1A8], 0
0x1800fae04  call    ?LoadFunc@HLinkDll@@AEAAHPEBDAEAP6A_JXZ@Z; HLinkDll::LoadFunc(char const *,__int64 (*&)(void))
0x1800fae09  xor     ecx, ecx
0x1800fae0b  test    eax, eax
0x1800fae0d  jz      loc_1800FB074
0x1800fae13  lea     rax, [rbp+130h+var_1A8]
0x1800fae17  xor     r9d, r9d
0x1800fae1a  mov     [rsp+230h+lpUsedDefaultChar], rax
0x1800fae1f  lea     r8, aThename; "TheName"
0x1800fae26  lea     rax, IID_IHlink
0x1800fae2d  mov     rdx, r14
0x1800fae30  mov     [rsp+230h+lpDefaultChar], rax
0x1800fae35  mov     rax, cs:qword_180169478
0x1800fae3c  mov     qword ptr [rsp+230h+cbMultiByte], rcx
0x1800fae41  mov     dword ptr [rsp+230h+lpMultiByteStr], ecx
0x1800fae45  mov     rcx, rsi
0x1800fae48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fae4d  xor     r14d, r14d
0x1800fae50  test    eax, eax
0x1800fae52  js      loc_1800FB077
0x1800fae58  test    rdi, rdi
0x1800fae5b  jz      loc_1800FB077
0x1800fae61  test    r15, r15
0x1800fae64  jz      short loc_1800FAED0
0x1800fae66  cmp     [r15], r14w
0x1800fae6a  jz      short loc_1800FAED0
0x1800fae6c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800fae70  mov     rax, rdx
0x1800fae73  inc     rax
0x1800fae76  cmp     [r15+rax*2], r14w
0x1800fae7b  jnz     short loc_1800FAE73
0x1800fae7d  inc     eax
0x1800fae7f  mov     [rsp+230h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1800fae84  mov     ecx, 14h
0x1800fae89  mov     [rsp+230h+lpDefaultChar], r14; lpDefaultChar
0x1800fae8e  cmp     eax, ecx
0x1800fae90  mov     r9d, edx; cchWideChar
0x1800fae93  mov     r8, r15; lpWideCharStr
0x1800fae96  cmovg   eax, ecx
0x1800fae99  xor     edx, edx; dwFlags
0x1800fae9b  mov     [rsp+230h+cbMultiByte], eax; cbMultiByte
0x1800fae9f  xor     ecx, ecx; CodePage
0x1800faea1  lea     rax, [rbp+130h+MultiByteStr]
0x1800faea5  mov     [rsp+230h+lpMultiByteStr], rax; lpMultiByteStr
0x1800faeaa  call    cs:__imp_WideCharToMultiByte
0x1800faeb1  nop     dword ptr [rax+rax+00h]
0x1800faeb6  lea     rdx, aBlank; "_blank"
0x1800faebd  lea     rcx, [rbp+130h+MultiByteStr]; lpString1
0x1800faec1  call    ?StrCmpIIA@@YAHPEBD0@Z; StrCmpIIA(char const *,char const *)
0x1800faec6  test    eax, eax
0x1800faec8  jnz     short loc_1800FAF3E
0x1800faeca  or      ebx, 80000002h
0x1800faed0  mov     edx, 2; dwFlags
0x1800faed5  lea     ecx, [rdx+0Ah]; FeatureEntry
0x1800faed8  call    CoInternetIsFeatureEnabled
0x1800faedd  mov     r14d, ebx
0x1800faee0  bts     r14d, 15h
0x1800faee5  cmp     eax, 1
0x1800faee8  cmovz   r14d, ebx
0x1800faeec  test    r14b, 2
0x1800faef0  jz      short loc_1800FAF0A
0x1800faef2  mov     r8, r15
0x1800faef5  mov     rdx, rsi
0x1800faef8  mov     rcx, r12; punk
0x1800faefb  call    QueryPopupManager
0x1800faf00  mov     ebx, eax
0x1800faf02  test    eax, eax
0x1800faf04  js      loc_1800FB293
0x1800faf0a  mov     rcx, [rbp+130h+var_1A8]
0x1800faf0e  mov     r8, r13
0x1800faf11  mov     rax, [rdi]
0x1800faf14  mov     edx, r14d
0x1800faf17  mov     r9, [rbp+130h+var_1A0]
0x1800faf1b  mov     [rsp+230h+lpMultiByteStr], rcx
0x1800faf20  mov     rcx, rdi
0x1800faf23  mov     rax, [rax+28h]
0x1800faf27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faf2c  xor     r14d, r14d
0x1800faf2f  mov     ebx, eax
0x1800faf31  test    eax, eax
0x1800faf33  jns     loc_1800FB293
0x1800faf39  jmp     loc_1800FB07C
0x1800faf3e  lea     rdx, IID_ITargetFrame
0x1800faf45  mov     [rsp+230h+lpDefaultChar], r14
0x1800faf4a  mov     qword ptr [rsp+230h+cbMultiByte], rdx
0x1800faf4f  lea     r8, [rsp+230h+var_1B8]
0x1800faf54  mov     rcx, r12
0x1800faf57  mov     [rsp+230h+lpMultiByteStr], rdx
0x1800faf5c  call    GetAnInterface
0x1800faf61  mov     rcx, r14
0x1800faf64  mov     [rsp+230h+pv], rcx
0x1800faf69  test    eax, eax
0x1800faf6b  js      short loc_1800FAF99
0x1800faf6d  mov     rcx, [rsp+230h+var_1B8]
0x1800faf72  lea     rdx, [rsp+230h+pv]
0x1800faf77  mov     [rsp+230h+lpMultiByteStr], rdx
0x1800faf7c  mov     r9d, 1
0x1800faf82  mov     r8, rdi
0x1800faf85  mov     rdx, r15
0x1800faf88  mov     rax, [rcx]
0x1800faf8b  mov     rax, [rax+30h]
0x1800faf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faf94  mov     rcx, [rsp+230h+pv]
0x1800faf99  mov     qword ptr [rsp+230h+pcchPath], r14
0x1800faf9e  test    rcx, rcx
0x1800fafa1  jz      short loc_1800FB012
0x1800fafa3  mov     [rsp+230h+lpWideCharStr], r14
0x1800fafa8  lea     r8, [rsp+230h+lpWideCharStr]
0x1800fafad  mov     rax, [rcx]
0x1800fafb0  lea     rdx, IID_IServiceProvider
0x1800fafb7  mov     rax, [rax]
0x1800fafba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fafbf  mov     rcx, [rsp+230h+lpWideCharStr]
0x1800fafc4  test    rcx, rcx
0x1800fafc7  jz      short loc_1800FAFF9
0x1800fafc9  mov     rax, [rcx]
0x1800fafcc  lea     r9, [rsp+230h+pcchPath]
0x1800fafd1  lea     r8, IID_IHlinkFrame
0x1800fafd8  lea     rdx, IID_IWebBrowserApp
0x1800fafdf  mov     rax, [rax+18h]
0x1800fafe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fafe8  mov     rcx, [rsp+230h+lpWideCharStr]
0x1800fafed  mov     rax, [rcx]
0x1800faff0  mov     rax, [rax+10h]
0x1800faff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faff9  mov     rdx, qword ptr [rsp+230h+pcchPath]; struct IHlinkFrame *
0x1800faffe  mov     rcx, [rsp+230h+var_1B8]; struct ITargetFrame *
0x1800fb003  call    ?AccessAllowed@@YAHPEAUITargetFrame@@PEAUIHlinkFrame@@@Z; AccessAllowed(ITargetFrame *,IHlinkFrame *)
0x1800fb008  mov     rcx, [rsp+230h+pv]
0x1800fb00d  mov     r14d, eax
0x1800fb010  jmp     short loc_1800FB01E
0x1800fb012  mov     r14d, 1
0x1800fb018  or      ebx, 80000002h
0x1800fb01e  test    rcx, rcx
0x1800fb021  jz      short loc_1800FB02F
0x1800fb023  mov     rax, [rcx]
0x1800fb026  mov     rax, [rax+10h]
0x1800fb02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb02f  mov     rcx, [rsp+230h+var_1B8]
0x1800fb034  test    rcx, rcx
0x1800fb037  jz      short loc_1800FB045
0x1800fb039  mov     rax, [rcx]
0x1800fb03c  mov     rax, [rax+10h]
0x1800fb040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb045  cmp     qword ptr [rsp+230h+pcchPath], 0
0x1800fb04b  jz      short loc_1800FB061
0x1800fb04d  mov     rax, [rdi]
0x1800fb050  mov     rcx, rdi
0x1800fb053  mov     rax, [rax+10h]
0x1800fb057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb05c  mov     rdi, qword ptr [rsp+230h+pcchPath]
0x1800fb061  test    r14d, r14d
0x1800fb064  jnz     loc_1800FAED0
0x1800fb06a  mov     ebx, 80070005h
0x1800fb06f  jmp     loc_1800FB293
0x1800fb074  xor     r14d, r14d
0x1800fb077  mov     ebx, 80004005h
0x1800fb07c  test    rdi, rdi
0x1800fb07f  jz      short loc_1800FB0BE
0x1800fb081  mov     rcx, [rsp+230h+var_1D8]
0x1800fb086  test    rcx, rcx
0x1800fb089  jz      short loc_1800FB09C
0x1800fb08b  mov     rax, [rcx]
0x1800fb08e  mov     rax, [rax+10h]
0x1800fb092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb097  mov     [rsp+230h+var_1D8], r14
0x1800fb09c  mov     rax, [rdi]
0x1800fb09f  lea     r8, [rsp+230h+var_1D8]
0x1800fb0a4  lea     rdx, IID_IWebBrowserApp
0x1800fb0ab  mov     rcx, rdi
0x1800fb0ae  mov     rax, [rax]
0x1800fb0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0b6  test    ebx, ebx
0x1800fb0b8  jns     loc_1800FB293
0x1800fb0be  mov     rcx, [rsp+230h+var_1D8]
0x1800fb0c3  test    rcx, rcx
0x1800fb0c6  jz      short loc_1800FB144
0x1800fb0c8  test    rsi, rsi
0x1800fb0cb  jz      short loc_1800FB13B
0x1800fb0cd  mov     rax, [rsi]
0x1800fb0d0  lea     r9, [rsp+230h+pv]
0x1800fb0d5  xor     r8d, r8d
0x1800fb0d8  mov     [rsp+230h+pv], r14
0x1800fb0dd  mov     rdx, r13
0x1800fb0e0  mov     rcx, rsi
0x1800fb0e3  mov     rax, [rax+0A0h]
0x1800fb0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0ef  mov     ebx, eax
0x1800fb0f1  test    eax, eax
0x1800fb0f3  js      short loc_1800FB136
0x1800fb0f5  mov     rcx, [rsp+230h+var_1D8]
0x1800fb0fa  xor     r9d, r9d
0x1800fb0fd  mov     rdx, [rsp+230h+pv]
0x1800fb102  xor     r8d, r8d
0x1800fb105  mov     qword ptr [rsp+230h+cbMultiByte], r14
0x1800fb10a  mov     [rsp+230h+lpMultiByteStr], r14
0x1800fb10f  mov     rax, [rcx]
0x1800fb112  mov     rax, [rax+58h]
0x1800fb116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb11b  mov     rcx, [rsp+230h+pv]; pv
0x1800fb120  mov     ebx, eax
0x1800fb122  call    cs:__imp_CoTaskMemFree
0x1800fb129  nop     dword ptr [rax+rax+00h]
0x1800fb12e  test    ebx, ebx
0x1800fb130  jns     loc_1800FB293
0x1800fb136  mov     rcx, [rsp+230h+var_1D8]
0x1800fb13b  test    rcx, rcx
  ... truncated ...
```
