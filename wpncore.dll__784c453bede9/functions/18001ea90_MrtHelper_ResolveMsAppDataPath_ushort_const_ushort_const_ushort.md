# MrtHelper::ResolveMsAppDataPath(ushort const *,ushort const *,ushort * *)

- ea: `0x18001ea90`
- end: `0x18001ed79`
- name: `?ResolveMsAppDataPath@MrtHelper@@UEAAJPEBG0PEAPEAG@Z`
- size: `745`
- prototype: `int(MrtHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180011618`
- `0x18001e6b4`
- `0x18001ea90`
- `0x18001ed80`
- `0x18001ef74`
- `0x18001f3ac`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ebae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ebae`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ebc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ebc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed41`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ecf9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ecf9`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18001eb01`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18001eb01`
- `urlmon!__imp_AppDataIUriToFileIUri` at `0x18001ec35`
- `urlmon!__imp_AppDataIUriToFileIUri` at `0x18001ec35`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall MrtHelper::ResolveMsAppDataPath(
        MrtHelper *this,
        const unsigned __int16 *a2,
        CallerIdentity *a3,
        unsigned __int16 **a4)
{
  __int64 v7; // rdx
  __int64 result; // rax
  HRESULT v9; // eax
  int PackageInfoFromPackageFullName; // eax
  void *v11; // rcx
  HANDLE CurrentProcess; // rax
  BOOL v13; // edi
  signed int LastError; // eax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  MrtHelper *v18; // rcx
  int v19; // eax
  const char *v20; // r9
  _QWORD *v21; // rcx
  void *v22; // rcx
  IUri *v23; // rcx
  struct PACKAGE_INFO **v24; // [rsp+20h] [rbp-78h]
  int v25; // [rsp+20h] [rbp-78h]
  int v26; // [rsp+20h] [rbp-78h]
  _QWORD *v27; // [rsp+30h] [rbp-68h] BYREF
  IUri *ppURI; // [rsp+38h] [rbp-60h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-48h] BYREF
  void **p_pv; // [rsp+58h] [rbp-40h]
  unsigned int v33[2]; // [rsp+60h] [rbp-38h] BYREF
  char v34; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned int v36; // [rsp+B8h] [rbp+20h] BYREF

  if ( !a4 )
  {
    v7 = 260;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
      (const char *)0x80070057LL,
      (int)v24);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v7 = 261;
    goto LABEL_3;
  }
  *a4 = 0;
  ppURI = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
  v9 = CreateUri(a2, 0x4000u, 0, &ppURI);
  try
  {
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
        (const char *)(unsigned int)v9,
        (int)v24);
    pv = 0;
    p_pv = &pv;
    *(_QWORD *)v33 = 0;
    v34 = 1;
    PackageInfoFromPackageFullName = CallerIdentity::GetPackageInfoFromPackageFullName(
                                       a3,
                                       0x70u,
                                       (unsigned int)&v36,
                                       v33,
                                       v24);
    if ( PackageInfoFromPackageFullName < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
        (const char *)(unsigned int)PackageInfoFromPackageFullName,
        v25);
    if ( v34 )
    {
      v11 = *p_pv;
      *p_pv = *(void **)v33;
      if ( v11 )
        CoTaskMemFree(v11);
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    v13 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( !v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x117,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
        (const char *)(unsigned int)LastError,
        v25);
    v27 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v26 = (int)TokenHandle;
    v15 = AppDataIUriToFileIUri(ppURI, pv, 1, AppDataUriCallbackViaStateAPIset);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
        (const char *)(unsigned int)v15,
        v26);
    bstrString = 0;
    v16 = *v27;
    p_pv = (void **)&bstrString;
    *(_QWORD *)v33 = 0;
    v34 = 1;
    v17 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *))(v16 + 56))(v27, v33);
    v18 = retaddr;
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
        (const char *)(unsigned int)v17,
        v26);
    if ( v34 )
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        p_pv,
        *(_QWORD *)v33);
    v19 = MrtHelper::ConvertFileUriToFilePath(v18, bstrString, a4);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
        (const char *)(unsigned int)v19,
        v26);
    if ( bstrString )
      SysFreeString(bstrString);
    v21 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    v22 = pv;
    pv = 0;
    if ( v22 )
      CoTaskMemFree(v22);
    v23 = ppURI;
    if ( ppURI )
    {
      ppURI = 0;
      ((void (__fastcall *)(IUri *))v23->lpVtbl->Release)(v23);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x120,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18001ea90  push    rbx
0x18001ea92  push    rsi
0x18001ea93  push    rdi
0x18001ea94  push    r14
0x18001ea96  sub     rsp, 78h
0x18001ea9a  mov     rbx, r9
0x18001ea9d  mov     rdi, r8
0x18001eaa0  mov     rsi, rdx
0x18001eaa3  xor     r14d, r14d
0x18001eaa6  test    r9, r9
0x18001eaa9  jnz     short loc_18001EAD3
0x18001eaab  mov     edx, 104h; void *
0x18001eab0  mov     ebx, 80070057h
0x18001eab5  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eabc  mov     r9d, ebx; char *
0x18001eabf  mov     rcx, [rsp+98h]; this
0x18001eac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eacc  mov     eax, ebx
0x18001eace  jmp     loc_18001ED6F
0x18001ead3  test    rdi, rdi
0x18001ead6  jnz     short loc_18001EADF
0x18001ead8  mov     edx, 105h
0x18001eadd  jmp     short loc_18001EAB0
0x18001eadf  mov     [r9], r14
0x18001eae2  mov     [rsp+98h+ppURI], r14
0x18001eae7  lea     rcx, [rsp+98h+ppURI]
0x18001eaec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eaf1  lea     r9, [rsp+98h+ppURI]; ppURI
0x18001eaf6  xor     r8d, r8d; dwReserved
0x18001eaf9  mov     edx, 4000h; dwFlags
0x18001eafe  mov     rcx, rsi; pwzURI
0x18001eb01  call    cs:__imp_CreateUri
0x18001eb07  mov     rcx, [rsp+98h]; this
0x18001eb0f  test    eax, eax
0x18001eb11  jns     short loc_18001EB27
0x18001eb13  mov     r9d, eax; char *
0x18001eb16  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eb1d  mov     edx, 10Ch; void *
0x18001eb22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eb27  mov     [rsp+98h+pv], r14
0x18001eb2c  lea     rax, [rsp+98h+pv]
0x18001eb31  mov     [rsp+98h+var_40], rax
0x18001eb36  mov     qword ptr [rsp+98h+var_38], r14
0x18001eb3b  mov     [rsp+98h+var_30], 1
0x18001eb40  lea     r9, [rsp+98h+var_38]; unsigned int *
0x18001eb45  lea     r8, [rsp+98h+arg_18]; unsigned int
0x18001eb4d  mov     edx, 70h ; 'p'; flags
0x18001eb52  mov     rcx, rdi; this
0x18001eb55  call    ?GetPackageInfoFromPackageFullName@CallerIdentity@@YAJPEBGIPEAIPEAPEAUPACKAGE_INFO@@@Z; CallerIdentity::GetPackageInfoFromPackageFullName(ushort const *,uint,uint *,PACKAGE_INFO * *)
0x18001eb5a  mov     rcx, [rsp+98h]; this
0x18001eb62  test    eax, eax
0x18001eb64  jns     short loc_18001EB7B
0x18001eb66  mov     r9d, eax; char *
0x18001eb69  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eb70  mov     edx, 114h; void *
0x18001eb75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eb7b  cmp     [rsp+98h+var_30], r14b
0x18001eb80  jz      short loc_18001EB9D
0x18001eb82  mov     rdx, [rsp+98h+var_40]
0x18001eb87  mov     rcx, [rdx]; pv
0x18001eb8a  mov     rax, qword ptr [rsp+98h+var_38]
0x18001eb8f  mov     [rdx], rax
0x18001eb92  test    rcx, rcx
0x18001eb95  jz      short loc_18001EB9D
0x18001eb97  call    cs:__imp_CoTaskMemFree
0x18001eb9d  mov     [rsp+98h+TokenHandle], r14
0x18001eba2  xor     edx, edx
0x18001eba4  lea     rcx, [rsp+98h+TokenHandle]
0x18001eba9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001ebae  call    cs:__imp_GetCurrentProcess
0x18001ebb4  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x18001ebb9  mov     edx, 8; DesiredAccess
0x18001ebbe  mov     rcx, rax; ProcessHandle
0x18001ebc1  call    cs:__imp_OpenProcessToken
0x18001ebc7  mov     edi, eax
0x18001ebc9  call    cs:__imp_GetLastError
0x18001ebcf  test    eax, eax
0x18001ebd1  jle     short loc_18001EBDB
0x18001ebd3  movzx   eax, ax
0x18001ebd6  or      eax, 80070000h
0x18001ebdb  mov     rcx, [rsp+98h]; this
0x18001ebe3  test    edi, edi
0x18001ebe5  jnz     short loc_18001EBFB
0x18001ebe7  mov     r9d, eax; char *
0x18001ebea  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ebf1  mov     edx, 117h; void *
0x18001ebf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ebfb  mov     [rsp+98h+var_68], r14
0x18001ec00  lea     rcx, [rsp+98h+var_68]
0x18001ec05  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ec0a  mov     rax, [rsp+98h+TokenHandle]
0x18001ec0f  lea     rcx, [rsp+98h+var_68]
0x18001ec14  mov     [rsp+98h+var_70], rcx
0x18001ec19  mov     qword ptr [rsp+98h+var_78], rax; int
0x18001ec1e  lea     r9, AppDataUriCallbackViaStateAPIset
0x18001ec25  mov     r8d, 1
0x18001ec2b  mov     rdx, [rsp+98h+pv]
0x18001ec30  mov     rcx, [rsp+98h+ppURI]
0x18001ec35  call    cs:__imp_AppDataIUriToFileIUri
0x18001ec3b  mov     rcx, [rsp+98h]; this
0x18001ec43  test    eax, eax
0x18001ec45  jns     short loc_18001EC5B
0x18001ec47  mov     r9d, eax; char *
0x18001ec4a  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ec51  mov     edx, 11Ah; void *
0x18001ec56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ec5b  mov     [rsp+98h+bstrString], r14
0x18001ec60  mov     rcx, [rsp+98h+var_68]
0x18001ec65  mov     rax, [rcx]
0x18001ec68  lea     rdx, [rsp+98h+bstrString]
0x18001ec6d  mov     [rsp+98h+var_40], rdx
0x18001ec72  mov     qword ptr [rsp+98h+var_38], r14
0x18001ec77  mov     [rsp+98h+var_30], 1
0x18001ec7c  lea     rdx, [rsp+98h+var_38]
0x18001ec81  mov     rax, [rax+38h]
0x18001ec85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec8a  mov     rcx, [rsp+98h]; this
0x18001ec92  test    eax, eax
0x18001ec94  jns     short loc_18001ECAB
0x18001ec96  mov     r9d, eax; char *
0x18001ec99  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eca0  mov     edx, 11Dh; void *
0x18001eca5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ecab  cmp     [rsp+98h+var_30], r14b
0x18001ecb0  jz      short loc_18001ECC1
0x18001ecb2  mov     rdx, qword ptr [rsp+98h+var_38]
0x18001ecb7  mov     rcx, [rsp+98h+var_40]
0x18001ecbc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001ecc1  mov     r8, rbx; unsigned __int16 **
0x18001ecc4  mov     rdx, [rsp+98h+bstrString]; unsigned __int16 *
0x18001ecc9  call    ?ConvertFileUriToFilePath@MrtHelper@@AEAAJPEBGPEAPEAG@Z; MrtHelper::ConvertFileUriToFilePath(ushort const *,ushort * *)
0x18001ecce  mov     rcx, [rsp+98h]; this
0x18001ecd6  test    eax, eax
0x18001ecd8  jns     short loc_18001ECEF
0x18001ecda  mov     r9d, eax; char *
0x18001ecdd  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ece4  mov     edx, 11Eh; void *
0x18001ece9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ecef  mov     rcx, [rsp+98h+bstrString]; bstrString
0x18001ecf4  test    rcx, rcx
0x18001ecf7  jz      short loc_18001ED00
0x18001ecf9  call    cs:__imp_SysFreeString
0x18001ecff  nop
0x18001ed00  mov     rcx, [rsp+98h+var_68]
0x18001ed05  test    rcx, rcx
0x18001ed08  jz      short loc_18001ED1C
0x18001ed0a  mov     [rsp+98h+var_68], r14
0x18001ed0f  mov     rax, [rcx]
0x18001ed12  mov     rax, [rax+10h]
0x18001ed16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed1b  nop
0x18001ed1c  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18001ed21  lea     rax, [rcx-1]
0x18001ed25  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ed29  ja      short loc_18001ED32
0x18001ed2b  call    cs:__imp_CloseHandle
0x18001ed31  nop
0x18001ed32  mov     rcx, [rsp+98h+pv]; pv
0x18001ed37  mov     [rsp+98h+pv], r14
0x18001ed3c  test    rcx, rcx
0x18001ed3f  jz      short loc_18001ED48
0x18001ed41  call    cs:__imp_CoTaskMemFree
0x18001ed47  nop
0x18001ed48  mov     rcx, [rsp+98h+ppURI]
0x18001ed4d  test    rcx, rcx
0x18001ed50  jz      short loc_18001ED64
0x18001ed52  mov     [rsp+98h+ppURI], r14
0x18001ed57  mov     rax, [rcx]
0x18001ed5a  mov     rax, [rax+10h]
0x18001ed5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed63  nop
0x18001ed64  xor     eax, eax
0x18001ed66  jmp     short loc_18001ED6F
0x18001ed68  mov     eax, [rsp+98h+arg_18]
0x18001ed6f  add     rsp, 78h
0x18001ed73  pop     r14
0x18001ed75  pop     rdi
0x18001ed76  pop     rsi
0x18001ed77  pop     rbx
0x18001ed78  retn
```
