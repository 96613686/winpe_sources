# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180006c18`
- end: `0x180006c98`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `128`
- prototype: `char *__fastcall(char *, char *, _WORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fdc`
- `0x1800062c8`

## callees

- `0x180004348`
- `0x180006c18`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<wchar_t const *>(char *a1, char *a2, _WORD *a3, _QWORD *a4)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  rsize_t v8; // rdx

  if ( a1 == a2 )
    goto LABEL_10;
  if ( !a3 )
    goto LABEL_10;
  if ( !*a3 )
    goto LABEL_10;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = 2 * v6 + 2;
  v8 = a2 - a1;
  if ( v8 >= v7 )
  {
    memcpy_s(a1, v8, a3, 2 * v6 + 2);
    if ( a4 )
      *a4 = a1;
    return &a1[v7];
  }
  else
  {
LABEL_10:
    if ( a4 )
      *a4 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x180006c18  mov     [rsp+arg_0], rbx
0x180006c1d  mov     [rsp+arg_8], rbp
0x180006c22  mov     [rsp+arg_10], rsi
0x180006c27  push    rdi
0x180006c28  sub     rsp, 20h
0x180006c2c  xor     ebp, ebp
0x180006c2e  mov     rbx, r9
0x180006c31  mov     rdi, rcx
0x180006c34  cmp     rcx, rdx
0x180006c37  jz      short loc_180006C78
0x180006c39  test    r8, r8
0x180006c3c  jz      short loc_180006C78
0x180006c3e  cmp     [r8], bp
0x180006c42  jz      short loc_180006C78
0x180006c44  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006c48  inc     rax
0x180006c4b  cmp     [r8+rax*2], bp
0x180006c50  jnz     short loc_180006C48
0x180006c52  lea     rsi, ds:2[rax*2]
0x180006c5a  sub     rdx, rdi; DestinationSize
0x180006c5d  cmp     rdx, rsi
0x180006c60  jb      short loc_180006C78
0x180006c62  mov     r9, rsi; SourceSize
0x180006c65  call    memcpy_s
0x180006c6a  test    rbx, rbx
0x180006c6d  jz      short loc_180006C72
0x180006c6f  mov     [rbx], rdi
0x180006c72  lea     rax, [rsi+rdi]
0x180006c76  jmp     short loc_180006C83
0x180006c78  test    rbx, rbx
0x180006c7b  jz      short loc_180006C80
0x180006c7d  mov     [r9], rbp
0x180006c80  mov     rax, rdi
0x180006c83  mov     rbx, [rsp+28h+arg_0]
0x180006c88  mov     rbp, [rsp+28h+arg_8]
0x180006c8d  mov     rsi, [rsp+28h+arg_10]
0x180006c92  add     rsp, 20h
0x180006c96  pop     rdi
0x180006c97  retn
```
