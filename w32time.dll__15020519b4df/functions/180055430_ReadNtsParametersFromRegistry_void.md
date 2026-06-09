# ReadNtsParametersFromRegistry(void)

- ea: `0x180055430`
- end: `0x18005554b`
- name: `?ReadNtsParametersFromRegistry@@YAJXZ`
- size: `283`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054828`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180034488`
- `0x18003a6a0`
- `0x1800538a8`
- `0x1800551a8`
- `0x180055430`
- `0x180055554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800554c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800554c4`

## string_xrefs

- `0x1800554bd`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient\Nts`
- `0x180055471`: `ReadNtsParametersFromRegistry: ReadManualCertInfo failed with error: 0x%08X\n`
- `0x1800554f3`: `ReadNtsParametersFromRegistry: Failed to read kePollInterval with error: 0x%08X\n`
- `0x180055524`: `ReadNtsParametersFromRegistry: ReadPreferredAEADList failed with error: 0x%08X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ReadNtsParametersFromRegistry(void)
{
  int ManualCertInfo; // ebx
  LSTATUS ValueW; // eax
  signed int v2; // ebx
  int PreferredAEADList; // ebx
  const char *v4; // r9
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbData; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+64h] [rbp+Ch]

  try
  {
    wil::critical_section::lock(&g_NtsState, &v6);
    CleanupPersistedServerSubkeys();
    if ( byte_1800A4948 )
    {
      ManualCertInfo = ReadManualCertInfo();
      if ( ManualCertInfo < 0 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
          FileLogAdd(
            L"ReadNtsParametersFromRegistry: ReadManualCertInfo failed with error: 0x%08X\n",
            (unsigned int)ManualCertInfo);
      }
    }
    v9 = -1;
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient\\Nts",
               L"NtsMinPollingInterval",
               0x10u,
               0,
               &dword_1800A494C,
               &pcbData);
    v2 = ValueW;
    if ( ValueW > 0 )
      v2 = (unsigned __int16)ValueW | 0x80070000;
    if ( v2 < 0 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(
          L"ReadNtsParametersFromRegistry: Failed to read kePollInterval with error: 0x%08X\n",
          (unsigned int)v2);
      dword_1800A494C = 10;
    }
    PreferredAEADList = ReadPreferredAEADList();
    if ( PreferredAEADList < 0 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(
          L"ReadNtsParametersFromRegistry: ReadPreferredAEADList failed with error: 0x%08X\n",
          (unsigned int)PreferredAEADList);
      PreferredAEADList = 0;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
    result = (unsigned int)PreferredAEADList;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD8,
                           (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\nts.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180055430  push    rbx
0x180055432  sub     rsp, 50h
0x180055436  lea     rdx, [rsp+58h+var_18]
0x18005543b  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x180055442  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x180055447  nop
0x180055448  call    ?CleanupPersistedServerSubkeys@@YAXXZ; CleanupPersistedServerSubkeys(void)
0x18005544d  cmp     cs:byte_1800A4948, 0
0x180055454  jz      short loc_18005547D
0x180055456  call    ?ReadManualCertInfo@@YAJXZ; ReadManualCertInfo(void)
0x18005545b  mov     ebx, eax
0x18005545d  test    eax, eax
0x18005545f  jns     short loc_18005547D
0x180055461  mov     ecx, 0C8h
0x180055466  call    FileLogAllowEntry
0x18005546b  test    al, al
0x18005546d  jz      short loc_18005547D
0x18005546f  mov     edx, ebx
0x180055471  lea     rcx, aReadntsparamet_0; "ReadNtsParametersFromRegistry: ReadManu"...
0x180055478  call    FileLogAdd
0x18005547d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180055484  mov     qword ptr [rsp+58h+arg_0], rcx
0x180055489  mov     [rsp+58h+arg_0], 4
0x180055491  lea     rax, [rsp+58h+arg_0]
0x180055496  mov     [rsp+58h+pcbData], rax; pcbData
0x18005549b  lea     rax, dword_1800A494C
0x1800554a2  mov     [rsp+58h+pvData], rax; pvData
0x1800554a7  mov     [rsp+58h+pdwType], 0; pdwType
0x1800554b0  mov     r9d, 10h; dwFlags
0x1800554b6  lea     r8, aNtsminpollingi; "NtsMinPollingInterval"
0x1800554bd  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services\\W3"...
0x1800554c4  call    cs:__imp_RegGetValueW
0x1800554cb  nop     dword ptr [rax+rax+00h]
0x1800554d0  mov     ebx, eax
0x1800554d2  test    eax, eax
0x1800554d4  jle     short loc_1800554DF
0x1800554d6  movzx   ebx, ax
0x1800554d9  or      ebx, 80070000h
0x1800554df  test    ebx, ebx
0x1800554e1  jns     short loc_180055509
0x1800554e3  mov     ecx, 0C8h
0x1800554e8  call    FileLogAllowEntry
0x1800554ed  test    al, al
0x1800554ef  jz      short loc_1800554FF
0x1800554f1  mov     edx, ebx
0x1800554f3  lea     rcx, aReadntsparamet; "ReadNtsParametersFromRegistry: Failed t"...
0x1800554fa  call    FileLogAdd
0x1800554ff  mov     cs:dword_1800A494C, 0Ah
0x180055509  call    ?ReadPreferredAEADList@@YAJXZ; ReadPreferredAEADList(void)
0x18005550e  mov     ebx, eax
0x180055510  test    eax, eax
0x180055512  jns     short loc_180055532
0x180055514  mov     ecx, 0C8h
0x180055519  call    FileLogAllowEntry
0x18005551e  test    al, al
0x180055520  jz      short loc_180055530
0x180055522  mov     edx, ebx
0x180055524  lea     rcx, aReadntsparamet_1; "ReadNtsParametersFromRegistry: ReadPref"...
0x18005552b  call    FileLogAdd
0x180055530  xor     ebx, ebx
0x180055532  lea     rcx, [rsp+58h+var_18]
0x180055537  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18005553c  mov     eax, ebx
0x18005553e  jmp     short loc_180055544
0x180055540  mov     eax, [rsp+58h+arg_0]
0x180055544  add     rsp, 50h
0x180055548  pop     rbx
0x180055549  retn
```
