# _anonymous_namespace_::vscode_debugger_interactive_launch

- ea: `0x18007928c`
- end: `0x18007934e`
- name: `_anonymous_namespace_::vscode_debugger_interactive_launch`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180076ad0`
- `0x180076bd0`

## callees

- `0x18007928c`
- `0x180096b94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800792f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800792f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180079298`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180079298`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800792a5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800792a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007932a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079341`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007932a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079341`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x1800792d5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x1800792d5`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x1800792fe`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x1800792fe`

## pseudocode

```c
char anonymous_namespace_::vscode_debugger_interactive_launch()
{
  DWORD CurrentProcessId; // eax
  HANDLE CurrentThread; // rax
  PWSTR Buffer; // [rsp+30h] [rbp+8h] BYREF
  DWORD pSessionId; // [rsp+38h] [rbp+10h] BYREF

  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 0;
  if ( !pSessionId )
    return 0;
  LOWORD(Buffer) = 0;
  if ( GetEnvironmentVariableA("LOCAL_LUA_DEBUGGER_VSCODE", (LPSTR)&Buffer, 2u) != 1 )
    return 0;
  if ( (_BYTE)Buffer != 49 )
    return 0;
  Buffer = 0;
  CurrentThread = GetCurrentThread();
  if ( GetThreadDescription(CurrentThread, &Buffer) < 0 )
    return 0;
  if ( wcscmp_0(Buffer, L"main") )
  {
    if ( Buffer )
      LocalFree(Buffer);
    return 0;
  }
  if ( Buffer )
    LocalFree(Buffer);
  return 1;
}

```

## disassembly

```asm
0x18007928c  sub     rsp, 28h
0x180079290  mov     [rsp+28h+pSessionId], 0
0x180079298  call    cs:__imp_GetCurrentProcessId
0x18007929e  mov     ecx, eax; dwProcessId
0x1800792a0  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x1800792a5  call    cs:__imp_ProcessIdToSessionId
0x1800792ab  test    eax, eax
0x1800792ad  jz      loc_180079347
0x1800792b3  cmp     [rsp+28h+pSessionId], 0
0x1800792b8  jz      loc_180079347
0x1800792be  xor     eax, eax
0x1800792c0  lea     rdx, [rsp+28h+Buffer]; lpBuffer
0x1800792c5  lea     rcx, aLocalLuaDebugg; "LOCAL_LUA_DEBUGGER_VSCODE"
0x1800792cc  mov     word ptr [rsp+28h+Buffer], ax
0x1800792d1  lea     r8d, [rax+2]; nSize
0x1800792d5  call    cs:__imp_GetEnvironmentVariableA
0x1800792db  cmp     eax, 1
0x1800792de  jnz     short loc_180079347
0x1800792e0  cmp     byte ptr [rsp+28h+Buffer], 31h ; '1'
0x1800792e5  jnz     short loc_180079347
0x1800792e7  mov     [rsp+28h+Buffer], 0
0x1800792f0  call    cs:__imp_GetCurrentThread
0x1800792f6  mov     rcx, rax; hThread
0x1800792f9  lea     rdx, [rsp+28h+Buffer]; ppszThreadDescription
0x1800792fe  call    cs:__imp_GetThreadDescription
0x180079304  test    eax, eax
0x180079306  js      short loc_180079347
0x180079308  mov     rcx, [rsp+28h+Buffer]; String1
0x18007930d  lea     rdx, aMain; "main"
0x180079314  call    wcscmp_0
0x180079319  test    eax, eax
0x18007931b  jnz     short loc_180079334
0x18007931d  cmp     [rsp+28h+Buffer], 0
0x180079323  jz      short loc_180079330
0x180079325  mov     rcx, [rsp+28h+Buffer]; hMem
0x18007932a  call    cs:__imp_LocalFree
0x180079330  mov     al, 1
0x180079332  jmp     short loc_180079349
0x180079334  cmp     [rsp+28h+Buffer], 0
0x18007933a  jz      short loc_180079347
0x18007933c  mov     rcx, [rsp+28h+Buffer]; hMem
0x180079341  call    cs:__imp_LocalFree
0x180079347  xor     al, al
0x180079349  add     rsp, 28h
0x18007934d  retn
```
