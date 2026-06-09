# HlinkSimpleNavigateToMoniker

- ea: `0x1800f0aa0`
- end: `0x1800f10ef`
- name: `HlinkSimpleNavigateToMoniker`
- size: `1615`
- prototype: `HRESULT __stdcall(IMoniker *pmkTarget, LPCWSTR szLocation, LPCWSTR szTargetFrameName, IUnknown *pUnk, IBindCtx *pbc, IBindStatusCallback *, DWORD grfHLNF, DWORD dwReserved)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f09a0`
- `0x1800f1100`

## callees

- `0x1800150e0`
- `0x18002d6f0`
- `0x180030880`
- `0x18009ef68`
- `0x1800ef490`
- `0x1800ef4b0`
- `0x1800efc0c`
- `0x1800efe3c`
- `0x1800f0594`
- `0x1800f0674`
- `0x1800f0aa0`
- `0x1800f11e0`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800f0cb4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800f0fe9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800f0cb4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800f0fe9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800f0aff`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800f0aff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1043`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800f1035`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800f1035`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlA` at `0x1800f1006`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlA` at `0x1800f1006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f106d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f10bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f0f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f106d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f10bb`

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
  int v14; // r9d
  struct IHlinkFrame *v16; // rdi
  DWORD v17; // ebx
  HRESULT PopupManager; // ebx
  struct IMonikerVtbl *lpVtbl; // rax
  __int64 v20; // rdx
  unsigned __int16 *v21; // rcx
  GUID *v22; // rcx
  __int64 v23; // rax
  int cbMultiByte; // eax
  int v25; // r9d
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
  _BYTE v49[8]; // [rsp+98h] [rbp-68h] BYREF
  int v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  CHAR MultiByteStr[32]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR pszPath[272]; // [rsp+D0h] [rbp-30h] BYREF

  v48 = a6;
  InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
  if ( byte_18015DE34 )
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
      GetAnInterface(
        (_DWORD)pUnk,
        (unsigned int)&IID_IWebBrowserApp,
        (unsigned int)&v41,
        v14,
        (__int64)&IID_IHlinkFrame,
        (__int64)&IID_IHlinkFrame,
        (__int64)&pv);
      v16 = (struct IHlinkFrame *)pv;
    }
    v47 = 0;
    if ( (unsigned int)HLinkDll::LoadFunc((HLinkDll *)v22, v12, v13)
      && (int)((__int64 (__fastcall *)(IMoniker *, LPCWSTR, const wchar_t *, _QWORD, _DWORD, _QWORD, GUID *, __int64 *))qword_18015C378)(
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
                          (_DWORD)pUnk,
                          (unsigned int)&IID_ITargetFrame,
                          (unsigned int)&v45,
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
  CShellDll::~CShellDll((CShellDll *)v49);
  return PopupManager;
}

```

## disassembly

```asm
0x1800f0aa0  push    rbp
0x1800f0aa2  push    rbx
0x1800f0aa3  push    rsi
0x1800f0aa4  push    rdi
0x1800f0aa5  push    r12
0x1800f0aa7  push    r13
0x1800f0aa9  push    r14
0x1800f0aab  push    r15
0x1800f0aad  lea     rbp, [rsp-0F8h]
0x1800f0ab5  sub     rsp, 1F8h
0x1800f0abc  mov     rax, cs:__security_cookie
0x1800f0ac3  xor     rax, rsp
0x1800f0ac6  mov     [rbp+130h+var_50], rax
0x1800f0acd  mov     rax, [rbp+130h+arg_28]
0x1800f0ad4  mov     r12, r9
0x1800f0ad7  mov     r13, [rbp+130h+pbc]
0x1800f0ade  mov     r15, r8
0x1800f0ae1  mov     r14, rdx
0x1800f0ae4  mov     [rbp+130h+var_1A0], rax
0x1800f0ae8  mov     rsi, rcx
0x1800f0aeb  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800f0af2  xor     r9d, r9d; Context
0x1800f0af5  lea     rcx, stru_18015EA38; InitOnce
0x1800f0afc  xor     r8d, r8d; Parameter
0x1800f0aff  call    cs:__imp_InitOnceExecuteOnce
0x1800f0b05  xor     ebx, ebx
0x1800f0b07  cmp     cs:byte_18015DE34, bl
0x1800f0b0d  jz      short loc_1800F0B19
0x1800f0b0f  mov     eax, 80004001h
0x1800f0b14  jmp     loc_1800F10CC
0x1800f0b19  mov     [rsp+230h+var_1D8], rbx
0x1800f0b1e  mov     rdi, rbx
0x1800f0b21  mov     [rsp+230h+pv], rbx
0x1800f0b26  mov     [rsp+230h+var_1B8], rbx
0x1800f0b2b  mov     [rbp+130h+var_190], ebx
0x1800f0b2e  mov     [rbp+130h+var_188], rbx
0x1800f0b32  mov     [rbp+130h+var_1B0], rbx
0x1800f0b36  test    rsi, rsi
0x1800f0b39  jnz     short loc_1800F0B5B
0x1800f0b3b  test    r14, r14
0x1800f0b3e  jz      short loc_1800F0B51
0x1800f0b40  cmp     [r14], bx
0x1800f0b44  jz      short loc_1800F0B51
0x1800f0b46  mov     ebx, [rbp+130h+grfHLNF]
0x1800f0b4c  or      ebx, 1
0x1800f0b4f  jmp     short loc_1800F0BCD
0x1800f0b51  mov     ebx, 80070057h
0x1800f0b56  jmp     loc_1800F10C1
0x1800f0b5b  mov     rax, [rsi]
0x1800f0b5e  lea     rdx, [rsp+230h+var_1C0]
0x1800f0b63  mov     rcx, rsi
0x1800f0b66  mov     [rsp+230h+var_1C0], ebx
0x1800f0b6a  mov     rax, [rax+0B0h]
0x1800f0b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0b76  test    eax, eax
0x1800f0b78  js      short loc_1800F0BC7
0x1800f0b7a  cmp     [rsp+230h+var_1C0], 6
0x1800f0b7f  jnz     short loc_1800F0BC7
0x1800f0b81  mov     rax, [rsi]
0x1800f0b84  lea     r9, [rbp+130h+var_1B0]
0x1800f0b88  xor     r8d, r8d
0x1800f0b8b  xor     edx, edx
0x1800f0b8d  mov     rcx, rsi
0x1800f0b90  mov     rax, [rax+0A0h]
0x1800f0b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0b9c  test    eax, eax
0x1800f0b9e  js      short loc_1800F0BC7
0x1800f0ba0  mov     rcx, [rbp+130h+var_1B0]; unsigned __int16 *
0x1800f0ba4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f0ba8  inc     rdx
0x1800f0bab  cmp     [rcx+rdx*2], bx
0x1800f0baf  jnz     short loc_1800F0BA8
0x1800f0bb1  inc     edx; unsigned int
0x1800f0bb3  call    ?WrapSpecialUrlFlat@@YAJPEAGK@Z; WrapSpecialUrlFlat(ushort *,ulong)
0x1800f0bb8  mov     ebx, eax
0x1800f0bba  test    eax, eax
0x1800f0bbc  jns     short loc_1800F0BC7
0x1800f0bbe  mov     rcx, [rbp+130h+var_1B0]
0x1800f0bc2  jmp     loc_1800F10BB
0x1800f0bc7  mov     ebx, [rbp+130h+grfHLNF]
0x1800f0bcd  lea     rcx, IID_IHlinkFrame
0x1800f0bd4  test    r12, r12
0x1800f0bd7  jz      short loc_1800F0C06
0x1800f0bd9  lea     rax, [rsp+230h+pv]
0x1800f0bde  mov     [rsp+230h+lpDefaultChar], rax
0x1800f0be3  lea     r8, [rsp+230h+var_1D8]
0x1800f0be8  mov     qword ptr [rsp+230h+cbMultiByte], rcx
0x1800f0bed  lea     rdx, IID_IWebBrowserApp
0x1800f0bf4  mov     [rsp+230h+lpMultiByteStr], rcx
0x1800f0bf9  mov     rcx, r12
0x1800f0bfc  call    GetAnInterface
0x1800f0c01  mov     rdi, [rsp+230h+pv]
0x1800f0c06  mov     [rbp+130h+var_1A8], 0
0x1800f0c0e  call    ?LoadFunc@HLinkDll@@AEAAHPEBDAEAP6A_JXZ@Z; HLinkDll::LoadFunc(char const *,__int64 (*&)(void))
0x1800f0c13  xor     ecx, ecx
0x1800f0c15  test    eax, eax
0x1800f0c17  jz      loc_1800F0E78
0x1800f0c1d  lea     rax, [rbp+130h+var_1A8]
0x1800f0c21  xor     r9d, r9d
0x1800f0c24  mov     [rsp+230h+lpUsedDefaultChar], rax
0x1800f0c29  lea     r8, aThename; "TheName"
0x1800f0c30  lea     rax, IID_IHlink
0x1800f0c37  mov     rdx, r14
0x1800f0c3a  mov     [rsp+230h+lpDefaultChar], rax
0x1800f0c3f  mov     rax, cs:qword_18015C378
0x1800f0c46  mov     qword ptr [rsp+230h+cbMultiByte], rcx
0x1800f0c4b  mov     dword ptr [rsp+230h+lpMultiByteStr], ecx
0x1800f0c4f  mov     rcx, rsi
0x1800f0c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0c57  xor     r14d, r14d
0x1800f0c5a  test    eax, eax
0x1800f0c5c  js      loc_1800F0E7B
0x1800f0c62  test    rdi, rdi
0x1800f0c65  jz      loc_1800F0E7B
0x1800f0c6b  test    r15, r15
0x1800f0c6e  jz      short loc_1800F0CD4
0x1800f0c70  cmp     [r15], r14w
0x1800f0c74  jz      short loc_1800F0CD4
0x1800f0c76  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f0c7a  mov     rax, rdx
0x1800f0c7d  inc     rax
0x1800f0c80  cmp     [r15+rax*2], r14w
0x1800f0c85  jnz     short loc_1800F0C7D
0x1800f0c87  inc     eax
0x1800f0c89  mov     [rsp+230h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1800f0c8e  mov     ecx, 14h
0x1800f0c93  mov     [rsp+230h+lpDefaultChar], r14; lpDefaultChar
0x1800f0c98  cmp     eax, ecx
0x1800f0c9a  mov     r9d, edx; cchWideChar
0x1800f0c9d  mov     r8, r15; lpWideCharStr
0x1800f0ca0  cmovg   eax, ecx
0x1800f0ca3  xor     edx, edx; dwFlags
0x1800f0ca5  mov     [rsp+230h+cbMultiByte], eax; cbMultiByte
0x1800f0ca9  xor     ecx, ecx; CodePage
0x1800f0cab  lea     rax, [rbp+130h+MultiByteStr]
0x1800f0caf  mov     [rsp+230h+lpMultiByteStr], rax; lpMultiByteStr
0x1800f0cb4  call    cs:__imp_WideCharToMultiByte
0x1800f0cba  lea     rdx, aBlank; "_blank"
0x1800f0cc1  lea     rcx, [rbp+130h+MultiByteStr]; lpString1
0x1800f0cc5  call    ?StrCmpIIA@@YAHPEBD0@Z; StrCmpIIA(char const *,char const *)
0x1800f0cca  test    eax, eax
0x1800f0ccc  jnz     short loc_1800F0D42
0x1800f0cce  or      ebx, 80000002h
0x1800f0cd4  mov     edx, 2; dwFlags
0x1800f0cd9  lea     ecx, [rdx+0Ah]; FeatureEntry
0x1800f0cdc  call    CoInternetIsFeatureEnabled
0x1800f0ce1  mov     r14d, ebx
0x1800f0ce4  bts     r14d, 15h
0x1800f0ce9  cmp     eax, 1
0x1800f0cec  cmovz   r14d, ebx
0x1800f0cf0  test    r14b, 2
0x1800f0cf4  jz      short loc_1800F0D0E
0x1800f0cf6  mov     r8, r15
0x1800f0cf9  mov     rdx, rsi
0x1800f0cfc  mov     rcx, r12; punk
0x1800f0cff  call    QueryPopupManager
0x1800f0d04  mov     ebx, eax
0x1800f0d06  test    eax, eax
0x1800f0d08  js      loc_1800F1073
0x1800f0d0e  mov     rcx, [rbp+130h+var_1A8]
0x1800f0d12  mov     r8, r13
0x1800f0d15  mov     rax, [rdi]
0x1800f0d18  mov     edx, r14d
0x1800f0d1b  mov     r9, [rbp+130h+var_1A0]
0x1800f0d1f  mov     [rsp+230h+lpMultiByteStr], rcx
0x1800f0d24  mov     rcx, rdi
0x1800f0d27  mov     rax, [rax+28h]
0x1800f0d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0d30  xor     r14d, r14d
0x1800f0d33  mov     ebx, eax
0x1800f0d35  test    eax, eax
0x1800f0d37  jns     loc_1800F1073
0x1800f0d3d  jmp     loc_1800F0E80
0x1800f0d42  lea     rdx, IID_ITargetFrame
0x1800f0d49  mov     [rsp+230h+lpDefaultChar], r14
0x1800f0d4e  mov     qword ptr [rsp+230h+cbMultiByte], rdx
0x1800f0d53  lea     r8, [rsp+230h+var_1B8]
0x1800f0d58  mov     rcx, r12
0x1800f0d5b  mov     [rsp+230h+lpMultiByteStr], rdx
0x1800f0d60  call    GetAnInterface
0x1800f0d65  mov     rcx, r14
0x1800f0d68  mov     [rsp+230h+pv], rcx
0x1800f0d6d  test    eax, eax
0x1800f0d6f  js      short loc_1800F0D9D
0x1800f0d71  mov     rcx, [rsp+230h+var_1B8]
0x1800f0d76  lea     rdx, [rsp+230h+pv]
0x1800f0d7b  mov     [rsp+230h+lpMultiByteStr], rdx
0x1800f0d80  mov     r9d, 1
0x1800f0d86  mov     r8, rdi
0x1800f0d89  mov     rdx, r15
0x1800f0d8c  mov     rax, [rcx]
0x1800f0d8f  mov     rax, [rax+30h]
0x1800f0d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0d98  mov     rcx, [rsp+230h+pv]
0x1800f0d9d  mov     qword ptr [rsp+230h+pcchPath], r14
0x1800f0da2  test    rcx, rcx
0x1800f0da5  jz      short loc_1800F0E16
0x1800f0da7  mov     [rsp+230h+lpWideCharStr], r14
0x1800f0dac  lea     r8, [rsp+230h+lpWideCharStr]
0x1800f0db1  mov     rax, [rcx]
0x1800f0db4  lea     rdx, IID_IServiceProvider
0x1800f0dbb  mov     rax, [rax]
0x1800f0dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0dc3  mov     rcx, [rsp+230h+lpWideCharStr]
0x1800f0dc8  test    rcx, rcx
0x1800f0dcb  jz      short loc_1800F0DFD
0x1800f0dcd  mov     rax, [rcx]
0x1800f0dd0  lea     r9, [rsp+230h+pcchPath]
0x1800f0dd5  lea     r8, IID_IHlinkFrame
0x1800f0ddc  lea     rdx, IID_IWebBrowserApp
0x1800f0de3  mov     rax, [rax+18h]
0x1800f0de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0dec  mov     rcx, [rsp+230h+lpWideCharStr]
0x1800f0df1  mov     rax, [rcx]
0x1800f0df4  mov     rax, [rax+10h]
0x1800f0df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0dfd  mov     rdx, qword ptr [rsp+230h+pcchPath]; struct IHlinkFrame *
0x1800f0e02  mov     rcx, [rsp+230h+var_1B8]; struct ITargetFrame *
0x1800f0e07  call    ?AccessAllowed@@YAHPEAUITargetFrame@@PEAUIHlinkFrame@@@Z; AccessAllowed(ITargetFrame *,IHlinkFrame *)
0x1800f0e0c  mov     rcx, [rsp+230h+pv]
0x1800f0e11  mov     r14d, eax
0x1800f0e14  jmp     short loc_1800F0E22
0x1800f0e16  mov     r14d, 1
0x1800f0e1c  or      ebx, 80000002h
0x1800f0e22  test    rcx, rcx
0x1800f0e25  jz      short loc_1800F0E33
0x1800f0e27  mov     rax, [rcx]
0x1800f0e2a  mov     rax, [rax+10h]
0x1800f0e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e33  mov     rcx, [rsp+230h+var_1B8]
0x1800f0e38  test    rcx, rcx
0x1800f0e3b  jz      short loc_1800F0E49
0x1800f0e3d  mov     rax, [rcx]
0x1800f0e40  mov     rax, [rax+10h]
0x1800f0e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e49  cmp     qword ptr [rsp+230h+pcchPath], 0
0x1800f0e4f  jz      short loc_1800F0E65
0x1800f0e51  mov     rax, [rdi]
0x1800f0e54  mov     rcx, rdi
0x1800f0e57  mov     rax, [rax+10h]
0x1800f0e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e60  mov     rdi, qword ptr [rsp+230h+pcchPath]
0x1800f0e65  test    r14d, r14d
0x1800f0e68  jnz     loc_1800F0CD4
0x1800f0e6e  mov     ebx, 80070005h
0x1800f0e73  jmp     loc_1800F1073
0x1800f0e78  xor     r14d, r14d
0x1800f0e7b  mov     ebx, 80004005h
0x1800f0e80  test    rdi, rdi
0x1800f0e83  jz      short loc_1800F0EC2
0x1800f0e85  mov     rcx, [rsp+230h+var_1D8]
0x1800f0e8a  test    rcx, rcx
0x1800f0e8d  jz      short loc_1800F0EA0
0x1800f0e8f  mov     rax, [rcx]
0x1800f0e92  mov     rax, [rax+10h]
0x1800f0e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e9b  mov     [rsp+230h+var_1D8], r14
0x1800f0ea0  mov     rax, [rdi]
0x1800f0ea3  lea     r8, [rsp+230h+var_1D8]
0x1800f0ea8  lea     rdx, IID_IWebBrowserApp
0x1800f0eaf  mov     rcx, rdi
0x1800f0eb2  mov     rax, [rax]
0x1800f0eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0eba  test    ebx, ebx
0x1800f0ebc  jns     loc_1800F1073
0x1800f0ec2  mov     rcx, [rsp+230h+var_1D8]
0x1800f0ec7  test    rcx, rcx
0x1800f0eca  jz      short loc_1800F0F42
0x1800f0ecc  test    rsi, rsi
0x1800f0ecf  jz      short loc_1800F0F39
0x1800f0ed1  mov     rax, [rsi]
0x1800f0ed4  lea     r9, [rsp+230h+pv]
0x1800f0ed9  xor     r8d, r8d
0x1800f0edc  mov     [rsp+230h+pv], r14
0x1800f0ee1  mov     rdx, r13
0x1800f0ee4  mov     rcx, rsi
0x1800f0ee7  mov     rax, [rax+0A0h]
0x1800f0eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0ef3  mov     ebx, eax
0x1800f0ef5  test    eax, eax
0x1800f0ef7  js      short loc_1800F0F34
0x1800f0ef9  mov     rcx, [rsp+230h+var_1D8]
0x1800f0efe  xor     r9d, r9d
0x1800f0f01  mov     rdx, [rsp+230h+pv]
0x1800f0f06  xor     r8d, r8d
0x1800f0f09  mov     qword ptr [rsp+230h+cbMultiByte], r14
0x1800f0f0e  mov     [rsp+230h+lpMultiByteStr], r14
0x1800f0f13  mov     rax, [rcx]
0x1800f0f16  mov     rax, [rax+58h]
0x1800f0f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f1f  mov     rcx, [rsp+230h+pv]; pv
0x1800f0f24  mov     ebx, eax
0x1800f0f26  call    cs:__imp_CoTaskMemFree
0x1800f0f2c  test    ebx, ebx
0x1800f0f2e  jns     loc_1800F1073
0x1800f0f34  mov     rcx, [rsp+230h+var_1D8]
0x1800f0f39  test    rcx, rcx
0x1800f0f3c  jnz     loc_1800F107D
0x1800f0f42  test    rsi, rsi
0x1800f0f45  jz      loc_1800F1089
  ... truncated ...
```
