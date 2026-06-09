# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x14000a168`
- end: `0x14000a2ff`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x14000864c`
- `0x14000b3f0`

## callees

- `0x140004384`
- `0x140004498`
- `0x140006cf8`
- `0x1400083b8`
- `0x140008480`
- `0x140008840`
- `0x140009540`
- `0x14000a168`
- `0x14000a5c0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a1f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a234`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a1f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a234`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a1b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a1b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a21d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a21d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a20f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a20f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a1e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a1e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a201`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a201`

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
0x14000a168  mov     [rsp+arg_0], rbx
0x14000a16d  mov     [rsp+arg_8], rsi
0x14000a172  push    rdi
0x14000a173  sub     rsp, 0E0h
0x14000a17a  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a181  mov     rbx, rcx
0x14000a184  jnz     loc_14000A244
0x14000a18a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a191  test    rax, rax
0x14000a194  jz      short loc_14000A1A3
0x14000a196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a19b  test    al, al
0x14000a19d  jnz     loc_14000A244
0x14000a1a3  mov     rdi, [rbx+8]
0x14000a1a7  xor     r8d, r8d; bAlertable
0x14000a1aa  mov     rcx, rdi; hHandle
0x14000a1ad  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000a1b0  call    cs:__imp_WaitForSingleObjectEx
0x14000a1b6  cmp     eax, 102h
0x14000a1bb  jz      short loc_14000A1CA
0x14000a1bd  test    eax, 0FFFFFF7Fh
0x14000a1c2  jnz     loc_14000A2DE
0x14000a1c8  jmp     short loc_14000A1CC
0x14000a1ca  xor     edi, edi
0x14000a1cc  mov     eax, [rbx]
0x14000a1ce  dec     eax
0x14000a1d0  mov     [rbx], eax
0x14000a1d2  mov     eax, [rbx]
0x14000a1d4  test    eax, eax
0x14000a1d6  jnz     short loc_14000A228
0x14000a1d8  lea     rcx, [rbx+10h]; this
0x14000a1dc  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x14000a1e1  test    rdi, rdi
0x14000a1e4  jz      short loc_14000A207
0x14000a1e6  call    cs:__imp_GetLastError
0x14000a1ec  mov     rcx, rdi; hMutex
0x14000a1ef  mov     esi, eax
0x14000a1f1  call    cs:__imp_ReleaseMutex
0x14000a1f7  test    eax, eax
0x14000a1f9  jz      loc_14000A2CB
0x14000a1ff  mov     ecx, esi; dwErrCode
0x14000a201  call    cs:__imp_SetLastError
0x14000a207  mov     rcx, rbx
0x14000a20a  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x14000a20f  call    cs:__imp_GetProcessHeap
0x14000a215  mov     r8, rbx; lpMem
0x14000a218  xor     edx, edx; dwFlags
0x14000a21a  mov     rcx, rax; hHeap
0x14000a21d  call    cs:__imp_HeapFree
0x14000a223  jmp     loc_14000A2B6
0x14000a228  test    rdi, rdi
0x14000a22b  jz      loc_14000A2B6
0x14000a231  mov     rcx, rdi; hMutex
0x14000a234  call    cs:__imp_ReleaseMutex
0x14000a23a  test    eax, eax
0x14000a23c  jz      loc_14000A2EC
0x14000a242  jmp     short loc_14000A2B6
0x14000a244  mov     eax, [rbx]
0x14000a246  dec     eax
0x14000a248  mov     [rbx], eax
0x14000a24a  mov     eax, [rbx]
0x14000a24c  test    eax, eax
0x14000a24e  jnz     short loc_14000A2B6
0x14000a250  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a255  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000a25a  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x14000a25e  cmp     byte ptr [rdx+38h], 0
0x14000a262  jz      short loc_14000A26E
0x14000a264  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a269  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000a26e  cmp     byte ptr [rbx+0A0h], 0
0x14000a275  jz      short loc_14000A285
0x14000a277  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x14000a27b  lea     rcx, [rsp+0E8h+var_88]; this
0x14000a280  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000a285  cmp     byte ptr [rbx+0E0h], 0
0x14000a28c  jz      short loc_14000A2A2
0x14000a28e  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x14000a295  lea     rcx, [rsp+0E8h+var_48]; this
0x14000a29d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000a2a2  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a2a7  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000a2ac  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a2b1  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000a2b6  lea     r11, [rsp+0E8h+var_8]
0x14000a2be  mov     rbx, [r11+10h]
0x14000a2c2  mov     rsi, [r11+18h]
0x14000a2c6  mov     rsp, r11
0x14000a2c9  pop     rdi
0x14000a2ca  retn
0x14000a2cb  mov     rcx, [rsp+0E8h]; this
0x14000a2d3  mov     edx, 0A15h; void *
0x14000a2d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a2de  mov     rcx, [rsp+0E8h]; this
0x14000a2e6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000a2ec  mov     rcx, [rsp+0E8h]; this
0x14000a2f4  mov     edx, 0A15h; void *
0x14000a2f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
