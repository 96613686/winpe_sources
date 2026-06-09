# CSecurityInformation::GetObjectInformation(_SI_OBJECT_INFO *)

- ea: `0x18000c1f0`
- end: `0x18000c22a`
- name: `?GetObjectInformation@CSecurityInformation@@UEAAJPEAU_SI_OBJECT_INFO@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(CSecurityInformation *__hidden this, struct _SI_OBJECT_INFO *)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000c1f0`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::GetObjectInformation(CSecurityInformation *this, struct _SI_OBJECT_INFO *a2)
{
  if ( !a2 )
    return 2147500035LL;
  a2->dwFlags = *((_DWORD *)this + 16) | 0x800;
  a2->hInstance = g_hInstance;
  a2->pszServerName = (LPWSTR)*((_QWORD *)this + 9);
  a2->pszObjectName = (LPWSTR)*((_QWORD *)this + 10);
  a2->pszPageTitle = (LPWSTR)((char *)this + 108);
  return 0;
}

```

## disassembly

```asm
0x18000c1f0  test    rdx, rdx
0x18000c1f3  jnz     short loc_18000C1FB
0x18000c1f5  mov     eax, 80004003h
0x18000c1fa  retn
0x18000c1fb  mov     eax, [rcx+40h]
0x18000c1fe  bts     eax, 0Bh
0x18000c202  mov     [rdx], eax
0x18000c204  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18000c20b  mov     [rdx+8], rax
0x18000c20f  mov     rax, [rcx+48h]
0x18000c213  mov     [rdx+10h], rax
0x18000c217  mov     rax, [rcx+50h]
0x18000c21b  mov     [rdx+18h], rax
0x18000c21f  lea     rax, [rcx+6Ch]
0x18000c223  mov     [rdx+20h], rax
0x18000c227  xor     eax, eax
0x18000c229  retn
```
