# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x140005244`
- end: `0x1400052c4`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400032e4`
- `0x1400042b0`

## callees

- `0x140002ba0`
- `0x140005244`

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
0x140005244  mov     [rsp+arg_0], rbx
0x140005249  mov     [rsp+arg_8], rbp
0x14000524e  mov     [rsp+arg_10], rsi
0x140005253  push    rdi
0x140005254  sub     rsp, 20h
0x140005258  xor     ebp, ebp
0x14000525a  mov     rbx, r9
0x14000525d  mov     rdi, rcx
0x140005260  cmp     rcx, rdx
0x140005263  jz      short loc_1400052A4
0x140005265  test    r8, r8
0x140005268  jz      short loc_1400052A4
0x14000526a  cmp     [r8], bp
0x14000526e  jz      short loc_1400052A4
0x140005270  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005274  inc     rax
0x140005277  cmp     [r8+rax*2], bp
0x14000527c  jnz     short loc_140005274
0x14000527e  lea     rsi, ds:2[rax*2]
0x140005286  sub     rdx, rdi; DestinationSize
0x140005289  cmp     rdx, rsi
0x14000528c  jb      short loc_1400052A4
0x14000528e  mov     r9, rsi; SourceSize
0x140005291  call    memcpy_s
0x140005296  test    rbx, rbx
0x140005299  jz      short loc_14000529E
0x14000529b  mov     [rbx], rdi
0x14000529e  lea     rax, [rsi+rdi]
0x1400052a2  jmp     short loc_1400052AF
0x1400052a4  test    rbx, rbx
0x1400052a7  jz      short loc_1400052AC
0x1400052a9  mov     [r9], rbp
0x1400052ac  mov     rax, rdi
0x1400052af  mov     rbx, [rsp+28h+arg_0]
0x1400052b4  mov     rbp, [rsp+28h+arg_8]
0x1400052b9  mov     rsi, [rsp+28h+arg_10]
0x1400052be  add     rsp, 20h
0x1400052c2  pop     rdi
0x1400052c3  retn
```
