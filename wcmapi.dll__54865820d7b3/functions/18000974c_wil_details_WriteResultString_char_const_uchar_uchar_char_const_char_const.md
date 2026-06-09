# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000974c`
- end: `0x1800097bd`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a3b4`
- `0x18000fde8`

## callees

- `0x18000974c`
- `0x18000a2b8`
- `0x18000aaf4`

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
0x18000974c  mov     [rsp+arg_0], rbx
0x180009751  mov     [rsp+arg_8], rsi
0x180009756  push    rdi
0x180009757  sub     rsp, 20h
0x18000975b  mov     rbx, r9
0x18000975e  mov     rdi, rcx
0x180009761  cmp     rcx, rdx
0x180009764  jz      short loc_18000979D
0x180009766  test    r8, r8
0x180009769  jz      short loc_18000979D
0x18000976b  cmp     byte ptr [r8], 0
0x18000976f  jz      short loc_18000979D
0x180009771  mov     rcx, r8; this
0x180009774  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009779  sub     rdx, rdi; DestinationSize
0x18000977c  mov     rsi, rax
0x18000977f  cmp     rdx, rax
0x180009782  jb      short loc_18000979D
0x180009784  mov     r9, rax; SourceSize
0x180009787  mov     rcx, rdi; Destination
0x18000978a  call    memcpy_s
0x18000978f  test    rbx, rbx
0x180009792  jz      short loc_180009797
0x180009794  mov     [rbx], rdi
0x180009797  lea     rax, [rsi+rdi]
0x18000979b  jmp     short loc_1800097AC
0x18000979d  test    rbx, rbx
0x1800097a0  jz      short loc_1800097A9
0x1800097a2  mov     qword ptr [r9], 0
0x1800097a9  mov     rax, rdi
0x1800097ac  mov     rbx, [rsp+28h+arg_0]
0x1800097b1  mov     rsi, [rsp+28h+arg_8]
0x1800097b6  add     rsp, 20h
0x1800097ba  pop     rdi
0x1800097bb  retn
```
