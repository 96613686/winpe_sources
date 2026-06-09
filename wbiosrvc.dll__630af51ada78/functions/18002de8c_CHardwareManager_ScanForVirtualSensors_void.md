# CHardwareManager::ScanForVirtualSensors(void)

- ea: `0x18002de8c`
- end: `0x18002e949`
- name: `?ScanForVirtualSensors@CHardwareManager@@QEAAJXZ`
- size: `2749`
- prototype: `__int64 __fastcall(CHardwareManager *__hidden this)`
- caller_count: `4`
- callee_count: `31`
- tags: `registry_config, service_task`

## callers

- `0x1800447b0`
- `0x1800515c8`
- `0x180072448`
- `0x180073538`

## callees

- `0x18000513c`
- `0x18000b760`
- `0x180010944`
- `0x1800120a0`
- `0x18001434c`
- `0x180014854`
- `0x180014894`
- `0x1800148b4`
- `0x180014914`
- `0x180014938`
- `0x180016338`
- `0x18001be8c`
- `0x18001d630`
- `0x180023d88`
- `0x18002de8c`
- `0x18002f3b0`
- `0x180055878`
- `0x180055928`
- `0x1800559b0`
- `0x1800559c8`
- `0x180058504`
- `0x180060254`
- `0x1800604c0`
- `0x180068f60`
- `0x18006963c`
- `0x180069cc8`
- `0x1800712e4`
- `0x1800714b0`
- `0x18007d06c`
- `0x180080ff4`
- `0x1800bf920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002e4f6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002e4f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e7f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e800`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e7f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e800`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e913`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e0e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e0e1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e04f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e19c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e04f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e19c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dfcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e082`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e12b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e234`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e530`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dfcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e082`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e12b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e234`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e530`

## string_xrefs

- `0x18002df80`: `Service Providers`
- `0x18002df8f`: `Service Providers`
- `0x18002e47f`: `Service Providers`
- `0x18002e48e`: `Service Providers`
- `0x18002df5c`: `System\CurrentControlSet\Services\WbioSrvc\`
- `0x18002df6b`: `System\CurrentControlSet\Services\WbioSrvc\`
- `0x18002e45c`: `System\CurrentControlSet\Services\WbioSrvc\`
- `0x18002e46b`: `System\CurrentControlSet\Services\WbioSrvc\`
- `0x18002e439`: `\\Registry\`
- `0x18002e448`: `\\Registry\`
- `0x18002e524`: `Configurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHardwareManager::ScanForVirtualSensors(CHardwareManager *this)
{
  __int64 v1; // rax
  __int64 v2; // r8
  const WCHAR *v3; // rax
  int v4; // eax
  DWORD i; // r14d
  int v6; // eax
  int ValueW; // eax
  int v8; // eax
  DWORD v9; // esi
  int v10; // eax
  __int64 v11; // rdx
  CHardwareManager *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned int v27; // edx
  int v28; // eax
  CSensorConfigSelector *v29; // rax
  unsigned __int16 *v30; // rdx
  int v31; // edi
  __int64 v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // rcx
  WCHAR *v35; // rax
  unsigned int v36; // ebx
  int v38; // [rsp+40h] [rbp-11C8h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-11C4h] BYREF
  DWORD v40; // [rsp+48h] [rbp-11C0h] BYREF
  DWORD v41; // [rsp+4Ch] [rbp-11BCh]
  int v42; // [rsp+50h] [rbp-11B8h] BYREF
  unsigned int pvData; // [rsp+54h] [rbp-11B4h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-11B0h] BYREF
  HKEY v45; // [rsp+60h] [rbp-11A8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-11A0h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-1198h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-1190h] BYREF
  CSensorConfigSelector *v49; // [rsp+80h] [rbp-1188h]
  HKEY v50; // [rsp+88h] [rbp-1180h] BYREF
  std::_Ref_count_base *v51[2]; // [rsp+90h] [rbp-1178h] BYREF
  CHardwareManager *v52; // [rsp+A0h] [rbp-1168h]
  _BYTE v53[8]; // [rsp+A8h] [rbp-1160h] BYREF
  _BYTE v54[24]; // [rsp+B0h] [rbp-1158h] BYREF
  __int128 v55; // [rsp+C8h] [rbp-1140h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-1130h]
  __int64 v57; // [rsp+E0h] [rbp-1128h]
  _BYTE v58[32]; // [rsp+E8h] [rbp-1120h] BYREF
  _BYTE v59[32]; // [rsp+108h] [rbp-1100h] BYREF
  _BYTE v60[40]; // [rsp+128h] [rbp-10E0h] BYREF
  _BYTE v61[360]; // [rsp+150h] [rbp-10B8h] BYREF
  int v62; // [rsp+2B8h] [rbp-F50h]
  struct _WINBIO_UNIT_SCHEMA v63; // [rsp+360h] [rbp-EA8h] BYREF
  char v64[46]; // [rsp+D80h] [rbp-488h] BYREF
  WCHAR SubKey[264]; // [rsp+DB0h] [rbp-458h] BYREF
  WCHAR Name[264]; // [rsp+FC0h] [rbp-248h] BYREF

  v52 = this;
  v38 = 0;
  v42 = 0;
  strcpy(v64, "CHardwareManager::ScanForVirtualSensors");
  _lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_::_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_(
    (_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_ *)v54,
    (const char (*)[46])v64,
    (enum _WppTraceIndentType *)&v42,
    (struct CBiometricUnit *)&v38);
  lambda_1802c43b285b7af25dd9030127e2d601_::operator()(v54);
  v42 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(v53, v54);
  hKey = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v1 = std::_WChar_traits<unsigned short>::length(L"System\\CurrentControlSet\\Services\\WbioSrvc\\");
  try
  {
    std::wstring::_Construct<1,unsigned short const *>(&v55, L"System\\CurrentControlSet\\Services\\WbioSrvc\\", v1);
    v2 = std::_WChar_traits<unsigned short>::length(L"Service Providers");
    std::wstring::_Append<unsigned short>(&v55, L"Service Providers", v2);
    v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v55);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
    if ( v4 )
    {
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v38 = v4;
    }
    std::wstring::_Tidy_deallocate(&v55);
  }
  catch ( std::bad_alloc )
  {
    v38 = -2147024882;
  }
  std::wstring::_Construct<1,unsigned short const *>(&v55, L"System\\CurrentControlSet\\Services\\WbioSrvc\\", v1);
  v2 = std::_WChar_traits<unsigned short>::length(L"Service Providers");
  std::wstring::_Append<unsigned short>(&v55, L"Service Providers", v2);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v55);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
}

```

## disassembly

```asm
0x18002de8c  push    rbx
0x18002de8e  push    rsi
0x18002de8f  push    rdi
0x18002de90  push    r14
0x18002de92  mov     eax, 11E8h
0x18002de97  call    _alloca_probe
0x18002de9c  sub     rsp, rax
0x18002de9f  mov     rax, cs:__security_cookie
0x18002dea6  xor     rax, rsp
0x18002dea9  mov     [rsp+1208h+var_38], rax
0x18002deb1  mov     [rsp+1208h+var_1168], rcx
0x18002deb9  xor     ebx, ebx
0x18002debb  mov     [rsp+1208h+var_11C8], ebx
0x18002debf  mov     [rsp+1208h+var_11B8], ebx
0x18002dec3  movups  xmm0, xmmword ptr cs:aChardwaremanag_0; "CHardwareManager::ScanForVirtualSensors"
0x18002deca  movups  xmmword ptr [rsp+1208h+var_488], xmm0
0x18002ded2  movups  xmm1, xmmword ptr cs:aChardwaremanag_0+10h; "::ScanForVirtualSensors"
0x18002ded9  movups  xmmword ptr [rsp+1208h+var_488+10h], xmm1
0x18002dee1  movsd   xmm0, qword ptr cs:aChardwaremanag_0+20h; "Sensors"
0x18002dee9  movsd   qword ptr [rsp+1208h+var_488+20h], xmm0
0x18002def2  lea     r9, [rsp+1208h+var_11C8]; struct CBiometricUnit *
0x18002def7  lea     r8, [rsp+1208h+var_11B8]; enum _WppTraceIndentType *
0x18002defc  lea     rdx, [rsp+1208h+var_488]; char (*)[46]
0x18002df04  lea     rcx, [rsp+1208h+var_1158]; this
0x18002df0c  call    ??0_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_@@QEAA@AEAY0CO@$$CBDAEAW4_WppTraceIndentType@@PEAVCBiometricUnit@@@Z; _lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_::_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_(char const (&)[46],_WppTraceIndentType &,CBiometricUnit *)
0x18002df11  lea     rcx, [rsp+1208h+var_1158]
0x18002df19  call    _lambda_1802c43b285b7af25dd9030127e2d601___operator__
0x18002df1e  mov     [rsp+1208h+var_11B8], 1
0x18002df26  lea     rdx, [rsp+1208h+var_1158]
0x18002df2e  lea     rcx, [rsp+1208h+var_1160]
0x18002df36  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18002df3b  nop
0x18002df3c  mov     [rsp+1208h+hKey], rbx
0x18002df41  xorps   xmm0, xmm0
0x18002df44  movups  [rsp+1208h+var_1140], xmm0
0x18002df4c  mov     [rsp+1208h+var_1130], rbx
0x18002df54  mov     [rsp+1208h+var_1128], rbx
0x18002df5c  lea     rcx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Wb"...
0x18002df63  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002df68  mov     r8, rax
0x18002df6b  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Wb"...
0x18002df72  lea     rcx, [rsp+1208h+var_1140]
0x18002df7a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002df7f  nop
0x18002df80  lea     rcx, aServiceProvide; "Service Providers"
0x18002df87  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002df8c  mov     r8, rax
0x18002df8f  lea     rdx, aServiceProvide; "Service Providers"
0x18002df96  lea     rcx, [rsp+1208h+var_1140]
0x18002df9e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002dfa3  lea     rcx, [rsp+1208h+var_1140]
0x18002dfab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002dfb0  mov     rdx, rax; lpSubKey
0x18002dfb3  lea     rax, [rsp+1208h+hKey]
0x18002dfb8  mov     [rsp+1208h+phkResult], rax; phkResult
0x18002dfbd  mov     r9d, 20019h; samDesired
0x18002dfc3  xor     r8d, r8d; ulOptions
0x18002dfc6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dfcd  call    cs:__imp_RegOpenKeyExW
0x18002dfd3  test    eax, eax
0x18002dfd5  jz      short loc_18002DFE5
0x18002dfd7  jle     short loc_18002DFE1
0x18002dfd9  movzx   eax, ax
0x18002dfdc  or      eax, 80070000h
0x18002dfe1  mov     [rsp+1208h+var_11C8], eax
0x18002dfe5  lea     rcx, [rsp+1208h+var_1140]
0x18002dfed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dff2  nop
0x18002dff3  jmp     short loc_18002DFF7
0x18002dff5  xor     ebx, ebx
0x18002dff7  cmp     [rsp+1208h+var_11C8], ebx
0x18002dffb  jl      loc_18002E90E
0x18002e001  xor     edx, edx; Val
0x18002e003  mov     r8d, 208h; Size
0x18002e009  lea     rcx, [rsp+1208h+Name]; void *
0x18002e011  call    memset_0
0x18002e016  mov     [rsp+1208h+cchName], 104h
0x18002e01e  mov     r14d, ebx
0x18002e021  mov     [rsp+1208h+var_11BC], r14d
0x18002e026  mov     [rsp+1208h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18002e02b  mov     [rsp+1208h+lpcchClass], rbx; lpcchClass
0x18002e030  mov     [rsp+1208h+lpClass], rbx; lpClass
0x18002e035  mov     [rsp+1208h+phkResult], rbx; lpReserved
0x18002e03a  lea     r9, [rsp+1208h+cchName]; lpcchName
0x18002e03f  lea     r8, [rsp+1208h+Name]; lpName
0x18002e047  mov     edx, r14d; dwIndex
0x18002e04a  mov     rcx, [rsp+1208h+hKey]; hKey
0x18002e04f  call    cs:__imp_RegEnumKeyExW
0x18002e055  test    eax, eax
0x18002e057  jnz     loc_18002E90E
0x18002e05d  mov     [rsp+1208h+hkey], rbx
0x18002e062  lea     rax, [rsp+1208h+hkey]
0x18002e067  mov     [rsp+1208h+phkResult], rax; phkResult
0x18002e06c  mov     r9d, 20019h; samDesired
0x18002e072  xor     r8d, r8d; ulOptions
0x18002e075  lea     rdx, [rsp+1208h+Name]; lpSubKey
0x18002e07d  mov     rcx, [rsp+1208h+hKey]; hKey
0x18002e082  call    cs:__imp_RegOpenKeyExW
0x18002e088  test    eax, eax
0x18002e08a  jz      short loc_18002E09C
0x18002e08c  jle     short loc_18002E096
0x18002e08e  movzx   eax, ax
0x18002e091  or      eax, 80070000h
0x18002e096  mov     [rsp+1208h+var_11C8], eax
0x18002e09a  jmp     short loc_18002E0A0
0x18002e09c  mov     eax, [rsp+1208h+var_11C8]
0x18002e0a0  mov     [rsp+1208h+pvData], ebx
0x18002e0a4  test    eax, eax
0x18002e0a6  js      loc_18002E8D7
0x18002e0ac  mov     [rsp+1208h+pcbData], 4
0x18002e0b4  lea     rax, [rsp+1208h+pcbData]
0x18002e0b9  mov     [rsp+1208h+lpcchClass], rax; pcbData
0x18002e0be  lea     rax, [rsp+1208h+pvData]
0x18002e0c3  mov     [rsp+1208h+lpClass], rax; pvData
0x18002e0c8  mov     [rsp+1208h+phkResult], rbx; pdwType
0x18002e0cd  mov     r9d, 10h; dwFlags
0x18002e0d3  lea     r8, aBiometrictype; "BiometricType"
0x18002e0da  xor     edx, edx; lpSubKey
0x18002e0dc  mov     rcx, [rsp+1208h+hkey]; hkey
0x18002e0e1  call    cs:__imp_RegGetValueW
0x18002e0e7  test    eax, eax
0x18002e0e9  jz      short loc_18002E0FB
0x18002e0eb  jle     short loc_18002E0F5
0x18002e0ed  movzx   eax, ax
0x18002e0f0  or      eax, 80070000h
0x18002e0f5  mov     [rsp+1208h+var_11C8], eax
0x18002e0f9  jmp     short loc_18002E0FF
0x18002e0fb  mov     eax, [rsp+1208h+var_11C8]
0x18002e0ff  test    eax, eax
0x18002e101  js      loc_18002E8D7
0x18002e107  mov     [rsp+1208h+var_11A0], rbx
0x18002e10c  lea     rax, [rsp+1208h+var_11A0]
0x18002e111  mov     [rsp+1208h+phkResult], rax; phkResult
0x18002e116  mov     r9d, 20019h; samDesired
0x18002e11c  xor     r8d, r8d; ulOptions
0x18002e11f  lea     rdx, aVirtualSensors; "Virtual Sensors"
0x18002e126  mov     rcx, [rsp+1208h+hkey]; hKey
0x18002e12b  call    cs:__imp_RegOpenKeyExW
0x18002e131  test    eax, eax
0x18002e133  jz      short loc_18002E145
0x18002e135  jle     short loc_18002E13F
0x18002e137  movzx   eax, ax
0x18002e13a  or      eax, 80070000h
0x18002e13f  mov     [rsp+1208h+var_11C8], eax
0x18002e143  jmp     short loc_18002E149
0x18002e145  mov     eax, [rsp+1208h+var_11C8]
0x18002e149  test    eax, eax
0x18002e14b  js      loc_18002E8CC
0x18002e151  xor     edx, edx; Val
0x18002e153  mov     r8d, 208h; Size
0x18002e159  lea     rcx, [rsp+1208h+SubKey]; void *
0x18002e161  call    memset_0
0x18002e166  mov     [rsp+1208h+var_11C0], 104h
0x18002e16e  mov     esi, ebx
0x18002e170  mov     [rsp+1208h+pcbData], ebx
0x18002e174  mov     [rsp+1208h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18002e179  mov     [rsp+1208h+lpcchClass], rbx; lpcchClass
0x18002e17e  mov     [rsp+1208h+lpClass], rbx; lpClass
0x18002e183  mov     [rsp+1208h+phkResult], rbx; lpReserved
0x18002e188  lea     r9, [rsp+1208h+var_11C0]; lpcchName
0x18002e18d  lea     r8, [rsp+1208h+SubKey]; lpName
0x18002e195  mov     edx, esi; dwIndex
0x18002e197  mov     rcx, [rsp+1208h+var_11A0]; hKey
0x18002e19c  call    cs:__imp_RegEnumKeyExW
0x18002e1a2  test    eax, eax
0x18002e1a4  jnz     loc_18002E8CC
0x18002e1aa  cmp     [rsp+1208h+var_11C0], 26h ; '&'
0x18002e1af  jnz     loc_18002E863
0x18002e1b5  cmp     [rsp+1208h+SubKey], 7Bh ; '{'
0x18002e1be  jnz     loc_18002E863
0x18002e1c4  cmp     [rsp+1208h+var_446], 2Dh ; '-'
0x18002e1cd  jnz     loc_18002E863
0x18002e1d3  cmp     [rsp+1208h+var_43C], 2Dh ; '-'
0x18002e1dc  jnz     loc_18002E863
0x18002e1e2  cmp     [rsp+1208h+var_432], 2Dh ; '-'
0x18002e1eb  jnz     loc_18002E863
0x18002e1f1  cmp     [rsp+1208h+var_428], 2Dh ; '-'
0x18002e1fa  jnz     loc_18002E863
0x18002e200  cmp     [rsp+1208h+var_40E], 7Dh ; '}'
0x18002e209  jnz     loc_18002E863
0x18002e20f  mov     [rsp+1208h+var_11A8], rbx
0x18002e214  lea     rax, [rsp+1208h+var_11A8]
0x18002e219  mov     [rsp+1208h+phkResult], rax; phkResult
0x18002e21e  mov     r9d, 20019h; samDesired
0x18002e224  xor     r8d, r8d; ulOptions
0x18002e227  lea     rdx, [rsp+1208h+SubKey]; lpSubKey
0x18002e22f  mov     rcx, [rsp+1208h+var_11A0]; hKey
0x18002e234  call    cs:__imp_RegOpenKeyExW
0x18002e23a  test    eax, eax
0x18002e23c  jz      short loc_18002E2A8
0x18002e23e  jle     short loc_18002E248
0x18002e240  movzx   eax, ax
0x18002e243  or      eax, 80070000h
0x18002e248  mov     [rsp+1208h+var_11C8], eax
0x18002e24c  lea     rcx, [rsp+1208h+var_10B8]; this
0x18002e254  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18002e259  nop
0x18002e25a  lea     r8, [rsp+1208h+SubKey]; unsigned __int16 *
0x18002e262  lea     rdx, [rsp+1208h+Name]; unsigned __int16 *
0x18002e26a  lea     rcx, [rsp+1208h+var_10B8]; this
0x18002e272  call    ?CaptureSensorInfo@CEtwEvent@@QEAAXPEBG0@Z; CEtwEvent::CaptureSensorInfo(ushort const *,ushort const *)
0x18002e277  mov     eax, [rsp+1208h+var_11C8]
0x18002e27b  mov     [rsp+1208h+var_F50], eax
0x18002e282  mov     edx, 456h
0x18002e287  mov     r8d, 1
0x18002e28d  lea     rcx, [rsp+1208h+var_10B8]
0x18002e295  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18002e29a  nop
0x18002e29b  lea     rcx, [rsp+1208h+var_10B8]; this
0x18002e2a3  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18002e2a8  xor     edx, edx; Val
0x18002e2aa  mov     r8d, 0A1Ch; Size
0x18002e2b0  lea     rcx, [rsp+1208h+var_EA8]; void *
0x18002e2b8  call    memset_0
0x18002e2bd  cmp     [rsp+1208h+var_11C8], ebx
0x18002e2c1  jl      short loc_18002E33D
0x18002e2c3  lea     r9, [rsp+1208h+var_EA8]; struct _WINBIO_UNIT_SCHEMA *
0x18002e2cb  mov     r8, [rsp+1208h+var_11A8]; HKEY
0x18002e2d0  mov     edx, [rsp+1208h+pvData]; unsigned int
0x18002e2d4  call    ?LoadVirtualSensorAttributes@CHardwareManager@@AEAAJIPEAUHKEY__@@AEAU_WINBIO_UNIT_SCHEMA@@@Z; CHardwareManager::LoadVirtualSensorAttributes(uint,HKEY__ *,_WINBIO_UNIT_SCHEMA &)
0x18002e2d9  mov     [rsp+1208h+var_11C8], eax
0x18002e2dd  test    eax, eax
0x18002e2df  jns     short loc_18002E33D
0x18002e2e1  lea     rcx, [rsp+1208h+var_10B8]; this
0x18002e2e9  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18002e2ee  nop
0x18002e2ef  lea     r8, [rsp+1208h+SubKey]; unsigned __int16 *
0x18002e2f7  lea     rdx, [rsp+1208h+Name]; unsigned __int16 *
0x18002e2ff  lea     rcx, [rsp+1208h+var_10B8]; this
0x18002e307  call    ?CaptureSensorInfo@CEtwEvent@@QEAAXPEBG0@Z; CEtwEvent::CaptureSensorInfo(ushort const *,ushort const *)
0x18002e30c  mov     eax, [rsp+1208h+var_11C8]
0x18002e310  mov     [rsp+1208h+var_F50], eax
0x18002e317  mov     edx, 456h
0x18002e31c  mov     r8d, 1
0x18002e322  lea     rcx, [rsp+1208h+var_10B8]
0x18002e32a  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18002e32f  nop
0x18002e330  lea     rcx, [rsp+1208h+var_10B8]; this
0x18002e338  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18002e33d  lea     rcx, [rsp+1208h+var_1140]
0x18002e345  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e34a  nop
0x18002e34b  lea     rcx, [rsp+1208h+var_1120]
0x18002e353  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e358  nop
0x18002e359  cmp     [rsp+1208h+var_11C8], ebx
0x18002e35d  jl      loc_18002E4D5
0x18002e363  lea     rcx, asc_1800DC1E4; "\\"
0x18002e36a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e36f  mov     r8, rax
0x18002e372  lea     rdx, asc_1800DC1E4; "\\"
0x18002e379  lea     rcx, [rsp+1208h+var_1140]
0x18002e381  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002e386  lea     rcx, [rsp+1208h+Name]
0x18002e38e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e393  mov     r8, rax
0x18002e396  lea     rdx, [rsp+1208h+Name]
0x18002e39e  lea     rcx, [rsp+1208h+var_1140]
0x18002e3a6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002e3ab  lea     rcx, asc_1800DC1E4; "\\"
0x18002e3b2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e3b7  mov     r8, rax
0x18002e3ba  lea     rdx, asc_1800DC1E4; "\\"
0x18002e3c1  lea     rcx, [rsp+1208h+var_1140]
0x18002e3c9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002e3ce  lea     rcx, aVirtualSensors; "Virtual Sensors"
0x18002e3d5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e3da  mov     r8, rax
0x18002e3dd  lea     rdx, aVirtualSensors; "Virtual Sensors"
0x18002e3e4  lea     rcx, [rsp+1208h+var_1140]
0x18002e3ec  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002e3f1  lea     rcx, asc_1800DC1E4; "\\"
0x18002e3f8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e3fd  mov     r8, rax
0x18002e400  lea     rdx, asc_1800DC1E4; "\\"
0x18002e407  lea     rcx, [rsp+1208h+var_1140]
0x18002e40f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002e414  lea     rcx, [rsp+1208h+SubKey]
0x18002e41c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e421  mov     r8, rax
0x18002e424  lea     rdx, [rsp+1208h+SubKey]
0x18002e42c  lea     rcx, [rsp+1208h+var_1140]
0x18002e434  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002e439  lea     rcx, aRegistry; "\\\\Registry\\"
0x18002e440  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e445  mov     r8, rax
0x18002e448  lea     rdx, aRegistry; "\\\\Registry\\"
0x18002e44f  lea     rcx, [rsp+1208h+var_1120]
0x18002e457  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002e45c  lea     rcx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Wb"...
0x18002e463  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e468  mov     r8, rax
0x18002e46b  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Wb"...
0x18002e472  lea     rcx, [rsp+1208h+var_1120]
0x18002e47a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002e47f  lea     rcx, aServiceProvide; "Service Providers"
0x18002e486  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002e48b  mov     r8, rax
0x18002e48e  lea     rdx, aServiceProvide; "Service Providers"
0x18002e495  lea     rcx, [rsp+1208h+var_1120]
  ... truncated ...
```
