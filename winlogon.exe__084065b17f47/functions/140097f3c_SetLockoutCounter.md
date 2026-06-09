# SetLockoutCounter

- ea: `0x140097f3c`
- end: `0x1400980d7`
- name: `SetLockoutCounter`
- size: `411`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140097c70`

## callees

- `0x140038250`
- `0x14008f7e8`
- `0x1400978b4`
- `0x140097f3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009804a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009804a`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14009807f`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14009807f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140097ff7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140097ff7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400980bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400980bb`

## string_xrefs

- `0x140097f9b`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140098036`: `DevicePasswordFailedAttempts`
- `0x14009800f`: `RegCreateKeyEx`
- `0x140098062`: `RegSetValueEx`

## pseudocode

```c
__int64 __fastcall SetLockoutCounter(PSID Sid, int a2)
{
  unsigned int UserStateKeyName; // ebx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-30h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-30h]
  int Data; // [rsp+68h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp+28h] BYREF

  Data = a2;
  lpSubKey = 0;
  hKey = 0;
  CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&lpSubKey);
  UserStateKeyName = GetUserStateKeyName(Sid);
  if ( UserStateKeyName )
  {
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      UserStateKeyName,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      545,
      L"GetUserStateKeyName",
      &pPassword);
  }
  else
  {
    UserStateKeyName = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 3u, 0, &hKey, 0);
    if ( UserStateKeyName )
    {
      dwOptions[0] = 557;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        UserStateKeyName,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
        *(_QWORD *)dwOptions,
        L"RegCreateKeyEx",
        &pPassword);
    }
    else
    {
      UserStateKeyName = RegSetValueExW(hKey, L"DevicePasswordFailedAttempts", 0, 4u, (const BYTE *)&Data, 4u);
      if ( UserStateKeyName )
      {
        dwOptionsa[0] = 567;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          UserStateKeyName,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
          *(_QWORD *)dwOptionsa,
          L"RegSetValueEx",
          &pPassword);
      }
      else
      {
        UserStateKeyName = RegFlushKey(hKey);
        if ( UserStateKeyName )
        {
          dwOptionsa[0] = 571;
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            UserStateKeyName,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
            *(_QWORD *)dwOptionsa,
            L"RegFlushKey",
            &pPassword);
        }
        else
        {
          UserStateKeyName = 0;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&lpSubKey);
  return UserStateKeyName;
}

```

## disassembly

```asm
0x140097f3c  mov     [rsp-8+arg_0], rbx
0x140097f41  mov     [rsp-8+Data], edx
0x140097f45  push    rbp
0x140097f46  mov     rbp, rsp
0x140097f49  sub     rsp, 50h
0x140097f4d  mov     rbx, rcx
0x140097f50  mov     [rbp+lpSubKey], 0
0x140097f58  lea     rcx, [rbp+lpSubKey]
0x140097f5c  mov     [rbp+hKey], 0
0x140097f64  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x140097f69  lea     rdx, [rbp+lpSubKey]
0x140097f6d  mov     rcx, rbx; Sid
0x140097f70  call    GetUserStateKeyName
0x140097f75  mov     ebx, eax
0x140097f77  test    eax, eax
0x140097f79  jz      short loc_140097FBB
0x140097f7b  lea     rax, pPassword
0x140097f82  mov     [rsp+50h+lpSecurityAttributes], rax
0x140097f87  lea     rax, aGetuserstateke; "GetUserStateKeyName"
0x140097f8e  mov     qword ptr [rsp+50h+samDesired], rax
0x140097f93  mov     [rsp+50h+dwOptions], 221h
0x140097f9b  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x140097fa2  mov     r8d, ebx
0x140097fa5  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097fac  mov     ecx, 1; unsigned int
0x140097fb1  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097fb6  jmp     loc_1400980B2
0x140097fbb  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140097fbf  lea     rax, [rbp+hKey]
0x140097fc3  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x140097fcc  xor     r9d, r9d; lpClass
0x140097fcf  mov     [rsp+50h+phkResult], rax; phkResult
0x140097fd4  xor     r8d, r8d; Reserved
0x140097fd7  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140097fe0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140097fe7  mov     [rsp+50h+samDesired], 3; samDesired
0x140097fef  mov     [rsp+50h+dwOptions], 0; dwOptions
0x140097ff7  call    cs:__imp_RegCreateKeyExW
0x140097ffd  mov     ebx, eax
0x140097fff  test    eax, eax
0x140098001  jz      short loc_140098028
0x140098003  lea     rax, pPassword
0x14009800a  mov     [rsp+50h+lpSecurityAttributes], rax
0x14009800f  lea     rax, aRegcreatekeyex; "RegCreateKeyEx"
0x140098016  mov     qword ptr [rsp+50h+samDesired], rax
0x14009801b  mov     [rsp+50h+dwOptions], 22Dh
0x140098023  jmp     loc_140097F9B
0x140098028  mov     rcx, [rbp+hKey]; hKey
0x14009802c  lea     rax, [rbp+Data]
0x140098030  mov     r9d, 4; dwType
0x140098036  lea     rdx, aDevicepassword; "DevicePasswordFailedAttempts"
0x14009803d  mov     [rsp+50h+samDesired], r9d; cbData
0x140098042  xor     r8d, r8d; Reserved
0x140098045  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14009804a  call    cs:__imp_RegSetValueExW
0x140098050  mov     ebx, eax
0x140098052  test    eax, eax
0x140098054  jz      short loc_14009807B
0x140098056  lea     rax, pPassword
0x14009805d  mov     [rsp+50h+lpSecurityAttributes], rax
0x140098062  lea     rax, aRegsetvalueex; "RegSetValueEx"
0x140098069  mov     qword ptr [rsp+50h+samDesired], rax
0x14009806e  mov     [rsp+50h+dwOptions], 237h
0x140098076  jmp     loc_140097F9B
0x14009807b  mov     rcx, [rbp+hKey]; hKey
0x14009807f  call    cs:__imp_RegFlushKey
0x140098085  mov     ebx, eax
0x140098087  test    eax, eax
0x140098089  jz      short loc_1400980B0
0x14009808b  lea     rax, pPassword
0x140098092  mov     [rsp+50h+lpSecurityAttributes], rax
0x140098097  lea     rax, aRegflushkey; "RegFlushKey"
0x14009809e  mov     qword ptr [rsp+50h+samDesired], rax
0x1400980a3  mov     [rsp+50h+dwOptions], 23Bh
0x1400980ab  jmp     loc_140097F9B
0x1400980b0  xor     ebx, ebx
0x1400980b2  mov     rcx, [rbp+hKey]; hKey
0x1400980b6  test    rcx, rcx
0x1400980b9  jz      short loc_1400980C1
0x1400980bb  call    cs:__imp_RegCloseKey
0x1400980c1  lea     rcx, [rbp+lpSubKey]
0x1400980c5  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x1400980ca  mov     eax, ebx
0x1400980cc  mov     rbx, [rsp+50h+arg_0]
0x1400980d1  add     rsp, 50h
0x1400980d5  pop     rbp
0x1400980d6  retn
```
