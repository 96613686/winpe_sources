# KspEnumAlgorithmsInternal(unsigned __int64,ulong,ulong *,_NCryptAlgorithmName * *,ulong)

- ea: `0x18001f61c`
- end: `0x18001fe9d`
- name: `?KspEnumAlgorithmsInternal@@YAJ_KKPEAKPEAPEAU_NCryptAlgorithmName@@K@Z`
- size: `2177`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, unsigned int *, struct _NCryptAlgorithmName **, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ac90`

## callees

- `0x180009e82`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011444`
- `0x180011fd8`
- `0x1800122b4`
- `0x1800135dc`
- `0x180013734`
- `0x180013aac`
- `0x18001f61c`
- `0x18002b140`
- `0x18002ec0c`
- `0x18003af5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KspEnumAlgorithmsInternal(
        __int64 a1,
        int a2,
        unsigned int *a3,
        struct _NCryptAlgorithmName **a4,
        unsigned int a5)
{
  PVOID v7; // rcx
  int Handle; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // r14d
  int v12; // ebp
  int v13; // ecx
  int v14; // r12d
  int v15; // r13d
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  int v18; // edx
  __int64 v19; // rdi
  __int64 v20; // rcx
  int v21; // ecx
  unsigned int v22; // eax
  int v23; // edi
  __int64 v24; // r15
  size_t v25; // rcx
  size_t v26; // rdi
  struct _NCryptAlgorithmName *v27; // rax
  struct _NCryptAlgorithmName *v28; // r14
  unsigned __int16 *v29; // rdi
  __int64 v30; // rcx
  int v31; // eax
  _QWORD *v32; // rcx
  int v33; // edx
  unsigned int v34; // ebp
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // ebx
  DWORD v38; // r11d
  __int64 v39; // rbp
  unsigned __int16 *v40; // rdi
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v43; // ebx
  DWORD v44; // r11d
  __int64 v45; // rbp
  unsigned __int16 *v46; // rdi
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v51; // ebx
  unsigned __int64 v52; // r11
  __int64 v53; // rbp
  unsigned __int16 *v54; // rdi
  __int64 v55; // rcx
  __int64 v56; // rcx
  int v57; // ebx
  unsigned __int64 v58; // r11
  __int64 v59; // rbp
  unsigned __int16 *v60; // rdi
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // rcx
  int v68; // [rsp+30h] [rbp-58h]
  int v69; // [rsp+34h] [rbp-54h]
  __int64 v70; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v71[9]; // [rsp+40h] [rbp-48h] BYREF

  v70 = 0;
  v71[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v71[1] = 0;
  if ( a3 && a4 )
  {
    if ( (a5 & 0xFFFFFFBF) != 0 )
    {
      WppTraceIndent((__int64)&Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable', 2u);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          a5);
      }
      WppTraceIndent((__int64)v7, 2u);
      Handle = -2146893815;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 69;
LABEL_119:
        WPP_SF_d(v9[2], v10, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, (unsigned int)Handle);
        goto LABEL_120;
      }
      goto LABEL_120;
    }
    v11 = 0;
    v69 = 0;
    v68 = 0;
    if ( !a2 || (a2 & 4) != 0 || (a2 & 0x10) != 0 )
    {
      v13 = a2 & 0x10;
      v12 = 1;
      if ( !a2 )
        goto LABEL_18;
    }
    else
    {
      v12 = 0;
      v13 = 0;
    }
    v14 = 0;
    if ( (a2 & 8) == 0 )
    {
LABEL_19:
      if ( !v13 )
      {
        v15 = 0;
        goto LABEL_23;
      }
LABEL_21:
      v15 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
      {
        v11 = 1;
        v69 = 1;
      }
LABEL_23:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl)
        && (!a2 || (a2 & 0x80u) != 0) )
      {
        v68 = 1;
      }
      Handle = HtGetHandle(a1, 3, &v70);
      if ( Handle )
      {
        WppTraceIndent(v16, 2u);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_120;
        }
        v18 = 70;
        goto LABEL_32;
      }
      v19 = v70;
      Handle = KspEnterCriticalSection(v70 + 16);
      if ( Handle )
      {
        WppTraceIndent(v20, 2u);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_120;
        }
        v18 = 71;
LABEL_32:
        WPP_SF_sd(
          v17[2],
          v18,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
        goto LABEL_120;
      }
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v71, v19 + 16);
      v21 = v12 != 0 ? 4 : 0;
      v22 = v12 != 0;
      if ( v14 )
      {
        v22 += 3;
        v21 += 30;
      }
      v23 = v21 + 33;
      if ( !v15 )
        v23 = v21;
      v24 = v22 + 3;
      if ( !v15 )
        v24 = v22;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
      {
        if ( v11 )
        {
          v24 = (unsigned int)(v24 + 1);
          v23 += 7;
        }
        if ( v68 )
        {
          v24 = (unsigned int)(v24 + 1);
          v23 += 7;
        }
      }
      if ( (_DWORD)v24 )
      {
        v25 = (unsigned int)(2 * (v23 + 12 * v24));
        v26 = (unsigned int)v25;
        v27 = (struct _NCryptAlgorithmName *)MIDL_user_allocate(v25);
        v28 = v27;
        if ( !v27 )
        {
          Handle = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              72,
              &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
              WPP_pszIndent);
          }
          goto LABEL_120;
        }
        memset_0(v27, 0, v26);
        v29 = (unsigned __int16 *)&v28[v24];
        if ( v12 )
        {
          v28->pszName = v29;
          v28->dwClass = 3;
          v28->dwAlgOperations = 20;
          Handle = StringCchCopyW((unsigned __int16 *)&v28[v24], 4u, L"RSA");
          if ( Handle < 0 )
          {
            WppTraceIndent(v30, 2u);
            v31 = HR_Remap((unsigned int)Handle);
            Handle = v31;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_112;
            }
            v33 = 73;
LABEL_111:
            WPP_SF_sd(
              v32[2],
              v33,
              (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
              (_DWORD)WPP_pszIndent,
              v31);
LABEL_112:
            CspFreeH(v28);
            goto LABEL_120;
          }
          v34 = 1;
          v29 += 4;
        }
        else
        {
          v34 = 0;
        }
        if ( v14 )
        {
          v35 = v34;
          v28[v35].pszName = v29;
          v28[v35].dwClass = 4;
          v28[v35].dwAlgOperations = 24;
          v37 = StringCchCopyW(v29, 0xAu, L"ECDH_P256");
          if ( v37 < 0 )
          {
            WppTraceIndent(v36, v38 - 22);
            v31 = HR_Remap((unsigned int)v37);
            Handle = v31;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_112;
            }
            v33 = 74;
            goto LABEL_111;
          }
          v39 = v34 + 1;
          v40 = v29 + 10;
          v41 = v39;
          v28[v41].pszName = v40;
          v28[v41].dwClass = 4;
          v28[v41].dwAlgOperations = v38;
          v43 = StringCchCopyW(v40, 0xAu, L"ECDH_P384");
          if ( v43 < 0 )
          {
            WppTraceIndent(v42, 2u);
            v31 = HR_Remap((unsigned int)v43);
            Handle = v31;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_112;
            }
            v33 = 75;
            goto LABEL_111;
          }
          v45 = (unsigned int)(v39 + 1);
          v46 = v40 + 10;
          v47 = v45;
          v28[v47].pszName = v46;
          v28[v47].dwClass = 4;
          v28[v47].dwAlgOperations = v44;
          Handle = StringCchCopyW(v46, 0xAu, L"ECDH_P521");
          if ( Handle < 0 )
          {
            WppTraceIndent(v48, 2u);
            v31 = HR_Remap((unsigned int)Handle);
            Handle = v31;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_112;
            }
            v33 = 76;
            goto LABEL_111;
          }
          v34 = v45 + 1;
          v29 = v46 + 10;
        }
        if ( v15 )
        {
          v49 = v34;
          v28[v49].pszName = v29;
          v28[v49].dwClass = 5;
          v28[v49].dwAlgOperations = 16;
          v51 = StringCchCopyW(v29, 0xBu, L"ECDSA_P256");
          if ( v51 < 0 )
          {
            WppTraceIndent(v50, 2u);
            v31 = HR_Remap((unsigned int)v51);
            Handle = v31;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_112;
            }
            v33 = 77;
            goto LABEL_111;
          }
          v53 = v34 + 1;
          v54 = v29 + 11;
          v55 = v53;
          v28[v55].pszName = v54;
          v28[v55].dwClass = 5;
          v28[v55].dwAlgOperations = 16;
          v57 = StringCchCopyW(v54, v52, L"ECDSA_P384");
          if ( v57 < 0 )
          {
            WppTraceIndent(v56, 2u);
            v31 = HR_Remap((unsigned int)v57);
            Handle = v31;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_112;
            }
            v33 = 78;
            goto LABEL_111;
          }
          v59 = (unsigned int)(v53 + 1);
          v60 = v54 + 11;
          v61 = v59;
          v28[v61].pszName = v60;
          v28[v61].dwClass = 5;
          v28[v61].dwAlgOperations = 16;
          Handle = StringCchCopyW(v60, v58, L"ECDSA_P521");
          if ( Handle < 0 )
          {
            WppTraceIndent(v62, 2u);
            v31 = HR_Remap((unsigned int)Handle);
            Handle = v31;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_112;
            }
            v33 = 79;
            goto LABEL_111;
          }
          v34 = v59 + 1;
          v29 = v60 + 11;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
        {
          if ( v69 )
          {
            v63 = v34;
            v28[v63].pszName = v29;
            v28[v63].dwClass = 5;
            v28[v63].dwAlgOperations = 16;
            Handle = StringCchCopyW(v29, 7u, L"ML-DSA");
            if ( Handle < 0 )
            {
              WppTraceIndent(v64, 2u);
              v31 = HR_Remap((unsigned int)Handle);
              Handle = v31;
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_112;
              }
              v33 = 80;
              goto LABEL_111;
            }
            ++v34;
            v29 += 7;
          }
          if ( v68 )
          {
            v65 = v34;
            v28[v65].pszName = v29;
            v28[v65].dwClass = 8;
            v28[v65].dwAlgOperations = 128;
            Handle = StringCchCopyW(v29, 7u, L"ML-KEM");
            if ( Handle < 0 )
            {
              WppTraceIndent(v66, 2u);
              v31 = HR_Remap((unsigned int)Handle);
              Handle = v31;
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_112;
              }
              v33 = 81;
              goto LABEL_111;
            }
          }
        }
        *a4 = v28;
      }
      *a3 = v24;
      goto LABEL_120;
    }
LABEL_18:
    v14 = 1;
    if ( !a2 )
      goto LABEL_21;
    goto LABEL_19;
  }
  WppTraceIndent((__int64)&Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable', 2u);
  Handle = -2146893785;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 67;
    goto LABEL_119;
  }
LABEL_120:
  v71[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v71);
  return (unsigned int)Handle;
}

```

## disassembly

```asm
0x18001f61c  mov     r11, rsp
0x18001f61f  mov     [r11+8], rbx
0x18001f623  mov     [r11+20h], r9
0x18001f627  mov     [r11+18h], r8
0x18001f62b  push    rbp
0x18001f62c  push    rsi
0x18001f62d  push    rdi
0x18001f62e  push    r12
0x18001f630  push    r13
0x18001f632  push    r14
0x18001f634  push    r15
0x18001f636  sub     rsp, 50h
0x18001f63a  mov     rax, r9
0x18001f63d  mov     ebx, edx
0x18001f63f  mov     rdi, rcx
0x18001f642  xor     r15d, r15d
0x18001f645  mov     [r11-50h], r15
0x18001f649  lea     rcx, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001f650  mov     [r11-48h], rcx
0x18001f654  mov     [r11-40h], r15
0x18001f658  test    r8, r8
0x18001f65b  jz      loc_18001FE23
0x18001f661  test    rax, rax
0x18001f664  jz      loc_18001FE23
0x18001f66a  mov     ebp, [rsp+88h+arg_20]
0x18001f671  test    ebp, 0FFFFFFBFh
0x18001f677  jz      loc_18001F704
0x18001f67d  lea     edx, [r15+2]
0x18001f681  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f686  lea     rdi, WPP_GLOBAL_Control
0x18001f68d  lea     esi, [r15+1]
0x18001f691  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f698  cmp     rcx, rdi
0x18001f69b  jz      short loc_18001F6C7
0x18001f69d  test    [rcx+1Ch], sil
0x18001f6a1  jz      short loc_18001F6C7
0x18001f6a3  cmp     byte ptr [rcx+19h], 2
0x18001f6a7  jb      short loc_18001F6C7
0x18001f6a9  lea     edx, [rsi+43h]
0x18001f6ac  mov     [rsp+88h+var_68], ebp
0x18001f6b0  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f6b7  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001f6be  mov     rcx, [rcx+10h]
0x18001f6c2  call    WPP_SF_sd
0x18001f6c7  mov     edx, 2
0x18001f6cc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f6d1  mov     ebx, 80090009h
0x18001f6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6dd  cmp     rcx, rdi
0x18001f6e0  jz      loc_18001FE6D
0x18001f6e6  test    [rcx+1Ch], sil
0x18001f6ea  jz      loc_18001FE6D
0x18001f6f0  cmp     byte ptr [rcx+19h], 2
0x18001f6f4  jb      loc_18001FE6D
0x18001f6fa  mov     edx, 45h ; 'E'
0x18001f6ff  jmp     loc_18001FE59
0x18001f704  mov     r14d, r15d
0x18001f707  mov     [rsp+88h+var_54], r15d
0x18001f70c  mov     [rsp+88h+var_58], r15d
0x18001f711  mov     esi, 1
0x18001f716  test    ebx, ebx
0x18001f718  jz      short loc_18001F72C
0x18001f71a  test    bl, 4
0x18001f71d  jnz     short loc_18001F72C
0x18001f71f  test    bl, 10h
0x18001f722  jnz     short loc_18001F72C
0x18001f724  mov     ebp, r15d
0x18001f727  mov     ecx, r15d
0x18001f72a  jmp     short loc_18001F737
0x18001f72c  mov     ecx, ebx
0x18001f72e  and     ecx, 10h
0x18001f731  mov     ebp, esi
0x18001f733  test    ebx, ebx
0x18001f735  jz      short loc_18001F73F
0x18001f737  mov     r12d, r15d
0x18001f73a  test    bl, 8
0x18001f73d  jz      short loc_18001F746
0x18001f73f  mov     r12d, esi
0x18001f742  test    ebx, ebx
0x18001f744  jz      short loc_18001F74F
0x18001f746  test    ecx, ecx
0x18001f748  jnz     short loc_18001F74F
0x18001f74a  mov     r13d, r15d
0x18001f74d  jmp     short loc_18001F769
0x18001f74f  mov     r13d, esi
0x18001f752  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl(void)'::`2'::impl
0x18001f759  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(void)
0x18001f75e  test    al, al
0x18001f760  jz      short loc_18001F769
0x18001f762  mov     r14d, esi
0x18001f765  mov     [rsp+88h+var_54], esi
0x18001f769  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl(void)'::`2'::impl
0x18001f770  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(void)
0x18001f775  test    al, al
0x18001f777  jz      short loc_18001F786
0x18001f779  test    ebx, ebx
0x18001f77b  jz      short loc_18001F782
0x18001f77d  test    bl, 80h
0x18001f780  jz      short loc_18001F786
0x18001f782  mov     [rsp+88h+var_58], esi
0x18001f786  lea     r8, [rsp+88h+var_50]
0x18001f78b  mov     edx, 3
0x18001f790  mov     rcx, rdi
0x18001f793  call    HtGetHandle
0x18001f798  mov     ebx, eax
0x18001f79a  test    eax, eax
0x18001f79c  jz      short loc_18001F7F8
0x18001f79e  mov     edx, 2
0x18001f7a3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f7a8  lea     rdi, WPP_GLOBAL_Control
0x18001f7af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7b6  cmp     rcx, rdi
0x18001f7b9  jz      loc_18001FE6D
0x18001f7bf  test    [rcx+1Ch], sil
0x18001f7c3  jz      loc_18001FE6D
0x18001f7c9  cmp     byte ptr [rcx+19h], 2
0x18001f7cd  jb      loc_18001FE6D
0x18001f7d3  mov     edx, 46h ; 'F'
0x18001f7d8  mov     [rsp+88h+var_68], ebx
0x18001f7dc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f7e3  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001f7ea  mov     rcx, [rcx+10h]
0x18001f7ee  call    WPP_SF_sd
0x18001f7f3  jmp     loc_18001FE6D
0x18001f7f8  mov     rdi, [rsp+88h+var_50]
0x18001f7fd  lea     rcx, [rdi+10h]
0x18001f801  call    KspEnterCriticalSection
0x18001f806  mov     ebx, eax
0x18001f808  test    eax, eax
0x18001f80a  jz      short loc_18001F848
0x18001f80c  mov     edx, 2
0x18001f811  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f816  lea     rdi, WPP_GLOBAL_Control
0x18001f81d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f824  cmp     rcx, rdi
0x18001f827  jz      loc_18001FE6D
0x18001f82d  test    [rcx+1Ch], sil
0x18001f831  jz      loc_18001FE6D
0x18001f837  cmp     byte ptr [rcx+19h], 2
0x18001f83b  jb      loc_18001FE6D
0x18001f841  mov     edx, 47h ; 'G'
0x18001f846  jmp     short loc_18001F7D8
0x18001f848  lea     rdx, [rdi+10h]
0x18001f84c  lea     rcx, [rsp+88h+var_48]
0x18001f851  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001f856  mov     eax, ebp
0x18001f858  neg     eax
0x18001f85a  sbb     ecx, ecx
0x18001f85c  and     ecx, 4
0x18001f85f  mov     eax, r15d
0x18001f862  test    ebp, ebp
0x18001f864  setnz   al
0x18001f867  test    r12d, r12d
0x18001f86a  jz      short loc_18001F872
0x18001f86c  add     eax, 3
0x18001f86f  add     ecx, 1Eh
0x18001f872  lea     edi, [rcx+21h]
0x18001f875  test    r13d, r13d
0x18001f878  cmovz   edi, ecx
0x18001f87b  lea     r15d, [rax+3]
0x18001f87f  cmovz   r15d, eax
0x18001f883  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl(void)'::`2'::impl
0x18001f88a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(void)
0x18001f88f  test    al, al
0x18001f891  jz      short loc_18001F8AB
0x18001f893  test    r14d, r14d
0x18001f896  jz      short loc_18001F89E
0x18001f898  inc     r15d
0x18001f89b  add     edi, 7
0x18001f89e  cmp     [rsp+88h+var_58], 0
0x18001f8a3  jz      short loc_18001F8AB
0x18001f8a5  add     r15d, esi
0x18001f8a8  add     edi, 7
0x18001f8ab  test    r15d, r15d
0x18001f8ae  jz      loc_18001FE16
0x18001f8b4  lea     eax, [r15+r15*2]
0x18001f8b8  lea     ecx, [rdi+rax*4]
0x18001f8bb  add     ecx, ecx; size
0x18001f8bd  mov     edi, ecx
0x18001f8bf  call    MIDL_user_allocate
0x18001f8c4  mov     r14, rax
0x18001f8c7  test    rax, rax
0x18001f8ca  jnz     short loc_18001F91B
0x18001f8cc  mov     ebx, 8009000Eh
0x18001f8d1  lea     rdi, WPP_GLOBAL_Control
0x18001f8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8df  cmp     rcx, rdi
0x18001f8e2  jz      loc_18001FE6D
0x18001f8e8  test    [rcx+1Ch], sil
0x18001f8ec  jz      loc_18001FE6D
0x18001f8f2  cmp     byte ptr [rcx+19h], 2
0x18001f8f6  jb      loc_18001FE6D
0x18001f8fc  lea     edx, [rax+48h]
0x18001f8ff  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f906  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001f90d  mov     rcx, [rcx+10h]
0x18001f911  call    WPP_SF_s
0x18001f916  jmp     loc_18001FE6D
0x18001f91b  mov     r8, rdi; Size
0x18001f91e  xor     edx, edx; Val
0x18001f920  mov     rcx, r14; void *
0x18001f923  call    memset_0
0x18001f928  lea     rcx, [r15+r15*2]
0x18001f92c  lea     rdi, [r14+rcx*8]
0x18001f930  test    ebp, ebp
0x18001f932  jz      short loc_18001F9B1
0x18001f934  mov     [r14], rdi
0x18001f937  mov     dword ptr [r14+8], 3
0x18001f93f  mov     dword ptr [r14+0Ch], 14h
0x18001f947  lea     r8, Src; "RSA"
0x18001f94e  mov     edx, 4; unsigned __int64
0x18001f953  mov     rcx, rdi; unsigned __int16 *
0x18001f956  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f95b  mov     ebx, eax
0x18001f95d  test    eax, eax
0x18001f95f  jns     short loc_18001F9A9
0x18001f961  mov     edx, 2
0x18001f966  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f96b  mov     ecx, ebx
0x18001f96d  call    HR_Remap
0x18001f972  mov     ebx, eax
0x18001f974  lea     rdi, WPP_GLOBAL_Control
0x18001f97b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f982  cmp     rcx, rdi
0x18001f985  jz      loc_18001FE01
0x18001f98b  test    [rcx+1Ch], sil
0x18001f98f  jz      loc_18001FE01
0x18001f995  cmp     byte ptr [rcx+19h], 2
0x18001f999  jb      loc_18001FE01
0x18001f99f  mov     edx, 49h ; 'I'
0x18001f9a4  jmp     loc_18001FDE6
0x18001f9a9  mov     ebp, esi
0x18001f9ab  add     rdi, 8
0x18001f9af  jmp     short loc_18001F9B3
0x18001f9b1  xor     ebp, ebp
0x18001f9b3  test    r12d, r12d
0x18001f9b6  jz      loc_18001FB49
0x18001f9bc  mov     eax, ebp
0x18001f9be  lea     rcx, [rax+rax*2]
0x18001f9c2  mov     [r14+rcx*8], rdi
0x18001f9c6  mov     dword ptr [r14+rcx*8+8], 4
0x18001f9cf  mov     r11d, 18h
0x18001f9d5  mov     [r14+rcx*8+0Ch], r11d
0x18001f9da  lea     r8, aEcdhP256; "ECDH_P256"
0x18001f9e1  lea     r12d, [r11-0Eh]
0x18001f9e5  mov     edx, r12d; unsigned __int64
0x18001f9e8  mov     rcx, rdi; unsigned __int16 *
0x18001f9eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f9f0  mov     ebx, eax
0x18001f9f2  test    eax, eax
0x18001f9f4  jns     short loc_18001FA3D
0x18001f9f6  lea     edx, [r11-16h]
0x18001f9fa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f9ff  mov     ecx, ebx
0x18001fa01  call    HR_Remap
0x18001fa06  mov     ebx, eax
0x18001fa08  lea     rdi, WPP_GLOBAL_Control
0x18001fa0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa16  cmp     rcx, rdi
0x18001fa19  jz      loc_18001FE01
0x18001fa1f  test    [rcx+1Ch], sil
0x18001fa23  jz      loc_18001FE01
0x18001fa29  cmp     byte ptr [rcx+19h], 2
0x18001fa2d  jb      loc_18001FE01
0x18001fa33  lea     edx, [r12+40h]
0x18001fa38  jmp     loc_18001FDE6
0x18001fa3d  inc     ebp
0x18001fa3f  add     rdi, 14h
0x18001fa43  lea     rcx, ds:0[rbp*2]
0x18001fa4b  add     rcx, rbp
0x18001fa4e  mov     [r14+rcx*8], rdi
0x18001fa52  mov     dword ptr [r14+rcx*8+8], 4
0x18001fa5b  mov     [r14+rcx*8+0Ch], r11d
0x18001fa60  lea     r8, aEcdhP384; "ECDH_P384"
0x18001fa67  mov     rdx, r12; unsigned __int64
0x18001fa6a  mov     rcx, rdi; unsigned __int16 *
0x18001fa6d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001fa72  mov     ebx, eax
0x18001fa74  test    eax, eax
0x18001fa76  jns     short loc_18001FAC0
0x18001fa78  mov     edx, 2
0x18001fa7d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001fa82  mov     ecx, ebx
0x18001fa84  call    HR_Remap
0x18001fa89  mov     ebx, eax
0x18001fa8b  lea     rdi, WPP_GLOBAL_Control
0x18001fa92  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa99  cmp     rcx, rdi
0x18001fa9c  jz      loc_18001FE01
0x18001faa2  test    [rcx+1Ch], sil
0x18001faa6  jz      loc_18001FE01
0x18001faac  cmp     byte ptr [rcx+19h], 2
0x18001fab0  jb      loc_18001FE01
0x18001fab6  mov     edx, 4Bh ; 'K'
0x18001fabb  jmp     loc_18001FDE6
0x18001fac0  inc     ebp
0x18001fac2  add     rdi, 14h
0x18001fac6  lea     rcx, ds:0[rbp*2]
0x18001face  add     rcx, rbp
0x18001fad1  mov     [r14+rcx*8], rdi
  ... truncated ...
```
