# PolicyTransforms::IsWindowsUpdateManaged(tagEnterprisePolicyValue_V1 *)

- ea: `0x180018020`
- end: `0x1800183c9`
- name: `?IsWindowsUpdateManaged@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `937`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180017e80`

## callees

- `0x18000aac0`
- `0x18000fb64`
- `0x180010ae0`
- `0x180016e74`
- `0x180018020`
- `0x1800185e8`
- `0x180018690`
- `0x18001a320`
- `0x18003002c`
- `0x180036a90`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180018252`
- `OLEAUT32!__imp_VariantClear` at `0x180018252`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PolicyTransforms::IsWindowsUpdateManaged(struct tagEnterprisePolicyValue_V1 *a1)
{
  _DWORD *v3; // rbx
  unsigned int v4; // r15d
  char *v5; // rcx
  __int64 v6; // rdi
  int PolicyWithFallback; // eax
  unsigned int v8; // esi
  _DWORD *v9; // rdi
  unsigned int v10; // r15d
  __m128i *p_Src; // r12
  int v12; // eax
  int v13; // r15d
  unsigned int *v14; // r12
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdi
  int v18; // eax
  int v19; // eax
  void *v20; // [rsp+20h] [rbp-50h] BYREF
  void *Block; // [rsp+28h] [rbp-48h] BYREF
  int v22; // [rsp+30h] [rbp-40h]
  char *v23; // [rsp+38h] [rbp-38h] BYREF
  char *v24; // [rsp+40h] [rbp-30h]
  char *v25; // [rsp+48h] [rbp-28h]
  int v26; // [rsp+50h] [rbp-20h] BYREF
  __m128i Src; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( a1 )
  {
    Src = _mm_load_si128((const __m128i *)&_xmm);
    v23 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
    v25 = v23 + 16;
    memmove(v23, &Src, 0x10u);
    v24 = v23 + 16;
    Block = 0;
    std::_Tidy_guard<std::vector<enum tagEnterprisePolicy>>::~_Tidy_guard<std::vector<enum tagEnterprisePolicy>>((__int64 *)&Block);
    Block = (void *)0x3D0000003CLL;
    v22 = 62;
    Src.m128i_i64[0] = 0x700000009LL;
    Src.m128i_i32[2] = 50;
    v26 = 12;
    v3 = 0;
    v20 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl'::`2'::impl) )
    {
      v4 = 0;
      v5 = v23;
      if ( (v24 - v23) >> 2 )
      {
        v6 = 0;
        while ( 1 )
        {
          if ( v3 )
          {
            operator delete(v3);
            v20 = 0;
            v5 = v23;
          }
          PolicyWithFallback = EnterprisePolicyReader::ReadPolicyWithFallback(*(_DWORD *)&v5[4 * v6], (__int64 *)&v20);
          v8 = PolicyWithFallback;
          v3 = v20;
          if ( PolicyWithFallback < 0 )
            break;
          if ( *((_DWORD *)v20 + 1) == 1 && *((_WORD *)v20 + 8) == 3 && *((_DWORD *)v20 + 6) == 1 )
            goto LABEL_37;
          v6 = ++v4;
          v5 = v23;
          if ( v4 >= (unsigned __int64)((v24 - v23) >> 2) )
            goto LABEL_13;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F2,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
          (const char *)(unsigned int)PolicyWithFallback,
          (int)v20);
      }
      else
      {
LABEL_13:
        v9 = 0;
        Block = 0;
        v10 = 0;
        p_Src = &Src;
        while ( 1 )
        {
          if ( v3 )
          {
            operator delete(v3);
            v20 = 0;
          }
          v12 = EnterprisePolicyReader::ReadPolicyWithFallback(p_Src->m128i_i32[0], (__int64 *)&v20);
          v8 = v12;
          v3 = v20;
          if ( v12 < 0 )
          {
            v16 = 1571;
LABEL_44:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v16,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
              (const char *)(unsigned int)v12,
              (int)v20);
            goto LABEL_45;
          }
          if ( *((_DWORD *)v20 + 1) == 1 )
            break;
          ++v10;
          p_Src = (__m128i *)((char *)p_Src + 4);
          if ( v10 >= 3 )
          {
            v13 = 0;
            v14 = (unsigned int *)&v26;
            do
            {
              if ( v9 )
              {
                operator delete(v9);
                Block = 0;
              }
              v15 = UpdatePolicyReader::ReadPolicy(*v14, &Block);
              v8 = v15;
              if ( v15 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x631,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
                  (const char *)(unsigned int)v15,
                  (int)v20);
                v9 = Block;
                goto LABEL_45;
              }
              v9 = Block;
              if ( *((_DWORD *)Block + 1) == 1 )
              {
                *((_DWORD *)a1 + 6) = 1;
                *((_WORD *)a1 + 8) = 3;
                *((_DWORD *)a1 + 1) = 1;
                v19 = v9[2];
                goto LABEL_39;
              }
              ++v13;
              ++v14;
            }
            while ( !v13 );
            *(_QWORD *)((char *)a1 + 4) = 0;
            v12 = VariantClear((VARIANTARG *)((char *)a1 + 16));
            v8 = v12;
            if ( v12 >= 0 )
              goto LABEL_40;
            v16 = 1597;
            goto LABEL_44;
          }
        }
        *((_DWORD *)a1 + 6) = 1;
        *((_WORD *)a1 + 8) = 3;
        *((_DWORD *)a1 + 1) = 1;
        v19 = v3[2];
LABEL_39:
        *((_DWORD *)a1 + 2) = v19;
LABEL_40:
        v8 = 0;
LABEL_45:
        if ( v9 )
          operator delete(v9);
      }
    }
    else
    {
      v17 = 0;
      while ( 1 )
      {
        if ( v3 )
        {
          operator delete(v3);
          v20 = 0;
        }
        v18 = EnterprisePolicyReader::ReadPolicyWithFallback(*((_DWORD *)&Block + v17), (__int64 *)&v20);
        v8 = v18;
        if ( v18 < 0 )
          break;
        v3 = v20;
        if ( *((_DWORD *)v20 + 1) == 1 && *((_WORD *)v20 + 8) == 3 && *((_DWORD *)v20 + 6) == 1 )
        {
LABEL_37:
          *((_DWORD *)a1 + 6) = 1;
          *((_WORD *)a1 + 8) = 3;
          *((_DWORD *)a1 + 1) = 1;
          *((_DWORD *)a1 + 2) = v3[2];
          v8 = 0;
          goto LABEL_48;
        }
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= 3 )
          goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x609,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
        (const char *)(unsigned int)v18,
        (int)v20);
      v3 = v20;
    }
LABEL_48:
    if ( v3 )
      operator delete(v3);
    std::vector<enum tagEnterprisePolicy>::~vector<enum tagEnterprisePolicy>((__int64)&v23);
    return v8;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D2,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
      (const char *)0x80004003LL,
      (int)v20);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180018020  mov     [rsp-28h+arg_8], rbx
0x180018025  mov     [rsp-28h+arg_10], rsi
0x18001802a  push    rbp
0x18001802b  push    rdi
0x18001802c  push    r12
0x18001802e  push    r14
0x180018030  push    r15
0x180018032  mov     rbp, rsp
0x180018035  sub     rsp, 70h
0x180018039  mov     r14, rcx
0x18001803c  test    rcx, rcx
0x18001803f  jnz     short loc_180018065
0x180018041  mov     rcx, [rbp+28h]; this
0x180018045  mov     ebx, 80004003h
0x18001804a  mov     r9d, ebx; char *
0x18001804d  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018054  mov     edx, 5D2h; void *
0x180018059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001805e  mov     eax, ebx
0x180018060  jmp     loc_1800183B0
0x180018065  xorps   xmm0, xmm0
0x180018068  xor     eax, eax
0x18001806a  movdqa  xmm1, cs:__xmm@000000400000003e0000003d0000003c
0x180018072  movdqu  [rbp+Src], xmm1
0x180018077  movdqu  [rbp+var_38], xmm0
0x18001807c  mov     [rbp+var_28], rax
0x180018080  lea     edi, [rax+10h]
0x180018083  mov     ecx, edi
0x180018085  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001808a  mov     qword ptr [rbp+var_38], rax
0x18001808e  mov     qword ptr [rbp+var_38+8], rax
0x180018092  lea     rbx, [rax+10h]
0x180018096  mov     [rbp+var_28], rbx
0x18001809a  mov     r8d, edi; Size
0x18001809d  lea     rdx, [rbp+Src]; Src
0x1800180a1  mov     rcx, rax; void *
0x1800180a4  call    memmove
0x1800180a9  mov     qword ptr [rbp+var_38+8], rbx
0x1800180ad  mov     [rbp+Block], 0
0x1800180b5  lea     rcx, [rbp+Block]
0x1800180b9  call    ??1?$_Tidy_guard@V?$vector@W4tagEnterprisePolicy@@V?$allocator@W4tagEnterprisePolicy@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<tagEnterprisePolicy>>::~_Tidy_guard<std::vector<tagEnterprisePolicy>>(void)
0x1800180be  nop
0x1800180bf  mov     dword ptr [rbp+Block], 3Ch ; '<'
0x1800180c6  mov     dword ptr [rbp+Block+4], 3Dh ; '='
0x1800180cd  mov     [rbp+var_40], 3Eh ; '>'
0x1800180d4  mov     dword ptr [rbp+Src], 9
0x1800180db  mov     dword ptr [rbp+Src+4], 7
0x1800180e2  mov     dword ptr [rbp+Src+8], 32h ; '2'
0x1800180e9  mov     [rbp+var_20], 0Ch
0x1800180f0  xor     ebx, ebx
0x1800180f2  mov     [rbp+var_50], rbx
0x1800180f6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::GetImpl(void)'::`2'::impl
0x1800180fd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QuickMachineRecoveryEnrolled_59112206>::__private_IsEnabled(void)
0x180018102  lea     r12d, [rdi-0Dh]
0x180018106  test    al, al
0x180018108  jz      loc_180018289
0x18001810e  xor     r15d, r15d
0x180018111  mov     rax, qword ptr [rbp+var_38+8]
0x180018115  mov     rcx, qword ptr [rbp+var_38]
0x180018119  sub     rax, rcx
0x18001811c  sar     rax, 2
0x180018120  test    rax, rax
0x180018123  jz      short loc_180018193
0x180018125  xor     edi, edi
0x180018127  test    rbx, rbx
0x18001812a  jz      short loc_180018145
0x18001812c  mov     edx, 30h ; '0'
0x180018131  mov     rcx, rbx; Block
0x180018134  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018139  mov     [rbp+var_50], 0
0x180018141  mov     rcx, qword ptr [rbp+var_38]
0x180018145  lea     rdx, [rbp+var_50]
0x180018149  mov     ecx, [rcx+rdi*4]
0x18001814c  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x180018151  mov     esi, eax
0x180018153  mov     rbx, [rbp+var_50]
0x180018157  test    eax, eax
0x180018159  js      loc_18001826C
0x18001815f  mov     edx, 1
0x180018164  cmp     [rbx+4], edx
0x180018167  jnz     short loc_180018179
0x180018169  cmp     [rbx+10h], r12w
0x18001816e  jnz     short loc_180018179
0x180018170  cmp     [rbx+18h], edx
0x180018173  jz      loc_1800182E2
0x180018179  add     r15d, edx
0x18001817c  mov     edi, r15d
0x18001817f  mov     rax, qword ptr [rbp+var_38+8]
0x180018183  mov     rcx, qword ptr [rbp+var_38]
0x180018187  sub     rax, rcx
0x18001818a  sar     rax, 2
0x18001818e  cmp     rdi, rax
0x180018191  jb      short loc_180018127
0x180018193  xor     edi, edi
0x180018195  mov     [rbp+Block], rdi
0x180018199  xor     r15d, r15d
0x18001819c  lea     r12, [rbp+Src]
0x1800181a0  test    rbx, rbx
0x1800181a3  jz      short loc_1800181BA
0x1800181a5  mov     edx, 30h ; '0'
0x1800181aa  mov     rcx, rbx; Block
0x1800181ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800181b2  mov     [rbp+var_50], 0
0x1800181ba  lea     rdx, [rbp+var_50]
0x1800181be  mov     ecx, [r12]
0x1800181c2  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x1800181c7  mov     esi, eax
0x1800181c9  mov     rbx, [rbp+var_50]
0x1800181cd  test    eax, eax
0x1800181cf  js      loc_180018349
0x1800181d5  mov     edx, 1
0x1800181da  cmp     [rbx+4], edx
0x1800181dd  jz      loc_180018335
0x1800181e3  add     r15d, edx
0x1800181e6  add     r12, 4
0x1800181ea  cmp     r15d, 3
0x1800181ee  jb      short loc_1800181A0
0x1800181f0  xor     r15d, r15d
0x1800181f3  lea     r12, [rbp+var_20]
0x1800181f7  test    rdi, rdi
0x1800181fa  jz      short loc_180018211
0x1800181fc  mov     edx, 28h ; '('
0x180018201  mov     rcx, rdi; Block
0x180018204  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018209  mov     [rbp+Block], 0
0x180018211  lea     rdx, [rbp+Block]
0x180018215  mov     ecx, [r12]
0x180018219  call    ?ReadPolicy@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)
0x18001821e  mov     esi, eax
0x180018220  test    eax, eax
0x180018222  js      loc_180018317
0x180018228  mov     rdi, [rbp+Block]
0x18001822c  mov     edx, 1
0x180018231  cmp     [rdi+4], edx
0x180018234  jz      loc_1800182FD
0x18001823a  add     r15d, edx
0x18001823d  add     r12, 4
0x180018241  cmp     r15d, edx
0x180018244  jb      short loc_1800181F7
0x180018246  mov     qword ptr [r14+4], 0
0x18001824e  lea     rcx, [r14+10h]; pvarg
0x180018252  call    cs:__imp_VariantClear
0x180018258  mov     esi, eax
0x18001825a  test    eax, eax
0x18001825c  jns     loc_180018313
0x180018262  mov     edx, 63Dh
0x180018267  jmp     loc_18001834E
0x18001826c  mov     rcx, [rbp+28h]; this
0x180018270  mov     r9d, eax; char *
0x180018273  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001827a  mov     edx, 5F2h; void *
0x18001827f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018284  jmp     loc_180018392
0x180018289  xor     edi, edi
0x18001828b  test    rbx, rbx
0x18001828e  jz      short loc_1800182A5
0x180018290  mov     edx, 30h ; '0'
0x180018295  mov     rcx, rbx; Block
0x180018298  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001829d  mov     [rbp+var_50], 0
0x1800182a5  lea     rdx, [rbp+var_50]
0x1800182a9  mov     ecx, dword ptr [rbp+rdi*4+Block]
0x1800182ad  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x1800182b2  mov     esi, eax
0x1800182b4  test    eax, eax
0x1800182b6  js      loc_180018376
0x1800182bc  mov     rbx, [rbp+var_50]
0x1800182c0  mov     edx, 1
0x1800182c5  cmp     [rbx+4], edx
0x1800182c8  jnz     short loc_1800182D6
0x1800182ca  cmp     [rbx+10h], r12w
0x1800182cf  jnz     short loc_1800182D6
0x1800182d1  cmp     [rbx+18h], edx
0x1800182d4  jz      short loc_1800182E2
0x1800182d6  add     edi, edx
0x1800182d8  cmp     edi, r12d
0x1800182db  jb      short loc_18001828B
0x1800182dd  jmp     loc_180018193
0x1800182e2  mov     [r14+18h], edx
0x1800182e6  mov     [r14+10h], r12w
0x1800182eb  mov     [r14+4], edx
0x1800182ef  mov     eax, [rbx+8]
0x1800182f2  mov     [r14+8], eax
0x1800182f6  xor     esi, esi
0x1800182f8  jmp     loc_180018392
0x1800182fd  mov     [r14+18h], edx
0x180018301  mov     word ptr [r14+10h], 3
0x180018308  mov     [r14+4], edx
0x18001830c  mov     eax, [rdi+8]
0x18001830f  mov     [r14+8], eax
0x180018313  xor     esi, esi
0x180018315  jmp     short loc_180018362
0x180018317  mov     rcx, [rbp+28h]; this
0x18001831b  mov     r9d, eax; char *
0x18001831e  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018325  mov     edx, 631h; void *
0x18001832a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001832f  mov     rdi, [rbp+Block]
0x180018333  jmp     short loc_180018362
0x180018335  mov     [r14+18h], edx
0x180018339  mov     word ptr [r14+10h], 3
0x180018340  mov     [r14+4], edx
0x180018344  mov     eax, [rbx+8]
0x180018347  jmp     short loc_18001830F
0x180018349  mov     edx, 623h; void *
0x18001834e  mov     r9d, eax; char *
0x180018351  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018358  mov     rcx, [rbp+28h]; this
0x18001835c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018361  nop
0x180018362  test    rdi, rdi
0x180018365  jz      short loc_180018392
0x180018367  mov     edx, 28h ; '('
0x18001836c  mov     rcx, rdi; Block
0x18001836f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018374  jmp     short loc_180018392
0x180018376  mov     rcx, [rbp+28h]; this
0x18001837a  mov     r9d, eax; char *
0x18001837d  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018384  mov     edx, 609h; void *
0x180018389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001838e  mov     rbx, [rbp+var_50]
0x180018392  test    rbx, rbx
0x180018395  jz      short loc_1800183A5
0x180018397  mov     edx, 30h ; '0'
0x18001839c  mov     rcx, rbx; Block
0x18001839f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800183a4  nop
0x1800183a5  lea     rcx, [rbp+var_38]
0x1800183a9  call    ??1?$vector@W4tagEnterprisePolicy@@V?$allocator@W4tagEnterprisePolicy@@@std@@@std@@QEAA@XZ; std::vector<tagEnterprisePolicy>::~vector<tagEnterprisePolicy>(void)
0x1800183ae  mov     eax, esi
0x1800183b0  lea     r11, [rsp+70h+var_s0]
0x1800183b5  mov     rbx, [r11+38h]
0x1800183b9  mov     rsi, [r11+40h]
0x1800183bd  mov     rsp, r11
0x1800183c0  pop     r15
0x1800183c2  pop     r14
0x1800183c4  pop     r12
0x1800183c6  pop     rdi
0x1800183c7  pop     rbp
0x1800183c8  retn
```
