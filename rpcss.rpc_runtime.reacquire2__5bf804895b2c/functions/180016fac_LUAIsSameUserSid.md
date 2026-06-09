# LUAIsSameUserSid

- ea: `0x180016fac`
- end: `0x1800171a8`
- name: `LUAIsSameUserSid`
- size: `508`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016e7c`

## callees

- `0x180016fac`
- `0x1800171b0`
- `0x1800a2ba8`
- `0x1800a2bf4`
- `0x18010b50c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800170eb`
- `ntdll!NtQueryInformationToken` at `0x180017171`
- `ntdll!NtQueryInformationToken` at `0x1800170eb`
- `ntdll!NtQueryInformationToken` at `0x180017171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017187`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001702a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017157`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001702a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017157`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017052`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017066`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017102`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017128`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017052`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017066`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017102`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180017128`

## pseudocode

```c
__int64 __fastcall LUAIsSameUserSid(HANDLE TokenHandle, HANDLE a2)
{
  HLOCAL v3; // rbx
  int v5; // r13d
  unsigned int v6; // esi
  int v7; // eax
  HLOCAL v8; // rdi
  HLOCAL hMem; // [rsp+38h] [rbp-18h] BYREF
  HLOCAL v11; // [rsp+40h] [rbp-10h] BYREF
  HANDLE TokenInformation; // [rsp+48h] [rbp-8h]

  v3 = 0;
  v11 = 0;
  hMem = 0;
  TokenInformation = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 0;
  v5 = 0;
  v6 = 1;
  if ( (int)_LUAGetUserFromToken(TokenHandle, (struct _TOKEN_USER **)&hMem) < 0 )
  {
    v8 = hMem;
  }
  else
  {
    v7 = _LUAGetUserFromToken(a2, (struct _TOKEN_USER **)&v11);
    v3 = v11;
    v8 = hMem;
    if ( v7 >= 0 )
    {
      if ( EqualSid(*(PSID *)hMem, *(PSID *)v11) )
      {
        v5 = 1;
      }
      else if ( (unsigned int)LUAIsShadowAdminEnabled() )
      {
        LUAIsElevatedToken(TokenHandle);
      }
    }
  }
  if ( TokenInformation )
    CloseHandle(TokenInformation);
  if ( v8 )
    LocalFree(v8);
  if ( v3 )
    LocalFree(v3);
  if ( !v5 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180016fac  mov     [rsp-38h+arg_0], rbx
0x180016fb1  push    rbp
0x180016fb2  push    rsi
0x180016fb3  push    rdi
0x180016fb4  push    r12
0x180016fb6  push    r13
0x180016fb8  push    r14
0x180016fba  push    r15
0x180016fbc  mov     rbp, rsp
0x180016fbf  sub     rsp, 50h
0x180016fc3  xor     edi, edi
0x180016fc5  mov     r12, rdx
0x180016fc8  mov     ebx, edi
0x180016fca  mov     [rbp+arg_18], edi
0x180016fcd  mov     [rbp+var_10], rbx
0x180016fd1  mov     r15, rcx
0x180016fd4  mov     [rbp+arg_10], edi
0x180016fd7  mov     [rbp+hMem], rdi
0x180016fdb  mov     [rbp+TokenInformation], rdi
0x180016fdf  mov     [rbp+var_20], edi
0x180016fe2  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180016fe7  test    eax, eax
0x180016fe9  jz      loc_18001709C
0x180016fef  lea     rdx, [rbp+hMem]; struct _TOKEN_USER **
0x180016ff3  mov     rcx, r15; TokenHandle
0x180016ff6  mov     r13d, edi
0x180016ff9  mov     r14d, edi
0x180016ffc  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x180017001  lea     esi, [rdi+1]
0x180017004  test    eax, eax
0x180017006  js      loc_180017096
0x18001700c  lea     rdx, [rbp+var_10]; struct _TOKEN_USER **
0x180017010  mov     rcx, r12; TokenHandle
0x180017013  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x180017018  mov     rbx, [rbp+var_10]
0x18001701c  mov     rdi, [rbp+hMem]
0x180017020  test    eax, eax
0x180017022  js      short loc_18001703D
0x180017024  mov     rdx, [rbx]; pSid2
0x180017027  mov     rcx, [rdi]; pSid1
0x18001702a  call    cs:__imp_EqualSid
0x180017031  nop     dword ptr [rax+rax+00h]
0x180017036  test    eax, eax
0x180017038  jz      short loc_1800170A0
0x18001703a  mov     r13d, esi
0x18001703d  mov     rcx, [rbp+TokenInformation]; hObject
0x180017041  test    rcx, rcx
0x180017044  jnz     loc_180017187
0x18001704a  test    rdi, rdi
0x18001704d  jz      short loc_18001705E
0x18001704f  mov     rcx, rdi; hMem
0x180017052  call    cs:__imp_LocalFree
0x180017059  nop     dword ptr [rax+rax+00h]
0x18001705e  test    rbx, rbx
0x180017061  jz      short loc_180017072
0x180017063  mov     rcx, rbx; hMem
0x180017066  call    cs:__imp_LocalFree
0x18001706d  nop     dword ptr [rax+rax+00h]
0x180017072  test    r13d, r13d
0x180017075  jz      loc_180017198
0x18001707b  mov     eax, esi
0x18001707d  mov     rbx, [rsp+50h+arg_0]
0x180017085  add     rsp, 50h
0x180017089  pop     r15
0x18001708b  pop     r14
0x18001708d  pop     r13
0x18001708f  pop     r12
0x180017091  pop     rdi
0x180017092  pop     rsi
0x180017093  pop     rbp
0x180017094  retn
0x180017096  mov     rdi, [rbp+hMem]
0x18001709a  jmp     short loc_18001703D
0x18001709c  xor     eax, eax
0x18001709e  jmp     short loc_18001707D
0x1800170a0  call    LUAIsShadowAdminEnabled
0x1800170a5  test    eax, eax
0x1800170a7  jz      short loc_18001703D
0x1800170a9  lea     r8, [rbp+arg_10]
0x1800170ad  mov     rcx, r15; TokenHandle
0x1800170b0  lea     rdx, [rbp+arg_18]
0x1800170b4  call    LUAIsElevatedToken
0x1800170b9  test    eax, eax
0x1800170bb  js      short loc_18001703D
0x1800170bd  cmp     [rbp+arg_10], r13d
0x1800170c1  jz      loc_18001703D
0x1800170c7  lea     rax, [rbp+var_20]
0x1800170cb  mov     r9d, 8; TokenInformationLength
0x1800170d1  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800170d5  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800170da  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800170de  cmp     [rbp+arg_18], r13d
0x1800170e2  jz      loc_18001716E
0x1800170e8  mov     rcx, r15; TokenHandle
0x1800170eb  call    cs:__imp_NtQueryInformationToken
0x1800170f2  nop     dword ptr [rax+rax+00h]
0x1800170f7  test    eax, eax
0x1800170f9  js      loc_18001703D
0x1800170ff  mov     rcx, rdi; hMem
0x180017102  call    cs:__imp_LocalFree
0x180017109  nop     dword ptr [rax+rax+00h]
0x18001710e  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x180017112  lea     rdx, [rbp+hMem]; struct _TOKEN_USER **
0x180017116  mov     [rbp+hMem], r13
0x18001711a  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x18001711f  mov     rdi, [rbp+hMem]
0x180017123  jmp     short loc_180017149
0x180017125  mov     rcx, rbx; hMem
0x180017128  call    cs:__imp_LocalFree
0x18001712f  nop     dword ptr [rax+rax+00h]
0x180017134  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x180017138  lea     rdx, [rbp+var_10]; struct _TOKEN_USER **
0x18001713c  mov     [rbp+var_10], r13
0x180017140  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x180017145  mov     rbx, [rbp+var_10]
0x180017149  test    eax, eax
0x18001714b  js      loc_18001703D
0x180017151  mov     rdx, [rbx]; pSid2
0x180017154  mov     rcx, [rdi]; pSid1
0x180017157  call    cs:__imp_EqualSid
0x18001715e  nop     dword ptr [rax+rax+00h]
0x180017163  test    eax, eax
0x180017165  cmovnz  r14d, esi
0x180017169  jmp     loc_18001703D
0x18001716e  mov     rcx, r12; TokenHandle
0x180017171  call    cs:__imp_NtQueryInformationToken
0x180017178  nop     dword ptr [rax+rax+00h]
0x18001717d  test    eax, eax
0x18001717f  js      loc_18001703D
0x180017185  jmp     short loc_180017125
0x180017187  call    cs:__imp_CloseHandle
0x18001718e  nop     dword ptr [rax+rax+00h]
0x180017193  jmp     loc_18001704A
0x180017198  test    r14d, r14d
0x18001719b  jnz     loc_18001707B
0x1800171a1  xor     esi, esi
0x1800171a3  jmp     loc_18001707B
```
