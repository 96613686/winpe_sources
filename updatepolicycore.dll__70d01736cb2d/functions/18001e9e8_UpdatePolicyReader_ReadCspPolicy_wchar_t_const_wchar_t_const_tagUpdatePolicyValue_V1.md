# UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)

- ea: `0x18001e9e8`
- end: `0x18001ebff`
- name: `?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, struct tagUpdatePolicyValue_V1 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ccf0`
- `0x18001d26c`
- `0x18001d380`
- `0x18001d534`

## callees

- `0x18000e310`
- `0x18000fd94`
- `0x18001e9e8`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001eb79`
- `OLEAUT32!__imp_SysAllocString` at `0x18001eb79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001eb67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001eb67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ea43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ea43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ebcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ebcc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ea60`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ea60`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadCspPolicy(
        const wchar_t *a1,
        const wchar_t *a2,
        struct tagUpdatePolicyValue_V1 *a3)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  int v8; // ebx
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
  v25 = 0;
  v24[0] = 0;
  v26 = 0;
  v28 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Management.Policies.NamedPolicy", 0x27u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18001EBFELL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_7f793be7_76c4_4058_8cad_67662cd05f0d, &v28) < 0 )
    goto LABEL_3;
  v9 = v28;
  v10 = *(int (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v28 + 48LL);
  v11 = v25;
  v25 = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v23, v7)[1].Reserved.Reserved1;
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v22,
          (const WCHAR **)&UpdatePolicyReader::c_szPolicy_CspUpdateAreaName,
          v13);
  if ( v10(v9, v14[1].Reserved.Reserved1, Reserved1, &v25) < 0 )
    goto LABEL_3;
  v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 72LL))(v25, v24);
  if ( v8 < 0 )
    goto LABEL_3;
  if ( !v24[0] )
    goto LABEL_4;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 64LL))(v25, &v26);
  if ( v8 < 0 )
  {
LABEL_3:
    v8 = 0;
LABEL_4:
    *((_DWORD *)a3 + 1) = 0;
    goto LABEL_18;
  }
  if ( v26 != 5 )
    goto LABEL_4;
  *((_DWORD *)a3 + 1) = 1;
  v15 = v25;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 128LL);
  WindowsDeleteString(v27);
  v27 = 0;
  v8 = v16(v15, &v27);
  if ( v8 < 0 )
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
    v8 = -2147024882;
  }
LABEL_18:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  WindowsDeleteString(v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e9e8  mov     [rsp-8+arg_8], rbx
0x18001e9ed  push    rbp
0x18001e9ee  push    rsi
0x18001e9ef  push    rdi
0x18001e9f0  push    r14
0x18001e9f2  push    r15
0x18001e9f4  lea     rbp, [rsp-37h]
0x18001e9f9  sub     rsp, 0B0h
0x18001ea00  mov     rax, cs:__security_cookie
0x18001ea07  xor     rax, rsp
0x18001ea0a  mov     [rbp+57h+var_30], rax
0x18001ea0e  mov     rsi, r8
0x18001ea11  mov     [rbp+57h+var_60], rcx
0x18001ea15  xor     r15d, r15d
0x18001ea18  mov     [rbp+57h+var_40], r15
0x18001ea1c  mov     [rbp+57h+var_50], r15
0x18001ea20  mov     [rbp+57h+var_58], r15b
0x18001ea24  mov     [rbp+57h+var_48], r15d
0x18001ea28  mov     [rbp+57h+var_38], r15
0x18001ea2c  mov     [rbp+57h+string], r15
0x18001ea30  lea     r9, [rbp+57h+string]; string
0x18001ea34  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001ea38  lea     edx, [r15+27h]; length
0x18001ea3c  lea     rcx, ?RuntimeClass_Windows_Management_Policies_NamedPolicy@@3QB_WB; "Windows.Management.Policies.NamedPolicy"
0x18001ea43  call    cs:__imp_WindowsCreateStringReference
0x18001ea49  test    eax, eax
0x18001ea4b  js      loc_18001EBF7
0x18001ea51  lea     r8, [rbp+57h+var_38]
0x18001ea55  lea     rdx, _GUID_7f793be7_76c4_4058_8cad_67662cd05f0d
0x18001ea5c  mov     rcx, [rbp+57h+string]
0x18001ea60  call    cs:__imp_RoGetActivationFactory
0x18001ea66  test    eax, eax
0x18001ea68  jns     short loc_18001EA76
0x18001ea6a  mov     ebx, r15d
0x18001ea6d  mov     [rsi+4], r15d
0x18001ea71  jmp     loc_18001EB9C
0x18001ea76  mov     rbx, [rbp+57h+var_38]
0x18001ea7a  mov     rax, [rbx]
0x18001ea7d  mov     r14, [rax+30h]
0x18001ea81  mov     rcx, [rbp+57h+var_50]
0x18001ea85  mov     [rbp+57h+var_50], r15
0x18001ea89  test    rcx, rcx
0x18001ea8c  jz      short loc_18001EA9B
0x18001ea8e  mov     rax, [rcx]
0x18001ea91  mov     rax, [rax+10h]
0x18001ea95  call    _guard_dispatch_icall
0x18001ea9a  nop
0x18001ea9b  lea     rdx, [rbp+57h+var_60]
0x18001ea9f  lea     rcx, [rbp+57h+hstringHeader]
0x18001eaa3  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001eaa8  nop
0x18001eaa9  mov     rdi, [rax+18h]
0x18001eaad  lea     rdx, ?c_szPolicy_CspUpdateAreaName@UpdatePolicyReader@@2QEB_WEB; wchar_t const * const UpdatePolicyReader::c_szPolicy_CspUpdateAreaName
0x18001eab4  lea     rcx, [rbp+57h+var_80]
0x18001eab8  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001eabd  nop
0x18001eabe  lea     r9, [rbp+57h+var_50]
0x18001eac2  mov     r8, rdi
0x18001eac5  mov     rdx, [rax+18h]
0x18001eac9  mov     rcx, rbx
0x18001eacc  mov     rax, r14
0x18001eacf  call    _guard_dispatch_icall
0x18001ead4  nop
0x18001ead5  test    eax, eax
0x18001ead7  js      short loc_18001EA6A
0x18001ead9  mov     rcx, [rbp+57h+var_50]
0x18001eadd  mov     rax, [rcx]
0x18001eae0  lea     rdx, [rbp+57h+var_58]
0x18001eae4  mov     rax, [rax+48h]
0x18001eae8  call    _guard_dispatch_icall
0x18001eaed  mov     ebx, eax
0x18001eaef  test    eax, eax
0x18001eaf1  js      loc_18001EA6A
0x18001eaf7  cmp     [rbp+57h+var_58], r15b
0x18001eafb  jz      loc_18001EA6D
0x18001eb01  mov     rcx, [rbp+57h+var_50]
0x18001eb05  mov     rax, [rcx]
0x18001eb08  lea     rdx, [rbp+57h+var_48]
0x18001eb0c  mov     rax, [rax+40h]
0x18001eb10  call    _guard_dispatch_icall
0x18001eb15  mov     ebx, eax
0x18001eb17  test    eax, eax
0x18001eb19  js      loc_18001EA6A
0x18001eb1f  cmp     [rbp+57h+var_48], 5
0x18001eb23  jnz     loc_18001EA6D
0x18001eb29  mov     dword ptr [rsi+4], 1
0x18001eb30  mov     rbx, [rbp+57h+var_50]
0x18001eb34  mov     rax, [rbx]
0x18001eb37  mov     rdi, [rax+80h]
0x18001eb3e  mov     rcx, [rbp+57h+var_40]; string
0x18001eb42  call    cs:__imp_WindowsDeleteString
0x18001eb48  mov     [rbp+57h+var_40], r15
0x18001eb4c  lea     rdx, [rbp+57h+var_40]
0x18001eb50  mov     rcx, rbx
0x18001eb53  mov     rax, rdi
0x18001eb56  call    _guard_dispatch_icall
0x18001eb5b  mov     ebx, eax
0x18001eb5d  test    eax, eax
0x18001eb5f  js      short loc_18001EB72
0x18001eb61  xor     edx, edx; length
0x18001eb63  mov     rcx, [rbp+57h+var_40]; string
0x18001eb67  call    cs:__imp_WindowsGetStringRawBuffer
0x18001eb6d  mov     rcx, rax
0x18001eb70  jmp     short loc_18001EB79
0x18001eb72  lea     rcx, psz; psz
0x18001eb79  call    cs:__imp_SysAllocString
0x18001eb7f  mov     [rsi+18h], rax
0x18001eb83  test    rax, rax
0x18001eb86  jnz     short loc_18001EB8F
0x18001eb88  mov     ebx, 8007000Eh
0x18001eb8d  jmp     short loc_18001EB9C
0x18001eb8f  mov     word ptr [rsi+10h], 8
0x18001eb95  mov     dword ptr [rsi+8], 2
0x18001eb9c  mov     rcx, [rbp+57h+var_50]
0x18001eba0  test    rcx, rcx
0x18001eba3  jz      short loc_18001EBB2
0x18001eba5  mov     rax, [rcx]
0x18001eba8  mov     rax, [rax+10h]
0x18001ebac  call    _guard_dispatch_icall
0x18001ebb1  nop
0x18001ebb2  mov     rcx, [rbp+57h+var_38]
0x18001ebb6  test    rcx, rcx
0x18001ebb9  jz      short loc_18001EBC8
0x18001ebbb  mov     rax, [rcx]
0x18001ebbe  mov     rax, [rax+10h]
0x18001ebc2  call    _guard_dispatch_icall
0x18001ebc7  nop
0x18001ebc8  mov     rcx, [rbp+57h+var_40]; string
0x18001ebcc  call    cs:__imp_WindowsDeleteString
0x18001ebd2  mov     eax, ebx
0x18001ebd4  mov     rcx, [rbp+57h+var_30]
0x18001ebd8  xor     rcx, rsp; StackCookie
0x18001ebdb  call    __security_check_cookie
0x18001ebe0  mov     rbx, [rsp+0D0h+arg_8]
0x18001ebe8  add     rsp, 0B0h
0x18001ebef  pop     r15
0x18001ebf1  pop     r14
0x18001ebf3  pop     rdi
0x18001ebf4  pop     rsi
0x18001ebf5  pop     rbp
0x18001ebf6  retn
0x18001ebf7  mov     ecx, eax; this
0x18001ebf9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
