# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180037c90`
- end: `0x180037e63`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `467`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180033fc8`
- `0x18009bbd0`

## callees

- `0x180033b68`
- `0x180033ef0`
- `0x180034278`
- `0x1800343cc`
- `0x180034f80`
- `0x180035284`
- `0x180036c6c`
- `0x180037c90`
- `0x180038d04`
- `0x1800396fc`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037cd2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037cd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037d13`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037d77`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037d13`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037d77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037d60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037d60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037d52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037d52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d44`

## string_xrefs

- `0x180037e0f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180037e37`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180037e51`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  DWORD LastError; // ebp
  const char *v8; // r9
  void *v9; // rcx
  const char *v10; // r9
  HANDLE ProcessHeap; // rax
  const char *v12; // r9
  _BYTE v13[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v15[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v13);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v13);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v13);
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v12);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v8);
        SetLastError(LastError);
      }
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v9 = (void *)*((_QWORD *)lpMem + 1);
      if ( v9 )
      {
        if ( !CloseHandle(v9) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v10);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x180037c90  push    rbx
0x180037c92  push    rbp
0x180037c93  push    rsi
0x180037c94  push    rdi
0x180037c95  sub     rsp, 0E8h
0x180037c9c  mov     rbx, rcx
0x180037c9f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180037ca6  jnz     loc_180037D87
0x180037cac  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180037cb3  test    rax, rax
0x180037cb6  jz      short loc_180037CC5
0x180037cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cbd  test    al, al
0x180037cbf  jnz     loc_180037D87
0x180037cc5  mov     rdi, [rbx+8]
0x180037cc9  xor     r8d, r8d; bAlertable
0x180037ccc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037ccf  mov     rcx, rdi; hHandle
0x180037cd2  call    cs:__imp_WaitForSingleObjectEx
0x180037cd8  cmp     eax, 102h
0x180037cdd  jz      short loc_180037CEC
0x180037cdf  test    eax, 0FFFFFF7Fh
0x180037ce4  jnz     loc_180037E21
0x180037cea  jmp     short loc_180037CEE
0x180037cec  xor     edi, edi
0x180037cee  mov     eax, [rbx]
0x180037cf0  dec     eax
0x180037cf2  mov     [rbx], eax
0x180037cf4  mov     eax, [rbx]
0x180037cf6  test    eax, eax
0x180037cf8  jnz     short loc_180037D6B
0x180037cfa  lea     rcx, [rbx+10h]; this
0x180037cfe  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180037d03  test    rdi, rdi
0x180037d06  jz      short loc_180037D29
0x180037d08  call    cs:__imp_GetLastError
0x180037d0e  mov     ebp, eax
0x180037d10  mov     rcx, rdi; hMutex
0x180037d13  call    cs:__imp_ReleaseMutex
0x180037d19  test    eax, eax
0x180037d1b  jz      loc_180037E49
0x180037d21  mov     ecx, ebp; dwErrCode
0x180037d23  call    cs:__imp_SetLastError
0x180037d29  lea     rcx, [rbx+20h]; this
0x180037d2d  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x180037d32  lea     rcx, [rbx+10h]; this
0x180037d36  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180037d3b  mov     rcx, [rbx+8]; hObject
0x180037d3f  test    rcx, rcx
0x180037d42  jz      short loc_180037D52
0x180037d44  call    cs:__imp_CloseHandle
0x180037d4a  test    eax, eax
0x180037d4c  jz      loc_180037E07
0x180037d52  call    cs:__imp_GetProcessHeap
0x180037d58  mov     rcx, rax; hHeap
0x180037d5b  mov     r8, rbx; lpMem
0x180037d5e  xor     edx, edx; dwFlags
0x180037d60  call    cs:__imp_HeapFree
0x180037d66  jmp     loc_180037DFB
0x180037d6b  test    rdi, rdi
0x180037d6e  jz      loc_180037DFB
0x180037d74  mov     rcx, rdi; hMutex
0x180037d77  call    cs:__imp_ReleaseMutex
0x180037d7d  test    eax, eax
0x180037d7f  jz      loc_180037E2F
0x180037d85  jmp     short loc_180037DFB
0x180037d87  mov     eax, [rbx]
0x180037d89  dec     eax
0x180037d8b  mov     [rbx], eax
0x180037d8d  mov     eax, [rbx]
0x180037d8f  test    eax, eax
0x180037d91  jnz     short loc_180037DFB
0x180037d93  lea     rcx, [rsp+108h+var_E8]; this
0x180037d98  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180037d9d  nop
0x180037d9e  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180037da2  cmp     byte ptr [rdx+38h], 0
0x180037da6  jz      short loc_180037DB2
0x180037da8  lea     rcx, [rsp+108h+var_E8]; this
0x180037dad  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180037db2  cmp     byte ptr [rbx+0A0h], 0
0x180037db9  jz      short loc_180037DC9
0x180037dbb  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180037dbf  lea     rcx, [rsp+108h+var_A8]; this
0x180037dc4  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180037dc9  cmp     byte ptr [rbx+0E0h], 0
0x180037dd0  jz      short loc_180037DE6
0x180037dd2  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180037dd9  lea     rcx, [rsp+108h+var_68]; this
0x180037de1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180037de6  lea     rcx, [rsp+108h+var_E8]; this
0x180037deb  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180037df0  nop
0x180037df1  lea     rcx, [rsp+108h+var_E8]; this
0x180037df6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180037dfb  add     rsp, 0E8h
0x180037e02  pop     rdi
0x180037e03  pop     rsi
0x180037e04  pop     rbp
0x180037e05  pop     rbx
0x180037e06  retn
0x180037e07  mov     rcx, [rsp+108h]; this
0x180037e0f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037e16  mov     edx, 0A0Bh; void *
0x180037e1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180037e21  mov     rcx, [rsp+108h]; this
0x180037e29  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180037e2f  mov     rcx, [rsp+108h]; this
0x180037e37  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037e3e  mov     edx, 0A15h; void *
0x180037e43  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180037e49  mov     rcx, [rsp+108h]; this
0x180037e51  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037e58  mov     edx, 0A15h; void *
0x180037e5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
