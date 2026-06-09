# CObjectPathParser::objref_rest(void)

- ea: `0x180015220`
- end: `0x180015341`
- name: `?objref_rest@CObjectPathParser@@AEAAHXZ`
- size: `289`
- prototype: `__int64 __fastcall(CObjectPathParser *this, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800150f0`
- `0x1800151b0`

## callees

- `0x180014588`
- `0x1800145d8`
- `0x1800147b8`
- `0x180014d28`
- `0x18001503c`
- `0x180015220`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001527d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001527d`
- `OLEAUT32!__imp_VariantInit` at `0x18001529b`
- `OLEAUT32!__imp_VariantInit` at `0x18001529b`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::objref_rest(CObjectPathParser *this, __int64 a2)
{
  __int64 v3; // rdx
  char *v5; // rax
  char *v6; // rsi
  unsigned int v7; // esi
  struct KeyRef *v8; // rdx
  KeyRef *v9; // rcx

  if ( *((_DWORD *)this + 2) != 104 )
  {
    if ( *((_DWORD *)this + 2) != 105 )
      return 0;
    if ( CObjectPathParser::NextToken((CGenLexer **)this, a2) )
      return CObjectPathParser::keyref_list(this);
    return 1;
  }
  if ( !CObjectPathParser::NextToken((CGenLexer **)this, a2) )
    return 1;
  if ( *((_DWORD *)this + 2) == 108 )
  {
    if ( !CObjectPathParser::NextToken((CGenLexer **)this, v3) || !*((_DWORD *)this + 2) )
    {
      *(_DWORD *)(*((_QWORD *)this + 3) + 48LL) = 1;
      return 0;
    }
    return 1;
  }
  v5 = (char *)CWin32DefaultArena::WbemMemAlloc(0x28u);
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = 0;
    VariantInit((VARIANTARG *)(v5 + 8));
    *((_DWORD *)v6 + 8) = 0;
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 4) = v6;
  if ( !v6 )
    return 3;
  v7 = CObjectPathParser::key_const(this);
  v8 = (struct KeyRef *)*((_QWORD *)this + 4);
  if ( v7 )
  {
    if ( v8 )
      KeyRef::`scalar deleting destructor'(*((KeyRef **)this + 4));
  }
  else
  {
    if ( (unsigned int)ParsedObjectPath::AddKeyRef(*((ParsedObjectPath **)this + 3), v8) )
    {
      *((_QWORD *)this + 4) = 0;
      return 0;
    }
    v9 = (KeyRef *)*((_QWORD *)this + 4);
    if ( v9 )
      KeyRef::`scalar deleting destructor'(v9);
    v7 = 3;
  }
  *((_QWORD *)this + 4) = 0;
  return v7;
}

```

## disassembly

```asm
0x180015220  mov     [rsp+arg_8], rsi
0x180015225  push    rdi
0x180015226  sub     rsp, 20h
0x18001522a  mov     rdi, rcx
0x18001522d  cmp     dword ptr [rcx+8], 68h ; 'h'
0x180015231  jnz     loc_180015317
0x180015237  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x18001523c  test    eax, eax
0x18001523e  jz      loc_18001532A
0x180015244  cmp     dword ptr [rdi+8], 6Ch ; 'l'
0x180015248  jnz     short loc_180015278
0x18001524a  mov     rcx, rdi; this
0x18001524d  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180015252  test    eax, eax
0x180015254  jz      short loc_180015260
0x180015256  cmp     dword ptr [rdi+8], 0
0x18001525a  jnz     loc_18001532A
0x180015260  mov     rax, [rdi+18h]
0x180015264  mov     dword ptr [rax+30h], 1
0x18001526b  xor     eax, eax
0x18001526d  mov     rsi, [rsp+28h+arg_8]
0x180015272  add     rsp, 20h
0x180015276  pop     rdi
0x180015277  retn
0x180015278  mov     ecx, 28h ; '('
0x18001527d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015283  mov     rsi, rax
0x180015286  mov     [rsp+28h+arg_0], rax
0x18001528b  test    rax, rax
0x18001528e  jz      short loc_1800152AA
0x180015290  mov     qword ptr [rax], 0
0x180015297  lea     rcx, [rax+8]; pvarg
0x18001529b  call    cs:__imp_VariantInit
0x1800152a1  mov     dword ptr [rsi+20h], 0
0x1800152a8  jmp     short loc_1800152AC
0x1800152aa  xor     esi, esi
0x1800152ac  mov     [rdi+20h], rsi
0x1800152b0  test    rsi, rsi
0x1800152b3  jnz     short loc_1800152BA
0x1800152b5  lea     eax, [rsi+3]
0x1800152b8  jmp     short loc_18001526D
0x1800152ba  mov     rcx, rdi; this
0x1800152bd  call    ?key_const@CObjectPathParser@@AEAAHXZ; CObjectPathParser::key_const(void)
0x1800152c2  mov     esi, eax
0x1800152c4  mov     rdx, [rdi+20h]; struct KeyRef *
0x1800152c8  test    eax, eax
0x1800152ca  jz      short loc_1800152DB
0x1800152cc  test    rdx, rdx
0x1800152cf  jz      short loc_1800152FB
0x1800152d1  mov     rcx, rdx; this
0x1800152d4  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x1800152d9  jmp     short loc_1800152FB
0x1800152db  mov     rcx, [rdi+18h]; this
0x1800152df  call    ?AddKeyRef@ParsedObjectPath@@QEAAHPEAUKeyRef@@@Z; ParsedObjectPath::AddKeyRef(KeyRef *)
0x1800152e4  test    eax, eax
0x1800152e6  jnz     short loc_18001530A
0x1800152e8  mov     rcx, [rdi+20h]; this
0x1800152ec  test    rcx, rcx
0x1800152ef  jz      short loc_1800152F6
0x1800152f1  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x1800152f6  mov     esi, 3
0x1800152fb  mov     qword ptr [rdi+20h], 0
0x180015303  mov     eax, esi
0x180015305  jmp     loc_18001526D
0x18001530a  mov     qword ptr [rdi+20h], 0
0x180015312  jmp     loc_18001526B
0x180015317  cmp     dword ptr [rcx+8], 69h ; 'i'
0x18001531b  jnz     loc_18001526B
0x180015321  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180015326  test    eax, eax
0x180015328  jnz     short loc_180015334
0x18001532a  mov     eax, 1
0x18001532f  jmp     loc_18001526D
0x180015334  mov     rcx, rdi; this
0x180015337  call    ?keyref_list@CObjectPathParser@@AEAAHXZ; CObjectPathParser::keyref_list(void)
0x18001533c  jmp     loc_18001526D
```
