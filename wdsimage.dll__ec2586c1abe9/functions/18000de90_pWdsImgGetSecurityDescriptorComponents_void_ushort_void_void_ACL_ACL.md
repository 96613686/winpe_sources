# pWdsImgGetSecurityDescriptorComponents(void *,ushort *,void * *,void * *,_ACL * *,_ACL * *)

- ea: `0x18000de90`
- end: `0x18000dfd4`
- name: `?pWdsImgGetSecurityDescriptorComponents@@YAJPEAXPEAGPEAPEAX2PEAPEAU_ACL@@3@Z`
- size: `324`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSecurityDescriptor@<rcx>, unsigned __int16 *@<rdx>, void **@<r8>, void **@<r9>, struct _ACL **, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dfdc`

## callees

- `0x18000de90`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18000df77`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18000df77`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18000df58`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18000df58`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18000df39`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18000df39`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18000df1e`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18000df1e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18000dede`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18000dede`
- `KERNEL32!GetLastError` at `0x18000deee`
- `KERNEL32!GetLastError` at `0x18000deee`

## pseudocode

```c
__int64 __fastcall pWdsImgGetSecurityDescriptorComponents(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        unsigned __int16 *a2,
        void **a3,
        void **a4,
        struct _ACL **a5,
        struct _ACL **a6)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  WORD pControl[2]; // [rsp+20h] [rbp-30h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+24h] [rbp-2Ch] BYREF
  WINBOOL bDaclPresent; // [rsp+28h] [rbp-28h] BYREF
  DWORD dwRevision; // [rsp+2Ch] [rbp-24h] BYREF
  PSID pOwner; // [rsp+30h] [rbp-20h] BYREF
  PSID pGroup; // [rsp+38h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-10h] BYREF
  PACL pSacl; // [rsp+48h] [rbp-8h] BYREF

  v6 = 0;
  dwRevision = 0;
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  pControl[0] = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  if ( GetSecurityDescriptorControl(pSecurityDescriptor, pControl, &dwRevision)
    && GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted)
    && GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bOwnerDefaulted)
    && GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted)
    && GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, &pSacl, &bOwnerDefaulted) )
  {
    *a2 = pControl[0];
    *a3 = pOwner;
    *a4 = pGroup;
    *a5 = pDacl;
    *a6 = pSacl;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    else
      return (unsigned int)LastError;
  }
  return v6;
}

```

## disassembly

```asm
0x18000de90  mov     [rsp-18h+arg_0], rbx
0x18000de95  mov     [rsp-18h+arg_8], rsi
0x18000de9a  mov     [rsp-18h+arg_10], rdi
0x18000de9f  push    rbp
0x18000dea0  push    r14
0x18000dea2  push    r15
0x18000dea4  mov     rbp, rsp
0x18000dea7  sub     rsp, 50h
0x18000deab  xor     ebx, ebx
0x18000dead  mov     r14, r8
0x18000deb0  mov     r15, rdx
0x18000deb3  mov     [rbp+dwRevision], ebx
0x18000deb6  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18000deba  mov     [rbp+bOwnerDefaulted], ebx
0x18000debd  lea     rdx, [rbp+pControl]; pControl
0x18000dec1  mov     [rbp+bDaclPresent], ebx
0x18000dec4  mov     [rbp+pControl], bx
0x18000dec8  mov     rsi, r9
0x18000decb  mov     [rbp+pOwner], rbx
0x18000decf  mov     rdi, rcx
0x18000ded2  mov     [rbp+pGroup], rbx
0x18000ded6  mov     [rbp+pDacl], rbx
0x18000deda  mov     [rbp+pSacl], rbx
0x18000dede  call    cs:__imp_GetSecurityDescriptorControl
0x18000dee5  nop     dword ptr [rax+rax+00h]
0x18000deea  test    eax, eax
0x18000deec  jnz     short loc_18000DF13
0x18000deee  call    cs:__imp_GetLastError
0x18000def5  nop     dword ptr [rax+rax+00h]
0x18000defa  test    eax, eax
0x18000defc  jg      short loc_18000DF05
0x18000defe  mov     ebx, eax
0x18000df00  jmp     loc_18000DFB7
0x18000df05  movzx   ebx, ax
0x18000df08  or      ebx, 80070000h
0x18000df0e  jmp     loc_18000DFB7
0x18000df13  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18000df17  mov     rcx, rdi; pSecurityDescriptor
0x18000df1a  lea     rdx, [rbp+pOwner]; pOwner
0x18000df1e  call    cs:__imp_GetSecurityDescriptorOwner
0x18000df25  nop     dword ptr [rax+rax+00h]
0x18000df2a  test    eax, eax
0x18000df2c  jz      short loc_18000DEEE
0x18000df2e  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18000df32  mov     rcx, rdi; pSecurityDescriptor
0x18000df35  lea     rdx, [rbp+pGroup]; pGroup
0x18000df39  call    cs:__imp_GetSecurityDescriptorGroup
0x18000df40  nop     dword ptr [rax+rax+00h]
0x18000df45  test    eax, eax
0x18000df47  jz      short loc_18000DEEE
0x18000df49  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18000df4d  mov     rcx, rdi; pSecurityDescriptor
0x18000df50  lea     r8, [rbp+pDacl]; pDacl
0x18000df54  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000df58  call    cs:__imp_GetSecurityDescriptorDacl
0x18000df5f  nop     dword ptr [rax+rax+00h]
0x18000df64  test    eax, eax
0x18000df66  jz      short loc_18000DEEE
0x18000df68  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18000df6c  mov     rcx, rdi; pSecurityDescriptor
0x18000df6f  lea     r8, [rbp+pSacl]; pSacl
0x18000df73  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18000df77  call    cs:__imp_GetSecurityDescriptorSacl
0x18000df7e  nop     dword ptr [rax+rax+00h]
0x18000df83  test    eax, eax
0x18000df85  jz      loc_18000DEEE
0x18000df8b  movzx   ecx, [rbp+pControl]
0x18000df8f  mov     rdx, [rbp+arg_20]
0x18000df93  mov     [r15], cx
0x18000df97  mov     rcx, [rbp+pOwner]
0x18000df9b  mov     [r14], rcx
0x18000df9e  mov     rcx, [rbp+pGroup]
0x18000dfa2  mov     [rsi], rcx
0x18000dfa5  mov     rcx, [rbp+pDacl]
0x18000dfa9  mov     [rdx], rcx
0x18000dfac  mov     rdx, [rbp+arg_28]
0x18000dfb0  mov     rcx, [rbp+pSacl]
0x18000dfb4  mov     [rdx], rcx
0x18000dfb7  lea     r11, [rsp+50h+var_s0]
0x18000dfbc  mov     eax, ebx
0x18000dfbe  mov     rbx, [r11+20h]
0x18000dfc2  mov     rsi, [r11+28h]
0x18000dfc6  mov     rdi, [r11+30h]
0x18000dfca  mov     rsp, r11
0x18000dfcd  pop     r15
0x18000dfcf  pop     r14
0x18000dfd1  pop     rbp
0x18000dfd2  retn
```
