# CConditionEvaluator::_EvaluateProperty(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,int *,int *)

- ea: `0x18007f96c`
- end: `0x18007ff0c`
- name: `?_EvaluateProperty@CConditionEvaluator@@AEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAH4@Z`
- size: `1440`
- prototype: `__int64 __usercall@<rax>(CConditionEvaluator *__hidden this@<rcx>, PROPVARIANT *propvarIn@<rdx>, PROPVARIANT *@<r8>, const struct _tagpropertykey *@<r9>, tagCONDITION_OPERATION, struct ICondition *, int, int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007f530`

## callees

- `0x18007f96c`
- `0x18008d914`
- `0x1800f7b88`
- `0x1800fb2a8`
- `0x18028b2d4`
- `0x18028b334`
- `0x18028e9f8`
- `0x1802913a8`
- `0x180293e34`
- `0x1802958b4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fee6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fee6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007fc6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007febf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007fc6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007febf`
- `PROPSYS!PropVariantCompareEx` at `0x18007fc4d`
- `PROPSYS!PropVariantCompareEx` at `0x18007fc4d`
- `PROPSYS!PropVariantChangeType` at `0x18007fc10`
- `PROPSYS!PropVariantChangeType` at `0x18007fc2e`
- `PROPSYS!PropVariantChangeType` at `0x18007fc10`
- `PROPSYS!PropVariantChangeType` at `0x18007fc2e`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18007fd0f`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18007fd0f`
- `PROPSYS!PropVariantGetElementCount` at `0x18007fa79`
- `PROPSYS!PropVariantGetElementCount` at `0x18007fa79`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18007f9ed`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18007fa16`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18007f9ed`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18007fa16`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007fb43`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007fb43`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::_EvaluateProperty(
        CConditionEvaluator *this,
        PROPVARIANT *propvarIn,
        PROPVARIANT *a3,
        struct _tagpropertykey *a4,
        tagCONDITION_OPERATION a5,
        struct ICondition *a6,
        unsigned int a7,
        int *a8,
        int *a9)
{
  enum tagCONDITION_OPERATION v9; // r14d
  struct ICondition *v10; // rdi
  unsigned int v14; // r13d
  HRESULT v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // r8
  LCID InputLocale; // ebx
  struct IConditionVtbl *lpVtbl; // rax
  const struct _GUID *v20; // r8
  int v21; // eax
  int *v22; // r15
  VARTYPE v23; // r9
  unsigned int v24; // esi
  PKA_FLAGS v25; // edi
  const PROPVARIANT *v26; // rbx
  HRESULT v27; // eax
  PROPVARIANT *v28; // r8
  int v29; // eax
  int *v30; // r15
  void *v31; // r13
  tagCONDITION_OPERATION v32; // eax
  unsigned int v33; // esi
  int *v34; // rcx
  int v36; // [rsp+28h] [rbp-89h]
  int v37; // [rsp+30h] [rbp-81h]
  struct IPropertyInfoProvider *v38; // [rsp+38h] [rbp-79h]
  LCID Locale[2]; // [rsp+48h] [rbp-69h]
  int v40; // [rsp+80h] [rbp-31h] BYREF
  tagCONDITION_OPERATION v41; // [rsp+84h] [rbp-2Dh]
  LPCWSTR pszStr1; // [rsp+88h] [rbp-29h] BYREF
  void *ppv; // [rsp+90h] [rbp-21h] BYREF
  PROPVARIANT ppropvarDest[2]; // [rsp+98h] [rbp-19h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-9h]

  v9 = a5;
  v10 = a6;
  v14 = 0;
  if ( a5 != COP_APPLICATION_SPECIFIC )
  {
LABEL_12:
    a5 = COP_IMPLICIT;
    if ( (int)GetLocaleFromCondition(v10, &a5) >= 0 )
    {
      InputLocale = a5;
      v41 = a5;
    }
    else
    {
      InputLocale = CConditionEvaluator::_GetInputLocale(this);
      v41 = InputLocale;
    }
    lpVtbl = v10->lpVtbl;
    pszStr1 = 0;
    ((void (__fastcall *)(struct ICondition *, LPCWSTR *))lpVtbl->GetValueType)(v10, &pszStr1);
    if ( !PropVariantGetElementCount(a3) )
    {
      v45 = 0;
      *(_QWORD *)Locale = *((_QWORD *)this + 6);
      v38 = (struct IPropertyInfoProvider *)*((_QWORD *)this + 4);
      v37 = *((_DWORD *)this + 7);
      v36 = *((_DWORD *)this + 6);
      *(_OWORD *)ppropvarDest = 0;
      v21 = CConditionEvaluator::FilterConditionCompareValues(
              this,
              propvarIn,
              ppropvarDest,
              a4,
              v9,
              v36,
              v37,
              v38,
              a7,
              *(_QWORD *)Locale,
              v14,
              pszStr1,
              InputLocale,
              a8,
              a9);
LABEL_59:
      v15 = v21;
      goto LABEL_75;
    }
    if ( (*(_WORD *)a3 & 0x3000) == 0 )
    {
      if ( v9 == COP_IMPLICIT )
      {
        v15 = 1;
LABEL_75:
        CoTaskMemFree((LPVOID)pszStr1);
        return (unsigned int)v15;
      }
      if ( (unsigned int)(v9 - 7) <= 6 )
      {
        v21 = CConditionEvaluator::LikeOpCompareValues(
                this,
                propvarIn,
                a3,
                v9,
                a4,
                *((_DWORD *)this + 6),
                *((_DWORD *)this + 7),
                *((struct IPropertyInfoProvider **)this + 4),
                a7,
                InputLocale,
                a8);
        goto LABEL_59;
      }
      ppv = (void *)*((_QWORD *)this + 6);
      if ( pszStr1 && !StrCmpICW(pszStr1, L"System.StructuredQueryType.SortKeyDescription") )
      {
        v21 = SortKeyCompareValues(
                (const struct tagPROPVARIANT *)propvarIn,
                (const struct tagPROPVARIANT *)a3,
                v9,
                a7,
                a8);
        goto LABEL_59;
      }
      if ( v14 )
      {
        v21 = BitwiseCompareValues(propvarIn, a3, v14, a7, a8);
        goto LABEL_59;
      }
      v22 = a8;
      *a8 = 0;
      v23 = *(_WORD *)propvarIn;
      if ( *(_WORD *)propvarIn == *(_WORD *)a3 || v23 && *(_WORD *)a3 )
      {
        v26 = propvarIn;
        v45 = 0;
        *(_OWORD *)ppropvarDest = 0;
        v25 = PKA_APPEND;
        if ( v23 != *(_WORD *)a3 && v23 != 1 && *(_WORD *)a3 != 1 )
        {
          if ( PropVariantChangeType(ppropvarDest, a3, 0, v23) < 0 )
          {
            v27 = PropVariantChangeType(ppropvarDest, propvarIn, 0, *(_WORD *)a3);
            v28 = ppropvarDest;
            if ( v27 < 0 )
              v28 = propvarIn;
            v26 = v28;
          }
          else
          {
            a3 = ppropvarDest;
          }
        }
        v29 = PropVariantCompareEx(a3, v26, PVCU_DEFAULT, 0);
        v24 = a7;
        v15 = _SimpleOpCompareResult(v29, v9, a7, v22);
        PropVariantClear(ppropvarDest);
        if ( v15 < 0 )
          goto LABEL_75;
LABEL_44:
        if ( *v22 )
          goto LABEL_75;
LABEL_45:
        v30 = a9;
        if ( !a9 )
          goto LABEL_75;
        v31 = ppv;
        if ( !ppv || (GetPropertyTypeFlags(a4, PDTF_ISINNATE) & 2) != 0 )
          goto LABEL_75;
        if ( v24 )
        {
          if ( v9 != COP_NOTEQUAL )
            goto LABEL_75;
        }
        else if ( v9 != COP_EQUAL )
        {
          goto LABEL_75;
        }
        ppv = 0;
        if ( (GetPropertyTypeFlags(a4, PDTF_MULTIPLEVALUES) & 1) == 0 || !*(_WORD *)propvarIn )
          v25 = PKA_SET;
        v15 = PSCreateSimplePropertyChange(v25, a4, propvarIn, &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431, &ppv);
        if ( v15 >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)v31 + 48LL))(v31, ppv);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        *v30 = v15 >= 0;
        goto LABEL_75;
      }
      v24 = a7;
      v25 = PKA_APPEND;
      if ( a7 )
      {
        if ( v9 != COP_EQUAL )
        {
          v15 = 0;
          goto LABEL_45;
        }
      }
      else if ( v9 != COP_NOTEQUAL )
      {
LABEL_34:
        v15 = 0;
        goto LABEL_44;
      }
      *v22 = 1;
      goto LABEL_34;
    }
    ppv = 0;
    v15 = CMultipleValues_CreateInstance((const struct tagPROPVARIANT *)a3, a4, v20, &ppv);
    if ( v15 < 0 )
      goto LABEL_75;
    v40 = 0;
    v15 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppv + 96LL))(ppv, &v40);
    if ( v15 < 0 )
    {
LABEL_74:
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_75;
    }
    v32 = COP_IMPLICIT;
    v33 = 0;
    a5 = COP_IMPLICIT;
    while ( 1 )
    {
      if ( v32 || (int)v33 >= v40 )
        goto LABEL_74;
      v45 = 0;
      *(_OWORD *)ppropvarDest = 0;
      v15 = (*(__int64 (__fastcall **)(void *, _QWORD, PROPVARIANT *))(*(_QWORD *)ppv + 88LL))(ppv, v33, ppropvarDest);
      if ( v15 >= 0 )
        break;
LABEL_73:
      v32 = a5;
      ++v33;
      if ( v15 < 0 )
        goto LABEL_74;
    }
    v34 = a9;
    if ( v33 )
      v34 = 0;
    v15 = CConditionEvaluator::FilterConditionCompareValues(
            this,
            propvarIn,
            ppropvarDest,
            a4,
            v9,
            *((_DWORD *)this + 6),
            *((_DWORD *)this + 7),
            *((_QWORD *)this + 4),
            a7,
            *((_QWORD *)this + 6),
            v14,
            pszStr1,
            v41,
            a8,
            v34);
    if ( v15 < 0 )
    {
LABEL_72:
      PropVariantClear(ppropvarDest);
      goto LABEL_73;
    }
    if ( *a8 )
    {
      if ( a7 )
      {
LABEL_71:
        a5 = COP_IMPLICIT;
        goto LABEL_72;
      }
    }
    else if ( !a7 )
    {
      goto LABEL_71;
    }
    a5 = COP_EQUAL;
    goto LABEL_72;
  }
  pszStr1 = 0;
  v15 = ((__int64 (__fastcall *)(struct ICondition *, LPCWSTR *))a6->lpVtbl->GetValueType)(a6, &pszStr1);
  if ( v15 >= 0 )
  {
    if ( pszStr1 )
    {
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( pszStr1[v17] );
      if ( StrCmpNICW(pszStr1, L"System.StructuredQueryType.AnyBitsSet", v17) )
      {
        do
          ++v16;
        while ( pszStr1[v16] );
        if ( !StrCmpNICW(pszStr1, L"System.StructuredQueryType.AllBitsSet", v16) )
          v14 = 2;
      }
      else
      {
        v14 = 3;
      }
      CoTaskMemFree((LPVOID)pszStr1);
    }
    goto LABEL_12;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18007f96c  mov     [rsp-8+key], r9
0x18007f971  push    rbp
0x18007f972  push    rbx
0x18007f973  push    rsi
0x18007f974  push    rdi
0x18007f975  push    r12
0x18007f977  push    r13
0x18007f979  push    r14
0x18007f97b  push    r15
0x18007f97d  lea     rbp, [rsp-7]
0x18007f982  sub     rsp, 0B8h
0x18007f989  mov     r14d, [rbp+3Fh+arg_20]
0x18007f98d  xor     eax, eax
0x18007f98f  mov     rdi, [rbp+3Fh+arg_28]
0x18007f993  mov     rsi, r8
0x18007f996  mov     r12, rdx
0x18007f999  mov     r15, rcx
0x18007f99c  mov     r13d, eax
0x18007f99f  cmp     r14d, 0Eh
0x18007f9a3  jnz     loc_18007FA33
0x18007f9a9  mov     [rbp+3Fh+pszStr1], rax
0x18007f9ad  lea     rdx, [rbp+3Fh+pszStr1]
0x18007f9b1  mov     rax, [rdi]
0x18007f9b4  mov     rcx, rdi
0x18007f9b7  mov     rax, [rax+58h]
0x18007f9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f9c0  mov     ebx, eax
0x18007f9c2  xor     eax, eax
0x18007f9c4  test    ebx, ebx
0x18007f9c6  js      loc_18007FEEC
0x18007f9cc  mov     rcx, [rbp+3Fh+pszStr1]; pszStr1
0x18007f9d0  test    rcx, rcx
0x18007f9d3  jz      short loc_18007FA33
0x18007f9d5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007f9d9  mov     r8, rbx
0x18007f9dc  inc     r8; nChar
0x18007f9df  cmp     [rcx+r8*2], ax
0x18007f9e4  jnz     short loc_18007F9DC
0x18007f9e6  lea     rdx, aSystemStructur; "System.StructuredQueryType.AnyBitsSet"
0x18007f9ed  call    cs:__imp_StrCmpNICW
0x18007f9f3  xor     edx, edx
0x18007f9f5  test    eax, eax
0x18007f9f7  jnz     short loc_18007F9FF
0x18007f9f9  lea     r13d, [rdx+3]
0x18007f9fd  jmp     short loc_18007FA27
0x18007f9ff  mov     rcx, [rbp+3Fh+pszStr1]; pszStr1
0x18007fa03  inc     rbx
0x18007fa06  cmp     [rcx+rbx*2], dx
0x18007fa0a  jnz     short loc_18007FA03
0x18007fa0c  mov     r8d, ebx; nChar
0x18007fa0f  lea     rdx, aSystemStructur_0; "System.StructuredQueryType.AllBitsSet"
0x18007fa16  call    cs:__imp_StrCmpNICW
0x18007fa1c  test    eax, eax
0x18007fa1e  mov     eax, 2
0x18007fa23  cmovz   r13d, eax
0x18007fa27  mov     rcx, [rbp+3Fh+pszStr1]; pv
0x18007fa2b  call    cs:__imp_CoTaskMemFree
0x18007fa31  xor     eax, eax
0x18007fa33  lea     rdx, [rbp+3Fh+arg_20]
0x18007fa37  mov     [rbp+3Fh+arg_20], eax
0x18007fa3a  mov     rcx, rdi
0x18007fa3d  call    GetLocaleFromCondition
0x18007fa42  test    eax, eax
0x18007fa44  jns     short loc_18007FA55
0x18007fa46  mov     rcx, r15; this
0x18007fa49  call    ?_GetInputLocale@CConditionEvaluator@@IEAAKXZ; CConditionEvaluator::_GetInputLocale(void)
0x18007fa4e  mov     ebx, eax
0x18007fa50  mov     [rbp+3Fh+var_6C], eax
0x18007fa53  jmp     short loc_18007FA5B
0x18007fa55  mov     ebx, [rbp+3Fh+arg_20]
0x18007fa58  mov     [rbp+3Fh+var_6C], ebx
0x18007fa5b  mov     rax, [rdi]
0x18007fa5e  lea     rdx, [rbp+3Fh+pszStr1]
0x18007fa62  mov     rcx, rdi
0x18007fa65  mov     [rbp+3Fh+pszStr1], 0
0x18007fa6d  mov     rax, [rax+58h]
0x18007fa71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fa76  mov     rcx, rsi; propvar
0x18007fa79  call    cs:__imp_PropVariantGetElementCount
0x18007fa7f  xor     edi, edi
0x18007fa81  test    eax, eax
0x18007fa83  jnz     short loc_18007FB02
0x18007fa85  mov     r9, [rbp+3Fh+key]
0x18007fa89  lea     r8, [rbp+3Fh+ppropvarDest]
0x18007fa8d  xor     eax, eax
0x18007fa8f  xorps   xmm0, xmm0
0x18007fa92  mov     [rbp+3Fh+var_48], rax
0x18007fa96  mov     rdx, r12
0x18007fa99  mov     rax, [rbp+3Fh+arg_40]
0x18007faa0  mov     rcx, r15
0x18007faa3  mov     [rsp+0F0h+var_80], rax
0x18007faa8  mov     rax, [rbp+3Fh+arg_38]
0x18007faaf  mov     [rsp+0F0h+var_88], rax
0x18007fab4  mov     rax, [rbp+3Fh+pszStr1]
0x18007fab8  mov     [rsp+0F0h+var_90], ebx
0x18007fabc  mov     [rsp+0F0h+var_98], rax
0x18007fac1  mov     rax, [r15+30h]
0x18007fac5  mov     dword ptr [rsp+0F0h+var_A0], r13d
0x18007faca  mov     qword ptr [rsp+0F0h+Locale], rax
0x18007facf  mov     eax, [rbp+3Fh+arg_30]
0x18007fad2  mov     [rsp+0F0h+var_B0], eax
0x18007fad6  mov     rax, [r15+20h]
0x18007fada  mov     [rsp+0F0h+var_B8], rax
0x18007fadf  mov     eax, [r15+1Ch]
0x18007fae3  mov     [rsp+0F0h+var_C0], eax
0x18007fae7  mov     eax, [r15+18h]
0x18007faeb  mov     [rsp+0F0h+var_C8], eax
0x18007faef  mov     dword ptr [rsp+0F0h+ppv], r14d
0x18007faf4  movups  xmmword ptr [rbp+3Fh+ppropvarDest], xmm0
0x18007faf8  call    ?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z; CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)
0x18007fafd  jmp     loc_18007FD9A
0x18007fb02  mov     eax, 3000h
0x18007fb07  test    [rsi], ax
0x18007fb0a  jnz     loc_18007FDA1
0x18007fb10  test    r14d, r14d
0x18007fb13  jnz     short loc_18007FB1E
0x18007fb15  lea     ebx, [r14+1]
0x18007fb19  jmp     loc_18007FEE2
0x18007fb1e  lea     eax, [r14-7]
0x18007fb22  cmp     eax, 6
0x18007fb25  jbe     loc_18007FD50
0x18007fb2b  mov     rcx, [rbp+3Fh+pszStr1]; pszStr1
0x18007fb2f  mov     rax, [r15+30h]
0x18007fb33  mov     [rbp+3Fh+var_60], rax
0x18007fb37  test    rcx, rcx
0x18007fb3a  jz      short loc_18007FB70
0x18007fb3c  lea     rdx, aSystemStructur_1; "System.StructuredQueryType.SortKeyDescr"...
0x18007fb43  call    cs:__imp_StrCmpICW
0x18007fb49  test    eax, eax
0x18007fb4b  jnz     short loc_18007FB70
0x18007fb4d  mov     rax, [rbp+3Fh+arg_38]
0x18007fb54  mov     r8d, r14d; enum tagCONDITION_OPERATION
0x18007fb57  mov     r9d, [rbp+3Fh+arg_30]; int
0x18007fb5b  mov     rdx, rsi; struct tagPROPVARIANT *
0x18007fb5e  mov     rcx, r12; struct tagPROPVARIANT *
0x18007fb61  mov     [rsp+0F0h+ppv], rax; int *
0x18007fb66  call    ?SortKeyCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; SortKeyCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x18007fb6b  jmp     loc_18007FD9A
0x18007fb70  test    r13d, r13d
0x18007fb73  jz      short loc_18007FB98
0x18007fb75  mov     rax, [rbp+3Fh+arg_38]
0x18007fb7c  mov     r8d, r13d
0x18007fb7f  mov     r9d, [rbp+3Fh+arg_30]
0x18007fb83  mov     rdx, rsi
0x18007fb86  mov     rcx, r12
0x18007fb89  mov     [rsp+0F0h+ppv], rax
0x18007fb8e  call    ?BitwiseCompareValues@@YAJAEBUtagPROPVARIANT@@0W4BITSSET@@HPEAH@Z; BitwiseCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,BITSSET,int,int *)
0x18007fb93  jmp     loc_18007FD9A
0x18007fb98  mov     r15, [rbp+3Fh+arg_38]
0x18007fb9f  mov     [r15], edi
0x18007fba2  movzx   r9d, word ptr [r12]; vt
0x18007fba7  cmp     r9w, [rsi]
0x18007fbab  jz      short loc_18007FBE2
0x18007fbad  test    r9w, r9w
0x18007fbb1  jz      short loc_18007FBB8
0x18007fbb3  cmp     [rsi], di
0x18007fbb6  jnz     short loc_18007FBE2
0x18007fbb8  mov     esi, [rbp+3Fh+arg_30]
0x18007fbbb  xor     eax, eax
0x18007fbbd  mov     edi, 1
0x18007fbc2  test    esi, esi
0x18007fbc4  jz      short loc_18007FBD2
0x18007fbc6  cmp     r14d, edi
0x18007fbc9  jz      short loc_18007FBD8
0x18007fbcb  mov     ebx, eax
0x18007fbcd  jmp     loc_18007FC85
0x18007fbd2  cmp     r14d, 2
0x18007fbd6  jnz     short loc_18007FBDB
0x18007fbd8  mov     [r15], edi
0x18007fbdb  mov     ebx, eax
0x18007fbdd  jmp     loc_18007FC7C
0x18007fbe2  xor     eax, eax
0x18007fbe4  xorps   xmm0, xmm0
0x18007fbe7  mov     rbx, r12
0x18007fbea  mov     [rbp+3Fh+var_48], rax
0x18007fbee  movups  xmmword ptr [rbp+3Fh+ppropvarDest], xmm0
0x18007fbf2  lea     edi, [rax+1]
0x18007fbf5  cmp     r9w, [rsi]
0x18007fbf9  jz      short loc_18007FC41
0x18007fbfb  cmp     r9w, di
0x18007fbff  jz      short loc_18007FC41
0x18007fc01  cmp     [rsi], di
0x18007fc04  jz      short loc_18007FC41
0x18007fc06  xor     r8d, r8d; flags
0x18007fc09  lea     rcx, [rbp+3Fh+ppropvarDest]; ppropvarDest
0x18007fc0d  mov     rdx, rsi; propvarSrc
0x18007fc10  call    cs:__imp_PropVariantChangeType
0x18007fc16  test    eax, eax
0x18007fc18  js      short loc_18007FC20
0x18007fc1a  lea     rsi, [rbp+3Fh+ppropvarDest]
0x18007fc1e  jmp     short loc_18007FC41
0x18007fc20  movzx   r9d, word ptr [rsi]; vt
0x18007fc24  lea     rcx, [rbp+3Fh+ppropvarDest]; ppropvarDest
0x18007fc28  xor     r8d, r8d; flags
0x18007fc2b  mov     rdx, r12; propvarSrc
0x18007fc2e  call    cs:__imp_PropVariantChangeType
0x18007fc34  test    eax, eax
0x18007fc36  lea     r8, [rbp+3Fh+ppropvarDest]
0x18007fc3a  cmovs   r8, rbx
0x18007fc3e  mov     rbx, r8
0x18007fc41  xor     r9d, r9d; flags
0x18007fc44  xor     r8d, r8d; unit
0x18007fc47  mov     rdx, rbx; propvar2
0x18007fc4a  mov     rcx, rsi; propvar1
0x18007fc4d  call    cs:__imp_PropVariantCompareEx
0x18007fc53  mov     esi, [rbp+3Fh+arg_30]
0x18007fc56  mov     r9, r15; int *
0x18007fc59  mov     ecx, eax; int
0x18007fc5b  mov     r8d, esi; int
0x18007fc5e  mov     edx, r14d; enum tagCONDITION_OPERATION
0x18007fc61  call    ?_SimpleOpCompareResult@@YAJHW4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareResult(int,tagCONDITION_OPERATION,int,int *)
0x18007fc66  lea     rcx, [rbp+3Fh+ppropvarDest]; pvar
0x18007fc6a  mov     ebx, eax
0x18007fc6c  call    cs:__imp_PropVariantClear
0x18007fc72  xor     eax, eax
0x18007fc74  test    ebx, ebx
0x18007fc76  js      loc_18007FEE2
0x18007fc7c  cmp     [r15], eax
0x18007fc7f  jnz     loc_18007FEE2
0x18007fc85  mov     r15, [rbp+3Fh+arg_40]
0x18007fc8c  test    r15, r15
0x18007fc8f  jz      loc_18007FEE2
0x18007fc95  mov     r13, [rbp+3Fh+var_60]
0x18007fc99  test    r13, r13
0x18007fc9c  jz      loc_18007FEE2
0x18007fca2  mov     rcx, [rbp+3Fh+key]; struct _tagpropertykey *
0x18007fca6  mov     edx, 2; enum PROPDESC_TYPE_FLAGS
0x18007fcab  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x18007fcb0  mov     ecx, 2
0x18007fcb5  test    cl, al
0x18007fcb7  jnz     loc_18007FEE2
0x18007fcbd  test    esi, esi
0x18007fcbf  jz      short loc_18007FCCC
0x18007fcc1  cmp     r14d, ecx
0x18007fcc4  jnz     loc_18007FEE2
0x18007fcca  jmp     short loc_18007FCD5
0x18007fccc  cmp     r14d, edi
0x18007fccf  jnz     loc_18007FEE2
0x18007fcd5  mov     rbx, [rbp+3Fh+key]
0x18007fcd9  xor     esi, esi
0x18007fcdb  mov     rcx, rbx; struct _tagpropertykey *
0x18007fcde  mov     [rbp+3Fh+var_60], rsi
0x18007fce2  mov     edx, edi; enum PROPDESC_TYPE_FLAGS
0x18007fce4  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x18007fce9  test    dil, al
0x18007fcec  jz      short loc_18007FCF5
0x18007fcee  cmp     [r12], si
0x18007fcf3  jnz     short loc_18007FCF7
0x18007fcf5  mov     edi, esi
0x18007fcf7  lea     rax, [rbp+3Fh+var_60]
0x18007fcfb  mov     r8, r12; propvar
0x18007fcfe  lea     r9, _GUID_f917bc8a_1bba_4478_a245_1bde03eb9431; riid
0x18007fd05  mov     [rsp+0F0h+ppv], rax; ppv
0x18007fd0a  mov     rdx, rbx; key
0x18007fd0d  mov     ecx, edi; flags
0x18007fd0f  call    cs:__imp_PSCreateSimplePropertyChange
0x18007fd15  mov     ebx, eax
0x18007fd17  test    eax, eax
0x18007fd19  js      short loc_18007FD41
0x18007fd1b  mov     rax, [r13+0]
0x18007fd1f  mov     rcx, r13
0x18007fd22  mov     rdx, [rbp+3Fh+var_60]
0x18007fd26  mov     rax, [rax+30h]
0x18007fd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fd2f  mov     rcx, [rbp+3Fh+var_60]
0x18007fd33  mov     ebx, eax
0x18007fd35  mov     rax, [rcx]
0x18007fd38  mov     rax, [rax+10h]
0x18007fd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fd41  mov     eax, ebx
0x18007fd43  not     eax
0x18007fd45  shr     eax, 1Fh
0x18007fd48  mov     [r15], eax
0x18007fd4b  jmp     loc_18007FEE2
0x18007fd50  mov     rax, [rbp+3Fh+arg_38]
0x18007fd57  mov     r9d, r14d; enum tagCONDITION_OPERATION
0x18007fd5a  mov     [rsp+0F0h+var_A0], rax; int *
0x18007fd5f  mov     r8, rsi; PROPVARIANT *
0x18007fd62  mov     eax, [rbp+3Fh+arg_30]
0x18007fd65  mov     rdx, r12; propvarIn
0x18007fd68  mov     [rsp+0F0h+Locale], ebx; Locale
0x18007fd6c  mov     rcx, r15; this
0x18007fd6f  mov     [rsp+0F0h+var_B0], eax; int
0x18007fd73  mov     rax, [r15+20h]
0x18007fd77  mov     [rsp+0F0h+var_B8], rax; struct IPropertyInfoProvider *
0x18007fd7c  mov     eax, [r15+1Ch]
0x18007fd80  mov     [rsp+0F0h+var_C0], eax; int
0x18007fd84  mov     eax, [r15+18h]
0x18007fd88  mov     [rsp+0F0h+var_C8], eax; int
0x18007fd8c  mov     rax, [rbp+3Fh+key]
0x18007fd90  mov     [rsp+0F0h+ppv], rax; propkey
0x18007fd95  call    ?LikeOpCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@AEBU_tagpropertykey@@HHPEAUIPropertyInfoProvider@@HKPEAH@Z; CConditionEvaluator::LikeOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,_tagpropertykey const &,int,int,IPropertyInfoProvider *,int,ulong,int *)
0x18007fd9a  mov     ebx, eax
0x18007fd9c  jmp     loc_18007FEE2
0x18007fda1  mov     rdx, [rbp+3Fh+key]; struct _tagpropertykey *
0x18007fda5  lea     r9, [rbp+3Fh+var_60]; void **
0x18007fda9  mov     rcx, rsi; struct tagPROPVARIANT *
0x18007fdac  mov     [rbp+3Fh+var_60], rdi
0x18007fdb0  call    ?CMultipleValues_CreateInstance@@YAJPEBUtagPROPVARIANT@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z; CMultipleValues_CreateInstance(tagPROPVARIANT const *,_tagpropertykey const &,_GUID const &,void * *)
0x18007fdb5  mov     ebx, eax
  ... truncated ...
```
