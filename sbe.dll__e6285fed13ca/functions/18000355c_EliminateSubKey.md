# EliminateSubKey

- ea: `0x18000355c`
- end: `0x18000369a`
- name: `EliminateSubKey`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800034d4`
- `0x18000355c`

## callees

- `0x180001c00`
- `0x180002e68`
- `0x18000355c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003651`
- `ADVAPI32!RegCloseKey` at `0x180003651`
- `ADVAPI32!RegEnumKeyExW` at `0x18000362f`
- `ADVAPI32!RegEnumKeyExW` at `0x18000362f`
- `ADVAPI32!RegDeleteKeyW` at `0x18000365d`
- `ADVAPI32!RegDeleteKeyW` at `0x18000365d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800035de`
- `ADVAPI32!RegOpenKeyExW` at `0x1800035de`

## pseudocode

```c
LSTATUS __fastcall EliminateSubKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS result; // eax
  bool v5; // cc
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  *(_QWORD *)cchName = 0;
  if ( (int)StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)cchName) < 0 || !*(_QWORD *)cchName )
    return -2147467259;
  result = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  v5 = result <= 0;
  if ( !result )
  {
    do
    {
      cchName[0] = 260;
      ftLastWriteTime = 0;
    }
    while ( !RegEnumKeyExW(hKey, 0, SubKey, cchName, 0, 0, 0, &ftLastWriteTime)
         && !(unsigned int)EliminateSubKey(hKey, SubKey) );
    RegCloseKey(hKey);
    result = RegDeleteKeyW(a1, a2);
    v5 = result <= 0;
  }
  if ( !v5 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000355c  mov     [rsp-8+arg_10], rbx
0x180003561  mov     [rsp-8+arg_18], rdi
0x180003566  push    rbp
0x180003567  lea     rbp, [rsp-180h]
0x18000356f  sub     rsp, 280h
0x180003576  mov     rax, cs:__security_cookie
0x18000357d  xor     rax, rsp
0x180003580  mov     [rbp+180h+var_10], rax
0x180003587  mov     rbx, rdx
0x18000358a  mov     [rsp+280h+hKey], 0
0x180003593  mov     rdi, rcx
0x180003596  mov     qword ptr [rsp+280h+cchName], 0
0x18000359f  mov     rcx, rbx; unsigned __int16 *
0x1800035a2  lea     r8, [rsp+280h+cchName]; unsigned __int64 *
0x1800035a7  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800035ac  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800035b1  test    eax, eax
0x1800035b3  js      loc_180003671
0x1800035b9  cmp     qword ptr [rsp+280h+cchName], 0
0x1800035bf  jz      loc_180003671
0x1800035c5  lea     rax, [rsp+280h+hKey]
0x1800035ca  mov     r9d, 2000000h; samDesired
0x1800035d0  xor     r8d, r8d; ulOptions
0x1800035d3  mov     [rsp+280h+phkResult], rax; phkResult
0x1800035d8  mov     rdx, rbx; lpSubKey
0x1800035db  mov     rcx, rdi; hKey
0x1800035de  call    cs:__imp_RegOpenKeyExW
0x1800035e4  test    eax, eax
0x1800035e6  jnz     short loc_180003665
0x1800035e8  mov     rcx, [rsp+280h+hKey]; hKey
0x1800035ed  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800035f2  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800035f7  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800035fc  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x180003605  lea     r8, [rsp+280h+SubKey]; lpName
0x18000360a  mov     [rsp+280h+lpClass], 0; lpClass
0x180003613  xor     edx, edx; dwIndex
0x180003615  mov     [rsp+280h+phkResult], 0; lpReserved
0x18000361e  mov     [rsp+280h+cchName], 104h
0x180003626  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x18000362f  call    cs:__imp_RegEnumKeyExW
0x180003635  test    eax, eax
0x180003637  jnz     short loc_18000364C
0x180003639  mov     rcx, [rsp+280h+hKey]
0x18000363e  lea     rdx, [rsp+280h+SubKey]
0x180003643  call    EliminateSubKey
0x180003648  test    eax, eax
0x18000364a  jz      short loc_1800035E8
0x18000364c  mov     rcx, [rsp+280h+hKey]; hKey
0x180003651  call    cs:__imp_RegCloseKey
0x180003657  mov     rdx, rbx; lpSubKey
0x18000365a  mov     rcx, rdi; hKey
0x18000365d  call    cs:__imp_RegDeleteKeyW
0x180003663  test    eax, eax
0x180003665  jle     short loc_180003676
0x180003667  movzx   eax, ax
0x18000366a  or      eax, 80070000h
0x18000366f  jmp     short loc_180003676
0x180003671  mov     eax, 80004005h
0x180003676  mov     rcx, [rbp+180h+var_10]
0x18000367d  xor     rcx, rsp; StackCookie
0x180003680  call    __security_check_cookie
0x180003685  lea     r11, [rsp+280h+var_s0]
0x18000368d  mov     rbx, [r11+20h]
0x180003691  mov     rdi, [r11+28h]
0x180003695  mov     rsp, r11
0x180003698  pop     rbp
0x180003699  retn
```
