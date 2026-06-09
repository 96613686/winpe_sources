# CObjectPathParser::keyref_list(void)

- ea: `0x18001503c`
- end: `0x18001507c`
- name: `?keyref_list@CObjectPathParser@@AEAAHXZ`
- size: `64`
- prototype: `__int64 __fastcall(CObjectPathParser *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001503c`
- `0x180015220`

## callees

- `0x1800147b8`
- `0x180014ef4`
- `0x18001503c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CObjectPathParser::keyref_list(CObjectPathParser *this)
{
  CObjectPathParser *v1; // rbx
  __int64 result; // rax

  while ( 1 )
  {
    v1 = this;
    result = CObjectPathParser::keyref(this);
    if ( (_DWORD)result )
      break;
    if ( *((_DWORD *)v1 + 2) != 109 )
      return 0;
    if ( !(unsigned int)CObjectPathParser::NextToken(v1) )
      return 1;
    this = v1;
  }
  return result;
}

```

## disassembly

```asm
0x18001503c  push    rbx
0x18001503e  sub     rsp, 20h
0x180015042  mov     rbx, rcx
0x180015045  call    ?keyref@CObjectPathParser@@AEAAHXZ; CObjectPathParser::keyref(void)
0x18001504a  test    eax, eax
0x18001504c  jnz     short loc_180015076
0x18001504e  cmp     dword ptr [rbx+8], 6Dh ; 'm'
0x180015052  jnz     short loc_180015074
0x180015054  mov     rcx, rbx; this
0x180015057  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x18001505c  test    eax, eax
0x18001505e  jnz     short loc_180015067
0x180015060  mov     eax, 1
0x180015065  jmp     short loc_180015076
0x180015067  mov     rcx, rbx; this
0x18001506a  add     rsp, 20h
0x18001506e  pop     rbx
0x18001506f  jmp     ?keyref_list@CObjectPathParser@@AEAAHXZ; CObjectPathParser::keyref_list(void)
0x180015074  xor     eax, eax
0x180015076  add     rsp, 20h
0x18001507a  pop     rbx
0x18001507b  retn
```
