# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003370`
- end: `0x1800033e0`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000521c`
- `0x180005358`

## callees

- `0x180003370`
- `0x180005138`
- `0x180005f70`

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
0x180003370  mov     [rsp+arg_0], rbx
0x180003375  mov     [rsp+arg_8], rsi
0x18000337a  push    rdi
0x18000337b  sub     rsp, 20h
0x18000337f  mov     rbx, r9
0x180003382  mov     rdi, rcx
0x180003385  cmp     rcx, rdx
0x180003388  jz      short loc_1800033C1
0x18000338a  test    r8, r8
0x18000338d  jz      short loc_1800033C1
0x18000338f  cmp     byte ptr [r8], 0
0x180003393  jz      short loc_1800033C1
0x180003395  mov     rcx, r8; this
0x180003398  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000339d  sub     rdx, rdi; DestinationSize
0x1800033a0  mov     rsi, rax
0x1800033a3  cmp     rdx, rax
0x1800033a6  jb      short loc_1800033C1
0x1800033a8  mov     r9, rax; SourceSize
0x1800033ab  mov     rcx, rdi; Destination
0x1800033ae  call    memcpy_s
0x1800033b3  test    rbx, rbx
0x1800033b6  jz      short loc_1800033BB
0x1800033b8  mov     [rbx], rdi
0x1800033bb  lea     rax, [rsi+rdi]
0x1800033bf  jmp     short loc_1800033D0
0x1800033c1  test    rbx, rbx
0x1800033c4  jz      short loc_1800033CD
0x1800033c6  mov     qword ptr [r9], 0
0x1800033cd  mov     rax, rdi
0x1800033d0  mov     rbx, [rsp+28h+arg_0]
0x1800033d5  mov     rsi, [rsp+28h+arg_8]
0x1800033da  add     rsp, 20h
0x1800033de  pop     rdi
0x1800033df  retn
```
