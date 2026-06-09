# InitSecurityDescriptor

- ea: `0x18002b064`
- end: `0x18002b255`
- name: `InitSecurityDescriptor`
- size: `497`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, _QWORD *, ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d6d0`

## callees

- `0x180001600`
- `0x18002b064`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002b0ae`
- `KERNEL32!HeapAlloc` at `0x18002b129`
- `KERNEL32!HeapAlloc` at `0x18002b0ae`
- `KERNEL32!HeapAlloc` at `0x18002b129`
- `KERNEL32!GetLastError` at `0x18002b0bc`
- `KERNEL32!GetLastError` at `0x18002b0f2`
- `KERNEL32!GetLastError` at `0x18002b137`
- `KERNEL32!GetLastError` at `0x18002b159`
- `KERNEL32!GetLastError` at `0x18002b186`
- `KERNEL32!GetLastError` at `0x18002b1aa`
- `KERNEL32!GetLastError` at `0x18002b1d3`
- `KERNEL32!GetLastError` at `0x18002b1f7`
- `KERNEL32!GetLastError` at `0x18002b21b`
- `KERNEL32!GetLastError` at `0x18002b0bc`
- `KERNEL32!GetLastError` at `0x18002b0f2`
- `KERNEL32!GetLastError` at `0x18002b137`
- `KERNEL32!GetLastError` at `0x18002b159`
- `KERNEL32!GetLastError` at `0x18002b186`
- `KERNEL32!GetLastError` at `0x18002b1aa`
- `KERNEL32!GetLastError` at `0x18002b1d3`
- `KERNEL32!GetLastError` at `0x18002b1f7`
- `KERNEL32!GetLastError` at `0x18002b21b`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002b211`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002b211`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b17c`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b17c`
- `ADVAPI32!GetLengthSid` at `0x18002b111`
- `ADVAPI32!GetLengthSid` at `0x18002b111`
- `ADVAPI32!InitializeAcl` at `0x18002b14f`
- `ADVAPI32!InitializeAcl` at `0x18002b14f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002b1a0`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002b1a0`
- `ADVAPI32!InitializeSid` at `0x18002b0e8`
- `ADVAPI32!InitializeSid` at `0x18002b0e8`
- `ADVAPI32!GetSidLengthRequired` at `0x18002b09b`
- `ADVAPI32!GetSidLengthRequired` at `0x18002b09b`
- `ADVAPI32!GetSidSubAuthority` at `0x18002b106`
- `ADVAPI32!GetSidSubAuthority` at `0x18002b106`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18002b1ed`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18002b1ed`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002b1c9`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002b1c9`

## string_xrefs

- `0x18002b0c2`: `GetSidLengthRequired() failed, err=%u`
- `0x18002b0f8`: `InitializeSid() failed, err=%u`
- `0x18002b15f`: `InitializeAcl() failed, err=%u`
- `0x18002b18c`: `AddAccessAllowedAce() failed, err=%u`
- `0x18002b1b0`: `InitializeSecurityDescriptor() failed, err=%u`
- `0x18002b1d9`: `SetSecurityDescriptorDacl() failed, err=%u`
- `0x18002b1fd`: `SetSecurityDescriptorOwnr() failed, err=%u`
- `0x18002b221`: `SetSecurityDescriptorGroup() failed, err=%u`

## pseudocode

```c
__int64 __fastcall InitSecurityDescriptor(PSECURITY_DESCRIPTOR pSecurityDescriptor, _QWORD *a2, ACL **a3)
{
  ACL *v4; // rdi
  DWORD SidLengthRequired; // eax
  void *v8; // rax
  void *v9; // rsi
  DWORD v10; // eax
  const char *v11; // rdx
  DWORD LastError; // ebx
  SIZE_T v13; // rbp
  ACL *v14; // rax
  __int64 result; // rax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+20h] [rbp-38h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  v4 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidLengthRequired = GetSidLengthRequired(1u);
  v8 = HeapAlloc(ghTapisrvHeap, 8u, SidLengthRequired);
  v9 = v8;
  if ( v8 )
  {
    if ( InitializeSid(v8, &pIdentifierAuthority, 1u) )
    {
      *GetSidSubAuthority(v9, 0) = 0;
      v13 = GetLengthSid(v9) + 20;
      v14 = (ACL *)HeapAlloc(ghTapisrvHeap, 8u, v13);
      v4 = v14;
      if ( !v14 )
      {
        LastError = GetLastError();
        goto LABEL_21;
      }
      if ( InitializeAcl(v14, v13, 2u) )
      {
        if ( AddAccessAllowedAce(v4, 2u, 0x1FFFFFu, v9) )
        {
          if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
          {
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v4, 0) )
            {
              if ( SetSecurityDescriptorOwner(pSecurityDescriptor, 0, 0) )
              {
                if ( SetSecurityDescriptorGroup(pSecurityDescriptor, 0, 0) )
                {
                  LastError = 0;
                  goto LABEL_21;
                }
                v10 = GetLastError();
                v11 = "SetSecurityDescriptorGroup() failed, err=%u";
              }
              else
              {
                v10 = GetLastError();
                v11 = "SetSecurityDescriptorOwnr() failed, err=%u";
              }
            }
            else
            {
              v10 = GetLastError();
              v11 = "SetSecurityDescriptorDacl() failed, err=%u";
            }
          }
          else
          {
            v10 = GetLastError();
            v11 = "InitializeSecurityDescriptor() failed, err=%u";
          }
        }
        else
        {
          v10 = GetLastError();
          v11 = "AddAccessAllowedAce() failed, err=%u";
        }
      }
      else
      {
        v10 = GetLastError();
        v11 = "InitializeAcl() failed, err=%u";
      }
    }
    else
    {
      v10 = GetLastError();
      v11 = "InitializeSid() failed, err=%u";
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = "GetSidLengthRequired() failed, err=%u";
  }
  LastError = v10;
  TRACELogPrint(65538, v11, v10);
LABEL_21:
  *a2 = v9;
  result = LastError;
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x18002b064  mov     [rsp+arg_18], rbx
0x18002b069  push    rbp
0x18002b06a  push    rsi
0x18002b06b  push    rdi
0x18002b06c  push    r14
0x18002b06e  push    r15
0x18002b070  sub     rsp, 30h
0x18002b074  mov     rax, cs:__security_cookie
0x18002b07b  xor     rax, rsp
0x18002b07e  mov     [rsp+58h+var_30], rax
0x18002b083  mov     rbx, rcx
0x18002b086  mov     word ptr [rsp+58h+pIdentifierAuthority.Value+4], 100h
0x18002b08d  xor     edi, edi
0x18002b08f  mov     cl, 1; nSubAuthorityCount
0x18002b091  mov     dword ptr [rsp+58h+pIdentifierAuthority.Value], edi
0x18002b095  mov     r15, r8
0x18002b098  mov     r14, rdx
0x18002b09b  call    cs:__imp_GetSidLengthRequired
0x18002b0a1  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002b0a8  lea     edx, [rdi+8]; dwFlags
0x18002b0ab  mov     r8d, eax; dwBytes
0x18002b0ae  call    cs:__imp_HeapAlloc
0x18002b0b4  mov     rsi, rax
0x18002b0b7  test    rax, rax
0x18002b0ba  jnz     short loc_18002B0DD
0x18002b0bc  call    cs:__imp_GetLastError
0x18002b0c2  lea     rdx, aGetsidlengthre_0; "GetSidLengthRequired() failed, err=%u"
0x18002b0c9  mov     r8d, eax
0x18002b0cc  mov     ecx, 10002h
0x18002b0d1  mov     ebx, eax
0x18002b0d3  call    TRACELogPrint
0x18002b0d8  jmp     loc_18002B22F
0x18002b0dd  mov     r8b, 1; nSubAuthorityCount
0x18002b0e0  lea     rdx, [rsp+58h+pIdentifierAuthority]; pIdentifierAuthority
0x18002b0e5  mov     rcx, rsi; Sid
0x18002b0e8  call    cs:__imp_InitializeSid
0x18002b0ee  test    eax, eax
0x18002b0f0  jnz     short loc_18002B101
0x18002b0f2  call    cs:__imp_GetLastError
0x18002b0f8  lea     rdx, aInitializesidF; "InitializeSid() failed, err=%u"
0x18002b0ff  jmp     short loc_18002B0C9
0x18002b101  xor     edx, edx; nSubAuthority
0x18002b103  mov     rcx, rsi; pSid
0x18002b106  call    cs:__imp_GetSidSubAuthority
0x18002b10c  mov     rcx, rsi; pSid
0x18002b10f  mov     [rax], edi
0x18002b111  call    cs:__imp_GetLengthSid
0x18002b117  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002b11e  mov     edx, 8; dwFlags
0x18002b123  lea     ebp, [rax+14h]
0x18002b126  mov     r8d, ebp; dwBytes
0x18002b129  call    cs:__imp_HeapAlloc
0x18002b12f  mov     rdi, rax
0x18002b132  test    rax, rax
0x18002b135  jnz     short loc_18002B144
0x18002b137  call    cs:__imp_GetLastError
0x18002b13d  mov     ebx, eax
0x18002b13f  jmp     loc_18002B22F
0x18002b144  mov     r8d, 2; dwAclRevision
0x18002b14a  mov     edx, ebp; nAclLength
0x18002b14c  mov     rcx, rdi; pAcl
0x18002b14f  call    cs:__imp_InitializeAcl
0x18002b155  test    eax, eax
0x18002b157  jnz     short loc_18002B16B
0x18002b159  call    cs:__imp_GetLastError
0x18002b15f  lea     rdx, aInitializeaclF; "InitializeAcl() failed, err=%u"
0x18002b166  jmp     loc_18002B0C9
0x18002b16b  mov     r9, rsi; pSid
0x18002b16e  mov     edx, 2; dwAceRevision
0x18002b173  mov     r8d, 1FFFFFh; AccessMask
0x18002b179  mov     rcx, rdi; pAcl
0x18002b17c  call    cs:__imp_AddAccessAllowedAce
0x18002b182  test    eax, eax
0x18002b184  jnz     short loc_18002B198
0x18002b186  call    cs:__imp_GetLastError
0x18002b18c  lea     rdx, aAddaccessallow_0; "AddAccessAllowedAce() failed, err=%u"
0x18002b193  jmp     loc_18002B0C9
0x18002b198  mov     edx, 1; dwRevision
0x18002b19d  mov     rcx, rbx; pSecurityDescriptor
0x18002b1a0  call    cs:__imp_InitializeSecurityDescriptor
0x18002b1a6  test    eax, eax
0x18002b1a8  jnz     short loc_18002B1BC
0x18002b1aa  call    cs:__imp_GetLastError
0x18002b1b0  lea     rdx, aInitializesecu_0; "InitializeSecurityDescriptor() failed, "...
0x18002b1b7  jmp     loc_18002B0C9
0x18002b1bc  xor     r9d, r9d; bDaclDefaulted
0x18002b1bf  mov     r8, rdi; pDacl
0x18002b1c2  mov     rcx, rbx; pSecurityDescriptor
0x18002b1c5  lea     edx, [r9+1]; bDaclPresent
0x18002b1c9  call    cs:__imp_SetSecurityDescriptorDacl
0x18002b1cf  test    eax, eax
0x18002b1d1  jnz     short loc_18002B1E5
0x18002b1d3  call    cs:__imp_GetLastError
0x18002b1d9  lea     rdx, aSetsecuritydes_3; "SetSecurityDescriptorDacl() failed, err"...
0x18002b1e0  jmp     loc_18002B0C9
0x18002b1e5  xor     r8d, r8d; bOwnerDefaulted
0x18002b1e8  xor     edx, edx; pOwner
0x18002b1ea  mov     rcx, rbx; pSecurityDescriptor
0x18002b1ed  call    cs:__imp_SetSecurityDescriptorOwner
0x18002b1f3  test    eax, eax
0x18002b1f5  jnz     short loc_18002B209
0x18002b1f7  call    cs:__imp_GetLastError
0x18002b1fd  lea     rdx, aSetsecuritydes_2; "SetSecurityDescriptorOwnr() failed, err"...
0x18002b204  jmp     loc_18002B0C9
0x18002b209  xor     r8d, r8d; bGroupDefaulted
0x18002b20c  xor     edx, edx; pGroup
0x18002b20e  mov     rcx, rbx; pSecurityDescriptor
0x18002b211  call    cs:__imp_SetSecurityDescriptorGroup
0x18002b217  test    eax, eax
0x18002b219  jnz     short loc_18002B22D
0x18002b21b  call    cs:__imp_GetLastError
0x18002b221  lea     rdx, aSetsecuritydes_4; "SetSecurityDescriptorGroup() failed, er"...
0x18002b228  jmp     loc_18002B0C9
0x18002b22d  xor     ebx, ebx
0x18002b22f  mov     [r14], rsi
0x18002b232  mov     eax, ebx
0x18002b234  mov     [r15], rdi
0x18002b237  mov     rcx, [rsp+58h+var_30]
0x18002b23c  xor     rcx, rsp; StackCookie
0x18002b23f  call    __security_check_cookie
0x18002b244  mov     rbx, [rsp+58h+arg_18]
0x18002b249  add     rsp, 30h
0x18002b24d  pop     r15
0x18002b24f  pop     r14
0x18002b251  pop     rdi
0x18002b252  pop     rsi
0x18002b253  pop     rbp
0x18002b254  retn
```
