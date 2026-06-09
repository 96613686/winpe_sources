# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003110`
- end: `0x180003180`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000503c`
- `0x180005178`

## callees

- `0x180003110`
- `0x180004f58`
- `0x180005d30`

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
0x180003110  mov     [rsp+arg_0], rbx
0x180003115  mov     [rsp+arg_8], rsi
0x18000311a  push    rdi
0x18000311b  sub     rsp, 20h
0x18000311f  mov     rbx, r9
0x180003122  mov     rdi, rcx
0x180003125  cmp     rcx, rdx
0x180003128  jz      short loc_180003161
0x18000312a  test    r8, r8
0x18000312d  jz      short loc_180003161
0x18000312f  cmp     byte ptr [r8], 0
0x180003133  jz      short loc_180003161
0x180003135  mov     rcx, r8; this
0x180003138  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000313d  sub     rdx, rdi; DestinationSize
0x180003140  mov     rsi, rax
0x180003143  cmp     rdx, rax
0x180003146  jb      short loc_180003161
0x180003148  mov     r9, rax; SourceSize
0x18000314b  mov     rcx, rdi; Destination
0x18000314e  call    memcpy_s
0x180003153  test    rbx, rbx
0x180003156  jz      short loc_18000315B
0x180003158  mov     [rbx], rdi
0x18000315b  lea     rax, [rsi+rdi]
0x18000315f  jmp     short loc_180003170
0x180003161  test    rbx, rbx
0x180003164  jz      short loc_18000316D
0x180003166  mov     qword ptr [r9], 0
0x18000316d  mov     rax, rdi
0x180003170  mov     rbx, [rsp+28h+arg_0]
0x180003175  mov     rsi, [rsp+28h+arg_8]
0x18000317a  add     rsp, 20h
0x18000317e  pop     rdi
0x18000317f  retn
```
