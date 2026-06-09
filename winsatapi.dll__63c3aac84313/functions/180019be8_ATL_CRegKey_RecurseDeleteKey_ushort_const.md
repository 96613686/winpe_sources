# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180019be8`
- end: `0x180019cf5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180019be8`
- `0x18001a0e0`

## callees

- `0x18000e234`
- `0x1800173a4`
- `0x1800186d0`
- `0x180019be8`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019c94`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019c94`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open(hKey, *this, a2, 0x2001Fu);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_7;
    }
    ATL::CRegKey::Close(hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close(hKey);
  return v4;
}

```

## disassembly

```asm
0x180019be8  mov     [rsp-8+arg_10], rbx
0x180019bed  push    rbp
0x180019bee  push    rsi
0x180019bef  push    rdi
0x180019bf0  lea     rbp, [rsp-180h]
0x180019bf8  sub     rsp, 280h
0x180019bff  mov     rax, cs:__security_cookie
0x180019c06  xor     rax, rsp
0x180019c09  mov     [rbp+190h+var_20], rax
0x180019c10  mov     rsi, rdx
0x180019c13  mov     [rsp+290h+hKey], 0
0x180019c1c  mov     r8, rdx; lpSubKey
0x180019c1f  mov     [rsp+290h+var_240], 0
0x180019c28  mov     rdx, [rcx]; hKey
0x180019c2b  mov     rdi, rcx
0x180019c2e  lea     rcx, [rsp+290h+hKey]; this
0x180019c33  mov     [rsp+290h+var_238], 0
0x180019c3c  mov     r9d, 2001Fh; unsigned int
0x180019c42  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019c47  mov     ebx, eax
0x180019c49  test    eax, eax
0x180019c4b  jnz     short loc_180019CC7
0x180019c4d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180019c56  mov     rcx, [rsp+290h+hKey]; hKey
0x180019c5b  lea     rax, [rsp+290h+ftLastWriteTime]
0x180019c60  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180019c65  lea     r9, [rsp+290h+cchName]; lpcchName
0x180019c6a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180019c73  lea     r8, [rsp+290h+Name]; lpName
0x180019c78  mov     [rsp+290h+lpClass], 0; lpClass
0x180019c81  xor     edx, edx; dwIndex
0x180019c83  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180019c8c  mov     [rsp+290h+cchName], 100h
0x180019c94  call    cs:__imp_RegEnumKeyExW
0x180019c9a  lea     rcx, [rsp+290h+hKey]; this
0x180019c9f  test    eax, eax
0x180019ca1  jnz     short loc_180019CB5
0x180019ca3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180019ca8  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180019cad  mov     ebx, eax
0x180019caf  test    eax, eax
0x180019cb1  jnz     short loc_180019CC7
0x180019cb3  jmp     short loc_180019C56
0x180019cb5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019cba  mov     rdx, rsi; unsigned __int16 *
0x180019cbd  mov     rcx, rdi; this
0x180019cc0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180019cc5  mov     ebx, eax
0x180019cc7  lea     rcx, [rsp+290h+hKey]; this
0x180019ccc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019cd1  mov     eax, ebx
0x180019cd3  mov     rcx, [rbp+190h+var_20]
0x180019cda  xor     rcx, rsp; StackCookie
0x180019cdd  call    __security_check_cookie
0x180019ce2  mov     rbx, [rsp+290h+arg_10]
0x180019cea  add     rsp, 280h
0x180019cf1  pop     rdi
0x180019cf2  pop     rsi
0x180019cf3  pop     rbp
0x180019cf4  retn
```
