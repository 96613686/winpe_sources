# ATL::CAtlArray<UnBCL::Object *,ATL::CElementTraits<UnBCL::Object *>>::InsertAt(unsigned __int64,UnBCL::Object * const &,unsigned __int64)

- ea: `0x18001b138`
- end: `0x18001b27c`
- name: `?InsertAt@?$CAtlArray@PEAVObject@UnBCL@@V?$CElementTraits@PEAVObject@UnBCL@@@ATL@@@ATL@@QEAAX_KAEBQEAVObject@UnBCL@@0@Z`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ac24`
- `0x18001ad00`

## callees

- `0x1800066cc`
- `0x180015990`
- `0x18001b138`
- `0x18001ef54`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001b1cd`
- `msvcrt!memmove_s` at `0x18001b1cd`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<UnBCL::Object *,ATL::CElementTraits<UnBCL::Object *>>::InsertAt(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 *a3)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rsi
  __int64 result; // rax
  __int64 v9; // r12
  errno_t v10; // eax
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rcx

  v6 = a1[1];
  if ( a2 >= v6 )
  {
    v7 = a2 + 1;
    result = ATL::CAtlArray<UnBCL::String *,ATL::CElementTraits<UnBCL::String *>>::SetCount(a1, a2 + 1, 0xFFFFFFFFLL);
    if ( (_BYTE)result )
    {
      v9 = 8 * a2;
      goto LABEL_11;
    }
LABEL_21:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( !(unsigned __int8)ATL::CAtlArray<UnBCL::String *,ATL::CElementTraits<UnBCL::String *>>::SetCount(
                           a1,
                           v6 + 1,
                           0xFFFFFFFFLL) )
    goto LABEL_21;
  v9 = 8 * a2;
  v7 = a2 + 1;
  v10 = memmove_s((void *const)(*a1 + 8 * (a2 + 1)), 8 * (v6 - a2), (const void *const)(8 * a2 + *a1), 8 * (v6 - a2));
  if ( v10 )
  {
    if ( v10 == 12 )
      goto LABEL_21;
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
    ATL::CElementTraitsBase<UnBCL::String *>::RelocateElements(*a1 + 8 * a2, *a1 + 8 * (a2 + 1), v6 - a2);
    ATL::CAtlArray<UnBCL::String *,ATL::CElementTraits<UnBCL::String *>>::SetCount(a1, v6, 0xFFFFFFFFLL);
    throw;
  }
LABEL_11:
  if ( a2 < v7 )
  {
    v12 = a2;
    if ( v7 - a2 < 2 )
      goto LABEL_31;
    v13 = v9 + *a1;
    if ( v13 <= (unsigned __int64)a1 && v13 >= (unsigned __int64)a1 )
      goto LABEL_31;
    if ( v13 <= (unsigned __int64)a3 && v13 >= (unsigned __int64)a3 )
      goto LABEL_31;
    do
    {
      v12 += 2LL;
      result = v12;
    }
    while ( v12 < a2 );
    if ( v12 < v7 )
    {
LABEL_31:
      do
      {
        result = *a3;
        *(_QWORD *)(*a1 + 8 * v12++) = *a3;
      }
      while ( v12 < v7 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b138  mov     rax, rsp
0x18001b13b  mov     [rax+20h], r9
0x18001b13f  mov     [rax+10h], rdx
0x18001b143  mov     [rax+8], rcx
0x18001b147  push    rsi
0x18001b148  push    rdi
0x18001b149  push    r12
0x18001b14b  push    r14
0x18001b14d  push    r15
0x18001b14f  sub     rsp, 30h
0x18001b153  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18001b15b  mov     [rax+18h], rbx
0x18001b15f  mov     r15, r8
0x18001b162  mov     rbx, rdx
0x18001b165  mov     rdi, rcx
0x18001b168  mov     r14, [rcx+8]
0x18001b16c  or      r8d, 0FFFFFFFFh
0x18001b170  cmp     rdx, r14
0x18001b173  jb      short loc_18001B193
0x18001b175  lea     rsi, [rdx+1]
0x18001b179  mov     rdx, rsi
0x18001b17c  call    ?SetCount@?$CAtlArray@PEAVString@UnBCL@@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::String *,ATL::CElementTraits<UnBCL::String *>>::SetCount(unsigned __int64,int)
0x18001b181  test    al, al
0x18001b183  jz      loc_18001B25B
0x18001b189  lea     r12, ds:0[rbx*8]
0x18001b191  jmp     short loc_18001B1FE
0x18001b193  lea     rdx, [r14+1]
0x18001b197  call    ?SetCount@?$CAtlArray@PEAVString@UnBCL@@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::String *,ATL::CElementTraits<UnBCL::String *>>::SetCount(unsigned __int64,int)
0x18001b19c  test    al, al
0x18001b19e  jz      loc_18001B25B
0x18001b1a4  mov     [rsp+58h+arg_18], r14
0x18001b1a9  mov     rax, [rdi]
0x18001b1ac  sub     r14, rbx
0x18001b1af  shl     r14, 3
0x18001b1b3  lea     r12, ds:0[rbx*8]
0x18001b1bb  lea     rsi, [rbx+1]
0x18001b1bf  lea     r8, [r12+rax]; Source
0x18001b1c3  lea     rcx, [rax+rsi*8]; Destination
0x18001b1c7  mov     r9, r14; SourceSize
0x18001b1ca  mov     rdx, r14; DestinationSize
0x18001b1cd  call    cs:__imp_memmove_s
0x18001b1d3  test    eax, eax
0x18001b1d5  jz      short loc_18001B1F3
0x18001b1d7  cmp     eax, 0Ch
0x18001b1da  jz      short loc_18001B25B
0x18001b1dc  cmp     eax, 16h
0x18001b1df  jz      loc_18001B271
0x18001b1e5  cmp     eax, 22h ; '"'
0x18001b1e8  jz      loc_18001B271
0x18001b1ee  cmp     eax, 50h ; 'P'
0x18001b1f1  jnz     short loc_18001B266
0x18001b1f3  mov     edx, 1
0x18001b1f8  call    ?CallConstructors@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@CAXPEAH_K@Z; ATL::CAtlArray<int,ATL::CElementTraits<int>>::CallConstructors(int *,unsigned __int64)
0x18001b1fd  nop
0x18001b1fe  cmp     rbx, rsi
0x18001b201  jnb     short loc_18001B249
0x18001b203  mov     rdx, rbx
0x18001b206  mov     rax, rsi
0x18001b209  sub     rax, rbx
0x18001b20c  cmp     rax, 2
0x18001b210  jb      short loc_18001B237
0x18001b212  mov     rcx, [rdi]
0x18001b215  add     rcx, r12
0x18001b218  cmp     rcx, rdi
0x18001b21b  ja      short loc_18001B21F
0x18001b21d  jnb     short loc_18001B237
0x18001b21f  cmp     rcx, r15
0x18001b222  ja      short loc_18001B226
0x18001b224  jnb     short loc_18001B237
0x18001b226  add     rdx, 2
0x18001b22a  mov     rax, rdx
0x18001b22d  cmp     rdx, rbx
0x18001b230  jb      short loc_18001B226
0x18001b232  cmp     rax, rsi
0x18001b235  jnb     short loc_18001B249
0x18001b237  mov     rcx, [rdi]
0x18001b23a  mov     rax, [r15]
0x18001b23d  mov     [rcx+rdx*8], rax
0x18001b241  inc     rdx
0x18001b244  cmp     rdx, rsi
0x18001b247  jb      short loc_18001B237
0x18001b249  mov     rbx, [rsp+58h+arg_10]
0x18001b24e  add     rsp, 30h
0x18001b252  pop     r15
0x18001b254  pop     r14
0x18001b256  pop     r12
0x18001b258  pop     rdi
0x18001b259  pop     rsi
0x18001b25a  retn
0x18001b25b  mov     ecx, 8007000Eh; int
0x18001b260  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001b266  mov     ecx, 80004005h; int
0x18001b26b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001b271  mov     ecx, 80070057h; int
0x18001b276  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
