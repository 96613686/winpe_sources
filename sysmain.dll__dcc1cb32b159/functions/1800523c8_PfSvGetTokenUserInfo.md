# PfSvGetTokenUserInfo

- ea: `0x1800523c8`
- end: `0x180052497`
- name: `PfSvGetTokenUserInfo`
- size: `207`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180052364`
- `0x18005ffe4`

## callees

- `0x1800523c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005240d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005240d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800523ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005245b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800523ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005245b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005247c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005247c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005242e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005242e`

## pseudocode

```c
DWORD __fastcall PfSvGetTokenUserInfo(HANDLE TokenHandle, _QWORD *a2)
{
  DWORD result; // eax
  void *v5; // rbx
  SIZE_T dwBytes; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  ReturnLength = 0;
  LODWORD(dwBytes) = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&dwBytes);
  if ( (_DWORD)dwBytes )
  {
    v5 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (unsigned int)dwBytes);
    if ( v5 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v5, dwBytes, &ReturnLength) )
      {
        *a2 = v5;
        return 0;
      }
      else
      {
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v5);
        return 24;
      }
    }
    else
    {
      return 8;
    }
  }
  else
  {
    result = GetLastError();
    if ( !result )
      return -536870343;
  }
  return result;
}

```

## disassembly

```asm
0x1800523c8  mov     rax, rsp
0x1800523cb  mov     [rax+8], rbx
0x1800523cf  mov     [rax+10h], rsi
0x1800523d3  push    rdi
0x1800523d4  sub     rsp, 30h
0x1800523d8  xor     r9d, r9d; TokenInformationLength
0x1800523db  mov     dword ptr [rax+20h], 0
0x1800523e2  mov     dword ptr [rax+18h], 0
0x1800523e9  lea     rax, [rax+18h]
0x1800523ed  mov     rdi, rdx
0x1800523f0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800523f5  xor     r8d, r8d; TokenInformation
0x1800523f8  mov     rsi, rcx
0x1800523fb  lea     edx, [r9+1]; TokenInformationClass
0x1800523ff  call    cs:__imp_GetTokenInformation
0x180052405  mov     eax, dword ptr [rsp+38h+dwBytes]
0x180052409  test    eax, eax
0x18005240b  jnz     short loc_18005241E
0x18005240d  call    cs:__imp_GetLastError
0x180052413  test    eax, eax
0x180052415  jnz     short loc_180052487
0x180052417  mov     eax, 0E0000239h
0x18005241c  jmp     short loc_180052487
0x18005241e  mov     rcx, cs:PfSvcGlobals
0x180052425  mov     r8, rax; dwBytes
0x180052428  xor     edx, edx; dwFlags
0x18005242a  mov     rcx, [rcx+58h]; hHeap
0x18005242e  call    cs:__imp_HeapAlloc
0x180052434  mov     rbx, rax
0x180052437  test    rax, rax
0x18005243a  jnz     short loc_180052441
0x18005243c  lea     eax, [rbx+8]
0x18005243f  jmp     short loc_180052487
0x180052441  mov     r9d, dword ptr [rsp+38h+dwBytes]; TokenInformationLength
0x180052446  lea     rax, [rsp+38h+arg_18]
0x18005244b  mov     r8, rbx; TokenInformation
0x18005244e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180052453  mov     edx, 1; TokenInformationClass
0x180052458  mov     rcx, rsi; TokenHandle
0x18005245b  call    cs:__imp_GetTokenInformation
0x180052461  test    eax, eax
0x180052463  jz      short loc_18005246C
0x180052465  mov     [rdi], rbx
0x180052468  xor     eax, eax
0x18005246a  jmp     short loc_180052487
0x18005246c  mov     rcx, cs:PfSvcGlobals
0x180052473  mov     r8, rbx; lpMem
0x180052476  xor     edx, edx; dwFlags
0x180052478  mov     rcx, [rcx+58h]; hHeap
0x18005247c  call    cs:__imp_HeapFree
0x180052482  mov     eax, 18h
0x180052487  mov     rbx, [rsp+38h+arg_0]
0x18005248c  mov     rsi, [rsp+38h+arg_8]
0x180052491  add     rsp, 30h
0x180052495  pop     rdi
0x180052496  retn
```
