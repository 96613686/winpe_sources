# CheckReadBoundsForTable

- ea: `0x180001f20`
- end: `0x180001f4f`
- name: `CheckReadBoundsForTable`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f60`
- `0x180002bd0`
- `0x18000b540`

## callees

- `0x180001f20`

## import_xrefs

- `msvcrt!longjmp` at `0x180001f48`
- `msvcrt!longjmp` at `0x180001f48`

## pseudocode

```c
unsigned __int64 __fastcall CheckReadBoundsForTable(_QWORD *a1, unsigned __int64 a2, int a3)
{
  unsigned __int64 result; // rax

  result = a2 + a3;
  if ( result > a1[3] || a2 < a1[2] )
    longjmp((_JBTYPE *)(a1[12] + 48LL), 3362);
  return result;
}

```

## disassembly

```asm
0x180001f20  sub     rsp, 28h
0x180001f24  movsxd  rax, r8d
0x180001f27  add     rax, rdx
0x180001f2a  cmp     rax, [rcx+18h]
0x180001f2e  ja      short loc_180001F3B
0x180001f30  cmp     rdx, [rcx+10h]
0x180001f34  jb      short loc_180001F3B
0x180001f36  add     rsp, 28h
0x180001f3a  retn
0x180001f3b  mov     rcx, [rcx+60h]
0x180001f3f  mov     edx, 0D22h; Value
0x180001f44  add     rcx, 30h ; '0'; Buf
0x180001f48  call    cs:__imp_longjmp
```
