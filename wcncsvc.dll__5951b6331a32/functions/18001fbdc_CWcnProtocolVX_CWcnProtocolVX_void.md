# CWcnProtocolVX::~CWcnProtocolVX(void)

- ea: `0x18001fbdc`
- end: `0x18001fdd5`
- name: `??1CWcnProtocolVX@@UEAA@XZ`
- size: `505`
- prototype: `void __fastcall(CWcnProtocolVX *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002e04`
- `0x18001ff20`
- `0x18005733c`
- `0x180057355`
- `0x18005736e`
- `0x180057387`

## callees

- `0x180004fb8`
- `0x18000d998`
- `0x18001e490`
- `0x18001fbdc`
- `0x180028674`
- `0x18002a848`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001fcb3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd31`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd52`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd88`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fda3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fcb3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd31`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd52`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd88`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fda3`

## pseudocode

```c
void __fastcall CWcnProtocolVX::~CWcnProtocolVX(CWcnProtocolVX *this)
{
  _BYTE *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  const char *v5; // rax
  __int64 v6; // r10
  __int64 *v7; // rdi
  __int64 *v8; // rbx
  void *v9; // rbp
  __int64 *i; // rax
  __int64 *v11; // rcx
  _QWORD **v12; // rbp
  _QWORD **j; // rbx
  _QWORD *v14; // rdi
  void *v15; // rcx
  void **v16; // rdi
  void **k; // rbx
  void *v18; // rcx
  void *v19; // rcx

  *(_QWORD *)this = &CWcnProtocolVX::`vftable';
  if ( *((_BYTE *)this + 156) )
  {
    CWcnParserVX::Shutdown();
    *((_BYTE *)this + 156) = 0;
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_7;
    Indent = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 10, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids, Indent);
  }
  v2 = WPP_GLOBAL_Control;
LABEL_7:
  if ( *((_BYTE *)this + 157) )
  {
    CWcnGeneratorVX::Shutdown();
    *((_BYTE *)this + 157) = 0;
  }
  else if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 3u )
  {
    v5 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 11, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids, v5);
  }
  v7 = (__int64 *)*((_QWORD *)this + 3);
  v8 = (__int64 *)*v7;
  while ( v8 != v7 )
  {
    v9 = (void *)v8[5];
    if ( v9 )
    {
      CWcnMessage::Clear((CWcnMessage *)v8[5]);
      operator delete(v9);
    }
    if ( !*((_BYTE *)v8 + 25) )
    {
      i = (__int64 *)v8[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v8[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v8 = i;
LABEL_25:
        v8 = i;
      }
      else
      {
        v11 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_25;
        do
        {
          v8 = v11;
          v11 = (__int64 *)*v11;
        }
        while ( !*((_BYTE *)v11 + 25) );
      }
    }
  }
  v12 = (_QWORD **)*((_QWORD *)this + 6);
  for ( j = (_QWORD **)*((_QWORD *)this + 5); j != v12; ++j )
  {
    v14 = *j;
    if ( *j )
    {
      v15 = (void *)v14[2];
      if ( v15 )
      {
        operator delete(v15);
        v14[2] = 0;
        v14[3] = 0;
        v14[4] = 0;
      }
      operator delete(v14);
    }
  }
  v16 = (void **)*((_QWORD *)this + 9);
  for ( k = (void **)*((_QWORD *)this + 8); k != v16; ++k )
  {
    if ( *k )
      operator delete(*k);
  }
  std::_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>((char *)this + 136);
  std::_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>((char *)this + 120);
  std::_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>((char *)this + 104);
  v18 = (void *)*((_QWORD *)this + 8);
  if ( v18 )
  {
    operator delete(v18);
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
  }
  v19 = (void *)*((_QWORD *)this + 5);
  if ( v19 )
  {
    operator delete(v19);
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
  }
  std::_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>((char *)this + 24);
  *(_QWORD *)this = &IWcnProtocol::`vftable';
}

```

## disassembly

```asm
0x18001fbdc  push    rbx
0x18001fbde  push    rbp
0x18001fbdf  push    rsi
0x18001fbe0  push    rdi
0x18001fbe1  push    r14
0x18001fbe3  push    r15
0x18001fbe5  sub     rsp, 28h
0x18001fbe9  mov     rsi, rcx
0x18001fbec  lea     rax, ??_7CWcnProtocolVX@@6B@; const CWcnProtocolVX::`vftable'
0x18001fbf3  mov     [rcx], rax
0x18001fbf6  lea     rbx, WPP_GLOBAL_Control
0x18001fbfd  xor     r15d, r15d
0x18001fc00  cmp     [rcx+9Ch], r15b
0x18001fc07  jz      short loc_18001FC17
0x18001fc09  call    ?Shutdown@CWcnParserVX@@SAXXZ; CWcnParserVX::Shutdown(void)
0x18001fc0e  mov     [rsi+9Ch], r15b
0x18001fc15  jmp     short loc_18001FC49
0x18001fc17  mov     r10, cs:WPP_GLOBAL_Control
0x18001fc1e  cmp     r10, rbx
0x18001fc21  jz      short loc_18001FC50
0x18001fc23  cmp     byte ptr [r10+19h], 3
0x18001fc28  jb      short loc_18001FC50
0x18001fc2a  xor     ecx, ecx; int
0x18001fc2c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001fc31  mov     edx, 0Ah
0x18001fc36  mov     r9, rax
0x18001fc39  lea     r8, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids
0x18001fc40  mov     rcx, [r10+10h]
0x18001fc44  call    WPP_SF_s
0x18001fc49  mov     r10, cs:WPP_GLOBAL_Control
0x18001fc50  cmp     [rsi+9Dh], r15b
0x18001fc57  jz      short loc_18001FC67
0x18001fc59  call    ?Shutdown@CWcnGeneratorVX@@SAXXZ; CWcnGeneratorVX::Shutdown(void)
0x18001fc5e  mov     [rsi+9Dh], r15b
0x18001fc65  jmp     short loc_18001FC92
0x18001fc67  cmp     r10, rbx
0x18001fc6a  jz      short loc_18001FC92
0x18001fc6c  cmp     byte ptr [r10+19h], 3
0x18001fc71  jb      short loc_18001FC92
0x18001fc73  xor     ecx, ecx; int
0x18001fc75  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001fc7a  mov     edx, 0Bh
0x18001fc7f  mov     r9, rax
0x18001fc82  lea     r8, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids
0x18001fc89  mov     rcx, [r10+10h]
0x18001fc8d  call    WPP_SF_s
0x18001fc92  mov     rdi, [rsi+18h]
0x18001fc96  mov     rbx, [rdi]
0x18001fc99  cmp     rbx, rdi
0x18001fc9c  jz      short loc_18001FD01
0x18001fc9e  mov     rbp, [rbx+28h]
0x18001fca2  test    rbp, rbp
0x18001fca5  jz      short loc_18001FCB9
0x18001fca7  mov     rcx, rbp; this
0x18001fcaa  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18001fcaf  nop
0x18001fcb0  mov     rcx, rbp
0x18001fcb3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fcb9  cmp     [rbx+19h], r15b
0x18001fcbd  jnz     short loc_18001FC99
0x18001fcbf  mov     rax, [rbx+10h]
0x18001fcc3  cmp     [rax+19h], r15b
0x18001fcc7  jnz     short loc_18001FCE3
0x18001fcc9  mov     rcx, [rax]
0x18001fccc  cmp     [rcx+19h], r15b
0x18001fcd0  jnz     short loc_18001FCFC
0x18001fcd2  mov     rbx, rcx
0x18001fcd5  mov     rax, [rcx]
0x18001fcd8  mov     rcx, rax
0x18001fcdb  cmp     [rax+19h], r15b
0x18001fcdf  jz      short loc_18001FCD2
0x18001fce1  jmp     short loc_18001FC99
0x18001fce3  mov     rax, [rbx+8]
0x18001fce7  jmp     short loc_18001FCF6
0x18001fce9  cmp     rbx, [rax+10h]
0x18001fced  jnz     short loc_18001FCFC
0x18001fcef  mov     rbx, rax
0x18001fcf2  mov     rax, [rax+8]
0x18001fcf6  cmp     [rax+19h], r15b
0x18001fcfa  jz      short loc_18001FCE9
0x18001fcfc  mov     rbx, rax
0x18001fcff  jmp     short loc_18001FC99
0x18001fd01  mov     rbp, [rsi+30h]
0x18001fd05  mov     rbx, [rsi+28h]
0x18001fd09  jmp     short loc_18001FD3B
0x18001fd0b  mov     rdi, [rbx]
0x18001fd0e  test    rdi, rdi
0x18001fd11  jz      short loc_18001FD37
0x18001fd13  mov     rcx, [rdi+10h]
0x18001fd17  test    rcx, rcx
0x18001fd1a  jz      short loc_18001FD2E
0x18001fd1c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd22  mov     [rdi+10h], r15
0x18001fd26  mov     [rdi+18h], r15
0x18001fd2a  mov     [rdi+20h], r15
0x18001fd2e  mov     rcx, rdi
0x18001fd31  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd37  add     rbx, 8
0x18001fd3b  cmp     rbx, rbp
0x18001fd3e  jnz     short loc_18001FD0B
0x18001fd40  mov     rdi, [rsi+48h]
0x18001fd44  mov     rbx, [rsi+40h]
0x18001fd48  jmp     short loc_18001FD5C
0x18001fd4a  mov     rcx, [rbx]
0x18001fd4d  test    rcx, rcx
0x18001fd50  jz      short loc_18001FD58
0x18001fd52  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd58  add     rbx, 8
0x18001fd5c  cmp     rbx, rdi
0x18001fd5f  jnz     short loc_18001FD4A
0x18001fd61  lea     rcx, [rsi+88h]
0x18001fd68  call    ??1?$_Tree@V?$_Tmap_traits@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>(void)
0x18001fd6d  lea     rcx, [rsi+78h]
0x18001fd71  call    ??1?$_Tree@V?$_Tmap_traits@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>(void)
0x18001fd76  lea     rcx, [rsi+68h]
0x18001fd7a  call    ??1?$_Tree@V?$_Tmap_traits@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>(void)
0x18001fd7f  mov     rcx, [rsi+40h]
0x18001fd83  test    rcx, rcx
0x18001fd86  jz      short loc_18001FD9A
0x18001fd88  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd8e  mov     [rsi+40h], r15
0x18001fd92  mov     [rsi+48h], r15
0x18001fd96  mov     [rsi+50h], r15
0x18001fd9a  mov     rcx, [rsi+28h]
0x18001fd9e  test    rcx, rcx
0x18001fda1  jz      short loc_18001FDB5
0x18001fda3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fda9  mov     [rsi+28h], r15
0x18001fdad  mov     [rsi+30h], r15
0x18001fdb1  mov     [rsi+38h], r15
0x18001fdb5  lea     rcx, [rsi+18h]
0x18001fdb9  call    ??1?$_Tree@V?$_Tmap_traits@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>(void)
0x18001fdbe  lea     rax, ??_7IWcnProtocol@@6B@; const IWcnProtocol::`vftable'
0x18001fdc5  mov     [rsi], rax
0x18001fdc8  add     rsp, 28h
0x18001fdcc  pop     r15
0x18001fdce  pop     r14
0x18001fdd0  pop     rdi
0x18001fdd1  pop     rsi
0x18001fdd2  pop     rbp
0x18001fdd3  pop     rbx
0x18001fdd4  retn
```
