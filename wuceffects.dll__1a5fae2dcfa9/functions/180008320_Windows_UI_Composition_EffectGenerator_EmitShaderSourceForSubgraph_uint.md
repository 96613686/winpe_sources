# Windows::UI::Composition::EffectGenerator::EmitShaderSourceForSubgraph(uint)

- ea: `0x180008320`
- end: `0x18000853b`
- name: `?EmitShaderSourceForSubgraph@EffectGenerator@Composition@UI@Windows@@AEAAXI@Z`
- size: `539`
- prototype: `void __fastcall(Windows::UI::Composition::EffectGenerator *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x180001330`
- `0x180001810`
- `0x180003470`
- `0x1800061b0`
- `0x180006960`
- `0x180007920`
- `0x180008320`
- `0x180008670`
- `0x1800090a0`
- `0x18000bfb0`
- `0x18001a7e4`
- `0x180021060`
- `0x180021cc8`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180008367`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180008367`

## string_xrefs

- `0x18000839a`: `Common.hlsl`

## pseudocode

```c
void __fastcall Windows::UI::Composition::EffectGenerator::EmitShaderSourceForSubgraph(
        Windows::UI::Composition::EffectGenerator *this,
        unsigned int a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  const struct Windows::UI::Composition::EffectSubgraph *v5; // r14
  _QWORD *i; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  void **v12; // rdx
  size_t v13; // r8
  __int64 v14; // rcx
  char v15[8]; // [rsp+20h] [rbp-30h] BYREF
  void *Buf2[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h]
  unsigned __int64 v18; // [rsp+40h] [rbp-10h]

  v3 = *(_QWORD *)this;
  v4 = *(_QWORD *)(*(_QWORD *)this + 24LL);
  if ( (*(_QWORD *)(v3 + 32) - v4) >> 3 <= (unsigned __int64)a2 )
    goto LABEL_2;
  v5 = *(const struct Windows::UI::Composition::EffectSubgraph **)(v4 + 8LL * a2);
  Windows::UI::Composition::EffectGenerator::InitializeSamplerData(this, v5);
  *(_OWORD *)Buf2 = 0;
  v17 = 0;
  v18 = 0;
  std::string::_Construct<1,char const *>(Buf2, "Common.hlsl", 11);
  for ( i = (_QWORD *)*((_QWORD *)this + 12); i != *((_QWORD **)this + 13); i += 4 )
  {
    v12 = Buf2;
    if ( v18 > 0xF )
      v12 = (void **)Buf2[0];
    v13 = i[2];
    v7 = i[3] > 0xFu ? (_QWORD *)*i : i;
    if ( v13 == v17 && (!v13 || !memcmp_0(v7, v12, v13)) )
      break;
  }
  if ( i == *((_QWORD **)this + 13) )
  {
    v14 = *((_QWORD *)this + 13);
    if ( v14 == *((_QWORD *)this + 14) )
    {
      std::vector<std::string>::_Emplace_reallocate<std::string>((char *)this + 96, *((_QWORD *)this + 13), Buf2);
    }
    else
    {
      std::string::string(v14, Buf2);
      *((_QWORD *)this + 13) += 32LL;
    }
  }
  std::string::~string(Buf2);
  v8 = *((_QWORD *)v5 + 1);
  v9 = *(unsigned int *)(v8 - 4);
  Windows::UI::Composition::EffectGenerator::EmitNode(this, *(_DWORD *)(v8 - 4), 0);
  v10 = *(_QWORD *)(*(_QWORD *)this + 48LL);
  if ( (*(_QWORD *)(*(_QWORD *)this + 56LL) - v10) >> 3 <= v9 )
    goto LABEL_2;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(***(_QWORD ***)(v10 + 8 * v9) + 88LL))(**(_QWORD **)(v10 + 8 * v9)) )
    **((_DWORD **)this + 1) |= 8u;
  Windows::UI::Composition::EffectGenerator::PopulateSamplerData(this, v5);
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::EffectGenerator *)((char *)this + 224),
    "    ");
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::EffectGenerator *)((char *)this + 224),
    "return ");
  v11 = *(unsigned int *)(*((_QWORD *)v5 + 1) - 4LL);
  if ( (__int64)(*((_QWORD *)this + 7) - *((_QWORD *)this + 6)) >> 5 <= v11 )
  {
LABEL_2:
    std::_Xout_of_range("invalid vector subscript");
    __debugbreak();
  }
  Windows::UI::Composition::StringBuilder::Append((char *)this + 224, *((_QWORD *)this + 6) + 32 * v11);
  Windows::UI::Composition::StringBuilder::Append(
    (Windows::UI::Composition::EffectGenerator *)((char *)this + 224),
    ";");
  v15[0] = 10;
  std::deque<char>::push_back((char *)this + 224, v15);
}

```

## disassembly

```asm
0x180008320  mov     [rsp-18h+arg_10], rbx
0x180008325  mov     [rsp-18h+arg_18], rsi
0x18000832a  push    rbp
0x18000832b  push    rdi
0x18000832c  push    r14
0x18000832e  mov     rbp, rsp
0x180008331  sub     rsp, 50h
0x180008335  mov     rax, cs:__security_cookie
0x18000833c  xor     rax, rsp
0x18000833f  mov     [rbp+var_8], rax
0x180008343  mov     rdi, rcx
0x180008346  mov     rax, [rcx]
0x180008349  mov     rcx, [rax+18h]
0x18000834d  mov     r8d, edx
0x180008350  mov     rdx, [rax+20h]
0x180008354  sub     rdx, rcx
0x180008357  sar     rdx, 3
0x18000835b  cmp     rdx, r8
0x18000835e  ja      short loc_18000836E
0x180008360  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180008367  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000836d  int     3; Trap to Debugger
0x18000836e  mov     r14, [rcx+r8*8]
0x180008372  mov     rdx, r14; struct Windows::UI::Composition::EffectSubgraph *
0x180008375  mov     rcx, rdi; this
0x180008378  call    ?InitializeSamplerData@EffectGenerator@Composition@UI@Windows@@AEAAXAEBUEffectSubgraph@234@@Z; Windows::UI::Composition::EffectGenerator::InitializeSamplerData(Windows::UI::Composition::EffectSubgraph const &)
0x18000837d  xorps   xmm0, xmm0
0x180008380  movups  xmmword ptr [rbp+Buf2], xmm0
0x180008384  mov     [rbp+var_18], 0
0x18000838c  mov     [rbp+var_10], 0
0x180008394  mov     r8d, 0Bh
0x18000839a  lea     rdx, aCommonHlsl; "Common.hlsl"
0x1800083a1  lea     rcx, [rbp+Buf2]
0x1800083a5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800083aa  nop
0x1800083ab  mov     rbx, [rdi+60h]
0x1800083af  jmp     short loc_1800083C2
0x1800083b1  mov     rcx, [rbx]; Buf1
0x1800083b4  cmp     r8, [rbp+var_18]
0x1800083b8  jz      loc_18000850C
0x1800083be  add     rbx, 20h ; ' '
0x1800083c2  cmp     rbx, [rdi+68h]
0x1800083c6  jnz     loc_1800084C8
0x1800083cc  cmp     rbx, [rdi+68h]
0x1800083d0  jz      loc_1800084ED
0x1800083d6  lea     rcx, [rbp+Buf2]; void *
0x1800083da  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800083df  mov     rax, [r14+8]
0x1800083e3  mov     ebx, [rax-4]
0x1800083e6  xor     r8d, r8d; bool
0x1800083e9  mov     edx, ebx; unsigned int
0x1800083eb  mov     rcx, rdi; this
0x1800083ee  call    ?EmitNode@EffectGenerator@Composition@UI@Windows@@AEAAXI_N@Z; Windows::UI::Composition::EffectGenerator::EmitNode(uint,bool)
0x1800083f3  mov     rax, [rdi]
0x1800083f6  mov     rdx, [rax+30h]
0x1800083fa  mov     rcx, [rax+38h]
0x1800083fe  sub     rcx, rdx
0x180008401  sar     rcx, 3
0x180008405  cmp     rcx, rbx
0x180008408  jbe     loc_180008360
0x18000840e  mov     rax, [rdx+rbx*8]
0x180008412  mov     rcx, [rax]
0x180008415  mov     rax, [rcx]
0x180008418  mov     rax, [rax+58h]
0x18000841c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008421  test    al, al
0x180008423  jz      short loc_18000842C
0x180008425  mov     rax, [rdi+8]
0x180008429  or      dword ptr [rax], 8
0x18000842c  mov     rdx, r14; struct Windows::UI::Composition::EffectSubgraph *
0x18000842f  mov     rcx, rdi; this
0x180008432  call    ?PopulateSamplerData@EffectGenerator@Composition@UI@Windows@@AEAAXAEBUEffectSubgraph@234@@Z; Windows::UI::Composition::EffectGenerator::PopulateSamplerData(Windows::UI::Composition::EffectSubgraph const &)
0x180008437  lea     rbx, [rdi+0E0h]
0x18000843e  lea     rdx, asc_18003403C; "    "
0x180008445  mov     rcx, rbx; this
0x180008448  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000844d  lea     rdx, aReturn; "return "
0x180008454  mov     rcx, rbx; this
0x180008457  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000845c  mov     rax, [r14+8]
0x180008460  mov     edx, [rax-4]
0x180008463  mov     rax, [rdi+38h]
0x180008467  sub     rax, [rdi+30h]
0x18000846b  sar     rax, 5
0x18000846f  cmp     rax, rdx
0x180008472  jbe     loc_180008360
0x180008478  shl     rdx, 5
0x18000847c  add     rdx, [rdi+30h]
0x180008480  mov     rcx, rbx
0x180008483  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Windows::UI::Composition::StringBuilder::Append(std::string const &)
0x180008488  lea     rdx, asc_180034050; ";"
0x18000848f  mov     rcx, rbx; this
0x180008492  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180008497  mov     [rbp+var_30], 0Ah
0x18000849b  lea     rdx, [rbp+var_30]
0x18000849f  mov     rcx, rbx
0x1800084a2  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x1800084a7  mov     rcx, [rbp+var_8]
0x1800084ab  xor     rcx, rsp; StackCookie
0x1800084ae  call    __security_check_cookie
0x1800084b3  lea     r11, [rsp+50h+var_s0]
0x1800084b8  mov     rbx, [r11+30h]
0x1800084bc  mov     rsi, [r11+38h]
0x1800084c0  mov     rsp, r11
0x1800084c3  pop     r14
0x1800084c5  pop     rdi
0x1800084c6  pop     rbp
0x1800084c7  retn
0x1800084c8  lea     rdx, [rbp+Buf2]
0x1800084cc  cmp     [rbp+var_10], 0Fh
0x1800084d1  cmova   rdx, [rbp+Buf2]; Buf2
0x1800084d6  mov     r8, [rbx+10h]; Size
0x1800084da  cmp     qword ptr [rbx+18h], 0Fh
0x1800084df  ja      loc_1800083B1
0x1800084e5  mov     rcx, rbx
0x1800084e8  jmp     loc_1800083B4
0x1800084ed  mov     rcx, [rdi+68h]
0x1800084f1  cmp     rcx, [rdi+70h]
0x1800084f5  jnz     short loc_180008527
0x1800084f7  lea     r8, [rbp+Buf2]
0x1800084fb  mov     rdx, rcx
0x1800084fe  lea     rcx, [rdi+60h]
0x180008502  call    ??$_Emplace_reallocate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string>(std::string * const,std::string &&)
0x180008507  jmp     loc_1800083D6
0x18000850c  test    r8, r8
0x18000850f  jz      loc_1800083CC
0x180008515  call    memcmp_0
0x18000851a  test    eax, eax
0x18000851c  jz      loc_1800083CC
0x180008522  jmp     loc_1800083BE
0x180008527  lea     rdx, [rbp+Buf2]
0x18000852b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180008530  add     qword ptr [rdi+68h], 20h ; ' '
0x180008535  jmp     loc_1800083D6
```
