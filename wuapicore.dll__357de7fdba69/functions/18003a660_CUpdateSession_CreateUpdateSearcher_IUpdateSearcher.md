# CUpdateSession::CreateUpdateSearcher(IUpdateSearcher * *)

- ea: `0x18003a660`
- end: `0x18003aaa4`
- name: `?CreateUpdateSearcher@CUpdateSession@@UEAAJPEAPEAUIUpdateSearcher@@@Z`
- size: `1092`
- prototype: `__int64 __fastcall(CUpdateSession *__hidden this, struct IUpdateSearcher **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180021a40`
- `0x18003a660`
- `0x18003da48`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003a98e`
- `OLEAUT32!__imp_VariantInit` at `0x18003a98e`
- `OLEAUT32!__imp_VariantClear` at `0x18003a9f1`
- `OLEAUT32!__imp_VariantClear` at `0x18003aa18`
- `OLEAUT32!__imp_VariantClear` at `0x18003a9f1`
- `OLEAUT32!__imp_VariantClear` at `0x18003aa18`

## string_xrefs

- `0x18003a6dd`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003a77d`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003a7c9`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003a813`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003a916`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003a977`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003a9dc`: `C:\__w\1\s\src\Client\comapi\Session.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CUpdateSession::CreateUpdateSearcher(CUpdateSession *this, struct IUpdateSearcher **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  char *v6; // r13
  int v7; // eax
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  unsigned int v10; // r15d
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD, GUID *, _QWORD **); // rcx
  struct IUpdateSearcher *v20; // rax
  VARIANTARG v22; // [rsp+20h] [rbp-60h] BYREF
  __int64 v23; // [rsp+40h] [rbp-40h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, _QWORD **); // [rsp+48h] [rbp-38h] BYREF
  _QWORD *v25; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v24 = 0;
  v23 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 163;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v4,
      *(int *)&v22.vt);
LABEL_36:
    v19 = v24;
    goto LABEL_40;
  }
  *a2 = 0;
  v6 = (char *)this - 48;
  v25 = 0;
  v7 = ATL::CComObject<CUpdateSearcher>::CreateInstance(&v25);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v7,
      *(int *)&v22.vt);
    if ( v25 )
      (*(void (__fastcall **)(_QWORD *))(v25[1] + 16LL))(v25 + 1);
    goto LABEL_16;
  }
  v8 = v25;
  v9 = v25 + 1;
  (*(void (__fastcall **)(_QWORD *))(v25[1] + 8LL))(v25 + 1);
  v10 = *((_DWORD *)v6 + 8);
  v11 = v8[41];
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 24) + 16LL))(v11 + 24);
  v8[41] = v6;
  (*(void (__fastcall **)(char *))(*((_QWORD *)v6 + 3) + 8LL))(v6 + 24);
  v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(v8[3] + 80LL))(v8 + 3, *((_QWORD *)v6 + 15));
  v4 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v12,
      *(int *)&v22.vt);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
LABEL_16:
    v5 = 167;
    goto LABEL_27;
  }
  if ( v10 != -1 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v9 + 24LL))(v9, v10);
    v4 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
        (const char *)(unsigned int)v13,
        *(int *)&v22.vt);
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      goto LABEL_16;
    }
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD))*v9)(v9, &GUID_8f45abf1_f9ae_4b95_a933_f0f66e5056ea, &v24);
  v4 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v14,
      *(int *)&v22.vt);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    goto LABEL_16;
  }
  (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v24;
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  v4 = (**v15)(v15, &GUID_f258056c_186d_4fac_929b_c86ebf8f0ad8, &v23);
  if ( v4 < 0 )
  {
    v5 = 168;
    goto LABEL_27;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v23 + 48LL))(v23, 1, *((_QWORD *)this + 34));
  if ( v4 < 0 )
  {
    v5 = 169;
    goto LABEL_27;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v23 + 48LL))(v23, 2, *((_QWORD *)this + 35));
  if ( v4 < 0 )
  {
    v5 = 170;
    goto LABEL_27;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v23 + 48LL))(v23, 3, *((_QWORD *)this + 36));
  if ( v4 < 0 )
  {
    v5 = 171;
    goto LABEL_27;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl,
                          v16)
    && *((_BYTE *)this + 296) )
  {
    v25 = 0;
    v17 = (**v24)(v24, &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b, &v25);
    v4 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
        (const char *)(unsigned int)v17,
        *(int *)&v22.vt);
      goto LABEL_34;
    }
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v22 = pvarg;
    v18 = (*(__int64 (__fastcall **)(_QWORD *, __int64, VARIANTARG *))(*v25 + 32LL))(v25, 262159, &v22);
    v4 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
        (const char *)(unsigned int)v18,
        *(int *)&v22.vt);
      VariantClear(&pvarg);
LABEL_34:
      if ( v25 )
        (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
      goto LABEL_36;
    }
    VariantClear(&pvarg);
    if ( v25 )
      (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
  }
  v20 = (struct IUpdateSearcher *)v24;
  v19 = 0;
  v24 = 0;
  *a2 = v20;
  v4 = 0;
LABEL_40:
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
    v19 = v24;
  }
  if ( v19 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v19)[2])(v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003a660  mov     [rsp-28h+arg_10], rbx
0x18003a665  mov     [rsp-28h+arg_18], rsi
0x18003a66a  push    rbp
0x18003a66b  push    rdi
0x18003a66c  push    r13
0x18003a66e  push    r14
0x18003a670  push    r15
0x18003a672  mov     rbp, rsp
0x18003a675  sub     rsp, 80h
0x18003a67c  mov     rax, cs:__security_cookie
0x18003a683  xor     rax, rsp
0x18003a686  mov     [rbp+var_10], rax
0x18003a68a  mov     r14, rdx
0x18003a68d  mov     rsi, rcx
0x18003a690  mov     [rbp+var_38], 0
0x18003a698  mov     [rbp+var_40], 0
0x18003a6a0  test    rdx, rdx
0x18003a6a3  jnz     short loc_18003A6B4
0x18003a6a5  mov     ebx, 80004003h
0x18003a6aa  mov     edx, 0A3h
0x18003a6af  jmp     loc_18003A90F
0x18003a6b4  mov     qword ptr [rdx], 0
0x18003a6bb  lea     r13, [rcx-30h]
0x18003a6bf  mov     [rbp+var_30], 0
0x18003a6c7  lea     rcx, [rbp+var_30]
0x18003a6cb  call    ?CreateInstance@?$CComObject@VCUpdateSearcher@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUpdateSearcher>::CreateInstance(ATL::CComObject<CUpdateSearcher> * *)
0x18003a6d0  mov     ebx, eax
0x18003a6d2  test    eax, eax
0x18003a6d4  jns     short loc_18003A70E
0x18003a6d6  mov     rcx, [rbp+28h]; this
0x18003a6da  mov     r9d, eax; char *
0x18003a6dd  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003a6e4  mov     edx, 1Fh; void *
0x18003a6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a6ee  nop
0x18003a6ef  mov     rax, [rbp+var_30]
0x18003a6f3  test    rax, rax
0x18003a6f6  jz      short loc_18003A709
0x18003a6f8  lea     rcx, [rax+8]
0x18003a6fc  mov     rax, [rcx]
0x18003a6ff  mov     rax, [rax+10h]
0x18003a703  call    _guard_dispatch_icall
0x18003a708  nop
0x18003a709  jmp     loc_18003A835
0x18003a70e  mov     rbx, [rbp+var_30]
0x18003a712  lea     rdi, [rbx+8]
0x18003a716  mov     rax, [rdi]
0x18003a719  mov     rcx, rdi
0x18003a71c  mov     rax, [rax+8]
0x18003a720  call    _guard_dispatch_icall
0x18003a725  mov     r15d, [r13+20h]
0x18003a729  mov     rcx, [rbx+148h]
0x18003a730  test    rcx, rcx
0x18003a733  jz      short loc_18003A745
0x18003a735  add     rcx, 18h
0x18003a739  mov     rax, [rcx]
0x18003a73c  mov     rax, [rax+10h]
0x18003a740  call    _guard_dispatch_icall
0x18003a745  mov     [rbx+148h], r13
0x18003a74c  lea     rcx, [r13+18h]
0x18003a750  mov     rax, [rcx]
0x18003a753  mov     rax, [rax+8]
0x18003a757  call    _guard_dispatch_icall
0x18003a75c  lea     rcx, [rbx+18h]
0x18003a760  mov     rax, [rcx]
0x18003a763  mov     rdx, [r13+78h]
0x18003a767  mov     rax, [rax+50h]
0x18003a76b  call    _guard_dispatch_icall
0x18003a770  mov     ebx, eax
0x18003a772  test    eax, eax
0x18003a774  jns     short loc_18003A7A4
0x18003a776  mov     rcx, [rbp+28h]; this
0x18003a77a  mov     r9d, eax; char *
0x18003a77d  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003a784  mov     edx, 26h ; '&'; void *
0x18003a789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a78e  nop
0x18003a78f  mov     rax, [rdi]
0x18003a792  mov     rcx, rdi
0x18003a795  mov     rax, [rax+10h]
0x18003a799  call    _guard_dispatch_icall
0x18003a79e  nop
0x18003a79f  jmp     loc_18003A835
0x18003a7a4  cmp     r15d, 0FFFFFFFFh
0x18003a7a8  jz      short loc_18003A7ED
0x18003a7aa  mov     rax, [rdi]
0x18003a7ad  mov     edx, r15d
0x18003a7b0  mov     rcx, rdi
0x18003a7b3  mov     rax, [rax+18h]
0x18003a7b7  call    _guard_dispatch_icall
0x18003a7bc  mov     ebx, eax
0x18003a7be  test    eax, eax
0x18003a7c0  jns     short loc_18003A7ED
0x18003a7c2  mov     rcx, [rbp+28h]; this
0x18003a7c6  mov     r9d, eax; char *
0x18003a7c9  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003a7d0  mov     edx, 2Ah ; '*'; void *
0x18003a7d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a7da  nop
0x18003a7db  mov     rax, [rdi]
0x18003a7de  mov     rcx, rdi
0x18003a7e1  mov     rax, [rax+10h]
0x18003a7e5  call    _guard_dispatch_icall
0x18003a7ea  nop
0x18003a7eb  jmp     short loc_18003A835
0x18003a7ed  mov     rax, [rdi]
0x18003a7f0  lea     r8, [rbp+var_38]
0x18003a7f4  lea     rdx, _GUID_8f45abf1_f9ae_4b95_a933_f0f66e5056ea
0x18003a7fb  mov     rcx, rdi
0x18003a7fe  mov     rax, [rax]
0x18003a801  call    _guard_dispatch_icall
0x18003a806  mov     ebx, eax
0x18003a808  test    eax, eax
0x18003a80a  jns     short loc_18003A83F
0x18003a80c  mov     rcx, [rbp+28h]; this
0x18003a810  mov     r9d, eax; char *
0x18003a813  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003a81a  mov     edx, 2Dh ; '-'; void *
0x18003a81f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a824  nop
0x18003a825  mov     rax, [rdi]
0x18003a828  mov     rcx, rdi
0x18003a82b  mov     rax, [rax+10h]
0x18003a82f  call    _guard_dispatch_icall
0x18003a834  nop
0x18003a835  mov     edx, 0A7h
0x18003a83a  jmp     loc_18003A90F
0x18003a83f  mov     rax, [rdi]
0x18003a842  mov     rcx, rdi
0x18003a845  mov     rax, [rax+10h]
0x18003a849  call    _guard_dispatch_icall
0x18003a84e  nop
0x18003a84f  mov     rbx, [rbp+var_38]
0x18003a853  mov     rcx, [rbp+var_40]
0x18003a857  test    rcx, rcx
0x18003a85a  jz      short loc_18003A870
0x18003a85c  mov     rax, [rcx]
0x18003a85f  mov     rax, [rax+10h]
0x18003a863  call    _guard_dispatch_icall
0x18003a868  mov     [rbp+var_40], 0
0x18003a870  mov     rax, [rbx]
0x18003a873  lea     r8, [rbp+var_40]
0x18003a877  lea     rdx, _GUID_f258056c_186d_4fac_929b_c86ebf8f0ad8
0x18003a87e  mov     rcx, rbx
0x18003a881  mov     rax, [rax]
0x18003a884  call    _guard_dispatch_icall
0x18003a889  mov     ebx, eax
0x18003a88b  test    eax, eax
0x18003a88d  jns     short loc_18003A896
0x18003a88f  mov     edx, 0A8h
0x18003a894  jmp     short loc_18003A90F
0x18003a896  mov     rcx, [rbp+var_40]
0x18003a89a  mov     rax, [rcx]
0x18003a89d  mov     r8, [rsi+110h]
0x18003a8a4  mov     edx, 1
0x18003a8a9  mov     rax, [rax+30h]
0x18003a8ad  call    _guard_dispatch_icall
0x18003a8b2  mov     ebx, eax
0x18003a8b4  test    eax, eax
0x18003a8b6  jns     short loc_18003A8BF
0x18003a8b8  mov     edx, 0A9h
0x18003a8bd  jmp     short loc_18003A90F
0x18003a8bf  mov     rcx, [rbp+var_40]
0x18003a8c3  mov     rax, [rcx]
0x18003a8c6  mov     r8, [rsi+118h]
0x18003a8cd  mov     edx, 2
0x18003a8d2  mov     rax, [rax+30h]
0x18003a8d6  call    _guard_dispatch_icall
0x18003a8db  mov     ebx, eax
0x18003a8dd  test    eax, eax
0x18003a8df  jns     short loc_18003A8E8
0x18003a8e1  mov     edx, 0AAh
0x18003a8e6  jmp     short loc_18003A90F
0x18003a8e8  mov     rcx, [rbp+var_40]
0x18003a8ec  mov     rax, [rcx]
0x18003a8ef  mov     r8, [rsi+120h]
0x18003a8f6  mov     edx, 3
0x18003a8fb  mov     rax, [rax+30h]
0x18003a8ff  call    _guard_dispatch_icall
0x18003a904  mov     ebx, eax
0x18003a906  test    eax, eax
0x18003a908  jns     short loc_18003A927
0x18003a90a  mov     edx, 0ABh; void *
0x18003a90f  mov     rcx, [rbp+28h]; this
0x18003a913  mov     r9d, ebx; char *
0x18003a916  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003a91d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a922  jmp     loc_18003AA0E
0x18003a927  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl(void)'::`2'::impl
0x18003a92e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(void)
0x18003a933  test    al, al
0x18003a935  jz      loc_18003AA35
0x18003a93b  cmp     byte ptr [rsi+128h], 0
0x18003a942  jz      loc_18003AA35
0x18003a948  mov     [rbp+var_30], 0
0x18003a950  mov     rcx, [rbp+var_38]
0x18003a954  mov     rax, [rcx]
0x18003a957  lea     r8, [rbp+var_30]
0x18003a95b  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18003a962  mov     rax, [rax]
0x18003a965  call    _guard_dispatch_icall
0x18003a96a  mov     ebx, eax
0x18003a96c  test    eax, eax
0x18003a96e  jns     short loc_18003A98A
0x18003a970  mov     rcx, [rbp+28h]; this
0x18003a974  mov     r9d, eax; char *
0x18003a977  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003a97e  mov     edx, 0B2h; void *
0x18003a983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a988  jmp     short loc_18003A9F8
0x18003a98a  lea     rcx, [rbp+pvarg]; pvarg
0x18003a98e  call    cs:__imp_VariantInit
0x18003a994  mov     eax, 0Bh
0x18003a999  mov     word ptr [rbp+pvarg], ax
0x18003a99d  or      eax, 0FFFFFFFFh
0x18003a9a0  mov     word ptr [rbp+pvarg+8], ax
0x18003a9a4  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18003a9a8  movaps  [rbp+var_60], xmm0
0x18003a9ac  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18003a9b1  movsd   [rbp+var_50], xmm1
0x18003a9b6  mov     rcx, [rbp+var_30]
0x18003a9ba  mov     rax, [rcx]
0x18003a9bd  lea     r8, [rbp+var_60]
0x18003a9c1  mov     edx, 4000Fh
0x18003a9c6  mov     rax, [rax+20h]
0x18003a9ca  call    _guard_dispatch_icall
0x18003a9cf  mov     ebx, eax
0x18003a9d1  test    eax, eax
0x18003a9d3  jns     short loc_18003AA14
0x18003a9d5  mov     rcx, [rbp+28h]; this
0x18003a9d9  mov     r9d, eax; char *
0x18003a9dc  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003a9e3  mov     edx, 0B9h; void *
0x18003a9e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a9ed  lea     rcx, [rbp+pvarg]; pvarg
0x18003a9f1  call    cs:__imp_VariantClear
0x18003a9f7  nop
0x18003a9f8  mov     rcx, [rbp+var_30]
0x18003a9fc  test    rcx, rcx
0x18003a9ff  jz      short loc_18003AA0E
0x18003aa01  mov     rax, [rcx]
0x18003aa04  mov     rax, [rax+10h]
0x18003aa08  call    _guard_dispatch_icall
0x18003aa0d  nop
0x18003aa0e  mov     rcx, [rbp+var_38]
0x18003aa12  jmp     short loc_18003AA44
0x18003aa14  lea     rcx, [rbp+pvarg]; pvarg
0x18003aa18  call    cs:__imp_VariantClear
0x18003aa1e  nop
0x18003aa1f  mov     rcx, [rbp+var_30]
0x18003aa23  test    rcx, rcx
0x18003aa26  jz      short loc_18003AA35
0x18003aa28  mov     rax, [rcx]
0x18003aa2b  mov     rax, [rax+10h]
0x18003aa2f  call    _guard_dispatch_icall
0x18003aa34  nop
0x18003aa35  mov     rax, [rbp+var_38]
0x18003aa39  xor     ecx, ecx
0x18003aa3b  mov     [rbp+var_38], rcx
0x18003aa3f  mov     [r14], rax
0x18003aa42  xor     ebx, ebx
0x18003aa44  mov     rdx, [rbp+var_40]
0x18003aa48  test    rdx, rdx
0x18003aa4b  jz      short loc_18003AA68
0x18003aa4d  mov     rax, [rdx]
0x18003aa50  mov     rcx, rdx
0x18003aa53  mov     rax, [rax+10h]
0x18003aa57  call    _guard_dispatch_icall
0x18003aa5c  mov     [rbp+var_40], 0
0x18003aa64  mov     rcx, [rbp+var_38]
0x18003aa68  test    rcx, rcx
0x18003aa6b  jz      short loc_18003AA7A
0x18003aa6d  mov     rdx, [rcx]
0x18003aa70  mov     rax, [rdx+10h]
0x18003aa74  call    _guard_dispatch_icall
0x18003aa79  nop
0x18003aa7a  mov     eax, ebx
0x18003aa7c  mov     rcx, [rbp+var_10]
0x18003aa80  xor     rcx, rsp; StackCookie
0x18003aa83  call    __security_check_cookie
0x18003aa88  lea     r11, [rsp+80h+var_s0]
0x18003aa90  mov     rbx, [r11+40h]
0x18003aa94  mov     rsi, [r11+48h]
0x18003aa98  mov     rsp, r11
0x18003aa9b  pop     r15
0x18003aa9d  pop     r14
0x18003aa9f  pop     r13
0x18003aaa1  pop     rdi
0x18003aaa2  pop     rbp
0x18003aaa3  retn
```
