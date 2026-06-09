# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004d50`
- end: `0x180004dc5`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006980`
- `0x18000b024`

## callees

- `0x180004d50`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004d92`
- `msvcrt!memcpy_s` at `0x180004d92`

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
0x180004d50  mov     [rsp+arg_0], rbx
0x180004d55  mov     [rsp+arg_8], rsi
0x180004d5a  push    rdi
0x180004d5b  sub     rsp, 20h
0x180004d5f  mov     rbx, r9
0x180004d62  mov     rdi, rcx
0x180004d65  cmp     rcx, rdx
0x180004d68  jz      short loc_180004DA6
0x180004d6a  test    r8, r8
0x180004d6d  jz      short loc_180004DA6
0x180004d6f  cmp     byte ptr [r8], 0
0x180004d73  jz      short loc_180004DA6
0x180004d75  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d79  inc     rax
0x180004d7c  cmp     byte ptr [r8+rax], 0
0x180004d81  jnz     short loc_180004D79
0x180004d83  lea     rsi, [rax+1]
0x180004d87  sub     rdx, rdi; DestinationSize
0x180004d8a  cmp     rdx, rsi
0x180004d8d  jb      short loc_180004DA6
0x180004d8f  mov     r9, rsi; SourceSize
0x180004d92  call    cs:__imp_memcpy_s
0x180004d98  test    rbx, rbx
0x180004d9b  jz      short loc_180004DA0
0x180004d9d  mov     [rbx], rdi
0x180004da0  lea     rax, [rsi+rdi]
0x180004da4  jmp     short loc_180004DB5
0x180004da6  test    rbx, rbx
0x180004da9  jz      short loc_180004DB2
0x180004dab  mov     qword ptr [r9], 0
0x180004db2  mov     rax, rdi
0x180004db5  mov     rbx, [rsp+28h+arg_0]
0x180004dba  mov     rsi, [rsp+28h+arg_8]
0x180004dbf  add     rsp, 20h
0x180004dc3  pop     rdi
0x180004dc4  retn
```
