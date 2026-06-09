# CRevertToSelf::IsImpersonated(void)

- ea: `0x1801ba280`
- end: `0x1801ba2ee`
- name: `?IsImpersonated@CRevertToSelf@@SAHXZ`
- size: `110`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012d020`
- `0x1801aab18`
- `0x180221b88`

## callees

- `0x1801480fc`
- `0x1801ba280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ba2b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ba2b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ba28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ba28d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ba2a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ba2a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ba2b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ba2b1`

## string_xrefs

- `0x1801ba2c9`: `[UtilSecurity] OpenThreadToken() failed. 0x%08x`

## pseudocode

```c
__int64 CRevertToSelf::IsImpersonated(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    CloseHandle(TokenHandle);
    return 1;
  }
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\secutil.cxx\"",
      (const wchar_t *)0x9A,
      (unsigned int)L"[UtilSecurity] OpenThreadToken() failed. 0x%08x",
      (const wchar_t *)LastError);
    return 1;
  }
  return v0;
}

```

## disassembly

```asm
0x1801ba280  push    rbx
0x1801ba282  sub     rsp, 20h
0x1801ba286  xor     ebx, ebx
0x1801ba288  mov     [rsp+28h+TokenHandle], rbx
0x1801ba28d  call    cs:__imp_GetCurrentThread
0x1801ba293  mov     rcx, rax; ThreadHandle
0x1801ba296  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1801ba29b  lea     edx, [rbx+8]; DesiredAccess
0x1801ba29e  lea     r8d, [rbx+1]; OpenAsSelf
0x1801ba2a2  call    cs:__imp_OpenThreadToken
0x1801ba2a8  test    eax, eax
0x1801ba2aa  jz      short loc_1801BA2B9
0x1801ba2ac  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1801ba2b1  call    cs:__imp_CloseHandle
0x1801ba2b7  jmp     short loc_1801BA2E1
0x1801ba2b9  call    cs:__imp_GetLastError
0x1801ba2bf  cmp     eax, 3F0h
0x1801ba2c4  jz      short loc_1801BA2E6
0x1801ba2c6  mov     r9d, eax; wchar_t *
0x1801ba2c9  lea     r8, aUtilsecurityOp_0; "[UtilSecurity] OpenThreadToken() failed"...
0x1801ba2d0  mov     edx, 9Ah; wchar_t *
0x1801ba2d5  lea     rcx, aOnecoreuapBase_159; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1801ba2dc  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1801ba2e1  mov     ebx, 1
0x1801ba2e6  mov     eax, ebx
0x1801ba2e8  add     rsp, 20h
0x1801ba2ec  pop     rbx
0x1801ba2ed  retn
```
