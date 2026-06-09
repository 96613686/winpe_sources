# CArchiveIDList::ExtractFromZipToFile(ushort const *,ulong,ushort const *,ushort const *,int,ulong,ushort const *,ZIPEXTRACTMODE,HWND__ *,int,int (*)(ushort const *,unsigned __int64,unsigned __int64,long,void *),void *)

- ea: `0x18001f284`
- end: `0x18001f67a`
- name: `?ExtractFromZipToFile@CArchiveIDList@@QEBAJPEBGK00HK0W4ZIPEXTRACTMODE@@PEAUHWND__@@HP6AH0_K3JPEAX@Z4@Z`
- size: `1014`
- prototype: `__int64 __fastcall(CArchiveIDList *, const unsigned __int16 *, int, __int64, const unsigned __int16 *pszPathIn, int, unsigned int, unsigned __int16 *, __int64, HWND hWnd, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `20`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ea30`
- `0x18001f204`
- `0x18002b0b0`

## callees

- `0x18000aa28`
- `0x18001495c`
- `0x18001f284`
- `0x180022ffc`
- `0x180023244`
- `0x180024944`
- `0x180024a24`
- `0x180025aac`
- `0x18002a664`
- `0x18002b4d4`
- `0x180036f50`
- `0x180037958`
- `0x18003ae64`
- `0x18003cfac`
- `0x18003edd4`
- `0x18003ee04`
- `0x18003ef3c`
- `0x18003f3a0`
- `0x18003f424`
- `0x180044e60`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001f47d`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18001f47d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f62d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f62d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f646`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f56f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f56f`

## pseudocode

```c
__int64 __fastcall CArchiveIDList::ExtractFromZipToFile(
        CArchiveIDList *a1,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        const unsigned __int16 *pszPathIn,
        int a6,
        unsigned int a7,
        unsigned __int16 *a8,
        __int64 a9,
        HWND hWnd,
        int a11,
        __int64 a12,
        __int64 a13)
{
  HWND v14; // rdx
  CArchiveIDList *v15; // rcx
  int EdpPolicyIfNeeded; // eax
  struct IShellItemArray *v17; // rbx
  int File; // edi
  char v19; // r15
  __int64 v20; // rcx
  __int64 v21; // r8
  const unsigned __int16 *v22; // r9
  int v23; // eax
  bool fuStyle; // [rsp+20h] [rbp-E0h]
  unsigned int fuStylea; // [rsp+20h] [rbp-E0h]
  int fuStyleb; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v28; // [rsp+30h] [rbp-D0h]
  char v29; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  CArchiveIDList *v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  PCWSTR pszMore[2]; // [rsp+80h] [rbp-80h] BYREF
  void **v36; // [rsp+90h] [rbp-70h] BYREF
  int v37; // [rsp+98h] [rbp-68h] BYREF
  char v38; // [rsp+9Ch] [rbp-64h]
  int v39; // [rsp+C0h] [rbp-40h] BYREF
  const char *v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  char v42; // [rsp+D8h] [rbp-28h]
  int v43; // [rsp+E0h] [rbp-20h]
  _BYTE v44[152]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v45; // [rsp+180h] [rbp+80h]
  int v46; // [rsp+190h] [rbp+90h]
  __int64 v47; // [rsp+198h] [rbp+98h]
  int *v48; // [rsp+1A0h] [rbp+A0h]
  __int64 v49; // [rsp+1A8h] [rbp+A8h]
  __int64 v50; // [rsp+1B0h] [rbp+B0h]
  void ***v51; // [rsp+1B8h] [rbp+B8h]
  __int64 v52; // [rsp+1C0h] [rbp+C0h]
  int v53; // [rsp+1C8h] [rbp+C8h]
  int *v54; // [rsp+1D0h] [rbp+D0h]
  char v55; // [rsp+1D8h] [rbp+D8h]
  struct HWND__ pszPathOut[132]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  v33 = a12;
  v32 = a13;
  LODWORD(pszMore[0]) = a3;
  v31 = a1;
  v40 = "ZipExtract";
  v34 = a4;
  v37 = 0;
  v38 = 0;
  v42 = 0;
  v39 = 0;
  v41 = 0;
  v43 = 0;
  v45 = 0;
  memset_0(v44, 0, sizeof(v44));
  v46 = 1;
  v47 = 0;
  v49 = 0;
  v48 = &v37;
  v51 = &v36;
  v54 = &v39;
  v36 = &FileExplorerTelemetry::ZipExtract::`vftable';
  v50 = 0;
  v52 = 0;
  v53 = 0;
  v55 = 0;
  FileExplorerTelemetry::ZipExtract::StartActivity((FileExplorerTelemetry::ZipExtract *)&v36);
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  EdpPolicyIfNeeded = CArchiveIDList::EvaluateExtractEdpPolicyIfNeeded(
                        v15,
                        v14,
                        a2,
                        pszPathIn,
                        fuStyle,
                        a7,
                        v28,
                        (unsigned __int16 **)&pv);
  v17 = (struct IShellItemArray *)pv;
  File = EdpPolicyIfNeeded;
  if ( EdpPolicyIfNeeded < 0 )
    goto LABEL_34;
  v19 = 0;
  v29 = 0;
  fuStylea = (unsigned int)pszPathIn;
  File = DZ_ExtractFile(hWnd, a2, LODWORD(pszMore[0]), v34);
  if ( File != 1 )
    goto LABEL_19;
  while ( 1 )
  {
    if ( !v29 )
    {
      _ReadPersistedPassword(a2);
      v29 = 1;
      goto LABEL_12;
    }
    if ( !hWnd )
      break;
    if ( v19 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
        MessageBoxHelper::ShellMessageBoxTextScaled__(v20, hWnd, v21);
      else
        ShellMessageBoxW(g_hmodThisDll, hWnd, (LPCWSTR)0x27CD, (LPCWSTR)0x2747, 0x30u);
    }
    File = CPassword::GetDecryptPassword((CPassword *)&g_password, hWnd, (const unsigned __int16 *)v31 + 46);
    if ( File )
      goto LABEL_15;
    v19 = 1;
LABEL_12:
    fuStylea = (unsigned int)pszPathIn;
    File = DZ_ExtractFile(hWnd, a2, LODWORD(pszMore[0]), v34);
    if ( File != 1 )
      goto LABEL_15;
  }
  File = -2147467259;
LABEL_15:
  if ( !v19 )
  {
LABEL_19:
    if ( File >= 0 )
      goto LABEL_20;
    goto LABEL_34;
  }
  if ( File >= 0 )
  {
    if ( word_18008BAB8 )
      _PersistPassword(a2);
LABEL_20:
    if ( v17 )
    {
      pszMore[0] = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        pszMore,
        0);
      if ( CArchiveIDList::GetFinalRelPathAfterExtract(v31, a6 != 0, a8, (unsigned __int16 **)pszMore) >= 0
        && PathCchCombine((PWSTR)pszPathOut, 0x104u, pszPathIn, pszMore[0]) >= 0
        && !(unsigned __int8)EdpIsExcludedPath(pszPathOut)
        && !(unsigned __int8)EdpIsExcludedExtension(pszPathOut) )
      {
        v23 = EdpHelpers::ProtectFilePathWithFileOperation(0, pszPathOut, v17, v22, fuStylea);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x126,
            (unsigned int)"shell\\ext\\zip\\arcentry.cpp",
            (const char *)(unsigned int)v23,
            fuStyleb);
      }
      if ( pszMore[0] )
        CoTaskMemFree((LPVOID)pszMore[0]);
    }
    if ( a11 )
    {
      pszMore[0] = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        pszMore,
        0);
      File = CArchiveIDList::GetFinalRelPathAfterExtract(v31, a6 != 0, a8, (unsigned __int16 **)pszMore);
      if ( File >= 0 )
        File = CheckUnZippedFile(hWnd, a2, pszPathIn, pszMore[0]);
      if ( pszMore[0] )
        CoTaskMemFree((LPVOID)pszMore[0]);
    }
  }
LABEL_34:
  wil::ActivityBase<FileExplorerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v36, (unsigned int)File);
  if ( v17 )
    CoTaskMemFree(v17);
  FileExplorerTelemetry::ZipExtract::~ZipExtract((FileExplorerTelemetry::ZipExtract *)&v36);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x18001f284  push    rbp
0x18001f286  push    rbx
0x18001f287  push    rsi
0x18001f288  push    rdi
0x18001f289  push    r12
0x18001f28b  push    r13
0x18001f28d  push    r14
0x18001f28f  push    r15
0x18001f291  lea     rbp, [rsp-308h]
0x18001f299  sub     rsp, 408h
0x18001f2a0  mov     rax, cs:__security_cookie
0x18001f2a7  xor     rax, rsp
0x18001f2aa  mov     [rbp+340h+var_50], rax
0x18001f2b1  mov     rax, [rbp+340h+arg_58]
0x18001f2b8  xor     ebx, ebx
0x18001f2ba  mov     r12, [rbp+340h+pszPathIn]
0x18001f2c1  mov     r14, rdx
0x18001f2c4  mov     r13, [rbp+340h+arg_38]
0x18001f2cb  xorps   xmm0, xmm0
0x18001f2ce  mov     rsi, [rbp+340h+hWnd]
0x18001f2d5  xor     edx, edx; Val
0x18001f2d7  mov     [rsp+440h+var_3D0], rax
0x18001f2dc  mov     rax, [rbp+340h+arg_60]
0x18001f2e3  mov     [rsp+440h+var_3D8], rax
0x18001f2e8  lea     rax, aZipextract; "ZipExtract"
0x18001f2ef  mov     dword ptr [rbp+340h+pszMore], r8d
0x18001f2f3  mov     r8d, 98h; Size
0x18001f2f9  mov     [rsp+440h+var_3E0], rcx
0x18001f2fe  lea     rcx, [rbp+340h+var_358]; void *
0x18001f302  mov     [rbp+340h+var_378], rax
0x18001f306  mov     [rsp+440h+var_3C8], r9
0x18001f30b  mov     [rbp+340h+var_3A8], ebx
0x18001f30e  mov     [rbp+340h+var_3A4], bl
0x18001f311  mov     [rbp+340h+var_368], bl
0x18001f314  mov     [rbp+340h+var_380], ebx
0x18001f317  mov     [rbp+340h+var_370], rbx
0x18001f31b  mov     [rbp+340h+var_360], ebx
0x18001f31e  movdqa  [rbp+340h+var_2C0], xmm0
0x18001f326  call    memset_0
0x18001f32b  xor     eax, eax
0x18001f32d  mov     [rbp+340h+var_2B0], 1
0x18001f337  mov     [rbp+340h+var_2A8], rax
0x18001f33e  lea     rcx, [rbp+340h+var_3B0]; this
0x18001f342  lea     rax, [rbp+340h+var_3A8]
0x18001f346  mov     [rbp+340h+var_298], rbx
0x18001f34d  mov     [rbp+340h+var_2A0], rax
0x18001f354  lea     rax, [rbp+340h+var_3B0]
0x18001f358  mov     [rbp+340h+var_288], rax
0x18001f35f  lea     rax, [rbp+340h+var_380]
0x18001f363  mov     [rbp+340h+var_270], rax
0x18001f36a  lea     rax, ??_7ZipExtract@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::ZipExtract::`vftable'
0x18001f371  mov     [rbp+340h+var_3B0], rax
0x18001f375  mov     [rbp+340h+var_290], rbx
0x18001f37c  mov     [rbp+340h+var_280], rbx
0x18001f383  mov     [rbp+340h+var_278], ebx
0x18001f389  mov     [rbp+340h+var_268], bl
0x18001f38f  call    ?StartActivity@ZipExtract@FileExplorerTelemetry@@QEAAXXZ; FileExplorerTelemetry::ZipExtract::StartActivity(void)
0x18001f394  xor     edx, edx
0x18001f396  mov     [rsp+440h+pv], rbx
0x18001f39b  lea     rcx, [rsp+440h+pv]
0x18001f3a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f3a5  lea     rax, [rsp+440h+pv]
0x18001f3aa  mov     r9, r12; unsigned __int16 *
0x18001f3ad  mov     [rsp+440h+var_408], rax; unsigned __int16 **
0x18001f3b2  mov     r8, r14; unsigned __int16 *
0x18001f3b5  mov     eax, [rbp+340h+arg_30]
0x18001f3bb  mov     [rsp+440h+var_418], eax; unsigned int
0x18001f3bf  call    ?EvaluateExtractEdpPolicyIfNeeded@CArchiveIDList@@AEBAJPEAUHWND__@@PEBG1_NK1PEAPEAG@Z; CArchiveIDList::EvaluateExtractEdpPolicyIfNeeded(HWND__ *,ushort const *,ushort const *,bool,ulong,ushort const *,ushort * *)
0x18001f3c4  mov     rbx, [rsp+440h+pv]
0x18001f3c9  mov     edi, eax
0x18001f3cb  xor     eax, eax
0x18001f3cd  test    edi, edi
0x18001f3cf  js      loc_18001F633
0x18001f3d5  mov     r9, [rsp+440h+var_3C8]
0x18001f3da  mov     r15b, al
0x18001f3dd  mov     r8d, dword ptr [rbp+340h+pszMore]
0x18001f3e1  mov     rdx, r14
0x18001f3e4  mov     [rsp+440h+var_3F0], al
0x18001f3e8  mov     rcx, rsi
0x18001f3eb  mov     rax, [rsp+440h+var_3D8]
0x18001f3f0  mov     [rsp+440h+var_400], rax
0x18001f3f5  mov     rax, [rsp+440h+var_3D0]
0x18001f3fa  mov     [rsp+440h+var_408], rax
0x18001f3ff  mov     eax, [rbp+340h+arg_40]
0x18001f405  mov     dword ptr [rsp+440h+var_410], eax
0x18001f409  mov     qword ptr [rsp+440h+var_418], r13
0x18001f40e  mov     qword ptr [rsp+440h+fuStyle], r12; int
0x18001f413  call    ?DZ_ExtractFile@@YAJPEAUHWND__@@PEBGK111W4ZIPEXTRACTMODE@@P6AH1_K3JPEAX@Z4@Z; DZ_ExtractFile(HWND__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ZIPEXTRACTMODE,int (*)(ushort const *,unsigned __int64,unsigned __int64,long,void *),void *)
0x18001f418  mov     edi, eax
0x18001f41a  cmp     eax, 1
0x18001f41d  jnz     loc_18001F518
0x18001f423  xor     eax, eax
0x18001f425  cmp     [rsp+440h+var_3F0], al
0x18001f429  jnz     short loc_18001F43A
0x18001f42b  mov     rcx, r14; unsigned __int16 *
0x18001f42e  call    ?_ReadPersistedPassword@@YAXPEBG@Z; _ReadPersistedPassword(ushort const *)
0x18001f433  mov     [rsp+440h+var_3F0], 1
0x18001f438  jmp     short loc_18001F4A6
0x18001f43a  test    rsi, rsi
0x18001f43d  jz      loc_18001F4F1
0x18001f443  test    r15b, r15b
0x18001f446  jz      short loc_18001F483
0x18001f448  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18001f44f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18001f454  mov     rdx, rsi; hWnd
0x18001f457  test    al, al
0x18001f459  jz      short loc_18001F462
0x18001f45b  call    MessageBoxHelper__ShellMessageBoxTextScaled__
0x18001f460  jmp     short loc_18001F483
0x18001f462  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18001f469  mov     r9d, 2747h; lpcTitle
0x18001f46f  mov     r8d, 27CDh; lpcText
0x18001f475  mov     [rsp+440h+fuStyle], 30h ; '0'; fuStyle
0x18001f47d  call    cs:__imp_ShellMessageBoxW
0x18001f483  mov     r8, [rsp+440h+var_3E0]
0x18001f488  lea     rcx, ?g_password@@3VCPassword@@A; this
0x18001f48f  add     r8, 5Ch ; '\'; unsigned __int16 *
0x18001f493  mov     rdx, rsi; HWND
0x18001f496  call    ?GetDecryptPassword@CPassword@@QEAAJPEAUHWND__@@PEFBG@Z; CPassword::GetDecryptPassword(HWND__ *,ushort const *)
0x18001f49b  mov     edi, eax
0x18001f49d  xor     eax, eax
0x18001f49f  test    edi, edi
0x18001f4a1  jnz     short loc_18001F4F6
0x18001f4a3  mov     r15b, 1
0x18001f4a6  mov     rax, [rsp+440h+var_3D8]
0x18001f4ab  mov     rdx, r14
0x18001f4ae  mov     r9, [rsp+440h+var_3C8]
0x18001f4b3  mov     rcx, rsi
0x18001f4b6  mov     r8d, dword ptr [rbp+340h+pszMore]
0x18001f4ba  mov     [rsp+440h+var_400], rax
0x18001f4bf  mov     rax, [rsp+440h+var_3D0]
0x18001f4c4  mov     [rsp+440h+var_408], rax
0x18001f4c9  mov     eax, [rbp+340h+arg_40]
0x18001f4cf  mov     dword ptr [rsp+440h+var_410], eax
0x18001f4d3  mov     qword ptr [rsp+440h+var_418], r13
0x18001f4d8  mov     qword ptr [rsp+440h+fuStyle], r12
0x18001f4dd  call    ?DZ_ExtractFile@@YAJPEAUHWND__@@PEBGK111W4ZIPEXTRACTMODE@@P6AH1_K3JPEAX@Z4@Z; DZ_ExtractFile(HWND__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ZIPEXTRACTMODE,int (*)(ushort const *,unsigned __int64,unsigned __int64,long,void *),void *)
0x18001f4e2  mov     edi, eax
0x18001f4e4  cmp     eax, 1
0x18001f4e7  jz      loc_18001F423
0x18001f4ed  xor     eax, eax
0x18001f4ef  jmp     short loc_18001F4F6
0x18001f4f1  mov     edi, 80004005h
0x18001f4f6  test    r15b, r15b
0x18001f4f9  jz      short loc_18001F51A
0x18001f4fb  test    edi, edi
0x18001f4fd  js      loc_18001F633
0x18001f503  cmp     cs:word_18008BAB8, ax
0x18001f50a  jz      short loc_18001F522
0x18001f50c  mov     rcx, r14; unsigned __int16 *
0x18001f50f  call    ?_PersistPassword@@YAJPEBG@Z; _PersistPassword(ushort const *)
0x18001f514  xor     eax, eax
0x18001f516  jmp     short loc_18001F522
0x18001f518  xor     eax, eax
0x18001f51a  test    edi, edi
0x18001f51c  js      loc_18001F633
0x18001f522  mov     r15d, [rbp+340h+arg_28]
0x18001f529  test    rbx, rbx
0x18001f52c  jz      loc_18001F5DC
0x18001f532  xor     edx, edx
0x18001f534  mov     [rbp+340h+pszMore], rax
0x18001f538  lea     rcx, [rbp+340h+pszMore]
0x18001f53c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f541  mov     rcx, [rsp+440h+var_3E0]; this
0x18001f546  lea     r9, [rbp+340h+pszMore]; unsigned __int16 **
0x18001f54a  test    r15d, r15d
0x18001f54d  mov     r8, r13; unsigned __int16 *
0x18001f550  setnz   dl; bool
0x18001f553  call    ?GetFinalRelPathAfterExtract@CArchiveIDList@@AEBAJ_NPEBGPEAPEAG@Z; CArchiveIDList::GetFinalRelPathAfterExtract(bool,ushort const *,ushort * *)
0x18001f558  test    eax, eax
0x18001f55a  js      short loc_18001F5C9
0x18001f55c  mov     r9, [rbp+340h+pszMore]; pszMore
0x18001f560  lea     rcx, [rbp+340h+pszPathOut]; pszPathOut
0x18001f567  mov     r8, r12; pszPathIn
0x18001f56a  mov     edx, 104h; cchPathOut
0x18001f56f  call    cs:__imp_PathCchCombine
0x18001f575  test    eax, eax
0x18001f577  js      short loc_18001F5C9
0x18001f579  lea     rcx, [rbp+340h+pszPathOut]
0x18001f580  call    _EdpIsExcludedPath
0x18001f585  test    al, al
0x18001f587  jnz     short loc_18001F5C9
0x18001f589  lea     rcx, [rbp+340h+pszPathOut]
0x18001f590  call    _EdpIsExcludedExtension
0x18001f595  test    al, al
0x18001f597  jnz     short loc_18001F5C9
0x18001f599  mov     r8, rbx; struct IShellItemArray *
0x18001f59c  lea     rdx, [rbp+340h+pszPathOut]; pszPath
0x18001f5a3  xor     ecx, ecx; this
0x18001f5a5  call    ?ProtectFilePathWithFileOperation@EdpHelpers@@YAJPEAUHWND__@@PEBG1K@Z; EdpHelpers::ProtectFilePathWithFileOperation(HWND__ *,ushort const *,ushort const *,ulong)
0x18001f5aa  test    eax, eax
0x18001f5ac  jns     short loc_18001F5C9
0x18001f5ae  mov     rcx, [rbp+348h]; this
0x18001f5b5  lea     r8, aShellExtZipArc_2; "shell\\ext\\zip\\arcentry.cpp"
0x18001f5bc  mov     r9d, eax; char *
0x18001f5bf  mov     edx, 126h; void *
0x18001f5c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f5c9  mov     rcx, [rbp+340h+pszMore]; pv
0x18001f5cd  xor     eax, eax
0x18001f5cf  test    rcx, rcx
0x18001f5d2  jz      short loc_18001F5DC
0x18001f5d4  call    cs:__imp_CoTaskMemFree
0x18001f5da  xor     eax, eax
0x18001f5dc  cmp     [rbp+340h+arg_50], eax
0x18001f5e2  jz      short loc_18001F633
0x18001f5e4  xor     edx, edx
0x18001f5e6  mov     [rbp+340h+pszMore], rax
0x18001f5ea  lea     rcx, [rbp+340h+pszMore]
0x18001f5ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f5f3  mov     rcx, [rsp+440h+var_3E0]; this
0x18001f5f8  lea     r9, [rbp+340h+pszMore]; unsigned __int16 **
0x18001f5fc  test    r15d, r15d
0x18001f5ff  mov     r8, r13; unsigned __int16 *
0x18001f602  setnz   dl; bool
0x18001f605  call    ?GetFinalRelPathAfterExtract@CArchiveIDList@@AEBAJ_NPEBGPEAPEAG@Z; CArchiveIDList::GetFinalRelPathAfterExtract(bool,ushort const *,ushort * *)
0x18001f60a  mov     edi, eax
0x18001f60c  test    eax, eax
0x18001f60e  js      short loc_18001F624
0x18001f610  mov     r9, [rbp+340h+pszMore]; unsigned __int16 *
0x18001f614  mov     r8, r12; unsigned __int16 *
0x18001f617  mov     rdx, r14; unsigned __int16 *
0x18001f61a  mov     rcx, rsi; HWND
0x18001f61d  call    ?CheckUnZippedFile@@YAJPEAUHWND__@@PEBG11@Z; CheckUnZippedFile(HWND__ *,ushort const *,ushort const *,ushort const *)
0x18001f622  mov     edi, eax
0x18001f624  mov     rcx, [rbp+340h+pszMore]; pv
0x18001f628  test    rcx, rcx
0x18001f62b  jz      short loc_18001F633
0x18001f62d  call    cs:__imp_CoTaskMemFree
0x18001f633  mov     edx, edi
0x18001f635  lea     rcx, [rbp+340h+var_3B0]
0x18001f639  call    ?Stop@?$ActivityBase@VFileExplorerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FileExplorerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001f63e  test    rbx, rbx
0x18001f641  jz      short loc_18001F64C
0x18001f643  mov     rcx, rbx; pv
0x18001f646  call    cs:__imp_CoTaskMemFree
0x18001f64c  lea     rcx, [rbp+340h+var_3B0]; this
0x18001f650  call    ??1ZipExtract@FileExplorerTelemetry@@QEAA@XZ; FileExplorerTelemetry::ZipExtract::~ZipExtract(void)
0x18001f655  mov     eax, edi
0x18001f657  mov     rcx, [rbp+340h+var_50]
0x18001f65e  xor     rcx, rsp; StackCookie
0x18001f661  call    __security_check_cookie
0x18001f666  add     rsp, 408h
0x18001f66d  pop     r15
0x18001f66f  pop     r14
0x18001f671  pop     r13
0x18001f673  pop     r12
0x18001f675  pop     rdi
0x18001f676  pop     rsi
0x18001f677  pop     rbx
0x18001f678  pop     rbp
0x18001f679  retn
```
