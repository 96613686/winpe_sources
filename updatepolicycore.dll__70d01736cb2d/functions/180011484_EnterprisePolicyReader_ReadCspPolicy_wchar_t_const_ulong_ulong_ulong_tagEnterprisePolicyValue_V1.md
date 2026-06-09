# EnterprisePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagEnterprisePolicyValue_V1 *)

- ea: `0x180011484`
- end: `0x18001169a`
- name: `?ReadCspPolicy@EnterprisePolicyReader@@CAJPEB_WKKKPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, unsigned int, unsigned int, struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010c1c`

## callees

- `0x18000e310`
- `0x18000fd94`
- `0x180011484`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011508`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011525`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011525`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadCspPolicy(
        const wchar_t *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        struct tagEnterprisePolicyValue_V1 *a5)
{
  int v8; // ebx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v13; // rbx
  int (__fastcall *v14)(__int64, PVOID, PVOID, __int64 *); // r13
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
  v29 = 0;
  v27 = 0;
  v25[0] = 0;
  v28 = 0;
  if ( !a5 )
  {
    v8 = -2147467261;
    goto LABEL_19;
  }
  *((_DWORD *)a5 + 1) = 0;
  v29 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Management.Policies.NamedPolicy", 0x27u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x180011699LL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_7f793be7_76c4_4058_8cad_67662cd05f0d, &v29) < 0 )
    goto LABEL_5;
  v13 = v29;
  v14 = *(int (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v29 + 48LL);
  v15 = v27;
  v27 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v24, v12)[1].Reserved.Reserved1;
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v23,
          (const WCHAR **)&EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName,
          v17);
  if ( v14(v13, v18[1].Reserved.Reserved1, Reserved1, &v27) < 0 )
    goto LABEL_5;
  v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 72LL))(v27, v25);
  if ( v8 < 0 )
    goto LABEL_5;
  if ( !v25[0] )
    goto LABEL_6;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 64LL))(v27, &v28);
  if ( v8 < 0 )
  {
LABEL_5:
    v8 = 0;
LABEL_6:
    *((_DWORD *)a5 + 1) = 0;
    goto LABEL_19;
  }
  if ( v28 != 3 )
    goto LABEL_6;
  *((_DWORD *)a5 + 1) = 1;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 112LL))(v27, &v26);
  if ( v8 < 0 || (v19 = v26, v26 < a3) || v26 > a4 )
  {
    v19 = a2;
    v26 = a2;
    v8 = 0;
  }
  *((_DWORD *)a5 + 6) = v19;
  *((_WORD *)a5 + 8) = 3;
  *((_DWORD *)a5 + 2) = 2;
LABEL_19:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011484  mov     rax, rsp
0x180011487  mov     [rax+10h], rbx
0x18001148b  mov     [rax+18h], rsi
0x18001148f  mov     [rax+20h], rdi
0x180011493  push    rbp
0x180011494  push    r12
0x180011496  push    r13
0x180011498  push    r14
0x18001149a  push    r15
0x18001149c  lea     rbp, [rax-57h]
0x1800114a0  sub     rsp, 0A0h
0x1800114a7  mov     rax, cs:__security_cookie
0x1800114ae  xor     rax, rsp
0x1800114b1  mov     [rbp+4Fh+var_28], rax
0x1800114b5  mov     r15d, r9d
0x1800114b8  mov     r14d, r8d
0x1800114bb  mov     r12d, edx
0x1800114be  mov     [rbp+4Fh+var_50], rcx
0x1800114c2  mov     rsi, [rbp+4Fh+arg_20]
0x1800114c6  xor     edi, edi
0x1800114c8  mov     [rbp+4Fh+var_44], edi
0x1800114cb  mov     [rbp+4Fh+var_30], rdi
0x1800114cf  mov     [rbp+4Fh+var_40], rdi
0x1800114d3  mov     [rbp+4Fh+var_48], dil
0x1800114d7  mov     [rbp+4Fh+var_38], edi
0x1800114da  test    rsi, rsi
0x1800114dd  jnz     short loc_1800114E9
0x1800114df  mov     ebx, 80004003h
0x1800114e4  jmp     loc_180011637
0x1800114e9  mov     [rsi+4], edi
0x1800114ec  mov     [rbp+4Fh+var_30], rdi
0x1800114f0  mov     [rbp+4Fh+string], rdi
0x1800114f4  lea     r9, [rbp+4Fh+string]; string
0x1800114f8  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800114fc  mov     edx, 27h ; '''; length
0x180011501  lea     rcx, ?RuntimeClass_Windows_Management_Policies_NamedPolicy@@3QB_WB; "Windows.Management.Policies.NamedPolicy"
0x180011508  call    cs:__imp_WindowsCreateStringReference
0x18001150e  test    eax, eax
0x180011510  js      loc_180011692
0x180011516  lea     r8, [rbp+4Fh+var_30]
0x18001151a  lea     rdx, _GUID_7f793be7_76c4_4058_8cad_67662cd05f0d
0x180011521  mov     rcx, [rbp+4Fh+string]
0x180011525  call    cs:__imp_RoGetActivationFactory
0x18001152b  test    eax, eax
0x18001152d  jns     short loc_180011539
0x18001152f  mov     ebx, edi
0x180011531  mov     [rsi+4], edi
0x180011534  jmp     loc_180011637
0x180011539  mov     rbx, [rbp+4Fh+var_30]
0x18001153d  mov     rax, [rbx]
0x180011540  mov     r13, [rax+30h]
0x180011544  mov     rcx, [rbp+4Fh+var_40]
0x180011548  mov     [rbp+4Fh+var_40], rdi
0x18001154c  test    rcx, rcx
0x18001154f  jz      short loc_18001155E
0x180011551  mov     rax, [rcx]
0x180011554  mov     rax, [rax+10h]
0x180011558  call    _guard_dispatch_icall
0x18001155d  nop
0x18001155e  lea     rdx, [rbp+4Fh+var_50]
0x180011562  lea     rcx, [rbp+4Fh+hstringHeader]
0x180011566  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001156b  nop
0x18001156c  mov     rdi, [rax+18h]
0x180011570  lea     rdx, ?c_szPolicy_CspUpdateAreaName@EnterprisePolicyReader@@2QEB_WEB; wchar_t const * const EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName
0x180011577  lea     rcx, [rbp+4Fh+var_70]
0x18001157b  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180011580  nop
0x180011581  lea     r9, [rbp+4Fh+var_40]
0x180011585  mov     r8, rdi
0x180011588  mov     rdx, [rax+18h]
0x18001158c  mov     rcx, rbx
0x18001158f  mov     rax, r13
0x180011592  call    _guard_dispatch_icall
0x180011597  nop
0x180011598  xor     edi, edi
0x18001159a  test    eax, eax
0x18001159c  js      short loc_18001152F
0x18001159e  mov     rcx, [rbp+4Fh+var_40]
0x1800115a2  mov     rax, [rcx]
0x1800115a5  lea     rdx, [rbp+4Fh+var_48]
0x1800115a9  mov     rax, [rax+48h]
0x1800115ad  call    _guard_dispatch_icall
0x1800115b2  mov     ebx, eax
0x1800115b4  test    eax, eax
0x1800115b6  js      loc_18001152F
0x1800115bc  cmp     [rbp+4Fh+var_48], dil
0x1800115c0  jz      loc_180011531
0x1800115c6  mov     rcx, [rbp+4Fh+var_40]
0x1800115ca  mov     rax, [rcx]
0x1800115cd  lea     rdx, [rbp+4Fh+var_38]
0x1800115d1  mov     rax, [rax+40h]
0x1800115d5  call    _guard_dispatch_icall
0x1800115da  mov     ebx, eax
0x1800115dc  test    eax, eax
0x1800115de  js      loc_18001152F
0x1800115e4  lea     r13d, [rdi+3]
0x1800115e8  cmp     [rbp+4Fh+var_38], r13d
0x1800115ec  jnz     loc_180011531
0x1800115f2  mov     dword ptr [rsi+4], 1
0x1800115f9  mov     rcx, [rbp+4Fh+var_40]
0x1800115fd  mov     rax, [rcx]
0x180011600  lea     rdx, [rbp+4Fh+var_44]
0x180011604  mov     rax, [rax+70h]
0x180011608  call    _guard_dispatch_icall
0x18001160d  mov     ebx, eax
0x18001160f  test    eax, eax
0x180011611  js      short loc_180011620
0x180011613  mov     eax, [rbp+4Fh+var_44]
0x180011616  cmp     eax, r14d
0x180011619  jb      short loc_180011620
0x18001161b  cmp     eax, r15d
0x18001161e  jbe     short loc_180011628
0x180011620  mov     eax, r12d
0x180011623  mov     [rbp+4Fh+var_44], eax
0x180011626  mov     ebx, edi
0x180011628  mov     [rsi+18h], eax
0x18001162b  mov     [rsi+10h], r13w
0x180011630  mov     dword ptr [rsi+8], 2
0x180011637  mov     rcx, [rbp+4Fh+var_40]
0x18001163b  test    rcx, rcx
0x18001163e  jz      short loc_18001164D
0x180011640  mov     rax, [rcx]
0x180011643  mov     rax, [rax+10h]
0x180011647  call    _guard_dispatch_icall
0x18001164c  nop
0x18001164d  mov     rcx, [rbp+4Fh+var_30]
0x180011651  test    rcx, rcx
0x180011654  jz      short loc_180011663
0x180011656  mov     rax, [rcx]
0x180011659  mov     rax, [rax+10h]
0x18001165d  call    _guard_dispatch_icall
0x180011662  nop
0x180011663  mov     eax, ebx
0x180011665  mov     rcx, [rbp+4Fh+var_28]
0x180011669  xor     rcx, rsp; StackCookie
0x18001166c  call    __security_check_cookie
0x180011671  lea     r11, [rsp+0C0h+var_20]
0x180011679  mov     rbx, [r11+38h]
0x18001167d  mov     rsi, [r11+40h]
0x180011681  mov     rdi, [r11+48h]
0x180011685  mov     rsp, r11
0x180011688  pop     r15
0x18001168a  pop     r14
0x18001168c  pop     r13
0x18001168e  pop     r12
0x180011690  pop     rbp
0x180011691  retn
0x180011692  mov     ecx, eax; this
0x180011694  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
