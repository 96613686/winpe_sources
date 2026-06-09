# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x180024cec`
- end: `0x180024e26`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `314`
- prototype: `__int64 __fastcall(unsigned int *, _WORD *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180026250`

## callees

- `0x180023d08`
- `0x180023e08`
- `0x180024cec`
- `0x180024e2c`
- `0x180025bd8`

## import_xrefs

- `msvcrt!free` at `0x180024d1e`
- `msvcrt!free` at `0x180024d1e`

## pseudocode

```c
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, _WORD *a2, int a3)
{
  void *v6; // rcx
  int v7; // eax
  unsigned __int64 v8; // rdi
  _WORD *v9; // rax
  _WORD *v10; // [rsp+38h] [rbp+10h] BYREF
  int v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = a3;
  if ( !a2 )
    return 10;
  v6 = (void *)*((_QWORD *)a1 + 1);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)a1 + 1) = 0;
  }
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 1;
  v10 = a2;
  v7 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 16);
  v8 = v7;
  if ( v7 < 0 )
    return 1;
  if ( *v10 == 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 28) < 0 )
      return 1;
    v9 = ++v10;
  }
  else
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 29) < 0 )
      return 1;
    v9 = v10;
  }
  LOBYTE(v11) = 1;
  if ( *v9 && (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(a1, &v10, &v11) >= 0 )
  {
    LOBYTE(v11) = 1;
    ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v10, &v11);
  }
  if ( *a1 )
    return *a1;
  if ( v8 >= *((_QWORD *)a1 + 2) )
    ATL::AtlThrowImpl(-2147024809);
  *(_QWORD *)(*((_QWORD *)a1 + 1) + 16 * v8 + 8) = 2;
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 30) >= 0 )
    return *a1;
  return 1;
}

```

## disassembly

```asm
0x180024cec  mov     [rsp+arg_0], rbx
0x180024cf1  mov     [rsp+arg_18], rsi
0x180024cf6  mov     [rsp+arg_10], r8d
0x180024cfb  push    rdi
0x180024cfc  sub     rsp, 20h
0x180024d00  mov     rdi, rdx
0x180024d03  mov     rbx, rcx
0x180024d06  xor     esi, esi
0x180024d08  test    rdx, rdx
0x180024d0b  jnz     short loc_180024D15
0x180024d0d  lea     eax, [rdx+0Ah]
0x180024d10  jmp     loc_180024E0B
0x180024d15  mov     rcx, [rcx+8]; Block
0x180024d19  test    rcx, rcx
0x180024d1c  jz      short loc_180024D28
0x180024d1e  call    cs:__imp_free
0x180024d24  mov     [rbx+8], rsi
0x180024d28  mov     [rbx+10h], rsi
0x180024d2c  mov     [rbx+18h], rsi
0x180024d30  mov     [rbx+28h], rsi
0x180024d34  mov     [rbx], esi
0x180024d36  mov     dword ptr [rbx+30h], 1
0x180024d3d  mov     [rsp+28h+arg_8], rdi
0x180024d42  mov     edx, 10h
0x180024d47  mov     rcx, rbx
0x180024d4a  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024d4f  movsxd  rdi, eax
0x180024d52  test    eax, eax
0x180024d54  js      loc_180024E06
0x180024d5a  mov     rax, [rsp+28h+arg_8]
0x180024d5f  mov     rcx, rbx
0x180024d62  cmp     word ptr [rax], 5Eh ; '^'
0x180024d66  jnz     short loc_180024D8A
0x180024d68  mov     edx, 1Ch
0x180024d6d  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024d72  test    eax, eax
0x180024d74  js      loc_180024E06
0x180024d7a  mov     rax, [rsp+28h+arg_8]
0x180024d7f  add     rax, 2
0x180024d83  mov     [rsp+28h+arg_8], rax
0x180024d88  jmp     short loc_180024D9D
0x180024d8a  mov     edx, 1Dh
0x180024d8f  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024d94  test    eax, eax
0x180024d96  js      short loc_180024E06
0x180024d98  mov     rax, [rsp+28h+arg_8]
0x180024d9d  mov     byte ptr [rsp+28h+arg_10], 1
0x180024da2  cmp     [rax], si
0x180024da5  jz      short loc_180024DD4
0x180024da7  lea     r8, [rsp+28h+arg_10]
0x180024dac  lea     rdx, [rsp+28h+arg_8]
0x180024db1  mov     rcx, rbx
0x180024db4  call    ?ParseAltE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(ushort const * *,bool &)
0x180024db9  test    eax, eax
0x180024dbb  js      short loc_180024DD4
0x180024dbd  mov     byte ptr [rsp+28h+arg_10], 1
0x180024dc2  lea     r8, [rsp+28h+arg_10]
0x180024dc7  lea     rdx, [rsp+28h+arg_8]
0x180024dcc  mov     rcx, rbx
0x180024dcf  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x180024dd4  cmp     [rbx], esi
0x180024dd6  jnz     short loc_180024E02
0x180024dd8  mov     rcx, rdi
0x180024ddb  cmp     rdi, [rbx+10h]
0x180024ddf  jnb     short loc_180024E1B
0x180024de1  add     rcx, rcx
0x180024de4  mov     rax, [rbx+8]
0x180024de8  mov     qword ptr [rax+rcx*8+8], 2
0x180024df1  mov     edx, 1Eh
0x180024df6  mov     rcx, rbx
0x180024df9  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024dfe  test    eax, eax
0x180024e00  js      short loc_180024E06
0x180024e02  mov     eax, [rbx]
0x180024e04  jmp     short loc_180024E0B
0x180024e06  mov     eax, 1
0x180024e0b  mov     rbx, [rsp+28h+arg_0]
0x180024e10  mov     rsi, [rsp+28h+arg_18]
0x180024e15  add     rsp, 20h
0x180024e19  pop     rdi
0x180024e1a  retn
0x180024e1b  mov     ecx, 80070057h; int
0x180024e20  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
