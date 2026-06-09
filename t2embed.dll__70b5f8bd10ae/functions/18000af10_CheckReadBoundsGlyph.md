# CheckReadBoundsGlyph

- ea: `0x18000af10`
- end: `0x18000af5c`
- name: `CheckReadBoundsGlyph`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e10`
- `0x18000a550`
- `0x18000a650`

## callees

- `0x18000af10`

## import_xrefs

- `msvcrt!longjmp` at `0x18000af3e`
- `msvcrt!longjmp` at `0x18000af55`
- `msvcrt!longjmp` at `0x18000af3e`
- `msvcrt!longjmp` at `0x18000af55`

## pseudocode

```c
unsigned __int64 __fastcall CheckReadBoundsGlyph(_QWORD *a1, unsigned __int64 a2, int a3)
{
  unsigned __int64 result; // rax

  result = a2 + a3;
  if ( result > a1[16] )
    longjmp((_JBTYPE *)(a1[17] + 48LL), 3362);
  if ( a2 < a1[15] )
    longjmp((_JBTYPE *)(a1[17] + 48LL), 3362);
  return result;
}

```

## disassembly

```asm
0x18000af10  sub     rsp, 28h
0x18000af14  movsxd  rax, r8d
0x18000af17  add     rax, rdx
0x18000af1a  cmp     rax, [rcx+80h]
0x18000af21  ja      short loc_18000AF2E
0x18000af23  cmp     rdx, [rcx+78h]
0x18000af27  jb      short loc_18000AF45
0x18000af29  add     rsp, 28h
0x18000af2d  retn
0x18000af2e  mov     rcx, [rcx+88h]
0x18000af35  mov     edx, 0D22h; Value
0x18000af3a  add     rcx, 30h ; '0'; Buf
0x18000af3e  call    cs:__imp_longjmp
0x18000af45  mov     rcx, [rcx+88h]
0x18000af4c  mov     edx, 0D22h; Value
0x18000af51  add     rcx, 30h ; '0'; Buf
0x18000af55  call    cs:__imp_longjmp
```
