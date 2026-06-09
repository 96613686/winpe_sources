# GetSidForProcessIdentity(void * *)

- ea: `0x18001b380`
- end: `0x18001b4d0`
- name: `?GetSidForProcessIdentity@@YAJPEAPEAX@Z`
- size: `336`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001b018`

## callees

- `0x18001b380`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001b499`
- `KERNEL32!CloseHandle` at `0x18001b499`
- `KERNEL32!GetLastError` at `0x18001b3ed`
- `KERNEL32!GetLastError` at `0x18001b3ed`
- `KERNEL32!GetCurrentProcess` at `0x18001b3a0`
- `KERNEL32!GetCurrentProcess` at `0x18001b3a0`
- `ADVAPI32!OpenProcessToken` at `0x18001b3b2`
- `ADVAPI32!OpenProcessToken` at `0x18001b3b2`
- `ADVAPI32!CopySid` at `0x18001b47c`
- `ADVAPI32!CopySid` at `0x18001b47c`
- `ADVAPI32!GetLengthSid` at `0x18001b44c`
- `ADVAPI32!GetLengthSid` at `0x18001b44c`
- `ADVAPI32!GetTokenInformation` at `0x18001b3df`
- `ADVAPI32!GetTokenInformation` at `0x18001b42e`
- `ADVAPI32!GetTokenInformation` at `0x18001b3df`
- `ADVAPI32!GetTokenInformation` at `0x18001b42e`
- `ADVAPI32!IsValidSid` at `0x18001b43b`
- `ADVAPI32!IsValidSid` at `0x18001b43b`

## pseudocode

```c
__int64 __fastcall GetSidForProcessIdentity(void **a1)
{
  unsigned int LastWin32Error; // ebx
  PSID *v3; // rdi
  HANDLE CurrentProcess; // rax
  DWORD LengthSid; // eax
  void *v6; // rax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF

  LastWin32Error = 0;
  TokenHandle = 0;
  v3 = 0;
  TokenInformationLength = 0;
  *a1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    goto LABEL_2;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastWin32Error = -2147418113;
  }
  else
  {
    v3 = (PSID *)MemAllocClear(TokenInformationLength + 1);
    if ( !v3 )
    {
LABEL_6:
      LastWin32Error = -2147024882;
      goto LABEL_14;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_2;
    if ( !IsValidSid(*v3) )
      goto LABEL_2;
    LengthSid = GetLengthSid(*v3);
    TokenInformationLength = LengthSid;
    if ( LengthSid - 1 > 0x7FF )
      goto LABEL_2;
    v6 = MemAllocClear(LengthSid);
    *a1 = v6;
    if ( !v6 )
      goto LABEL_6;
    if ( !CopySid(TokenInformationLength, v6, *v3) )
LABEL_2:
      LastWin32Error = GetLastWin32Error();
  }
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
    MemFree(v3);
  if ( LastWin32Error && *a1 )
  {
    MemFree(*a1);
    *a1 = 0;
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x18001b380  mov     [rsp-18h+arg_10], rbx
0x18001b385  push    rbp
0x18001b386  push    rsi
0x18001b387  push    rdi
0x18001b388  mov     rbp, rsp
0x18001b38b  sub     rsp, 30h
0x18001b38f  xor     ebx, ebx
0x18001b391  mov     rsi, rcx
0x18001b394  and     [rbp+TokenHandle], rbx
0x18001b398  xor     edi, edi
0x18001b39a  and     [rbp+TokenInformationLength], ebx
0x18001b39d  and     [rcx], rbx
0x18001b3a0  call    cs:__imp_GetCurrentProcess
0x18001b3a6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001b3aa  mov     edx, 20008h; DesiredAccess
0x18001b3af  mov     rcx, rax; ProcessHandle
0x18001b3b2  call    cs:__imp_OpenProcessToken
0x18001b3b8  test    eax, eax
0x18001b3ba  jnz     short loc_18001B3C8
0x18001b3bc  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001b3c1  mov     ebx, eax
0x18001b3c3  jmp     loc_18001B490
0x18001b3c8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001b3cc  lea     rax, [rbp+TokenInformationLength]
0x18001b3d0  xor     r9d, r9d; TokenInformationLength
0x18001b3d3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001b3d8  xor     r8d, r8d; TokenInformation
0x18001b3db  lea     edx, [r9+1]; TokenInformationClass
0x18001b3df  call    cs:__imp_GetTokenInformation
0x18001b3e5  test    eax, eax
0x18001b3e7  jnz     loc_18001B48B
0x18001b3ed  call    cs:__imp_GetLastError
0x18001b3f3  cmp     eax, 7Ah ; 'z'
0x18001b3f6  jnz     loc_18001B48B
0x18001b3fc  mov     ecx, [rbp+TokenInformationLength]
0x18001b3ff  inc     ecx; unsigned __int64
0x18001b401  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18001b406  mov     rdi, rax
0x18001b409  test    rax, rax
0x18001b40c  jnz     short loc_18001B415
0x18001b40e  mov     ebx, 8007000Eh
0x18001b413  jmp     short loc_18001B490
0x18001b415  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001b419  lea     rax, [rbp+TokenInformationLength]
0x18001b41d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001b421  mov     r8, rdi; TokenInformation
0x18001b424  mov     edx, 1; TokenInformationClass
0x18001b429  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001b42e  call    cs:__imp_GetTokenInformation
0x18001b434  test    eax, eax
0x18001b436  jz      short loc_18001B3BC
0x18001b438  mov     rcx, [rdi]; pSid
0x18001b43b  call    cs:__imp_IsValidSid
0x18001b441  test    eax, eax
0x18001b443  jz      loc_18001B3BC
0x18001b449  mov     rcx, [rdi]; pSid
0x18001b44c  call    cs:__imp_GetLengthSid
0x18001b452  mov     [rbp+TokenInformationLength], eax
0x18001b455  lea     ecx, [rax-1]
0x18001b458  cmp     ecx, 7FFh
0x18001b45e  ja      loc_18001B3BC
0x18001b464  mov     ecx, eax; unsigned __int64
0x18001b466  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18001b46b  mov     [rsi], rax
0x18001b46e  test    rax, rax
0x18001b471  jz      short loc_18001B40E
0x18001b473  mov     r8, [rdi]; pSourceSid
0x18001b476  mov     rdx, rax; pDestinationSid
0x18001b479  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x18001b47c  call    cs:__imp_CopySid
0x18001b482  test    eax, eax
0x18001b484  jnz     short loc_18001B490
0x18001b486  jmp     loc_18001B3BC
0x18001b48b  mov     ebx, 8000FFFFh
0x18001b490  mov     rcx, [rbp+TokenHandle]; hObject
0x18001b494  test    rcx, rcx
0x18001b497  jz      short loc_18001B49F
0x18001b499  call    cs:__imp_CloseHandle
0x18001b49f  test    rdi, rdi
0x18001b4a2  jz      short loc_18001B4AC
0x18001b4a4  mov     rcx, rdi; lpMem
0x18001b4a7  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001b4ac  test    ebx, ebx
0x18001b4ae  jz      short loc_18001B4C1
0x18001b4b0  mov     rcx, [rsi]; lpMem
0x18001b4b3  test    rcx, rcx
0x18001b4b6  jz      short loc_18001B4C1
0x18001b4b8  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001b4bd  and     qword ptr [rsi], 0
0x18001b4c1  mov     eax, ebx
0x18001b4c3  mov     rbx, [rsp+30h+arg_10]
0x18001b4c8  add     rsp, 30h
0x18001b4cc  pop     rdi
0x18001b4cd  pop     rsi
0x18001b4ce  pop     rbp
0x18001b4cf  retn
```
