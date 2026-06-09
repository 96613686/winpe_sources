# Windows::UI::Composition::EffectGenerator::DeclareShaderVariableForProperty(uint)

- ea: `0x180002cd0`
- end: `0x180002de5`
- name: `?DeclareShaderVariableForProperty@EffectGenerator@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@Z`
- size: `277`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned int)`
- caller_count: `16`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001950`
- `0x180001da0`
- `0x180002080`
- `0x180008550`
- `0x1800088a0`
- `0x18001f800`
- `0x18001fc70`
- `0x180020150`
- `0x180020570`
- `0x180025e20`
- `0x180026c40`
- `0x180027920`
- `0x180027ad0`
- `0x180027cd0`
- `0x180027de0`
- `0x180028ba0`

## callees

- `0x180002cd0`
- `0x180002dec`
- `0x18000303c`
- `0x180003804`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180002dde`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180002dde`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectGenerator::DeclareShaderVariableForProperty(
        __int64 *a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // r12
  __int64 v10; // r14
  __int64 v11; // rdi
  __int64 DCompExpressionTypeFromFloatCount; // r8
  __int64 v13; // r9
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int64 (__fastcall **v17)(); // [rsp+40h] [rbp-40h] BYREF
  __int128 v18; // [rsp+48h] [rbp-38h]
  __int128 v19; // [rsp+58h] [rbp-28h]
  __int64 (__fastcall ***v20)(); // [rsp+78h] [rbp-8h]
  int v21; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v22; // [rsp+D8h] [rbp+58h] BYREF

  v4 = a3;
  v5 = *((unsigned int *)a1 + 4);
  v7 = *a1;
  if ( (__int64)(*(_QWORD *)(v7 + 56) - *(_QWORD *)(v7 + 48)) >> 3 <= v5 )
  {
    std::_Xout_of_range("invalid vector subscript");
    JUMPOUT(0x180002DE4LL);
  }
  _mm_lfence();
  v8 = *(_QWORD *)(v7 + 48);
  v21 = 0;
  v22 = 0;
  v9 = *(_QWORD **)(v8 + 8 * v5);
  (*(void (__fastcall **)(_QWORD, int *, __int64 *))(*(_QWORD *)*v9 + 144LL))(*v9, &v21, &v22);
  v10 = v22;
  v11 = 32LL * (unsigned int)v4;
  DCompExpressionTypeFromFloatCount = (unsigned int)Windows::UI::Composition::GetDCompExpressionTypeFromFloatCount(*(unsigned int *)(v11 + v22 + 20));
  v13 = *(_QWORD *)(v11 + v10);
  if ( *(_WORD *)(v9[4] + 2 * v4) )
  {
    v15 = *(_OWORD *)(v11 + v10);
    v16 = *(_OWORD *)(v11 + v10 + 16);
    v17 = off_18002F000;
    v20 = &v17;
    v18 = v15;
    v19 = v16;
    Windows::UI::Composition::EffectGenerator::DeclareDynamicShaderVariable(
      a1,
      a2,
      DCompExpressionTypeFromFloatCount,
      v13,
      &v17);
  }
  else
  {
    Windows::UI::Composition::EffectGenerator::DeclareShaderConstant(
      a1,
      a2,
      DCompExpressionTypeFromFloatCount,
      v13,
      v9[3] + *(unsigned int *)(v11 + v10 + 8));
  }
  return a2;
}

```

## disassembly

```asm
0x180002cd0  mov     [rsp-38h+arg_8], rbx
0x180002cd5  push    rbp
0x180002cd6  push    rsi
0x180002cd7  push    rdi
0x180002cd8  push    r12
0x180002cda  push    r13
0x180002cdc  push    r14
0x180002cde  push    r15
0x180002ce0  mov     rbp, rsp
0x180002ce3  sub     rsp, 80h
0x180002cea  mov     rsi, rdx
0x180002ced  mov     ebx, r8d
0x180002cf0  mov     edx, [rcx+10h]
0x180002cf3  mov     r15, rcx
0x180002cf6  mov     rcx, [rcx]
0x180002cf9  xor     r13d, r13d
0x180002cfc  mov     rax, [rcx+38h]
0x180002d00  sub     rax, [rcx+30h]
0x180002d04  sar     rax, 3
0x180002d08  cmp     rax, rdx
0x180002d0b  jbe     loc_180002DD7
0x180002d11  lfence
0x180002d14  mov     rax, [rcx+30h]
0x180002d18  lea     r8, [rbp+arg_18]
0x180002d1c  mov     [rbp+arg_0], r13d
0x180002d20  mov     [rbp+arg_18], r13
0x180002d24  mov     r12, [rax+rdx*8]
0x180002d28  lea     rdx, [rbp+arg_0]
0x180002d2c  mov     rcx, [r12]
0x180002d30  mov     rax, [rcx]
0x180002d33  mov     rax, [rax+90h]
0x180002d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d3f  mov     r14, [rbp+arg_18]
0x180002d43  mov     edi, ebx
0x180002d45  shl     rdi, 5
0x180002d49  mov     ecx, [rdi+r14+14h]
0x180002d4e  call    ?GetDCompExpressionTypeFromFloatCount@Composition@UI@Windows@@YA?AW4DCOMPOSITION_EXPRESSION_TYPE@@I@Z; Windows::UI::Composition::GetDCompExpressionTypeFromFloatCount(uint)
0x180002d53  mov     rcx, [r12+20h]
0x180002d58  mov     r8d, eax
0x180002d5b  mov     r9, [rdi+r14]
0x180002d5f  mov     rdx, rsi
0x180002d62  cmp     [rcx+rbx*2], r13w
0x180002d67  jnz     short loc_180002D9E
0x180002d69  mov     ecx, [rdi+r14+8]
0x180002d6e  add     rcx, [r12+18h]
0x180002d73  mov     [rsp+80h+var_60], rcx
0x180002d78  mov     rcx, r15
0x180002d7b  call    ?DeclareShaderConstant@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDPEBX@Z; Windows::UI::Composition::EffectGenerator::DeclareShaderConstant(DCOMPOSITION_EXPRESSION_TYPE,char const *,void const *)
0x180002d80  mov     rbx, [rsp+80h+arg_8]
0x180002d88  mov     rax, rsi
0x180002d8b  add     rsp, 80h
0x180002d92  pop     r15
0x180002d94  pop     r14
0x180002d96  pop     r13
0x180002d98  pop     r12
0x180002d9a  pop     rdi
0x180002d9b  pop     rsi
0x180002d9c  pop     rbp
0x180002d9d  retn
0x180002d9e  movups  xmm0, xmmword ptr [rdi+r14]
0x180002da3  lea     rcx, off_18002F000
0x180002daa  movups  xmm1, xmmword ptr [rdi+r14+10h]
0x180002db0  mov     [rbp+var_40], rcx
0x180002db4  lea     rcx, [rbp+var_40]
0x180002db8  mov     [rbp+var_8], rcx
0x180002dbc  lea     rcx, [rbp+var_40]
0x180002dc0  mov     [rsp+80h+var_60], rcx
0x180002dc5  mov     rcx, r15
0x180002dc8  movups  [rbp+var_38], xmm0
0x180002dcc  movups  [rbp+var_28], xmm1
0x180002dd0  call    ?DeclareDynamicShaderVariable@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDV?$function@$$A6AXPEBXPEAX@Z@6@@Z; Windows::UI::Composition::EffectGenerator::DeclareDynamicShaderVariable(DCOMPOSITION_EXPRESSION_TYPE,char const *,std::function<void (void const *,void *)>)
0x180002dd5  jmp     short loc_180002D80
0x180002dd7  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180002dde  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
