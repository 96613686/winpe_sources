# OpenSubscriptionEventSourceKey

- ea: `0x18000ef44`
- end: `0x18000f109`
- name: `OpenSubscriptionEventSourceKey`
- size: `453`
- prototype: `HKEY __fastcall(__int64, __int64, REGSAM, char)`
- caller_count: `8`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800081e4`
- `0x18000e134`
- `0x18000e2f8`
- `0x18000f1f8`
- `0x18000f3d0`
- `0x18000f8bc`
- `0x18000fd88`
- `0x1800103b8`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x1800062d4`
- `0x1800064e0`
- `0x18000ef44`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f01b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f01b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f047`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f047`

## string_xrefs

- `0x18000f092`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY __fastcall OpenSubscriptionEventSourceKey(__int64 a1, __int64 a2, REGSAM a3, char a4)
{
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  const WCHAR *v11; // rdx
  unsigned int v12; // ebx
  HKEY v13; // rbx
  DWORD dwDisposition; // [rsp+50h] [rbp-39h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-31h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-29h] BYREF
  char v18; // [rsp+68h] [rbp-21h]
  const char *v19; // [rsp+70h] [rbp-19h]
  __int64 v20; // [rsp+78h] [rbp-11h]
  __int64 v21; // [rsp+80h] [rbp-9h]
  unsigned int v22; // [rsp+88h] [rbp-1h]
  int v23; // [rsp+8Ch] [rbp+3h]
  int v24; // [rsp+90h] [rbp+7h]
  LPCWSTR lpSubKey[3]; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int64 v26; // [rsp+B0h] [rbp+27h]

  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  std::wstring::append(lpSubKey, L"\\Subscriptions\\");
  std::wstring::append(lpSubKey, a1);
  if ( a2 )
  {
    std::wstring::append(lpSubKey, L"\\EventSources\\");
    std::wstring::append(lpSubKey, a2);
  }
  phkResult = 0;
  if ( a4 && a2 )
  {
    dwDisposition = 0;
    v8 = (const WCHAR *)lpSubKey;
    if ( v26 >= 8 )
      v8 = lpSubKey[0];
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, a3, 0, &phkResult, &dwDisposition);
  }
  else
  {
    v11 = (const WCHAR *)lpSubKey;
    if ( v26 >= 8 )
      v11 = lpSubKey[0];
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, a3, &phkResult);
  }
  v12 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v9);
    }
    v18 = 0;
    v19 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v20 = 0;
    v21 = 0;
    v22 = v12;
    v23 = -1;
    v24 = 147;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v13 = phkResult;
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(lpSubKey, v10, 0);
  return v13;
}

```

## disassembly

```asm
0x18000ef44  push    rbp
0x18000ef46  push    rbx
0x18000ef47  push    rsi
0x18000ef48  push    rdi
0x18000ef49  push    r14
0x18000ef4b  lea     rbp, [rsp-37h]
0x18000ef50  sub     rsp, 0C0h
0x18000ef57  mov     rax, cs:__security_cookie
0x18000ef5e  xor     rax, rsp
0x18000ef61  mov     [rbp+57h+var_28], rax
0x18000ef65  mov     sil, r9b
0x18000ef68  mov     r14d, r8d
0x18000ef6b  mov     rdi, rdx
0x18000ef6e  mov     rbx, rcx
0x18000ef71  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000ef78  lea     rcx, [rbp+57h+lpSubKey]
0x18000ef7c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000ef81  nop
0x18000ef82  lea     rdx, aSubscriptions_1; "\\Subscriptions\\"
0x18000ef89  lea     rcx, [rbp+57h+lpSubKey]
0x18000ef8d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000ef92  mov     rdx, rbx
0x18000ef95  lea     rcx, [rbp+57h+lpSubKey]
0x18000ef99  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000ef9e  test    rdi, rdi
0x18000efa1  jz      short loc_18000EFBF
0x18000efa3  lea     rdx, aEventsources_0; "\\EventSources\\"
0x18000efaa  lea     rcx, [rbp+57h+lpSubKey]
0x18000efae  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000efb3  mov     rdx, rdi
0x18000efb6  lea     rcx, [rbp+57h+lpSubKey]
0x18000efba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000efbf  mov     [rbp+57h+var_88], 0
0x18000efc7  test    sil, sil
0x18000efca  jz      short loc_18000F023
0x18000efcc  test    rdi, rdi
0x18000efcf  jz      short loc_18000F023
0x18000efd1  mov     [rbp+57h+dwDisposition], 0
0x18000efd8  lea     rdx, [rbp+57h+lpSubKey]
0x18000efdc  cmp     [rbp+57h+var_30], 8
0x18000efe1  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000efe6  lea     rax, [rbp+57h+dwDisposition]
0x18000efea  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x18000efef  lea     rax, [rbp+57h+var_88]
0x18000eff3  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18000eff8  mov     [rsp+0E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000f001  mov     [rsp+0E0h+samDesired], r14d; samDesired
0x18000f006  mov     [rsp+0E0h+dwOptions], 0; dwOptions
0x18000f00e  xor     r9d, r9d; lpClass
0x18000f011  xor     r8d, r8d; Reserved
0x18000f014  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f01b  call    cs:__imp_RegCreateKeyExW
0x18000f021  jmp     short loc_18000F04D
0x18000f023  lea     rdx, [rbp+57h+lpSubKey]
0x18000f027  cmp     [rbp+57h+var_30], 8
0x18000f02c  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000f031  lea     rax, [rbp+57h+var_88]
0x18000f035  mov     qword ptr [rsp+0E0h+dwOptions], rax; phkResult
0x18000f03a  mov     r9d, r14d; samDesired
0x18000f03d  xor     r8d, r8d; ulOptions
0x18000f040  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f047  call    cs:__imp_RegOpenKeyExW
0x18000f04d  mov     ebx, eax
0x18000f04f  test    eax, eax
0x18000f051  jz      loc_18000F0DA
0x18000f057  lea     rax, WPP_GLOBAL_Control
0x18000f05e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f065  cmp     rcx, rax
0x18000f068  jz      short loc_18000F08E
0x18000f06a  test    byte ptr [rcx+1Ch], 10h
0x18000f06e  jz      short loc_18000F08E
0x18000f070  cmp     byte ptr [rcx+19h], 2
0x18000f074  jb      short loc_18000F08E
0x18000f076  mov     edx, 0Eh
0x18000f07b  mov     r9d, ebx
0x18000f07e  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000f085  mov     rcx, [rcx+10h]
0x18000f089  call    WPP_SF_D
0x18000f08e  mov     [rbp+57h+var_78], 0
0x18000f092  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000f099  mov     [rbp+57h+var_70], rax
0x18000f09d  mov     [rbp+57h+var_68], 0
0x18000f0a5  mov     [rbp+57h+var_60], 0
0x18000f0ad  mov     [rbp+57h+var_58], ebx
0x18000f0b0  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x18000f0b7  mov     [rbp+57h+var_50], 93h
0x18000f0be  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000f0c5  mov     [rbp+57h+pExceptionObject], rax
0x18000f0c9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000f0d0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f0d4  call    _CxxThrowException_0
0x18000f0da  mov     rbx, [rbp+57h+var_88]
0x18000f0de  xor     r8d, r8d
0x18000f0e1  mov     dl, 1
0x18000f0e3  lea     rcx, [rbp+57h+lpSubKey]
0x18000f0e7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f0ec  mov     rax, rbx
0x18000f0ef  mov     rcx, [rbp+57h+var_28]
0x18000f0f3  xor     rcx, rsp; StackCookie
0x18000f0f6  call    __security_check_cookie
0x18000f0fb  add     rsp, 0C0h
0x18000f102  pop     r14
0x18000f104  pop     rdi
0x18000f105  pop     rsi
0x18000f106  pop     rbx
0x18000f107  pop     rbp
0x18000f108  retn
```
