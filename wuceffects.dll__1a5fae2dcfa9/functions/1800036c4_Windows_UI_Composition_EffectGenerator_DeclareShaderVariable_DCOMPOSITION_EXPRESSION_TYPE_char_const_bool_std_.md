# Windows::UI::Composition::EffectGenerator::DeclareShaderVariable(DCOMPOSITION_EXPRESSION_TYPE,char const *,bool,std::function<void (void const *,void *)>)

- ea: `0x1800036c4`
- end: `0x1800037fb`
- name: `?DeclareShaderVariable@EffectGenerator@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBD_NV?$function@$$A6AXPEBXPEAX@Z@6@@Z`
- size: `311`
- prototype: `__int64 __fastcall(unsigned int *, __int64, unsigned int, __int64, char, __int64)`
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001410`
- `0x180008220`
- `0x18001f220`
- `0x18001f800`
- `0x18001fc70`
- `0x180020150`
- `0x180020570`
- `0x180026770`
- `0x180027170`
- `0x180028920`

## callees

- `0x18000303c`
- `0x1800036c4`
- `0x180003804`
- `0x180003a98`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800037ed`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800037ed`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800037f4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800037f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UI::Composition::EffectGenerator::DeclareShaderVariable(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        char a5,
        __int64 a6)
{
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  __int64 (__fastcall ***v14)(_QWORD, _BYTE *); // rcx
  _BYTE *v15; // [rsp+30h] [rbp-69h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v17[56]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v18; // [rsp+88h] [rbp-11h]

  v15 = (_BYTE *)a2;
  v16[1] = a6;
  if ( a5 )
  {
    v15 = v17;
    v18 = 0;
    v14 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a6 + 56);
    if ( v14 )
      v18 = (**v14)(v14, v17);
    Windows::UI::Composition::EffectGenerator::DeclareDynamicShaderVariable((__int64)a1, a2, a3, a4, (__int64)v17);
  }
  else
  {
    v10 = *(_QWORD *)(*(_QWORD *)a1 + 48LL);
    v11 = a1[4];
    if ( (*(_QWORD *)(*(_QWORD *)a1 + 56LL) - v10) >> 3 <= v11 )
    {
      std::_Xout_of_range("invalid vector subscript");
      __debugbreak();
    }
    v15 = *(_BYTE **)(*(_QWORD *)(v10 + 8 * v11) + 24LL);
    v16[0] = v17;
    v12 = *(_QWORD *)(a6 + 56);
    if ( !v12 )
    {
      std::_Xbad_function_call();
      JUMPOUT(0x1800037FALL);
    }
    (*(void (__fastcall **)(__int64, _BYTE **, _QWORD *))(*(_QWORD *)v12 + 16LL))(v12, &v15, v16);
    Windows::UI::Composition::EffectGenerator::DeclareShaderConstant(a1, a2, a3, a4, v17);
  }
  std::_Func_class<void,void const *,void *>::_Tidy(a6);
  return a2;
}

```

## disassembly

```asm
0x1800036c4  push    rbp
0x1800036c6  push    rbx
0x1800036c7  push    rsi
0x1800036c8  push    rdi
0x1800036c9  push    r14
0x1800036cb  push    r15
0x1800036cd  lea     rbp, [rsp-1Fh]
0x1800036d2  sub     rsp, 0B8h
0x1800036d9  mov     rax, cs:__security_cookie
0x1800036e0  xor     rax, rsp
0x1800036e3  mov     [rbp+47h+var_40], rax
0x1800036e7  mov     r15, r9
0x1800036ea  mov     r14d, r8d
0x1800036ed  mov     rdi, rdx
0x1800036f0  mov     rsi, rcx
0x1800036f3  mov     [rbp+47h+var_B0], rdx
0x1800036f7  mov     rbx, [rbp+47h+arg_28]
0x1800036fb  mov     [rbp+47h+var_98], rbx
0x1800036ff  xor     r9d, r9d
0x180003702  cmp     [rbp+47h+arg_20], r9b
0x180003706  jnz     loc_1800037A2
0x18000370c  mov     rax, [rcx]
0x18000370f  mov     rdx, [rax+30h]
0x180003713  mov     r8d, [rcx+10h]
0x180003717  mov     rcx, [rax+38h]
0x18000371b  sub     rcx, rdx
0x18000371e  sar     rcx, 3
0x180003722  cmp     rcx, r8
0x180003725  jbe     loc_1800037E6
0x18000372b  mov     rax, [rdx+r8*8]
0x18000372f  mov     rcx, [rax+18h]
0x180003733  mov     [rbp+47h+var_B0], rcx
0x180003737  lea     rax, [rbp+47h+var_90]
0x18000373b  mov     [rbp+47h+var_A0], rax
0x18000373f  mov     rcx, [rbx+38h]
0x180003743  test    rcx, rcx
0x180003746  jz      loc_1800037F4
0x18000374c  mov     rax, [rcx]
0x18000374f  lea     r8, [rbp+47h+var_A0]
0x180003753  lea     rdx, [rbp+47h+var_B0]
0x180003757  mov     rax, [rax+10h]
0x18000375b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003760  lea     rax, [rbp+47h+var_90]
0x180003764  mov     [rsp+0E0h+var_C0], rax
0x180003769  mov     r9, r15
0x18000376c  mov     r8d, r14d
0x18000376f  mov     rdx, rdi
0x180003772  mov     rcx, rsi
0x180003775  call    ?DeclareShaderConstant@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDPEBX@Z; Windows::UI::Composition::EffectGenerator::DeclareShaderConstant(DCOMPOSITION_EXPRESSION_TYPE,char const *,void const *)
0x18000377a  nop
0x18000377b  mov     rcx, rbx
0x18000377e  call    ?_Tidy@?$_Func_class@XPEBXPEAX@std@@IEAAXXZ; std::_Func_class<void,void const *,void *>::_Tidy(void)
0x180003783  mov     rax, rdi
0x180003786  mov     rcx, [rbp+47h+var_40]
0x18000378a  xor     rcx, rsp; StackCookie
0x18000378d  call    __security_check_cookie
0x180003792  add     rsp, 0B8h
0x180003799  pop     r15
0x18000379b  pop     r14
0x18000379d  pop     rdi
0x18000379e  pop     rsi
0x18000379f  pop     rbx
0x1800037a0  pop     rbp
0x1800037a1  retn
0x1800037a2  lea     rax, [rbp+47h+var_90]
0x1800037a6  mov     [rbp+47h+var_B0], rax
0x1800037aa  mov     [rbp+47h+var_58], r9
0x1800037ae  mov     rcx, [rbx+38h]
0x1800037b2  test    rcx, rcx
0x1800037b5  jz      short loc_1800037CA
0x1800037b7  mov     rax, [rcx]
0x1800037ba  lea     rdx, [rbp+47h+var_90]
0x1800037be  mov     rax, [rax]
0x1800037c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c6  mov     [rbp+47h+var_58], rax
0x1800037ca  lea     rax, [rbp+47h+var_90]
0x1800037ce  mov     [rsp+0E0h+var_C0], rax
0x1800037d3  mov     r9, r15
0x1800037d6  mov     r8d, r14d
0x1800037d9  mov     rdx, rdi
0x1800037dc  mov     rcx, rsi
0x1800037df  call    ?DeclareDynamicShaderVariable@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDV?$function@$$A6AXPEBXPEAX@Z@6@@Z; Windows::UI::Composition::EffectGenerator::DeclareDynamicShaderVariable(DCOMPOSITION_EXPRESSION_TYPE,char const *,std::function<void (void const *,void *)>)
0x1800037e4  jmp     short loc_18000377B
0x1800037e6  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x1800037ed  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800037f3  int     3; Trap to Debugger
0x1800037f4  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
