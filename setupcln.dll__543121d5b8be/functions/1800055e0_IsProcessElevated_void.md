# IsProcessElevated(void)

- ea: `0x1800055e0`
- end: `0x1800056b9`
- name: `?IsProcessElevated@@YAHXZ`
- size: `217`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180005b50`

## callees

- `0x1800047ac`
- `0x1800055e0`
- `0x180008e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000563b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000563b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800055f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800055f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000560a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000560a`
- `WDSCORE!CurrentIP` at `0x180005643`
- `WDSCORE!CurrentIP` at `0x180005643`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800056a9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800056a9`

## pseudocode

```c
__int64 IsProcessElevated(void)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // edi
  __int64 v2; // rbx
  struct tagLOG_PARTIAL_MSG *v3; // rax
  void *TokenHandle; // [rsp+90h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    LUAIsElevatedToken(TokenHandle);
  LastError = GetLastError();
  v2 = CurrentIP();
  v3 = ConstructPartialMsgW(0x4000000, "IsProcessElevated - bResult: %x", 0);
  WdsSetupLogMessageW(
    v3,
    0,
    L"D",
    0,
    1190,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"IsProcessElevated",
    v2,
    LastError,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x1800055e0  mov     rax, rsp
0x1800055e3  push    rbx
0x1800055e4  push    rsi
0x1800055e5  push    rdi
0x1800055e6  sub     rsp, 60h
0x1800055ea  xor     esi, esi
0x1800055ec  mov     [rax+8], esi
0x1800055ef  mov     [rax+10h], esi
0x1800055f2  mov     [rax+18h], rsi
0x1800055f6  call    cs:__imp_GetCurrentProcess
0x1800055fc  mov     rcx, rax; ProcessHandle
0x1800055ff  lea     r8, [rsp+78h+TokenHandle]; TokenHandle
0x180005607  lea     edx, [rsi+8]; DesiredAccess
0x18000560a  call    cs:__imp_OpenProcessToken
0x180005610  test    eax, eax
0x180005612  jz      short loc_18000563B
0x180005614  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18000561c  lea     r8, [rsp+78h+arg_8]
0x180005624  lea     rdx, [rsp+78h+arg_0]
0x18000562c  call    LUAIsElevatedToken
0x180005631  test    eax, eax
0x180005633  cmovns  esi, [rsp+78h+arg_0]
0x18000563b  call    cs:__imp_GetLastError
0x180005641  mov     edi, eax
0x180005643  call    cs:__imp_CurrentIP
0x180005649  mov     r8d, esi
0x18000564c  lea     rdx, aIsprocesseleva_0; "IsProcessElevated - bResult: %x"
0x180005653  mov     ecx, 4000000h; unsigned int
0x180005658  mov     rbx, rax
0x18000565b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005660  mov     [rsp+78h+var_28], 0
0x180005668  lea     rcx, aIsprocesseleva; "IsProcessElevated"
0x18000566f  mov     [rsp+78h+var_30], 0
0x180005678  lea     r8, aD; "D"
0x18000567f  mov     [rsp+78h+var_38], edi
0x180005683  xor     r9d, r9d
0x180005686  mov     [rsp+78h+var_40], rbx
0x18000568b  xor     edx, edx
0x18000568d  mov     [rsp+78h+var_48], rcx
0x180005692  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005699  mov     [rsp+78h+var_50], rcx
0x18000569e  mov     rcx, rax
0x1800056a1  mov     [rsp+78h+var_58], 4A6h
0x1800056a9  call    cs:__imp_WdsSetupLogMessageW
0x1800056af  mov     eax, esi
0x1800056b1  add     rsp, 60h
0x1800056b5  pop     rdi
0x1800056b6  pop     rsi
0x1800056b7  pop     rbx
0x1800056b8  retn
```
