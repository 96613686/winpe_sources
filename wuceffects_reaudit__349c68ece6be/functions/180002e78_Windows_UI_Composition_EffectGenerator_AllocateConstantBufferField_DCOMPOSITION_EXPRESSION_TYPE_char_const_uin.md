# Windows::UI::Composition::EffectGenerator::AllocateConstantBufferField(DCOMPOSITION_EXPRESSION_TYPE,char const *,uint *)

- ea: `0x180002e78`
- end: `0x180003035`
- name: `?AllocateConstantBufferField@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDPEAI@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003804`

## callees

- `0x180002e78`
- `0x180003508`
- `0x180003560`
- `0x1800035a0`
- `0x180008730`
- `0x18000ad40`
- `0x180021ce0`
- `0x180021cec`
- `0x1800261c0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000301b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000301b`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectGenerator::AllocateConstantBufferField(
        int a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        _DWORD *a5)
{
  unsigned int ExpressionTypeChannelCount; // eax
  __int64 v7; // r9
  __int64 v8; // rbp
  unsigned __int64 v9; // rdi
  __int64 v10; // rsi
  _BYTE *v11; // rbx
  _BYTE *v12; // rcx
  __int64 v13; // r14
  unsigned __int64 v14; // r15
  SIZE_T v15; // rdi
  char *v16; // rbx
  _BYTE *v18; // rax
  _BYTE v19[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v20[17]; // [rsp+34h] [rbp-44h] BYREF

  ExpressionTypeChannelCount = GetExpressionTypeChannelCount(a3);
  v8 = ExpressionTypeChannelCount;
  if ( ExpressionTypeChannelCount == 1 )
  {
    v9 = 4;
  }
  else
  {
    v9 = 16;
    if ( ExpressionTypeChannelCount == 2 )
      v9 = 8;
  }
  v10 = *(_QWORD *)(v7 + 8) + 64LL;
  while ( 1 )
  {
    v11 = *(_BYTE **)(v10 + 8);
    v12 = *(_BYTE **)v10;
    if ( !((unsigned __int64)&v11[-*(_QWORD *)v10] % v9) )
      break;
    v19[0] = 0;
    if ( v11 == *(_BYTE **)(v10 + 16) )
    {
      std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(v10, v11, v19);
    }
    else
    {
      *v11 = 0;
      ++*(_QWORD *)(v10 + 8);
    }
  }
  v13 = v11 - v12;
  v14 = (unsigned __int64)&v11[4 * v8 - (_QWORD)v12];
  if ( v14 < v11 - v12 )
  {
    v18 = &v11[4 * v8];
LABEL_17:
    *(_QWORD *)(v10 + 8) = v18;
    goto LABEL_10;
  }
  if ( v14 <= v11 - v12 )
    goto LABEL_10;
  if ( v14 <= *(_QWORD *)(v10 + 16) - (_QWORD)v12 )
  {
    memset_0(*(void **)(v10 + 8), 0, 4 * v8);
    v18 = &v11[4 * v8];
    goto LABEL_17;
  }
  if ( v14 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v15 = std::vector<unsigned char>::_Calculate_growth(v10, &v11[4 * v8 - (_QWORD)v12]);
  v16 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v15);
  memset_0(&v16[v13], 0, 4 * v8);
  memmove_0(v16, *(const void **)v10, *(_QWORD *)(v10 + 8) - *(_QWORD *)v10);
  std::vector<unsigned char>::_Change_array(v10, v16, v14, v15);
LABEL_10:
  *a5 = v13;
  v20[0] = (unsigned int)v13 >> 2;
  Windows::UI::Composition::PixelShaderSourceBuilder::DeclareConstantBufferField(a1 + 88, a2, a4, a3, (__int64)v20);
  return a2;
}

```

## disassembly

```asm
0x180002e78  mov     rax, rsp
0x180002e7b  mov     [rax+10h], rbx
0x180002e7f  mov     [rax+20h], r9
0x180002e83  mov     [rax+18h], r8d
0x180002e87  mov     [rax+8], rcx
0x180002e8b  push    rbp
0x180002e8c  push    rsi
0x180002e8d  push    rdi
0x180002e8e  push    r12
0x180002e90  push    r13
0x180002e92  push    r14
0x180002e94  push    r15
0x180002e96  sub     rsp, 40h
0x180002e9a  mov     r9, rcx
0x180002e9d  mov     r13, rdx
0x180002ea0  mov     ecx, r8d
0x180002ea3  xor     r14d, r14d
0x180002ea6  call    ?GetExpressionTypeChannelCount@@YAIW4DCOMPOSITION_EXPRESSION_TYPE@@@Z; GetExpressionTypeChannelCount(DCOMPOSITION_EXPRESSION_TYPE)
0x180002eab  mov     ebp, eax
0x180002ead  cmp     eax, 1
0x180002eb0  jnz     loc_180002FC8
0x180002eb6  lea     edi, [rax+3]
0x180002eb9  mov     rsi, [r9+8]
0x180002ebd  add     rsi, 40h ; '@'
0x180002ec1  mov     rbx, [rsi+8]
0x180002ec5  xor     edx, edx
0x180002ec7  mov     rcx, [rsi]
0x180002eca  mov     rax, rbx
0x180002ecd  sub     rax, rcx
0x180002ed0  div     rdi
0x180002ed3  test    rdx, rdx
0x180002ed6  jnz     loc_180002FDB
0x180002edc  lea     r12, ds:0[rbp*4]
0x180002ee4  mov     r14, rbx
0x180002ee7  mov     r15, r12
0x180002eea  sub     r14, rcx
0x180002eed  sub     r15, rcx
0x180002ef0  add     r15, rbx
0x180002ef3  cmp     r15, r14
0x180002ef6  jb      loc_180002FF2
0x180002efc  jbe     short loc_180002F6B
0x180002efe  mov     rax, [rsi+10h]
0x180002f02  sub     rax, rcx
0x180002f05  cmp     r15, rax
0x180002f08  jbe     loc_180003022
0x180002f0e  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002f18  cmp     r15, rax
0x180002f1b  ja      loc_180003014
0x180002f21  mov     rdx, r15
0x180002f24  mov     rcx, rsi
0x180002f27  call    ?_Calculate_growth@?$vector@EV?$allocator@E@std@@@std@@AEBA_K_K@Z; std::vector<uchar>::_Calculate_growth(unsigned __int64)
0x180002f2c  mov     rcx, rax; dwBytes
0x180002f2f  mov     rdi, rax
0x180002f32  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180002f37  mov     r8, r12; Size
0x180002f3a  xor     edx, edx; Val
0x180002f3c  mov     rbx, rax
0x180002f3f  lea     rcx, [r14+rax]; void *
0x180002f43  call    memset_0
0x180002f48  mov     r8, [rsi+8]
0x180002f4c  mov     rcx, rbx; void *
0x180002f4f  sub     r8, [rsi]; Size
0x180002f52  mov     rdx, [rsi]; Src
0x180002f55  call    memmove_0
0x180002f5a  mov     r9, rdi
0x180002f5d  mov     r8, r15
0x180002f60  mov     rdx, rbx
0x180002f63  mov     rcx, rsi
0x180002f66  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x180002f6b  mov     rax, [rsp+78h+arg_20]
0x180002f73  mov     rdx, r13
0x180002f76  mov     rcx, [rsp+78h+arg_0]
0x180002f7e  mov     r9d, [rsp+78h+arg_10]
0x180002f86  add     rcx, 58h ; 'X'
0x180002f8a  mov     r8, [rsp+78h+arg_18]
0x180002f92  mov     [rax], r14d
0x180002f95  lea     rax, [rsp+78h+var_44]
0x180002f9a  shr     r14d, 2
0x180002f9e  mov     [rsp+78h+var_44], r14d
0x180002fa3  mov     [rsp+78h+var_58], rax
0x180002fa8  call    ?DeclareConstantBufferField@PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4DCOMPOSITION_EXPRESSION_TYPE@@PEBI@Z; Windows::UI::Composition::PixelShaderSourceBuilder::DeclareConstantBufferField(char const *,DCOMPOSITION_EXPRESSION_TYPE,uint const *)
0x180002fad  mov     rbx, [rsp+78h+arg_8]
0x180002fb5  mov     rax, r13
0x180002fb8  add     rsp, 40h
0x180002fbc  pop     r15
0x180002fbe  pop     r14
0x180002fc0  pop     r13
0x180002fc2  pop     r12
0x180002fc4  pop     rdi
0x180002fc5  pop     rsi
0x180002fc6  pop     rbp
0x180002fc7  retn
0x180002fc8  mov     edi, 10h
0x180002fcd  cmp     ebp, 2
0x180002fd0  lea     eax, [rdi-8]
0x180002fd3  cmovz   edi, eax
0x180002fd6  jmp     loc_180002EB9
0x180002fdb  mov     [rsp+78h+var_48], r14b
0x180002fe0  cmp     rbx, [rsi+10h]
0x180002fe4  jz      short loc_180002FFF
0x180002fe6  mov     [rbx], r14b
0x180002fe9  inc     qword ptr [rsi+8]
0x180002fed  jmp     loc_180002EC1
0x180002ff2  lea     rax, [r15+rcx]
0x180002ff6  mov     [rsi+8], rax
0x180002ffa  jmp     loc_180002F6B
0x180002fff  lea     r8, [rsp+78h+var_48]
0x180003004  mov     rdx, rbx
0x180003007  mov     rcx, rsi
0x18000300a  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x18000300f  jmp     loc_180002EC1
0x180003014  lea     rcx, aVectorTooLong; "vector too long"
0x18000301b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003022  mov     r8, r12; Size
0x180003025  xor     edx, edx; Val
0x180003027  mov     rcx, rbx; void *
0x18000302a  call    memset_0
0x18000302f  lea     rax, [r12+rbx]
0x180003033  jmp     short loc_180002FF6
```
