# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800222e0`
- end: `0x18002235c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800273a4`
- `0x1800277c4`

## callees

- `0x1800222e0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180022322`
- `msvcrt!memcpy_s` at `0x180022322`

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
0x1800222e0  mov     [rsp+arg_0], rbx
0x1800222e5  mov     [rsp+arg_8], rsi
0x1800222ea  push    rdi
0x1800222eb  sub     rsp, 20h
0x1800222ef  mov     rbx, r9
0x1800222f2  mov     rdi, rcx
0x1800222f5  cmp     rcx, rdx
0x1800222f8  jz      short loc_18002233C
0x1800222fa  test    r8, r8
0x1800222fd  jz      short loc_18002233C
0x1800222ff  cmp     byte ptr [r8], 0
0x180022303  jz      short loc_18002233C
0x180022305  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022309  inc     rax
0x18002230c  cmp     byte ptr [r8+rax], 0
0x180022311  jnz     short loc_180022309
0x180022313  lea     rsi, [rax+1]
0x180022317  sub     rdx, rdi; DestinationSize
0x18002231a  cmp     rdx, rsi
0x18002231d  jb      short loc_18002233C
0x18002231f  mov     r9, rsi; SourceSize
0x180022322  call    cs:__imp_memcpy_s
0x180022329  nop     dword ptr [rax+rax+00h]
0x18002232e  test    rbx, rbx
0x180022331  jz      short loc_180022336
0x180022333  mov     [rbx], rdi
0x180022336  lea     rax, [rsi+rdi]
0x18002233a  jmp     short loc_18002234B
0x18002233c  test    rbx, rbx
0x18002233f  jz      short loc_180022348
0x180022341  mov     qword ptr [r9], 0
0x180022348  mov     rax, rdi
0x18002234b  mov     rbx, [rsp+28h+arg_0]
0x180022350  mov     rsi, [rsp+28h+arg_8]
0x180022355  add     rsp, 20h
0x180022359  pop     rdi
0x18002235a  retn
```
