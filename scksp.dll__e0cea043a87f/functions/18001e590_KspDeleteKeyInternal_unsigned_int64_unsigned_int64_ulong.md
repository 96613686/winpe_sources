# KspDeleteKeyInternal(unsigned __int64,unsigned __int64,ulong)

- ea: `0x18001e590`
- end: `0x18001e923`
- name: `?KspDeleteKeyInternal@@YAJ_K0K@Z`
- size: `915`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002ab20`

## callees

- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x180012d08`
- `0x1800135dc`
- `0x180013aac`
- `0x180014648`
- `0x1800146c4`
- `0x18001594c`
- `0x18001e590`
- `0x18002e180`
- `0x18003af5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KspDeleteKeyInternal(__int64 a1, __int64 a2, int a3)
{
  char v3; // r15
  __int64 v5; // r14
  int v6; // r12d
  PVOID v7; // rcx
  unsigned int Handle; // edi
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  int v11; // edx
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v20; // [rsp+30h] [rbp-38h] BYREF
  void **v21; // [rsp+38h] [rbp-30h] BYREF
  __int64 v22; // [rsp+40h] [rbp-28h]
  _QWORD v23[4]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+60h] BYREF

  v3 = a3;
  v20 = 0;
  v5 = 0;
  v24 = 0;
  v6 = 0;
  v21 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v22 = 0;
  v23[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v23[1] = 0;
  if ( (a3 & 0xFFFFFFBF) != 0 )
  {
    WppTraceIndent(a1, 2u);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        v3);
    }
    WppTraceIndent((__int64)v7, 2u);
    Handle = -2146893815;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073481LL);
    }
    goto LABEL_44;
  }
  Handle = HtGetHandle(a1, 3, &v20);
  if ( Handle )
  {
    WppTraceIndent(v9, 2u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_44;
    }
    v11 = 43;
    goto LABEL_43;
  }
  v12 = v20;
  Handle = KspEnterCriticalSection(v20 + 16);
  if ( Handle )
  {
    WppTraceIndent(v13, 2u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_44;
    }
    v11 = 44;
    goto LABEL_43;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v23, v12 + 16);
  Handle = HtGetHandle(a2, 2, &v24);
  if ( !Handle )
  {
    v6 = 1;
    v5 = v24;
    if ( !*(_DWORD *)(v24 + 1048) || !*(_DWORD *)(v24 + 1056) )
      goto LABEL_44;
    Handle = KsppBeginCardCall(v24 + 1072);
    if ( Handle )
    {
      WppTraceIndent(v15, 2u);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      v11 = 46;
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v21, *(_QWORD *)(v5 + 1088) + 624LL);
      Handle = KsppAuthenticateUser(v5 + 1072, 1, 0, *(_DWORD *)(v5 + 1112) | v3 & 0x40u);
      if ( Handle )
      {
        WppTraceIndent(v16, 2u);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_44;
        }
        v11 = 47;
      }
      else
      {
        LOBYTE(v17) = *(_BYTE *)(v5 + 1068);
        Handle = CspRemoveContainer(*(_QWORD *)(v5 + 1088), v5, v17);
        if ( !Handle )
          goto LABEL_44;
        WppTraceIndent(v18, 2u);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_44;
        }
        v11 = 48;
      }
    }
LABEL_43:
    WPP_SF_sd(
      v10[2],
      v11,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
    goto LABEL_44;
  }
  WppTraceIndent(v14, 2u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
  }
  v5 = v24;
LABEL_44:
  if ( v22 )
  {
    v22 = 0;
    KsppEndCardCall(v5 + 1072);
  }
  if ( v6 )
    HtDeleteHandle(a2, 2);
  v23[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v23);
  v21 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v21);
  return Handle;
}

```

## disassembly

```asm
0x18001e590  push    rbp
0x18001e592  push    rbx
0x18001e593  push    rsi
0x18001e594  push    rdi
0x18001e595  push    r12
0x18001e597  push    r13
0x18001e599  push    r14
0x18001e59b  push    r15
0x18001e59d  mov     rbp, rsp
0x18001e5a0  sub     rsp, 68h
0x18001e5a4  mov     r15d, r8d
0x18001e5a7  mov     r13, rdx
0x18001e5aa  xor     ebx, ebx
0x18001e5ac  mov     [rbp+var_38], rbx
0x18001e5b0  mov     r14d, ebx
0x18001e5b3  mov     [rbp+arg_18], rbx
0x18001e5b7  mov     r12d, ebx
0x18001e5ba  lea     rsi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001e5c1  mov     [rbp+var_30], rsi
0x18001e5c5  mov     [rbp+var_28], rbx
0x18001e5c9  mov     [rbp+var_20], rsi
0x18001e5cd  mov     [rbp+var_18], rbx
0x18001e5d1  test    r8d, 0FFFFFFBFh
0x18001e5d8  jz      loc_18001E672
0x18001e5de  lea     ebx, [r14+2]
0x18001e5e2  mov     edx, ebx
0x18001e5e4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e5e9  lea     rsi, WPP_GLOBAL_Control
0x18001e5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5f7  cmp     rcx, rsi
0x18001e5fa  jz      short loc_18001E626
0x18001e5fc  test    byte ptr [rcx+1Ch], 1
0x18001e600  jz      short loc_18001E626
0x18001e602  cmp     [rcx+19h], bl
0x18001e605  jb      short loc_18001E626
0x18001e607  lea     edx, [rbx+27h]
0x18001e60a  mov     [rsp+68h+var_48], r15d
0x18001e60f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001e616  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001e61d  mov     rcx, [rcx+10h]
0x18001e621  call    WPP_SF_sd
0x18001e626  mov     edx, ebx
0x18001e628  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e62d  mov     edi, 80090009h
0x18001e632  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e639  cmp     rcx, rsi
0x18001e63c  jz      loc_18001E8C3
0x18001e642  test    byte ptr [rcx+1Ch], 1
0x18001e646  jz      loc_18001E8C3
0x18001e64c  cmp     [rcx+19h], bl
0x18001e64f  jb      loc_18001E8C3
0x18001e655  mov     edx, 2Ah ; '*'
0x18001e65a  mov     r9d, edi
0x18001e65d  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001e664  mov     rcx, [rcx+10h]
0x18001e668  call    WPP_SF_d
0x18001e66d  jmp     loc_18001E8C3
0x18001e672  lea     r8, [rbp+var_38]
0x18001e676  mov     edx, 3
0x18001e67b  call    HtGetHandle
0x18001e680  mov     edi, eax
0x18001e682  test    eax, eax
0x18001e684  jz      short loc_18001E6C4
0x18001e686  mov     ebx, 2
0x18001e68b  mov     edx, ebx
0x18001e68d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e692  lea     rsi, WPP_GLOBAL_Control
0x18001e699  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6a0  cmp     rcx, rsi
0x18001e6a3  jz      loc_18001E8C3
0x18001e6a9  test    byte ptr [rcx+1Ch], 1
0x18001e6ad  jz      loc_18001E8C3
0x18001e6b3  cmp     [rcx+19h], bl
0x18001e6b6  jb      loc_18001E8C3
0x18001e6bc  lea     edx, [rbx+29h]
0x18001e6bf  jmp     loc_18001E8A8
0x18001e6c4  mov     rbx, [rbp+var_38]
0x18001e6c8  lea     rcx, [rbx+10h]
0x18001e6cc  call    KspEnterCriticalSection
0x18001e6d1  mov     edi, eax
0x18001e6d3  test    eax, eax
0x18001e6d5  jz      short loc_18001E715
0x18001e6d7  mov     ebx, 2
0x18001e6dc  mov     edx, ebx
0x18001e6de  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e6e3  lea     rsi, WPP_GLOBAL_Control
0x18001e6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6f1  cmp     rcx, rsi
0x18001e6f4  jz      loc_18001E8C3
0x18001e6fa  test    byte ptr [rcx+1Ch], 1
0x18001e6fe  jz      loc_18001E8C3
0x18001e704  cmp     [rcx+19h], bl
0x18001e707  jb      loc_18001E8C3
0x18001e70d  lea     edx, [rbx+2Ah]
0x18001e710  jmp     loc_18001E8A8
0x18001e715  lea     rdx, [rbx+10h]
0x18001e719  lea     rcx, [rbp+var_20]
0x18001e71d  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001e722  lea     r8, [rbp+arg_18]
0x18001e726  mov     ebx, 2
0x18001e72b  mov     edx, ebx
0x18001e72d  mov     rcx, r13
0x18001e730  call    HtGetHandle
0x18001e735  mov     edi, eax
0x18001e737  test    eax, eax
0x18001e739  jz      short loc_18001E787
0x18001e73b  mov     edx, ebx
0x18001e73d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e742  lea     rsi, WPP_GLOBAL_Control
0x18001e749  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e750  cmp     rcx, rsi
0x18001e753  jz      short loc_18001E77E
0x18001e755  test    byte ptr [rcx+1Ch], 1
0x18001e759  jz      short loc_18001E77E
0x18001e75b  cmp     [rcx+19h], bl
0x18001e75e  jb      short loc_18001E77E
0x18001e760  lea     edx, [rbx+2Bh]
0x18001e763  mov     [rsp+68h+var_48], edi
0x18001e767  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001e76e  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001e775  mov     rcx, [rcx+10h]
0x18001e779  call    WPP_SF_sd
0x18001e77e  mov     r14, [rbp+arg_18]
0x18001e782  jmp     loc_18001E8C3
0x18001e787  mov     r12d, 1
0x18001e78d  mov     r14, [rbp+arg_18]
0x18001e791  cmp     dword ptr [r14+418h], 0
0x18001e799  jz      loc_18001E8CA
0x18001e79f  cmp     dword ptr [r14+420h], 0
0x18001e7a7  jz      loc_18001E8CA
0x18001e7ad  lea     rsi, [r14+430h]
0x18001e7b4  mov     rcx, rsi
0x18001e7b7  call    KsppBeginCardCall
0x18001e7bc  mov     edi, eax
0x18001e7be  test    eax, eax
0x18001e7c0  jz      short loc_18001E7FD
0x18001e7c2  mov     edx, ebx
0x18001e7c4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e7c9  lea     rsi, WPP_GLOBAL_Control
0x18001e7d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7d7  cmp     rcx, rsi
0x18001e7da  jz      loc_18001E8C3
0x18001e7e0  test    [rcx+1Ch], r12b
0x18001e7e4  jz      loc_18001E8C3
0x18001e7ea  cmp     [rcx+19h], bl
0x18001e7ed  jb      loc_18001E8C3
0x18001e7f3  lea     edx, [r12+2Dh]
0x18001e7f8  jmp     loc_18001E8A8
0x18001e7fd  mov     rdx, [r14+440h]
0x18001e804  add     rdx, 270h
0x18001e80b  lea     rcx, [rbp+var_30]
0x18001e80f  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18001e814  and     r15d, 40h
0x18001e818  or      r15d, [r14+458h]
0x18001e81f  mov     r9d, r15d
0x18001e822  xor     r8d, r8d
0x18001e825  mov     edx, r12d
0x18001e828  mov     rcx, rsi
0x18001e82b  call    KsppAuthenticateUser
0x18001e830  mov     edi, eax
0x18001e832  test    eax, eax
0x18001e834  jz      short loc_18001E862
0x18001e836  mov     edx, ebx
0x18001e838  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e83d  lea     rsi, WPP_GLOBAL_Control
0x18001e844  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e84b  cmp     rcx, rsi
0x18001e84e  jz      short loc_18001E8C3
0x18001e850  test    [rcx+1Ch], r12b
0x18001e854  jz      short loc_18001E8C3
0x18001e856  cmp     [rcx+19h], bl
0x18001e859  jb      short loc_18001E8C3
0x18001e85b  mov     edx, 2Fh ; '/'
0x18001e860  jmp     short loc_18001E8A8
0x18001e862  mov     r8b, [r14+42Ch]
0x18001e869  mov     rdx, r14
0x18001e86c  mov     rcx, [r14+440h]
0x18001e873  call    CspRemoveContainer
0x18001e878  mov     edi, eax
0x18001e87a  test    eax, eax
0x18001e87c  jz      short loc_18001E8C3
0x18001e87e  mov     edx, ebx
0x18001e880  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e885  lea     rsi, WPP_GLOBAL_Control
0x18001e88c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e893  cmp     rcx, rsi
0x18001e896  jz      short loc_18001E8C3
0x18001e898  test    [rcx+1Ch], r12b
0x18001e89c  jz      short loc_18001E8C3
0x18001e89e  cmp     [rcx+19h], bl
0x18001e8a1  jb      short loc_18001E8C3
0x18001e8a3  mov     edx, 30h ; '0'
0x18001e8a8  mov     [rsp+68h+var_48], edi
0x18001e8ac  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001e8b3  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001e8ba  mov     rcx, [rcx+10h]
0x18001e8be  call    WPP_SF_sd
0x18001e8c3  lea     rsi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001e8ca  cmp     [rbp+var_28], 0
0x18001e8cf  jz      short loc_18001E8E5
0x18001e8d1  mov     [rbp+var_28], 0
0x18001e8d9  lea     rcx, [r14+430h]
0x18001e8e0  call    KsppEndCardCall
0x18001e8e5  test    r12d, r12d
0x18001e8e8  jz      short loc_18001E8F5
0x18001e8ea  mov     edx, ebx
0x18001e8ec  mov     rcx, r13
0x18001e8ef  call    HtDeleteHandle
0x18001e8f4  nop
0x18001e8f5  mov     [rbp+var_20], rsi
0x18001e8f9  lea     rcx, [rbp+var_20]
0x18001e8fd  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18001e902  nop
0x18001e903  mov     [rbp+var_30], rsi
0x18001e907  lea     rcx, [rbp+var_30]
0x18001e90b  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18001e910  mov     eax, edi
0x18001e912  add     rsp, 68h
0x18001e916  pop     r15
0x18001e918  pop     r14
0x18001e91a  pop     r13
0x18001e91c  pop     r12
0x18001e91e  pop     rdi
0x18001e91f  pop     rsi
0x18001e920  pop     rbx
0x18001e921  pop     rbp
0x18001e922  retn
```
