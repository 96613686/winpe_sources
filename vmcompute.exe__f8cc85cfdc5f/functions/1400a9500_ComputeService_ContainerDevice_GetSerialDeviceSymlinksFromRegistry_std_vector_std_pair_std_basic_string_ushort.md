# ComputeService::ContainerDevice::GetSerialDeviceSymlinksFromRegistry(std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x1400a9500`
- end: `0x1400a97bf`
- name: `?GetSerialDeviceSymlinksFromRegistry@ContainerDevice@ComputeService@@YAJAEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x14021235c`

## callees

- `0x14001d490`
- `0x140077dbc`
- `0x1400a94dc`
- `0x1400a9500`
- `0x1400a97c8`
- `0x1400e4f40`
- `0x1400f4da8`
- `0x1401332f0`
- `0x140211694`
- `0x140218290`
- `0x140218618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400a96c6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400a96c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400a9572`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400a9572`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a9712`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a9712`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400a95da`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400a963c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400a95da`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400a963c`

## string_xrefs

- `0x1400a9771`: `onecore\vm\compute\management\shared\container\containerdevices.cpp`
- `0x1400a9564`: `HARDWARE\DEVICEMAP\SERIALCOMM`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ComputeService::ContainerDevice::GetSerialDeviceSymlinksFromRegistry(__int64 a1)
{
  unsigned int v2; // edi
  LSTATUS ValueW; // eax
  bool v4; // cc
  unsigned int v5; // eax
  __int64 v6; // rdx
  DWORD v7; // esi
  __int64 v8; // rax
  __int64 v9; // rax
  PVOID v10; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-99h]
  _BYTE v13[8]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v14[8]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v16[32]; // [rsp+90h] [rbp-29h] BYREF
  DWORD cbMaxValueLen; // [rsp+B0h] [rbp-9h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+B4h] [rbp-5h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-1h] BYREF
  DWORD cValues; // [rsp+C0h] [rbp+7h] BYREF
  DWORD Type; // [rsp+C4h] [rbp+Bh] BYREF
  LPWSTR lpValueName; // [rsp+C8h] [rbp+Fh] BYREF
  PVOID pvData; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = 0;
  hKey = 0;
  cValues = 0;
  pvData = 0;
  cbMaxValueLen = 0;
  lpValueName = 0;
  cbMaxValueNameLen = 0;
  Type = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"HARDWARE\\DEVICEMAP\\SERIALCOMM", 0, 1u, &hKey);
  if ( (unsigned int)(ValueW - 2) > 1 )
  {
    v4 = ValueW <= 0;
    if ( ValueW )
    {
LABEL_3:
      if ( !v4 )
      {
        v2 = (unsigned __int16)ValueW | 0x80070000;
        goto LABEL_20;
      }
LABEL_19:
      v2 = ValueW;
      goto LABEL_20;
    }
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    if ( v5 )
    {
      v6 = 485;
LABEL_18:
      ValueW = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v6,
                 (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerdevices.cpp",
                 (const char *)v5,
                 phkResult);
      goto LABEL_19;
    }
    v7 = 0;
LABEL_8:
    if ( v7 < cValues )
    {
      while ( 1 )
      {
        v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
        if ( v5 )
          break;
        ++cbMaxValueNameLen;
        cbMaxValueLen += 2;
        v8 = std::make_unique<unsigned short [0],0>(v13, cbMaxValueNameLen);
        std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(&lpValueName, v8);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v13);
        v9 = std::make_unique<unsigned short [0],0>(v14, (unsigned __int64)cbMaxValueLen >> 1);
        std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(&pvData, v9);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v14);
        ValueW = RegEnumValueW(hKey, v7, lpValueName, &cbMaxValueNameLen, 0, &Type, 0, 0);
        if ( ValueW != 234 )
        {
          v4 = ValueW <= 0;
          if ( ValueW )
            goto LABEL_3;
          if ( Type != 1 )
            goto LABEL_16;
          v10 = pvData;
          ValueW = RegGetValueW(hKey, 0, lpValueName, 2u, 0, pvData, &cbMaxValueLen);
          if ( ValueW != 234 )
          {
            v4 = ValueW <= 0;
            if ( ValueW )
              goto LABEL_3;
            std::wstring::wstring(v15, v10);
            std::wstring::wstring(v16, lpValueName);
            std::vector<std::pair<std::wstring,std::wstring>>::emplace_back<std::pair<std::wstring,std::wstring>>(
              a1,
              v15);
            std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)v15);
LABEL_16:
            ++v7;
            goto LABEL_8;
          }
        }
      }
      v6 = 494;
      goto LABEL_18;
    }
  }
LABEL_20:
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pvData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x1400a9500  push    rbp
0x1400a9502  push    rbx
0x1400a9503  push    rsi
0x1400a9504  push    rdi
0x1400a9505  push    r12
0x1400a9507  push    r15
0x1400a9509  lea     rbp, [rsp-2Fh]
0x1400a950e  sub     rsp, 0E8h
0x1400a9515  mov     rax, cs:__security_cookie
0x1400a951c  xor     rax, rsp
0x1400a951f  mov     [rbp+57h+var_38], rax
0x1400a9523  mov     r15, rcx
0x1400a9526  xor     r12d, r12d
0x1400a9529  mov     edi, r12d
0x1400a952c  mov     [rbp+57h+hKey], r12
0x1400a9530  mov     [rbp+57h+cValues], r12d
0x1400a9534  mov     [rbp+57h+pvData], r12
0x1400a9538  mov     [rbp+57h+cbMaxValueLen], r12d
0x1400a953c  mov     [rbp+57h+lpValueName], r12
0x1400a9540  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x1400a9544  mov     [rbp+57h+Type], r12d
0x1400a9548  xor     edx, edx
0x1400a954a  lea     rcx, [rbp+57h+hKey]
0x1400a954e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1400a9553  lea     rax, [rbp+57h+hKey]
0x1400a9557  mov     [rsp+110h+phkResult], rax; phkResult
0x1400a955c  lea     r9d, [r12+1]; samDesired
0x1400a9561  xor     r8d, r8d; ulOptions
0x1400a9564  lea     rdx, aHardwareDevice; "HARDWARE\\DEVICEMAP\\SERIALCOMM"
0x1400a956b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a9572  call    cs:__imp_RegOpenKeyExW
0x1400a9579  nop     dword ptr [rax+rax+00h]
0x1400a957e  lea     ecx, [rax-2]
0x1400a9581  cmp     ecx, 1
0x1400a9584  jbe     loc_1400A9783
0x1400a958a  test    eax, eax
0x1400a958c  jz      short loc_1400A95A2
0x1400a958e  jle     loc_1400A9781
0x1400a9594  movzx   edi, ax
0x1400a9597  or      edi, 80070000h
0x1400a959d  jmp     loc_1400A9783
0x1400a95a2  mov     [rsp+110h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1400a95a7  mov     [rsp+110h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1400a95ac  mov     [rsp+110h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1400a95b1  mov     [rsp+110h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1400a95b6  lea     rax, [rbp+57h+cValues]
0x1400a95ba  mov     [rsp+110h+lpcValues], rax; lpcValues
0x1400a95bf  mov     [rsp+110h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1400a95c4  mov     [rsp+110h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1400a95c9  mov     [rsp+110h+phkResult], r12; lpcSubKeys
0x1400a95ce  xor     r9d, r9d; lpReserved
0x1400a95d1  xor     r8d, r8d; lpcchClass
0x1400a95d4  xor     edx, edx; lpClass
0x1400a95d6  mov     rcx, [rbp+57h+hKey]; hKey
0x1400a95da  call    cs:__imp_RegQueryInfoKeyW
0x1400a95e1  nop     dword ptr [rax+rax+00h]
0x1400a95e6  test    eax, eax
0x1400a95e8  jz      short loc_1400A95F4
0x1400a95ea  mov     edx, 1E5h
0x1400a95ef  jmp     loc_1400A976E
0x1400a95f4  mov     esi, r12d
0x1400a95f7  cmp     esi, [rbp+57h+cValues]
0x1400a95fa  jnb     loc_1400A9783
0x1400a9600  mov     [rsp+110h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1400a9605  mov     [rsp+110h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1400a960a  lea     rax, [rbp+57h+cbMaxValueLen]
0x1400a960e  mov     [rsp+110h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1400a9613  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1400a9617  mov     [rsp+110h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1400a961c  mov     [rsp+110h+lpcValues], r12; lpcValues
0x1400a9621  mov     [rsp+110h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1400a9626  mov     [rsp+110h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1400a962b  mov     [rsp+110h+phkResult], r12; unsigned int
0x1400a9630  xor     r9d, r9d; lpReserved
0x1400a9633  xor     r8d, r8d; lpcchClass
0x1400a9636  xor     edx, edx; lpClass
0x1400a9638  mov     rcx, [rbp+57h+hKey]; hKey
0x1400a963c  call    cs:__imp_RegQueryInfoKeyW
0x1400a9643  nop     dword ptr [rax+rax+00h]
0x1400a9648  test    eax, eax
0x1400a964a  jnz     loc_1400A9769
0x1400a9650  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1400a9653  inc     eax
0x1400a9655  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1400a9658  mov     edx, eax
0x1400a965a  add     [rbp+57h+cbMaxValueLen], 2
0x1400a965e  lea     rcx, [rbp+57h+var_B0]
0x1400a9662  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x1400a9667  mov     rdx, rax
0x1400a966a  lea     rcx, [rbp+57h+lpValueName]
0x1400a966e  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1400a9673  lea     rcx, [rbp+57h+var_B0]
0x1400a9677  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400a967c  mov     edx, [rbp+57h+cbMaxValueLen]
0x1400a967f  shr     rdx, 1
0x1400a9682  lea     rcx, [rbp+57h+var_A8]
0x1400a9686  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x1400a968b  mov     rdx, rax
0x1400a968e  lea     rcx, [rbp+57h+pvData]
0x1400a9692  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1400a9697  lea     rcx, [rbp+57h+var_A8]
0x1400a969b  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400a96a0  mov     [rsp+110h+lpcValues], r12; lpcbData
0x1400a96a5  mov     [rsp+110h+lpcbMaxClassLen], r12; lpData
0x1400a96aa  lea     rax, [rbp+57h+Type]
0x1400a96ae  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpType
0x1400a96b3  mov     [rsp+110h+phkResult], r12; lpReserved
0x1400a96b8  lea     r9, [rbp+57h+cbMaxValueNameLen]; lpcchValueName
0x1400a96bc  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x1400a96c0  mov     edx, esi; dwIndex
0x1400a96c2  mov     rcx, [rbp+57h+hKey]; hKey
0x1400a96c6  call    cs:__imp_RegEnumValueW
0x1400a96cd  nop     dword ptr [rax+rax+00h]
0x1400a96d2  cmp     eax, 0EAh
0x1400a96d7  jz      loc_1400A9600
0x1400a96dd  test    eax, eax
0x1400a96df  jnz     loc_1400A958E
0x1400a96e5  cmp     [rbp+57h+Type], 1
0x1400a96e9  jnz     short loc_1400A9762
0x1400a96eb  lea     rax, [rbp+57h+cbMaxValueLen]
0x1400a96ef  mov     [rsp+110h+lpcbMaxClassLen], rax; pcbData
0x1400a96f4  mov     rbx, [rbp+57h+pvData]
0x1400a96f8  mov     [rsp+110h+lpcbMaxSubKeyLen], rbx; pvData
0x1400a96fd  mov     [rsp+110h+phkResult], r12; pdwType
0x1400a9702  mov     r9d, 2; dwFlags
0x1400a9708  mov     r8, [rbp+57h+lpValueName]; lpValue
0x1400a970c  xor     edx, edx; lpSubKey
0x1400a970e  mov     rcx, [rbp+57h+hKey]; hkey
0x1400a9712  call    cs:__imp_RegGetValueW
0x1400a9719  nop     dword ptr [rax+rax+00h]
0x1400a971e  cmp     eax, 0EAh
0x1400a9723  jz      loc_1400A9600
0x1400a9729  test    eax, eax
0x1400a972b  jnz     loc_1400A958E
0x1400a9731  mov     rdx, rbx
0x1400a9734  lea     rcx, [rbp+57h+var_A0]
0x1400a9738  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400a973d  nop
0x1400a973e  mov     rdx, [rbp+57h+lpValueName]
0x1400a9742  lea     rcx, [rbp+57h+var_80]
0x1400a9746  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400a974b  nop
0x1400a974c  lea     rdx, [rbp+57h+var_A0]
0x1400a9750  mov     rcx, r15
0x1400a9753  call    ??$emplace_back@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@$$QEAU21@@Z; std::vector<std::pair<std::wstring,std::wstring>>::emplace_back<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x1400a9758  nop
0x1400a9759  lea     rcx, [rbp+57h+var_A0]; this
0x1400a975d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1400a9762  inc     esi
0x1400a9764  jmp     loc_1400A95F7
0x1400a9769  mov     edx, 1EEh; void *
0x1400a976e  mov     r9d, eax; char *
0x1400a9771  lea     r8, aOnecoreVmCompu_28; "onecore\\vm\\compute\\management\\share"...
0x1400a9778  mov     rcx, [rbp+5Fh]; this
0x1400a977c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400a9781  mov     edi, eax
0x1400a9783  lea     rcx, [rbp+57h+lpValueName]
0x1400a9787  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400a978c  nop
0x1400a978d  lea     rcx, [rbp+57h+pvData]
0x1400a9791  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400a9796  nop
0x1400a9797  lea     rcx, [rbp+57h+hKey]
0x1400a979b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400a97a0  mov     eax, edi
0x1400a97a2  mov     rcx, [rbp+57h+var_38]
0x1400a97a6  xor     rcx, rsp; StackCookie
0x1400a97a9  call    __security_check_cookie
0x1400a97ae  add     rsp, 0E8h
0x1400a97b5  pop     r15
0x1400a97b7  pop     r12
0x1400a97b9  pop     rdi
0x1400a97ba  pop     rsi
0x1400a97bb  pop     rbx
0x1400a97bc  pop     rbp
0x1400a97bd  retn
```
