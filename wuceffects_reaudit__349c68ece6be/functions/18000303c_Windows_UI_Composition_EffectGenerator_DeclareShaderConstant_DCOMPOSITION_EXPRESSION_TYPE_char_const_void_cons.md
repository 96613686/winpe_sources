# Windows::UI::Composition::EffectGenerator::DeclareShaderConstant(DCOMPOSITION_EXPRESSION_TYPE,char const *,void const *)

- ea: `0x18000303c`
- end: `0x1800032ee`
- name: `?DeclareShaderConstant@EffectGenerator@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBDPEBX@Z`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002cd0`
- `0x1800036c4`

## callees

- `0x18000303c`
- `0x1800032f4`
- `0x180003508`
- `0x180003620`
- `0x180004db8`
- `0x180006e1c`
- `0x180007ee4`
- `0x1800090a0`
- `0x18001de54`
- `0x180021060`
- `0x180021084`
- `0x1800257b8`
- `0x180026144`
- `0x1800263a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void *__fastcall Windows::UI::Composition::EffectGenerator::DeclareShaderConstant(
        int a1,
        void *a2,
        unsigned int a3,
        int a4,
        __int64 a5)
{
  unsigned int v9; // ebx
  unsigned int ExpressionTypeChannelCount; // r14d
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rbx
  const char *v13; // rdx
  __int64 v14; // r8
  unsigned __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned __int64 v18; // rcx
  __int128 *p_Src; // rax
  void *v20; // rcx
  unsigned __int64 v21; // rcx
  __int128 *v22; // rax
  char *v23; // rdx
  __int64 v25; // rcx
  void *v26; // [rsp+30h] [rbp-51h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-49h] BYREF
  __int128 Src; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int64 v29; // [rsp+58h] [rbp-29h]
  unsigned __int64 v30; // [rsp+60h] [rbp-21h]
  void *v31[3]; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int64 v32; // [rsp+80h] [rbp-1h]

  v26 = a2;
  v9 = 0;
  ExpressionTypeChannelCount = GetExpressionTypeChannelCount(a3);
  Src = 0;
  v29 = 0;
  v30 = 0;
  v11 = 6 * (unsigned int)std::string::_Construct_empty(&Src) + 10;
  if ( v30 < v11 )
  {
    v12 = v29;
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAX_K_Z___V___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(
      &Src,
      v11 - v29);
    v29 = v12;
    v9 = 0;
  }
  switch ( a3 )
  {
    case 0x45u:
      v13 = "minfloat4";
      break;
    case 0x12u:
      v13 = "minfloat";
      break;
    case 0x23u:
      v13 = "minfloat2";
      break;
    case 0x34u:
      v13 = "minfloat3";
      break;
    case 0x68u:
      v13 = "minfloat3x2";
      break;
    case 0x109u:
      v13 = "minfloat4x4";
      break;
    default:
      std::wstring::wstring(v31, L"Unexpected property type.");
      Windows::UI::Composition::OriginateException(v25, (__int64 *)v31);
  }
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  std::string::_Append<char>(&Src);
  v18 = v29;
  if ( v29 >= v30 )
  {
    LOBYTE(v17) = 40;
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(
      &Src,
      v15,
      v16,
      v17);
  }
  else
  {
    ++v29;
    p_Src = &Src;
    if ( v30 > 0xF )
      p_Src = (__int128 *)Src;
    *(_WORD *)((char *)p_Src + v18) = 40;
  }
  while ( v9 < ExpressionTypeChannelCount )
  {
    if ( v9 )
      std::string::_Append<char>(&Src);
    Windows::UI::Composition::FloatToString((__int64)v31, *(float *)(a5 + 4LL * v9));
    std::string::_Append<char>(&Src);
    v15 = v32;
    if ( v32 > 0xF )
    {
      v27 = v32 + 1;
      v20 = v31[0];
      v26 = v31[0];
      if ( v32 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v26, &v27);
        v20 = v26;
      }
      operator delete(v20);
    }
    ++v9;
  }
  v21 = v29;
  if ( v29 >= v30 )
  {
    LOBYTE(v17) = 41;
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(
      &Src,
      v15,
      v16,
      v17);
  }
  else
  {
    ++v29;
    v22 = &Src;
    if ( v30 > 0xF )
      v22 = (__int128 *)Src;
    *(_WORD *)((char *)v22 + v21) = 41;
  }
  v23 = (char *)&Src;
  if ( v30 > 0xF )
    v23 = (char *)Src;
  Windows::UI::Composition::PixelShaderSourceBuilder::DeclareLocal(a1 + 88, (int)a2, a3, a4, v23);
  std::string::~string(&Src);
  return a2;
}

```

## disassembly

```asm
0x18000303c  push    rbp
0x18000303e  push    rbx
0x18000303f  push    rsi
0x180003040  push    rdi
0x180003041  push    r12
0x180003043  push    r13
0x180003045  push    r14
0x180003047  push    r15
0x180003049  lea     rbp, [rsp-17h]
0x18000304e  sub     rsp, 98h
0x180003055  mov     rax, cs:__security_cookie
0x18000305c  xor     rax, rsp
0x18000305f  mov     [rbp+4Fh+var_48], rax
0x180003063  mov     r12, r9
0x180003066  mov     edi, r8d
0x180003069  mov     rsi, rdx
0x18000306c  mov     r13, rcx
0x18000306f  mov     [rbp+4Fh+var_A0], rdx
0x180003073  mov     r15, [rbp+4Fh+arg_20]
0x180003077  xor     ebx, ebx
0x180003079  mov     ecx, r8d
0x18000307c  call    ?GetExpressionTypeChannelCount@@YAIW4DCOMPOSITION_EXPRESSION_TYPE@@@Z; GetExpressionTypeChannelCount(DCOMPOSITION_EXPRESSION_TYPE)
0x180003081  mov     r14d, eax
0x180003084  xorps   xmm0, xmm0
0x180003087  movups  [rbp+4Fh+Src], xmm0
0x18000308b  mov     [rbp+4Fh+var_78], rbx
0x18000308f  mov     [rbp+4Fh+var_70], rbx
0x180003093  lea     rcx, [rbp+4Fh+Src]
0x180003097  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x18000309c  nop
0x18000309d  lea     eax, [rax+rax*2]
0x1800030a0  lea     edx, ds:0Ah[rax*2]
0x1800030a7  cmp     [rbp+4Fh+var_70], rdx
0x1800030ab  jnb     short loc_1800030C3
0x1800030ad  mov     rbx, [rbp+4Fh+var_78]
0x1800030b1  sub     rdx, rbx
0x1800030b4  lea     rcx, [rbp+4Fh+Src]
0x1800030b8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::string::_Reallocate_grow_by<`std::string::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::string::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x1800030bd  mov     [rbp+4Fh+var_78], rbx
0x1800030c1  xor     ebx, ebx
0x1800030c3  cmp     edi, 45h ; 'E'
0x1800030c6  jnz     loc_180003227
0x1800030cc  lea     rdx, aMinfloat4; "minfloat4"
0x1800030d3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800030d7  inc     r8
0x1800030da  cmp     [rdx+r8], bl
0x1800030de  jnz     short loc_1800030D7
0x1800030e0  lea     rcx, [rbp+4Fh+Src]; Src
0x1800030e4  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800030e9  mov     rcx, [rbp+4Fh+var_78]
0x1800030ed  cmp     rcx, [rbp+4Fh+var_70]
0x1800030f1  jnb     loc_1800032B1
0x1800030f7  lea     rax, [rcx+1]
0x1800030fb  mov     [rbp+4Fh+var_78], rax
0x1800030ff  lea     rax, [rbp+4Fh+Src]
0x180003103  cmp     [rbp+4Fh+var_70], 0Fh
0x180003108  cmova   rax, qword ptr [rbp+4Fh+Src]
0x18000310d  mov     word ptr [rax+rcx], 28h ; '('
0x180003113  cmp     ebx, r14d
0x180003116  jnb     loc_1800031AB
0x18000311c  test    ebx, ebx
0x18000311e  jz      short loc_180003136
0x180003120  mov     r8d, 2
0x180003126  lea     rdx, asc_180033E90; ", "
0x18000312d  lea     rcx, [rbp+4Fh+Src]; Src
0x180003131  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180003136  mov     eax, ebx
0x180003138  movss   xmm0, dword ptr [r15+rax*4]
0x18000313e  mulss   xmm0, cs:__real@00000000
0x180003146  lea     rcx, [rbp+4Fh+var_68]
0x18000314a  ucomiss xmm0, xmm0
0x18000314d  jp      loc_180003238
0x180003153  movss   xmm1, dword ptr [r15+rax*4]
0x180003159  call    Windows__UI__Composition__FloatToString
0x18000315e  nop
0x18000315f  mov     r8, [rax+10h]
0x180003163  cmp     qword ptr [rax+18h], 0Fh
0x180003168  jbe     short loc_18000316D
0x18000316a  mov     rax, [rax]
0x18000316d  mov     rdx, rax
0x180003170  lea     rcx, [rbp+4Fh+Src]; Src
0x180003174  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180003179  nop
0x18000317a  mov     rdx, [rbp+4Fh+var_50]
0x18000317e  cmp     rdx, 0Fh
0x180003182  ja      short loc_180003188
0x180003184  inc     ebx
0x180003186  jmp     short loc_180003113
0x180003188  inc     rdx; unsigned __int64
0x18000318b  mov     [rbp+4Fh+var_98], rdx
0x18000318f  mov     rcx, [rbp+4Fh+var_68]; void *
0x180003193  mov     [rbp+4Fh+var_A0], rcx
0x180003197  cmp     rdx, 1000h
0x18000319e  jnb     loc_1800032C2
0x1800031a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800031a9  jmp     short loc_180003184
0x1800031ab  mov     rcx, [rbp+4Fh+var_78]
0x1800031af  cmp     rcx, [rbp+4Fh+var_70]
0x1800031b3  jnb     loc_1800032DC
0x1800031b9  lea     rax, [rcx+1]
0x1800031bd  mov     [rbp+4Fh+var_78], rax
0x1800031c1  lea     rax, [rbp+4Fh+Src]
0x1800031c5  cmp     [rbp+4Fh+var_70], 0Fh
0x1800031ca  cmova   rax, qword ptr [rbp+4Fh+Src]
0x1800031cf  mov     word ptr [rax+rcx], 29h ; ')'
0x1800031d5  lea     rcx, [r13+58h]; int
0x1800031d9  lea     rdx, [rbp+4Fh+Src]
0x1800031dd  cmp     [rbp+4Fh+var_70], 0Fh
0x1800031e2  cmova   rdx, qword ptr [rbp+4Fh+Src]
0x1800031e7  mov     [rsp+0D0h+var_B0], rdx; char *
0x1800031ec  mov     r9, r12; int
0x1800031ef  mov     r8d, edi; int
0x1800031f2  mov     rdx, rsi; int
0x1800031f5  call    ?DeclareLocal@PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBD1@Z; Windows::UI::Composition::PixelShaderSourceBuilder::DeclareLocal(DCOMPOSITION_EXPRESSION_TYPE,char const *,char const *)
0x1800031fa  nop
0x1800031fb  lea     rcx, [rbp+4Fh+Src]; void *
0x1800031ff  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180003204  mov     rax, rsi
0x180003207  mov     rcx, [rbp+4Fh+var_48]
0x18000320b  xor     rcx, rsp; StackCookie
0x18000320e  call    __security_check_cookie
0x180003213  add     rsp, 98h
0x18000321a  pop     r15
0x18000321c  pop     r14
0x18000321e  pop     r13
0x180003220  pop     r12
0x180003222  pop     rdi
0x180003223  pop     rsi
0x180003224  pop     rbx
0x180003225  pop     rbp
0x180003226  retn
0x180003227  cmp     edi, 12h
0x18000322a  jnz     short loc_18000324F
0x18000322c  lea     rdx, aMinfloat; "minfloat"
0x180003233  jmp     loc_1800030D3
0x180003238  lea     rdx, aNonFiniteFloat; "Non-finite floating-point value."
0x18000323f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003244  nop
0x180003245  lea     rdx, [rbp+4Fh+var_68]
0x180003249  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000324f  cmp     edi, 23h ; '#'
0x180003252  jz      short loc_1800032A5
0x180003254  cmp     edi, 34h ; '4'
0x180003257  jz      short loc_180003299
0x180003259  cmp     edi, 68h ; 'h'
0x18000325c  jz      short loc_18000328D
0x18000325e  cmp     edi, 109h
0x180003264  jz      short loc_180003281
0x180003266  lea     rdx, aUnexpectedProp; "Unexpected property type."
0x18000326d  lea     rcx, [rbp+4Fh+var_68]
0x180003271  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003276  nop
0x180003277  lea     rdx, [rbp+4Fh+var_68]
0x18000327b  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x180003281  lea     rdx, aMinfloat4x4; "minfloat4x4"
0x180003288  jmp     loc_1800030D3
0x18000328d  lea     rdx, aMinfloat3x2; "minfloat3x2"
0x180003294  jmp     loc_1800030D3
0x180003299  lea     rdx, aMinfloat3; "minfloat3"
0x1800032a0  jmp     loc_1800030D3
0x1800032a5  lea     rdx, aMinfloat2; "minfloat2"
0x1800032ac  jmp     loc_1800030D3
0x1800032b1  mov     r9b, 28h ; '('
0x1800032b4  lea     rcx, [rbp+4Fh+Src]
0x1800032b8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800032bd  jmp     loc_180003113
0x1800032c2  lea     rdx, [rbp+4Fh+var_98]; unsigned __int64 *
0x1800032c6  lea     rcx, [rbp+4Fh+var_A0]; void **
0x1800032ca  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800032cf  mov     rdx, [rbp+4Fh+var_98]
0x1800032d3  mov     rcx, [rbp+4Fh+var_A0]
0x1800032d7  jmp     loc_1800031A4
0x1800032dc  mov     r9b, 29h ; ')'
0x1800032df  lea     rcx, [rbp+4Fh+Src]
0x1800032e3  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800032e8  jmp     loc_1800031D5
```
