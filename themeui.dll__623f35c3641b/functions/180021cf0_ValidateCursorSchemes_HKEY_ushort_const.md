# ValidateCursorSchemes(HKEY__ *,ushort const *)

- ea: `0x180021cf0`
- end: `0x180021f01`
- name: `?ValidateCursorSchemes@@YAJPEAUHKEY__@@PEBG@Z`
- size: `529`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041a2c`

## callees

- `0x180021cf0`
- `0x1800358c0`

## import_xrefs

- `SHCORE!SHDeleteValueW` at `0x180021e57`
- `SHCORE!SHDeleteValueW` at `0x180021e57`
- `SHLWAPI!PathFileExistsW` at `0x180021e01`
- `SHLWAPI!PathFileExistsW` at `0x180021e01`
- `SHLWAPI!StrChrW` at `0x180021d9d`
- `SHLWAPI!StrChrW` at `0x180021e2c`
- `SHLWAPI!StrChrW` at `0x180021d9d`
- `SHLWAPI!StrChrW` at `0x180021e2c`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180021df0`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180021df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ecb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ed6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ed6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021d46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021d46`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180021e9e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180021e9e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180021dcf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180021dcf`

## pseudocode

```c
__int64 __fastcall ValidateCursorSchemes(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v2; // eax
  int v3; // ebx
  BYTE *lpData; // rdi
  DWORD v5; // r15d
  DWORD i; // edx
  bool v7; // si
  int v8; // r12d
  const WCHAR *v9; // r14
  LPWSTR v10; // rax
  void *v11; // rcx
  const WCHAR *v12; // r13
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  void *v17; // [rsp+50h] [rbp-B0h]
  WCHAR pszValue[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF

  hkey = 0;
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors\\Schemes", 0, 0x20019u, &hkey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    cbData = 8840;
    lpData = (BYTE *)CoTaskMemAlloc(0x2288u);
    if ( lpData )
    {
      v5 = 0;
      for ( i = 0; ; i = v5 )
      {
        cchValueName = 260;
        v3 = RegEnumValueW(hkey, i, pszValue, &cchValueName, 0, 0, lpData, &cbData);
        if ( v3 )
          break;
        v17 = lpData;
        v7 = 0;
        v8 = 0;
        v9 = StrChrW((PCWSTR)lpData, 0x2Cu);
        if ( v9 )
        {
          while ( !v7 )
          {
            if ( !*off_18006E940[v8] )
              goto LABEL_14;
            v10 = CharNextW(v9);
            v11 = v17;
            v12 = v10;
            *v9 = 0;
            if ( (unsigned int)SHExpandEnvironmentStringsW(v11, pszPath, 260) )
              v7 = PathFileExistsW(pszPath);
            v17 = (void *)v12;
            ++v8;
            v9 = StrChrW(v12, 0x2Cu);
            if ( !v9 )
            {
              if ( !v7 )
                goto LABEL_14;
              break;
            }
          }
          ++v5;
        }
        else
        {
LABEL_14:
          v3 = SHDeleteValueW(hkey, 0, pszValue);
        }
        if ( v3 )
          break;
        cbData = 8840;
      }
      if ( v3 == 259 )
      {
        v3 = 0;
      }
      else if ( v3 > 0 )
      {
        v3 = (unsigned __int16)v3 | 0x80070000;
      }
      CoTaskMemFree(lpData);
    }
    RegCloseKey(hkey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180021cf0  push    rbp
0x180021cf2  push    rbx
0x180021cf3  push    rsi
0x180021cf4  push    rdi
0x180021cf5  push    r12
0x180021cf7  push    r13
0x180021cf9  push    r14
0x180021cfb  push    r15
0x180021cfd  lea     rbp, [rsp-398h]
0x180021d05  sub     rsp, 498h
0x180021d0c  mov     rax, cs:__security_cookie
0x180021d13  xor     rax, rsp
0x180021d16  mov     [rbp+3D0h+var_50], rax
0x180021d1d  lea     rax, [rsp+4D0h+hkey]
0x180021d22  xor     r13d, r13d
0x180021d25  mov     r9d, 20019h; samDesired
0x180021d2b  mov     [rsp+4D0h+hkey], r13
0x180021d30  xor     r8d, r8d; ulOptions
0x180021d33  mov     [rsp+4D0h+phkResult], rax; phkResult
0x180021d38  lea     rdx, aControlPanelCu_0; "Control Panel\\Cursors\\Schemes"
0x180021d3f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180021d46  call    cs:__imp_RegOpenKeyExW
0x180021d4c  mov     ebx, eax
0x180021d4e  test    eax, eax
0x180021d50  jle     short loc_180021D5B
0x180021d52  movzx   ebx, ax
0x180021d55  or      ebx, 80070000h
0x180021d5b  test    ebx, ebx
0x180021d5d  js      loc_180021EDC
0x180021d63  mov     eax, 2288h
0x180021d68  mov     ecx, eax; cb
0x180021d6a  mov     [rsp+4D0h+cbData], eax
0x180021d6e  call    cs:__imp_CoTaskMemAlloc
0x180021d74  mov     rdi, rax
0x180021d77  test    rax, rax
0x180021d7a  jz      loc_180021ED1
0x180021d80  mov     r15d, r13d
0x180021d83  xor     edx, edx
0x180021d85  jmp     loc_180021E6E
0x180021d8a  mov     edx, 2Ch ; ','; wMatch
0x180021d8f  mov     [rsp+4D0h+var_480], rdi
0x180021d94  mov     rcx, rdi; pszStart
0x180021d97  mov     sil, r13b
0x180021d9a  mov     r12d, r13d
0x180021d9d  call    cs:__imp_StrChrW
0x180021da3  mov     r14, rax
0x180021da6  test    rax, rax
0x180021da9  jz      loc_180021E4B
0x180021daf  test    sil, sil
0x180021db2  jnz     loc_180021E46
0x180021db8  movsxd  rax, r12d
0x180021dbb  lea     rcx, off_18006E940; "Arrow"
0x180021dc2  mov     rax, [rcx+rax*8]
0x180021dc6  cmp     [rax], r13w
0x180021dca  jz      short loc_180021E4B
0x180021dcc  mov     rcx, r14; lpsz
0x180021dcf  call    cs:__imp_CharNextW
0x180021dd5  mov     rcx, [rsp+4D0h+var_480]
0x180021dda  lea     rdx, [rbp+3D0h+pszPath]
0x180021de1  mov     r13, rax
0x180021de4  mov     r8d, 104h
0x180021dea  xor     eax, eax
0x180021dec  mov     [r14], ax
0x180021df0  call    cs:__imp_SHExpandEnvironmentStringsW
0x180021df6  test    eax, eax
0x180021df8  jz      short loc_180021E17
0x180021dfa  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x180021e01  call    cs:__imp_PathFileExistsW
0x180021e07  test    eax, eax
0x180021e09  movzx   esi, sil
0x180021e0d  mov     eax, 1
0x180021e12  cmovnz  esi, eax
0x180021e15  jmp     short loc_180021E1C
0x180021e17  mov     eax, 1
0x180021e1c  mov     edx, 2Ch ; ','; wMatch
0x180021e21  mov     [rsp+4D0h+var_480], r13
0x180021e26  mov     rcx, r13; pszStart
0x180021e29  add     r12d, eax
0x180021e2c  call    cs:__imp_StrChrW
0x180021e32  xor     r13d, r13d
0x180021e35  mov     r14, rax
0x180021e38  test    rax, rax
0x180021e3b  jnz     loc_180021DAF
0x180021e41  test    sil, sil
0x180021e44  jz      short loc_180021E4B
0x180021e46  inc     r15d
0x180021e49  jmp     short loc_180021E5F
0x180021e4b  mov     rcx, [rsp+4D0h+hkey]; hkey
0x180021e50  lea     r8, [rsp+4D0h+pszValue]; pszValue
0x180021e55  xor     edx, edx; pszSubKey
0x180021e57  call    cs:__imp_SHDeleteValueW
0x180021e5d  mov     ebx, eax
0x180021e5f  test    ebx, ebx
0x180021e61  jnz     short loc_180021EAE
0x180021e63  mov     [rsp+4D0h+cbData], 2288h
0x180021e6b  mov     edx, r15d; dwIndex
0x180021e6e  mov     rcx, [rsp+4D0h+hkey]; hKey
0x180021e73  lea     rax, [rsp+4D0h+cbData]
0x180021e78  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x180021e7d  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180021e82  mov     [rsp+4D0h+lpData], rdi; lpData
0x180021e87  lea     r8, [rsp+4D0h+pszValue]; lpValueName
0x180021e8c  mov     [rsp+4D0h+lpType], r13; lpType
0x180021e91  mov     [rsp+4D0h+phkResult], r13; lpReserved
0x180021e96  mov     [rsp+4D0h+cchValueName], 104h
0x180021e9e  call    cs:__imp_RegEnumValueW
0x180021ea4  mov     ebx, eax
0x180021ea6  test    eax, eax
0x180021ea8  jz      loc_180021D8A
0x180021eae  cmp     ebx, 103h
0x180021eb4  jnz     short loc_180021EBB
0x180021eb6  mov     ebx, r13d
0x180021eb9  jmp     short loc_180021EC8
0x180021ebb  test    ebx, ebx
0x180021ebd  jle     short loc_180021EC8
0x180021ebf  movzx   ebx, bx
0x180021ec2  or      ebx, 80070000h
0x180021ec8  mov     rcx, rdi; pv
0x180021ecb  call    cs:__imp_CoTaskMemFree
0x180021ed1  mov     rcx, [rsp+4D0h+hkey]; hKey
0x180021ed6  call    cs:__imp_RegCloseKey
0x180021edc  mov     eax, ebx
0x180021ede  mov     rcx, [rbp+3D0h+var_50]
0x180021ee5  xor     rcx, rsp; StackCookie
0x180021ee8  call    __security_check_cookie
0x180021eed  add     rsp, 498h
0x180021ef4  pop     r15
0x180021ef6  pop     r14
0x180021ef8  pop     r13
0x180021efa  pop     r12
0x180021efc  pop     rdi
0x180021efd  pop     rsi
0x180021efe  pop     rbx
0x180021eff  pop     rbp
0x180021f00  retn
```
