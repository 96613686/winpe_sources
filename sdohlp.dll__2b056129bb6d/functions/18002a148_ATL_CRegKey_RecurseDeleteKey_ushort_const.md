# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18002a148`
- end: `0x18002a255`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a148`
- `0x18002a62c`

## callees

- `0x180026a40`
- `0x1800277bc`
- `0x180029c20`
- `0x18002a148`
- `0x180055030`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18002a1f4`
- `ADVAPI32!RegEnumKeyExW` at `0x18002a1f4`

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
0x18002a148  mov     [rsp-8+arg_10], rbx
0x18002a14d  push    rbp
0x18002a14e  push    rsi
0x18002a14f  push    rdi
0x18002a150  lea     rbp, [rsp-180h]
0x18002a158  sub     rsp, 280h
0x18002a15f  mov     rax, cs:__security_cookie
0x18002a166  xor     rax, rsp
0x18002a169  mov     [rbp+190h+var_20], rax
0x18002a170  mov     rsi, rdx
0x18002a173  mov     [rsp+290h+hKey], 0
0x18002a17c  mov     r8, rdx; lpSubKey
0x18002a17f  mov     [rsp+290h+var_240], 0
0x18002a188  mov     rdx, [rcx]; hKey
0x18002a18b  mov     rdi, rcx
0x18002a18e  lea     rcx, [rsp+290h+hKey]; this
0x18002a193  mov     [rsp+290h+var_238], 0
0x18002a19c  mov     r9d, 2001Fh; unsigned int
0x18002a1a2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002a1a7  mov     ebx, eax
0x18002a1a9  test    eax, eax
0x18002a1ab  jnz     short loc_18002A227
0x18002a1ad  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18002a1b6  mov     rcx, [rsp+290h+hKey]; hKey
0x18002a1bb  lea     rax, [rsp+290h+ftLastWriteTime]
0x18002a1c0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002a1c5  lea     r9, [rsp+290h+cchName]; lpcchName
0x18002a1ca  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18002a1d3  lea     r8, [rsp+290h+Name]; lpName
0x18002a1d8  mov     [rsp+290h+lpClass], 0; lpClass
0x18002a1e1  xor     edx, edx; dwIndex
0x18002a1e3  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18002a1ec  mov     [rsp+290h+cchName], 100h
0x18002a1f4  call    cs:__imp_RegEnumKeyExW
0x18002a1fa  lea     rcx, [rsp+290h+hKey]; this
0x18002a1ff  test    eax, eax
0x18002a201  jnz     short loc_18002A215
0x18002a203  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18002a208  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002a20d  mov     ebx, eax
0x18002a20f  test    eax, eax
0x18002a211  jnz     short loc_18002A227
0x18002a213  jmp     short loc_18002A1B6
0x18002a215  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a21a  mov     rdx, rsi; unsigned __int16 *
0x18002a21d  mov     rcx, rdi; this
0x18002a220  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002a225  mov     ebx, eax
0x18002a227  lea     rcx, [rsp+290h+hKey]; this
0x18002a22c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a231  mov     eax, ebx
0x18002a233  mov     rcx, [rbp+190h+var_20]
0x18002a23a  xor     rcx, rsp; StackCookie
0x18002a23d  call    __security_check_cookie
0x18002a242  mov     rbx, [rsp+290h+arg_10]
0x18002a24a  add     rsp, 280h
0x18002a251  pop     rdi
0x18002a252  pop     rsi
0x18002a253  pop     rbp
0x18002a254  retn
```
