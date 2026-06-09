# KspSetProviderPropertyInternal(unsigned __int64,ushort const *,uchar *,ulong,ulong)

- ea: `0x1800283dc`
- end: `0x180028a29`
- name: `?KspSetProviderPropertyInternal@@YAJ_KPEBGPEAEKK@Z`
- size: `1613`
- prototype: `int(unsigned __int64, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18002b000`

## callees

- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x1800135dc`
- `0x180013aac`
- `0x180013e10`
- `0x180014070`
- `0x180014648`
- `0x18001594c`
- `0x180018774`
- `0x1800283dc`
- `0x1800318e8`
- `0x18003af5c`
- `0x18003c20e`

## string_xrefs

- `0x180028681`: `SmartCardReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KspSetProviderPropertyInternal(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v9; // rsi
  unsigned int v10; // r14d
  PVOID v11; // rcx
  unsigned int Handle; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned int v25; // r14d
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  void **v31; // [rsp+30h] [rbp-28h] BYREF
  __int64 v32; // [rsp+38h] [rbp-20h]
  _QWORD v33[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v34; // [rsp+A0h] [rbp+48h] BYREF

  v9 = 0;
  v34 = 0;
  v31 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v32 = 0;
  v33[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v33[1] = 0;
  if ( !a1 || !a2 || (!a3 || !a4) && wcscmp_0(a2, L"Use Context") )
  {
    WppTraceIndent(a1, 2u);
    Handle = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 383, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073511LL);
    }
    goto LABEL_17;
  }
  v10 = a5;
  if ( (a5 & 0x3FFFFFBF) != 0 )
  {
    WppTraceIndent(a1, 2u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        384,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        v10);
    }
    WppTraceIndent((__int64)v11, 2u);
    Handle = -2146893815;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 385;
LABEL_15:
      v15 = Handle;
LABEL_16:
      WPP_SF_d(v13[2], v14, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v15);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  Handle = HtGetHandle(a1, 3, &v34);
  if ( Handle )
  {
    WppTraceIndent(v17, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        386,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle);
    }
    v9 = v34;
    goto LABEL_17;
  }
  v9 = v34;
  Handle = KspEnterCriticalSection(v34 + 16);
  if ( Handle )
  {
    WppTraceIndent(v18, 2u);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v20 = 387;
    goto LABEL_31;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v33, v9 + 16);
  if ( !wcscmp_0(a2, L"HWND Handle") )
  {
    if ( a4 == 8 )
    {
      *(_QWORD *)(v9 + 104) = *(_QWORD *)a3;
    }
    else
    {
      WppTraceIndent(v21, 2u);
      v15 = 2148073511LL;
      Handle = -2146893785;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 388;
        goto LABEL_16;
      }
    }
    goto LABEL_17;
  }
  if ( !wcscmp_0(a2, L"SmartCardReader") )
  {
    Handle = KsppAllocateAndCopyString(v9 + 144, a3, a4);
    if ( !Handle )
      goto LABEL_17;
    WppTraceIndent(v22, 2u);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v20 = 389;
    goto LABEL_31;
  }
  if ( !wcscmp_0(a2, L"Use Context") )
  {
    Handle = KsppAllocateAndCopyString(v9 + 80, a3, a4);
    if ( !Handle )
      goto LABEL_17;
    WppTraceIndent(v23, 2u);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v20 = 390;
    goto LABEL_31;
  }
  if ( wcscmp_0(a2, L"SmartcardRootCertStore") )
  {
    if ( (v10 & 0x40000000) == 0 )
    {
      WppTraceIndent(v24, 2u);
      v15 = 2148073511LL;
      Handle = -2146893785;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 397;
        goto LABEL_16;
      }
      goto LABEL_17;
    }
    Handle = KsppAddMiscProperty(v9 + 8, a2, a3, a4);
    if ( !Handle )
      goto LABEL_17;
    WppTraceIndent(v30, 2u);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v20 = 396;
LABEL_31:
    WPP_SF_sd(
      v19[2],
      v20,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
    goto LABEL_17;
  }
  if ( a4 != 8 )
  {
    WppTraceIndent(v24, 2u);
    v15 = 2148073511LL;
    Handle = -2146893785;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 391;
      goto LABEL_16;
    }
    goto LABEL_17;
  }
  v25 = v10 & 0x40;
  Handle = KsppGetCard(v9, v25);
  if ( Handle )
  {
    WppTraceIndent(v26, 2u);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v20 = 392;
    goto LABEL_31;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v31, *(_QWORD *)(v9 + 88) + 624LL);
  if ( !*(_DWORD *)(*(_QWORD *)(v9 + 88) + 700LL) )
  {
    Handle = KsppAuthenticateUser(v9 + 72, 1, 0, *(_DWORD *)(v9 + 112) | v25);
    if ( Handle )
    {
      WppTraceIndent(v28, 2u);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v20 = 394;
    }
    else
    {
      Handle = CspWriteRootCertStore(*(_QWORD *)(v9 + 88), a3);
      if ( !Handle )
        goto LABEL_17;
      WppTraceIndent(v29, 2u);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v20 = 395;
    }
    goto LABEL_31;
  }
  WppTraceIndent(v27, 2u);
  Handle = -2146435020;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 393;
    goto LABEL_15;
  }
LABEL_17:
  if ( v32 )
  {
    v32 = 0;
    KsppEndCardCall(v9 + 72);
  }
  v33[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v33);
  v31 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v31);
  return Handle;
}

```

## disassembly

```asm
0x1800283dc  push    rbp
0x1800283de  push    rbx
0x1800283df  push    rsi
0x1800283e0  push    rdi
0x1800283e1  push    r12
0x1800283e3  push    r13
0x1800283e5  push    r14
0x1800283e7  push    r15
0x1800283e9  mov     rbp, rsp
0x1800283ec  sub     rsp, 58h
0x1800283f0  mov     ebx, r9d
0x1800283f3  mov     r12, r8
0x1800283f6  mov     r15, rdx
0x1800283f9  mov     rdi, rcx
0x1800283fc  xor     esi, esi
0x1800283fe  mov     [rbp+arg_0], rsi
0x180028402  lea     r14, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180028409  mov     [rbp+var_28], r14
0x18002840d  mov     [rbp+var_20], rsi
0x180028411  mov     [rbp+var_18], r14
0x180028415  mov     [rbp+var_10], rsi
0x180028419  test    rcx, rcx
0x18002841c  jz      loc_1800289D0
0x180028422  test    rdx, rdx
0x180028425  jz      loc_1800289D0
0x18002842b  test    r8, r8
0x18002842e  jz      short loc_180028434
0x180028430  test    ebx, ebx
0x180028432  jnz     short loc_18002844B
0x180028434  lea     rdx, aUseContext; "Use Context"
0x18002843b  mov     rcx, r15; String1
0x18002843e  call    wcscmp_0
0x180028443  test    eax, eax
0x180028445  jnz     loc_1800289D0
0x18002844b  mov     r14d, [rbp+arg_20]
0x18002844f  test    r14d, 3FFFFFBFh
0x180028456  jz      loc_180028533
0x18002845c  mov     edx, 2
0x180028461  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028466  lea     rbx, WPP_GLOBAL_Control
0x18002846d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028474  cmp     rcx, rbx
0x180028477  jz      short loc_1800284A6
0x180028479  test    byte ptr [rcx+1Ch], 1
0x18002847d  jz      short loc_1800284A6
0x18002847f  cmp     byte ptr [rcx+19h], 2
0x180028483  jb      short loc_1800284A6
0x180028485  mov     edx, 180h
0x18002848a  mov     [rsp+58h+var_38], r14d
0x18002848f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180028496  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002849d  mov     rcx, [rcx+10h]
0x1800284a1  call    WPP_SF_sd
0x1800284a6  mov     edx, 2
0x1800284ab  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800284b0  mov     edi, 80090009h
0x1800284b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284bc  cmp     rcx, rbx
0x1800284bf  jz      short loc_1800284E5
0x1800284c1  test    byte ptr [rcx+1Ch], 1
0x1800284c5  jz      short loc_1800284E5
0x1800284c7  cmp     byte ptr [rcx+19h], 2
0x1800284cb  jb      short loc_1800284E5
0x1800284cd  mov     edx, 181h
0x1800284d2  mov     r9d, edi
0x1800284d5  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800284dc  mov     rcx, [rcx+10h]
0x1800284e0  call    WPP_SF_d
0x1800284e5  lea     r14, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x1800284ec  cmp     [rbp+var_20], 0
0x1800284f1  jz      short loc_180028505
0x1800284f3  mov     [rbp+var_20], 0
0x1800284fb  lea     rcx, [rsi+48h]
0x1800284ff  call    KsppEndCardCall
0x180028504  nop
0x180028505  mov     [rbp+var_18], r14
0x180028509  lea     rcx, [rbp+var_18]
0x18002850d  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180028512  nop
0x180028513  mov     [rbp+var_28], r14
0x180028517  lea     rcx, [rbp+var_28]
0x18002851b  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180028520  mov     eax, edi
0x180028522  add     rsp, 58h
0x180028526  pop     r15
0x180028528  pop     r14
0x18002852a  pop     r13
0x18002852c  pop     r12
0x18002852e  pop     rdi
0x18002852f  pop     rsi
0x180028530  pop     rbx
0x180028531  pop     rbp
0x180028532  retn
0x180028533  lea     r8, [rbp+arg_0]
0x180028537  mov     edx, 3
0x18002853c  mov     rcx, rdi
0x18002853f  call    HtGetHandle
0x180028544  mov     edi, eax
0x180028546  test    eax, eax
0x180028548  jz      short loc_18002859C
0x18002854a  mov     edx, 2
0x18002854f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028554  lea     rbx, WPP_GLOBAL_Control
0x18002855b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028562  cmp     rcx, rbx
0x180028565  jz      short loc_180028593
0x180028567  test    byte ptr [rcx+1Ch], 1
0x18002856b  jz      short loc_180028593
0x18002856d  cmp     byte ptr [rcx+19h], 2
0x180028571  jb      short loc_180028593
0x180028573  mov     edx, 182h
0x180028578  mov     [rsp+58h+var_38], edi
0x18002857c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180028583  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002858a  mov     rcx, [rcx+10h]
0x18002858e  call    WPP_SF_sd
0x180028593  mov     rsi, [rbp+arg_0]
0x180028597  jmp     loc_1800284E5
0x18002859c  mov     rsi, [rbp+arg_0]
0x1800285a0  lea     rcx, [rsi+10h]
0x1800285a4  call    KspEnterCriticalSection
0x1800285a9  mov     edi, eax
0x1800285ab  test    eax, eax
0x1800285ad  jz      short loc_180028609
0x1800285af  mov     edx, 2
0x1800285b4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800285b9  lea     rbx, WPP_GLOBAL_Control
0x1800285c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285c7  cmp     rcx, rbx
0x1800285ca  jz      loc_1800284E5
0x1800285d0  test    byte ptr [rcx+1Ch], 1
0x1800285d4  jz      loc_1800284E5
0x1800285da  cmp     byte ptr [rcx+19h], 2
0x1800285de  jb      loc_1800284E5
0x1800285e4  mov     edx, 183h
0x1800285e9  mov     [rsp+58h+var_38], edi
0x1800285ed  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800285f4  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800285fb  mov     rcx, [rcx+10h]
0x1800285ff  call    WPP_SF_sd
0x180028604  jmp     loc_1800284E5
0x180028609  lea     rdx, [rsi+10h]
0x18002860d  lea     rcx, [rbp+var_18]
0x180028611  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180028616  lea     rdx, aHwndHandle; "HWND Handle"
0x18002861d  mov     rcx, r15; String1
0x180028620  call    wcscmp_0
0x180028625  test    eax, eax
0x180028627  jnz     short loc_180028681
0x180028629  cmp     ebx, 8
0x18002862c  jz      short loc_180028674
0x18002862e  lea     edx, [rax+2]
0x180028631  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028636  mov     r9d, 80090027h
0x18002863c  mov     edi, r9d
0x18002863f  lea     rbx, WPP_GLOBAL_Control
0x180028646  mov     rcx, cs:WPP_GLOBAL_Control
0x18002864d  cmp     rcx, rbx
0x180028650  jz      loc_1800284E5
0x180028656  test    byte ptr [rcx+1Ch], 1
0x18002865a  jz      loc_1800284E5
0x180028660  cmp     byte ptr [rcx+19h], 2
0x180028664  jb      loc_1800284E5
0x18002866a  mov     edx, 184h
0x18002866f  jmp     loc_1800284D5
0x180028674  mov     rax, [r12]
0x180028678  mov     [rsi+68h], rax
0x18002867c  jmp     loc_1800284E5
0x180028681  lea     rdx, aSmartcardreade; "SmartCardReader"
0x180028688  mov     rcx, r15; String1
0x18002868b  call    wcscmp_0
0x180028690  test    eax, eax
0x180028692  jnz     short loc_1800286EF
0x180028694  lea     rcx, [rsi+90h]
0x18002869b  mov     r8d, ebx
0x18002869e  mov     rdx, r12
0x1800286a1  call    KsppAllocateAndCopyString
0x1800286a6  mov     edi, eax
0x1800286a8  test    eax, eax
0x1800286aa  jz      loc_1800284E5
0x1800286b0  mov     edx, 2
0x1800286b5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800286ba  lea     rbx, WPP_GLOBAL_Control
0x1800286c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286c8  cmp     rcx, rbx
0x1800286cb  jz      loc_1800284E5
0x1800286d1  test    byte ptr [rcx+1Ch], 1
0x1800286d5  jz      loc_1800284E5
0x1800286db  cmp     byte ptr [rcx+19h], 2
0x1800286df  jb      loc_1800284E5
0x1800286e5  mov     edx, 185h
0x1800286ea  jmp     loc_1800285E9
0x1800286ef  lea     rdx, aUseContext; "Use Context"
0x1800286f6  mov     rcx, r15; String1
0x1800286f9  call    wcscmp_0
0x1800286fe  test    eax, eax
0x180028700  jnz     short loc_18002875A
0x180028702  lea     rcx, [rsi+50h]
0x180028706  mov     r8d, ebx
0x180028709  mov     rdx, r12
0x18002870c  call    KsppAllocateAndCopyString
0x180028711  mov     edi, eax
0x180028713  test    eax, eax
0x180028715  jz      loc_1800284E5
0x18002871b  mov     edx, 2
0x180028720  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028725  lea     rbx, WPP_GLOBAL_Control
0x18002872c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028733  cmp     rcx, rbx
0x180028736  jz      loc_1800284E5
0x18002873c  test    byte ptr [rcx+1Ch], 1
0x180028740  jz      loc_1800284E5
0x180028746  cmp     byte ptr [rcx+19h], 2
0x18002874a  jb      loc_1800284E5
0x180028750  mov     edx, 186h
0x180028755  jmp     loc_1800285E9
0x18002875a  lea     rdx, aSmartcardrootc; "SmartcardRootCertStore"
0x180028761  mov     rcx, r15; String1
0x180028764  call    wcscmp_0
0x180028769  test    eax, eax
0x18002876b  jnz     loc_180028926
0x180028771  cmp     ebx, 8
0x180028774  jz      short loc_1800287BC
0x180028776  lea     edx, [rax+2]
0x180028779  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002877e  mov     r9d, 80090027h
0x180028784  mov     edi, r9d
0x180028787  lea     rbx, WPP_GLOBAL_Control
0x18002878e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028795  cmp     rcx, rbx
0x180028798  jz      loc_1800284E5
0x18002879e  test    byte ptr [rcx+1Ch], 1
0x1800287a2  jz      loc_1800284E5
0x1800287a8  cmp     byte ptr [rcx+19h], 2
0x1800287ac  jb      loc_1800284E5
0x1800287b2  mov     edx, 187h
0x1800287b7  jmp     loc_1800284D5
0x1800287bc  and     r14d, 40h
0x1800287c0  mov     edx, r14d
0x1800287c3  mov     rcx, rsi
0x1800287c6  call    KsppGetCard
0x1800287cb  mov     edi, eax
0x1800287cd  test    eax, eax
0x1800287cf  jz      short loc_180028810
0x1800287d1  mov     edx, 2
0x1800287d6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800287db  lea     rbx, WPP_GLOBAL_Control
0x1800287e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287e9  cmp     rcx, rbx
0x1800287ec  jz      loc_1800284E5
0x1800287f2  test    byte ptr [rcx+1Ch], 1
0x1800287f6  jz      loc_1800284E5
0x1800287fc  cmp     byte ptr [rcx+19h], 2
0x180028800  jb      loc_1800284E5
0x180028806  mov     edx, 188h
0x18002880b  jmp     loc_1800285E9
0x180028810  mov     rdx, [rsi+58h]
0x180028814  add     rdx, 270h
0x18002881b  lea     rcx, [rbp+var_28]
0x18002881f  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180028824  mov     rax, [rsi+58h]
0x180028828  cmp     dword ptr [rax+2BCh], 0
0x18002882f  jz      short loc_180028875
0x180028831  mov     edx, 2
0x180028836  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002883b  mov     edi, 80100034h
0x180028840  lea     rbx, WPP_GLOBAL_Control
0x180028847  mov     rcx, cs:WPP_GLOBAL_Control
0x18002884e  cmp     rcx, rbx
0x180028851  jz      loc_1800284E5
0x180028857  test    byte ptr [rcx+1Ch], 1
0x18002885b  jz      loc_1800284E5
0x180028861  cmp     byte ptr [rcx+19h], 2
0x180028865  jb      loc_1800284E5
0x18002886b  mov     edx, 189h
0x180028870  jmp     loc_1800284D2
0x180028875  or      r14d, [rsi+70h]
0x180028879  mov     r9d, r14d
0x18002887c  xor     r8d, r8d
0x18002887f  lea     edx, [r8+1]
0x180028883  lea     rcx, [rsi+48h]
0x180028887  call    KsppAuthenticateUser
0x18002888c  mov     edi, eax
0x18002888e  test    eax, eax
0x180028890  jz      short loc_1800288D1
0x180028892  mov     edx, 2
0x180028897  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002889c  lea     rbx, WPP_GLOBAL_Control
0x1800288a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288aa  cmp     rcx, rbx
0x1800288ad  jz      loc_1800284E5
0x1800288b3  test    byte ptr [rcx+1Ch], 1
0x1800288b7  jz      loc_1800284E5
0x1800288bd  cmp     byte ptr [rcx+19h], 2
0x1800288c1  jb      loc_1800284E5
0x1800288c7  mov     edx, 18Ah
0x1800288cc  jmp     loc_1800285E9
0x1800288d1  mov     rdx, r12
0x1800288d4  mov     rcx, [rsi+58h]
0x1800288d8  call    CspWriteRootCertStore
  ... truncated ...
```
