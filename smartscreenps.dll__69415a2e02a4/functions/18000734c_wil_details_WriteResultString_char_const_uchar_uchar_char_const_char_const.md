# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000734c`
- end: `0x1800073bd`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000926c`
- `0x1800093b8`

## callees

- `0x18000734c`
- `0x180009178`
- `0x18000a028`

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
0x18000734c  mov     [rsp+arg_0], rbx
0x180007351  mov     [rsp+arg_8], rsi
0x180007356  push    rdi
0x180007357  sub     rsp, 20h
0x18000735b  mov     rbx, r9
0x18000735e  mov     rdi, rcx
0x180007361  cmp     rcx, rdx
0x180007364  jz      short loc_18000739D
0x180007366  test    r8, r8
0x180007369  jz      short loc_18000739D
0x18000736b  cmp     byte ptr [r8], 0
0x18000736f  jz      short loc_18000739D
0x180007371  mov     rcx, r8; this
0x180007374  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007379  sub     rdx, rdi; DestinationSize
0x18000737c  mov     rsi, rax
0x18000737f  cmp     rdx, rax
0x180007382  jb      short loc_18000739D
0x180007384  mov     r9, rax; SourceSize
0x180007387  mov     rcx, rdi; Destination
0x18000738a  call    memcpy_s
0x18000738f  test    rbx, rbx
0x180007392  jz      short loc_180007397
0x180007394  mov     [rbx], rdi
0x180007397  lea     rax, [rsi+rdi]
0x18000739b  jmp     short loc_1800073AC
0x18000739d  test    rbx, rbx
0x1800073a0  jz      short loc_1800073A9
0x1800073a2  mov     qword ptr [r9], 0
0x1800073a9  mov     rax, rdi
0x1800073ac  mov     rbx, [rsp+28h+arg_0]
0x1800073b1  mov     rsi, [rsp+28h+arg_8]
0x1800073b6  add     rsp, 20h
0x1800073ba  pop     rdi
0x1800073bb  retn
```
