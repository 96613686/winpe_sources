# Windows::UI::Composition::CompositeEffectType::GenerateCode(Windows::UI::Composition::EffectNode const &,Windows::UI::Composition::EffectGenerator *,char const *)

- ea: `0x180006470`
- end: `0x1800066d1`
- name: `?GenerateCode@CompositeEffectType@Composition@UI@Windows@@UEBAXAEBVEffectNode@234@PEAVEffectGenerator@234@PEBD@Z`
- size: `609`
- prototype: `void __fastcall(Windows::UI::Composition::CompositeEffectType *this, const struct Windows::UI::Composition::EffectNode *, struct Windows::UI::Composition::EffectGenerator *, const char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001330`
- `0x180001810`
- `0x180001bf0`
- `0x1800024f0`
- `0x180003470`
- `0x180003db4`
- `0x1800061b0`
- `0x180006470`
- `0x180007920`
- `0x180008670`
- `0x1800090a0`
- `0x180021060`

## string_xrefs

- `0x1800064e7`: `D2DComposite.hlsl`
- `0x180006615`: ` = D2DComposite`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Windows::UI::Composition::CompositeEffectType::GenerateCode(
        Windows::UI::Composition::CompositeEffectType *this,
        const struct Windows::UI::Composition::EffectNode *a2,
        struct Windows::UI::Composition::EffectGenerator *a3,
        const char *a4)
{
  int *v7; // r15
  _QWORD *InputPixelName; // rax
  __int64 v9; // r8
  __int64 v10; // rdi
  const char *v11; // rbx
  const char *v12; // r15
  unsigned int i; // ebx
  _QWORD *v14; // rax
  __int64 v15; // r8
  char v16[8]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v17; // [rsp+28h] [rbp-48h] BYREF
  __int128 v18; // [rsp+38h] [rbp-38h]
  char *v19[2]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v20; // [rsp+58h] [rbp-18h]

  v7 = (int *)*((_QWORD *)a2 + 3);
  InputPixelName = (_QWORD *)Windows::UI::Composition::EffectGenerator::GetInputPixelName(a3, (__int64)a2, 0);
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v9 = InputPixelName[2];
  if ( InputPixelName[3] > 0xFu )
    InputPixelName = (_QWORD *)*InputPixelName;
  std::string::_Construct<2,char const *>(v19, InputPixelName, v9);
  v17 = 0;
  v18 = 0;
  std::string::_Construct<1,char const *>(&v17, "D2DComposite.hlsl", 17);
  v10 = *((_QWORD *)a3 + 13);
  if ( std::_Find_unchecked<std::string *,std::string>(*((_QWORD *)a3 + 12), v10, &v17) == v10 )
  {
    if ( v10 == *((_QWORD *)a3 + 14) )
    {
      std::vector<std::string>::_Emplace_reallocate<std::string>((char *)a3 + 96, v10, &v17);
    }
    else
    {
      std::string::string(v10, &v17);
      *((_QWORD *)a3 + 13) += 32LL;
    }
  }
  std::string::~string(&v17);
  v11 = (const char *)v19;
  if ( *((_QWORD *)&v20 + 1) > 0xFu )
    v11 = v19[0];
  v12 = off_1800327F0[*v7];
  Windows::UI::Composition::StringBuilder::Append(
    (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
    "    ");
  Windows::UI::Composition::StringBuilder::Append(
    (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
    a4);
  Windows::UI::Composition::StringBuilder::Append(
    (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
    " = ");
  Windows::UI::Composition::StringBuilder::Append(
    (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
    v11);
  Windows::UI::Composition::StringBuilder::Append(
    (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
    ";");
  v16[0] = 10;
  std::deque<char>::push_back((char *)a3 + 224, v16);
  for ( i = 1; i < *((_DWORD *)a2 + 5); ++i )
  {
    v14 = (_QWORD *)Windows::UI::Composition::EffectGenerator::GetInputPixelName(a3, (__int64)a2, i);
    v17 = 0;
    v18 = 0;
    v15 = v14[2];
    if ( v14[3] > 0xFu )
      v14 = (_QWORD *)*v14;
    std::string::_Construct<2,char const *>(&v17, v14, v15);
    Windows::UI::Composition::StringBuilder::Append(
      (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
      "    ");
    Windows::UI::Composition::StringBuilder::Append(
      (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
      a4);
    Windows::UI::Composition::StringBuilder::Append(
      (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
      " = D2DComposite");
    Windows::UI::Composition::StringBuilder::Append(
      (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
      v12);
    v16[0] = 40;
    std::deque<char>::push_back((char *)a3 + 224, v16);
    Windows::UI::Composition::StringBuilder::Append((char *)a3 + 224, &v17);
    Windows::UI::Composition::StringBuilder::Append(
      (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
      ", ");
    Windows::UI::Composition::StringBuilder::Append(
      (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
      a4);
    Windows::UI::Composition::StringBuilder::Append(
      (struct Windows::UI::Composition::EffectGenerator *)((char *)a3 + 224),
      ");");
    v16[0] = 10;
    std::deque<char>::push_back((char *)a3 + 224, v16);
    std::string::~string(&v17);
  }
  std::string::~string(v19);
}

```

## disassembly

```asm
0x180006470  push    rbp
0x180006472  push    rbx
0x180006473  push    rsi
0x180006474  push    rdi
0x180006475  push    r12
0x180006477  push    r14
0x180006479  push    r15
0x18000647b  mov     rbp, rsp
0x18000647e  sub     rsp, 70h
0x180006482  mov     rax, cs:__security_cookie
0x180006489  xor     rax, rsp
0x18000648c  mov     [rbp+var_8], rax
0x180006490  mov     r12, r9
0x180006493  mov     rsi, r8
0x180006496  mov     r14, rdx
0x180006499  mov     r15, [rdx+18h]
0x18000649d  xor     r8d, r8d
0x1800064a0  mov     rcx, rsi
0x1800064a3  call    ?GetInputPixelName@EffectGenerator@Composition@UI@Windows@@QEAAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVEffectNode@234@_K@Z; Windows::UI::Composition::EffectGenerator::GetInputPixelName(Windows::UI::Composition::EffectNode const &,unsigned __int64)
0x1800064a8  xorps   xmm0, xmm0
0x1800064ab  movups  xmmword ptr [rbp+var_28], xmm0
0x1800064af  xorps   xmm1, xmm1
0x1800064b2  movdqu  [rbp+var_18], xmm1
0x1800064b7  mov     r8, [rax+10h]
0x1800064bb  cmp     qword ptr [rax+18h], 0Fh
0x1800064c0  jbe     short loc_1800064C5
0x1800064c2  mov     rax, [rax]
0x1800064c5  mov     rdx, rax
0x1800064c8  lea     rcx, [rbp+var_28]
0x1800064cc  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800064d1  nop
0x1800064d2  xorps   xmm0, xmm0
0x1800064d5  movups  [rbp+var_48], xmm0
0x1800064d9  xorps   xmm1, xmm1
0x1800064dc  movdqu  [rbp+var_38], xmm1
0x1800064e1  mov     r8d, 11h
0x1800064e7  lea     rdx, aD2dcompositeHl; "D2DComposite.hlsl"
0x1800064ee  lea     rcx, [rbp+var_48]
0x1800064f2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800064f7  nop
0x1800064f8  mov     rdi, [rsi+68h]
0x1800064fc  lea     r8, [rbp+var_48]
0x180006500  mov     rdx, rdi
0x180006503  mov     rcx, [rsi+60h]
0x180006507  call    ??$_Find_unchecked@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@YAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@PEAV10@QEAV10@AEBV10@@Z; std::_Find_unchecked<std::string *,std::string>(std::string *,std::string * const,std::string const &)
0x18000650c  cmp     rax, rdi
0x18000650f  jz      loc_18000669F
0x180006515  lea     rcx, [rbp+var_48]; void *
0x180006519  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000651e  lea     rbx, [rbp+var_28]
0x180006522  cmp     qword ptr [rbp+var_18+8], 0Fh
0x180006527  cmova   rbx, [rbp+var_28]
0x18000652c  movsxd  rax, dword ptr [r15]
0x18000652f  lea     r15, off_1800327F0; "SourceOver"
0x180006536  mov     r15, [r15+rax*8]
0x18000653a  lea     rdi, [rsi+0E0h]
0x180006541  lea     rdx, asc_18003403C; "    "
0x180006548  mov     rcx, rdi; this
0x18000654b  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180006550  mov     rdx, r12; char *
0x180006553  mov     rcx, rdi; this
0x180006556  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000655b  lea     rdx, asc_180034054; " = "
0x180006562  mov     rcx, rdi; this
0x180006565  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000656a  mov     rdx, rbx; char *
0x18000656d  mov     rcx, rdi; this
0x180006570  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180006575  lea     rdx, asc_180034050; ";"
0x18000657c  mov     rcx, rdi; this
0x18000657f  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180006584  mov     [rbp+var_50], 0Ah
0x180006588  lea     rdx, [rbp+var_50]
0x18000658c  mov     rcx, rdi
0x18000658f  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x180006594  mov     ebx, 1
0x180006599  cmp     [r14+14h], ebx
0x18000659d  ja      short loc_1800065C3
0x18000659f  lea     rcx, [rbp+var_28]; void *
0x1800065a3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800065a8  mov     rcx, [rbp+var_8]
0x1800065ac  xor     rcx, rsp; StackCookie
0x1800065af  call    __security_check_cookie
0x1800065b4  add     rsp, 70h
0x1800065b8  pop     r15
0x1800065ba  pop     r14
0x1800065bc  pop     r12
0x1800065be  pop     rdi
0x1800065bf  pop     rsi
0x1800065c0  pop     rbx
0x1800065c1  pop     rbp
0x1800065c2  retn
0x1800065c3  mov     r8d, ebx
0x1800065c6  mov     rdx, r14
0x1800065c9  mov     rcx, rsi
0x1800065cc  call    ?GetInputPixelName@EffectGenerator@Composition@UI@Windows@@QEAAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVEffectNode@234@_K@Z; Windows::UI::Composition::EffectGenerator::GetInputPixelName(Windows::UI::Composition::EffectNode const &,unsigned __int64)
0x1800065d1  xorps   xmm0, xmm0
0x1800065d4  movups  [rbp+var_48], xmm0
0x1800065d8  xorps   xmm1, xmm1
0x1800065db  movdqu  [rbp+var_38], xmm1
0x1800065e0  mov     r8, [rax+10h]
0x1800065e4  cmp     qword ptr [rax+18h], 0Fh
0x1800065e9  jbe     short loc_1800065EE
0x1800065eb  mov     rax, [rax]
0x1800065ee  mov     rdx, rax
0x1800065f1  lea     rcx, [rbp+var_48]
0x1800065f5  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800065fa  nop
0x1800065fb  lea     rdx, asc_18003403C; "    "
0x180006602  mov     rcx, rdi; this
0x180006605  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000660a  mov     rdx, r12; char *
0x18000660d  mov     rcx, rdi; this
0x180006610  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180006615  lea     rdx, aD2dcomposite; " = D2DComposite"
0x18000661c  mov     rcx, rdi; this
0x18000661f  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180006624  mov     rdx, r15; char *
0x180006627  mov     rcx, rdi; this
0x18000662a  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000662f  mov     [rbp+var_50], 28h ; '('
0x180006633  lea     rdx, [rbp+var_50]
0x180006637  mov     rcx, rdi
0x18000663a  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x18000663f  lea     rdx, [rbp+var_48]
0x180006643  mov     rcx, rdi
0x180006646  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Windows::UI::Composition::StringBuilder::Append(std::string const &)
0x18000664b  lea     rdx, asc_180033E90; ", "
0x180006652  mov     rcx, rdi; this
0x180006655  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x18000665a  mov     rdx, r12; char *
0x18000665d  mov     rcx, rdi; this
0x180006660  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180006665  lea     rdx, asc_18003423C; ");"
0x18000666c  mov     rcx, rdi; this
0x18000666f  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180006674  mov     [rbp+var_50], 0Ah
0x180006678  lea     rdx, [rbp+var_50]
0x18000667c  mov     rcx, rdi
0x18000667f  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x180006684  nop
0x180006685  lea     rcx, [rbp+var_48]; void *
0x180006689  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000668e  inc     ebx
0x180006690  cmp     ebx, [r14+14h]
0x180006694  jnb     loc_18000659F
0x18000669a  jmp     loc_1800065C3
0x18000669f  cmp     rdi, [rsi+70h]
0x1800066a3  jnz     short loc_1800066BA
0x1800066a5  lea     r8, [rbp+var_48]
0x1800066a9  mov     rdx, rdi
0x1800066ac  lea     rcx, [rsi+60h]
0x1800066b0  call    ??$_Emplace_reallocate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string>(std::string * const,std::string &&)
0x1800066b5  jmp     loc_180006515
0x1800066ba  lea     rdx, [rbp+var_48]
0x1800066be  mov     rcx, rdi
0x1800066c1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x1800066c6  add     qword ptr [rsi+68h], 20h ; ' '
0x1800066cb  jmp     loc_180006515
```
