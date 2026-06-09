# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180009890`
- end: `0x180009910`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `128`
- prototype: `char *__fastcall(char *, char *, _WORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000811c`
- `0x180009220`

## callees

- `0x180007c08`
- `0x180009890`

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
0x180009890  mov     [rsp+arg_0], rbx
0x180009895  mov     [rsp+arg_8], rbp
0x18000989a  mov     [rsp+arg_10], rsi
0x18000989f  push    rdi
0x1800098a0  sub     rsp, 20h
0x1800098a4  xor     ebp, ebp
0x1800098a6  mov     rbx, r9
0x1800098a9  mov     rdi, rcx
0x1800098ac  cmp     rcx, rdx
0x1800098af  jz      short loc_1800098F0
0x1800098b1  test    r8, r8
0x1800098b4  jz      short loc_1800098F0
0x1800098b6  cmp     [r8], bp
0x1800098ba  jz      short loc_1800098F0
0x1800098bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800098c0  inc     rax
0x1800098c3  cmp     [r8+rax*2], bp
0x1800098c8  jnz     short loc_1800098C0
0x1800098ca  lea     rsi, ds:2[rax*2]
0x1800098d2  sub     rdx, rdi; DestinationSize
0x1800098d5  cmp     rdx, rsi
0x1800098d8  jb      short loc_1800098F0
0x1800098da  mov     r9, rsi; SourceSize
0x1800098dd  call    memcpy_s
0x1800098e2  test    rbx, rbx
0x1800098e5  jz      short loc_1800098EA
0x1800098e7  mov     [rbx], rdi
0x1800098ea  lea     rax, [rsi+rdi]
0x1800098ee  jmp     short loc_1800098FB
0x1800098f0  test    rbx, rbx
0x1800098f3  jz      short loc_1800098F8
0x1800098f5  mov     [r9], rbp
0x1800098f8  mov     rax, rdi
0x1800098fb  mov     rbx, [rsp+28h+arg_0]
0x180009900  mov     rbp, [rsp+28h+arg_8]
0x180009905  mov     rsi, [rsp+28h+arg_10]
0x18000990a  add     rsp, 20h
0x18000990e  pop     rdi
0x18000990f  retn
```
