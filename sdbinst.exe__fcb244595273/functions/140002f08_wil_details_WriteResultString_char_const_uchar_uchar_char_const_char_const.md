# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002f08`
- end: `0x140002f7d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400068d0`
- `0x140006cd4`

## callees

- `0x140002f08`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002f4a`
- `msvcrt!memcpy_s` at `0x140002f4a`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rsi
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
  v7 = v6 + 1;
  v8 = a2 - a1;
  if ( v8 >= v6 + 1 )
  {
    memcpy_s(a1, v8, a3, v6 + 1);
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
0x140002f08  mov     [rsp+arg_0], rbx
0x140002f0d  mov     [rsp+arg_8], rsi
0x140002f12  push    rdi
0x140002f13  sub     rsp, 20h
0x140002f17  mov     rbx, r9
0x140002f1a  mov     rdi, rcx
0x140002f1d  cmp     rcx, rdx
0x140002f20  jz      short loc_140002F5E
0x140002f22  test    r8, r8
0x140002f25  jz      short loc_140002F5E
0x140002f27  cmp     byte ptr [r8], 0
0x140002f2b  jz      short loc_140002F5E
0x140002f2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002f31  inc     rax
0x140002f34  cmp     byte ptr [r8+rax], 0
0x140002f39  jnz     short loc_140002F31
0x140002f3b  lea     rsi, [rax+1]
0x140002f3f  sub     rdx, rdi; DestinationSize
0x140002f42  cmp     rdx, rsi
0x140002f45  jb      short loc_140002F5E
0x140002f47  mov     r9, rsi; SourceSize
0x140002f4a  call    cs:__imp_memcpy_s
0x140002f50  test    rbx, rbx
0x140002f53  jz      short loc_140002F58
0x140002f55  mov     [rbx], rdi
0x140002f58  lea     rax, [rsi+rdi]
0x140002f5c  jmp     short loc_140002F6D
0x140002f5e  test    rbx, rbx
0x140002f61  jz      short loc_140002F6A
0x140002f63  mov     qword ptr [r9], 0
0x140002f6a  mov     rax, rdi
0x140002f6d  mov     rbx, [rsp+28h+arg_0]
0x140002f72  mov     rsi, [rsp+28h+arg_8]
0x140002f77  add     rsp, 20h
0x140002f7b  pop     rdi
0x140002f7c  retn
```
