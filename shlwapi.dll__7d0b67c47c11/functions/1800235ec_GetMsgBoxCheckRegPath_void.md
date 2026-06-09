# GetMsgBoxCheckRegPath(void)

- ea: `0x1800235ec`
- end: `0x180023676`
- name: `?GetMsgBoxCheckRegPath@@YAPEBGXZ`
- size: `138`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800250a0`
- `0x1800251c0`
- `0x180025310`

## callees

- `0x18000eaf0`
- `0x1800235ec`
- `0x180035da0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023616`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800235f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800235f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002363f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002363f`

## string_xrefs

- `0x180023665`: `Software\Microsoft\Windows\CurrentVersion\Explorer\LowRegistry\DontShowMeThisDialogAgain`

## pseudocode

```c
const unsigned __int16 *GetMsgBoxCheckRegPath(void)
{
  HANDLE CurrentProcess; // rax
  int TokenIL; // ebx
  BOOL v2; // ecx
  const unsigned __int16 *result; // rax
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  CurrentProcess = GetCurrentProcess();
  v4 = 0;
  TokenHandle = 0;
  v2 = 0;
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) || (int)ResultFromKnownLastError() >= 0 )
  {
    TokenIL = GetTokenIL(TokenHandle, &v4);
    CloseHandle(TokenHandle);
    if ( TokenIL >= 0 && v4 < 0x2000 )
      v2 = 1;
  }
  result = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LowRegistry\\DontShowMeThisDialogAgain";
  if ( !v2 )
    return L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\DontShowMeThisDialogAgain";
  return result;
}

```

## disassembly

```asm
0x1800235ec  push    rbx
0x1800235ee  sub     rsp, 20h
0x1800235f2  call    cs:__imp_GetCurrentProcess
0x1800235f8  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800235fd  mov     [rsp+28h+arg_0], 0
0x180023605  mov     rcx, rax; ProcessHandle
0x180023608  mov     [rsp+28h+TokenHandle], 0
0x180023611  mov     edx, 8; DesiredAccess
0x180023616  call    cs:__imp_OpenProcessToken
0x18002361c  test    eax, eax
0x18002361e  jnz     short loc_180023629
0x180023620  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023625  test    eax, eax
0x180023627  js      short loc_18002365A
0x180023629  mov     rcx, [rsp+28h+TokenHandle]
0x18002362e  lea     rdx, [rsp+28h+arg_0]
0x180023633  call    GetTokenIL
0x180023638  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002363d  mov     ebx, eax
0x18002363f  call    cs:__imp_CloseHandle
0x180023645  test    ebx, ebx
0x180023647  js      short loc_18002365A
0x180023649  cmp     [rsp+28h+arg_0], 2000h
0x180023651  jnb     short loc_18002365A
0x180023653  mov     ecx, 1
0x180023658  jmp     short loc_18002365C
0x18002365a  xor     ecx, ecx
0x18002365c  test    ecx, ecx
0x18002365e  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023665  lea     rax, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002366c  cmovz   rax, rdx
0x180023670  add     rsp, 20h
0x180023674  pop     rbx
0x180023675  retn
```
