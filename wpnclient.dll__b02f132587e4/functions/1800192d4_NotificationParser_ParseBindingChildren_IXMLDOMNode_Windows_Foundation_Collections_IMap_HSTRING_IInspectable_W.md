# NotificationParser::ParseBindingChildren(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,WPN_APP_TYPE,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST)

- ea: `0x1800192d4`
- end: `0x1800199d5`
- name: `?ParseBindingChildren@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@W4WPN_APP_TYPE@@PEBG3W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@@Z`
- size: `1793`
- prototype: `__int64 __fastcall(int, int, int, int, PCWSTR packageFullName, int, int, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018d90`

## callees

- `0x180005670`
- `0x180008910`
- `0x180009890`
- `0x18000a460`
- `0x18000cb68`
- `0x18000dc30`
- `0x1800192d4`
- `0x1800199dc`
- `0x180019b4c`
- `0x18001b848`
- `0x18001be84`
- `0x18001bf44`
- `0x18001d4cc`
- `0x18001ff00`
- `0x180020d34`
- `0x180025aa0`
- `0x18002c1e4`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180019874`
- `OLEAUT32!__imp_SysFreeString` at `0x180019874`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180019777`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180019777`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NotificationParser::ParseBindingChildren(
        NotificationParser *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int16 *packageFullName,
        int a6,
        int a7,
        int a8)
{
  unsigned int v10; // r14d
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // esi
  unsigned int i; // r15d
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, struct IXMLDOMNode **); // rbx
  int v18; // eax
  int v19; // eax
  wchar_t *v20; // rbx
  int v21; // eax
  const unsigned __int16 *v22; // r9
  __int64 (__fastcall *v23)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v24; // rbx
  int v25; // eax
  __int64 *v26; // rcx
  int v27; // eax
  __int64 v28; // r9
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64, char *); // rdi
  __int64 v30; // rbx
  int v31; // eax
  int v32; // eax
  __int64 v33; // r9
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64, char *); // rdi
  __int64 v35; // rbx
  int v36; // eax
  int v37; // eax
  const unsigned __int16 *v38; // r9
  __int64 (__fastcall *v39)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v40; // rbx
  int v41; // eax
  unsigned int v42; // eax
  int v43; // r14d
  __int64 v44; // rcx
  bool v45; // bl
  int v46; // eax
  __int64 (__fastcall *v47)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v48; // rbx
  int v49; // eax
  unsigned int v51; // [rsp+20h] [rbp-E0h]
  __int64 v52; // [rsp+28h] [rbp-D8h]
  char v53; // [rsp+40h] [rbp-C0h] BYREF
  bool v54; // [rsp+41h] [rbp-BFh] BYREF
  struct IXMLDOMNode *v55; // [rsp+48h] [rbp-B8h] BYREF
  int v56; // [rsp+50h] [rbp-B0h] BYREF
  NotificationParser *v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v59; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h] BYREF
  __int64 v61; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v62; // [rsp+80h] [rbp-80h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v63; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-70h] BYREF
  int v65; // [rsp+98h] [rbp-68h]
  UINT32 packageFamilyNameLength; // [rsp+9Ch] [rbp-64h] BYREF
  int v67; // [rsp+A0h] [rbp-60h]
  _QWORD v68[4]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v69[12]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v65 = a4;
  v57 = a1;
  v10 = 0;
  v67 = 0;
  v58 = 0;
  v53 = 0;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  v12 = v11(a2, &v58);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2DF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v12,
      v51);
  v56 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v58 + 64LL))(v58, &v56);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v13,
      v51);
  v14 = 0;
  for ( i = 0; (int)i < v56; ++i )
  {
    v55 = 0;
    v16 = v58;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v58 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
    v18 = v17(v16, i, &v55);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v18,
        v51);
    String1 = 0;
    v19 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v55->lpVtbl->get_nodeName)(v55, &String1);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2ED,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v19,
        v51);
    v20 = String1;
    if ( !wcscmp_0(String1, L"text") )
    {
      v21 = StringCchPrintfW(v69, 0xAu, L"%ld", v14);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v21,
          v51);
      v59 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
      NotificationParser::ParseText(v57, v55, packageFullName, v22, &v59);
      v23 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *))(*(_QWORD *)a3 + 80LL);
      v24 = v59;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v68, v69);
      v25 = v23(a3, v68[0], v24, &v53);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F7,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v25,
          v51);
      v26 = (__int64 *)&v59;
    }
    else if ( !wcscmp_0(v20, L"image") )
    {
      v27 = StringCchPrintfW(v69, 0xAu, L"%ld", v14);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2FC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v27,
          v51);
      v60 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
      NotificationParser::ParseImage(v57, (__int64)v55, packageFullName, v28, a7, a8, &v60);
      v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, char *))(*(_QWORD *)a3 + 80LL);
      v30 = v60;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v68, v69);
      v31 = v29(a3, v68[0], v30, &v53);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x301,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v31,
          v51);
      v26 = &v60;
    }
    else if ( !wcscmp_0(v20, L"group") )
    {
      v32 = StringCchPrintfW(v69, 0xAu, L"%ld", v14);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x306,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v32,
          v51);
      v61 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
      LODWORD(v52) = a8;
      NotificationParser::ParseGroup((__int64 *)v57, (__int64)v55, (__int64)packageFullName, v33, a7, v52, &v61);
      v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, char *))(*(_QWORD *)a3 + 80LL);
      v35 = v61;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v68, v69);
      v36 = v34(a3, v68[0], v35, &v53);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x30B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v36,
          v51);
      v26 = &v61;
    }
    else if ( !wcscmp_0(v20, L"progress") )
    {
      v37 = StringCchPrintfW(v69, 0xAu, L"%ld", v14);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x310,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v37,
          v51);
      v62 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
      NotificationParser::ParseProgress(v57, v55, packageFullName, v38, &v62);
      v39 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *))(*(_QWORD *)a3 + 80LL);
      v40 = v62;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v68, v69);
      v41 = v39(a3, v68[0], v40, &v53);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x315,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v41,
          v51);
      v26 = (__int64 *)&v62;
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECU8397>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ECU8397>::GetImpl'::`2'::impl)
        || wcscmp_0(String1, L"cameraPreview")
        || v65 != 0x10000000 )
      {
        goto LABEL_37;
      }
      memset_0(packageFamilyName, 0, 0x82u);
      packageFamilyNameLength = 65;
      v42 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
      if ( v42 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x321,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)v42,
          v51);
      v54 = 0;
      std::wstring::wstring(v68, packageFamilyName);
      v43 = v10 | 1;
      v67 = v43;
      v45 = (int)NotificationParser::IsCameraAccessAllowed(v44, v68, &v54) >= 0 && v54;
      v10 = v43 & 0xFFFFFFFE;
      std::wstring::~wstring(v68);
      if ( !v45 )
        goto LABEL_37;
      v46 = StringCchPrintfW(v69, 0xAu, L"%ld", v14);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x328,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v46,
          v51);
      v63 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
      NotificationParser::ParseCameraPreview(v57, v55, &v63);
      v47 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, char *))(*(_QWORD *)a3 + 80LL);
      v48 = v63;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v68, v69);
      v49 = v47(a3, v68[0], v48, &v53);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x32D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v49,
          v51);
      v26 = (__int64 *)&v63;
    }
    ++v14;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26);
LABEL_37:
    SysFreeString(String1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
}

```

## disassembly

```asm
0x1800192d4  mov     [rsp-8+arg_18], rbx
0x1800192d9  push    rbp
0x1800192da  push    rsi
0x1800192db  push    rdi
0x1800192dc  push    r12
0x1800192de  push    r13
0x1800192e0  push    r14
0x1800192e2  push    r15
0x1800192e4  lea     rbp, [rsp-80h]
0x1800192e9  sub     rsp, 180h
0x1800192f0  mov     rax, cs:__security_cookie
0x1800192f7  xor     rax, rsp
0x1800192fa  mov     [rbp+0B0h+var_40], rax
0x1800192fe  mov     [rbp+0B0h+var_118], r9d
0x180019302  mov     r12, r8
0x180019305  mov     rdi, rdx
0x180019308  mov     [rsp+1B0h+var_158], rcx
0x18001930d  mov     r13, [rbp+0B0h+packageFullName]
0x180019314  xor     r14d, r14d
0x180019317  mov     [rbp+0B0h+var_110], r14d
0x18001931b  mov     [rsp+1B0h+var_150], r14
0x180019320  mov     [rsp+1B0h+var_170], r14b
0x180019325  mov     rax, [rdx]
0x180019328  mov     rbx, [rax+60h]
0x18001932c  lea     rcx, [rsp+1B0h+var_150]
0x180019331  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019336  lea     rdx, [rsp+1B0h+var_150]
0x18001933b  mov     rcx, rdi
0x18001933e  mov     rax, rbx
0x180019341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019346  mov     rcx, [rbp+0B8h]; this
0x18001934d  test    eax, eax
0x18001934f  jns     short loc_180019366
0x180019351  mov     r9d, eax; char *
0x180019354  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001935b  mov     edx, 2DFh; void *
0x180019360  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019366  mov     [rsp+1B0h+var_160], 0
0x18001936e  mov     rcx, [rsp+1B0h+var_150]
0x180019373  mov     rax, [rcx]
0x180019376  lea     rdx, [rsp+1B0h+var_160]
0x18001937b  mov     rax, [rax+40h]
0x18001937f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019384  mov     rcx, [rbp+0B8h]; this
0x18001938b  test    eax, eax
0x18001938d  jns     short loc_1800193A4
0x18001938f  mov     r9d, eax; char *
0x180019392  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019399  mov     edx, 2E2h; void *
0x18001939e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800193a4  xor     esi, esi
0x1800193a6  xor     r15d, r15d
0x1800193a9  cmp     [rsp+1B0h+var_160], esi
0x1800193ad  jle     loc_180019893
0x1800193b3  mov     [rsp+1B0h+var_168], 0
0x1800193bc  mov     rdi, [rsp+1B0h+var_150]
0x1800193c1  mov     rax, [rdi]
0x1800193c4  mov     rbx, [rax+38h]
0x1800193c8  lea     rcx, [rsp+1B0h+var_168]
0x1800193cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800193d2  lea     r8, [rsp+1B0h+var_168]
0x1800193d7  mov     edx, r15d
0x1800193da  mov     rcx, rdi
0x1800193dd  mov     rax, rbx
0x1800193e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193e5  mov     rcx, [rbp+0B8h]; this
0x1800193ec  test    eax, eax
0x1800193ee  js      loc_1800199C0
0x1800193f4  mov     [rbp+0B0h+String1], 0
0x1800193fc  mov     rcx, [rsp+1B0h+var_168]
0x180019401  mov     rax, [rcx]
0x180019404  lea     rdx, [rbp+0B0h+String1]
0x180019408  mov     rax, [rax+38h]
0x18001940c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019411  mov     rcx, [rbp+0B8h]; this
0x180019418  test    eax, eax
0x18001941a  js      loc_1800199AB
0x180019420  lea     rdx, aText; "text"
0x180019427  mov     rbx, [rbp+0B0h+String1]
0x18001942b  mov     rcx, rbx; String1
0x18001942e  call    wcscmp_0
0x180019433  test    eax, eax
0x180019435  jnz     loc_1800194D9
0x18001943b  mov     r9d, esi
0x18001943e  lea     r8, aLd; "%ld"
0x180019445  lea     edx, [rax+0Ah]; unsigned __int64
0x180019448  lea     rcx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x18001944c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019451  mov     rcx, [rbp+0B8h]; this
0x180019458  test    eax, eax
0x18001945a  js      loc_1800198D9
0x180019460  mov     [rsp+1B0h+var_148], 0
0x180019469  lea     rcx, [rsp+1B0h+var_148]
0x18001946e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019473  lea     rax, [rsp+1B0h+var_148]
0x180019478  mov     [rsp+1B0h+var_190], rax; int
0x18001947d  mov     r8, r13; unsigned __int16 *
0x180019480  mov     rdx, [rsp+1B0h+var_168]; struct IXMLDOMNode *
0x180019485  mov     rcx, [rsp+1B0h+var_158]; this
0x18001948a  call    ?ParseText@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseText(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x18001948f  mov     rax, [r12]
0x180019493  mov     rdi, [rax+50h]
0x180019497  mov     rbx, [rsp+1B0h+var_148]
0x18001949c  lea     rdx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x1800194a0  lea     rcx, [rbp+0B0h+var_108]; this
0x1800194a4  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800194a9  lea     r9, [rsp+1B0h+var_170]
0x1800194ae  mov     r8, rbx
0x1800194b1  mov     rdx, [rbp+0B0h+var_108]
0x1800194b5  mov     rcx, r12
0x1800194b8  mov     rax, rdi
0x1800194bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194c0  mov     rcx, [rbp+0B8h]; this
0x1800194c7  test    eax, eax
0x1800194c9  js      loc_1800198C4
0x1800194cf  lea     rcx, [rsp+1B0h+var_148]
0x1800194d4  jmp     loc_180019868
0x1800194d9  lea     rdx, aImage; "image"
0x1800194e0  mov     rcx, rbx; String1
0x1800194e3  call    wcscmp_0
0x1800194e8  test    eax, eax
0x1800194ea  jnz     loc_1800195A2
0x1800194f0  mov     r9d, esi
0x1800194f3  lea     r8, aLd; "%ld"
0x1800194fa  lea     edx, [rax+0Ah]; unsigned __int64
0x1800194fd  lea     rcx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x180019501  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019506  mov     rcx, [rbp+0B8h]; this
0x18001950d  test    eax, eax
0x18001950f  js      loc_180019903
0x180019515  mov     [rsp+1B0h+var_140], 0
0x18001951e  lea     rcx, [rsp+1B0h+var_140]
0x180019523  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019528  lea     rax, [rsp+1B0h+var_140]
0x18001952d  mov     [rsp+1B0h+var_180], rax
0x180019532  mov     eax, [rbp+0B0h+arg_38]
0x180019538  mov     dword ptr [rsp+1B0h+var_188], eax
0x18001953c  mov     eax, [rbp+0B0h+arg_30]
0x180019542  mov     dword ptr [rsp+1B0h+var_190], eax; int
0x180019546  mov     r8, r13
0x180019549  mov     rdx, [rsp+1B0h+var_168]
0x18001954e  mov     rcx, [rsp+1B0h+var_158]
0x180019553  call    ?ParseImage@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseImage(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x180019558  mov     rax, [r12]
0x18001955c  mov     rdi, [rax+50h]
0x180019560  mov     rbx, [rsp+1B0h+var_140]
0x180019565  lea     rdx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x180019569  lea     rcx, [rbp+0B0h+var_108]; this
0x18001956d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180019572  lea     r9, [rsp+1B0h+var_170]
0x180019577  mov     r8, rbx
0x18001957a  mov     rdx, [rbp+0B0h+var_108]
0x18001957e  mov     rcx, r12
0x180019581  mov     rax, rdi
0x180019584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019589  mov     rcx, [rbp+0B8h]; this
0x180019590  test    eax, eax
0x180019592  js      loc_1800198EE
0x180019598  lea     rcx, [rsp+1B0h+var_140]
0x18001959d  jmp     loc_180019868
0x1800195a2  lea     rdx, aGroup; "group"
0x1800195a9  mov     rcx, rbx; String1
0x1800195ac  call    wcscmp_0
0x1800195b1  test    eax, eax
0x1800195b3  jnz     loc_18001966B
0x1800195b9  mov     r9d, esi
0x1800195bc  lea     r8, aLd; "%ld"
0x1800195c3  lea     edx, [rax+0Ah]; unsigned __int64
0x1800195c6  lea     rcx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x1800195ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800195cf  mov     rcx, [rbp+0B8h]; this
0x1800195d6  test    eax, eax
0x1800195d8  js      loc_18001992D
0x1800195de  mov     [rsp+1B0h+var_138], 0
0x1800195e7  lea     rcx, [rsp+1B0h+var_138]
0x1800195ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800195f1  lea     rax, [rsp+1B0h+var_138]
0x1800195f6  mov     [rsp+1B0h+var_180], rax
0x1800195fb  mov     eax, [rbp+0B0h+arg_38]
0x180019601  mov     dword ptr [rsp+1B0h+var_188], eax
0x180019605  mov     eax, [rbp+0B0h+arg_30]
0x18001960b  mov     dword ptr [rsp+1B0h+var_190], eax; int
0x18001960f  mov     r8, r13
0x180019612  mov     rdx, [rsp+1B0h+var_168]
0x180019617  mov     rcx, [rsp+1B0h+var_158]
0x18001961c  call    ?ParseGroup@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseGroup(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x180019621  mov     rax, [r12]
0x180019625  mov     rdi, [rax+50h]
0x180019629  mov     rbx, [rsp+1B0h+var_138]
0x18001962e  lea     rdx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x180019632  lea     rcx, [rbp+0B0h+var_108]; this
0x180019636  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001963b  lea     r9, [rsp+1B0h+var_170]
0x180019640  mov     r8, rbx
0x180019643  mov     rdx, [rbp+0B0h+var_108]
0x180019647  mov     rcx, r12
0x18001964a  mov     rax, rdi
0x18001964d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019652  mov     rcx, [rbp+0B8h]; this
0x180019659  test    eax, eax
0x18001965b  js      loc_180019918
0x180019661  lea     rcx, [rsp+1B0h+var_138]
0x180019666  jmp     loc_180019868
0x18001966b  lea     rdx, aProgress; "progress"
0x180019672  mov     rcx, rbx; String1
0x180019675  call    wcscmp_0
0x18001967a  test    eax, eax
0x18001967c  jnz     loc_18001971B
0x180019682  mov     r9d, esi
0x180019685  lea     r8, aLd; "%ld"
0x18001968c  lea     edx, [rax+0Ah]; unsigned __int64
0x18001968f  lea     rcx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x180019693  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019698  mov     rcx, [rbp+0B8h]; this
0x18001969f  test    eax, eax
0x1800196a1  js      loc_180019957
0x1800196a7  mov     [rbp+0B0h+var_130], 0
0x1800196af  lea     rcx, [rbp+0B0h+var_130]
0x1800196b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800196b8  lea     rax, [rbp+0B0h+var_130]
0x1800196bc  mov     [rsp+1B0h+var_190], rax; int
0x1800196c1  mov     r8, r13; unsigned __int16 *
0x1800196c4  mov     rdx, [rsp+1B0h+var_168]; struct IXMLDOMNode *
0x1800196c9  mov     rcx, [rsp+1B0h+var_158]; this
0x1800196ce  call    ?ParseProgress@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseProgress(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x1800196d3  mov     rax, [r12]
0x1800196d7  mov     rdi, [rax+50h]
0x1800196db  mov     rbx, [rbp+0B0h+var_130]
0x1800196df  lea     rdx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x1800196e3  lea     rcx, [rbp+0B0h+var_108]; this
0x1800196e7  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800196ec  lea     r9, [rsp+1B0h+var_170]
0x1800196f1  mov     r8, rbx
0x1800196f4  mov     rdx, [rbp+0B0h+var_108]
0x1800196f8  mov     rcx, r12
0x1800196fb  mov     rax, rdi
0x1800196fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019703  mov     rcx, [rbp+0B8h]; this
0x18001970a  test    eax, eax
0x18001970c  js      loc_180019942
0x180019712  lea     rcx, [rbp+0B0h+var_130]
0x180019716  jmp     loc_180019868
0x18001971b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ECU8397@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ECU8397@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECU8397> `wil::Feature<__WilFeatureTraits_Feature_ECU8397>::GetImpl(void)'::`2'::impl
0x180019722  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ECU8397@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECU8397>::__private_IsEnabled(void)
0x180019727  test    al, al
0x180019729  jz      loc_180019870
0x18001972f  lea     rdx, aCamerapreview; "cameraPreview"
0x180019736  mov     rcx, [rbp+0B0h+String1]; String1
0x18001973a  call    wcscmp_0
0x18001973f  test    eax, eax
0x180019741  jnz     loc_180019870
0x180019747  cmp     [rbp+0B0h+var_118], 10000000h
0x18001974e  jnz     loc_180019870
0x180019754  xor     edx, edx; Val
0x180019756  mov     r8d, 82h; Size
0x18001975c  lea     rcx, [rbp+0B0h+packageFamilyName]; void *
0x180019760  call    memset_0
0x180019765  mov     [rbp+0B0h+packageFamilyNameLength], 41h ; 'A'
0x18001976c  lea     r8, [rbp+0B0h+packageFamilyName]; packageFamilyName
0x180019770  lea     rdx, [rbp+0B0h+packageFamilyNameLength]; packageFamilyNameLength
0x180019774  mov     rcx, r13; packageFullName
0x180019777  call    cs:__imp_PackageFamilyNameFromFullName
0x18001977d  mov     rcx, [rbp+0B8h]; this
0x180019784  test    eax, eax
0x180019786  jnz     loc_180019996
0x18001978c  mov     [rsp+1B0h+var_16F], al
0x180019790  lea     rdx, [rbp+0B0h+packageFamilyName]
0x180019794  lea     rcx, [rbp+0B0h+var_108]
0x180019798  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001979d  nop
0x18001979e  or      r14d, 1
0x1800197a2  mov     [rbp+0B0h+var_110], r14d
0x1800197a6  lea     r8, [rsp+1B0h+var_16F]
0x1800197ab  lea     rdx, [rbp+0B0h+var_108]
0x1800197af  call    ?IsCameraAccessAllowed@NotificationParser@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; NotificationParser::IsCameraAccessAllowed(std::wstring const &,bool &)
0x1800197b4  test    eax, eax
0x1800197b6  js      short loc_1800197C3
0x1800197b8  cmp     [rsp+1B0h+var_16F], 0
0x1800197bd  jz      short loc_1800197C3
0x1800197bf  mov     bl, 1
0x1800197c1  jmp     short loc_1800197C5
0x1800197c3  xor     bl, bl
0x1800197c5  and     r14d, 0FFFFFFFEh
0x1800197c9  lea     rcx, [rbp+0B0h+var_108]
0x1800197cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800197d2  test    bl, bl
0x1800197d4  jz      loc_180019870
0x1800197da  mov     r9d, esi
0x1800197dd  lea     r8, aLd; "%ld"
0x1800197e4  mov     edx, 0Ah; unsigned __int64
0x1800197e9  lea     rcx, [rbp+0B0h+var_E8]; unsigned __int16 *
0x1800197ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800197f2  mov     rcx, [rbp+0B8h]; this
0x1800197f9  test    eax, eax
0x1800197fb  js      loc_180019981
0x180019801  mov     [rbp+0B0h+var_128], 0
0x180019809  lea     rcx, [rbp+0B0h+var_128]
0x18001980d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019812  lea     r8, [rbp+0B0h+var_128]; struct Windows::Foundation::Collections::IPropertySet **
0x180019816  mov     rdx, [rsp+1B0h+var_168]; struct IXMLDOMNode *
  ... truncated ...
```
