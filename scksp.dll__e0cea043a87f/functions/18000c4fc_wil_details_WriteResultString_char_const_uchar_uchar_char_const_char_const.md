# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000c4fc`
- end: `0x18000c56d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d30`
- `0x180010f5c`

## callees

- `0x18000c4fc`
- `0x180010ba8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c53a`
- `msvcrt!memcpy_s` at `0x18000c53a`

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
0x18000c4fc  mov     [rsp+arg_0], rbx
0x18000c501  mov     [rsp+arg_8], rsi
0x18000c506  push    rdi
0x18000c507  sub     rsp, 20h
0x18000c50b  mov     rbx, r9
0x18000c50e  mov     rdi, rcx
0x18000c511  cmp     rcx, rdx
0x18000c514  jz      short loc_18000C54E
0x18000c516  test    r8, r8
0x18000c519  jz      short loc_18000C54E
0x18000c51b  cmp     byte ptr [r8], 0
0x18000c51f  jz      short loc_18000C54E
0x18000c521  mov     rcx, r8; this
0x18000c524  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c529  sub     rdx, rdi; DestinationSize
0x18000c52c  mov     rsi, rax
0x18000c52f  cmp     rdx, rax
0x18000c532  jb      short loc_18000C54E
0x18000c534  mov     r9, rax; SourceSize
0x18000c537  mov     rcx, rdi; Destination
0x18000c53a  call    cs:__imp_memcpy_s
0x18000c540  test    rbx, rbx
0x18000c543  jz      short loc_18000C548
0x18000c545  mov     [rbx], rdi
0x18000c548  lea     rax, [rsi+rdi]
0x18000c54c  jmp     short loc_18000C55D
0x18000c54e  test    rbx, rbx
0x18000c551  jz      short loc_18000C55A
0x18000c553  mov     qword ptr [r9], 0
0x18000c55a  mov     rax, rdi
0x18000c55d  mov     rbx, [rsp+28h+arg_0]
0x18000c562  mov     rsi, [rsp+28h+arg_8]
0x18000c567  add     rsp, 20h
0x18000c56b  pop     rdi
0x18000c56c  retn
```
