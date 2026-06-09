# CWcnMessage::SetWfaVendorExtensionSubMessage(tagWCN_MESSAGE_RULE const *,unsigned __int64)

- ea: `0x18001f10c`
- end: `0x18001f29e`
- name: `?SetWfaVendorExtensionSubMessage@CWcnMessage@@QEAAJPEBUtagWCN_MESSAGE_RULE@@_K@Z`
- size: `402`
- prototype: `__int64 __fastcall(CWcnMessage *__hidden this, const struct tagWCN_MESSAGE_RULE *, unsigned __int64)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18003dfb0`
- `0x180045958`
- `0x180045bc0`
- `0x18004af24`
- `0x18004b180`
- `0x18004ddb0`

## callees

- `0x180001404`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18001e490`
- `0x18001e828`
- `0x18001f10c`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001f1f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f1f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWcnMessage::SetWfaVendorExtensionSubMessage(
        CWcnMessage *this,
        const struct tagWCN_MESSAGE_RULE *a2,
        __int64 a3)
{
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  CWcnMessage *v10; // rdi
  _DWORD *v11; // rax
  int v12; // eax
  int v13; // edi
  _BYTE *v14; // r10
  unsigned int v15; // eax
  __int64 v16; // r10
  __int64 v17; // rax
  std::bad_alloc *v18; // [rsp+30h] [rbp-28h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 35, WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    try
    {
      v10 = (CWcnMessage *)*((_QWORD *)this + 6);
      v11 = operator new(0x38u);
      if ( v11 )
      {
        v11[4] = 8;
        *((_QWORD *)v11 + 3) = 0;
        *((_BYTE *)v11 + 36) = 0;
        *((_QWORD *)v11 + 5) = 0;
        *((_QWORD *)v11 + 6) = 0;
        *(_QWORD *)v11 = 0;
      }
    }
    catch ( std::bad_alloc *v18 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v18 + 8LL))(v18);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids, v17);
      }
      v13 = -2147024882;
      goto LABEL_17;
    }
    *((_QWORD *)this + 6) = v11;
    if ( v10 )
    {
      CWcnMessage::Clear(v10);
      operator delete(v10);
    }
    v12 = CWcnMessage::Init(*((_QWORD *)this + 6), 9, (__int64)a2, a3);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)v13;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_18:
        if ( v14 != (_BYTE *)&WPP_GLOBAL_Control && (v13 < 0 || v14[25] >= 6u) )
        {
          v15 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v16 + 16), 39, (unsigned int)WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids, v15, v13);
        }
        return (unsigned int)v13;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids,
        (unsigned int)v12);
    }
LABEL_17:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
    WPP_SF_s(v6[2], 36, WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids, "pRules");
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001f10c  mov     [rsp+arg_0], rsi
0x18001f111  mov     [rsp+arg_10], rdi
0x18001f116  push    r12
0x18001f118  push    r14
0x18001f11a  push    r15
0x18001f11c  sub     rsp, 40h
0x18001f120  mov     r12, r8
0x18001f123  mov     r15, rdx
0x18001f126  mov     r14, rcx
0x18001f129  lea     rsi, WPP_GLOBAL_Control
0x18001f130  mov     r10, cs:WPP_GLOBAL_Control
0x18001f137  cmp     r10, rsi
0x18001f13a  jz      short loc_18001F16C
0x18001f13c  cmp     byte ptr [r10+19h], 6
0x18001f141  jb      short loc_18001F16C
0x18001f143  mov     ecx, 1; int
0x18001f148  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001f14d  mov     edx, 23h ; '#'
0x18001f152  mov     r9, rax
0x18001f155  lea     r8, WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids
0x18001f15c  mov     rcx, [r10+10h]
0x18001f160  call    WPP_SF_s
0x18001f165  mov     r10, cs:WPP_GLOBAL_Control
0x18001f16c  test    r15, r15
0x18001f16f  jnz     short loc_18001F1A2
0x18001f171  cmp     r10, rsi
0x18001f174  jz      short loc_18001F198
0x18001f176  cmp     byte ptr [r10+19h], 2
0x18001f17b  jb      short loc_18001F198
0x18001f17d  lea     edx, [r15+24h]
0x18001f181  lea     r9, aPrules; "pRules"
0x18001f188  lea     r8, WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids
0x18001f18f  mov     rcx, [r10+10h]
0x18001f193  call    WPP_SF_s
0x18001f198  mov     eax, 80004003h
0x18001f19d  jmp     loc_18001F289
0x18001f1a2  mov     rdi, [r14+30h]
0x18001f1a6  mov     ecx, 38h ; '8'; Size
0x18001f1ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f1b0  test    rax, rax
0x18001f1b3  jz      short loc_18001F1DF
0x18001f1b5  mov     dword ptr [rax+10h], 8
0x18001f1bc  mov     qword ptr [rax+18h], 0
0x18001f1c4  mov     byte ptr [rax+24h], 0
0x18001f1c8  mov     qword ptr [rax+28h], 0
0x18001f1d0  mov     qword ptr [rax+30h], 0
0x18001f1d8  mov     qword ptr [rax], 0
0x18001f1df  mov     [r14+30h], rax
0x18001f1e3  test    rdi, rdi
0x18001f1e6  jz      short loc_18001F1FA
0x18001f1e8  mov     rcx, rdi; this
0x18001f1eb  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18001f1f0  nop
0x18001f1f1  mov     rcx, rdi
0x18001f1f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f1fa  mov     r9, r12
0x18001f1fd  mov     r8, r15
0x18001f200  mov     edx, 9
0x18001f205  mov     rcx, [r14+30h]
0x18001f209  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x18001f20e  mov     edi, eax
0x18001f210  test    eax, eax
0x18001f212  jns     short loc_18001F24C
0x18001f214  mov     r10, cs:WPP_GLOBAL_Control
0x18001f21b  cmp     r10, rsi
0x18001f21e  jz      short loc_18001F287
0x18001f220  cmp     byte ptr [r10+19h], 2
0x18001f225  jb      short loc_18001F253
0x18001f227  mov     edx, 26h ; '&'
0x18001f22c  mov     r9d, eax
0x18001f22f  lea     r8, WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids
0x18001f236  mov     rcx, [r10+10h]
0x18001f23a  call    WPP_SF_d
0x18001f23f  jmp     short loc_18001F24C
0x18001f241  lea     rsi, WPP_GLOBAL_Control
0x18001f248  mov     edi, [rsp+58h+arg_8]
0x18001f24c  mov     r10, cs:WPP_GLOBAL_Control
0x18001f253  cmp     r10, rsi
0x18001f256  jz      short loc_18001F287
0x18001f258  test    edi, edi
0x18001f25a  js      short loc_18001F263
0x18001f25c  cmp     byte ptr [r10+19h], 6
0x18001f261  jb      short loc_18001F287
0x18001f263  or      ecx, 0FFFFFFFFh; int
0x18001f266  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001f26b  mov     edx, 27h ; '''
0x18001f270  mov     [rsp+58h+var_38], edi
0x18001f274  mov     r9, rax
0x18001f277  lea     r8, WPP_ebbc341f3c523277fee0101aac43f93e_Traceguids
0x18001f27e  mov     rcx, [r10+10h]
0x18001f282  call    WPP_SF_sd
0x18001f287  mov     eax, edi
0x18001f289  mov     rsi, [rsp+58h+arg_0]
0x18001f28e  mov     rdi, [rsp+58h+arg_10]
0x18001f293  add     rsp, 40h
0x18001f297  pop     r15
0x18001f299  pop     r14
0x18001f29b  pop     r12
0x18001f29d  retn
```
