# BinXmlWriter::Parse(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)

- ea: `0x18002ebac`
- end: `0x18002eeb3`
- name: `?Parse@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z`
- size: `775`
- prototype: `__int64 __fastcall(BinXmlWriter *this, __int128 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x180027570`
- `0x18002e094`

## callees

- `0x18000a4b4`
- `0x180018468`
- `0x18001ab4c`
- `0x18001d000`
- `0x18001fc00`
- `0x1800210b0`
- `0x180023cec`
- `0x1800243e4`
- `0x18002e548`
- `0x18002e654`
- `0x18002e68c`
- `0x18002e6c4`
- `0x18002e900`
- `0x18002e934`
- `0x18002e96c`
- `0x18002e9a8`
- `0x18002eb18`
- `0x18002eb60`
- `0x18002ebac`
- `0x18002eebc`
- `0x18002f41c`
- `0x18002fd40`

## pseudocode

```c
__int64 __fastcall BinXmlWriter::Parse(BinXmlWriter *this, __int128 *a2)
{
  int Token; // esi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int128 v7; // xmm0
  BinXmlWriter *v8; // rcx
  bool v9; // dl
  __int64 v10; // rax
  wchar_t v11; // di
  int v12; // edx
  __int64 v13; // r8
  char *v14; // rcx
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // r8
  __int64 v19; // [rsp+20h] [rbp-69h]
  int v20; // [rsp+20h] [rbp-69h]
  __int64 v21; // [rsp+28h] [rbp-61h]
  __int128 v22; // [rsp+30h] [rbp-59h] BYREF
  int *v23; // [rsp+40h] [rbp-49h] BYREF
  int v24; // [rsp+48h] [rbp-41h]
  char v25; // [rsp+4Ch] [rbp-3Dh]
  __int128 v26; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v27[24]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v28[40]; // [rsp+78h] [rbp-11h] BYREF
  int v29; // [rsp+A0h] [rbp+17h]
  char v30; // [rsp+B0h] [rbp+27h] BYREF
  char v31; // [rsp+C0h] [rbp+37h] BYREF
  unsigned int v32; // [rsp+F8h] [rbp+6Fh] BYREF

  v26 = *a2;
  WevtXMLParser::WevtXMLParser(v27, &v26);
  do
  {
    v23 = &dword_180040824;
    v24 = 0;
    v25 = 1;
    Token = (unsigned __int8)WevtXMLParser::NextToken(v27);
    GenericLexer::GetTokenText(v28, &v26);
    if ( (unsigned __int8)Token > 7u )
    {
      switch ( Token )
      {
        case 9:
          v22 = v26;
          BinXmlWriter::CDATA(this, &v22);
          break;
        case 11:
          v22 = v26;
          BinXmlString::SetString(&v23, &v22);
          BinXmlWriter::EntityRef(this, (const struct BinXmlString *)&v23);
          break;
        case 12:
          v11 = 126;
          v12 = v26;
          v13 = v26 + 2LL * *((_QWORD *)&v26 + 1);
          if ( (_QWORD)v26 == v13 || *(_WORD *)v26 != 120 )
          {
            v20 = 10;
            v14 = &v31;
          }
          else
          {
            v12 = v26 + 2;
            v20 = 16;
            v14 = &v30;
          }
          v32 = 0;
          v16 = *(_DWORD *)(utl::_FromCharsImpl<utl::from_wchars_result,unsigned int,wchar_t>(
                              (_DWORD)v14,
                              v12,
                              v13,
                              (unsigned int)&v32,
                              v20,
                              0)
                          + 8);
          if ( v16 || (v32 <= 0xFFFF ? (v11 = v32) : (v16 = 34), v16) )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v17, &v26);
            }
          }
          BinXmlWriter::CharRef(this, v11);
          break;
        case 13:
          v22 = v26;
          BinXmlString::SetString(&v23, &v22);
          BinXmlWriter::PITarget(this, (const struct BinXmlString *)&v23);
          break;
        case 14:
          v22 = v26;
          BinXmlWriter::PIData(this, &v22);
          break;
        case 15:
          BinXmlWriter::EndOfFile(this);
          break;
      }
    }
    else
    {
      v7 = v26;
      if ( (_BYTE)Token == 7 )
      {
        v10 = *((_QWORD *)this + 7);
        if ( *((_QWORD *)this + 6) != v10 && (*((_BYTE *)this + 104) || *(_BYTE *)(v10 - 4)) )
          goto LABEL_23;
        v22 = v26;
        if ( !(unsigned __int8)IsStringWhitespace(&v22, v4, v5, v6, v19, v21) )
          goto LABEL_23;
      }
      else
      {
        switch ( Token )
        {
          case 1:
            v22 = v26;
            BinXmlString::SetString(&v23, &v22);
            BinXmlWriter::OpenStartElementTag(this, (const struct BinXmlString *)&v23);
            break;
          case 2:
            goto LABEL_15;
          case 3:
            v9 = 0;
            v8 = this;
LABEL_17:
            BinXmlWriter::CloseStartElementTag(v8, v9);
            break;
          case 4:
            v8 = this;
            if ( v29 <= 0 )
            {
              BinXmlWriter::CloseStartElementTag(this, 0);
LABEL_15:
              BinXmlWriter::EndElementTag(this);
              break;
            }
            v9 = 1;
            goto LABEL_17;
          case 5:
            v22 = v26;
            BinXmlString::SetString(&v23, &v22);
            BinXmlWriter::Attribute(this, (const struct BinXmlString *)&v23);
            break;
          case 6:
LABEL_23:
            v22 = v7;
            if ( *((_BYTE *)this + 105) )
              BinXmlWriter::ParseTemplateString(this);
            else
              BinXmlWriter::StrLenValue(this, &v22, v5);
            break;
        }
      }
    }
    BinXmlString::~BinXmlString((BinXmlString *)&v23);
  }
  while ( (_BYTE)Token != 15 );
  return utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v27);
}

```

## disassembly

```asm
0x18002ebac  mov     [rsp-8+arg_0], rbx
0x18002ebb1  mov     [rsp-8+arg_10], rsi
0x18002ebb6  push    rbp
0x18002ebb7  push    rdi
0x18002ebb8  push    r14
0x18002ebba  lea     rbp, [rsp-47h]
0x18002ebbf  sub     rsp, 0D0h
0x18002ebc6  mov     r14b, r8b
0x18002ebc9  mov     rbx, rcx
0x18002ebcc  movaps  xmm0, xmmword ptr [rdx]
0x18002ebcf  movdqa  [rbp+57h+var_90], xmm0
0x18002ebd4  lea     rdx, [rbp+57h+var_90]
0x18002ebd8  lea     rcx, [rbp+57h+var_80]
0x18002ebdc  call    ??0WevtXMLParser@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; WevtXMLParser::WevtXMLParser(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ebe1  nop
0x18002ebe2  lea     rax, dword_180040824
0x18002ebe9  mov     [rbp+57h+var_A0], rax
0x18002ebed  xor     eax, eax
0x18002ebef  mov     [rbp+57h+var_98], eax
0x18002ebf2  mov     [rbp+57h+var_94], 1
0x18002ebf6  lea     rcx, [rbp+57h+var_80]
0x18002ebfa  call    ?NextToken@WevtXMLParser@@QEAA?AW4XmlTokenType@@XZ; WevtXMLParser::NextToken(void)
0x18002ebff  movzx   esi, al
0x18002ec02  lea     rdx, [rbp+57h+var_90]
0x18002ec06  lea     rcx, [rbp+57h+var_68]
0x18002ec0a  call    ?GetTokenText@GenericLexer@@QEAA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@XZ; GenericLexer::GetTokenText(void)
0x18002ec0f  cmp     sil, 7
0x18002ec13  ja      loc_18002ED17
0x18002ec19  movaps  xmm0, [rbp+57h+var_90]
0x18002ec1d  jz      loc_18002ECC2
0x18002ec23  mov     edx, esi
0x18002ec25  sub     edx, 1
0x18002ec28  jz      short loc_18002EC9F
0x18002ec2a  sub     edx, 1
0x18002ec2d  jz      short loc_18002EC83
0x18002ec2f  sub     edx, 1
0x18002ec32  jz      short loc_18002EC90
0x18002ec34  sub     edx, 1
0x18002ec37  jz      short loc_18002EC6F
0x18002ec39  sub     edx, 1
0x18002ec3c  jz      short loc_18002EC4C
0x18002ec3e  cmp     edx, 1
0x18002ec41  jz      loc_18002ECEE
0x18002ec47  jmp     loc_18002EE7F
0x18002ec4c  movdqa  [rbp+57h+var_B0], xmm0
0x18002ec51  lea     rdx, [rbp+57h+var_B0]
0x18002ec55  lea     rcx, [rbp+57h+var_A0]
0x18002ec59  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ec5e  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002ec62  mov     rcx, rbx; this
0x18002ec65  call    ?Attribute@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::Attribute(BinXmlString const &)
0x18002ec6a  jmp     loc_18002EE7F
0x18002ec6f  mov     rcx, rbx; this
0x18002ec72  cmp     [rbp+57h+var_40], 0
0x18002ec76  jle     short loc_18002EC7C
0x18002ec78  mov     dl, 1
0x18002ec7a  jmp     short loc_18002EC95
0x18002ec7c  xor     edx, edx; bool
0x18002ec7e  call    ?CloseStartElementTag@BinXmlWriter@@QEAAX_N@Z; BinXmlWriter::CloseStartElementTag(bool)
0x18002ec83  mov     rcx, rbx; this
0x18002ec86  call    ?EndElementTag@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndElementTag(void)
0x18002ec8b  jmp     loc_18002EE7F
0x18002ec90  xor     edx, edx; bool
0x18002ec92  mov     rcx, rbx; this
0x18002ec95  call    ?CloseStartElementTag@BinXmlWriter@@QEAAX_N@Z; BinXmlWriter::CloseStartElementTag(bool)
0x18002ec9a  jmp     loc_18002EE7F
0x18002ec9f  movdqa  [rbp+57h+var_B0], xmm0
0x18002eca4  lea     rdx, [rbp+57h+var_B0]
0x18002eca8  lea     rcx, [rbp+57h+var_A0]
0x18002ecac  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ecb1  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002ecb5  mov     rcx, rbx; this
0x18002ecb8  call    ?OpenStartElementTag@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::OpenStartElementTag(BinXmlString const &)
0x18002ecbd  jmp     loc_18002EE7F
0x18002ecc2  mov     rax, [rbx+38h]
0x18002ecc6  cmp     [rbx+30h], rax
0x18002ecca  jz      short loc_18002ECD8
0x18002eccc  cmp     byte ptr [rbx+68h], 0
0x18002ecd0  jnz     short loc_18002ECEE
0x18002ecd2  cmp     byte ptr [rax-4], 0
0x18002ecd6  jnz     short loc_18002ECEE
0x18002ecd8  movdqa  [rbp+57h+var_B0], xmm0
0x18002ecdd  lea     rcx, [rbp+57h+var_B0]
0x18002ece1  call    IsStringWhitespace
0x18002ece6  test    al, al
0x18002ece8  jnz     loc_18002EE7F
0x18002ecee  movdqa  [rbp+57h+var_B0], xmm0
0x18002ecf3  lea     rdx, [rbp+57h+var_B0]
0x18002ecf7  mov     rcx, rbx; this
0x18002ecfa  cmp     byte ptr [rbx+69h], 0
0x18002ecfe  jnz     short loc_18002ED0A
0x18002ed00  call    ?StrLenValue@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::StrLenValue(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ed05  jmp     loc_18002EE7F
0x18002ed0a  mov     r8b, r14b
0x18002ed0d  call    ?ParseTemplateString@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z; BinXmlWriter::ParseTemplateString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)
0x18002ed12  jmp     loc_18002EE7F
0x18002ed17  mov     ecx, esi
0x18002ed19  sub     ecx, 9
0x18002ed1c  jz      loc_18002EE69
0x18002ed22  sub     ecx, 2
0x18002ed25  jz      loc_18002EE45
0x18002ed2b  sub     ecx, 1
0x18002ed2e  jz      short loc_18002ED91
0x18002ed30  sub     ecx, 1
0x18002ed33  jz      short loc_18002ED6A
0x18002ed35  sub     ecx, 1
0x18002ed38  jz      short loc_18002ED50
0x18002ed3a  cmp     ecx, 1
0x18002ed3d  jnz     loc_18002EE7F
0x18002ed43  mov     rcx, rbx; this
0x18002ed46  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x18002ed4b  jmp     loc_18002EE7F
0x18002ed50  movaps  xmm0, [rbp+57h+var_90]
0x18002ed54  movdqa  [rbp+57h+var_B0], xmm0
0x18002ed59  lea     rdx, [rbp+57h+var_B0]
0x18002ed5d  mov     rcx, rbx
0x18002ed60  call    ?PIData@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::PIData(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ed65  jmp     loc_18002EE7F
0x18002ed6a  movaps  xmm0, [rbp+57h+var_90]
0x18002ed6e  movdqa  [rbp+57h+var_B0], xmm0
0x18002ed73  lea     rdx, [rbp+57h+var_B0]
0x18002ed77  lea     rcx, [rbp+57h+var_A0]
0x18002ed7b  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ed80  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002ed84  mov     rcx, rbx; this
0x18002ed87  call    ?PITarget@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::PITarget(BinXmlString const &)
0x18002ed8c  jmp     loc_18002EE7F
0x18002ed91  mov     edi, 7Eh ; '~'
0x18002ed96  mov     rdx, qword ptr [rbp+57h+var_90]
0x18002ed9a  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18002ed9e  lea     r8, [rdx+rax*2]
0x18002eda2  cmp     rdx, r8
0x18002eda5  jz      short loc_18002EDC8
0x18002eda7  cmp     word ptr [rdx], 78h ; 'x'
0x18002edab  jnz     short loc_18002EDC8
0x18002edad  add     rdx, 2
0x18002edb1  mov     [rsp+0E0h+var_B8], 0
0x18002edba  mov     dword ptr [rsp+0E0h+var_C0], 10h
0x18002edc2  lea     rcx, [rbp+57h+var_30]
0x18002edc6  jmp     short loc_18002EDDD
0x18002edc8  mov     [rsp+0E0h+var_B8], 0
0x18002edd1  mov     dword ptr [rsp+0E0h+var_C0], 0Ah
0x18002edd9  lea     rcx, [rbp+57h+var_20]
0x18002eddd  mov     [rbp+57h+arg_8], 0
0x18002ede4  lea     r9, [rbp+57h+arg_8]
0x18002ede8  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@I_W@utl@@YA?AUfrom_wchars_result@0@PEB_W0AEAIHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,uint,wchar_t>(wchar_t const *,wchar_t const *,uint &,int,bool *)
0x18002eded  mov     ecx, [rax+8]
0x18002edf0  test    ecx, ecx
0x18002edf2  jnz     short loc_18002EE0C
0x18002edf4  cmp     [rbp+57h+arg_8], 0FFFFh
0x18002edfb  jbe     short loc_18002EE04
0x18002edfd  mov     ecx, 22h ; '"'
0x18002ee02  jmp     short loc_18002EE08
0x18002ee04  movzx   edi, word ptr [rbp+57h+arg_8]
0x18002ee08  test    ecx, ecx
0x18002ee0a  jz      short loc_18002EE38
0x18002ee0c  lea     rax, WPP_GLOBAL_Control
0x18002ee13  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee1a  cmp     rcx, rax
0x18002ee1d  jz      short loc_18002EE38
0x18002ee1f  test    byte ptr [rcx+1Ch], 2
0x18002ee23  jz      short loc_18002EE38
0x18002ee25  cmp     byte ptr [rcx+19h], 3
0x18002ee29  jb      short loc_18002EE38
0x18002ee2b  lea     r9, [rbp+57h+var_90]
0x18002ee2f  mov     rcx, [rcx+10h]
0x18002ee33  call    WPP_SF__utlwsv_
0x18002ee38  movzx   edx, di; wchar_t
0x18002ee3b  mov     rcx, rbx; this
0x18002ee3e  call    ?CharRef@BinXmlWriter@@QEAAX_W@Z; BinXmlWriter::CharRef(wchar_t)
0x18002ee43  jmp     short loc_18002EE7F
0x18002ee45  movaps  xmm0, [rbp+57h+var_90]
0x18002ee49  movdqa  [rbp+57h+var_B0], xmm0
0x18002ee4e  lea     rdx, [rbp+57h+var_B0]
0x18002ee52  lea     rcx, [rbp+57h+var_A0]
0x18002ee56  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ee5b  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002ee5f  mov     rcx, rbx; this
0x18002ee62  call    ?EntityRef@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::EntityRef(BinXmlString const &)
0x18002ee67  jmp     short loc_18002EE7F
0x18002ee69  movaps  xmm0, [rbp+57h+var_90]
0x18002ee6d  movdqa  [rbp+57h+var_B0], xmm0
0x18002ee72  lea     rdx, [rbp+57h+var_B0]
0x18002ee76  mov     rcx, rbx
0x18002ee79  call    ?CDATA@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::CDATA(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ee7e  nop
0x18002ee7f  lea     rcx, [rbp+57h+var_A0]; this
0x18002ee83  call    ??1BinXmlString@@QEAA@XZ; BinXmlString::~BinXmlString(void)
0x18002ee88  cmp     sil, 0Fh
0x18002ee8c  jnz     loc_18002EBE2
0x18002ee92  lea     rcx, [rbp+57h+var_80]
0x18002ee96  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002ee9b  lea     r11, [rsp+0E0h+var_10]
0x18002eea3  mov     rbx, [r11+20h]
0x18002eea7  mov     rsi, [r11+30h]
0x18002eeab  mov     rsp, r11
0x18002eeae  pop     r14
0x18002eeb0  pop     rdi
0x18002eeb1  pop     rbp
0x18002eeb2  retn
```
