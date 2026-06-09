# CWdsTptNamespaceStore::Initialize(ushort const *,ushort const *)

- ea: `0x18001b8b4`
- end: `0x18001b988`
- name: `?Initialize@CWdsTptNamespaceStore@@AEAAKPEBG0@Z`
- size: `212`
- prototype: `unsigned int(CWdsTptNamespaceStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a9ec`

## callees

- `0x18001b8b4`
- `0x180025850`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001b902`
- `ADVAPI32!RegCloseKey` at `0x18001b913`
- `ADVAPI32!RegCloseKey` at `0x18001b946`
- `ADVAPI32!RegCloseKey` at `0x18001b902`
- `ADVAPI32!RegCloseKey` at `0x18001b913`
- `ADVAPI32!RegCloseKey` at `0x18001b946`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b934`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b934`

## pseudocode

```c
__int64 __fastcall CWdsTptNamespaceStore::Initialize(
        CWdsTptNamespaceStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  HKEY *phkResult; // rbx
  HKEY v7; // rcx
  const char *v8; // rdx

  if ( *(_DWORD *)this )
  {
    return 1247;
  }
  else if ( a3 && *a3 )
  {
    phkResult = (HKEY *)((char *)this + 48);
    v7 = (HKEY)*((_QWORD *)this + 6);
    if ( v7 )
    {
      RegCloseKey(v7);
      *phkResult = 0;
    }
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0xF013Fu, phkResult);
    if ( !ElValidateWin32(v5, v8, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x7BFu) )
      *(_DWORD *)this = 1;
  }
  else
  {
    return 87;
  }
  return v5;
}

```

## disassembly

```asm
0x18001b8b4  mov     rax, rsp
0x18001b8b7  mov     [rax+8], rbx
0x18001b8bb  mov     [rax+18h], rbp
0x18001b8bf  mov     [rax+20h], rsi
0x18001b8c3  mov     [rax+10h], rdx
0x18001b8c7  push    rdi
0x18001b8c8  sub     rsp, 30h
0x18001b8cc  xor     ebp, ebp
0x18001b8ce  mov     rdi, r8
0x18001b8d1  mov     rsi, rcx
0x18001b8d4  cmp     [rcx], ebp
0x18001b8d6  jz      short loc_18001B8E2
0x18001b8d8  mov     ebx, 4DFh
0x18001b8dd  jmp     loc_18001B971
0x18001b8e2  test    rdi, rdi
0x18001b8e5  jz      loc_18001B96C
0x18001b8eb  cmp     [r8], bp
0x18001b8ef  jz      short loc_18001B96C
0x18001b8f1  lea     rbx, [rcx+30h]
0x18001b8f5  mov     [rsp+38h+hKey], rbp
0x18001b8fa  mov     rcx, [rbx]; hKey
0x18001b8fd  test    rcx, rcx
0x18001b900  jz      short loc_18001B91C
0x18001b902  call    cs:__imp_RegCloseKey
0x18001b908  mov     rcx, rbp; hKey
0x18001b90b  mov     [rbx], rbp
0x18001b90e  test    rcx, rcx
0x18001b911  jz      short loc_18001B91C
0x18001b913  call    cs:__imp_RegCloseKey
0x18001b919  mov     [rbx], rbp
0x18001b91c  mov     r9d, 0F013Fh; samDesired
0x18001b922  mov     [rsp+38h+phkResult], rbx; phkResult
0x18001b927  xor     r8d, r8d; ulOptions
0x18001b92a  mov     rdx, rdi; lpSubKey
0x18001b92d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b934  call    cs:__imp_RegOpenKeyExW
0x18001b93a  mov     rcx, [rsp+38h+hKey]; hKey
0x18001b93f  mov     ebx, eax
0x18001b941  test    rcx, rcx
0x18001b944  jz      short loc_18001B94C
0x18001b946  call    cs:__imp_RegCloseKey
0x18001b94c  mov     r9d, 7BFh; unsigned int
0x18001b952  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b959  mov     ecx, ebx; unsigned int
0x18001b95b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b960  test    eax, eax
0x18001b962  jnz     short loc_18001B971
0x18001b964  mov     dword ptr [rsi], 1
0x18001b96a  jmp     short loc_18001B971
0x18001b96c  mov     ebx, 57h ; 'W'
0x18001b971  mov     rbp, [rsp+38h+arg_10]
0x18001b976  mov     eax, ebx
0x18001b978  mov     rbx, [rsp+38h+arg_0]
0x18001b97d  mov     rsi, [rsp+38h+arg_18]
0x18001b982  add     rsp, 30h
0x18001b986  pop     rdi
0x18001b987  retn
```
