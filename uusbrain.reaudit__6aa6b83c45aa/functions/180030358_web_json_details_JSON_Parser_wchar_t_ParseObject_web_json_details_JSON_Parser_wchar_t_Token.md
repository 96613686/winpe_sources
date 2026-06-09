# web::json::details::JSON_Parser<wchar_t>::_ParseObject(web::json::details::JSON_Parser<wchar_t>::Token &)

- ea: `0x180030358`
- end: `0x18003066c`
- name: `?_ParseObject@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f6a4`

## callees

- `0x180029644`
- `0x180029a10`
- `0x18002a57c`
- `0x18002e198`
- `0x18002f6a4`
- `0x180030358`
- `0x1800310f4`
- `0x180042bfc`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall web::json::details::JSON_Parser<wchar_t>::_ParseObject(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rbx
  _OWORD *v7; // r14
  bool v8; // al
  __int128 *v9; // r15
  __int128 v10; // xmm6
  __int128 v11; // xmm7
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  web::json::details *v15; // rcx
  const struct web::json::details::json_error_category_impl *v16; // rax
  _QWORD *v17; // rax
  __int128 v19; // [rsp+28h] [rbp-69h] BYREF
  __int128 v20; // [rsp+38h] [rbp-59h]
  __int64 v21; // [rsp+48h] [rbp-49h] BYREF
  __int128 v22; // [rsp+50h] [rbp-41h] BYREF
  _OWORD *v23; // [rsp+60h] [rbp-31h]
  __int128 v24; // [rsp+70h] [rbp-21h] BYREF
  __int128 v25; // [rsp+80h] [rbp-11h]

  v6 = 0;
  v7 = operator new(0x28u);
  *(_QWORD *)&v22 = v7;
  *v7 = 0;
  v7[1] = 0;
  *((_QWORD *)v7 + 4) = 0;
  v8 = web::json::details::g_keep_json_object_unsorted;
  *(_QWORD *)v7 = &web::json::details::_Object::`vftable';
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 0;
  *((_BYTE *)v7 + 32) = v8;
  v23 = v7;
  web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
  if ( *(_DWORD *)(a3 + 72) )
    goto LABEL_23;
  if ( *(_DWORD *)a3 != 2 )
  {
    v19 = 0;
    *(_QWORD *)&v20 = 0;
    *((_QWORD *)&v20 + 1) = 7;
    LOWORD(v19) = 0;
    if ( *(_DWORD *)a3 == 7 )
    {
      v9 = (__int128 *)(a3 + 8);
      while ( 1 )
      {
        if ( &v19 == v9 )
        {
          v11 = v20;
          v10 = v19;
        }
        else
        {
          std::wstring::_Tidy_deallocate(&v19);
          v10 = *v9;
          v19 = *v9;
          v11 = *(_OWORD *)(a3 + 24);
          v20 = v11;
          *(_QWORD *)(a3 + 24) = 0;
          *(_QWORD *)(a3 + 32) = 7;
          *(_WORD *)v9 = 0;
        }
        web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
        if ( *(_DWORD *)(a3 + 72) )
          break;
        if ( *(_DWORD *)a3 != 6 )
          goto LABEL_25;
        web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
        if ( *(_DWORD *)(a3 + 72) )
          break;
        v12 = web::json::details::JSON_Parser<wchar_t>::_ParseValue(a1, &v22, a3);
        v13 = *v12;
        *v12 = 0;
        v21 = v13;
        v24 = v10;
        v25 = v11;
        *(_QWORD *)&v20 = 0;
        *((_QWORD *)&v20 + 1) = 7;
        LOWORD(v19) = 0;
        v14 = *((_QWORD *)v7 + 2);
        if ( v14 == *((_QWORD *)v7 + 3) )
        {
          std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(
            (char *)v7 + 8,
            v14,
            &v24,
            &v21);
          v6 = v21;
        }
        else
        {
          *(_OWORD *)v14 = v10;
          *(_OWORD *)(v14 + 16) = v11;
          *(_QWORD *)&v25 = 0;
          *((_QWORD *)&v25 + 1) = 7;
          LOWORD(v24) = 0;
          *(_QWORD *)(v14 + 32) = v13;
          *((_QWORD *)v7 + 2) += 40LL;
        }
        std::wstring::_Tidy_deallocate(&v24);
        if ( v6 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 192LL))(v6, 1);
        v6 = 0;
        if ( *(_DWORD *)(a3 + 72) )
          break;
        if ( *(_DWORD *)a3 == 2 )
        {
LABEL_25:
          std::wstring::_Tidy_deallocate(&v19);
          goto LABEL_26;
        }
        if ( *(_DWORD *)a3 == 5 )
        {
          web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
          if ( !*(_DWORD *)(a3 + 72) )
          {
            std::wstring::_Tidy_deallocate(&v19);
            v19 = 0;
            *(_QWORD *)&v20 = 0;
            *((_QWORD *)&v20 + 1) = 7;
            LOWORD(v19) = 0;
            if ( *(_DWORD *)a3 == 7 )
              continue;
          }
        }
        break;
      }
    }
    std::wstring::_Tidy_deallocate(&v19);
    if ( !*(_DWORD *)(a3 + 72) )
    {
      v16 = web::json::details::json_error_category(v15);
      LODWORD(v22) = 5;
      *((_QWORD *)&v22 + 1) = v16;
      *(_OWORD *)(a3 + 72) = v22;
    }
    goto LABEL_23;
  }
LABEL_26:
  web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
  if ( *(_DWORD *)(a3 + 72) )
  {
LABEL_23:
    v17 = operator new(8u);
    v23 = v17;
    *v17 = &web::json::details::_Null::`vftable';
    *a2 = v17;
    (*(void (__fastcall **)(_OWORD *, __int64))(*(_QWORD *)v7 + 192LL))(v7, 1);
    return a2;
  }
  if ( !web::json::details::g_keep_json_object_unsorted )
    std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
      *((_QWORD *)v7 + 1),
      *((_QWORD *)v7 + 2),
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v7 + 2) - *((_QWORD *)v7 + 1)) >> 3),
      web::json::object::compare_with_key);
  *a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x180030358  mov     rax, rsp
0x18003035b  mov     [rax+20h], rbx
0x18003035f  push    rbp
0x180030360  push    rsi
0x180030361  push    rdi
0x180030362  push    r12
0x180030364  push    r13
0x180030366  push    r14
0x180030368  push    r15
0x18003036a  lea     rbp, [rax-5Fh]
0x18003036e  sub     rsp, 0B0h
0x180030375  movaps  xmmword ptr [rax-48h], xmm6
0x180030379  movaps  xmmword ptr [rax-58h], xmm7
0x18003037d  mov     rdi, r8
0x180030380  mov     rsi, rdx
0x180030383  mov     r13, rcx
0x180030386  mov     qword ptr [rbp+57h+var_98], rdx
0x18003038a  xor     ebx, ebx
0x18003038c  lea     ecx, [rbx+28h]; Size
0x18003038f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030394  mov     r14, rax
0x180030397  mov     qword ptr [rbp+57h+var_98], rax
0x18003039b  xorps   xmm0, xmm0
0x18003039e  xor     eax, eax
0x1800303a0  movups  xmmword ptr [r14], xmm0
0x1800303a4  movups  xmmword ptr [r14+10h], xmm0
0x1800303a9  mov     [r14+20h], rax
0x1800303ad  mov     al, cs:?g_keep_json_object_unsorted@details@json@web@@3_NA; bool web::json::details::g_keep_json_object_unsorted
0x1800303b3  lea     rcx, ??_7_Object@details@json@web@@6B@; const web::json::details::_Object::`vftable'
0x1800303ba  mov     [r14], rcx
0x1800303bd  lea     r12, [r14+8]
0x1800303c1  mov     [r12], rbx
0x1800303c5  mov     [r12+8], rbx
0x1800303ca  mov     [r12+10h], rbx
0x1800303cf  mov     [r12+18h], al
0x1800303d4  mov     [rbp+57h+var_88], r14
0x1800303d8  mov     rdx, rdi
0x1800303db  mov     rcx, r13
0x1800303de  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x1800303e3  cmp     [rdi+48h], ebx
0x1800303e6  jnz     loc_180030594
0x1800303ec  cmp     dword ptr [rdi], 2
0x1800303ef  jz      loc_1800305F7
0x1800303f5  xorps   xmm0, xmm0
0x1800303f8  movups  [rbp+57h+var_C0], xmm0
0x1800303fc  mov     qword ptr [rbp+57h+var_B0], rbx
0x180030400  mov     qword ptr [rbp+57h+var_B0+8], 7
0x180030408  mov     word ptr [rbp+57h+var_C0], bx
0x18003040c  cmp     dword ptr [rdi], 7
0x18003040f  jnz     loc_18003056D
0x180030415  lea     r15, [rdi+8]
0x180030419  lea     rax, [rbp+57h+var_C0]
0x18003041d  cmp     rax, r15
0x180030420  jz      short loc_18003044E
0x180030422  lea     rcx, [rbp+57h+var_C0]
0x180030426  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003042b  movups  xmm6, xmmword ptr [r15]
0x18003042f  movups  [rbp+57h+var_C0], xmm6
0x180030433  movups  xmm7, xmmword ptr [r15+10h]
0x180030438  movups  [rbp+57h+var_B0], xmm7
0x18003043c  mov     [r15+10h], rbx
0x180030440  mov     qword ptr [r15+18h], 7
0x180030448  mov     [r15], bx
0x18003044c  jmp     short loc_180030456
0x18003044e  movups  xmm7, [rbp+57h+var_B0]
0x180030452  movups  xmm6, [rbp+57h+var_C0]
0x180030456  mov     rdx, rdi
0x180030459  mov     rcx, r13
0x18003045c  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x180030461  cmp     [rdi+48h], ebx
0x180030464  jnz     loc_18003056D
0x18003046a  cmp     dword ptr [rdi], 6
0x18003046d  jnz     loc_1800305EE
0x180030473  mov     rdx, rdi
0x180030476  mov     rcx, r13
0x180030479  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18003047e  cmp     [rdi+48h], ebx
0x180030481  jnz     loc_18003056D
0x180030487  mov     r8, rdi
0x18003048a  lea     rdx, [rbp+57h+var_98]
0x18003048e  mov     rcx, r13
0x180030491  call    ?_ParseValue@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::_ParseValue(web::json::details::JSON_Parser<wchar_t>::Token &)
0x180030496  mov     rcx, [rax]
0x180030499  mov     [rax], rbx
0x18003049c  mov     [rbp+57h+var_A0], rcx
0x1800304a0  movups  [rbp+57h+var_78], xmm6
0x1800304a4  movups  [rbp+57h+var_68], xmm7
0x1800304a8  mov     qword ptr [rbp+57h+var_B0], rbx
0x1800304ac  mov     eax, 7
0x1800304b1  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1800304b5  mov     word ptr [rbp+57h+var_C0], bx
0x1800304b9  mov     rdx, [r12+8]
0x1800304be  cmp     rdx, [r12+10h]
0x1800304c3  jz      short loc_1800304E4
0x1800304c5  movups  xmmword ptr [rdx], xmm6
0x1800304c8  movups  xmmword ptr [rdx+10h], xmm7
0x1800304cc  mov     qword ptr [rbp+57h+var_68], rbx
0x1800304d0  mov     qword ptr [rbp+57h+var_68+8], rax
0x1800304d4  mov     word ptr [rbp+57h+var_78], bx
0x1800304d8  mov     [rdx+20h], rcx
0x1800304dc  add     qword ptr [r12+8], 28h ; '('
0x1800304e2  jmp     short loc_1800304F8
0x1800304e4  lea     r9, [rbp+57h+var_A0]
0x1800304e8  lea     r8, [rbp+57h+var_78]
0x1800304ec  mov     rcx, r12
0x1800304ef  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAVvalue@json@web@@@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(std::pair<std::wstring,web::json::value> * const,std::wstring &&,web::json::value &&)
0x1800304f4  mov     rbx, [rbp+57h+var_A0]
0x1800304f8  lea     rcx, [rbp+57h+var_78]
0x1800304fc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030501  nop
0x180030502  test    rbx, rbx
0x180030505  jz      short loc_18003051E
0x180030507  mov     rax, [rbx]
0x18003050a  mov     edx, 1
0x18003050f  mov     rcx, rbx
0x180030512  mov     rax, [rax+0C0h]
0x180030519  call    _guard_dispatch_icall
0x18003051e  xor     ebx, ebx
0x180030520  cmp     [rdi+48h], ebx
0x180030523  jnz     short loc_18003056D
0x180030525  cmp     dword ptr [rdi], 2
0x180030528  jz      loc_1800305EE
0x18003052e  cmp     dword ptr [rdi], 5
0x180030531  jnz     short loc_18003056D
0x180030533  mov     rdx, rdi
0x180030536  mov     rcx, r13
0x180030539  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18003053e  nop
0x18003053f  lea     rcx, [rbp+57h+var_C0]
0x180030543  cmp     [rdi+48h], ebx
0x180030546  jnz     short loc_180030571
0x180030548  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003054d  xorps   xmm0, xmm0
0x180030550  movups  [rbp+57h+var_C0], xmm0
0x180030554  mov     qword ptr [rbp+57h+var_B0], rbx
0x180030558  mov     qword ptr [rbp+57h+var_B0+8], 7
0x180030560  mov     word ptr [rbp+57h+var_C0], bx
0x180030564  cmp     dword ptr [rdi], 7
0x180030567  jz      loc_180030419
0x18003056d  lea     rcx, [rbp+57h+var_C0]
0x180030571  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030576  cmp     [rdi+48h], ebx
0x180030579  jnz     short loc_180030594
0x18003057b  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x180030580  mov     dword ptr [rbp+57h+var_98], 5
0x180030587  mov     qword ptr [rbp+57h+var_98+8], rax
0x18003058b  movups  xmm0, [rbp+57h+var_98]
0x18003058f  movdqu  xmmword ptr [rdi+48h], xmm0
0x180030594  mov     ecx, 8; Size
0x180030599  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003059e  mov     [rbp+57h+var_88], rax
0x1800305a2  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x1800305a9  mov     [rax], rcx
0x1800305ac  mov     [rsi], rax
0x1800305af  mov     rax, [r14]
0x1800305b2  mov     rax, [rax+0C0h]
0x1800305b9  mov     edx, 1
0x1800305be  mov     rcx, r14
0x1800305c1  call    _guard_dispatch_icall
0x1800305c6  mov     rax, rsi
0x1800305c9  lea     r11, [rsp+0E0h+var_30]
0x1800305d1  mov     rbx, [r11+58h]
0x1800305d5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800305da  movaps  xmm7, xmmword ptr [r11-20h]
0x1800305df  mov     rsp, r11
0x1800305e2  pop     r15
0x1800305e4  pop     r14
0x1800305e6  pop     r13
0x1800305e8  pop     r12
0x1800305ea  pop     rdi
0x1800305eb  pop     rsi
0x1800305ec  pop     rbp
0x1800305ed  retn
0x1800305ee  lea     rcx, [rbp+57h+var_C0]
0x1800305f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800305f7  mov     rdx, rdi
0x1800305fa  mov     rcx, r13
0x1800305fd  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x180030602  cmp     [rdi+48h], ebx
0x180030605  jz      short loc_18003062E
0x180030607  mov     ecx, 8; Size
0x18003060c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030611  mov     [rbp+57h+var_88], rax
0x180030615  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18003061c  mov     [rax], rcx
0x18003061f  mov     [rsi], rax
0x180030622  mov     rcx, [r14]
0x180030625  mov     rax, [rcx+0C0h]
0x18003062c  jmp     short loc_1800305B9
0x18003062e  cmp     cs:?g_keep_json_object_unsorted@details@json@web@@3_NA, bl; bool web::json::details::g_keep_json_object_unsorted
0x180030634  jnz     short loc_180030664
0x180030636  mov     rdx, [r12+8]
0x18003063b  mov     r8, rdx
0x18003063e  sub     r8, [r12]
0x180030642  sar     r8, 3
0x180030646  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180030650  imul    r8, rax
0x180030654  lea     r9, ?compare_with_key@object@json@web@@CA_NAEBU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; web::json::object::compare_with_key(std::pair<std::wstring,web::json::value> const &,std::wstring const &)
0x18003065b  mov     rcx, [r12]
0x18003065f  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z; std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,__int64,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x180030664  mov     [rsi], r14
0x180030667  jmp     loc_1800305C6
```
