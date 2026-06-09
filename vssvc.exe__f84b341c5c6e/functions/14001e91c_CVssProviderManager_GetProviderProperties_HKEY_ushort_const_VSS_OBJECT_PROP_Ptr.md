# CVssProviderManager::GetProviderProperties(HKEY__ *,ushort const *,VSS_OBJECT_PROP_Ptr &)

- ea: `0x14001e91c`
- end: `0x14001f069`
- name: `?GetProviderProperties@CVssProviderManager@@CAJPEAUHKEY__@@PEBGAEAVVSS_OBJECT_PROP_Ptr@@@Z`
- size: `1869`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, struct VSS_OBJECT_PROP_Ptr *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007250`

## callees

- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x14001e49c`
- `0x14001e91c`
- `0x14001f070`
- `0x14001f334`
- `0x140049ec4`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ef40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001efc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ef40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001efc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ea21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ec42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ea21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ec42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ef32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001efb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ef32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001efb9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001e9ec`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001ec09`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001ed15`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001e9ec`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001ec09`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14001ed15`

## string_xrefs

- `0x14001ec36`: `CLSID`
- `0x14001ecde`: `CLSID`
- `0x14001ea8a`: `RegOpenKeyExW(hKeyProviders,%s,KEY_READ,...)`
- `0x14001ecae`: `CLSIDFromString(%s)`
- `0x14001ee0b`: `CLSIDFromString(%s)`
- `0x14001ee7c`: `CLSIDFromString(%s)`
- `0x14001eee9`: `CLSIDFromString(%s)`
- `0x14001f01a`: `Error closing the hKeyCLSID key. [0x%08lx]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssProviderManager::GetProviderProperties(
        HKEY a1,
        const unsigned __int16 *a2,
        struct VSS_OBJECT_PROP_Ptr *a3)
{
  HRESULT v3; // eax
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // r9
  HRESULT v8; // ebx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  HRESULT v11; // ebx
  LSTATUS v12; // eax
  DWORD LastError; // ebx
  LSTATUS v14; // eax
  DWORD v15; // ebx
  unsigned int v16; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-A18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A18h]
  unsigned int phkResultc; // [rsp+20h] [rbp-A18h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A18h]
  enum _VSS_PROVIDER_TYPE lpsza; // [rsp+48h] [rbp-9F0h]
  HKEY v25; // [rsp+50h] [rbp-9E8h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-9E0h] BYREF
  const unsigned __int16 *v27; // [rsp+60h] [rbp-9D8h] BYREF
  const unsigned __int16 *v28; // [rsp+68h] [rbp-9D0h]
  const unsigned __int16 *v29; // [rsp+70h] [rbp-9C8h]
  int v30; // [rsp+78h] [rbp-9C0h]
  int v31; // [rsp+7Ch] [rbp-9BCh]
  int v32; // [rsp+80h] [rbp-9B8h]
  _BYTE v33[120]; // [rsp+88h] [rbp-9B0h] BYREF
  int v34; // [rsp+100h] [rbp-938h]
  HKEY v35; // [rsp+108h] [rbp-930h] BYREF
  LPVOID v36; // [rsp+110h] [rbp-928h] BYREF
  unsigned int v37; // [rsp+118h] [rbp-920h]
  unsigned int v38; // [rsp+134h] [rbp-904h]
  int v39; // [rsp+180h] [rbp-8B8h] BYREF
  HKEY hKey[2]; // [rsp+190h] [rbp-8A8h] BYREF
  _com_error *v41; // [rsp+1A0h] [rbp-898h] BYREF
  const std::exception *v42; // [rsp+1A8h] [rbp-890h] BYREF
  struct _GUID v43; // [rsp+1B0h] [rbp-888h] BYREF
  struct _GUID v44; // [rsp+1C0h] [rbp-878h] BYREF
  GUID v45; // [rsp+1D0h] [rbp-868h] BYREF
  GUID v46; // [rsp+1E0h] [rbp-858h] BYREF
  GUID pclsid; // [rsp+1F0h] [rbp-848h] BYREF
  OLECHAR sz[256]; // [rsp+200h] [rbp-838h] BYREF
  OLECHAR v49[256]; // [rsp+400h] [rbp-638h] BYREF
  unsigned __int16 v50[256]; // [rsp+600h] [rbp-438h] BYREF
  unsigned __int16 v51[256]; // [rsp+800h] [rbp-238h] BYREF

  hKey[0] = a1;
  v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v28 = L"CVssProviderManager::GetProviderProperties";
  v29 = L"CORPRVMC";
  v30 = 1405;
  v31 = 1;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v36, (__int64)&v27, 0);
  v25 = 0;
  v35 = 0;
  pclsid = 0;
  v3 = CLSIDFromString(a2, &pclsid);
  try
  {
    v37 = v3;
    if ( v3 < 0 )
    {
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v28 = L"CVssProviderManager::GetProviderProperties";
      v29 = L"CORPRVMC";
      v30 = 1421;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::TranslateGenericError(&v36, &v27, v37, L"CLSIDFromString(%s)", a2);
    }
    v4 = RegOpenKeyExW(hKey[0], a2, 0, 0x20019u, &v25);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v28 = L"CVssProviderManager::GetProviderProperties";
      v29 = L"CORPRVMC";
      v30 = 1432;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::TranslateGenericError(&v36, &v27, v5, L"RegOpenKeyExW(hKeyProviders,%s,KEY_READ,...)", a2);
    }
    v6 = a2;
    QueryStringValue((struct CVssFunctionTracer *)&v36, v25, a2, &dword_1400FB76C, phkResult, v51);
    v26 = 0;
    QueryDWORDValue((struct CVssFunctionTracer *)&v36, v25, a2, v7, &v26);
    lpsza = v26;
    if ( v26 != 1 && v26 != 2 && v26 - 3 >= 2 )
    {
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v28 = L"CVssProviderManager::GetProviderProperties";
      v29 = L"CORPRVMC";
      v30 = 1465;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::TranslateGenericError(
        &v36,
        &v27,
        0,
        L"QueryDWORDValue(hProvider,%s,%s,%d)",
        v6,
        L"Type",
        lpsza);
    }
    QueryStringValue((struct CVssFunctionTracer *)&v36, v25, v6, L"Version", phkResulta, v50);
    QueryStringValue((struct CVssFunctionTracer *)&v36, v25, v6, L"VersionId", phkResultc, sz);
    v46 = 0;
    v8 = CLSIDFromString(sz, &v46);
    v37 = v8;
    if ( v8 < 0 )
    {
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v28 = L"CVssProviderManager::GetProviderProperties";
      v29 = L"CORPRVMC";
      v30 = 1497;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::TranslateGenericError(&v36, &v27, (unsigned int)v8, L"CLSIDFromString(%s)", sz);
    }
    v9 = RegOpenKeyExW(v25, L"CLSID", 0, 0x20019u, &v35);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v28 = L"CVssProviderManager::GetProviderProperties";
      v29 = L"CORPRVMC";
      v30 = 1509;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::TranslateGenericError(&v36, &v27, v10, L"CLSIDFromString(%s)", sz);
    }
    QueryStringValue((struct CVssFunctionTracer *)&v36, v35, L"CLSID", &qword_1400FB798, phkResultb, v49);
    v45 = 0;
    v11 = CLSIDFromString(v49, &v45);
    v37 = v11;
    if ( v11 < 0 )
    {
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v28 = L"CVssProviderManager::GetProviderProperties";
      v29 = L"CORPRVMC";
      v30 = 1528;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::TranslateGenericError(&v36, &v27, (unsigned int)v11, L"CLSIDFromString(%s)", v49);
    }
    *(GUID *)hKey = v45;
    v43 = v46;
    v44 = pclsid;
    VSS_OBJECT_PROP_Ptr::InitializeAsProvider(
      a3,
      (struct CVssFunctionTracer *)&v36,
      &v44,
      v51,
      lpsza,
      v50,
      &v43,
      (struct _GUID *)hKey);
  }
  catch ( long v39 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v36,
      v39,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::GetProviderProperties",
      0x604u,
      v38);
  }
  catch ( _com_error *v41 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v36,
      v41,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::GetProviderProperties",
      0x604u,
      v38);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v36,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::GetProviderProperties",
      0x604u,
      v38);
  }
  catch ( const std::exception *v42 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v36,
      v42,
      L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx",
      L"CORPRVMC",
      L"CVssProviderManager::GetProviderProperties",
      0x604u,
      v38);
  }
  if ( v25 )
    v12 = RegCloseKey(v25);
  else
    v12 = 0;
  if ( v12 )
  {
    LastError = GetLastError();
    v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v28 = L"CVssProviderManager::GetProviderProperties";
    v29 = L"CORPRVMC";
    v30 = 1545;
    v31 = 1;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Trace(&v36, &v27, L"Error closing the hKeyProvider key. [0x%08lx]", LastError);
  }
  if ( v35 )
    v14 = RegCloseKey(v35);
  else
    v14 = 0;
  if ( v14 )
  {
    v15 = GetLastError();
    v27 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v28 = L"CVssProviderManager::GetProviderProperties";
    v29 = L"CORPRVMC";
    v30 = 1549;
    v31 = 1;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Trace(&v36, &v27, L"Error closing the hKeyCLSID key. [0x%08lx]", v15);
  }
  v16 = v37;
  CVssFunctionTracer::~CVssFunctionTracer(&v36);
  return v16;
}

```

## disassembly

```asm
0x14001e91c  push    rbx
0x14001e91e  push    rdi
0x14001e91f  push    r12
0x14001e921  push    r14
0x14001e923  push    r15
0x14001e925  sub     rsp, 0A10h
0x14001e92c  mov     rax, cs:__security_cookie
0x14001e933  xor     rax, rsp
0x14001e936  mov     [rsp+0A38h+var_38], rax
0x14001e93e  mov     [rsp+0A38h+var_9F8], r8
0x14001e943  mov     [rsp+0A38h+lpsz], rdx
0x14001e948  mov     [rsp+0A38h+hKey], rcx
0x14001e950  lea     r14, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x14001e957  mov     [rsp+0A38h+var_9D8], r14
0x14001e95c  lea     r15, aCvssproviderma_8; "CVssProviderManager::GetProviderPropert"...
0x14001e963  mov     [rsp+0A38h+var_9D0], r15
0x14001e968  lea     r12, aCorprvmc; "CORPRVMC"
0x14001e96f  mov     [rsp+0A38h+var_9C8], r12
0x14001e974  mov     [rsp+0A38h+var_9C0], 57Dh
0x14001e97c  mov     [rsp+0A38h+var_9BC], 1
0x14001e984  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001e98f  xor     edi, edi
0x14001e991  mov     [rsp+0A38h+var_938], 1000000h
0x14001e99c  lea     ebx, [rdi+78h]
0x14001e99f  mov     r8d, ebx; Size
0x14001e9a2  xor     edx, edx; Val
0x14001e9a4  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001e9ac  call    memset_0
0x14001e9b1  xor     r8d, r8d
0x14001e9b4  lea     rdx, [rsp+0A38h+var_9D8]
0x14001e9b9  lea     rcx, [rsp+0A38h+var_928]
0x14001e9c1  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14001e9c6  nop
0x14001e9c7  mov     [rsp+0A38h+var_9E8], rdi
0x14001e9cc  mov     [rsp+0A38h+var_930], rdi
0x14001e9d4  xorps   xmm0, xmm0
0x14001e9d7  movups  xmmword ptr [rsp+0A38h+pclsid.Data1], xmm0
0x14001e9df  lea     rdx, [rsp+0A38h+pclsid]; pclsid
0x14001e9e7  mov     rcx, [rsp+0A38h+lpsz]; lpsz
0x14001e9ec  call    cs:__imp_CLSIDFromString
0x14001e9f2  mov     [rsp+0A38h+var_920], eax
0x14001e9f9  test    eax, eax
0x14001e9fb  js      loc_14001EE98
0x14001ea01  lea     rax, [rsp+0A38h+var_9E8]
0x14001ea06  mov     [rsp+0A38h+phkResult], rax; unsigned int
0x14001ea0b  mov     r9d, 20019h; samDesired
0x14001ea11  xor     r8d, r8d; ulOptions
0x14001ea14  mov     rdx, [rsp+0A38h+lpsz]; lpSubKey
0x14001ea19  mov     rcx, [rsp+0A38h+hKey]; hKey
0x14001ea21  call    cs:__imp_RegOpenKeyExW
0x14001ea27  mov     ebx, eax
0x14001ea29  test    eax, eax
0x14001ea2b  jz      short loc_14001EAA6
0x14001ea2d  jle     short loc_14001EA38
0x14001ea2f  movzx   ebx, ax
0x14001ea32  or      ebx, 80070000h
0x14001ea38  mov     [rsp+0A38h+var_9D8], r14
0x14001ea3d  mov     [rsp+0A38h+var_9D0], r15
0x14001ea42  mov     [rsp+0A38h+var_9C8], r12
0x14001ea47  mov     [rsp+0A38h+var_9C0], 598h
0x14001ea4f  mov     [rsp+0A38h+var_9BC], 1
0x14001ea57  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001ea62  mov     [rsp+0A38h+var_938], 1000000h
0x14001ea6d  xor     edx, edx; Val
0x14001ea6f  lea     r8d, [rdx+78h]; Size
0x14001ea73  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001ea7b  call    memset_0
0x14001ea80  mov     rax, [rsp+0A38h+lpsz]
0x14001ea85  mov     [rsp+0A38h+phkResult], rax
0x14001ea8a  lea     r9, aRegopenkeyexwH_0; "RegOpenKeyExW(hKeyProviders,%s,KEY_READ"...
0x14001ea91  mov     r8d, ebx
0x14001ea94  lea     rdx, [rsp+0A38h+var_9D8]
0x14001ea99  lea     rcx, [rsp+0A38h+var_928]
0x14001eaa1  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001eaa6  lea     rax, [rsp+0A38h+var_238]
0x14001eaae  mov     [rsp+0A38h+var_A10], rax; unsigned __int16 *
0x14001eab3  lea     r9, dword_1400FB76C; unsigned __int16 *
0x14001eaba  mov     rbx, [rsp+0A38h+lpsz]
0x14001eabf  mov     r8, rbx; unsigned __int16 *
0x14001eac2  mov     rdx, [rsp+0A38h+var_9E8]; HKEY
0x14001eac7  lea     rcx, [rsp+0A38h+var_928]; struct CVssFunctionTracer *
0x14001eacf  call    ?QueryStringValue@@YAXAEAVCVssFunctionTracer@@PEAUHKEY__@@PEBG2K2@Z; QueryStringValue(CVssFunctionTracer &,HKEY__ *,ushort const *,ushort const *,ulong,ushort const *)
0x14001ead4  mov     [rsp+0A38h+var_9E0], edi
0x14001ead8  lea     rax, [rsp+0A38h+var_9E0]
0x14001eadd  mov     [rsp+0A38h+phkResult], rax; unsigned int
0x14001eae2  mov     r8, rbx; unsigned __int16 *
0x14001eae5  mov     rdx, [rsp+0A38h+var_9E8]; HKEY
0x14001eaea  lea     rcx, [rsp+0A38h+var_928]; struct CVssFunctionTracer *
0x14001eaf2  call    ?QueryDWORDValue@@YAXAEAVCVssFunctionTracer@@PEAUHKEY__@@PEBG2PEAK@Z; QueryDWORDValue(CVssFunctionTracer &,HKEY__ *,ushort const *,ushort const *,ulong *)
0x14001eaf7  mov     eax, [rsp+0A38h+var_9E0]
0x14001eafb  mov     dword ptr [rsp+0A38h+lpsz], eax
0x14001eaff  sub     eax, 1
0x14001eb02  jz      loc_14001EB9C
0x14001eb08  sub     eax, 1
0x14001eb0b  jz      loc_14001EB9C
0x14001eb11  sub     eax, 1
0x14001eb14  jz      loc_14001EB9C
0x14001eb1a  cmp     eax, 1
0x14001eb1d  jz      short loc_14001EB9C
0x14001eb1f  mov     [rsp+0A38h+var_9D8], r14
0x14001eb24  mov     [rsp+0A38h+var_9D0], r15
0x14001eb29  mov     [rsp+0A38h+var_9C8], r12
0x14001eb2e  mov     [rsp+0A38h+var_9C0], 5B9h
0x14001eb36  mov     [rsp+0A38h+var_9BC], 1
0x14001eb3e  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001eb49  mov     [rsp+0A38h+var_938], 1000000h
0x14001eb54  xor     edx, edx; Val
0x14001eb56  lea     r8d, [rdx+78h]; Size
0x14001eb5a  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001eb62  call    memset_0
0x14001eb67  mov     eax, dword ptr [rsp+0A38h+lpsz]
0x14001eb6b  mov     dword ptr [rsp+0A38h+var_A08], eax
0x14001eb6f  lea     rax, ValueName; "Type"
0x14001eb76  mov     [rsp+0A38h+var_A10], rax
0x14001eb7b  mov     [rsp+0A38h+phkResult], rbx
0x14001eb80  lea     r9, aQuerydwordvalu_0; "QueryDWORDValue(hProvider,%s,%s,%d)"
0x14001eb87  xor     r8d, r8d
0x14001eb8a  lea     rdx, [rsp+0A38h+var_9D8]
0x14001eb8f  lea     rcx, [rsp+0A38h+var_928]
0x14001eb97  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001eb9c  lea     rax, [rsp+0A38h+var_438]
0x14001eba4  mov     [rsp+0A38h+var_A10], rax; unsigned __int16 *
0x14001eba9  lea     r9, aVersion_0; "Version"
0x14001ebb0  mov     r8, rbx; unsigned __int16 *
0x14001ebb3  mov     rdx, [rsp+0A38h+var_9E8]; HKEY
0x14001ebb8  lea     rcx, [rsp+0A38h+var_928]; struct CVssFunctionTracer *
0x14001ebc0  call    ?QueryStringValue@@YAXAEAVCVssFunctionTracer@@PEAUHKEY__@@PEBG2K2@Z; QueryStringValue(CVssFunctionTracer &,HKEY__ *,ushort const *,ushort const *,ulong,ushort const *)
0x14001ebc5  lea     rax, [rsp+0A38h+sz]
0x14001ebcd  mov     [rsp+0A38h+var_A10], rax; unsigned __int16 *
0x14001ebd2  lea     r9, aVersionid; "VersionId"
0x14001ebd9  mov     r8, rbx; unsigned __int16 *
0x14001ebdc  mov     rdx, [rsp+0A38h+var_9E8]; HKEY
0x14001ebe1  lea     rcx, [rsp+0A38h+var_928]; struct CVssFunctionTracer *
0x14001ebe9  call    ?QueryStringValue@@YAXAEAVCVssFunctionTracer@@PEAUHKEY__@@PEBG2K2@Z; QueryStringValue(CVssFunctionTracer &,HKEY__ *,ushort const *,ushort const *,ulong,ushort const *)
0x14001ebee  xorps   xmm0, xmm0
0x14001ebf1  movups  xmmword ptr [rsp+0A38h+var_858.Data1], xmm0
0x14001ebf9  lea     rdx, [rsp+0A38h+var_858]; pclsid
0x14001ec01  lea     rcx, [rsp+0A38h+sz]; lpsz
0x14001ec09  call    cs:__imp_CLSIDFromString
0x14001ec0f  mov     ebx, eax
0x14001ec11  mov     [rsp+0A38h+var_920], eax
0x14001ec18  test    eax, eax
0x14001ec1a  js      loc_14001EE27
0x14001ec20  lea     rax, [rsp+0A38h+var_930]
0x14001ec28  mov     [rsp+0A38h+phkResult], rax; unsigned int
0x14001ec2d  mov     r9d, 20019h; samDesired
0x14001ec33  xor     r8d, r8d; ulOptions
0x14001ec36  lea     rdx, SubKey; "CLSID"
0x14001ec3d  mov     rcx, [rsp+0A38h+var_9E8]; hKey
0x14001ec42  call    cs:__imp_RegOpenKeyExW
0x14001ec48  mov     ebx, eax
0x14001ec4a  test    eax, eax
0x14001ec4c  jz      short loc_14001ECCA
0x14001ec4e  jle     short loc_14001EC59
0x14001ec50  movzx   ebx, ax
0x14001ec53  or      ebx, 80070000h
0x14001ec59  mov     [rsp+0A38h+var_9D8], r14
0x14001ec5e  mov     [rsp+0A38h+var_9D0], r15
0x14001ec63  mov     [rsp+0A38h+var_9C8], r12
0x14001ec68  mov     [rsp+0A38h+var_9C0], 5E5h
0x14001ec70  mov     [rsp+0A38h+var_9BC], 1
0x14001ec78  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001ec83  mov     [rsp+0A38h+var_938], 1000000h
0x14001ec8e  xor     edx, edx; Val
0x14001ec90  lea     r8d, [rdx+78h]; Size
0x14001ec94  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001ec9c  call    memset_0
0x14001eca1  lea     rax, [rsp+0A38h+sz]
0x14001eca9  mov     [rsp+0A38h+phkResult], rax
0x14001ecae  lea     r9, aClsidfromstrin_0; "CLSIDFromString(%s)"
0x14001ecb5  mov     r8d, ebx
0x14001ecb8  lea     rdx, [rsp+0A38h+var_9D8]
0x14001ecbd  lea     rcx, [rsp+0A38h+var_928]
0x14001ecc5  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001ecca  lea     rax, [rsp+0A38h+var_638]
0x14001ecd2  mov     [rsp+0A38h+var_A10], rax; unsigned __int16 *
0x14001ecd7  lea     r9, qword_1400FB798; unsigned __int16 *
0x14001ecde  lea     r8, SubKey; "CLSID"
0x14001ece5  mov     rdx, [rsp+0A38h+var_930]; HKEY
0x14001eced  lea     rcx, [rsp+0A38h+var_928]; struct CVssFunctionTracer *
0x14001ecf5  call    ?QueryStringValue@@YAXAEAVCVssFunctionTracer@@PEAUHKEY__@@PEBG2K2@Z; QueryStringValue(CVssFunctionTracer &,HKEY__ *,ushort const *,ushort const *,ulong,ushort const *)
0x14001ecfa  xorps   xmm0, xmm0
0x14001ecfd  movups  xmmword ptr [rsp+0A38h+var_868.Data1], xmm0
0x14001ed05  lea     rdx, [rsp+0A38h+var_868]; pclsid
0x14001ed0d  lea     rcx, [rsp+0A38h+var_638]; lpsz
0x14001ed15  call    cs:__imp_CLSIDFromString
0x14001ed1b  mov     ebx, eax
0x14001ed1d  mov     [rsp+0A38h+var_920], eax
0x14001ed24  test    eax, eax
0x14001ed26  js      loc_14001EDB6
0x14001ed2c  movaps  xmm0, xmmword ptr [rsp+0A38h+var_868.Data1]
0x14001ed34  movdqa  xmmword ptr [rsp+0A38h+hKey], xmm0
0x14001ed3d  movaps  xmm1, xmmword ptr [rsp+0A38h+var_858.Data1]
0x14001ed45  movdqa  xmmword ptr [rsp+0A38h+var_888.Data1], xmm1
0x14001ed4e  movaps  xmm0, xmmword ptr [rsp+0A38h+pclsid.Data1]
0x14001ed56  movdqa  xmmword ptr [rsp+0A38h+var_878.Data1], xmm0
0x14001ed5f  lea     rax, [rsp+0A38h+hKey]
0x14001ed67  mov     [rsp+0A38h+var_A00], rax; struct _GUID *
0x14001ed6c  lea     rax, [rsp+0A38h+var_888]
0x14001ed74  mov     [rsp+0A38h+var_A08], rax; struct _GUID *
0x14001ed79  lea     rax, [rsp+0A38h+var_438]
0x14001ed81  mov     [rsp+0A38h+var_A10], rax; unsigned __int16 *
0x14001ed86  mov     eax, dword ptr [rsp+0A38h+lpsz]
0x14001ed8a  mov     dword ptr [rsp+0A38h+phkResult], eax; enum _VSS_PROVIDER_TYPE
0x14001ed8e  lea     r9, [rsp+0A38h+var_238]; unsigned __int16 *
0x14001ed96  lea     r8, [rsp+0A38h+var_878]; struct _GUID *
0x14001ed9e  lea     rdx, [rsp+0A38h+var_928]; struct CVssFunctionTracer *
0x14001eda6  mov     rcx, [rsp+0A38h+var_9F8]; this
0x14001edab  call    ?InitializeAsProvider@VSS_OBJECT_PROP_Ptr@@QEAAXAEAVCVssFunctionTracer@@U_GUID@@PEAGW4_VSS_PROVIDER_TYPE@@211@Z; VSS_OBJECT_PROP_Ptr::InitializeAsProvider(CVssFunctionTracer &,_GUID,ushort *,_VSS_PROVIDER_TYPE,ushort *,_GUID,_GUID)
0x14001edb0  nop
0x14001edb1  jmp     loc_14001EF28
0x14001edb6  mov     [rsp+0A38h+var_9D8], r14
0x14001edbb  mov     [rsp+0A38h+var_9D0], r15
0x14001edc0  mov     [rsp+0A38h+var_9C8], r12
0x14001edc5  mov     [rsp+0A38h+var_9C0], 5F8h
0x14001edcd  mov     [rsp+0A38h+var_9BC], 1
0x14001edd5  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001ede0  mov     [rsp+0A38h+var_938], 1000000h
0x14001edeb  xor     edx, edx; Val
0x14001eded  lea     r8d, [rdx+78h]; Size
0x14001edf1  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001edf9  call    memset_0
0x14001edfe  lea     rax, [rsp+0A38h+var_638]
0x14001ee06  mov     [rsp+0A38h+phkResult], rax
0x14001ee0b  lea     r9, aClsidfromstrin_0; "CLSIDFromString(%s)"
0x14001ee12  mov     r8d, ebx
0x14001ee15  lea     rdx, [rsp+0A38h+var_9D8]
0x14001ee1a  lea     rcx, [rsp+0A38h+var_928]
0x14001ee22  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001ee27  mov     [rsp+0A38h+var_9D8], r14
0x14001ee2c  mov     [rsp+0A38h+var_9D0], r15
0x14001ee31  mov     [rsp+0A38h+var_9C8], r12
0x14001ee36  mov     [rsp+0A38h+var_9C0], 5D9h
0x14001ee3e  mov     [rsp+0A38h+var_9BC], 1
0x14001ee46  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001ee51  mov     [rsp+0A38h+var_938], 1000000h
0x14001ee5c  xor     edx, edx; Val
0x14001ee5e  lea     r8d, [rdx+78h]; Size
0x14001ee62  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001ee6a  call    memset_0
0x14001ee6f  lea     rax, [rsp+0A38h+sz]
0x14001ee77  mov     [rsp+0A38h+phkResult], rax
0x14001ee7c  lea     r9, aClsidfromstrin_0; "CLSIDFromString(%s)"
0x14001ee83  mov     r8d, ebx
0x14001ee86  lea     rdx, [rsp+0A38h+var_9D8]
0x14001ee8b  lea     rcx, [rsp+0A38h+var_928]
0x14001ee93  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001ee98  mov     [rsp+0A38h+var_9D8], r14
0x14001ee9d  mov     [rsp+0A38h+var_9D0], r15
0x14001eea2  mov     [rsp+0A38h+var_9C8], r12
0x14001eea7  mov     [rsp+0A38h+var_9C0], 58Dh
0x14001eeaf  mov     [rsp+0A38h+var_9BC], 1
0x14001eeb7  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001eec2  mov     [rsp+0A38h+var_938], 1000000h
0x14001eecd  mov     r8, rbx; Size
0x14001eed0  xor     edx, edx; Val
0x14001eed2  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001eeda  call    memset_0
0x14001eedf  mov     rax, [rsp+0A38h+lpsz]
0x14001eee4  mov     [rsp+0A38h+phkResult], rax
0x14001eee9  lea     r9, aClsidfromstrin_0; "CLSIDFromString(%s)"
0x14001eef0  mov     r8d, [rsp+0A38h+var_920]
0x14001eef8  lea     rdx, [rsp+0A38h+var_9D8]
0x14001eefd  lea     rcx, [rsp+0A38h+var_928]
0x14001ef05  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14001ef0b  jmp     short loc_14001EF11
0x14001ef0d  jmp     short loc_14001EF11
0x14001ef0f  jmp     short $+2
0x14001ef11  xor     edi, edi
0x14001ef13  lea     r12, aCorprvmc; "CORPRVMC"
0x14001ef1a  lea     r15, aCvssproviderma_8; "CVssProviderManager::GetProviderPropert"...
0x14001ef21  lea     r14, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x14001ef28  mov     rcx, [rsp+0A38h+var_9E8]; hKey
0x14001ef2d  test    rcx, rcx
0x14001ef30  jz      short loc_14001EF3A
0x14001ef32  call    cs:__imp_RegCloseKey
0x14001ef38  jmp     short loc_14001EF3C
0x14001ef3a  mov     eax, edi
0x14001ef3c  test    eax, eax
0x14001ef3e  jz      short loc_14001EFAC
0x14001ef40  call    cs:__imp_GetLastError
0x14001ef46  mov     ebx, eax
0x14001ef48  mov     [rsp+0A38h+var_9D8], r14
0x14001ef4d  mov     [rsp+0A38h+var_9D0], r15
0x14001ef52  mov     [rsp+0A38h+var_9C8], r12
0x14001ef57  mov     [rsp+0A38h+var_9C0], 609h
0x14001ef5f  mov     [rsp+0A38h+var_9BC], 1
0x14001ef67  mov     [rsp+0A38h+var_9B8], 0FFh
0x14001ef72  mov     [rsp+0A38h+var_938], 1000000h
0x14001ef7d  xor     edx, edx; Val
0x14001ef7f  lea     r8d, [rdx+78h]; Size
0x14001ef83  lea     rcx, [rsp+0A38h+var_9B0]; void *
0x14001ef8b  call    memset_0
0x14001ef90  mov     r9d, ebx
0x14001ef93  lea     r8, aErrorClosingTh_4; "Error closing the hKeyProvider key. [0x"...
0x14001ef9a  lea     rdx, [rsp+0A38h+var_9D8]
0x14001ef9f  lea     rcx, [rsp+0A38h+var_928]
0x14001efa7  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14001efac  mov     rcx, [rsp+0A38h+var_930]; hKey
0x14001efb4  test    rcx, rcx
  ... truncated ...
```
