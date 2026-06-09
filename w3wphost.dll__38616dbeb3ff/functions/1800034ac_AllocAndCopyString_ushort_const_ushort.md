# AllocAndCopyString(ushort const *,ushort * *)

- ea: `0x1800034ac`
- end: `0x180003537`
- name: `?AllocAndCopyString@@YAJPEBGPEAPEAG@Z`
- size: `139`
- prototype: `__int64 __fastcall(wchar_t *Source, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ad0`
- `0x180004b20`
- `0x180004ee4`

## callees

- `0x180002090`
- `0x1800034ac`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003513`
- `msvcrt!wcscpy_s` at `0x180003513`

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
0x1800034ac  push    rbx
0x1800034ae  push    rbp
0x1800034af  push    rsi
0x1800034b0  push    rdi
0x1800034b1  push    r14
0x1800034b3  sub     rsp, 20h
0x1800034b7  xor     ebx, ebx
0x1800034b9  mov     rsi, rdx
0x1800034bc  mov     rdi, rcx
0x1800034bf  test    rcx, rcx
0x1800034c2  jz      short loc_180003526
0x1800034c4  test    rdx, rdx
0x1800034c7  jz      short loc_180003526
0x1800034c9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800034cd  mov     rax, r8
0x1800034d0  inc     rax
0x1800034d3  cmp     [rcx+rax*2], bx
0x1800034d7  jnz     short loc_1800034D0
0x1800034d9  mov     ecx, 0FFFFFFFFh
0x1800034de  cmp     rax, rcx
0x1800034e1  jnb     short loc_180003526
0x1800034e3  lea     r14, [rax+1]
0x1800034e7  mov     eax, 2
0x1800034ec  mul     r14
0x1800034ef  cmovb   rax, r8
0x1800034f3  mov     rcx, rax; Size
0x1800034f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800034fb  mov     rbp, rax
0x1800034fe  test    rax, rax
0x180003501  jnz     short loc_18000350A
0x180003503  mov     ebx, 8007000Eh
0x180003508  jmp     short loc_180003522
0x18000350a  mov     r8, rdi; Source
0x18000350d  mov     rdx, r14; SizeInWords
0x180003510  mov     rcx, rbp; Destination
0x180003513  call    cs:__imp_wcscpy_s
0x18000351a  nop     dword ptr [rax+rax+00h]
0x18000351f  mov     [rsi], rbp
0x180003522  mov     eax, ebx
0x180003524  jmp     short loc_18000352B
0x180003526  mov     eax, 80070057h
0x18000352b  add     rsp, 20h
0x18000352f  pop     r14
0x180003531  pop     rdi
0x180003532  pop     rsi
0x180003533  pop     rbp
0x180003534  pop     rbx
0x180003535  retn
```
