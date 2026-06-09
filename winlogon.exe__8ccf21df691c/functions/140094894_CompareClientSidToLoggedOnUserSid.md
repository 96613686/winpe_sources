# CompareClientSidToLoggedOnUserSid

- ea: `0x140094894`
- end: `0x1400949d8`
- name: `CompareClientSidToLoggedOnUserSid`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400949e0`
- `0x140094e90`

## callees

- `0x140094894`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140094917`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140094917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009497b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009497b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140094909`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14009496d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140094909`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14009496d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14009495b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14009495b`
- `ntdll!NtOpenThreadToken` at `0x1400948c7`
- `ntdll!NtOpenThreadToken` at `0x1400948c7`
- `ntdll!NtQueryInformationToken` at `0x1400948f5`
- `ntdll!NtQueryInformationToken` at `0x140094945`
- `ntdll!NtQueryInformationToken` at `0x1400949a8`
- `ntdll!NtQueryInformationToken` at `0x1400948f5`
- `ntdll!NtQueryInformationToken` at `0x140094945`
- `ntdll!NtQueryInformationToken` at `0x1400949a8`
- `ntdll!NtClose` at `0x1400949c3`
- `ntdll!NtClose` at `0x1400949c3`

## pseudocode

```c
__int64 __fastcall CompareClientSidToLoggedOnUserSid(int a1)
{
  NTSTATUS v2; // ebx
  ULONG v3; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v5; // rdi
  HANDLE v6; // rax
  ULONG TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  int TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v2 >= 0 )
  {
    TokenInformationLength = 0;
    if ( NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) != -1073741789 )
      goto LABEL_12;
    v3 = TokenInformationLength;
    ProcessHeap = GetProcessHeap();
    v5 = (PSID *)HeapAlloc(ProcessHeap, 0, v3);
    if ( v5 )
    {
      v2 = NtQueryInformationToken(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength);
      if ( v2 >= 0 )
        v2 = !EqualSid(SecureDesktopLoggedOnUserSid, *v5) ? 0xC0000022 : 0;
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
    }
    else
    {
      v2 = -1073741801;
    }
    if ( a1 )
    {
      if ( v2 >= 0 )
      {
        TokenInformationLength = 4;
        v2 = NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &TokenInformationLength);
        if ( v2 >= 0 && !TokenInformation )
LABEL_12:
          v2 = -1073741790;
      }
    }
    NtClose(TokenHandle);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140094894  mov     [rsp-18h+arg_0], rbx
0x140094899  push    rbp
0x14009489a  push    rsi
0x14009489b  push    rdi
0x14009489c  mov     rbp, rsp
0x14009489f  sub     rsp, 30h
0x1400948a3  mov     esi, ecx
0x1400948a5  mov     [rbp+TokenHandle], 0
0x1400948ad  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400948b4  mov     [rbp+TokenInformation], 0
0x1400948bb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400948bf  mov     r8b, 1; OpenAsSelf
0x1400948c2  mov     edx, 8; DesiredAccess
0x1400948c7  call    cs:__imp_NtOpenThreadToken
0x1400948cd  mov     ebx, eax
0x1400948cf  test    eax, eax
0x1400948d1  js      loc_1400949C9
0x1400948d7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400948db  lea     rax, [rbp+TokenInformationLength]
0x1400948df  xor     r9d, r9d; TokenInformationLength
0x1400948e2  mov     [rbp+TokenInformationLength], 0
0x1400948e9  xor     r8d, r8d; TokenInformation
0x1400948ec  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1400948f1  lea     edx, [r9+1]; TokenInformationClass
0x1400948f5  call    cs:__imp_NtQueryInformationToken
0x1400948fb  cmp     eax, 0C0000023h
0x140094900  jnz     loc_1400949BA
0x140094906  mov     ebx, [rbp+TokenInformationLength]
0x140094909  call    cs:__imp_GetProcessHeap
0x14009490f  mov     r8d, ebx; dwBytes
0x140094912  xor     edx, edx; dwFlags
0x140094914  mov     rcx, rax; hHeap
0x140094917  call    cs:__imp_HeapAlloc
0x14009491d  mov     rdi, rax
0x140094920  test    rax, rax
0x140094923  jnz     short loc_14009492C
0x140094925  mov     ebx, 0C0000017h
0x14009492a  jmp     short loc_140094981
0x14009492c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140094930  lea     rax, [rbp+TokenInformationLength]
0x140094934  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140094938  mov     r8, rdi; TokenInformation
0x14009493b  mov     edx, 1; TokenInformationClass
0x140094940  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140094945  call    cs:__imp_NtQueryInformationToken
0x14009494b  mov     ebx, eax
0x14009494d  test    eax, eax
0x14009494f  js      short loc_14009496D
0x140094951  mov     rdx, [rdi]; pSid2
0x140094954  mov     rcx, cs:SecureDesktopLoggedOnUserSid; pSid1
0x14009495b  call    cs:__imp_EqualSid
0x140094961  neg     eax
0x140094963  sbb     ebx, ebx
0x140094965  not     ebx
0x140094967  and     ebx, 0C0000022h
0x14009496d  call    cs:__imp_GetProcessHeap
0x140094973  mov     r8, rdi; lpMem
0x140094976  xor     edx, edx; dwFlags
0x140094978  mov     rcx, rax; hHeap
0x14009497b  call    cs:__imp_HeapFree
0x140094981  test    esi, esi
0x140094983  jz      short loc_1400949BF
0x140094985  test    ebx, ebx
0x140094987  js      short loc_1400949BF
0x140094989  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14009498d  lea     rax, [rbp+TokenInformationLength]
0x140094991  mov     r9d, 4; TokenInformationLength
0x140094997  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14009499c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400949a0  mov     [rbp+TokenInformationLength], r9d
0x1400949a4  lea     edx, [r9+16h]; TokenInformationClass
0x1400949a8  call    cs:__imp_NtQueryInformationToken
0x1400949ae  mov     ebx, eax
0x1400949b0  test    eax, eax
0x1400949b2  js      short loc_1400949BF
0x1400949b4  cmp     [rbp+TokenInformation], 0
0x1400949b8  jnz     short loc_1400949BF
0x1400949ba  mov     ebx, 0C0000022h
0x1400949bf  mov     rcx, [rbp+TokenHandle]; Handle
0x1400949c3  call    cs:__imp_NtClose
0x1400949c9  mov     eax, ebx
0x1400949cb  mov     rbx, [rsp+30h+arg_0]
0x1400949d0  add     rsp, 30h
0x1400949d4  pop     rdi
0x1400949d5  pop     rsi
0x1400949d6  pop     rbp
0x1400949d7  retn
```
