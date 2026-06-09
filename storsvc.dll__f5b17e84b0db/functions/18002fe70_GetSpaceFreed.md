# GetSpaceFreed

- ea: `0x18002fe70`
- end: `0x180030070`
- name: `GetSpaceFreed`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18003037c`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180019db4`
- `0x18002fa54`
- `0x18002fe70`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff5e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180030021`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180030021`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002ff89`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002ff89`

## string_xrefs

- `0x18002ff24`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002ffac`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetSpaceFreed(_DWORD *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  DWORD v5; // edi
  int v6; // ebx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchValueName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR ValueName[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  phkResult = 0;
  cchValueName = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  v2 = OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"StoragePolicy", &hKey);
  v3 = v2;
  if ( v2 >= 0 )
  {
    phkResult = 0;
    v4 = RegCreateKeyW(hKey, L"SpaceHistory", &phkResult);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
    {
      v5 = 0;
      v6 = 0;
      CleanupSpaceFreedLogs(phkResult);
      while ( 1 )
      {
        cchValueName = 260;
        cbData = 4;
        if ( RegEnumValueW(phkResult, v5, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
          break;
        ++v5;
        if ( Type == 4 )
          v6 += *(_DWORD *)Data;
      }
      *a1 = v6;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58C,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)v3,
        lpReserved);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58B,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v2,
      lpReserved);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x18002fe70  push    rbp
0x18002fe72  push    rbx
0x18002fe73  push    rsi
0x18002fe74  push    rdi
0x18002fe75  lea     rbp, [rsp-198h]
0x18002fe7d  sub     rsp, 298h
0x18002fe84  mov     rax, cs:__security_cookie
0x18002fe8b  xor     rax, rsp
0x18002fe8e  mov     [rbp+1B0h+var_30], rax
0x18002fe95  mov     rsi, rcx
0x18002fe98  mov     [rsp+2B0h+hKey], 0
0x18002fea1  mov     [rsp+2B0h+phkResult], 0
0x18002feaa  mov     [rsp+2B0h+cchValueName], 0
0x18002feb2  mov     [rsp+2B0h+Type], 0
0x18002feba  mov     dword ptr [rsp+2B0h+Data], 0
0x18002fec2  mov     [rsp+2B0h+cbData], 0
0x18002feca  mov     rbx, [rsp+2B0h+hKey]
0x18002fecf  test    rbx, rbx
0x18002fed2  jz      short loc_18002FEF3
0x18002fed4  lea     rcx, [rsp+2B0h+var_250]; this
0x18002fed9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002fede  nop
0x18002fedf  mov     rcx, rbx; hKey
0x18002fee2  call    cs:__imp_RegCloseKey
0x18002fee8  nop
0x18002fee9  lea     rcx, [rsp+2B0h+var_250]; this
0x18002feee  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002fef3  mov     [rsp+2B0h+hKey], 0
0x18002fefc  lea     r8, [rsp+2B0h+hKey]; phkResult
0x18002ff01  lea     rdx, aStoragepolicy; "StoragePolicy"
0x18002ff08  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002ff0f  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18002ff14  mov     ebx, eax
0x18002ff16  test    eax, eax
0x18002ff18  jns     short loc_18002FF46
0x18002ff1a  mov     rcx, [rbp+1B8h]; this
0x18002ff21  mov     r9d, eax; char *
0x18002ff24  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002ff2b  mov     edx, 58Bh; void *
0x18002ff30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff35  nop
0x18002ff36  lea     rcx, [rsp+2B0h+phkResult]
0x18002ff3b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ff40  nop
0x18002ff41  jmp     loc_180030049
0x18002ff46  mov     rbx, [rsp+2B0h+phkResult]
0x18002ff4b  test    rbx, rbx
0x18002ff4e  jz      short loc_18002FF6F
0x18002ff50  lea     rcx, [rsp+2B0h+var_250]; this
0x18002ff55  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ff5a  nop
0x18002ff5b  mov     rcx, rbx; hKey
0x18002ff5e  call    cs:__imp_RegCloseKey
0x18002ff64  nop
0x18002ff65  lea     rcx, [rsp+2B0h+var_250]; this
0x18002ff6a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ff6f  mov     [rsp+2B0h+phkResult], 0
0x18002ff78  lea     r8, [rsp+2B0h+phkResult]; phkResult
0x18002ff7d  lea     rdx, aSpacehistory; "SpaceHistory"
0x18002ff84  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002ff89  call    cs:__imp_RegCreateKeyW
0x18002ff8f  mov     ebx, eax
0x18002ff91  test    eax, eax
0x18002ff93  jle     short loc_18002FF9E
0x18002ff95  movzx   ebx, ax
0x18002ff98  or      ebx, 80070000h
0x18002ff9e  test    ebx, ebx
0x18002ffa0  jns     short loc_18002FFCB
0x18002ffa2  mov     rcx, [rbp+1B8h]; this
0x18002ffa9  mov     r9d, ebx; char *
0x18002ffac  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002ffb3  mov     edx, 58Ch; void *
0x18002ffb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ffbd  nop
0x18002ffbe  lea     rcx, [rsp+2B0h+phkResult]
0x18002ffc3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ffc8  nop
0x18002ffc9  jmp     short loc_180030049
0x18002ffcb  xor     edi, edi
0x18002ffcd  xor     ebx, ebx
0x18002ffcf  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x18002ffd4  call    CleanupSpaceFreedLogs
0x18002ffd9  mov     [rsp+2B0h+cchValueName], 104h
0x18002ffe1  mov     [rsp+2B0h+cbData], 4
0x18002ffe9  lea     rax, [rsp+2B0h+cbData]
0x18002ffee  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18002fff3  lea     rax, [rsp+2B0h+Data]
0x18002fff8  mov     [rsp+2B0h+lpData], rax; lpData
0x18002fffd  lea     rax, [rsp+2B0h+Type]
0x180030002  mov     [rsp+2B0h+lpType], rax; lpType
0x180030007  mov     [rsp+2B0h+lpReserved], 0; lpReserved
0x180030010  lea     r9, [rsp+2B0h+cchValueName]; lpcchValueName
0x180030015  lea     r8, [rsp+2B0h+ValueName]; lpValueName
0x18003001a  mov     edx, edi; dwIndex
0x18003001c  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x180030021  call    cs:__imp_RegEnumValueW
0x180030027  test    eax, eax
0x180030029  jnz     short loc_18003003A
0x18003002b  inc     edi
0x18003002d  cmp     [rsp+2B0h+Type], 4
0x180030032  jnz     short loc_18002FFD9
0x180030034  add     ebx, dword ptr [rsp+2B0h+Data]
0x180030038  jmp     short loc_18002FFD9
0x18003003a  mov     [rsi], ebx
0x18003003c  lea     rcx, [rsp+2B0h+phkResult]
0x180030041  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030046  nop
0x180030047  xor     ebx, ebx
0x180030049  lea     rcx, [rsp+2B0h+hKey]
0x18003004e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030053  mov     eax, ebx
0x180030055  mov     rcx, [rbp+1B0h+var_30]
0x18003005c  xor     rcx, rsp; StackCookie
0x18003005f  call    __security_check_cookie
0x180030064  add     rsp, 298h
0x18003006b  pop     rdi
0x18003006c  pop     rsi
0x18003006d  pop     rbx
0x18003006e  pop     rbp
0x18003006f  retn
```
