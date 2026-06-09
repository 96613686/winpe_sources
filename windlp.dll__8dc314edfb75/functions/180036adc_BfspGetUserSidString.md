# BfspGetUserSidString

- ea: `0x180036adc`
- end: `0x180036c1e`
- name: `BfspGetUserSidString`
- size: `322`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036ca8`

## callees

- `0x1800366b8`
- `0x180036adc`
- `0x180036c24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036b5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036bef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036b5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036bef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036b70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036b70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036bfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036bfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036c09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036be4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036be4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036b33`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036b9e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036b33`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036b9e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036bb2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036bb2`

## string_xrefs

- `0x180036b50`: `Failed to get token information! Error code = %#x`
- `0x180036bc4`: `Failed to convert user SID! Error code = %#x`

## pseudocode

```c
__int64 __fastcall BfspGetUserSidString(LPWSTR *StringSid)
{
  PSID *v2; // rsi
  unsigned int UserToken; // ebx
  DWORD LastError; // edi
  DWORD v5; // eax
  const wchar_t *v6; // rdx
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  v2 = 0;
  UserToken = BfspGetUserToken(&TokenHandle);
  if ( !UserToken )
  {
    LastError = GetLastError();
    goto LABEL_12;
  }
  UserToken = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( !UserToken && GetLastError() != 122 )
    goto LABEL_5;
  v7 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  LastError = 8;
  v2 = (PSID *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( !v2 )
  {
    UserToken = 0;
    goto LABEL_12;
  }
  UserToken = GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength);
  if ( UserToken )
  {
    LastError = 0;
    UserToken = ConvertSidToStringSidW(*v2, StringSid);
    if ( UserToken )
      goto LABEL_12;
    v5 = GetLastError();
    v6 = L"Failed to convert user SID! Error code = %#x";
  }
  else
  {
LABEL_5:
    v5 = GetLastError();
    v6 = L"Failed to get token information! Error code = %#x";
  }
  LastError = v5;
  BfspLogMessage(4, v6, v5);
LABEL_12:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v2);
  }
  if ( !UserToken )
    SetLastError(LastError);
  return UserToken;
}

```

## disassembly

```asm
0x180036adc  mov     rax, rsp
0x180036adf  mov     [rax+8], rbx
0x180036ae3  push    rbp
0x180036ae4  push    rsi
0x180036ae5  push    rdi
0x180036ae6  sub     rsp, 30h
0x180036aea  mov     rbp, rcx
0x180036aed  mov     dword ptr [rax+10h], 0
0x180036af4  lea     rcx, [rax+18h]; TokenHandle
0x180036af8  mov     qword ptr [rax+18h], 0
0x180036b00  xor     esi, esi
0x180036b02  call    BfspGetUserToken
0x180036b07  mov     ebx, eax
0x180036b09  test    eax, eax
0x180036b0b  jnz     short loc_180036B1A
0x180036b0d  call    cs:__imp_GetLastError
0x180036b13  mov     edi, eax
0x180036b15  jmp     loc_180036BDA
0x180036b1a  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180036b1f  lea     rax, [rsp+48h+TokenInformationLength]
0x180036b24  xor     r9d, r9d; TokenInformationLength
0x180036b27  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180036b2c  xor     r8d, r8d; TokenInformation
0x180036b2f  lea     edx, [r9+1]; TokenInformationClass
0x180036b33  call    cs:__imp_GetTokenInformation
0x180036b39  mov     ebx, eax
0x180036b3b  test    eax, eax
0x180036b3d  jnz     short loc_180036B59
0x180036b3f  call    cs:__imp_GetLastError
0x180036b45  cmp     eax, 7Ah ; 'z'
0x180036b48  jz      short loc_180036B59
0x180036b4a  call    cs:__imp_GetLastError
0x180036b50  lea     rdx, aFailedToGetTok; "Failed to get token information! Error "...
0x180036b57  jmp     short loc_180036BCB
0x180036b59  mov     ebx, [rsp+48h+TokenInformationLength]
0x180036b5d  call    cs:__imp_GetProcessHeap
0x180036b63  mov     edi, 8
0x180036b68  mov     r8d, ebx; dwBytes
0x180036b6b  mov     rcx, rax; hHeap
0x180036b6e  mov     edx, edi; dwFlags
0x180036b70  call    cs:__imp_HeapAlloc
0x180036b76  mov     rsi, rax
0x180036b79  test    rax, rax
0x180036b7c  jnz     short loc_180036B82
0x180036b7e  xor     ebx, ebx
0x180036b80  jmp     short loc_180036BDA
0x180036b82  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180036b87  lea     rax, [rsp+48h+TokenInformationLength]
0x180036b8c  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180036b91  mov     r8, rsi; TokenInformation
0x180036b94  mov     edx, 1; TokenInformationClass
0x180036b99  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180036b9e  call    cs:__imp_GetTokenInformation
0x180036ba4  mov     ebx, eax
0x180036ba6  test    eax, eax
0x180036ba8  jz      short loc_180036B4A
0x180036baa  mov     rcx, [rsi]; Sid
0x180036bad  mov     rdx, rbp; StringSid
0x180036bb0  xor     edi, edi
0x180036bb2  call    cs:__imp_ConvertSidToStringSidW
0x180036bb8  mov     ebx, eax
0x180036bba  test    eax, eax
0x180036bbc  jnz     short loc_180036BDA
0x180036bbe  call    cs:__imp_GetLastError
0x180036bc4  lea     rdx, aFailedToConver; "Failed to convert user SID! Error code "...
0x180036bcb  mov     r8d, eax
0x180036bce  mov     ecx, 4
0x180036bd3  mov     edi, eax
0x180036bd5  call    BfspLogMessage
0x180036bda  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180036bdf  test    rcx, rcx
0x180036be2  jz      short loc_180036BEA
0x180036be4  call    cs:__imp_CloseHandle
0x180036bea  test    rsi, rsi
0x180036bed  jz      short loc_180036C03
0x180036bef  call    cs:__imp_GetProcessHeap
0x180036bf5  mov     r8, rsi; lpMem
0x180036bf8  xor     edx, edx; dwFlags
0x180036bfa  mov     rcx, rax; hHeap
0x180036bfd  call    cs:__imp_HeapFree
0x180036c03  test    ebx, ebx
0x180036c05  jnz     short loc_180036C0F
0x180036c07  mov     ecx, edi; dwErrCode
0x180036c09  call    cs:__imp_SetLastError
0x180036c0f  mov     eax, ebx
0x180036c11  mov     rbx, [rsp+48h+arg_0]
0x180036c16  add     rsp, 30h
0x180036c1a  pop     rdi
0x180036c1b  pop     rsi
0x180036c1c  pop     rbp
0x180036c1d  retn
```
