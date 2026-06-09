# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800085a8`
- end: `0x180008619`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009bd4`

## callees

- `0x1800085a8`
- `0x180009ab8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800085e6`
- `msvcrt!memcpy_s` at `0x1800085e6`

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
0x1800085a8  mov     [rsp+arg_0], rbx
0x1800085ad  mov     [rsp+arg_8], rsi
0x1800085b2  push    rdi
0x1800085b3  sub     rsp, 20h
0x1800085b7  mov     rbx, r9
0x1800085ba  mov     rdi, rcx
0x1800085bd  cmp     rcx, rdx
0x1800085c0  jz      short loc_1800085FA
0x1800085c2  test    r8, r8
0x1800085c5  jz      short loc_1800085FA
0x1800085c7  cmp     byte ptr [r8], 0
0x1800085cb  jz      short loc_1800085FA
0x1800085cd  mov     rcx, r8; this
0x1800085d0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800085d5  sub     rdx, rdi; DestinationSize
0x1800085d8  mov     rsi, rax
0x1800085db  cmp     rdx, rax
0x1800085de  jb      short loc_1800085FA
0x1800085e0  mov     r9, rax; SourceSize
0x1800085e3  mov     rcx, rdi; Destination
0x1800085e6  call    cs:__imp_memcpy_s
0x1800085ec  test    rbx, rbx
0x1800085ef  jz      short loc_1800085F4
0x1800085f1  mov     [rbx], rdi
0x1800085f4  lea     rax, [rsi+rdi]
0x1800085f8  jmp     short loc_180008609
0x1800085fa  test    rbx, rbx
0x1800085fd  jz      short loc_180008606
0x1800085ff  mov     qword ptr [r9], 0
0x180008606  mov     rax, rdi
0x180008609  mov     rbx, [rsp+28h+arg_0]
0x18000860e  mov     rsi, [rsp+28h+arg_8]
0x180008613  add     rsp, 20h
0x180008617  pop     rdi
0x180008618  retn
```
