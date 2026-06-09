# web::json::details::JSON_Parser<char>::_ParseArray(web::json::details::JSON_Parser<char>::Token &)

- ea: `0x180030b24`
- end: `0x180030ced`
- name: `?_ParseArray@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `457`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003008c`

## callees

- `0x180029a10`
- `0x18002c70c`
- `0x18002e6b0`
- `0x18003008c`
- `0x180030b24`
- `0x180031368`
- `0x180042bfc`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall web::json::details::JSON_Parser<char>::_ParseArray(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  _QWORD *v6; // rax
  void *v7; // rdi
  _QWORD *v8; // rax
  __int64 *v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // rax
  const struct web::json::details::json_error_category_impl *v12; // rax
  __int64 v14; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v15; // [rsp+28h] [rbp-50h] BYREF
  __int128 v16; // [rsp+30h] [rbp-48h]
  void *v17; // [rsp+48h] [rbp-30h]

  v15 = a2;
  web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
  if ( a3[18] )
  {
    v6 = operator new(8u);
    v15 = v6;
    *v6 = &web::json::details::_Null::`vftable';
    *a2 = v6;
  }
  else
  {
    v7 = operator new(0x20u);
    v15 = v7;
    *(_OWORD *)v7 = 0;
    *((_OWORD *)v7 + 1) = 0;
    *(_QWORD *)v7 = &web::json::details::_Array::`vftable';
    *((_QWORD *)v7 + 1) = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    v17 = v7;
    if ( *a3 == 4 )
    {
      web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
      if ( !a3[18] )
      {
LABEL_16:
        *a2 = v7;
        return a2;
      }
    }
    else
    {
      do
      {
        v8 = (_QWORD *)web::json::details::JSON_Parser<char>::_ParseValue(a1, &v15, a3);
        web::json::value::value(&v14, v8);
        v9 = (__int64 *)*((_QWORD *)v7 + 2);
        if ( v9 == *((__int64 **)v7 + 3) )
        {
          std::vector<web::json::value>::_Emplace_reallocate<web::json::value>((_QWORD *)v7 + 1, v9, &v14);
        }
        else
        {
          v10 = v14;
          v14 = 0;
          *v9 = v10;
          *((_QWORD *)v7 + 2) += 8LL;
        }
        if ( v14 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 192LL))(v14, 1);
        if ( a3[18] )
          break;
        if ( *a3 == 4 )
        {
          web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
          if ( a3[18] )
            break;
          goto LABEL_16;
        }
        if ( *a3 != 5 )
        {
          v12 = web::json::details::json_error_category((web::json::details *)(unsigned int)(*a3 - 4));
          LODWORD(v16) = 2;
          *((_QWORD *)&v16 + 1) = v12;
          *(_OWORD *)(a3 + 18) = v16;
          break;
        }
        web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
      }
      while ( !a3[18] );
    }
    v11 = operator new(8u);
    *(_QWORD *)&v16 = v11;
    *v11 = &web::json::details::_Null::`vftable';
    *a2 = v11;
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v7 + 192LL))(v7, 1);
  }
  return a2;
}

```

## disassembly

```asm
0x180030b24  mov     [rsp+arg_18], rbx
0x180030b29  push    rbp
0x180030b2a  push    rsi
0x180030b2b  push    rdi
0x180030b2c  push    r12
0x180030b2e  push    r15
0x180030b30  sub     rsp, 50h
0x180030b34  mov     rsi, r8
0x180030b37  mov     rbx, rdx
0x180030b3a  mov     r12, rcx
0x180030b3d  mov     [rsp+78h+var_50], rdx
0x180030b42  mov     rdx, r8
0x180030b45  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x180030b4a  cmp     dword ptr [rsi+48h], 0
0x180030b4e  jz      short loc_180030B71
0x180030b50  mov     ecx, 8; Size
0x180030b55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030b5a  mov     [rsp+78h+var_50], rax
0x180030b5f  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180030b66  mov     [rax], rcx
0x180030b69  mov     [rbx], rax
0x180030b6c  jmp     loc_180030CBA
0x180030b71  mov     ecx, 20h ; ' '; Size
0x180030b76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030b7b  mov     rdi, rax
0x180030b7e  mov     [rsp+78h+var_50], rax
0x180030b83  xorps   xmm0, xmm0
0x180030b86  movups  xmmword ptr [rax], xmm0
0x180030b89  movups  xmmword ptr [rax+10h], xmm0
0x180030b8d  lea     rax, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x180030b94  mov     [rdi], rax
0x180030b97  mov     qword ptr [rdi+8], 0
0x180030b9f  mov     qword ptr [rdi+10h], 0
0x180030ba7  mov     qword ptr [rdi+18h], 0
0x180030baf  mov     [rsp+78h+var_30], rdi
0x180030bb4  cmp     dword ptr [rsi], 4
0x180030bb7  jz      loc_180030CD1
0x180030bbd  mov     ebp, 8
0x180030bc2  mov     r8, rsi
0x180030bc5  lea     rdx, [rsp+78h+var_50]
0x180030bca  mov     rcx, r12
0x180030bcd  call    ?_ParseValue@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::_ParseValue(web::json::details::JSON_Parser<char>::Token &)
0x180030bd2  mov     rdx, rax
0x180030bd5  lea     rcx, [rsp+78h+var_58]
0x180030bda  call    ??0value@json@web@@AEAA@V?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@@Z; web::json::value::value(std::unique_ptr<web::json::details::_Value>)
0x180030bdf  nop
0x180030be0  mov     rdx, [rdi+10h]
0x180030be4  cmp     rdx, [rdi+18h]
0x180030be8  jz      short loc_180030C01
0x180030bea  mov     rax, [rsp+78h+var_58]
0x180030bef  mov     [rsp+78h+var_58], 0
0x180030bf8  mov     [rdx], rax
0x180030bfb  add     [rdi+10h], rbp
0x180030bff  jmp     short loc_180030C10
0x180030c01  lea     r8, [rsp+78h+var_58]
0x180030c06  lea     rcx, [rdi+8]
0x180030c0a  call    ??$_Emplace_reallocate@Vvalue@json@web@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAPEAVvalue@json@web@@QEAV234@$$QEAV234@@Z; std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(web::json::value * const,web::json::value &&)
0x180030c0f  nop
0x180030c10  mov     rcx, [rsp+78h+var_58]
0x180030c15  test    rcx, rcx
0x180030c18  jz      short loc_180030C2E
0x180030c1a  mov     rax, [rcx]
0x180030c1d  mov     edx, 1
0x180030c22  mov     rax, [rax+0C0h]
0x180030c29  call    _guard_dispatch_icall
0x180030c2e  cmp     dword ptr [rsi+48h], 0
0x180030c32  jnz     short loc_180030C55
0x180030c34  mov     ecx, [rsi]
0x180030c36  sub     ecx, 4; this
0x180030c39  jz      short loc_180030CA6
0x180030c3b  cmp     ecx, 1
0x180030c3e  jnz     short loc_180030C88
0x180030c40  mov     rdx, rsi
0x180030c43  mov     rcx, r12
0x180030c46  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x180030c4b  cmp     dword ptr [rsi+48h], 0
0x180030c4f  jz      loc_180030BC2
0x180030c55  mov     rcx, rbp; Size
0x180030c58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030c5d  mov     qword ptr [rsp+78h+var_48], rax
0x180030c62  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180030c69  mov     [rax], rcx
0x180030c6c  mov     [rbx], rax
0x180030c6f  mov     rax, [rdi]
0x180030c72  mov     edx, 1
0x180030c77  mov     rcx, rdi
0x180030c7a  mov     rax, [rax+0C0h]
0x180030c81  call    _guard_dispatch_icall
0x180030c86  jmp     short loc_180030CBA
0x180030c88  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x180030c8d  mov     dword ptr [rsp+78h+var_48], 2
0x180030c95  mov     qword ptr [rsp+78h+var_48+8], rax
0x180030c9a  movups  xmm0, [rsp+78h+var_48]
0x180030c9f  movdqu  xmmword ptr [rsi+48h], xmm0
0x180030ca4  jmp     short loc_180030C55
0x180030ca6  mov     rdx, rsi
0x180030ca9  mov     rcx, r12
0x180030cac  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x180030cb1  cmp     dword ptr [rsi+48h], 0
0x180030cb5  jnz     short loc_180030C55
0x180030cb7  mov     [rbx], rdi
0x180030cba  mov     rax, rbx
0x180030cbd  mov     rbx, [rsp+78h+arg_18]
0x180030cc5  add     rsp, 50h
0x180030cc9  pop     r15
0x180030ccb  pop     r12
0x180030ccd  pop     rdi
0x180030cce  pop     rsi
0x180030ccf  pop     rbp
0x180030cd0  retn
0x180030cd1  mov     rdx, rsi
0x180030cd4  mov     rcx, r12
0x180030cd7  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x180030cdc  cmp     dword ptr [rsi+48h], 0
0x180030ce0  jz      short loc_180030CB7
0x180030ce2  mov     ecx, 8
0x180030ce7  jmp     loc_180030C58
```
