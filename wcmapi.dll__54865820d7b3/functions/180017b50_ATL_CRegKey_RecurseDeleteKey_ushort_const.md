# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180017b50`
- end: `0x180017c68`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `280`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006750`
- `0x180007db0`
- `0x180008010`
- `0x180017b50`

## callees

- `0x1800075e8`
- `0x180008a90`
- `0x180017588`
- `0x180017a60`
- `0x180017b50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017c00`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017c00`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  HKEY hKey[3]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
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
0x180017b50  mov     [rsp-8+arg_10], rbx
0x180017b55  push    rbp
0x180017b56  push    rsi
0x180017b57  push    rdi
0x180017b58  lea     rbp, [rsp-180h]
0x180017b60  sub     rsp, 280h
0x180017b67  mov     rax, cs:__security_cookie
0x180017b6e  xor     rax, rsp
0x180017b71  mov     [rbp+190h+var_20], rax
0x180017b78  mov     rsi, rdx
0x180017b7b  mov     [rsp+290h+hKey], 0
0x180017b84  mov     r8, rdx; lpSubKey
0x180017b87  mov     [rsp+290h+var_248], 0
0x180017b90  mov     rdx, [rcx]; hKey
0x180017b93  mov     rdi, rcx
0x180017b96  lea     rcx, [rsp+290h+hKey]; this
0x180017b9b  mov     [rsp+290h+var_240], 0
0x180017ba4  mov     r9d, 2001Fh; unsigned int
0x180017baa  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180017baf  mov     ebx, eax
0x180017bb1  test    eax, eax
0x180017bb3  jnz     loc_180017C39
0x180017bb9  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180017bc2  mov     rcx, [rsp+290h+hKey]; hKey
0x180017bc7  lea     rax, [rsp+290h+ftLastWriteTime]
0x180017bcc  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180017bd1  lea     r9, [rsp+290h+cchName]; lpcchName
0x180017bd6  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180017bdf  lea     r8, [rsp+290h+Name]; lpName
0x180017be4  mov     [rsp+290h+lpClass], 0; lpClass
0x180017bed  xor     edx, edx; dwIndex
0x180017bef  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180017bf8  mov     [rsp+290h+cchName], 100h
0x180017c00  call    cs:__imp_RegEnumKeyExW
0x180017c07  nop     dword ptr [rax+rax+00h]
0x180017c0c  lea     rcx, [rsp+290h+hKey]; this
0x180017c11  test    eax, eax
0x180017c13  jnz     short loc_180017C27
0x180017c15  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180017c1a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180017c1f  mov     ebx, eax
0x180017c21  test    eax, eax
0x180017c23  jnz     short loc_180017C39
0x180017c25  jmp     short loc_180017BC2
0x180017c27  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017c2c  mov     rdx, rsi; unsigned __int16 *
0x180017c2f  mov     rcx, rdi; this
0x180017c32  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180017c37  mov     ebx, eax
0x180017c39  lea     rcx, [rsp+290h+hKey]; this
0x180017c3e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017c43  mov     eax, ebx
0x180017c45  mov     rcx, [rbp+190h+var_20]
0x180017c4c  xor     rcx, rsp; StackCookie
0x180017c4f  call    __security_check_cookie
0x180017c54  mov     rbx, [rsp+290h+arg_10]
0x180017c5c  add     rsp, 280h
0x180017c63  pop     rdi
0x180017c64  pop     rsi
0x180017c65  pop     rbp
0x180017c66  retn
```
