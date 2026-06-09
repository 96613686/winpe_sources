# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000ba88`
- end: `0x18000baf9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e01c`

## callees

- `0x18000ba88`
- `0x18000df50`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bac6`
- `msvcrt!memcpy_s` at `0x18000bac6`

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
0x18000ba88  mov     [rsp+arg_0], rbx
0x18000ba8d  mov     [rsp+arg_8], rsi
0x18000ba92  push    rdi
0x18000ba93  sub     rsp, 20h
0x18000ba97  mov     rbx, r9
0x18000ba9a  mov     rdi, rcx
0x18000ba9d  cmp     rcx, rdx
0x18000baa0  jz      short loc_18000BADA
0x18000baa2  test    r8, r8
0x18000baa5  jz      short loc_18000BADA
0x18000baa7  cmp     byte ptr [r8], 0
0x18000baab  jz      short loc_18000BADA
0x18000baad  mov     rcx, r8; this
0x18000bab0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000bab5  sub     rdx, rdi; DestinationSize
0x18000bab8  mov     rsi, rax
0x18000babb  cmp     rdx, rax
0x18000babe  jb      short loc_18000BADA
0x18000bac0  mov     r9, rax; SourceSize
0x18000bac3  mov     rcx, rdi; Destination
0x18000bac6  call    cs:__imp_memcpy_s
0x18000bacc  test    rbx, rbx
0x18000bacf  jz      short loc_18000BAD4
0x18000bad1  mov     [rbx], rdi
0x18000bad4  lea     rax, [rsi+rdi]
0x18000bad8  jmp     short loc_18000BAE9
0x18000bada  test    rbx, rbx
0x18000badd  jz      short loc_18000BAE6
0x18000badf  mov     qword ptr [r9], 0
0x18000bae6  mov     rax, rdi
0x18000bae9  mov     rbx, [rsp+28h+arg_0]
0x18000baee  mov     rsi, [rsp+28h+arg_8]
0x18000baf3  add     rsp, 20h
0x18000baf7  pop     rdi
0x18000baf8  retn
```
