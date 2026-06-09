# CShareSecurityInformation::GetObjectInformation(_SI_OBJECT_INFO *)

- ea: `0x18000afb0`
- end: `0x18000afe9`
- name: `?GetObjectInformation@CShareSecurityInformation@@UEAAJPEAU_SI_OBJECT_INFO@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(CShareSecurityInformation *__hidden this, struct _SI_OBJECT_INFO *)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000afb0`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::GetObjectInformation(
        CShareSecurityInformation *this,
        struct _SI_OBJECT_INFO *a2)
{
  if ( !a2 )
    return 2147500035LL;
  a2->dwFlags = *((_DWORD *)this + 66);
  a2->hInstance = g_hInstance;
  a2->pszServerName = (LPWSTR)*((_QWORD *)this + 2);
  a2->pszObjectName = (LPWSTR)*((_QWORD *)this + 1);
  a2->pszPageTitle = (LPWSTR)((char *)this + 28);
  return 0;
}

```

## disassembly

```asm
0x18000afb0  test    rdx, rdx
0x18000afb3  jnz     short loc_18000AFBB
0x18000afb5  mov     eax, 80004003h
0x18000afba  retn
0x18000afbb  mov     eax, [rcx+108h]
0x18000afc1  mov     [rdx], eax
0x18000afc3  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18000afca  mov     [rdx+8], rax
0x18000afce  mov     rax, [rcx+10h]
0x18000afd2  mov     [rdx+10h], rax
0x18000afd6  mov     rax, [rcx+8]
0x18000afda  mov     [rdx+18h], rax
0x18000afde  lea     rax, [rcx+1Ch]
0x18000afe2  mov     [rdx+20h], rax
0x18000afe6  xor     eax, eax
0x18000afe8  retn
```
