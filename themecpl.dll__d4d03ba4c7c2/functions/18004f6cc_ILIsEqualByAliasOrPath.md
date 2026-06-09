# ILIsEqualByAliasOrPath

- ea: `0x18004f6cc`
- end: `0x18004f803`
- name: `ILIsEqualByAliasOrPath`
- size: `311`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, LPCITEMIDLIST)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003d500`
- `0x18003f4dc`
- `0x180042154`
- `0x1800423e0`
- `0x180042ab4`

## callees

- `0x180002280`
- `0x18004f6cc`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x18004f788`
- `SHELL32!SHGetPathFromIDListW` at `0x18004f7a0`
- `SHELL32!SHGetPathFromIDListW` at `0x18004f788`
- `SHELL32!SHGetPathFromIDListW` at `0x18004f7a0`
- `SHELL32!__imp_ILIsEqual` at `0x18004f6f9`
- `SHELL32!__imp_ILIsEqual` at `0x18004f744`
- `SHELL32!__imp_ILIsEqual` at `0x18004f6f9`
- `SHELL32!__imp_ILIsEqual` at `0x18004f744`
- `SHELL32!__imp_SHLogILFromFSIL` at `0x18004f70c`
- `SHELL32!__imp_SHLogILFromFSIL` at `0x18004f728`
- `SHELL32!__imp_SHLogILFromFSIL` at `0x18004f70c`
- `SHELL32!__imp_SHLogILFromFSIL` at `0x18004f728`
- `SHELL32!__imp_ILFree` at `0x18004f755`
- `SHELL32!__imp_ILFree` at `0x18004f764`
- `SHELL32!__imp_ILFree` at `0x18004f755`
- `SHELL32!__imp_ILFree` at `0x18004f764`
- `SHELL32!__imp_PathComparePaths` at `0x18004f7bd`
- `SHELL32!__imp_PathComparePaths` at `0x18004f7bd`

## pseudocode

```c
__int64 __fastcall ILIsEqualByAliasOrPath(LPCITEMIDLIST pidl, LPCITEMIDLIST a2)
{
  __int64 v4; // rax
  const ITEMIDLIST *v5; // rbx
  ITEMIDLIST *v6; // rsi
  __int64 v7; // rax
  const ITEMIDLIST *v8; // rdx
  ITEMIDLIST *v9; // rdi
  BOOL v10; // ebx
  unsigned int v11; // ebx
  WCHAR v13[264]; // [rsp+20h] [rbp-448h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp-238h] BYREF

  if ( ILIsEqual(pidl, a2) )
    return 1;
  v4 = SHLogILFromFSIL(pidl);
  v5 = pidl;
  v6 = (ITEMIDLIST *)v4;
  if ( v4 )
    v5 = (const ITEMIDLIST *)v4;
  v7 = SHLogILFromFSIL(a2);
  v8 = a2;
  v9 = (ITEMIDLIST *)v7;
  if ( v7 )
    v8 = (const ITEMIDLIST *)v7;
  v10 = ILIsEqual(v5, v8);
  ILFree(v6);
  ILFree(v9);
  if ( v10 )
  {
    return 1;
  }
  else
  {
    v11 = 0;
    if ( SHGetPathFromIDListW(pidl, pszPath) && SHGetPathFromIDListW(a2, v13) )
      return (unsigned int)PathComparePaths(pszPath, v13) == 2;
  }
  return v11;
}

```

## disassembly

```asm
0x18004f6cc  mov     [rsp+arg_10], rbx
0x18004f6d1  mov     [rsp+arg_18], rbp
0x18004f6d6  push    rsi
0x18004f6d7  push    rdi
0x18004f6d8  push    r14
0x18004f6da  sub     rsp, 450h
0x18004f6e1  mov     rax, cs:__security_cookie
0x18004f6e8  xor     rax, rsp
0x18004f6eb  mov     [rsp+468h+var_28], rax
0x18004f6f3  mov     r14, rdx
0x18004f6f6  mov     rbp, rcx
0x18004f6f9  call    cs:__imp_ILIsEqual
0x18004f700  nop     dword ptr [rax+rax+00h]
0x18004f705  test    eax, eax
0x18004f707  jnz     short loc_18004F774
0x18004f709  mov     rcx, rbp
0x18004f70c  call    cs:__imp_SHLogILFromFSIL
0x18004f713  nop     dword ptr [rax+rax+00h]
0x18004f718  mov     rbx, rbp
0x18004f71b  mov     rcx, r14
0x18004f71e  test    rax, rax
0x18004f721  mov     rsi, rax
0x18004f724  cmovnz  rbx, rax
0x18004f728  call    cs:__imp_SHLogILFromFSIL
0x18004f72f  nop     dword ptr [rax+rax+00h]
0x18004f734  mov     rdx, r14
0x18004f737  mov     rcx, rbx; pidl1
0x18004f73a  test    rax, rax
0x18004f73d  mov     rdi, rax
0x18004f740  cmovnz  rdx, rax; pidl2
0x18004f744  call    cs:__imp_ILIsEqual
0x18004f74b  nop     dword ptr [rax+rax+00h]
0x18004f750  mov     rcx, rsi; pidl
0x18004f753  mov     ebx, eax
0x18004f755  call    cs:__imp_ILFree
0x18004f75c  nop     dword ptr [rax+rax+00h]
0x18004f761  mov     rcx, rdi; pidl
0x18004f764  call    cs:__imp_ILFree
0x18004f76b  nop     dword ptr [rax+rax+00h]
0x18004f770  test    ebx, ebx
0x18004f772  jz      short loc_18004F77B
0x18004f774  mov     ebx, 1
0x18004f779  jmp     short loc_18004F7D8
0x18004f77b  lea     rdx, [rsp+468h+pszPath]; pszPath
0x18004f783  mov     rcx, rbp; pidl
0x18004f786  xor     ebx, ebx
0x18004f788  call    cs:__imp_SHGetPathFromIDListW
0x18004f78f  nop     dword ptr [rax+rax+00h]
0x18004f794  test    eax, eax
0x18004f796  jz      short loc_18004F7D8
0x18004f798  lea     rdx, [rsp+468h+var_448]; pszPath
0x18004f79d  mov     rcx, r14; pidl
0x18004f7a0  call    cs:__imp_SHGetPathFromIDListW
0x18004f7a7  nop     dword ptr [rax+rax+00h]
0x18004f7ac  test    eax, eax
0x18004f7ae  jz      short loc_18004F7D8
0x18004f7b0  lea     rdx, [rsp+468h+var_448]
0x18004f7b5  lea     rcx, [rsp+468h+pszPath]
0x18004f7bd  call    cs:__imp_PathComparePaths
0x18004f7c4  nop     dword ptr [rax+rax+00h]
0x18004f7c9  mov     ecx, ebx
0x18004f7cb  mov     ebx, 1
0x18004f7d0  cmp     eax, 2
0x18004f7d3  cmovz   ecx, ebx
0x18004f7d6  mov     ebx, ecx
0x18004f7d8  mov     eax, ebx
0x18004f7da  mov     rcx, [rsp+468h+var_28]
0x18004f7e2  xor     rcx, rsp; StackCookie
0x18004f7e5  call    __security_check_cookie
0x18004f7ea  lea     r11, [rsp+468h+var_18]
0x18004f7f2  mov     rbx, [r11+30h]
0x18004f7f6  mov     rbp, [r11+38h]
0x18004f7fa  mov     rsp, r11
0x18004f7fd  pop     r14
0x18004f7ff  pop     rdi
0x18004f800  pop     rsi
0x18004f801  retn
```
