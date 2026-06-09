# web::json::details::JSON_Parser<char>::_ParseValue(web::json::details::JSON_Parser<char>::Token &)

- ea: `0x18003008c`
- end: `0x180030350`
- name: `?_ParseValue@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `708`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002df20`
- `0x180030844`
- `0x180030b24`

## callees

- `0x180029a10`
- `0x18002e6b0`
- `0x18003008c`
- `0x180030844`
- `0x180030b24`
- `0x180031c5c`
- `0x180042bfc`
- `0x180047a30`

## pseudocode

```c
_QWORD *__fastcall web::json::details::JSON_Parser<char>::_ParseValue(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rbx
  char v7; // cl
  __int64 v8; // rax
  char *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // xmm0_8
  char *v13; // r14
  char v14; // bl
  _QWORD *v16; // [rsp+20h] [rbp-48h]
  _QWORD *v17; // [rsp+20h] [rbp-48h]
  _QWORD *v18; // [rsp+20h] [rbp-48h]
  __int128 v19; // [rsp+28h] [rbp-40h]
  _QWORD *v20; // [rsp+28h] [rbp-40h]

  switch ( *(_DWORD *)a3 )
  {
    case 1:
      web::json::details::JSON_Parser<char>::_ParseObject(a1, a2, (_DWORD *)a3);
      return a2;
    case 3:
      web::json::details::JSON_Parser<char>::_ParseArray(a1, a2, (_DWORD *)a3);
      return a2;
    case 7:
      v13 = (char *)operator new(0x30u);
      v14 = *(_BYTE *)(a3 + 56);
      *(_QWORD *)v13 = &web::json::details::_String::`vftable';
      utility::conversions::utf8_to_utf16(v13 + 8);
      v13[40] = v14;
      web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v13;
        return a2;
      }
      v20 = operator new(8u);
      *v20 = &web::json::details::_Null::`vftable';
      *a2 = v20;
      v8 = *(_QWORD *)v13;
      v9 = v13;
      goto LABEL_14;
    case 8:
      v6 = operator new(0x18u);
      v12 = *(_QWORD *)(a3 + 56);
      *v6 = &web::json::details::_Number::`vftable';
      v6[1] = v12;
      *((_DWORD *)v6 + 4) = 2;
      web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v6;
        return a2;
      }
LABEL_12:
      v17 = operator new(8u);
      *v17 = &web::json::details::_Null::`vftable';
      *a2 = v17;
LABEL_13:
      v8 = *v6;
      v9 = (char *)v6;
LABEL_14:
      (*(void (__fastcall **)(char *, __int64))(v8 + 192))(v9, 1);
      return a2;
  }
  if ( *(_DWORD *)a3 != 9 )
  {
    if ( *(_DWORD *)a3 != 10 )
    {
      if ( *(_DWORD *)a3 == 11 )
      {
        web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
      }
      else
      {
        LODWORD(v19) = 8;
        *((_QWORD *)&v19 + 1) = web::json::details::json_error_category((web::json::details *)(unsigned int)(*(_DWORD *)a3 - 10));
        *(_OWORD *)(a3 + 72) = v19;
      }
      v16 = operator new(8u);
      *v16 = &web::json::details::_Null::`vftable';
      *a2 = v16;
      return a2;
    }
    v6 = operator new(0x10u);
    v7 = *(_BYTE *)(a3 + 56);
    *v6 = &web::json::details::_Boolean::`vftable';
    *((_BYTE *)v6 + 8) = v7;
    web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
    if ( !*(_DWORD *)(a3 + 72) )
    {
      *a2 = v6;
      return a2;
    }
    goto LABEL_12;
  }
  if ( *(_BYTE *)(a3 + 64) )
  {
    v6 = operator new(0x18u);
    v10 = *(_QWORD *)(a3 + 56);
    *v6 = &web::json::details::_Number::`vftable';
    v6[1] = v10;
    *((_DWORD *)v6 + 4) = v10 >= 0;
  }
  else
  {
    v6 = operator new(0x18u);
    v11 = *(_QWORD *)(a3 + 56);
    *v6 = &web::json::details::_Number::`vftable';
    v6[1] = v11;
    *((_DWORD *)v6 + 4) = 1;
  }
  web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
  if ( !*(_DWORD *)(a3 + 72) )
  {
    *a2 = v6;
    return a2;
  }
  v18 = operator new(8u);
  *v18 = &web::json::details::_Null::`vftable';
  *a2 = v18;
  if ( v6 )
    goto LABEL_13;
  return a2;
}

```

## disassembly

```asm
0x18003008c  push    rbx
0x18003008e  push    rbp
0x18003008f  push    rsi
0x180030090  push    rdi
0x180030091  push    r14
0x180030093  sub     rsp, 40h
0x180030097  mov     rsi, r8
0x18003009a  mov     rdi, rdx
0x18003009d  mov     rbp, rcx
0x1800300a0  mov     [rsp+68h+var_48], rdx
0x1800300a5  mov     ecx, [r8]
0x1800300a8  sub     ecx, 1
0x1800300ab  jz      loc_18003033A
0x1800300b1  sub     ecx, 2
0x1800300b4  jz      loc_180030330
0x1800300ba  sub     ecx, 4
0x1800300bd  jz      loc_1800302BE
0x1800300c3  sub     ecx, 1
0x1800300c6  jz      loc_180030252
0x1800300cc  sub     ecx, 1
0x1800300cf  jz      loc_1800301A1
0x1800300d5  sub     ecx, 1; this
0x1800300d8  jz      short loc_180030129
0x1800300da  cmp     ecx, 1
0x1800300dd  jz      short loc_18003011C
0x1800300df  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x1800300e4  mov     dword ptr [rsp+68h+var_40], 8
0x1800300ec  mov     qword ptr [rsp+68h+var_40+8], rax
0x1800300f1  movups  xmm0, [rsp+68h+var_40]
0x1800300f6  movdqu  xmmword ptr [rsi+48h], xmm0
0x1800300fb  mov     ecx, 8; Size
0x180030100  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030105  mov     [rsp+68h+var_48], rax
0x18003010a  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180030111  mov     [rax], rcx
0x180030114  mov     [rdi], rax
0x180030117  jmp     loc_180030342
0x18003011c  mov     rdx, rsi
0x18003011f  mov     rcx, rbp
0x180030122  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x180030127  jmp     short loc_1800300FB
0x180030129  mov     ecx, 10h; Size
0x18003012e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030133  mov     rbx, rax
0x180030136  mov     [rsp+68h+var_48], rax
0x18003013b  mov     cl, [rsi+38h]
0x18003013e  lea     rax, ??_7_Boolean@details@json@web@@6B@; const web::json::details::_Boolean::`vftable'
0x180030145  mov     [rbx], rax
0x180030148  mov     [rbx+8], cl
0x18003014b  mov     [rsp+68h+var_48], rbx
0x180030150  mov     rdx, rsi
0x180030153  mov     rcx, rbp
0x180030156  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x18003015b  cmp     dword ptr [rsi+48h], 0
0x18003015f  jz      short loc_180030199
0x180030161  mov     ecx, 8; Size
0x180030166  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003016b  mov     [rsp+68h+var_48], rax
0x180030170  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180030177  mov     [rax], rcx
0x18003017a  mov     [rdi], rax
0x18003017d  mov     rax, [rbx]
0x180030180  mov     rcx, rbx
0x180030183  mov     edx, 1
0x180030188  mov     rax, [rax+0C0h]
0x18003018f  call    _guard_dispatch_icall
0x180030194  jmp     loc_180030342
0x180030199  mov     [rdi], rbx
0x18003019c  jmp     loc_180030342
0x1800301a1  mov     [rsp+68h+var_48], 0
0x1800301aa  mov     ecx, 18h; Size
0x1800301af  cmp     byte ptr [r8+40h], 0
0x1800301b4  jz      short loc_1800301E1
0x1800301b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800301bb  mov     rbx, rax
0x1800301be  mov     [rsp+68h+var_48], rax
0x1800301c3  mov     rax, [rsi+38h]
0x1800301c7  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x1800301ce  mov     [rbx], rcx
0x1800301d1  mov     [rbx+8], rax
0x1800301d5  shr     rax, 3Fh
0x1800301d9  xor     eax, 1
0x1800301dc  mov     [rbx+10h], eax
0x1800301df  jmp     short loc_180030207
0x1800301e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800301e6  mov     rbx, rax
0x1800301e9  mov     [rsp+68h+var_48], rax
0x1800301ee  mov     rax, [rsi+38h]
0x1800301f2  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x1800301f9  mov     [rbx], rcx
0x1800301fc  mov     [rbx+8], rax
0x180030200  mov     dword ptr [rbx+10h], 1
0x180030207  mov     r14, rbx
0x18003020a  mov     [rsp+68h+var_48], rbx
0x18003020f  mov     rdx, rsi
0x180030212  mov     rcx, rbp
0x180030215  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x18003021a  cmp     dword ptr [rsi+48h], 0
0x18003021e  jz      short loc_18003024A
0x180030220  mov     ecx, 8; Size
0x180030225  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003022a  mov     [rsp+68h+var_48], rax
0x18003022f  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180030236  mov     [rax], rcx
0x180030239  mov     [rdi], rax
0x18003023c  test    rbx, rbx
0x18003023f  jz      loc_180030342
0x180030245  jmp     loc_18003017D
0x18003024a  mov     [rdi], rbx
0x18003024d  jmp     loc_180030342
0x180030252  mov     ecx, 18h; Size
0x180030257  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003025c  mov     rbx, rax
0x18003025f  mov     [rsp+68h+var_48], rax
0x180030264  movsd   xmm0, qword ptr [rsi+38h]
0x180030269  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x180030270  mov     [rax], rcx
0x180030273  movsd   qword ptr [rax+8], xmm0
0x180030278  mov     dword ptr [rax+10h], 2
0x18003027f  mov     [rsp+68h+var_48], rax
0x180030284  mov     rdx, rsi
0x180030287  mov     rcx, rbp
0x18003028a  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x18003028f  cmp     dword ptr [rsi+48h], 0
0x180030293  jz      short loc_1800302B6
0x180030295  mov     ecx, 8; Size
0x18003029a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003029f  mov     [rsp+68h+var_48], rax
0x1800302a4  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x1800302ab  mov     [rax], rcx
0x1800302ae  mov     [rdi], rax
0x1800302b1  jmp     loc_18003017D
0x1800302b6  mov     [rdi], rbx
0x1800302b9  jmp     loc_180030342
0x1800302be  mov     ecx, 30h ; '0'; Size
0x1800302c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800302c8  mov     r14, rax
0x1800302cb  mov     [rsp+68h+var_48], rax
0x1800302d0  mov     bl, [rsi+38h]
0x1800302d3  lea     rdx, [rsi+8]
0x1800302d7  lea     rax, ??_7_String@details@json@web@@6B@; const web::json::details::_String::`vftable'
0x1800302de  mov     [r14], rax
0x1800302e1  lea     rcx, [r14+8]; Src
0x1800302e5  call    ?utf8_to_utf16@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::utf8_to_utf16(std::string const &)
0x1800302ea  mov     [r14+28h], bl
0x1800302ee  mov     qword ptr [rsp+68h+var_40], r14
0x1800302f3  mov     rdx, rsi
0x1800302f6  mov     rcx, rbp
0x1800302f9  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x1800302fe  cmp     dword ptr [rsi+48h], 0
0x180030302  jz      short loc_18003032B
0x180030304  mov     ecx, 8; Size
0x180030309  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003030e  mov     qword ptr [rsp+68h+var_40], rax
0x180030313  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18003031a  mov     [rax], rcx
0x18003031d  mov     [rdi], rax
0x180030320  mov     rax, [r14]
0x180030323  mov     rcx, r14
0x180030326  jmp     loc_180030183
0x18003032b  mov     [rdi], r14
0x18003032e  jmp     short loc_180030342
0x180030330  mov     rcx, rbp
0x180030333  call    ?_ParseArray@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::_ParseArray(web::json::details::JSON_Parser<char>::Token &)
0x180030338  jmp     short loc_180030342
0x18003033a  mov     rcx, rbp
0x18003033d  call    ?_ParseObject@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::_ParseObject(web::json::details::JSON_Parser<char>::Token &)
0x180030342  mov     rax, rdi
0x180030345  add     rsp, 40h
0x180030349  pop     r14
0x18003034b  pop     rdi
0x18003034c  pop     rsi
0x18003034d  pop     rbp
0x18003034e  pop     rbx
0x18003034f  retn
```
