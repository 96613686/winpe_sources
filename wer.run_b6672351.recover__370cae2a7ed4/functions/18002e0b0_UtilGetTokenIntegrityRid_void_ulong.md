# UtilGetTokenIntegrityRid(void *,ulong *)

- ea: `0x18002e0b0`
- end: `0x18002e1fd`
- name: `?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z`
- size: `333`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009b978`

## callees

- `0x18002e0b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e1c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e1c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e127`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e0f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e15f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e0f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e15f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e1a3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e1a3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e18f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e18f`

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
0x18002e0b0  mov     [rsp+arg_0], rbx
0x18002e0b5  mov     [rsp+arg_10], rsi
0x18002e0ba  push    rdi
0x18002e0bb  sub     rsp, 30h
0x18002e0bf  mov     rbx, rdx
0x18002e0c2  mov     rsi, rcx
0x18002e0c5  test    rdx, rdx
0x18002e0c8  jnz     short loc_18002E0D4
0x18002e0ca  mov     ebx, 80070057h
0x18002e0cf  jmp     loc_18002E1EA
0x18002e0d4  xor     r9d, r9d; TokenInformationLength
0x18002e0d7  mov     [rsp+38h+TokenInformationLength], 0
0x18002e0df  lea     rax, [rsp+38h+TokenInformationLength]
0x18002e0e4  xor     r8d, r8d; TokenInformation
0x18002e0e7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002e0ec  lea     edx, [r9+19h]; TokenInformationClass
0x18002e0f0  call    cs:__imp_GetTokenInformation
0x18002e0f7  nop     dword ptr [rax+rax+00h]
0x18002e0fc  test    eax, eax
0x18002e0fe  jnz     loc_18002E1CF
0x18002e104  call    cs:__imp_GetLastError
0x18002e10b  nop     dword ptr [rax+rax+00h]
0x18002e110  cmp     eax, 7Ah ; 'z'
0x18002e113  jnz     loc_18002E1CF
0x18002e119  mov     r8d, [rsp+38h+TokenInformationLength]; dwBytes
0x18002e11e  xor     edx, edx; dwFlags
0x18002e120  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002e127  call    cs:__imp_HeapAlloc
0x18002e12e  nop     dword ptr [rax+rax+00h]
0x18002e133  mov     rdi, rax
0x18002e136  test    rax, rax
0x18002e139  jnz     short loc_18002E145
0x18002e13b  mov     ebx, 8007000Eh
0x18002e140  jmp     loc_18002E1EA
0x18002e145  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002e14a  lea     rax, [rsp+38h+TokenInformationLength]
0x18002e14f  mov     r8, rdi; TokenInformation
0x18002e152  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002e157  mov     edx, 19h; TokenInformationClass
0x18002e15c  mov     rcx, rsi; TokenHandle
0x18002e15f  call    cs:__imp_GetTokenInformation
0x18002e166  nop     dword ptr [rax+rax+00h]
0x18002e16b  test    eax, eax
0x18002e16d  jnz     short loc_18002E18C
0x18002e16f  call    cs:__imp_GetLastError
0x18002e176  nop     dword ptr [rax+rax+00h]
0x18002e17b  mov     ebx, eax
0x18002e17d  test    eax, eax
0x18002e17f  jle     short loc_18002E1B5
0x18002e181  movzx   ebx, ax
0x18002e184  or      ebx, 80070000h
0x18002e18a  jmp     short loc_18002E1B5
0x18002e18c  mov     rcx, [rdi]; pSid
0x18002e18f  call    cs:__imp_GetSidSubAuthorityCount
0x18002e196  nop     dword ptr [rax+rax+00h]
0x18002e19b  mov     rcx, [rdi]; pSid
0x18002e19e  movzx   edx, byte ptr [rax]
0x18002e1a1  dec     edx; nSubAuthority
0x18002e1a3  call    cs:__imp_GetSidSubAuthority
0x18002e1aa  nop     dword ptr [rax+rax+00h]
0x18002e1af  mov     ecx, [rax]
0x18002e1b1  mov     [rbx], ecx
0x18002e1b3  xor     ebx, ebx
0x18002e1b5  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002e1bc  mov     r8, rdi; lpMem
0x18002e1bf  xor     edx, edx; dwFlags
0x18002e1c1  call    cs:__imp_HeapFree
0x18002e1c8  nop     dword ptr [rax+rax+00h]
0x18002e1cd  jmp     short loc_18002E1EA
0x18002e1cf  call    cs:__imp_GetLastError
0x18002e1d6  nop     dword ptr [rax+rax+00h]
0x18002e1db  mov     ebx, eax
0x18002e1dd  test    eax, eax
0x18002e1df  jle     short loc_18002E1EA
0x18002e1e1  movzx   ebx, ax
0x18002e1e4  or      ebx, 80070000h
0x18002e1ea  mov     rsi, [rsp+38h+arg_10]
0x18002e1ef  mov     eax, ebx
0x18002e1f1  mov     rbx, [rsp+38h+arg_0]
0x18002e1f6  add     rsp, 30h
0x18002e1fa  pop     rdi
0x18002e1fb  retn
```
