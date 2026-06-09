# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x18000cf44`
- end: `0x18000d095`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `337`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c4d0`

## callees

- `0x18000c24c`
- `0x18000c278`
- `0x18000c3b8`
- `0x18000cf44`
- `0x18000dbec`
- `0x18000e028`
- `0x18000e09c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000cfce`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000cfce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d075`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d075`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000cfa1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000cfa1`

## pseudocode

```c
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, unsigned __int64 a2, int a3)
{
  __int64 v6; // rax
  size_t v7; // rbp
  ATL::Checked *v8; // rax
  wchar_t *v9; // rdi
  errno_t v10; // eax
  int v11; // eax
  unsigned __int64 v12; // rbp
  unsigned __int64 v13; // [rsp+20h] [rbp-28h]
  wchar_t *v14; // [rsp+58h] [rbp+10h] BYREF
  int v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = a3;
  if ( !a2 )
    return 10;
  ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(
    a1 + 2,
    0);
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  v7 = 2 * (int)v6 + 2;
  v8 = (ATL::Checked *)malloc(v7);
  v9 = (wchar_t *)v8;
  if ( !v8 )
    return 1;
  ATL::Checked::memcpy_s(v8, (void *)v7, a2, (const void *)v7, v13);
  v10 = _wcslwr_s(v9, (int)(v7 >> 1));
  ATL::AtlCrtErrorCheck(v10);
  v14 = v9;
  v11 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 16);
  v12 = v11;
  if ( v11 < 0 )
    return 1;
  if ( *v14 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 29) >= 0 )
      goto LABEL_11;
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 28) < 0 )
    return 1;
  ++v14;
LABEL_11:
  LOBYTE(v15) = 1;
  ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v14, &v15);
  if ( !*a1 )
  {
    *(_QWORD *)(ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](
                  (_QWORD *)a1 + 1,
                  v12)
              + 8) = 2;
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 30) < 0 )
      return 1;
  }
  if ( v9 != (wchar_t *)a2 )
    free(v9);
  return *a1;
}

```

## disassembly

```asm
0x18000cf44  mov     [rsp+arg_0], rbx
0x18000cf49  mov     [rsp+arg_10], r8d
0x18000cf4e  push    rbp
0x18000cf4f  push    rsi
0x18000cf50  push    rdi
0x18000cf51  push    r14
0x18000cf53  push    r15; unsigned __int64
0x18000cf55  sub     rsp, 20h
0x18000cf59  mov     rsi, rdx
0x18000cf5c  mov     rbx, rcx
0x18000cf5f  xor     r15d, r15d
0x18000cf62  test    rdx, rdx
0x18000cf65  jnz     short loc_18000CF6F
0x18000cf67  lea     eax, [rdx+0Ah]
0x18000cf6a  jmp     loc_18000D084
0x18000cf6f  xor     edx, edx
0x18000cf71  add     rcx, 8
0x18000cf75  call    ?SetCount@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(unsigned __int64,int)
0x18000cf7a  nop
0x18000cf7b  mov     [rbx+28h], r15
0x18000cf7f  mov     [rbx], r15d
0x18000cf82  mov     [rbx+30h], r15d
0x18000cf86  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cf8a  inc     rax
0x18000cf8d  cmp     [rsi+rax*2], r15w
0x18000cf92  jnz     short loc_18000CF8A
0x18000cf94  lea     eax, ds:2[rax*2]
0x18000cf9b  movsxd  rbp, eax
0x18000cf9e  mov     rcx, rbp; Size
0x18000cfa1  call    cs:__imp_malloc
0x18000cfa7  mov     rdi, rax
0x18000cfaa  test    rax, rax
0x18000cfad  jz      loc_18000D07F
0x18000cfb3  mov     r9, rbp; void *
0x18000cfb6  mov     r8, rsi; unsigned __int64
0x18000cfb9  mov     rdx, rbp; void *
0x18000cfbc  mov     rcx, rax; this
0x18000cfbf  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18000cfc4  nop
0x18000cfc5  shr     rbp, 1
0x18000cfc8  movsxd  rdx, ebp; SizeInWords
0x18000cfcb  mov     rcx, rdi; String
0x18000cfce  call    cs:__imp__wcslwr_s
0x18000cfd4  mov     ecx, eax; int
0x18000cfd6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000cfdb  nop
0x18000cfdc  mov     [rsp+48h+arg_8], rdi
0x18000cfe1  mov     edx, 10h
0x18000cfe6  mov     rcx, rbx
0x18000cfe9  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000cfee  movsxd  rbp, eax
0x18000cff1  test    eax, eax
0x18000cff3  js      loc_18000D07F
0x18000cff9  mov     rcx, [rsp+48h+arg_8]
0x18000cffe  cmp     word ptr [rcx], 5Eh ; '^'
0x18000d002  mov     rcx, rbx
0x18000d005  jnz     short loc_18000D01D
0x18000d007  mov     edx, 1Ch
0x18000d00c  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000d011  test    eax, eax
0x18000d013  js      short loc_18000D07F
0x18000d015  add     [rsp+48h+arg_8], 2
0x18000d01b  jmp     short loc_18000D02B
0x18000d01d  mov     edx, 1Dh
0x18000d022  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000d027  test    eax, eax
0x18000d029  js      short loc_18000D07F
0x18000d02b  mov     byte ptr [rsp+48h+arg_10], 1
0x18000d030  lea     r8, [rsp+48h+arg_10]
0x18000d035  lea     rdx, [rsp+48h+arg_8]
0x18000d03a  mov     rcx, rbx
0x18000d03d  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x18000d042  cmp     [rbx], r15d
0x18000d045  jnz     short loc_18000D06D
0x18000d047  mov     rdx, rbp
0x18000d04a  lea     rcx, [rbx+8]
0x18000d04e  call    ??A?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAAAEAUINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](unsigned __int64)
0x18000d053  nop
0x18000d054  mov     qword ptr [rax+8], 2
0x18000d05c  mov     edx, 1Eh
0x18000d061  mov     rcx, rbx
0x18000d064  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000d069  test    eax, eax
0x18000d06b  js      short loc_18000D07F
0x18000d06d  cmp     rdi, rsi
0x18000d070  jz      short loc_18000D07B
0x18000d072  mov     rcx, rdi; Block
0x18000d075  call    cs:__imp_free
0x18000d07b  mov     eax, [rbx]
0x18000d07d  jmp     short loc_18000D084
0x18000d07f  mov     eax, 1
0x18000d084  mov     rbx, [rsp+48h+arg_0]
0x18000d089  add     rsp, 20h
0x18000d08d  pop     r15
0x18000d08f  pop     r14
0x18000d091  pop     rdi
0x18000d092  pop     rsi
0x18000d093  pop     rbp
0x18000d094  retn
```
