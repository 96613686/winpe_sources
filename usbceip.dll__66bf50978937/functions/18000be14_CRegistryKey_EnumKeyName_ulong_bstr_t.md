# CRegistryKey::EnumKeyName(ulong,_bstr_t &)

- ea: `0x18000be14`
- end: `0x18000beb5`
- name: `?EnumKeyName@CRegistryKey@@AEAAEKAEAV_bstr_t@@@Z`
- size: `161`
- prototype: `unsigned __int8 __fastcall(HKEY *this, DWORD, struct _bstr_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c01c`

## callees

- `0x180002410`
- `0x180007afc`
- `0x180008020`
- `0x18000be14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000be6b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000be6b`

## pseudocode

```c
unsigned __int8 __fastcall CRegistryKey::EnumKeyName(HKEY *this, DWORD a2, struct _bstr_t *a3)
{
  HKEY v3; // rcx
  unsigned int v5; // eax
  DWORD cchName[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR Name[256]; // [rsp+50h] [rbp-218h] BYREF

  v3 = *this;
  cchName[0] = 256;
  v5 = RegEnumKeyExW(v3, a2, Name, cchName, 0, 0, 0, 0);
  if ( v5 == 259 )
    return 0;
  if ( v5 )
    CException::ThrowException(v5, 0, 0);
  _bstr_t::operator=(a3, Name);
  return 1;
}

```

## disassembly

```asm
0x18000be14  push    rbx
0x18000be16  sub     rsp, 260h
0x18000be1d  mov     rax, cs:__security_cookie
0x18000be24  xor     rax, rsp
0x18000be27  mov     [rsp+268h+var_18], rax
0x18000be2f  mov     rcx, [rcx]; hKey
0x18000be32  lea     r9, [rsp+268h+cchName]; lpcchName
0x18000be37  mov     [rsp+268h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000be40  mov     rbx, r8
0x18000be43  mov     [rsp+268h+lpcchClass], 0; lpcchClass
0x18000be4c  lea     r8, [rsp+268h+Name]; lpName
0x18000be51  mov     [rsp+268h+lpClass], 0; lpClass
0x18000be5a  mov     [rsp+268h+lpReserved], 0; lpReserved
0x18000be63  mov     [rsp+268h+cchName], 100h
0x18000be6b  call    cs:__imp_RegEnumKeyExW
0x18000be71  cmp     eax, 103h
0x18000be76  jnz     short loc_18000BE7C
0x18000be78  xor     al, al
0x18000be7a  jmp     short loc_18000BE9C
0x18000be7c  test    eax, eax
0x18000be7e  jz      short loc_18000BE8D
0x18000be80  xor     r8d, r8d
0x18000be83  xor     edx, edx
0x18000be85  mov     ecx, eax
0x18000be87  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000be8d  lea     rdx, [rsp+268h+Name]
0x18000be92  mov     rcx, rbx
0x18000be95  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000be9a  mov     al, 1
0x18000be9c  mov     rcx, [rsp+268h+var_18]
0x18000bea4  xor     rcx, rsp; StackCookie
0x18000bea7  call    __security_check_cookie
0x18000beac  add     rsp, 260h
0x18000beb3  pop     rbx
0x18000beb4  retn
```
