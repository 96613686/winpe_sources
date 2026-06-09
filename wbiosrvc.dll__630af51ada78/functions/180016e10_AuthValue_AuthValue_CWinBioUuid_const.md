# AuthValue::AuthValue(CWinBioUuid const &)

- ea: `0x180016e10`
- end: `0x180017392`
- name: `??0AuthValue@@QEAA@AEBVCWinBioUuid@@@Z`
- size: `1410`
- prototype: `AuthValue *__fastcall(AuthValue *this, const struct CWinBioUuid *, __int64, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e8dc`
- `0x180063cf8`

## callees

- `0x18000367c`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x1800148b4`
- `0x180014914`
- `0x180016968`
- `0x180016e10`
- `0x180017398`
- `0x180017658`
- `0x180035d98`
- `0x18003f80c`
- `0x180046aa8`
- `0x1800530c4`
- `0x180058504`
- `0x180060254`
- `0x180068f60`
- `0x180069cc8`
- `0x180072da0`
- `0x1800967e0`
- `0x180096874`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017357`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016f40`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016f40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016fb3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001700c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001708b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017154`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800171d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017266`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016fb3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001700c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001708b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017154`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800171d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017266`

## string_xrefs

- `0x180016e87`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180016eb5`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x1800170e2`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180017197`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x1800172ab`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x18001707a`: `BioServiceKey`
- `0x180017146`: `BioServiceKey`
- `0x1800170d6`: `Failed to read %ls [%ls]`
- `0x18001718b`: `Failed to read %ls [%ls]`
- `0x18001729f`: `Failed to read %ls [%ls]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
AuthValue *__fastcall AuthValue::AuthValue(AuthValue *this, const struct CWinBioUuid *a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rcx
  HKEY *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int WinBioRegistryLocation; // eax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // r8d
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  LSTATUS ValueW; // r9d
  unsigned int v26; // eax
  unsigned int v27; // r8d
  __int64 v28; // rcx
  unsigned int v29; // eax
  __int64 v30; // r8
  char *v31; // rsi
  char *v32; // rax
  const char *v33; // rax
  const char *v34; // r9
  size_t v35; // rbx
  unsigned int v36; // eax
  unsigned int v37; // r8d
  const char *v38; // rax
  const char *v39; // r9
  unsigned int v40; // eax
  __int64 v41; // r8
  char *v42; // rsi
  char *v43; // rax
  size_t v44; // rbx
  unsigned int v45; // eax
  unsigned int v46; // r8d
  const char *v47; // rax
  const char *v48; // r9
  int dwOptions; // [rsp+20h] [rbp-B9h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-B9h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-B9h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-B9h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-B9h]
  DWORD pcbData; // [rsp+50h] [rbp-89h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-81h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-79h] BYREF
  PVOID v58[2]; // [rsp+68h] [rbp-71h] BYREF
  __int64 v59; // [rsp+78h] [rbp-61h]
  PVOID v60[2]; // [rsp+80h] [rbp-59h] BYREF
  __int64 v61; // [rsp+90h] [rbp-49h]
  PVOID pvData[2]; // [rsp+98h] [rbp-41h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-31h]
  AuthValue *v64; // [rsp+B0h] [rbp-29h]
  _BYTE v65[32]; // [rsp+B8h] [rbp-21h] BYREF
  _BYTE v66[32]; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v64 = this;
  std::wstring::wstring(this, a2, a2, a4);
  v6 = (HKEY *)(v5 + 32);
  *(_QWORD *)(v5 + 32) = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v5 + 40);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((char *)this + 64);
  std::wstring::wstring((char *)this + 88, v7, v8, v9);
  v11 = CWinBioUuid::ToString(v10, this);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
      (const char *)(unsigned int)v11,
      dwOptions);
  std::wstring::wstring(v65, v12, v13, v14);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v65);
  if ( WinBioRegistryLocation < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      dwOptions);
  v16 = std::_WChar_traits<unsigned short>::length(L"SensorInfo\\");
  std::wstring::_Append<unsigned short>(v65, v17, v16);
  v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
  std::wstring::_Append<unsigned short>(v65, v18, *((_QWORD *)this + 2));
  dwDisposition = 0;
  hkey = 0;
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
  v20 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0, 0, 0xF003Fu, 0, &hkey, &dwDisposition);
  if ( v20 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x3F, v21, (const char *)v20, dwOptionsa);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v60);
  std::wstring::wstring(v66, v22, v23, v24);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v58);
  if ( dwDisposition != 2 )
    goto LABEL_39;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, L"TpmKeyName", 2u, 0, 0, &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v33 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
        v34,
        (unsigned int)"Failed to read %ls [%ls]",
        v33,
        L"TpmKeyName");
    }
  }
  else
  {
    *(_OWORD *)pvData = 0;
    v63 = 0;
    std::vector<unsigned short>::_Construct_n<>(pvData, ((unsigned __int64)pcbData >> 1) + 1);
    v26 = RegGetValueW(hkey, 0, L"TpmKeyName", 2u, 0, pvData[0], &pcbData);
    if ( v26 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x5D, v27, (const char *)v26, dwOptionsb);
    std::_WChar_traits<unsigned short>::length(pvData[0]);
    std::wstring::_Assign<unsigned short>(v66, v28);
    if ( pvData[0] )
      std::_Deallocate<16>(pvData[0], 2 * ((signed __int64)(v63 - (unsigned __int64)pvData[0]) >> 1));
  }
  pcbData = 0;
  v29 = RegGetValueW(hkey, 0, L"BioServiceKey", 8u, 0, 0, &pcbData);
  if ( v29 )
  {
    if ( v29 != 2 )
    {
      v38 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
        v39,
        (unsigned int)"Failed to read %ls [%ls]",
        v38,
        L"BioServiceKey");
    }
    goto LABEL_27;
  }
  v31 = (char *)v58[1];
  if ( (PVOID)pcbData >= (PVOID)((char *)v58[1] - (char *)v58[0]) )
  {
    if ( (PVOID)pcbData <= (PVOID)((char *)v58[1] - (char *)v58[0]) )
      goto LABEL_23;
    if ( pcbData > v59 - (unsigned __int64)v58[0] )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v58, pcbData, v30, v29);
      goto LABEL_23;
    }
    v35 = pcbData - (unsigned __int64)((char *)v58[1] - (char *)v58[0]);
    memset_0(v58[1], 0, v35);
    v32 = &v31[v35];
  }
  else
  {
    v32 = (char *)v58[0] + pcbData;
  }
  v58[1] = v32;
LABEL_23:
  v36 = RegGetValueW(hkey, 0, L"BioServiceKey", 8u, 0, v58[0], &pcbData);
  if ( v36 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x7E, v37, (const char *)v36, dwOptionsc);
LABEL_27:
  pcbData = 0;
  v40 = RegGetValueW(hkey, 0, L"SensorKeyIdentifier", 8u, 0, 0, &pcbData);
  if ( !v40 )
  {
    v42 = (char *)v60[1];
    if ( (PVOID)pcbData >= (PVOID)((char *)v60[1] - (char *)v60[0]) )
    {
      if ( (PVOID)pcbData <= (PVOID)((char *)v60[1] - (char *)v60[0]) )
        goto LABEL_35;
      if ( pcbData > v61 - (unsigned __int64)v60[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v60, pcbData, v41, v40);
        goto LABEL_35;
      }
      v44 = pcbData - (unsigned __int64)((char *)v60[1] - (char *)v60[0]);
      memset_0(v60[1], 0, v44);
      v43 = &v42[v44];
    }
    else
    {
      v43 = (char *)v60[0] + pcbData;
    }
    v60[1] = v43;
LABEL_35:
    v45 = RegGetValueW(hkey, 0, L"SensorKeyIdentifier", 8u, 0, v60[0], &pcbData);
    if ( v45 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x9D, v46, (const char *)v45, dwOptionsd);
    goto LABEL_39;
  }
  if ( v40 != 2 )
  {
    v47 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
      v48,
      (unsigned int)"Failed to read %ls [%ls]",
      v47,
      L"SensorKeyIdentifier");
  }
LABEL_39:
  if ( v6 != &hkey )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v6,
      hkey);
    hkey = 0;
  }
  std::vector<unsigned char>::operator=((char *)this + 64, v60);
  std::wstring::operator=((char *)this + 88, v66);
  std::vector<unsigned char>::operator=((char *)this + 40, v58);
  if ( v58[0] )
  {
    std::_Deallocate<16>(v58[0], v59 - (unsigned __int64)v58[0]);
    *(_OWORD *)v58 = 0;
    v59 = 0;
  }
  std::wstring::_Tidy_deallocate(v66);
  if ( v60[0] )
  {
    std::_Deallocate<16>(v60[0], v61 - (unsigned __int64)v60[0]);
    *(_OWORD *)v60 = 0;
    v61 = 0;
  }
  if ( hkey )
    RegCloseKey(hkey);
  std::wstring::_Tidy_deallocate(v65);
  return this;
}

```

## disassembly

```asm
0x180016e10  mov     [rsp-8+arg_10], rbx
0x180016e15  push    rbp
0x180016e16  push    rsi
0x180016e17  push    rdi
0x180016e18  push    r12
0x180016e1a  push    r13
0x180016e1c  push    r14
0x180016e1e  push    r15
0x180016e20  lea     rbp, [rsp-27h]
0x180016e25  sub     rsp, 100h
0x180016e2c  mov     rax, cs:__security_cookie
0x180016e33  xor     rax, rsp
0x180016e36  mov     [rbp+57h+var_38], rax
0x180016e3a  mov     r8, rdx
0x180016e3d  mov     rdi, rcx
0x180016e40  mov     [rbp+57h+var_80], rcx
0x180016e44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016e49  nop
0x180016e4a  lea     r14, [rcx+20h]
0x180016e4e  xor     ebx, ebx
0x180016e50  mov     [r14], rbx
0x180016e53  add     rcx, 28h ; '('
0x180016e57  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180016e5c  nop
0x180016e5d  lea     rcx, [rdi+40h]
0x180016e61  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180016e66  nop
0x180016e67  lea     rcx, [rdi+58h]
0x180016e6b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016e70  nop
0x180016e71  mov     rdx, rdi
0x180016e74  mov     rcx, r8
0x180016e77  call    ?ToString@CWinBioUuid@@QEBAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CWinBioUuid::ToString(std::wstring *)
0x180016e7c  mov     rcx, [rbp+5Fh]; this
0x180016e80  test    eax, eax
0x180016e82  jns     short loc_180016E97
0x180016e84  mov     r9d, eax; char *
0x180016e87  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180016e8e  lea     edx, [rbx+2Ah]; void *
0x180016e91  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016e97  lea     rcx, [rbp+57h+var_78]
0x180016e9b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016ea0  nop
0x180016ea1  lea     rcx, [rbp+57h+var_78]
0x180016ea5  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180016eaa  mov     rcx, [rbp+5Fh]; this
0x180016eae  test    eax, eax
0x180016eb0  jns     short loc_180016EC7
0x180016eb2  mov     r9d, eax; char *
0x180016eb5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180016ebc  mov     edx, 2Fh ; '/'; void *
0x180016ec1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016ec7  lea     rcx, aSensorinfo; "SensorInfo\\"
0x180016ece  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180016ed3  mov     r8, rax
0x180016ed6  mov     rdx, rcx
0x180016ed9  lea     rcx, [rbp+57h+var_78]
0x180016edd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180016ee2  mov     rcx, rdi
0x180016ee5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016eea  mov     r8, [rdi+10h]
0x180016eee  mov     rdx, rax
0x180016ef1  lea     rcx, [rbp+57h+var_78]
0x180016ef5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180016efa  nop
0x180016efb  mov     [rbp+57h+dwDisposition], ebx
0x180016efe  mov     [rsp+130h+hkey], rbx
0x180016f03  lea     rcx, [rbp+57h+var_78]
0x180016f07  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016f0c  mov     rdx, rax; lpSubKey
0x180016f0f  lea     rax, [rbp+57h+dwDisposition]
0x180016f13  mov     [rsp+130h+lpdwDisposition], rax; lpdwDisposition
0x180016f18  lea     rax, [rsp+130h+hkey]
0x180016f1d  mov     [rsp+130h+phkResult], rax; phkResult
0x180016f22  mov     [rsp+130h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180016f27  mov     [rsp+130h+samDesired], 0F003Fh; samDesired
0x180016f2f  mov     [rsp+130h+dwOptions], ebx; unsigned int
0x180016f33  xor     r9d, r9d; lpClass
0x180016f36  xor     r8d, r8d; Reserved
0x180016f39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016f40  call    cs:__imp_RegCreateKeyExW
0x180016f46  mov     rcx, [rbp+5Fh]; this
0x180016f4a  test    eax, eax
0x180016f4c  jz      short loc_180016F5C
0x180016f4e  mov     r9d, eax; char *
0x180016f51  mov     edx, 3Fh ; '?'; void *
0x180016f56  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180016f5c  lea     rcx, [rbp+57h+var_B0]
0x180016f60  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180016f65  nop
0x180016f66  lea     rcx, [rbp+57h+var_58]
0x180016f6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016f6f  nop
0x180016f70  lea     rcx, [rbp+57h+var_C8]
0x180016f74  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180016f79  nop
0x180016f7a  cmp     [rbp+57h+dwDisposition], 2
0x180016f7e  jnz     loc_1800172BD
0x180016f84  mov     [rsp+130h+pcbData], ebx
0x180016f88  lea     rax, [rsp+130h+pcbData]
0x180016f8d  mov     [rsp+130h+lpSecurityAttributes], rax; pcbData
0x180016f92  mov     qword ptr [rsp+130h+samDesired], rbx; pvData
0x180016f97  mov     qword ptr [rsp+130h+dwOptions], rbx; pdwType
0x180016f9c  mov     r9d, 2; dwFlags
0x180016fa2  lea     rsi, aTpmkeyname; "TpmKeyName"
0x180016fa9  mov     r8, rsi; lpValue
0x180016fac  xor     edx, edx; lpSubKey
0x180016fae  mov     rcx, [rsp+130h+hkey]; hkey
0x180016fb3  call    cs:__imp_RegGetValueW
0x180016fb9  mov     r9d, eax
0x180016fbc  test    eax, eax
0x180016fbe  jnz     loc_1800170B9
0x180016fc4  xorps   xmm0, xmm0
0x180016fc7  movdqu  xmmword ptr [rbp+57h+pvData], xmm0
0x180016fcc  mov     [rbp+57h+var_88], rbx
0x180016fd0  mov     edx, [rsp+130h+pcbData]
0x180016fd4  shr     rdx, 1
0x180016fd7  inc     rdx
0x180016fda  lea     rcx, [rbp+57h+pvData]
0x180016fde  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x180016fe3  nop
0x180016fe4  mov     rax, [rbp+57h+pvData]
0x180016fe8  lea     rcx, [rsp+130h+pcbData]
0x180016fed  mov     [rsp+130h+lpSecurityAttributes], rcx; pcbData
0x180016ff2  mov     qword ptr [rsp+130h+samDesired], rax; pvData
0x180016ff7  mov     qword ptr [rsp+130h+dwOptions], rbx; unsigned int
0x180016ffc  mov     r9d, 2; dwFlags
0x180017002  mov     r8, rsi; lpValue
0x180017005  xor     edx, edx; lpSubKey
0x180017007  mov     rcx, [rsp+130h+hkey]; hkey
0x18001700c  call    cs:__imp_RegGetValueW
0x180017012  mov     rcx, [rbp+5Fh]; this
0x180017016  test    eax, eax
0x180017018  jz      short loc_180017028
0x18001701a  mov     r9d, eax; char *
0x18001701d  mov     edx, 5Dh ; ']'; void *
0x180017022  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180017028  mov     rcx, [rbp+57h+pvData]
0x18001702c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180017031  mov     r8, rax
0x180017034  mov     rdx, rcx
0x180017037  lea     rcx, [rbp+57h+var_58]
0x18001703b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180017040  nop
0x180017041  mov     rcx, [rbp+57h+pvData]
0x180017045  test    rcx, rcx
0x180017048  jz      short loc_18001705C
0x18001704a  mov     rdx, [rbp+57h+var_88]
0x18001704e  sub     rdx, rcx
0x180017051  sar     rdx, 1
0x180017054  add     rdx, rdx
0x180017057  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001705c  mov     [rsp+130h+pcbData], ebx
0x180017060  lea     rax, [rsp+130h+pcbData]
0x180017065  mov     [rsp+130h+lpSecurityAttributes], rax; pcbData
0x18001706a  mov     qword ptr [rsp+130h+samDesired], rbx; pvData
0x18001706f  mov     qword ptr [rsp+130h+dwOptions], rbx; pdwType
0x180017074  mov     r9d, 8; dwFlags
0x18001707a  lea     rsi, aBioservicekey; "BioServiceKey"
0x180017081  mov     r8, rsi; lpValue
0x180017084  xor     edx, edx; lpSubKey
0x180017086  mov     rcx, [rsp+130h+hkey]; hkey
0x18001708b  call    cs:__imp_RegGetValueW
0x180017091  mov     r9d, eax
0x180017094  test    eax, eax
0x180017096  jnz     loc_18001716E
0x18001709c  mov     ebx, [rsp+130h+pcbData]
0x1800170a0  mov     rdx, [rbp+57h+var_C8]
0x1800170a4  mov     rsi, [rbp+57h+var_C8+8]
0x1800170a8  mov     rcx, rsi
0x1800170ab  sub     rcx, rdx
0x1800170ae  cmp     rbx, rcx
0x1800170b1  jnb     short loc_1800170F4
0x1800170b3  lea     rax, [rbx+rdx]
0x1800170b7  jmp     short loc_180017124
0x1800170b9  cmp     r9d, 2
0x1800170bd  jz      short loc_18001705C
0x1800170bf  lea     rcx, [rbp+57h+var_78]
0x1800170c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800170c8  mov     rcx, [rbp+5Fh]; this
0x1800170cc  mov     [rsp+130h+lpSecurityAttributes], rsi
0x1800170d1  mov     qword ptr [rsp+130h+samDesired], rax; char *
0x1800170d6  lea     rax, aFailedToReadLs; "Failed to read %ls [%ls]"
0x1800170dd  mov     qword ptr [rsp+130h+dwOptions], rax; unsigned int
0x1800170e2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x1800170e9  mov     edx, 67h ; 'g'; void *
0x1800170ee  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800170f4  jbe     short loc_180017128
0x1800170f6  mov     rax, [rbp+57h+var_B8]
0x1800170fa  sub     rax, rdx
0x1800170fd  cmp     rbx, rax
0x180017100  jbe     short loc_180017110
0x180017102  mov     rdx, rbx
0x180017105  lea     rcx, [rbp+57h+var_C8]
0x180017109  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001710e  jmp     short loc_180017128
0x180017110  sub     rbx, rcx
0x180017113  mov     r8, rbx; Size
0x180017116  xor     edx, edx; Val
0x180017118  mov     rcx, rsi; void *
0x18001711b  call    memset_0
0x180017120  lea     rax, [rbx+rsi]
0x180017124  mov     [rbp+57h+var_C8+8], rax
0x180017128  mov     rax, [rbp+57h+var_C8]
0x18001712c  lea     rcx, [rsp+130h+pcbData]
0x180017131  mov     [rsp+130h+lpSecurityAttributes], rcx; pcbData
0x180017136  mov     qword ptr [rsp+130h+samDesired], rax; pvData
0x18001713b  xor     ebx, ebx
0x18001713d  mov     qword ptr [rsp+130h+dwOptions], rbx; unsigned int
0x180017142  lea     r9d, [rbx+8]; dwFlags
0x180017146  lea     r8, aBioservicekey; "BioServiceKey"
0x18001714d  xor     edx, edx; lpSubKey
0x18001714f  mov     rcx, [rsp+130h+hkey]; hkey
0x180017154  call    cs:__imp_RegGetValueW
0x18001715a  mov     rcx, [rbp+5Fh]; this
0x18001715e  test    eax, eax
0x180017160  jz      short loc_1800171A9
0x180017162  mov     r9d, eax; char *
0x180017165  lea     edx, [rbx+7Eh]; void *
0x180017168  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001716e  cmp     r9d, 2
0x180017172  jz      short loc_1800171A9
0x180017174  lea     rcx, [rbp+57h+var_78]
0x180017178  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001717d  mov     rcx, [rbp+5Fh]; this
0x180017181  mov     [rsp+130h+lpSecurityAttributes], rsi
0x180017186  mov     qword ptr [rsp+130h+samDesired], rax; char *
0x18001718b  lea     rax, aFailedToReadLs; "Failed to read %ls [%ls]"
0x180017192  mov     qword ptr [rsp+130h+dwOptions], rax; unsigned int
0x180017197  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x18001719e  mov     edx, 86h; void *
0x1800171a3  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800171a9  mov     [rsp+130h+pcbData], ebx
0x1800171ad  lea     rax, [rsp+130h+pcbData]
0x1800171b2  mov     [rsp+130h+lpSecurityAttributes], rax; pcbData
0x1800171b7  mov     qword ptr [rsp+130h+samDesired], rbx; pvData
0x1800171bc  mov     qword ptr [rsp+130h+dwOptions], rbx; pdwType
0x1800171c1  mov     r9d, 8; dwFlags
0x1800171c7  lea     rsi, aSensorkeyident; "SensorKeyIdentifier"
0x1800171ce  mov     r8, rsi; lpValue
0x1800171d1  xor     edx, edx; lpSubKey
0x1800171d3  mov     rcx, [rsp+130h+hkey]; hkey
0x1800171d8  call    cs:__imp_RegGetValueW
0x1800171de  mov     r9d, eax
0x1800171e1  test    eax, eax
0x1800171e3  jnz     loc_180017282
0x1800171e9  mov     ebx, [rsp+130h+pcbData]
0x1800171ed  mov     rdx, [rbp+57h+var_B0]
0x1800171f1  mov     rsi, [rbp+57h+var_B0+8]
0x1800171f5  mov     rcx, rsi
0x1800171f8  sub     rcx, rdx
0x1800171fb  cmp     rbx, rcx
0x1800171fe  jnb     short loc_180017206
0x180017200  lea     rax, [rbx+rdx]
0x180017204  jmp     short loc_180017236
0x180017206  jbe     short loc_18001723A
0x180017208  mov     rax, [rbp+57h+var_A0]
0x18001720c  sub     rax, rdx
0x18001720f  cmp     rbx, rax
0x180017212  jbe     short loc_180017222
0x180017214  mov     rdx, rbx
0x180017217  lea     rcx, [rbp+57h+var_B0]
0x18001721b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180017220  jmp     short loc_18001723A
0x180017222  sub     rbx, rcx
0x180017225  mov     r8, rbx; Size
0x180017228  xor     edx, edx; Val
0x18001722a  mov     rcx, rsi; void *
0x18001722d  call    memset_0
0x180017232  lea     rax, [rbx+rsi]
0x180017236  mov     [rbp+57h+var_B0+8], rax
0x18001723a  mov     rax, [rbp+57h+var_B0]
0x18001723e  lea     rcx, [rsp+130h+pcbData]
0x180017243  mov     [rsp+130h+lpSecurityAttributes], rcx; pcbData
0x180017248  mov     qword ptr [rsp+130h+samDesired], rax; pvData
0x18001724d  xor     ebx, ebx
0x18001724f  mov     qword ptr [rsp+130h+dwOptions], rbx; unsigned int
0x180017254  lea     r9d, [rbx+8]; dwFlags
0x180017258  lea     r8, aSensorkeyident; "SensorKeyIdentifier"
0x18001725f  xor     edx, edx; lpSubKey
0x180017261  mov     rcx, [rsp+130h+hkey]; hkey
0x180017266  call    cs:__imp_RegGetValueW
0x18001726c  mov     rcx, [rbp+5Fh]; this
0x180017270  test    eax, eax
0x180017272  jz      short loc_1800172BD
0x180017274  mov     r9d, eax; char *
0x180017277  mov     edx, 9Dh; void *
0x18001727c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180017282  cmp     r9d, 2
0x180017286  jz      short loc_1800172BD
0x180017288  lea     rcx, [rbp+57h+var_78]
0x18001728c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017291  mov     rcx, [rbp+5Fh]; this
0x180017295  mov     [rsp+130h+lpSecurityAttributes], rsi
0x18001729a  mov     qword ptr [rsp+130h+samDesired], rax; char *
0x18001729f  lea     rax, aFailedToReadLs; "Failed to read %ls [%ls]"
0x1800172a6  mov     qword ptr [rsp+130h+dwOptions], rax; unsigned int
0x1800172ab  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x1800172b2  mov     edx, 0A5h; void *
0x1800172b7  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
  ... truncated ...
```
