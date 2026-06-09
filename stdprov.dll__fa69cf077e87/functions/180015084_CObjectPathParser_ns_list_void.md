# CObjectPathParser::ns_list(void)

- ea: `0x180015084`
- end: `0x1800150e8`
- name: `?ns_list@CObjectPathParser@@AEAAHXZ`
- size: `100`
- prototype: `__int64 __fastcall(CObjectPathParser *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180014c24`
- `0x180015084`
- `0x1800150f0`

## callees

- `0x180014660`
- `0x1800147b8`
- `0x180015084`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::ns_list(CObjectPathParser *this)
{
  CObjectPathParser *v1; // rbx
  __int64 v2; // rdx
  __int64 v4; // rdx

  while ( 1 )
  {
    v1 = this;
    if ( *((_DWORD *)this + 2) != 100 )
      break;
    if ( !(unsigned int)ParsedObjectPath::AddNamespace(
                          *((ParsedObjectPath **)this + 3),
                          **((const unsigned __int16 ***)this + 2)) )
      return 3;
    if ( !CObjectPathParser::NextToken((CGenLexer **)v1, v2) )
      break;
    if ( *((_DWORD *)v1 + 2) != 110 )
      return 0;
    if ( !CObjectPathParser::NextToken((CGenLexer **)v1, v4) )
      break;
    this = v1;
  }
  return 1;
}

```

## disassembly

```asm
0x180015084  push    rbx
0x180015086  sub     rsp, 20h
0x18001508a  cmp     dword ptr [rcx+8], 64h ; 'd'
0x18001508e  mov     rbx, rcx
0x180015091  jnz     short loc_1800150DD
0x180015093  mov     rdx, [rcx+10h]
0x180015097  mov     rcx, [rcx+18h]; this
0x18001509b  mov     rdx, [rdx]; unsigned __int16 *
0x18001509e  call    ?AddNamespace@ParsedObjectPath@@QEAAHPEBG@Z; ParsedObjectPath::AddNamespace(ushort const *)
0x1800150a3  test    eax, eax
0x1800150a5  jnz     short loc_1800150AE
0x1800150a7  mov     eax, 3
0x1800150ac  jmp     short loc_1800150E2
0x1800150ae  mov     rcx, rbx; this
0x1800150b1  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x1800150b6  test    eax, eax
0x1800150b8  jz      short loc_1800150DD
0x1800150ba  cmp     dword ptr [rbx+8], 6Eh ; 'n'
0x1800150be  jnz     short loc_1800150D9
0x1800150c0  mov     rcx, rbx; this
0x1800150c3  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x1800150c8  test    eax, eax
0x1800150ca  jz      short loc_1800150DD
0x1800150cc  mov     rcx, rbx; this
0x1800150cf  add     rsp, 20h
0x1800150d3  pop     rbx
0x1800150d4  jmp     ?ns_list@CObjectPathParser@@AEAAHXZ; CObjectPathParser::ns_list(void)
0x1800150d9  xor     eax, eax
0x1800150db  jmp     short loc_1800150E2
0x1800150dd  mov     eax, 1
0x1800150e2  add     rsp, 20h
0x1800150e6  pop     rbx
0x1800150e7  retn
```
