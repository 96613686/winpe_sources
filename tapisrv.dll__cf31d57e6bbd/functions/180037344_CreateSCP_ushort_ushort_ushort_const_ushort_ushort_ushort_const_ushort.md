# CreateSCP(ushort *,ushort *,ushort const *,ushort *,ushort *,ushort const *,ushort * *)

- ea: `0x180037344`
- end: `0x180037a4a`
- name: `?CreateSCP@@YAJPEAG0PEBG001PEAPEAG@Z`
- size: `1798`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180037264`
- `0x18003ca9c`

## callees

- `0x180001600`
- `0x18001c740`
- `0x18001c854`
- `0x180036b7c`
- `0x180037344`
- `0x180039080`
- `0x1800390e4`
- `0x18003ad1c`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800375dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800375dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003799d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003799d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800379fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800379fc`
- `KERNEL32!HeapAlloc` at `0x180037930`
- `KERNEL32!HeapAlloc` at `0x180037930`
- `KERNEL32!GetComputerNameExW` at `0x180037574`
- `KERNEL32!GetComputerNameExW` at `0x180037574`
- `KERNEL32!GetLastError` at `0x180037582`
- `KERNEL32!GetLastError` at `0x180037725`
- `KERNEL32!GetLastError` at `0x1800379a7`
- `KERNEL32!GetLastError` at `0x180037a0a`
- `KERNEL32!GetLastError` at `0x180037582`
- `KERNEL32!GetLastError` at `0x180037725`
- `KERNEL32!GetLastError` at `0x1800379a7`
- `KERNEL32!GetLastError` at `0x180037a0a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180037631`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180037631`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180037529`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180037529`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800377a7`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800377a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800375ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800375ec`
- `Secur32!GetComputerObjectNameW` at `0x180037719`
- `Secur32!GetComputerObjectNameW` at `0x180037719`

## string_xrefs

- `0x1800373d1`: `serviceDNSName`
- `0x180037413`: `serviceDNSNameType`
- `0x180037596`: `GetComputerNameEx: %ls\n`
- `0x180037677`: `serviceConnectionPoint`
- `0x18003743f`: `serviceClassName`
- `0x18003746b`: `serviceBindingInformation`
- `0x180037a3e`: `Failed to bind Computer Object. 0x%x`
- `0x180037739`: `GetComputerObjectName: %ls\n`
- `0x180037859`: `Failed to set ACEs on SCP DACL: 0x%x\n`
- `0x1800377e8`: `Failed to create SCP: 0x%x\n`
- `0x1800379ad`: `RegCreateKeyEx failed: 0x%x\n`
- `0x180037a12`: `RegSetValueEx failed: 0x%x\n`

## pseudocode

```c
__int64 __fastcall CreateSCP(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        LPCWSTR lpValueName,
        unsigned __int16 **a7)
{
  unsigned __int16 *v10; // rdi
  int v11; // eax
  int Object; // ebx
  void *v13; // rcx
  unsigned int v15; // r11d
  int v16; // eax
  int v17; // eax
  const char *v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // rax
  size_t v21; // rbx
  unsigned __int16 *v22; // rax
  DWORD nSize; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  struct IADs *v26; // [rsp+60h] [rbp-A0h] BYREF
  void *ppObject; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  __int128 v32; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int128 v36; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-30h]
  __int128 v38; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v39; // [rsp+E8h] [rbp-18h]
  __int128 v40; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v41; // [rsp+100h] [rbp+0h]
  __int128 v42; // [rsp+108h] [rbp+8h] BYREF
  __int64 v43; // [rsp+118h] [rbp+18h]
  const wchar_t *v44; // [rsp+120h] [rbp+20h] BYREF
  int v45; // [rsp+128h] [rbp+28h]
  int v46; // [rsp+12Ch] [rbp+2Ch]
  __int128 *v47; // [rsp+130h] [rbp+30h]
  int v48; // [rsp+138h] [rbp+38h]
  const wchar_t *v49; // [rsp+140h] [rbp+40h]
  int v50; // [rsp+148h] [rbp+48h]
  int v51; // [rsp+14Ch] [rbp+4Ch]
  __int128 *v52; // [rsp+150h] [rbp+50h]
  int v53; // [rsp+158h] [rbp+58h]
  const wchar_t *v54; // [rsp+160h] [rbp+60h]
  int v55; // [rsp+168h] [rbp+68h]
  int v56; // [rsp+16Ch] [rbp+6Ch]
  int *v57; // [rsp+170h] [rbp+70h]
  int v58; // [rsp+178h] [rbp+78h]
  const wchar_t *v59; // [rsp+180h] [rbp+80h]
  int v60; // [rsp+188h] [rbp+88h]
  int v61; // [rsp+18Ch] [rbp+8Ch]
  __int128 *v62; // [rsp+190h] [rbp+90h]
  int v63; // [rsp+198h] [rbp+98h]
  const wchar_t *v64; // [rsp+1A0h] [rbp+A0h]
  int v65; // [rsp+1A8h] [rbp+A8h]
  int v66; // [rsp+1ACh] [rbp+ACh]
  __int128 *v67; // [rsp+1B0h] [rbp+B0h]
  int v68; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v69; // [rsp+1C0h] [rbp+C0h]
  int v70; // [rsp+1C8h] [rbp+C8h]
  int v71; // [rsp+1CCh] [rbp+CCh]
  __int128 *v72; // [rsp+1D0h] [rbp+D0h]
  int v73; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v74; // [rsp+1E0h] [rbp+E0h]
  int v75; // [rsp+1E8h] [rbp+E8h]
  int v76; // [rsp+1ECh] [rbp+ECh]
  __int128 *v77; // [rsp+1F0h] [rbp+F0h]
  int v78; // [rsp+1F8h] [rbp+F8h]
  int v79; // [rsp+200h] [rbp+100h] BYREF
  const wchar_t *v80; // [rsp+208h] [rbp+108h]
  int v81; // [rsp+218h] [rbp+118h]
  const unsigned __int16 *v82; // [rsp+220h] [rbp+120h]
  int v83; // [rsp+230h] [rbp+130h]
  const wchar_t *v84; // [rsp+238h] [rbp+138h]
  int v85; // [rsp+248h] [rbp+148h]
  unsigned __int16 *v86; // [rsp+250h] [rbp+150h]
  int v87; // [rsp+260h] [rbp+160h]
  unsigned __int16 *v88; // [rsp+268h] [rbp+168h]
  wchar_t pszSrc[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Buffer[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR NameBuffer[264]; // [rsp+510h] [rbp+410h] BYREF
  wchar_t pszDest[264]; // [rsp+720h] [rbp+620h] BYREF

  nSize = 0;
  v29 = 0;
  ppObject = 0;
  v10 = 0;
  v26 = 0;
  v11 = 4;
  v25 = 0;
  v24 = 0;
  if ( a4 && *a4 )
  {
    v10 = a4;
    v11 = 5;
  }
  v58 = v11;
  v33 = 0;
  v35 = 0;
  v59 = L"serviceDNSName";
  v43 = 0;
  v41 = 0;
  v37 = 0;
  v39 = 0;
  v62 = &v36;
  v44 = L"cn";
  v64 = L"serviceDNSNameType";
  v47 = &v32;
  v67 = &v38;
  v49 = L"objectClass";
  v69 = L"serviceClassName";
  v52 = &v34;
  v72 = &v40;
  v54 = L"keywords";
  v74 = L"serviceBindingInformation";
  v57 = &v79;
  v77 = &v42;
  hKey = 0;
  dwDisposition = 0;
  v32 = 0;
  v45 = 2;
  v34 = 0;
  v46 = 3;
  v42 = 0;
  v48 = 1;
  v40 = 0;
  v50 = 2;
  v36 = 0;
  v51 = 3;
  v38 = 0;
  v53 = 1;
  v55 = 2;
  v56 = 3;
  v60 = 2;
  v61 = 3;
  v63 = 1;
  v65 = 2;
  v66 = 3;
  v68 = 1;
  v70 = 2;
  v71 = 3;
  v73 = 1;
  v75 = 2;
  v76 = 3;
  v78 = 1;
  bstrString = 0;
  Object = CoInitializeEx(0, 0);
  if ( Object < 0 )
    goto LABEL_10;
  v25 = 1;
  if ( (unsigned int)IsCurrentLocalSystem() )
  {
    Object = ImpersonateLocalSystem();
    if ( Object )
      goto LABEL_10;
    v24 = 1;
  }
  nSize = 260;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize) )
  {
    Object = GetLastError() | 0x10000000;
    TRACELogPrint(65538, "GetComputerNameEx: %ls\n", Buffer);
    goto LABEL_10;
  }
  v82 = a3;
  *((_QWORD *)&v32 + 1) = a1 + 3;
  LODWORD(v32) = 3;
  *((_QWORD *)&v34 + 1) = L"serviceConnectionPoint";
  LODWORD(v34) = 3;
  v80 = L"937924B8-AA44-11d2-81F1-00C04FB9624E";
  v79 = 3;
  v84 = L"Microsoft";
  v81 = 3;
  *((_QWORD *)&v36 + 1) = Buffer;
  *((_QWORD *)&v38 + 1) = L"A";
  *((_QWORD *)&v42 + 1) = a5;
  v83 = 3;
  v85 = 3;
  v87 = 3;
  v86 = a2;
  v88 = v10;
  LODWORD(v36) = 3;
  LODWORD(v38) = 3;
  LODWORD(v40) = 3;
  *((_QWORD *)&v40 + 1) = a2;
  LODWORD(v42) = 3;
  nSize = 260;
  if ( !GetComputerObjectNameW(NameFullyQualifiedDN, NameBuffer, &nSize) )
  {
    Object = GetLastError() | 0x10000000;
    TRACELogPrint(65538, "GetComputerObjectName: %ls\n", NameBuffer);
    goto LABEL_10;
  }
  Object = StringCbCopyW(pszDest, 0x208u, L"LDAP://");
  if ( Object < 0
    || (Object = StringCbCatW(pszDest, v15, NameBuffer), Object < 0)
    || (Object = ADsGetObject(pszDest, &IID_IDirectoryObject, &ppObject), Object < 0) )
  {
    TRACELogPrint(65538, "Failed to bind Computer Object. 0x%x", (unsigned int)Object);
    goto LABEL_10;
  }
  v16 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, const wchar_t **, __int64, __int64 *))(*(_QWORD *)ppObject + 48LL))(
          ppObject,
          a1,
          &v44,
          7,
          &v29);
  Object = v16;
  if ( v16 < 0 )
  {
    TRACELogPrint(65538, "Failed to create SCP: 0x%x\n", v16);
    if ( (_WORD)Object == 5010 )
      Object = -22;
    goto LABEL_10;
  }
  v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IADs **))v29)(v29, &IID_IADs, &v26);
  Object = v17;
  if ( v17 < 0 )
  {
    v18 = "Failed to QI for IADs: 0x%x\n";
LABEL_37:
    TRACELogPrint(65538, v18, (unsigned int)v17);
    goto LABEL_10;
  }
  v17 = AllowAccessToScpProperties(v26);
  Object = v17;
  if ( v17 < 0 )
  {
    v18 = "Failed to set ACEs on SCP DACL: 0x%x\n";
    goto LABEL_37;
  }
  v17 = ((__int64 (__fastcall *)(struct IADs *, BSTR *))v26->lpVtbl->get_GUID)(v26, &bstrString);
  Object = v17;
  if ( v17 < 0 )
  {
    v18 = "Failed to get GUID: 0x%x\n";
    goto LABEL_37;
  }
  Object = StringCbCopyW(pszSrc, 0x80u, L"LDAP://<GUID=");
  if ( Object < 0
    || (Object = StringCbCatW(pszSrc, 0x80u, bstrString), Object < 0)
    || (Object = StringCbCatW(pszSrc, 0x80u, L">"), Object < 0) )
  {
    TRACELogPrint(65538, "Error building binding string");
    goto LABEL_10;
  }
  TRACELogPrint(262146, "GUID binding string: %S\n", pszSrc);
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( pszSrc[v20] );
  if ( a7 )
  {
    v21 = 2 * v20 + 2;
    v22 = (unsigned __int16 *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v20 + 2));
    *a7 = v22;
    if ( !v22 )
    {
      Object = -2147483580;
      goto LABEL_10;
    }
    Object = StringCbCopyW(v22, v21, pszSrc);
  }
  if ( lpValueName )
  {
    if ( RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           &dwDisposition) )
    {
      Object = GetLastError() | 0x10000000;
      TRACELogPrint(65538, "RegCreateKeyEx failed: 0x%x\n", Object);
      return (unsigned int)Object;
    }
    do
      ++v19;
    while ( pszSrc[v19] );
    if ( RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)pszSrc, 2 * v19) )
    {
      Object = GetLastError() | 0x10000000;
      TRACELogPrint(65538, "RegSetValueEx failed: 0x%x\n", (unsigned int)Object);
    }
  }
LABEL_10:
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v26 )
    ((void (__fastcall *)(struct IADs *))v26->lpVtbl->Release)(v26);
  if ( hKey )
    RegCloseKey(hKey);
  if ( bstrString )
    SysFreeString(bstrString);
  v13 = ppObject;
  if ( ppObject )
  {
    if ( Object < 0 )
    {
      (*(void (__fastcall **)(void *, unsigned __int16 *))(*(_QWORD *)ppObject + 56LL))(ppObject, a1);
      v13 = ppObject;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v24 )
    RevertLocalSystemImp();
  if ( v25 )
    CoUninitialize();
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180037344  mov     [rsp-8+arg_18], rbx
0x180037349  push    rbp
0x18003734a  push    rsi
0x18003734b  push    rdi
0x18003734c  push    r12
0x18003734e  push    r13
0x180037350  push    r14
0x180037352  push    r15
0x180037354  lea     rbp, [rsp-840h]
0x18003735c  sub     rsp, 940h
0x180037363  mov     rax, cs:__security_cookie
0x18003736a  xor     rax, rsp
0x18003736d  mov     [rbp+870h+var_40], rax
0x180037374  mov     r15, [rbp+870h+lpValueName]
0x18003737b  mov     rsi, rdx
0x18003737e  mov     r14, [rbp+870h+arg_30]
0x180037385  xor     edx, edx; dwCoInit
0x180037387  mov     [rsp+970h+nSize], edx
0x18003738b  mov     r12, r8
0x18003738e  mov     [rsp+970h+var_8F8], rdx
0x180037393  mov     r13, rcx
0x180037396  mov     [rsp+970h+ppObject], rdx
0x18003739b  mov     edi, edx
0x18003739d  mov     [rsp+970h+var_910], rdx
0x1800373a2  lea     eax, [rdx+4]
0x1800373a5  mov     [rsp+970h+var_918], edx
0x1800373a9  mov     [rsp+970h+var_91C], edx
0x1800373ad  test    r9, r9
0x1800373b0  jz      short loc_1800373BE
0x1800373b2  cmp     [r9], dx
0x1800373b6  jz      short loc_1800373BE
0x1800373b8  mov     rdi, r9
0x1800373bb  lea     eax, [rdx+5]
0x1800373be  xor     ecx, ecx
0x1800373c0  mov     [rbp+870h+var_7F8], eax
0x1800373c3  mov     r10d, 2
0x1800373c9  mov     [rbp+870h+var_8D0], rcx
0x1800373cd  mov     [rbp+870h+var_8B8], rcx
0x1800373d1  lea     rax, aServicednsname_2; "serviceDNSName"
0x1800373d8  mov     [rbp+870h+var_7F0], rax
0x1800373df  xorps   xmm0, xmm0
0x1800373e2  mov     [rbp+870h+var_858], rcx
0x1800373e6  lea     rax, [rbp+870h+var_8B0]
0x1800373ea  mov     [rbp+870h+var_870], rcx
0x1800373ee  lea     r8d, [r10+1]
0x1800373f2  mov     [rbp+870h+var_8A0], rcx
0x1800373f6  lea     r9d, [r10-1]
0x1800373fa  mov     [rbp+870h+var_888], rcx
0x1800373fe  xorps   xmm1, xmm1
0x180037401  mov     [rbp+870h+var_7E0], rax
0x180037408  lea     rcx, aCn; "cn"
0x18003740f  mov     [rbp+870h+var_850], rcx
0x180037413  lea     rax, aServicednsname_0; "serviceDNSNameType"
0x18003741a  mov     [rbp+870h+var_7D0], rax
0x180037421  lea     rcx, [rbp+870h+var_8E0]
0x180037425  mov     [rbp+870h+var_840], rcx
0x180037429  lea     rax, [rbp+870h+var_898]
0x18003742d  mov     [rbp+870h+var_7C0], rax
0x180037434  lea     rcx, aObjectclass; "objectClass"
0x18003743b  mov     [rbp+870h+var_830], rcx
0x18003743f  lea     rax, aServiceclassna; "serviceClassName"
0x180037446  mov     [rbp+870h+var_7B0], rax
0x18003744d  lea     rcx, [rbp+870h+var_8C8]
0x180037451  mov     [rbp+870h+var_820], rcx
0x180037455  lea     rax, [rbp+870h+var_880]
0x180037459  mov     [rbp+870h+var_7A0], rax
0x180037460  lea     rcx, aKeywords; "keywords"
0x180037467  mov     [rbp+870h+var_810], rcx
0x18003746b  lea     rax, aServicebinding_0; "serviceBindingInformation"
0x180037472  lea     rcx, [rbp+870h+var_770]
0x180037479  mov     [rbp+870h+var_790], rax
0x180037480  lea     rax, [rbp+870h+var_868]
0x180037484  mov     [rbp+870h+var_800], rcx
0x180037488  xor     ecx, ecx; pvReserved
0x18003748a  mov     [rbp+870h+var_780], rax
0x180037491  mov     [rbp+870h+hKey], rdx
0x180037495  mov     [rsp+970h+dwDisposition], edx
0x180037499  movups  [rbp+870h+var_8E0], xmm0
0x18003749d  mov     [rbp+870h+var_848], r10d
0x1800374a1  movups  [rbp+870h+var_8C8], xmm1
0x1800374a5  mov     [rbp+870h+var_844], r8d
0x1800374a9  movups  [rbp+870h+var_868], xmm0
0x1800374ad  mov     [rbp+870h+var_838], r9d
0x1800374b1  movups  [rbp+870h+var_880], xmm1
0x1800374b5  mov     [rbp+870h+var_828], r10d
0x1800374b9  movups  [rbp+870h+var_8B0], xmm0
0x1800374bd  mov     [rbp+870h+var_824], r8d
0x1800374c1  movups  [rbp+870h+var_898], xmm1
0x1800374c5  mov     [rbp+870h+var_818], r9d
0x1800374c9  mov     [rbp+870h+var_808], r10d
0x1800374cd  mov     [rbp+870h+var_804], r8d
0x1800374d1  mov     [rbp+870h+var_7E8], r10d
0x1800374d8  mov     [rbp+870h+var_7E4], r8d
0x1800374df  mov     [rbp+870h+var_7D8], r9d
0x1800374e6  mov     [rbp+870h+var_7C8], r10d
0x1800374ed  mov     [rbp+870h+var_7C4], r8d
0x1800374f4  mov     [rbp+870h+var_7B8], r9d
0x1800374fb  mov     [rbp+870h+var_7A8], r10d
0x180037502  mov     [rbp+870h+var_7A4], r8d
0x180037509  mov     [rbp+870h+var_798], r9d
0x180037510  mov     [rbp+870h+var_788], r10d
0x180037517  mov     [rbp+870h+var_784], r8d
0x18003751e  mov     [rbp+870h+var_778], r9d
0x180037525  mov     [rbp+870h+bstrString], rdx
0x180037529  call    cs:__imp_CoInitializeEx
0x18003752f  mov     ebx, eax
0x180037531  test    eax, eax
0x180037533  js      short loc_1800375A6
0x180037535  mov     [rsp+970h+var_918], 1
0x18003753d  call    ?IsCurrentLocalSystem@@YAJXZ; IsCurrentLocalSystem(void)
0x180037542  test    eax, eax
0x180037544  jz      short loc_180037559
0x180037546  call    ?ImpersonateLocalSystem@@YAJXZ; ImpersonateLocalSystem(void)
0x18003754b  mov     ebx, eax
0x18003754d  test    eax, eax
0x18003754f  jnz     short loc_1800375A6
0x180037551  mov     [rsp+970h+var_91C], 1
0x180037559  mov     ebx, 3
0x18003755e  mov     [rsp+970h+nSize], 104h
0x180037566  mov     ecx, ebx; NameType
0x180037568  lea     r8, [rsp+970h+nSize]; nSize
0x18003756d  lea     rdx, [rbp+870h+Buffer]; lpBuffer
0x180037574  call    cs:__imp_GetComputerNameExW
0x18003757a  test    eax, eax
0x18003757c  jnz     loc_180037663
0x180037582  call    cs:__imp_GetLastError
0x180037588  lea     r8, [rbp+870h+Buffer]
0x18003758f  mov     ecx, 10002h
0x180037594  mov     ebx, eax
0x180037596  lea     rdx, aGetcomputernam; "GetComputerNameEx: %ls\n"
0x18003759d  bts     ebx, 1Ch
0x1800375a1  call    TRACELogPrint
0x1800375a6  xor     esi, esi
0x1800375a8  mov     rcx, [rsp+970h+var_8F8]
0x1800375ad  test    rcx, rcx
0x1800375b0  jz      short loc_1800375BE
0x1800375b2  mov     rax, [rcx]
0x1800375b5  mov     rax, [rax+10h]
0x1800375b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375be  mov     rcx, [rsp+970h+var_910]
0x1800375c3  test    rcx, rcx
0x1800375c6  jz      short loc_1800375D4
0x1800375c8  mov     rax, [rcx]
0x1800375cb  mov     rax, [rax+10h]
0x1800375cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375d4  mov     rcx, [rbp+870h+hKey]; hKey
0x1800375d8  test    rcx, rcx
0x1800375db  jz      short loc_1800375E3
0x1800375dd  call    cs:__imp_RegCloseKey
0x1800375e3  mov     rcx, [rbp+870h+bstrString]; bstrString
0x1800375e7  test    rcx, rcx
0x1800375ea  jz      short loc_1800375F2
0x1800375ec  call    cs:__imp_SysFreeString
0x1800375f2  mov     rcx, [rsp+970h+ppObject]
0x1800375f7  test    rcx, rcx
0x1800375fa  jz      short loc_180037620
0x1800375fc  test    ebx, ebx
0x1800375fe  jns     short loc_180037614
0x180037600  mov     rax, [rcx]
0x180037603  mov     rdx, r13
0x180037606  mov     rax, [rax+38h]
0x18003760a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003760f  mov     rcx, [rsp+970h+ppObject]
0x180037614  mov     rax, [rcx]
0x180037617  mov     rax, [rax+10h]
0x18003761b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037620  cmp     [rsp+970h+var_91C], esi
0x180037624  jz      short loc_18003762B
0x180037626  call    ?RevertLocalSystemImp@@YAJXZ; RevertLocalSystemImp(void)
0x18003762b  cmp     [rsp+970h+var_918], esi
0x18003762f  jz      short loc_180037637
0x180037631  call    cs:__imp_CoUninitialize
0x180037637  mov     eax, ebx
0x180037639  mov     rcx, [rbp+870h+var_40]
0x180037640  xor     rcx, rsp; StackCookie
0x180037643  call    __security_check_cookie
0x180037648  mov     rbx, [rsp+970h+arg_18]
0x180037650  add     rsp, 940h
0x180037657  pop     r15
0x180037659  pop     r14
0x18003765b  pop     r13
0x18003765d  pop     r12
0x18003765f  pop     rdi
0x180037660  pop     rsi
0x180037661  pop     rbp
0x180037662  retn
0x180037663  lea     rax, [r13+6]
0x180037667  mov     [rbp+870h+var_750], r12
0x18003766e  mov     qword ptr [rbp+870h+var_8E0+8], rax
0x180037672  lea     r8, [rsp+970h+nSize]; nSize
0x180037677  lea     rax, aServiceconnect; "serviceConnectionPoint"
0x18003767e  mov     dword ptr [rbp+870h+var_8E0], ebx
0x180037681  mov     qword ptr [rbp+870h+var_8C8+8], rax
0x180037685  lea     rdx, [rbp+870h+NameBuffer]; lpNameBuffer
0x18003768c  lea     rax, a937924b8Aa4411; "937924B8-AA44-11d2-81F1-00C04FB9624E"
0x180037693  mov     dword ptr [rbp+870h+var_8C8], ebx
0x180037696  mov     [rbp+870h+var_768], rax
0x18003769d  mov     r12d, 1
0x1800376a3  lea     rax, aMicrosoft; "Microsoft"
0x1800376aa  mov     [rbp+870h+var_770], ebx
0x1800376b0  mov     [rbp+870h+var_738], rax
0x1800376b7  mov     ecx, r12d; NameFormat
0x1800376ba  lea     rax, [rbp+870h+Buffer]
0x1800376c1  mov     [rbp+870h+var_758], ebx
0x1800376c7  mov     qword ptr [rbp+870h+var_8B0+8], rax
0x1800376cb  lea     rax, aA; "A"
0x1800376d2  mov     qword ptr [rbp+870h+var_898+8], rax
0x1800376d6  mov     rax, [rbp+870h+arg_20]
0x1800376dd  mov     qword ptr [rbp+870h+var_868+8], rax
0x1800376e1  mov     [rbp+870h+var_740], ebx
0x1800376e7  mov     [rbp+870h+var_728], ebx
0x1800376ed  mov     [rbp+870h+var_710], ebx
0x1800376f3  mov     [rbp+870h+var_720], rsi
0x1800376fa  mov     [rbp+870h+var_708], rdi
0x180037701  mov     dword ptr [rbp+870h+var_8B0], ebx
0x180037704  mov     dword ptr [rbp+870h+var_898], ebx
0x180037707  mov     dword ptr [rbp+870h+var_880], ebx
0x18003770a  mov     qword ptr [rbp+870h+var_880+8], rsi
0x18003770e  mov     dword ptr [rbp+870h+var_868], ebx
0x180037711  mov     [rsp+970h+nSize], 104h
0x180037719  call    cs:__imp_GetComputerObjectNameW
0x18003771f  xor     esi, esi
0x180037721  test    al, al
0x180037723  jnz     short loc_18003774E
0x180037725  call    cs:__imp_GetLastError
0x18003772b  lea     r8, [rbp+870h+NameBuffer]
0x180037732  mov     ecx, 10002h
0x180037737  mov     ebx, eax
0x180037739  lea     rdx, aGetcomputerobj_0; "GetComputerObjectName: %ls\n"
0x180037740  bts     ebx, 1Ch
0x180037744  call    TRACELogPrint
0x180037749  jmp     loc_1800375A8
0x18003774e  mov     r11d, 208h
0x180037754  lea     r8, aLdap; "LDAP://"
0x18003775b  mov     edx, r11d; cbDest
0x18003775e  lea     rcx, [rbp+870h+pszDest]; pszDest
0x180037765  call    StringCbCopyW
0x18003776a  mov     ebx, eax
0x18003776c  test    eax, eax
0x18003776e  js      loc_180037A3B
0x180037774  lea     r8, [rbp+870h+NameBuffer]; pszSrc
0x18003777b  mov     edx, r11d; cbDest
0x18003777e  lea     rcx, [rbp+870h+pszDest]; pszDest
0x180037785  call    StringCbCatW
0x18003778a  mov     ebx, eax
0x18003778c  test    eax, eax
0x18003778e  js      loc_180037A3B
0x180037794  lea     r8, [rsp+970h+ppObject]; ppObject
0x180037799  lea     rdx, IID_IDirectoryObject; riid
0x1800377a0  lea     rcx, [rbp+870h+pszDest]; lpszPathName
0x1800377a7  call    cs:__imp_ADsGetObject
0x1800377ad  mov     ebx, eax
0x1800377af  test    eax, eax
0x1800377b1  js      loc_180037A3B
0x1800377b7  mov     rcx, [rsp+970h+ppObject]
0x1800377bc  lea     rdx, [rsp+970h+var_8F8]
0x1800377c1  mov     qword ptr [rsp+970h+dwOptions], rdx
0x1800377c6  lea     r8, [rbp+870h+var_850]
0x1800377ca  mov     r9d, 7
0x1800377d0  mov     rdx, r13
0x1800377d3  mov     rax, [rcx]
0x1800377d6  mov     rax, [rax+30h]
0x1800377da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377df  mov     ebx, eax
0x1800377e1  test    eax, eax
0x1800377e3  jns     short loc_18003780E
0x1800377e5  mov     r8d, eax
0x1800377e8  lea     rdx, aFailedToCreate_0; "Failed to create SCP: 0x%x\n"
0x1800377ef  mov     ecx, 10002h
0x1800377f4  call    TRACELogPrint
0x1800377f9  cmp     bx, 1392h
0x1800377fe  jnz     loc_1800375A8
0x180037804  mov     ebx, 0FFFFFFEAh
0x180037809  jmp     loc_1800375A8
0x18003780e  mov     rcx, [rsp+970h+var_8F8]
0x180037813  lea     r8, [rsp+970h+var_910]
0x180037818  lea     rdx, IID_IADs
0x18003781f  mov     rax, [rcx]
0x180037822  mov     rax, [rax]
0x180037825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003782a  mov     ebx, eax
0x18003782c  test    eax, eax
0x18003782e  jns     short loc_180037849
0x180037830  lea     rdx, aFailedToQiForI; "Failed to QI for IADs: 0x%x\n"
0x180037837  mov     r8d, eax
0x18003783a  mov     ecx, 10002h
0x18003783f  call    TRACELogPrint
0x180037844  jmp     loc_1800375A8
0x180037849  mov     rcx, [rsp+970h+var_910]; struct IADs *
0x18003784e  call    ?AllowAccessToScpProperties@@YAJPEAUIADs@@@Z; AllowAccessToScpProperties(IADs *)
0x180037853  mov     ebx, eax
0x180037855  test    eax, eax
0x180037857  jns     short loc_180037862
0x180037859  lea     rdx, aFailedToSetAce; "Failed to set ACEs on SCP DACL: 0x%x\n"
0x180037860  jmp     short loc_180037837
0x180037862  mov     rcx, [rsp+970h+var_910]
0x180037867  lea     rdx, [rbp+870h+bstrString]
0x18003786b  mov     rax, [rcx]
0x18003786e  mov     rax, [rax+48h]
0x180037872  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
