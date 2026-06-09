# GetClientSessionID(ulong &)

- ea: `0x180058fdc`
- end: `0x180059124`
- name: `?GetClientSessionID@@YAHAEAK@Z`
- size: `328`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020f48`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002de18`
- `0x18002def8`
- `0x180058fdc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180059058`
- `KERNEL32!GetLastError` at `0x180059086`
- `KERNEL32!GetLastError` at `0x1800590be`
- `KERNEL32!GetLastError` at `0x1800590ec`
- `KERNEL32!GetLastError` at `0x180059058`
- `KERNEL32!GetLastError` at `0x180059086`
- `KERNEL32!GetLastError` at `0x1800590be`
- `KERNEL32!GetLastError` at `0x1800590ec`
- `KERNEL32!CloseHandle` at `0x1800590b6`
- `KERNEL32!CloseHandle` at `0x1800590b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059016`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180059001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180059001`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180059044`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180059044`

## string_xrefs

- `0x1800590c6`: `OpenThreadToken failed (%#x)`
- `0x1800590f4`: `OpenThreadToken failed (%#x)`
- `0x180059060`: `GetTokenInformation failed (%#x)`
- `0x18005908e`: `GetTokenInformation failed (%#x)`

## pseudocode

```c
__int64 __fastcall GetClientSessionID(unsigned int *a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // edi
  char *v4; // rbx
  void *v5; // rdx
  DWORD LastError; // eax
  void **v7; // rax
  void *v8; // rdx
  __int64 v9; // rcx
  char *v10; // rbx
  void *v11; // rdx
  DWORD v12; // eax
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  unsigned int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( v3 )
  {
    v3 = GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
    if ( v3 )
    {
      *a1 = TokenInformation;
    }
    else
    {
      GetLastError();
      v4 = (char *)WiaTrace_TraceLog("GetTokenInformation failed (%#x)");
      WriteDbgTraceErrorWI("GetClientSessionID", v4);
      WiaTrcLib::Free((WiaTrcLib *)v4, v5);
      LastError = GetLastError();
      v7 = (void **)WiaTrace_Trace("GetTokenInformation failed (%#x)", LastError);
      WiaTrace_ProcessTrace_Ex(v9, v8, (void *)"GetClientSessionID", 1, v7);
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    GetLastError();
    v10 = (char *)WiaTrace_TraceLog("OpenThreadToken failed (%#x)");
    WriteDbgTraceErrorWI("GetClientSessionID", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = GetLastError();
    v13 = (void **)WiaTrace_Trace("OpenThreadToken failed (%#x)", v12);
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"GetClientSessionID", 1, v13);
  }
  return v3;
}

```

## disassembly

```asm
0x180058fdc  mov     rax, rsp
0x180058fdf  mov     [rax+8], rbx
0x180058fe3  push    rdi
0x180058fe4  sub     rsp, 30h
0x180058fe8  mov     rbx, rcx
0x180058feb  mov     qword ptr [rax+20h], 0
0x180058ff3  mov     dword ptr [rax+10h], 0
0x180058ffa  mov     dword ptr [rax+18h], 0
0x180059001  call    cs:__imp_GetCurrentThread
0x180059007  xor     r8d, r8d; OpenAsSelf
0x18005900a  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18005900f  mov     rcx, rax; ThreadHandle
0x180059012  lea     edx, [r8+8]; DesiredAccess
0x180059016  call    cs:__imp_OpenThreadToken
0x18005901c  mov     edi, eax
0x18005901e  test    eax, eax
0x180059020  jz      loc_1800590BE
0x180059026  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18005902b  lea     rax, [rsp+38h+arg_10]
0x180059030  mov     r9d, 4; TokenInformationLength
0x180059036  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005903b  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180059040  lea     edx, [r9+8]; TokenInformationClass
0x180059044  call    cs:__imp_GetTokenInformation
0x18005904a  mov     edi, eax
0x18005904c  test    eax, eax
0x18005904e  jz      short loc_180059058
0x180059050  mov     eax, [rsp+38h+TokenInformation]
0x180059054  mov     [rbx], eax
0x180059056  jmp     short loc_1800590B1
0x180059058  call    cs:__imp_GetLastError
0x18005905e  mov     edx, eax
0x180059060  lea     rcx, aGettokeninform; "GetTokenInformation failed (%#x)"
0x180059067  call    WiaTrace_TraceLog
0x18005906c  mov     rdx, rax; char *
0x18005906f  lea     rcx, aGetclientsessi; "GetClientSessionID"
0x180059076  mov     rbx, rax
0x180059079  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005907e  mov     rcx, rbx; this
0x180059081  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180059086  call    cs:__imp_GetLastError
0x18005908c  mov     edx, eax
0x18005908e  lea     rcx, aGettokeninform; "GetTokenInformation failed (%#x)"
0x180059095  call    WiaTrace_Trace
0x18005909a  mov     r9d, 1; int
0x1800590a0  mov     [rsp+38h+ReturnLength], rax; lpMem
0x1800590a5  lea     r8, aGetclientsessi; "GetClientSessionID"
0x1800590ac  call    WiaTrace_ProcessTrace_Ex
0x1800590b1  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800590b6  call    cs:__imp_CloseHandle
0x1800590bc  jmp     short loc_180059117
0x1800590be  call    cs:__imp_GetLastError
0x1800590c4  mov     edx, eax
0x1800590c6  lea     rcx, aOpenthreadtoke; "OpenThreadToken failed (%#x)"
0x1800590cd  call    WiaTrace_TraceLog
0x1800590d2  mov     rdx, rax; char *
0x1800590d5  lea     rcx, aGetclientsessi; "GetClientSessionID"
0x1800590dc  mov     rbx, rax
0x1800590df  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800590e4  mov     rcx, rbx; this
0x1800590e7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800590ec  call    cs:__imp_GetLastError
0x1800590f2  mov     edx, eax
0x1800590f4  lea     rcx, aOpenthreadtoke; "OpenThreadToken failed (%#x)"
0x1800590fb  call    WiaTrace_Trace
0x180059100  mov     r9d, 1; int
0x180059106  mov     [rsp+38h+ReturnLength], rax; lpMem
0x18005910b  lea     r8, aGetclientsessi; "GetClientSessionID"
0x180059112  call    WiaTrace_ProcessTrace_Ex
0x180059117  mov     rbx, [rsp+38h+arg_0]
0x18005911c  mov     eax, edi
0x18005911e  add     rsp, 30h
0x180059122  pop     rdi
0x180059123  retn
```
