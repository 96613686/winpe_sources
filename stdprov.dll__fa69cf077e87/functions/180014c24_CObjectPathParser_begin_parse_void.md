# CObjectPathParser::begin_parse(void)

- ea: `0x180014c24`
- end: `0x180014ce2`
- name: `?begin_parse@CObjectPathParser@@AEAAHXZ`
- size: `190`
- prototype: `__int64 __fastcall(const unsigned __int16 ***this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800147e4`

## callees

- `0x18001474c`
- `0x1800147b8`
- `0x180014c24`
- `0x180015084`
- `0x1800150f0`
- `0x1800151b0`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::begin_parse(const unsigned __int16 ***this)
{
  int v2; // ecx
  __int64 result; // rax
  unsigned __int16 *v4; // rax
  const unsigned __int16 **v5; // rcx

  if ( !(unsigned int)CObjectPathParser::NextToken((CObjectPathParser *)this) )
    return 1;
  if ( *((_DWORD *)this + 2) != 110 )
  {
    if ( *((_DWORD *)this + 2) != 100 )
      goto LABEL_8;
    v4 = Macro_CloneLPWSTR(*this[2]);
    v5 = this[2];
    *this = (const unsigned __int16 **)v4;
    if ( v4 )
    {
      if ( *v5 )
      {
LABEL_16:
        if ( (unsigned int)CObjectPathParser::NextToken((CObjectPathParser *)this) )
          return CObjectPathParser::ns_or_class((CObjectPathParser *)this);
        return 1;
      }
    }
    else if ( !*v5 )
    {
      goto LABEL_16;
    }
    return 3;
  }
  if ( !(unsigned int)CObjectPathParser::NextToken((CObjectPathParser *)this) )
    return 1;
  v2 = *((_DWORD *)this + 2);
  if ( v2 == 110 )
    return 1;
  if ( v2 != 100 )
    return v2 != 0;
  result = CObjectPathParser::ns_list((CObjectPathParser *)this);
  if ( !(_DWORD)result && *((_DWORD *)this + 2) )
  {
LABEL_8:
    if ( *((_DWORD *)this + 2) == 111 && (unsigned int)CObjectPathParser::NextToken((CObjectPathParser *)this) )
      return CObjectPathParser::objref((CObjectPathParser *)this);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180014c24  push    rbx
0x180014c26  sub     rsp, 20h
0x180014c2a  mov     rbx, rcx
0x180014c2d  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180014c32  test    eax, eax
0x180014c34  jz      short loc_180014C78
0x180014c36  cmp     dword ptr [rbx+8], 6Eh ; 'n'
0x180014c3a  jnz     short loc_180014C8C
0x180014c3c  mov     rcx, rbx; this
0x180014c3f  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180014c44  test    eax, eax
0x180014c46  jz      short loc_180014C78
0x180014c48  mov     ecx, [rbx+8]
0x180014c4b  cmp     ecx, 6Eh ; 'n'
0x180014c4e  jz      short loc_180014C78
0x180014c50  cmp     ecx, 64h ; 'd'
0x180014c53  jnz     short loc_180014C83
0x180014c55  mov     rcx, rbx; this
0x180014c58  call    ?ns_list@CObjectPathParser@@AEAAHXZ; CObjectPathParser::ns_list(void)
0x180014c5d  test    eax, eax
0x180014c5f  jnz     short loc_180014C7D
0x180014c61  cmp     [rbx+8], eax
0x180014c64  jz      short loc_180014C7D
0x180014c66  cmp     dword ptr [rbx+8], 6Fh ; 'o'
0x180014c6a  jnz     short loc_180014C78
0x180014c6c  mov     rcx, rbx; this
0x180014c6f  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180014c74  test    eax, eax
0x180014c76  jnz     short loc_180014CD5
0x180014c78  mov     eax, 1
0x180014c7d  add     rsp, 20h
0x180014c81  pop     rbx
0x180014c82  retn
0x180014c83  xor     eax, eax
0x180014c85  test    ecx, ecx
0x180014c87  setnz   al
0x180014c8a  jmp     short loc_180014C7D
0x180014c8c  cmp     dword ptr [rbx+8], 64h ; 'd'
0x180014c90  jnz     short loc_180014C66
0x180014c92  mov     rcx, [rbx+10h]
0x180014c96  mov     rcx, [rcx]; Src
0x180014c99  call    ?Macro_CloneLPWSTR@@YAPEAGPEBG@Z; Macro_CloneLPWSTR(ushort const *)
0x180014c9e  mov     rcx, [rbx+10h]
0x180014ca2  mov     [rbx], rax
0x180014ca5  test    rax, rax
0x180014ca8  jnz     short loc_180014CC8
0x180014caa  cmp     [rcx], rax
0x180014cad  jnz     short loc_180014CCE
0x180014caf  mov     rcx, rbx; this
0x180014cb2  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180014cb7  test    eax, eax
0x180014cb9  jz      short loc_180014C78
0x180014cbb  mov     rcx, rbx; this
0x180014cbe  add     rsp, 20h
0x180014cc2  pop     rbx
0x180014cc3  jmp     ?ns_or_class@CObjectPathParser@@AEAAHXZ; CObjectPathParser::ns_or_class(void)
0x180014cc8  cmp     qword ptr [rcx], 0
0x180014ccc  jnz     short loc_180014CAF
0x180014cce  mov     eax, 3
0x180014cd3  jmp     short loc_180014C7D
0x180014cd5  mov     rcx, rbx; this
0x180014cd8  add     rsp, 20h
0x180014cdc  pop     rbx
0x180014cdd  jmp     ?objref@CObjectPathParser@@AEAAHXZ; CObjectPathParser::objref(void)
```
