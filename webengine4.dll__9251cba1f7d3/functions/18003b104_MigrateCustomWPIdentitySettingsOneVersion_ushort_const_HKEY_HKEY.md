# MigrateCustomWPIdentitySettingsOneVersion(ushort const *,HKEY__ *,HKEY__ *)

- ea: `0x18003b104`
- end: `0x18003b2c7`
- name: `?MigrateCustomWPIdentitySettingsOneVersion@@YAJPEBGPEAUHKEY__@@1@Z`
- size: `451`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003af84`

## callees

- `0x18001c550`
- `0x180039628`
- `0x1800396b4`
- `0x18003b104`
- `0x18004c0c7`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003b248`
- `KERNEL32!LocalFree` at `0x18003b248`
- `ADVAPI32!RegCloseKey` at `0x18003b1e3`
- `ADVAPI32!RegCloseKey` at `0x18003b289`
- `ADVAPI32!RegCloseKey` at `0x18003b29e`
- `ADVAPI32!RegCloseKey` at `0x18003b1e3`
- `ADVAPI32!RegCloseKey` at `0x18003b289`
- `ADVAPI32!RegCloseKey` at `0x18003b29e`
- `ADVAPI32!RegEnumKeyExW` at `0x18003b1c6`
- `ADVAPI32!RegEnumKeyExW` at `0x18003b1c6`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b173`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b209`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b173`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b209`

## pseudocode

```c
__int64 __fastcall MigrateCustomWPIdentitySettingsOneVersion(LPCWSTR lpSubKey, HKEY hKey, HKEY a3)
{
  unsigned int LastWin32Error; // esi
  int v7; // r14d
  LSTATUS v8; // eax
  DWORD v9; // ebx
  LSTATUS v10; // eax
  unsigned int v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  LastWin32Error = 0;
  phkResult = 0;
  cchName = 0;
  v7 = IsVista();
  Sid = 0;
  v8 = RegOpenKeyExW(a3, lpSubKey, 0, 0x20019u, &hKeya);
  if ( v8 )
  {
    LastWin32Error = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      LastWin32Error = v8;
  }
  else
  {
    v9 = 0;
    while ( 1 )
    {
      cchName = 260;
      Name[0] = 0;
      v10 = RegEnumKeyExW(hKeya, v9, Name, &cchName, 0, 0, 0, 0);
      if ( v10 )
        break;
      if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
      {
        if ( ConvertStringSidToSidW_0(Name, &Sid) )
        {
          if ( v7 )
            v11 = GrantAccessToUserAccountOnVistaCore(Sid, 1);
          else
            v11 = GrantAccessToUserAccountCore(Sid);
          LastWin32Error = v11;
          LocalFree(Sid);
          Sid = 0;
        }
        else
        {
          LastWin32Error = GetLastWin32Error();
        }
      }
      if ( ++v9 >= 0x2710 )
        goto LABEL_20;
    }
    if ( v10 != 259 )
      LastWin32Error = GetLastWin32Error();
  }
LABEL_20:
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKeya);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003b104  push    rbp
0x18003b106  push    rbx
0x18003b107  push    rsi
0x18003b108  push    rdi
0x18003b109  push    r12
0x18003b10b  push    r14
0x18003b10d  push    r15
0x18003b10f  lea     rbp, [rsp-180h]
0x18003b117  sub     rsp, 280h
0x18003b11e  mov     rax, cs:__security_cookie
0x18003b125  xor     rax, rsp
0x18003b128  mov     [rbp+1B0h+var_40], rax
0x18003b12f  xor     r12d, r12d
0x18003b132  mov     rdi, r8
0x18003b135  mov     [rsp+2B0h+hKey], r12
0x18003b13a  mov     esi, r12d
0x18003b13d  mov     [rsp+2B0h+var_260], r12
0x18003b142  mov     r15, rdx
0x18003b145  mov     [rsp+2B0h+cchName], r12d
0x18003b14a  mov     rbx, rcx
0x18003b14d  call    ?IsVista@@YAHXZ
0x18003b152  mov     r14d, eax
0x18003b155  mov     [rsp+2B0h+Sid], r12
0x18003b15a  lea     rax, [rsp+2B0h+hKey]
0x18003b15f  mov     r9d, 20019h; samDesired
0x18003b165  xor     r8d, r8d; ulOptions
0x18003b168  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18003b16d  mov     rdx, rbx; lpSubKey
0x18003b170  mov     rcx, rdi; hKey
0x18003b173  call    cs:__imp_RegOpenKeyExW
0x18003b179  test    eax, eax
0x18003b17b  jz      short loc_18003B190
0x18003b17d  movzx   esi, ax
0x18003b180  or      esi, 80070000h
0x18003b186  test    eax, eax
0x18003b188  cmovle  esi, eax
0x18003b18b  jmp     loc_18003B27A
0x18003b190  mov     ebx, r12d
0x18003b193  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003b198  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18003b19d  mov     [rsp+2B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003b1a2  lea     r8, [rsp+2B0h+Name]; lpName
0x18003b1a7  mov     [rsp+2B0h+lpcchClass], r12; lpcchClass
0x18003b1ac  mov     edx, ebx; dwIndex
0x18003b1ae  mov     [rsp+2B0h+lpClass], r12; lpClass
0x18003b1b3  mov     [rsp+2B0h+phkResult], r12; lpReserved
0x18003b1b8  mov     [rsp+2B0h+cchName], 104h
0x18003b1c0  mov     [rsp+2B0h+Name], r12w
0x18003b1c6  call    cs:__imp_RegEnumKeyExW
0x18003b1cc  test    eax, eax
0x18003b1ce  jnz     loc_18003B26C
0x18003b1d4  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18003b1d9  lea     rax, [rcx-1]
0x18003b1dd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b1e1  ja      short loc_18003B1EE
0x18003b1e3  call    cs:__imp_RegCloseKey
0x18003b1e9  mov     [rsp+2B0h+var_260], r12
0x18003b1ee  lea     rax, [rsp+2B0h+var_260]
0x18003b1f3  mov     r9d, 20019h; samDesired
0x18003b1f9  xor     r8d, r8d; ulOptions
0x18003b1fc  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18003b201  lea     rdx, [rsp+2B0h+Name]; lpSubKey
0x18003b206  mov     rcx, r15; hKey
0x18003b209  call    cs:__imp_RegOpenKeyExW
0x18003b20f  test    eax, eax
0x18003b211  jz      short loc_18003B25C
0x18003b213  lea     rdx, [rsp+2B0h+Sid]; Sid
0x18003b218  lea     rcx, [rsp+2B0h+Name]; StringSid
0x18003b21d  call    ConvertStringSidToSidW_0
0x18003b222  test    eax, eax
0x18003b224  jz      short loc_18003B255
0x18003b226  mov     rcx, [rsp+2B0h+Sid]; pSid1
0x18003b22b  test    r14d, r14d
0x18003b22e  jz      short loc_18003B23C
0x18003b230  mov     edx, 1; int
0x18003b235  call    ?GrantAccessToUserAccountOnVistaCore@@YAJPEAXH@Z
0x18003b23a  jmp     short loc_18003B241
0x18003b23c  call    ?GrantAccessToUserAccountCore@@YAJPEAX@Z
0x18003b241  mov     rcx, [rsp+2B0h+Sid]; hMem
0x18003b246  mov     esi, eax
0x18003b248  call    cs:__imp_LocalFree
0x18003b24e  mov     [rsp+2B0h+Sid], r12
0x18003b253  jmp     short loc_18003B25C
0x18003b255  call    ?GetLastWin32Error@@YAJXZ
0x18003b25a  mov     esi, eax
0x18003b25c  inc     ebx
0x18003b25e  cmp     ebx, 2710h
0x18003b264  jb      loc_18003B193
0x18003b26a  jmp     short loc_18003B27A
0x18003b26c  cmp     eax, 103h
0x18003b271  jz      short loc_18003B27A
0x18003b273  call    ?GetLastWin32Error@@YAJXZ
0x18003b278  mov     esi, eax
0x18003b27a  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18003b27f  lea     rax, [rcx-1]
0x18003b283  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b287  ja      short loc_18003B28F
0x18003b289  call    cs:__imp_RegCloseKey
0x18003b28f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003b294  lea     rax, [rcx-1]
0x18003b298  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b29c  ja      short loc_18003B2A4
0x18003b29e  call    cs:__imp_RegCloseKey
0x18003b2a4  mov     eax, esi
0x18003b2a6  mov     rcx, [rbp+1B0h+var_40]
0x18003b2ad  xor     rcx, rsp; StackCookie
0x18003b2b0  call    __security_check_cookie
0x18003b2b5  add     rsp, 280h
0x18003b2bc  pop     r15
0x18003b2be  pop     r14
0x18003b2c0  pop     r12
0x18003b2c2  pop     rdi
0x18003b2c3  pop     rsi
0x18003b2c4  pop     rbx
0x18003b2c5  pop     rbp
0x18003b2c6  retn
```
