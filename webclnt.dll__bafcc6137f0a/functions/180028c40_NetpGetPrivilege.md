# NetpGetPrivilege

- ea: `0x180028c40`
- end: `0x180028eae`
- name: `NetpGetPrivilege`
- size: `622`
- prototype: `DWORD __fastcall(__int64, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c350`
- `0x18000c628`

## callees

- `0x180028c40`
- `0x18002cfa0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180028d68`
- `ntdll!RtlNtStatusToDosError` at `0x180028d68`
- `ntdll!NtClose` at `0x180028db5`
- `ntdll!NtClose` at `0x180028e3e`
- `ntdll!NtClose` at `0x180028e84`
- `ntdll!NtClose` at `0x180028e8e`
- `ntdll!NtClose` at `0x180028db5`
- `ntdll!NtClose` at `0x180028e3e`
- `ntdll!NtClose` at `0x180028e84`
- `ntdll!NtClose` at `0x180028e8e`
- `ntdll!NtOpenProcessToken` at `0x180028d48`
- `ntdll!NtOpenProcessToken` at `0x180028d48`
- `ntdll!NtDuplicateToken` at `0x180028d93`
- `ntdll!NtDuplicateToken` at `0x180028d93`
- `ntdll!NtAdjustPrivilegesToken` at `0x180028dda`
- `ntdll!NtAdjustPrivilegesToken` at `0x180028e1c`
- `ntdll!NtAdjustPrivilegesToken` at `0x180028dda`
- `ntdll!NtAdjustPrivilegesToken` at `0x180028e1c`
- `ntdll!NtSetInformationThread` at `0x180028e62`
- `ntdll!NtSetInformationThread` at `0x180028e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d23`
- `KERNEL32!LocalFree` at `0x180028d2e`
- `KERNEL32!LocalFree` at `0x180028d57`
- `KERNEL32!LocalFree` at `0x180028d60`
- `KERNEL32!LocalFree` at `0x180028da2`
- `KERNEL32!LocalFree` at `0x180028dab`
- `KERNEL32!LocalFree` at `0x180028dec`
- `KERNEL32!LocalFree` at `0x180028e2b`
- `KERNEL32!LocalFree` at `0x180028e34`
- `KERNEL32!LocalFree` at `0x180028e71`
- `KERNEL32!LocalFree` at `0x180028e7a`
- `KERNEL32!LocalFree` at `0x180028d2e`
- `KERNEL32!LocalFree` at `0x180028d57`
- `KERNEL32!LocalFree` at `0x180028d60`
- `KERNEL32!LocalFree` at `0x180028da2`
- `KERNEL32!LocalFree` at `0x180028dab`
- `KERNEL32!LocalFree` at `0x180028dec`
- `KERNEL32!LocalFree` at `0x180028e2b`
- `KERNEL32!LocalFree` at `0x180028e34`
- `KERNEL32!LocalFree` at `0x180028e71`
- `KERNEL32!LocalFree` at `0x180028e7a`
- `KERNEL32!LocalAlloc` at `0x180028c92`
- `KERNEL32!LocalAlloc` at `0x180028d15`
- `KERNEL32!LocalAlloc` at `0x180028df9`
- `KERNEL32!LocalAlloc` at `0x180028c92`
- `KERNEL32!LocalAlloc` at `0x180028d15`
- `KERNEL32!LocalAlloc` at `0x180028df9`

## pseudocode

```c
DWORD __fastcall NetpGetPrivilege(__int64 a1, unsigned int *a2)
{
  _DWORD *v3; // rax
  _DWORD *v4; // rdi
  unsigned int v6; // eax
  struct _TOKEN_PRIVILEGES *v7; // rsi
  DWORD LastError; // ebx
  int v9; // ebx
  HANDLE v10; // rcx
  ULONG v11; // ebx
  struct _TOKEN_PRIVILEGES *v12; // rcx
  ULONG ReturnLength; // [rsp+30h] [rbp-39h] BYREF
  HANDLE ThreadInformation; // [rsp+38h] [rbp-31h] BYREF
  void *TokenHandle[2]; // [rsp+40h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  __int64 v17; // [rsp+80h] [rbp+17h] BYREF
  int v18; // [rsp+88h] [rbp+1Fh]

  TokenHandle[0] = 0;
  ThreadInformation = 0;
  v17 = 0;
  v18 = 0;
  ReturnLength = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = LocalAlloc(0, 0x1Cu);
  v4 = v3;
  if ( !v3 )
    return GetLastError();
  *v3 = 1;
  v6 = *a2;
  v4[3] = 2;
  TokenHandle[1] = (void *)v6;
  *(_QWORD *)(v4 + 1) = v6;
  ObjectAttributes.SecurityQualityOfService = &v17;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v17 = 0x20000000CLL;
  LOWORD(v18) = 0;
  v7 = (struct _TOKEN_PRIVILEGES *)LocalAlloc(0, 0x200u);
  if ( !v7 )
  {
    LastError = GetLastError();
    LocalFree(v4);
    return LastError;
  }
  v9 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 2u, TokenHandle);
  if ( v9 < 0 )
  {
    LocalFree(v7);
    LocalFree(v4);
    return RtlNtStatusToDosError(v9);
  }
  v9 = NtDuplicateToken(TokenHandle[0], 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, &ThreadInformation);
  if ( v9 < 0 )
  {
    LocalFree(v7);
    LocalFree(v4);
    v10 = TokenHandle[0];
LABEL_10:
    NtClose(v10);
    return RtlNtStatusToDosError(v9);
  }
  v9 = NtAdjustPrivilegesToken(ThreadInformation, 0, (PTOKEN_PRIVILEGES)v4, 0x200u, v7, &ReturnLength);
  if ( v9 == -1073741789 )
  {
    LocalFree(v7);
    v11 = ReturnLength;
    v7 = (struct _TOKEN_PRIVILEGES *)LocalAlloc(0, ReturnLength);
    v9 = NtAdjustPrivilegesToken(ThreadInformation, 0, (PTOKEN_PRIVILEGES)v4, v11, v7, &ReturnLength);
  }
  if ( v9 < 0 )
  {
    v12 = v7;
LABEL_15:
    LocalFree(v12);
    LocalFree(v4);
    NtClose(TokenHandle[0]);
    v10 = ThreadInformation;
    goto LABEL_10;
  }
  v9 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  v12 = v7;
  if ( v9 < 0 )
    goto LABEL_15;
  LocalFree(v7);
  LocalFree(v4);
  NtClose(TokenHandle[0]);
  NtClose(ThreadInformation);
  return 0;
}

```

## disassembly

```asm
0x180028c40  push    rbp
0x180028c42  push    rbx
0x180028c43  push    rsi
0x180028c44  push    rdi
0x180028c45  lea     rbp, [rsp-3Fh]
0x180028c4a  sub     rsp, 0A8h
0x180028c51  mov     rax, cs:__security_cookie
0x180028c58  xor     rax, rsp
0x180028c5b  mov     [rbp+57h+var_30], rax
0x180028c5f  xor     eax, eax
0x180028c61  mov     [rbp+57h+TokenHandle], 0
0x180028c69  xorps   xmm0, xmm0
0x180028c6c  mov     [rbp+57h+ThreadInformation], 0
0x180028c74  mov     rbx, rdx
0x180028c77  mov     [rbp+57h+var_40], rax
0x180028c7b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180028c7f  lea     edx, [rax+1Ch]; uBytes
0x180028c82  mov     [rbp+57h+var_38], eax
0x180028c85  xor     ecx, ecx; uFlags
0x180028c87  mov     [rbp+57h+ReturnLength], eax
0x180028c8a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180028c8e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180028c92  call    cs:__imp_LocalAlloc
0x180028c98  mov     rdi, rax
0x180028c9b  test    rax, rax
0x180028c9e  jnz     short loc_180028CAB
0x180028ca0  call    cs:__imp_GetLastError
0x180028ca6  jmp     loc_180028E96
0x180028cab  mov     dword ptr [rax], 1
0x180028cb1  mov     edx, 200h; uBytes
0x180028cb6  mov     eax, [rbx]
0x180028cb8  xor     ecx, ecx; uFlags
0x180028cba  mov     dword ptr [rdi+0Ch], 2
0x180028cc1  mov     dword ptr [rbp+57h+var_78], eax
0x180028cc4  mov     dword ptr [rbp+57h+var_78+4], 0
0x180028ccb  mov     rax, [rbp+57h+var_78]
0x180028ccf  mov     [rdi+4], rax
0x180028cd3  lea     rax, [rbp+57h+var_40]
0x180028cd7  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180028cdb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180028ce2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180028cea  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180028cf1  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180028cf9  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x180028d01  mov     dword ptr [rbp+57h+var_40], 0Ch
0x180028d08  mov     dword ptr [rbp+57h+var_40+4], 2
0x180028d0f  mov     word ptr [rbp+57h+var_38], 0
0x180028d15  call    cs:__imp_LocalAlloc
0x180028d1b  mov     rsi, rax
0x180028d1e  test    rax, rax
0x180028d21  jnz     short loc_180028D3B
0x180028d23  call    cs:__imp_GetLastError
0x180028d29  mov     rcx, rdi; hMem
0x180028d2c  mov     ebx, eax
0x180028d2e  call    cs:__imp_LocalFree
0x180028d34  mov     eax, ebx
0x180028d36  jmp     loc_180028E96
0x180028d3b  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180028d3f  mov     edx, 2; DesiredAccess
0x180028d44  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180028d48  call    cs:__imp_NtOpenProcessToken
0x180028d4e  mov     ebx, eax
0x180028d50  test    eax, eax
0x180028d52  jns     short loc_180028D73
0x180028d54  mov     rcx, rsi; hMem
0x180028d57  call    cs:__imp_LocalFree
0x180028d5d  mov     rcx, rdi; hMem
0x180028d60  call    cs:__imp_LocalFree
0x180028d66  mov     ecx, ebx; Status
0x180028d68  call    cs:__imp_RtlNtStatusToDosError
0x180028d6e  jmp     loc_180028E96
0x180028d73  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180028d77  lea     rax, [rbp+57h+ThreadInformation]
0x180028d7b  xor     r9d, r9d; EffectiveOnly
0x180028d7e  mov     [rsp+0C0h+NewTokenHandle], rax; NewTokenHandle
0x180028d83  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180028d87  mov     [rsp+0C0h+TokenType], 2; TokenType
0x180028d8f  lea     edx, [r9+2Ch]; DesiredAccess
0x180028d93  call    cs:__imp_NtDuplicateToken
0x180028d99  mov     ebx, eax
0x180028d9b  test    eax, eax
0x180028d9d  jns     short loc_180028DBD
0x180028d9f  mov     rcx, rsi; hMem
0x180028da2  call    cs:__imp_LocalFree
0x180028da8  mov     rcx, rdi; hMem
0x180028dab  call    cs:__imp_LocalFree
0x180028db1  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180028db5  call    cs:__imp_NtClose
0x180028dbb  jmp     short loc_180028D66
0x180028dbd  mov     rcx, [rbp+57h+ThreadInformation]; TokenHandle
0x180028dc1  lea     rax, [rbp+57h+ReturnLength]
0x180028dc5  mov     [rsp+0C0h+NewTokenHandle], rax; ReturnLength
0x180028dca  mov     r9d, 200h; BufferLength
0x180028dd0  mov     r8, rdi; NewState
0x180028dd3  mov     qword ptr [rsp+0C0h+TokenType], rsi; PreviousState
0x180028dd8  xor     edx, edx; DisableAllPrivileges
0x180028dda  call    cs:__imp_NtAdjustPrivilegesToken
0x180028de0  mov     ebx, eax
0x180028de2  cmp     eax, 0C0000023h
0x180028de7  jnz     short loc_180028E24
0x180028de9  mov     rcx, rsi; hMem
0x180028dec  call    cs:__imp_LocalFree
0x180028df2  mov     ebx, [rbp+57h+ReturnLength]
0x180028df5  xor     ecx, ecx; uFlags
0x180028df7  mov     edx, ebx; uBytes
0x180028df9  call    cs:__imp_LocalAlloc
0x180028dff  mov     rcx, [rbp+57h+ThreadInformation]; TokenHandle
0x180028e03  mov     r9d, ebx; BufferLength
0x180028e06  mov     rsi, rax
0x180028e09  mov     r8, rdi; NewState
0x180028e0c  lea     rax, [rbp+57h+ReturnLength]
0x180028e10  xor     edx, edx; DisableAllPrivileges
0x180028e12  mov     [rsp+0C0h+NewTokenHandle], rax; ReturnLength
0x180028e17  mov     qword ptr [rsp+0C0h+TokenType], rsi; PreviousState
0x180028e1c  call    cs:__imp_NtAdjustPrivilegesToken
0x180028e22  mov     ebx, eax
0x180028e24  test    ebx, ebx
0x180028e26  jns     short loc_180028E4D
0x180028e28  mov     rcx, rsi; hMem
0x180028e2b  call    cs:__imp_LocalFree
0x180028e31  mov     rcx, rdi; hMem
0x180028e34  call    cs:__imp_LocalFree
0x180028e3a  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180028e3e  call    cs:__imp_NtClose
0x180028e44  mov     rcx, [rbp+57h+ThreadInformation]
0x180028e48  jmp     loc_180028DB5
0x180028e4d  mov     r9d, 8; ThreadInformationLength
0x180028e53  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x180028e57  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180028e5e  lea     edx, [r9-3]; ThreadInformationClass
0x180028e62  call    cs:__imp_NtSetInformationThread
0x180028e68  mov     ebx, eax
0x180028e6a  mov     rcx, rsi; hMem
0x180028e6d  test    eax, eax
0x180028e6f  js      short loc_180028E2B
0x180028e71  call    cs:__imp_LocalFree
0x180028e77  mov     rcx, rdi; hMem
0x180028e7a  call    cs:__imp_LocalFree
0x180028e80  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180028e84  call    cs:__imp_NtClose
0x180028e8a  mov     rcx, [rbp+57h+ThreadInformation]; Handle
0x180028e8e  call    cs:__imp_NtClose
0x180028e94  xor     eax, eax
0x180028e96  mov     rcx, [rbp+57h+var_30]
0x180028e9a  xor     rcx, rsp; StackCookie
0x180028e9d  call    __security_check_cookie
0x180028ea2  add     rsp, 0A8h
0x180028ea9  pop     rdi
0x180028eaa  pop     rsi
0x180028eab  pop     rbx
0x180028eac  pop     rbp
0x180028ead  retn
```
