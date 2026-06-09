# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180008ffc`
- end: `0x180009084`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b9a8`
- `0x18000bd00`

## callees

- `0x180008ffc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009049`
- `msvcrt!memcpy_s` at `0x180009049`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(char *a1, char *a2, _WORD *a3, _QWORD *a4)
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
0x180008ffc  mov     [rsp+arg_0], rbx
0x180009001  mov     [rsp+arg_8], rbp
0x180009006  mov     [rsp+arg_10], rsi
0x18000900b  push    rdi
0x18000900c  sub     rsp, 20h
0x180009010  xor     ebp, ebp
0x180009012  mov     rbx, r9
0x180009015  mov     rdi, rcx
0x180009018  cmp     rcx, rdx
0x18000901b  jz      short loc_180009063
0x18000901d  test    r8, r8
0x180009020  jz      short loc_180009063
0x180009022  cmp     [r8], bp
0x180009026  jz      short loc_180009063
0x180009028  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000902c  inc     rax
0x18000902f  cmp     [r8+rax*2], bp
0x180009034  jnz     short loc_18000902C
0x180009036  lea     rsi, ds:2[rax*2]
0x18000903e  sub     rdx, rdi; DestinationSize
0x180009041  cmp     rdx, rsi
0x180009044  jb      short loc_180009063
0x180009046  mov     r9, rsi; SourceSize
0x180009049  call    cs:__imp_memcpy_s
0x180009050  nop     dword ptr [rax+rax+00h]
0x180009055  test    rbx, rbx
0x180009058  jz      short loc_18000905D
0x18000905a  mov     [rbx], rdi
0x18000905d  lea     rax, [rsi+rdi]
0x180009061  jmp     short loc_18000906E
0x180009063  test    rbx, rbx
0x180009066  jz      short loc_18000906B
0x180009068  mov     [r9], rbp
0x18000906b  mov     rax, rdi
0x18000906e  mov     rbx, [rsp+28h+arg_0]
0x180009073  mov     rbp, [rsp+28h+arg_8]
0x180009078  mov     rsi, [rsp+28h+arg_10]
0x18000907d  add     rsp, 20h
0x180009081  pop     rdi
0x180009082  retn
```
