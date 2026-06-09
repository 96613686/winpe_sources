# CShellWrappers::IsPathParent(ushort const *,ushort const *)

- ea: `0x18002da3c`
- end: `0x18002dac9`
- name: `?IsPathParent@CShellWrappers@@SAHPEBG0@Z`
- size: `141`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014880`
- `0x18002506c`

## callees

- `0x18002da3c`
- `0x18002dad0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002da8c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002da8c`

## pseudocode

```c
__int64 __fastcall CShellWrappers::IsPathParent(PCNZWCH lpString1, PCNZWCH lpString2)
{
  __int64 v2; // rax
  __int64 cchCount2; // rbx
  unsigned int v6; // edi

  v2 = -1;
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( lpString1[cchCount2] );
  v6 = 0;
  do
    ++v2;
  while ( lpString2[v2] );
  if ( (int)cchCount2 < (int)v2 && CompareStringW(0x7Fu, 1u, lpString1, cchCount2, lpString2, cchCount2) == 2 )
  {
    LOBYTE(v6) = (unsigned int)IsSlash(lpString1[(int)cchCount2 - 1]) != 0;
    if ( (unsigned int)IsSlash(lpString2[(int)cchCount2]) )
      return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x18002da3c  push    rbx
0x18002da3e  push    rbp
0x18002da3f  push    rsi
0x18002da40  push    rdi
0x18002da41  push    r14
0x18002da43  push    r15
0x18002da45  sub     rsp, 38h
0x18002da49  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002da4d  mov     r14, rdx
0x18002da50  mov     rbx, rax
0x18002da53  xor     ebp, ebp
0x18002da55  mov     rsi, rcx
0x18002da58  inc     rbx
0x18002da5b  cmp     [rcx+rbx*2], bp
0x18002da5f  jnz     short loc_18002DA58
0x18002da61  mov     edi, ebp
0x18002da63  inc     rax
0x18002da66  cmp     [rdx+rax*2], bp
0x18002da6a  jnz     short loc_18002DA63
0x18002da6c  cmp     ebx, eax
0x18002da6e  jge     short loc_18002DABA
0x18002da70  mov     r15d, 1
0x18002da76  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x18002da7a  mov     r9d, ebx; cchCount1
0x18002da7d  mov     [rsp+68h+lpString2], r14; lpString2
0x18002da82  mov     r8, rsi; lpString1
0x18002da85  mov     edx, r15d; dwCmpFlags
0x18002da88  lea     ecx, [r15+7Eh]; Locale
0x18002da8c  call    cs:__imp_CompareStringW
0x18002da92  cmp     eax, 2
0x18002da95  jnz     short loc_18002DABA
0x18002da97  movsxd  rbx, ebx
0x18002da9a  movzx   ecx, word ptr [rsi+rbx*2-2]; unsigned __int16
0x18002da9f  call    ?IsSlash@@YAHG@Z; IsSlash(ushort)
0x18002daa4  movzx   ecx, word ptr [r14+rbx*2]; unsigned __int16
0x18002daa9  test    eax, eax
0x18002daab  setnz   dil
0x18002daaf  call    ?IsSlash@@YAHG@Z; IsSlash(ushort)
0x18002dab4  test    eax, eax
0x18002dab6  cmovnz  edi, r15d
0x18002daba  mov     eax, edi
0x18002dabc  add     rsp, 38h
0x18002dac0  pop     r15
0x18002dac2  pop     r14
0x18002dac4  pop     rdi
0x18002dac5  pop     rsi
0x18002dac6  pop     rbp
0x18002dac7  pop     rbx
0x18002dac8  retn
```
