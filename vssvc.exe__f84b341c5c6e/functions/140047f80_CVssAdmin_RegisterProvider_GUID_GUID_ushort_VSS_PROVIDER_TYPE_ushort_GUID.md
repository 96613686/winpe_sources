# CVssAdmin::RegisterProvider(_GUID,_GUID,ushort *,_VSS_PROVIDER_TYPE,ushort *,_GUID)

- ea: `0x140047f80`
- end: `0x140049ebe`
- name: `?RegisterProvider@CVssAdmin@@MEAAJU_GUID@@0PEAGW4_VSS_PROVIDER_TYPE@@10@Z`
- size: `7998`
- prototype: `__int64 __fastcall(CVssAdmin *__hidden this, struct _GUID *, struct _GUID *, unsigned __int16 *, enum _VSS_PROVIDER_TYPE, unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x14000a834`
- `0x140010170`
- `0x140011440`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140016710`
- `0x140019760`
- `0x140019990`
- `0x140030230`
- `0x1400437b4`
- `0x140047cb0`
- `0x140047f80`
- `0x140049ec4`
- `0x140091560`
- `0x1400921dc`
- `0x14009df00`
- `0x1400da308`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049c21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140048fc2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400490e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140049209`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400493dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400496bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140048fc2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400490e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140049209`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400493dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400496bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049a56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049b7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049c12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049a56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049b7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049c12`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140048b4c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140048c33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140048dc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049507`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140048b4c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140048c33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140048dc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049507`

## string_xrefs

- `0x140048b3e`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140048bc2`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140048cb5`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140048e54`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140048f0d`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x14004907c`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140049196`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x1400492c3`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140049496`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x1400495a2`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140049781`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140049da3`: `SYSTEM\CurrentControlSet\Services\VSS`
- `0x140049088`: `RegSetValueExW(HKLM\%s\%s\%s,%s,0,REG_SZ,%s.%d)`
- `0x1400492cf`: `RegSetValueExW(HKLM\%s\%s\%s,%s,0,REG_SZ,%s.%d)`
- `0x1400494a2`: `RegSetValueExW(HKLM\%s\%s\%s,%s,0,REG_SZ,%s.%d)`
- `0x1400494f8`: `CLSID`
- `0x14004957d`: `CLSID`
- `0x14004975c`: `CLSID`
- `0x1400495ae`: `RegCreateKeyExW(HKLM\%s\%s\%s,%s,...)`
- `0x1400491a2`: `RegSetValueExW(HKLM\%s\%s\%s,%s,0,REG_DWORD,%d,%d)`
- `0x140048cc1`: `RegCreateKeyExW(HKLM\%s,%s,...)`
- `0x140048e60`: `RegCreateKeyExW(HKLM\%s\%s,%s,...)`
- `0x14004978d`: `RegSetValueExW(HKLM\%s\%s\%s\%s,%s,0,REG_SZ,%s.%d)`
- `0x1400484ca`: `Parameters: \nProviderId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x},\nClassId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x},\npwszProviderName = %s\neProviderType = %d\npwszProviderVersion = %s\nProviderVersionId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x},\n`
- `0x140048bce`: `RegCreateKeyExW(HKLM,%s,...)`
- `0x140048f55`: `Provider with Id %s already registered `
- `0x140048f19`: `RegCreateKeyExW(HKLM\%s\%s,%s,...,[%d])`
- `0x140049ac1`: `Error closing the hRegKeyCLSID key. [0x%08lx]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVssAdmin::RegisterProvider(
        CVssAdmin *this,
        struct _GUID *a2,
        struct _GUID *a3,
        BYTE *a4,
        enum _VSS_PROVIDER_TYPE a5,
        unsigned __int16 *a6,
        struct _GUID *a7)
{
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  __int64 v12; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rax
  LSTATUS v16; // eax
  __int64 v17; // rax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  __int64 v20; // rax
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  DWORD LastError; // ebx
  LSTATUS v24; // eax
  DWORD v25; // ebx
  LSTATUS v26; // eax
  DWORD v27; // ebx
  LSTATUS v28; // eax
  DWORD v29; // ebx
  HKEY v30; // rdx
  int v31; // ebx
  unsigned int v32; // ebx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-AA8h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-AA8h]
  DWORD dwOptionsb[2]; // [rsp+20h] [rbp-AA8h]
  DWORD dwOptionsc[2]; // [rsp+20h] [rbp-AA8h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-AA0h]
  REGSAM samDesireda[2]; // [rsp+28h] [rbp-AA0h]
  REGSAM samDesiredb[2]; // [rsp+28h] [rbp-AA0h]
  REGSAM samDesiredc[2]; // [rsp+28h] [rbp-AA0h]
  REGSAM samDesiredd[2]; // [rsp+28h] [rbp-AA0h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-A98h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesa; // [rsp+30h] [rbp-A98h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesb; // [rsp+30h] [rbp-A98h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesc; // [rsp+30h] [rbp-A98h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesd; // [rsp+30h] [rbp-A98h]
  PHKEY phkResult; // [rsp+38h] [rbp-A90h]
  PHKEY phkResulta; // [rsp+38h] [rbp-A90h]
  PHKEY phkResultb; // [rsp+38h] [rbp-A90h]
  PHKEY phkResultc; // [rsp+38h] [rbp-A90h]
  PHKEY phkResultd; // [rsp+38h] [rbp-A90h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-A88h]
  LPDWORD lpdwDispositiona; // [rsp+40h] [rbp-A88h]
  LPDWORD lpdwDispositionb; // [rsp+40h] [rbp-A88h]
  LPDWORD lpdwDispositionc; // [rsp+40h] [rbp-A88h]
  LPDWORD lpdwDispositiond; // [rsp+40h] [rbp-A88h]
  __int64 v58; // [rsp+48h] [rbp-A80h]
  __int64 v59; // [rsp+48h] [rbp-A80h]
  __int64 v60; // [rsp+48h] [rbp-A80h]
  __int64 v61; // [rsp+48h] [rbp-A80h]
  __int64 v62; // [rsp+48h] [rbp-A80h]
  __int64 v63; // [rsp+50h] [rbp-A78h]
  __int64 v64; // [rsp+50h] [rbp-A78h]
  __int64 v65; // [rsp+50h] [rbp-A78h]
  __int64 v66; // [rsp+50h] [rbp-A78h]
  __int64 v67; // [rsp+50h] [rbp-A78h]
  __int64 v68; // [rsp+58h] [rbp-A70h]
  __int64 v69; // [rsp+58h] [rbp-A70h]
  __int64 v70; // [rsp+58h] [rbp-A70h]
  __int64 v71; // [rsp+58h] [rbp-A70h]
  __int64 v72; // [rsp+58h] [rbp-A70h]
  __int64 v73; // [rsp+60h] [rbp-A68h]
  __int64 v74; // [rsp+60h] [rbp-A68h]
  __int64 v75; // [rsp+60h] [rbp-A68h]
  __int64 v76; // [rsp+60h] [rbp-A68h]
  __int64 v77; // [rsp+60h] [rbp-A68h]
  __int64 v78; // [rsp+68h] [rbp-A60h]
  __int64 v79; // [rsp+68h] [rbp-A60h]
  __int64 v80; // [rsp+68h] [rbp-A60h]
  __int64 v81; // [rsp+68h] [rbp-A60h]
  __int64 v82; // [rsp+68h] [rbp-A60h]
  __int64 v83; // [rsp+70h] [rbp-A58h]
  __int64 v84; // [rsp+70h] [rbp-A58h]
  __int64 v85; // [rsp+78h] [rbp-A50h]
  unsigned int v87; // [rsp+148h] [rbp-980h]
  unsigned int v88; // [rsp+148h] [rbp-980h]
  unsigned int v89; // [rsp+148h] [rbp-980h]
  unsigned int v90; // [rsp+148h] [rbp-980h]
  unsigned int v91; // [rsp+148h] [rbp-980h]
  unsigned int v92; // [rsp+148h] [rbp-980h]
  const unsigned __int16 *v93; // [rsp+150h] [rbp-978h] BYREF
  const unsigned __int16 *v94; // [rsp+158h] [rbp-970h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp-968h]
  int v96; // [rsp+168h] [rbp-960h]
  int v97; // [rsp+16Ch] [rbp-95Ch]
  int v98; // [rsp+170h] [rbp-958h]
  _BYTE v99[120]; // [rsp+178h] [rbp-950h] BYREF
  int v100; // [rsp+1F0h] [rbp-8D8h]
  unsigned int v101; // [rsp+200h] [rbp-8C8h]
  struct _GUID v102; // [rsp+210h] [rbp-8B8h] BYREF
  DWORD dwDisposition; // [rsp+220h] [rbp-8A8h] BYREF
  unsigned int v104; // [rsp+224h] [rbp-8A4h]
  void *Buf1; // [rsp+228h] [rbp-8A0h]
  int v106; // [rsp+230h] [rbp-898h]
  int v107; // [rsp+234h] [rbp-894h]
  int v108; // [rsp+238h] [rbp-890h]
  int v109; // [rsp+23Ch] [rbp-88Ch]
  int v110; // [rsp+240h] [rbp-888h]
  int v111; // [rsp+244h] [rbp-884h]
  int v112; // [rsp+248h] [rbp-880h]
  int v113; // [rsp+24Ch] [rbp-87Ch]
  REGSAM v114; // [rsp+250h] [rbp-878h]
  DWORD v115; // [rsp+254h] [rbp-874h]
  __int64 v116; // [rsp+258h] [rbp-870h]
  HKEY v117; // [rsp+260h] [rbp-868h] BYREF
  BYTE *v118; // [rsp+268h] [rbp-860h]
  BYTE *lpData; // [rsp+270h] [rbp-858h]
  int v120; // [rsp+278h] [rbp-850h]
  REGSAM v121; // [rsp+27Ch] [rbp-84Ch]
  int v122; // [rsp+280h] [rbp-848h]
  BYTE Data[4]; // [rsp+284h] [rbp-844h] BYREF
  int v124; // [rsp+288h] [rbp-840h]
  int v125; // [rsp+28Ch] [rbp-83Ch]
  int v126; // [rsp+290h] [rbp-838h]
  int v127; // [rsp+294h] [rbp-834h]
  int v128; // [rsp+298h] [rbp-830h]
  int v129; // [rsp+29Ch] [rbp-82Ch]
  int v130; // [rsp+2A0h] [rbp-828h]
  REGSAM v131; // [rsp+2A4h] [rbp-824h]
  int v132; // [rsp+2A8h] [rbp-820h]
  int v133; // [rsp+2ACh] [rbp-81Ch]
  int v134; // [rsp+2B0h] [rbp-818h]
  int v135; // [rsp+2B4h] [rbp-814h]
  int v136; // [rsp+2B8h] [rbp-810h]
  int v137; // [rsp+2BCh] [rbp-80Ch]
  int v138; // [rsp+2C0h] [rbp-808h]
  struct _GUID *v139; // [rsp+2C8h] [rbp-800h]
  HKEY hKey; // [rsp+2D0h] [rbp-7F8h] BYREF
  __int64 v141; // [rsp+2D8h] [rbp-7F0h]
  __int64 v142; // [rsp+2E0h] [rbp-7E8h]
  LPVOID v143; // [rsp+2F0h] [rbp-7D8h] BYREF
  int v144; // [rsp+2F8h] [rbp-7D0h]
  unsigned int v145; // [rsp+314h] [rbp-7B4h]
  HKEY v146; // [rsp+360h] [rbp-768h] BYREF
  HKEY v147; // [rsp+368h] [rbp-760h] BYREF
  struct _GUID v148; // [rsp+370h] [rbp-758h] BYREF
  struct _GUID *v149; // [rsp+380h] [rbp-748h]
  struct _GUID v150; // [rsp+390h] [rbp-738h] BYREF
  int v151; // [rsp+3A0h] [rbp-728h] BYREF
  int v152; // [rsp+3A4h] [rbp-724h] BYREF
  const unsigned __int16 *v153; // [rsp+3A8h] [rbp-720h] BYREF
  const unsigned __int16 *v154; // [rsp+3B0h] [rbp-718h]
  const unsigned __int16 *v155; // [rsp+3B8h] [rbp-710h]
  int v156; // [rsp+3C0h] [rbp-708h]
  int v157; // [rsp+3C4h] [rbp-704h]
  int v158; // [rsp+3C8h] [rbp-700h]
  _BYTE v159[120]; // [rsp+3D0h] [rbp-6F8h] BYREF
  int v160; // [rsp+448h] [rbp-680h]
  _com_error *v161; // [rsp+450h] [rbp-678h] BYREF
  const std::exception *v162; // [rsp+458h] [rbp-670h] BYREF
  const std::exception *v163; // [rsp+460h] [rbp-668h] BYREF
  _com_error *v164; // [rsp+468h] [rbp-660h] BYREF
  LPCRITICAL_SECTION v165[2]; // [rsp+470h] [rbp-658h] BYREF
  WCHAR SubKey[256]; // [rsp+480h] [rbp-648h] BYREF
  unsigned __int16 v167[256]; // [rsp+680h] [rbp-448h] BYREF
  unsigned __int16 v168[256]; // [rsp+880h] [rbp-248h] BYREF

  lpData = a4;
  *(_QWORD *)&v150.Data1 = a3;
  Buf1 = a2;
  v149 = a2;
  *(_QWORD *)&v148.Data1 = a7;
  v139 = a2;
  v118 = (BYTE *)a6;
  v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
  v94 = L"CVssAdmin::RegisterProvider";
  v95 = L"CORADMNC";
  v96 = 139;
  v97 = 1;
  v98 = 255;
  v100 = 0x1000000;
  memset_0(v99, 0, sizeof(v99));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v143, (__int64)&v93, 0);
  try
  {
    hKey = 0;
    v146 = 0;
    v117 = 0;
    v147 = 0;
    if ( !IsInGroup(0x220u) )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 153;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::Throw(
        &v143,
        &v93,
        2147942405LL,
        L"The client process is not running under an administrator account");
    }
    v132 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 15LL);
    v133 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 14LL);
    v134 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 13LL);
    v135 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 12LL);
    v136 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 11LL);
    v138 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 10LL);
    v137 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 9LL);
    v120 = *(unsigned __int8 *)(*(_QWORD *)&v148.Data1 + 8LL);
    v121 = *(unsigned __int16 *)(*(_QWORD *)&v148.Data1 + 6LL);
    LODWORD(v142) = *(unsigned __int16 *)(*(_QWORD *)&v148.Data1 + 4LL);
    v101 = **(_DWORD **)&v148.Data1;
    v124 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 15LL);
    v125 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 14LL);
    v126 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 13LL);
    v127 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 12LL);
    v128 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 11LL);
    v122 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 10LL);
    v129 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 9LL);
    v130 = *(unsigned __int8 *)(*(_QWORD *)&v150.Data1 + 8LL);
    v131 = *(unsigned __int16 *)(*(_QWORD *)&v150.Data1 + 6LL);
    LODWORD(v141) = *(unsigned __int16 *)(*(_QWORD *)&v150.Data1 + 4LL);
    v104 = **(_DWORD **)&v150.Data1;
    v106 = *((unsigned __int8 *)Buf1 + 15);
    v107 = *((unsigned __int8 *)Buf1 + 14);
    v108 = *((unsigned __int8 *)Buf1 + 13);
    v109 = *((unsigned __int8 *)Buf1 + 12);
    v110 = *((unsigned __int8 *)Buf1 + 11);
    v111 = *((unsigned __int8 *)Buf1 + 10);
    v112 = *((unsigned __int8 *)Buf1 + 9);
    v113 = *((unsigned __int8 *)Buf1 + 8);
    v114 = *((unsigned __int16 *)Buf1 + 3);
    v115 = *((unsigned __int16 *)Buf1 + 2);
    LODWORD(v116) = *(_DWORD *)Buf1;
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 157;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::Trace(
      &v143,
      &v93,
      L"Parameters: \n"
       "ProviderId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x},\n"
       "ClassId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x},\n"
       "pwszProviderName = %s\n"
       "eProviderType = %d\n"
       "pwszProviderVersion = %s\n"
       "ProviderVersionId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x},\n",
      (unsigned int)v116,
      v115,
      v114,
      v113,
      v112,
      v111,
      v110,
      v109,
      v108,
      v107,
      v106,
      v104,
      v141,
      v131,
      v130,
      v129,
      v122,
      v128,
      v127,
      v126,
      v125,
      v124,
      lpData,
      a5,
      v118,
      v101,
      v142,
      v121,
      v120,
      v137,
      v138,
      v136,
      v135,
      v134,
      v133,
      v132);
    if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 174;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::Throw(&v143, &v93, 2147942487LL, L"NULL Provider ID");
    }
    if ( !lpData )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 176;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::Throw(&v143, &v93, 2147942487LL, L"NULL name");
    }
    if ( !*(_WORD *)lpData )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 178;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::Throw(&v143, &v93, 2147942487LL, L"Empty name");
    }
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&lpData[2 * v7] );
    if ( v7 > 0xFF )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 180;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      dwOptions[0] = 255;
      CVssFunctionTracer::Throw(
        &v143,
        &v93,
        2147942487LL,
        L"pwszProviderName length greater than %d",
        *(_QWORD *)dwOptions);
    }
    if ( a5 != VSS_PROV_SOFTWARE )
    {
      if ( (unsigned int)(a5 - 3) >= 2 )
      {
        v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
        v94 = L"CVssAdmin::RegisterProvider";
        v95 = L"CORADMNC";
        v96 = 190;
        v97 = 1;
        v98 = 255;
        v100 = 0x1000000;
        memset_0(v99, 0, sizeof(v99));
        dwOptions[0] = a5;
        CVssFunctionTracer::Throw(&v143, &v93, 2147942487LL, L"invalid provider type %d", *(_QWORD *)dwOptions);
      }
      if ( (unsigned int)CVssSKU::IsClient() )
      {
        v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
        v94 = L"CVssAdmin::RegisterProvider";
        v95 = L"CORADMNC";
        v96 = 187;
        v97 = 1;
        v98 = 255;
        v100 = 0x1000000;
        memset_0(v99, 0, sizeof(v99));
        CVssFunctionTracer::Throw(&v143, &v93, 2147942487LL, L"Context not implemented in client SKU");
      }
    }
    if ( !v118 )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 193;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::Throw(&v143, &v93, 2147942487LL, L"NULL version");
    }
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v118[2 * v8] );
    if ( v8 > 0xFF )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 195;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      dwOptions[0] = 255;
      CVssFunctionTracer::Throw(
        &v143,
        &v93,
        2147942487LL,
        L"pwszProviderVersion length greater than %d",
        *(_QWORD *)dwOptions);
    }
    CVssAutomaticLock2::CVssAutomaticLock2((CVssAutomaticLock2 *)v165, (CVssAdmin *)((char *)this + 8));
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 200;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::AddOperation((__int64)&v143, (__int64)&v93, 0x192u);
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 201;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::AddContext((__int64)&v143, (__int64)&v93, 5016, (__int64)lpData);
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 202;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::AddContext((__int64)&v143, (__int64)&v93, 5017, (__int64)v118);
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 203;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    LODWORD(v83) = v106;
    LODWORD(v78) = v107;
    LODWORD(v73) = v108;
    LODWORD(v68) = v109;
    LODWORD(v63) = v110;
    LODWORD(v58) = v111;
    LODWORD(lpdwDisposition) = v112;
    LODWORD(phkResult) = v113;
    LODWORD(lpSecurityAttributes) = v114;
    samDesired[0] = v115;
    dwOptions[0] = v116;
    CVssFunctionTracer::AddContextEx(
      (__int64)&v143,
      (__int64)&v93,
      0x1391u,
      L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      *(_QWORD *)dwOptions,
      *(_QWORD *)samDesired,
      lpSecurityAttributes,
      phkResult,
      lpdwDisposition,
      v58,
      v63,
      v68,
      v73,
      v78,
      v83);
    dwDisposition = 0;
    v9 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\VSS",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           &dwDisposition);
    v87 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v87 = (unsigned __int16)v9 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 219;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v87,
        L"RegCreateKeyExW(HKLM,%s,...)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS");
    }
    v10 = RegCreateKeyExW(hKey, L"Providers", 0, 0, 0, 0x20006u, 0, &v146, &dwDisposition);
    v88 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v88 = (unsigned __int16)v10 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 235;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v88,
        L"RegCreateKeyExW(HKLM\\%s,%s,...)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers");
    }
    LODWORD(v79) = v106;
    LODWORD(v74) = v107;
    LODWORD(v69) = v108;
    LODWORD(v64) = v109;
    LODWORD(v59) = v110;
    LODWORD(lpdwDispositiona) = v111;
    LODWORD(phkResulta) = v112;
    LODWORD(lpSecurityAttributesa) = v113;
    samDesireda[0] = v114;
    dwOptionsa[0] = v115;
    v144 = StringCchPrintfW(
             SubKey,
             0x100u,
             L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
             (unsigned int)v116,
             *(_QWORD *)dwOptionsa,
             *(_QWORD *)samDesireda,
             lpSecurityAttributesa,
             phkResulta,
             lpdwDispositiona,
             v59,
             v64,
             v69,
             v74,
             v79);
    if ( v144 < 0 )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 243;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(&v143, &v93, (unsigned int)v144, L"StringCchPrintfW()");
    }
    v11 = RegCreateKeyExW(v146, SubKey, 0, 0, 0, 0x20006u, 0, &v117, &dwDisposition);
    v89 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v89 = (unsigned __int16)v11 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 256;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v89,
        L"RegCreateKeyExW(HKLM\\%s\\%s,%s,...)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers",
        SubKey);
    }
    if ( dwDisposition != 1 )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      if ( dwDisposition != 2 )
      {
        v96 = 271;
        memset_0(v99, 0, sizeof(v99));
        LODWORD(phkResultb) = dwDisposition;
        CVssFunctionTracer::TranslateGenericError(
          &v143,
          &v93,
          0,
          L"RegCreateKeyExW(HKLM\\%s\\%s,%s,...,[%d])",
          L"SYSTEM\\CurrentControlSet\\Services\\VSS",
          L"Providers",
          SubKey,
          phkResultb);
      }
      v96 = 267;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::Throw(&v143, &v93, 2147754755LL, L"Provider with Id %s already registered ", SubKey);
    }
    v12 = -1;
    do
      v116 = ++v12;
    while ( *(_WORD *)&lpData[2 * v12] );
    v13 = RegSetValueExW(v117, &word_1401004B0, 0, 1u, lpData, 2 * v12 + 2);
    v90 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v90 = (unsigned __int16)v13 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 288;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v90,
        L"RegSetValueExW(HKLM\\%s\\%s\\%s,%s,0,REG_SZ,%s.%d)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers",
        SubKey,
        &word_1401004B0,
        lpData,
        2LL * (unsigned int)(v116 + 1));
    }
    *(_DWORD *)Data = a5;
    v14 = RegSetValueExW(v117, L"Type", 0, 4u, Data, 4u);
    v91 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v91 = (unsigned __int16)v14 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 304;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      LODWORD(lpdwDispositionb) = *(_DWORD *)Data;
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v91,
        L"RegSetValueExW(HKLM\\%s\\%s\\%s,%s,0,REG_DWORD,%d,%d)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers",
        SubKey,
        L"Type",
        lpdwDispositionb,
        4);
    }
    v15 = -1;
    do
      v116 = ++v15;
    while ( *(_WORD *)&v118[2 * v15] );
    v16 = RegSetValueExW(v117, L"Version", 0, 1u, v118, 2 * v15 + 2);
    v92 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v92 = (unsigned __int16)v16 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 320;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v92,
        L"RegSetValueExW(HKLM\\%s\\%s\\%s,%s,0,REG_SZ,%s.%d)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers",
        SubKey,
        L"Version",
        v118,
        2LL * (unsigned int)(v116 + 1));
    }
    LODWORD(v80) = v132;
    LODWORD(v75) = v133;
    LODWORD(v70) = v134;
    LODWORD(v65) = v135;
    LODWORD(v60) = v136;
    LODWORD(lpdwDispositionb) = v138;
    LODWORD(phkResultb) = v137;
    LODWORD(lpSecurityAttributesb) = v120;
    samDesiredb[0] = v121;
    dwOptionsb[0] = v142;
    v144 = StringCchPrintfW(
             v167,
             0x100u,
             L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
             v101,
             *(_QWORD *)dwOptionsb,
             *(_QWORD *)samDesiredb,
             lpSecurityAttributesb,
             phkResultb,
             lpdwDispositionb,
             v60,
             v65,
             v70,
             v75,
             v80);
    if ( v144 < 0 )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 329;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(&v143, &v93, (unsigned int)v144, L"StringCchPrintfW()");
    }
    v17 = -1;
    do
      v142 = ++v17;
    while ( v167[v17] );
    v18 = RegSetValueExW(v117, L"VersionId", 0, 1u, (const BYTE *)v167, 2 * v17 + 2);
    v101 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v101 = (unsigned __int16)v18 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 341;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v101,
        L"RegSetValueExW(HKLM\\%s\\%s\\%s,%s,0,REG_SZ,%s.%d)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers",
        SubKey,
        L"VersionId",
        v167,
        2LL * (unsigned int)(v142 + 1));
    }
    v19 = RegCreateKeyExW(v117, L"CLSID", 0, 0, 0, 0x20006u, 0, &v147, &dwDisposition);
    v101 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v101 = (unsigned __int16)v19 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 359;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v101,
        L"RegCreateKeyExW(HKLM\\%s\\%s\\%s,%s,...)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers",
        SubKey,
        L"CLSID");
    }
    LODWORD(v81) = v124;
    LODWORD(v76) = v125;
    LODWORD(v71) = v126;
    LODWORD(v66) = v127;
    LODWORD(v61) = v128;
    LODWORD(lpdwDispositionc) = v122;
    LODWORD(phkResultc) = v129;
    LODWORD(lpSecurityAttributesc) = v130;
    samDesiredc[0] = v131;
    dwOptionsc[0] = v141;
    v144 = StringCchPrintfW(
             v167,
             0x100u,
             L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
             v104,
             *(_QWORD *)dwOptionsc,
             *(_QWORD *)samDesiredc,
             lpSecurityAttributesc,
             phkResultc,
             lpdwDispositionc,
             v61,
             v66,
             v71,
             v76,
             v81);
    if ( v144 < 0 )
    {
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 368;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(&v143, &v93, (unsigned int)v144, L"StringCchPrintfW()");
    }
    v20 = -1;
    do
      v141 = ++v20;
    while ( v167[v20] );
    v21 = RegSetValueExW(v147, &word_1401006B0, 0, 1u, (const BYTE *)v167, 2 * v20 + 2);
    v104 = v21;
    if ( v21 )
    {
      if ( v21 > 0 )
        v104 = (unsigned __int16)v21 | 0x80070000;
      v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v94 = L"CVssAdmin::RegisterProvider";
      v95 = L"CORADMNC";
      v96 = 380;
      v97 = 1;
      v98 = 255;
      v100 = 0x1000000;
      memset_0(v99, 0, sizeof(v99));
      CVssFunctionTracer::TranslateGenericError(
        &v143,
        &v93,
        v104,
        L"RegSetValueExW(HKLM\\%s\\%s\\%s\\%s,%s,0,REG_SZ,%s.%d)",
        L"SYSTEM\\CurrentControlSet\\Services\\VSS",
        L"Providers",
        SubKey,
        L"CLSID",
        &word_1401006B0,
        v167,
        2LL * (unsigned int)(v141 + 1));
    }
    v102 = *(struct _GUID *)*(_QWORD *)&v150.Data1;
    v148 = *(struct _GUID *)*(_QWORD *)&v148.Data1;
    v150 = *(struct _GUID *)Buf1;
    CVssProviderManager::AddProviderIntoArray(
      &v150,
      (unsigned __int16 *)lpData,
      a5,
      (unsigned __int16 *)v118,
      &v148,
      &v102);
    CVssAutomaticLock2::~CVssAutomaticLock2(v165);
  }
  catch ( long v152 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v143,
      v152,
      L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
      L"CORADMNC",
      L"CVssAdmin::RegisterProvider",
      0x18Au,
      v145);
    Buf1 = v139;
  }
  catch ( _com_error *v161 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v143,
      v161,
      L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
      L"CORADMNC",
      L"CVssAdmin::RegisterProvider",
      0x18Au,
      v145);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v143,
      L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
      L"CORADMNC",
      L"CVssAdmin::RegisterProvider",
      0x18Au,
      v145);
    Buf1 = v139;
  }
  catch ( const std::exception *v162 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v143,
      v162,
      L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
      L"CORADMNC",
      L"CVssAdmin::RegisterProvider",
      0x18Au,
      v145);
  }
  if ( v147 )
    v22 = RegCloseKey(v147);
  else
    v22 = 0;
  if ( v22 )
  {
    LastError = GetLastError();
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 401;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::Trace(&v143, &v93, L"Error closing the hRegKeyCLSID key. [0x%08lx]", LastError);
  }
  if ( v117 )
    v24 = RegCloseKey(v117);
  else
    v24 = 0;
  if ( v24 )
  {
    v25 = GetLastError();
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 405;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::Trace(&v143, &v93, L"Error closing the hRegKeyNewProvider key. [0x%08lx]", v25);
  }
  if ( v146 )
    v26 = RegCloseKey(v146);
  else
    v26 = 0;
  if ( v26 )
  {
    v27 = GetLastError();
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 409;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::Trace(&v143, &v93, L"Error closing the hRegKeyProviders key. [0x%08lx]", v27);
  }
  if ( hKey )
    v28 = RegCloseKey(hKey);
  else
    v28 = 0;
  if ( v28 )
  {
    v29 = GetLastError();
    v93 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v94 = L"CVssAdmin::RegisterProvider";
    v95 = L"CORADMNC";
    v96 = 413;
    v97 = 1;
    v98 = 255;
    v100 = 0x1000000;
    memset_0(v99, 0, sizeof(v99));
    CVssFunctionTracer::Trace(&v143, &v93, L"Error closing the hRegKeyVSS key. [0x%08lx]", v29);
  }
  if ( v144 < 0 )
  {
    v153 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
    v154 = L"CVssAdmin::RegisterProvider";
    v155 = L"CORADMNC";
    v156 = 417;
    v157 = 1;
    v158 = 255;
    v160 = 0x1000000;
    memset_0(v159, 0, sizeof(v159));
    CVssFunctionTracer::CVssFunctionTracer(
      (__int64)&v93,
      (__int64)&v153,
      (__int64)L"CVssAdmin::RegisterProvider_rec_del");
    LODWORD(v85) = *((unsigned __int8 *)Buf1 + 15);
    LODWORD(v84) = *((unsigned __int8 *)Buf1 + 14);
    LODWORD(v82) = *((unsigned __int8 *)Buf1 + 13);
    LODWORD(v77) = *((unsigned __int8 *)Buf1 + 12);
    LODWORD(v72) = *((unsigned __int8 *)Buf1 + 11);
    LODWORD(v67) = *((unsigned __int8 *)Buf1 + 10);
    LODWORD(v62) = *((unsigned __int8 *)Buf1 + 9);
    LODWORD(lpdwDispositiond) = *((unsigned __int8 *)Buf1 + 8);
    LODWORD(phkResultd) = *((unsigned __int16 *)Buf1 + 3);
    LODWORD(lpSecurityAttributesd) = *((unsigned __int16 *)Buf1 + 2);
    samDesiredd[0] = v149->Data1;
    v31 = StringCchPrintfW(
            v168,
            0x100u,
            L"%s\\%s\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
            L"SYSTEM\\CurrentControlSet\\Services\\VSS",
            L"Providers",
            *(_QWORD *)samDesiredd,
            lpSecurityAttributesd,
            phkResultd,
            lpdwDispositiond,
            v62,
            v67,
            v72,
            v77,
            v82,
            v84,
            v85);
    v144 = v31;
    if ( v31 < 0 )
    {
      v153 = L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx";
      v154 = L"CVssAdmin::RegisterProvider";
      v155 = L"CORADMNC";
      v156 = 423;
      v157 = 1;
      v158 = 255;
      v160 = 0x1000000;
      memset_0(v159, 0, sizeof(v159));
      CVssFunctionTracer::TranslateGenericError(&v143, &v153, (unsigned int)v31, L"StringCchPrintfW()");
    }
    try
    {
      RecursiveDeleteKey((struct CVssFunctionTracer *)&v93, v30, v168);
      CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v93);
    }
    catch ( long v151 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v143,
        v151,
        L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
        L"CORADMNC",
        L"CVssAdmin::RegisterProvider",
        0x1ABu,
        v145);
    }
    catch ( _com_error *v164 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v143,
        v164,
        L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
        L"CORADMNC",
        L"CVssAdmin::RegisterProvider",
        0x1ABu,
        v145);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v143,
        L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
        L"CORADMNC",
        L"CVssAdmin::RegisterProvider",
        0x1ABu,
        v145);
    }
    catch ( const std::exception *v163 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v143,
        v163,
        L"base\\stor\\vss\\modules\\coord\\src\\admin.cxx",
        L"CORADMNC",
        L"CVssAdmin::RegisterProvider",
        0x1ABu,
        v145);
    }
  }
  v32 = v144;
  CVssFunctionTracer::~CVssFunctionTracer(&v143);
  return v32;
}

```

## disassembly

```asm
0x140047f80  mov     r11, rsp
0x140047f83  push    rbx
0x140047f84  push    rsi
0x140047f85  push    rdi
0x140047f86  push    r12
0x140047f88  push    r13
0x140047f8a  push    r14
0x140047f8c  push    r15
0x140047f8e  sub     rsp, 0A90h
0x140047f95  mov     rax, cs:__security_cookie
0x140047f9c  xor     rax, rsp
0x140047f9f  mov     [rsp+0AC8h+var_48], rax
0x140047fa7  mov     [rsp+0AC8h+lpData], r9
0x140047faf  mov     qword ptr [rsp+0AC8h+var_738.Data1], r8
0x140047fb7  mov     [rsp+0AC8h+Buf1], rdx
0x140047fbf  mov     [rsp+0AC8h+var_980], rcx
0x140047fc7  mov     [rsp+0AC8h+var_748], rdx
0x140047fcf  mov     rcx, [rsp+0AC8h+arg_30]
0x140047fd7  mov     qword ptr [rsp+0AC8h+var_758.Data1], rcx
0x140047fdf  mov     [rsp+0AC8h+var_800], rdx
0x140047fe7  mov     rax, [rsp+0AC8h+arg_28]
0x140047fef  mov     [rsp+0AC8h+var_860], rax
0x140047ff7  lea     rdi, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\coord\\src\\a"...
0x140047ffe  mov     [r11-978h], rdi
0x140048005  lea     rsi, aCvssadminRegis_0; "CVssAdmin::RegisterProvider"
0x14004800c  mov     [r11-970h], rsi
0x140048013  lea     r14, aCoradmnc; "CORADMNC"
0x14004801a  mov     [r11-968h], r14
0x140048021  mov     [rsp+0AC8h+var_960], 8Bh
0x14004802c  mov     r12d, 1
0x140048032  mov     [r11-95Ch], r12d
0x140048039  mov     r13d, 0FFh
0x14004803f  mov     [r11-958h], r13d
0x140048046  xor     r15d, r15d
0x140048049  mov     [rsp+0AC8h+var_8D8], 1000000h
0x140048054  lea     ebx, [r12+77h]
0x140048059  mov     r8d, ebx; Size
0x14004805c  xor     edx, edx; Val
0x14004805e  lea     rcx, [r11-950h]; void *
0x140048065  call    memset_0
0x14004806a  xor     r8d, r8d
0x14004806d  lea     rdx, [rsp+0AC8h+var_978]
0x140048075  lea     rcx, [rsp+0AC8h+var_7D8]
0x14004807d  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140048082  nop
0x140048083  mov     [rsp+0AC8h+hKey], r15
0x14004808b  mov     [rsp+0AC8h+var_768], r15
0x140048093  mov     [rsp+0AC8h+var_868], r15
0x14004809b  mov     [rsp+0AC8h+var_760], r15
0x1400480a3  mov     [rsp+0AC8h+var_988], r15b
0x1400480ab  mov     ecx, 220h; nSubAuthority1
0x1400480b0  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x1400480b5  test    al, al
0x1400480b7  jnz     short loc_14004812B
0x1400480b9  mov     [rsp+0AC8h+var_978], rdi
0x1400480c1  mov     [rsp+0AC8h+var_970], rsi
0x1400480c9  mov     [rsp+0AC8h+var_968], r14
0x1400480d1  mov     [rsp+0AC8h+var_960], 99h
0x1400480dc  mov     [rsp+0AC8h+var_95C], r12d
0x1400480e4  mov     [rsp+0AC8h+var_958], r13d
0x1400480ec  mov     [rsp+0AC8h+var_8D8], 1000000h
0x1400480f7  mov     r8d, ebx; Size
0x1400480fa  xor     edx, edx; Val
0x1400480fc  lea     rcx, [rsp+0AC8h+var_950]; void *
0x140048104  call    memset_0
0x140048109  lea     r9, aTheClientProce_1; "The client process is not running under"...
0x140048110  mov     r8d, 80070005h
0x140048116  lea     rdx, [rsp+0AC8h+var_978]
0x14004811e  lea     rcx, [rsp+0AC8h+var_7D8]
0x140048126  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14004812b  mov     rax, qword ptr [rsp+0AC8h+var_758.Data1]
0x140048133  movzx   ecx, byte ptr [rax+0Fh]
0x140048137  mov     [rsp+0AC8h+var_820], ecx
0x14004813e  movzx   ecx, byte ptr [rax+0Eh]
0x140048142  mov     [rsp+0AC8h+var_81C], ecx
0x140048149  movzx   ecx, byte ptr [rax+0Dh]
0x14004814d  mov     [rsp+0AC8h+var_818], ecx
0x140048154  movzx   ecx, byte ptr [rax+0Ch]
0x140048158  mov     [rsp+0AC8h+var_814], ecx
0x14004815f  movzx   ecx, byte ptr [rax+0Bh]
0x140048163  mov     [rsp+0AC8h+var_810], ecx
0x14004816a  movzx   ecx, byte ptr [rax+0Ah]
0x14004816e  mov     [rsp+0AC8h+var_808], ecx
0x140048175  movzx   ecx, byte ptr [rax+9]
0x140048179  mov     [rsp+0AC8h+var_80C], ecx
0x140048180  movzx   ecx, byte ptr [rax+8]
0x140048184  mov     [rsp+0AC8h+var_850], ecx
0x14004818b  movzx   ecx, word ptr [rax+6]
0x14004818f  mov     [rsp+0AC8h+var_84C], ecx
0x140048196  movzx   ecx, word ptr [rax+4]
0x14004819a  mov     dword ptr [rsp+0AC8h+var_7E8], ecx
0x1400481a1  mov     ecx, [rax]
0x1400481a3  mov     [rsp+0AC8h+var_8C8], ecx
0x1400481aa  mov     rax, qword ptr [rsp+0AC8h+var_738.Data1]
0x1400481b2  movzx   ecx, byte ptr [rax+0Fh]
0x1400481b6  mov     [rsp+0AC8h+var_840], ecx
0x1400481bd  movzx   ecx, byte ptr [rax+0Eh]
0x1400481c1  mov     [rsp+0AC8h+var_83C], ecx
0x1400481c8  movzx   ecx, byte ptr [rax+0Dh]
0x1400481cc  mov     [rsp+0AC8h+var_838], ecx
0x1400481d3  movzx   ecx, byte ptr [rax+0Ch]
0x1400481d7  mov     [rsp+0AC8h+var_834], ecx
0x1400481de  movzx   ecx, byte ptr [rax+0Bh]
0x1400481e2  mov     [rsp+0AC8h+var_830], ecx
0x1400481e9  movzx   ecx, byte ptr [rax+0Ah]
0x1400481ed  mov     [rsp+0AC8h+var_848], ecx
0x1400481f4  movzx   ecx, byte ptr [rax+9]
0x1400481f8  mov     [rsp+0AC8h+var_82C], ecx
0x1400481ff  movzx   ecx, byte ptr [rax+8]
0x140048203  mov     [rsp+0AC8h+var_828], ecx
0x14004820a  movzx   ecx, word ptr [rax+6]
0x14004820e  mov     [rsp+0AC8h+var_824], ecx
0x140048215  movzx   ecx, word ptr [rax+4]
0x140048219  mov     dword ptr [rsp+0AC8h+var_7F0], ecx
0x140048220  mov     ecx, [rax]
0x140048222  mov     [rsp+0AC8h+var_8A4], ecx
0x140048229  mov     rax, [rsp+0AC8h+Buf1]
0x140048231  movzx   ecx, byte ptr [rax+0Fh]
0x140048235  mov     [rsp+0AC8h+var_898], ecx
0x14004823c  movzx   ecx, byte ptr [rax+0Eh]
0x140048240  mov     [rsp+0AC8h+var_894], ecx
0x140048247  movzx   ecx, byte ptr [rax+0Dh]
0x14004824b  mov     [rsp+0AC8h+var_890], ecx
0x140048252  movzx   ecx, byte ptr [rax+0Ch]
0x140048256  mov     [rsp+0AC8h+var_88C], ecx
0x14004825d  movzx   ecx, byte ptr [rax+0Bh]
0x140048261  mov     [rsp+0AC8h+var_888], ecx
0x140048268  movzx   ecx, byte ptr [rax+0Ah]
0x14004826c  mov     [rsp+0AC8h+var_884], ecx
0x140048273  movzx   ecx, byte ptr [rax+9]
0x140048277  mov     [rsp+0AC8h+var_880], ecx
0x14004827e  movzx   ecx, byte ptr [rax+8]
0x140048282  mov     [rsp+0AC8h+var_87C], ecx
0x140048289  movzx   ecx, word ptr [rax+6]
0x14004828d  mov     [rsp+0AC8h+var_878], ecx
0x140048294  movzx   ecx, word ptr [rax+4]
0x140048298  mov     [rsp+0AC8h+var_874], ecx
0x14004829f  mov     eax, [rax]
0x1400482a1  mov     dword ptr [rsp+0AC8h+var_870], eax
0x1400482a8  mov     [rsp+0AC8h+var_978], rdi
0x1400482b0  mov     [rsp+0AC8h+var_970], rsi
0x1400482b8  mov     [rsp+0AC8h+var_968], r14
0x1400482c0  mov     [rsp+0AC8h+var_960], 9Dh
0x1400482cb  mov     [rsp+0AC8h+var_95C], r12d
0x1400482d3  mov     [rsp+0AC8h+var_958], r13d
0x1400482db  mov     [rsp+0AC8h+var_8D8], 1000000h
0x1400482e6  mov     r8, rbx; Size
0x1400482e9  xor     edx, edx; Val
0x1400482eb  lea     rcx, [rsp+0AC8h+var_950]; void *
0x1400482f3  call    memset_0
0x1400482f8  mov     eax, [rsp+0AC8h+var_820]
0x1400482ff  mov     [rsp+0AC8h+var_998], eax
0x140048306  mov     eax, [rsp+0AC8h+var_81C]
0x14004830d  mov     [rsp+0AC8h+var_9A0], eax
0x140048314  mov     eax, [rsp+0AC8h+var_818]
0x14004831b  mov     [rsp+0AC8h+var_9A8], eax
0x140048322  mov     eax, [rsp+0AC8h+var_814]
0x140048329  mov     [rsp+0AC8h+var_9B0], eax
0x140048330  mov     eax, [rsp+0AC8h+var_810]
0x140048337  mov     [rsp+0AC8h+var_9B8], eax
0x14004833e  mov     eax, [rsp+0AC8h+var_808]
0x140048345  mov     [rsp+0AC8h+var_9C0], eax
0x14004834c  mov     eax, [rsp+0AC8h+var_80C]
0x140048353  mov     [rsp+0AC8h+var_9C8], eax
0x14004835a  mov     eax, [rsp+0AC8h+var_850]
0x140048361  mov     [rsp+0AC8h+var_9D0], eax
0x140048368  mov     eax, [rsp+0AC8h+var_84C]
0x14004836f  mov     [rsp+0AC8h+var_9D8], eax
0x140048376  mov     eax, dword ptr [rsp+0AC8h+var_7E8]
0x14004837d  mov     [rsp+0AC8h+var_9E0], eax
0x140048384  mov     eax, [rsp+0AC8h+var_8C8]
0x14004838b  mov     [rsp+0AC8h+var_9E8], eax
0x140048392  mov     r9, [rsp+0AC8h+var_860]
0x14004839a  mov     [rsp+0AC8h+var_9F0], r9
0x1400483a2  mov     eax, [rsp+0AC8h+arg_20]
0x1400483a9  mov     [rsp+0AC8h+var_9F8], eax
0x1400483b0  mov     rdx, [rsp+0AC8h+lpData]
0x1400483b8  mov     [rsp+0AC8h+var_A00], rdx
0x1400483c0  mov     eax, [rsp+0AC8h+var_840]
0x1400483c7  mov     [rsp+0AC8h+var_A08], eax
0x1400483ce  mov     eax, [rsp+0AC8h+var_83C]
0x1400483d5  mov     [rsp+0AC8h+var_A10], eax
0x1400483dc  mov     eax, [rsp+0AC8h+var_838]
0x1400483e3  mov     [rsp+0AC8h+var_A18], eax
0x1400483ea  mov     eax, [rsp+0AC8h+var_834]
0x1400483f1  mov     [rsp+0AC8h+var_A20], eax
0x1400483f8  mov     eax, [rsp+0AC8h+var_830]
0x1400483ff  mov     [rsp+0AC8h+var_A28], eax
0x140048406  mov     eax, [rsp+0AC8h+var_848]
0x14004840d  mov     [rsp+0AC8h+var_A30], eax
0x140048414  mov     eax, [rsp+0AC8h+var_82C]
0x14004841b  mov     [rsp+0AC8h+var_A38], eax
0x140048422  mov     eax, [rsp+0AC8h+var_828]
0x140048429  mov     [rsp+0AC8h+var_A40], eax
0x140048430  mov     eax, [rsp+0AC8h+var_824]
0x140048437  mov     [rsp+0AC8h+var_A48], eax
0x14004843e  mov     eax, dword ptr [rsp+0AC8h+var_7F0]
0x140048445  mov     dword ptr [rsp+0AC8h+var_A50], eax
0x140048449  mov     eax, [rsp+0AC8h+var_8A4]
0x140048450  mov     dword ptr [rsp+0AC8h+var_A58], eax
0x140048454  mov     eax, [rsp+0AC8h+var_898]
0x14004845b  mov     dword ptr [rsp+0AC8h+var_A60], eax
0x14004845f  mov     eax, [rsp+0AC8h+var_894]
0x140048466  mov     dword ptr [rsp+0AC8h+var_A68], eax
0x14004846a  mov     eax, [rsp+0AC8h+var_890]
0x140048471  mov     dword ptr [rsp+0AC8h+var_A70], eax
0x140048475  mov     eax, [rsp+0AC8h+var_88C]
0x14004847c  mov     dword ptr [rsp+0AC8h+var_A78], eax
0x140048480  mov     eax, [rsp+0AC8h+var_888]
0x140048487  mov     dword ptr [rsp+0AC8h+var_A80], eax
0x14004848b  mov     eax, [rsp+0AC8h+var_884]
0x140048492  mov     dword ptr [rsp+0AC8h+lpdwDisposition], eax
0x140048496  mov     eax, [rsp+0AC8h+var_880]
0x14004849d  mov     dword ptr [rsp+0AC8h+phkResult], eax
0x1400484a1  mov     eax, [rsp+0AC8h+var_87C]
0x1400484a8  mov     dword ptr [rsp+0AC8h+lpSecurityAttributes], eax
0x1400484ac  mov     eax, [rsp+0AC8h+var_878]
0x1400484b3  mov     [rsp+0AC8h+samDesired], eax
0x1400484b7  mov     eax, [rsp+0AC8h+var_874]
0x1400484be  mov     [rsp+0AC8h+dwOptions], eax
0x1400484c2  mov     r9d, dword ptr [rsp+0AC8h+var_870]
0x1400484ca  lea     r8, aParametersProv_4; "Parameters: \nProviderId = {%.8x-%.4x-%"...
0x1400484d1  lea     rdx, [rsp+0AC8h+var_978]
0x1400484d9  lea     rcx, [rsp+0AC8h+var_7D8]
0x1400484e1  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400484e6  mov     r8d, 10h; Size
0x1400484ec  lea     rdx, GUID_NULL; Buf2
0x1400484f3  mov     rcx, [rsp+0AC8h+Buf1]; Buf1
0x1400484fb  call    memcmp_0
0x140048500  test    eax, eax
0x140048502  jz      loc_14004999E
0x140048508  mov     rcx, [rsp+0AC8h+lpData]
0x140048510  test    rcx, rcx
0x140048513  jnz     short loc_140048587
0x140048515  mov     [rsp+0AC8h+var_978], rdi
0x14004851d  mov     [rsp+0AC8h+var_970], rsi
0x140048525  mov     [rsp+0AC8h+var_968], r14
0x14004852d  mov     [rsp+0AC8h+var_960], 0B0h
0x140048538  mov     [rsp+0AC8h+var_95C], r12d
0x140048540  mov     [rsp+0AC8h+var_958], r13d
0x140048548  mov     [rsp+0AC8h+var_8D8], 1000000h
0x140048553  mov     r8, rbx; Size
0x140048556  xor     edx, edx; Val
0x140048558  lea     rcx, [rsp+0AC8h+var_950]; void *
0x140048560  call    memset_0
0x140048565  lea     r9, aNullName; "NULL name"
0x14004856c  mov     r8d, 80070057h
0x140048572  lea     rdx, [rsp+0AC8h+var_978]
0x14004857a  lea     rcx, [rsp+0AC8h+var_7D8]
0x140048582  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140048587  cmp     [rcx], r15w
0x14004858b  jnz     short loc_1400485FF
0x14004858d  mov     [rsp+0AC8h+var_978], rdi
0x140048595  mov     [rsp+0AC8h+var_970], rsi
0x14004859d  mov     [rsp+0AC8h+var_968], r14
0x1400485a5  mov     [rsp+0AC8h+var_960], 0B2h
0x1400485b0  mov     [rsp+0AC8h+var_95C], r12d
0x1400485b8  mov     [rsp+0AC8h+var_958], r13d
0x1400485c0  mov     [rsp+0AC8h+var_8D8], 1000000h
0x1400485cb  mov     r8, rbx; Size
0x1400485ce  xor     edx, edx; Val
0x1400485d0  lea     rcx, [rsp+0AC8h+var_950]; void *
0x1400485d8  call    memset_0
0x1400485dd  lea     r9, aEmptyName; "Empty name"
0x1400485e4  mov     r8d, 80070057h
0x1400485ea  lea     rdx, [rsp+0AC8h+var_978]
0x1400485f2  lea     rcx, [rsp+0AC8h+var_7D8]
0x1400485fa  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400485ff  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140048603  mov     rax, rdx
0x140048606  inc     rax
0x140048609  cmp     [rcx+rax*2], r15w
0x14004860e  jnz     short loc_140048606
0x140048610  cmp     rax, r13
0x140048613  jbe     short loc_14004868C
0x140048615  mov     [rsp+0AC8h+var_978], rdi
0x14004861d  mov     [rsp+0AC8h+var_970], rsi
0x140048625  mov     [rsp+0AC8h+var_968], r14
0x14004862d  mov     [rsp+0AC8h+var_960], 0B4h
0x140048638  mov     [rsp+0AC8h+var_95C], r12d
0x140048640  mov     [rsp+0AC8h+var_958], r13d
0x140048648  mov     [rsp+0AC8h+var_8D8], 1000000h
0x140048653  mov     r8, rbx; Size
0x140048656  xor     edx, edx; Val
0x140048658  lea     rcx, [rsp+0AC8h+var_950]; void *
0x140048660  call    memset_0
0x140048665  mov     [rsp+0AC8h+dwOptions], r13d
0x14004866a  lea     r9, aPwszproviderna; "pwszProviderName length greater than %d"
0x140048671  mov     r8d, 80070057h
0x140048677  lea     rdx, [rsp+0AC8h+var_978]
0x14004867f  lea     rcx, [rsp+0AC8h+var_7D8]
0x140048687  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14004868c  mov     ecx, [rsp+0AC8h+arg_20]
0x140048693  sub     ecx, 2
0x140048696  jz      loc_1400487A6
0x14004869c  sub     ecx, 1
0x14004869f  jz      loc_140048727
0x1400486a5  cmp     ecx, 1
0x1400486a8  jz      short loc_140048727
0x1400486aa  mov     [rsp+0AC8h+var_978], rdi
  ... truncated ...
```
