# EnsureAdminFileAccess(ushort *)

- ea: `0x1800307cc`
- end: `0x180030928`
- name: `?EnsureAdminFileAccess@@YAKPEAG@Z`
- size: `348`
- prototype: `unsigned int __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18002fc14`
- `0x180032ac4`

## callees

- `0x1800307cc`
- `0x18006e628`
- `0x18006e6f8`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030901`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18003088b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18003088b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003084c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003084c`
- `ADVAPI32!TreeResetNamedSecurityInfoW` at `0x1800308e2`
- `ADVAPI32!TreeResetNamedSecurityInfoW` at `0x1800308e2`

## string_xrefs

- `0x18003085a`: `SeTakeOwnershipPrivilege`

## pseudocode

```c
__int64 __fastcall EnsureAdminFileAccess(LPWSTR pObjectName)
{
  DWORD v2; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+68h] [rbp-98h] BYREF
  PSID pOwner; // [rsp+70h] [rbp-90h] BYREF
  struct _TOKEN_PRIVILEGES v7[2]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR StringSecurityDescriptor[48]; // [rsp+A0h] [rbp-60h] BYREF

  wcscpy(StringSecurityDescriptor, L"O:BAG:BAD:(A;OICI;FA;;;SY)(A;OICI;FA;;BA)");
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    pOwner = 0;
    bOwnerDefaulted = 0;
    CAutoPrivilegeEnable::CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v7, L"SeTakeOwnershipPrivilege");
    GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted);
    v2 = TreeResetNamedSecurityInfoW(
           pObjectName,
           SE_FILE_OBJECT,
           1u,
           pOwner,
           0,
           0,
           0,
           0,
           _TreeResetCallback,
           ProgressInvokeEveryObject,
           SecurityDescriptor);
    LocalFree(SecurityDescriptor);
    CAutoPrivilegeEnable::~CAutoPrivilegeEnable(v7);
  }
  else
  {
    return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x1800307cc  mov     [rsp-8+arg_8], rbx
0x1800307d1  push    rbp
0x1800307d2  lea     rbp, [rsp-10h]
0x1800307d7  sub     rsp, 110h
0x1800307de  mov     rax, cs:__security_cookie
0x1800307e5  xor     rax, rsp
0x1800307e8  mov     [rbp+10h+var_10], rax
0x1800307ec  movaps  xmm0, xmmword ptr cs:aOBagBadAOiciFa; "O:BAG:BAD:(A;OICI;FA;;;SY)(A;OICI;FA;;;"...
0x1800307f3  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x1800307f8  movaps  xmm1, xmmword ptr cs:aOBagBadAOiciFa+10h; "D:(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)"
0x1800307ff  xor     r9d, r9d; SecurityDescriptorSize
0x180030802  movaps  xmmword ptr [rbp+10h+StringSecurityDescriptor], xmm0
0x180030806  mov     rbx, rcx
0x180030809  movaps  xmm0, xmmword ptr cs:aOBagBadAOiciFa+20h; "I;FA;;;SY)(A;OICI;FA;;;BA)"
0x180030810  lea     rcx, [rbp+10h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180030814  movaps  [rbp+10h+var_60], xmm1
0x180030818  movaps  xmm1, xmmword ptr cs:aOBagBadAOiciFa+30h; "Y)(A;OICI;FA;;;BA)"
0x18003081f  lea     edx, [r9+1]; StringSDRevision
0x180030823  movaps  [rbp+10h+var_50], xmm0
0x180030827  movaps  xmm0, xmmword ptr cs:aOBagBadAOiciFa+40h; "I;FA;;;BA)"
0x18003082e  movaps  [rbp+10h+var_40], xmm1
0x180030832  movsd   xmm1, qword ptr cs:aOBagBadAOiciFa+4Eh; "BA)"
0x18003083a  movaps  [rbp+10h+var_30], xmm0
0x18003083e  movsd   qword ptr [rbp+10h+var_30+0Eh], xmm1
0x180030843  mov     [rsp+110h+SecurityDescriptor], 0
0x18003084c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180030852  test    eax, eax
0x180030854  jz      loc_180030901
0x18003085a  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180030861  mov     [rsp+110h+pOwner], 0
0x18003086a  lea     rcx, [rsp+110h+var_98]; this
0x18003086f  mov     [rsp+110h+bOwnerDefaulted], 0
0x180030877  call    ??0CAutoPrivilegeEnable@@QEAA@PEBG@Z; CAutoPrivilegeEnable::CAutoPrivilegeEnable(ushort const *)
0x18003087c  mov     rcx, [rsp+110h+SecurityDescriptor]; pSecurityDescriptor
0x180030881  lea     r8, [rsp+110h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180030886  lea     rdx, [rsp+110h+pOwner]; pOwner
0x18003088b  call    cs:__imp_GetSecurityDescriptorOwner
0x180030891  mov     rax, [rsp+110h+SecurityDescriptor]
0x180030896  mov     edx, 1; ObjectType
0x18003089b  mov     r9, [rsp+110h+pOwner]; pOwner
0x1800308a0  mov     r8d, edx; SecurityInfo
0x1800308a3  mov     [rsp+110h+Args], rax; Args
0x1800308a8  mov     rcx, rbx; pObjectName
0x1800308ab  mov     [rsp+110h+ProgressInvokeSetting], 2; ProgressInvokeSetting
0x1800308b3  lea     rax, ?_TreeResetCallback@@YAXPEAGKPEAW4_PROGRESS_INVOKE_SETTING@@PEAXH@Z; _TreeResetCallback(ushort *,ulong,_PROGRESS_INVOKE_SETTING *,void *,int)
0x1800308ba  mov     [rsp+110h+fnProgress], rax; fnProgress
0x1800308bf  mov     [rsp+110h+KeepExplicit], 0; KeepExplicit
0x1800308c7  mov     [rsp+110h+pSacl], 0; pSacl
0x1800308d0  mov     [rsp+110h+pDacl], 0; pDacl
0x1800308d9  mov     [rsp+110h+pGroup], 0; pGroup
0x1800308e2  call    cs:__imp_TreeResetNamedSecurityInfoW
0x1800308e8  mov     rcx, [rsp+110h+SecurityDescriptor]; hMem
0x1800308ed  mov     ebx, eax
0x1800308ef  call    cs:__imp_LocalFree
0x1800308f5  lea     rcx, [rsp+110h+var_98]; this
0x1800308fa  call    ??1CAutoPrivilegeEnable@@QEAA@XZ; CAutoPrivilegeEnable::~CAutoPrivilegeEnable(void)
0x1800308ff  jmp     short loc_180030909
0x180030901  call    cs:__imp_GetLastError
0x180030907  mov     ebx, eax
0x180030909  mov     eax, ebx
0x18003090b  mov     rcx, [rbp+10h+var_10]
0x18003090f  xor     rcx, rsp; StackCookie
0x180030912  call    __security_check_cookie
0x180030917  mov     rbx, [rsp+110h+arg_8]
0x18003091f  add     rsp, 110h
0x180030926  pop     rbp
0x180030927  retn
```
