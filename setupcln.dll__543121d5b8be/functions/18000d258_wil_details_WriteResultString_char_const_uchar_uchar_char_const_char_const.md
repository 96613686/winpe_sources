# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000d258`
- end: `0x18000d2c9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d80`
- `0x180010fac`

## callees

- `0x18000d258`
- `0x180010bf8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d296`
- `msvcrt!memcpy_s` at `0x18000d296`

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
0x18000d258  mov     [rsp+arg_0], rbx
0x18000d25d  mov     [rsp+arg_8], rsi
0x18000d262  push    rdi
0x18000d263  sub     rsp, 20h
0x18000d267  mov     rbx, r9
0x18000d26a  mov     rdi, rcx
0x18000d26d  cmp     rcx, rdx
0x18000d270  jz      short loc_18000D2AA
0x18000d272  test    r8, r8
0x18000d275  jz      short loc_18000D2AA
0x18000d277  cmp     byte ptr [r8], 0
0x18000d27b  jz      short loc_18000D2AA
0x18000d27d  mov     rcx, r8; this
0x18000d280  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000d285  sub     rdx, rdi; DestinationSize
0x18000d288  mov     rsi, rax
0x18000d28b  cmp     rdx, rax
0x18000d28e  jb      short loc_18000D2AA
0x18000d290  mov     r9, rax; SourceSize
0x18000d293  mov     rcx, rdi; Destination
0x18000d296  call    cs:__imp_memcpy_s
0x18000d29c  test    rbx, rbx
0x18000d29f  jz      short loc_18000D2A4
0x18000d2a1  mov     [rbx], rdi
0x18000d2a4  lea     rax, [rsi+rdi]
0x18000d2a8  jmp     short loc_18000D2B9
0x18000d2aa  test    rbx, rbx
0x18000d2ad  jz      short loc_18000D2B6
0x18000d2af  mov     qword ptr [r9], 0
0x18000d2b6  mov     rax, rdi
0x18000d2b9  mov     rbx, [rsp+28h+arg_0]
0x18000d2be  mov     rsi, [rsp+28h+arg_8]
0x18000d2c3  add     rsp, 20h
0x18000d2c7  pop     rdi
0x18000d2c8  retn
```
