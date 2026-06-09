# CQuerySpec::TryExtractBaseQuery(CSearchQueryBuilder &)

- ea: `0x180135430`
- end: `0x18013595a`
- name: `?TryExtractBaseQuery@CQuerySpec@@EEAAXAEAVCSearchQueryBuilder@@@Z`
- size: `1322`
- prototype: `void(CQuerySpec *__hidden this, struct CSearchQueryBuilder *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180038f08`
- `0x18008c694`
- `0x1800f3e64`
- `0x180109500`
- `0x18010eeb4`
- `0x18010fc70`
- `0x180135430`
- `0x180175ee8`
- `0x180175f9c`
- `0x180188d90`
- `0x180188dc0`
- `0x180189cce`
- `0x1801b20b8`
- `0x1801b2c24`
- `0x1801b2ce0`
- `0x1802c0010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801356b0`
- `OLEAUT32!__imp_VariantClear` at `0x1801356bd`
- `OLEAUT32!__imp_VariantClear` at `0x1801356b0`
- `OLEAUT32!__imp_VariantClear` at `0x1801356bd`
- `PROPSYS!InitVariantFromGUIDAsString` at `0x1801355d6`
- `PROPSYS!InitVariantFromGUIDAsString` at `0x18013561a`
- `PROPSYS!InitVariantFromGUIDAsString` at `0x18013564e`
- `PROPSYS!InitVariantFromGUIDAsString` at `0x1801355d6`
- `PROPSYS!InitVariantFromGUIDAsString` at `0x18013561a`
- `PROPSYS!InitVariantFromGUIDAsString` at `0x18013564e`

## string_xrefs

- `0x1801358b5`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`
- `0x1801358ca`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`
- `0x1801358df`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`
- `0x1801358f4`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`
- `0x180135909`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`
- `0x18013591e`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`
- `0x180135933`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`
- `0x180135948`: `onecoreuap\base\appmodel\search\tquery\icommand\stdqspec.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CQuerySpec::TryExtractBaseQuery(CQuerySpec *this, struct CSearchQueryBuilder *a2)
{
  void *v3; // rdi
  __int64 v4; // rbx
  wchar_t *Buffer; // rax
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // r8d
  HRESULT inited; // eax
  unsigned int v10; // r8d
  HRESULT v11; // eax
  HRESULT v12; // eax
  int v13; // edi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  struct IRowset *v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  struct ICondition *v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  struct ICondition *v26; // [rsp+80h] [rbp-80h] BYREF
  int v27[2]; // [rsp+88h] [rbp-78h] BYREF
  GUID guid; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+A0h] [rbp-60h]
  int v30; // [rsp+A4h] [rbp-5Ch]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  _DWORD *v32; // [rsp+B0h] [rbp-50h] BYREF
  int v33; // [rsp+B8h] [rbp-48h]
  int v34; // [rsp+BCh] [rbp-44h]
  int v35; // [rsp+C0h] [rbp-40h]
  int v36; // [rsp+C4h] [rbp-3Ch]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  _DWORD v38[12]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v39; // [rsp+100h] [rbp+0h]
  __int16 v40; // [rsp+108h] [rbp+8h]
  _DWORD v41[12]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v42; // [rsp+150h] [rbp+50h]
  __int16 v43; // [rsp+158h] [rbp+58h]
  int v44; // [rsp+168h] [rbp+68h]
  int v45; // [rsp+16Ch] [rbp+6Ch]
  VARIANT pvar; // [rsp+198h] [rbp+98h] BYREF
  int v47; // [rsp+1B0h] [rbp+B0h]
  int v48; // [rsp+1B4h] [rbp+B4h]
  VARIANT pvarg; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v22 = 0;
  v26 = 0;
  if ( CSearchQueryBuilder::IsSplittableCondition(a2, *((struct ICondition **)this + 347), &v22, &v26) )
  {
    v23 = 0;
    v3 = operator new(0xBD0u);
    *(_QWORD *)&guid.Data1 = v3;
    v4 = *((_QWORD *)this + 345);
    Buffer = CLMString::GetBuffer((CQuerySpec *)((char *)this + 2928), 0);
    v17 = v4;
    CQuerySpec::CQuerySpec(v3, 0, &v23, Buffer);
    v19 = 0;
    v6 = v23;
    TComPointer<ICommandProperties>::InitializeByCertainQI(&v19, v23);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) )
    {
      memset_0(v41, 0, 0xD8u);
      v41[0] = 15;
      v41[1] = 1;
      v42 = 11;
      v43 = -1;
      v44 = 18;
      v45 = 1;
      CUtlProps::GetValGuid((CQuerySpec *)((char *)this + 416), &guid, v8, 0xDu);
      inited = InitVariantFromGUIDAsString(&guid, &pvar);
      if ( inited < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F7,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
          (const char *)(unsigned int)inited,
          v17);
      v47 = 17;
      v48 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60916561>::GetImpl'::`2'::impl) )
      {
        v11 = InitVariantFromGUIDAsString(&FE_SCOPE_QUERY, &pvarg);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2FF,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
            (const char *)(unsigned int)v11,
            v17);
      }
      else
      {
        CUtlProps::GetValGuid((CQuerySpec *)((char *)this + 416), &guid, v10, 0xCu);
        v12 = InitVariantFromGUIDAsString(&guid, &pvarg);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x303,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
            (const char *)(unsigned int)v12,
            v17);
      }
      v37 = 629145848;
      v33 = 3;
      v34 = -1481869331;
      v35 = 298776791;
      v36 = 536909991;
      v32 = v41;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD **))(*(_QWORD *)v19 + 32LL))(v19, 1, &v32);
      VariantClear(&pvar);
      VariantClear(&pvarg);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x30E,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
          (const char *)(unsigned int)v13,
          v17);
    }
    else
    {
      memset_0(v38, 0, 0x48u);
      v38[0] = 15;
      v38[1] = 1;
      v39 = 11;
      v40 = -1;
      v31 = 629145848;
      *(_DWORD *)guid.Data4 = 1;
      *(_DWORD *)&guid.Data4[4] = -1481869331;
      v29 = 298776791;
      v30 = 536909991;
      *(_QWORD *)&guid.Data1 = v38;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *))(*(_QWORD *)v19 + 32LL))(v19, 1, &guid);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x31D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
          (const char *)(unsigned int)v7,
          v17);
    }
    v18 = 0;
    TComPointer<ICommandSearch>::InitializeByCertainQI(&v18, v6);
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 48LL))(v18, *((_QWORD *)this + 346));
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x325,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
        (const char *)(unsigned int)v14,
        v17);
    v25 = 0;
    v24 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, struct ICondition *, GUID *, __int64 *))(*(_QWORD *)v18 + 56LL))(
            v18,
            v22,
            &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
            &v25);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
        (const char *)(unsigned int)v15,
        (int)&GUID_0fc988d4_c935_4b97_a973_46282ea175c8);
    v21 = 0;
    *(_QWORD *)v27 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD))(*(_QWORD *)v18 + 32LL))(v18, 0, &IID_IRowset, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x331,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\stdqspec.cxx",
        (const char *)(unsigned int)v16,
        (int)v27);
    v20 = 0;
    TComPointer<IRowset>::InitializeByCertainQI(&v20, v21);
    CRootQuerySpec::SetReuseContext((CQuerySpec *)((char *)this + 48), v20);
    if ( v20 )
      ((void (__fastcall *)(struct IRowset *))v20->lpVtbl->Release)(v20);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v26 )
    ((void (__fastcall *)(struct ICondition *))v26->lpVtbl->Release)(v26);
  if ( v22 )
    ((void (__fastcall *)(struct ICondition *))v22->lpVtbl->Release)(v22);
}

```

## disassembly

```asm
0x180135430  mov     [rsp-8+arg_10], rbx
0x180135435  push    rbp
0x180135436  push    rsi
0x180135437  push    rdi
0x180135438  push    r14
0x18013543a  push    r15
0x18013543c  lea     rbp, [rsp-110h]
0x180135444  sub     rsp, 210h
0x18013544b  mov     rax, cs:__security_cookie
0x180135452  xor     rax, rsp
0x180135455  mov     [rbp+130h+var_30], rax
0x18013545c  mov     rax, rdx
0x18013545f  mov     rsi, rcx
0x180135462  xor     r14d, r14d
0x180135465  mov     [rsp+230h+var_1D0], r14
0x18013546a  mov     [rbp+130h+var_1B0], r14
0x18013546e  lea     r9, [rbp+130h+var_1B0]; struct ICondition **
0x180135472  lea     r8, [rsp+230h+var_1D0]; struct ICondition **
0x180135477  mov     rdx, [rcx+0AD8h]; struct ICondition *
0x18013547e  mov     rcx, rax; this
0x180135481  call    ?IsSplittableCondition@CSearchQueryBuilder@@QEAA_NPEAUICondition@@PEAPEAU2@1@Z; CSearchQueryBuilder::IsSplittableCondition(ICondition *,ICondition * *,ICondition * *)
0x180135486  test    al, al
0x180135488  jz      loc_18013585F
0x18013548e  mov     [rsp+230h+var_1C8], r14
0x180135493  mov     ecx, 0BD0h; Size
0x180135498  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18013549d  mov     rdi, rax
0x1801354a0  mov     qword ptr [rbp+130h+guid.Data1], rax
0x1801354a4  mov     rbx, [rsi+0AC8h]
0x1801354ab  lea     rcx, [rsi+0B70h]; this
0x1801354b2  xor     edx, edx; int
0x1801354b4  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1801354b9  lea     r15d, [r14+1]
0x1801354bd  mov     dword ptr [rsp+230h+var_208], r15d
0x1801354c2  mov     qword ptr [rsp+230h+var_210], rbx; int
0x1801354c7  mov     r9, rax
0x1801354ca  lea     r8, [rsp+230h+var_1C8]
0x1801354cf  xor     edx, edx
0x1801354d1  mov     rcx, rdi
0x1801354d4  call    ??0CQuerySpec@@QEAA@PEAUIUnknown@@PEAPEAU1@PEA_W0W4REUSEWHERE_MODE@@@Z; CQuerySpec::CQuerySpec(IUnknown *,IUnknown * *,wchar_t *,IUnknown *,REUSEWHERE_MODE)
0x1801354d9  nop
0x1801354da  mov     [rsp+230h+var_1E8], r14
0x1801354df  mov     rbx, [rsp+230h+var_1C8]
0x1801354e4  mov     rdx, rbx
0x1801354e7  lea     rcx, [rsp+230h+var_1E8]
0x1801354ec  call    ?InitializeByCertainQI@?$TComPointer@UICommandProperties@@@@QEAAXPEAUIUnknown@@@Z; TComPointer<ICommandProperties>::InitializeByCertainQI(IUnknown *)
0x1801354f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57994465@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465> `wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl(void)'::`2'::impl
0x1801354f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(void)
0x1801354fd  xor     edx, edx; Val
0x1801354ff  test    al, al
0x180135501  jnz     short loc_18013557F
0x180135503  lea     r8d, [r14+48h]; Size
0x180135507  lea     rcx, [rbp+130h+var_160]; void *
0x18013550b  call    memset_0
0x180135510  mov     [rbp+130h+var_160], 0Fh
0x180135517  mov     [rbp+130h+var_15C], r15d
0x18013551b  lea     eax, [r14+0Bh]
0x18013551f  mov     [rbp+130h+var_130], ax
0x180135523  or      eax, 0FFFFFFFFh
0x180135526  mov     [rbp+130h+var_128], ax
0x18013552a  mov     [rbp+130h+var_188], 258000F8h
0x180135532  mov     dword ptr [rbp+130h+guid.Data4], r15d
0x180135536  mov     dword ptr [rbp+130h+guid.Data4+4], 0A7AC77EDh
0x18013553d  mov     [rbp+130h+var_190], 11CEF8D7h
0x180135544  mov     [rbp+130h+var_18C], 200098A7h
0x18013554b  lea     rax, [rbp+130h+var_160]
0x18013554f  mov     qword ptr [rbp+130h+guid.Data1], rax
0x180135553  mov     rcx, [rsp+230h+var_1E8]
0x180135558  mov     rax, [rcx]
0x18013555b  lea     r8, [rbp+130h+guid]
0x18013555f  mov     edx, r15d
0x180135562  mov     rax, [rax+20h]
0x180135566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013556b  mov     rcx, [rbp+138h]; this
0x180135572  test    eax, eax
0x180135574  js      loc_1801358C7
0x18013557a  jmp     loc_1801356D2
0x18013557f  mov     r8d, 0D8h; Size
0x180135585  lea     rcx, [rbp+130h+var_110]; void *
0x180135589  call    memset_0
0x18013558e  mov     [rbp+130h+var_110], 0Fh
0x180135595  mov     [rbp+130h+var_10C], r15d
0x180135599  mov     eax, 0Bh
0x18013559e  mov     [rbp+130h+var_E0], ax
0x1801355a2  or      eax, 0FFFFFFFFh
0x1801355a5  mov     [rbp+130h+var_D8], ax
0x1801355a9  mov     [rbp+130h+var_C8], 12h
0x1801355b0  mov     [rbp+130h+var_C4], r15d
0x1801355b4  lea     rdi, [rsi+1A0h]
0x1801355bb  lea     r9d, [rax+0Eh]; unsigned int
0x1801355bf  lea     rdx, [rbp+130h+guid]; retstr
0x1801355c3  mov     rcx, rdi; this
0x1801355c6  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x1801355cb  lea     rdx, [rbp+130h+pvar]; pvar
0x1801355d2  lea     rcx, [rbp+130h+guid]; guid
0x1801355d6  call    cs:__imp_InitVariantFromGUIDAsString
0x1801355dc  mov     rcx, [rbp+138h]; this
0x1801355e3  test    eax, eax
0x1801355e5  js      loc_1801358F1
0x1801355eb  mov     [rbp+130h+var_80], 11h
0x1801355f5  mov     [rbp+130h+var_7C], r15d
0x1801355fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60916561@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60916561@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561> `wil::Feature<__WilFeatureTraits_Feature_60916561>::GetImpl(void)'::`2'::impl
0x180135603  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60916561@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60916561>::__private_IsEnabled(void)
0x180135608  test    al, al
0x18013560a  jz      short loc_180135631
0x18013560c  lea     rdx, [rbp+130h+pvarg]; pvar
0x180135613  lea     rcx, ?FE_SCOPE_QUERY@@3U_GUID@@B; guid
0x18013561a  call    cs:__imp_InitVariantFromGUIDAsString
0x180135620  mov     rcx, [rbp+138h]; this
0x180135627  test    eax, eax
0x180135629  js      loc_1801358DC
0x18013562f  jmp     short loc_180135663
0x180135631  mov     r9d, 0Ch; unsigned int
0x180135637  lea     rdx, [rbp+130h+guid]; retstr
0x18013563b  mov     rcx, rdi; this
0x18013563e  call    ?GetValGuid@CUtlProps@@QEAA?BU_GUID@@KK@Z; CUtlProps::GetValGuid(ulong,ulong)
0x180135643  lea     rdx, [rbp+130h+pvarg]; pvar
0x18013564a  lea     rcx, [rbp+130h+guid]; guid
0x18013564e  call    cs:__imp_InitVariantFromGUIDAsString
0x180135654  mov     rcx, [rbp+138h]; this
0x18013565b  test    eax, eax
0x18013565d  js      loc_180135906
0x180135663  mov     [rbp+130h+var_168], 258000F8h
0x18013566b  mov     [rbp+130h+var_178], 3
0x180135672  mov     [rbp+130h+var_174], 0A7AC77EDh
0x180135679  mov     [rbp+130h+var_170], 11CEF8D7h
0x180135680  mov     [rbp+130h+var_16C], 200098A7h
0x180135687  lea     rax, [rbp+130h+var_110]
0x18013568b  mov     [rbp+130h+var_180], rax
0x18013568f  mov     rcx, [rsp+230h+var_1E8]
0x180135694  mov     rax, [rcx]
0x180135697  lea     r8, [rbp+130h+var_180]
0x18013569b  mov     edx, r15d
0x18013569e  mov     rax, [rax+20h]
0x1801356a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801356a7  mov     edi, eax
0x1801356a9  lea     rcx, [rbp+130h+pvar]; pvarg
0x1801356b0  call    cs:__imp_VariantClear
0x1801356b6  lea     rcx, [rbp+130h+pvarg]; pvarg
0x1801356bd  call    cs:__imp_VariantClear
0x1801356c3  mov     rcx, [rbp+138h]; this
0x1801356ca  test    edi, edi
0x1801356cc  js      loc_18013591B
0x1801356d2  mov     [rsp+230h+var_1F0], r14
0x1801356d7  mov     rdx, rbx
0x1801356da  lea     rcx, [rsp+230h+var_1F0]
0x1801356df  call    ?InitializeByCertainQI@?$TComPointer@UICommandSearch@@@@QEAAXPEAUIUnknown@@@Z; TComPointer<ICommandSearch>::InitializeByCertainQI(IUnknown *)
0x1801356e4  mov     rcx, [rsp+230h+var_1F0]
0x1801356e9  mov     rax, [rcx]
0x1801356ec  mov     rdx, [rsi+0AD0h]
0x1801356f3  mov     rax, [rax+30h]
0x1801356f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801356fc  mov     rcx, [rbp+138h]; this
0x180135703  test    eax, eax
0x180135705  js      loc_180135930
0x18013570b  mov     [rsp+230h+var_1B8], r14
0x180135710  mov     [rsp+230h+var_1C0], r14
0x180135715  mov     rcx, [rsp+230h+var_1F0]
0x18013571a  mov     rax, [rcx]
0x18013571d  lea     rdx, [rsp+230h+var_1C0]
0x180135722  mov     [rsp+230h+var_208], rdx
0x180135727  lea     r8, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18013572e  mov     qword ptr [rsp+230h+var_210], r8; int
0x180135733  lea     r9, [rsp+230h+var_1B8]
0x180135738  mov     rdx, [rsp+230h+var_1D0]
0x18013573d  mov     rax, [rax+38h]
0x180135741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135746  mov     rcx, [rbp+138h]; this
0x18013574d  test    eax, eax
0x18013574f  js      loc_180135945
0x180135755  mov     [rsp+230h+var_1D8], r14
0x18013575a  mov     qword ptr [rbp+130h+var_1A8], r14
0x18013575e  mov     rcx, [rsp+230h+var_1F0]
0x180135763  mov     rax, [rcx]
0x180135766  lea     rdx, [rsp+230h+var_1D8]
0x18013576b  mov     [rsp+230h+var_208], rdx
0x180135770  lea     rdx, [rbp+130h+var_1A8]
0x180135774  mov     qword ptr [rsp+230h+var_210], rdx; int
0x180135779  xor     r9d, r9d
0x18013577c  lea     r8, IID_IRowset
0x180135783  xor     edx, edx
0x180135785  mov     rax, [rax+20h]
0x180135789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013578e  mov     rcx, [rbp+138h]; this
0x180135795  test    eax, eax
0x180135797  js      loc_1801358B2
0x18013579d  mov     [rsp+230h+var_1E0], r14
0x1801357a2  mov     rdx, [rsp+230h+var_1D8]
0x1801357a7  lea     rcx, [rsp+230h+var_1E0]
0x1801357ac  call    ?InitializeByCertainQI@?$TComPointer@UIRowset@@@@QEAAXPEAUIUnknown@@@Z; TComPointer<IRowset>::InitializeByCertainQI(IUnknown *)
0x1801357b1  lea     rcx, [rsi+30h]; this
0x1801357b5  mov     rdx, [rsp+230h+var_1E0]; struct IRowset *
0x1801357ba  call    ?SetReuseContext@CRootQuerySpec@@UEAAJPEAUIRowset@@@Z; CRootQuerySpec::SetReuseContext(IRowset *)
0x1801357bf  nop
0x1801357c0  mov     rcx, [rsp+230h+var_1E0]
0x1801357c5  test    rcx, rcx
0x1801357c8  jz      short loc_1801357D7
0x1801357ca  mov     rax, [rcx]
0x1801357cd  mov     rax, [rax+10h]
0x1801357d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801357d6  nop
0x1801357d7  mov     rcx, [rsp+230h+var_1D8]
0x1801357dc  test    rcx, rcx
0x1801357df  jz      short loc_1801357EE
0x1801357e1  mov     rax, [rcx]
0x1801357e4  mov     rax, [rax+10h]
0x1801357e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801357ed  nop
0x1801357ee  mov     rcx, [rsp+230h+var_1C0]
0x1801357f3  test    rcx, rcx
0x1801357f6  jz      short loc_180135805
0x1801357f8  mov     rax, [rcx]
0x1801357fb  mov     rax, [rax+10h]
0x1801357ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135804  nop
0x180135805  mov     rcx, [rsp+230h+var_1B8]
0x18013580a  test    rcx, rcx
0x18013580d  jz      short loc_18013581C
0x18013580f  mov     rax, [rcx]
0x180135812  mov     rax, [rax+10h]
0x180135816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013581b  nop
0x18013581c  mov     rcx, [rsp+230h+var_1F0]
0x180135821  test    rcx, rcx
0x180135824  jz      short loc_180135833
0x180135826  mov     rax, [rcx]
0x180135829  mov     rax, [rax+10h]
0x18013582d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135832  nop
0x180135833  mov     rcx, [rsp+230h+var_1E8]
0x180135838  test    rcx, rcx
0x18013583b  jz      short loc_18013584A
0x18013583d  mov     rax, [rcx]
0x180135840  mov     rax, [rax+10h]
0x180135844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135849  nop
0x18013584a  test    rbx, rbx
0x18013584d  jz      short loc_18013585F
0x18013584f  mov     rax, [rbx]
0x180135852  mov     rcx, rbx
0x180135855  mov     rax, [rax+10h]
0x180135859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013585e  nop
0x18013585f  mov     rcx, [rbp+130h+var_1B0]
0x180135863  test    rcx, rcx
0x180135866  jz      short loc_180135875
0x180135868  mov     rax, [rcx]
0x18013586b  mov     rax, [rax+10h]
0x18013586f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135874  nop
0x180135875  mov     rcx, [rsp+230h+var_1D0]
0x18013587a  test    rcx, rcx
0x18013587d  jz      short loc_18013588C
0x18013587f  mov     rax, [rcx]
0x180135882  mov     rax, [rax+10h]
0x180135886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013588b  nop
0x18013588c  mov     rcx, [rbp+130h+var_30]
0x180135893  xor     rcx, rsp; StackCookie
0x180135896  call    __security_check_cookie
0x18013589b  mov     rbx, [rsp+230h+arg_10]
0x1801358a3  add     rsp, 210h
0x1801358aa  pop     r15
0x1801358ac  pop     r14
0x1801358ae  pop     rdi
0x1801358af  pop     rsi
0x1801358b0  pop     rbp
0x1801358b1  retn
0x1801358b2  mov     r9d, eax; char *
0x1801358b5  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801358bc  mov     edx, 331h; void *
0x1801358c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801358c7  mov     r9d, eax; char *
0x1801358ca  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801358d1  mov     edx, 31Dh; void *
0x1801358d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801358dc  mov     r9d, eax; char *
0x1801358df  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801358e6  mov     edx, 2FFh; void *
0x1801358eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801358f1  mov     r9d, eax; char *
0x1801358f4  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801358fb  mov     edx, 2F7h; void *
0x180135900  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180135906  mov     r9d, eax; char *
0x180135909  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180135910  mov     edx, 303h; void *
0x180135915  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013591b  mov     r9d, edi; char *
0x18013591e  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180135925  mov     edx, 30Eh; void *
0x18013592a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180135930  mov     r9d, eax; char *
0x180135933  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18013593a  mov     edx, 325h; void *
0x18013593f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180135945  mov     r9d, eax; char *
0x180135948  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18013594f  mov     edx, 32Bh; void *
0x180135954  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
