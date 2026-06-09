# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18001de04`
- end: `0x18001de75`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f3b4`

## callees

- `0x18001de04`
- `0x18001f324`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001de42`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001de42`

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
0x18001de04  mov     [rsp+arg_0], rbx
0x18001de09  mov     [rsp+arg_8], rsi
0x18001de0e  push    rdi
0x18001de0f  sub     rsp, 20h
0x18001de13  mov     rbx, r9
0x18001de16  mov     rdi, rcx
0x18001de19  cmp     rcx, rdx
0x18001de1c  jz      short loc_18001DE56
0x18001de1e  test    r8, r8
0x18001de21  jz      short loc_18001DE56
0x18001de23  cmp     byte ptr [r8], 0
0x18001de27  jz      short loc_18001DE56
0x18001de29  mov     rcx, r8; this
0x18001de2c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001de31  sub     rdx, rdi; DestinationSize
0x18001de34  mov     rsi, rax
0x18001de37  cmp     rdx, rax
0x18001de3a  jb      short loc_18001DE56
0x18001de3c  mov     r9, rax; SourceSize
0x18001de3f  mov     rcx, rdi; Destination
0x18001de42  call    cs:__imp_memcpy_s
0x18001de48  test    rbx, rbx
0x18001de4b  jz      short loc_18001DE50
0x18001de4d  mov     [rbx], rdi
0x18001de50  lea     rax, [rsi+rdi]
0x18001de54  jmp     short loc_18001DE65
0x18001de56  test    rbx, rbx
0x18001de59  jz      short loc_18001DE62
0x18001de5b  mov     qword ptr [r9], 0
0x18001de62  mov     rax, rdi
0x18001de65  mov     rbx, [rsp+28h+arg_0]
0x18001de6a  mov     rsi, [rsp+28h+arg_8]
0x18001de6f  add     rsp, 20h
0x18001de73  pop     rdi
0x18001de74  retn
```
