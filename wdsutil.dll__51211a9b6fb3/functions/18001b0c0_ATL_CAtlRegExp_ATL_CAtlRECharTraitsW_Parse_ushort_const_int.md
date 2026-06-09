# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x18001b0c0`
- end: `0x18001b2ce`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001486c`
- `0x18001e334`

## callees

- `0x1800085b8`
- `0x180017ef4`
- `0x18001b0c0`
- `0x18001b2d4`
- `0x18001bed4`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x18001b17f`
- `msvcrt!_wcslwr_s` at `0x18001b17f`
- `msvcrt!memcpy_s` at `0x18001b143`
- `msvcrt!memcpy_s` at `0x18001b143`
- `msvcrt!malloc` at `0x18001b119`
- `msvcrt!malloc` at `0x18001b119`
- `msvcrt!free` at `0x18001b0f1`
- `msvcrt!free` at `0x18001b284`
- `msvcrt!free` at `0x18001b0f1`
- `msvcrt!free` at `0x18001b284`

## string_xrefs

- `0x18001b134`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, wchar_t *a2, int a3)
{
  void *v4; // rcx
  wchar_t *v5; // rax
  wchar_t *v6; // rdi
  errno_t v7; // eax
  errno_t v8; // eax
  int v9; // eax
  unsigned __int64 v10; // rsi
  wchar_t *v11; // rax
  wchar_t *v13; // [rsp+58h] [rbp+10h] BYREF
  int v14; // [rsp+60h] [rbp+18h] BYREF

  v14 = a3;
  v13 = a2;
  v4 = (void *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)a1 + 1) = 0;
  }
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 0;
  v5 = (wchar_t *)malloc(0x6Au);
  v6 = v5;
  if ( !v5 )
    return 1;
  v7 = memcpy_s(v5, 0x6Au, L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})", 0x6Au);
  if ( v7 )
  {
    if ( v7 == 12 )
      goto LABEL_32;
    if ( v7 == 22 || v7 == 34 )
      goto LABEL_30;
    if ( v7 != 80 )
LABEL_31:
      ATL::AtlThrowImpl(-2147467259);
  }
  v8 = _wcslwr_s(v6, 0x35u);
  switch ( v8 )
  {
    case 0:
      goto LABEL_14;
    case 12:
LABEL_32:
      ATL::AtlThrowImpl(-2147024882);
    case 22:
    case 34:
      goto LABEL_30;
  }
  if ( v8 != 80 )
    goto LABEL_31;
LABEL_14:
  v13 = v6;
  v9 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 16);
  v10 = v9;
  if ( v9 < 0 )
    return 1;
  if ( *v13 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 29) >= 0 )
    {
      v11 = v13;
      goto LABEL_20;
    }
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 28) < 0 )
    return 1;
  v11 = ++v13;
LABEL_20:
  LOBYTE(v14) = 1;
  if ( *v11 && (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(a1, &v13, &v14) >= 0 )
  {
    LOBYTE(v14) = 1;
    ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v13, &v14);
  }
  if ( *a1 )
    goto LABEL_26;
  if ( v10 >= *((_QWORD *)a1 + 2) )
LABEL_30:
    ATL::AtlThrowImpl(-2147024809);
  *(_QWORD *)(*((_QWORD *)a1 + 1) + 16 * v10 + 8) = 2;
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 30) < 0 )
    return 1;
LABEL_26:
  if ( v6 != L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})" )
    free(v6);
  return *a1;
}

```

## disassembly

```asm
0x18001b0c0  mov     rax, rsp
0x18001b0c3  mov     [rax+18h], r8d
0x18001b0c7  mov     [rax+10h], rdx
0x18001b0cb  push    rsi
0x18001b0cc  push    rdi
0x18001b0cd  push    r14
0x18001b0cf  sub     rsp, 30h
0x18001b0d3  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001b0db  mov     [rax+8], rbx
0x18001b0df  mov     [rax+20h], rbp
0x18001b0e3  mov     rbx, rcx
0x18001b0e6  mov     rcx, [rcx+8]; Block
0x18001b0ea  xor     ebp, ebp
0x18001b0ec  test    rcx, rcx
0x18001b0ef  jz      short loc_18001B101
0x18001b0f1  call    cs:__imp_free
0x18001b0f8  nop     dword ptr [rax+rax+00h]
0x18001b0fd  mov     [rbx+8], rbp
0x18001b101  mov     [rbx+10h], rbp
0x18001b105  mov     [rbx+18h], rbp
0x18001b109  mov     [rbx+28h], rbp
0x18001b10d  mov     [rbx], ebp
0x18001b10f  mov     [rbx+30h], ebp
0x18001b112  mov     esi, 6Ah ; 'j'
0x18001b117  mov     ecx, esi; Size
0x18001b119  call    cs:__imp_malloc
0x18001b120  nop     dword ptr [rax+rax+00h]
0x18001b125  mov     rdi, rax
0x18001b128  test    rax, rax
0x18001b12b  jz      loc_18001B294
0x18001b131  mov     r9d, esi; SourceSize
0x18001b134  lea     r14, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x18001b13b  mov     r8, r14; Source
0x18001b13e  mov     edx, esi; DestinationSize
0x18001b140  mov     rcx, rax; Destination
0x18001b143  call    cs:__imp_memcpy_s
0x18001b14a  nop     dword ptr [rax+rax+00h]
0x18001b14f  test    eax, eax
0x18001b151  jz      short loc_18001B177
0x18001b153  cmp     eax, 0Ch
0x18001b156  jz      loc_18001B2C3
0x18001b15c  cmp     eax, 16h
0x18001b15f  jz      loc_18001B2AD
0x18001b165  cmp     eax, 22h ; '"'
0x18001b168  jz      loc_18001B2AD
0x18001b16e  cmp     eax, 50h ; 'P'
0x18001b171  jnz     loc_18001B2B8
0x18001b177  mov     edx, 35h ; '5'; SizeInWords
0x18001b17c  mov     rcx, rdi; String
0x18001b17f  call    cs:__imp__wcslwr_s
0x18001b186  nop     dword ptr [rax+rax+00h]
0x18001b18b  test    eax, eax
0x18001b18d  jz      short loc_18001B1B3
0x18001b18f  cmp     eax, 0Ch
0x18001b192  jz      loc_18001B2C3
0x18001b198  cmp     eax, 16h
0x18001b19b  jz      loc_18001B2AD
0x18001b1a1  cmp     eax, 22h ; '"'
0x18001b1a4  jz      loc_18001B2AD
0x18001b1aa  cmp     eax, 50h ; 'P'
0x18001b1ad  jnz     loc_18001B2B8
0x18001b1b3  mov     [rsp+48h+arg_8], rdi
0x18001b1b8  mov     edx, 10h
0x18001b1bd  mov     rcx, rbx
0x18001b1c0  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18001b1c5  movsxd  rsi, eax
0x18001b1c8  test    eax, eax
0x18001b1ca  js      loc_18001B294
0x18001b1d0  mov     rcx, [rsp+48h+arg_8]
0x18001b1d5  cmp     word ptr [rcx], 5Eh ; '^'
0x18001b1d9  mov     rcx, rbx
0x18001b1dc  jnz     short loc_18001B200
0x18001b1de  mov     edx, 1Ch
0x18001b1e3  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18001b1e8  test    eax, eax
0x18001b1ea  js      loc_18001B294
0x18001b1f0  mov     rax, [rsp+48h+arg_8]
0x18001b1f5  add     rax, 2
0x18001b1f9  mov     [rsp+48h+arg_8], rax
0x18001b1fe  jmp     short loc_18001B217
0x18001b200  mov     edx, 1Dh
0x18001b205  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18001b20a  test    eax, eax
0x18001b20c  js      loc_18001B294
0x18001b212  mov     rax, [rsp+48h+arg_8]
0x18001b217  mov     byte ptr [rsp+48h+arg_10], 1
0x18001b21c  cmp     [rax], bp
0x18001b21f  jz      short loc_18001B24E
0x18001b221  lea     r8, [rsp+48h+arg_10]
0x18001b226  lea     rdx, [rsp+48h+arg_8]
0x18001b22b  mov     rcx, rbx
0x18001b22e  call    ?ParseAltE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(ushort const * *,bool &)
0x18001b233  test    eax, eax
0x18001b235  js      short loc_18001B24E
0x18001b237  mov     byte ptr [rsp+48h+arg_10], 1
0x18001b23c  lea     r8, [rsp+48h+arg_10]
0x18001b241  lea     rdx, [rsp+48h+arg_8]
0x18001b246  mov     rcx, rbx
0x18001b249  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x18001b24e  cmp     [rbx], ebp
0x18001b250  jnz     short loc_18001B27C
0x18001b252  mov     rcx, rsi
0x18001b255  cmp     rsi, [rbx+10h]
0x18001b259  jnb     short loc_18001B2AD
0x18001b25b  add     rcx, rcx
0x18001b25e  mov     rax, [rbx+8]
0x18001b262  mov     qword ptr [rax+rcx*8+8], 2
0x18001b26b  mov     edx, 1Eh
0x18001b270  mov     rcx, rbx
0x18001b273  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18001b278  test    eax, eax
0x18001b27a  js      short loc_18001B294
0x18001b27c  cmp     rdi, r14
0x18001b27f  jz      short loc_18001B290
0x18001b281  mov     rcx, rdi; Block
0x18001b284  call    cs:__imp_free
0x18001b28b  nop     dword ptr [rax+rax+00h]
0x18001b290  mov     eax, [rbx]
0x18001b292  jmp     short loc_18001B299
0x18001b294  mov     eax, 1
0x18001b299  mov     rbx, [rsp+48h+arg_0]
0x18001b29e  mov     rbp, [rsp+48h+arg_18]
0x18001b2a3  add     rsp, 30h
0x18001b2a7  pop     r14
0x18001b2a9  pop     rdi
0x18001b2aa  pop     rsi
0x18001b2ab  retn
0x18001b2ad  mov     ecx, 80070057h; int
0x18001b2b2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001b2b8  mov     ecx, 80004005h; int
0x18001b2bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001b2c3  mov     ecx, 8007000Eh; int
0x18001b2c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
