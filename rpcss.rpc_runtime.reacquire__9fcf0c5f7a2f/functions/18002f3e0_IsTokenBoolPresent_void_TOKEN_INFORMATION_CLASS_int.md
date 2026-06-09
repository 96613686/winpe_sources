# IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)

- ea: `0x18002f3e0`
- end: `0x18002f590`
- name: `?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z`
- size: `432`
- prototype: `int(void *, enum _TOKEN_INFORMATION_CLASS, int *)`
- caller_count: `16`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a5bc`
- `0x18002cb68`
- `0x18002f160`
- `0x180035a7c`
- `0x1800450b0`
- `0x1800454f0`
- `0x18004c4b0`
- `0x1800562a0`
- `0x18006af3c`
- `0x180073e10`
- `0x18007554c`
- `0x18007b310`
- `0x18007f1d8`
- `0x18008c020`
- `0x1800a40d4`
- `0x1800ff84c`

## callees

- `0x18002f3e0`
- `0x180034260`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18008172c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f566`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f566`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002f44b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002f44b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f433`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f433`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f4df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f4df`

## string_xrefs

- `0x18002f4ad`: `onecore\com\combase\common\internal\tokenproperties.cpp`
- `0x18002f541`: `onecore\com\combase\common\internal\tokenproperties.cpp`
- `0x18002f4a1`: `IsTokenBoolPresent`
- `0x18002f535`: `IsTokenBoolPresent`

## pseudocode

```c
__int64 __fastcall IsTokenBoolPresent(void *a1, TOKEN_INFORMATION_CLASS a2, int *a3)
{
  unsigned int v3; // ebx
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  HANDLE v9; // rcx
  signed int LastError; // eax
  HANDLE Token; // [rsp+30h] [rbp-10h] BYREF
  int TokenInformation; // [rsp+60h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF

  v3 = 0;
  Token = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  *a3 = 0;
  if ( a1 )
  {
LABEL_12:
    if ( GetTokenInformation(a1, a2, &TokenInformation, 4u, &ReturnLength) )
    {
      *a3 = TokenInformation != 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\common\\internal\\tokenproperties.cpp",
          (unsigned int)"IsTokenBoolPresent",
          58,
          0,
          (__int64)L"hr:%!HRESULT!",
          v3);
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    v9 = Token;
    if ( !Token )
      return v3;
    goto LABEL_23;
  }
  result = SuspendImpersonate(&Token);
  v3 = result;
  if ( (int)result < 0 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    a1 = TokenHandle;
    goto LABEL_12;
  }
  v8 = GetLastError();
  v3 = v8;
  if ( v8 > 0 )
    v3 = (unsigned __int16)v8 | 0x80070000;
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\common\\internal\\tokenproperties.cpp",
      (unsigned int)"IsTokenBoolPresent",
      42,
      0,
      (__int64)L"hr:%!HRESULT!",
      v3);
  v9 = Token;
LABEL_23:
  ResumeImpersonate(v9);
  return v3;
}

```

## disassembly

```asm
0x18002f3e0  mov     [rsp-18h+arg_8], rbx
0x18002f3e5  push    rbp
0x18002f3e6  push    rsi
0x18002f3e7  push    rdi
0x18002f3e8  mov     rbp, rsp
0x18002f3eb  sub     rsp, 40h
0x18002f3ef  xor     ebx, ebx
0x18002f3f1  mov     [rbp+Token], 0
0x18002f3f9  mov     [rbp+TokenHandle], 0
0x18002f401  mov     rdi, r8
0x18002f404  mov     [rbp+TokenInformation], 0
0x18002f40b  mov     esi, edx
0x18002f40d  mov     [rbp+arg_10], 0
0x18002f414  mov     [r8], ebx
0x18002f417  test    rcx, rcx
0x18002f41a  jnz     loc_18002F4CA
0x18002f420  lea     rcx, [rbp+Token]; TokenHandle
0x18002f424  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x18002f429  mov     ebx, eax
0x18002f42b  test    eax, eax
0x18002f42d  js      loc_18002F582
0x18002f433  call    cs:__imp_GetCurrentProcess
0x18002f43a  nop     dword ptr [rax+rax+00h]
0x18002f43f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002f443  mov     edx, 8; DesiredAccess
0x18002f448  mov     rcx, rax; ProcessHandle
0x18002f44b  call    cs:__imp_OpenProcessToken
0x18002f452  nop     dword ptr [rax+rax+00h]
0x18002f457  test    eax, eax
0x18002f459  jnz     short loc_18002F4C6
0x18002f45b  call    cs:__imp_GetLastError
0x18002f462  nop     dword ptr [rax+rax+00h]
0x18002f467  mov     ebx, eax
0x18002f469  test    eax, eax
0x18002f46b  jle     short loc_18002F476
0x18002f46d  movzx   ebx, ax
0x18002f470  or      ebx, 80070000h
0x18002f476  mov     eax, cs:dword_1801574B8
0x18002f47c  test    eax, eax
0x18002f47e  jnz     short loc_18002F493
0x18002f480  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18002f486  jz      short loc_18002F4BD
0x18002f488  xor     ecx, ecx
0x18002f48a  call    IsWppLevelEnabled
0x18002f48f  test    al, al
0x18002f491  jz      short loc_18002F4BD
0x18002f493  xor     r9d, r9d
0x18002f496  mov     [rsp+40h+var_18], ebx
0x18002f49a  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x18002f4a1  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x18002f4a8  mov     [rsp+40h+ReturnLength], rax
0x18002f4ad  lea     rcx, aOnecoreComComb_25; "onecore\\com\\combase\\common\\internal"...
0x18002f4b4  lea     r8d, [r9+2Ah]
0x18002f4b8  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18002f4bd  mov     rcx, [rbp+Token]
0x18002f4c1  jmp     loc_18002F57B
0x18002f4c6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002f4ca  lea     rax, [rbp+arg_10]
0x18002f4ce  mov     r9d, 4; TokenInformationLength
0x18002f4d4  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002f4d8  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18002f4dd  mov     edx, esi; TokenInformationClass
0x18002f4df  call    cs:__imp_GetTokenInformation
0x18002f4e6  nop     dword ptr [rax+rax+00h]
0x18002f4eb  test    eax, eax
0x18002f4ed  jnz     short loc_18002F553
0x18002f4ef  call    cs:__imp_GetLastError
0x18002f4f6  nop     dword ptr [rax+rax+00h]
0x18002f4fb  mov     ebx, eax
0x18002f4fd  test    eax, eax
0x18002f4ff  jle     short loc_18002F50A
0x18002f501  movzx   ebx, ax
0x18002f504  or      ebx, 80070000h
0x18002f50a  mov     eax, cs:dword_1801574B8
0x18002f510  test    eax, eax
0x18002f512  jnz     short loc_18002F527
0x18002f514  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18002f51a  jz      short loc_18002F55D
0x18002f51c  xor     ecx, ecx
0x18002f51e  call    IsWppLevelEnabled
0x18002f523  test    al, al
0x18002f525  jz      short loc_18002F55D
0x18002f527  xor     r9d, r9d
0x18002f52a  mov     [rsp+40h+var_18], ebx
0x18002f52e  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x18002f535  lea     rdx, aIstokenboolpre; "IsTokenBoolPresent"
0x18002f53c  mov     [rsp+40h+ReturnLength], rax
0x18002f541  lea     rcx, aOnecoreComComb_25; "onecore\\com\\combase\\common\\internal"...
0x18002f548  lea     r8d, [r9+3Ah]
0x18002f54c  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18002f551  jmp     short loc_18002F55D
0x18002f553  xor     eax, eax
0x18002f555  cmp     [rbp+TokenInformation], eax
0x18002f558  setnz   al
0x18002f55b  mov     [rdi], eax
0x18002f55d  mov     rcx, [rbp+TokenHandle]; hObject
0x18002f561  test    rcx, rcx
0x18002f564  jz      short loc_18002F572
0x18002f566  call    cs:__imp_CloseHandle
0x18002f56d  nop     dword ptr [rax+rax+00h]
0x18002f572  mov     rcx, [rbp+Token]; Token
0x18002f576  test    rcx, rcx
0x18002f579  jz      short loc_18002F580
0x18002f57b  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x18002f580  mov     eax, ebx
0x18002f582  mov     rbx, [rsp+40h+arg_8]
0x18002f587  add     rsp, 40h
0x18002f58b  pop     rdi
0x18002f58c  pop     rsi
0x18002f58d  pop     rbp
0x18002f58e  retn
```
