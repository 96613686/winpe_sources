# CReportStore::InitMachineStore(void)

- ea: `0x18000ac40`
- end: `0x18000ad8f`
- name: `?InitMachineStore@CReportStore@@UEAAJXZ`
- size: `335`
- prototype: `__int64 __fastcall(CReportStore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009b50`
- `0x18000a6c0`

## callees

- `0x18000a9f0`
- `0x18000ac40`
- `0x18000c504`
- `0x18003fb94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ad6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ad6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000acc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000acc2`

## string_xrefs

- `0x18000ad20`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18000ad49`: `StoreDontForceCompression`

## pseudocode

```c
__int64 __fastcall CReportStore::InitMachineStore(CReportStore *this)
{
  int Settings; // ebx
  LSTATUS v3; // eax
  bool v4; // sf
  bool v5; // cc
  int v6; // ebx
  __int64 v8; // rdx
  LSTATUS ValueW; // eax
  int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  Settings = CSettings::LoadSettings((CReportStore *)((char *)this + 72), 0, 0, WerConsentNotAsked);
  if ( Settings < 0 )
  {
    v8 = 141;
    goto LABEL_12;
  }
  Settings = CReportStore::GetMachineStoreDir((__int64 (__fastcall ***)(_QWORD))this, (_QWORD *)this + 2);
  if ( Settings < 0 )
  {
    v8 = 143;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)(unsigned int)Settings,
      phkResult);
    return (unsigned int)Settings;
  }
  *((_DWORD *)this + 2) = 3;
  pvData = 0;
  pcbData = 4;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
         0,
         0x101u,
         &hKey);
  v4 = v3 < 0;
  v5 = v3 <= 0;
  if ( !v3 )
  {
    ValueW = RegGetValueW(hKey, 0, L"StoreDontForceCompression", 0x10u, 0, &pvData, &pcbData);
    v4 = ValueW < 0;
    v5 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_7;
  }
  if ( !v5 )
    v4 = 1;
  if ( v4 )
  {
    v6 = 0;
    pvData = 0;
  }
  else
  {
LABEL_7:
    v6 = pvData;
  }
  if ( hKey )
    RegCloseKey(hKey);
  *((_DWORD *)this + 12) = v6 != 0;
  return 0;
}

```

## disassembly

```asm
0x18000ac40  mov     [rsp+arg_18], rbx
0x18000ac45  push    rdi
0x18000ac46  sub     rsp, 40h
0x18000ac4a  mov     rdi, rcx
0x18000ac4d  mov     r9d, 1; enum _WER_CONSENT
0x18000ac53  add     rcx, 48h ; 'H'; this
0x18000ac57  xor     r8d, r8d; wchar_t *
0x18000ac5a  xor     edx, edx; wchar_t *
0x18000ac5c  call    ?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z; CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)
0x18000ac61  mov     ebx, eax
0x18000ac63  test    eax, eax
0x18000ac65  js      loc_18000AD33
0x18000ac6b  lea     rdx, [rdi+10h]
0x18000ac6f  mov     rcx, rdi
0x18000ac72  call    ?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000ac77  mov     ebx, eax
0x18000ac79  test    eax, eax
0x18000ac7b  js      loc_18000AD16
0x18000ac81  lea     rax, [rsp+48h+hKey]
0x18000ac86  mov     dword ptr [rdi+8], 3
0x18000ac8d  mov     r9d, 101h; samDesired
0x18000ac93  mov     [rsp+48h+phkResult], rax; phkResult
0x18000ac98  xor     r8d, r8d; ulOptions
0x18000ac9b  mov     [rsp+48h+arg_0], 0
0x18000aca3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x18000acaa  mov     [rsp+48h+arg_8], 4
0x18000acb2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000acb9  mov     [rsp+48h+hKey], 0
0x18000acc2  call    cs:__imp_RegOpenKeyExW
0x18000acc9  nop     dword ptr [rax+rax+00h]
0x18000acce  test    eax, eax
0x18000acd0  jz      short loc_18000AD3A
0x18000acd2  jle     short loc_18000ACDE
0x18000acd4  movzx   eax, ax
0x18000acd7  or      eax, 80070000h
0x18000acdc  test    eax, eax
0x18000acde  js      loc_18000AD84
0x18000ace4  mov     ebx, [rsp+48h+arg_0]
0x18000ace8  mov     rcx, [rsp+48h+hKey]; hKey
0x18000aced  test    rcx, rcx
0x18000acf0  jz      short loc_18000ACFE
0x18000acf2  call    cs:__imp_RegCloseKey
0x18000acf9  nop     dword ptr [rax+rax+00h]
0x18000acfe  xor     eax, eax
0x18000ad00  test    ebx, ebx
0x18000ad02  setnz   al
0x18000ad05  mov     [rdi+30h], eax
0x18000ad08  xor     eax, eax
0x18000ad0a  mov     rbx, [rsp+48h+arg_18]
0x18000ad0f  add     rsp, 40h
0x18000ad13  pop     rdi
0x18000ad14  retn
0x18000ad16  mov     edx, 8Fh; void *
0x18000ad1b  mov     rcx, [rsp+48h]; this
0x18000ad20  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18000ad27  mov     r9d, ebx; char *
0x18000ad2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad2f  mov     eax, ebx
0x18000ad31  jmp     short loc_18000AD0A
0x18000ad33  mov     edx, 8Dh
0x18000ad38  jmp     short loc_18000AD1B
0x18000ad3a  mov     rcx, [rsp+48h+hKey]; hkey
0x18000ad3f  lea     rax, [rsp+48h+arg_8]
0x18000ad44  mov     [rsp+48h+pcbData], rax; pcbData
0x18000ad49  lea     r8, Value; "StoreDontForceCompression"
0x18000ad50  lea     rax, [rsp+48h+arg_0]
0x18000ad55  mov     r9d, 10h; dwFlags
0x18000ad5b  mov     [rsp+48h+pvData], rax; pvData
0x18000ad60  xor     edx, edx; lpSubKey
0x18000ad62  mov     [rsp+48h+phkResult], 0; pdwType
0x18000ad6b  call    cs:__imp_RegGetValueW
0x18000ad72  nop     dword ptr [rax+rax+00h]
0x18000ad77  test    eax, eax
0x18000ad79  jz      loc_18000ACE4
0x18000ad7f  jmp     loc_18000ACD2
0x18000ad84  xor     ebx, ebx
0x18000ad86  mov     [rsp+48h+arg_0], ebx
0x18000ad8a  jmp     loc_18000ACE8
```
