# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180009c14`
- end: `0x180009d2d`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180033c60`

## callees

- `0x180005e58`
- `0x1800071a0`
- `0x1800074e0`
- `0x180009c14`
- `0x18000b76c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009cd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009cd2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009c59`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009c59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ca6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c8f`

## string_xrefs

- `0x180009d0b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  unsigned int v7; // r8d
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return --*(_DWORD *)lpMem;
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
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v10, v11);
      }
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v7, v8);
        SetLastError(LastError);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(lpMem);
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009c14  mov     [rsp+arg_8], rbx
0x180009c19  mov     [rsp+arg_10], rsi
0x180009c1e  push    rdi
0x180009c1f  sub     rsp, 20h
0x180009c23  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009c2a  mov     rbx, rcx
0x180009c2d  jnz     loc_180009CDE
0x180009c33  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009c3a  test    rax, rax
0x180009c3d  jz      short loc_180009C4C
0x180009c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c44  test    al, al
0x180009c46  jnz     loc_180009CDE
0x180009c4c  mov     rdi, [rbx+8]
0x180009c50  xor     r8d, r8d; bAlertable
0x180009c53  mov     rcx, rdi; hHandle
0x180009c56  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009c59  call    cs:__imp_WaitForSingleObjectEx
0x180009c5f  cmp     eax, 102h
0x180009c64  jz      short loc_180009C73
0x180009c66  test    eax, 0FFFFFF7Fh
0x180009c6b  jnz     loc_180009D06
0x180009c71  jmp     short loc_180009C75
0x180009c73  xor     edi, edi
0x180009c75  mov     eax, [rbx]
0x180009c77  dec     eax
0x180009c79  mov     [rbx], eax
0x180009c7b  mov     eax, [rbx]
0x180009c7d  test    eax, eax
0x180009c7f  jnz     short loc_180009CCA
0x180009c81  lea     rcx, [rbx+10h]; this
0x180009c85  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180009c8a  test    rdi, rdi
0x180009c8d  jz      short loc_180009CAC
0x180009c8f  call    cs:__imp_GetLastError
0x180009c95  mov     rcx, rdi; hMutex
0x180009c98  mov     esi, eax
0x180009c9a  call    cs:__imp_ReleaseMutex
0x180009ca0  test    eax, eax
0x180009ca2  jz      short loc_180009CF6
0x180009ca4  mov     ecx, esi; dwErrCode
0x180009ca6  call    cs:__imp_SetLastError
0x180009cac  mov     rcx, rbx
0x180009caf  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180009cb4  call    cs:__imp_GetProcessHeap
0x180009cba  mov     r8, rbx; lpMem
0x180009cbd  xor     edx, edx; dwFlags
0x180009cbf  mov     rcx, rax; hHeap
0x180009cc2  call    cs:__imp_HeapFree
0x180009cc8  jmp     short loc_180009CE6
0x180009cca  test    rdi, rdi
0x180009ccd  jz      short loc_180009CE6
0x180009ccf  mov     rcx, rdi; hMutex
0x180009cd2  call    cs:__imp_ReleaseMutex
0x180009cd8  test    eax, eax
0x180009cda  jz      short loc_180009D1D
0x180009cdc  jmp     short loc_180009CE6
0x180009cde  mov     eax, [rbx]
0x180009ce0  dec     eax
0x180009ce2  mov     [rbx], eax
0x180009ce4  mov     eax, [rbx]
0x180009ce6  mov     rbx, [rsp+28h+arg_8]
0x180009ceb  mov     rsi, [rsp+28h+arg_10]
0x180009cf0  add     rsp, 20h
0x180009cf4  pop     rdi
0x180009cf5  retn
0x180009cf6  mov     rcx, [rsp+28h]; this
0x180009cfb  mov     edx, 0A15h; void *
0x180009d00  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d06  mov     rcx, [rsp+28h]; this
0x180009d0b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009d12  mov     edx, 0E01h; void *
0x180009d17  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009d1d  mov     rcx, [rsp+28h]; this
0x180009d22  mov     edx, 0A15h; void *
0x180009d27  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
