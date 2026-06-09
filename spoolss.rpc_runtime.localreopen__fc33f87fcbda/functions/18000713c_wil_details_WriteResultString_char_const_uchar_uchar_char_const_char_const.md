# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000713c`
- end: `0x1800071ad`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b1c4`
- `0x18000b310`

## callees

- `0x18000713c`
- `0x18000ab38`
- `0x18001028c`

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
0x18000713c  mov     [rsp+arg_0], rbx
0x180007141  mov     [rsp+arg_8], rsi
0x180007146  push    rdi
0x180007147  sub     rsp, 20h
0x18000714b  mov     rbx, r9
0x18000714e  mov     rdi, rcx
0x180007151  cmp     rcx, rdx
0x180007154  jz      short loc_18000718D
0x180007156  test    r8, r8
0x180007159  jz      short loc_18000718D
0x18000715b  cmp     byte ptr [r8], 0
0x18000715f  jz      short loc_18000718D
0x180007161  mov     rcx, r8; this
0x180007164  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007169  sub     rdx, rdi; DestinationSize
0x18000716c  mov     rsi, rax
0x18000716f  cmp     rdx, rax
0x180007172  jb      short loc_18000718D
0x180007174  mov     r9, rax; SourceSize
0x180007177  mov     rcx, rdi; Destination
0x18000717a  call    memcpy_s
0x18000717f  test    rbx, rbx
0x180007182  jz      short loc_180007187
0x180007184  mov     [rbx], rdi
0x180007187  lea     rax, [rsi+rdi]
0x18000718b  jmp     short loc_18000719C
0x18000718d  test    rbx, rbx
0x180007190  jz      short loc_180007199
0x180007192  mov     qword ptr [r9], 0
0x180007199  mov     rax, rdi
0x18000719c  mov     rbx, [rsp+28h+arg_0]
0x1800071a1  mov     rsi, [rsp+28h+arg_8]
0x1800071a6  add     rsp, 20h
0x1800071aa  pop     rdi
0x1800071ab  retn
```
