# CDavSetParser::CloseSubElement(IXmlReader *)

- ea: `0x1800124f8`
- end: `0x18001260e`
- name: `?CloseSubElement@CDavSetParser@@AEAAJPEAUIXmlReader@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CDavSetParser *this, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800129f0`

## callees

- `0x1800124f8`
- `0x18001eb10`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800125db`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800125db`
- `iisutil!SAFE_snwprintf` at `0x18001259a`
- `iisutil!SAFE_snwprintf` at `0x1800125c4`
- `iisutil!SAFE_snwprintf` at `0x18001259a`
- `iisutil!SAFE_snwprintf` at `0x1800125c4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012532`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012532`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800125e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800125e7`

## pseudocode

```c
__int64 __fastcall CDavSetParser::CloseSubElement(CDavSetParser *this, struct IXmlReader *a2)
{
  int NamespaceAndName; // ebx
  int v5; // eax
  __int64 v6; // rax
  __int64 v8; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int16 *v9; // [rsp+38h] [rbp-11h] BYREF
  unsigned __int16 *v10; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v11[56]; // [rsp+48h] [rbp-1h] BYREF

  v10 = 0;
  v9 = 0;
  v8 = 0;
  STRU::STRU((STRU *)v11);
  NamespaceAndName = XmlGetNamespaceAndName(a2, (const unsigned __int16 **)&v10, (const unsigned __int16 **)&v9);
  if ( NamespaceAndName >= 0 )
  {
    NamespaceAndName = (*(__int64 (__fastcall **)(char *, unsigned __int16 *, __int64 *, __int64))(*((_QWORD *)this + 39)
                                                                                                 + 24LL))(
                         (char *)this + 312,
                         v10,
                         &v8,
                         1);
    if ( NamespaceAndName >= 0 )
    {
      if ( *(_WORD *)(**(__int64 (__fastcall ***)(__int64))v8)(v8) )
      {
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
        v5 = SAFE_snwprintf((struct STRU *)v11, L"</%s:%s>", v6, v9);
      }
      else
      {
        v5 = SAFE_snwprintf((struct STRU *)v11, L"</%s>", v9);
      }
      NamespaceAndName = v5;
      if ( v5 >= 0 )
        NamespaceAndName = STRU::Append((CDavSetParser *)((char *)this + 200), (const struct STRU *)v11);
    }
  }
  STRU::~STRU((STRU *)v11);
  return (unsigned int)NamespaceAndName;
}

```

## disassembly

```asm
0x1800124f8  mov     [rsp-8+arg_10], rbx
0x1800124fd  push    rbp
0x1800124fe  push    rsi
0x1800124ff  push    rdi
0x180012500  lea     rbp, [rsp-47h]
0x180012505  sub     rsp, 90h
0x18001250c  mov     rax, cs:__security_cookie
0x180012513  xor     rax, rsp
0x180012516  mov     [rbp+57h+var_20], rax
0x18001251a  xor     esi, esi
0x18001251c  mov     rdi, rcx
0x18001251f  lea     rcx, [rbp+57h+var_58]
0x180012523  mov     [rbp+57h+var_60], rsi
0x180012527  mov     [rbp+57h+var_68], rsi
0x18001252b  mov     rbx, rdx
0x18001252e  mov     [rbp+57h+var_70], rsi
0x180012532  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012538  lea     r8, [rbp+57h+var_68]; unsigned __int16 **
0x18001253c  mov     rcx, rbx; struct IXmlReader *
0x18001253f  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x180012543  call    ?XmlGetNamespaceAndName@@YAJPEAUIXmlReader@@PEAPEBG1@Z; XmlGetNamespaceAndName(IXmlReader *,ushort const * *,ushort const * *)
0x180012548  mov     ebx, eax
0x18001254a  test    eax, eax
0x18001254c  js      loc_1800125E3
0x180012552  mov     rdx, [rbp+57h+var_60]
0x180012556  lea     rcx, [rdi+138h]
0x18001255d  mov     rax, [rcx]
0x180012560  lea     r9d, [rsi+1]
0x180012564  lea     r8, [rbp+57h+var_70]
0x180012568  mov     rax, [rax+18h]
0x18001256c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012571  mov     ebx, eax
0x180012573  test    eax, eax
0x180012575  js      short loc_1800125E3
0x180012577  mov     rcx, [rbp+57h+var_70]
0x18001257b  mov     rax, [rcx]
0x18001257e  mov     rax, [rax]
0x180012581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012586  cmp     [rax], si
0x180012589  jnz     short loc_1800125A2
0x18001258b  mov     r8, [rbp+57h+var_68]
0x18001258f  lea     rdx, aS; "</%s>"
0x180012596  lea     rcx, [rbp+57h+var_58]
0x18001259a  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800125a0  jmp     short loc_1800125CA
0x1800125a2  mov     rcx, [rbp+57h+var_70]
0x1800125a6  mov     rax, [rcx]
0x1800125a9  mov     rax, [rax+8]
0x1800125ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b2  mov     r9, [rbp+57h+var_68]
0x1800125b6  lea     rdx, aSS_0; "</%s:%s>"
0x1800125bd  mov     r8, rax
0x1800125c0  lea     rcx, [rbp+57h+var_58]
0x1800125c4  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800125ca  mov     ebx, eax
0x1800125cc  test    eax, eax
0x1800125ce  js      short loc_1800125E3
0x1800125d0  lea     rcx, [rdi+0C8h]
0x1800125d7  lea     rdx, [rbp+57h+var_58]
0x1800125db  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800125e1  mov     ebx, eax
0x1800125e3  lea     rcx, [rbp+57h+var_58]
0x1800125e7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800125ed  mov     eax, ebx
0x1800125ef  mov     rcx, [rbp+57h+var_20]
0x1800125f3  xor     rcx, rsp; StackCookie
0x1800125f6  call    __security_check_cookie
0x1800125fb  mov     rbx, [rsp+0A0h+arg_10]
0x180012603  add     rsp, 90h
0x18001260a  pop     rdi
0x18001260b  pop     rsi
0x18001260c  pop     rbp
0x18001260d  retn
```
