# TSNUTL_GetSessionSid(void *)

- ea: `0x18000a230`
- end: `0x18000a34a`
- name: `?TSNUTL_GetSessionSid@@YAPEAXPEAX@Z`
- size: `282`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004190`

## callees

- `0x1800090b0`
- `0x18000a230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a338`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a257`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a2a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a257`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a2a0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a2d5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a2d5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a2f4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a2f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a316`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a330`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a316`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a330`

## pseudocode

```c
void *__fastcall TSNUTL_GetSessionSid(HANDLE TokenHandle)
{
  void *v1; // rbx
  unsigned int *v3; // rdi
  unsigned int i; // ecx
  __int64 v5; // rsi
  DWORD LengthSid; // ebp
  void *v7; // rax
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength)
    && GetLastError() == 122
    && (v3 = (unsigned int *)ALLOCMEM(TokenInformationLength)) != 0 )
  {
    if ( GetTokenInformation(TokenHandle, TokenGroups, v3, TokenInformationLength, &TokenInformationLength) )
    {
      for ( i = 0; i < *v3; ++i )
      {
        v5 = *(_QWORD *)&v3[4 * i + 2];
        if ( *(_BYTE *)(v5 + 1) == 3 && *(_DWORD *)(v5 + 8) == 5 )
        {
          LengthSid = GetLengthSid(*(PSID *)&v3[4 * i + 2]);
          v7 = ALLOCMEM(LengthSid);
          v1 = v7;
          if ( v7 && !CopySid(LengthSid, v7, (PSID)v5) )
          {
            GetLastError();
            HeapFree(NtCurrentPeb()->ProcessHeap, 0, v1);
            v1 = 0;
          }
          break;
        }
      }
    }
    else
    {
      GetLastError();
    }
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v3);
  }
  else
  {
    GetLastError();
  }
  return v1;
}

```

## disassembly

```asm
0x18000a230  push    rbx
0x18000a232  push    rbp
0x18000a233  push    rsi
0x18000a234  push    rdi
0x18000a235  sub     rsp, 38h
0x18000a239  xor     ebx, ebx
0x18000a23b  lea     rax, [rsp+58h+TokenInformationLength]
0x18000a240  xor     r9d, r9d; TokenInformationLength
0x18000a243  mov     [rsp+58h+TokenInformationLength], ebx
0x18000a247  xor     r8d, r8d; TokenInformation
0x18000a24a  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000a24f  mov     rsi, rcx
0x18000a252  lea     ebp, [rbx+2]
0x18000a255  mov     edx, ebp; TokenInformationClass
0x18000a257  call    cs:__imp_GetTokenInformation
0x18000a25d  test    eax, eax
0x18000a25f  jnz     loc_18000A338
0x18000a265  call    cs:__imp_GetLastError
0x18000a26b  cmp     eax, 7Ah ; 'z'
0x18000a26e  jnz     loc_18000A338
0x18000a274  mov     ecx, [rsp+58h+TokenInformationLength]; dwBytes
0x18000a278  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x18000a27d  mov     rdi, rax
0x18000a280  test    rax, rax
0x18000a283  jz      loc_18000A338
0x18000a289  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000a28e  lea     rax, [rsp+58h+TokenInformationLength]
0x18000a293  mov     r8, rdi; TokenInformation
0x18000a296  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000a29b  mov     edx, ebp; TokenInformationClass
0x18000a29d  mov     rcx, rsi; TokenHandle
0x18000a2a0  call    cs:__imp_GetTokenInformation
0x18000a2a6  test    eax, eax
0x18000a2a8  jnz     short loc_18000A2B2
0x18000a2aa  call    cs:__imp_GetLastError
0x18000a2b0  jmp     short loc_18000A31E
0x18000a2b2  xor     ecx, ecx
0x18000a2b4  cmp     ecx, [rdi]
0x18000a2b6  jnb     short loc_18000A31E
0x18000a2b8  mov     eax, ecx
0x18000a2ba  add     rax, rax
0x18000a2bd  mov     rsi, [rdi+rax*8+8]
0x18000a2c2  cmp     byte ptr [rsi+1], 3
0x18000a2c6  jnz     short loc_18000A2CE
0x18000a2c8  cmp     dword ptr [rsi+8], 5
0x18000a2cc  jz      short loc_18000A2D2
0x18000a2ce  inc     ecx
0x18000a2d0  jmp     short loc_18000A2B4
0x18000a2d2  mov     rcx, rsi; pSid
0x18000a2d5  call    cs:__imp_GetLengthSid
0x18000a2db  mov     ecx, eax; dwBytes
0x18000a2dd  mov     ebp, eax
0x18000a2df  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x18000a2e4  mov     rbx, rax
0x18000a2e7  test    rax, rax
0x18000a2ea  jz      short loc_18000A31E
0x18000a2ec  mov     r8, rsi; pSourceSid
0x18000a2ef  mov     rdx, rax; pDestinationSid
0x18000a2f2  mov     ecx, ebp; nDestinationSidLength
0x18000a2f4  call    cs:__imp_CopySid
0x18000a2fa  test    eax, eax
0x18000a2fc  jnz     short loc_18000A31E
0x18000a2fe  call    cs:__imp_GetLastError
0x18000a304  mov     rcx, gs:60h
0x18000a30d  mov     r8, rbx; lpMem
0x18000a310  xor     edx, edx; dwFlags
0x18000a312  mov     rcx, [rcx+30h]; hHeap
0x18000a316  call    cs:__imp_HeapFree
0x18000a31c  xor     ebx, ebx
0x18000a31e  mov     rcx, gs:60h
0x18000a327  mov     r8, rdi; lpMem
0x18000a32a  xor     edx, edx; dwFlags
0x18000a32c  mov     rcx, [rcx+30h]; hHeap
0x18000a330  call    cs:__imp_HeapFree
0x18000a336  jmp     short loc_18000A33E
0x18000a338  call    cs:__imp_GetLastError
0x18000a33e  mov     rax, rbx
0x18000a341  add     rsp, 38h
0x18000a345  pop     rdi
0x18000a346  pop     rsi
0x18000a347  pop     rbp
0x18000a348  pop     rbx
0x18000a349  retn
```
