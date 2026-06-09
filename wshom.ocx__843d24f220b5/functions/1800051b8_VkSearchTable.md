# VkSearchTable

- ea: `0x1800051b8`
- end: `0x180005214`
- name: `VkSearchTable`
- size: `92`
- prototype: `__int64 __fastcall(PCNZCH lpString2, int cchCount2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005238`

## callees

- `0x1800051b8`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x1800051f1`
- `KERNEL32!CompareStringA` at `0x1800051f1`

## pseudocode

```c
__int64 __fastcall VkSearchTable(PCNZCH lpString2, int cchCount2, unsigned __int64 a3, unsigned int a4)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v6; // rdi

  v4 = a3;
  v6 = a3 + 16LL * a4;
  while ( 1 )
  {
    if ( v4 >= v6 )
      return 0xFFFFFFFFLL;
    if ( CompareStringA(0x409u, 3u, *(PCNZCH *)v4, -1, lpString2, cchCount2) == 2 )
      break;
    v4 += 16LL;
  }
  return *(unsigned __int8 *)(v4 + 8);
}

```

## disassembly

```asm
0x1800051b8  push    rbx
0x1800051ba  push    rbp
0x1800051bb  push    rsi
0x1800051bc  push    rdi
0x1800051bd  sub     rsp, 38h
0x1800051c1  mov     edi, r9d
0x1800051c4  mov     rbx, r8
0x1800051c7  shl     rdi, 4
0x1800051cb  mov     esi, edx
0x1800051cd  add     rdi, r8
0x1800051d0  mov     rbp, rcx
0x1800051d3  cmp     rbx, rdi
0x1800051d6  jnb     short loc_180005202
0x1800051d8  mov     r8, [rbx]; lpString1
0x1800051db  or      r9d, 0FFFFFFFFh; cchCount1
0x1800051df  mov     [rsp+58h+cchCount2], esi; cchCount2
0x1800051e3  mov     ecx, 409h; Locale
0x1800051e8  mov     [rsp+58h+lpString2], rbp; lpString2
0x1800051ed  lea     edx, [r9+4]; dwCmpFlags
0x1800051f1  call    cs:__imp_CompareStringA
0x1800051f7  cmp     eax, 2
0x1800051fa  jz      short loc_18000520E
0x1800051fc  add     rbx, 10h
0x180005200  jmp     short loc_1800051D3
0x180005202  or      eax, 0FFFFFFFFh
0x180005205  add     rsp, 38h
0x180005209  pop     rdi
0x18000520a  pop     rsi
0x18000520b  pop     rbp
0x18000520c  pop     rbx
0x18000520d  retn
0x18000520e  movzx   eax, byte ptr [rbx+8]
0x180005212  jmp     short loc_180005205
```
