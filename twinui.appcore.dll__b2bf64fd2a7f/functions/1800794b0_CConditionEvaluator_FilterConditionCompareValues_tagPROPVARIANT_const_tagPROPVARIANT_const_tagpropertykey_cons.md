# CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)

- ea: `0x1800794b0`
- end: `0x1800796b1`
- name: `?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z`
- size: `513`
- prototype: `int __high(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct _tagpropertykey *, enum tagCONDITION_OPERATION, int, int, struct IPropertyInfoProvider *, int, struct IPropertyChangeArray *, enum BITSSET, unsigned __int16 *, unsigned int, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800791dc`
- `0x18007d590`

## callees

- `0x180078538`
- `0x1800794b0`
- `0x18007a178`
- `0x18007b898`
- `0x18007c728`
- `0x18007f61c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007954f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18007954f`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x180079662`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x180079662`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::FilterConditionCompareValues(
        CConditionEvaluator *a1,
        PROPVARIANT *a2,
        PROPVARIANT *a3,
        struct _tagpropertykey *a4,
        enum tagCONDITION_OPERATION a5,
        int a6,
        int a7,
        struct IPropertyInfoProvider *a8,
        unsigned int a9,
        __int64 a10,
        unsigned int a11,
        const WCHAR *pszStr1,
        LCID Locale,
        int *a14,
        _DWORD *a15)
{
  HRESULT v18; // ebx
  PKA_FLAGS v20; // edi
  void *ppv; // [rsp+60h] [rbp-48h] BYREF

  if ( a5 == COP_IMPLICIT )
    return 1;
  if ( (unsigned int)(a5 - 7) <= 6 )
    return (unsigned int)CConditionEvaluator::LikeOpCompareValues(a1, a2, a3, a5, a4, a6, a7, a8, a9, Locale, a14);
  if ( pszStr1 && !StrCmpICW(pszStr1, L"System.StructuredQueryType.SortKeyDescription") )
    return (unsigned int)SortKeyCompareValues(
                           (const struct tagPROPVARIANT *)a2,
                           (const struct tagPROPVARIANT *)a3,
                           a5,
                           a9,
                           a14);
  if ( a11 )
    return (unsigned int)BitwiseCompareValues(a2, a3, a11, a9, a14);
  v18 = _SimpleOpCompareValues(a2, a3, a5, a9, a14);
  if ( v18 >= 0 && !*a14 && a15 && a10 && (GetPropertyTypeFlags(a4, PDTF_ISINNATE) & 2) == 0 )
  {
    v20 = PKA_APPEND;
    if ( a9 )
    {
      if ( a5 != COP_NOTEQUAL )
        return (unsigned int)v18;
    }
    else if ( a5 != COP_EQUAL )
    {
      return (unsigned int)v18;
    }
    ppv = 0;
    if ( (GetPropertyTypeFlags(a4, PDTF_MULTIPLEVALUES) & 1) == 0 || !*(_WORD *)a2 )
      v20 = PKA_SET;
    v18 = PSCreateSimplePropertyChange(v20, a4, a2, &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431, &ppv);
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)a10 + 48LL))(a10, ppv);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    *a15 = v18 >= 0;
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800794b0  push    rbx
0x1800794b2  push    rbp
0x1800794b3  push    rsi
0x1800794b4  push    rdi
0x1800794b5  push    r12
0x1800794b7  push    r14
0x1800794b9  push    r15
0x1800794bb  sub     rsp, 70h
0x1800794bf  mov     esi, [rsp+0A8h+arg_20]
0x1800794c6  xor     r12d, r12d
0x1800794c9  mov     r15, r9
0x1800794cc  mov     rbx, r8
0x1800794cf  mov     rbp, rdx
0x1800794d2  test    esi, esi
0x1800794d4  jnz     short loc_1800794DE
0x1800794d6  lea     ebx, [rsi+1]
0x1800794d9  jmp     loc_1800796A0
0x1800794de  lea     eax, [rsi-7]
0x1800794e1  cmp     eax, 6
0x1800794e4  ja      short loc_18007953B
0x1800794e6  mov     rax, [rsp+0A8h+arg_68]
0x1800794ee  mov     r9d, esi; enum tagCONDITION_OPERATION
0x1800794f1  mov     [rsp+0A8h+var_58], rax; int *
0x1800794f6  mov     eax, [rsp+0A8h+arg_60]
0x1800794fd  mov     [rsp+0A8h+Locale], eax; Locale
0x180079501  mov     eax, [rsp+0A8h+arg_40]
0x180079508  mov     [rsp+0A8h+var_68], eax; int
0x18007950c  mov     rax, [rsp+0A8h+arg_38]
0x180079514  mov     [rsp+0A8h+var_70], rax; struct IPropertyInfoProvider *
0x180079519  mov     eax, [rsp+0A8h+arg_30]
0x180079520  mov     [rsp+0A8h+var_78], eax; int
0x180079524  mov     eax, [rsp+0A8h+arg_28]
0x18007952b  mov     [rsp+0A8h+var_80], eax; int
0x18007952f  mov     [rsp+0A8h+ppv], r15; propkey
0x180079534  call    ?LikeOpCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@AEBU_tagpropertykey@@HHPEAUIPropertyInfoProvider@@HKPEAH@Z; CConditionEvaluator::LikeOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,_tagpropertykey const &,int,int,IPropertyInfoProvider *,int,ulong,int *)
0x180079539  jmp     short loc_1800795AB
0x18007953b  mov     rcx, [rsp+0A8h+pszStr1]; pszStr1
0x180079543  test    rcx, rcx
0x180079546  jz      short loc_18007957E
0x180079548  lea     rdx, aSystemStructur_1; "System.StructuredQueryType.SortKeyDescr"...
0x18007954f  call    cs:__imp_StrCmpICW
0x180079555  test    eax, eax
0x180079557  jnz     short loc_18007957E
0x180079559  mov     rax, [rsp+0A8h+arg_68]
0x180079561  mov     r8d, esi; enum tagCONDITION_OPERATION
0x180079564  mov     r9d, [rsp+0A8h+arg_40]; int
0x18007956c  mov     rdx, rbx; struct tagPROPVARIANT *
0x18007956f  mov     rcx, rbp; struct tagPROPVARIANT *
0x180079572  mov     [rsp+0A8h+ppv], rax; int *
0x180079577  call    ?SortKeyCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; SortKeyCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x18007957c  jmp     short loc_1800795AB
0x18007957e  mov     r8d, [rsp+0A8h+arg_50]
0x180079586  mov     rdx, rbx; propvar1
0x180079589  mov     r9d, [rsp+0A8h+arg_40]; int
0x180079591  mov     rcx, rbp; propvar2
0x180079594  test    r8d, r8d
0x180079597  jz      short loc_1800795B2
0x180079599  mov     rax, [rsp+0A8h+arg_68]
0x1800795a1  mov     [rsp+0A8h+ppv], rax
0x1800795a6  call    ?BitwiseCompareValues@@YAJAEBUtagPROPVARIANT@@0W4BITSSET@@HPEAH@Z; BitwiseCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,BITSSET,int,int *)
0x1800795ab  mov     ebx, eax
0x1800795ad  jmp     loc_1800796A0
0x1800795b2  mov     rdi, [rsp+0A8h+arg_68]
0x1800795ba  mov     r8d, esi; enum tagCONDITION_OPERATION
0x1800795bd  mov     [rsp+0A8h+ppv], rdi; int *
0x1800795c2  call    ?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x1800795c7  mov     ebx, eax
0x1800795c9  test    eax, eax
0x1800795cb  js      loc_1800796A0
0x1800795d1  cmp     [rdi], r12d
0x1800795d4  jnz     loc_1800796A0
0x1800795da  mov     r14, [rsp+0A8h+arg_70]
0x1800795e2  test    r14, r14
0x1800795e5  jz      loc_1800796A0
0x1800795eb  mov     r12, [rsp+0A8h+arg_48]
0x1800795f3  test    r12, r12
0x1800795f6  jz      loc_1800796A0
0x1800795fc  mov     edx, 2; enum PROPDESC_TYPE_FLAGS
0x180079601  mov     rcx, r15; struct _tagpropertykey *
0x180079604  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x180079609  test    al, 2
0x18007960b  jnz     loc_1800796A0
0x180079611  cmp     [rsp+0A8h+arg_40], 0
0x180079619  mov     edi, 1
0x18007961e  jz      short loc_180079627
0x180079620  cmp     esi, 2
0x180079623  jz      short loc_18007962B
0x180079625  jmp     short loc_1800796A0
0x180079627  cmp     esi, edi
0x180079629  jnz     short loc_1800796A0
0x18007962b  xor     esi, esi
0x18007962d  mov     edx, edi; enum PROPDESC_TYPE_FLAGS
0x18007962f  mov     rcx, r15; struct _tagpropertykey *
0x180079632  mov     [rsp+0A8h+var_48], rsi
0x180079637  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x18007963c  test    dil, al
0x18007963f  jz      short loc_180079647
0x180079641  cmp     [rbp+0], si
0x180079645  jnz     short loc_180079649
0x180079647  mov     edi, esi
0x180079649  lea     rax, [rsp+0A8h+var_48]
0x18007964e  mov     r8, rbp; propvar
0x180079651  lea     r9, _GUID_f917bc8a_1bba_4478_a245_1bde03eb9431; riid
0x180079658  mov     [rsp+0A8h+ppv], rax; ppv
0x18007965d  mov     rdx, r15; key
0x180079660  mov     ecx, edi; flags
0x180079662  call    cs:__imp_PSCreateSimplePropertyChange
0x180079668  mov     ebx, eax
0x18007966a  test    eax, eax
0x18007966c  js      short loc_180079696
0x18007966e  mov     rax, [r12]
0x180079672  mov     rcx, r12
0x180079675  mov     rdx, [rsp+0A8h+var_48]
0x18007967a  mov     rax, [rax+30h]
0x18007967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079683  mov     rcx, [rsp+0A8h+var_48]
0x180079688  mov     ebx, eax
0x18007968a  mov     rax, [rcx]
0x18007968d  mov     rax, [rax+10h]
0x180079691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079696  mov     eax, ebx
0x180079698  not     eax
0x18007969a  shr     eax, 1Fh
0x18007969d  mov     [r14], eax
0x1800796a0  mov     eax, ebx
0x1800796a2  add     rsp, 70h
0x1800796a6  pop     r15
0x1800796a8  pop     r14
0x1800796aa  pop     r12
0x1800796ac  pop     rdi
0x1800796ad  pop     rsi
0x1800796ae  pop     rbp
0x1800796af  pop     rbx
0x1800796b0  retn
```
