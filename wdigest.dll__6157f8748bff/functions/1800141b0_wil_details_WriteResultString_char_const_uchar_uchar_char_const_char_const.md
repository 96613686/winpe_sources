# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800141b0`
- end: `0x180014220`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016198`
- `0x180033cc4`

## callees

- `0x18000f770`
- `0x1800141b0`
- `0x180016058`

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
0x1800141b0  mov     [rsp+arg_0], rbx
0x1800141b5  mov     [rsp+arg_8], rsi
0x1800141ba  push    rdi
0x1800141bb  sub     rsp, 20h
0x1800141bf  mov     rbx, r9
0x1800141c2  mov     rdi, rcx
0x1800141c5  cmp     rcx, rdx
0x1800141c8  jz      short loc_180014201
0x1800141ca  test    r8, r8
0x1800141cd  jz      short loc_180014201
0x1800141cf  cmp     byte ptr [r8], 0
0x1800141d3  jz      short loc_180014201
0x1800141d5  mov     rcx, r8; this
0x1800141d8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800141dd  sub     rdx, rdi; DestinationSize
0x1800141e0  mov     rsi, rax
0x1800141e3  cmp     rdx, rax
0x1800141e6  jb      short loc_180014201
0x1800141e8  mov     r9, rax; SourceSize
0x1800141eb  mov     rcx, rdi; Destination
0x1800141ee  call    memcpy_s
0x1800141f3  test    rbx, rbx
0x1800141f6  jz      short loc_1800141FB
0x1800141f8  mov     [rbx], rdi
0x1800141fb  lea     rax, [rsi+rdi]
0x1800141ff  jmp     short loc_180014210
0x180014201  test    rbx, rbx
0x180014204  jz      short loc_18001420D
0x180014206  mov     qword ptr [r9], 0
0x18001420d  mov     rax, rdi
0x180014210  mov     rbx, [rsp+28h+arg_0]
0x180014215  mov     rsi, [rsp+28h+arg_8]
0x18001421a  add     rsp, 20h
0x18001421e  pop     rdi
0x18001421f  retn
```
