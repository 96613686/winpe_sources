# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800182b4`
- end: `0x180018323`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b928`

## callees

- `0x1800182b4`
- `0x18001b7c8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800182f4`
- `msvcrt!memcpy_s` at `0x1800182f4`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x1800182b4  push    rbx
0x1800182b6  push    rbp
0x1800182b7  push    rsi
0x1800182b8  push    rdi
0x1800182b9  sub     rsp, 28h
0x1800182bd  xor     ebp, ebp
0x1800182bf  mov     rbx, r9
0x1800182c2  mov     r10, rdx
0x1800182c5  mov     rdi, rcx
0x1800182c8  cmp     rcx, rdx
0x1800182cb  jz      short loc_18001830E
0x1800182cd  test    r8, r8
0x1800182d0  jz      short loc_18001830E
0x1800182d2  cmp     [r8], bp
0x1800182d6  jz      short loc_18001830E
0x1800182d8  mov     rcx, r8; this
0x1800182db  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800182e0  sub     r10, rdi
0x1800182e3  mov     rsi, rax
0x1800182e6  cmp     r10, rax
0x1800182e9  jb      short loc_18001830E
0x1800182eb  mov     r9, rax; SourceSize
0x1800182ee  mov     rdx, r10; DestinationSize
0x1800182f1  mov     rcx, rdi; Destination
0x1800182f4  call    cs:__imp_memcpy_s
0x1800182fb  nop     dword ptr [rax+rax+00h]
0x180018300  test    rbx, rbx
0x180018303  jz      short loc_180018308
0x180018305  mov     [rbx], rdi
0x180018308  lea     rax, [rsi+rdi]
0x18001830c  jmp     short loc_180018319
0x18001830e  test    rbx, rbx
0x180018311  jz      short loc_180018316
0x180018313  mov     [r9], rbp
0x180018316  mov     rax, rdi
0x180018319  add     rsp, 28h
0x18001831d  pop     rdi
0x18001831e  pop     rsi
0x18001831f  pop     rbp
0x180018320  pop     rbx
0x180018321  retn
```
