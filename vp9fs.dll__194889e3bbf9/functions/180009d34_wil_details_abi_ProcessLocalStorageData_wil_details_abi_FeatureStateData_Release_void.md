# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180009d34`
- end: `0x180009e5a`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `294`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180006158`
- `0x180033c00`

## callees

- `0x180005f24`
- `0x1800071a0`
- `0x1800074e0`
- `0x180008b90`
- `0x180009d34`
- `0x18000b76c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009df2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009df2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009d79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009d79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009de2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009de2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009daf`

## string_xrefs

- `0x180009e38`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
      wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)(lpMem + 4));
  }
  else
  {
    v2 = (void *)lpMem[1];
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v9, v10);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
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
0x180009d34  mov     [rsp+arg_8], rbx
0x180009d39  mov     [rsp+arg_10], rsi
0x180009d3e  push    rdi
0x180009d3f  sub     rsp, 20h
0x180009d43  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009d4a  mov     rbx, rcx
0x180009d4d  jnz     loc_180009DFE
0x180009d53  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009d5a  test    rax, rax
0x180009d5d  jz      short loc_180009D6C
0x180009d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d64  test    al, al
0x180009d66  jnz     loc_180009DFE
0x180009d6c  mov     rdi, [rbx+8]
0x180009d70  xor     r8d, r8d; bAlertable
0x180009d73  mov     rcx, rdi; hHandle
0x180009d76  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009d79  call    cs:__imp_WaitForSingleObjectEx
0x180009d7f  cmp     eax, 102h
0x180009d84  jz      short loc_180009D93
0x180009d86  test    eax, 0FFFFFF7Fh
0x180009d8b  jnz     loc_180009E33
0x180009d91  jmp     short loc_180009D95
0x180009d93  xor     edi, edi
0x180009d95  mov     eax, [rbx]
0x180009d97  dec     eax
0x180009d99  mov     [rbx], eax
0x180009d9b  mov     eax, [rbx]
0x180009d9d  test    eax, eax
0x180009d9f  jnz     short loc_180009DEA
0x180009da1  lea     rcx, [rbx+10h]; this
0x180009da5  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180009daa  test    rdi, rdi
0x180009dad  jz      short loc_180009DCC
0x180009daf  call    cs:__imp_GetLastError
0x180009db5  mov     rcx, rdi; hMutex
0x180009db8  mov     esi, eax
0x180009dba  call    cs:__imp_ReleaseMutex
0x180009dc0  test    eax, eax
0x180009dc2  jz      short loc_180009E23
0x180009dc4  mov     ecx, esi; dwErrCode
0x180009dc6  call    cs:__imp_SetLastError
0x180009dcc  mov     rcx, rbx
0x180009dcf  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x180009dd4  call    cs:__imp_GetProcessHeap
0x180009dda  mov     r8, rbx; lpMem
0x180009ddd  xor     edx, edx; dwFlags
0x180009ddf  mov     rcx, rax; hHeap
0x180009de2  call    cs:__imp_HeapFree
0x180009de8  jmp     short loc_180009E13
0x180009dea  test    rdi, rdi
0x180009ded  jz      short loc_180009E13
0x180009def  mov     rcx, rdi; hMutex
0x180009df2  call    cs:__imp_ReleaseMutex
0x180009df8  test    eax, eax
0x180009dfa  jz      short loc_180009E4A
0x180009dfc  jmp     short loc_180009E13
0x180009dfe  mov     eax, [rbx]
0x180009e00  dec     eax
0x180009e02  mov     [rbx], eax
0x180009e04  mov     eax, [rbx]
0x180009e06  test    eax, eax
0x180009e08  jnz     short loc_180009E13
0x180009e0a  lea     rcx, [rbx+20h]; this
0x180009e0e  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x180009e13  mov     rbx, [rsp+28h+arg_8]
0x180009e18  mov     rsi, [rsp+28h+arg_10]
0x180009e1d  add     rsp, 20h
0x180009e21  pop     rdi
0x180009e22  retn
0x180009e23  mov     rcx, [rsp+28h]; this
0x180009e28  mov     edx, 0A15h; void *
0x180009e2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009e33  mov     rcx, [rsp+28h]; this
0x180009e38  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009e3f  mov     edx, 0E01h; void *
0x180009e44  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009e4a  mov     rcx, [rsp+28h]; this
0x180009e4f  mov     edx, 0A15h; void *
0x180009e54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
