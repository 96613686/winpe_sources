# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004a08`
- end: `0x180004b07`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004a08`
- `0x180004f1c`

## callees

- `0x1800041b0`
- `0x1800041e0`
- `0x180004754`
- `0x180004a08`
- `0x18001e9f0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180004a9f`
- `ADVAPI32!RegEnumKeyExW` at `0x180004a9f`

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
0x180004a08  mov     [rsp-8+arg_10], rbx
0x180004a0d  push    rbp
0x180004a0e  push    rsi
0x180004a0f  push    rdi
0x180004a10  lea     rbp, [rsp-180h]
0x180004a18  sub     rsp, 280h
0x180004a1f  mov     rax, cs:__security_cookie
0x180004a26  xor     rax, rsp
0x180004a29  mov     [rbp+190h+var_20], rax
0x180004a30  and     [rsp+290h+hKey], 0
0x180004a36  mov     rsi, rdx
0x180004a39  and     [rsp+290h+var_240], 0
0x180004a3f  mov     r8, rdx; lpSubKey
0x180004a42  mov     rdx, [rcx]; hKey
0x180004a45  mov     rdi, rcx
0x180004a48  and     [rsp+290h+var_238], 0
0x180004a4e  lea     rcx, [rsp+290h+hKey]; this
0x180004a53  mov     r9d, 2001Fh; unsigned int
0x180004a59  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180004a5e  mov     ebx, eax
0x180004a60  test    eax, eax
0x180004a62  jnz     short loc_180004AD8
0x180004a64  and     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180004a6a  mov     rcx, [rsp+290h+hKey]; hKey
0x180004a6f  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004a74  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004a79  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004a7e  and     [rsp+290h+var_260], 0
0x180004a84  lea     r8, [rsp+290h+Name]; lpName
0x180004a89  and     [rsp+290h+var_268], 0
0x180004a8f  xor     edx, edx; dwIndex
0x180004a91  and     [rsp+290h+var_270], 0
0x180004a97  mov     [rsp+290h+cchName], 100h
0x180004a9f  call    cs:__imp_RegEnumKeyExW
0x180004aa6  nop     dword ptr [rax+rax+00h]
0x180004aab  lea     rcx, [rsp+290h+hKey]; this
0x180004ab0  test    eax, eax
0x180004ab2  jnz     short loc_180004AC6
0x180004ab4  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004ab9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004abe  mov     ebx, eax
0x180004ac0  test    eax, eax
0x180004ac2  jnz     short loc_180004AD8
0x180004ac4  jmp     short loc_180004A6A
0x180004ac6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004acb  mov     rdx, rsi; unsigned __int16 *
0x180004ace  mov     rcx, rdi; this
0x180004ad1  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004ad6  mov     ebx, eax
0x180004ad8  lea     rcx, [rsp+290h+hKey]; this
0x180004add  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004ae2  mov     eax, ebx
0x180004ae4  mov     rcx, [rbp+190h+var_20]
0x180004aeb  xor     rcx, rsp; StackCookie
0x180004aee  call    __security_check_cookie
0x180004af3  mov     rbx, [rsp+290h+arg_10]
0x180004afb  add     rsp, 280h
0x180004b02  pop     rdi
0x180004b03  pop     rsi
0x180004b04  pop     rbp
0x180004b05  retn
```
