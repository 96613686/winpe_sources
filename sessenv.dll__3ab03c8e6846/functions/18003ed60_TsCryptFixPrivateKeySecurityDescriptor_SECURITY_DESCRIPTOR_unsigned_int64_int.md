# TsCryptFixPrivateKeySecurityDescriptor(_SECURITY_DESCRIPTOR *,unsigned __int64,int *)

- ea: `0x18003ed60`
- end: `0x18003ee7c`
- name: `?TsCryptFixPrivateKeySecurityDescriptor@@YAHPEAU_SECURITY_DESCRIPTOR@@_KPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(PBYTE pbInput, NCRYPT_HANDLE hObject, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f2e0`

## callees

- `0x18001a280`
- `0x18003ed60`
- `0x18003ee84`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003edf3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003edf3`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18003ee0d`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18003ee0d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003edd9`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003edd9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18003edab`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18003edab`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003ee29`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003ee29`
- `ncrypt!NCryptSetProperty` at `0x18003ee47`
- `ncrypt!NCryptSetProperty` at `0x18003ee47`

## string_xrefs

- `0x18003ee3d`: `Security Descr`

## pseudocode

```c
__int64 __fastcall TsCryptFixPrivateKeySecurityDescriptor(
        struct _SECURITY_DESCRIPTOR *pbInput,
        NCRYPT_HANDLE hObject,
        DWORD *a3)
{
  DWORD v3; // ebx
  struct _ACL *Dacl; // rsi
  unsigned int v8; // edi
  DWORD SecurityDescriptorLength; // eax
  LPVOID pAce; // [rsp+30h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-40h] BYREF
  int v13; // [rsp+40h] [rbp-38h]

  v3 = 0;
  *a3 = 0;
  Dacl = TsCryptGetDacl(pbInput);
  if ( !Dacl )
    goto LABEL_11;
  v8 = 0;
  if ( SetSecurityDescriptorControl(pbInput, 0x1000u, 0x1000u) )
  {
    pAclInformation = 0;
    v13 = 0;
    pAce = 0;
    if ( GetAclInformation(Dacl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      while ( v3 < (unsigned int)pAclInformation )
      {
        if ( !GetAce(Dacl, v3, &pAce) )
          return v8;
        if ( (*((_BYTE *)pAce + 1) & 0x10) != 0 )
        {
          if ( !DeleteAce(Dacl, v3) )
            return v8;
          --v3;
          LODWORD(pAclInformation) = pAclInformation - 1;
        }
        ++v3;
      }
      v3 = 1;
      SecurityDescriptorLength = GetSecurityDescriptorLength(pbInput);
      if ( NCryptSetProperty(hObject, L"Security Descr", &pbInput->Revision, SecurityDescriptorLength, 4u) >= 0 )
      {
LABEL_11:
        *a3 = v3;
        return 1;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18003ed60  mov     [rsp+arg_18], rbx
0x18003ed65  push    rbp
0x18003ed66  push    rsi
0x18003ed67  push    rdi
0x18003ed68  push    r14
0x18003ed6a  push    r15
0x18003ed6c  sub     rsp, 50h
0x18003ed70  mov     rax, cs:__security_cookie
0x18003ed77  xor     rax, rsp
0x18003ed7a  mov     [rsp+78h+var_30], rax
0x18003ed7f  xor     ebx, ebx
0x18003ed81  mov     r14, r8
0x18003ed84  mov     [r8], ebx
0x18003ed87  mov     r15, rdx
0x18003ed8a  mov     rbp, rcx
0x18003ed8d  call    ?TsCryptGetDacl@@YAPEAU_ACL@@PEAU_SECURITY_DESCRIPTOR@@@Z; TsCryptGetDacl(_SECURITY_DESCRIPTOR *)
0x18003ed92  mov     rsi, rax
0x18003ed95  test    rax, rax
0x18003ed98  jz      loc_18003EE51
0x18003ed9e  mov     edx, 1000h; ControlBitsOfInterest
0x18003eda3  mov     rcx, rbp; pSecurityDescriptor
0x18003eda6  mov     r8d, edx; ControlBitsToSet
0x18003eda9  xor     edi, edi
0x18003edab  call    cs:__imp_SetSecurityDescriptorControl
0x18003edb1  test    eax, eax
0x18003edb3  jz      loc_18003EE59
0x18003edb9  xor     eax, eax
0x18003edbb  lea     r9d, [rbx+2]; dwAclInformationClass
0x18003edbf  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x18003edc3  mov     [rsp+78h+pAclInformation], rax
0x18003edc8  lea     rdx, [rsp+78h+pAclInformation]; pAclInformation
0x18003edcd  mov     [rsp+78h+var_38], eax
0x18003edd1  mov     rcx, rsi; pAcl
0x18003edd4  mov     [rsp+78h+pAce], rax
0x18003edd9  call    cs:__imp_GetAclInformation
0x18003eddf  test    eax, eax
0x18003ede1  jz      short loc_18003EE59
0x18003ede3  cmp     ebx, dword ptr [rsp+78h+pAclInformation]
0x18003ede7  jnb     short loc_18003EE21
0x18003ede9  lea     r8, [rsp+78h+pAce]; pAce
0x18003edee  mov     edx, ebx; dwAceIndex
0x18003edf0  mov     rcx, rsi; pAcl
0x18003edf3  call    cs:__imp_GetAce
0x18003edf9  test    eax, eax
0x18003edfb  jz      short loc_18003EE59
0x18003edfd  mov     rax, [rsp+78h+pAce]
0x18003ee02  test    byte ptr [rax+1], 10h
0x18003ee06  jz      short loc_18003EE1D
0x18003ee08  mov     edx, ebx; dwAceIndex
0x18003ee0a  mov     rcx, rsi; pAcl
0x18003ee0d  call    cs:__imp_DeleteAce
0x18003ee13  test    eax, eax
0x18003ee15  jz      short loc_18003EE59
0x18003ee17  dec     ebx
0x18003ee19  dec     dword ptr [rsp+78h+pAclInformation]
0x18003ee1d  inc     ebx
0x18003ee1f  jmp     short loc_18003EDE3
0x18003ee21  mov     rcx, rbp; pSecurityDescriptor
0x18003ee24  mov     ebx, 1
0x18003ee29  call    cs:__imp_GetSecurityDescriptorLength
0x18003ee2f  mov     r8, rbp; pbInput
0x18003ee32  mov     [rsp+78h+dwFlags], 4; dwFlags
0x18003ee3a  mov     r9d, eax; cbInput
0x18003ee3d  lea     rdx, pszProperty; "Security Descr"
0x18003ee44  mov     rcx, r15; hObject
0x18003ee47  call    cs:__imp_NCryptSetProperty
0x18003ee4d  test    eax, eax
0x18003ee4f  js      short loc_18003EE59
0x18003ee51  mov     [r14], ebx
0x18003ee54  mov     edi, 1
0x18003ee59  mov     eax, edi
0x18003ee5b  mov     rcx, [rsp+78h+var_30]
0x18003ee60  xor     rcx, rsp; StackCookie
0x18003ee63  call    __security_check_cookie
0x18003ee68  mov     rbx, [rsp+78h+arg_18]
0x18003ee70  add     rsp, 50h
0x18003ee74  pop     r15
0x18003ee76  pop     r14
0x18003ee78  pop     rdi
0x18003ee79  pop     rsi
0x18003ee7a  pop     rbp
0x18003ee7b  retn
```
