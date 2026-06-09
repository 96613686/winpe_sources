# Reg_GetCommand(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)

- ea: `0x18001ee10`
- end: `0x18001eff0`
- name: `?Reg_GetCommand@@YAHPEAUHKEY__@@PEBG1PEAGK@Z`
- size: `480`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001ee10`
- `0x180020630`

## callees

- `0x180003400`
- `0x180012550`
- `0x180012930`
- `0x18001ee10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ef1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ef1e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001eeaa`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001eeaa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001ee93`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001ee93`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ef48`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ef6e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ef8e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ef48`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ef6e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001ef8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ee5d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ee5d`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18001eed5`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18001eed5`

## pseudocode

```c
__int64 __fastcall Reg_GetCommand(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v7; // eax
  unsigned __int64 v8; // rcx
  HKEY v9; // r11
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String[1024]; // [rsp+50h] [rbp-B0h] BYREF

  StringCchCopyW(String, 0x400u, a2);
  v7 = lstrlenW(String);
  *a4 = 0;
  if ( *((_WORD *)&pcbData[3] + v7 + 1) == 92 )
  {
    if ( !a3 )
    {
      v8 = 2LL * v7 - 2;
      if ( v8 >= 0x800 )
        _report_rangecheckfailure(v8, 2048);
      *(WCHAR *)((char *)String + v8) = 0;
    }
    goto LABEL_10;
  }
  if ( a3 && !*a3 )
  {
LABEL_10:
    pcbData[0] = 2048;
    if ( RegGetValueW(a1, String, a3, 2u, 0, a4, pcbData) )
      *a4 = 0;
    goto LABEL_12;
  }
  pcbData[0] = 2048;
  if ( !a3 && !PathFindFileNameW(String) )
    return 0;
  PathCchRemoveFileSpec(String, 0x400u);
  SHRegGetValueW(a1, String, 0, 65538, 0, a4, pcbData);
LABEL_12:
  if ( !*a4 )
    return 0;
  if ( StrCmpNICW(a4, L"HKCU:", 5) && StrCmpNICW(a4, L"HKLM:", 5) && StrCmpNICW(a4, L"HKCR:", 5) )
    return *a4;
  StringCchCopyW(String, 0x400u, a4 + 5);
  return Reg_GetCommand(v9, String, 0, a4, 0x400u);
}

```

## disassembly

```asm
0x18001ee10  push    rbp
0x18001ee12  push    rbx
0x18001ee13  push    rsi
0x18001ee14  push    rdi
0x18001ee15  push    r14
0x18001ee17  push    r15
0x18001ee19  lea     rbp, [rsp-768h]
0x18001ee21  sub     rsp, 868h
0x18001ee28  mov     rax, cs:__security_cookie
0x18001ee2f  xor     rax, rsp
0x18001ee32  mov     [rbp+790h+var_40], rax
0x18001ee39  mov     rdi, r8
0x18001ee3c  mov     rsi, rcx
0x18001ee3f  mov     r8, rdx; unsigned __int16 *
0x18001ee42  lea     rcx, [rsp+890h+String]; unsigned __int16 *
0x18001ee47  mov     r15d, 400h
0x18001ee4d  mov     rbx, r9
0x18001ee50  mov     edx, r15d; unsigned __int64
0x18001ee53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ee58  lea     rcx, [rsp+890h+String]; lpString
0x18001ee5d  call    cs:__imp_lstrlenW
0x18001ee63  xor     r14d, r14d
0x18001ee66  movsxd  rcx, eax
0x18001ee69  mov     [rbx], r14w
0x18001ee6d  mov     edx, 800h
0x18001ee72  cmp     [rsp+rcx*2+890h+var_842], 5Ch ; '\'
0x18001ee78  jz      short loc_18001EEDD
0x18001ee7a  test    rdi, rdi
0x18001ee7d  jz      short loc_18001EE85
0x18001ee7f  cmp     [rdi], r14w
0x18001ee83  jz      short loc_18001EEF5
0x18001ee85  mov     [rsp+890h+var_850], edx
0x18001ee89  test    rdi, rdi
0x18001ee8c  jnz     short loc_18001EEA2
0x18001ee8e  lea     rcx, [rsp+890h+String]; pszPath
0x18001ee93  call    cs:__imp_PathFindFileNameW
0x18001ee99  test    rax, rax
0x18001ee9c  jz      loc_18001EFCF
0x18001eea2  mov     rdx, r15; cchPath
0x18001eea5  lea     rcx, [rsp+890h+String]; pszPath
0x18001eeaa  call    cs:__imp_PathCchRemoveFileSpec
0x18001eeb0  lea     rax, [rsp+890h+var_850]
0x18001eeb5  mov     r9d, 10002h; srrfFlags
0x18001eebb  mov     [rsp+890h+pcbData], rax; pcbData
0x18001eec0  lea     rdx, [rsp+890h+String]; pszSubKey
0x18001eec5  mov     [rsp+890h+pvData], rbx; pvData
0x18001eeca  xor     r8d, r8d; pszValue
0x18001eecd  mov     rcx, rsi; hkey
0x18001eed0  mov     [rsp+890h+pdwType], r14; pdwType
0x18001eed5  call    cs:__imp_SHRegGetValueW
0x18001eedb  jmp     short loc_18001EF2C
0x18001eedd  test    rdi, rdi
0x18001eee0  jnz     short loc_18001EEF5
0x18001eee2  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x18001eeea  cmp     rcx, rdx
0x18001eeed  jnb     short loc_18001EF5B
0x18001eeef  mov     [rsp+rcx+890h+String], r14w
0x18001eef5  lea     rax, [rsp+890h+var_850]
0x18001eefa  mov     [rsp+890h+var_850], edx
0x18001eefe  mov     [rsp+890h+pcbData], rax; pcbData
0x18001ef03  lea     rdx, [rsp+890h+String]; lpSubKey
0x18001ef08  mov     [rsp+890h+pvData], rbx; pvData
0x18001ef0d  mov     r9d, 2; dwFlags
0x18001ef13  mov     r8, rdi; lpValue
0x18001ef16  mov     [rsp+890h+pdwType], r14; pdwType
0x18001ef1b  mov     rcx, rsi; hkey
0x18001ef1e  call    cs:__imp_RegGetValueW
0x18001ef24  test    eax, eax
0x18001ef26  jz      short loc_18001EF2C
0x18001ef28  mov     [rbx], r14w
0x18001ef2c  cmp     [rbx], r14w
0x18001ef30  jz      loc_18001EFCF
0x18001ef36  mov     edi, 5
0x18001ef3b  lea     rdx, pszStr2; "HKCU:"
0x18001ef42  mov     r8d, edi; nChar
0x18001ef45  mov     rcx, rbx; pszStr1
0x18001ef48  call    cs:__imp_StrCmpNICW
0x18001ef4e  test    eax, eax
0x18001ef50  jnz     short loc_18001EF61
0x18001ef52  mov     r11, 0FFFFFFFF80000001h
0x18001ef59  jmp     short loc_18001EF9F
0x18001ef5b  call    __report_rangecheckfailure
0x18001ef61  mov     r8d, edi; nChar
0x18001ef64  lea     rdx, aHklm; "HKLM:"
0x18001ef6b  mov     rcx, rbx; pszStr1
0x18001ef6e  call    cs:__imp_StrCmpNICW
0x18001ef74  test    eax, eax
0x18001ef76  jnz     short loc_18001EF81
0x18001ef78  mov     r11, 0FFFFFFFF80000002h
0x18001ef7f  jmp     short loc_18001EF9F
0x18001ef81  mov     r8d, edi; nChar
0x18001ef84  lea     rdx, aHkcr; "HKCR:"
0x18001ef8b  mov     rcx, rbx; pszStr1
0x18001ef8e  call    cs:__imp_StrCmpNICW
0x18001ef94  test    eax, eax
0x18001ef96  jnz     short loc_18001EFCA
0x18001ef98  mov     r11, 0FFFFFFFF80000000h
0x18001ef9f  lea     r8, [rbx+0Ah]; unsigned __int16 *
0x18001efa3  mov     rdx, r15; unsigned __int64
0x18001efa6  lea     rcx, [rsp+890h+String]; unsigned __int16 *
0x18001efab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001efb0  mov     r9, rbx; unsigned __int16 *
0x18001efb3  mov     dword ptr [rsp+890h+pdwType], r15d; unsigned int
0x18001efb8  xor     r8d, r8d; unsigned __int16 *
0x18001efbb  lea     rdx, [rsp+890h+String]; unsigned __int16 *
0x18001efc0  mov     rcx, r11; HKEY
0x18001efc3  call    ?Reg_GetCommand@@YAHPEAUHKEY__@@PEBG1PEAGK@Z; Reg_GetCommand(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18001efc8  jmp     short loc_18001EFD1
0x18001efca  movzx   eax, word ptr [rbx]
0x18001efcd  jmp     short loc_18001EFD1
0x18001efcf  xor     eax, eax
0x18001efd1  mov     rcx, [rbp+790h+var_40]
0x18001efd8  xor     rcx, rsp; StackCookie
0x18001efdb  call    __security_check_cookie
0x18001efe0  add     rsp, 868h
0x18001efe7  pop     r15
0x18001efe9  pop     r14
0x18001efeb  pop     rdi
0x18001efec  pop     rsi
0x18001efed  pop     rbx
0x18001efee  pop     rbp
0x18001efef  retn
```
