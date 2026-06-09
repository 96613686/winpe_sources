# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x140008820`
- end: `0x1400089b7`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400050c0`
- `0x14000d380`

## callees

- `0x140004d60`
- `0x140004ef4`
- `0x140005374`
- `0x140006000`
- `0x140006234`
- `0x140007a6c`
- `0x140008820`
- `0x140009770`
- `0x14000a01c`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400088b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400088b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000889e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000889e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400088a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400088ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400088a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400088ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008868`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400088d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400088d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400088c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400088c7`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  DWORD LastError; // esi
  __int64 v8; // r8
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // r8
  const struct wil::details_abi::RawUsageIndex *v14; // r9
  struct wil::details_abi::RawUsageIndex *v15; // rdx
  _BYTE v16[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v17[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v18[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v16);
      v15 = (struct wil::details_abi::RawUsageIndex *)(lpMem + 40);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap((wil::details_abi::RawUsageIndex *)v16, v15);
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v17,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v18,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v16, (__int64)v15, v13, v14);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v16);
    }
  }
  else
  {
    v2 = (void *)*((_QWORD *)lpMem + 1);
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v11, v12);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v8, v9);
        SetLastError(LastError);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(lpMem);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x140008820  mov     [rsp+arg_0], rbx
0x140008825  mov     [rsp+arg_8], rsi
0x14000882a  push    rdi
0x14000882b  sub     rsp, 0E0h
0x140008832  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008839  mov     rbx, rcx
0x14000883c  jnz     loc_1400088FC
0x140008842  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008849  test    rax, rax
0x14000884c  jz      short loc_14000885B
0x14000884e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008853  test    al, al
0x140008855  jnz     loc_1400088FC
0x14000885b  mov     rdi, [rbx+8]
0x14000885f  xor     r8d, r8d; bAlertable
0x140008862  mov     rcx, rdi; hHandle
0x140008865  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140008868  call    cs:__imp_WaitForSingleObjectEx
0x14000886e  cmp     eax, 102h
0x140008873  jz      short loc_140008882
0x140008875  test    eax, 0FFFFFF7Fh
0x14000887a  jnz     loc_140008996
0x140008880  jmp     short loc_140008884
0x140008882  xor     edi, edi
0x140008884  mov     eax, [rbx]
0x140008886  dec     eax
0x140008888  mov     [rbx], eax
0x14000888a  mov     eax, [rbx]
0x14000888c  test    eax, eax
0x14000888e  jnz     short loc_1400088E0
0x140008890  lea     rcx, [rbx+10h]; this
0x140008894  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x140008899  test    rdi, rdi
0x14000889c  jz      short loc_1400088BF
0x14000889e  call    cs:__imp_GetLastError
0x1400088a4  mov     rcx, rdi; hMutex
0x1400088a7  mov     esi, eax
0x1400088a9  call    cs:__imp_ReleaseMutex
0x1400088af  test    eax, eax
0x1400088b1  jz      loc_140008983
0x1400088b7  mov     ecx, esi; dwErrCode
0x1400088b9  call    cs:__imp_SetLastError
0x1400088bf  mov     rcx, rbx
0x1400088c2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1400088c7  call    cs:__imp_GetProcessHeap
0x1400088cd  mov     r8, rbx; lpMem
0x1400088d0  xor     edx, edx; dwFlags
0x1400088d2  mov     rcx, rax; hHeap
0x1400088d5  call    cs:__imp_HeapFree
0x1400088db  jmp     loc_14000896E
0x1400088e0  test    rdi, rdi
0x1400088e3  jz      loc_14000896E
0x1400088e9  mov     rcx, rdi; hMutex
0x1400088ec  call    cs:__imp_ReleaseMutex
0x1400088f2  test    eax, eax
0x1400088f4  jz      loc_1400089A4
0x1400088fa  jmp     short loc_14000896E
0x1400088fc  mov     eax, [rbx]
0x1400088fe  dec     eax
0x140008900  mov     [rbx], eax
0x140008902  mov     eax, [rbx]
0x140008904  test    eax, eax
0x140008906  jnz     short loc_14000896E
0x140008908  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000890d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140008912  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x140008916  cmp     byte ptr [rdx+38h], 0
0x14000891a  jz      short loc_140008926
0x14000891c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008921  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008926  cmp     byte ptr [rbx+0A0h], 0
0x14000892d  jz      short loc_14000893D
0x14000892f  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x140008933  lea     rcx, [rsp+0E8h+var_88]; this
0x140008938  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000893d  cmp     byte ptr [rbx+0E0h], 0
0x140008944  jz      short loc_14000895A
0x140008946  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x14000894d  lea     rcx, [rsp+0E8h+var_48]; this
0x140008955  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000895a  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000895f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140008964  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008969  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000896e  lea     r11, [rsp+0E8h+var_8]
0x140008976  mov     rbx, [r11+10h]
0x14000897a  mov     rsi, [r11+18h]
0x14000897e  mov     rsp, r11
0x140008981  pop     rdi
0x140008982  retn
0x140008983  mov     rcx, [rsp+0E8h]; this
0x14000898b  mov     edx, 0A15h; void *
0x140008990  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008996  mov     rcx, [rsp+0E8h]; this
0x14000899e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400089a4  mov     rcx, [rsp+0E8h]; this
0x1400089ac  mov     edx, 0A15h; void *
0x1400089b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
