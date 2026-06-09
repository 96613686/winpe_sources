# WmiConvertDispatchArray(tagVARIANT &,ATL::CComPtr<IDispatch> &,long)

- ea: `0x180026120`
- end: `0x180026413`
- name: `?WmiConvertDispatchArray@@YAJAEAUtagVARIANT@@AEAV?$CComPtr@UIDispatch@@@ATL@@J@Z`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800265f0`

## callees

- `0x18000c0b0`
- `0x180019114`
- `0x180024ff4`
- `0x180025034`
- `0x180026120`
- `0x1800265f0`
- `0x180036010`

## import_xrefs

- `msvcrt!wcstol` at `0x1800261e7`
- `msvcrt!wcstol` at `0x1800262b5`
- `msvcrt!wcstol` at `0x1800261e7`
- `msvcrt!wcstol` at `0x1800262b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002639e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002639e`
- `OLEAUT32!__imp_VariantInit` at `0x1800262eb`
- `OLEAUT32!__imp_VariantInit` at `0x18002633c`
- `OLEAUT32!__imp_VariantInit` at `0x1800262eb`
- `OLEAUT32!__imp_VariantInit` at `0x18002633c`
- `OLEAUT32!__imp_VariantClear` at `0x18002638f`
- `OLEAUT32!__imp_VariantClear` at `0x18002638f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026221`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026221`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800263bd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800263bd`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002637f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002637f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WmiConvertDispatchArray(__int64 a1, _QWORD *a2, int a3)
{
  int v6; // r14d
  int v7; // r13d
  signed int v8; // edi
  unsigned int v9; // r15d
  VARTYPE v10; // ax
  VARTYPE v11; // bx
  SAFEARRAY *v12; // rsi
  bool v13; // di
  int v14; // eax
  int v15; // edx
  void *bstrVal; // r8
  __int64 v18; // [rsp+50h] [rbp-49h] BYREF
  wchar_t *EndPtr; // [rsp+58h] [rbp-41h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-39h] BYREF
  wchar_t *v21; // [rsp+68h] [rbp-31h] BYREF
  __int64 v22; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG pv; // [rsp+78h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-9h] BYREF
  __int128 v25; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+B8h] [rbp+1Fh]
  unsigned int v27; // [rsp+108h] [rbp+6Fh] BYREF
  int v28; // [rsp+110h] [rbp+77h]
  wchar_t *String; // [rsp+118h] [rbp+7Fh] BYREF

  v28 = a3;
  v6 = -2147217407;
  v7 = 0;
  if ( *a2 )
  {
    ATL::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>(&v18);
    if ( v18 )
    {
      ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(
        &v22,
        *a2);
      if ( !v22 )
      {
        v8 = 0;
        v9 = -1;
        v27 = -1;
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v18 + 104LL))(
                   v18,
                   2,
                   v27,
                   &v27) )
        {
          String = 0;
          EndPtr = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v18 + 96LL))(v18, v27, &String) >= 0 )
          {
            wcstol(String, &EndPtr, 10);
            if ( !*EndPtr )
              ++v8;
          }
        }
        v10 = 12;
        if ( v8 )
          v10 = CimTypeToVtType(a3);
        v11 = v10;
        rgsabound.cElements = v8;
        rgsabound.lLbound = 0;
        v12 = SafeArrayCreate(v10, 1u, &rgsabound);
        if ( v12 )
        {
          if ( v8 > 0 )
          {
            v13 = 1;
            v27 = -1;
            v25 = 0;
            v26 = 0;
            v21 = 0;
            while ( 1 )
            {
              v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v18 + 104LL))(
                      v18,
                      2,
                      v9,
                      &v27);
              if ( v14 < 0 )
                break;
              if ( v14 == 1 )
                goto LABEL_29;
              EndPtr = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v18 + 96LL))(v18, v27, &EndPtr) < 0 )
                goto LABEL_26;
              v15 = wcstol(EndPtr, &v21, 10);
              LODWORD(String) = v15;
              if ( *v21 )
                goto LABEL_27;
              if ( v15 == v7
                && (++v7,
                    memset(&pvarg, 0, sizeof(pvarg)),
                    VariantInit(&pvarg),
                    (*(int (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v18 + 64LL))(
                      v18,
                      v27,
                      0,
                      2,
                      &v25,
                      &pvarg,
                      0,
                      0) >= 0) )
              {
                memset(&pv, 0, sizeof(pv));
                VariantInit(&pv);
                v6 = WmiVariantChangeType(&pv, &pvarg, v28);
                if ( v6 >= 0 )
                {
                  if ( ((v11 - 8) & 0xFFFA) != 0 || (bstrVal = pv.bstrVal, v11 == 12) )
                    bstrVal = &pv.decVal.8;
                  v13 = SafeArrayPutElement(v12, (LONG *)&String, bstrVal) == 0;
                }
                VariantClear(&pv);
              }
              else
              {
LABEL_26:
                v13 = 0;
              }
LABEL_27:
              SysFreeString(EndPtr);
              if ( !v13 )
              {
LABEL_29:
                if ( v13 )
                  break;
                SafeArrayDestroy(v12);
                goto LABEL_33;
              }
              v9 = v27;
            }
          }
          *(_WORD *)a1 = v11 | 0x2000;
          *(_QWORD *)(a1 + 8) = v12;
          v6 = 0;
        }
        else
        {
          v6 = -2147217402;
        }
      }
LABEL_33:
      ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v22);
    }
    ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v18);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180026120  mov     [rsp-8+arg_0], rbx
0x180026125  mov     [rsp-8+arg_10], r8d
0x18002612a  push    rbp
0x18002612b  push    rsi
0x18002612c  push    rdi
0x18002612d  push    r12
0x18002612f  push    r13
0x180026131  push    r14
0x180026133  push    r15
0x180026135  lea     rbp, [rsp-27h]
0x18002613a  sub     rsp, 0C0h
0x180026141  mov     esi, r8d
0x180026144  mov     rbx, rdx
0x180026147  mov     r12, rcx
0x18002614a  mov     r14d, 80041001h
0x180026150  mov     rdx, [rdx]
0x180026153  xor     r13d, r13d
0x180026156  test    rdx, rdx
0x180026159  jz      loc_1800263F5
0x18002615f  lea     rcx, [rbp+57h+var_A0]
0x180026163  call    ??0?$CComQIPtr@UIDispatchEx@@$1?_GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>(IUnknown *)
0x180026168  nop
0x180026169  cmp     [rbp+57h+var_A0], r13
0x18002616d  jz      loc_1800263EC
0x180026173  mov     rdx, [rbx]
0x180026176  lea     rcx, [rbp+57h+var_80]
0x18002617a  call    ??0?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(IUnknown *)
0x18002617f  nop
0x180026180  cmp     [rbp+57h+var_80], r13
0x180026184  jnz     loc_1800263E2
0x18002618a  mov     edi, r13d
0x18002618d  or      r15d, 0FFFFFFFFh
0x180026191  mov     [rbp+57h+arg_8], r15d
0x180026195  mov     rcx, [rbp+57h+var_A0]
0x180026199  mov     rax, [rcx]
0x18002619c  lea     r9, [rbp+57h+arg_8]
0x1800261a0  mov     r8d, [rbp+57h+arg_8]
0x1800261a4  mov     edx, 2
0x1800261a9  mov     rax, [rax+68h]
0x1800261ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261b2  test    eax, eax
0x1800261b4  jnz     short loc_1800261FB
0x1800261b6  mov     [rbp+57h+String], r13
0x1800261ba  mov     [rbp+57h+EndPtr], r13
0x1800261be  mov     rcx, [rbp+57h+var_A0]
0x1800261c2  mov     rax, [rcx]
0x1800261c5  lea     r8, [rbp+57h+String]
0x1800261c9  mov     edx, [rbp+57h+arg_8]
0x1800261cc  mov     rax, [rax+60h]
0x1800261d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261d5  test    eax, eax
0x1800261d7  js      short loc_180026195
0x1800261d9  mov     r8d, 0Ah; Radix
0x1800261df  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800261e3  mov     rcx, [rbp+57h+String]; String
0x1800261e7  call    cs:__imp_wcstol
0x1800261ed  mov     rax, [rbp+57h+EndPtr]
0x1800261f1  cmp     r13w, [rax]
0x1800261f5  jnz     short loc_180026195
0x1800261f7  inc     edi
0x1800261f9  jmp     short loc_180026195
0x1800261fb  mov     eax, 0Ch
0x180026200  test    edi, edi
0x180026202  jz      short loc_18002620B
0x180026204  mov     ecx, esi; int
0x180026206  call    ?CimTypeToVtType@@YAGJ@Z; CimTypeToVtType(long)
0x18002620b  movzx   ebx, ax
0x18002620e  mov     [rbp+57h+rgsabound.cElements], edi
0x180026211  mov     [rbp+57h+rgsabound.lLbound], r13d
0x180026215  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180026219  mov     edx, 1; cDims
0x18002621e  movzx   ecx, ax; vt
0x180026221  call    cs:__imp_SafeArrayCreate
0x180026227  mov     rsi, rax
0x18002622a  test    rax, rax
0x18002622d  jz      loc_1800263DC
0x180026233  test    edi, edi
0x180026235  jle     loc_1800263C8
0x18002623b  mov     dil, 1
0x18002623e  mov     [rbp+57h+arg_8], r15d
0x180026242  xorps   xmm0, xmm0
0x180026245  movdqu  [rbp+57h+var_48], xmm0
0x18002624a  mov     [rbp+57h+var_38], r13
0x18002624e  mov     [rbp+57h+var_88], 0
0x180026256  mov     rcx, [rbp+57h+var_A0]
0x18002625a  mov     rax, [rcx]
0x18002625d  lea     r9, [rbp+57h+arg_8]
0x180026261  mov     r8d, r15d
0x180026264  mov     edx, 2
0x180026269  mov     rax, [rax+68h]
0x18002626d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026272  xor     r15d, r15d
0x180026275  test    eax, eax
0x180026277  js      loc_1800263C5
0x18002627d  cmp     eax, 1
0x180026280  jz      loc_1800263B2
0x180026286  mov     [rbp+57h+EndPtr], r15
0x18002628a  mov     rcx, [rbp+57h+var_A0]
0x18002628e  mov     rax, [rcx]
0x180026291  lea     r8, [rbp+57h+EndPtr]
0x180026295  mov     edx, [rbp+57h+arg_8]
0x180026298  mov     rax, [rax+60h]
0x18002629c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262a1  test    eax, eax
0x1800262a3  js      loc_180026397
0x1800262a9  lea     r8d, [r15+0Ah]; Radix
0x1800262ad  lea     rdx, [rbp+57h+var_88]; EndPtr
0x1800262b1  mov     rcx, [rbp+57h+EndPtr]; String
0x1800262b5  call    cs:__imp_wcstol
0x1800262bb  mov     edx, eax
0x1800262bd  mov     dword ptr [rbp+57h+String], eax
0x1800262c0  mov     rax, [rbp+57h+var_88]
0x1800262c4  cmp     r15w, [rax]
0x1800262c8  jnz     loc_18002639A
0x1800262ce  cmp     edx, r13d
0x1800262d1  jnz     loc_180026397
0x1800262d7  inc     r13d
0x1800262da  xorps   xmm0, xmm0
0x1800262dd  xor     eax, eax
0x1800262df  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800262e3  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800262e7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800262eb  call    cs:__imp_VariantInit
0x1800262f1  mov     rcx, [rbp+57h+var_A0]
0x1800262f5  mov     rax, [rcx]
0x1800262f8  lea     r9d, [r15+2]
0x1800262fc  mov     [rsp+0F0h+var_B8], r15
0x180026301  mov     [rsp+0F0h+var_C0], r15
0x180026306  lea     rdx, [rbp+57h+pvarg]
0x18002630a  mov     [rsp+0F0h+var_C8], rdx
0x18002630f  lea     rdx, [rbp+57h+var_48]
0x180026313  mov     [rsp+0F0h+var_D0], rdx
0x180026318  xor     r8d, r8d
0x18002631b  mov     edx, [rbp+57h+arg_8]
0x18002631e  mov     rax, [rax+40h]
0x180026322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026327  test    eax, eax
0x180026329  js      short loc_180026397
0x18002632b  xorps   xmm0, xmm0
0x18002632e  xor     eax, eax
0x180026330  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180026334  mov     qword ptr [rbp+57h+pv+10h], rax
0x180026338  lea     rcx, [rbp+57h+pv]; pvarg
0x18002633c  call    cs:__imp_VariantInit
0x180026342  mov     r8d, [rbp+57h+arg_10]; int
0x180026346  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x18002634a  lea     rcx, [rbp+57h+pv]; struct tagVARIANT *
0x18002634e  call    ?WmiVariantChangeType@@YAJAEAUtagVARIANT@@PEAU1@J@Z; WmiVariantChangeType(tagVARIANT &,tagVARIANT *,long)
0x180026353  mov     r14d, eax
0x180026356  test    eax, eax
0x180026358  js      short loc_18002638B
0x18002635a  lea     ecx, [rbx-8]
0x18002635d  mov     eax, 0FFFAh
0x180026362  test    ax, cx
0x180026365  jnz     short loc_180026374
0x180026367  lea     eax, [r15+0Ch]
0x18002636b  cmp     bx, ax
0x18002636e  mov     r8, qword ptr [rbp+57h+pv+8]
0x180026372  jnz     short loc_180026378
0x180026374  lea     r8, [rbp+57h+pv+8]; pv
0x180026378  lea     rdx, [rbp+57h+String]; rgIndices
0x18002637c  mov     rcx, rsi; psa
0x18002637f  call    cs:__imp_SafeArrayPutElement
0x180026385  test    eax, eax
0x180026387  setz    dil
0x18002638b  lea     rcx, [rbp+57h+pv]; pvarg
0x18002638f  call    cs:__imp_VariantClear
0x180026395  jmp     short loc_18002639A
0x180026397  mov     dil, r15b
0x18002639a  mov     rcx, [rbp+57h+EndPtr]; bstrString
0x18002639e  call    cs:__imp_SysFreeString
0x1800263a4  test    dil, dil
0x1800263a7  jz      short loc_1800263B2
0x1800263a9  mov     r15d, [rbp+57h+arg_8]
0x1800263ad  jmp     loc_180026256
0x1800263b2  xor     r13d, r13d
0x1800263b5  test    dil, dil
0x1800263b8  jnz     short loc_1800263C8
0x1800263ba  mov     rcx, rsi; psa
0x1800263bd  call    cs:__imp_SafeArrayDestroy
0x1800263c3  jmp     short loc_1800263E2
0x1800263c5  xor     r13d, r13d
0x1800263c8  or      bx, 2000h
0x1800263cd  mov     [r12], bx
0x1800263d2  mov     [r12+8], rsi
0x1800263d7  mov     r14d, r13d
0x1800263da  jmp     short loc_1800263E2
0x1800263dc  mov     r14d, 80041006h
0x1800263e2  lea     rcx, [rbp+57h+var_80]
0x1800263e6  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x1800263eb  nop
0x1800263ec  lea     rcx, [rbp+57h+var_A0]
0x1800263f0  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x1800263f5  mov     eax, r14d
0x1800263f8  mov     rbx, [rsp+0F0h+arg_0]
0x180026400  add     rsp, 0C0h
0x180026407  pop     r15
0x180026409  pop     r14
0x18002640b  pop     r13
0x18002640d  pop     r12
0x18002640f  pop     rdi
0x180026410  pop     rsi
0x180026411  pop     rbp
0x180026412  retn
```
