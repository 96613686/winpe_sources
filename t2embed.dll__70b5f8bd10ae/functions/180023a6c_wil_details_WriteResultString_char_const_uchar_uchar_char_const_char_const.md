# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180023a6c`
- end: `0x180023add`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180025aec`
- `0x180025c28`

## callees

- `0x180023a6c`
- `0x180025a1c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180023aaa`
- `msvcrt!memcpy_s` at `0x180023aaa`

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
0x180023a6c  mov     [rsp+arg_0], rbx
0x180023a71  mov     [rsp+arg_8], rsi
0x180023a76  push    rdi
0x180023a77  sub     rsp, 20h
0x180023a7b  mov     rbx, r9
0x180023a7e  mov     rdi, rcx
0x180023a81  cmp     rcx, rdx
0x180023a84  jz      short loc_180023ABE
0x180023a86  test    r8, r8
0x180023a89  jz      short loc_180023ABE
0x180023a8b  cmp     byte ptr [r8], 0
0x180023a8f  jz      short loc_180023ABE
0x180023a91  mov     rcx, r8; this
0x180023a94  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180023a99  sub     rdx, rdi; DestinationSize
0x180023a9c  mov     rsi, rax
0x180023a9f  cmp     rdx, rax
0x180023aa2  jb      short loc_180023ABE
0x180023aa4  mov     r9, rax; SourceSize
0x180023aa7  mov     rcx, rdi; Destination
0x180023aaa  call    cs:__imp_memcpy_s
0x180023ab0  test    rbx, rbx
0x180023ab3  jz      short loc_180023AB8
0x180023ab5  mov     [rbx], rdi
0x180023ab8  lea     rax, [rsi+rdi]
0x180023abc  jmp     short loc_180023ACD
0x180023abe  test    rbx, rbx
0x180023ac1  jz      short loc_180023ACA
0x180023ac3  mov     qword ptr [r9], 0
0x180023aca  mov     rax, rdi
0x180023acd  mov     rbx, [rsp+28h+arg_0]
0x180023ad2  mov     rsi, [rsp+28h+arg_8]
0x180023ad7  add     rsp, 20h
0x180023adb  pop     rdi
0x180023adc  retn
```
