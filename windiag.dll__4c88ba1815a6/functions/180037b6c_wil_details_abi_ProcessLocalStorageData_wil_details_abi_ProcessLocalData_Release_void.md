# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180037b6c`
- end: `0x180037c87`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `283`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18009bc30`

## callees

- `0x180033c68`
- `0x180034f80`
- `0x180035284`
- `0x180037b6c`
- `0x1800396fc`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037bb1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037c2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037c2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037c1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037c1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037c0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037c0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037be7`

## string_xrefs

- `0x180037c53`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180037c75`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(__int64 *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  int result; // eax
  DWORD LastError; // esi
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v11);
      }
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v9);
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
0x180037b6c  mov     [rsp+arg_0], rbx
0x180037b71  mov     [rsp+arg_8], rsi
0x180037b76  push    rdi
0x180037b77  sub     rsp, 20h
0x180037b7b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180037b82  mov     rbx, rcx
0x180037b85  jnz     loc_180037C36
0x180037b8b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180037b92  test    rax, rax
0x180037b95  jz      short loc_180037BA4
0x180037b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b9c  test    al, al
0x180037b9e  jnz     loc_180037C36
0x180037ba4  mov     rdi, [rbx+8]
0x180037ba8  xor     r8d, r8d; bAlertable
0x180037bab  mov     rcx, rdi; hHandle
0x180037bae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037bb1  call    cs:__imp_WaitForSingleObjectEx
0x180037bb7  cmp     eax, 102h
0x180037bbc  jz      short loc_180037BCB
0x180037bbe  test    eax, 0FFFFFF7Fh
0x180037bc3  jnz     loc_180037C65
0x180037bc9  jmp     short loc_180037BCD
0x180037bcb  xor     edi, edi
0x180037bcd  mov     eax, [rbx]
0x180037bcf  dec     eax
0x180037bd1  mov     [rbx], eax
0x180037bd3  mov     eax, [rbx]
0x180037bd5  test    eax, eax
0x180037bd7  jnz     short loc_180037C22
0x180037bd9  lea     rcx, [rbx+10h]; this
0x180037bdd  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180037be2  test    rdi, rdi
0x180037be5  jz      short loc_180037C04
0x180037be7  call    cs:__imp_GetLastError
0x180037bed  mov     rcx, rdi; hMutex
0x180037bf0  mov     esi, eax
0x180037bf2  call    cs:__imp_ReleaseMutex
0x180037bf8  test    eax, eax
0x180037bfa  jz      short loc_180037C4E
0x180037bfc  mov     ecx, esi; dwErrCode
0x180037bfe  call    cs:__imp_SetLastError
0x180037c04  mov     rcx, rbx
0x180037c07  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180037c0c  call    cs:__imp_GetProcessHeap
0x180037c12  mov     r8, rbx; lpMem
0x180037c15  xor     edx, edx; dwFlags
0x180037c17  mov     rcx, rax; hHeap
0x180037c1a  call    cs:__imp_HeapFree
0x180037c20  jmp     short loc_180037C3E
0x180037c22  test    rdi, rdi
0x180037c25  jz      short loc_180037C3E
0x180037c27  mov     rcx, rdi; hMutex
0x180037c2a  call    cs:__imp_ReleaseMutex
0x180037c30  test    eax, eax
0x180037c32  jz      short loc_180037C70
0x180037c34  jmp     short loc_180037C3E
0x180037c36  mov     eax, [rbx]
0x180037c38  dec     eax
0x180037c3a  mov     [rbx], eax
0x180037c3c  mov     eax, [rbx]
0x180037c3e  mov     rbx, [rsp+28h+arg_0]
0x180037c43  mov     rsi, [rsp+28h+arg_8]
0x180037c48  add     rsp, 20h
0x180037c4c  pop     rdi
0x180037c4d  retn
0x180037c4e  mov     rcx, [rsp+28h]; this
0x180037c53  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037c5a  mov     edx, 0A15h; void *
0x180037c5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180037c65  mov     rcx, [rsp+28h]; this
0x180037c6a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180037c70  mov     rcx, [rsp+28h]; this
0x180037c75  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037c7c  mov     edx, 0A15h; void *
0x180037c81  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
