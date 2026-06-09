# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180008d7c`
- end: `0x180008df1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180010774`
- `0x180010b78`

## callees

- `0x180008d7c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008dbe`
- `msvcrt!memcpy_s` at `0x180008dbe`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rsi
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
  if ( v8 >= v6 + 1 )
  {
    memcpy_s(a1, v8, a3, v6 + 1);
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
0x180008d7c  mov     [rsp+arg_0], rbx
0x180008d81  mov     [rsp+arg_8], rsi
0x180008d86  push    rdi
0x180008d87  sub     rsp, 20h
0x180008d8b  mov     rbx, r9
0x180008d8e  mov     rdi, rcx
0x180008d91  cmp     rcx, rdx
0x180008d94  jz      short loc_180008DD2
0x180008d96  test    r8, r8
0x180008d99  jz      short loc_180008DD2
0x180008d9b  cmp     byte ptr [r8], 0
0x180008d9f  jz      short loc_180008DD2
0x180008da1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008da5  inc     rax
0x180008da8  cmp     byte ptr [r8+rax], 0
0x180008dad  jnz     short loc_180008DA5
0x180008daf  lea     rsi, [rax+1]
0x180008db3  sub     rdx, rdi; DestinationSize
0x180008db6  cmp     rdx, rsi
0x180008db9  jb      short loc_180008DD2
0x180008dbb  mov     r9, rsi; SourceSize
0x180008dbe  call    cs:__imp_memcpy_s
0x180008dc4  test    rbx, rbx
0x180008dc7  jz      short loc_180008DCC
0x180008dc9  mov     [rbx], rdi
0x180008dcc  lea     rax, [rsi+rdi]
0x180008dd0  jmp     short loc_180008DE1
0x180008dd2  test    rbx, rbx
0x180008dd5  jz      short loc_180008DDE
0x180008dd7  mov     qword ptr [r9], 0
0x180008dde  mov     rax, rdi
0x180008de1  mov     rbx, [rsp+28h+arg_0]
0x180008de6  mov     rsi, [rsp+28h+arg_8]
0x180008deb  add     rsp, 20h
0x180008def  pop     rdi
0x180008df0  retn
```
