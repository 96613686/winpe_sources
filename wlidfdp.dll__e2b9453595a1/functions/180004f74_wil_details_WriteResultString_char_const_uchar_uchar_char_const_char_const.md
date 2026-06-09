# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004f74`
- end: `0x180004fe4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800086d4`
- `0x180008810`

## callees

- `0x180004f74`
- `0x180008590`
- `0x180009b1c`

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
0x180004f74  mov     [rsp+arg_0], rbx
0x180004f79  mov     [rsp+arg_8], rsi
0x180004f7e  push    rdi
0x180004f7f  sub     rsp, 20h
0x180004f83  mov     rbx, r9
0x180004f86  mov     rdi, rcx
0x180004f89  cmp     rcx, rdx
0x180004f8c  jz      short loc_180004FC5
0x180004f8e  test    r8, r8
0x180004f91  jz      short loc_180004FC5
0x180004f93  cmp     byte ptr [r8], 0
0x180004f97  jz      short loc_180004FC5
0x180004f99  mov     rcx, r8; this
0x180004f9c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004fa1  sub     rdx, rdi; DestinationSize
0x180004fa4  mov     rsi, rax
0x180004fa7  cmp     rdx, rax
0x180004faa  jb      short loc_180004FC5
0x180004fac  mov     r9, rax; SourceSize
0x180004faf  mov     rcx, rdi; Destination
0x180004fb2  call    memcpy_s
0x180004fb7  test    rbx, rbx
0x180004fba  jz      short loc_180004FBF
0x180004fbc  mov     [rbx], rdi
0x180004fbf  lea     rax, [rsi+rdi]
0x180004fc3  jmp     short loc_180004FD4
0x180004fc5  test    rbx, rbx
0x180004fc8  jz      short loc_180004FD1
0x180004fca  mov     qword ptr [r9], 0
0x180004fd1  mov     rax, rdi
0x180004fd4  mov     rbx, [rsp+28h+arg_0]
0x180004fd9  mov     rsi, [rsp+28h+arg_8]
0x180004fde  add     rsp, 20h
0x180004fe2  pop     rdi
0x180004fe3  retn
```
