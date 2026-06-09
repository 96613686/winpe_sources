# ValidateHash(IQuerySource *,ulong,ushort const *,ushort const *,ushort const *,ushort * *,bool *)

- ea: `0x18038bddc`
- end: `0x18038c33a`
- name: `?ValidateHash@@YAJPEAUIQuerySource@@KPEBG11PEAPEAGPEA_N@Z`
- size: `1374`
- prototype: `int(struct IQuerySource *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180576814`

## callees

- `0x18000d6cc`
- `0x1800432f0`
- `0x18004a030`
- `0x18005e720`
- `0x1800d13a0`
- `0x18026aaf4`
- `0x18033a56c`
- `0x18038bddc`
- `0x1803a4cb0`
- `0x1805e8634`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18038bff4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18038c241`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18038bff4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18038c241`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038bf2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c2cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038bf2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038c2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038be72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038bfa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c1ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c260`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c2bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c2e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038be72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038bfa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c1ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c260`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c2bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038c2e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ValidateHash(
        __int64 (__fastcall ***a1)(struct IQuerySource *, GUID *, __int64 *),
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6,
        bool *a7)
{
  __int64 (__fastcall *v11)(struct IQuerySource *, const WCHAR *, const WCHAR *, __int64); // rbx
  __int64 v12; // rax
  int TruncatedSystemTimeFromRegKey; // ebx
  __int64 (__fastcall *v15)(struct IQuerySource *, GUID *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, HKEY *); // rbx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rdx
  HKEY v21; // rcx
  unsigned __int16 **v22; // rax
  int v23; // eax
  __int64 (__fastcall *v24)(struct IQuerySource *, const WCHAR *, const WCHAR *, __int64); // rbx
  __int64 v25; // rax
  unsigned __int16 *v26; // rax
  __int64 v27; // rax
  __int64 (__fastcall *v28)(struct IQuerySource *, GUID *, __int64 *); // rbx
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, HKEY *); // rbx
  const unsigned __int16 *v32; // rdx
  __int64 v33; // rdx
  unsigned __int16 **v34; // rax
  int v35; // eax
  __int64 (__fastcall *v36)(struct IQuerySource *, const WCHAR *, const WCHAR *, __int64); // rbx
  __int64 v37; // rax
  unsigned __int16 *v38; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-71h]
  int bIgnoreCasea; // [rsp+20h] [rbp-71h]
  LPCWCH lpString2; // [rsp+40h] [rbp-51h] BYREF
  unsigned __int16 *v42; // [rsp+48h] [rbp-49h]
  bool *v43; // [rsp+50h] [rbp-41h]
  LPVOID pv; // [rsp+58h] [rbp-39h] BYREF
  __int64 v45; // [rsp+60h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-29h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-21h] BYREF
  struct _SYSTEMTIME v48; // [rsp+78h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v42 = a5;
  v43 = a7;
  *a6 = 0;
  *a7 = 0;
  v11 = (__int64 (__fastcall *)(struct IQuerySource *, const WCHAR *, const WCHAR *, __int64))(*a1)[4];
  pv = 0;
  if ( !a2 )
  {
    v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    TruncatedSystemTimeFromRegKey = v11((struct IQuerySource *)a1, L"UserChoice", L"ProgId", v12);
    if ( TruncatedSystemTimeFromRegKey < 0 )
      goto LABEL_3;
    v45 = 0;
    v15 = **a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    v16 = v15((struct IQuerySource *)a1, &GUID_d960050c_f4e1_4294_ac4b_598913605923, &v45);
    TruncatedSystemTimeFromRegKey = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2EF,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\userchoicehelpers.h",
        (const char *)(unsigned int)v16,
        bIgnoreCase);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      goto LABEL_3;
    }
    hKey = 0;
    v17 = v45;
    v18 = *(__int64 (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)v45 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    TruncatedSystemTimeFromRegKey = v18(v17, 131097, &hKey);
    if ( TruncatedSystemTimeFromRegKey < 0 )
    {
      v20 = 754;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\userchoicehelpers.h",
        (const char *)(unsigned int)TruncatedSystemTimeFromRegKey,
        bIgnoreCase);
      goto LABEL_12;
    }
    v48 = 0;
    TruncatedSystemTimeFromRegKey = GetTruncatedSystemTimeFromRegKey(hKey, v19, &v48);
    if ( TruncatedSystemTimeFromRegKey < 0 )
    {
      v20 = 757;
      goto LABEL_11;
    }
    lpString2 = 0;
    v22 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString2);
    v23 = HashAssociation(v42, a3, (const unsigned __int16 *)pv, &v48, v22);
    TruncatedSystemTimeFromRegKey = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F8,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\userchoicehelpers.h",
        (const char *)(unsigned int)v23,
        bIgnoreCasea);
      if ( lpString2 )
        CoTaskMemFree((LPVOID)lpString2);
LABEL_12:
      v21 = hKey;
      if ( !hKey )
        goto LABEL_8;
LABEL_13:
      RegCloseKey(v21);
      goto LABEL_8;
    }
    lpString1 = 0;
    v24 = (__int64 (__fastcall *)(struct IQuerySource *, const WCHAR *, const WCHAR *, __int64))(*a1)[4];
    v25 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString1);
    TruncatedSystemTimeFromRegKey = v24((struct IQuerySource *)a1, L"UserChoice", L"Hash", v25);
    if ( TruncatedSystemTimeFromRegKey >= 0 && CompareStringOrdinal(lpString1, -1, lpString2, -1, 0) == 2 )
    {
      v26 = (unsigned __int16 *)pv;
      pv = 0;
      *a6 = v26;
      if ( lpString1 )
        CoTaskMemFree((LPVOID)lpString1);
      if ( lpString2 )
        CoTaskMemFree((LPVOID)lpString2);
      if ( hKey )
        RegCloseKey(hKey);
LABEL_57:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    if ( lpString1 )
      CoTaskMemFree((LPVOID)lpString1);
    if ( lpString2 )
      CoTaskMemFree((LPVOID)lpString2);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_66;
  }
  v27 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  TruncatedSystemTimeFromRegKey = v11((struct IQuerySource *)a1, L"UserChoiceLatest\\ProgId", L"ProgId", v27);
  if ( TruncatedSystemTimeFromRegKey < 0 )
  {
LABEL_3:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)TruncatedSystemTimeFromRegKey;
  }
  v45 = 0;
  v28 = **a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  v29 = v28((struct IQuerySource *)a1, &GUID_d960050c_f4e1_4294_ac4b_598913605923, &v45);
  TruncatedSystemTimeFromRegKey = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x308,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\userchoicehelpers.h",
      (const char *)(unsigned int)v29,
      bIgnoreCase);
    goto LABEL_8;
  }
  hKey = 0;
  v30 = v45;
  v31 = *(__int64 (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)v45 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  TruncatedSystemTimeFromRegKey = v31(v30, 131097, &hKey);
  if ( TruncatedSystemTimeFromRegKey < 0 )
  {
    v33 = 779;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\userchoicehelpers.h",
      (const char *)(unsigned int)TruncatedSystemTimeFromRegKey,
      bIgnoreCase);
    goto LABEL_42;
  }
  v48 = 0;
  TruncatedSystemTimeFromRegKey = GetSystemTimeFromRegKey(hKey, v32, &v48);
  if ( TruncatedSystemTimeFromRegKey < 0 )
  {
    v33 = 782;
    goto LABEL_41;
  }
  lpString2 = 0;
  v34 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString2);
  v35 = HashAssociationRotation(a2, a4, v42, a3, (const unsigned __int16 *)pv, &v48, v34);
  TruncatedSystemTimeFromRegKey = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\userchoicehelpers.h",
      (const char *)(unsigned int)v35,
      bIgnoreCasea);
    if ( lpString2 )
      CoTaskMemFree((LPVOID)lpString2);
LABEL_42:
    v21 = hKey;
    if ( !hKey )
      goto LABEL_8;
    goto LABEL_13;
  }
  lpString1 = 0;
  v36 = (__int64 (__fastcall *)(struct IQuerySource *, const WCHAR *, const WCHAR *, __int64))(*a1)[4];
  v37 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString1);
  TruncatedSystemTimeFromRegKey = v36((struct IQuerySource *)a1, L"UserChoiceLatest", L"Hash", v37);
  if ( TruncatedSystemTimeFromRegKey >= 0 && CompareStringOrdinal(lpString1, -1, lpString2, -1, 0) == 2 )
  {
    v38 = (unsigned __int16 *)pv;
    pv = 0;
    *a6 = v38;
    if ( lpString1 )
      CoTaskMemFree((LPVOID)lpString1);
    if ( lpString2 )
      CoTaskMemFree((LPVOID)lpString2);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_57;
  }
  if ( lpString1 )
    CoTaskMemFree((LPVOID)lpString1);
  if ( lpString2 )
    CoTaskMemFree((LPVOID)lpString2);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_66:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  if ( pv )
    CoTaskMemFree(pv);
  *v43 = 1;
  if ( TruncatedSystemTimeFromRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\userchoicehelpers.h",
      (const char *)(unsigned int)TruncatedSystemTimeFromRegKey,
      bIgnoreCasea);
    return (unsigned int)TruncatedSystemTimeFromRegKey;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18038bddc  push    rbp
0x18038bdde  push    rbx
0x18038bddf  push    rsi
0x18038bde0  push    rdi
0x18038bde1  push    r12
0x18038bde3  push    r13
0x18038bde5  push    r14
0x18038bde7  push    r15
0x18038bde9  lea     rbp, [rsp-7]
0x18038bdee  sub     rsp, 98h
0x18038bdf5  mov     rax, cs:__security_cookie
0x18038bdfc  xor     rax, rsp
0x18038bdff  mov     [rbp+3Fh+var_48], rax
0x18038be03  mov     r12, r9
0x18038be06  mov     r13, r8
0x18038be09  mov     r15d, edx
0x18038be0c  mov     rsi, rcx
0x18038be0f  mov     rax, [rbp+3Fh+arg_20]
0x18038be13  mov     [rbp+3Fh+var_88], rax
0x18038be17  mov     r14, [rbp+3Fh+arg_28]
0x18038be1b  mov     rax, [rbp+3Fh+arg_30]
0x18038be1f  mov     [rbp+3Fh+var_80], rax
0x18038be23  xor     edi, edi
0x18038be25  mov     [r14], rdi
0x18038be28  mov     [rax], dil
0x18038be2b  mov     rax, [rcx]
0x18038be2e  mov     rbx, [rax+20h]
0x18038be32  mov     [rbp+3Fh+pv], rdi
0x18038be36  test    edx, edx
0x18038be38  jnz     loc_18038C088
0x18038be3e  lea     rcx, [rbp+3Fh+pv]
0x18038be42  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18038be47  mov     r9, rax
0x18038be4a  lea     r8, aProgid_1; "ProgId"
0x18038be51  lea     rdx, aUserchoice; "UserChoice"
0x18038be58  mov     rcx, rsi
0x18038be5b  mov     rax, rbx
0x18038be5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038be63  mov     ebx, eax
0x18038be65  test    eax, eax
0x18038be67  jns     short loc_18038BE7F
0x18038be69  mov     rcx, [rbp+3Fh+pv]; pv
0x18038be6d  test    rcx, rcx
0x18038be70  jz      short loc_18038BE78
0x18038be72  call    cs:__imp_CoTaskMemFree
0x18038be78  mov     eax, ebx
0x18038be7a  jmp     loc_18038C31A
0x18038be7f  mov     [rbp+3Fh+var_70], rdi
0x18038be83  mov     rax, [rsi]
0x18038be86  mov     rbx, [rax]
0x18038be89  lea     rcx, [rbp+3Fh+var_70]
0x18038be8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18038be92  lea     r8, [rbp+3Fh+var_70]
0x18038be96  lea     rdx, _GUID_d960050c_f4e1_4294_ac4b_598913605923
0x18038be9d  mov     rcx, rsi
0x18038bea0  mov     rax, rbx
0x18038bea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038bea8  mov     ebx, eax
0x18038beaa  test    eax, eax
0x18038beac  jns     short loc_18038BED2
0x18038beae  mov     rcx, [rbp+47h]; this
0x18038beb2  mov     r9d, eax; char *
0x18038beb5  lea     r8, aOnecoreuapInte_14; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18038bebc  mov     edx, 2EFh; void *
0x18038bec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038bec6  nop
0x18038bec7  lea     rcx, [rbp+3Fh+var_70]
0x18038becb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18038bed0  jmp     short loc_18038BE69
0x18038bed2  mov     [rbp+3Fh+hKey], rdi
0x18038bed6  mov     rdi, [rbp+3Fh+var_70]
0x18038beda  mov     rax, [rdi]
0x18038bedd  mov     rbx, [rax+20h]
0x18038bee1  xor     edx, edx
0x18038bee3  lea     rcx, [rbp+3Fh+hKey]
0x18038bee7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18038beec  lea     r8, [rbp+3Fh+hKey]
0x18038bef0  mov     edx, 20019h
0x18038bef5  mov     rcx, rdi
0x18038bef8  mov     rax, rbx
0x18038befb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038bf00  mov     ebx, eax
0x18038bf02  xor     edi, edi
0x18038bf04  test    eax, eax
0x18038bf06  jns     short loc_18038BF32
0x18038bf08  mov     edx, 2F2h; void *
0x18038bf0d  lea     r8, aOnecoreuapInte_14; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18038bf14  mov     r9d, ebx; char *
0x18038bf17  mov     rcx, [rbp+47h]; this
0x18038bf1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038bf20  nop
0x18038bf21  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18038bf25  test    rcx, rcx
0x18038bf28  jz      short loc_18038BEC7
0x18038bf2a  call    cs:__imp_RegCloseKey
0x18038bf30  jmp     short loc_18038BEC7
0x18038bf32  xorps   xmm0, xmm0
0x18038bf35  movups  xmmword ptr [rbp+3Fh+var_58.wYear], xmm0
0x18038bf39  lea     r8, [rbp+3Fh+var_58]; struct _SYSTEMTIME *
0x18038bf3d  mov     rcx, [rbp+3Fh+hKey]; HKEY
0x18038bf41  call    ?GetTruncatedSystemTimeFromRegKey@@YAJPEAUHKEY__@@PEBGPEAU_SYSTEMTIME@@@Z; GetTruncatedSystemTimeFromRegKey(HKEY__ *,ushort const *,_SYSTEMTIME *)
0x18038bf46  mov     ebx, eax
0x18038bf48  test    eax, eax
0x18038bf4a  jns     short loc_18038BF53
0x18038bf4c  mov     edx, 2F5h
0x18038bf51  jmp     short loc_18038BF0D
0x18038bf53  mov     [rbp+3Fh+lpString2], rdi
0x18038bf57  lea     rcx, [rbp+3Fh+lpString2]
0x18038bf5b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18038bf60  mov     qword ptr [rsp+0D0h+bIgnoreCase], rax; int
0x18038bf65  lea     r9, [rbp+3Fh+var_58]; struct _SYSTEMTIME *
0x18038bf69  mov     r8, [rbp+3Fh+pv]; unsigned __int16 *
0x18038bf6d  mov     rdx, r13; unsigned __int16 *
0x18038bf70  mov     rcx, [rbp+3Fh+var_88]; unsigned __int16 *
0x18038bf74  call    ?HashAssociation@@YAJPEBG00AEBU_SYSTEMTIME@@PEAPEAG@Z; HashAssociation(ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)
0x18038bf79  mov     ebx, eax
0x18038bf7b  test    eax, eax
0x18038bf7d  jns     short loc_18038BFAC
0x18038bf7f  mov     rcx, [rbp+47h]; this
0x18038bf83  mov     r9d, eax; char *
0x18038bf86  lea     r8, aOnecoreuapInte_14; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18038bf8d  mov     edx, 2F8h; void *
0x18038bf92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038bf97  nop
0x18038bf98  mov     rcx, [rbp+3Fh+lpString2]; pv
0x18038bf9c  test    rcx, rcx
0x18038bf9f  jz      short loc_18038BF21
0x18038bfa1  call    cs:__imp_CoTaskMemFree
0x18038bfa7  jmp     loc_18038BF21
0x18038bfac  mov     [rbp+3Fh+lpString1], rdi
0x18038bfb0  mov     rax, [rsi]
0x18038bfb3  mov     rbx, [rax+20h]
0x18038bfb7  lea     rcx, [rbp+3Fh+lpString1]
0x18038bfbb  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18038bfc0  mov     r9, rax
0x18038bfc3  lea     r8, aHash; "Hash"
0x18038bfca  lea     rdx, aUserchoice; "UserChoice"
0x18038bfd1  mov     rcx, rsi
0x18038bfd4  mov     rax, rbx
0x18038bfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038bfdc  mov     ebx, eax
0x18038bfde  test    eax, eax
0x18038bfe0  js      short loc_18038C049
0x18038bfe2  mov     [rsp+0D0h+bIgnoreCase], edi; bIgnoreCase
0x18038bfe6  or      edx, 0FFFFFFFFh; cchCount1
0x18038bfe9  mov     r9d, edx; cchCount2
0x18038bfec  mov     r8, [rbp+3Fh+lpString2]; lpString2
0x18038bff0  mov     rcx, [rbp+3Fh+lpString1]; lpString1
0x18038bff4  call    cs:__imp_CompareStringOrdinal
0x18038bffa  cmp     eax, 2
0x18038bffd  jnz     short loc_18038C049
0x18038bfff  mov     rax, [rbp+3Fh+pv]
0x18038c003  mov     [rbp+3Fh+pv], rdi
0x18038c007  mov     [r14], rax
0x18038c00a  mov     rcx, [rbp+3Fh+lpString1]; pv
0x18038c00e  test    rcx, rcx
0x18038c011  jz      short loc_18038C01A
0x18038c013  call    cs:__imp_CoTaskMemFree
0x18038c019  nop
0x18038c01a  mov     rcx, [rbp+3Fh+lpString2]; pv
0x18038c01e  test    rcx, rcx
0x18038c021  jz      short loc_18038C02A
0x18038c023  call    cs:__imp_CoTaskMemFree
0x18038c029  nop
0x18038c02a  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18038c02e  test    rcx, rcx
0x18038c031  jz      short loc_18038C03A
0x18038c033  call    cs:__imp_RegCloseKey
0x18038c039  nop
0x18038c03a  lea     rcx, [rbp+3Fh+var_70]
0x18038c03e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18038c043  nop
0x18038c044  jmp     loc_18038C291
0x18038c049  mov     rcx, [rbp+3Fh+lpString1]; pv
0x18038c04d  test    rcx, rcx
0x18038c050  jz      short loc_18038C059
0x18038c052  call    cs:__imp_CoTaskMemFree
0x18038c058  nop
0x18038c059  mov     rcx, [rbp+3Fh+lpString2]; pv
0x18038c05d  test    rcx, rcx
0x18038c060  jz      short loc_18038C069
0x18038c062  call    cs:__imp_CoTaskMemFree
0x18038c068  nop
0x18038c069  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18038c06d  test    rcx, rcx
0x18038c070  jz      short loc_18038C079
0x18038c072  call    cs:__imp_RegCloseKey
0x18038c078  nop
0x18038c079  lea     rcx, [rbp+3Fh+var_70]
0x18038c07d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18038c082  nop
0x18038c083  jmp     loc_18038C2DE
0x18038c088  lea     rcx, [rbp+3Fh+pv]
0x18038c08c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18038c091  mov     r9, rax
0x18038c094  lea     r8, aProgid_1; "ProgId"
0x18038c09b  lea     rdx, aUserchoicelate_0; "UserChoiceLatest\\ProgId"
0x18038c0a2  mov     rcx, rsi
0x18038c0a5  mov     rax, rbx
0x18038c0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038c0ad  mov     ebx, eax
0x18038c0af  test    eax, eax
0x18038c0b1  jns     short loc_18038C0B8
0x18038c0b3  jmp     loc_18038BE69
0x18038c0b8  mov     [rbp+3Fh+var_70], rdi
0x18038c0bc  mov     rax, [rsi]
0x18038c0bf  mov     rbx, [rax]
0x18038c0c2  lea     rcx, [rbp+3Fh+var_70]
0x18038c0c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18038c0cb  lea     r8, [rbp+3Fh+var_70]
0x18038c0cf  lea     rdx, _GUID_d960050c_f4e1_4294_ac4b_598913605923
0x18038c0d6  mov     rcx, rsi
0x18038c0d9  mov     rax, rbx
0x18038c0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038c0e1  mov     ebx, eax
0x18038c0e3  test    eax, eax
0x18038c0e5  jns     short loc_18038C10B
0x18038c0e7  mov     rcx, [rbp+47h]; this
0x18038c0eb  mov     r9d, eax; char *
0x18038c0ee  lea     r8, aOnecoreuapInte_14; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18038c0f5  mov     edx, 308h; void *
0x18038c0fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038c0ff  nop
0x18038c100  lea     rcx, [rbp+3Fh+var_70]
0x18038c104  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18038c109  jmp     short loc_18038C0B3
0x18038c10b  mov     [rbp+3Fh+hKey], rdi
0x18038c10f  mov     rdi, [rbp+3Fh+var_70]
0x18038c113  mov     rax, [rdi]
0x18038c116  mov     rbx, [rax+20h]
0x18038c11a  xor     edx, edx
0x18038c11c  lea     rcx, [rbp+3Fh+hKey]
0x18038c120  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18038c125  lea     r8, [rbp+3Fh+hKey]
0x18038c129  mov     edx, 20019h
0x18038c12e  mov     rcx, rdi
0x18038c131  mov     rax, rbx
0x18038c134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038c139  mov     ebx, eax
0x18038c13b  xor     edi, edi
0x18038c13d  test    eax, eax
0x18038c13f  jns     short loc_18038C16B
0x18038c141  mov     edx, 30Bh; void *
0x18038c146  lea     r8, aOnecoreuapInte_14; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18038c14d  mov     r9d, ebx; char *
0x18038c150  mov     rcx, [rbp+47h]; this
0x18038c154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038c159  nop
0x18038c15a  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18038c15e  test    rcx, rcx
0x18038c161  jz      short loc_18038C100
0x18038c163  call    cs:__imp_RegCloseKey
0x18038c169  jmp     short loc_18038C100
0x18038c16b  xorps   xmm0, xmm0
0x18038c16e  movups  xmmword ptr [rbp+3Fh+var_58.wYear], xmm0
0x18038c172  lea     r8, [rbp+3Fh+var_58]; struct _SYSTEMTIME *
0x18038c176  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18038c17a  call    ?GetSystemTimeFromRegKey@@YAJPEAUHKEY__@@PEBGPEAU_SYSTEMTIME@@@Z; GetSystemTimeFromRegKey(HKEY__ *,ushort const *,_SYSTEMTIME *)
0x18038c17f  mov     ebx, eax
0x18038c181  test    eax, eax
0x18038c183  jns     short loc_18038C18C
0x18038c185  mov     edx, 30Eh
0x18038c18a  jmp     short loc_18038C146
0x18038c18c  mov     [rbp+3Fh+lpString2], rdi
0x18038c190  lea     rcx, [rbp+3Fh+lpString2]
0x18038c194  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18038c199  mov     r8, [rbp+3Fh+pv]
0x18038c19d  mov     [rsp+0D0h+var_A0], rax; unsigned __int16 **
0x18038c1a2  lea     rax, [rbp+3Fh+var_58]
0x18038c1a6  mov     [rsp+0D0h+var_A8], rax; struct _SYSTEMTIME *
0x18038c1ab  mov     qword ptr [rsp+0D0h+bIgnoreCase], r8; int
0x18038c1b0  mov     r9, r13; unsigned __int16 *
0x18038c1b3  mov     r8, [rbp+3Fh+var_88]; unsigned __int16 *
0x18038c1b7  mov     rdx, r12; unsigned __int16 *
0x18038c1ba  mov     ecx, r15d; unsigned int
0x18038c1bd  call    ?HashAssociationRotation@@YAJIPEBG000AEBU_SYSTEMTIME@@PEAPEAG@Z; HashAssociationRotation(uint,ushort const *,ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)
0x18038c1c2  mov     ebx, eax
0x18038c1c4  test    eax, eax
0x18038c1c6  jns     short loc_18038C1F9
0x18038c1c8  mov     rcx, [rbp+47h]; this
0x18038c1cc  mov     r9d, eax; char *
0x18038c1cf  lea     r8, aOnecoreuapInte_14; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18038c1d6  mov     edx, 311h; void *
0x18038c1db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038c1e0  nop
0x18038c1e1  mov     rcx, [rbp+3Fh+lpString2]; pv
0x18038c1e5  test    rcx, rcx
0x18038c1e8  jz      loc_18038C15A
0x18038c1ee  call    cs:__imp_CoTaskMemFree
0x18038c1f4  jmp     loc_18038C15A
0x18038c1f9  mov     [rbp+3Fh+lpString1], rdi
0x18038c1fd  mov     rax, [rsi]
0x18038c200  mov     rbx, [rax+20h]
0x18038c204  lea     rcx, [rbp+3Fh+lpString1]
0x18038c208  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18038c20d  mov     r9, rax
0x18038c210  lea     r8, aHash; "Hash"
0x18038c217  lea     rdx, aUserchoicelate; "UserChoiceLatest"
0x18038c21e  mov     rcx, rsi
0x18038c221  mov     rax, rbx
  ... truncated ...
```
