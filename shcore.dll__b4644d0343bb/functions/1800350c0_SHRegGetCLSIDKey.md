# SHRegGetCLSIDKey

- ea: `0x1800350c0`
- end: `0x1800351f8`
- name: `SHRegGetCLSIDKey`
- size: `312`
- prototype: `__int64 __fastcall(int, int, int, int, REGSAM samDesired, PHKEY)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006ac0`
- `0x1800350c0`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800351f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800351f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035172`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035172`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180035101`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180035101`

## string_xrefs

- `0x18003513a`: `%sCLSID\%s`
- `0x1800351b0`: `%sCLSID\%s\%s`

## pseudocode

```c
LSTATUS __fastcall SHRegGetCLSIDKey(const GUID *a1, __int64 a2, int a3, int a4, REGSAM samDesired, PHKEY phkResult)
{
  const wchar_t *v9; // r9
  LSTATUS result; // eax
  HKEY v11; // rcx
  OLECHAR sz[40]; // [rsp+50h] [rbp-2E8h] BYREF
  WCHAR SubKey[304]; // [rsp+A0h] [rbp-298h] BYREF

  StringFromGUID2(a1, sz, 39);
  v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\";
  if ( !a3 )
    v9 = &SourceString;
  if ( a2 )
    result = StringCchPrintfW(SubKey, 0x12Cu, L"%sCLSID\\%s\\%s", v9, sz, a2);
  else
    result = StringCchPrintfW(SubKey, 0x12Cu, L"%sCLSID\\%s", v9, sz);
  if ( result >= 0 )
  {
    v11 = (HKEY)((a3 != 0) - 0x80000000LL);
    if ( a4 )
      result = RegCreateKeyExW(v11, SubKey, 0, (LPWSTR)&SourceString, 0, samDesired, 0, phkResult, 0);
    else
      result = RegOpenKeyExW(v11, SubKey, 0, samDesired, phkResult);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800350c0  mov     [rsp+arg_10], rbx
0x1800350c5  push    rbp
0x1800350c6  push    rsi
0x1800350c7  push    rdi
0x1800350c8  push    r14
0x1800350ca  push    r15
0x1800350cc  sub     rsp, 310h
0x1800350d3  mov     rax, cs:__security_cookie
0x1800350da  xor     rax, rsp
0x1800350dd  mov     [rsp+338h+var_38], rax
0x1800350e5  mov     rbp, [rsp+338h+arg_28]
0x1800350ed  mov     ebx, r8d
0x1800350f0  mov     r14, rdx
0x1800350f3  mov     r8d, 27h ; '''; cchMax
0x1800350f9  lea     rdx, [rsp+338h+sz]; lpsz
0x1800350fe  mov     esi, r9d
0x180035101  call    cs:__imp_StringFromGUID2
0x180035107  test    ebx, ebx
0x180035109  lea     r15, SourceString
0x180035110  lea     r9, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180035117  mov     edx, 12Ch; unsigned __int64
0x18003511c  cmovz   r9, r15
0x180035120  lea     rax, [rsp+338h+sz]
0x180035125  xor     edi, edi
0x180035127  lea     rcx, [rsp+338h+SubKey]; unsigned __int16 *
0x18003512f  test    ebx, ebx
0x180035131  setnz   dil
0x180035135  test    r14, r14
0x180035138  jnz     short loc_1800351AB
0x18003513a  lea     r8, aSclsidS; "%sCLSID\\%s"
0x180035141  mov     [rsp+338h+phkResult], rax
0x180035146  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003514b  test    eax, eax
0x18003514d  js      short loc_180035184
0x18003514f  xor     r8d, r8d; Reserved
0x180035152  lea     rdx, [rsp+338h+SubKey]; lpSubKey
0x18003515a  lea     rcx, [rdi-80000000h]; hKey
0x180035161  test    esi, esi
0x180035163  jnz     short loc_1800351C3
0x180035165  mov     r9d, [rsp+338h+samDesired]; samDesired
0x18003516d  mov     [rsp+338h+phkResult], rbp; phkResult
0x180035172  call    cs:__imp_RegOpenKeyExW
0x180035178  test    eax, eax
0x18003517a  jle     short loc_180035184
0x18003517c  movzx   eax, ax
0x18003517f  or      eax, 80070000h
0x180035184  mov     rcx, [rsp+338h+var_38]
0x18003518c  xor     rcx, rsp; StackCookie
0x18003518f  call    __security_check_cookie
0x180035194  mov     rbx, [rsp+338h+arg_10]
0x18003519c  add     rsp, 310h
0x1800351a3  pop     r15
0x1800351a5  pop     r14
0x1800351a7  pop     rdi
0x1800351a8  pop     rsi
0x1800351a9  pop     rbp
0x1800351aa  retn
0x1800351ab  mov     qword ptr [rsp+338h+var_310], r14
0x1800351b0  lea     r8, aSclsidSS; "%sCLSID\\%s\\%s"
0x1800351b7  mov     [rsp+338h+phkResult], rax
0x1800351bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800351c1  jmp     short loc_18003514B
0x1800351c3  mov     eax, [rsp+338h+samDesired]
0x1800351ca  mov     r9, r15; lpClass
0x1800351cd  mov     [rsp+338h+lpdwDisposition], 0; lpdwDisposition
0x1800351d6  mov     [rsp+338h+var_300], rbp; phkResult
0x1800351db  mov     [rsp+338h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800351e4  mov     [rsp+338h+var_310], eax; samDesired
0x1800351e8  mov     dword ptr [rsp+338h+phkResult], 0; dwOptions
0x1800351f0  call    cs:__imp_RegCreateKeyExW
0x1800351f6  jmp     short loc_180035178
```
