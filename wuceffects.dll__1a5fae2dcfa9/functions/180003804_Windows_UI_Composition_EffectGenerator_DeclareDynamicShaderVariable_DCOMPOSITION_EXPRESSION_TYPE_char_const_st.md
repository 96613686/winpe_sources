# Windows::UI::Composition::EffectGenerator::DeclareDynamicShaderVariable(DCOMPOSITION_EXPRESSION_TYPE,char const *,std::function<void (void const *,void *)>)

- ea: `0x180003804`
- end: `0x180003a92`
- name: `?DeclareDynamicShaderVariable@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDV?$function@$$A6AXPEBXPEAX@Z@6@@Z`
- size: `654`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002cd0`
- `0x1800036c4`

## callees

- `0x180002e78`
- `0x180003804`
- `0x180003a98`
- `0x180003ad0`
- `0x180003b7c`
- `0x180003c28`
- `0x180006e1c`
- `0x180007ee4`
- `0x1800090a0`
- `0x18001afe4`
- `0x180021060`
- `0x180026144`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180003a76`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180003a84`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180003a76`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180003a84`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180003a8b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180003a8b`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectGenerator::DeclareDynamicShaderVariable(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5)
{
  __int64 v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // r13
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, _BYTE *); // rcx
  _BYTE *v17; // rdx
  __int64 v18; // rbx
  _DWORD *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  void *v22; // rax
  void *v23; // rax
  void *v24; // rax
  char *p_Src; // rax
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 Src; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v30; // [rsp+60h] [rbp-A0h]
  _QWORD v31[2]; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+90h] [rbp-70h] BYREF
  int v33; // [rsp+94h] [rbp-6Ch]
  _BYTE v34[56]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-30h]
  _BYTE v36[56]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v37; // [rsp+118h] [rbp+18h]

  v28[0] = a2;
  v28[2] = a5;
  v9 = *(_QWORD *)(*(_QWORD *)a1 + 48LL);
  v10 = *(unsigned int *)(a1 + 16);
  if ( (*(_QWORD *)(*(_QWORD *)a1 + 56LL) - v9) >> 3 <= v10 )
  {
    std::_Xout_of_range("invalid vector subscript");
LABEL_17:
    std::_Xout_of_range("invalid vector subscript");
    __debugbreak();
  }
  v11 = *(_QWORD *)(v9 + 8 * v10);
  LODWORD(v27) = 0;
  Windows::UI::Composition::EffectGenerator::AllocateConstantBufferField(a1, (__int64)v31, a3, a4, &v27);
  v12 = *(_QWORD *)(a1 + 8);
  v13 = *(_QWORD *)(v12 + 64);
  if ( *(_QWORD *)(v12 + 72) == v13 )
    goto LABEL_17;
  v14 = v27;
  v27 = v13 + (unsigned int)v27;
  v28[0] = *(_QWORD *)(v11 + 24);
  v15 = *(_QWORD *)(a5 + 56);
  if ( !v15 )
  {
    std::_Xbad_function_call();
    JUMPOUT(0x180003A91LL);
  }
  (*(void (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v15 + 16LL))(v15, v28, &v27);
  v35 = 0;
  v32 = *(_DWORD *)(a1 + 16);
  v37 = 0;
  v16 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a5 + 56);
  if ( v16 )
    v37 = (_BYTE *)(**v16)(v16, v36);
  std::_Func_class<void,void const *,void *>::_Swap(v36, v34);
  if ( v37 )
  {
    v17 = v36;
    LOBYTE(v17) = v37 != v36;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v37 + 32LL))(v37, v17);
  }
  v33 = v14;
  v18 = *(_QWORD *)(a1 + 8);
  v19 = *(_DWORD **)(v18 + 48);
  if ( v19 == *(_DWORD **)(v18 + 56) )
  {
    std::vector<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater>::_Emplace_reallocate<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater &>(
      v18 + 40,
      v19,
      &v32);
  }
  else
  {
    *v19 = v32;
    v19[1] = v33;
    std::function<void (void const *,void *)>::function<void (void const *,void *)>(v19 + 2, v34);
    *(_QWORD *)(v18 + 48) += 72LL;
  }
  Windows::UI::Composition::PixelShaderSourceBuilder::GetHlslTypeName(a3, 0);
  Src = 0;
  v30 = 0;
  v20 = std::string::_Construct_empty(&Src);
  v21 = -1;
  do
    ++v21;
  while ( *(_BYTE *)(v20 + v21) );
  v22 = (void *)std::string::_Append<char>(&Src);
  v23 = (void *)std::string::_Append<char>(v22);
  v24 = (void *)std::string::_Append<char>(v23);
  std::string::_Append<char>(v24);
  p_Src = (char *)&Src;
  if ( *((_QWORD *)&v30 + 1) > 0xFu )
    p_Src = (char *)Src;
  Windows::UI::Composition::PixelShaderSourceBuilder::DeclareLocal(a1 + 88, a2, a3, a4, p_Src);
  std::string::~string(&Src);
  std::_Func_class<void,void const *,void *>::_Tidy(v34);
  std::string::~string(v31);
  std::_Func_class<void,void const *,void *>::_Tidy(a5);
  return a2;
}

```

## disassembly

```asm
0x180003804  push    rbp
0x180003806  push    rbx
0x180003807  push    rsi
0x180003808  push    rdi
0x180003809  push    r12
0x18000380b  push    r13
0x18000380d  push    r14
0x18000380f  push    r15
0x180003811  lea     rbp, [rsp-38h]
0x180003816  sub     rsp, 138h
0x18000381d  mov     rax, cs:__security_cookie
0x180003824  xor     rax, rsp
0x180003827  mov     [rbp+70h+var_50], rax
0x18000382b  mov     r12, r9
0x18000382e  mov     r14d, r8d
0x180003831  mov     r15, rdx
0x180003834  mov     rdi, rcx
0x180003837  mov     [rsp+170h+var_138], rdx
0x18000383c  mov     rsi, [rbp+70h+arg_20]
0x180003843  mov     [rsp+170h+var_128], rsi
0x180003848  mov     rax, [rcx]
0x18000384b  mov     rdx, [rax+30h]
0x18000384f  mov     r8d, [rcx+10h]
0x180003853  mov     rcx, [rax+38h]
0x180003857  sub     rcx, rdx
0x18000385a  sar     rcx, 3
0x18000385e  cmp     rcx, r8
0x180003861  jbe     loc_180003A6F
0x180003867  mov     r13, [rdx+r8*8]
0x18000386b  mov     dword ptr [rsp+170h+var_140], 0
0x180003873  lea     rax, [rsp+170h+var_140]
0x180003878  mov     [rsp+170h+var_150], rax
0x18000387d  mov     r8d, r14d
0x180003880  lea     rdx, [rsp+170h+var_100]
0x180003885  mov     rcx, rdi
0x180003888  call    ?AllocateConstantBufferField@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDPEAI@Z; Windows::UI::Composition::EffectGenerator::AllocateConstantBufferField(DCOMPOSITION_EXPRESSION_TYPE,char const *,uint *)
0x18000388d  nop
0x18000388e  mov     rax, [rdi+8]
0x180003892  mov     rcx, [rax+40h]
0x180003896  cmp     [rax+48h], rcx
0x18000389a  jz      loc_180003A7D
0x1800038a0  mov     ebx, dword ptr [rsp+170h+var_140]
0x1800038a4  lea     rax, [rcx+rbx]
0x1800038a8  mov     [rsp+170h+var_140], rax
0x1800038ad  mov     rax, [r13+18h]
0x1800038b1  mov     [rsp+170h+var_138], rax
0x1800038b6  mov     rcx, [rsi+38h]
0x1800038ba  xor     r13d, r13d
0x1800038bd  test    rcx, rcx
0x1800038c0  jz      loc_180003A8B
0x1800038c6  mov     rax, [rcx]
0x1800038c9  lea     r8, [rsp+170h+var_140]
0x1800038ce  lea     rdx, [rsp+170h+var_138]
0x1800038d3  mov     rax, [rax+10h]
0x1800038d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038dc  mov     [rbp+70h+var_A0], r13
0x1800038e0  mov     eax, [rdi+10h]
0x1800038e3  mov     [rbp+70h+var_E0], eax
0x1800038e6  mov     [rbp+70h+var_58], r13
0x1800038ea  mov     rcx, [rsi+38h]
0x1800038ee  test    rcx, rcx
0x1800038f1  jz      short loc_180003906
0x1800038f3  mov     rax, [rcx]
0x1800038f6  lea     rdx, [rbp+70h+var_90]
0x1800038fa  mov     rax, [rax]
0x1800038fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003902  mov     [rbp+70h+var_58], rax
0x180003906  lea     rdx, [rbp+70h+var_D8]
0x18000390a  lea     rcx, [rbp+70h+var_90]
0x18000390e  call    ?_Swap@?$_Func_class@XPEBXPEAX@std@@IEAAXAEAV12@@Z; std::_Func_class<void,void const *,void *>::_Swap(std::_Func_class<void,void const *,void *> &)
0x180003913  mov     rcx, [rbp+70h+var_58]
0x180003917  test    rcx, rcx
0x18000391a  jz      short loc_180003932
0x18000391c  mov     rax, [rcx]
0x18000391f  lea     rdx, [rbp+70h+var_90]
0x180003923  cmp     rcx, rdx
0x180003926  setnz   dl
0x180003929  mov     rax, [rax+20h]
0x18000392d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003932  mov     [rbp+70h+var_DC], ebx
0x180003935  mov     rbx, [rdi+8]
0x180003939  mov     rdx, [rbx+30h]
0x18000393d  cmp     rdx, [rbx+38h]
0x180003941  jnz     loc_180003A4D
0x180003947  lea     r8, [rbp+70h+var_E0]
0x18000394b  lea     rcx, [rbx+28h]
0x18000394f  call    ??$_Emplace_reallocate@AEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@?$vector@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@QEAU23456@AEAU23456@@Z; std::vector<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater>::_Emplace_reallocate<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater &>(Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater * const,Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater &)
0x180003954  xor     edx, edx
0x180003956  mov     ecx, r14d
0x180003959  call    ?GetHlslTypeName@PixelShaderSourceBuilder@Composition@UI@Windows@@SAPEBDW4DCOMPOSITION_EXPRESSION_TYPE@@_N@Z; Windows::UI::Composition::PixelShaderSourceBuilder::GetHlslTypeName(DCOMPOSITION_EXPRESSION_TYPE,bool)
0x18000395e  xorps   xmm0, xmm0
0x180003961  movups  [rsp+170h+Src], xmm0
0x180003966  xorps   xmm1, xmm1
0x180003969  movdqu  [rsp+170h+var_110], xmm1
0x18000396f  lea     rcx, [rsp+170h+Src]
0x180003974  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x180003979  nop
0x18000397a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000397e  inc     r8
0x180003981  cmp     [rax+r8], r13b
0x180003985  jnz     short loc_18000397E
0x180003987  mov     rdx, rax
0x18000398a  lea     rcx, [rsp+170h+Src]; Src
0x18000398f  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180003994  mov     ebx, 1
0x180003999  mov     r8d, ebx
0x18000399c  lea     rdx, asc_180033E94; "("
0x1800039a3  mov     rcx, rax; Src
0x1800039a6  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800039ab  lea     rdx, [rsp+170h+var_100]
0x1800039b0  cmp     [rbp+70h+var_E8], 0Fh
0x1800039b5  cmova   rdx, [rsp+170h+var_100]
0x1800039bb  mov     r8, [rbp+70h+var_F0]
0x1800039bf  mov     rcx, rax; Src
0x1800039c2  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800039c7  mov     r8d, ebx
0x1800039ca  lea     rdx, asc_180034140; ")"
0x1800039d1  mov     rcx, rax; Src
0x1800039d4  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800039d9  lea     rax, [rsp+170h+Src]
0x1800039de  cmp     qword ptr [rsp+170h+var_110+8], 0Fh
0x1800039e4  cmova   rax, qword ptr [rsp+170h+Src]
0x1800039ea  lea     rcx, [rdi+58h]; int
0x1800039ee  mov     [rsp+170h+var_150], rax; char *
0x1800039f3  mov     r9, r12; int
0x1800039f6  mov     r8d, r14d; int
0x1800039f9  mov     rdx, r15; int
0x1800039fc  call    ?DeclareLocal@PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBD1@Z; Windows::UI::Composition::PixelShaderSourceBuilder::DeclareLocal(DCOMPOSITION_EXPRESSION_TYPE,char const *,char const *)
0x180003a01  nop
0x180003a02  lea     rcx, [rsp+170h+Src]; void *
0x180003a07  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180003a0c  nop
0x180003a0d  lea     rcx, [rbp+70h+var_D8]
0x180003a11  call    ?_Tidy@?$_Func_class@XPEBXPEAX@std@@IEAAXXZ; std::_Func_class<void,void const *,void *>::_Tidy(void)
0x180003a16  nop
0x180003a17  lea     rcx, [rsp+170h+var_100]; void *
0x180003a1c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180003a21  nop
0x180003a22  mov     rcx, rsi
0x180003a25  call    ?_Tidy@?$_Func_class@XPEBXPEAX@std@@IEAAXXZ; std::_Func_class<void,void const *,void *>::_Tidy(void)
0x180003a2a  mov     rax, r15
0x180003a2d  mov     rcx, [rbp+70h+var_50]
0x180003a31  xor     rcx, rsp; StackCookie
0x180003a34  call    __security_check_cookie
0x180003a39  add     rsp, 138h
0x180003a40  pop     r15
0x180003a42  pop     r14
0x180003a44  pop     r13
0x180003a46  pop     r12
0x180003a48  pop     rdi
0x180003a49  pop     rsi
0x180003a4a  pop     rbx
0x180003a4b  pop     rbp
0x180003a4c  retn
0x180003a4d  mov     eax, [rbp+70h+var_E0]
0x180003a50  mov     [rdx], eax
0x180003a52  mov     eax, [rbp+70h+var_DC]
0x180003a55  mov     [rdx+4], eax
0x180003a58  lea     rcx, [rdx+8]
0x180003a5c  lea     rdx, [rbp+70h+var_D8]
0x180003a60  call    ??0?$function@$$A6AXPEBXPEAX@Z@std@@QEAA@AEBV01@@Z; std::function<void (void const *,void *)>::function<void (void const *,void *)>(std::function<void (void const *,void *)> const &)
0x180003a65  add     qword ptr [rbx+30h], 48h ; 'H'
0x180003a6a  jmp     loc_180003954
0x180003a6f  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180003a76  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180003a7c  nop
0x180003a7d  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180003a84  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180003a8a  int     3; Trap to Debugger
0x180003a8b  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
