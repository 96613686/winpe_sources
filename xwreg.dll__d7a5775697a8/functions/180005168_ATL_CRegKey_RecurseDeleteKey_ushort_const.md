# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180005168`
- end: `0x180005275`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005168`
- `0x1800055a0`

## callees

- `0x180003de4`
- `0x18000465c`
- `0x180004cc0`
- `0x180005168`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005214`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005214`

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
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, 0x2001Fu);
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
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x180005168  mov     [rsp-8+arg_10], rbx
0x18000516d  push    rbp
0x18000516e  push    rsi
0x18000516f  push    rdi
0x180005170  lea     rbp, [rsp-180h]
0x180005178  sub     rsp, 280h
0x18000517f  mov     rax, cs:__security_cookie
0x180005186  xor     rax, rsp
0x180005189  mov     [rbp+190h+var_20], rax
0x180005190  mov     rsi, rdx
0x180005193  mov     [rsp+290h+hKey], 0
0x18000519c  mov     r8, rdx; lpSubKey
0x18000519f  mov     [rsp+290h+var_240], 0
0x1800051a8  mov     rdx, [rcx]; hKey
0x1800051ab  mov     rdi, rcx
0x1800051ae  lea     rcx, [rsp+290h+hKey]; this
0x1800051b3  mov     [rsp+290h+var_238], 0
0x1800051bc  mov     r9d, 2001Fh; unsigned int
0x1800051c2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800051c7  mov     ebx, eax
0x1800051c9  test    eax, eax
0x1800051cb  jnz     short loc_180005247
0x1800051cd  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800051d6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800051db  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800051e0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800051e5  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800051ea  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800051f3  lea     r8, [rsp+290h+Name]; lpName
0x1800051f8  mov     [rsp+290h+lpClass], 0; lpClass
0x180005201  xor     edx, edx; dwIndex
0x180005203  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000520c  mov     [rsp+290h+cchName], 100h
0x180005214  call    cs:__imp_RegEnumKeyExW
0x18000521a  lea     rcx, [rsp+290h+hKey]; this
0x18000521f  test    eax, eax
0x180005221  jnz     short loc_180005235
0x180005223  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005228  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000522d  mov     ebx, eax
0x18000522f  test    eax, eax
0x180005231  jnz     short loc_180005247
0x180005233  jmp     short loc_1800051D6
0x180005235  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000523a  mov     rdx, rsi; unsigned __int16 *
0x18000523d  mov     rcx, rdi; this
0x180005240  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180005245  mov     ebx, eax
0x180005247  lea     rcx, [rsp+290h+hKey]; this
0x18000524c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005251  mov     eax, ebx
0x180005253  mov     rcx, [rbp+190h+var_20]
0x18000525a  xor     rcx, rsp; StackCookie
0x18000525d  call    __security_check_cookie
0x180005262  mov     rbx, [rsp+290h+arg_10]
0x18000526a  add     rsp, 280h
0x180005271  pop     rdi
0x180005272  pop     rsi
0x180005273  pop     rbp
0x180005274  retn
```
