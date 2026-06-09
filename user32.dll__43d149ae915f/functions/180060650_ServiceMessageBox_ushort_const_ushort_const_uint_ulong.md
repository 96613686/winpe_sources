# ServiceMessageBox(ushort const *,ushort const *,uint,ulong)

- ea: `0x180060650`
- end: `0x1800607eb`
- name: `?ServiceMessageBox@@YAHPEBG0IK@Z`
- size: `411`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180027334`

## callees

- `0x180060650`
- `0x180096e00`

## import_xrefs

- `ntdll!NtRaiseHardError` at `0x1800a0c97`
- `ntdll!NtRaiseHardError` at `0x1800a0c97`
- `ntdll!NtOpenThreadToken` at `0x1800606be`
- `ntdll!NtOpenThreadToken` at `0x1800606be`
- `ntdll!NtQueryInformationToken` at `0x1800606e7`
- `ntdll!NtQueryInformationToken` at `0x1800606e7`
- `ntdll!RtlInitUnicodeString` at `0x1800a0c49`
- `ntdll!RtlInitUnicodeString` at `0x1800a0c56`
- `ntdll!RtlInitUnicodeString` at `0x1800a0c49`
- `ntdll!RtlInitUnicodeString` at `0x1800a0c56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060701`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060701`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800606a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800606a9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006070d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006070d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800606f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800606f3`
- `WINSTA!WinStationSendMessageW` at `0x1800607a4`
- `WINSTA!WinStationSendMessageW` at `0x1800607a4`

## pseudocode

```c
__int64 __fastcall ServiceMessageBox(WCHAR *SourceString, WCHAR *a2, unsigned int a3, unsigned int a4)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v7; // r15
  HANDLE CurrentThread; // rax
  NTSTATUS v9; // ebx
  DWORD CurrentProcessId; // eax
  DWORD SessionId; // ecx
  int *v12; // rcx
  int *v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  ULONG v16; // ecx
  __int64 v18; // rax
  char v19; // [rsp+48h] [rbp-41h]
  ULONG Response; // [rsp+50h] [rbp-39h] BYREF
  DWORD pSessionId; // [rsp+54h] [rbp-35h] BYREF
  unsigned int TokenInformation; // [rsp+58h] [rbp-31h] BYREF
  ULONG ReturnLength; // [rsp+5Ch] [rbp-2Dh] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  struct _UNICODE_STRING v26; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int64 Parameters[4]; // [rsp+88h] [rbp-1h] BYREF

  v4 = a4;
  TokenHandle = 0;
  TokenInformation = 0;
  DestinationString = 0;
  pSessionId = 0;
  v26 = 0;
  ReturnLength = 0;
  v7 = a3;
  Response = 1;
  CurrentThread = GetCurrentThread();
  if ( NtOpenThreadToken(CurrentThread, 0x28u, 1u, &TokenHandle) < 0
    || (v9 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength),
        CloseHandle(TokenHandle),
        v9 < 0)
    || ((CurrentProcessId = GetCurrentProcessId(), ProcessIdToSessionId(CurrentProcessId, &pSessionId))
      ? (SessionId = pSessionId)
      : (SessionId = NtCurrentPeb()->SessionId, pSessionId = SessionId),
        TokenInformation == SessionId) )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlInitUnicodeString(&v26, a2);
    Parameters[2] = v7;
    Parameters[0] = (unsigned __int64)&DestinationString;
    Parameters[3] = v4;
    Parameters[1] = (unsigned __int64)&v26;
    if ( NtRaiseHardError(1342177304, 4u, 3u, Parameters, 1u, &Response) < 0 || (v18 = Response, Response >= 0xB) )
      v18 = 1;
    return *((unsigned int *)&qword_1800AC348 + v18);
  }
  else
  {
    v12 = &dword_1800AA33C;
    v13 = &dword_1800AA33C;
    if ( a2 )
      v13 = (int *)a2;
    if ( SourceString )
      v12 = (int *)SourceString;
    if ( (_DWORD)v4 != -1 )
      LODWORD(v4) = (unsigned int)v4 / 0x3E8;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v12 + v15) );
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v19 = 0;
    if ( (unsigned __int8)WinStationSendMessageW(
                            0,
                            TokenInformation,
                            v13,
                            (unsigned int)(2 * v14),
                            v12,
                            2 * (int)v15,
                            v7,
                            v4,
                            &Response,
                            v19) != 1 )
      return 0;
    v16 = Response;
    if ( ((Response - 32000) & 0xFFFFFFFD) == 0 )
      return 0;
    return v16;
  }
}

```

## disassembly

```asm
0x180060650  push    rbp
0x180060652  push    rbx
0x180060653  push    rsi
0x180060654  push    rdi
0x180060655  push    r12
0x180060657  push    r14
0x180060659  push    r15
0x18006065b  lea     rbp, [rsp-27h]
0x180060660  sub     rsp, 0B0h
0x180060667  mov     rax, cs:__security_cookie
0x18006066e  xor     rax, rsp
0x180060671  mov     [rbp+57h+var_38], rax
0x180060675  xor     r12d, r12d
0x180060678  mov     edi, r9d
0x18006067b  xorps   xmm0, xmm0
0x18006067e  mov     [rbp+57h+TokenHandle], r12
0x180060682  xorps   xmm1, xmm1
0x180060685  mov     [rbp+57h+TokenInformation], r12d
0x180060689  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006068d  mov     [rbp+57h+pSessionId], r12d
0x180060691  mov     r14, rdx
0x180060694  movups  xmmword ptr [rbp+57h+var_68.Length], xmm1
0x180060698  mov     [rbp+57h+var_84], r12d
0x18006069c  mov     rsi, rcx
0x18006069f  mov     r15d, r8d
0x1800606a2  mov     [rbp+57h+var_90], 1
0x1800606a9  call    cs:__imp_GetCurrentThread
0x1800606af  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800606b3  mov     r8b, 1; OpenAsSelf
0x1800606b6  mov     rcx, rax; ThreadHandle
0x1800606b9  lea     edx, [r12+28h]; DesiredAccess
0x1800606be  call    cs:__imp_NtOpenThreadToken
0x1800606c4  test    eax, eax
0x1800606c6  js      loc_1800A0C42
0x1800606cc  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800606d0  lea     rax, [rbp+57h+var_84]
0x1800606d4  lea     r9d, [r12+4]; TokenInformationLength
0x1800606d9  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800606de  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800606e2  lea     edx, [r12+0Ch]; TokenInformationClass
0x1800606e7  call    cs:__imp_NtQueryInformationToken
0x1800606ed  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800606f1  mov     ebx, eax
0x1800606f3  call    cs:__imp_CloseHandle
0x1800606f9  test    ebx, ebx
0x1800606fb  js      loc_1800A0C42
0x180060701  call    cs:__imp_GetCurrentProcessId
0x180060707  mov     ecx, eax; dwProcessId
0x180060709  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18006070d  call    cs:__imp_ProcessIdToSessionId
0x180060713  test    eax, eax
0x180060715  jnz     loc_1800607D1
0x18006071b  mov     rax, gs:60h
0x180060724  mov     ecx, [rax+2C0h]
0x18006072a  mov     [rbp+57h+pSessionId], ecx
0x18006072d  cmp     [rbp+57h+TokenInformation], ecx
0x180060730  jz      loc_1800A0C42
0x180060736  test    r14, r14
0x180060739  lea     rcx, dword_1800AA33C
0x180060740  mov     r8, rcx
0x180060743  cmovnz  r8, r14
0x180060747  test    rsi, rsi
0x18006074a  cmovnz  rcx, rsi
0x18006074e  cmp     edi, 0FFFFFFFFh
0x180060751  jz      short loc_18006075F
0x180060753  mov     eax, 10624DD3h
0x180060758  mul     edi
0x18006075a  mov     edi, edx
0x18006075c  shr     edi, 6
0x18006075f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180060763  mov     rax, r9
0x180060766  inc     rax
0x180060769  cmp     [rcx+rax*2], r12w
0x18006076e  jnz     short loc_180060766
0x180060770  inc     r9
0x180060773  cmp     [r8+r9*2], r12w
0x180060778  jnz     short loc_180060770
0x18006077a  mov     [rsp+0E0h+var_98], r12b
0x18006077f  lea     rdx, [rbp+57h+var_90]
0x180060783  mov     [rsp+0E0h+var_A0], rdx
0x180060788  add     eax, eax
0x18006078a  mov     edx, [rbp+57h+TokenInformation]
0x18006078d  add     r9d, r9d
0x180060790  mov     [rsp+0E0h+var_A8], edi
0x180060794  mov     [rsp+0E0h+var_B0], r15d
0x180060799  mov     dword ptr [rsp+0E0h+Response], eax
0x18006079d  mov     [rsp+0E0h+ReturnLength], rcx
0x1800607a2  xor     ecx, ecx
0x1800607a4  call    cs:__imp_WinStationSendMessageW
0x1800607aa  cmp     al, 1
0x1800607ac  jz      short loc_1800607D9
0x1800607ae  mov     ecx, r12d
0x1800607b1  mov     eax, ecx
0x1800607b3  mov     rcx, [rbp+57h+var_38]
0x1800607b7  xor     rcx, rsp; StackCookie
0x1800607ba  call    __security_check_cookie
0x1800607bf  add     rsp, 0B0h
0x1800607c6  pop     r15
0x1800607c8  pop     r14
0x1800607ca  pop     r12
0x1800607cc  pop     rdi
0x1800607cd  pop     rsi
0x1800607ce  pop     rbx
0x1800607cf  pop     rbp
0x1800607d0  retn
0x1800607d1  mov     ecx, [rbp+57h+pSessionId]
0x1800607d4  jmp     loc_18006072D
0x1800607d9  mov     ecx, [rbp+57h+var_90]
0x1800607dc  lea     eax, [rcx-7D00h]
0x1800607e2  test    eax, 0FFFFFFFDh
0x1800607e7  jnz     short loc_1800607B1
0x1800607e9  jmp     short loc_1800607AE
0x1800a0c42  mov     rdx, rsi; SourceString
0x1800a0c45  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800a0c49  call    cs:__imp_RtlInitUnicodeString
0x1800a0c4f  mov     rdx, r14; SourceString
0x1800a0c52  lea     rcx, [rbp+57h+var_68]; DestinationString
0x1800a0c56  call    cs:__imp_RtlInitUnicodeString
0x1800a0c5c  lea     rax, [rbp+57h+DestinationString]
0x1800a0c60  mov     [rbp+57h+var_48], r15
0x1800a0c64  mov     [rbp+57h+Parameters], rax
0x1800a0c68  lea     r9, [rbp+57h+Parameters]; Parameters
0x1800a0c6c  lea     rax, [rbp+57h+var_68]
0x1800a0c70  mov     [rbp+57h+var_40], rdi
0x1800a0c74  mov     edx, 4; NumberOfParameters
0x1800a0c79  mov     [rbp+57h+var_50], rax
0x1800a0c7d  lea     rax, [rbp+57h+var_90]
0x1800a0c81  mov     ecx, 50000018h; ErrorStatus
0x1800a0c86  mov     [rsp+0E0h+Response], rax; Response
0x1800a0c8b  mov     dword ptr [rsp+0E0h+ReturnLength], 1; ValidResponseOptions
0x1800a0c93  lea     r8d, [rdx-1]; UnicodeStringParameterMask
0x1800a0c97  call    cs:__imp_NtRaiseHardError
0x1800a0c9d  test    eax, eax
0x1800a0c9f  js      short loc_1800A0CA9
0x1800a0ca1  mov     eax, [rbp+57h+var_90]
0x1800a0ca4  cmp     eax, 0Bh
0x1800a0ca7  jb      short loc_1800A0CAE
0x1800a0ca9  mov     eax, 1
0x1800a0cae  lea     rcx, qword_1800AC348
0x1800a0cb5  mov     eax, [rcx+rax*4]
0x1800a0cb8  jmp     loc_1800607B3
```
