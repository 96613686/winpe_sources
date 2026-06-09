# ATL::CAtlArray<ushort,ATL::CElementTraits<ushort>>::InsertAt(unsigned __int64,ushort,unsigned __int64)

- ea: `0x18001aecc`
- end: `0x18001aff7`
- name: `?InsertAt@?$CAtlArray@GV?$CElementTraits@G@ATL@@@ATL@@QEAAX_KG0@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001aa80`

## callees

- `0x1800066cc`
- `0x180015990`
- `0x18001aecc`
- `0x18001ee5c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001af59`
- `msvcrt!memmove_s` at `0x18001af59`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<unsigned short,ATL::CElementTraits<unsigned short>>::InsertAt(
        __int64 *a1,
        unsigned __int64 a2,
        __int16 a3)
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
    result = ATL::CAtlArray<unsigned short,ATL::CElementTraits<unsigned short>>::SetCount(a1, a2 + 1, 0xFFFFFFFFLL);
    if ( (_BYTE)result )
    {
      v9 = 2 * a2;
      goto LABEL_11;
    }
LABEL_19:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( !(unsigned __int8)ATL::CAtlArray<unsigned short,ATL::CElementTraits<unsigned short>>::SetCount(
                           a1,
                           v6 + 1,
                           0xFFFFFFFFLL) )
    goto LABEL_19;
  v9 = 2 * a2;
  v7 = a2 + 1;
  v10 = memmove_s((void *const)(*a1 + 2 * (a2 + 1)), 2 * (v6 - a2), (const void *const)(2 * a2 + *a1), 2 * (v6 - a2));
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
    ATL::CElementTraitsBase<unsigned short>::RelocateElements(*a1 + 2 * a2, *a1 + 2 * (a2 + 1), v6 - a2);
    ATL::CAtlArray<unsigned short,ATL::CElementTraits<unsigned short>>::SetCount(a1, v6, 0xFFFFFFFFLL);
    throw;
  }
LABEL_11:
  if ( a2 < v7 )
  {
    v12 = a2;
    if ( v7 - a2 < 8 )
      goto LABEL_29;
    v13 = v9 + *a1;
    if ( v13 <= (unsigned __int64)a1 && v13 >= (unsigned __int64)a1 )
      goto LABEL_29;
    do
    {
      v12 += 8LL;
      result = v12;
    }
    while ( v12 < a2 );
    if ( v12 < v7 )
    {
LABEL_29:
      do
      {
        result = *a1;
        *(_WORD *)(*a1 + 2 * v12++) = a3;
      }
      while ( v12 < v7 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001aecc  mov     rax, rsp
0x18001aecf  mov     [rax+20h], r9
0x18001aed3  mov     [rax+10h], rdx
0x18001aed7  mov     [rax+8], rcx
0x18001aedb  push    rsi
0x18001aedc  push    rdi
0x18001aedd  push    r12
0x18001aedf  push    r14
0x18001aee1  push    r15
0x18001aee3  sub     rsp, 30h
0x18001aee7  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18001aeef  mov     [rax+18h], rbx
0x18001aef3  movzx   r12d, r8w
0x18001aef7  mov     rbx, rdx
0x18001aefa  mov     rdi, rcx
0x18001aefd  mov     r14, [rcx+8]
0x18001af01  or      r8d, 0FFFFFFFFh
0x18001af05  cmp     rdx, r14
0x18001af08  jb      short loc_18001AF24
0x18001af0a  lea     rsi, [rdx+1]
0x18001af0e  mov     rdx, rsi
0x18001af11  call    ?SetCount@?$CAtlArray@GV?$CElementTraits@G@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ushort,ATL::CElementTraits<ushort>>::SetCount(unsigned __int64,int)
0x18001af16  test    al, al
0x18001af18  jz      loc_18001AFD6
0x18001af1e  lea     r15, [rbx+rbx]
0x18001af22  jmp     short loc_18001AF82
0x18001af24  lea     rdx, [r14+1]
0x18001af28  call    ?SetCount@?$CAtlArray@GV?$CElementTraits@G@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ushort,ATL::CElementTraits<ushort>>::SetCount(unsigned __int64,int)
0x18001af2d  test    al, al
0x18001af2f  jz      loc_18001AFD6
0x18001af35  mov     [rsp+58h+arg_18], r14
0x18001af3a  mov     rax, [rdi]
0x18001af3d  sub     r14, rbx
0x18001af40  add     r14, r14
0x18001af43  lea     r15, [rbx+rbx]
0x18001af47  lea     rsi, [rbx+1]
0x18001af4b  lea     r8, [r15+rax]; Source
0x18001af4f  lea     rcx, [rax+rsi*2]; Destination
0x18001af53  mov     r9, r14; SourceSize
0x18001af56  mov     rdx, r14; DestinationSize
0x18001af59  call    cs:__imp_memmove_s
0x18001af5f  test    eax, eax
0x18001af61  jz      short loc_18001AF77
0x18001af63  cmp     eax, 0Ch
0x18001af66  jz      short loc_18001AFD6
0x18001af68  cmp     eax, 16h
0x18001af6b  jz      short loc_18001AFEC
0x18001af6d  cmp     eax, 22h ; '"'
0x18001af70  jz      short loc_18001AFEC
0x18001af72  cmp     eax, 50h ; 'P'
0x18001af75  jnz     short loc_18001AFE1
0x18001af77  mov     edx, 1
0x18001af7c  call    ?CallConstructors@?$CAtlArray@HV?$CElementTraits@H@ATL@@@ATL@@CAXPEAH_K@Z; ATL::CAtlArray<int,ATL::CElementTraits<int>>::CallConstructors(int *,unsigned __int64)
0x18001af81  nop
0x18001af82  cmp     rbx, rsi
0x18001af85  jnb     short loc_18001AFC4
0x18001af87  mov     rcx, rbx
0x18001af8a  mov     rax, rsi
0x18001af8d  sub     rax, rbx
0x18001af90  cmp     rax, 8
0x18001af94  jb      short loc_18001AFB4
0x18001af96  mov     rdx, [rdi]
0x18001af99  add     rdx, r15
0x18001af9c  cmp     rdx, rdi
0x18001af9f  ja      short loc_18001AFA3
0x18001afa1  jnb     short loc_18001AFB4
0x18001afa3  add     rcx, 8
0x18001afa7  mov     rax, rcx
0x18001afaa  cmp     rcx, rbx
0x18001afad  jb      short loc_18001AFA3
0x18001afaf  cmp     rax, rsi
0x18001afb2  jnb     short loc_18001AFC4
0x18001afb4  mov     rax, [rdi]
0x18001afb7  mov     [rax+rcx*2], r12w
0x18001afbc  inc     rcx
0x18001afbf  cmp     rcx, rsi
0x18001afc2  jb      short loc_18001AFB4
0x18001afc4  mov     rbx, [rsp+58h+arg_10]
0x18001afc9  add     rsp, 30h
0x18001afcd  pop     r15
0x18001afcf  pop     r14
0x18001afd1  pop     r12
0x18001afd3  pop     rdi
0x18001afd4  pop     rsi
0x18001afd5  retn
0x18001afd6  mov     ecx, 8007000Eh; int
0x18001afdb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001afe1  mov     ecx, 80004005h; int
0x18001afe6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001afec  mov     ecx, 80070057h; int
0x18001aff1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
