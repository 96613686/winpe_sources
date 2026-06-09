# GetUniqueSessionKey

- ea: `0x14005be08`
- end: `0x14005bfb6`
- name: `GetUniqueSessionKey`
- size: `430`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000eb40`
- `0x140016520`
- `0x14005afc0`
- `0x14005b568`
- `0x14005bba0`
- `0x140077f78`

## callees

- `0x140059a6c`
- `0x14005bdc8`
- `0x14005be08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005bf7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005bf99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005bf7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005bf99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005be9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005be9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005be69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005be69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005bf5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005bf5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005be8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005beda`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005be8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005beda`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14005bf31`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14005bf31`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14005bf10`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14005bf10`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14005bf41`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14005bf41`

## pseudocode

```c
__int64 __fastcall GetUniqueSessionKey(HANDLE a1, LPWSTR *a2)
{
  void *v2; // rsi
  unsigned int *v3; // rdi
  HANDLE v5; // r14
  unsigned int TokenInformation; // ebx
  unsigned int i; // ecx
  __int64 v8; // rbp
  DWORD LengthSid; // r15d
  void *v10; // rax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  TokenHandle = 0;
  v3 = 0;
  TokenInformationLength = 0;
  v5 = a1;
  if ( a1 )
  {
    TokenInformation = 0;
    TokenHandle = a1;
  }
  else
  {
    TokenInformation = GetTokenHandle(&TokenHandle);
    if ( !TokenInformation )
      goto LABEL_20;
    a1 = TokenHandle;
  }
  if ( a2 )
  {
    TokenInformation = GetTokenInformation(a1, TokenGroups, 0, 0, &TokenInformationLength);
    if ( !TokenInformation && GetLastError() == 122 )
    {
      v3 = (unsigned int *)ALLOCMEM(TokenInformationLength);
      if ( v3 )
      {
        TokenInformation = GetTokenInformation(
                             TokenHandle,
                             TokenGroups,
                             v3,
                             TokenInformationLength,
                             &TokenInformationLength);
        if ( TokenInformation )
        {
          TokenInformation = 0;
          for ( i = 0; i < *v3; ++i )
          {
            v8 = *(_QWORD *)&v3[4 * i + 2];
            if ( *(_BYTE *)(v8 + 1) == 3 && *(_DWORD *)(v8 + 8) == 5 )
            {
              LengthSid = GetLengthSid(*(PSID *)&v3[4 * i + 2]);
              v10 = (void *)ALLOCMEM(LengthSid);
              v2 = v10;
              if ( v10 && CopySid(LengthSid, v10, (PSID)v8) && ConvertSidToStringSidW(v2, a2) )
                TokenInformation = 1;
              break;
            }
          }
        }
      }
    }
  }
  else
  {
    SetLastError(0x57u);
  }
LABEL_20:
  if ( TokenHandle && !v5 )
    CloseHandle(TokenHandle);
  if ( v2 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v3 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v3);
  return TokenInformation;
}

```

## disassembly

```asm
0x14005be08  mov     rax, rsp
0x14005be0b  mov     [rax+10h], rbx
0x14005be0f  push    rbp
0x14005be10  push    rsi
0x14005be11  push    rdi
0x14005be12  push    r12
0x14005be14  push    r13
0x14005be16  push    r14
0x14005be18  push    r15
0x14005be1a  sub     rsp, 30h
0x14005be1e  xor     esi, esi
0x14005be20  mov     qword ptr [rax+18h], 0
0x14005be28  xor     edi, edi
0x14005be2a  mov     [rax+8], esi
0x14005be2d  mov     r12, rdx
0x14005be30  mov     r14, rcx
0x14005be33  test    rcx, rcx
0x14005be36  jnz     short loc_14005BE55
0x14005be38  lea     rcx, [rax+18h]; TokenHandle
0x14005be3c  call    GetTokenHandle
0x14005be41  mov     ebx, eax
0x14005be43  test    eax, eax
0x14005be45  jz      loc_14005BF4D
0x14005be4b  mov     rcx, [rsp+68h+TokenHandle]
0x14005be53  jmp     short loc_14005BE5F
0x14005be55  xor     ebx, ebx
0x14005be57  mov     [rsp+68h+TokenHandle], rcx
0x14005be5f  test    r12, r12
0x14005be62  jnz     short loc_14005BE74
0x14005be64  lea     ecx, [r12+57h]; dwErrCode
0x14005be69  call    cs:__imp_SetLastError
0x14005be6f  jmp     loc_14005BF4D
0x14005be74  xor     r9d, r9d; TokenInformationLength
0x14005be77  lea     rax, [rsp+68h+TokenInformationLength]
0x14005be7c  xor     r8d, r8d; TokenInformation
0x14005be7f  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x14005be84  lea     ebp, [r9+2]
0x14005be88  mov     edx, ebp; TokenInformationClass
0x14005be8a  call    cs:__imp_GetTokenInformation
0x14005be90  mov     ebx, eax
0x14005be92  test    eax, eax
0x14005be94  jnz     loc_14005BF4D
0x14005be9a  call    cs:__imp_GetLastError
0x14005bea0  cmp     eax, 7Ah ; 'z'
0x14005bea3  jnz     loc_14005BF4D
0x14005bea9  mov     ecx, [rsp+68h+TokenInformationLength]; dwBytes
0x14005bead  call    ALLOCMEM
0x14005beb2  mov     rdi, rax
0x14005beb5  test    rax, rax
0x14005beb8  jz      loc_14005BF4D
0x14005bebe  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x14005bec3  lea     rax, [rsp+68h+TokenInformationLength]
0x14005bec8  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x14005bed0  mov     r8, rdi; TokenInformation
0x14005bed3  mov     edx, ebp; TokenInformationClass
0x14005bed5  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x14005beda  call    cs:__imp_GetTokenInformation
0x14005bee0  mov     ebx, eax
0x14005bee2  test    eax, eax
0x14005bee4  jz      short loc_14005BF4D
0x14005bee6  xor     ebx, ebx
0x14005bee8  lea     r13d, [rbp-1]
0x14005beec  xor     ecx, ecx
0x14005beee  cmp     ecx, [rdi]
0x14005bef0  jnb     short loc_14005BF4D
0x14005bef2  mov     eax, ecx
0x14005bef4  add     rax, rax
0x14005bef7  mov     rbp, [rdi+rax*8+8]
0x14005befc  cmp     byte ptr [rbp+1], 3
0x14005bf00  jnz     short loc_14005BF08
0x14005bf02  cmp     dword ptr [rbp+8], 5
0x14005bf06  jz      short loc_14005BF0D
0x14005bf08  add     ecx, r13d
0x14005bf0b  jmp     short loc_14005BEEE
0x14005bf0d  mov     rcx, rbp; pSid
0x14005bf10  call    cs:__imp_GetLengthSid
0x14005bf16  mov     ecx, eax; dwBytes
0x14005bf18  mov     r15d, eax
0x14005bf1b  call    ALLOCMEM
0x14005bf20  mov     rsi, rax
0x14005bf23  test    rax, rax
0x14005bf26  jz      short loc_14005BF4D
0x14005bf28  mov     r8, rbp; pSourceSid
0x14005bf2b  mov     rdx, rax; pDestinationSid
0x14005bf2e  mov     ecx, r15d; nDestinationSidLength
0x14005bf31  call    cs:__imp_CopySid
0x14005bf37  test    eax, eax
0x14005bf39  jz      short loc_14005BF4D
0x14005bf3b  mov     rdx, r12; StringSid
0x14005bf3e  mov     rcx, rsi; Sid
0x14005bf41  call    cs:__imp_ConvertSidToStringSidW
0x14005bf47  test    eax, eax
0x14005bf49  cmovnz  ebx, r13d
0x14005bf4d  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x14005bf55  test    rcx, rcx
0x14005bf58  jz      short loc_14005BF65
0x14005bf5a  test    r14, r14
0x14005bf5d  jnz     short loc_14005BF65
0x14005bf5f  call    cs:__imp_CloseHandle
0x14005bf65  test    rsi, rsi
0x14005bf68  jz      short loc_14005BF82
0x14005bf6a  mov     rcx, gs:60h
0x14005bf73  mov     r8, rsi; lpMem
0x14005bf76  xor     edx, edx; dwFlags
0x14005bf78  mov     rcx, [rcx+30h]; hHeap
0x14005bf7c  call    cs:__imp_HeapFree
0x14005bf82  test    rdi, rdi
0x14005bf85  jz      short loc_14005BF9F
0x14005bf87  mov     rcx, gs:60h
0x14005bf90  mov     r8, rdi; lpMem
0x14005bf93  xor     edx, edx; dwFlags
0x14005bf95  mov     rcx, [rcx+30h]; hHeap
0x14005bf99  call    cs:__imp_HeapFree
0x14005bf9f  mov     eax, ebx
0x14005bfa1  mov     rbx, [rsp+68h+arg_8]
0x14005bfa6  add     rsp, 30h
0x14005bfaa  pop     r15
0x14005bfac  pop     r14
0x14005bfae  pop     r13
0x14005bfb0  pop     r12
0x14005bfb2  pop     rdi
0x14005bfb3  pop     rsi
0x14005bfb4  pop     rbp
0x14005bfb5  retn
```
