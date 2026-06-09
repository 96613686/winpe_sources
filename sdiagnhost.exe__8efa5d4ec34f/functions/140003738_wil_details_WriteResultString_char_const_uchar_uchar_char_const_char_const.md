# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140003738`
- end: `0x1400037ad`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006180`
- `0x140006584`

## callees

- `0x140003738`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000377a`
- `msvcrt!memcpy_s` at `0x14000377a`

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
0x140003738  mov     [rsp+arg_0], rbx
0x14000373d  mov     [rsp+arg_8], rsi
0x140003742  push    rdi
0x140003743  sub     rsp, 20h
0x140003747  mov     rbx, r9
0x14000374a  mov     rdi, rcx
0x14000374d  cmp     rcx, rdx
0x140003750  jz      short loc_14000378E
0x140003752  test    r8, r8
0x140003755  jz      short loc_14000378E
0x140003757  cmp     byte ptr [r8], 0
0x14000375b  jz      short loc_14000378E
0x14000375d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003761  inc     rax
0x140003764  cmp     byte ptr [r8+rax], 0
0x140003769  jnz     short loc_140003761
0x14000376b  lea     rsi, [rax+1]
0x14000376f  sub     rdx, rdi; DestinationSize
0x140003772  cmp     rdx, rsi
0x140003775  jb      short loc_14000378E
0x140003777  mov     r9, rsi; SourceSize
0x14000377a  call    cs:__imp_memcpy_s
0x140003780  test    rbx, rbx
0x140003783  jz      short loc_140003788
0x140003785  mov     [rbx], rdi
0x140003788  lea     rax, [rsi+rdi]
0x14000378c  jmp     short loc_14000379D
0x14000378e  test    rbx, rbx
0x140003791  jz      short loc_14000379A
0x140003793  mov     qword ptr [r9], 0
0x14000379a  mov     rax, rdi
0x14000379d  mov     rbx, [rsp+28h+arg_0]
0x1400037a2  mov     rsi, [rsp+28h+arg_8]
0x1400037a7  add     rsp, 20h
0x1400037ab  pop     rdi
0x1400037ac  retn
```
