# LogonVirtualAccountUser(_VIRTUAL_ACCOUNT_CONTEXT const *,void * *)

- ea: `0x1800d5da4`
- end: `0x1800d60c1`
- name: `?LogonVirtualAccountUser@@YAJPEBU_VIRTUAL_ACCOUNT_CONTEXT@@PEAPEAX@Z`
- size: `797`
- prototype: `__int64 __fastcall(const struct _VIRTUAL_ACCOUNT_CONTEXT *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026d78`

## callees

- `0x18006f1c9`
- `0x1800d5da4`
- `0x1800d60c8`
- `0x1800d60ec`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800d5fa2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800d5fa2`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800d6026`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800d6026`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5e9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5e9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d6091`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d6091`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d6083`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d6083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d604e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d604e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6063`
- `ntdll!RtlFreeSid` at `0x1800d6078`
- `ntdll!RtlFreeSid` at `0x1800d6078`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d5e4e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d5e4e`
- `SspiCli!LogonUserExExW` at `0x1800d5f4e`
- `SspiCli!LogonUserExExW` at `0x1800d5f4e`

## pseudocode

```c
__int64 __fastcall LogonVirtualAccountUser(const struct _VIRTUAL_ACCOUNT_CONTEXT *a1, void **a2)
{
  NTSTATUS v4; // eax
  _DWORD *v5; // rdi
  unsigned int Error; // eax
  unsigned int v7; // ebx
  int v8; // r14d
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  HANDLE v15; // rax
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  void *NewTokenHandle; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+80h] [rbp-80h] BYREF
  __int128 v22; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+A0h] [rbp-60h]
  struct _LUID_AND_ATTRIBUTES PrivilegesToDelete; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+BCh] [rbp-44h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  __int64 v27; // [rsp+D4h] [rbp-2Ch]
  __int64 v28; // [rsp+E0h] [rbp-20h]
  __int64 v29; // [rsp+ECh] [rbp-14h]
  __int64 v30; // [rsp+F8h] [rbp-8h]
  __int64 v31; // [rsp+104h] [rbp+4h]
  __int64 v32; // [rsp+110h] [rbp+10h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 512;
  TokenHandle = 0;
  NewTokenHandle = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  PrivilegesToDelete.Luid.LowPart = 0;
  memset_0(&PrivilegesToDelete.Luid.HighPart, 0, 0x68u);
  v23 = 0;
  NewState = 0;
  v22 = 0;
  v4 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v4 < 0 )
  {
    v5 = 0;
    Error = ResultFromWin32FromStatus(v4);
LABEL_3:
    v7 = Error;
    goto LABEL_17;
  }
  v8 = (*((_QWORD *)a1 + 5) != 0) + 2;
  if ( !*((_QWORD *)a1 + 3) )
    v8 = (*((_QWORD *)a1 + 5) != 0) + 1;
  v9 = v8 + 1;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 16LL * v9 + 24);
  v5 = v11;
  if ( v11 )
  {
    *v11 = v9;
    *((_QWORD *)v11 + 1) = Sid;
    v12 = v11 + 6;
    v5[4] = 7;
    v13 = *((_QWORD *)a1 + 5);
    if ( v13 )
    {
      *(_QWORD *)v12 = v13;
      v5[8] = 7;
      v12 = v5 + 10;
    }
    v14 = *((_QWORD *)a1 + 3);
    if ( v14 )
    {
      *(_QWORD *)v12 = v14;
      v12[2] = 7;
      v12 += 4;
    }
    v12[2] = 7;
    *(_QWORD *)v12 = &CapSessionImpersonationGroupSidBuffer;
    if ( !(unsigned int)LogonUserExExW(
                          *((_QWORD *)a1 + 1),
                          *(&g_virtualAccountDomainMap + 4 * *(unsigned int *)a1),
                          &cchOriginalDestLength,
                          2,
                          4,
                          v5,
                          &TokenHandle,
                          0,
                          0,
                          0,
                          0) )
      goto LABEL_13;
    NewState.PrivilegeCount = 2;
    NewState.Privileges[0].Attributes = 2;
    NewState.Privileges[0].Luid = (LUID)23LL;
    DWORD2(v22) = 2;
    *(_QWORD *)&v22 = 33;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x28u, 0, 0) )
      goto LABEL_13;
    PrivilegesToDelete.Luid = (LUID)3LL;
    v25 = 5;
    v26 = 12;
    v27 = 19;
    v28 = 29;
    v29 = 34;
    v30 = 21;
    v31 = 25;
    v32 = 36;
    if ( !CreateRestrictedToken(TokenHandle, 0, 0, 0, 9u, &PrivilegesToDelete, 0, 0, &NewTokenHandle) )
    {
LABEL_13:
      Error = ResultFromLastError();
      goto LABEL_3;
    }
    v7 = 0;
    *a2 = NewTokenHandle;
    NewTokenHandle = 0;
  }
  else
  {
    v7 = -2147024882;
  }
LABEL_17:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( NewTokenHandle )
  {
    CloseHandle(NewTokenHandle);
    NewTokenHandle = 0;
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v5 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v5);
  }
  return v7;
}

```

## disassembly

```asm
0x1800d5da4  mov     [rsp-8+arg_10], rbx
0x1800d5da9  mov     [rsp-8+arg_18], rsi
0x1800d5dae  push    rbp
0x1800d5daf  push    rdi
0x1800d5db0  push    r12
0x1800d5db2  push    r14
0x1800d5db4  push    r15
0x1800d5db6  lea     rbp, [rsp-30h]
0x1800d5dbb  sub     rsp, 130h
0x1800d5dc2  mov     rax, cs:__security_cookie
0x1800d5dc9  xor     rax, rsp
0x1800d5dcc  mov     [rbp+50h+var_30], rax
0x1800d5dd0  xor     r12d, r12d
0x1800d5dd3  mov     word ptr [rsp+150h+IdentifierAuthority.Value+4], 200h
0x1800d5dda  mov     r15, rdx
0x1800d5ddd  mov     [rsp+150h+TokenHandle], r12
0x1800d5de2  mov     rsi, rcx
0x1800d5de5  mov     [rsp+150h+NewTokenHandle], r12
0x1800d5dea  xor     edx, edx; Val
0x1800d5dec  mov     [rsp+150h+var_E0], r12
0x1800d5df1  lea     r8d, [r12+68h]; Size
0x1800d5df6  mov     dword ptr [rsp+150h+IdentifierAuthority.Value], r12d
0x1800d5dfb  lea     rcx, [rbp+50h+PrivilegesToDelete.Luid.HighPart]; void *
0x1800d5dff  mov     [rbp+50h+PrivilegesToDelete.Luid.LowPart], r12d
0x1800d5e03  call    memset_0
0x1800d5e08  xor     eax, eax
0x1800d5e0a  lea     rcx, [rsp+150h+IdentifierAuthority]; IdentifierAuthority
0x1800d5e0f  xorps   xmm0, xmm0
0x1800d5e12  mov     [rbp+50h+var_B0], rax
0x1800d5e16  lea     rax, [rsp+150h+var_E0]
0x1800d5e1b  xor     r9d, r9d; SubAuthority1
0x1800d5e1e  mov     [rsp+150h+Sid], rax; Sid
0x1800d5e23  xor     r8d, r8d; SubAuthority0
0x1800d5e26  mov     [rsp+150h+SubAuthority7], r12d; SubAuthority7
0x1800d5e2b  mov     dl, 1; SubAuthorityCount
0x1800d5e2d  mov     [rsp+150h+SubAuthority6], r12d; SubAuthority6
0x1800d5e32  mov     [rsp+150h+SubAuthority5], r12d; SubAuthority5
0x1800d5e37  mov     [rsp+150h+SubAuthority4], r12d; SubAuthority4
0x1800d5e3c  mov     [rsp+150h+SubAuthority3], r12d; SubAuthority3
0x1800d5e41  mov     [rsp+150h+SubAuthority2], r12d; SubAuthority2
0x1800d5e46  movups  xmmword ptr [rbp+50h+NewState.PrivilegeCount], xmm0
0x1800d5e4a  movups  [rbp+50h+var_C0], xmm0
0x1800d5e4e  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800d5e54  test    eax, eax
0x1800d5e56  jns     short loc_1800D5E69
0x1800d5e58  mov     ecx, eax; int
0x1800d5e5a  mov     edi, r12d
0x1800d5e5d  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1800d5e62  mov     ebx, eax
0x1800d5e64  jmp     loc_1800D6044
0x1800d5e69  mov     rax, [rsi+28h]
0x1800d5e6d  neg     rax
0x1800d5e70  sbb     ecx, ecx
0x1800d5e72  neg     ecx
0x1800d5e74  inc     ecx
0x1800d5e76  cmp     [rsi+18h], r12
0x1800d5e7a  lea     r14d, [rcx+1]
0x1800d5e7e  cmovz   r14d, ecx
0x1800d5e82  inc     r14d
0x1800d5e85  mov     ebx, r14d
0x1800d5e88  shl     rbx, 4
0x1800d5e8c  call    cs:__imp_GetProcessHeap
0x1800d5e92  lea     r8, [rbx+18h]; dwBytes
0x1800d5e96  mov     edx, 8; dwFlags
0x1800d5e9b  mov     rcx, rax; hHeap
0x1800d5e9e  call    cs:__imp_HeapAlloc
0x1800d5ea4  mov     rdi, rax
0x1800d5ea7  test    rax, rax
0x1800d5eaa  jnz     short loc_1800D5EB6
0x1800d5eac  mov     ebx, 8007000Eh
0x1800d5eb1  jmp     loc_1800D6044
0x1800d5eb6  mov     [rax], r14d
0x1800d5eb9  mov     edx, 7
0x1800d5ebe  mov     rax, [rsp+150h+var_E0]
0x1800d5ec3  mov     [rdi+8], rax
0x1800d5ec7  lea     rax, [rdi+18h]
0x1800d5ecb  mov     [rdi+10h], edx
0x1800d5ece  mov     rcx, [rsi+28h]
0x1800d5ed2  test    rcx, rcx
0x1800d5ed5  jz      short loc_1800D5EE1
0x1800d5ed7  mov     [rax], rcx
0x1800d5eda  mov     [rax+8], edx
0x1800d5edd  add     rax, 10h
0x1800d5ee1  mov     rcx, [rsi+18h]
0x1800d5ee5  test    rcx, rcx
0x1800d5ee8  jz      short loc_1800D5EF4
0x1800d5eea  mov     [rax], rcx
0x1800d5eed  mov     [rax+8], edx
0x1800d5ef0  add     rax, 10h
0x1800d5ef4  mov     [rax+8], edx
0x1800d5ef7  lea     rcx, ?CapSessionImpersonationGroupSidBuffer@@3PAEA; uchar near * CapSessionImpersonationGroupSidBuffer
0x1800d5efe  mov     [rax], rcx
0x1800d5f01  lea     r8, cchOriginalDestLength
0x1800d5f08  mov     edx, [rsi]
0x1800d5f0a  lea     rcx, ?g_virtualAccountDomainMap@@3PAU_VIRTUAL_ACCOUNT_DOMAIN_MAP@@A; _VIRTUAL_ACCOUNT_DOMAIN_MAP near * g_virtualAccountDomainMap
0x1800d5f11  mov     [rsp+150h+Sid], r12
0x1800d5f16  lea     rax, [rsp+150h+TokenHandle]
0x1800d5f1b  mov     qword ptr [rsp+150h+SubAuthority7], r12
0x1800d5f20  mov     r9d, 2
0x1800d5f26  mov     qword ptr [rsp+150h+SubAuthority6], r12
0x1800d5f2b  mov     qword ptr [rsp+150h+SubAuthority5], r12
0x1800d5f30  mov     qword ptr [rsp+150h+SubAuthority4], rax
0x1800d5f35  shl     rdx, 5
0x1800d5f39  mov     qword ptr [rsp+150h+SubAuthority3], rdi
0x1800d5f3e  mov     [rsp+150h+SubAuthority2], 4
0x1800d5f46  mov     rdx, [rdx+rcx]
0x1800d5f4a  mov     rcx, [rsi+8]
0x1800d5f4e  call    cs:__imp_LogonUserExExW
0x1800d5f54  test    eax, eax
0x1800d5f56  jnz     short loc_1800D5F62
0x1800d5f58  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800d5f5d  jmp     loc_1800D5E62
0x1800d5f62  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x1800d5f67  lea     r8, [rbp+50h+NewState]; NewState
0x1800d5f6b  mov     qword ptr [rsp+150h+SubAuthority3], r12; ReturnLength
0x1800d5f70  mov     r9d, 28h ; '('; BufferLength
0x1800d5f76  xor     edx, edx; DisableAllPrivileges
0x1800d5f78  mov     qword ptr [rsp+150h+SubAuthority2], r12; PreviousState
0x1800d5f7d  mov     [rbp+50h+NewState.PrivilegeCount], 2
0x1800d5f84  mov     [rbp+50h+NewState.Privileges.Attributes], 2
0x1800d5f8b  mov     qword ptr [rbp+50h+NewState.Privileges.Luid.LowPart], 17h
0x1800d5f93  mov     dword ptr [rbp+50h+var_C0+8], 2
0x1800d5f9a  mov     qword ptr [rbp+50h+var_C0], 21h ; '!'
0x1800d5fa2  call    cs:__imp_AdjustTokenPrivileges
0x1800d5fa8  test    eax, eax
0x1800d5faa  jz      short loc_1800D5F58
0x1800d5fac  mov     rcx, [rsp+150h+TokenHandle]; ExistingTokenHandle
0x1800d5fb1  lea     rax, [rsp+150h+NewTokenHandle]
0x1800d5fb6  mov     qword ptr [rsp+150h+SubAuthority6], rax; NewTokenHandle
0x1800d5fbb  xor     r9d, r9d; SidsToDisable
0x1800d5fbe  mov     qword ptr [rsp+150h+SubAuthority5], r12; SidsToRestrict
0x1800d5fc3  lea     rax, [rbp+50h+PrivilegesToDelete]
0x1800d5fc7  mov     [rsp+150h+SubAuthority4], r12d; RestrictedSidCount
0x1800d5fcc  xor     r8d, r8d; DisableSidCount
0x1800d5fcf  mov     qword ptr [rsp+150h+SubAuthority3], rax; PrivilegesToDelete
0x1800d5fd4  xor     edx, edx; Flags
0x1800d5fd6  mov     [rsp+150h+SubAuthority2], 9; DeletePrivilegeCount
0x1800d5fde  mov     qword ptr [rbp+50h+PrivilegesToDelete.Luid.LowPart], 3
0x1800d5fe6  mov     [rbp+50h+var_94], 5
0x1800d5fee  mov     [rbp+50h+var_88], 0Ch
0x1800d5ff6  mov     [rbp+50h+var_7C], 13h
0x1800d5ffe  mov     [rbp+50h+var_70], 1Dh
0x1800d6006  mov     [rbp+50h+var_64], 22h ; '"'
0x1800d600e  mov     [rbp+50h+var_58], 15h
0x1800d6016  mov     [rbp+50h+var_4C], 19h
0x1800d601e  mov     [rbp+50h+var_40], 24h ; '$'
0x1800d6026  call    cs:__imp_CreateRestrictedToken
0x1800d602c  test    eax, eax
0x1800d602e  jz      loc_1800D5F58
0x1800d6034  mov     rax, [rsp+150h+NewTokenHandle]
0x1800d6039  mov     ebx, r12d
0x1800d603c  mov     [r15], rax
0x1800d603f  mov     [rsp+150h+NewTokenHandle], r12
0x1800d6044  mov     rcx, [rsp+150h+TokenHandle]; hObject
0x1800d6049  test    rcx, rcx
0x1800d604c  jz      short loc_1800D6059
0x1800d604e  call    cs:__imp_CloseHandle
0x1800d6054  mov     [rsp+150h+TokenHandle], r12
0x1800d6059  mov     rcx, [rsp+150h+NewTokenHandle]; hObject
0x1800d605e  test    rcx, rcx
0x1800d6061  jz      short loc_1800D606E
0x1800d6063  call    cs:__imp_CloseHandle
0x1800d6069  mov     [rsp+150h+NewTokenHandle], r12
0x1800d606e  mov     rcx, [rsp+150h+var_E0]; Sid
0x1800d6073  test    rcx, rcx
0x1800d6076  jz      short loc_1800D607E
0x1800d6078  call    cs:__imp_RtlFreeSid
0x1800d607e  test    rdi, rdi
0x1800d6081  jz      short loc_1800D6097
0x1800d6083  call    cs:__imp_GetProcessHeap
0x1800d6089  mov     r8, rdi; lpMem
0x1800d608c  xor     edx, edx; dwFlags
0x1800d608e  mov     rcx, rax; hHeap
0x1800d6091  call    cs:__imp_HeapFree
0x1800d6097  mov     eax, ebx
0x1800d6099  mov     rcx, [rbp+50h+var_30]
0x1800d609d  xor     rcx, rsp; StackCookie
0x1800d60a0  call    __security_check_cookie
0x1800d60a5  lea     r11, [rsp+150h+var_20]
0x1800d60ad  mov     rbx, [r11+40h]
0x1800d60b1  mov     rsi, [r11+48h]
0x1800d60b5  mov     rsp, r11
0x1800d60b8  pop     r15
0x1800d60ba  pop     r14
0x1800d60bc  pop     r12
0x1800d60be  pop     rdi
0x1800d60bf  pop     rbp
0x1800d60c0  retn
```
