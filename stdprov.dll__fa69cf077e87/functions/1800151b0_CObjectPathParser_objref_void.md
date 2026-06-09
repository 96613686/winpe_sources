# CObjectPathParser::objref(void)

- ea: `0x1800151b0`
- end: `0x18001521a`
- name: `?objref@CObjectPathParser@@AEAAHXZ`
- size: `106`
- prototype: `__int64 __fastcall(const unsigned __int16 ***this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180014c24`
- `0x1800150f0`

## callees

- `0x18001474c`
- `0x1800147b8`
- `0x1800151b0`
- `0x180015220`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::objref(const unsigned __int16 ***this)
{
  unsigned __int16 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx

  if ( *((_DWORD *)this + 2) == 100 )
  {
    v2 = Macro_CloneLPWSTR(*this[2]);
    v3 = (__int64)this[3];
    *(_QWORD *)(v3 + 24) = v2;
    v4 = (__int64)*this[2];
    if ( this[3][3] )
    {
      if ( v4 )
      {
LABEL_4:
        if ( CObjectPathParser::NextToken((CGenLexer **)this, v3) )
          return CObjectPathParser::objref_rest((CObjectPathParser *)this);
        return 1;
      }
    }
    else if ( !v4 )
    {
      goto LABEL_4;
    }
    return 3;
  }
  return 1;
}

```

## disassembly

```asm
0x1800151b0  push    rbx
0x1800151b2  sub     rsp, 20h
0x1800151b6  cmp     dword ptr [rcx+8], 64h ; 'd'
0x1800151ba  mov     rbx, rcx
0x1800151bd  jnz     short loc_18001520F
0x1800151bf  mov     rcx, [rcx+10h]
0x1800151c3  mov     rcx, [rcx]; Src
0x1800151c6  call    ?Macro_CloneLPWSTR@@YAPEAGPEBG@Z; Macro_CloneLPWSTR(ushort const *)
0x1800151cb  mov     rdx, [rbx+18h]
0x1800151cf  mov     [rdx+18h], rax
0x1800151d3  mov     rax, [rbx+10h]
0x1800151d7  mov     rcx, [rax]
0x1800151da  mov     rax, [rbx+18h]
0x1800151de  cmp     qword ptr [rax+18h], 0
0x1800151e3  jnz     short loc_180015203
0x1800151e5  test    rcx, rcx
0x1800151e8  jnz     short loc_180015208
0x1800151ea  mov     rcx, rbx; this
0x1800151ed  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x1800151f2  test    eax, eax
0x1800151f4  jz      short loc_18001520F
0x1800151f6  mov     rcx, rbx; this
0x1800151f9  add     rsp, 20h
0x1800151fd  pop     rbx
0x1800151fe  jmp     ?objref_rest@CObjectPathParser@@AEAAHXZ; CObjectPathParser::objref_rest(void)
0x180015203  test    rcx, rcx
0x180015206  jnz     short loc_1800151EA
0x180015208  mov     eax, 3
0x18001520d  jmp     short loc_180015214
0x18001520f  mov     eax, 1
0x180015214  add     rsp, 20h
0x180015218  pop     rbx
0x180015219  retn
```
