# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003b6c`
- end: `0x180003bdc`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ea0`
- `0x180005fdc`

## callees

- `0x180003b6c`
- `0x180005d38`
- `0x1800074c8`

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
0x180003b6c  mov     [rsp+arg_0], rbx
0x180003b71  mov     [rsp+arg_8], rsi
0x180003b76  push    rdi
0x180003b77  sub     rsp, 20h
0x180003b7b  mov     rbx, r9
0x180003b7e  mov     rdi, rcx
0x180003b81  cmp     rcx, rdx
0x180003b84  jz      short loc_180003BBD
0x180003b86  test    r8, r8
0x180003b89  jz      short loc_180003BBD
0x180003b8b  cmp     byte ptr [r8], 0
0x180003b8f  jz      short loc_180003BBD
0x180003b91  mov     rcx, r8; this
0x180003b94  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180003b99  sub     rdx, rdi; DestinationSize
0x180003b9c  mov     rsi, rax
0x180003b9f  cmp     rdx, rax
0x180003ba2  jb      short loc_180003BBD
0x180003ba4  mov     r9, rax; SourceSize
0x180003ba7  mov     rcx, rdi; Destination
0x180003baa  call    memcpy_s
0x180003baf  test    rbx, rbx
0x180003bb2  jz      short loc_180003BB7
0x180003bb4  mov     [rbx], rdi
0x180003bb7  lea     rax, [rsi+rdi]
0x180003bbb  jmp     short loc_180003BCC
0x180003bbd  test    rbx, rbx
0x180003bc0  jz      short loc_180003BC9
0x180003bc2  mov     qword ptr [r9], 0
0x180003bc9  mov     rax, rdi
0x180003bcc  mov     rbx, [rsp+28h+arg_0]
0x180003bd1  mov     rsi, [rsp+28h+arg_8]
0x180003bd6  add     rsp, 20h
0x180003bda  pop     rdi
0x180003bdb  retn
```
