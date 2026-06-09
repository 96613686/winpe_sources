# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x180007aac`
- end: `0x180007bd4`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `296`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007aac`
- `0x180007ee0`

## callees

- `0x1800079ac`
- `0x180007aac`
- `0x180007c10`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007b6a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007b6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ba5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ba5`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(ATL::CRegKey *this, const wchar_t *a2)
{
  int v2; // r9d
  HKEY v5; // rdx
  unsigned int v7; // eax
  HKEY v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  LSTATUS v11; // eax
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  v2 = *((_DWORD *)this + 2);
  v14 = 0;
  hKey = 0;
  v5 = *(HKEY *)this;
  v15 = 0;
  v7 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v5, a2, v2 | 0x2001Fu);
  v8 = hKey;
  v9 = v7;
  if ( !v7 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v8, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v10 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, Name);
      v8 = hKey;
      v9 = v10;
      if ( v10 )
        goto LABEL_8;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    LODWORD(v14) = 0;
    v11 = ATL::CRegKey::DeleteSubKey(this, a2);
    v8 = hKey;
    v9 = v11;
  }
LABEL_8:
  if ( v8 )
    RegCloseKey(v8);
  return v9;
}

```

## disassembly

```asm
0x180007aac  mov     [rsp-8+arg_10], rbx
0x180007ab1  mov     [rsp-8+arg_18], rsi
0x180007ab6  push    rbp
0x180007ab7  push    rdi
0x180007ab8  push    r14
0x180007aba  lea     rbp, [rsp-180h]
0x180007ac2  sub     rsp, 280h
0x180007ac9  mov     rax, cs:__security_cookie
0x180007ad0  xor     rax, rsp
0x180007ad3  mov     [rbp+190h+var_20], rax
0x180007ada  mov     r9d, [rcx+8]
0x180007ade  xor     r14d, r14d
0x180007ae1  mov     rsi, rdx
0x180007ae4  mov     [rsp+290h+var_248], r14
0x180007ae9  mov     r8, rdx; wchar_t *
0x180007aec  mov     [rsp+290h+hKey], r14
0x180007af1  mov     rdx, [rcx]; HKEY
0x180007af4  mov     rdi, rcx
0x180007af7  or      r9d, 2001Fh; unsigned int
0x180007afe  mov     [rsp+290h+var_240], r14
0x180007b03  lea     rcx, [rsp+290h+hKey]; this
0x180007b08  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180007b0d  mov     rcx, [rsp+290h+hKey]
0x180007b12  mov     ebx, eax
0x180007b14  test    eax, eax
0x180007b16  jnz     loc_180007BA0
0x180007b1c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180007b21  jmp     short loc_180007B3D
0x180007b23  lea     rdx, [rsp+290h+Name]; wchar_t *
0x180007b28  lea     rcx, [rsp+290h+hKey]; this
0x180007b2d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x180007b32  mov     rcx, [rsp+290h+hKey]; hKey
0x180007b37  mov     ebx, eax
0x180007b39  test    eax, eax
0x180007b3b  jnz     short loc_180007BA0
0x180007b3d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180007b42  mov     [rsp+290h+cchName], 100h
0x180007b4a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007b4f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180007b54  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180007b59  lea     r8, [rsp+290h+Name]; lpName
0x180007b5e  mov     [rsp+290h+lpClass], r14; lpClass
0x180007b63  xor     edx, edx; dwIndex
0x180007b65  mov     [rsp+290h+lpReserved], r14; lpReserved
0x180007b6a  call    cs:__imp_RegEnumKeyExW
0x180007b70  test    eax, eax
0x180007b72  jz      short loc_180007B23
0x180007b74  mov     rcx, [rsp+290h+hKey]; hKey
0x180007b79  test    rcx, rcx
0x180007b7c  jz      short loc_180007B89
0x180007b7e  call    cs:__imp_RegCloseKey
0x180007b84  mov     [rsp+290h+hKey], r14
0x180007b89  mov     rdx, rsi; wchar_t *
0x180007b8c  mov     dword ptr [rsp+290h+var_248], r14d
0x180007b91  mov     rcx, rdi; this
0x180007b94  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180007b99  mov     rcx, [rsp+290h+hKey]; hKey
0x180007b9e  mov     ebx, eax
0x180007ba0  test    rcx, rcx
0x180007ba3  jz      short loc_180007BAB
0x180007ba5  call    cs:__imp_RegCloseKey
0x180007bab  mov     eax, ebx
0x180007bad  mov     rcx, [rbp+190h+var_20]
0x180007bb4  xor     rcx, rsp; StackCookie
0x180007bb7  call    __security_check_cookie
0x180007bbc  lea     r11, [rsp+290h+var_10]
0x180007bc4  mov     rbx, [r11+30h]
0x180007bc8  mov     rsi, [r11+38h]
0x180007bcc  mov     rsp, r11
0x180007bcf  pop     r14
0x180007bd1  pop     rdi
0x180007bd2  pop     rbp
0x180007bd3  retn
```
