# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003c24`
- end: `0x180003c95`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008954`
- `0x180008b80`

## callees

- `0x180003c24`
- `0x180008770`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003c62`
- `msvcrt!memcpy_s` at `0x180003c62`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x180003c24  mov     [rsp+arg_0], rbx
0x180003c29  mov     [rsp+arg_8], rsi
0x180003c2e  push    rdi
0x180003c2f  sub     rsp, 20h
0x180003c33  mov     rbx, r9
0x180003c36  mov     rdi, rcx
0x180003c39  cmp     rcx, rdx
0x180003c3c  jz      short loc_180003C76
0x180003c3e  test    r8, r8
0x180003c41  jz      short loc_180003C76
0x180003c43  cmp     byte ptr [r8], 0
0x180003c47  jz      short loc_180003C76
0x180003c49  mov     rcx, r8; this
0x180003c4c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180003c51  sub     rdx, rdi; DestinationSize
0x180003c54  mov     rsi, rax
0x180003c57  cmp     rdx, rax
0x180003c5a  jb      short loc_180003C76
0x180003c5c  mov     r9, rax; SourceSize
0x180003c5f  mov     rcx, rdi; Destination
0x180003c62  call    cs:__imp_memcpy_s
0x180003c68  test    rbx, rbx
0x180003c6b  jz      short loc_180003C70
0x180003c6d  mov     [rbx], rdi
0x180003c70  lea     rax, [rsi+rdi]
0x180003c74  jmp     short loc_180003C85
0x180003c76  test    rbx, rbx
0x180003c79  jz      short loc_180003C82
0x180003c7b  mov     qword ptr [r9], 0
0x180003c82  mov     rax, rdi
0x180003c85  mov     rbx, [rsp+28h+arg_0]
0x180003c8a  mov     rsi, [rsp+28h+arg_8]
0x180003c8f  add     rsp, 20h
0x180003c93  pop     rdi
0x180003c94  retn
```
