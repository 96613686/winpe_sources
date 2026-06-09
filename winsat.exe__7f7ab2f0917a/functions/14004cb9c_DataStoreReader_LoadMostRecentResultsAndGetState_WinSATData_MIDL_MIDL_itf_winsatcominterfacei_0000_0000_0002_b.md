# DataStoreReader::LoadMostRecentResultsAndGetState(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,bool)

- ea: `0x14004cb9c`
- end: `0x14004ccac`
- name: `?LoadMostRecentResultsAndGetState@DataStoreReader@@SAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@_N@Z`
- size: `272`
- prototype: `__int64 __fastcall(struct WinSATData *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000917c`
- `0x140032ec8`

## callees

- `0x140007a74`
- `0x140049be0`
- `0x14004c2b0`
- `0x14004cb9c`
- `0x14004ccb4`
- `0x14004d72c`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14004cbe9`
- `KERNEL32!GetCurrentProcessId` at `0x14004cbe9`
- `KERNEL32!GetLastError` at `0x14004cc00`
- `KERNEL32!GetLastError` at `0x14004cc00`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x14004cc11`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x14004cc11`
- `KERNEL32!ProcessIdToSessionId` at `0x14004cbf6`
- `KERNEL32!ProcessIdToSessionId` at `0x14004cbf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreReader::LoadMostRecentResultsAndGetState(
        struct WinSATData *a1,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *a2,
        struct IXMLDOMDocument2 **a3)
{
  __int64 result; // rax
  DWORD CurrentProcessId; // eax
  int v7; // edi
  DWORD pSessionId[4]; // [rsp+20h] [rbp-1A8h] BYREF
  _BYTE v9[8]; // [rsp+30h] [rbp-198h] BYREF
  __int64 v10; // [rsp+38h] [rbp-190h]
  __int128 v11; // [rsp+40h] [rbp-188h]
  __int64 v12; // [rsp+68h] [rbp-160h]
  __int128 v13; // [rsp+70h] [rbp-158h]

  result = DataStoreReader::LoadMostRecentResultsGetStateGetDoc(a1, a2, a3);
  if ( (int)result >= 0 )
  {
    if ( *a2 == WINSAT_ASSESSMENT_STATE_VALID )
    {
      RunningOverTs();
      pSessionId[0] = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( ProcessIdToSessionId(CurrentProcessId, pSessionId) )
      {
        WTSGetActiveConsoleSessionId();
      }
      else if ( GetLastError() )
      {
        return 2147500037LL;
      }
      v10 = 0;
      v11 = 0;
      v12 = 0;
      v13 = 0;
      v7 = WinSATCriticalHardwareInfo::PopulateFromCurrentHardware(v9, 2078);
      if ( v7 < 0 )
      {
        WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo((WinSATCriticalHardwareInfo *)v9);
        return (unsigned int)v7;
      }
      if ( (unsigned int)WinSATCriticalHardwareInfo::GetDifferences(v9, a1, 2078) )
        *a2 = WINSAT_ASSESSMENT_STATE_INCOHERENT_WITH_HARDWARE;
      WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo((WinSATCriticalHardwareInfo *)v9);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14004cb9c  mov     [rsp+arg_10], rbx
0x14004cba1  mov     [rsp+arg_18], rsi
0x14004cba6  push    rdi
0x14004cba7  sub     rsp, 1C0h
0x14004cbae  mov     rax, cs:__security_cookie
0x14004cbb5  xor     rax, rsp
0x14004cbb8  mov     [rsp+1C8h+var_18], rax
0x14004cbc0  mov     rbx, rdx
0x14004cbc3  mov     rsi, rcx
0x14004cbc6  call    ?LoadMostRecentResultsGetStateGetDoc@DataStoreReader@@KAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@PEAPEAUIXMLDOMDocument2@@@Z; DataStoreReader::LoadMostRecentResultsGetStateGetDoc(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,IXMLDOMDocument2 * *)
0x14004cbcb  test    eax, eax
0x14004cbcd  js      loc_14004CC87
0x14004cbd3  cmp     dword ptr [rbx], 1
0x14004cbd6  jnz     loc_14004CC85
0x14004cbdc  call    ?RunningOverTs@@YA_NXZ; RunningOverTs(void)
0x14004cbe1  mov     [rsp+1C8h+pSessionId], 0
0x14004cbe9  call    cs:__imp_GetCurrentProcessId
0x14004cbef  mov     ecx, eax; dwProcessId
0x14004cbf1  lea     rdx, [rsp+1C8h+pSessionId]; pSessionId
0x14004cbf6  call    cs:__imp_ProcessIdToSessionId
0x14004cbfc  test    eax, eax
0x14004cbfe  jnz     short loc_14004CC11
0x14004cc00  call    cs:__imp_GetLastError
0x14004cc06  test    eax, eax
0x14004cc08  jz      short loc_14004CC17
0x14004cc0a  mov     eax, 80004005h
0x14004cc0f  jmp     short loc_14004CC87
0x14004cc11  call    cs:__imp_WTSGetActiveConsoleSessionId
0x14004cc17  mov     [rsp+1C8h+var_190], 0
0x14004cc20  xorps   xmm0, xmm0
0x14004cc23  movdqa  [rsp+1C8h+var_188], xmm0
0x14004cc29  mov     [rsp+1C8h+var_160], 0
0x14004cc32  xorps   xmm1, xmm1
0x14004cc35  movdqa  [rsp+1C8h+var_158], xmm1
0x14004cc3b  mov     edx, 81Eh
0x14004cc40  lea     rcx, [rsp+1C8h+var_198]
0x14004cc45  call    ?PopulateFromCurrentHardware@WinSATCriticalHardwareInfo@@QEAAJW4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateFromCurrentHardware(HardwareID)
0x14004cc4a  mov     edi, eax
0x14004cc4c  test    eax, eax
0x14004cc4e  jns     short loc_14004CC5E
0x14004cc50  lea     rcx, [rsp+1C8h+var_198]; this
0x14004cc55  call    ??1WinSATCriticalHardwareInfo@@QEAA@XZ; WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo(void)
0x14004cc5a  mov     eax, edi
0x14004cc5c  jmp     short loc_14004CC87
0x14004cc5e  mov     r8d, 81Eh
0x14004cc64  mov     rdx, rsi
0x14004cc67  lea     rcx, [rsp+1C8h+var_198]
0x14004cc6c  call    ?GetDifferences@WinSATCriticalHardwareInfo@@QEBA?AW4HardwareID@@AEBU1@W42@@Z; WinSATCriticalHardwareInfo::GetDifferences(WinSATCriticalHardwareInfo const &,HardwareID)
0x14004cc71  test    eax, eax
0x14004cc73  jz      short loc_14004CC7B
0x14004cc75  mov     dword ptr [rbx], 2
0x14004cc7b  lea     rcx, [rsp+1C8h+var_198]; this
0x14004cc80  call    ??1WinSATCriticalHardwareInfo@@QEAA@XZ; WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo(void)
0x14004cc85  xor     eax, eax
0x14004cc87  mov     rcx, [rsp+1C8h+var_18]
0x14004cc8f  xor     rcx, rsp; StackCookie
0x14004cc92  call    __security_check_cookie
0x14004cc97  lea     r11, [rsp+1C8h+var_8]
0x14004cc9f  mov     rbx, [r11+20h]
0x14004cca3  mov     rsi, [r11+28h]
0x14004cca7  mov     rsp, r11
0x14004ccaa  pop     rdi
0x14004ccab  retn
```
