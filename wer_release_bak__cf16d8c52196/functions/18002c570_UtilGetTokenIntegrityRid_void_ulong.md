# UtilGetTokenIntegrityRid(void *,ulong *)

- ea: `0x18002c570`
- end: `0x18002c686`
- name: `?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z`
- size: `278`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800975e8`

## callees

- `0x18002c570`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c657`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c5db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c5db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c5b0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c60d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c5b0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c60d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002c63f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002c63f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002c631`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002c631`

## pseudocode

```c
__int64 __fastcall UtilGetTokenIntegrityRid(HANDLE TokenHandle, unsigned int *a2)
{
  unsigned int v4; // ebx
  PSID *v5; // rdi
  signed int v6; // eax
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = (PSID *)HeapAlloc(g_hWerheap, 0, TokenInformationLength);
      if ( v5 )
      {
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v5);
          *a2 = *GetSidSubAuthority(*v5, (unsigned int)*SidSubAuthorityCount - 1);
          v4 = 0;
        }
        else
        {
          v6 = GetLastError();
          v4 = v6;
          if ( v6 > 0 )
            v4 = (unsigned __int16)v6 | 0x80070000;
        }
        HeapFree(g_hWerheap, 0, v5);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18002c570  mov     [rsp+arg_0], rbx
0x18002c575  mov     [rsp+arg_10], rsi
0x18002c57a  push    rdi
0x18002c57b  sub     rsp, 30h
0x18002c57f  mov     rbx, rdx
0x18002c582  mov     rsi, rcx
0x18002c585  test    rdx, rdx
0x18002c588  jnz     short loc_18002C594
0x18002c58a  mov     ebx, 80070057h
0x18002c58f  jmp     loc_18002C674
0x18002c594  xor     r9d, r9d; TokenInformationLength
0x18002c597  mov     [rsp+38h+TokenInformationLength], 0
0x18002c59f  lea     rax, [rsp+38h+TokenInformationLength]
0x18002c5a4  xor     r8d, r8d; TokenInformation
0x18002c5a7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002c5ac  lea     edx, [r9+19h]; TokenInformationClass
0x18002c5b0  call    cs:__imp_GetTokenInformation
0x18002c5b6  test    eax, eax
0x18002c5b8  jnz     loc_18002C65F
0x18002c5be  call    cs:__imp_GetLastError
0x18002c5c4  cmp     eax, 7Ah ; 'z'
0x18002c5c7  jnz     loc_18002C65F
0x18002c5cd  mov     r8d, [rsp+38h+TokenInformationLength]; dwBytes
0x18002c5d2  xor     edx, edx; dwFlags
0x18002c5d4  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002c5db  call    cs:__imp_HeapAlloc
0x18002c5e1  mov     rdi, rax
0x18002c5e4  test    rax, rax
0x18002c5e7  jnz     short loc_18002C5F3
0x18002c5e9  mov     ebx, 8007000Eh
0x18002c5ee  jmp     loc_18002C674
0x18002c5f3  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002c5f8  lea     rax, [rsp+38h+TokenInformationLength]
0x18002c5fd  mov     r8, rdi; TokenInformation
0x18002c600  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002c605  mov     edx, 19h; TokenInformationClass
0x18002c60a  mov     rcx, rsi; TokenHandle
0x18002c60d  call    cs:__imp_GetTokenInformation
0x18002c613  test    eax, eax
0x18002c615  jnz     short loc_18002C62E
0x18002c617  call    cs:__imp_GetLastError
0x18002c61d  mov     ebx, eax
0x18002c61f  test    eax, eax
0x18002c621  jle     short loc_18002C64B
0x18002c623  movzx   ebx, ax
0x18002c626  or      ebx, 80070000h
0x18002c62c  jmp     short loc_18002C64B
0x18002c62e  mov     rcx, [rdi]; pSid
0x18002c631  call    cs:__imp_GetSidSubAuthorityCount
0x18002c637  mov     rcx, [rdi]; pSid
0x18002c63a  movzx   edx, byte ptr [rax]
0x18002c63d  dec     edx; nSubAuthority
0x18002c63f  call    cs:__imp_GetSidSubAuthority
0x18002c645  mov     ecx, [rax]
0x18002c647  mov     [rbx], ecx
0x18002c649  xor     ebx, ebx
0x18002c64b  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002c652  mov     r8, rdi; lpMem
0x18002c655  xor     edx, edx; dwFlags
0x18002c657  call    cs:__imp_HeapFree
0x18002c65d  jmp     short loc_18002C674
0x18002c65f  call    cs:__imp_GetLastError
0x18002c665  mov     ebx, eax
0x18002c667  test    eax, eax
0x18002c669  jle     short loc_18002C674
0x18002c66b  movzx   ebx, ax
0x18002c66e  or      ebx, 80070000h
0x18002c674  mov     rsi, [rsp+38h+arg_10]
0x18002c679  mov     eax, ebx
0x18002c67b  mov     rbx, [rsp+38h+arg_0]
0x18002c680  add     rsp, 30h
0x18002c684  pop     rdi
0x18002c685  retn
```
