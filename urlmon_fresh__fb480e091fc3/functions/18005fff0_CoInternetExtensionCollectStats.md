# CoInternetExtensionCollectStats

- ea: `0x18005fff0`
- end: `0x18006034d`
- name: `CoInternetExtensionCollectStats`
- size: `861`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005fe70`
- `0x1800d3998`

## callees

- `0x180001fb4`
- `0x180033980`
- `0x18005fff0`
- `0x180089154`
- `0x180092578`
- `0x180098410`
- `0x180098850`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800601ca`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800602d4`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800601ca`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800602d4`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x180060023`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x180060045`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x180060023`
- `iertutil!__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ` at `0x180060045`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800600f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800600f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006012f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060175`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060264`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006012f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060175`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060264`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060326`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060326`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180060232`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180060232`

## pseudocode

```c
LSTATUS __fastcall CoInternetExtensionCollectStats(struct _GUID *a1, unsigned int a2, int a3)
{
  struct ILegacyBrowsingEnvironment *v5; // rax
  struct ILegacyBrowsingEnvironment *LegacyBrowsingEnvironment; // rax
  LSTATUS result; // eax
  unsigned __int64 v8; // r8
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  char v15[8]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  BYTE v20[4]; // [rsp+74h] [rbp-8Ch] BYREF
  struct _GUID *v21; // [rsp+78h] [rbp-88h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v22; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *CLSID; // [rsp+88h] [rbp-78h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF

  *(_DWORD *)Data = a3;
  if ( (a2 & 2) != 0
    || (v5 = GetLegacyBrowsingEnvironment(),
        !(*(unsigned __int8 (__fastcall **)(struct ILegacyBrowsingEnvironment *))(*(_QWORD *)v5 + 120LL))(v5)) )
  {
    hKey = 0;
    dwDisposition = 0;
    *(_DWORD *)v20 = 0;
    result = CoInternetIsFeatureEnabled(FEATURE_ADDON_MANAGEMENT, 2u);
    if ( result != 1 )
    {
      result = Ext_GetStatsKey(a1, SubKey, v8);
      if ( result >= 0 )
      {
        result = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
        if ( !result )
        {
          RegSetValueExW(hKey, L"Type", 0, 4u, Data, 4u);
          if ( dwDisposition == 1 )
          {
            *(_DWORD *)v20 = 0;
            RegSetValueExW(hKey, L"Flags", 0, 4u, v20, 4u);
            if ( (unsigned int)dword_180166000 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_180166000, 0x400000000000LL) )
              {
                v17 = *(_DWORD *)Data;
                v21 = a1;
                v15[0] = 1;
                v22 = GlobalThreadState();
                CLSID = (struct _GUID *)IEConfiguration_GetCLSID(268435459);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
                  v9,
                  (unsigned int)&byte_180152E9F,
                  v10,
                  v11,
                  (__int64)&CLSID,
                  (__int64)&v22,
                  (__int64)v15,
                  (__int64)&v17,
                  (__int64)&v21);
              }
            }
          }
          IncrementRegDword(hKey, L"Count");
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          RegSetValueExW(hKey, L"Time", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
          if ( (a2 & 1) != 0 )
          {
            if ( (unsigned int)dword_180166000 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_180166000, 0x400000000000LL) )
              {
                v17 = *(_DWORD *)Data;
                CLSID = a1;
                v15[0] = 1;
                v22 = GlobalThreadState();
                v21 = (struct _GUID *)IEConfiguration_GetCLSID(268435459);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
                  v12,
                  (unsigned int)byte_180152F09,
                  v13,
                  v14,
                  (__int64)&v21,
                  (__int64)&v22,
                  (__int64)v15,
                  (__int64)&v17,
                  (__int64)&CLSID);
              }
            }
          }
          else
          {
            IncrementRegDword(hKey, L"Blocked");
          }
          return RegCloseKey(hKey);
        }
      }
    }
  }
  else
  {
    LegacyBrowsingEnvironment = GetLegacyBrowsingEnvironment();
    return (*(__int64 (__fastcall **)(struct ILegacyBrowsingEnvironment *, struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)LegacyBrowsingEnvironment + 112LL))(
             LegacyBrowsingEnvironment,
             a1,
             a2,
             *(unsigned int *)Data);
  }
  return result;
}

```

## disassembly

```asm
0x18005fff0  push    rbp
0x18005fff2  push    rbx
0x18005fff3  push    rdi
0x18005fff4  lea     rbp, [rsp-1C0h]
0x18005fffc  sub     rsp, 2C0h
0x180060003  mov     rax, cs:__security_cookie
0x18006000a  xor     rax, rsp
0x18006000d  mov     [rbp+1D0h+var_20], rax
0x180060014  mov     dword ptr [rsp+2D0h+Data], r8d
0x180060019  mov     edi, edx
0x18006001b  mov     rbx, rcx
0x18006001e  test    dl, 2
0x180060021  jnz     short loc_180060073
0x180060023  call    cs:__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ; GetLegacyBrowsingEnvironment(void)
0x18006002a  nop     dword ptr [rax+rax+00h]
0x18006002f  mov     r9, rax
0x180060032  mov     rcx, [rax]
0x180060035  mov     rax, [rcx+78h]
0x180060039  mov     rcx, r9
0x18006003c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060041  test    al, al
0x180060043  jz      short loc_180060073
0x180060045  call    cs:__imp_?GetLegacyBrowsingEnvironment@@YAPEAUILegacyBrowsingEnvironment@@XZ; GetLegacyBrowsingEnvironment(void)
0x18006004c  nop     dword ptr [rax+rax+00h]
0x180060051  mov     r9d, dword ptr [rsp+2D0h+Data]
0x180060056  mov     r8d, edi
0x180060059  mov     r10, rax
0x18006005c  mov     rdx, rbx
0x18006005f  mov     rcx, [rax]
0x180060062  mov     rax, [rcx+70h]
0x180060066  mov     rcx, r10
0x180060069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006006e  jmp     loc_180060332
0x180060073  mov     edx, 2; dwFlags
0x180060078  mov     [rsp+2D0h+hKey], 0
0x180060081  mov     [rsp+2D0h+dwDisposition], 0
0x180060089  mov     dword ptr [rsp+2D0h+var_25C], 0
0x180060091  lea     ecx, [rdx+0Bh]; FeatureEntry
0x180060094  call    CoInternetIsFeatureEnabled
0x180060099  cmp     eax, 1
0x18006009c  jz      loc_180060332
0x1800600a2  lea     rdx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x1800600a6  mov     rcx, rbx; struct _GUID *
0x1800600a9  call    ?Ext_GetStatsKey@@YAJAEBU_GUID@@PEAG_K@Z; Ext_GetStatsKey(_GUID const &,ushort *,unsigned __int64)
0x1800600ae  test    eax, eax
0x1800600b0  js      loc_180060332
0x1800600b6  lea     rax, [rsp+2D0h+dwDisposition]
0x1800600bb  xor     r9d, r9d; lpClass
0x1800600be  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x1800600c3  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800600c7  lea     rax, [rsp+2D0h+hKey]
0x1800600cc  xor     r8d, r8d; Reserved
0x1800600cf  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800600d4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800600db  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800600e4  mov     [rsp+2D0h+samDesired], 2001Fh; samDesired
0x1800600ec  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x1800600f4  call    cs:__imp_RegCreateKeyExW
0x1800600fb  nop     dword ptr [rax+rax+00h]
0x180060100  test    eax, eax
0x180060102  jnz     loc_180060332
0x180060108  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18006010d  lea     rax, [rsp+2D0h+Data]
0x180060112  mov     [rsp+2D0h+samDesired], 4; cbData
0x18006011a  lea     rdx, aType; "Type"
0x180060121  mov     r9d, 4; dwType
0x180060127  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18006012c  xor     r8d, r8d; Reserved
0x18006012f  call    cs:__imp_RegSetValueExW
0x180060136  nop     dword ptr [rax+rax+00h]
0x18006013b  cmp     [rsp+2D0h+dwDisposition], 1
0x180060140  jnz     loc_180060216
0x180060146  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18006014b  lea     rax, [rsp+2D0h+var_25C]
0x180060150  mov     [rsp+2D0h+samDesired], 4; cbData
0x180060158  lea     rdx, aFlags; "Flags"
0x18006015f  mov     r9d, 4; dwType
0x180060165  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18006016a  xor     r8d, r8d; Reserved
0x18006016d  mov     dword ptr [rsp+2D0h+var_25C], 0
0x180060175  call    cs:__imp_RegSetValueExW
0x18006017c  nop     dword ptr [rax+rax+00h]
0x180060181  mov     eax, cs:dword_180166000
0x180060187  cmp     eax, 5
0x18006018a  jbe     loc_180060216
0x180060190  mov     rdx, 400000000000h
0x18006019a  lea     rcx, dword_180166000
0x1800601a1  call    _tlgKeywordOn
0x1800601a6  test    al, al
0x1800601a8  jz      short loc_180060216
0x1800601aa  mov     eax, dword ptr [rsp+2D0h+Data]
0x1800601ae  mov     [rsp+2D0h+var_270], eax
0x1800601b2  mov     [rsp+2D0h+var_258], rbx
0x1800601b7  mov     [rsp+2D0h+var_280], 1
0x1800601bc  call    ?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800601c1  mov     ecx, 10000003h
0x1800601c6  mov     [rbp+1D0h+var_250], rax
0x1800601ca  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800601d1  nop     dword ptr [rax+rax+00h]
0x1800601d6  mov     [rbp+1D0h+var_248], rax
0x1800601da  lea     rdx, byte_180152E9F
0x1800601e1  lea     rax, [rsp+2D0h+var_258]
0x1800601e6  mov     [rsp+2D0h+lpdwDisposition], rax
0x1800601eb  lea     rax, [rsp+2D0h+var_270]
0x1800601f0  mov     [rsp+2D0h+phkResult], rax
0x1800601f5  lea     rax, [rsp+2D0h+var_280]
0x1800601fa  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x1800601ff  lea     rax, [rbp+1D0h+var_250]
0x180060203  mov     qword ptr [rsp+2D0h+samDesired], rax
0x180060208  lea     rax, [rbp+1D0h+var_248]
0x18006020c  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x180060211  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180060216  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18006021b  lea     rdx, aCount; "Count"
0x180060222  call    ?IncrementRegDword@@YAXPEAUHKEY__@@PEBG@Z; IncrementRegDword(HKEY__ *,ushort const *)
0x180060227  xorps   xmm0, xmm0
0x18006022a  lea     rcx, [rbp+1D0h+SystemTime]; lpSystemTime
0x18006022e  movups  xmmword ptr [rbp+1D0h+SystemTime.wYear], xmm0
0x180060232  call    cs:__imp_GetSystemTime
0x180060239  nop     dword ptr [rax+rax+00h]
0x18006023e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180060243  lea     rax, [rbp+1D0h+SystemTime]
0x180060247  mov     [rsp+2D0h+samDesired], 10h; cbData
0x18006024f  lea     rdx, aTime; "Time"
0x180060256  mov     r9d, 3; dwType
0x18006025c  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180060261  xor     r8d, r8d; Reserved
0x180060264  call    cs:__imp_RegSetValueExW
0x18006026b  nop     dword ptr [rax+rax+00h]
0x180060270  test    dil, 1
0x180060274  jnz     short loc_18006028C
0x180060276  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18006027b  lea     rdx, aBlocked; "Blocked"
0x180060282  call    ?IncrementRegDword@@YAXPEAUHKEY__@@PEBG@Z; IncrementRegDword(HKEY__ *,ushort const *)
0x180060287  jmp     loc_180060321
0x18006028c  mov     eax, cs:dword_180166000
0x180060292  cmp     eax, 5
0x180060295  jbe     loc_180060321
0x18006029b  mov     rdx, 400000000000h
0x1800602a5  lea     rcx, dword_180166000
0x1800602ac  call    _tlgKeywordOn
0x1800602b1  test    al, al
0x1800602b3  jz      short loc_180060321
0x1800602b5  mov     eax, dword ptr [rsp+2D0h+Data]
0x1800602b9  mov     [rsp+2D0h+var_270], eax
0x1800602bd  mov     [rbp+1D0h+var_248], rbx
0x1800602c1  mov     [rsp+2D0h+var_280], 1
0x1800602c6  call    ?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800602cb  mov     ecx, 10000003h
0x1800602d0  mov     [rbp+1D0h+var_250], rax
0x1800602d4  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800602db  nop     dword ptr [rax+rax+00h]
0x1800602e0  mov     [rsp+2D0h+var_258], rax
0x1800602e5  lea     rdx, byte_180152F09
0x1800602ec  lea     rax, [rbp+1D0h+var_248]
0x1800602f0  mov     [rsp+2D0h+lpdwDisposition], rax
0x1800602f5  lea     rax, [rsp+2D0h+var_270]
0x1800602fa  mov     [rsp+2D0h+phkResult], rax
0x1800602ff  lea     rax, [rsp+2D0h+var_280]
0x180060304  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x180060309  lea     rax, [rbp+1D0h+var_250]
0x18006030d  mov     qword ptr [rsp+2D0h+samDesired], rax
0x180060312  lea     rax, [rsp+2D0h+var_258]
0x180060317  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x18006031c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180060321  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180060326  call    cs:__imp_RegCloseKey
0x18006032d  nop     dword ptr [rax+rax+00h]
0x180060332  mov     rcx, [rbp+1D0h+var_20]
0x180060339  xor     rcx, rsp; StackCookie
0x18006033c  call    __security_check_cookie
0x180060341  add     rsp, 2C0h
0x180060348  pop     rdi
0x180060349  pop     rbx
0x18006034a  pop     rbp
0x18006034b  retn
```
