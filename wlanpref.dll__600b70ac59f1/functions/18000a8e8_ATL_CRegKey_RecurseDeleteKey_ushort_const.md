# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000a8e8`
- end: `0x18000a9f5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a8e8`
- `0x18000af10`

## callees

- `0x180005814`
- `0x180007534`
- `0x180009034`
- `0x18000a8e8`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a994`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a994`

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
0x18000a8e8  mov     [rsp-8+arg_10], rbx
0x18000a8ed  push    rbp
0x18000a8ee  push    rsi
0x18000a8ef  push    rdi
0x18000a8f0  lea     rbp, [rsp-180h]
0x18000a8f8  sub     rsp, 280h
0x18000a8ff  mov     rax, cs:__security_cookie
0x18000a906  xor     rax, rsp
0x18000a909  mov     [rbp+190h+var_20], rax
0x18000a910  mov     rsi, rdx
0x18000a913  mov     [rsp+290h+hKey], 0
0x18000a91c  mov     r8, rdx; lpSubKey
0x18000a91f  mov     [rsp+290h+var_240], 0
0x18000a928  mov     rdx, [rcx]; hKey
0x18000a92b  mov     rdi, rcx
0x18000a92e  lea     rcx, [rsp+290h+hKey]; this
0x18000a933  mov     [rsp+290h+var_238], 0
0x18000a93c  mov     r9d, 2001Fh; unsigned int
0x18000a942  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000a947  mov     ebx, eax
0x18000a949  test    eax, eax
0x18000a94b  jnz     short loc_18000A9C7
0x18000a94d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18000a956  mov     rcx, [rsp+290h+hKey]; hKey
0x18000a95b  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000a960  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000a965  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000a96a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18000a973  lea     r8, [rsp+290h+Name]; lpName
0x18000a978  mov     [rsp+290h+lpClass], 0; lpClass
0x18000a981  xor     edx, edx; dwIndex
0x18000a983  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000a98c  mov     [rsp+290h+cchName], 100h
0x18000a994  call    cs:__imp_RegEnumKeyExW
0x18000a99a  lea     rcx, [rsp+290h+hKey]; this
0x18000a99f  test    eax, eax
0x18000a9a1  jnz     short loc_18000A9B5
0x18000a9a3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000a9a8  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000a9ad  mov     ebx, eax
0x18000a9af  test    eax, eax
0x18000a9b1  jnz     short loc_18000A9C7
0x18000a9b3  jmp     short loc_18000A956
0x18000a9b5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000a9ba  mov     rdx, rsi; unsigned __int16 *
0x18000a9bd  mov     rcx, rdi; this
0x18000a9c0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000a9c5  mov     ebx, eax
0x18000a9c7  lea     rcx, [rsp+290h+hKey]; this
0x18000a9cc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000a9d1  mov     eax, ebx
0x18000a9d3  mov     rcx, [rbp+190h+var_20]
0x18000a9da  xor     rcx, rsp; StackCookie
0x18000a9dd  call    __security_check_cookie
0x18000a9e2  mov     rbx, [rsp+290h+arg_10]
0x18000a9ea  add     rsp, 280h
0x18000a9f1  pop     rdi
0x18000a9f2  pop     rsi
0x18000a9f3  pop     rbp
0x18000a9f4  retn
```
