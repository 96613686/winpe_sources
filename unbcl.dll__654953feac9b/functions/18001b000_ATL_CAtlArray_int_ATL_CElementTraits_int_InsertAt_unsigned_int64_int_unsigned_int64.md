# ATL::CAtlArray<int,ATL::CElementTraits<int>>::InsertAt(unsigned __int64,int,unsigned __int64)

- ea: `0x18001b000`
- end: `0x18001b132`
- name: `?InsertAt@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@QEAAX_KH0@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ab54`

## callees

- `0x1800066cc`
- `0x180015990`
- `0x18001b000`
- `0x18001eed8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001b095`
- `msvcrt!memmove_s` at `0x18001b095`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<int,ATL::CElementTraits<int>>::InsertAt(__int64 *a1, unsigned __int64 a2, int a3)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rsi
  __int64 result; // rax
  __int64 v9; // r15
  errno_t v10; // eax
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx

  v6 = a1[1];
  if ( a2 >= v6 )
  {
    v7 = a2 + 1;
    result = ATL::CAtlArray<int,ATL::CElementTraits<int>>::SetCount(a1, a2 + 1, 0xFFFFFFFFLL);
    if ( (_BYTE)result )
    {
      v9 = 4 * a2;
      goto LABEL_11;
    }
LABEL_19:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( !(unsigned __int8)ATL::CAtlArray<int,ATL::CElementTraits<int>>::SetCount(a1, v6 + 1, 0xFFFFFFFFLL) )
    goto LABEL_19;
  v9 = 4 * a2;
  v7 = a2 + 1;
  v10 = memmove_s((void *const)(*a1 + 4 * (a2 + 1)), 4 * (v6 - a2), (const void *const)(4 * a2 + *a1), 4 * (v6 - a2));
  if ( v10 )
  {
    if ( v10 == 12 )
      goto LABEL_19;
    if ( v10 == 22 || v10 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v10 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  try
  {
    result = ATL::CAtlArray<int,ATL::CElementTraits<int>>::CallConstructors(v11, 1);
  }
  catch ( ... )
  {
    ATL::CElementTraitsBase<int>::RelocateElements(*a1 + 4 * a2, *a1 + 4 * (a2 + 1), v6 - a2);
    ATL::CAtlArray<int,ATL::CElementTraits<int>>::SetCount(a1, v6, 0xFFFFFFFFLL);
    throw;
  }
LABEL_11:
  if ( a2 < v7 )
  {
    v12 = a2;
    if ( v7 - a2 < 4 )
      goto LABEL_29;
    v13 = v9 + *a1;
    if ( v13 <= (unsigned __int64)a1 && v13 >= (unsigned __int64)a1 )
      goto LABEL_29;
    do
    {
      v12 += 4LL;
      result = v12;
    }
    while ( v12 < a2 );
    if ( v12 < v7 )
    {
LABEL_29:
      do
      {
        result = *a1;
        *(_DWORD *)(*a1 + 4 * v12++) = a3;
      }
      while ( v12 < v7 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b000  mov     rax, rsp
0x18001b003  mov     [rax+20h], r9
0x18001b007  mov     [rax+10h], rdx
0x18001b00b  mov     [rax+8], rcx
0x18001b00f  push    rsi
0x18001b010  push    rdi
0x18001b011  push    r12
0x18001b013  push    r14
0x18001b015  push    r15
0x18001b017  sub     rsp, 30h
0x18001b01b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18001b023  mov     [rax+18h], rbx
0x18001b027  mov     r12d, r8d
0x18001b02a  mov     rbx, rdx
0x18001b02d  mov     rdi, rcx
0x18001b030  mov     r14, [rcx+8]
0x18001b034  or      r8d, 0FFFFFFFFh
0x18001b038  cmp     rdx, r14
0x18001b03b  jb      short loc_18001B05B
0x18001b03d  lea     rsi, [rdx+1]
0x18001b041  mov     rdx, rsi
0x18001b044  call    ?SetCount@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<int,ATL::CElementTraits<int>>::SetCount(unsigned __int64,int)
0x18001b049  test    al, al
0x18001b04b  jz      loc_18001B111
0x18001b051  lea     r15, ds:0[rbx*4]
0x18001b059  jmp     short loc_18001B0BE
0x18001b05b  lea     rdx, [r14+1]
0x18001b05f  call    ?SetCount@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<int,ATL::CElementTraits<int>>::SetCount(unsigned __int64,int)
0x18001b064  test    al, al
0x18001b066  jz      loc_18001B111
0x18001b06c  mov     [rsp+58h+arg_18], r14
0x18001b071  mov     rax, [rdi]
0x18001b074  sub     r14, rbx
0x18001b077  shl     r14, 2
0x18001b07b  lea     r15, ds:0[rbx*4]
0x18001b083  lea     rsi, [rbx+1]
0x18001b087  lea     r8, [r15+rax]; Source
0x18001b08b  lea     rcx, [rax+rsi*4]; Destination
0x18001b08f  mov     r9, r14; SourceSize
0x18001b092  mov     rdx, r14; DestinationSize
0x18001b095  call    cs:__imp_memmove_s
0x18001b09b  test    eax, eax
0x18001b09d  jz      short loc_18001B0B3
0x18001b09f  cmp     eax, 0Ch
0x18001b0a2  jz      short loc_18001B111
0x18001b0a4  cmp     eax, 16h
0x18001b0a7  jz      short loc_18001B127
0x18001b0a9  cmp     eax, 22h ; '"'
0x18001b0ac  jz      short loc_18001B127
0x18001b0ae  cmp     eax, 50h ; 'P'
0x18001b0b1  jnz     short loc_18001B11C
0x18001b0b3  mov     edx, 1
0x18001b0b8  call    ?CallConstructors@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@CAXPEAH_K@Z; ATL::CAtlArray<int,ATL::CElementTraits<int>>::CallConstructors(int *,unsigned __int64)
0x18001b0bd  nop
0x18001b0be  cmp     rbx, rsi
0x18001b0c1  jnb     short loc_18001B0FF
0x18001b0c3  mov     rcx, rbx
0x18001b0c6  mov     rax, rsi
0x18001b0c9  sub     rax, rbx
0x18001b0cc  cmp     rax, 4
0x18001b0d0  jb      short loc_18001B0F0
0x18001b0d2  mov     rdx, [rdi]
0x18001b0d5  add     rdx, r15
0x18001b0d8  cmp     rdx, rdi
0x18001b0db  ja      short loc_18001B0DF
0x18001b0dd  jnb     short loc_18001B0F0
0x18001b0df  add     rcx, 4
0x18001b0e3  mov     rax, rcx
0x18001b0e6  cmp     rcx, rbx
0x18001b0e9  jb      short loc_18001B0DF
0x18001b0eb  cmp     rax, rsi
0x18001b0ee  jnb     short loc_18001B0FF
0x18001b0f0  mov     rax, [rdi]
0x18001b0f3  mov     [rax+rcx*4], r12d
0x18001b0f7  inc     rcx
0x18001b0fa  cmp     rcx, rsi
0x18001b0fd  jb      short loc_18001B0F0
0x18001b0ff  mov     rbx, [rsp+58h+arg_10]
0x18001b104  add     rsp, 30h
0x18001b108  pop     r15
0x18001b10a  pop     r14
0x18001b10c  pop     r12
0x18001b10e  pop     rdi
0x18001b10f  pop     rsi
0x18001b110  retn
0x18001b111  mov     ecx, 8007000Eh; int
0x18001b116  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001b11c  mov     ecx, 80004005h; int
0x18001b121  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001b127  mov     ecx, 80070057h; int
0x18001b12c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
