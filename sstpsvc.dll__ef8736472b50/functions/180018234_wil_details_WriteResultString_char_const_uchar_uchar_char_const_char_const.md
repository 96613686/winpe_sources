# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180018234`
- end: `0x1800182ac`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b928`

## callees

- `0x180018234`
- `0x18001b7a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180018272`
- `msvcrt!memcpy_s` at `0x180018272`

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
0x180018234  mov     [rsp+arg_0], rbx
0x180018239  mov     [rsp+arg_8], rsi
0x18001823e  push    rdi
0x18001823f  sub     rsp, 20h
0x180018243  mov     rbx, r9
0x180018246  mov     rdi, rcx
0x180018249  cmp     rcx, rdx
0x18001824c  jz      short loc_18001828C
0x18001824e  test    r8, r8
0x180018251  jz      short loc_18001828C
0x180018253  cmp     byte ptr [r8], 0
0x180018257  jz      short loc_18001828C
0x180018259  mov     rcx, r8; this
0x18001825c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180018261  sub     rdx, rdi; DestinationSize
0x180018264  mov     rsi, rax
0x180018267  cmp     rdx, rax
0x18001826a  jb      short loc_18001828C
0x18001826c  mov     r9, rax; SourceSize
0x18001826f  mov     rcx, rdi; Destination
0x180018272  call    cs:__imp_memcpy_s
0x180018279  nop     dword ptr [rax+rax+00h]
0x18001827e  test    rbx, rbx
0x180018281  jz      short loc_180018286
0x180018283  mov     [rbx], rdi
0x180018286  lea     rax, [rsi+rdi]
0x18001828a  jmp     short loc_18001829B
0x18001828c  test    rbx, rbx
0x18001828f  jz      short loc_180018298
0x180018291  mov     qword ptr [r9], 0
0x180018298  mov     rax, rdi
0x18001829b  mov     rbx, [rsp+28h+arg_0]
0x1800182a0  mov     rsi, [rsp+28h+arg_8]
0x1800182a5  add     rsp, 20h
0x1800182a9  pop     rdi
0x1800182aa  retn
```
