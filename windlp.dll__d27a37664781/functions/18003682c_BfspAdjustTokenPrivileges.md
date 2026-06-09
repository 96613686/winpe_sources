# BfspAdjustTokenPrivileges

- ea: `0x18003682c`
- end: `0x1800369d8`
- name: `BfspAdjustTokenPrivileges`
- size: `428`
- prototype: `__int64 __fastcall(PTOKEN_PRIVILEGES NewState)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031344`
- `0x180032518`
- `0x1800345e8`

## callees

- `0x1800366b8`
- `0x18003682c`
- `0x180036c24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800368a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036928`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800369a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800368a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036928`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800369a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800368b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036936`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800368b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036936`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003691f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003691f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800369b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003686b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003696b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003686b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003696b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036994`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036994`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800368ec`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003695f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800368ec`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003695f`

## string_xrefs

- `0x180036971`: `Failed to adjust token priveleges! Error code = %#x`
- `0x180036871`: `Failed to get user token! Error code = %#x`

## pseudocode

```c
__int64 __fastcall BfspAdjustTokenPrivileges(PTOKEN_PRIVILEGES NewState, struct _TOKEN_PRIVILEGES **a2)
{
  unsigned int UserToken; // edi
  struct _TOKEN_PRIVILEGES *PreviousState; // rbx
  DWORD LastError; // eax
  const wchar_t *v7; // rdx
  DWORD v8; // esi
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  struct _TOKEN_PRIVILEGES *v11; // rax
  DWORD v12; // r9d
  int v13; // r12d
  BOOL v14; // eax
  HANDLE v15; // rax
  DWORD v16; // ebx
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD BufferLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  BufferLength = 0;
  TokenHandle = 0;
  UserToken = BfspGetUserToken(&TokenHandle);
  if ( !UserToken )
  {
    PreviousState = 0;
    LastError = GetLastError();
    v7 = L"Failed to get user token! Error code = %#x";
LABEL_3:
    v8 = LastError;
    BfspLogMessage(4, v7, LastError);
    goto LABEL_19;
  }
  v8 = 8;
  if ( a2 )
  {
    BufferLength = 12 * NewState->PrivilegeCount + 4;
    v9 = BufferLength;
    ProcessHeap = GetProcessHeap();
    v11 = (struct _TOKEN_PRIVILEGES *)HeapAlloc(ProcessHeap, 8u, v9);
    v12 = BufferLength;
    v13 = 0;
    PreviousState = v11;
  }
  else
  {
    PreviousState = 0;
    v12 = 0;
    BufferLength = 0;
    v13 = 1;
  }
  v14 = AdjustTokenPrivileges(TokenHandle, 0, NewState, v12, PreviousState, &BufferLength);
  UserToken = v14;
  if ( v13 )
  {
LABEL_14:
    if ( !UserToken )
      goto LABEL_15;
    goto LABEL_17;
  }
  if ( !v14 )
  {
    if ( GetLastError() != 122 )
    {
LABEL_15:
      LastError = GetLastError();
      v7 = L"Failed to adjust token priveleges! Error code = %#x";
      goto LABEL_3;
    }
    if ( PreviousState )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, PreviousState);
    }
    v16 = BufferLength;
    v17 = GetProcessHeap();
    PreviousState = (struct _TOKEN_PRIVILEGES *)HeapAlloc(v17, 8u, v16);
    if ( !PreviousState )
    {
      UserToken = 0;
      goto LABEL_19;
    }
    UserToken = AdjustTokenPrivileges(TokenHandle, 0, NewState, BufferLength, PreviousState, &BufferLength);
    goto LABEL_14;
  }
LABEL_17:
  v8 = 0;
  if ( a2 )
    *a2 = PreviousState;
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( !UserToken )
  {
    if ( PreviousState )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, PreviousState);
    }
    SetLastError(v8);
  }
  return UserToken;
}

```

## disassembly

```asm
0x18003682c  mov     [rsp-28h+arg_0], rbx
0x180036831  mov     [rsp-28h+arg_8], rsi
0x180036836  push    rbp
0x180036837  push    rdi
0x180036838  push    r12
0x18003683a  push    r14
0x18003683c  push    r15
0x18003683e  mov     rbp, rsp
0x180036841  sub     rsp, 30h
0x180036845  mov     r15, rcx
0x180036848  mov     [rbp+BufferLength], 0
0x18003684f  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x180036853  mov     [rbp+TokenHandle], 0
0x18003685b  mov     r14, rdx
0x18003685e  call    BfspGetUserToken
0x180036863  mov     edi, eax
0x180036865  test    eax, eax
0x180036867  jnz     short loc_18003688C
0x180036869  xor     ebx, ebx
0x18003686b  call    cs:__imp_GetLastError
0x180036871  lea     rdx, aFailedToGetUse; "Failed to get user token! Error code = "...
0x180036878  mov     r8d, eax
0x18003687b  mov     ecx, 4
0x180036880  mov     esi, eax
0x180036882  call    BfspLogMessage
0x180036887  jmp     loc_18003698B
0x18003688c  mov     esi, 8
0x180036891  test    r14, r14
0x180036894  jz      short loc_1800368C8
0x180036896  mov     eax, [r15]
0x180036899  lea     ecx, [rax+rax*2]
0x18003689c  lea     ecx, ds:4[rcx*4]
0x1800368a3  mov     [rbp+BufferLength], ecx
0x1800368a6  mov     ebx, ecx
0x1800368a8  call    cs:__imp_GetProcessHeap
0x1800368ae  mov     r8d, ebx; dwBytes
0x1800368b1  mov     edx, esi; dwFlags
0x1800368b3  mov     rcx, rax; hHeap
0x1800368b6  call    cs:__imp_HeapAlloc
0x1800368bc  mov     r9d, [rbp+BufferLength]
0x1800368c0  xor     r12d, r12d
0x1800368c3  mov     rbx, rax
0x1800368c6  jmp     short loc_1800368D5
0x1800368c8  xor     ebx, ebx
0x1800368ca  xor     r9d, r9d; BufferLength
0x1800368cd  mov     [rbp+BufferLength], r9d
0x1800368d1  lea     r12d, [rbx+1]
0x1800368d5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800368d9  lea     rax, [rbp+BufferLength]
0x1800368dd  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800368e2  mov     r8, r15; NewState
0x1800368e5  xor     edx, edx; DisableAllPrivileges
0x1800368e7  mov     [rsp+30h+PreviousState], rbx; PreviousState
0x1800368ec  call    cs:__imp_AdjustTokenPrivileges
0x1800368f2  mov     edi, eax
0x1800368f4  test    r12d, r12d
0x1800368f7  jnz     short loc_180036967
0x1800368f9  test    eax, eax
0x1800368fb  jnz     loc_180036981
0x180036901  call    cs:__imp_GetLastError
0x180036907  cmp     eax, 7Ah ; 'z'
0x18003690a  jnz     short loc_18003696B
0x18003690c  test    rbx, rbx
0x18003690f  jz      short loc_180036925
0x180036911  call    cs:__imp_GetProcessHeap
0x180036917  mov     r8, rbx; lpMem
0x18003691a  xor     edx, edx; dwFlags
0x18003691c  mov     rcx, rax; hHeap
0x18003691f  call    cs:__imp_HeapFree
0x180036925  mov     ebx, [rbp+BufferLength]
0x180036928  call    cs:__imp_GetProcessHeap
0x18003692e  mov     r8d, ebx; dwBytes
0x180036931  mov     edx, esi; dwFlags
0x180036933  mov     rcx, rax; hHeap
0x180036936  call    cs:__imp_HeapAlloc
0x18003693c  mov     rbx, rax
0x18003693f  test    rax, rax
0x180036942  jz      short loc_18003697D
0x180036944  mov     r9d, [rbp+BufferLength]; BufferLength
0x180036948  lea     rax, [rbp+BufferLength]
0x18003694c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180036950  mov     r8, r15; NewState
0x180036953  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180036958  xor     edx, edx; DisableAllPrivileges
0x18003695a  mov     [rsp+30h+PreviousState], rbx; PreviousState
0x18003695f  call    cs:__imp_AdjustTokenPrivileges
0x180036965  mov     edi, eax
0x180036967  test    edi, edi
0x180036969  jnz     short loc_180036981
0x18003696b  call    cs:__imp_GetLastError
0x180036971  lea     rdx, aFailedToAdjust; "Failed to adjust token priveleges! Erro"...
0x180036978  jmp     loc_180036878
0x18003697d  xor     edi, edi
0x18003697f  jmp     short loc_18003698B
0x180036981  xor     esi, esi
0x180036983  test    r14, r14
0x180036986  jz      short loc_18003698B
0x180036988  mov     [r14], rbx
0x18003698b  mov     rcx, [rbp+TokenHandle]; hObject
0x18003698f  test    rcx, rcx
0x180036992  jz      short loc_18003699A
0x180036994  call    cs:__imp_CloseHandle
0x18003699a  test    edi, edi
0x18003699c  jnz     short loc_1800369BF
0x18003699e  test    rbx, rbx
0x1800369a1  jz      short loc_1800369B7
0x1800369a3  call    cs:__imp_GetProcessHeap
0x1800369a9  mov     r8, rbx; lpMem
0x1800369ac  xor     edx, edx; dwFlags
0x1800369ae  mov     rcx, rax; hHeap
0x1800369b1  call    cs:__imp_HeapFree
0x1800369b7  mov     ecx, esi; dwErrCode
0x1800369b9  call    cs:__imp_SetLastError
0x1800369bf  mov     rbx, [rsp+30h+arg_0]
0x1800369c4  mov     eax, edi
0x1800369c6  mov     rsi, [rsp+30h+arg_8]
0x1800369cb  add     rsp, 30h
0x1800369cf  pop     r15
0x1800369d1  pop     r14
0x1800369d3  pop     r12
0x1800369d5  pop     rdi
0x1800369d6  pop     rbp
0x1800369d7  retn
```
