# AllocAndCopyString(ushort const *,ushort * *)

- ea: `0x1800032a8`
- end: `0x18000332c`
- name: `?AllocAndCopyString@@YAJPEBGPEAPEAG@Z`
- size: `132`
- prototype: `__int64 __fastcall(wchar_t *Source, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004700`
- `0x180004750`
- `0x180004ad4`

## callees

- `0x180001f68`
- `0x1800032a8`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000330f`
- `msvcrt!wcscpy_s` at `0x18000330f`

## pseudocode

```c
__int64 __fastcall AllocAndCopyString(wchar_t *Source, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  unsigned __int64 v5; // rax
  rsize_t v6; // r14
  wchar_t *v7; // rax
  unsigned __int16 *v8; // rbp

  v2 = 0;
  if ( !Source )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  if ( v5 >= 0xFFFFFFFF )
    return 2147942487LL;
  v6 = v5 + 1;
  v7 = (wchar_t *)operator new(saturated_mul(v5 + 1, 2u));
  v8 = v7;
  if ( v7 )
  {
    wcscpy_s(v7, v6, Source);
    *a2 = v8;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v2;
}

```

## disassembly

```asm
0x1800032a8  push    rbx
0x1800032aa  push    rbp
0x1800032ab  push    rsi
0x1800032ac  push    rdi
0x1800032ad  push    r14
0x1800032af  sub     rsp, 20h
0x1800032b3  xor     ebx, ebx
0x1800032b5  mov     rsi, rdx
0x1800032b8  mov     rdi, rcx
0x1800032bb  test    rcx, rcx
0x1800032be  jz      short loc_18000331C
0x1800032c0  test    rdx, rdx
0x1800032c3  jz      short loc_18000331C
0x1800032c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800032c9  mov     rax, r8
0x1800032cc  inc     rax
0x1800032cf  cmp     [rcx+rax*2], bx
0x1800032d3  jnz     short loc_1800032CC
0x1800032d5  mov     ecx, 0FFFFFFFFh
0x1800032da  cmp     rax, rcx
0x1800032dd  jnb     short loc_18000331C
0x1800032df  lea     r14, [rax+1]
0x1800032e3  mov     eax, 2
0x1800032e8  mul     r14
0x1800032eb  cmovb   rax, r8
0x1800032ef  mov     rcx, rax; Size
0x1800032f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800032f7  mov     rbp, rax
0x1800032fa  test    rax, rax
0x1800032fd  jnz     short loc_180003306
0x1800032ff  mov     ebx, 8007000Eh
0x180003304  jmp     short loc_180003318
0x180003306  mov     r8, rdi; Source
0x180003309  mov     rdx, r14; SizeInWords
0x18000330c  mov     rcx, rbp; Destination
0x18000330f  call    cs:__imp_wcscpy_s
0x180003315  mov     [rsi], rbp
0x180003318  mov     eax, ebx
0x18000331a  jmp     short loc_180003321
0x18000331c  mov     eax, 80070057h
0x180003321  add     rsp, 20h
0x180003325  pop     r14
0x180003327  pop     rdi
0x180003328  pop     rsi
0x180003329  pop     rbp
0x18000332a  pop     rbx
0x18000332b  retn
```
