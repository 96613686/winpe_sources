# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800049e4`
- end: `0x180004a55`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054bc`
- `0x180016364`

## callees

- `0x1800049e4`
- `0x180005414`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004a22`
- `msvcrt!memcpy_s` at `0x180004a22`

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
0x1800049e4  mov     [rsp+arg_0], rbx
0x1800049e9  mov     [rsp+arg_8], rsi
0x1800049ee  push    rdi
0x1800049ef  sub     rsp, 20h
0x1800049f3  mov     rbx, r9
0x1800049f6  mov     rdi, rcx
0x1800049f9  cmp     rcx, rdx
0x1800049fc  jz      short loc_180004A36
0x1800049fe  test    r8, r8
0x180004a01  jz      short loc_180004A36
0x180004a03  cmp     byte ptr [r8], 0
0x180004a07  jz      short loc_180004A36
0x180004a09  mov     rcx, r8; this
0x180004a0c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004a11  sub     rdx, rdi; DestinationSize
0x180004a14  mov     rsi, rax
0x180004a17  cmp     rdx, rax
0x180004a1a  jb      short loc_180004A36
0x180004a1c  mov     r9, rax; SourceSize
0x180004a1f  mov     rcx, rdi; Destination
0x180004a22  call    cs:__imp_memcpy_s
0x180004a28  test    rbx, rbx
0x180004a2b  jz      short loc_180004A30
0x180004a2d  mov     [rbx], rdi
0x180004a30  lea     rax, [rsi+rdi]
0x180004a34  jmp     short loc_180004A45
0x180004a36  test    rbx, rbx
0x180004a39  jz      short loc_180004A42
0x180004a3b  mov     qword ptr [r9], 0
0x180004a42  mov     rax, rdi
0x180004a45  mov     rbx, [rsp+28h+arg_0]
0x180004a4a  mov     rsi, [rsp+28h+arg_8]
0x180004a4f  add     rsp, 20h
0x180004a53  pop     rdi
0x180004a54  retn
```
