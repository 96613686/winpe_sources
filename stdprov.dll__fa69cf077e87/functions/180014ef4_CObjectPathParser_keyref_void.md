# CObjectPathParser::keyref(void)

- ea: `0x180014ef4`
- end: `0x180015034`
- name: `?keyref@CObjectPathParser@@AEAAHXZ`
- size: `320`
- prototype: `__int64 __fastcall(CObjectPathParser *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001503c`

## callees

- `0x180014588`
- `0x1800145d8`
- `0x18001474c`
- `0x1800147b8`
- `0x180014d28`
- `0x180014ef4`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014f06`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014f06`
- `OLEAUT32!__imp_VariantInit` at `0x180014f24`
- `OLEAUT32!__imp_VariantInit` at `0x180014f24`

## pseudocode

```c
__int64 __fastcall CObjectPathParser::keyref(CObjectPathParser *this)
{
  char *v2; // rax
  char *v3; // rbx
  __int64 v5; // rcx
  KeyRef *v6; // rcx
  unsigned int v7; // ebx
  KeyRef *v8; // rcx
  KeyRef *v9; // rcx
  struct KeyRef *v10; // rdx
  KeyRef *v11; // rcx

  v2 = (char *)CWin32DefaultArena::WbemMemAlloc(0x28u);
  v3 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = 0;
    VariantInit((VARIANTARG *)(v2 + 8));
    *((_DWORD *)v3 + 8) = 0;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 4) = v3;
  if ( !v3 )
    return 3;
  if ( *((_DWORD *)this + 2) != 100 )
    goto LABEL_13;
  **((_QWORD **)this + 4) = Macro_CloneLPWSTR(**((const unsigned __int16 ***)this + 2));
  v5 = **((_QWORD **)this + 2);
  if ( !**((_QWORD **)this + 4) )
  {
    if ( !v5 )
      goto LABEL_9;
LABEL_17:
    v7 = 3;
LABEL_14:
    v8 = (KeyRef *)*((_QWORD *)this + 4);
    if ( v8 )
      goto LABEL_26;
    goto LABEL_32;
  }
  if ( !v5 )
    goto LABEL_17;
LABEL_9:
  if ( !(unsigned int)CObjectPathParser::NextToken(this) )
  {
    v6 = (KeyRef *)*((_QWORD *)this + 4);
    if ( v6 )
      KeyRef::`scalar deleting destructor'(v6);
    *((_QWORD *)this + 4) = 0;
LABEL_13:
    v7 = 1;
    goto LABEL_14;
  }
  if ( *((_DWORD *)this + 2) != 104 || !(unsigned int)CObjectPathParser::NextToken(this) )
  {
    v9 = (KeyRef *)*((_QWORD *)this + 4);
    if ( v9 )
      KeyRef::`scalar deleting destructor'(v9);
    v7 = 1;
    goto LABEL_32;
  }
  v7 = CObjectPathParser::key_const(this);
  v10 = (struct KeyRef *)*((_QWORD *)this + 4);
  if ( !v7 )
  {
    if ( (unsigned int)ParsedObjectPath::AddKeyRef(*((ParsedObjectPath **)this + 3), v10) )
    {
      v7 = 0;
    }
    else
    {
      v11 = (KeyRef *)*((_QWORD *)this + 4);
      if ( v11 )
        KeyRef::`scalar deleting destructor'(v11);
      v7 = 3;
    }
    goto LABEL_32;
  }
  if ( v10 )
  {
    v8 = (KeyRef *)*((_QWORD *)this + 4);
LABEL_26:
    KeyRef::`scalar deleting destructor'(v8);
  }
LABEL_32:
  *((_QWORD *)this + 4) = 0;
  return v7;
}

```

## disassembly

```asm
0x180014ef4  mov     [rsp+arg_8], rbx
0x180014ef9  push    rdi
0x180014efa  sub     rsp, 20h
0x180014efe  mov     rdi, rcx
0x180014f01  mov     ecx, 28h ; '('
0x180014f06  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014f0c  mov     rbx, rax
0x180014f0f  mov     [rsp+28h+arg_0], rax
0x180014f14  test    rax, rax
0x180014f17  jz      short loc_180014F33
0x180014f19  mov     qword ptr [rax], 0
0x180014f20  lea     rcx, [rax+8]; pvarg
0x180014f24  call    cs:__imp_VariantInit
0x180014f2a  mov     dword ptr [rbx+20h], 0
0x180014f31  jmp     short loc_180014F35
0x180014f33  xor     ebx, ebx
0x180014f35  mov     [rdi+20h], rbx
0x180014f39  test    rbx, rbx
0x180014f3c  jnz     short loc_180014F46
0x180014f3e  lea     eax, [rbx+3]
0x180014f41  jmp     loc_180015029
0x180014f46  cmp     dword ptr [rdi+8], 64h ; 'd'
0x180014f4a  jnz     short loc_180014F97
0x180014f4c  mov     rcx, [rdi+10h]
0x180014f50  mov     rcx, [rcx]; Src
0x180014f53  call    ?Macro_CloneLPWSTR@@YAPEAGPEBG@Z; Macro_CloneLPWSTR(ushort const *)
0x180014f58  mov     rcx, [rdi+20h]
0x180014f5c  mov     [rcx], rax
0x180014f5f  mov     rax, [rdi+10h]
0x180014f63  mov     rcx, [rax]
0x180014f66  mov     rax, [rdi+20h]
0x180014f6a  cmp     qword ptr [rax], 0
0x180014f6e  jnz     short loc_180014FA7
0x180014f70  test    rcx, rcx
0x180014f73  jnz     short loc_180014FAC
0x180014f75  mov     rcx, rdi; this
0x180014f78  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180014f7d  test    eax, eax
0x180014f7f  jnz     short loc_180014FB3
0x180014f81  mov     rcx, [rdi+20h]; this
0x180014f85  test    rcx, rcx
0x180014f88  jz      short loc_180014F8F
0x180014f8a  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x180014f8f  mov     qword ptr [rdi+20h], 0
0x180014f97  mov     ebx, 1
0x180014f9c  mov     rcx, [rdi+20h]
0x180014fa0  test    rcx, rcx
0x180014fa3  jz      short loc_18001501F
0x180014fa5  jmp     short loc_180014FF4
0x180014fa7  test    rcx, rcx
0x180014faa  jnz     short loc_180014F75
0x180014fac  mov     ebx, 3
0x180014fb1  jmp     short loc_180014F9C
0x180014fb3  cmp     dword ptr [rdi+8], 68h ; 'h'
0x180014fb7  jnz     short loc_180014FC5
0x180014fb9  mov     rcx, rdi; this
0x180014fbc  call    ?NextToken@CObjectPathParser@@AEAAHXZ; CObjectPathParser::NextToken(void)
0x180014fc1  test    eax, eax
0x180014fc3  jnz     short loc_180014FDA
0x180014fc5  mov     rcx, [rdi+20h]; this
0x180014fc9  test    rcx, rcx
0x180014fcc  jz      short loc_180014FD3
0x180014fce  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x180014fd3  mov     ebx, 1
0x180014fd8  jmp     short loc_18001501F
0x180014fda  mov     rcx, rdi; this
0x180014fdd  call    ?key_const@CObjectPathParser@@AEAAHXZ; CObjectPathParser::key_const(void)
0x180014fe2  mov     ebx, eax
0x180014fe4  mov     rdx, [rdi+20h]; struct KeyRef *
0x180014fe8  test    eax, eax
0x180014fea  jz      short loc_180014FFB
0x180014fec  test    rdx, rdx
0x180014fef  jz      short loc_18001501F
0x180014ff1  mov     rcx, rdx; this
0x180014ff4  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x180014ff9  jmp     short loc_18001501F
0x180014ffb  mov     rcx, [rdi+18h]; this
0x180014fff  call    ?AddKeyRef@ParsedObjectPath@@QEAAHPEAUKeyRef@@@Z; ParsedObjectPath::AddKeyRef(KeyRef *)
0x180015004  test    eax, eax
0x180015006  jnz     short loc_18001501D
0x180015008  mov     rcx, [rdi+20h]; this
0x18001500c  test    rcx, rcx
0x18001500f  jz      short loc_180015016
0x180015011  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x180015016  mov     ebx, 3
0x18001501b  jmp     short loc_18001501F
0x18001501d  xor     ebx, ebx
0x18001501f  mov     qword ptr [rdi+20h], 0
0x180015027  mov     eax, ebx
0x180015029  mov     rbx, [rsp+28h+arg_8]
0x18001502e  add     rsp, 20h
0x180015032  pop     rdi
0x180015033  retn
```
