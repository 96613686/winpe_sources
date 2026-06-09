# CObjectPathParser::NextToken(void)

- ea: `0x1800147b8`
- end: `0x1800147dd`
- name: `?NextToken@CObjectPathParser@@AEAAHXZ`
- size: `37`
- prototype: `_BOOL8 __fastcall(CGenLexer **this, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180014c24`
- `0x180014d28`
- `0x180014ef4`
- `0x18001503c`
- `0x180015084`
- `0x1800150f0`
- `0x1800151b0`
- `0x180015220`

## callees

- `0x180015374`

## pseudocode

```c
_BOOL8 __fastcall CObjectPathParser::NextToken(CGenLexer **this, __int64 a2)
{
  int Token; // eax

  Token = CGenLexer::NextToken(this[2], a2);
  *((_DWORD *)this + 2) = Token;
  return Token != 1;
}

```

## disassembly

```asm
0x1800147b8  push    rbx
0x1800147ba  sub     rsp, 20h
0x1800147be  mov     rbx, rcx
0x1800147c1  mov     rcx, [rcx+10h]; this
0x1800147c5  call    ?NextToken@CGenLexer@@QEAAHXZ; CGenLexer::NextToken(void)
0x1800147ca  xor     ecx, ecx
0x1800147cc  mov     [rbx+8], eax
0x1800147cf  cmp     eax, 1
0x1800147d2  setnz   cl
0x1800147d5  mov     eax, ecx
0x1800147d7  add     rsp, 20h
0x1800147db  pop     rbx
0x1800147dc  retn
```
