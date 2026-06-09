# CRegEventProvider::AccessCheck(ushort const *,ushort const *,long,uchar const *)

- ea: `0x180007100`
- end: `0x1800079ee`
- name: `?AccessCheck@CRegEventProvider@@UEAAJPEBG0JPEBE@Z`
- size: `2286`
- prototype: `__int64 __fastcall(CRegEventProvider *this, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006fe0`
- `0x180007100`
- `0x180007a00`
- `0x180007ca8`
- `0x180007d10`
- `0x180007d70`
- `0x180009c6c`
- `0x180009da0`
- `0x18000b14c`
- `0x18000b758`
- `0x18000bb30`
- `0x18000bb54`
- `0x1800141e8`
- `0x180014380`
- `0x180015680`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800075d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800075d4`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180007601`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000763f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180007601`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000763f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073a2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007258`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800072b1`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007258`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800072b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007159`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007159`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000716e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000716e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000779a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000779a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007675`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007675`
- `esscli!GetAccessMask` at `0x18000769f`
- `esscli!GetAccessMask` at `0x18000769f`
- `wbemcomn!?Init@CPropertyName@@QEAAXXZ` at `0x180007316`
- `wbemcomn!?Init@CPropertyName@@QEAAXXZ` at `0x180007316`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007368`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007426`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007470`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x1800074c6`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007542`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x1800076f6`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007907`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007962`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x1800079bd`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007368`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007426`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007470`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x1800074c6`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007542`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x1800076f6`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007907`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x180007962`
- `wbemcomn!?Empty@CPropertyName@@QEAAXXZ` at `0x1800079bd`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18000733a`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x1800074f9`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18000733a`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x1800074f9`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000735d`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000741b`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007465`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007522`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007537`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800076d6`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800076eb`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007836`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000785e`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007886`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078ae`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078c9`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078e7`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078fc`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007942`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007957`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000799d`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800079b2`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000735d`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000741b`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007465`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007522`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007537`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800076d6`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800076eb`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007836`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000785e`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007886`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078ae`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078c9`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078e7`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800078fc`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007942`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180007957`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18000799d`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x1800079b2`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x180007377`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x180007377`
- `wbemcomn!??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z` at `0x1800071b6`
- `wbemcomn!??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z` at `0x1800071b6`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000738e`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000743f`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180007489`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000755b`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000770f`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180007920`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000797b`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x1800079d6`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000738e`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000743f`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180007489`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000755b`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000770f`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180007920`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18000797b`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x1800079d6`
- `wbemcomn!?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z` at `0x1800071d2`
- `wbemcomn!?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z` at `0x1800071d2`
- `wbemcomn!?AddElement@CPropertyName@@QEAAXPEBG@Z` at `0x180007328`
- `wbemcomn!?AddElement@CPropertyName@@QEAAXPEBG@Z` at `0x1800074e4`
- `wbemcomn!?AddElement@CPropertyName@@QEAAXPEBG@Z` at `0x180007328`
- `wbemcomn!?AddElement@CPropertyName@@QEAAXPEBG@Z` at `0x1800074e4`
- `wbemcomn!??ACFlexArray@@QEBAPEAXH@Z` at `0x1800073ce`
- `wbemcomn!??ACFlexArray@@QEBAPEAXH@Z` at `0x180007594`
- `wbemcomn!??ACFlexArray@@QEBAPEAXH@Z` at `0x1800075b2`
- `wbemcomn!??ACFlexArray@@QEBAPEAXH@Z` at `0x1800073ce`
- `wbemcomn!??ACFlexArray@@QEBAPEAXH@Z` at `0x180007594`
- `wbemcomn!??ACFlexArray@@QEBAPEAXH@Z` at `0x1800075b2`
- `wbemcomn!GetMemLogObject` at `0x1800077d5`
- `wbemcomn!GetMemLogObject` at `0x1800077d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800077e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800077e3`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180007585`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180007585`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180007380`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180007380`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800073e9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007614`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800073e9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007614`

## string_xrefs

- `0x1800071ea`: `RegistryValueChangeEvent`
- `0x1800072ef`: `RegistryTreeChangeEvent`
- `0x1800074dd`: `KeyPath`
- `0x1800074d4`: `RootPath`
- `0x1800072d6`: `RegistryKeyChangeEvent`

## pseudocode

```c
__int64 __fastcall CRegEventProvider::AccessCheck(
        CRegEventProvider *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int8 *a5)
{
  char *v6; // rbx
  int v7; // r15d
  __int64 result; // rax
  HANDLE CurrentThread; // rax
  BOOL v10; // ebx
  QL_LEVEL_1_RPN_EXPRESSION *v11; // r13
  const wchar_t *v12; // r14
  WCHAR *i; // rsi
  WCHAR v14; // di
  int v15; // eax
  WCHAR v16; // cx
  int v17; // eax
  CRegEventProvider *v18; // rcx
  int ValuesForProp; // edi
  unsigned int j; // ebx
  const unsigned __int16 *v21; // rax
  CRegEventProvider *v22; // rcx
  HKEY v23; // rdi
  HKEY *v24; // rax
  const unsigned __int16 *v25; // rdx
  CRegEventProvider *v26; // rcx
  int v27; // ebx
  unsigned int v28; // ebx
  HKEY v29; // r14
  unsigned int k; // esi
  const WCHAR *v31; // rax
  void *v32; // rax
  void *v33; // rdi
  int AccessMask; // eax
  char v35; // di
  CMemoryLog *MemLogObject; // rax
  int v37; // edx
  int v38; // r8d
  WCHAR DestStr[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SrcStr[2]; // [rsp+48h] [rbp-B8h] BYREF
  char *v41; // [rsp+50h] [rbp-B0h] BYREF
  struct QL_LEVEL_1_RPN_EXPRESSION *v42; // [rsp+58h] [rbp-A8h] BYREF
  BOOL AccessStatus; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v44; // [rsp+68h] [rbp-98h] BYREF
  BOOL bDaclDefaulted; // [rsp+70h] [rbp-90h] BYREF
  struct QL_LEVEL_1_RPN_EXPRESSION *v46; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v47[32]; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE TokenHandle; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v50[2]; // [rsp+B0h] [rbp-50h] BYREF
  PACL pDacl; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v52; // [rsp+C8h] [rbp-38h]
  _DWORD v53[24]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v54[24]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v55[4]; // [rsp+190h] [rbp+90h] BYREF
  _DWORD v56[24]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v57[192]; // [rsp+210h] [rbp+110h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+2D0h] [rbp+1D0h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+2E0h] [rbp+1E0h] BYREF

  v52 = a3;
  v6 = 0;
  TokenHandle = 0;
  v7 = 1;
  if ( !a5 )
  {
    result = WbemCoImpersonateClient();
    if ( (int)result < 0 )
      return result;
    CurrentThread = GetCurrentThread();
    v10 = OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle);
    WbemCoRevertToSelf();
    if ( !v10 )
      return 2147749891LL;
    v6 = (char *)TokenHandle;
  }
  v41 = v6;
  v55[0] = &CTextLexSource::`vftable';
  v55[2] = a3;
  v55[1] = a3;
  QL1_Parser::QL1_Parser((QL1_Parser *)v57, (struct CGenLexSource *)v55);
  v46 = 0;
  if ( QL1_Parser::Parse((QL1_Parser *)v57, &v46) )
  {
LABEL_40:
    QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
    CCloseMe::~CCloseMe((CCloseMe *)&v41);
    return 2147749911LL;
  }
  else
  {
    v11 = v46;
    v42 = v46;
    v12 = L"RegistryValueChangeEvent";
    for ( i = (WCHAR *)*((_QWORD *)v46 + 3); ; ++i )
    {
      v14 = *i;
      if ( *i )
      {
        if ( v14 > 0x7Fu )
        {
          SrcStr[0] = *i;
          DestStr[0] = 0;
          v15 = LCMapStringW(0x7Fu, 0x100u, SrcStr, 1, DestStr, 1);
          v14 = DestStr[0];
          if ( !v15 )
            v14 = SrcStr[0];
        }
        else if ( (unsigned __int16)(v14 - 65) <= 0x19u )
        {
          v14 += 32;
        }
      }
      else if ( !*v12 )
      {
        v7 = 0;
        goto LABEL_25;
      }
      v16 = *v12;
      if ( *v12 > 0x7Fu )
      {
        DestStr[0] = *v12;
        SrcStr[0] = 0;
        v17 = LCMapStringW(0x7Fu, 0x100u, DestStr, 1, SrcStr, 1);
        v16 = SrcStr[0];
        if ( !v17 )
          v16 = DestStr[0];
      }
      else if ( (unsigned __int16)(v16 - 65) <= 0x19u )
      {
        v16 += 32;
      }
      if ( v14 != v16 )
        break;
      ++v12;
    }
    if ( (unsigned int)wbem_wcsicmp(*((const unsigned __int16 **)v46 + 3), L"RegistryKeyChangeEvent") )
    {
      if ( (unsigned int)wbem_wcsicmp(*((const unsigned __int16 **)v46 + 3), L"RegistryTreeChangeEvent") )
      {
LABEL_39:
        CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(&v42);
        goto LABEL_40;
      }
      v7 = 2;
    }
LABEL_25:
    CPropertyName::Init((CPropertyName *)v47);
    CPropertyName::AddElement((CPropertyName *)v47, L"Hive");
    CWStringArray::CWStringArray((CWStringArray *)v53, 0, 100);
    ValuesForProp = CRegEventProvider::GetValuesForProp(
                      v18,
                      v46,
                      (struct CPropertyName *)v47,
                      (struct CWStringArray *)v53);
    if ( ValuesForProp >= 0 )
    {
      CUniquePointerArray<HKEY__ *>::CUniquePointerArray<HKEY__ *>(v54);
      for ( j = 0; (int)j < v53[0]; ++j )
      {
        v21 = (const unsigned __int16 *)CFlexArray::operator[](v53, j);
        v23 = CRegEventProvider::TranslateHiveName(v22, v21);
        if ( !v23 )
        {
          CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(v54);
          CWStringArray::~CWStringArray((CWStringArray *)v53);
          CPropertyName::Empty((CPropertyName *)v47);
          goto LABEL_39;
        }
        v24 = (HKEY *)CWin32DefaultArena::WbemMemAlloc(8u);
        if ( v24 )
        {
          *v24 = v23;
          if ( (int)CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::Add(v54, v24) >= 0 )
            continue;
        }
LABEL_37:
        CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(v54);
        CWStringArray::~CWStringArray((CWStringArray *)v53);
        CPropertyName::Empty((CPropertyName *)v47);
        CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(&v42);
        QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
        CCloseMe::~CCloseMe((CCloseMe *)&v41);
        return 2147749894LL;
      }
      CPropertyName::Empty((CPropertyName *)v47);
      v25 = L"RootPath";
      if ( v7 != 2 )
        v25 = L"KeyPath";
      CPropertyName::AddElement((CPropertyName *)v47, v25);
      CWStringArray::CWStringArray((CWStringArray *)v56, 0, 100);
      v27 = CRegEventProvider::GetValuesForProp(v26, v46, (struct CPropertyName *)v47, (struct CWStringArray *)v56);
      if ( v27 >= 0 )
      {
        v28 = 0;
LABEL_47:
        if ( (int)v28 >= v54[0] )
        {
          CWStringArray::~CWStringArray((CWStringArray *)v56);
          CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(v54);
          CWStringArray::~CWStringArray((CWStringArray *)v53);
          CPropertyName::Empty((CPropertyName *)v47);
          CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(&v42);
          QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
          CCloseMe::~CCloseMe((CCloseMe *)&v41);
          return 0;
        }
        else
        {
          v29 = *(HKEY *)CFlexArray::GetAt((CFlexArray *)v54, v28);
          CFlexArray::operator[](v53, v28);
          for ( k = 0; ; ++k )
          {
            if ( (int)k >= v56[0] )
            {
              ++v28;
              goto LABEL_47;
            }
            v31 = (const WCHAR *)CFlexArray::operator[](v56, k);
            phkResult = 0;
            if ( RegOpenKeyExW(v29, v31, 0, 0x20000u, &phkResult) )
              break;
            v44 = phkResult;
            *(_DWORD *)SrcStr = 0;
            if ( RegGetKeySecurity(phkResult, 7u, 0, (LPDWORD)SrcStr) != 122 )
            {
              CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v44);
              CWStringArray::~CWStringArray((CWStringArray *)v56);
LABEL_75:
              CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(v54);
              CWStringArray::~CWStringArray((CWStringArray *)v53);
              CPropertyName::Empty((CPropertyName *)v47);
              CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(&v42);
              QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
              CCloseMe::~CCloseMe((CCloseMe *)&v41);
              return 2147749889LL;
            }
            v32 = CWin32DefaultArena::WbemMemAlloc(*(unsigned int *)SrcStr);
            v33 = v32;
            if ( !v32 )
            {
              CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v44);
              CWStringArray::~CWStringArray((CWStringArray *)v56);
              goto LABEL_37;
            }
            v50[0] = v32;
            v50[1] = 0;
            if ( RegGetKeySecurity(phkResult, 7u, v32, (LPDWORD)SrcStr) )
              goto LABEL_69;
            bDaclDefaulted = 0;
            if ( a5 )
            {
              pDacl = 0;
              *(_DWORD *)DestStr = 0;
              if ( !GetSecurityDescriptorDacl(v33, (LPBOOL)DestStr, &pDacl, &bDaclDefaulted) )
                goto LABEL_69;
              if ( *(_DWORD *)DestStr )
              {
                AccessStatus = 0;
                AccessMask = GetAccessMask(a5, pDacl, (unsigned int *)&AccessStatus);
                v35 = AccessMask;
                if ( AccessMask )
                {
                  MemLogObject = GetMemLogObject();
                  CMemoryLog::Write(MemLogObject, -1);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, v38, (_DWORD)v52, v35);
                  }
LABEL_69:
                  CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>(v50);
                  CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v44);
                  CWStringArray::~CWStringArray((CWStringArray *)v56);
                  goto LABEL_75;
                }
                if ( (AccessStatus & 0x10) == 0 )
                  goto LABEL_59;
              }
            }
            else
            {
              GenericMapping.GenericRead = 131097;
              GenericMapping.GenericWrite = 131078;
              GenericMapping.GenericExecute = 131097;
              GenericMapping.GenericAll = 983103;
              wcscpy(DestStr, L"È");
              AccessStatus = 0;
              if ( !AccessCheck(
                      v33,
                      TokenHandle,
                      0x10u,
                      &GenericMapping,
                      &PrivilegeSet,
                      (LPDWORD)DestStr,
                      (LPDWORD)&bDaclDefaulted,
                      &AccessStatus)
                || !AccessStatus )
              {
LABEL_59:
                CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>(v50);
                CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v44);
                CWStringArray::~CWStringArray((CWStringArray *)v56);
                CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(v54);
                CWStringArray::~CWStringArray((CWStringArray *)v53);
                CPropertyName::Empty((CPropertyName *)v47);
                CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(&v42);
                QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
                CCloseMe::~CCloseMe((CCloseMe *)&v41);
                return 2147749891LL;
              }
            }
            CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>(v50);
            CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v44);
          }
          CWStringArray::~CWStringArray((CWStringArray *)v56);
          CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(v54);
          CWStringArray::~CWStringArray((CWStringArray *)v53);
          CPropertyName::Empty((CPropertyName *)v47);
          CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(&v42);
          QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
          CCloseMe::~CCloseMe((CCloseMe *)&v41);
          return 2147749890LL;
        }
      }
      else
      {
        CWStringArray::~CWStringArray((CWStringArray *)v56);
        CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(v54);
        CWStringArray::~CWStringArray((CWStringArray *)v53);
        CPropertyName::Empty((CPropertyName *)v47);
        CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(&v42);
        QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
        CCloseMe::~CCloseMe((CCloseMe *)&v41);
        return (unsigned int)v27;
      }
    }
    else
    {
      CWStringArray::~CWStringArray((CWStringArray *)v53);
      CPropertyName::Empty((CPropertyName *)v47);
      if ( v11 )
      {
        QL_LEVEL_1_RPN_EXPRESSION::~QL_LEVEL_1_RPN_EXPRESSION(v11);
        CWin32DefaultArena::WbemMemFree(v11);
      }
      QL1_Parser::~QL1_Parser((QL1_Parser *)v57);
      if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v6);
      return (unsigned int)ValuesForProp;
    }
  }
}

```

## disassembly

```asm
0x180007100  push    rbp
0x180007102  push    rbx
0x180007103  push    rsi
0x180007104  push    rdi
0x180007105  push    r12
0x180007107  push    r13
0x180007109  push    r14
0x18000710b  push    r15
0x18000710d  lea     rbp, [rsp-2C8h]
0x180007115  sub     rsp, 3C8h
0x18000711c  mov     rax, cs:__security_cookie
0x180007123  xor     rax, rsp
0x180007126  mov     [rbp+300h+var_50], rax
0x18000712d  mov     rdi, r8
0x180007130  mov     [rbp+300h+var_338], r8
0x180007134  mov     r12, [rbp+300h+arg_20]
0x18000713b  xor     ebx, ebx
0x18000713d  mov     [rbp+300h+TokenHandle], rbx
0x180007141  mov     r15d, 1
0x180007147  test    r12, r12
0x18000714a  jnz     short loc_180007187
0x18000714c  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x180007151  test    eax, eax
0x180007153  js      loc_18000749F
0x180007159  call    cs:__imp_GetCurrentThread
0x18000715f  mov     rcx, rax; ThreadHandle
0x180007162  lea     r9, [rbp+300h+TokenHandle]; TokenHandle
0x180007166  mov     r8d, r15d; OpenAsSelf
0x180007169  mov     edx, 20008h; DesiredAccess
0x18000716e  call    cs:__imp_OpenThreadToken
0x180007174  mov     ebx, eax
0x180007176  call    ?WbemCoRevertToSelf@@YAJXZ; WbemCoRevertToSelf(void)
0x18000717b  test    ebx, ebx
0x18000717d  jz      loc_180007720
0x180007183  mov     rbx, [rbp+300h+TokenHandle]
0x180007187  mov     [rsp+400h+var_3B0], rbx
0x18000718c  lea     rax, ??_7CTextLexSource@@6B@; const CTextLexSource::`vftable'
0x180007193  mov     [rbp+300h+var_270], rax
0x18000719a  mov     [rbp+300h+var_260], rdi
0x1800071a1  mov     [rbp+300h+var_268], rdi
0x1800071a8  lea     rdx, [rbp+300h+var_270]
0x1800071af  lea     rcx, [rbp+300h+var_1F0]
0x1800071b6  call    cs:__imp_??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z; QL1_Parser::QL1_Parser(CGenLexSource *)
0x1800071bc  nop
0x1800071bd  mov     [rsp+400h+var_388], 0
0x1800071c6  lea     rdx, [rsp+400h+var_388]
0x1800071cb  lea     rcx, [rbp+300h+var_1F0]
0x1800071d2  call    cs:__imp_?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z; QL1_Parser::Parse(QL_LEVEL_1_RPN_EXPRESSION * *)
0x1800071d8  test    eax, eax
0x1800071da  jnz     loc_180007482
0x1800071e0  mov     r13, [rsp+400h+var_388]
0x1800071e5  mov     [rsp+400h+var_3A8], r13
0x1800071ea  lea     r14, aRegistryvaluec; "RegistryValueChangeEvent"
0x1800071f1  mov     rax, [rsp+400h+var_388]
0x1800071f6  mov     rsi, [rax+18h]
0x1800071fa  nop     word ptr [rax+rax+00h]
0x180007200  movzx   edi, word ptr [rsi]
0x180007203  test    di, di
0x180007206  jnz     short loc_180007216
0x180007208  cmp     [r14], di
0x18000720c  jnz     short loc_18000726B
0x18000720e  xor     r15d, r15d
0x180007211  jmp     loc_180007312
0x180007216  cmp     di, 7Fh
0x18000721a  ja      short loc_18000722B
0x18000721c  lea     eax, [rdi-41h]
0x18000721f  cmp     ax, 19h
0x180007223  ja      short loc_18000726B
0x180007225  add     di, 20h ; ' '
0x180007229  jmp     short loc_18000726B
0x18000722b  mov     [rsp+400h+SrcStr], di
0x180007230  xor     eax, eax
0x180007232  mov     [rsp+400h+DestStr], ax
0x180007237  mov     [rsp+400h+cchDest], r15d; cchDest
0x18000723c  lea     rax, [rsp+400h+DestStr]
0x180007241  mov     [rsp+400h+lpDestStr], rax; lpDestStr
0x180007246  mov     r9d, r15d; cchSrc
0x180007249  lea     r8, [rsp+400h+SrcStr]; lpSrcStr
0x18000724e  mov     edx, 100h; dwMapFlags
0x180007253  mov     ecx, 7Fh; Locale
0x180007258  call    cs:__imp_LCMapStringW
0x18000725e  movzx   edi, [rsp+400h+DestStr]
0x180007263  test    eax, eax
0x180007265  cmovz   di, [rsp+400h+SrcStr]
0x18000726b  movzx   ecx, word ptr [r14]
0x18000726f  cmp     cx, 7Fh
0x180007273  ja      short loc_180007284
0x180007275  lea     eax, [rcx-41h]
0x180007278  cmp     ax, 19h
0x18000727c  ja      short loc_1800072C4
0x18000727e  add     cx, 20h ; ' '
0x180007282  jmp     short loc_1800072C4
0x180007284  mov     [rsp+400h+DestStr], cx
0x180007289  xor     eax, eax
0x18000728b  mov     [rsp+400h+SrcStr], ax
0x180007290  mov     [rsp+400h+cchDest], r15d; cchDest
0x180007295  lea     rax, [rsp+400h+SrcStr]
0x18000729a  mov     [rsp+400h+lpDestStr], rax; lpDestStr
0x18000729f  mov     r9d, r15d; cchSrc
0x1800072a2  lea     r8, [rsp+400h+DestStr]; lpSrcStr
0x1800072a7  mov     edx, 100h; dwMapFlags
0x1800072ac  mov     ecx, 7Fh; Locale
0x1800072b1  call    cs:__imp_LCMapStringW
0x1800072b7  movzx   ecx, [rsp+400h+SrcStr]
0x1800072bc  test    eax, eax
0x1800072be  cmovz   cx, [rsp+400h+DestStr]
0x1800072c4  cmp     di, cx
0x1800072c7  jnz     short loc_1800072D6
0x1800072c9  add     rsi, 2
0x1800072cd  add     r14, 2
0x1800072d1  jmp     loc_180007200
0x1800072d6  lea     rdx, aRegistrykeycha; "RegistryKeyChangeEvent"
0x1800072dd  mov     rcx, [rsp+400h+var_388]
0x1800072e2  mov     rcx, [rcx+18h]; unsigned __int16 *
0x1800072e6  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800072eb  test    eax, eax
0x1800072ed  jz      short loc_180007312
0x1800072ef  lea     rdx, aRegistrytreech; "RegistryTreeChangeEvent"
0x1800072f6  mov     rcx, [rsp+400h+var_388]
0x1800072fb  mov     rcx, [rcx+18h]; unsigned __int16 *
0x1800072ff  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180007304  test    eax, eax
0x180007306  jnz     loc_180007477
0x18000730c  mov     r15d, 2
0x180007312  lea     rcx, [rbp+300h+var_380]
0x180007316  call    cs:__imp_?Init@CPropertyName@@QEAAXXZ; CPropertyName::Init(void)
0x18000731c  nop
0x18000731d  lea     rdx, aHive; "Hive"
0x180007324  lea     rcx, [rbp+300h+var_380]
0x180007328  call    cs:__imp_?AddElement@CPropertyName@@QEAAXPEBG@Z; CPropertyName::AddElement(ushort const *)
0x18000732e  xor     edx, edx
0x180007330  mov     r8d, 64h ; 'd'
0x180007336  lea     rcx, [rbp+300h+var_330]
0x18000733a  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x180007340  nop
0x180007341  lea     r9, [rbp+300h+var_330]; struct CWStringArray *
0x180007345  lea     r8, [rbp+300h+var_380]; struct CPropertyName *
0x180007349  mov     rdx, [rsp+400h+var_388]; struct QL_LEVEL_1_RPN_EXPRESSION *
0x18000734e  call    ?GetValuesForProp@CRegEventProvider@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@AEAVCPropertyName@@AEAVCWStringArray@@@Z; CRegEventProvider::GetValuesForProp(QL_LEVEL_1_RPN_EXPRESSION *,CPropertyName &,CWStringArray &)
0x180007353  mov     edi, eax
0x180007355  test    eax, eax
0x180007357  jns     short loc_1800073AF
0x180007359  lea     rcx, [rbp+300h+var_330]
0x18000735d  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180007363  nop
0x180007364  lea     rcx, [rbp+300h+var_380]
0x180007368  call    cs:__imp_?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x18000736e  nop
0x18000736f  test    r13, r13
0x180007372  jz      short loc_180007387
0x180007374  mov     rcx, r13
0x180007377  call    cs:__imp_??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ; QL_LEVEL_1_RPN_EXPRESSION::~QL_LEVEL_1_RPN_EXPRESSION(void)
0x18000737d  mov     rcx, r13
0x180007380  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180007386  nop
0x180007387  lea     rcx, [rbp+300h+var_1F0]
0x18000738e  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x180007394  nop
0x180007395  lea     rax, [rbx-1]
0x180007399  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000739d  ja      short loc_1800073A8
0x18000739f  mov     rcx, rbx; hObject
0x1800073a2  call    cs:__imp_CloseHandle
0x1800073a8  mov     eax, edi
0x1800073aa  jmp     loc_18000749F
0x1800073af  lea     rcx, [rbp+300h+var_2D0]
0x1800073b3  call    ??0?$CUniquePointerArray@PEAUHKEY__@@@@QEAA@XZ; CUniquePointerArray<HKEY__ *>::CUniquePointerArray<HKEY__ *>(void)
0x1800073b8  nop
0x1800073b9  xor     r13d, r13d
0x1800073bc  mov     ebx, r13d
0x1800073bf  cmp     ebx, [rbp+300h+var_330]
0x1800073c2  jge     loc_1800074C2
0x1800073c8  mov     edx, ebx
0x1800073ca  lea     rcx, [rbp+300h+var_330]
0x1800073ce  call    cs:__imp_??ACFlexArray@@QEBAPEAXH@Z; CFlexArray::operator[](int)
0x1800073d4  mov     rdx, rax; unsigned __int16 *
0x1800073d7  call    ?TranslateHiveName@CRegEventProvider@@IEAAPEAUHKEY__@@PEBG@Z; CRegEventProvider::TranslateHiveName(ushort const *)
0x1800073dc  mov     rdi, rax
0x1800073df  test    rax, rax
0x1800073e2  jz      short loc_180007457
0x1800073e4  mov     ecx, 8
0x1800073e9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800073ef  test    rax, rax
0x1800073f2  jz      short loc_18000740D
0x1800073f4  mov     [rax], rdi
0x1800073f7  mov     rdx, rax
0x1800073fa  lea     rcx, [rbp+300h+var_2D0]
0x1800073fe  call    ?Add@?$CPointerArray@PEAUHKEY__@@V?$CUniqueManager@PEAUHKEY__@@@@VCFlexArray@@@@QEAAHPEAPEAUHKEY__@@@Z; CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::Add(HKEY__ * *)
0x180007403  test    eax, eax
0x180007405  js      short loc_18000740B
0x180007407  inc     ebx
0x180007409  jmp     short loc_1800073BF
0x18000740b  jmp     short $+2
0x18000740d  lea     rcx, [rbp+300h+var_2D0]
0x180007411  call    ??1?$CPointerArray@PEAUHKEY__@@V?$CUniqueManager@PEAUHKEY__@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(void)
0x180007416  nop
0x180007417  lea     rcx, [rbp+300h+var_330]
0x18000741b  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180007421  nop
0x180007422  lea     rcx, [rbp+300h+var_380]
0x180007426  call    cs:__imp_?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x18000742c  nop
0x18000742d  lea     rcx, [rsp+400h+var_3A8]
0x180007432  call    ??1?$CDeleteMe@UQL_LEVEL_1_RPN_EXPRESSION@@@@QEAA@XZ; CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(void)
0x180007437  nop
0x180007438  lea     rcx, [rbp+300h+var_1F0]
0x18000743f  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x180007445  nop
0x180007446  lea     rcx, [rsp+400h+var_3B0]; this
0x18000744b  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x180007450  mov     eax, 80041006h
0x180007455  jmp     short loc_18000749F
0x180007457  lea     rcx, [rbp+300h+var_2D0]
0x18000745b  call    ??1?$CPointerArray@PEAUHKEY__@@V?$CUniqueManager@PEAUHKEY__@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(void)
0x180007460  nop
0x180007461  lea     rcx, [rbp+300h+var_330]
0x180007465  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x18000746b  nop
0x18000746c  lea     rcx, [rbp+300h+var_380]
0x180007470  call    cs:__imp_?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x180007476  nop
0x180007477  lea     rcx, [rsp+400h+var_3A8]
0x18000747c  call    ??1?$CDeleteMe@UQL_LEVEL_1_RPN_EXPRESSION@@@@QEAA@XZ; CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(void)
0x180007481  nop
0x180007482  lea     rcx, [rbp+300h+var_1F0]
0x180007489  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x18000748f  nop
0x180007490  lea     rcx, [rsp+400h+var_3B0]; this
0x180007495  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x18000749a  mov     eax, 80041017h
0x18000749f  mov     rcx, [rbp+300h+var_50]
0x1800074a6  xor     rcx, rsp; StackCookie
0x1800074a9  call    __security_check_cookie
0x1800074ae  add     rsp, 3C8h
0x1800074b5  pop     r15
0x1800074b7  pop     r14
0x1800074b9  pop     r13
0x1800074bb  pop     r12
0x1800074bd  pop     rdi
0x1800074be  pop     rsi
0x1800074bf  pop     rbx
0x1800074c0  pop     rbp
0x1800074c1  retn
0x1800074c2  lea     rcx, [rbp+300h+var_380]
0x1800074c6  call    cs:__imp_?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x1800074cc  lea     rcx, [rbp+300h+var_380]
0x1800074d0  cmp     r15d, 2
0x1800074d4  lea     rdx, aRootpath; "RootPath"
0x1800074db  jz      short loc_1800074E4
0x1800074dd  lea     rdx, aKeypath; "KeyPath"
0x1800074e4  call    cs:__imp_?AddElement@CPropertyName@@QEAAXPEBG@Z; CPropertyName::AddElement(ushort const *)
0x1800074ea  xor     edx, edx
0x1800074ec  mov     r8d, 64h ; 'd'
0x1800074f2  lea     rcx, [rbp+300h+var_250]
0x1800074f9  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x1800074ff  nop
0x180007500  lea     r9, [rbp+300h+var_250]; struct CWStringArray *
0x180007507  lea     r8, [rbp+300h+var_380]; struct CPropertyName *
0x18000750b  mov     rdx, [rsp+400h+var_388]; struct QL_LEVEL_1_RPN_EXPRESSION *
0x180007510  call    ?GetValuesForProp@CRegEventProvider@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@AEAVCPropertyName@@AEAVCWStringArray@@@Z; CRegEventProvider::GetValuesForProp(QL_LEVEL_1_RPN_EXPRESSION *,CPropertyName &,CWStringArray &)
0x180007515  mov     ebx, eax
0x180007517  test    eax, eax
0x180007519  jns     short loc_180007573
0x18000751b  lea     rcx, [rbp+300h+var_250]
0x180007522  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180007528  nop
0x180007529  lea     rcx, [rbp+300h+var_2D0]
0x18000752d  call    ??1?$CPointerArray@PEAUHKEY__@@V?$CUniqueManager@PEAUHKEY__@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(void)
0x180007532  nop
0x180007533  lea     rcx, [rbp+300h+var_330]
0x180007537  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x18000753d  nop
0x18000753e  lea     rcx, [rbp+300h+var_380]
0x180007542  call    cs:__imp_?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x180007548  nop
0x180007549  lea     rcx, [rsp+400h+var_3A8]
0x18000754e  call    ??1?$CDeleteMe@UQL_LEVEL_1_RPN_EXPRESSION@@@@QEAA@XZ; CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(void)
0x180007553  nop
0x180007554  lea     rcx, [rbp+300h+var_1F0]
0x18000755b  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x180007561  nop
0x180007562  lea     rcx, [rsp+400h+var_3B0]; this
0x180007567  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x18000756c  mov     eax, ebx
0x18000756e  jmp     loc_18000749F
0x180007573  mov     ebx, r13d
0x180007576  cmp     ebx, [rbp+300h+var_2D0]
0x180007579  jge     loc_180007996
0x18000757f  mov     edx, ebx
0x180007581  lea     rcx, [rbp+300h+var_2D0]
0x180007585  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000758b  mov     r14, [rax]
0x18000758e  mov     edx, ebx
0x180007590  lea     rcx, [rbp+300h+var_330]
0x180007594  call    cs:__imp_??ACFlexArray@@QEBAPEAXH@Z; CFlexArray::operator[](int)
0x18000759a  mov     esi, r13d
0x18000759d  cmp     esi, [rbp+300h+var_250]
0x1800075a3  jge     loc_1800077CE
0x1800075a9  mov     edx, esi
0x1800075ab  lea     rcx, [rbp+300h+var_250]
  ... truncated ...
```
