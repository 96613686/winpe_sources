# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000d198`
- end: `0x18000d208`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fa84`

## callees

- `0x18000d198`
- `0x18000f930`
- `0x180010e4c`

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
0x18000d198  mov     [rsp+arg_0], rbx
0x18000d19d  mov     [rsp+arg_8], rsi
0x18000d1a2  push    rdi
0x18000d1a3  sub     rsp, 20h
0x18000d1a7  mov     rbx, r9
0x18000d1aa  mov     rdi, rcx
0x18000d1ad  cmp     rcx, rdx
0x18000d1b0  jz      short loc_18000D1E9
0x18000d1b2  test    r8, r8
0x18000d1b5  jz      short loc_18000D1E9
0x18000d1b7  cmp     byte ptr [r8], 0
0x18000d1bb  jz      short loc_18000D1E9
0x18000d1bd  mov     rcx, r8; this
0x18000d1c0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000d1c5  sub     rdx, rdi; DestinationSize
0x18000d1c8  mov     rsi, rax
0x18000d1cb  cmp     rdx, rax
0x18000d1ce  jb      short loc_18000D1E9
0x18000d1d0  mov     r9, rax; SourceSize
0x18000d1d3  mov     rcx, rdi; Destination
0x18000d1d6  call    memcpy_s
0x18000d1db  test    rbx, rbx
0x18000d1de  jz      short loc_18000D1E3
0x18000d1e0  mov     [rbx], rdi
0x18000d1e3  lea     rax, [rsi+rdi]
0x18000d1e7  jmp     short loc_18000D1F8
0x18000d1e9  test    rbx, rbx
0x18000d1ec  jz      short loc_18000D1F5
0x18000d1ee  mov     qword ptr [r9], 0
0x18000d1f5  mov     rax, rdi
0x18000d1f8  mov     rbx, [rsp+28h+arg_0]
0x18000d1fd  mov     rsi, [rsp+28h+arg_8]
0x18000d202  add     rsp, 20h
0x18000d206  pop     rdi
0x18000d207  retn
```
