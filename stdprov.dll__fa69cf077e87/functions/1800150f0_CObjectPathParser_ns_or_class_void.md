# CObjectPathParser::ns_or_class(void)

- ea: `0x1800150f0`
- end: `0x1800151a7`
- name: `?ns_or_class@CObjectPathParser@@AEAAHXZ`
- size: `183`
- prototype: `__int64 __fastcall(ParsedObjectPath **this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014c24`

## callees

- `0x18001474c`
- `0x1800147b8`
- `0x180014ce8`
- `0x180015084`
- `0x1800150f0`
- `0x1800151b0`
- `0x180015220`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001518d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001518d`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::ns_or_class(ParsedObjectPath **this)
{
  __int64 result; // rax
  __int64 v3; // rdx
  __int64 v4; // rdx
  ParsedObjectPath *v5; // rcx

  if ( *((_DWORD *)this + 2) != 111 )
  {
    if ( *((_DWORD *)this + 2) == 110 )
    {
      result = CObjectPathParser::ident_becomes_ns(this);
      if ( (_DWORD)result )
        return result;
      if ( CObjectPathParser::NextToken(this, v4) )
      {
        result = CObjectPathParser::ns_list((CObjectPathParser *)this);
        if ( (_DWORD)result || !*((_DWORD *)this + 2) )
          return result;
        if ( *((_DWORD *)this + 2) == 111 )
        {
LABEL_3:
          if ( CObjectPathParser::NextToken(this, v3) )
            return CObjectPathParser::objref((CObjectPathParser *)this);
        }
      }
      return 1;
    }
    *((_QWORD *)this[3] + 3) = Macro_CloneLPWSTR((const unsigned __int16 *)*this);
    v5 = *this;
    if ( *((_QWORD *)this[3] + 3) )
    {
      if ( !v5 )
        return 3;
    }
    else if ( v5 )
    {
      return 3;
    }
    CWin32DefaultArena::WbemMemFree(v5);
    *this = 0;
    return CObjectPathParser::objref_rest((CObjectPathParser *)this);
  }
  result = CObjectPathParser::ident_becomes_ns(this);
  if ( !(_DWORD)result )
    goto LABEL_3;
  return result;
}

```

## disassembly

```asm
0x1800150f0  push    rbx
0x1800150f2  sub     rsp, 20h
0x1800150f6  cmp     dword ptr [rcx+8], 6Fh ; 'o'
0x1800150fa  mov     rbx, rcx
0x1800150fd  jnz     short loc_180015121
0x1800150ff  call    ?ident_becomes_ns@CObjectPathParser@@AEAAHXZ; CObjectPathParser::ident_becomes_ns(void)
0x180015104  test    eax, eax
0x180015106  jnz     short loc_180015182
0x180015108  mov     rcx, rbx; this
0x18001510b  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180015110  test    eax, eax
0x180015112  jz      short loc_180015153
0x180015114  mov     rcx, rbx; this
0x180015117  add     rsp, 20h
0x18001511b  pop     rbx
0x18001511c  jmp     ?objref@CObjectPathParser@@AEAAHXZ; CObjectPathParser::objref(void)
0x180015121  cmp     dword ptr [rcx+8], 6Eh ; 'n'
0x180015125  jnz     short loc_18001515A
0x180015127  call    ?ident_becomes_ns@CObjectPathParser@@AEAAHXZ; CObjectPathParser::ident_becomes_ns(void)
0x18001512c  test    eax, eax
0x18001512e  jnz     short loc_180015182
0x180015130  mov     rcx, rbx; this
0x180015133  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180015138  test    eax, eax
0x18001513a  jz      short loc_180015153
0x18001513c  mov     rcx, rbx; this
0x18001513f  call    ?ns_list@CObjectPathParser@@AEAAHXZ; CObjectPathParser::ns_list(void)
0x180015144  test    eax, eax
0x180015146  jnz     short loc_180015182
0x180015148  cmp     [rbx+8], eax
0x18001514b  jz      short loc_180015182
0x18001514d  cmp     dword ptr [rbx+8], 6Fh ; 'o'
0x180015151  jz      short loc_180015108
0x180015153  mov     eax, 1
0x180015158  jmp     short loc_180015182
0x18001515a  mov     rcx, [rcx]; Src
0x18001515d  call    ?Macro_CloneLPWSTR@@YAPEAGPEBG@Z; Macro_CloneLPWSTR(ushort const *)
0x180015162  mov     rcx, [rbx+18h]
0x180015166  mov     [rcx+18h], rax
0x18001516a  mov     rax, [rbx+18h]
0x18001516e  mov     rcx, [rbx]
0x180015171  cmp     qword ptr [rax+18h], 0
0x180015176  jnz     short loc_180015188
0x180015178  test    rcx, rcx
0x18001517b  jz      short loc_18001518D
0x18001517d  mov     eax, 3
0x180015182  add     rsp, 20h
0x180015186  pop     rbx
0x180015187  retn
0x180015188  test    rcx, rcx
0x18001518b  jz      short loc_18001517D
0x18001518d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180015193  mov     rcx, rbx; this
0x180015196  mov     qword ptr [rbx], 0
0x18001519d  add     rsp, 20h
0x1800151a1  pop     rbx
0x1800151a2  jmp     ?objref_rest@CObjectPathParser@@AEAAHXZ; CObjectPathParser::objref_rest(void)
```
