# UsoCommitHelper::PersistRebootEndTime(void)

- ea: `0x14000af7c`
- end: `0x14000b135`
- name: `?PersistRebootEndTime@UsoCommitHelper@@CAXXZ`
- size: `441`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000b13c`

## callees

- `0x14000af7c`
- `0x14000b41c`
- `0x14005eebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b107`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b107`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b043`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b043`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000afb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000afb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000afcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b0ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000afcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b0ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000b07a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000b07a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000b0b4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000b0e9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000b0b4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000b0e9`

## string_xrefs

- `0x14000afa4`: `SOFTWARE\Microsoft\WindowsUpdate\UX\RebootDowntime`
- `0x14000b0aa`: `SOFTWARE\Microsoft\WindowsUpdate\UX\RebootDowntime`
- `0x14000b0df`: `SOFTWARE\Microsoft\WindowsUpdate\UX\RebootDowntime`
- `0x14000afd7`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x14000b036`: `FirstLogonAfterUpdateFlag`
- `0x14000b0d8`: `FirstLogonAfterUpdateFlag`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void UsoCommitHelper::PersistRebootEndTime(void)
{
  unsigned int ValueW; // eax
  int v1; // ebx
  int v2; // edi
  HKEY v3; // rsi
  DWORD LastError; // ebx
  __int64 v5; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int Data; // [rsp+70h] [rbp+30h] BYREF
  HKEY pcbData; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF

  hKey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\RebootDowntime",
             0,
             0x20019u,
             &hKey);
  if ( ValueW - 2 <= 1 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return;
  }
  if ( ValueW )
  {
    v5 = 266;
    goto LABEL_4;
  }
  Data = 0;
  LODWORD(pcbData) = 4;
  ValueW = RegGetValueW(hKey, 0, L"FirstLogonAfterUpdateFlag", 0x18u, 0, &Data, (LPDWORD)&pcbData);
  if ( ValueW == 2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return;
  }
  if ( ValueW )
  {
    v5 = 284;
LABEL_4:
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
           (const char *)ValueW,
           phkResult);
    v2 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( v1 < 0 )
      return;
    goto LABEL_11;
  }
  v2 = Data;
  v3 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v3);
    SetLastError(LastError);
  }
LABEL_11:
  if ( v2 )
  {
    pcbData = 0;
    GetSystemTimeAsFileTime((LPFILETIME)&pcbData);
    hKey = pcbData;
    RegSetKeyValueW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\RebootDowntime",
      L"EndTime",
      0xBu,
      &hKey,
      8u);
    Data = 0;
    RegSetKeyValueW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\RebootDowntime",
      L"FirstLogonAfterUpdateFlag",
      4u,
      &Data,
      4u);
  }
}

```

## disassembly

```asm
0x14000af7c  push    rbp
0x14000af7e  push    rbx
0x14000af7f  push    rsi
0x14000af80  push    rdi
0x14000af81  push    r13
0x14000af83  mov     rbp, rsp
0x14000af86  sub     rsp, 40h
0x14000af8a  mov     [rbp+hKey], 0
0x14000af92  lea     rax, [rbp+hKey]
0x14000af96  mov     [rsp+40h+phkResult], rax; unsigned int
0x14000af9b  mov     r9d, 20019h; samDesired
0x14000afa1  xor     r8d, r8d; ulOptions
0x14000afa4  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x14000afab  mov     r13, 0FFFFFFFF80000002h
0x14000afb2  mov     rcx, r13; hKey
0x14000afb5  call    cs:__imp_RegOpenKeyExW
0x14000afbb  lea     ecx, [rax-2]
0x14000afbe  cmp     ecx, 1
0x14000afc1  ja      short loc_14000B003
0x14000afc3  mov     rcx, [rbp+hKey]; hKey
0x14000afc7  test    rcx, rcx
0x14000afca  jz      short loc_14000AFF8
0x14000afcc  call    cs:__imp_RegCloseKey
0x14000afd2  jmp     short loc_14000AFF8
0x14000afd4  mov     r9d, eax; char *
0x14000afd7  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x14000afde  mov     rcx, [rbp+28h]; this
0x14000afe2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000afe7  mov     ebx, eax
0x14000afe9  lea     rcx, [rbp+hKey]
0x14000afed  xor     edi, edi
0x14000afef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000aff4  test    ebx, ebx
0x14000aff6  jns     short loc_14000B06A
0x14000aff8  add     rsp, 40h
0x14000affc  pop     r13
0x14000affe  pop     rdi
0x14000afff  pop     rsi
0x14000b000  pop     rbx
0x14000b001  pop     rbp
0x14000b002  retn
0x14000b003  test    eax, eax
0x14000b005  jnz     loc_14000B112
0x14000b00b  mov     [rbp+Data], eax
0x14000b00e  mov     dword ptr [rbp+arg_8], 4
0x14000b015  lea     rax, [rbp+arg_8]
0x14000b019  mov     [rsp+40h+pcbData], rax; pcbData
0x14000b01e  lea     rax, [rbp+Data]
0x14000b022  mov     [rsp+40h+pvData], rax; pvData
0x14000b027  mov     [rsp+40h+phkResult], 0; pdwType
0x14000b030  mov     r9d, 18h; dwFlags
0x14000b036  lea     r8, Value; "FirstLogonAfterUpdateFlag"
0x14000b03d  xor     edx, edx; lpSubKey
0x14000b03f  mov     rcx, [rbp+hKey]; hkey
0x14000b043  call    cs:__imp_RegGetValueW
0x14000b049  cmp     eax, 2
0x14000b04c  jz      loc_14000B11C
0x14000b052  test    eax, eax
0x14000b054  jnz     loc_14000B12A
0x14000b05a  mov     edi, [rbp+Data]
0x14000b05d  mov     rsi, [rbp+hKey]
0x14000b061  test    rsi, rsi
0x14000b064  jnz     loc_14000B0F4
0x14000b06a  test    edi, edi
0x14000b06c  jz      short loc_14000AFF8
0x14000b06e  mov     [rbp+arg_8], 0
0x14000b076  lea     rcx, [rbp+arg_8]; lpSystemTimeAsFileTime
0x14000b07a  call    cs:__imp_GetSystemTimeAsFileTime
0x14000b080  mov     eax, dword ptr [rbp+arg_8]
0x14000b083  mov     ecx, dword ptr [rbp+arg_8+4]
0x14000b086  mov     dword ptr [rbp+hKey], eax
0x14000b089  mov     dword ptr [rbp+hKey+4], ecx
0x14000b08c  mov     dword ptr [rsp+40h+pvData], 8; cbData
0x14000b094  lea     rax, [rbp+hKey]
0x14000b098  mov     [rsp+40h+phkResult], rax; lpData
0x14000b09d  mov     r9d, 0Bh; dwType
0x14000b0a3  lea     r8, aEndtime; "EndTime"
0x14000b0aa  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x14000b0b1  mov     rcx, r13; hKey
0x14000b0b4  call    cs:__imp_RegSetKeyValueW
0x14000b0ba  mov     [rbp+Data], 0
0x14000b0c1  mov     dword ptr [rsp+40h+pvData], 4; cbData
0x14000b0c9  lea     rax, [rbp+Data]
0x14000b0cd  mov     [rsp+40h+phkResult], rax; lpData
0x14000b0d2  mov     r9d, 4; dwType
0x14000b0d8  lea     r8, Value; "FirstLogonAfterUpdateFlag"
0x14000b0df  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x14000b0e6  mov     rcx, r13; hKey
0x14000b0e9  call    cs:__imp_RegSetKeyValueW
0x14000b0ef  jmp     loc_14000AFF8
0x14000b0f4  call    cs:__imp_GetLastError
0x14000b0fa  mov     ebx, eax
0x14000b0fc  mov     rcx, rsi; hKey
0x14000b0ff  call    cs:__imp_RegCloseKey
0x14000b105  mov     ecx, ebx; dwErrCode
0x14000b107  call    cs:__imp_SetLastError
0x14000b10d  jmp     loc_14000B06A
0x14000b112  mov     edx, 10Ah; void *
0x14000b117  jmp     loc_14000AFD4
0x14000b11c  lea     rcx, [rbp+hKey]
0x14000b120  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000b125  jmp     loc_14000AFF8
0x14000b12a  mov     edx, 11Ch
0x14000b12f  jmp     loc_14000AFD4
```
