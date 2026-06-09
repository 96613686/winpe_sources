# CheckReadBoundsTTFConverter

- ea: `0x18000bc34`
- end: `0x18000bc75`
- name: `CheckReadBoundsTTFConverter`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b728`

## callees

- `0x18000bc34`

## import_xrefs

- `msvcrt!longjmp` at `0x18000bc55`
- `msvcrt!longjmp` at `0x18000bc69`
- `msvcrt!longjmp` at `0x18000bc55`
- `msvcrt!longjmp` at `0x18000bc69`

## pseudocode

```c
unsigned __int64 __fastcall CheckReadBoundsTTFConverter(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 result; // rax

  result = a2 + 1;
  if ( a2 + 1 > a1[3] )
    longjmp((_JBTYPE *)(a1[12] + 48LL), 3362);
  if ( a2 < a1[2] )
    longjmp((_JBTYPE *)(a1[12] + 48LL), 3362);
  return result;
}

```

## disassembly

```asm
0x18000bc34  sub     rsp, 28h
0x18000bc38  lea     rax, [rdx+1]
0x18000bc3c  cmp     rax, [rcx+18h]
0x18000bc40  ja      short loc_18000BC5C
0x18000bc42  cmp     rdx, [rcx+10h]
0x18000bc46  jnb     short loc_18000BC70
0x18000bc48  mov     rcx, [rcx+60h]
0x18000bc4c  mov     edx, 0D22h; Value
0x18000bc51  add     rcx, 30h ; '0'; Buf
0x18000bc55  call    cs:__imp_longjmp
0x18000bc5c  mov     rcx, [rcx+60h]
0x18000bc60  mov     edx, 0D22h; Value
0x18000bc65  add     rcx, 30h ; '0'; Buf
0x18000bc69  call    cs:__imp_longjmp
0x18000bc70  add     rsp, 28h
0x18000bc74  retn
```
