# CheckCallerAdminAccess(void)

- ea: `0x180001f58`
- end: `0x180002140`
- name: `?CheckCallerAdminAccess@@YAJXZ`
- size: `488`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002760`
- `0x180002870`
- `0x1800029d0`
- `0x180002b30`
- `0x180002e70`

## callees

- `0x180001e04`
- `0x180001f58`
- `0x180003be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fbf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180001fb5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180001fb5`
- `ntdll!NtAccessCheck` at `0x1800020ae`
- `ntdll!NtAccessCheck` at `0x1800020ae`
- `ntdll!NtOpenThreadToken` at `0x180002026`
- `ntdll!NtOpenThreadToken` at `0x180002026`
- `ntdll!RtlNtStatusToDosError` at `0x180002032`
- `ntdll!RtlNtStatusToDosError` at `0x1800020ba`
- `ntdll!RtlNtStatusToDosError` at `0x1800020fc`
- `ntdll!RtlNtStatusToDosError` at `0x180002032`
- `ntdll!RtlNtStatusToDosError` at `0x1800020ba`
- `ntdll!RtlNtStatusToDosError` at `0x1800020fc`
- `ntdll!NtClose` at `0x18000211b`
- `ntdll!NtClose` at `0x18000211b`

## pseudocode

```c
__int64 CheckCallerAdminAccess(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  int v4; // eax
  signed int v5; // eax
  int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  NTSTATUS Status; // [rsp+40h] [rbp-C0h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-BCh] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-A0h] BYREF

  TokenHandle = 0;
  SecurityDescriptor = 0;
  ReturnLength = 256;
  GrantedAccess = 0;
  Status = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:BAG:BAD:(A;;0x1;;;BA)S:(ML;;NWNXNR;;;HI)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( v4 >= 0 )
    {
      v6 = NtAccessCheck(
             SecurityDescriptor,
             TokenHandle,
             1u,
             &GenericMapping,
             &PrivilegeSet,
             &ReturnLength,
             &GrantedAccess,
             &Status);
      if ( v6 >= 0 )
      {
        v1 = 0;
        if ( Status < 0 )
        {
          v8 = RtlNtStatusToDosError(Status);
          v1 = v8;
          if ( v8 > 0 )
            v1 = (unsigned __int16)v8 | 0x80070000;
        }
      }
      else
      {
        v7 = RtlNtStatusToDosError(v6);
        v1 = v7;
        if ( v7 > 0 )
          v1 = (unsigned __int16)v7 | 0x80070000;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v3 = 45;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v5 = RtlNtStatusToDosError(v4);
      v1 = v5;
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 44;
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 43;
LABEL_7:
      WPP_SF_D(v2[2], v3, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids, v1);
    }
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180001f58  mov     [rsp-8+arg_0], rbx
0x180001f5d  push    rbp
0x180001f5e  lea     rbp, [rsp-70h]
0x180001f63  sub     rsp, 170h
0x180001f6a  mov     rax, cs:__security_cookie
0x180001f71  xor     rax, rsp
0x180001f74  mov     [rbp+70h+var_10], rax
0x180001f78  xor     r9d, r9d; SecurityDescriptorSize
0x180001f7b  mov     [rsp+170h+TokenHandle], 0
0x180001f84  lea     r8, [rsp+170h+SecurityDescriptor]; SecurityDescriptor
0x180001f89  mov     [rsp+170h+SecurityDescriptor], 0
0x180001f92  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x1;;;BA)S:(ML;;NWNXNR;;;"...
0x180001f99  mov     [rsp+170h+var_128], 100h
0x180001fa1  mov     [rsp+170h+var_12C], 0
0x180001fa9  lea     edx, [r9+1]; StringSDRevision
0x180001fad  mov     [rsp+170h+Status], 0
0x180001fb5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180001fbb  test    eax, eax
0x180001fbd  jnz     short loc_180002012
0x180001fbf  call    cs:__imp_GetLastError
0x180001fc5  mov     ebx, eax
0x180001fc7  test    eax, eax
0x180001fc9  jle     short loc_180001FD4
0x180001fcb  movzx   ebx, ax
0x180001fce  or      ebx, 80070000h
0x180001fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fdb  lea     rax, WPP_GLOBAL_Control
0x180001fe2  cmp     rcx, rax
0x180001fe5  jz      loc_180002111
0x180001feb  test    byte ptr [rcx+1Ch], 1
0x180001fef  jz      loc_180002111
0x180001ff5  mov     edx, 2Bh ; '+'
0x180001ffa  mov     rcx, [rcx+10h]
0x180001ffe  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002005  mov     r9d, ebx
0x180002008  call    WPP_SF_D
0x18000200d  jmp     loc_180002111
0x180002012  lea     r9, [rsp+170h+TokenHandle]; TokenHandle
0x180002017  mov     r8b, 1; OpenAsSelf
0x18000201a  mov     edx, 8; DesiredAccess
0x18000201f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180002026  call    cs:__imp_NtOpenThreadToken
0x18000202c  test    eax, eax
0x18000202e  jns     short loc_18000206F
0x180002030  mov     ecx, eax; Status
0x180002032  call    cs:__imp_RtlNtStatusToDosError
0x180002038  mov     ebx, eax
0x18000203a  test    eax, eax
0x18000203c  jle     short loc_180002047
0x18000203e  movzx   ebx, ax
0x180002041  or      ebx, 80070000h
0x180002047  mov     rcx, cs:WPP_GLOBAL_Control
0x18000204e  lea     rax, WPP_GLOBAL_Control
0x180002055  cmp     rcx, rax
0x180002058  jz      loc_180002111
0x18000205e  test    byte ptr [rcx+1Ch], 1
0x180002062  jz      loc_180002111
0x180002068  mov     edx, 2Ch ; ','
0x18000206d  jmp     short loc_180001FFA
0x18000206f  mov     rdx, [rsp+170h+TokenHandle]; ClientToken
0x180002074  lea     rax, [rsp+170h+Status]
0x180002079  mov     rcx, [rsp+170h+SecurityDescriptor]; SecurityDescriptor
0x18000207e  lea     r9, GenericMapping; GenericMapping
0x180002085  mov     [rsp+170h+AccessStatus], rax; AccessStatus
0x18000208a  mov     r8d, 1; DesiredAccess
0x180002090  lea     rax, [rsp+170h+var_12C]
0x180002095  mov     [rsp+170h+GrantedAccess], rax; GrantedAccess
0x18000209a  lea     rax, [rsp+170h+var_128]
0x18000209f  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x1800020a4  lea     rax, [rsp+170h+var_110]
0x1800020a9  mov     [rsp+170h+PrivilegeSet], rax; PrivilegeSet
0x1800020ae  call    cs:__imp_NtAccessCheck
0x1800020b4  test    eax, eax
0x1800020b6  jns     short loc_1800020F2
0x1800020b8  mov     ecx, eax; Status
0x1800020ba  call    cs:__imp_RtlNtStatusToDosError
0x1800020c0  mov     ebx, eax
0x1800020c2  test    eax, eax
0x1800020c4  jle     short loc_1800020CF
0x1800020c6  movzx   ebx, ax
0x1800020c9  or      ebx, 80070000h
0x1800020cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020d6  lea     rax, WPP_GLOBAL_Control
0x1800020dd  cmp     rcx, rax
0x1800020e0  jz      short loc_180002111
0x1800020e2  test    byte ptr [rcx+1Ch], 1
0x1800020e6  jz      short loc_180002111
0x1800020e8  mov     edx, 2Dh ; '-'
0x1800020ed  jmp     loc_180001FFA
0x1800020f2  mov     ecx, [rsp+170h+Status]; Status
0x1800020f6  xor     ebx, ebx
0x1800020f8  test    ecx, ecx
0x1800020fa  jns     short loc_180002111
0x1800020fc  call    cs:__imp_RtlNtStatusToDosError
0x180002102  mov     ebx, eax
0x180002104  test    eax, eax
0x180002106  jle     short loc_180002111
0x180002108  movzx   ebx, ax
0x18000210b  or      ebx, 80070000h
0x180002111  mov     rcx, [rsp+170h+TokenHandle]; Handle
0x180002116  test    rcx, rcx
0x180002119  jz      short loc_180002121
0x18000211b  call    cs:__imp_NtClose
0x180002121  mov     eax, ebx
0x180002123  mov     rcx, [rbp+70h+var_10]
0x180002127  xor     rcx, rsp; StackCookie
0x18000212a  call    __security_check_cookie
0x18000212f  mov     rbx, [rsp+170h+arg_0]
0x180002137  add     rsp, 170h
0x18000213e  pop     rbp
0x18000213f  retn
```
