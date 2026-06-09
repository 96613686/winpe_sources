# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180007328`
- end: `0x180007398`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800090fc`
- `0x180009238`

## callees

- `0x180007328`
- `0x180009018`
- `0x180009dfc`

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
0x180007328  mov     [rsp+arg_0], rbx
0x18000732d  mov     [rsp+arg_8], rsi
0x180007332  push    rdi
0x180007333  sub     rsp, 20h
0x180007337  mov     rbx, r9
0x18000733a  mov     rdi, rcx
0x18000733d  cmp     rcx, rdx
0x180007340  jz      short loc_180007379
0x180007342  test    r8, r8
0x180007345  jz      short loc_180007379
0x180007347  cmp     byte ptr [r8], 0
0x18000734b  jz      short loc_180007379
0x18000734d  mov     rcx, r8; this
0x180007350  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007355  sub     rdx, rdi; DestinationSize
0x180007358  mov     rsi, rax
0x18000735b  cmp     rdx, rax
0x18000735e  jb      short loc_180007379
0x180007360  mov     r9, rax; SourceSize
0x180007363  mov     rcx, rdi; Destination
0x180007366  call    memcpy_s
0x18000736b  test    rbx, rbx
0x18000736e  jz      short loc_180007373
0x180007370  mov     [rbx], rdi
0x180007373  lea     rax, [rsi+rdi]
0x180007377  jmp     short loc_180007388
0x180007379  test    rbx, rbx
0x18000737c  jz      short loc_180007385
0x18000737e  mov     qword ptr [r9], 0
0x180007385  mov     rax, rdi
0x180007388  mov     rbx, [rsp+28h+arg_0]
0x18000738d  mov     rsi, [rsp+28h+arg_8]
0x180007392  add     rsp, 20h
0x180007396  pop     rdi
0x180007397  retn
```
