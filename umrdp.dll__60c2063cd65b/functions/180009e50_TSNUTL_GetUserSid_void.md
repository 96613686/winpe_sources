# TSNUTL_GetUserSid(void *)

- ea: `0x180009e50`
- end: `0x180009f9f`
- name: `?TSNUTL_GetUserSid@@YAPEAXPEAX@Z`
- size: `335`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004190`
- `0x180006170`
- `0x1800146a0`

## callees

- `0x1800090b0`
- `0x180009e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009e8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009e8c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009eb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009f0d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009eb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009f0d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009f22`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009f22`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009f45`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009f45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009edc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009edc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f86`

## pseudocode

```c
void *__fastcall TSNUTL_GetUserSid(HANDLE TokenHandle)
{
  void *v2; // rdi
  PSID *v3; // rbx
  void *v4; // rax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  TokenInformationLength = 0;
  v3 = (PSID *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 0, 0x10u);
  if ( v3 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, v3, 0x10u, &TokenInformationLength) )
    {
      if ( GetLastError() != 122 )
        goto LABEL_12;
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v3);
      v3 = (PSID *)ALLOCMEM(TokenInformationLength);
      if ( !v3 )
      {
LABEL_11:
        if ( !v3 )
          return v2;
LABEL_12:
        HeapFree(NtCurrentPeb()->ProcessHeap, 0, v3);
        return v2;
      }
      if ( !GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
      {
        GetLastError();
        goto LABEL_12;
      }
    }
    TokenInformationLength = GetLengthSid(*v3);
    v4 = ALLOCMEM(TokenInformationLength);
    v2 = v4;
    if ( !v4 )
      goto LABEL_12;
    if ( !CopySid(TokenInformationLength, v4, *v3) )
    {
      GetLastError();
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v2);
      v2 = 0;
    }
    goto LABEL_11;
  }
  SetLastError(0xEu);
  return v2;
}

```

## disassembly

```asm
0x180009e50  mov     [rsp+arg_0], rbx
0x180009e55  mov     [rsp+arg_10], rsi
0x180009e5a  push    rdi
0x180009e5b  sub     rsp, 30h
0x180009e5f  mov     rsi, rcx
0x180009e62  xor     edi, edi
0x180009e64  mov     [rsp+38h+TokenInformationLength], edi
0x180009e68  xor     edx, edx; dwFlags
0x180009e6a  mov     rcx, gs:60h
0x180009e73  lea     r8d, [rdi+10h]; dwBytes
0x180009e77  mov     rcx, [rcx+30h]; hHeap
0x180009e7b  call    cs:__imp_HeapAlloc
0x180009e81  mov     rbx, rax
0x180009e84  test    rax, rax
0x180009e87  jnz     short loc_180009E97
0x180009e89  lea     ecx, [rdi+0Eh]; dwErrCode
0x180009e8c  call    cs:__imp_SetLastError
0x180009e92  jmp     loc_180009F8C
0x180009e97  mov     r9d, 10h; TokenInformationLength
0x180009e9d  lea     rax, [rsp+38h+TokenInformationLength]
0x180009ea2  mov     r8, rbx; TokenInformation
0x180009ea5  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180009eaa  mov     rcx, rsi; TokenHandle
0x180009ead  lea     edx, [r9-0Fh]; TokenInformationClass
0x180009eb1  call    cs:__imp_GetTokenInformation
0x180009eb7  test    eax, eax
0x180009eb9  jnz     short loc_180009F1F
0x180009ebb  call    cs:__imp_GetLastError
0x180009ec1  cmp     eax, 7Ah ; 'z'
0x180009ec4  jnz     loc_180009F74
0x180009eca  mov     rcx, gs:60h
0x180009ed3  mov     r8, rbx; lpMem
0x180009ed6  xor     edx, edx; dwFlags
0x180009ed8  mov     rcx, [rcx+30h]; hHeap
0x180009edc  call    cs:__imp_HeapFree
0x180009ee2  mov     ecx, [rsp+38h+TokenInformationLength]; dwBytes
0x180009ee6  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x180009eeb  mov     rbx, rax
0x180009eee  test    rax, rax
0x180009ef1  jz      short loc_180009F6F
0x180009ef3  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180009ef8  lea     rax, [rsp+38h+TokenInformationLength]
0x180009efd  mov     r8, rbx; TokenInformation
0x180009f00  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180009f05  mov     edx, 1; TokenInformationClass
0x180009f0a  mov     rcx, rsi; TokenHandle
0x180009f0d  call    cs:__imp_GetTokenInformation
0x180009f13  test    eax, eax
0x180009f15  jnz     short loc_180009F1F
0x180009f17  call    cs:__imp_GetLastError
0x180009f1d  jmp     short loc_180009F74
0x180009f1f  mov     rcx, [rbx]; pSid
0x180009f22  call    cs:__imp_GetLengthSid
0x180009f28  mov     ecx, eax; dwBytes
0x180009f2a  mov     [rsp+38h+TokenInformationLength], ecx
0x180009f2e  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x180009f33  mov     rdi, rax
0x180009f36  test    rax, rax
0x180009f39  jz      short loc_180009F74
0x180009f3b  mov     r8, [rbx]; pSourceSid
0x180009f3e  mov     rdx, rax; pDestinationSid
0x180009f41  mov     ecx, [rsp+38h+TokenInformationLength]; nDestinationSidLength
0x180009f45  call    cs:__imp_CopySid
0x180009f4b  test    eax, eax
0x180009f4d  jnz     short loc_180009F6F
0x180009f4f  call    cs:__imp_GetLastError
0x180009f55  mov     rcx, gs:60h
0x180009f5e  mov     r8, rdi; lpMem
0x180009f61  xor     edx, edx; dwFlags
0x180009f63  mov     rcx, [rcx+30h]; hHeap
0x180009f67  call    cs:__imp_HeapFree
0x180009f6d  xor     edi, edi
0x180009f6f  test    rbx, rbx
0x180009f72  jz      short loc_180009F8C
0x180009f74  mov     rcx, gs:60h
0x180009f7d  mov     r8, rbx; lpMem
0x180009f80  xor     edx, edx; dwFlags
0x180009f82  mov     rcx, [rcx+30h]; hHeap
0x180009f86  call    cs:__imp_HeapFree
0x180009f8c  mov     rbx, [rsp+38h+arg_0]
0x180009f91  mov     rax, rdi
0x180009f94  mov     rsi, [rsp+38h+arg_10]
0x180009f99  add     rsp, 30h
0x180009f9d  pop     rdi
0x180009f9e  retn
```
