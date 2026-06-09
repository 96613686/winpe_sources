# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180007648`
- end: `0x1800076b9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae54`

## callees

- `0x180007648`
- `0x18000acd8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007686`
- `msvcrt!memcpy_s` at `0x180007686`

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
0x180007648  mov     [rsp+arg_0], rbx
0x18000764d  mov     [rsp+arg_8], rsi
0x180007652  push    rdi
0x180007653  sub     rsp, 20h
0x180007657  mov     rbx, r9
0x18000765a  mov     rdi, rcx
0x18000765d  cmp     rcx, rdx
0x180007660  jz      short loc_18000769A
0x180007662  test    r8, r8
0x180007665  jz      short loc_18000769A
0x180007667  cmp     byte ptr [r8], 0
0x18000766b  jz      short loc_18000769A
0x18000766d  mov     rcx, r8; this
0x180007670  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007675  sub     rdx, rdi; DestinationSize
0x180007678  mov     rsi, rax
0x18000767b  cmp     rdx, rax
0x18000767e  jb      short loc_18000769A
0x180007680  mov     r9, rax; SourceSize
0x180007683  mov     rcx, rdi; Destination
0x180007686  call    cs:__imp_memcpy_s
0x18000768c  test    rbx, rbx
0x18000768f  jz      short loc_180007694
0x180007691  mov     [rbx], rdi
0x180007694  lea     rax, [rsi+rdi]
0x180007698  jmp     short loc_1800076A9
0x18000769a  test    rbx, rbx
0x18000769d  jz      short loc_1800076A6
0x18000769f  mov     qword ptr [r9], 0
0x1800076a6  mov     rax, rdi
0x1800076a9  mov     rbx, [rsp+28h+arg_0]
0x1800076ae  mov     rsi, [rsp+28h+arg_8]
0x1800076b3  add     rsp, 20h
0x1800076b7  pop     rdi
0x1800076b8  retn
```
