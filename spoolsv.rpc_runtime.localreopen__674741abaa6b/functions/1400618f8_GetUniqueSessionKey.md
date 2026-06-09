# GetUniqueSessionKey

- ea: `0x1400618f8`
- end: `0x140061ae3`
- name: `GetUniqueSessionKey`
- size: `491`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000fd70`
- `0x140017970`
- `0x1400608d8`
- `0x140060fb0`
- `0x140061658`
- `0x14007f2f0`

## callees

- `0x14005f274`
- `0x1400618ac`
- `0x1400618f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140061a9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140061abf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140061a9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140061abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140061996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140061996`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140061959`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140061959`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140061a79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140061a79`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140061980`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400619dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140061980`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400619dc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140061a3f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140061a3f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140061a18`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140061a18`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140061a55`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140061a55`

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
0x1400618f8  mov     rax, rsp
0x1400618fb  mov     [rax+10h], rbx
0x1400618ff  push    rbp
0x140061900  push    rsi
0x140061901  push    rdi
0x140061902  push    r12
0x140061904  push    r13
0x140061906  push    r14
0x140061908  push    r15
0x14006190a  sub     rsp, 30h
0x14006190e  xor     esi, esi
0x140061910  mov     qword ptr [rax+18h], 0
0x140061918  xor     edi, edi
0x14006191a  mov     [rax+8], esi
0x14006191d  mov     r12, rdx
0x140061920  mov     r14, rcx
0x140061923  test    rcx, rcx
0x140061926  jnz     short loc_140061945
0x140061928  lea     rcx, [rax+18h]; TokenHandle
0x14006192c  call    GetTokenHandle
0x140061931  mov     ebx, eax
0x140061933  test    eax, eax
0x140061935  jz      loc_140061A67
0x14006193b  mov     rcx, [rsp+68h+TokenHandle]
0x140061943  jmp     short loc_14006194F
0x140061945  xor     ebx, ebx
0x140061947  mov     [rsp+68h+TokenHandle], rcx
0x14006194f  test    r12, r12
0x140061952  jnz     short loc_14006196A
0x140061954  lea     ecx, [r12+57h]; dwErrCode
0x140061959  call    cs:__imp_SetLastError
0x140061960  nop     dword ptr [rax+rax+00h]
0x140061965  jmp     loc_140061A67
0x14006196a  xor     r9d, r9d; TokenInformationLength
0x14006196d  lea     rax, [rsp+68h+TokenInformationLength]
0x140061972  xor     r8d, r8d; TokenInformation
0x140061975  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x14006197a  lea     ebp, [r9+2]
0x14006197e  mov     edx, ebp; TokenInformationClass
0x140061980  call    cs:__imp_GetTokenInformation
0x140061987  nop     dword ptr [rax+rax+00h]
0x14006198c  mov     ebx, eax
0x14006198e  test    eax, eax
0x140061990  jnz     loc_140061A67
0x140061996  call    cs:__imp_GetLastError
0x14006199d  nop     dword ptr [rax+rax+00h]
0x1400619a2  cmp     eax, 7Ah ; 'z'
0x1400619a5  jnz     loc_140061A67
0x1400619ab  mov     ecx, [rsp+68h+TokenInformationLength]; dwBytes
0x1400619af  call    ALLOCMEM
0x1400619b4  mov     rdi, rax
0x1400619b7  test    rax, rax
0x1400619ba  jz      loc_140061A67
0x1400619c0  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x1400619c5  lea     rax, [rsp+68h+TokenInformationLength]
0x1400619ca  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1400619d2  mov     r8, rdi; TokenInformation
0x1400619d5  mov     edx, ebp; TokenInformationClass
0x1400619d7  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1400619dc  call    cs:__imp_GetTokenInformation
0x1400619e3  nop     dword ptr [rax+rax+00h]
0x1400619e8  mov     ebx, eax
0x1400619ea  test    eax, eax
0x1400619ec  jz      short loc_140061A67
0x1400619ee  xor     ebx, ebx
0x1400619f0  lea     r13d, [rbp-1]
0x1400619f4  xor     ecx, ecx
0x1400619f6  cmp     ecx, [rdi]
0x1400619f8  jnb     short loc_140061A67
0x1400619fa  mov     eax, ecx
0x1400619fc  add     rax, rax
0x1400619ff  mov     rbp, [rdi+rax*8+8]
0x140061a04  cmp     byte ptr [rbp+1], 3
0x140061a08  jnz     short loc_140061A10
0x140061a0a  cmp     dword ptr [rbp+8], 5
0x140061a0e  jz      short loc_140061A15
0x140061a10  add     ecx, r13d
0x140061a13  jmp     short loc_1400619F6
0x140061a15  mov     rcx, rbp; pSid
0x140061a18  call    cs:__imp_GetLengthSid
0x140061a1f  nop     dword ptr [rax+rax+00h]
0x140061a24  mov     ecx, eax; dwBytes
0x140061a26  mov     r15d, eax
0x140061a29  call    ALLOCMEM
0x140061a2e  mov     rsi, rax
0x140061a31  test    rax, rax
0x140061a34  jz      short loc_140061A67
0x140061a36  mov     r8, rbp; pSourceSid
0x140061a39  mov     rdx, rax; pDestinationSid
0x140061a3c  mov     ecx, r15d; nDestinationSidLength
0x140061a3f  call    cs:__imp_CopySid
0x140061a46  nop     dword ptr [rax+rax+00h]
0x140061a4b  test    eax, eax
0x140061a4d  jz      short loc_140061A67
0x140061a4f  mov     rdx, r12; StringSid
0x140061a52  mov     rcx, rsi; Sid
0x140061a55  call    cs:__imp_ConvertSidToStringSidW
0x140061a5c  nop     dword ptr [rax+rax+00h]
0x140061a61  test    eax, eax
0x140061a63  cmovnz  ebx, r13d
0x140061a67  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x140061a6f  test    rcx, rcx
0x140061a72  jz      short loc_140061A85
0x140061a74  test    r14, r14
0x140061a77  jnz     short loc_140061A85
0x140061a79  call    cs:__imp_CloseHandle
0x140061a80  nop     dword ptr [rax+rax+00h]
0x140061a85  test    rsi, rsi
0x140061a88  jz      short loc_140061AA8
0x140061a8a  mov     rcx, gs:60h
0x140061a93  mov     r8, rsi; lpMem
0x140061a96  xor     edx, edx; dwFlags
0x140061a98  mov     rcx, [rcx+30h]; hHeap
0x140061a9c  call    cs:__imp_HeapFree
0x140061aa3  nop     dword ptr [rax+rax+00h]
0x140061aa8  test    rdi, rdi
0x140061aab  jz      short loc_140061ACB
0x140061aad  mov     rcx, gs:60h
0x140061ab6  mov     r8, rdi; lpMem
0x140061ab9  xor     edx, edx; dwFlags
0x140061abb  mov     rcx, [rcx+30h]; hHeap
0x140061abf  call    cs:__imp_HeapFree
0x140061ac6  nop     dword ptr [rax+rax+00h]
0x140061acb  mov     eax, ebx
0x140061acd  mov     rbx, [rsp+68h+arg_8]
0x140061ad2  add     rsp, 30h
0x140061ad6  pop     r15
0x140061ad8  pop     r14
0x140061ada  pop     r13
0x140061adc  pop     r12
0x140061ade  pop     rdi
0x140061adf  pop     rsi
0x140061ae0  pop     rbp
0x140061ae1  retn
```
