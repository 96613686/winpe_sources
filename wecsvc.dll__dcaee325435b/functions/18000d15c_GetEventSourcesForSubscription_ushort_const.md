# GetEventSourcesForSubscription(ushort const *)

- ea: `0x18000d15c`
- end: `0x18000d45f`
- name: `?GetEventSourcesForSubscription@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z`
- size: `771`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004608`
- `0x18000d5b0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x180003e6c`
- `0x1800062d4`
- `0x1800064e0`
- `0x18000d15c`
- `0x1800111f8`
- `0x180011c24`
- `0x180011d6c`
- `0x180011f40`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d2a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d2a1`

## string_xrefs

- `0x18000d240`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000d2f1`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000d3d0`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall GetEventSourcesForSubscription(_QWORD *a1, __int64 a2)
{
  const WCHAR *v4; // rdx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY v8; // rdx
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-71h] BYREF
  int v16; // [rsp+40h] [rbp-69h]
  _QWORD *v17; // [rsp+48h] [rbp-61h]
  _BYTE v18[8]; // [rsp+50h] [rbp-59h] BYREF
  int v19; // [rsp+58h] [rbp-51h]
  __int64 v20; // [rsp+78h] [rbp-31h]
  void **pExceptionObject; // [rsp+88h] [rbp-21h] BYREF
  char v22; // [rsp+90h] [rbp-19h]
  const char *v23; // [rsp+98h] [rbp-11h]
  __int64 v24; // [rsp+A0h] [rbp-9h]
  __int64 v25; // [rsp+A8h] [rbp-1h]
  unsigned int v26; // [rsp+B0h] [rbp+7h]
  int v27; // [rsp+B4h] [rbp+Bh]
  int v28; // [rsp+B8h] [rbp+Fh]
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp+17h] BYREF

  v17 = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v16 = 1;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  std::wstring::append(lpSubKey, L"\\Subscriptions\\");
  std::wstring::append(lpSubKey, a2);
  hKey = 0;
  v4 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] >= (LPCWSTR)8 )
    v4 = lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v5);
    }
    v22 = 0;
    v23 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
    v24 = 0;
    v25 = 0;
    v26 = v5;
    v27 = -1;
    v28 = 316;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  phkResult = 0;
  v6 = RegOpenKeyExW(hKey, L"EventSources", 0, 0x20019u, &phkResult);
  v7 = v6;
  if ( v6 != 2 )
  {
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v6);
      }
      v22 = 0;
      v23 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v24 = 0;
      v25 = 0;
      v26 = v7;
      v27 = -1;
      v28 = 330;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v8 = phkResult;
    phkResult = 0;
    RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v18, v8);
    v19 = 0;
    while ( 1 )
    {
      v10 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v18);
      v11 = v10;
      if ( v10 )
        break;
      std::wstring::wstring(&pExceptionObject, v20);
      std::vector<std::wstring>::push_back(a1, &pExceptionObject);
      LOBYTE(v9) = 1;
      std::wstring::_Tidy(&pExceptionObject, v9, 0);
    }
    if ( v10 != 259 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v10);
      }
      v22 = 0;
      v23 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v24 = 0;
      v25 = 0;
      v26 = v11;
      v27 = -1;
      v28 = 340;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    RegistryKeyEnumerator::~RegistryKeyEnumerator((RegistryKeyEnumerator *)v18);
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(lpSubKey, v12, 0);
  return a1;
}

```

## disassembly

```asm
0x18000d15c  mov     [rsp-8+arg_10], rbx
0x18000d161  push    rbp
0x18000d162  push    rsi
0x18000d163  push    rdi
0x18000d164  lea     rbp, [rsp-47h]
0x18000d169  sub     rsp, 0F0h
0x18000d170  mov     rax, cs:__security_cookie
0x18000d177  xor     rax, rsp
0x18000d17a  mov     [rbp+57h+var_20], rax
0x18000d17e  mov     rbx, rdx
0x18000d181  mov     rdi, rcx
0x18000d184  mov     [rbp+57h+var_B8], rcx
0x18000d188  mov     [rbp+57h+var_C0], 1
0x18000d18f  xor     esi, esi
0x18000d191  mov     [rcx], rsi
0x18000d194  mov     [rcx+8], rsi
0x18000d198  mov     [rcx+10h], rsi
0x18000d19c  mov     [rbp+57h+var_C0], 1
0x18000d1a3  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000d1aa  lea     rcx, [rbp+57h+lpSubKey]
0x18000d1ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000d1b3  nop
0x18000d1b4  lea     rdx, aSubscriptions_1; "\\Subscriptions\\"
0x18000d1bb  lea     rcx, [rbp+57h+lpSubKey]
0x18000d1bf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000d1c4  mov     rdx, rbx
0x18000d1c7  lea     rcx, [rbp+57h+lpSubKey]
0x18000d1cb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000d1d0  mov     [rbp+57h+hKey], rsi
0x18000d1d4  lea     rdx, [rbp+57h+lpSubKey]
0x18000d1d8  cmp     [rbp+57h+var_28], 8
0x18000d1dd  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000d1e2  lea     rax, [rbp+57h+hKey]
0x18000d1e6  mov     [rsp+100h+phkResult], rax; phkResult
0x18000d1eb  mov     r9d, 20019h; samDesired
0x18000d1f1  xor     r8d, r8d; ulOptions
0x18000d1f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d1fb  call    cs:__imp_RegOpenKeyExW
0x18000d201  mov     ebx, eax
0x18000d203  test    eax, eax
0x18000d205  jz      short loc_18000D280
0x18000d207  lea     rax, WPP_GLOBAL_Control
0x18000d20e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d215  cmp     rcx, rax
0x18000d218  jz      short loc_18000D23C
0x18000d21a  test    byte ptr [rcx+1Ch], 10h
0x18000d21e  jz      short loc_18000D23C
0x18000d220  cmp     byte ptr [rcx+19h], 2
0x18000d224  jb      short loc_18000D23C
0x18000d226  lea     edx, [rsi+0Fh]
0x18000d229  mov     r9d, ebx
0x18000d22c  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000d233  mov     rcx, [rcx+10h]
0x18000d237  call    WPP_SF_D
0x18000d23c  mov     [rbp+57h+var_70], sil
0x18000d240  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000d247  mov     [rbp+57h+var_68], rax
0x18000d24b  mov     [rbp+57h+var_60], rsi
0x18000d24f  mov     [rbp+57h+var_58], rsi
0x18000d253  mov     [rbp+57h+var_50], ebx
0x18000d256  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x18000d25d  mov     [rbp+57h+var_48], 13Ch
0x18000d264  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000d26b  mov     [rbp+57h+pExceptionObject], rax
0x18000d26f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000d276  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000d27a  call    _CxxThrowException_0
0x18000d280  mov     [rbp+57h+var_D0], rsi
0x18000d284  lea     rax, [rbp+57h+var_D0]
0x18000d288  mov     [rsp+100h+phkResult], rax; phkResult
0x18000d28d  mov     r9d, 20019h; samDesired
0x18000d293  xor     r8d, r8d; ulOptions
0x18000d296  lea     rdx, aEventsources; "EventSources"
0x18000d29d  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d2a1  call    cs:__imp_RegOpenKeyExW
0x18000d2a7  mov     ebx, eax
0x18000d2a9  cmp     eax, 2
0x18000d2ac  jz      loc_18000D41A
0x18000d2b2  test    eax, eax
0x18000d2b4  jz      short loc_18000D331
0x18000d2b6  lea     rax, WPP_GLOBAL_Control
0x18000d2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2c4  cmp     rcx, rax
0x18000d2c7  jz      short loc_18000D2ED
0x18000d2c9  test    byte ptr [rcx+1Ch], 10h
0x18000d2cd  jz      short loc_18000D2ED
0x18000d2cf  cmp     byte ptr [rcx+19h], 2
0x18000d2d3  jb      short loc_18000D2ED
0x18000d2d5  mov     edx, 10h
0x18000d2da  mov     r9d, ebx
0x18000d2dd  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000d2e4  mov     rcx, [rcx+10h]
0x18000d2e8  call    WPP_SF_D
0x18000d2ed  mov     [rbp+57h+var_70], sil
0x18000d2f1  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000d2f8  mov     [rbp+57h+var_68], rax
0x18000d2fc  mov     [rbp+57h+var_60], rsi
0x18000d300  mov     [rbp+57h+var_58], rsi
0x18000d304  mov     [rbp+57h+var_50], ebx
0x18000d307  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x18000d30e  mov     [rbp+57h+var_48], 14Ah
0x18000d315  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000d31c  mov     [rbp+57h+pExceptionObject], rax
0x18000d320  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000d327  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000d32b  call    _CxxThrowException_0
0x18000d331  mov     rdx, [rbp+57h+var_D0]; HKEY
0x18000d335  mov     [rbp+57h+var_D0], rsi
0x18000d339  lea     rcx, [rbp+57h+var_B0]; this
0x18000d33d  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *)
0x18000d342  nop
0x18000d343  mov     [rbp+57h+var_A8], esi
0x18000d346  jmp     short loc_18000D371
0x18000d348  mov     rdx, [rbp+57h+var_88]
0x18000d34c  lea     rcx, [rbp+57h+pExceptionObject]
0x18000d350  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000d355  nop
0x18000d356  lea     rdx, [rbp+57h+pExceptionObject]
0x18000d35a  mov     rcx, rdi
0x18000d35d  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18000d362  nop
0x18000d363  xor     r8d, r8d
0x18000d366  mov     dl, 1
0x18000d368  lea     rcx, [rbp+57h+pExceptionObject]
0x18000d36c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d371  lea     rcx, [rbp+57h+var_B0]; this
0x18000d375  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18000d37a  test    eax, eax
0x18000d37c  mov     ebx, eax
0x18000d37e  jz      short loc_18000D348
0x18000d380  cmp     eax, 103h
0x18000d385  jz      loc_18000D410
0x18000d38b  mov     eax, 507h
0x18000d390  test    ebx, ebx
0x18000d392  cmovz   ebx, eax
0x18000d395  lea     rax, WPP_GLOBAL_Control
0x18000d39c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3a3  cmp     rcx, rax
0x18000d3a6  jz      short loc_18000D3CC
0x18000d3a8  test    byte ptr [rcx+1Ch], 10h
0x18000d3ac  jz      short loc_18000D3CC
0x18000d3ae  cmp     byte ptr [rcx+19h], 2
0x18000d3b2  jb      short loc_18000D3CC
0x18000d3b4  mov     edx, 11h
0x18000d3b9  mov     r9d, ebx
0x18000d3bc  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000d3c3  mov     rcx, [rcx+10h]
0x18000d3c7  call    WPP_SF_D
0x18000d3cc  mov     [rbp+57h+var_70], sil
0x18000d3d0  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000d3d7  mov     [rbp+57h+var_68], rax
0x18000d3db  mov     [rbp+57h+var_60], rsi
0x18000d3df  mov     [rbp+57h+var_58], rsi
0x18000d3e3  mov     [rbp+57h+var_50], ebx
0x18000d3e6  mov     [rbp+57h+var_4C], 0FFFFFFFFh
0x18000d3ed  mov     [rbp+57h+var_48], 154h
0x18000d3f4  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000d3fb  mov     [rbp+57h+pExceptionObject], rax
0x18000d3ff  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000d406  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000d40a  call    _CxxThrowException_0
0x18000d410  lea     rcx, [rbp+57h+var_B0]; this
0x18000d414  call    ??1RegistryKeyEnumerator@@QEAA@XZ; RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x18000d419  nop
0x18000d41a  lea     rcx, [rbp+57h+var_D0]; this
0x18000d41e  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000d423  nop
0x18000d424  lea     rcx, [rbp+57h+hKey]; this
0x18000d428  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000d42d  nop
0x18000d42e  xor     r8d, r8d
0x18000d431  mov     dl, 1
0x18000d433  lea     rcx, [rbp+57h+lpSubKey]
0x18000d437  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d43c  nop
0x18000d43d  mov     rax, rdi
0x18000d440  mov     rcx, [rbp+57h+var_20]
0x18000d444  xor     rcx, rsp; StackCookie
0x18000d447  call    __security_check_cookie
0x18000d44c  mov     rbx, [rsp+100h+arg_10]
0x18000d454  add     rsp, 0F0h
0x18000d45b  pop     rdi
0x18000d45c  pop     rsi
0x18000d45d  pop     rbp
0x18000d45e  retn
```
