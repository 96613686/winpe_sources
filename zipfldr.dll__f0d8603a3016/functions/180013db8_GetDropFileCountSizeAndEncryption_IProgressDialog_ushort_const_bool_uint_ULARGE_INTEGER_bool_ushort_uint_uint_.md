# GetDropFileCountSizeAndEncryption(IProgressDialog *,ushort const *,bool,uint *,_ULARGE_INTEGER *,bool *,ushort *,uint,uint *,ushort *,uint,ushort * *)

- ea: `0x180013db8`
- end: `0x1800142a1`
- name: `?GetDropFileCountSizeAndEncryption@@YAJPEAUIProgressDialog@@PEBG_NPEAIPEAT_ULARGE_INTEGER@@PEA_NPEAGI36IPEAPEAG@Z`
- size: `1257`
- prototype: `__int64 __fastcall(struct IProgressDialog *, const unsigned __int16 *, bool, unsigned int *, union _ULARGE_INTEGER *, bool *, unsigned __int16 *, unsigned int, unsigned int *, unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b430`
- `0x180013db8`

## callees

- `0x180010c30`
- `0x180013db8`
- `0x1800142a8`
- `0x180036f50`
- `0x180037958`
- `0x18003edd4`
- `0x180041050`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014077`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014077`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014130`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180013f2d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180013f72`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180013f2d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180013f72`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013e50`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013f42`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013e50`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013f42`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001405e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001405e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013ee5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180014272`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013ee5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180014272`
- `ntdll!RtlIsPartialPlaceholder` at `0x180013ec1`
- `ntdll!RtlIsPartialPlaceholder` at `0x180013f93`
- `ntdll!RtlIsPartialPlaceholder` at `0x180013ec1`
- `ntdll!RtlIsPartialPlaceholder` at `0x180013f93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDropFileCountSizeAndEncryption(
        struct IProgressDialog *a1,
        const unsigned __int16 *a2,
        bool a3,
        unsigned int *a4,
        union _ULARGE_INTEGER *a5,
        bool *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned int *a9,
        unsigned __int16 *a10,
        unsigned int a11,
        unsigned __int16 **a12)
{
  HRESULT DropFileCountSizeAndEncryption; // edi
  int v16; // eax
  void *v17; // r10
  unsigned __int64 v18; // r11
  void *v19; // rbx
  HANDLE FirstFileW; // rsi
  DWORD nFileSizeLow; // eax
  DWORD dwFileAttributes; // edx
  int v24; // eax
  __int16 v25; // r11
  void *v26; // r10
  unsigned __int16 *v27; // rcx
  int v28; // eax
  unsigned __int16 *v29; // rcx
  HRESULT v30; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  bool v32; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  struct IProgressDialog *v34; // [rsp+70h] [rbp-90h]
  union _ULARGE_INTEGER v35; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v36; // [rsp+80h] [rbp-80h]
  unsigned __int16 **v37; // [rsp+88h] [rbp-78h]
  bool *v38; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v39; // [rsp+98h] [rbp-68h]
  HANDLE hFindFile; // [rsp+A0h] [rbp-60h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR pszPathOut[264]; // [rsp+510h] [rbp+410h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+678h]

  v38 = a6;
  v36 = a10;
  v37 = a12;
  v34 = a1;
  DropFileCountSizeAndEncryption = 0;
  a5->QuadPart = 0;
  *a4 = 0;
  v39 = a7;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hFindFile = FindFirstFileW(a2, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
    return (unsigned int)DropFileCountSizeAndEncryption;
  v32 = 0;
  pv = 0;
  v16 = CheckFileEncryption(a2, FindFileData.dwFileAttributes, &v32, (unsigned __int16 **)&pv);
  v17 = 0;
  v18 = 260;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x607,
      (unsigned int)"shell\\ext\\zip\\dropin.cpp",
      (const char *)(unsigned int)v16,
      v31);
    v19 = pv;
    v18 = 260;
  }
  else
  {
    if ( v32 && !*a9 )
    {
      v28 = StringCchCopyW(a7, 0x104u, FindFileData.cFileName);
      ++*a9;
      DropFileCountSizeAndEncryption = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x612,
          (unsigned int)"shell\\ext\\zip\\dropin.cpp",
          (const char *)(unsigned int)v28,
          v31);
        v19 = pv;
LABEL_43:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x619,
          (unsigned int)"shell\\ext\\zip\\dropin.cpp",
          (const char *)(unsigned int)DropFileCountSizeAndEncryption,
          v31);
        goto LABEL_11;
      }
    }
    v19 = pv;
    if ( pv )
    {
      v29 = v36;
      if ( *v36 == (_WORD)v17 )
      {
        v19 = v17;
        *v37 = (unsigned __int16 *)pv;
        DropFileCountSizeAndEncryption = StringCchCopyW(v29, v18, a2);
      }
    }
    if ( DropFileCountSizeAndEncryption < 0 )
      goto LABEL_43;
  }
  if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
  {
    if ( (unsigned __int8)RtlIsPartialPlaceholder(FindFileData.dwFileAttributes, FindFileData.dwReserved0) )
      DropFileCountSizeAndEncryption = DownloadPlaceholderFile(v34, a2, &FindFileData, a3, v38);
    ++*a4;
    a5->LowPart = FindFileData.nFileSizeLow;
    a5->HighPart = FindFileData.nFileSizeHigh;
    goto LABEL_10;
  }
  if ( PathCchCombine(pszPathOut, v18, a2, L"*.*") < 0 )
    goto LABEL_10;
  FirstFileW = FindFirstFileW(pszPathOut, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_10;
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || !FindFileData.cFileName[2] && FindFileData.cFileName[1] == 46) )
    {
      goto LABEL_29;
    }
    DropFileCountSizeAndEncryption = PathCchCombine(FileName, 0x104u, a2, FindFileData.cFileName);
    if ( DropFileCountSizeAndEncryption < 0 )
      goto LABEL_51;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      if ( (unsigned __int8)RtlIsPartialPlaceholder(FindFileData.dwFileAttributes, FindFileData.dwReserved0) )
        DropFileCountSizeAndEncryption = DownloadPlaceholderFile(v34, FileName, &FindFileData, 0, v38);
      nFileSizeLow = FindFileData.nFileSizeLow;
      ++*a4;
      dwFileAttributes = FindFileData.dwFileAttributes;
      a5->LowPart = nFileSizeLow;
      a5->HighPart = FindFileData.nFileSizeHigh;
      v32 = 0;
      pv = 0;
      v24 = CheckFileEncryption(FileName, dwFileAttributes, &v32, (unsigned __int16 **)&pv);
      v25 = 0;
      if ( v24 >= 0 )
      {
        if ( v32 && !*a9 )
        {
          v30 = StringCchCopyW(v39, 0x104u, FindFileData.cFileName);
          ++*a9;
          DropFileCountSizeAndEncryption = v30;
        }
        if ( DropFileCountSizeAndEncryption >= 0 )
        {
          v26 = pv;
          if ( !pv )
            goto LABEL_30;
          v27 = v36;
          if ( *v36 == v25 )
          {
            *v37 = (unsigned __int16 *)pv;
            DropFileCountSizeAndEncryption = StringCchCopyW(v27, 0x104u, FileName);
          }
          goto LABEL_27;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x65B,
          (unsigned int)"shell\\ext\\zip\\dropin.cpp",
          (const char *)(unsigned int)DropFileCountSizeAndEncryption,
          v31);
      }
      v26 = pv;
LABEL_27:
      if ( v26 )
        CoTaskMemFree(v26);
LABEL_29:
      if ( DropFileCountSizeAndEncryption < 0 )
        goto LABEL_51;
      goto LABEL_30;
    }
    LODWORD(pv) = 0;
    v35.QuadPart = 0;
    DropFileCountSizeAndEncryption = GetDropFileCountSizeAndEncryption(
                                       v34,
                                       FileName,
                                       0,
                                       (unsigned int *)&pv,
                                       &v35,
                                       v38,
                                       v39,
                                       0x104u,
                                       a9,
                                       v36,
                                       0x104u,
                                       v37);
    if ( DropFileCountSizeAndEncryption < 0 )
      goto LABEL_51;
    *a4 += (unsigned int)pv;
    a5->QuadPart += v35.QuadPart;
LABEL_30:
    if ( ((unsigned int (__fastcall *)(struct IProgressDialog *))v34->lpVtbl->SetLine)(v34) )
      break;
    DropFileCountSizeAndEncryption = 0;
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_51;
  }
  DropFileCountSizeAndEncryption = -2147023673;
LABEL_51:
  FindClose(FirstFileW);
LABEL_10:
  FindClose(hFindFile);
LABEL_11:
  if ( v19 )
    CoTaskMemFree(v19);
  return (unsigned int)DropFileCountSizeAndEncryption;
}

```

## disassembly

```asm
0x180013db8  push    rbp
0x180013dba  push    rbx
0x180013dbb  push    rsi
0x180013dbc  push    rdi
0x180013dbd  push    r12
0x180013dbf  push    r13
0x180013dc1  push    r14
0x180013dc3  push    r15
0x180013dc5  lea     rbp, [rsp-638h]
0x180013dcd  sub     rsp, 738h
0x180013dd4  mov     rax, cs:__security_cookie
0x180013ddb  xor     rax, rsp
0x180013dde  mov     [rbp+670h+var_50], rax
0x180013de5  mov     rax, [rbp+670h+arg_28]
0x180013dec  mov     sil, r8b
0x180013def  mov     r12, [rbp+670h+arg_20]
0x180013df6  mov     r13, rdx
0x180013df9  mov     rbx, [rbp+670h+arg_30]
0x180013e00  xor     edx, edx; Val
0x180013e02  mov     r14, [rbp+670h+arg_40]
0x180013e09  mov     r8d, 250h; Size
0x180013e0f  mov     [rbp+670h+var_6E0], rax
0x180013e13  mov     r15, r9
0x180013e16  mov     rax, [rbp+670h+arg_48]
0x180013e1d  mov     [rbp+670h+var_6F0], rax
0x180013e21  mov     rax, [rbp+670h+arg_58]
0x180013e28  mov     [rbp+670h+var_6E8], rax
0x180013e2c  xor     eax, eax
0x180013e2e  mov     [rsp+770h+var_700], rcx
0x180013e33  mov     edi, eax
0x180013e35  mov     [r12], rax
0x180013e39  lea     rcx, [rbp+670h+FindFileData]; void *
0x180013e3d  mov     [r9], eax
0x180013e40  mov     [rbp+670h+var_6D8], rbx
0x180013e44  call    memset_0
0x180013e49  lea     rdx, [rbp+670h+FindFileData]; lpFindFileData
0x180013e4d  mov     rcx, r13; lpFileName
0x180013e50  call    cs:__imp_FindFirstFileW
0x180013e56  mov     [rbp+670h+hFindFile], rax
0x180013e5a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013e5e  jz      loc_180013EF4
0x180013e64  mov     edx, [rbp+670h+FindFileData.dwFileAttributes]; unsigned int
0x180013e67  lea     r9, [rsp+770h+pv]; unsigned __int16 **
0x180013e6c  xor     eax, eax
0x180013e6e  lea     r8, [rsp+770h+var_710]; bool *
0x180013e73  mov     rcx, r13; pszPath
0x180013e76  mov     [rsp+770h+var_710], al
0x180013e7a  mov     [rsp+770h+pv], rax
0x180013e7f  call    ?CheckFileEncryption@@YAJPEBGKPEA_NPEAPEAG@Z; CheckFileEncryption(ushort const *,ulong,bool *,ushort * *)
0x180013e84  xor     r10d, r10d
0x180013e87  mov     r11d, 104h
0x180013e8d  test    eax, eax
0x180013e8f  js      loc_18001413B
0x180013e95  cmp     [rsp+770h+var_710], r10b
0x180013e9a  jnz     loc_180014166
0x180013ea0  mov     rbx, [rsp+770h+pv]
0x180013ea5  test    rbx, rbx
0x180013ea8  jnz     loc_1800141CB
0x180013eae  test    edi, edi
0x180013eb0  js      loc_1800141AB
0x180013eb6  mov     ecx, [rbp+670h+FindFileData.dwFileAttributes]
0x180013eb9  test    cl, 10h
0x180013ebc  jnz     short loc_180013F19
0x180013ebe  mov     edx, [rbp+670h+FindFileData.dwReserved0]
0x180013ec1  call    cs:__imp_RtlIsPartialPlaceholder
0x180013ec7  test    al, al
0x180013ec9  jnz     loc_18001427D
0x180013ecf  inc     dword ptr [r15]
0x180013ed2  mov     eax, [rbp+670h+FindFileData.nFileSizeLow]
0x180013ed5  mov     [r12], eax
0x180013ed9  mov     eax, [rbp+670h+FindFileData.nFileSizeHigh]
0x180013edc  mov     [r12+4], eax
0x180013ee1  mov     rcx, [rbp+670h+hFindFile]; hFindFile
0x180013ee5  call    cs:__imp_FindClose
0x180013eeb  test    rbx, rbx
0x180013eee  jnz     loc_180014074
0x180013ef4  mov     eax, edi
0x180013ef6  mov     rcx, [rbp+670h+var_50]
0x180013efd  xor     rcx, rsp; StackCookie
0x180013f00  call    __security_check_cookie
0x180013f05  add     rsp, 738h
0x180013f0c  pop     r15
0x180013f0e  pop     r14
0x180013f10  pop     r13
0x180013f12  pop     r12
0x180013f14  pop     rdi
0x180013f15  pop     rsi
0x180013f16  pop     rbx
0x180013f17  pop     rbp
0x180013f18  retn
0x180013f19  lea     r9, pszMore; "*.*"
0x180013f20  mov     r8, r13; pszPathIn
0x180013f23  mov     rdx, r11; cchPathOut
0x180013f26  lea     rcx, [rbp+670h+pszPathOut]; pszPathOut
0x180013f2d  call    cs:__imp_PathCchCombine
0x180013f33  test    eax, eax
0x180013f35  js      short loc_180013EE1
0x180013f37  lea     rdx, [rbp+670h+FindFileData]; lpFindFileData
0x180013f3b  lea     rcx, [rbp+670h+pszPathOut]; lpFileName
0x180013f42  call    cs:__imp_FindFirstFileW
0x180013f48  mov     rsi, rax
0x180013f4b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013f4f  jz      short loc_180013EE1
0x180013f51  xor     r11d, r11d
0x180013f54  cmp     [rbp+670h+FindFileData.cFileName], 2Eh ; '.'
0x180013f59  jz      loc_180014106
0x180013f5f  lea     r9, [rbp+670h+FindFileData.cFileName]; pszMore
0x180013f63  mov     r8, r13; pszPathIn
0x180013f66  mov     edx, 104h; cchPathOut
0x180013f6b  lea     rcx, [rbp+670h+FileName]; pszPathOut
0x180013f72  call    cs:__imp_PathCchCombine
0x180013f78  mov     edi, eax
0x180013f7a  xor     eax, eax
0x180013f7c  test    edi, edi
0x180013f7e  js      loc_18001426F
0x180013f84  mov     ecx, [rbp+670h+FindFileData.dwFileAttributes]
0x180013f87  test    cl, 10h
0x180013f8a  jnz     loc_180014082
0x180013f90  mov     edx, [rbp+670h+FindFileData.dwReserved0]
0x180013f93  call    cs:__imp_RtlIsPartialPlaceholder
0x180013f99  test    al, al
0x180013f9b  jnz     loc_1800141F8
0x180013fa1  mov     eax, [rbp+670h+FindFileData.nFileSizeLow]
0x180013fa4  lea     r9, [rsp+770h+pv]; unsigned __int16 **
0x180013fa9  inc     dword ptr [r15]
0x180013fac  lea     r8, [rsp+770h+var_710]; bool *
0x180013fb1  mov     edx, [rbp+670h+FindFileData.dwFileAttributes]; unsigned int
0x180013fb4  lea     rcx, [rbp+670h+FileName]; pszPath
0x180013fbb  mov     [r12], eax
0x180013fbf  mov     eax, [rbp+670h+FindFileData.nFileSizeHigh]
0x180013fc2  mov     [r12+4], eax
0x180013fc7  xor     eax, eax
0x180013fc9  mov     [rsp+770h+var_710], al
0x180013fcd  mov     [rsp+770h+pv], rax
0x180013fd2  call    ?CheckFileEncryption@@YAJPEBGKPEA_NPEAPEAG@Z; CheckFileEncryption(ushort const *,ulong,bool *,ushort * *)
0x180013fd7  xor     r11d, r11d
0x180013fda  test    eax, eax
0x180013fdc  js      loc_180014260
0x180013fe2  cmp     [rsp+770h+var_710], r11b
0x180013fe7  jnz     loc_180014220
0x180013fed  test    edi, edi
0x180013fef  js      loc_180014245
0x180013ff5  mov     r10, [rsp+770h+pv]
0x180013ffa  test    r10, r10
0x180013ffd  jz      short loc_18001403A
0x180013fff  mov     rcx, [rbp+670h+var_6F0]; unsigned __int16 *
0x180014003  cmp     [rcx], r11w
0x180014007  jnz     short loc_180014029
0x180014009  mov     rdx, [rbp+670h+var_6E8]
0x18001400d  lea     r8, [rbp+670h+FileName]; unsigned __int16 *
0x180014014  mov     rax, r10
0x180014017  mov     r10, r11
0x18001401a  mov     [rdx], rax
0x18001401d  mov     edx, 104h; unsigned __int64
0x180014022  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014027  mov     edi, eax
0x180014029  test    r10, r10
0x18001402c  jnz     loc_18001412D
0x180014032  test    edi, edi
0x180014034  js      loc_18001426F
0x18001403a  mov     rcx, [rsp+770h+var_700]
0x18001403f  mov     rax, [rcx]
0x180014042  mov     rax, [rax+38h]
0x180014046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001404b  xor     ecx, ecx
0x18001404d  test    eax, eax
0x18001404f  jnz     loc_18001426A
0x180014055  mov     edi, ecx
0x180014057  lea     rdx, [rbp+670h+FindFileData]; lpFindFileData
0x18001405b  mov     rcx, rsi; hFindFile
0x18001405e  call    cs:__imp_FindNextFileW
0x180014064  xor     r11d, r11d
0x180014067  test    eax, eax
0x180014069  jnz     loc_180013F54
0x18001406f  jmp     loc_18001426F
0x180014074  mov     rcx, rbx; pv
0x180014077  call    cs:__imp_CoTaskMemFree
0x18001407d  jmp     loc_180013EF4
0x180014082  mov     rcx, [rsp+770h+var_700]; struct IProgressDialog *
0x180014087  lea     r9, [rsp+770h+pv]; unsigned int *
0x18001408c  mov     dword ptr [rsp+770h+pv], eax
0x180014090  lea     rdx, [rbp+670h+FileName]; unsigned __int16 *
0x180014097  mov     qword ptr [rsp+770h+var_6F8], rax
0x18001409c  xor     r8d, r8d; bool
0x18001409f  mov     rax, [rbp+670h+var_6E8]
0x1800140a3  mov     [rsp+770h+var_718], rax; unsigned __int16 **
0x1800140a8  mov     rax, [rbp+670h+var_6F0]
0x1800140ac  mov     [rsp+770h+var_720], 104h; unsigned int
0x1800140b4  mov     [rsp+770h+var_728], rax; unsigned __int16 *
0x1800140b9  mov     rax, [rbp+670h+var_6D8]
0x1800140bd  mov     [rsp+770h+var_730], r14; unsigned int *
0x1800140c2  mov     [rsp+770h+var_738], 104h; unsigned int
0x1800140ca  mov     [rsp+770h+var_740], rax; unsigned __int16 *
0x1800140cf  mov     rax, [rbp+670h+var_6E0]
0x1800140d3  mov     [rsp+770h+var_748], rax; bool *
0x1800140d8  lea     rax, [rsp+770h+var_6F8]
0x1800140dd  mov     [rsp+770h+var_750], rax; int
0x1800140e2  call    ?GetDropFileCountSizeAndEncryption@@YAJPEAUIProgressDialog@@PEBG_NPEAIPEAT_ULARGE_INTEGER@@PEA_NPEAGI36IPEAPEAG@Z; GetDropFileCountSizeAndEncryption(IProgressDialog *,ushort const *,bool,uint *,_ULARGE_INTEGER *,bool *,ushort *,uint,uint *,ushort *,uint,ushort * *)
0x1800140e7  mov     edi, eax
0x1800140e9  test    eax, eax
0x1800140eb  js      loc_18001426F
0x1800140f1  mov     eax, dword ptr [rsp+770h+pv]
0x1800140f5  add     [r15], eax
0x1800140f8  mov     rax, qword ptr [rsp+770h+var_6F8]
0x1800140fd  add     [r12], rax
0x180014101  jmp     loc_18001403A
0x180014106  movzx   ecx, [rbp+670h+FindFileData.cFileName+2]
0x18001410a  test    cx, cx
0x18001410d  jz      loc_180014032
0x180014113  cmp     [rbp+670h+FindFileData.cFileName+4], r11w
0x180014118  jnz     loc_180013F5F
0x18001411e  cmp     cx, 2Eh ; '.'
0x180014122  jnz     loc_180013F5F
0x180014128  jmp     loc_180014032
0x18001412d  mov     rcx, r10; pv
0x180014130  call    cs:__imp_CoTaskMemFree
0x180014136  jmp     loc_180014032
0x18001413b  mov     rcx, [rbp+678h]; this
0x180014142  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x180014149  mov     r9d, eax; char *
0x18001414c  mov     edx, 607h; void *
0x180014151  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014156  mov     rbx, [rsp+770h+pv]
0x18001415b  mov     r11d, 104h
0x180014161  jmp     loc_180013EB6
0x180014166  cmp     [r14], r10d
0x180014169  jnz     loc_180013EA0
0x18001416f  lea     r8, [rbp+670h+FindFileData.cFileName]; unsigned __int16 *
0x180014173  mov     rdx, r11; unsigned __int64
0x180014176  mov     rcx, rbx; unsigned __int16 *
0x180014179  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001417e  inc     dword ptr [r14]
0x180014181  mov     edi, eax
0x180014183  test    eax, eax
0x180014185  jns     loc_180013EA0
0x18001418b  mov     rcx, [rbp+678h]; this
0x180014192  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x180014199  mov     r9d, eax; char *
0x18001419c  mov     edx, 612h; void *
0x1800141a1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800141a6  mov     rbx, [rsp+770h+pv]
0x1800141ab  mov     rcx, [rbp+678h]; this
0x1800141b2  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x1800141b9  mov     r9d, edi; char *
0x1800141bc  mov     edx, 619h; void *
0x1800141c1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800141c6  jmp     loc_180013EEB
0x1800141cb  mov     rcx, [rbp+670h+var_6F0]; unsigned __int16 *
0x1800141cf  cmp     [rcx], r10w
0x1800141d3  jnz     loc_180013EAE
0x1800141d9  mov     rdx, [rbp+670h+var_6E8]
0x1800141dd  mov     rax, rbx
0x1800141e0  mov     r8, r13; unsigned __int16 *
0x1800141e3  mov     rbx, r10
0x1800141e6  mov     [rdx], rax
0x1800141e9  mov     rdx, r11; unsigned __int64
0x1800141ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800141f1  mov     edi, eax
0x1800141f3  jmp     loc_180013EAE
0x1800141f8  mov     rax, [rbp+670h+var_6E0]
0x1800141fc  lea     r8, [rbp+670h+FindFileData]; struct _WIN32_FIND_DATAW *
0x180014200  mov     rcx, [rsp+770h+var_700]; struct IProgressDialog *
0x180014205  lea     rdx, [rbp+670h+FileName]; pszName
0x18001420c  xor     r9d, r9d; bool
0x18001420f  mov     [rsp+770h+var_750], rax; bool *
0x180014214  call    ?DownloadPlaceholderFile@@YAJPEAUIProgressDialog@@PEBGAEBU_WIN32_FIND_DATAW@@_NPEA_N@Z; DownloadPlaceholderFile(IProgressDialog *,ushort const *,_WIN32_FIND_DATAW const &,bool,bool *)
0x180014219  mov     edi, eax
0x18001421b  jmp     loc_180013FA1
0x180014220  cmp     [r14], r11d
0x180014223  jnz     loc_180013FED
0x180014229  mov     rcx, [rbp+670h+var_6D8]; unsigned __int16 *
0x18001422d  lea     r8, [rbp+670h+FindFileData.cFileName]; unsigned __int16 *
0x180014231  mov     edx, 104h; unsigned __int64
0x180014236  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001423b  inc     dword ptr [r14]
0x18001423e  mov     edi, eax
0x180014240  jmp     loc_180013FED
0x180014245  mov     rcx, [rbp+678h]; this
0x18001424c  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x180014253  mov     r9d, edi; char *
0x180014256  mov     edx, 65Bh; void *
0x18001425b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014260  mov     r10, [rsp+770h+pv]
0x180014265  jmp     loc_180014029
0x18001426a  mov     edi, 800704C7h
0x18001426f  mov     rcx, rsi; hFindFile
0x180014272  call    cs:__imp_FindClose
0x180014278  jmp     loc_180013EE1
0x18001427d  mov     rax, [rbp+670h+var_6E0]
0x180014281  lea     r8, [rbp+670h+FindFileData]; struct _WIN32_FIND_DATAW *
0x180014285  mov     rcx, [rsp+770h+var_700]; struct IProgressDialog *
0x18001428a  mov     r9b, sil; bool
0x18001428d  mov     rdx, r13; pszName
0x180014290  mov     [rsp+770h+var_750], rax; bool *
0x180014295  call    ?DownloadPlaceholderFile@@YAJPEAUIProgressDialog@@PEBGAEBU_WIN32_FIND_DATAW@@_NPEA_N@Z; DownloadPlaceholderFile(IProgressDialog *,ushort const *,_WIN32_FIND_DATAW const &,bool,bool *)
0x18001429a  mov     edi, eax
0x18001429c  jmp     loc_180013ECF
```
