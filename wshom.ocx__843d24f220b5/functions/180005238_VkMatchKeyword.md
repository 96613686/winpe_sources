# VkMatchKeyword

- ea: `0x180005238`
- end: `0x1800052f0`
- name: `VkMatchKeyword`
- size: `184`
- prototype: `__int64 __fastcall(PCNZCH lpString2)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004704`

## callees

- `0x1800051b8`
- `0x180005238`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x18000527b`
- `KERNEL32!CompareStringA` at `0x18000527b`

## pseudocode

```c
__int64 __fastcall VkMatchKeyword(PCNZCH lpString2, int a2)
{
  char **v2; // rbx
  int cchCount2; // edi
  __int64 result; // rax

  v2 = &off_180012400;
  cchCount2 = a2 - (_DWORD)lpString2;
  while ( v2 < (char **)&ExceptionInfo )
  {
    if ( CompareStringA(0x409u, 3u, *v2, -1, lpString2, cchCount2) == 2 )
      return *((unsigned __int8 *)v2 + 8);
    v2 += 2;
  }
  result = VkSearchTable(lpString2, cchCount2);
  if ( (_DWORD)result != -1 )
  {
    if ( dword_180018BE4 )
      return result;
    return 0;
  }
  result = VkSearchTable(lpString2, cchCount2);
  if ( (_DWORD)result != -1 && !dword_180018BE0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180005238  mov     [rsp+arg_0], rbx
0x18000523d  mov     [rsp+arg_8], rsi
0x180005242  push    rdi
0x180005243  sub     rsp, 30h
0x180005247  mov     rdi, rdx
0x18000524a  lea     rbx, off_180012400; "ENTER"
0x180005251  sub     edi, ecx
0x180005253  mov     rsi, rcx
0x180005256  lea     rax, ExceptionInfo
0x18000525d  cmp     rbx, rax
0x180005260  jnb     short loc_180005292
0x180005262  mov     r8, [rbx]; lpString1
0x180005265  or      r9d, 0FFFFFFFFh; cchCount1
0x180005269  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18000526d  mov     ecx, 409h; Locale
0x180005272  mov     [rsp+38h+lpString2], rsi; lpString2
0x180005277  lea     edx, [r9+4]; dwCmpFlags
0x18000527b  call    cs:__imp_CompareStringA
0x180005281  cmp     eax, 2
0x180005284  jz      short loc_18000528C
0x180005286  add     rbx, 10h
0x18000528a  jmp     short loc_180005256
0x18000528c  movzx   eax, byte ptr [rbx+8]
0x180005290  jmp     short loc_1800052E0
0x180005292  mov     r9d, 6
0x180005298  lea     r8, off_180012B20; "KANA"
0x18000529f  mov     edx, edi; cchCount2
0x1800052a1  mov     rcx, rsi; lpString2
0x1800052a4  call    VkSearchTable
0x1800052a9  cmp     eax, 0FFFFFFFFh
0x1800052ac  jz      short loc_1800052B9
0x1800052ae  cmp     cs:dword_180018BE4, 0
0x1800052b5  jnz     short loc_1800052E0
0x1800052b7  jmp     short loc_1800052DE
0x1800052b9  mov     r9d, 4
0x1800052bf  lea     r8, off_180012B80; "HANGEUL"
0x1800052c6  mov     edx, edi; cchCount2
0x1800052c8  mov     rcx, rsi; lpString2
0x1800052cb  call    VkSearchTable
0x1800052d0  cmp     eax, 0FFFFFFFFh
0x1800052d3  jz      short loc_1800052E0
0x1800052d5  cmp     cs:dword_180018BE0, 0
0x1800052dc  jnz     short loc_1800052E0
0x1800052de  xor     eax, eax
0x1800052e0  mov     rbx, [rsp+38h+arg_0]
0x1800052e5  mov     rsi, [rsp+38h+arg_8]
0x1800052ea  add     rsp, 30h
0x1800052ee  pop     rdi
0x1800052ef  retn
```
