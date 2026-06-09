# web::json::details::JSON_Parser<wchar_t>::_ParseArray(web::json::details::JSON_Parser<wchar_t>::Token &)

- ea: `0x180030674`
- end: `0x18003083d`
- name: `?_ParseArray@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `457`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f6a4`

## callees

- `0x180029a10`
- `0x18002c70c`
- `0x18002e198`
- `0x18002f6a4`
- `0x180030674`
- `0x180031368`
- `0x180042bfc`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall web::json::details::JSON_Parser<wchar_t>::_ParseArray(__int64 a1, _QWORD *a2, _DWORD *a3)
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
  web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
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
      web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
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
        v8 = (_QWORD *)web::json::details::JSON_Parser<wchar_t>::_ParseValue(a1, &v15, a3);
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
          web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
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
        web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
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
0x180030674  mov     [rsp+arg_18], rbx
0x180030679  push    rbp
0x18003067a  push    rsi
0x18003067b  push    rdi
0x18003067c  push    r12
0x18003067e  push    r15
0x180030680  sub     rsp, 50h
0x180030684  mov     rsi, r8
0x180030687  mov     rbx, rdx
0x18003068a  mov     r12, rcx
0x18003068d  mov     [rsp+78h+var_50], rdx
0x180030692  mov     rdx, r8
0x180030695  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18003069a  cmp     dword ptr [rsi+48h], 0
0x18003069e  jz      short loc_1800306C1
0x1800306a0  mov     ecx, 8; Size
0x1800306a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800306aa  mov     [rsp+78h+var_50], rax
0x1800306af  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x1800306b6  mov     [rax], rcx
0x1800306b9  mov     [rbx], rax
0x1800306bc  jmp     loc_18003080A
0x1800306c1  mov     ecx, 20h ; ' '; Size
0x1800306c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800306cb  mov     rdi, rax
0x1800306ce  mov     [rsp+78h+var_50], rax
0x1800306d3  xorps   xmm0, xmm0
0x1800306d6  movups  xmmword ptr [rax], xmm0
0x1800306d9  movups  xmmword ptr [rax+10h], xmm0
0x1800306dd  lea     rax, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x1800306e4  mov     [rdi], rax
0x1800306e7  mov     qword ptr [rdi+8], 0
0x1800306ef  mov     qword ptr [rdi+10h], 0
0x1800306f7  mov     qword ptr [rdi+18h], 0
0x1800306ff  mov     [rsp+78h+var_30], rdi
0x180030704  cmp     dword ptr [rsi], 4
0x180030707  jz      loc_180030821
0x18003070d  mov     ebp, 8
0x180030712  mov     r8, rsi
0x180030715  lea     rdx, [rsp+78h+var_50]
0x18003071a  mov     rcx, r12
0x18003071d  call    ?_ParseValue@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::_ParseValue(web::json::details::JSON_Parser<wchar_t>::Token &)
0x180030722  mov     rdx, rax
0x180030725  lea     rcx, [rsp+78h+var_58]
0x18003072a  call    ??0value@json@web@@AEAA@V?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@@Z; web::json::value::value(std::unique_ptr<web::json::details::_Value>)
0x18003072f  nop
0x180030730  mov     rdx, [rdi+10h]
0x180030734  cmp     rdx, [rdi+18h]
0x180030738  jz      short loc_180030751
0x18003073a  mov     rax, [rsp+78h+var_58]
0x18003073f  mov     [rsp+78h+var_58], 0
0x180030748  mov     [rdx], rax
0x18003074b  add     [rdi+10h], rbp
0x18003074f  jmp     short loc_180030760
0x180030751  lea     r8, [rsp+78h+var_58]
0x180030756  lea     rcx, [rdi+8]
0x18003075a  call    ??$_Emplace_reallocate@Vvalue@json@web@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAPEAVvalue@json@web@@QEAV234@$$QEAV234@@Z; std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(web::json::value * const,web::json::value &&)
0x18003075f  nop
0x180030760  mov     rcx, [rsp+78h+var_58]
0x180030765  test    rcx, rcx
0x180030768  jz      short loc_18003077E
0x18003076a  mov     rax, [rcx]
0x18003076d  mov     edx, 1
0x180030772  mov     rax, [rax+0C0h]
0x180030779  call    _guard_dispatch_icall
0x18003077e  cmp     dword ptr [rsi+48h], 0
0x180030782  jnz     short loc_1800307A5
0x180030784  mov     ecx, [rsi]
0x180030786  sub     ecx, 4; this
0x180030789  jz      short loc_1800307F6
0x18003078b  cmp     ecx, 1
0x18003078e  jnz     short loc_1800307D8
0x180030790  mov     rdx, rsi
0x180030793  mov     rcx, r12
0x180030796  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18003079b  cmp     dword ptr [rsi+48h], 0
0x18003079f  jz      loc_180030712
0x1800307a5  mov     rcx, rbp; Size
0x1800307a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800307ad  mov     qword ptr [rsp+78h+var_48], rax
0x1800307b2  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x1800307b9  mov     [rax], rcx
0x1800307bc  mov     [rbx], rax
0x1800307bf  mov     rax, [rdi]
0x1800307c2  mov     edx, 1
0x1800307c7  mov     rcx, rdi
0x1800307ca  mov     rax, [rax+0C0h]
0x1800307d1  call    _guard_dispatch_icall
0x1800307d6  jmp     short loc_18003080A
0x1800307d8  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x1800307dd  mov     dword ptr [rsp+78h+var_48], 2
0x1800307e5  mov     qword ptr [rsp+78h+var_48+8], rax
0x1800307ea  movups  xmm0, [rsp+78h+var_48]
0x1800307ef  movdqu  xmmword ptr [rsi+48h], xmm0
0x1800307f4  jmp     short loc_1800307A5
0x1800307f6  mov     rdx, rsi
0x1800307f9  mov     rcx, r12
0x1800307fc  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x180030801  cmp     dword ptr [rsi+48h], 0
0x180030805  jnz     short loc_1800307A5
0x180030807  mov     [rbx], rdi
0x18003080a  mov     rax, rbx
0x18003080d  mov     rbx, [rsp+78h+arg_18]
0x180030815  add     rsp, 50h
0x180030819  pop     r15
0x18003081b  pop     r12
0x18003081d  pop     rdi
0x18003081e  pop     rsi
0x18003081f  pop     rbp
0x180030820  retn
0x180030821  mov     rdx, rsi
0x180030824  mov     rcx, r12
0x180030827  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18003082c  cmp     dword ptr [rsi+48h], 0
0x180030830  jz      short loc_180030807
0x180030832  mov     ecx, 8
0x180030837  jmp     loc_1800307A8
```
