# CUtils::GetIAS2Directory(_bstr_t &)

- ea: `0x180047298`
- end: `0x180047451`
- name: `?GetIAS2Directory@CUtils@@QEBAJAEAV_bstr_t@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(CUtils *__hidden this, struct _bstr_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003cee8`
- `0x18003d140`

## callees

- `0x180023f68`
- `0x180024508`
- `0x180024578`
- `0x180039830`
- `0x18004724c`
- `0x180047298`
- `0x180055030`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800473fb`
- `msvcrt!wcsncpy_s` at `0x1800473fb`
- `ADVAPI32!RegOpenKeyExW` at `0x18004734d`
- `ADVAPI32!RegOpenKeyExW` at `0x18004734d`
- `ADVAPI32!RegQueryValueExW` at `0x18004738f`
- `ADVAPI32!RegQueryValueExW` at `0x18004738f`
- `ADVAPI32!RegCloseKey` at `0x18004739c`
- `ADVAPI32!RegCloseKey` at `0x18004739c`
- `KERNEL32!GetLastError` at `0x1800473e0`
- `KERNEL32!GetLastError` at `0x1800473e0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800473d6`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800473d6`

## string_xrefs

- `0x18004733f`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
LSTATUS __fastcall CUtils::GetIAS2Directory(CUtils *this, struct _bstr_t *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // ebx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Data[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  if ( dword_1800790D8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800790D8);
    if ( dword_1800790D8 == -1 )
    {
      atexit(CUtils::GetIAS2Directory_::_2_::_dynamic_atexit_destructor_for__IASDirString__);
      Init_thread_footer(&dword_1800790D8);
    }
  }
  if ( !dword_180079090 )
  {
    hKey = 0;
    result = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
               0,
               0x20019u,
               &hKey);
    if ( result )
      return result;
    Type = 0;
    cbData = 520;
    v4 = RegQueryValueExW(hKey, L"ProductDir", 0, &Type, (LPBYTE)Data, &cbData);
    RegCloseKey(hKey);
    if ( v4 )
      return v4;
    if ( Type != 1 )
    {
      if ( Type != 2 )
        return -2147221165;
      if ( !ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
        return GetLastError();
      wcsncpy_s(Data, 0x104u, Dst, 0xFFFFFFFFFFFFFFFFuLL);
    }
    _bstr_t::operator=(&qword_1800790E0, Data);
    dword_180079090 = 1;
  }
  _bstr_t::operator=(a2, &qword_1800790E0);
  return 0;
}

```

## disassembly

```asm
0x180047298  mov     [rsp-8+arg_0], rbx
0x18004729d  mov     [rsp-8+arg_10], rdi
0x1800472a2  push    rbp
0x1800472a3  lea     rbp, [rsp-370h]
0x1800472ab  sub     rsp, 470h
0x1800472b2  mov     rax, cs:__security_cookie
0x1800472b9  xor     rax, rsp
0x1800472bc  mov     [rbp+370h+var_10], rax
0x1800472c3  mov     ecx, cs:_tls_index
0x1800472c9  mov     rdi, rdx
0x1800472cc  mov     rax, gs:58h
0x1800472d5  mov     edx, 4
0x1800472da  mov     rax, [rax+rcx*8]
0x1800472de  mov     eax, [rdx+rax]
0x1800472e1  cmp     cs:dword_1800790D8, eax
0x1800472e7  jle     short loc_180047316
0x1800472e9  lea     rcx, dword_1800790D8
0x1800472f0  call    _Init_thread_header
0x1800472f5  cmp     cs:dword_1800790D8, 0FFFFFFFFh
0x1800472fc  jnz     short loc_180047316
0x1800472fe  lea     rcx, _CUtils__GetIAS2Directory____2____dynamic_atexit_destructor_for__IASDirString__; void (__cdecl *)()
0x180047305  call    atexit
0x18004730a  lea     rcx, dword_1800790D8
0x180047311  call    _Init_thread_footer
0x180047316  cmp     cs:dword_180079090, 0
0x18004731d  jnz     loc_18004741C
0x180047323  lea     rax, [rsp+470h+hKey]
0x180047328  mov     [rsp+470h+hKey], 0
0x180047331  mov     r9d, 20019h; samDesired
0x180047337  mov     [rsp+470h+phkResult], rax; phkResult
0x18004733c  xor     r8d, r8d; ulOptions
0x18004733f  lea     rdx, ?IAS_KEY@CUtils@@0QBGB; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180047346  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004734d  call    cs:__imp_RegOpenKeyExW
0x180047353  test    eax, eax
0x180047355  jnz     loc_18004742D
0x18004735b  mov     rcx, [rsp+470h+hKey]; hKey
0x180047360  lea     r9, [rsp+470h+Type]; lpType
0x180047365  mov     [rsp+470h+Type], eax
0x180047369  lea     rdx, ValueName; "ProductDir"
0x180047370  lea     rax, [rsp+470h+cbData]
0x180047375  mov     [rsp+470h+cbData], 208h
0x18004737d  mov     [rsp+470h+lpcbData], rax; lpcbData
0x180047382  xor     r8d, r8d; lpReserved
0x180047385  lea     rax, [rsp+470h+Data]
0x18004738a  mov     [rsp+470h+phkResult], rax; lpData
0x18004738f  call    cs:__imp_RegQueryValueExW
0x180047395  mov     rcx, [rsp+470h+hKey]; hKey
0x18004739a  mov     ebx, eax
0x18004739c  call    cs:__imp_RegCloseKey
0x1800473a2  test    ebx, ebx
0x1800473a4  jz      short loc_1800473AD
0x1800473a6  mov     eax, ebx
0x1800473a8  jmp     loc_18004742D
0x1800473ad  cmp     [rsp+470h+Type], 1
0x1800473b2  jz      short loc_180047401
0x1800473b4  cmp     [rsp+470h+Type], 2
0x1800473b9  jz      short loc_1800473C2
0x1800473bb  mov     eax, 80040153h
0x1800473c0  jmp     short loc_18004742D
0x1800473c2  mov     ebx, 104h
0x1800473c7  lea     rdx, [rbp+370h+Dst]; lpDst
0x1800473ce  mov     r8d, ebx; nSize
0x1800473d1  lea     rcx, [rsp+470h+Data]; lpSrc
0x1800473d6  call    cs:__imp_ExpandEnvironmentStringsW
0x1800473dc  test    eax, eax
0x1800473de  jnz     short loc_1800473E8
0x1800473e0  call    cs:__imp_GetLastError
0x1800473e6  jmp     short loc_18004742D
0x1800473e8  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800473ec  lea     r8, [rbp+370h+Dst]; Source
0x1800473f3  mov     rdx, rbx; SizeInWords
0x1800473f6  lea     rcx, [rsp+470h+Data]; Destination
0x1800473fb  call    cs:__imp_wcsncpy_s
0x180047401  lea     rdx, [rsp+470h+Data]
0x180047406  lea     rcx, qword_1800790E0
0x18004740d  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180047412  mov     cs:dword_180079090, 1
0x18004741c  lea     rdx, qword_1800790E0
0x180047423  mov     rcx, rdi
0x180047426  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004742b  xor     eax, eax
0x18004742d  mov     rcx, [rbp+370h+var_10]
0x180047434  xor     rcx, rsp; StackCookie
0x180047437  call    __security_check_cookie
0x18004743c  lea     r11, [rsp+470h+var_s0]
0x180047444  mov     rbx, [r11+10h]
0x180047448  mov     rdi, [r11+20h]
0x18004744c  mov     rsp, r11
0x18004744f  pop     rbp
0x180047450  retn
```
