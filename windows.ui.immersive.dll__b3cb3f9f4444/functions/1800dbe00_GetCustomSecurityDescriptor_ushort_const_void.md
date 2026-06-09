# GetCustomSecurityDescriptor(ushort const *,void *)

- ea: `0x1800dbe00`
- end: `0x1800dbfbe`
- name: `?GetCustomSecurityDescriptor@@YAJPEBGPEAX@Z`
- size: `446`
- prototype: `int(const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005021c`
- `0x1800dba30`

## callees

- `0x18003d244`
- `0x180059b4c`
- `0x1800db88c`
- `0x1800dbbf8`
- `0x1800dbe00`
- `0x1800dc6fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbf86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbf9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbf86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbf9e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800dbf63`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800dbf63`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800dbf3d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800dbf3d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800dbf14`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800dbf14`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800dbe6e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800dbe6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800dbe29`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800dbe29`

## pseudocode

```c
__int64 __fastcall GetCustomSecurityDescriptor(const unsigned __int16 *a1, void *a2)
{
  int Error; // ebx
  PSECURITY_DESCRIPTOR v4; // r14
  struct _ACL *v5; // r15
  CAceList *v6; // rax
  int v7; // r9d
  CAceList *v8; // rdi
  void *v9; // rdx
  CAceList *v10; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-20h] BYREF
  PACL v13; // [rsp+28h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-10h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+80h] [rbp+40h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp+48h] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, &SecurityDescriptor, 0)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    pDacl = 0;
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_18;
    }
    v4 = SecurityDescriptor;
    v5 = pDacl;
    Error = -2147024882;
    v6 = (CAceList *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v6;
    if ( !v6 )
      goto LABEL_18;
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 1;
    Error = CAceList::_InitFromAclAndSD(v6, v5, v4, v7);
    v10 = v8;
    if ( Error < 0 )
    {
LABEL_17:
      CAceList::`scalar deleting destructor'(v10, (unsigned int)v9);
LABEL_18:
      LocalFree(SecurityDescriptor);
      return (unsigned int)Error;
    }
    v13 = 0;
    Error = CAceList::GetAclForExplicitEntries(v8, v9, &v13);
    if ( Error >= 0 )
    {
      if ( InitializeSecurityDescriptor(a2, 1u) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        if ( SetSecurityDescriptorDacl(a2, 1, v13, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          if ( SetSecurityDescriptorControl(a2, 0x1000u, 0x1000u) )
          {
            Error = 0;
            goto LABEL_16;
          }
          Error = ResultFromKnownLastError();
          if ( Error >= 0 )
            goto LABEL_16;
        }
      }
      LocalFree(v13);
    }
LABEL_16:
    v10 = v8;
    goto LABEL_17;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800dbe00  mov     [rsp-28h+arg_0], rbx
0x1800dbe05  push    rbp
0x1800dbe06  push    rsi
0x1800dbe07  push    rdi
0x1800dbe08  push    r14
0x1800dbe0a  push    r15
0x1800dbe0c  mov     rbp, rsp
0x1800dbe0f  sub     rsp, 40h
0x1800dbe13  xor     r9d, r9d; SecurityDescriptorSize
0x1800dbe16  mov     [rbp+SecurityDescriptor], 0
0x1800dbe1e  mov     rsi, rdx
0x1800dbe21  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800dbe25  lea     edx, [r9+1]; StringSDRevision
0x1800dbe29  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800dbe30  nop     dword ptr [rax+rax+00h]
0x1800dbe35  test    eax, eax
0x1800dbe37  jnz     short loc_1800DBE48
0x1800dbe39  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dbe3e  mov     ebx, eax
0x1800dbe40  test    eax, eax
0x1800dbe42  js      loc_1800DBFAA
0x1800dbe48  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800dbe4c  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800dbe50  lea     r8, [rbp+pDacl]; pDacl
0x1800dbe54  mov     [rbp+pDacl], 0
0x1800dbe5c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800dbe60  mov     [rbp+bDaclDefaulted], 0
0x1800dbe67  mov     [rbp+bDaclPresent], 0
0x1800dbe6e  call    cs:__imp_GetSecurityDescriptorDacl
0x1800dbe75  nop     dword ptr [rax+rax+00h]
0x1800dbe7a  test    eax, eax
0x1800dbe7c  jnz     short loc_1800DBE8D
0x1800dbe7e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dbe83  mov     ebx, eax
0x1800dbe85  test    eax, eax
0x1800dbe87  js      loc_1800DBF9A
0x1800dbe8d  mov     r14, [rbp+SecurityDescriptor]
0x1800dbe91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800dbe98  mov     r15, [rbp+pDacl]
0x1800dbe9c  mov     ecx, 20h ; ' '; unsigned __int64
0x1800dbea1  mov     ebx, 8007000Eh
0x1800dbea6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800dbeab  mov     rdi, rax
0x1800dbeae  test    rax, rax
0x1800dbeb1  jz      loc_1800DBF9A
0x1800dbeb7  mov     qword ptr [rax], 0
0x1800dbebe  mov     r8, r14; void *
0x1800dbec1  mov     qword ptr [rax+8], 0
0x1800dbec9  mov     rdx, r15; struct _ACL *
0x1800dbecc  mov     qword ptr [rax+10h], 0
0x1800dbed4  mov     rcx, rax; this
0x1800dbed7  mov     qword ptr [rax+18h], 1
0x1800dbedf  call    ?_InitFromAclAndSD@CAceList@@AEAAJPEAU_ACL@@PEAXH@Z; CAceList::_InitFromAclAndSD(_ACL *,void *,int)
0x1800dbee4  mov     ebx, eax
0x1800dbee6  mov     rcx, rdi; this
0x1800dbee9  test    eax, eax
0x1800dbeeb  js      loc_1800DBF95
0x1800dbef1  lea     r8, [rbp+var_18]; struct _ACL **
0x1800dbef5  mov     [rbp+var_18], 0
0x1800dbefd  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x1800dbf02  mov     ebx, eax
0x1800dbf04  test    eax, eax
0x1800dbf06  js      loc_1800DBF92
0x1800dbf0c  mov     edx, 1; dwRevision
0x1800dbf11  mov     rcx, rsi; pSecurityDescriptor
0x1800dbf14  call    cs:__imp_InitializeSecurityDescriptor
0x1800dbf1b  nop     dword ptr [rax+rax+00h]
0x1800dbf20  test    eax, eax
0x1800dbf22  jnz     short loc_1800DBF2F
0x1800dbf24  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dbf29  mov     ebx, eax
0x1800dbf2b  test    eax, eax
0x1800dbf2d  js      short loc_1800DBF82
0x1800dbf2f  mov     r8, [rbp+var_18]; pDacl
0x1800dbf33  xor     r9d, r9d; bDaclDefaulted
0x1800dbf36  mov     rcx, rsi; pSecurityDescriptor
0x1800dbf39  lea     edx, [r9+1]; bDaclPresent
0x1800dbf3d  call    cs:__imp_SetSecurityDescriptorDacl
0x1800dbf44  nop     dword ptr [rax+rax+00h]
0x1800dbf49  test    eax, eax
0x1800dbf4b  jnz     short loc_1800DBF58
0x1800dbf4d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dbf52  mov     ebx, eax
0x1800dbf54  test    eax, eax
0x1800dbf56  js      short loc_1800DBF82
0x1800dbf58  mov     edx, 1000h; ControlBitsOfInterest
0x1800dbf5d  mov     rcx, rsi; pSecurityDescriptor
0x1800dbf60  mov     r8d, edx; ControlBitsToSet
0x1800dbf63  call    cs:__imp_SetSecurityDescriptorControl
0x1800dbf6a  nop     dword ptr [rax+rax+00h]
0x1800dbf6f  test    eax, eax
0x1800dbf71  jz      short loc_1800DBF77
0x1800dbf73  xor     ebx, ebx
0x1800dbf75  jmp     short loc_1800DBF92
0x1800dbf77  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dbf7c  mov     ebx, eax
0x1800dbf7e  test    eax, eax
0x1800dbf80  jns     short loc_1800DBF92
0x1800dbf82  mov     rcx, [rbp+var_18]; hMem
0x1800dbf86  call    cs:__imp_LocalFree
0x1800dbf8d  nop     dword ptr [rax+rax+00h]
0x1800dbf92  mov     rcx, rdi; this
0x1800dbf95  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x1800dbf9a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800dbf9e  call    cs:__imp_LocalFree
0x1800dbfa5  nop     dword ptr [rax+rax+00h]
0x1800dbfaa  mov     eax, ebx
0x1800dbfac  mov     rbx, [rsp+40h+arg_0]
0x1800dbfb1  add     rsp, 40h
0x1800dbfb5  pop     r15
0x1800dbfb7  pop     r14
0x1800dbfb9  pop     rdi
0x1800dbfba  pop     rsi
0x1800dbfbb  pop     rbp
0x1800dbfbc  retn
```
