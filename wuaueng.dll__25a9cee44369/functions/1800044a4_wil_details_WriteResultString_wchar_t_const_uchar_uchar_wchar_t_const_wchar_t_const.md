# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x1800044a4`
- end: `0x180004524`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `128`
- prototype: `char *__fastcall(char *, char *, _WORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000280c`
- `0x180003dd0`

## callees

- `0x180001ab4`
- `0x1800044a4`

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
0x1800044a4  mov     [rsp+arg_0], rbx
0x1800044a9  mov     [rsp+arg_8], rbp
0x1800044ae  mov     [rsp+arg_10], rsi
0x1800044b3  push    rdi
0x1800044b4  sub     rsp, 20h
0x1800044b8  xor     ebp, ebp
0x1800044ba  mov     rbx, r9
0x1800044bd  mov     rdi, rcx
0x1800044c0  cmp     rcx, rdx
0x1800044c3  jz      short loc_180004504
0x1800044c5  test    r8, r8
0x1800044c8  jz      short loc_180004504
0x1800044ca  cmp     [r8], bp
0x1800044ce  jz      short loc_180004504
0x1800044d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800044d4  inc     rax
0x1800044d7  cmp     [r8+rax*2], bp
0x1800044dc  jnz     short loc_1800044D4
0x1800044de  lea     rsi, ds:2[rax*2]
0x1800044e6  sub     rdx, rdi; DestinationSize
0x1800044e9  cmp     rdx, rsi
0x1800044ec  jb      short loc_180004504
0x1800044ee  mov     r9, rsi; SourceSize
0x1800044f1  call    memcpy_s
0x1800044f6  test    rbx, rbx
0x1800044f9  jz      short loc_1800044FE
0x1800044fb  mov     [rbx], rdi
0x1800044fe  lea     rax, [rsi+rdi]
0x180004502  jmp     short loc_18000450F
0x180004504  test    rbx, rbx
0x180004507  jz      short loc_18000450C
0x180004509  mov     [r9], rbp
0x18000450c  mov     rax, rdi
0x18000450f  mov     rbx, [rsp+28h+arg_0]
0x180004514  mov     rbp, [rsp+28h+arg_8]
0x180004519  mov     rsi, [rsp+28h+arg_10]
0x18000451e  add     rsp, 20h
0x180004522  pop     rdi
0x180004523  retn
```
