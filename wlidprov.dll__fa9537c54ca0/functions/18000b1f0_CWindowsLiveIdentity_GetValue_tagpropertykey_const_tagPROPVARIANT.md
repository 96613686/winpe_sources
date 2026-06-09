# CWindowsLiveIdentity::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18000b1f0`
- end: `0x18000bcbc`
- name: `?GetValue@CWindowsLiveIdentity@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `2764`
- prototype: `int(CWindowsLiveIdentity *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800090c0`
- `0x18000a3a0`
- `0x18000a400`
- `0x18000b1f0`
- `0x18000bcc4`
- `0x18000f0d8`
- `0x18001a0d0`
- `0x1800535d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b490`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b490`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b341`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b341`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b506`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b69d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b69d`
- `ntdll!strrchr` at `0x18000b273`
- `ntdll!strrchr` at `0x18000b5a6`
- `ntdll!strrchr` at `0x18000b6c9`
- `ntdll!strrchr` at `0x18000b79f`
- `ntdll!strrchr` at `0x18000b878`
- `ntdll!strrchr` at `0x18000b94e`
- `ntdll!strrchr` at `0x18000ba28`
- `ntdll!strrchr` at `0x18000b273`
- `ntdll!strrchr` at `0x18000b5a6`
- `ntdll!strrchr` at `0x18000b6c9`
- `ntdll!strrchr` at `0x18000b79f`
- `ntdll!strrchr` at `0x18000b878`
- `ntdll!strrchr` at `0x18000b94e`
- `ntdll!strrchr` at `0x18000ba28`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18000b555`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18000b555`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18000b47b`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18000b47b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWindowsLiveIdentity::GetValue(
        CWindowsLiveIdentity *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3)
{
  char *v6; // rax
  __int64 v7; // r8
  const char *v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  DWORD pid; // r9d
  unsigned int i; // ecx
  __int16 v14; // ax
  _WORD *v15; // rax
  bool v16; // cf
  int v17; // eax
  HRESULT inited; // eax
  _WORD *v20; // rdi
  SIZE_T v21; // rbx
  void *v22; // rax
  char *v23; // rax
  __int64 v24; // r8
  const char *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  char *v28; // rax
  __int64 v29; // r8
  const char *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  char *v33; // rax
  __int64 v34; // r8
  const char *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  char *v38; // rax
  __int64 v39; // r8
  const char *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  char *v43; // rax
  __int64 v44; // r8
  const char *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  char *v48; // rax
  __int64 v49; // r8
  const char *v50; // rcx
  __int64 v51; // rax
  int v52; // eax
  int v53; // eax
  __int64 v54; // [rsp+20h] [rbp-F8h]
  int v55; // [rsp+30h] [rbp-E8h] BYREF
  int v56; // [rsp+38h] [rbp-E0h] BYREF
  char *v57; // [rsp+40h] [rbp-D8h] BYREF
  char v58; // [rsp+48h] [rbp-D0h]
  _QWORD v59[8]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v60[16]; // [rsp+90h] [rbp-88h] BYREF
  const char *v61; // [rsp+A0h] [rbp-78h]
  int v62; // [rsp+A8h] [rbp-70h]
  int v63; // [rsp+ACh] [rbp-6Ch]
  const char *v64; // [rsp+B0h] [rbp-68h]
  __int64 v65; // [rsp+B8h] [rbp-60h]
  int *v66; // [rsp+C0h] [rbp-58h]
  __int64 v67; // [rsp+C8h] [rbp-50h]
  const wchar_t *v68; // [rsp+D0h] [rbp-48h]
  __int64 v69; // [rsp+D8h] [rbp-40h]

  v55 = 0;
  v59[0] = "CWindowsLiveIdentity::GetValue";
  v59[1] = &v55;
  v59[2] = 0;
  v59[3] = 0;
  if ( dword_18008532C == 7 )
  {
    if ( (byte_180084E48 & 8) != 0 )
    {
      v6 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp", 92);
      if ( v6 )
        v8 = v6 + 1;
      else
        v8 = "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp";
      v56 = 426;
      v9 = -1;
      if ( v8 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v8[v10] );
        v11 = v10 + 1;
      }
      else
      {
        v11 = 5;
        v8 = "NULL";
      }
      v61 = v8;
      v62 = v11;
      v63 = 0;
      v64 = "CWindowsLiveIdentity::GetValue";
      v65 = 31;
      v66 = &v56;
      v67 = 4;
      v68 = L"NULL";
      v69 = 10;
      McGenEventWrite_EventWriteTransfer(v8, WlidProv_TraceFunction_Enter, v7, 5, v60);
    }
    else
    {
LABEL_48:
      v9 = -1;
    }
  }
  else
  {
    switch ( dword_18008532C )
    {
      case 4:
        if ( (byte_180084E44 & 4) == 0 )
          goto LABEL_48;
        v23 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp", 92);
        if ( v23 )
          v25 = v23 + 1;
        else
          v25 = "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp";
        v56 = 426;
        v9 = -1;
        if ( v25 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v25[v26] );
          v27 = v26 + 1;
        }
        else
        {
          v27 = 5;
          v25 = "NULL";
        }
        v61 = v25;
        v62 = v27;
        v63 = 0;
        v64 = "CWindowsLiveIdentity::GetValue";
        v65 = 31;
        v66 = &v56;
        v67 = 4;
        v68 = L"NULL";
        v69 = 10;
        McGenEventWrite_EventWriteTransfer(v25, WlidSvc_TraceFunction_Enter, v24, 5, v60);
        break;
      case 5:
        if ( byte_180084E45 >= 0 )
          goto LABEL_48;
        v28 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp", 92);
        if ( v28 )
          v30 = v28 + 1;
        else
          v30 = "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp";
        v56 = 426;
        v9 = -1;
        if ( v30 )
        {
          v31 = -1;
          do
            ++v31;
          while ( v30[v31] );
          v32 = v31 + 1;
        }
        else
        {
          v32 = 5;
          v30 = "NULL";
        }
        v61 = v30;
        v62 = v32;
        v63 = 0;
        v64 = "CWindowsLiveIdentity::GetValue";
        v65 = 31;
        v66 = &v56;
        v67 = 4;
        v68 = L"NULL";
        v69 = 10;
        McGenEventWrite_EventWriteTransfer(v30, WlidModern_TraceFunction_Enter, v29, 5, v60);
        break;
      case 6:
        if ( (byte_180084E47 & 8) == 0 )
          goto LABEL_48;
        v33 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp", 92);
        if ( v33 )
          v35 = v33 + 1;
        else
          v35 = "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp";
        v56 = 426;
        v9 = -1;
        if ( v35 )
        {
          v36 = -1;
          do
            ++v36;
          while ( v35[v36] );
          v37 = v36 + 1;
        }
        else
        {
          v37 = 5;
          v35 = "NULL";
        }
        v61 = v35;
        v62 = v37;
        v63 = 0;
        v64 = "CWindowsLiveIdentity::GetValue";
        v65 = 31;
        v66 = &v56;
        v67 = 4;
        v68 = L"NULL";
        v69 = 10;
        McGenEventWrite_EventWriteTransfer(v35, WlidCli_TraceFunction_Enter, v34, 5, v60);
        break;
      case 8:
        if ( (byte_180084E49 & 0x10) == 0 )
          goto LABEL_48;
        v38 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp", 92);
        if ( v38 )
          v40 = v38 + 1;
        else
          v40 = "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp";
        v56 = 426;
        v9 = -1;
        if ( v40 )
        {
          v41 = -1;
          do
            ++v41;
          while ( v40[v41] );
          v42 = v41 + 1;
        }
        else
        {
          v42 = 5;
          v40 = "NULL";
        }
        v61 = v40;
        v62 = v42;
        v63 = 0;
        v64 = "CWindowsLiveIdentity::GetValue";
        v65 = 31;
        v66 = &v56;
        v67 = 4;
        v68 = L"NULL";
        v69 = 10;
        McGenEventWrite_EventWriteTransfer(v40, WlidBho_TraceFunction_Enter, v39, 5, v60);
        break;
      case 9:
        if ( (byte_180084E4A & 0x10) == 0 )
          goto LABEL_48;
        v43 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp", 92);
        if ( v43 )
          v45 = v43 + 1;
        else
          v45 = "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp";
        v56 = 426;
        v9 = -1;
        if ( v45 )
        {
          v46 = -1;
          do
            ++v46;
          while ( v45[v46] );
          v47 = v46 + 1;
        }
        else
        {
          v47 = 5;
          v45 = "NULL";
        }
        v61 = v45;
        v62 = v47;
        v63 = 0;
        v64 = "CWindowsLiveIdentity::GetValue";
        v65 = 31;
        v66 = &v56;
        v67 = 4;
        v68 = L"NULL";
        v69 = 10;
        McGenEventWrite_EventWriteTransfer(v45, TokenProvider_TraceFunction_Enter, v44, 5, v60);
        break;
      case 10:
        if ( (byte_180084E4B & 0x10) == 0 )
          goto LABEL_48;
        v48 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp", 92);
        if ( v48 )
          v50 = v48 + 1;
        else
          v50 = "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp";
        v56 = 426;
        v9 = -1;
        if ( v50 )
        {
          v51 = -1;
          do
            ++v51;
          while ( v50[v51] );
          v52 = v51 + 1;
        }
        else
        {
          v52 = 5;
          v50 = "NULL";
        }
        v61 = v50;
        v62 = v52;
        v63 = 0;
        v64 = "CWindowsLiveIdentity::GetValue";
        v65 = 31;
        v66 = &v56;
        v67 = 4;
        v68 = L"NULL";
        v69 = 10;
        McGenEventWrite_EventWriteTransfer(v50, Extension_TraceFunction_Enter, v49, 5, v60);
        break;
      default:
        goto LABEL_48;
    }
  }
  v57 = (char *)this + 136;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v58 = 1;
  if ( !a3 )
  {
LABEL_107:
    v55 = -2147024809;
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v57);
    CTraceFuncW<long>::~CTraceFuncW<long>(v59);
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v55, 0, 0);
  }
  pid = a2->pid;
  if ( pid == 100
    && a2->fmtid.Data1 == 1957158473
    && *(_DWORD *)&a2->fmtid.Data2 == *(_DWORD *)&PKEY_Identity_ProviderID.fmtid.Data2
    && *(_DWORD *)a2->fmtid.Data4 == *(_DWORD *)PKEY_Identity_ProviderID.fmtid.Data4
    && *(_DWORD *)&a2->fmtid.Data4[4] == *(_DWORD *)&PKEY_Identity_ProviderID.fmtid.Data4[4] )
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp",
      0x1BAu,
      L"Query for ProviderID");
    inited = InitPropVariantFromCLSID(&GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f, a3);
    v55 = inited;
    if ( inited < 0 )
    {
      LODWORD(v54) = inited;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp",
        0x1C2u,
        L"Failed Populate provider id. (0x%x)",
        v54);
      ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v57);
      CTraceFuncW<long>::~CTraceFuncW<long>(v59);
      return ErrorHandlingUtilities::MapInternalErrorToExternal(v55, 0, 0);
    }
    goto LABEL_28;
  }
  for ( i = 1; ; ++i )
  {
    if ( i >= 9 )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveidentity.cpp",
        0x219u,
        L"Property doesn't exist");
      PropVariantClear(a3);
      goto LABEL_28;
    }
    if ( pid == dword_180084380[12 * i]
      && *(_OWORD *)&a2->fmtid == __PAIR128__(
                                    __PAIR64__(HIDWORD(xmmword_180084370[3 * i]), DWORD2(xmmword_180084370[3 * i])),
                                    __PAIR64__(DWORD1(xmmword_180084370[3 * i]), xmmword_180084370[3 * i])) )
    {
      break;
    }
  }
  v14 = word_180084390[24 * i];
  if ( v14 != 31 )
  {
    if ( v14 == 11 )
    {
      v15 = (_WORD *)*((_QWORD *)this + i + 8);
      v16 = *v15 < 0x31u;
      if ( *v15 != 49 || (v16 = 0, v15[1]) )
        v17 = v16 ? -1 : 1;
      else
        v17 = 0;
      *(_WORD *)a3 = 11;
      *((_WORD *)a3 + 4) = (v17 != 0) - 1;
      v55 = 0;
    }
    else
    {
      if ( v14 != 4127 )
        goto LABEL_107;
      v55 = InitPropVariantFromStringAsVector(*((PCWSTR *)this + i + 8), a3);
      if ( v55 < 0 )
      {
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v57);
        CTraceFuncW<long>::~CTraceFuncW<long>(v59);
        return ErrorHandlingUtilities::MapInternalErrorToExternal(v55, 0, 0);
      }
    }
    goto LABEL_28;
  }
  v20 = (_WORD *)*((_QWORD *)this + i + 8);
  if ( !v20 )
  {
    v53 = -2147024809;
    goto LABEL_92;
  }
  do
    ++v9;
  while ( v20[v9] );
  v21 = 2 * v9 + 2;
  v22 = CoTaskMemAlloc(v21);
  a3[1] = v22;
  if ( !v22 )
  {
    v53 = -2147024882;
LABEL_92:
    *(_OWORD *)a3 = 0;
    a3[2] = 0;
    v55 = v53;
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v57);
    CTraceFuncW<long>::~CTraceFuncW<long>(v59);
    return ErrorHandlingUtilities::MapInternalErrorToExternal(v55, 0, 0);
  }
  if ( v21 )
    memcpy_0(v22, v20, v21);
  *(_WORD *)a3 = 31;
  v55 = 0;
LABEL_28:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  CTraceFuncW<long>::~CTraceFuncW<long>(v59);
  return ErrorHandlingUtilities::MapInternalErrorToExternal(v55, 0, 0);
}

```

## disassembly

```asm
0x18000b1f0  mov     [rsp+arg_8], rbx
0x18000b1f5  mov     [rsp+arg_18], rsi
0x18000b1fa  push    rdi
0x18000b1fb  push    r12
0x18000b1fd  push    r13
0x18000b1ff  push    r14
0x18000b201  push    r15
0x18000b203  sub     rsp, 0F0h
0x18000b20a  mov     rax, cs:__security_cookie
0x18000b211  xor     rax, rsp
0x18000b214  mov     [rsp+118h+var_38], rax
0x18000b21c  mov     r12, r8
0x18000b21f  mov     r14, rdx
0x18000b222  mov     r13, rcx
0x18000b225  xor     esi, esi
0x18000b227  mov     [rsp+118h+var_E8], esi
0x18000b22b  lea     r15, aCwindowsliveid_6; "CWindowsLiveIdentity::GetValue"
0x18000b232  mov     [rsp+118h+var_C8], r15
0x18000b237  lea     rax, [rsp+118h+var_E8]
0x18000b23c  mov     [rsp+118h+var_C0], rax
0x18000b241  mov     [rsp+118h+var_B8], rsi
0x18000b246  mov     [rsp+118h+var_B0], rsi
0x18000b24b  mov     eax, cs:dword_18008532C
0x18000b251  cmp     eax, 7
0x18000b254  jnz     loc_18000B56C
0x18000b25a  test    cs:byte_180084E48, 8
0x18000b261  jz      def_18000B58B; jumptable 000000018000B58B default case
0x18000b267  mov     edx, 5Ch ; '\'; Ch
0x18000b26c  lea     rcx, Str; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000b273  call    cs:__imp_strrchr
0x18000b279  test    rax, rax
0x18000b27c  jz      loc_18000B6A8
0x18000b282  lea     rcx, [rax+1]
0x18000b286  mov     [rsp+118h+var_E0], 1AAh
0x18000b28e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b295  test    rcx, rcx
0x18000b298  jz      loc_18000BBD0
0x18000b29e  mov     rax, rbx
0x18000b2a1  inc     rax
0x18000b2a4  cmp     byte ptr [rcx+rax], 0
0x18000b2a8  jnz     short loc_18000B2A1
0x18000b2aa  inc     eax
0x18000b2ac  mov     [rsp+118h+var_78], rcx
0x18000b2b4  mov     [rsp+118h+var_70], eax
0x18000b2bb  mov     [rsp+118h+var_6C], esi
0x18000b2c2  mov     [rsp+118h+var_68], r15
0x18000b2ca  mov     r15d, 1Fh
0x18000b2d0  mov     [rsp+118h+var_60], r15
0x18000b2d8  lea     rax, [rsp+118h+var_E0]
0x18000b2dd  mov     [rsp+118h+var_58], rax
0x18000b2e5  mov     [rsp+118h+var_50], 4
0x18000b2f1  lea     rax, aNull_1; "NULL"
0x18000b2f8  mov     [rsp+118h+var_48], rax
0x18000b300  mov     [rsp+118h+var_40], 0Ah
0x18000b30c  lea     rax, [rsp+118h+var_88]
0x18000b314  mov     [rsp+118h+var_F8], rax
0x18000b319  mov     r9d, 5
0x18000b31f  lea     rdx, WlidProv_TraceFunction_Enter
0x18000b326  call    McGenEventWrite_EventWriteTransfer
0x18000b32b  lea     rdi, __ImageBase
0x18000b332  lea     rsi, [r13+88h]
0x18000b339  mov     [rsp+118h+var_D8], rsi
0x18000b33e  mov     rcx, rsi; lpCriticalSection
0x18000b341  call    cs:__imp_EnterCriticalSection
0x18000b347  mov     [rsp+118h+var_D0], 1
0x18000b34c  test    r12, r12
0x18000b34f  jz      loc_18000BBE1
0x18000b355  mov     r9d, [r14+10h]
0x18000b359  cmp     r9d, 64h ; 'd'
0x18000b35d  jz      loc_18000B416
0x18000b363  mov     ecx, 1
0x18000b368  cmp     ecx, 9
0x18000b36b  jnb     loc_18000B67C
0x18000b371  mov     r8d, ecx
0x18000b374  lea     rdx, [r8+r8*2]
0x18000b378  add     rdx, rdx
0x18000b37b  cmp     r9d, rva dword_180084380[rdi+rdx*8]
0x18000b383  jz      short loc_18000B389
0x18000b385  inc     ecx
0x18000b387  jmp     short loc_18000B368
0x18000b389  mov     eax, dword ptr rva xmmword_180084370[rdi+rdx*8]
0x18000b390  cmp     [r14], eax
0x18000b393  jnz     short loc_18000B385
0x18000b395  mov     eax, dword ptr (rva xmmword_180084370+4)[rdi+rdx*8]
0x18000b39c  cmp     [r14+4], eax
0x18000b3a0  jnz     short loc_18000B385
0x18000b3a2  mov     eax, dword ptr (rva xmmword_180084370+8)[rdi+rdx*8]
0x18000b3a9  cmp     [r14+8], eax
0x18000b3ad  jnz     short loc_18000B385
0x18000b3af  mov     eax, dword ptr (rva xmmword_180084370+0Ch)[rdi+rdx*8]
0x18000b3b6  cmp     [r14+0Ch], eax
0x18000b3ba  jnz     short loc_18000B385
0x18000b3bc  movzx   eax, rva word_180084390[rdi+rdx*8]
0x18000b3c4  cmp     ax, 1Fh
0x18000b3c8  jz      loc_18000B4DD
0x18000b3ce  cmp     ax, 0Bh
0x18000b3d2  jnz     loc_18000B53F
0x18000b3d8  mov     rax, [r13+r8*8+40h]
0x18000b3dd  cmp     word ptr [rax], 31h ; '1'
0x18000b3e1  jnz     loc_18000BB60
0x18000b3e7  cmp     word ptr [rax+2], 0
0x18000b3ec  jnz     loc_18000BB60
0x18000b3f2  xor     eax, eax
0x18000b3f4  mov     word ptr [r12], 0Bh
0x18000b3fb  neg     eax
0x18000b3fd  sbb     ax, ax
0x18000b400  neg     ax
0x18000b403  dec     ax
0x18000b406  mov     [r12+8], ax
0x18000b40c  mov     [rsp+118h+var_E8], 0
0x18000b414  jmp     short loc_18000B48D
0x18000b416  cmp     dword ptr [r14], 74A7DE49h
0x18000b41d  jnz     loc_18000B363
0x18000b423  mov     eax, dword ptr cs:PKEY_Identity_ProviderID.fmtid.Data2
0x18000b429  cmp     [r14+4], eax
0x18000b42d  jnz     loc_18000B363
0x18000b433  mov     eax, dword ptr cs:PKEY_Identity_ProviderID.fmtid.Data4
0x18000b439  cmp     [r14+8], eax
0x18000b43d  jnz     loc_18000B363
0x18000b443  mov     eax, dword ptr cs:PKEY_Identity_ProviderID.fmtid.Data4+4
0x18000b449  cmp     [r14+0Ch], eax
0x18000b44d  jnz     loc_18000B363
0x18000b453  lea     r9, aQueryForProvid; "Query for ProviderID"
0x18000b45a  mov     r8d, 1BAh; unsigned int
0x18000b460  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000b467  mov     ecx, 5; unsigned __int8
0x18000b46c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000b471  mov     rdx, r12; ppropvar
0x18000b474  lea     rcx, _GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f; clsid
0x18000b47b  call    cs:__imp_InitPropVariantFromCLSID
0x18000b481  mov     [rsp+118h+var_E8], eax
0x18000b485  test    eax, eax
0x18000b487  js      loc_18000BC05
0x18000b48d  mov     rcx, rsi; lpCriticalSection
0x18000b490  call    cs:__imp_LeaveCriticalSection
0x18000b496  nop
0x18000b497  lea     rcx, [rsp+118h+var_C8]
0x18000b49c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000b4a1  nop
0x18000b4a2  xor     r8d, r8d; bool *
0x18000b4a5  xor     edx, edx; bool
0x18000b4a7  mov     ecx, [rsp+118h+var_E8]; int
0x18000b4ab  call    ?MapInternalErrorToExternal@ErrorHandlingUtilities@@SAJJ_NPEA_N@Z; ErrorHandlingUtilities::MapInternalErrorToExternal(long,bool,bool *)
0x18000b4b0  mov     rcx, [rsp+118h+var_38]
0x18000b4b8  xor     rcx, rsp; StackCookie
0x18000b4bb  call    __security_check_cookie
0x18000b4c0  lea     r11, [rsp+118h+var_28]
0x18000b4c8  mov     rbx, [r11+38h]
0x18000b4cc  mov     rsi, [r11+48h]
0x18000b4d0  mov     rsp, r11
0x18000b4d3  pop     r15
0x18000b4d5  pop     r14
0x18000b4d7  pop     r13
0x18000b4d9  pop     r12
0x18000b4db  pop     rdi
0x18000b4dc  retn
0x18000b4dd  mov     rdi, [r13+r8*8+40h]
0x18000b4e2  test    rdi, rdi
0x18000b4e5  jz      loc_18000BC81
0x18000b4eb  nop     dword ptr [rax+rax+00h]
0x18000b4f0  lea     rbx, [rbx+1]
0x18000b4f4  cmp     word ptr [rdi+rbx*2], 0
0x18000b4f9  jnz     short loc_18000B4F0
0x18000b4fb  lea     rbx, ds:2[rbx*2]
0x18000b503  mov     rcx, rbx; cb
0x18000b506  call    cs:__imp_CoTaskMemAlloc
0x18000b50c  mov     [r12+8], rax
0x18000b511  test    rax, rax
0x18000b514  jz      loc_18000BAE5
0x18000b51a  test    rbx, rbx
0x18000b51d  jz      short loc_18000B52D
0x18000b51f  mov     r8, rbx; Size
0x18000b522  mov     rdx, rdi; Src
0x18000b525  mov     rcx, rax; void *
0x18000b528  call    memcpy_0
0x18000b52d  mov     [r12], r15w
0x18000b532  mov     [rsp+118h+var_E8], 0
0x18000b53a  jmp     loc_18000B48D
0x18000b53f  mov     ecx, 101Fh
0x18000b544  cmp     ax, cx
0x18000b547  jnz     loc_18000BC42
0x18000b54d  mov     rdx, r12; ppropvar
0x18000b550  mov     rcx, [r13+r8*8+40h]; psz
0x18000b555  call    cs:__imp_InitPropVariantFromStringAsVector
0x18000b55b  mov     [rsp+118h+var_E8], eax
0x18000b55f  test    eax, eax
0x18000b561  jns     loc_18000B48D
0x18000b567  jmp     loc_18000BC66
0x18000b56c  add     eax, 0FFFFFFFCh; switch 7 cases
0x18000b56f  cmp     eax, 6
0x18000b572  ja      def_18000B58B; jumptable 000000018000B58B default case
0x18000b578  cdqe
0x18000b57a  lea     rdi, __ImageBase
0x18000b581  mov     eax, ds:(jpt_18000B58B - 180000000h)[rdi+rax*4]
0x18000b588  add     rax, rdi
0x18000b58b  jmp     rax; switch jump
0x18000b58d  test    cs:byte_180084E44, 4; jumptable 000000018000B58B case 4
0x18000b594  jz      loc_18000B66A; jumptable 000000018000B58B case 7
0x18000b59a  mov     edx, 5Ch ; '\'; Ch
0x18000b59f  lea     rcx, Str; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000b5a6  call    cs:__imp_strrchr
0x18000b5ac  test    rax, rax
0x18000b5af  jz      loc_18000BB18
0x18000b5b5  lea     rcx, [rax+1]
0x18000b5b9  mov     [rsp+118h+var_E0], 1AAh
0x18000b5c1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b5c8  test    rcx, rcx
0x18000b5cb  jz      loc_18000BB6A
0x18000b5d1  mov     rax, rbx
0x18000b5d4  inc     rax
0x18000b5d7  cmp     byte ptr [rcx+rax], 0
0x18000b5db  jnz     short loc_18000B5D4
0x18000b5dd  inc     eax
0x18000b5df  mov     [rsp+118h+var_78], rcx
0x18000b5e7  mov     [rsp+118h+var_70], eax
0x18000b5ee  mov     [rsp+118h+var_6C], esi
0x18000b5f5  mov     [rsp+118h+var_68], r15
0x18000b5fd  mov     r15d, 1Fh
0x18000b603  mov     [rsp+118h+var_60], r15
0x18000b60b  lea     rax, [rsp+118h+var_E0]
0x18000b610  mov     [rsp+118h+var_58], rax
0x18000b618  mov     [rsp+118h+var_50], 4
0x18000b624  lea     rax, aNull_1; "NULL"
0x18000b62b  mov     [rsp+118h+var_48], rax
0x18000b633  mov     [rsp+118h+var_40], 0Ah
0x18000b63f  lea     rax, [rsp+118h+var_88]
0x18000b647  mov     [rsp+118h+var_F8], rax
0x18000b64c  mov     r9d, 5
0x18000b652  lea     rdx, WlidSvc_TraceFunction_Enter
0x18000b659  call    McGenEventWrite_EventWriteTransfer
0x18000b65e  jmp     loc_18000B332
0x18000b663  lea     rdi, __ImageBase; jumptable 000000018000B58B default case
0x18000b66a  mov     r15d, 1Fh; jumptable 000000018000B58B case 7
0x18000b670  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b677  jmp     loc_18000B332
0x18000b67c  lea     r9, aPropertyDoesnT; "Property doesn't exist"
0x18000b683  mov     r8d, 219h; unsigned int
0x18000b689  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000b690  mov     ecx, 5; unsigned __int8
0x18000b695  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000b69a  mov     rcx, r12; pvar
0x18000b69d  call    cs:__imp_PropVariantClear
0x18000b6a3  jmp     loc_18000B48D
0x18000b6a8  lea     rcx, Str; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000b6af  jmp     loc_18000B286
0x18000b6b4  cmp     cs:byte_180084E45, 0; jumptable 000000018000B58B case 5
0x18000b6bb  jge     short loc_18000B66A; jumptable 000000018000B58B case 7
0x18000b6bd  mov     edx, 5Ch ; '\'; Ch
0x18000b6c2  lea     rcx, Str; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000b6c9  call    cs:__imp_strrchr
0x18000b6cf  test    rax, rax
0x18000b6d2  jz      loc_18000BB24
0x18000b6d8  lea     rcx, [rax+1]
0x18000b6dc  mov     [rsp+118h+var_E0], 1AAh
0x18000b6e4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b6eb  test    rcx, rcx
0x18000b6ee  jz      loc_18000BB7B
0x18000b6f4  mov     rax, rbx
0x18000b6f7  inc     rax
0x18000b6fa  cmp     byte ptr [rcx+rax], 0
0x18000b6fe  jnz     short loc_18000B6F7
0x18000b700  inc     eax
0x18000b702  mov     [rsp+118h+var_78], rcx
0x18000b70a  mov     [rsp+118h+var_70], eax
0x18000b711  mov     [rsp+118h+var_6C], esi
0x18000b718  mov     [rsp+118h+var_68], r15
0x18000b720  mov     r15d, 1Fh
0x18000b726  mov     [rsp+118h+var_60], r15
0x18000b72e  lea     rax, [rsp+118h+var_E0]
0x18000b733  mov     [rsp+118h+var_58], rax
0x18000b73b  mov     [rsp+118h+var_50], 4
0x18000b747  lea     rax, aNull_1; "NULL"
0x18000b74e  mov     [rsp+118h+var_48], rax
0x18000b756  mov     [rsp+118h+var_40], 0Ah
0x18000b762  lea     rax, [rsp+118h+var_88]
0x18000b76a  mov     [rsp+118h+var_F8], rax
0x18000b76f  mov     r9d, 5
0x18000b775  lea     rdx, WlidModern_TraceFunction_Enter
0x18000b77c  call    McGenEventWrite_EventWriteTransfer
0x18000b781  jmp     loc_18000B332
0x18000b786  test    cs:byte_180084E47, 8; jumptable 000000018000B58B case 6
0x18000b78d  jz      loc_18000B66A; jumptable 000000018000B58B case 7
0x18000b793  mov     edx, 5Ch ; '\'; Ch
0x18000b798  lea     rcx, Str; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000b79f  call    cs:__imp_strrchr
0x18000b7a5  test    rax, rax
0x18000b7a8  jz      loc_18000BB30
0x18000b7ae  lea     rcx, [rax+1]
0x18000b7b2  mov     [rsp+118h+var_E0], 1AAh
0x18000b7ba  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b7c1  test    rcx, rcx
0x18000b7c4  jz      loc_18000BB8C
0x18000b7ca  mov     rax, rbx
0x18000b7cd  nop     dword ptr [rax]
0x18000b7d0  inc     rax
0x18000b7d3  cmp     byte ptr [rcx+rax], 0
0x18000b7d7  jnz     short loc_18000B7D0
0x18000b7d9  inc     eax
0x18000b7db  mov     [rsp+118h+var_78], rcx
0x18000b7e3  mov     [rsp+118h+var_70], eax
  ... truncated ...
```
