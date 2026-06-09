# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180014d00`
- end: `0x180014d70`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800244ac`

## callees

- `0x180014d00`
- `0x1800243e4`
- `0x180027394`

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
0x180014d00  mov     [rsp+arg_0], rbx
0x180014d05  mov     [rsp+arg_8], rsi
0x180014d0a  push    rdi
0x180014d0b  sub     rsp, 20h
0x180014d0f  mov     rbx, r9
0x180014d12  mov     rdi, rcx
0x180014d15  cmp     rcx, rdx
0x180014d18  jz      short loc_180014D51
0x180014d1a  test    r8, r8
0x180014d1d  jz      short loc_180014D51
0x180014d1f  cmp     byte ptr [r8], 0
0x180014d23  jz      short loc_180014D51
0x180014d25  mov     rcx, r8; this
0x180014d28  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180014d2d  sub     rdx, rdi; DestinationSize
0x180014d30  mov     rsi, rax
0x180014d33  cmp     rdx, rax
0x180014d36  jb      short loc_180014D51
0x180014d38  mov     r9, rax; SourceSize
0x180014d3b  mov     rcx, rdi; Destination
0x180014d3e  call    memcpy_s
0x180014d43  test    rbx, rbx
0x180014d46  jz      short loc_180014D4B
0x180014d48  mov     [rbx], rdi
0x180014d4b  lea     rax, [rsi+rdi]
0x180014d4f  jmp     short loc_180014D60
0x180014d51  test    rbx, rbx
0x180014d54  jz      short loc_180014D5D
0x180014d56  mov     qword ptr [r9], 0
0x180014d5d  mov     rax, rdi
0x180014d60  mov     rbx, [rsp+28h+arg_0]
0x180014d65  mov     rsi, [rsp+28h+arg_8]
0x180014d6a  add     rsp, 20h
0x180014d6e  pop     rdi
0x180014d6f  retn
```
