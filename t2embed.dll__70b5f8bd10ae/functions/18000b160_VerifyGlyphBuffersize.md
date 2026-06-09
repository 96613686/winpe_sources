# VerifyGlyphBuffersize

- ea: `0x18000b160`
- end: `0x18000b1a5`
- name: `VerifyGlyphBuffersize`
- size: `69`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059a0`
- `0x18000a650`
- `0x18000b8f0`
- `0x18000bd00`
- `0x18000d5a0`

## callees

- `0x18000b160`

## import_xrefs

- `msvcrt!longjmp` at `0x18000b187`
- `msvcrt!longjmp` at `0x18000b19e`
- `msvcrt!longjmp` at `0x18000b187`
- `msvcrt!longjmp` at `0x18000b19e`

## pseudocode

```c
void __fastcall VerifyGlyphBuffersize(__int64 a1, int a2, int a3)
{
  if ( a3 < 0 )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  if ( a3 * a2 < a3 )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
}

```

## disassembly

```asm
0x18000b160  sub     rsp, 28h
0x18000b164  test    r8d, r8d
0x18000b167  js      short loc_18000B177
0x18000b169  imul    edx, r8d
0x18000b16d  cmp     edx, r8d
0x18000b170  jl      short loc_18000B18E
0x18000b172  add     rsp, 28h
0x18000b176  retn
0x18000b177  mov     rcx, [rcx+88h]
0x18000b17e  mov     edx, 0D22h; Value
0x18000b183  add     rcx, 30h ; '0'; Buf
0x18000b187  call    cs:__imp_longjmp
0x18000b18e  mov     rcx, [rcx+88h]
0x18000b195  mov     edx, 0D22h; Value
0x18000b19a  add     rcx, 30h ; '0'; Buf
0x18000b19e  call    cs:__imp_longjmp
```
