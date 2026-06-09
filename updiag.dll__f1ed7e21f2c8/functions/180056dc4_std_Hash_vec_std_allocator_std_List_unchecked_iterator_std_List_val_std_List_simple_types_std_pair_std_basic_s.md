# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>)

- ea: `0x180056dc4`
- end: `0x180056ebe`
- name: `?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@2@@Z`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x1800301cc`
- `0x180038ddc`
- `0x180038ebc`
- `0x18003e240`
- `0x180046c14`
- `0x180046d0c`
- `0x180058170`
- `0x18005837c`
- `0x18005b290`
- `0x18005c5d8`
- `0x18005e34c`
- `0x18005e9c4`
- `0x18005ec60`
- `0x180069b90`
- `0x18006aee0`
- `0x18006b710`
- `0x18006bbe4`
- `0x18006e738`

## callees

- `0x180018f80`
- `0x180019058`
- `0x180056dc4`
- `0x18008ffd4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180056e76`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180056e76`

## pseudocode

```c
unsigned __int64 *__fastcall __Assign_grow____Hash_vec_V__allocator_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___std___std___std__QEAAX_KV___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___2__Z(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rdi
  __int64 v6; // rcx
  __int64 v7; // r14
  unsigned __int64 *v8; // rax
  _QWORD *v9; // rcx
  unsigned __int64 *v10; // rdi
  __int64 v11; // rdx
  unsigned __int64 *result; // rax
  unsigned __int64 v13; // rcx

  v3 = *(_QWORD *)(a1 + 8);
  v6 = v3 - *(_QWORD *)a1;
  if ( v6 >> 3 >= a2 )
  {
    result = 0;
    v13 = (unsigned __int64)(v6 + 7) >> 3;
    if ( *(_QWORD *)a1 > v3 )
      v13 = 0;
    if ( v13 )
    {
      result = (unsigned __int64 *)a3;
      memset64(*(void **)a1, a3, v13);
    }
  }
  else
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
    v7 = a2;
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(8 * a2);
    v9 = *(_QWORD **)a1;
    v10 = v8;
    v11 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
    if ( v11 )
    {
      if ( (unsigned __int64)(8 * v11) >= 0x1000 )
      {
        if ( (unsigned __int64)v9 - *(v9 - 1) - 8 > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
        v9 = (_QWORD *)*(v9 - 1);
      }
      operator delete(v9);
    }
    result = &v10[v7];
    *(_QWORD *)a1 = v10;
    *(_QWORD *)(a1 + 8) = &v10[v7];
    *(_QWORD *)(a1 + 16) = &v10[v7];
    while ( v10 != result )
      *v10++ = a3;
  }
  return result;
}

```

## disassembly

```asm
0x180056dc4  mov     [rsp+arg_10], rbx
0x180056dc9  push    rsi
0x180056dca  push    rdi
0x180056dcb  push    r14
0x180056dcd  sub     rsp, 30h
0x180056dd1  mov     rdi, [rcx+8]
0x180056dd5  mov     rsi, rcx
0x180056dd8  mov     rcx, rdi
0x180056ddb  mov     rbx, r8
0x180056dde  sub     rcx, [rsi]
0x180056de1  mov     rax, rcx
0x180056de4  sar     rax, 3
0x180056de8  cmp     rax, rdx
0x180056deb  jnb     loc_180056E8B
0x180056df1  mov     rax, 1FFFFFFFFFFFFFFFh
0x180056dfb  cmp     rdx, rax
0x180056dfe  ja      loc_180056EB8
0x180056e04  lea     r14, ds:0[rdx*8]
0x180056e0c  mov     rcx, r14
0x180056e0f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180056e14  mov     rcx, [rsi]
0x180056e17  mov     rdi, rax
0x180056e1a  mov     rdx, [rsi+10h]
0x180056e1e  xor     eax, eax
0x180056e20  sub     rdx, rcx
0x180056e23  sar     rdx, 3
0x180056e27  test    rdx, rdx
0x180056e2a  jz      short loc_180056E56
0x180056e2c  shl     rdx, 3
0x180056e30  cmp     rdx, 1000h
0x180056e37  jb      short loc_180056E51
0x180056e39  mov     r8, [rcx-8]
0x180056e3d  add     rdx, 27h ; '''; unsigned __int64
0x180056e41  sub     rcx, r8
0x180056e44  sub     rcx, 8
0x180056e48  cmp     rcx, 1Fh
0x180056e4c  ja      short loc_180056E67
0x180056e4e  mov     rcx, r8; void *
0x180056e51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180056e56  lea     rax, [r14+rdi]
0x180056e5a  mov     [rsi], rdi
0x180056e5d  mov     [rsi+8], rax
0x180056e61  mov     [rsi+10h], rax
0x180056e65  jmp     short loc_180056E84
0x180056e67  xor     r9d, r9d; LineNo
0x180056e6a  mov     [rsp+48h+Reserved], rax; Reserved
0x180056e6f  xor     r8d, r8d; FileName
0x180056e72  xor     edx, edx; FunctionName
0x180056e74  xor     ecx, ecx; Expression
0x180056e76  call    cs:__imp__invoke_watson
0x180056e7d  mov     [rdi], rbx
0x180056e80  add     rdi, 8
0x180056e84  cmp     rdi, rax
0x180056e87  jnz     short loc_180056E7D
0x180056e89  jmp     short loc_180056EAA
0x180056e8b  add     rcx, 7
0x180056e8f  xor     eax, eax
0x180056e91  shr     rcx, 3
0x180056e95  cmp     [rsi], rdi
0x180056e98  cmova   rcx, rax
0x180056e9c  test    rcx, rcx
0x180056e9f  jz      short loc_180056EAA
0x180056ea1  mov     rdi, [rsi]
0x180056ea4  mov     rax, rbx
0x180056ea7  rep stosq
0x180056eaa  mov     rbx, [rsp+48h+arg_10]
0x180056eaf  add     rsp, 30h
0x180056eb3  pop     r14
0x180056eb5  pop     rdi
0x180056eb6  pop     rsi
0x180056eb7  retn
0x180056eb8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
