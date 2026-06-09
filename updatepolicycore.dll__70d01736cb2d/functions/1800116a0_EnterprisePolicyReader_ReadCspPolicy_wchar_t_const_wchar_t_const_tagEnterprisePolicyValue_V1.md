# EnterprisePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagEnterprisePolicyValue_V1 *)

- ea: `0x1800116a0`
- end: `0x1800118cb`
- name: `?ReadCspPolicy@EnterprisePolicyReader@@CAJPEB_W0PEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010c1c`

## callees

- `0x18000e310`
- `0x18000fd94`
- `0x1800116a0`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011845`
- `OLEAUT32!__imp_SysAllocString` at `0x180011845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001170f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001170f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001180e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001180e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011898`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001172c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001172c`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadCspPolicy(
        const wchar_t *a1,
        const wchar_t *a2,
        struct tagEnterprisePolicyValue_V1 *a3)
{
  int v4; // ebx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  __int64 v9; // rbx
  int (__fastcall *v10)(__int64, PVOID, PVOID, __int64 *); // r14
  __int64 v11; // rcx
  PVOID Reserved1; // rdi
  unsigned int v13; // r8d
  HSTRING_HEADER *v14; // rax
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rdi
  const OLECHAR *StringRawBuffer; // rcx
  BSTR v18; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  HSTRING_HEADER v22; // [rsp+50h] [rbp-29h] BYREF
  const WCHAR *v23; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v24[8]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h] BYREF
  int v26; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING v27; // [rsp+90h] [rbp+17h] BYREF
  __int64 v28; // [rsp+98h] [rbp+1Fh] BYREF

  v23 = a1;
  v27 = 0;
  v28 = 0;
  v25 = 0;
  v24[0] = 0;
  v26 = 0;
  if ( !a3 )
  {
    v4 = -2147467261;
    goto LABEL_20;
  }
  v28 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Management.Policies.NamedPolicy", 0x27u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    JUMPOUT(0x1800118CALL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_7f793be7_76c4_4058_8cad_67662cd05f0d, &v28) < 0 )
    goto LABEL_5;
  v9 = v28;
  v10 = *(int (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v28 + 48LL);
  v11 = v25;
  v25 = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v23, v8)[1].Reserved.Reserved1;
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v22,
          (const WCHAR **)&EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName,
          v13);
  if ( v10(v9, v14[1].Reserved.Reserved1, Reserved1, &v25) < 0 )
    goto LABEL_5;
  v4 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 72LL))(v25, v24);
  if ( v4 < 0 )
    goto LABEL_5;
  if ( !v24[0] )
    goto LABEL_6;
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 64LL))(v25, &v26);
  if ( v4 < 0 )
  {
LABEL_5:
    v4 = 0;
LABEL_6:
    *((_DWORD *)a3 + 1) = 0;
    goto LABEL_20;
  }
  if ( v26 != 5 )
    goto LABEL_6;
  *((_DWORD *)a3 + 1) = 1;
  v15 = v25;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 128LL);
  WindowsDeleteString(v27);
  v27 = 0;
  v4 = v16(v15, &v27);
  if ( v4 < 0 )
    StringRawBuffer = &psz;
  else
    StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
  v18 = SysAllocString(StringRawBuffer);
  *((_QWORD *)a3 + 3) = v18;
  if ( v18 )
  {
    *((_WORD *)a3 + 8) = 8;
    *((_DWORD *)a3 + 2) = 2;
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_20:
  if ( v25 )
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v25 + 16LL))(v25, a2);
  if ( v28 )
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v28 + 16LL))(v28, a2);
  WindowsDeleteString(v27);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800116a0  mov     [rsp-8+arg_8], rbx
0x1800116a5  push    rbp
0x1800116a6  push    rsi
0x1800116a7  push    rdi
0x1800116a8  push    r14
0x1800116aa  push    r15
0x1800116ac  lea     rbp, [rsp-37h]
0x1800116b1  sub     rsp, 0B0h
0x1800116b8  mov     rax, cs:__security_cookie
0x1800116bf  xor     rax, rsp
0x1800116c2  mov     [rbp+57h+var_30], rax
0x1800116c6  mov     rsi, r8
0x1800116c9  mov     [rbp+57h+var_60], rcx
0x1800116cd  xor     r15d, r15d
0x1800116d0  mov     [rbp+57h+var_40], r15
0x1800116d4  mov     [rbp+57h+var_38], r15
0x1800116d8  mov     [rbp+57h+var_50], r15
0x1800116dc  mov     [rbp+57h+var_58], r15b
0x1800116e0  mov     [rbp+57h+var_48], r15d
0x1800116e4  test    r8, r8
0x1800116e7  jnz     short loc_1800116F3
0x1800116e9  mov     ebx, 80004003h
0x1800116ee  jmp     loc_180011868
0x1800116f3  mov     [rbp+57h+var_38], r15
0x1800116f7  mov     [rbp+57h+string], r15
0x1800116fb  lea     r9, [rbp+57h+string]; string
0x1800116ff  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180011703  mov     edx, 27h ; '''; length
0x180011708  lea     rcx, ?RuntimeClass_Windows_Management_Policies_NamedPolicy@@3QB_WB; "Windows.Management.Policies.NamedPolicy"
0x18001170f  call    cs:__imp_WindowsCreateStringReference
0x180011715  test    eax, eax
0x180011717  js      loc_1800118C3
0x18001171d  lea     r8, [rbp+57h+var_38]
0x180011721  lea     rdx, _GUID_7f793be7_76c4_4058_8cad_67662cd05f0d
0x180011728  mov     rcx, [rbp+57h+string]
0x18001172c  call    cs:__imp_RoGetActivationFactory
0x180011732  test    eax, eax
0x180011734  jns     short loc_180011742
0x180011736  mov     ebx, r15d
0x180011739  mov     [rsi+4], r15d
0x18001173d  jmp     loc_180011868
0x180011742  mov     rbx, [rbp+57h+var_38]
0x180011746  mov     rax, [rbx]
0x180011749  mov     r14, [rax+30h]
0x18001174d  mov     rcx, [rbp+57h+var_50]
0x180011751  mov     [rbp+57h+var_50], r15
0x180011755  test    rcx, rcx
0x180011758  jz      short loc_180011767
0x18001175a  mov     rax, [rcx]
0x18001175d  mov     rax, [rax+10h]
0x180011761  call    _guard_dispatch_icall
0x180011766  nop
0x180011767  lea     rdx, [rbp+57h+var_60]
0x18001176b  lea     rcx, [rbp+57h+hstringHeader]
0x18001176f  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180011774  nop
0x180011775  mov     rdi, [rax+18h]
0x180011779  lea     rdx, ?c_szPolicy_CspUpdateAreaName@EnterprisePolicyReader@@2QEB_WEB; wchar_t const * const EnterprisePolicyReader::c_szPolicy_CspUpdateAreaName
0x180011780  lea     rcx, [rbp+57h+var_80]
0x180011784  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180011789  nop
0x18001178a  lea     r9, [rbp+57h+var_50]
0x18001178e  mov     r8, rdi
0x180011791  mov     rdx, [rax+18h]
0x180011795  mov     rcx, rbx
0x180011798  mov     rax, r14
0x18001179b  call    _guard_dispatch_icall
0x1800117a0  nop
0x1800117a1  test    eax, eax
0x1800117a3  js      short loc_180011736
0x1800117a5  mov     rcx, [rbp+57h+var_50]
0x1800117a9  mov     rax, [rcx]
0x1800117ac  lea     rdx, [rbp+57h+var_58]
0x1800117b0  mov     rax, [rax+48h]
0x1800117b4  call    _guard_dispatch_icall
0x1800117b9  mov     ebx, eax
0x1800117bb  test    eax, eax
0x1800117bd  js      loc_180011736
0x1800117c3  cmp     [rbp+57h+var_58], r15b
0x1800117c7  jz      loc_180011739
0x1800117cd  mov     rcx, [rbp+57h+var_50]
0x1800117d1  mov     rax, [rcx]
0x1800117d4  lea     rdx, [rbp+57h+var_48]
0x1800117d8  mov     rax, [rax+40h]
0x1800117dc  call    _guard_dispatch_icall
0x1800117e1  mov     ebx, eax
0x1800117e3  test    eax, eax
0x1800117e5  js      loc_180011736
0x1800117eb  cmp     [rbp+57h+var_48], 5
0x1800117ef  jnz     loc_180011739
0x1800117f5  mov     dword ptr [rsi+4], 1
0x1800117fc  mov     rbx, [rbp+57h+var_50]
0x180011800  mov     rax, [rbx]
0x180011803  mov     rdi, [rax+80h]
0x18001180a  mov     rcx, [rbp+57h+var_40]; string
0x18001180e  call    cs:__imp_WindowsDeleteString
0x180011814  mov     [rbp+57h+var_40], r15
0x180011818  lea     rdx, [rbp+57h+var_40]
0x18001181c  mov     rcx, rbx
0x18001181f  mov     rax, rdi
0x180011822  call    _guard_dispatch_icall
0x180011827  mov     ebx, eax
0x180011829  test    eax, eax
0x18001182b  js      short loc_18001183E
0x18001182d  xor     edx, edx; length
0x18001182f  mov     rcx, [rbp+57h+var_40]; string
0x180011833  call    cs:__imp_WindowsGetStringRawBuffer
0x180011839  mov     rcx, rax
0x18001183c  jmp     short loc_180011845
0x18001183e  lea     rcx, psz; psz
0x180011845  call    cs:__imp_SysAllocString
0x18001184b  mov     [rsi+18h], rax
0x18001184f  test    rax, rax
0x180011852  jnz     short loc_18001185B
0x180011854  mov     ebx, 8007000Eh
0x180011859  jmp     short loc_180011868
0x18001185b  mov     word ptr [rsi+10h], 8
0x180011861  mov     dword ptr [rsi+8], 2
0x180011868  mov     rcx, [rbp+57h+var_50]
0x18001186c  test    rcx, rcx
0x18001186f  jz      short loc_18001187E
0x180011871  mov     rax, [rcx]
0x180011874  mov     rax, [rax+10h]
0x180011878  call    _guard_dispatch_icall
0x18001187d  nop
0x18001187e  mov     rcx, [rbp+57h+var_38]
0x180011882  test    rcx, rcx
0x180011885  jz      short loc_180011894
0x180011887  mov     rax, [rcx]
0x18001188a  mov     rax, [rax+10h]
0x18001188e  call    _guard_dispatch_icall
0x180011893  nop
0x180011894  mov     rcx, [rbp+57h+var_40]; string
0x180011898  call    cs:__imp_WindowsDeleteString
0x18001189e  mov     eax, ebx
0x1800118a0  mov     rcx, [rbp+57h+var_30]
0x1800118a4  xor     rcx, rsp; StackCookie
0x1800118a7  call    __security_check_cookie
0x1800118ac  mov     rbx, [rsp+0D0h+arg_8]
0x1800118b4  add     rsp, 0B0h
0x1800118bb  pop     r15
0x1800118bd  pop     r14
0x1800118bf  pop     rdi
0x1800118c0  pop     rsi
0x1800118c1  pop     rbp
0x1800118c2  retn
0x1800118c3  mov     ecx, eax; this
0x1800118c5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
