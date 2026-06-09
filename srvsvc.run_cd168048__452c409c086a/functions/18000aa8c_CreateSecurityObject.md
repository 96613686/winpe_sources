# CreateSecurityObject

- ea: `0x18000aa8c`
- end: `0x18000ad53`
- name: `CreateSecurityObject`
- size: `711`
- prototype: ``
- caller_count: `8`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a994`
- `0x1800271c4`
- `0x1800273c0`
- `0x18002747c`
- `0x180027504`
- `0x1800275a0`
- `0x180027ec0`
- `0x1800284b4`

## callees

- `0x18000aa8c`
- `0x18000ae90`
- `0x18001d9ac`
- `0x1800215e8`
- `0x1800259f0`
- `0x180026768`
- `0x180026fd4`
- `0x180027f60`
- `0x18002801c`
- `0x18002842c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000ab01`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000abce`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000ab01`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000abce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac1d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000aca4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000aca4`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18000ac85`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18000ac90`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18000ac85`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18000ac90`

## pseudocode

```c
__int64 __fastcall CreateSecurityObject(
        const WCHAR **a1,
        const WCHAR *a2,
        struct _GENERIC_MAPPING *a3,
        int a4,
        int a5,
        char a6,
        unsigned int a7)
{
  bool v7; // zf
  PSECURITY_DESCRIPTOR *NewDescriptor; // rdi
  PSECURITY_DESCRIPTOR v12; // rcx
  __int64 v13; // rcx
  NTSTATUS v14; // ecx
  PSECURITY_DESCRIPTOR v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int SecurityObject; // ebx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-8h] BYREF
  WINBOOL bDaclPresent; // [rsp+80h] [rbp+30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+88h] [rbp+38h] BYREF
  PACL pDacl; // [rsp+90h] [rbp+40h] BYREF

  v7 = (_BYTE)a7 == 0;
  NewDescriptor = (PSECURITY_DESCRIPTOR *)(a1 + 2);
  *a1 = a2;
  a1[1] = (const WCHAR *)a3;
  if ( !v7 || !(unsigned __int8)SsGetDefaultSdFromRegistry(a2, a1 + 2) )
  {
    SecurityObject = NetpCreateSecurityObject(
                       a4,
                       a5,
                       *(_QWORD *)(qword_18005CDC0 + 32),
                       *(_QWORD *)(qword_18005CDC0 + 32),
                       a3,
                       NewDescriptor);
    if ( SecurityObject < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids,
          (_DWORD)a2,
          SecurityObject);
      }
      v14 = SecurityObject;
      return NetpNtStatusToApiStatus(v14);
    }
    SsWriteDefaultSdToRegistry(a2, *NewDescriptor);
    return 0;
  }
  if ( !a6 )
    goto LABEL_17;
  v12 = *NewDescriptor;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  a7 = 0;
  if ( !GetSecurityDescriptorDacl(v12, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    return 1336;
  if ( !bDaclPresent
    || !(unsigned __int8)DoesAclContainSid(pDacl, *(PSID *)(qword_18005CDC0 + 64))
    && !(unsigned __int8)DoesAclContainSid(pDacl, *(PSID *)(qword_18005CDC0 + 8))
    || SsRestrictNullSessions )
  {
LABEL_17:
    v24[0] = a2;
    v24[1] = a3;
    SecurityDescriptor = 0;
    v17 = NetpCreateSecurityObject(
            a4,
            a5,
            *(_QWORD *)(qword_18005CDC0 + 32),
            *(_QWORD *)(qword_18005CDC0 + 32),
            a3,
            &SecurityDescriptor);
    if ( v17 < 0 )
    {
      v14 = v17;
      return NetpNtStatusToApiStatus(v14);
    }
    v19 = RtlLengthSecurityDescriptor(SecurityDescriptor);
    if ( ((_DWORD)v19 != RtlLengthSecurityDescriptor(*NewDescriptor)
       || RtlCompareMemory(SecurityDescriptor, *NewDescriptor, (unsigned int)v19) != v19)
      && (byte_18005FE19 & 0x40) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v21, v20, a2);
    }
    DeleteSecurityObject(v24);
    return 0;
  }
  pSecurityDescriptor = 0;
  if ( (unsigned __int8)DoesAclContainSid(pDacl, *(PSID *)(qword_18005CDC0 + 8)) )
  {
LABEL_13:
    if ( !(unsigned __int8)DoesAclContainSid(pDacl, *(PSID *)(qword_18005CDC0 + 72)) )
    {
      if ( !(unsigned __int8)AppendAllowedAceToSelfRelativeSD(
                               v16,
                               a7,
                               *(_QWORD *)(qword_18005CDC0 + 72),
                               *NewDescriptor,
                               &pSecurityDescriptor) )
        goto LABEL_11;
      LocalFree(*NewDescriptor);
      *NewDescriptor = pSecurityDescriptor;
    }
    SsWriteDefaultSdToRegistry(a2, *NewDescriptor);
    goto LABEL_17;
  }
  if ( (unsigned __int8)AppendAllowedAceToSelfRelativeSD(
                          v13,
                          a7,
                          *(_QWORD *)(qword_18005CDC0 + 8),
                          *NewDescriptor,
                          &pSecurityDescriptor) )
  {
    LocalFree(*NewDescriptor);
    v15 = pSecurityDescriptor;
    *NewDescriptor = pSecurityDescriptor;
    if ( GetSecurityDescriptorDacl(v15, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      goto LABEL_13;
    return 1336;
  }
LABEL_11:
  v14 = -1073741703;
  return NetpNtStatusToApiStatus(v14);
}

```

## disassembly

```asm
0x18000aa8c  push    rbp
0x18000aa8e  push    rbx
0x18000aa8f  push    rsi
0x18000aa90  push    rdi
0x18000aa91  push    r14
0x18000aa93  mov     rbp, rsp
0x18000aa96  sub     rsp, 50h
0x18000aa9a  cmp     byte ptr [rbp+arg_30], 0
0x18000aa9e  lea     rdi, [rcx+10h]
0x18000aaa2  mov     rbx, r8
0x18000aaa5  mov     [rcx], rdx
0x18000aaa8  mov     [rcx+8], rbx
0x18000aaac  mov     r14, r9
0x18000aaaf  mov     rsi, rdx
0x18000aab2  jnz     loc_18000ACCB
0x18000aab8  mov     rdx, rdi
0x18000aabb  mov     rcx, rsi
0x18000aabe  call    SsGetDefaultSdFromRegistry
0x18000aac3  test    al, al
0x18000aac5  jz      loc_18000ACCB
0x18000aacb  cmp     [rbp+arg_28], 0
0x18000aacf  jz      loc_18000AC35
0x18000aad5  mov     rcx, [rdi]; pSecurityDescriptor
0x18000aad8  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18000aadc  lea     r8, [rbp+pDacl]; pDacl
0x18000aae0  mov     [rbp+pDacl], 0
0x18000aae8  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000aaec  mov     [rbp+bDaclPresent], 0
0x18000aaf3  mov     [rbp+bDaclDefaulted], 0
0x18000aafa  mov     [rbp+arg_30], 0
0x18000ab01  call    cs:__imp_GetSecurityDescriptorDacl
0x18000ab07  test    eax, eax
0x18000ab09  jz      loc_18000AC77
0x18000ab0f  cmp     [rbp+bDaclPresent], 0
0x18000ab13  jz      loc_18000AC35
0x18000ab19  mov     rdx, cs:qword_18005CDC0
0x18000ab20  lea     r8, [rbp+arg_30]
0x18000ab24  mov     rcx, [rbp+pDacl]; pAcl
0x18000ab28  mov     rdx, [rdx+40h]; pSid2
0x18000ab2c  call    DoesAclContainSid
0x18000ab31  test    al, al
0x18000ab33  jnz     short loc_18000AB55
0x18000ab35  mov     rdx, cs:qword_18005CDC0
0x18000ab3c  lea     r8, [rbp+arg_30]
0x18000ab40  mov     rcx, [rbp+pDacl]; pAcl
0x18000ab44  mov     rdx, [rdx+8]; pSid2
0x18000ab48  call    DoesAclContainSid
0x18000ab4d  test    al, al
0x18000ab4f  jz      loc_18000AC35
0x18000ab55  cmp     cs:SsRestrictNullSessions, 0
0x18000ab5c  jnz     loc_18000AC35
0x18000ab62  mov     rdx, cs:qword_18005CDC0
0x18000ab69  xor     r8d, r8d
0x18000ab6c  mov     rcx, [rbp+pDacl]; pAcl
0x18000ab70  mov     [rbp+pSecurityDescriptor], 0
0x18000ab78  mov     rdx, [rdx+8]; pSid2
0x18000ab7c  call    DoesAclContainSid
0x18000ab81  test    al, al
0x18000ab83  jnz     short loc_18000ABDC
0x18000ab85  mov     r8, cs:qword_18005CDC0
0x18000ab8c  lea     rax, [rbp+pSecurityDescriptor]
0x18000ab90  mov     r9, [rdi]
0x18000ab93  mov     edx, [rbp+arg_30]
0x18000ab96  mov     [rsp+50h+var_30], rax
0x18000ab9b  mov     r8, [r8+8]
0x18000ab9f  call    AppendAllowedAceToSelfRelativeSD
0x18000aba4  test    al, al
0x18000aba6  jnz     short loc_18000ABB2
0x18000aba8  mov     ecx, 0C0000079h
0x18000abad  jmp     loc_18000AD43
0x18000abb2  mov     rcx, [rdi]; hMem
0x18000abb5  call    cs:__imp_LocalFree
0x18000abbb  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000abbf  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18000abc3  lea     r8, [rbp+pDacl]; pDacl
0x18000abc7  mov     [rdi], rcx
0x18000abca  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000abce  call    cs:__imp_GetSecurityDescriptorDacl
0x18000abd4  test    eax, eax
0x18000abd6  jz      loc_18000AC77
0x18000abdc  mov     rdx, cs:qword_18005CDC0
0x18000abe3  xor     r8d, r8d
0x18000abe6  mov     rcx, [rbp+pDacl]; pAcl
0x18000abea  mov     rdx, [rdx+48h]; pSid2
0x18000abee  call    DoesAclContainSid
0x18000abf3  test    al, al
0x18000abf5  jnz     short loc_18000AC2A
0x18000abf7  mov     r8, cs:qword_18005CDC0
0x18000abfe  lea     rax, [rbp+pSecurityDescriptor]
0x18000ac02  mov     r9, [rdi]
0x18000ac05  mov     edx, [rbp+arg_30]
0x18000ac08  mov     [rsp+50h+var_30], rax
0x18000ac0d  mov     r8, [r8+48h]
0x18000ac11  call    AppendAllowedAceToSelfRelativeSD
0x18000ac16  test    al, al
0x18000ac18  jz      short loc_18000ABA8
0x18000ac1a  mov     rcx, [rdi]; hMem
0x18000ac1d  call    cs:__imp_LocalFree
0x18000ac23  mov     rax, [rbp+pSecurityDescriptor]
0x18000ac27  mov     [rdi], rax
0x18000ac2a  mov     rdx, [rdi]; ValueData
0x18000ac2d  mov     rcx, rsi; ValueName
0x18000ac30  call    SsWriteDefaultSdToRegistry
0x18000ac35  mov     rax, cs:qword_18005CDC0
0x18000ac3c  mov     rcx, r14; int
0x18000ac3f  mov     edx, [rbp+arg_20]; int
0x18000ac42  mov     [rbp+var_18], rsi
0x18000ac46  mov     [rbp+var_10], rbx
0x18000ac4a  mov     [rbp+SecurityDescriptor], 0
0x18000ac52  mov     r8, [rax+20h]; int
0x18000ac56  lea     rax, [rbp+SecurityDescriptor]
0x18000ac5a  mov     [rsp+50h+NewDescriptor], rax; NewDescriptor
0x18000ac5f  mov     r9, r8; int
0x18000ac62  mov     [rsp+50h+var_30], rbx; PGENERIC_MAPPING
0x18000ac67  call    NetpCreateSecurityObject
0x18000ac6c  test    eax, eax
0x18000ac6e  jns     short loc_18000AC81
0x18000ac70  mov     ecx, eax
0x18000ac72  jmp     loc_18000AD43
0x18000ac77  mov     eax, 538h
0x18000ac7c  jmp     loc_18000AD48
0x18000ac81  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000ac85  call    cs:__imp_RtlLengthSecurityDescriptor
0x18000ac8b  mov     rcx, [rdi]; SecurityDescriptor
0x18000ac8e  mov     ebx, eax
0x18000ac90  call    cs:__imp_RtlLengthSecurityDescriptor
0x18000ac96  cmp     ebx, eax
0x18000ac98  jnz     short loc_18000ACAF
0x18000ac9a  mov     rdx, [rdi]; Source2
0x18000ac9d  mov     r8d, ebx; Length
0x18000aca0  mov     rcx, [rbp+SecurityDescriptor]; Source1
0x18000aca4  call    cs:__imp_RtlCompareMemory
0x18000acaa  cmp     rax, rbx
0x18000acad  jz      short loc_18000ACC0
0x18000acaf  test    cs:byte_18005FE19, 40h
0x18000acb6  jz      short loc_18000ACC0
0x18000acb8  mov     r8, rsi
0x18000acbb  call    McTemplateU0z_EventWriteTransfer
0x18000acc0  lea     rcx, [rbp+var_18]
0x18000acc4  call    DeleteSecurityObject
0x18000acc9  jmp     short loc_18000ACFF
0x18000accb  mov     rax, cs:qword_18005CDC0
0x18000acd2  mov     rcx, r14; int
0x18000acd5  mov     edx, [rbp+arg_20]; int
0x18000acd8  mov     [rsp+50h+NewDescriptor], rdi; NewDescriptor
0x18000acdd  mov     [rsp+50h+var_30], rbx; PGENERIC_MAPPING
0x18000ace2  mov     r8, [rax+20h]; int
0x18000ace6  mov     r9, r8; int
0x18000ace9  call    NetpCreateSecurityObject
0x18000acee  mov     ebx, eax
0x18000acf0  test    eax, eax
0x18000acf2  js      short loc_18000AD03
0x18000acf4  mov     rdx, [rdi]; ValueData
0x18000acf7  mov     rcx, rsi; ValueName
0x18000acfa  call    SsWriteDefaultSdToRegistry
0x18000acff  xor     eax, eax
0x18000ad01  jmp     short loc_18000AD48
0x18000ad03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad0a  lea     rax, WPP_GLOBAL_Control
0x18000ad11  cmp     rcx, rax
0x18000ad14  jz      short loc_18000AD41
0x18000ad16  test    dword ptr [rcx+1Ch], 200h
0x18000ad1d  jz      short loc_18000AD41
0x18000ad1f  cmp     byte ptr [rcx+19h], 1
0x18000ad23  jb      short loc_18000AD41
0x18000ad25  mov     rcx, [rcx+10h]
0x18000ad29  lea     r8, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids
0x18000ad30  mov     edx, 0Bh
0x18000ad35  mov     dword ptr [rsp+50h+var_30], ebx
0x18000ad39  mov     r9, rsi
0x18000ad3c  call    WPP_SF_Sd
0x18000ad41  mov     ecx, ebx; Status
0x18000ad43  call    NetpNtStatusToApiStatus
0x18000ad48  add     rsp, 50h
0x18000ad4c  pop     r14
0x18000ad4e  pop     rdi
0x18000ad4f  pop     rsi
0x18000ad50  pop     rbx
0x18000ad51  pop     rbp
0x18000ad52  retn
```
