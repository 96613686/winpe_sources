# CSecurityInformation::GetEffectivePermission(_GUID const *,void *,ushort const *,void *,_OBJECT_TYPE_LIST * *,ulong *,ulong * *,ulong *)

- ea: `0x18000bf90`
- end: `0x18000c1e4`
- name: `?GetEffectivePermission@CSecurityInformation@@UEAAJPEBU_GUID@@PEAXPEBG1PEAPEAU_OBJECT_TYPE_LIST@@PEAKPEAPEAK4@Z`
- size: `596`
- prototype: `__int64 __fastcall(CSecurityInformation *this, const struct _GUID *, void *, unsigned __int16 *, PSECURITY_DESCRIPTOR pSecurityDescriptor, struct _OBJECT_TYPE_LIST **, unsigned int *, unsigned int **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000bf90`
- `0x18000c7d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c158`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c198`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c0f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c114`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c0f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c114`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000c036`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000c036`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c047`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c047`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18000c0c1`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18000c0c1`
- `AUTHZ!AuthzFreeContext` at `0x18000c176`
- `AUTHZ!AuthzFreeContext` at `0x18000c176`
- `AUTHZ!AuthzAccessCheck` at `0x18000c14e`
- `AUTHZ!AuthzAccessCheck` at `0x18000c14e`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::GetEffectivePermission(
        CSecurityInformation *this,
        const struct _GUID *a2,
        void *a3,
        unsigned __int16 *a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        struct _OBJECT_TYPE_LIST **a6,
        unsigned int *a7,
        unsigned int **a8,
        unsigned int *a9)
{
  void *v11; // rdi
  struct _OBJECT_TYPE_LIST **v12; // r14
  unsigned int *v13; // r15
  unsigned int **v14; // r12
  unsigned int *v15; // r13
  AUTHZ_RESOURCE_MANAGER_HANDLE v16; // rsi
  signed int v17; // ebx
  int v18; // eax
  signed int LastError; // eax
  DWORD ObjectTypeListLength; // edx
  PACCESS_MASK GrantedAccessMask; // rcx
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+58h] [rbp-41h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+78h] [rbp-21h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+F0h] [rbp+57h] BYREF
  unsigned __int16 *v26; // [rsp+F8h] [rbp+5Fh]

  v26 = a4;
  hAuthzClientContext = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  memset(&pReply, 0, sizeof(pReply));
  if ( !a3 )
    return 2147500035LL;
  v11 = pSecurityDescriptor;
  if ( !pSecurityDescriptor )
    return 2147500035LL;
  v12 = a6;
  if ( !a6 )
    return 2147500035LL;
  v13 = a7;
  if ( !a7 )
    return 2147500035LL;
  v14 = a8;
  if ( !a8 )
    return 2147500035LL;
  v15 = a9;
  if ( !a9 )
    return 2147500035LL;
  if ( !IsValidSecurityDescriptor(pSecurityDescriptor) || !IsValidSid(a3) )
    return 2147942487LL;
  v16 = (AUTHZ_RESOURCE_MANAGER_HANDLE)*((_QWORD *)this + 11);
  pRequest.ObjectTypeList = (POBJECT_TYPE_LIST)&g_DefaultOTL;
  pRequest.ObjectTypeListLength = 1;
  pReply.GrantedAccessMask = 0;
  pReply.Error = 0;
  if ( v16 )
  {
    v18 = SkipLocalGroup(v26, a3);
    if ( AuthzInitializeContextFromSid(v18 != 0 ? 2 : 0, a3, v16, 0, (LUID)0xBEEF0000DEADLL, 0, &hAuthzClientContext) )
    {
      pRequest.DesiredAccess = 0x2000000;
      pRequest.PrincipalSelfSid = 0;
      pRequest.OptionalArguments = 0;
      pReply.ResultListLength = pRequest.ObjectTypeListLength;
      pReply.SaclEvaluationResults = 0;
      pReply.GrantedAccessMask = (PACCESS_MASK)LocalAlloc(0x40u, 4LL * pRequest.ObjectTypeListLength);
      if ( !pReply.GrantedAccessMask || (pReply.Error = (PDWORD)LocalAlloc(0x40u, 4LL * pReply.ResultListLength)) == 0 )
      {
        v17 = -2147024882;
        goto LABEL_18;
      }
      v17 = 0;
      if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, v11, 0, 0, &pReply, 0) )
        goto LABEL_18;
    }
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  v17 = -2147418113;
LABEL_18:
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  if ( v17 >= 0 )
  {
    ObjectTypeListLength = pRequest.ObjectTypeListLength;
    *v12 = pRequest.ObjectTypeList;
    GrantedAccessMask = pReply.GrantedAccessMask;
    *v13 = ObjectTypeListLength;
    *v14 = GrantedAccessMask;
    *v15 = ObjectTypeListLength;
  }
  else
  {
    if ( pReply.GrantedAccessMask )
      LocalFree(pReply.GrantedAccessMask);
    if ( pReply.Error )
      LocalFree(pReply.Error);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000bf90  mov     [rsp-8+arg_0], rbx
0x18000bf95  mov     [rsp-8+arg_18], r9
0x18000bf9a  push    rbp
0x18000bf9b  push    rsi
0x18000bf9c  push    rdi
0x18000bf9d  push    r12
0x18000bf9f  push    r13
0x18000bfa1  push    r14
0x18000bfa3  push    r15
0x18000bfa5  lea     rbp, [rsp-7]
0x18000bfaa  sub     rsp, 0A0h
0x18000bfb1  xorps   xmm0, xmm0
0x18000bfb4  mov     [rbp+37h+hAuthzClientContext], 0
0x18000bfbc  xor     eax, eax
0x18000bfbe  mov     [rbp+37h+var_80.LowPart], 0DEADh
0x18000bfc5  mov     [rbp+37h+var_80.HighPart], 0BEEFh
0x18000bfcc  mov     rbx, r8
0x18000bfcf  mov     [rbp+37h+pRequest.OptionalArguments], rax
0x18000bfd3  mov     rsi, rcx
0x18000bfd6  movups  xmmword ptr [rbp+37h+pRequest.DesiredAccess], xmm0
0x18000bfda  movups  xmmword ptr [rbp+37h+pRequest.ObjectTypeList], xmm0
0x18000bfde  movups  xmmword ptr [rbp+37h+var_78.ResultListLength], xmm0
0x18000bfe2  movups  xmmword ptr [rbp+37h+var_78.SaclEvaluationResults], xmm0
0x18000bfe6  test    r8, r8
0x18000bfe9  jz      loc_18000C1C4
0x18000bfef  mov     rdi, [rbp+37h+pSecurityDescriptor]
0x18000bff3  test    rdi, rdi
0x18000bff6  jz      loc_18000C1C4
0x18000bffc  mov     r14, [rbp+37h+arg_28]
0x18000c000  test    r14, r14
0x18000c003  jz      loc_18000C1C4
0x18000c009  mov     r15, [rbp+37h+arg_30]
0x18000c00d  test    r15, r15
0x18000c010  jz      loc_18000C1C4
0x18000c016  mov     r12, [rbp+37h+arg_38]
0x18000c01a  test    r12, r12
0x18000c01d  jz      loc_18000C1C4
0x18000c023  mov     r13, [rbp+37h+arg_40]
0x18000c02a  test    r13, r13
0x18000c02d  jz      loc_18000C1C4
0x18000c033  mov     rcx, rdi; pSecurityDescriptor
0x18000c036  call    cs:__imp_IsValidSecurityDescriptor
0x18000c03c  test    eax, eax
0x18000c03e  jz      loc_18000C1BD
0x18000c044  mov     rcx, rbx; pSid
0x18000c047  call    cs:__imp_IsValidSid
0x18000c04d  test    eax, eax
0x18000c04f  jz      loc_18000C1BD
0x18000c055  mov     rsi, [rsi+58h]
0x18000c059  lea     rax, ?g_DefaultOTL@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * g_DefaultOTL
0x18000c060  mov     [rbp+37h+pRequest.ObjectTypeList], rax
0x18000c064  mov     [rbp+37h+pRequest.ObjectTypeListLength], 1
0x18000c06b  mov     [rbp+37h+var_78.GrantedAccessMask], 0
0x18000c073  mov     [rbp+37h+var_78.Error], 0
0x18000c07b  test    rsi, rsi
0x18000c07e  jnz     short loc_18000C08A
0x18000c080  mov     ebx, 8000FFFFh
0x18000c085  jmp     loc_18000C16D
0x18000c08a  mov     rcx, [rbp+37h+arg_18]; unsigned __int16 *
0x18000c08e  mov     rdx, rbx; void *
0x18000c091  call    ?SkipLocalGroup@@YAHPEBGPEAX@Z; SkipLocalGroup(ushort const *,void *)
0x18000c096  neg     eax
0x18000c098  mov     r8, rsi; hAuthzResourceManager
0x18000c09b  lea     rax, [rbp+37h+hAuthzClientContext]
0x18000c09f  mov     rdx, rbx; UserSid
0x18000c0a2  mov     [rsp+0D0h+phAuthzClientContext], rax; phAuthzClientContext
0x18000c0a7  sbb     ecx, ecx
0x18000c0a9  mov     rax, qword ptr [rbp+37h+var_80.LowPart]
0x18000c0ad  and     ecx, 2; Flags
0x18000c0b0  mov     [rsp+0D0h+DynamicGroupArgs], 0; DynamicGroupArgs
0x18000c0b9  xor     r9d, r9d; pExpirationTime
0x18000c0bc  mov     qword ptr [rsp+0D0h+Identifier.LowPart], rax; Identifier
0x18000c0c1  call    cs:__imp_AuthzInitializeContextFromSid
0x18000c0c7  xor     esi, esi
0x18000c0c9  test    eax, eax
0x18000c0cb  jz      loc_18000C158
0x18000c0d1  mov     eax, [rbp+37h+pRequest.ObjectTypeListLength]
0x18000c0d4  lea     ebx, [rsi+40h]
0x18000c0d7  mov     edx, eax
0x18000c0d9  mov     [rbp+37h+pRequest.DesiredAccess], 2000000h
0x18000c0e0  shl     rdx, 2; uBytes
0x18000c0e4  mov     ecx, ebx; uFlags
0x18000c0e6  mov     [rbp+37h+pRequest.PrincipalSelfSid], rsi
0x18000c0ea  mov     [rbp+37h+pRequest.OptionalArguments], rsi
0x18000c0ee  mov     [rbp+37h+var_78.ResultListLength], eax
0x18000c0f1  mov     [rbp+37h+var_78.SaclEvaluationResults], rsi
0x18000c0f5  call    cs:__imp_LocalAlloc
0x18000c0fb  mov     [rbp+37h+var_78.GrantedAccessMask], rax
0x18000c0ff  test    rax, rax
0x18000c102  jnz     short loc_18000C10B
0x18000c104  mov     ebx, 8007000Eh
0x18000c109  jmp     short loc_18000C16D
0x18000c10b  mov     edx, [rbp+37h+var_78.ResultListLength]
0x18000c10e  mov     ecx, ebx; uFlags
0x18000c110  shl     rdx, 2; uBytes
0x18000c114  call    cs:__imp_LocalAlloc
0x18000c11a  mov     [rbp+37h+var_78.Error], rax
0x18000c11e  test    rax, rax
0x18000c121  jz      short loc_18000C104
0x18000c123  mov     rdx, [rbp+37h+hAuthzClientContext]; hAuthzClientContext
0x18000c127  lea     rax, [rbp+37h+var_78]
0x18000c12b  mov     [rsp+0D0h+phAccessCheckResults], rsi; phAccessCheckResults
0x18000c130  lea     r8, [rbp+37h+pRequest]; pRequest
0x18000c134  mov     [rsp+0D0h+pReply], rax; pReply
0x18000c139  xor     r9d, r9d; hAuditEvent
0x18000c13c  mov     dword ptr [rsp+0D0h+phAuthzClientContext], esi; OptionalSecurityDescriptorCount
0x18000c140  xor     ecx, ecx; Flags
0x18000c142  mov     [rsp+0D0h+DynamicGroupArgs], rsi; OptionalSecurityDescriptorArray
0x18000c147  mov     ebx, esi
0x18000c149  mov     qword ptr [rsp+0D0h+Identifier.LowPart], rdi; pSecurityDescriptor
0x18000c14e  call    cs:__imp_AuthzAccessCheck
0x18000c154  test    eax, eax
0x18000c156  jnz     short loc_18000C16D
0x18000c158  call    cs:__imp_GetLastError
0x18000c15e  mov     ebx, eax
0x18000c160  test    eax, eax
0x18000c162  jle     short loc_18000C16D
0x18000c164  movzx   ebx, ax
0x18000c167  or      ebx, 80070000h
0x18000c16d  mov     rcx, [rbp+37h+hAuthzClientContext]; hAuthzClientContext
0x18000c171  test    rcx, rcx
0x18000c174  jz      short loc_18000C17C
0x18000c176  call    cs:__imp_AuthzFreeContext
0x18000c17c  test    ebx, ebx
0x18000c17e  jns     short loc_18000C1A0
0x18000c180  mov     rcx, [rbp+37h+var_78.GrantedAccessMask]; hMem
0x18000c184  test    rcx, rcx
0x18000c187  jz      short loc_18000C18F
0x18000c189  call    cs:__imp_LocalFree
0x18000c18f  mov     rcx, [rbp+37h+var_78.Error]; hMem
0x18000c193  test    rcx, rcx
0x18000c196  jz      short loc_18000C1B9
0x18000c198  call    cs:__imp_LocalFree
0x18000c19e  jmp     short loc_18000C1B9
0x18000c1a0  mov     rcx, [rbp+37h+pRequest.ObjectTypeList]
0x18000c1a4  mov     edx, [rbp+37h+pRequest.ObjectTypeListLength]
0x18000c1a7  mov     [r14], rcx
0x18000c1aa  mov     rcx, [rbp+37h+var_78.GrantedAccessMask]
0x18000c1ae  mov     [r15], edx
0x18000c1b1  mov     [r12], rcx
0x18000c1b5  mov     [r13+0], edx
0x18000c1b9  mov     eax, ebx
0x18000c1bb  jmp     short loc_18000C1C9
0x18000c1bd  mov     eax, 80070057h
0x18000c1c2  jmp     short loc_18000C1C9
0x18000c1c4  mov     eax, 80004003h
0x18000c1c9  mov     rbx, [rsp+0D0h+arg_0]
0x18000c1d1  add     rsp, 0A0h
0x18000c1d8  pop     r15
0x18000c1da  pop     r14
0x18000c1dc  pop     r13
0x18000c1de  pop     r12
0x18000c1e0  pop     rdi
0x18000c1e1  pop     rsi
0x18000c1e2  pop     rbp
0x18000c1e3  retn
```
