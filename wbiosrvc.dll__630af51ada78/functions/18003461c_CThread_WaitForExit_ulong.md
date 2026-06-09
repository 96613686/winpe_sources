# CThread::WaitForExit(ulong)

- ea: `0x18003461c`
- end: `0x180034678`
- name: `?WaitForExit@CThread@@AEBAEK@Z`
- size: `92`
- prototype: `unsigned __int8(CThread *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180034604`
- `0x18005262c`

## callees

- `0x18003461c`
- `0x180060964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034643`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034633`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034633`

## string_xrefs

- `0x180034666`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`

## pseudocode

```c
bool __fastcall CThread::WaitForExit(CThread *this, DWORD a2)
{
  int v2; // ebx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() == v2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
      v5);
  return WaitForSingleObject(*((HANDLE *)this + 15), a2) != 258;
}

```

## disassembly

```asm
0x18003461c  mov     [rsp+arg_0], rbx
0x180034621  mov     [rsp+arg_8], rsi
0x180034626  push    rdi
0x180034627  sub     rsp, 20h
0x18003462b  mov     ebx, [rcx+10h]
0x18003462e  mov     esi, edx
0x180034630  mov     rdi, rcx
0x180034633  call    cs:__imp_GetCurrentThreadId
0x180034639  cmp     eax, ebx
0x18003463b  jz      short loc_180034661
0x18003463d  mov     rcx, [rdi+78h]; hHandle
0x180034641  mov     edx, esi; dwMilliseconds
0x180034643  call    cs:__imp_WaitForSingleObject
0x180034649  mov     rbx, [rsp+28h+arg_0]
0x18003464e  cmp     eax, 102h
0x180034653  mov     rsi, [rsp+28h+arg_8]
0x180034658  setnz   al
0x18003465b  add     rsp, 20h
0x18003465f  pop     rdi
0x180034660  retn
0x180034661  mov     rcx, [rsp+28h]; this
0x180034666  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\biometrics\\cred"...
0x18003466d  mov     edx, 174h; void *
0x180034672  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
