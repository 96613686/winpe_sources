# DataStoreReader::LoadMostRecentResultsAndGetState(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,bool)

- ea: `0x180004114`
- end: `0x1800042c8`
- name: `?LoadMostRecentResultsAndGetState@DataStoreReader@@SAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@_N@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct WinSATData *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *, bool)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002678`
- `0x18001ff90`
- `0x180020830`

## callees

- `0x1800039c0`
- `0x180004114`
- `0x1800042d0`
- `0x180004e00`
- `0x18000d07c`
- `0x18000d108`
- `0x18000f8a4`
- `0x18000ff48`
- `0x180010658`
- `0x180010db8`
- `0x18002b22c`
- `0x18002dec0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000429e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000429e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000418c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000418c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004175`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004175`
- `USER32!GetSystemMetrics` at `0x180004167`
- `USER32!GetSystemMetrics` at `0x180004167`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1800041a0`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1800041a0`
- `KERNEL32!ProcessIdToSessionId` at `0x180004182`
- `KERNEL32!ProcessIdToSessionId` at `0x180004182`

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
  int v7; // ebx
  __int16 v8; // dx
  __int64 v9; // rcx
  DWORD pSessionId[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D8h]
  __int64 v12; // [rsp+38h] [rbp-D0h] BYREF
  void *v13; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+48h] [rbp-C0h]
  __int64 v15; // [rsp+58h] [rbp-B0h]
  __int64 v16; // [rsp+60h] [rbp-A8h]
  __int64 v17; // [rsp+68h] [rbp-A0h]
  _BYTE v18[28]; // [rsp+70h] [rbp-98h] BYREF
  int v19; // [rsp+8Ch] [rbp-7Ch]
  __int64 v20; // [rsp+90h] [rbp-78h]
  __int16 v21; // [rsp+98h] [rbp-70h]
  __int16 v22; // [rsp+118h] [rbp+10h]
  __int64 v23; // [rsp+120h] [rbp+18h]
  __int16 v24; // [rsp+128h] [rbp+20h]
  __int16 v25; // [rsp+1A8h] [rbp+A0h]

  v11 = -2;
  result = DataStoreReader::LoadMostRecentResultsGetStateGetDoc(a1, a2, a3);
  if ( (int)result >= 0 )
  {
    if ( *a2 == WINSAT_ASSESSMENT_STATE_VALID )
    {
      GetSystemMetrics(4096);
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
      v13 = 0;
      v14 = 0;
      memset(v18, 0, 24);
      LOBYTE(v12) = 0;
      std::vector<WinsatSystemBoardInfo>::clear(&v13);
      v15 = -1;
      v16 = -1;
      v21 = 0;
      v22 = 0;
      v23 = -1;
      v19 = -1;
      v20 = -1;
      LOBYTE(v17) = 0;
      v24 = 0;
      v25 = 0;
      std::vector<WinsatMemoryInfo>::clear(v18);
      v7 = WinSATCriticalHardwareInfo::PopulateCPUInfo((WinSATCriticalHardwareInfo *)&v12);
      if ( v7 < 0 )
        goto LABEL_11;
      v7 = WinSATCriticalHardwareInfo::PopulateMemoryInfo((WinSATCriticalHardwareInfo *)&v12);
      if ( v7 < 0 )
        goto LABEL_11;
      if ( !(unsigned __int8)WinSATCriticalHardwareInfo::IsPopulated(&v12, 2078) )
      {
        v7 = -2147467259;
LABEL_11:
        WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo((WinSATCriticalHardwareInfo *)&v12);
        return (unsigned int)v7;
      }
      if ( (unsigned int)WinSATCriticalHardwareInfo::GetDifferences((__int64)&v12, (__int64)a1, v8) )
        *a2 = WINSAT_ASSESSMENT_STATE_INCOHERENT_WITH_HARDWARE;
      std::vector<WinsatMemoryInfo>::_Tidy(v18);
      if ( v13 )
      {
        std::vector<WinsatSystemBoardInfo>::_Destroy(v9, v13, v14);
        operator delete(v13);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004114  mov     rax, rsp
0x180004117  push    rbp
0x180004118  push    rsi
0x180004119  push    rdi
0x18000411a  lea     rbp, [rax-0D8h]
0x180004121  sub     rsp, 1C0h
0x180004128  mov     [rsp+1D0h+var_1A8], 0FFFFFFFFFFFFFFFEh
0x180004131  mov     [rax+18h], rbx
0x180004135  mov     rax, cs:__security_cookie
0x18000413c  xor     rax, rsp
0x18000413f  mov     [rbp+0D0h+var_20], rax
0x180004146  mov     rdi, rdx
0x180004149  mov     rsi, rcx
0x18000414c  call    ?LoadMostRecentResultsGetStateGetDoc@DataStoreReader@@KAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@PEAPEAUIXMLDOMDocument2@@@Z; DataStoreReader::LoadMostRecentResultsGetStateGetDoc(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,IXMLDOMDocument2 * *)
0x180004151  test    eax, eax
0x180004153  js      loc_1800042A6
0x180004159  cmp     dword ptr [rdi], 1
0x18000415c  jnz     loc_1800042A4
0x180004162  mov     ecx, 1000h; nIndex
0x180004167  call    cs:__imp_GetSystemMetrics
0x18000416d  mov     [rsp+1D0h+pSessionId], 0
0x180004175  call    cs:__imp_GetCurrentProcessId
0x18000417b  mov     ecx, eax; dwProcessId
0x18000417d  lea     rdx, [rsp+1D0h+pSessionId]; pSessionId
0x180004182  call    cs:__imp_ProcessIdToSessionId
0x180004188  test    eax, eax
0x18000418a  jnz     short loc_1800041A0
0x18000418c  call    cs:__imp_GetLastError
0x180004192  test    eax, eax
0x180004194  jz      short loc_1800041A6
0x180004196  mov     eax, 80004005h
0x18000419b  jmp     loc_1800042A6
0x1800041a0  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800041a6  mov     qword ptr [rsp+1D0h+var_198], 0
0x1800041af  xorps   xmm0, xmm0
0x1800041b2  movdqa  [rsp+1D0h+var_198+8], xmm0
0x1800041b8  mov     qword ptr [rsp+1D0h+var_168], 0
0x1800041c1  xorps   xmm1, xmm1
0x1800041c4  movdqa  xmmword ptr [rsp+1D0h+var_168+8], xmm1
0x1800041ca  mov     byte ptr [rsp+1D0h+var_1A0], 0
0x1800041cf  lea     rcx, [rsp+1D0h+var_198]
0x1800041d4  call    ?clear@?$vector@UWinsatSystemBoardInfo@@V?$allocator@UWinsatSystemBoardInfo@@@std@@@std@@QEAAXXZ; std::vector<WinsatSystemBoardInfo>::clear(void)
0x1800041d9  or      edx, 0FFFFFFFFh
0x1800041dc  mov     dword ptr [rsp+1D0h+var_180], edx
0x1800041e0  mov     dword ptr [rsp+1D0h+var_180+4], edx
0x1800041e4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800041e8  mov     [rsp+1D0h+var_178], rcx
0x1800041ed  xor     eax, eax
0x1800041ef  mov     [rbp+0D0h+var_140], ax
0x1800041f3  mov     [rbp+0D0h+var_C0], ax
0x1800041f7  mov     [rbp+0D0h+var_B8], rcx
0x1800041fb  mov     [rbp+0D0h+var_14C], edx
0x1800041fe  mov     [rbp+0D0h+var_148], rcx
0x180004202  mov     byte ptr [rsp+1D0h+var_170], al
0x180004206  mov     [rbp+0D0h+var_B0], ax
0x18000420a  mov     [rbp+0D0h+var_30], ax
0x180004211  lea     rcx, [rsp+1D0h+var_168]
0x180004216  call    ?clear@?$vector@UWinsatMemoryInfo@@V?$allocator@UWinsatMemoryInfo@@@std@@@std@@QEAAXXZ; std::vector<WinsatMemoryInfo>::clear(void)
0x18000421b  lea     rcx, [rsp+1D0h+var_1A0]; this
0x180004220  call    ?PopulateCPUInfo@WinSATCriticalHardwareInfo@@AEAAJXZ; WinSATCriticalHardwareInfo::PopulateCPUInfo(void)
0x180004225  mov     ebx, eax
0x180004227  test    eax, eax
0x180004229  js      short loc_180004253
0x18000422b  lea     rcx, [rsp+1D0h+var_1A0]; this
0x180004230  call    ?PopulateMemoryInfo@WinSATCriticalHardwareInfo@@AEAAJXZ; WinSATCriticalHardwareInfo::PopulateMemoryInfo(void)
0x180004235  mov     ebx, eax
0x180004237  test    eax, eax
0x180004239  js      short loc_180004253
0x18000423b  mov     edx, 81Eh
0x180004240  lea     rcx, [rsp+1D0h+var_1A0]
0x180004245  call    ?IsPopulated@WinSATCriticalHardwareInfo@@QEBA_NW4HardwareID@@@Z; WinSATCriticalHardwareInfo::IsPopulated(HardwareID)
0x18000424a  test    al, al
0x18000424c  jnz     short loc_180004261
0x18000424e  mov     ebx, 80004005h
0x180004253  lea     rcx, [rsp+1D0h+var_1A0]; this
0x180004258  call    ??1WinSATCriticalHardwareInfo@@QEAA@XZ; WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo(void)
0x18000425d  mov     eax, ebx
0x18000425f  jmp     short loc_1800042A6
0x180004261  mov     r8d, edx
0x180004264  mov     rdx, rsi
0x180004267  lea     rcx, [rsp+1D0h+var_1A0]
0x18000426c  call    ?GetDifferences@WinSATCriticalHardwareInfo@@QEBA?AW4HardwareID@@AEBU1@W42@@Z; WinSATCriticalHardwareInfo::GetDifferences(WinSATCriticalHardwareInfo const &,HardwareID)
0x180004271  test    eax, eax
0x180004273  jz      short loc_18000427B
0x180004275  mov     dword ptr [rdi], 2
0x18000427b  lea     rcx, [rsp+1D0h+var_168]
0x180004280  call    ?_Tidy@?$vector@UWinsatMemoryInfo@@V?$allocator@UWinsatMemoryInfo@@@std@@@std@@IEAAXXZ; std::vector<WinsatMemoryInfo>::_Tidy(void)
0x180004285  mov     rdx, qword ptr [rsp+1D0h+var_198]
0x18000428a  test    rdx, rdx
0x18000428d  jz      short loc_1800042A4
0x18000428f  mov     r8, qword ptr [rsp+1D0h+var_198+8]
0x180004294  call    ?_Destroy@?$vector@UWinsatSystemBoardInfo@@V?$allocator@UWinsatSystemBoardInfo@@@std@@@std@@IEAAXPEAUWinsatSystemBoardInfo@@0@Z; std::vector<WinsatSystemBoardInfo>::_Destroy(WinsatSystemBoardInfo *,WinsatSystemBoardInfo *)
0x180004299  mov     rcx, qword ptr [rsp+1D0h+var_198]
0x18000429e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800042a4  xor     eax, eax
0x1800042a6  mov     rcx, [rbp+0D0h+var_20]
0x1800042ad  xor     rcx, rsp; StackCookie
0x1800042b0  call    __security_check_cookie
0x1800042b5  mov     rbx, [rsp+1D0h+arg_10]
0x1800042bd  add     rsp, 1C0h
0x1800042c4  pop     rdi
0x1800042c5  pop     rsi
0x1800042c6  pop     rbp
0x1800042c7  retn
```
