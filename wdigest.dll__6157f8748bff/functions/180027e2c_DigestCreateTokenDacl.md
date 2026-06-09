# DigestCreateTokenDacl

- ea: `0x180027e2c`
- end: `0x180028188`
- name: `DigestCreateTokenDacl`
- size: `860`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028190`

## callees

- `0x1800061a0`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x180018b18`
- `0x180027e2c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f3b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180027f79`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180027f79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002810d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002810d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027f0e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027f0e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180028085`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180028085`
- `ntdll!RtlCreateAcl` at `0x180028048`
- `ntdll!RtlCreateAcl` at `0x180028048`
- `ntdll!RtlAddAccessAllowedAce` at `0x180028061`
- `ntdll!RtlAddAccessAllowedAce` at `0x180028077`
- `ntdll!RtlAddAccessAllowedAce` at `0x180028061`
- `ntdll!RtlAddAccessAllowedAce` at `0x180028077`
- `ntdll!NtQueryInformationToken` at `0x180027fa2`
- `ntdll!NtQueryInformationToken` at `0x180027fa2`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180028096`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180028096`
- `ntdll!RtlLengthSid` at `0x180028015`
- `ntdll!RtlLengthSid` at `0x180028021`
- `ntdll!RtlLengthSid` at `0x180028015`
- `ntdll!RtlLengthSid` at `0x180028021`
- `ntdll!NtClose` at `0x180027fd9`
- `ntdll!NtClose` at `0x180028126`
- `ntdll!NtClose` at `0x180027fd9`
- `ntdll!NtClose` at `0x180028126`

## pseudocode

```c
__int64 __fastcall DigestCreateTokenDacl(PSECURITY_DESCRIPTOR SecurityDescriptor, struct _ACL **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  HANDLE v7; // rax
  void *v8; // rdi
  DWORD LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  ULONG v12; // esi
  ULONG v13; // esi
  struct _ACL *Memory; // rax
  struct _ACL *v15; // rbx
  void *TokenHandle; // [rsp+30h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-41h] BYREF
  DWORD dwProcessId[4]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+50h] [rbp-29h]
  PSID TokenInformation[8]; // [rsp+60h] [rbp-19h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  *(_OWORD *)dwProcessId = 0;
  v20 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
  v4 = *(_QWORD *)&g_LsaFunctions;
  *a2 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(DWORD *))(v4 + 192))(dwProcessId) )
  {
    v5 = -1073741595;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
LABEL_30:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v7 = OpenProcess(0x400u, 0, dwProcessId[0]);
  v8 = v7;
  if ( v7 )
  {
    if ( OpenProcessToken(v7, 8u, &TokenHandle) )
    {
      if ( NtQueryInformationToken(TokenHandle, TokenOwner, TokenInformation, 0x40u, &ReturnLength) >= 0 )
      {
        NtClose(TokenHandle);
        TokenHandle = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
        v12 = RtlLengthSid(&qword_180045320);
        v13 = RtlLengthSid(TokenInformation[0]) + v12;
        Memory = (struct _ACL *)DigestAllocateMemory(v13 + 24);
        v15 = Memory;
        if ( Memory )
        {
          RtlCreateAcl(Memory, v13 + 24, 2u);
          RtlAddAccessAllowedAce(v15, 2u, 0xF01FFu, &qword_180045320);
          RtlAddAccessAllowedAce(v15, 2u, 0x20008u, TokenInformation[0]);
          RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
          RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v15, 0);
          *a2 = v15;
          v5 = 0;
        }
        else
        {
          v5 = -2146893056;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              195,
              &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids,
              2148074240LL);
        }
        goto LABEL_29;
      }
      v5 = -1073741595;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_29:
        CloseHandle(v8);
        goto LABEL_30;
      }
      v11 = 192;
    }
    else
    {
      v5 = -1073741595;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_29;
      v11 = 193;
    }
    WPP_SF_(v10[2], v11, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    goto LABEL_29;
  }
  v5 = -1073741595;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids,
      LastError,
      -1073741595);
    goto LABEL_30;
  }
LABEL_31:
  if ( TokenHandle )
  {
    NtClose(TokenHandle);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    TokenHandle = 0;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 )
    WPP_SF_d(v6[2], 196, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180027e2c  mov     [rsp-8+arg_10], rbx
0x180027e31  mov     [rsp-8+arg_18], rsi
0x180027e36  push    rbp
0x180027e37  push    rdi
0x180027e38  push    r12
0x180027e3a  push    r14
0x180027e3c  push    r15
0x180027e3e  lea     rbp, [rsp-37h]
0x180027e43  sub     rsp, 0B0h
0x180027e4a  mov     rax, cs:__security_cookie
0x180027e51  xor     rax, rsp
0x180027e54  mov     [rbp+57h+var_30], rax
0x180027e58  xorps   xmm0, xmm0
0x180027e5b  mov     [rbp+57h+TokenHandle], 0
0x180027e63  xor     eax, eax
0x180027e65  mov     [rbp+57h+var_98], 0
0x180027e6c  movups  xmmword ptr [rbp+57h+dwProcessId], xmm0
0x180027e70  mov     [rbp+57h+var_80], rax
0x180027e74  mov     r14, rdx
0x180027e77  mov     r15, rcx
0x180027e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e81  lea     r12, WPP_GLOBAL_Control
0x180027e88  cmp     rcx, r12
0x180027e8b  jz      short loc_180027EA8
0x180027e8d  test    byte ptr [rcx+1Ch], 80h
0x180027e91  jz      short loc_180027EA8
0x180027e93  mov     rcx, [rcx+10h]
0x180027e97  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180027e9e  mov     edx, 0BDh
0x180027ea3  call    WPP_SF_
0x180027ea8  mov     rax, cs:g_LsaFunctions
0x180027eaf  lea     rcx, [rbp+57h+dwProcessId]
0x180027eb3  mov     qword ptr [r14], 0
0x180027eba  mov     rax, [rax+0C0h]
0x180027ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ec6  test    al, al
0x180027ec8  jnz     short loc_180027F03
0x180027eca  mov     ebx, 0C00000E5h
0x180027ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ed6  cmp     rcx, r12
0x180027ed9  jz      loc_18002811A
0x180027edf  test    byte ptr [rcx+1Ch], 1
0x180027ee3  jz      loc_18002811A
0x180027ee9  mov     rcx, [rcx+10h]
0x180027eed  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180027ef4  mov     edx, 0BEh
0x180027ef9  call    WPP_SF_
0x180027efe  jmp     loc_180028113
0x180027f03  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x180027f07  xor     edx, edx; bInheritHandle
0x180027f09  mov     ecx, 400h; dwDesiredAccess
0x180027f0e  call    cs:__imp_OpenProcess
0x180027f14  mov     rdi, rax
0x180027f17  test    rax, rax
0x180027f1a  jnz     short loc_180027F6D
0x180027f1c  mov     ebx, 0C00000E5h
0x180027f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f28  cmp     rcx, r12
0x180027f2b  jz      loc_18002811A
0x180027f31  test    byte ptr [rcx+1Ch], 1
0x180027f35  jz      loc_18002811A
0x180027f3b  call    cs:__imp_GetLastError
0x180027f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f48  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180027f4f  mov     edx, 0BFh
0x180027f54  mov     dword ptr [rsp+0D0h+ReturnLength], 0C00000E5h
0x180027f5c  mov     r9d, eax
0x180027f5f  mov     rcx, [rcx+10h]
0x180027f63  call    WPP_SF_dd
0x180027f68  jmp     loc_180028113
0x180027f6d  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180027f71  mov     edx, 8; DesiredAccess
0x180027f76  mov     rcx, rdi; ProcessHandle
0x180027f79  call    cs:__imp_OpenProcessToken
0x180027f7f  test    eax, eax
0x180027f81  jz      loc_1800280DE
0x180027f87  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180027f8b  lea     rax, [rbp+57h+var_98]
0x180027f8f  mov     r9d, 40h ; '@'; TokenInformationLength
0x180027f95  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180027f9a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180027f9e  lea     edx, [r9-3Ch]; TokenInformationClass
0x180027fa2  call    cs:__imp_NtQueryInformationToken
0x180027fa8  test    eax, eax
0x180027faa  jns     short loc_180027FD5
0x180027fac  mov     ebx, 0C00000E5h
0x180027fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fb8  cmp     rcx, r12
0x180027fbb  jz      loc_18002810A
0x180027fc1  test    byte ptr [rcx+1Ch], 1
0x180027fc5  jz      loc_18002810A
0x180027fcb  mov     edx, 0C0h
0x180027fd0  jmp     loc_1800280FA
0x180027fd5  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180027fd9  call    cs:__imp_NtClose
0x180027fdf  mov     [rbp+57h+TokenHandle], 0
0x180027fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fee  cmp     rcx, r12
0x180027ff1  jz      short loc_18002800E
0x180027ff3  test    byte ptr [rcx+1Ch], 4
0x180027ff7  jz      short loc_18002800E
0x180027ff9  mov     rcx, [rcx+10h]
0x180027ffd  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180028004  mov     edx, 0C2h
0x180028009  call    WPP_SF_
0x18002800e  lea     rcx, qword_180045320; Sid
0x180028015  call    cs:__imp_RtlLengthSid
0x18002801b  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x18002801f  mov     esi, eax
0x180028021  call    cs:__imp_RtlLengthSid
0x180028027  add     esi, eax
0x180028029  lea     ecx, [rsi+18h]; Size
0x18002802c  call    DigestAllocateMemory
0x180028031  mov     rbx, rax
0x180028034  test    rax, rax
0x180028037  jz      short loc_1800280AA
0x180028039  mov     r12d, 2
0x18002803f  lea     edx, [rsi+18h]; AclSize
0x180028042  mov     r8d, r12d; AclRevision
0x180028045  mov     rcx, rax; Acl
0x180028048  call    cs:__imp_RtlCreateAcl
0x18002804e  lea     r9, qword_180045320; Sid
0x180028055  mov     r8d, 0F01FFh; AccessMask
0x18002805b  mov     edx, r12d; Revision
0x18002805e  mov     rcx, rbx; Acl
0x180028061  call    cs:__imp_RtlAddAccessAllowedAce
0x180028067  mov     r9, [rbp+57h+TokenInformation]; Sid
0x18002806b  mov     r8d, 20008h; AccessMask
0x180028071  mov     edx, r12d; Revision
0x180028074  mov     rcx, rbx; Acl
0x180028077  call    cs:__imp_RtlAddAccessAllowedAce
0x18002807d  lea     edx, [r12-1]; Revision
0x180028082  mov     rcx, r15; SecurityDescriptor
0x180028085  call    cs:__imp_RtlCreateSecurityDescriptor
0x18002808b  xor     r9d, r9d; DaclDefaulted
0x18002808e  mov     r8, rbx; Dacl
0x180028091  mov     dl, 1; DaclPresent
0x180028093  mov     rcx, r15; SecurityDescriptor
0x180028096  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18002809c  mov     [r14], rbx
0x18002809f  lea     r12, WPP_GLOBAL_Control
0x1800280a6  xor     ebx, ebx
0x1800280a8  jmp     short loc_18002810A
0x1800280aa  mov     ebx, 80090300h
0x1800280af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280b6  cmp     rcx, r12
0x1800280b9  jz      short loc_18002810A
0x1800280bb  test    byte ptr [rcx+1Ch], 1
0x1800280bf  jz      short loc_18002810A
0x1800280c1  mov     rcx, [rcx+10h]
0x1800280c5  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x1800280cc  mov     edx, 0C3h
0x1800280d1  mov     r9d, 80090300h
0x1800280d7  call    WPP_SF_d
0x1800280dc  jmp     short loc_18002810A
0x1800280de  mov     ebx, 0C00000E5h
0x1800280e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280ea  cmp     rcx, r12
0x1800280ed  jz      short loc_18002810A
0x1800280ef  test    byte ptr [rcx+1Ch], 1
0x1800280f3  jz      short loc_18002810A
0x1800280f5  mov     edx, 0C1h
0x1800280fa  mov     rcx, [rcx+10h]
0x1800280fe  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180028105  call    WPP_SF_
0x18002810a  mov     rcx, rdi; hObject
0x18002810d  call    cs:__imp_CloseHandle
0x180028113  mov     rcx, cs:WPP_GLOBAL_Control
0x18002811a  mov     rax, [rbp+57h+TokenHandle]
0x18002811e  test    rax, rax
0x180028121  jz      short loc_18002813B
0x180028123  mov     rcx, rax; Handle
0x180028126  call    cs:__imp_NtClose
0x18002812c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028133  mov     [rbp+57h+TokenHandle], 0
0x18002813b  cmp     rcx, r12
0x18002813e  jz      short loc_18002815E
0x180028140  test    byte ptr [rcx+1Ch], 80h
0x180028144  jz      short loc_18002815E
0x180028146  mov     rcx, [rcx+10h]
0x18002814a  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180028151  mov     edx, 0C4h
0x180028156  mov     r9d, ebx
0x180028159  call    WPP_SF_d
0x18002815e  mov     eax, ebx
0x180028160  mov     rcx, [rbp+57h+var_30]
0x180028164  xor     rcx, rsp; StackCookie
0x180028167  call    __security_check_cookie
0x18002816c  lea     r11, [rsp+0D0h+var_20]
0x180028174  mov     rbx, [r11+40h]
0x180028178  mov     rsi, [r11+48h]
0x18002817c  mov     rsp, r11
0x18002817f  pop     r15
0x180028181  pop     r14
0x180028183  pop     r12
0x180028185  pop     rdi
0x180028186  pop     rbp
0x180028187  retn
```
