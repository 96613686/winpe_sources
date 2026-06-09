# CSWbemNamedValue::put_Value(tagVARIANT *)

- ea: `0x1800229f0`
- end: `0x180022c55`
- name: `?put_Value@CSWbemNamedValue@@UEAAJPEAUtagVARIANT@@@Z`
- size: `613`
- prototype: `int(CSWbemNamedValue *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x18000c0b0`
- `0x180018038`
- `0x1800224e0`
- `0x1800229f0`
- `0x180025c74`
- `0x180033834`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022b08`
- `OLEAUT32!__imp_SysAllocString` at `0x180022bbb`
- `OLEAUT32!__imp_SysAllocString` at `0x180022b08`
- `OLEAUT32!__imp_SysAllocString` at `0x180022bbb`
- `OLEAUT32!__imp_SysFreeString` at `0x180022b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180022be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180022b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180022be0`
- `OLEAUT32!__imp_VariantInit` at `0x180022aa8`
- `OLEAUT32!__imp_VariantInit` at `0x180022aa8`
- `OLEAUT32!__imp_VariantClear` at `0x180022b60`
- `OLEAUT32!__imp_VariantClear` at `0x180022b60`
- `OLEAUT32!__imp_VariantChangeType` at `0x180022ae8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180022ae8`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180022ad6`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180022ad6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSWbemNamedValue::put_Value(CSWbemNamedValue *this, struct tagVARIANT *a2)
{
  int v4; // ebx
  struct IWbemContext *IWbemContext; // rax
  int v6; // edx
  __int64 v7; // rdi
  CWbemPathCracker *v8; // r15
  __int64 v9; // rax
  __int64 v10; // rcx
  HRESULT v11; // eax
  int v12; // edx
  enum WbemCimtypeEnum v13; // esi
  OLECHAR *v14; // rbx
  bool v15; // si
  enum WbemCimtypeEnum v16; // esi
  OLECHAR *v17; // rbx
  bool v18; // si
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF
  OLECHAR *v22; // [rsp+90h] [rbp+40h] BYREF

  ResetLastErrors();
  if ( !a2 )
  {
    v4 = -2147217400;
LABEL_29:
    CDispatchHelp::RaiseException((CSWbemNamedValue *)((char *)this + 40), v4);
    return (unsigned int)v4;
  }
  if ( !*((_BYTE *)this + 128) )
  {
    v4 = -2147217373;
    goto LABEL_29;
  }
  v4 = -2147217407;
  v21 = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(*((CSWbemNamedValueSet **)this + 4));
  ATL::CComPtr<IWbemContext>::Attach(&v21, IWbemContext);
  v7 = v21;
  if ( v21 )
  {
    v8 = 0;
    v9 = *((_QWORD *)this + 4);
    v10 = *(_QWORD *)(v9 + 136);
    if ( v10 )
    {
      v8 = *(CWbemPathCracker **)(v9 + 136);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    }
    if ( (a2->vt & 0x4000) != 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (a2->vt & 0x2000) != 0 )
      {
        pvarg.vt = a2->vt & 0xBFFF;
        v11 = SafeArrayCopy(*a2->pparray, &pvarg.parray);
      }
      else
      {
        v11 = VariantChangeType(&pvarg, a2, 0, a2->vt & 0xBFFF);
      }
      v4 = v11;
      if ( v11 >= 0 )
      {
        v13 = MapVariantTypeToCimType(&pvarg, v12);
        if ( v8
          && (v14 = SysAllocString(*((const OLECHAR **)this + 15)),
              v22 = v14,
              v15 = CWbemPathCracker::SetKey(v8, (const struct ATL::CComBSTR *)&v22, v13, &pvarg),
              SysFreeString(v14),
              v15) )
        {
          v4 = -2147217407;
        }
        else
        {
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, VARIANTARG *))(*(_QWORD *)v7 + 64LL))(
                 v7,
                 *((_QWORD *)this + 15),
                 0,
                 &pvarg);
        }
      }
      VariantClear(&pvarg);
LABEL_26:
      if ( !v8 )
        goto LABEL_28;
      goto LABEL_27;
    }
    if ( a2->vt == 10 && a2->lVal == -2147352572 )
    {
      a2->vt = 1;
      if ( !v8 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct tagVARIANT *))(*(_QWORD *)v7 + 64LL))(
               v7,
               *((_QWORD *)this + 15),
               0,
               a2);
        goto LABEL_28;
      }
    }
    else
    {
      v16 = MapVariantTypeToCimType(a2, v6);
      if ( !v8
        || (v17 = SysAllocString(*((const OLECHAR **)this + 15)),
            v22 = v17,
            v18 = CWbemPathCracker::SetKey(v8, (const struct ATL::CComBSTR *)&v22, v16, a2),
            SysFreeString(v17),
            !v18) )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct tagVARIANT *))(*(_QWORD *)v7 + 64LL))(
               v7,
               *((_QWORD *)this + 15),
               0,
               a2);
        goto LABEL_26;
      }
    }
    v4 = -2147217407;
LABEL_27:
    (*(void (__fastcall **)(CWbemPathCracker *))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_28:
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v21);
  if ( v4 < 0 )
    goto LABEL_29;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800229f0  mov     [rsp-28h+arg_0], rbx
0x1800229f5  mov     [rsp-28h+arg_18], rsi
0x1800229fa  push    rbp
0x1800229fb  push    rdi
0x1800229fc  push    r13
0x1800229fe  push    r14
0x180022a00  push    r15
0x180022a02  mov     rbp, rsp
0x180022a05  sub     rsp, 50h
0x180022a09  mov     r14, rdx
0x180022a0c  mov     r13, rcx
0x180022a0f  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180022a14  test    r14, r14
0x180022a17  jnz     short loc_180022A23
0x180022a19  mov     ebx, 80041008h
0x180022a1e  jmp     loc_180022C2F
0x180022a23  cmp     byte ptr [r13+80h], 0
0x180022a2b  jnz     short loc_180022A37
0x180022a2d  mov     ebx, 80041023h
0x180022a32  jmp     loc_180022C2F
0x180022a37  mov     ebx, 80041001h
0x180022a3c  mov     [rbp+arg_8], 0
0x180022a44  mov     rcx, [r13+20h]; this
0x180022a48  call    ?GetIWbemContext@CSWbemNamedValueSet@@QEAAPEAUIWbemContext@@XZ; CSWbemNamedValueSet::GetIWbemContext(void)
0x180022a4d  mov     rdx, rax
0x180022a50  lea     rcx, [rbp+arg_8]
0x180022a54  call    ?Attach@?$CComPtr@UIWbemContext@@@ATL@@QEAAXPEAUIWbemContext@@@Z; ATL::CComPtr<IWbemContext>::Attach(IWbemContext *)
0x180022a59  mov     rdi, [rbp+arg_8]
0x180022a5d  test    rdi, rdi
0x180022a60  jz      loc_180022C22
0x180022a66  xor     r15d, r15d
0x180022a69  mov     rax, [r13+20h]
0x180022a6d  mov     rcx, [rax+88h]
0x180022a74  test    rcx, rcx
0x180022a77  jz      short loc_180022A88
0x180022a79  mov     r15, rcx
0x180022a7c  mov     rax, [rcx]
0x180022a7f  mov     rax, [rax+8]
0x180022a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a88  mov     eax, 4000h
0x180022a8d  test    [r14], ax
0x180022a91  jz      loc_180022B6B
0x180022a97  xorps   xmm0, xmm0
0x180022a9a  xor     eax, eax
0x180022a9c  movups  xmmword ptr [rbp+pvarg], xmm0
0x180022aa0  mov     qword ptr [rbp+pvarg+10h], rax
0x180022aa4  lea     rcx, [rbp+pvarg]; pvarg
0x180022aa8  call    cs:__imp_VariantInit
0x180022aae  mov     eax, 0BFFFh
0x180022ab3  movzx   r9d, word ptr [r14]
0x180022ab7  and     r9w, ax; vt
0x180022abb  mov     eax, 2000h
0x180022ac0  test    [r14], ax
0x180022ac4  jz      short loc_180022ADE
0x180022ac6  mov     word ptr [rbp+pvarg], r9w
0x180022acb  mov     rcx, [r14+8]
0x180022acf  lea     rdx, [rbp+pvarg+8]; ppsaOut
0x180022ad3  mov     rcx, [rcx]; psa
0x180022ad6  call    cs:__imp_SafeArrayCopy
0x180022adc  jmp     short loc_180022AEE
0x180022ade  xor     r8d, r8d; wFlags
0x180022ae1  mov     rdx, r14; pvarSrc
0x180022ae4  lea     rcx, [rbp+pvarg]; pvargDest
0x180022ae8  call    cs:__imp_VariantChangeType
0x180022aee  mov     ebx, eax
0x180022af0  test    eax, eax
0x180022af2  js      short loc_180022B5C
0x180022af4  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x180022af8  call    ?MapVariantTypeToCimType@@YA?AW4WbemCimtypeEnum@@PEAUtagVARIANT@@J@Z; MapVariantTypeToCimType(tagVARIANT *,long)
0x180022afd  mov     esi, eax
0x180022aff  test    r15, r15
0x180022b02  jz      short loc_180022B40
0x180022b04  mov     rcx, [r13+78h]; psz
0x180022b08  call    cs:__imp_SysAllocString
0x180022b0e  mov     rbx, rax
0x180022b11  mov     [rbp+arg_10], rax
0x180022b15  lea     r9, [rbp+pvarg]; struct tagVARIANT *
0x180022b19  mov     r8d, esi; enum WbemCimtypeEnum
0x180022b1c  lea     rdx, [rbp+arg_10]; struct ATL::CComBSTR *
0x180022b20  mov     rcx, r15; this
0x180022b23  call    ?SetKey@CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@W4WbemCimtypeEnum@@AEAUtagVARIANT@@@Z; CWbemPathCracker::SetKey(ATL::CComBSTR const &,WbemCimtypeEnum,tagVARIANT &)
0x180022b28  mov     sil, al
0x180022b2b  mov     rcx, rbx; bstrString
0x180022b2e  call    cs:__imp_SysFreeString
0x180022b34  test    sil, sil
0x180022b37  jz      short loc_180022B40
0x180022b39  mov     ebx, 80041001h
0x180022b3e  jmp     short loc_180022B5C
0x180022b40  mov     rax, [rdi]
0x180022b43  lea     r9, [rbp+pvarg]
0x180022b47  xor     r8d, r8d
0x180022b4a  mov     rdx, [r13+78h]
0x180022b4e  mov     rcx, rdi
0x180022b51  mov     rax, [rax+40h]
0x180022b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b5a  mov     ebx, eax
0x180022b5c  lea     rcx, [rbp+pvarg]; pvarg
0x180022b60  call    cs:__imp_VariantClear
0x180022b66  jmp     loc_180022C0D
0x180022b6b  mov     eax, 0Ah
0x180022b70  cmp     ax, [r14]
0x180022b74  jnz     short loc_180022BA8
0x180022b76  cmp     dword ptr [r14+8], 80020004h
0x180022b7e  jnz     short loc_180022BA8
0x180022b80  mov     word ptr [r14], 1
0x180022b86  test    r15, r15
0x180022b89  jnz     short loc_180022BEB
0x180022b8b  mov     rax, [rdi]
0x180022b8e  mov     r9, r14
0x180022b91  xor     r8d, r8d
0x180022b94  mov     rdx, [r13+78h]
0x180022b98  mov     rcx, rdi
0x180022b9b  mov     rax, [rax+40h]
0x180022b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ba4  mov     ebx, eax
0x180022ba6  jmp     short loc_180022C22
0x180022ba8  mov     rcx, r14; struct tagVARIANT *
0x180022bab  call    ?MapVariantTypeToCimType@@YA?AW4WbemCimtypeEnum@@PEAUtagVARIANT@@J@Z; MapVariantTypeToCimType(tagVARIANT *,long)
0x180022bb0  mov     esi, eax
0x180022bb2  test    r15, r15
0x180022bb5  jz      short loc_180022BF2
0x180022bb7  mov     rcx, [r13+78h]; psz
0x180022bbb  call    cs:__imp_SysAllocString
0x180022bc1  mov     rbx, rax
0x180022bc4  mov     [rbp+arg_10], rax
0x180022bc8  mov     r9, r14; struct tagVARIANT *
0x180022bcb  mov     r8d, esi; enum WbemCimtypeEnum
0x180022bce  lea     rdx, [rbp+arg_10]; struct ATL::CComBSTR *
0x180022bd2  mov     rcx, r15; this
0x180022bd5  call    ?SetKey@CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@W4WbemCimtypeEnum@@AEAUtagVARIANT@@@Z; CWbemPathCracker::SetKey(ATL::CComBSTR const &,WbemCimtypeEnum,tagVARIANT &)
0x180022bda  mov     sil, al
0x180022bdd  mov     rcx, rbx; bstrString
0x180022be0  call    cs:__imp_SysFreeString
0x180022be6  test    sil, sil
0x180022be9  jz      short loc_180022BF2
0x180022beb  mov     ebx, 80041001h
0x180022bf0  jmp     short loc_180022C12
0x180022bf2  mov     rax, [rdi]
0x180022bf5  mov     r9, r14
0x180022bf8  xor     r8d, r8d
0x180022bfb  mov     rdx, [r13+78h]
0x180022bff  mov     rcx, rdi
0x180022c02  mov     rax, [rax+40h]
0x180022c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c0b  mov     ebx, eax
0x180022c0d  test    r15, r15
0x180022c10  jz      short loc_180022C22
0x180022c12  mov     rax, [r15]
0x180022c15  mov     rcx, r15
0x180022c18  mov     rax, [rax+10h]
0x180022c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c21  nop
0x180022c22  lea     rcx, [rbp+arg_8]
0x180022c26  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180022c2b  test    ebx, ebx
0x180022c2d  jns     short loc_180022C3A
0x180022c2f  lea     rcx, [r13+28h]; this
0x180022c33  mov     edx, ebx; int
0x180022c35  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180022c3a  mov     eax, ebx
0x180022c3c  lea     r11, [rsp+50h+var_s0]
0x180022c41  mov     rbx, [r11+30h]
0x180022c45  mov     rsi, [r11+48h]
0x180022c49  mov     rsp, r11
0x180022c4c  pop     r15
0x180022c4e  pop     r14
0x180022c50  pop     r13
0x180022c52  pop     rdi
0x180022c53  pop     rbp
0x180022c54  retn
```
