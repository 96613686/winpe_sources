# GetSessionID(ulong *,_LARGE_INTEGER *)

- ea: `0x180032b58`
- end: `0x180032cee`
- name: `?GetSessionID@@YAKPEAKPEAT_LARGE_INTEGER@@@Z`
- size: `406`
- prototype: `unsigned int __fastcall(unsigned int *TokenInformation, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032cf4`
- `0x180035d6c`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x180032b58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180032be2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180032be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032c91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032c91`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032c24`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032c24`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180032c4f`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180032c4f`
- `WTSAPI32!WTSFreeMemory` at `0x180032c82`
- `WTSAPI32!WTSFreeMemory` at `0x180032c82`

## pseudocode

```c
__int64 __fastcall GetSessionID(unsigned int *TokenInformation, union _LARGE_INTEGER *a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  void *v6; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  DWORD pBytesReturned; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR ppBuffer; // [rsp+78h] [rbp+38h] BYREF

  TokenHandle = 0;
  pBytesReturned = 0;
  ppBuffer = 0;
  WppTraceIndent(TokenInformation, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenSessionId, TokenInformation, 4u, &pBytesReturned)
      || !WTSQuerySessionInformationW(0, *TokenInformation, WTSSessionInfo, &ppBuffer, &pBytesReturned) )
    {
      LastError = GetLastError();
      goto LABEL_15;
    }
    if ( pBytesReturned != 216 )
    {
      LastError = -2146893820;
      goto LABEL_15;
    }
    *a2 = *(union _LARGE_INTEGER *)(ppBuffer + 88);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_15;
    *TokenInformation = -1;
    a2->QuadPart = 0;
  }
  LastError = 0;
LABEL_15:
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  v6 = TokenHandle;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180032b58  mov     [rsp-18h+arg_0], rbx
0x180032b5d  mov     [rsp-18h+arg_8], rsi
0x180032b62  push    rbp
0x180032b63  push    rdi
0x180032b64  push    r15
0x180032b66  mov     rbp, rsp
0x180032b69  sub     rsp, 40h
0x180032b6d  mov     rsi, rdx
0x180032b70  mov     [rbp+TokenHandle], 0
0x180032b78  xor     edx, edx
0x180032b7a  mov     [rbp+pBytesReturned], 0
0x180032b81  mov     rdi, rcx
0x180032b84  mov     [rbp+ppBuffer], 0
0x180032b8c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b98  lea     r15, WPP_GLOBAL_Control
0x180032b9f  cmp     rcx, r15
0x180032ba2  jz      short loc_180032BCC
0x180032ba4  test    byte ptr [rcx+1Ch], 2
0x180032ba8  jz      short loc_180032BCC
0x180032baa  cmp     byte ptr [rcx+19h], 5
0x180032bae  jb      short loc_180032BCC
0x180032bb0  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032bb7  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180032bbe  mov     rcx, [rcx+10h]
0x180032bc2  mov     edx, 17h
0x180032bc7  call    WPP_SF_s
0x180032bcc  call    cs:__imp_GetCurrentThread
0x180032bd2  mov     edx, 8; DesiredAccess
0x180032bd7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180032bdb  mov     rcx, rax; ThreadHandle
0x180032bde  lea     r8d, [rdx-7]; OpenAsSelf
0x180032be2  call    cs:__imp_OpenThreadToken
0x180032be8  test    eax, eax
0x180032bea  jnz     short loc_180032C0A
0x180032bec  call    cs:__imp_GetLastError
0x180032bf2  mov     ebx, eax
0x180032bf4  cmp     eax, 3F0h
0x180032bf9  jnz     short loc_180032C79
0x180032bfb  mov     dword ptr [rdi], 0FFFFFFFFh
0x180032c01  mov     qword ptr [rsi], 0
0x180032c08  jmp     short loc_180032C77
0x180032c0a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180032c0e  lea     rax, [rbp+pBytesReturned]
0x180032c12  mov     r9d, 4; TokenInformationLength
0x180032c18  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180032c1d  mov     r8, rdi; TokenInformation
0x180032c20  lea     edx, [r9+8]; TokenInformationClass
0x180032c24  call    cs:__imp_GetTokenInformation
0x180032c2a  test    eax, eax
0x180032c2c  jnz     short loc_180032C38
0x180032c2e  call    cs:__imp_GetLastError
0x180032c34  mov     ebx, eax
0x180032c36  jmp     short loc_180032C79
0x180032c38  mov     edx, [rdi]; SessionId
0x180032c3a  lea     rax, [rbp+pBytesReturned]
0x180032c3e  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180032c42  mov     [rsp+40h+ReturnLength], rax; pBytesReturned
0x180032c47  mov     r8d, 18h; WTSInfoClass
0x180032c4d  xor     ecx, ecx; hServer
0x180032c4f  call    cs:__imp_WTSQuerySessionInformationW
0x180032c55  test    eax, eax
0x180032c57  jz      short loc_180032C2E
0x180032c59  cmp     [rbp+pBytesReturned], 0D8h
0x180032c60  jz      short loc_180032C69
0x180032c62  mov     ebx, 80090004h
0x180032c67  jmp     short loc_180032C79
0x180032c69  mov     rax, [rbp+ppBuffer]
0x180032c6d  mov     rcx, [rax+0B0h]
0x180032c74  mov     [rsi], rcx
0x180032c77  xor     ebx, ebx
0x180032c79  mov     rcx, [rbp+ppBuffer]; pMemory
0x180032c7d  test    rcx, rcx
0x180032c80  jz      short loc_180032C88
0x180032c82  call    cs:__imp_WTSFreeMemory
0x180032c88  mov     rcx, [rbp+TokenHandle]; hObject
0x180032c8c  test    rcx, rcx
0x180032c8f  jz      short loc_180032C97
0x180032c91  call    cs:__imp_CloseHandle
0x180032c97  mov     edx, 1
0x180032c9c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ca8  cmp     rcx, r15
0x180032cab  jz      short loc_180032CD9
0x180032cad  test    byte ptr [rcx+1Ch], 2
0x180032cb1  jz      short loc_180032CD9
0x180032cb3  cmp     byte ptr [rcx+19h], 5
0x180032cb7  jb      short loc_180032CD9
0x180032cb9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032cc0  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180032cc7  mov     rcx, [rcx+10h]
0x180032ccb  mov     edx, 18h
0x180032cd0  mov     dword ptr [rsp+40h+ReturnLength], ebx
0x180032cd4  call    WPP_SF_sd
0x180032cd9  mov     rsi, [rsp+40h+arg_8]
0x180032cde  mov     eax, ebx
0x180032ce0  mov     rbx, [rsp+40h+arg_0]
0x180032ce5  add     rsp, 40h
0x180032ce9  pop     r15
0x180032ceb  pop     rdi
0x180032cec  pop     rbp
0x180032ced  retn
```
