# ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::InsertAt(unsigned __int64,uchar,unsigned __int64)

- ea: `0x18001adb0`
- end: `0x18001aec5`
- name: `?InsertAt@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAAX_KE0@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a9a4`

## callees

- `0x1800066cc`
- `0x180015990`
- `0x18001adb0`
- `0x18001ede0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001ae28`
- `msvcrt!memmove_s` at `0x18001ae28`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::InsertAt(
        __int64 *a1,
        unsigned __int64 a2,
        char a3)
{
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rsi
  __int64 result; // rax
  errno_t v9; // eax
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx

  v6 = a1[1];
  if ( a2 >= v6 )
  {
    v7 = a2 + 1;
    result = ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::SetCount(a1, a2 + 1, 0xFFFFFFFFLL);
    if ( (_BYTE)result )
      goto LABEL_11;
LABEL_19:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( !(unsigned __int8)ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::SetCount(
                           a1,
                           v6 + 1,
                           0xFFFFFFFFLL) )
    goto LABEL_19;
  v9 = memmove_s((void *const)(a2 + *a1 + 1), v6 - a2, (const void *const)(a2 + *a1), v6 - a2);
  if ( v9 )
  {
    if ( v9 == 12 )
      goto LABEL_19;
    if ( v9 == 22 || v9 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v9 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  result = ATL::CAtlArray<int,ATL::CElementTraits<int>>::CallConstructors(v10, 1);
  v7 = a2 + 1;
LABEL_11:
  if ( a2 < v7 )
  {
    v11 = a2;
    if ( v7 - a2 < 0x10 )
      goto LABEL_24;
    v12 = a2 + *a1;
    if ( v12 <= (unsigned __int64)a1 && v12 >= (unsigned __int64)a1 )
      goto LABEL_24;
    do
    {
      v11 += 16LL;
      result = v11;
    }
    while ( v11 < a2 );
    if ( v11 < v7 )
    {
LABEL_24:
      do
      {
        result = *a1;
        *(_BYTE *)(v11 + *a1) = a3;
        ++v11;
      }
      while ( v11 < v7 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001adb0  mov     rax, rsp
0x18001adb3  mov     [rax+20h], r9
0x18001adb7  mov     [rax+10h], rdx
0x18001adbb  mov     [rax+8], rcx
0x18001adbf  push    rsi
0x18001adc0  push    rdi
0x18001adc1  push    r14
0x18001adc3  sub     rsp, 30h
0x18001adc7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001adcf  mov     [rax+18h], rbx
0x18001add3  mov     r14b, r8b
0x18001add6  mov     rbx, rdx
0x18001add9  mov     rdi, rcx
0x18001addc  mov     rsi, [rcx+8]
0x18001ade0  or      r8d, 0FFFFFFFFh
0x18001ade4  cmp     rdx, rsi
0x18001ade7  jb      short loc_18001ADFF
0x18001ade9  lea     rsi, [rdx+1]
0x18001aded  mov     rdx, rsi
0x18001adf0  call    ?SetCount@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::SetCount(unsigned __int64,int)
0x18001adf5  test    al, al
0x18001adf7  jz      loc_18001AEA4
0x18001adfd  jmp     short loc_18001AE55
0x18001adff  lea     rdx, [rsi+1]
0x18001ae03  call    ?SetCount@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::SetCount(unsigned __int64,int)
0x18001ae08  test    al, al
0x18001ae0a  jz      loc_18001AEA4
0x18001ae10  mov     [rsp+48h+arg_18], rsi
0x18001ae15  sub     rsi, rbx
0x18001ae18  mov     r8, [rdi]
0x18001ae1b  add     r8, rbx; Source
0x18001ae1e  lea     rcx, [r8+1]; Destination
0x18001ae22  mov     r9, rsi; SourceSize
0x18001ae25  mov     rdx, rsi; DestinationSize
0x18001ae28  call    cs:__imp_memmove_s
0x18001ae2e  test    eax, eax
0x18001ae30  jz      short loc_18001AE46
0x18001ae32  cmp     eax, 0Ch
0x18001ae35  jz      short loc_18001AEA4
0x18001ae37  cmp     eax, 16h
0x18001ae3a  jz      short loc_18001AEBA
0x18001ae3c  cmp     eax, 22h ; '"'
0x18001ae3f  jz      short loc_18001AEBA
0x18001ae41  cmp     eax, 50h ; 'P'
0x18001ae44  jnz     short loc_18001AEAF
0x18001ae46  mov     edx, 1
0x18001ae4b  call    ?CallConstructors@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@CAXPEAH_K@Z; ATL::CAtlArray<int,ATL::CElementTraits<int>>::CallConstructors(int *,unsigned __int64)
0x18001ae50  nop
0x18001ae51  lea     rsi, [rbx+1]
0x18001ae55  cmp     rbx, rsi
0x18001ae58  jnb     short loc_18001AE96
0x18001ae5a  mov     rcx, rbx
0x18001ae5d  mov     rax, rsi
0x18001ae60  sub     rax, rbx
0x18001ae63  cmp     rax, 10h
0x18001ae67  jb      short loc_18001AE87
0x18001ae69  mov     rdx, [rdi]
0x18001ae6c  add     rdx, rbx
0x18001ae6f  cmp     rdx, rdi
0x18001ae72  ja      short loc_18001AE76
0x18001ae74  jnb     short loc_18001AE87
0x18001ae76  add     rcx, 10h
0x18001ae7a  mov     rax, rcx
0x18001ae7d  cmp     rcx, rbx
0x18001ae80  jb      short loc_18001AE76
0x18001ae82  cmp     rax, rsi
0x18001ae85  jnb     short loc_18001AE96
0x18001ae87  mov     rax, [rdi]
0x18001ae8a  mov     [rcx+rax], r14b
0x18001ae8e  inc     rcx
0x18001ae91  cmp     rcx, rsi
0x18001ae94  jb      short loc_18001AE87
0x18001ae96  mov     rbx, [rsp+48h+arg_10]
0x18001ae9b  add     rsp, 30h
0x18001ae9f  pop     r14
0x18001aea1  pop     rdi
0x18001aea2  pop     rsi
0x18001aea3  retn
0x18001aea4  mov     ecx, 8007000Eh; int
0x18001aea9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001aeaf  mov     ecx, 80004005h; int
0x18001aeb4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001aeba  mov     ecx, 80070057h; int
0x18001aebf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
