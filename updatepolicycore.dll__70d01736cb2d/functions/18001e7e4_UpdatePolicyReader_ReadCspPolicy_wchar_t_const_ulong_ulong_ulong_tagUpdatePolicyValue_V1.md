# UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)

- ea: `0x18001e7e4`
- end: `0x18001e9e2`
- name: `?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, unsigned int, unsigned int, struct tagUpdatePolicyValue_V1 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ccf0`
- `0x18001d380`
- `0x18001d534`

## callees

- `0x18000e310`
- `0x18000fd94`
- `0x18001e7e4`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e850`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e86d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e86d`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadCspPolicy(
        const wchar_t *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        struct tagUpdatePolicyValue_V1 *a5)
{
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  int v12; // ebx
  __int64 v13; // rbx
  int (__fastcall *v14)(__int64, PVOID, PVOID, __int64 *); // r14
  __int64 v15; // rcx
  PVOID Reserved1; // rdi
  unsigned int v17; // r8d
  HSTRING_HEADER *v18; // rax
  unsigned int v19; // eax
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+50h] [rbp-29h] BYREF
  HSTRING_HEADER v23; // [rsp+58h] [rbp-21h] BYREF
  const WCHAR *v24; // [rsp+78h] [rbp-1h] BYREF
  _BYTE v25[4]; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v26; // [rsp+84h] [rbp+Bh] BYREF
  __int64 v27; // [rsp+88h] [rbp+Fh] BYREF
  int v28; // [rsp+90h] [rbp+17h] BYREF
  __int64 v29; // [rsp+98h] [rbp+1Fh] BYREF

  v24 = a1;
  v26 = 0;
  v27 = 0;
  v25[0] = 0;
  v28 = 0;
  v29 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Management.Policies.NamedPolicy", 0x27u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    JUMPOUT(0x18001E9E1LL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_7f793be7_76c4_4058_8cad_67662cd05f0d, &v29) < 0 )
    goto LABEL_3;
  v13 = v29;
  v14 = *(int (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v29 + 48LL);
  v15 = v27;
  v27 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v24, v11)[1].Reserved.Reserved1;
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v23,
          (const WCHAR **)&UpdatePolicyReader::c_szPolicy_CspUpdateAreaName,
          v17);
  if ( v14(v13, v18[1].Reserved.Reserved1, Reserved1, &v27) < 0 )
    goto LABEL_3;
  v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 72LL))(v27, v25);
  if ( v12 < 0 )
    goto LABEL_3;
  if ( !v25[0] )
    goto LABEL_4;
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 64LL))(v27, &v28);
  if ( v12 < 0 )
  {
LABEL_3:
    v12 = 0;
LABEL_4:
    *((_DWORD *)a5 + 1) = 0;
    goto LABEL_17;
  }
  if ( v28 != 3 )
    goto LABEL_4;
  *((_DWORD *)a5 + 1) = 1;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 112LL))(v27, &v26);
  if ( v12 < 0 || (v19 = v26, v26 < a3) || v26 > a4 )
  {
    v19 = a2;
    v26 = a2;
    v12 = 0;
  }
  *((_DWORD *)a5 + 6) = v19;
  *((_WORD *)a5 + 8) = 3;
  *((_DWORD *)a5 + 2) = 2;
LABEL_17:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001e7e4  mov     rax, rsp
0x18001e7e7  mov     [rax+10h], rbx
0x18001e7eb  mov     [rax+18h], rsi
0x18001e7ef  mov     [rax+20h], rdi
0x18001e7f3  push    rbp
0x18001e7f4  push    r12
0x18001e7f6  push    r13
0x18001e7f8  push    r14
0x18001e7fa  push    r15
0x18001e7fc  lea     rbp, [rax-57h]
0x18001e800  sub     rsp, 0A0h
0x18001e807  mov     rax, cs:__security_cookie
0x18001e80e  xor     rax, rsp
0x18001e811  mov     [rbp+4Fh+var_28], rax
0x18001e815  mov     r12d, r9d
0x18001e818  mov     r15d, r8d
0x18001e81b  mov     r13d, edx
0x18001e81e  mov     [rbp+4Fh+var_50], rcx
0x18001e822  mov     rsi, [rbp+4Fh+arg_20]
0x18001e826  xor     edi, edi
0x18001e828  mov     [rbp+4Fh+var_44], edi
0x18001e82b  mov     [rbp+4Fh+var_40], rdi
0x18001e82f  mov     [rbp+4Fh+var_48], dil
0x18001e833  mov     [rbp+4Fh+var_38], edi
0x18001e836  mov     [rbp+4Fh+var_30], rdi
0x18001e83a  mov     [rbp+4Fh+string], rdi
0x18001e83e  lea     r9, [rbp+4Fh+string]; string
0x18001e842  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x18001e846  lea     edx, [rdi+27h]; length
0x18001e849  lea     rcx, ?RuntimeClass_Windows_Management_Policies_NamedPolicy@@3QB_WB; "Windows.Management.Policies.NamedPolicy"
0x18001e850  call    cs:__imp_WindowsCreateStringReference
0x18001e856  test    eax, eax
0x18001e858  js      loc_18001E9DA
0x18001e85e  lea     r8, [rbp+4Fh+var_30]
0x18001e862  lea     rdx, _GUID_7f793be7_76c4_4058_8cad_67662cd05f0d
0x18001e869  mov     rcx, [rbp+4Fh+string]
0x18001e86d  call    cs:__imp_RoGetActivationFactory
0x18001e873  test    eax, eax
0x18001e875  jns     short loc_18001E881
0x18001e877  mov     ebx, edi
0x18001e879  mov     [rsi+4], edi
0x18001e87c  jmp     loc_18001E97F
0x18001e881  mov     rbx, [rbp+4Fh+var_30]
0x18001e885  mov     rax, [rbx]
0x18001e888  mov     r14, [rax+30h]
0x18001e88c  mov     rcx, [rbp+4Fh+var_40]
0x18001e890  mov     [rbp+4Fh+var_40], rdi
0x18001e894  test    rcx, rcx
0x18001e897  jz      short loc_18001E8A6
0x18001e899  mov     rax, [rcx]
0x18001e89c  mov     rax, [rax+10h]
0x18001e8a0  call    _guard_dispatch_icall
0x18001e8a5  nop
0x18001e8a6  lea     rdx, [rbp+4Fh+var_50]
0x18001e8aa  lea     rcx, [rbp+4Fh+hstringHeader]
0x18001e8ae  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001e8b3  nop
0x18001e8b4  mov     rdi, [rax+18h]
0x18001e8b8  lea     rdx, ?c_szPolicy_CspUpdateAreaName@UpdatePolicyReader@@2QEB_WEB; wchar_t const * const UpdatePolicyReader::c_szPolicy_CspUpdateAreaName
0x18001e8bf  lea     rcx, [rbp+4Fh+var_70]
0x18001e8c3  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001e8c8  nop
0x18001e8c9  lea     r9, [rbp+4Fh+var_40]
0x18001e8cd  mov     r8, rdi
0x18001e8d0  mov     rdx, [rax+18h]
0x18001e8d4  mov     rcx, rbx
0x18001e8d7  mov     rax, r14
0x18001e8da  call    _guard_dispatch_icall
0x18001e8df  nop
0x18001e8e0  xor     edi, edi
0x18001e8e2  test    eax, eax
0x18001e8e4  js      short loc_18001E877
0x18001e8e6  mov     rcx, [rbp+4Fh+var_40]
0x18001e8ea  mov     rax, [rcx]
0x18001e8ed  lea     rdx, [rbp+4Fh+var_48]
0x18001e8f1  mov     rax, [rax+48h]
0x18001e8f5  call    _guard_dispatch_icall
0x18001e8fa  mov     ebx, eax
0x18001e8fc  test    eax, eax
0x18001e8fe  js      loc_18001E877
0x18001e904  cmp     [rbp+4Fh+var_48], dil
0x18001e908  jz      loc_18001E879
0x18001e90e  mov     rcx, [rbp+4Fh+var_40]
0x18001e912  mov     rax, [rcx]
0x18001e915  lea     rdx, [rbp+4Fh+var_38]
0x18001e919  mov     rax, [rax+40h]
0x18001e91d  call    _guard_dispatch_icall
0x18001e922  mov     ebx, eax
0x18001e924  test    eax, eax
0x18001e926  js      loc_18001E877
0x18001e92c  lea     r14d, [rdi+3]
0x18001e930  cmp     [rbp+4Fh+var_38], r14d
0x18001e934  jnz     loc_18001E879
0x18001e93a  mov     dword ptr [rsi+4], 1
0x18001e941  mov     rcx, [rbp+4Fh+var_40]
0x18001e945  mov     rax, [rcx]
0x18001e948  lea     rdx, [rbp+4Fh+var_44]
0x18001e94c  mov     rax, [rax+70h]
0x18001e950  call    _guard_dispatch_icall
0x18001e955  mov     ebx, eax
0x18001e957  test    eax, eax
0x18001e959  js      short loc_18001E968
0x18001e95b  mov     eax, [rbp+4Fh+var_44]
0x18001e95e  cmp     eax, r15d
0x18001e961  jb      short loc_18001E968
0x18001e963  cmp     eax, r12d
0x18001e966  jbe     short loc_18001E970
0x18001e968  mov     eax, r13d
0x18001e96b  mov     [rbp+4Fh+var_44], eax
0x18001e96e  mov     ebx, edi
0x18001e970  mov     [rsi+18h], eax
0x18001e973  mov     [rsi+10h], r14w
0x18001e978  mov     dword ptr [rsi+8], 2
0x18001e97f  mov     rcx, [rbp+4Fh+var_40]
0x18001e983  test    rcx, rcx
0x18001e986  jz      short loc_18001E995
0x18001e988  mov     rax, [rcx]
0x18001e98b  mov     rax, [rax+10h]
0x18001e98f  call    _guard_dispatch_icall
0x18001e994  nop
0x18001e995  mov     rcx, [rbp+4Fh+var_30]
0x18001e999  test    rcx, rcx
0x18001e99c  jz      short loc_18001E9AB
0x18001e99e  mov     rax, [rcx]
0x18001e9a1  mov     rax, [rax+10h]
0x18001e9a5  call    _guard_dispatch_icall
0x18001e9aa  nop
0x18001e9ab  mov     eax, ebx
0x18001e9ad  mov     rcx, [rbp+4Fh+var_28]
0x18001e9b1  xor     rcx, rsp; StackCookie
0x18001e9b4  call    __security_check_cookie
0x18001e9b9  lea     r11, [rsp+0C0h+var_20]
0x18001e9c1  mov     rbx, [r11+38h]
0x18001e9c5  mov     rsi, [r11+40h]
0x18001e9c9  mov     rdi, [r11+48h]
0x18001e9cd  mov     rsp, r11
0x18001e9d0  pop     r15
0x18001e9d2  pop     r14
0x18001e9d4  pop     r13
0x18001e9d6  pop     r12
0x18001e9d8  pop     rbp
0x18001e9d9  retn
0x18001e9da  mov     ecx, eax; this
0x18001e9dc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
