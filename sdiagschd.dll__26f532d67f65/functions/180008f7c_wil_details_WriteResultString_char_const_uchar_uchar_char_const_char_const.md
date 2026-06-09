# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180008f7c`
- end: `0x180008ff4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b9a8`
- `0x18000bd00`

## callees

- `0x180008f7c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008fbd`
- `msvcrt!memcpy_s` at `0x180008fbd`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rsi
  rsize_t v7; // rsi
  rsize_t v8; // rdx

  if ( a1 == a2 )
    goto LABEL_10;
  if ( !a3 )
    goto LABEL_10;
  if ( !*a3 )
    goto LABEL_10;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = v6 + 1;
  v8 = a2 - a1;
  if ( v8 >= v7 )
  {
    memcpy_s(a1, v8, a3, v7);
    if ( a4 )
      *a4 = a1;
    return &a1[v7];
  }
  else
  {
LABEL_10:
    if ( a4 )
      *a4 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x180008f7c  mov     [rsp+arg_0], rbx
0x180008f81  mov     [rsp+arg_8], rsi
0x180008f86  push    rdi
0x180008f87  sub     rsp, 20h
0x180008f8b  mov     rbx, r9
0x180008f8e  mov     rdi, rcx
0x180008f91  cmp     rcx, rdx
0x180008f94  jz      short loc_180008FD7
0x180008f96  test    r8, r8
0x180008f99  jz      short loc_180008FD7
0x180008f9b  cmp     byte ptr [r8], 0
0x180008f9f  jz      short loc_180008FD7
0x180008fa1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008fa5  inc     rsi
0x180008fa8  cmp     byte ptr [r8+rsi], 0
0x180008fad  jnz     short loc_180008FA5
0x180008faf  inc     rsi
0x180008fb2  sub     rdx, rdi; DestinationSize
0x180008fb5  cmp     rdx, rsi
0x180008fb8  jb      short loc_180008FD7
0x180008fba  mov     r9, rsi; SourceSize
0x180008fbd  call    cs:__imp_memcpy_s
0x180008fc4  nop     dword ptr [rax+rax+00h]
0x180008fc9  test    rbx, rbx
0x180008fcc  jz      short loc_180008FD1
0x180008fce  mov     [rbx], rdi
0x180008fd1  lea     rax, [rsi+rdi]
0x180008fd5  jmp     short loc_180008FE3
0x180008fd7  test    rbx, rbx
0x180008fda  jz      short loc_180008FE0
0x180008fdc  and     qword ptr [r9], 0
0x180008fe0  mov     rax, rdi
0x180008fe3  mov     rbx, [rsp+28h+arg_0]
0x180008fe8  mov     rsi, [rsp+28h+arg_8]
0x180008fed  add     rsp, 20h
0x180008ff1  pop     rdi
0x180008ff2  retn
```
