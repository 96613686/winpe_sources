# DuplicateAndSetTokenClaim(void *,ushort const *,_TOKEN_SECURITY_ATTRIBUTE_V1 *,void * *)

- ea: `0x1800c6e44`
- end: `0x1800c7014`
- name: `?DuplicateAndSetTokenClaim@@YAJPEAXPEBGPEAU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEAPEAX@Z`
- size: `464`
- prototype: `int(void *, const unsigned __int16 *, struct _TOKEN_SECURITY_ATTRIBUTE_V1 *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c6df8`
- `0x1800c701c`

## callees

- `0x180034540`
- `0x18007e3d4`
- `0x1800c6e44`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800c6f5a`
- `ntdll!RtlAcquirePrivilege` at `0x1800c6f5a`
- `ntdll!NtSetInformationToken` at `0x1800c6fb3`
- `ntdll!NtSetInformationToken` at `0x1800c6fb3`
- `ntdll!RtlReleasePrivilege` at `0x1800c6fbf`
- `ntdll!RtlReleasePrivilege` at `0x1800c6fbf`
- `ntdll!NtDuplicateToken` at `0x1800c6eac`
- `ntdll!NtDuplicateToken` at `0x1800c6eac`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6f01`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6f01`
- `ntdll!RtlInitUnicodeString` at `0x1800c6f22`
- `ntdll!RtlInitUnicodeString` at `0x1800c6f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6f6a`

## string_xrefs

- `0x1800c6ef3`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x1800c6ed3`: `NtDuplicateToken failed: %!STATUS!`
- `0x1800c6f93`: `RtlAcquirePrivilege failed: %!STATUS!`
- `0x1800c6ee4`: `DuplicateAndSetTokenClaim`
- `0x1800c6fec`: `NtSetInformationToken failed: %!STATUS!`

## pseudocode

```c
int __fastcall DuplicateAndSetTokenClaim(void *a1, const unsigned __int16 *a2, struct _UNICODE_STRING *a3, void **a4)
{
  int v7; // ebx
  const wchar_t *v8; // rax
  int v9; // r8d
  int result; // eax
  PHANDLE NewTokenHandle; // [rsp+28h] [rbp-50h]
  __int64 Privilege; // [rsp+30h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-40h] BYREF
  PVOID ReturnedState; // [rsp+40h] [rbp-38h] BYREF
  __int128 v15; // [rsp+48h] [rbp-30h] BYREF
  __int128 TokenInformation; // [rsp+58h] [rbp-20h] BYREF
  int v17; // [rsp+C8h] [rbp+50h] BYREF

  *a4 = 0;
  v17 = 4;
  hObject = 0;
  LODWORD(Privilege) = 7;
  ReturnedState = 0;
  v15 = 0;
  TokenInformation = 0;
  v7 = NtDuplicateToken(a1, 0, 0, 0, TokenPrimary, &hObject);
  if ( v7 < 0 )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      goto LABEL_7;
    v8 = L"NtDuplicateToken failed: %!STATUS!";
    v9 = 433;
    goto LABEL_6;
  }
  RtlInitUnicodeString(a3, a2);
  LODWORD(a3[1].Buffer) = 1;
  *(_QWORD *)&TokenInformation = &v15;
  LOWORD(v15) = 1;
  *((_QWORD *)&TokenInformation + 1) = &v17;
  DWORD1(v15) = 1;
  *((_QWORD *)&v15 + 1) = a3;
  v7 = RtlAcquirePrivilege((PULONG)&Privilege, 1u, 2u, &ReturnedState);
  if ( v7 < 0 )
  {
    CloseHandle(hObject);
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
      goto LABEL_7;
    v8 = L"RtlAcquirePrivilege failed: %!STATUS!";
    v9 = 461;
    goto LABEL_6;
  }
  v7 = NtSetInformationToken(hObject, TokenSecurityAttributes, &TokenInformation, 0x10u);
  RtlReleasePrivilege(ReturnedState);
  if ( v7 >= 0 )
  {
    *a4 = hObject;
    return 0;
  }
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
  {
    v8 = L"NtSetInformationToken failed: %!STATUS!";
    v9 = 472;
LABEL_6:
    LODWORD(NewTokenHandle) = v7;
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\processtoken\\processtoken.cxx",
      (unsigned int)"DuplicateAndSetTokenClaim",
      v9,
      0,
      (__int64)v8,
      NewTokenHandle,
      Privilege);
  }
LABEL_7:
  result = RtlNtStatusToDosError(v7);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800c6e44  push    rbp
0x1800c6e46  push    rbx
0x1800c6e47  push    rsi
0x1800c6e48  push    rdi
0x1800c6e49  push    r12
0x1800c6e4b  push    r14
0x1800c6e4d  mov     rbp, rsp
0x1800c6e50  sub     rsp, 78h
0x1800c6e54  lea     rax, [rbp+hObject]
0x1800c6e58  mov     qword ptr [r9], 0
0x1800c6e5f  mov     rdi, r9
0x1800c6e62  mov     [rsp+78h+NewTokenHandle], rax; NewTokenHandle
0x1800c6e67  mov     rsi, r8
0x1800c6e6a  mov     [rbp+arg_18], 4
0x1800c6e71  mov     r14, rdx
0x1800c6e74  mov     [rbp+hObject], 0
0x1800c6e7c  xorps   xmm0, xmm0
0x1800c6e7f  mov     dword ptr [rbp+Privilege], 7
0x1800c6e86  xorps   xmm1, xmm1
0x1800c6e89  mov     [rbp+ReturnedState], 0
0x1800c6e91  mov     r12d, 1
0x1800c6e97  xor     r9d, r9d; EffectiveOnly
0x1800c6e9a  xor     r8d, r8d; ObjectAttributes
0x1800c6e9d  mov     [rsp+78h+TokenType], r12d; TokenType
0x1800c6ea2  xor     edx, edx; DesiredAccess
0x1800c6ea4  movups  [rbp+var_30], xmm0
0x1800c6ea8  movups  [rbp+TokenInformation], xmm1
0x1800c6eac  call    cs:__imp_NtDuplicateToken
0x1800c6eb2  mov     ebx, eax
0x1800c6eb4  test    eax, eax
0x1800c6eb6  jns     short loc_1800C6F1C
0x1800c6eb8  mov     ecx, cs:dword_18014E4B8
0x1800c6ebe  test    ecx, ecx
0x1800c6ec0  jnz     short loc_1800C6ED3
0x1800c6ec2  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800c6ec8  jz      short loc_1800C6EFF
0x1800c6eca  call    IsWppLevelEnabled
0x1800c6ecf  test    al, al
0x1800c6ed1  jz      short loc_1800C6EFF
0x1800c6ed3  lea     rax, aNtduplicatetok; "NtDuplicateToken failed: %!STATUS!"
0x1800c6eda  mov     r8d, 1B1h
0x1800c6ee0  mov     dword ptr [rsp+78h+NewTokenHandle], ebx
0x1800c6ee4  lea     rdx, aDuplicateandse; "DuplicateAndSetTokenClaim"
0x1800c6eeb  xor     r9d, r9d
0x1800c6eee  mov     qword ptr [rsp+78h+TokenType], rax
0x1800c6ef3  lea     rcx, aOnecoreComComb_112; "onecore\\com\\combase\\processtoken\\pr"...
0x1800c6efa  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800c6eff  mov     ecx, ebx; Status
0x1800c6f01  call    cs:__imp_RtlNtStatusToDosError
0x1800c6f07  test    eax, eax
0x1800c6f09  jle     loc_1800C7007
0x1800c6f0f  movzx   eax, ax
0x1800c6f12  or      eax, 80070000h
0x1800c6f17  jmp     loc_1800C7007
0x1800c6f1c  mov     rdx, r14; SourceString
0x1800c6f1f  mov     rcx, rsi; DestinationString
0x1800c6f22  call    cs:__imp_RtlInitUnicodeString
0x1800c6f28  lea     rax, [rbp+var_30]
0x1800c6f2c  mov     [rsi+18h], r12d
0x1800c6f30  mov     qword ptr [rbp+TokenInformation], rax
0x1800c6f34  lea     r9, [rbp+ReturnedState]; ReturnedState
0x1800c6f38  lea     rax, [rbp+arg_18]
0x1800c6f3c  mov     word ptr [rbp+var_30], r12w
0x1800c6f41  mov     r8d, 2; Flags
0x1800c6f47  mov     qword ptr [rbp+TokenInformation+8], rax
0x1800c6f4b  mov     edx, r12d; NumPriv
0x1800c6f4e  mov     dword ptr [rbp+var_30+4], r12d
0x1800c6f52  lea     rcx, [rbp+Privilege]; Privilege
0x1800c6f56  mov     qword ptr [rbp+var_30+8], rsi
0x1800c6f5a  call    cs:__imp_RtlAcquirePrivilege
0x1800c6f60  mov     rcx, [rbp+hObject]; TokenHandle
0x1800c6f64  mov     ebx, eax
0x1800c6f66  test    eax, eax
0x1800c6f68  jns     short loc_1800C6FA5
0x1800c6f6a  call    cs:__imp_CloseHandle
0x1800c6f70  mov     ecx, cs:dword_18014E4B8
0x1800c6f76  test    ecx, ecx
0x1800c6f78  jnz     short loc_1800C6F93
0x1800c6f7a  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800c6f80  jz      loc_1800C6EFF
0x1800c6f86  call    IsWppLevelEnabled
0x1800c6f8b  test    al, al
0x1800c6f8d  jz      loc_1800C6EFF
0x1800c6f93  lea     rax, aRtlacquirepriv; "RtlAcquirePrivilege failed: %!STATUS!"
0x1800c6f9a  mov     r8d, 1CDh
0x1800c6fa0  jmp     loc_1800C6EE0
0x1800c6fa5  mov     r9d, 10h; TokenInformationLength
0x1800c6fab  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800c6faf  lea     edx, [r9+17h]; TokenInformationClass
0x1800c6fb3  call    cs:__imp_NtSetInformationToken
0x1800c6fb9  mov     rcx, [rbp+ReturnedState]; ReturnedState
0x1800c6fbd  mov     ebx, eax
0x1800c6fbf  call    cs:__imp_RtlReleasePrivilege
0x1800c6fc5  test    ebx, ebx
0x1800c6fc7  jns     short loc_1800C6FFE
0x1800c6fc9  mov     ecx, cs:dword_18014E4B8
0x1800c6fcf  test    ecx, ecx
0x1800c6fd1  jnz     short loc_1800C6FEC
0x1800c6fd3  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800c6fd9  jz      loc_1800C6EFF
0x1800c6fdf  call    IsWppLevelEnabled
0x1800c6fe4  test    al, al
0x1800c6fe6  jz      loc_1800C6EFF
0x1800c6fec  lea     rax, aNtsetinformati; "NtSetInformationToken failed: %!STATUS!"
0x1800c6ff3  mov     r8d, 1D8h
0x1800c6ff9  jmp     loc_1800C6EE0
0x1800c6ffe  mov     rax, [rbp+hObject]
0x1800c7002  mov     [rdi], rax
0x1800c7005  xor     eax, eax
0x1800c7007  add     rsp, 78h
0x1800c700b  pop     r14
0x1800c700d  pop     r12
0x1800c700f  pop     rdi
0x1800c7010  pop     rsi
0x1800c7011  pop     rbx
0x1800c7012  pop     rbp
0x1800c7013  retn
```
