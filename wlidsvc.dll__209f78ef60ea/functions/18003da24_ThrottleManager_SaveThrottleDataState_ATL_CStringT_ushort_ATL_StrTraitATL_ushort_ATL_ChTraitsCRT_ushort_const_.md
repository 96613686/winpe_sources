# ThrottleManager::SaveThrottleDataState(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ThrottleData &)

- ea: `0x18003da24`
- end: `0x18003dbe1`
- name: `?SaveThrottleDataState@ThrottleManager@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAUThrottleData@@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d910`

## callees

- `0x180013fb4`
- `0x1800146f0`
- `0x180015fb0`
- `0x180019690`
- `0x18003da24`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003db37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003db6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003db37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003db6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003db9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003db9e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003dafe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003dafe`

## string_xrefs

- `0x18003da60`: `Software\Microsoft\IdentityCRL\ThrottleCache`
- `0x18003dbaa`: `ThrottleManager::SaveThrottleDataState failure on Create. lRes: 0x%x`
- `0x18003daa3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\throttle.cpp`
- `0x18003db85`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\throttle.cpp`
- `0x18003dbb7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\throttle.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ThrottleManager::SaveThrottleDataState(const WCHAR *a1, _QWORD *a2, __int64 *a3)
{
  const WCHAR *v5; // rbx
  LSTATUS v6; // eax
  HKEY v7; // rdi
  LSTATUS v8; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-40h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp+20h] BYREF
  __int64 Data; // [rsp+98h] [rbp+38h] BYREF

  lpSubKey = a1;
  lpSubKey = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpSubKey,
    L"%ls\\%ls",
    L"Software\\Microsoft\\IdentityCRL\\ThrottleCache",
    *a2);
  v5 = lpSubKey;
  if ( *((int *)lpSubKey - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&lpSubKey, *((unsigned int *)lpSubKey - 4));
    v5 = lpSubKey;
  }
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\throttle.cpp",
    0xEDu,
    L"ThrottleManager::SaveThrottleDataState keyName: %ls",
    v5);
  LODWORD(lpSubKey) = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 1u, 0x2001Fu, 0, &hKey, (LPDWORD)&lpSubKey);
  if ( v6 )
  {
    dwOptions[0] = v6;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\throttle.cpp",
      0x105u,
      L"ThrottleManager::SaveThrottleDataState failure on Create. lRes: 0x%x",
      *(_QWORD *)dwOptions);
  }
  else
  {
    v7 = hKey;
    LODWORD(Data) = *((_DWORD *)a3 + 2);
    v8 = RegSetValueExW(hKey, L"ThrottleCount", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v8 )
    {
      dwOptionsa[0] = v8;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\throttle.cpp",
        0x100u,
        L"ThrottleManager::SaveThrottleDataState failure on SetDWORDValue. lRes: 0x%x",
        *(_QWORD *)dwOptionsa);
    }
    else
    {
      Data = *a3;
      RegSetValueExW(v7, L"ThrottleStartedTime", 0, 0xBu, (const BYTE *)&Data, 8u);
    }
    if ( v7 )
      RegCloseKey(v7);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
}

```

## disassembly

```asm
0x18003da24  mov     [rsp-18h+arg_8], rbx
0x18003da29  mov     [rsp-18h+lpSubKey], rcx
0x18003da2e  push    rbp
0x18003da2f  push    rsi
0x18003da30  push    rdi
0x18003da31  mov     rbp, rsp
0x18003da34  sub     rsp, 60h
0x18003da38  mov     rsi, r8
0x18003da3b  mov     rbx, rdx
0x18003da3e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003da45  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003da4c  mov     rax, [rax+18h]
0x18003da50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da55  add     rax, 18h
0x18003da59  mov     [rbp+lpSubKey], rax
0x18003da5d  mov     r9, [rbx]
0x18003da60  lea     r8, aSoftwareMicros; "Software\\Microsoft\\IdentityCRL\\Throt"...
0x18003da67  lea     rdx, aLsLs; "%ls\\%ls"
0x18003da6e  lea     rcx, [rbp+lpSubKey]
0x18003da72  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18003da77  mov     rbx, [rbp+lpSubKey]
0x18003da7b  cmp     dword ptr [rbx-8], 1
0x18003da7f  jle     short loc_18003DA91
0x18003da81  mov     edx, [rbx-10h]
0x18003da84  lea     rcx, [rbp+lpSubKey]
0x18003da88  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18003da8d  mov     rbx, [rbp+lpSubKey]
0x18003da91  mov     qword ptr [rsp+60h+dwOptions], rbx
0x18003da96  lea     r9, aThrottlemanage_2; "ThrottleManager::SaveThrottleDataState "...
0x18003da9d  mov     r8d, 0EDh; unsigned int
0x18003daa3  lea     rdx, aOnecoreuapDsEx_110; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003daaa  mov     ecx, 5; unsigned __int8
0x18003daaf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003dab4  mov     dword ptr [rbp+lpSubKey], 0
0x18003dabb  mov     [rbp+hKey], 0
0x18003dac3  lea     rax, [rbp+lpSubKey]
0x18003dac7  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18003dacc  lea     rax, [rbp+hKey]
0x18003dad0  mov     [rsp+60h+phkResult], rax; phkResult
0x18003dad5  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003dade  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18003dae6  mov     [rsp+60h+dwOptions], 1; dwOptions
0x18003daee  xor     r9d, r9d; lpClass
0x18003daf1  xor     r8d, r8d; Reserved
0x18003daf4  mov     rdx, rbx; lpSubKey
0x18003daf7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003dafe  call    cs:__imp_RegCreateKeyExW
0x18003db04  test    eax, eax
0x18003db06  jnz     loc_18003DBA6
0x18003db0c  mov     rdi, [rbp+hKey]
0x18003db10  mov     eax, [rsi+8]
0x18003db13  mov     dword ptr [rbp+Data], eax
0x18003db16  mov     r9d, 4; dwType
0x18003db1c  mov     [rsp+60h+samDesired], r9d; cbData
0x18003db21  lea     rax, [rbp+Data]
0x18003db25  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003db2a  xor     r8d, r8d; Reserved
0x18003db2d  lea     rdx, aThrottlecount; "ThrottleCount"
0x18003db34  mov     rcx, rdi; hKey
0x18003db37  call    cs:__imp_RegSetValueExW
0x18003db3d  test    eax, eax
0x18003db3f  jnz     short loc_18003DB74
0x18003db41  mov     rax, [rsi]
0x18003db44  mov     [rbp+Data], rax
0x18003db48  mov     [rsp+60h+samDesired], 8; cbData
0x18003db50  lea     rax, [rbp+Data]
0x18003db54  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18003db59  mov     r9d, 0Bh; dwType
0x18003db5f  xor     r8d, r8d; Reserved
0x18003db62  lea     rdx, aThrottlestarte; "ThrottleStartedTime"
0x18003db69  mov     rcx, rdi; hKey
0x18003db6c  call    cs:__imp_RegSetValueExW
0x18003db72  jmp     short loc_18003DB96
0x18003db74  mov     [rsp+60h+dwOptions], eax
0x18003db78  lea     r9, aThrottlemanage_1; "ThrottleManager::SaveThrottleDataState "...
0x18003db7f  mov     r8d, 100h; unsigned int
0x18003db85  lea     rdx, aOnecoreuapDsEx_110; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003db8c  mov     ecx, 5; unsigned __int8
0x18003db91  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003db96  test    rdi, rdi
0x18003db99  jz      short loc_18003DBC9
0x18003db9b  mov     rcx, rdi; hKey
0x18003db9e  call    cs:__imp_RegCloseKey
0x18003dba4  jmp     short loc_18003DBC9
0x18003dba6  mov     [rsp+60h+dwOptions], eax
0x18003dbaa  lea     r9, aThrottlemanage_4; "ThrottleManager::SaveThrottleDataState "...
0x18003dbb1  mov     r8d, 105h; unsigned int
0x18003dbb7  lea     rdx, aOnecoreuapDsEx_110; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003dbbe  mov     ecx, 5; unsigned __int8
0x18003dbc3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003dbc8  nop
0x18003dbc9  lea     rcx, [rbx-18h]; this
0x18003dbcd  mov     rbx, [rsp+60h+arg_8]
0x18003dbd5  add     rsp, 60h
0x18003dbd9  pop     rdi
0x18003dbda  pop     rsi
0x18003dbdb  pop     rbp
0x18003dbdc  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
