# BuildPrivateDirectorySecurityDescriptor(ulong,void *,void *,ulong,void *)

- ea: `0x1800d4b2c`
- end: `0x1800d4e90`
- name: `?BuildPrivateDirectorySecurityDescriptor@@YAJKPEAX0K0@Z`
- size: `868`
- prototype: `int(unsigned int, void *, void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d5218`

## callees

- `0x18006f1c9`
- `0x1800d4b2c`
- `0x1800de450`

## import_xrefs

- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800d4bcb`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800d4bcb`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800d4bac`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800d4bac`
- `ntdll!RtlFreeSid` at `0x1800d4e52`
- `ntdll!RtlFreeSid` at `0x1800d4e61`
- `ntdll!RtlFreeSid` at `0x1800d4e52`
- `ntdll!RtlFreeSid` at `0x1800d4e61`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d4c6b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d4cc6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d4c6b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d4cc6`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800d4dbc`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800d4de5`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800d4e0e`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800d4dbc`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800d4de5`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800d4e0e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800d4e25`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800d4e25`
- `ntdll!RtlAllocateHeap` at `0x1800d4d04`
- `ntdll!RtlAllocateHeap` at `0x1800d4d04`
- `ntdll!RtlFreeHeap` at `0x1800d4e43`
- `ntdll!RtlFreeHeap` at `0x1800d4e43`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800d4d92`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800d4d92`
- `ntdll!RtlAddAce` at `0x1800d4d73`
- `ntdll!RtlAddAce` at `0x1800d4d73`
- `ntdll!RtlCreateAcl` at `0x1800d4d32`
- `ntdll!RtlCreateAcl` at `0x1800d4d32`
- `ntdll!RtlQueryInformationAcl` at `0x1800d4beb`
- `ntdll!RtlQueryInformationAcl` at `0x1800d4c0a`
- `ntdll!RtlQueryInformationAcl` at `0x1800d4beb`
- `ntdll!RtlQueryInformationAcl` at `0x1800d4c0a`
- `ntdll!RtlLengthSid` at `0x1800d4c1d`
- `ntdll!RtlLengthSid` at `0x1800d4c84`
- `ntdll!RtlLengthSid` at `0x1800d4cdc`
- `ntdll!RtlLengthSid` at `0x1800d4c1d`
- `ntdll!RtlLengthSid` at `0x1800d4c84`
- `ntdll!RtlLengthSid` at `0x1800d4cdc`
- `ntdll!RtlGetAce` at `0x1800d4d4c`
- `ntdll!RtlGetAce` at `0x1800d4d4c`

## pseudocode

```c
__int64 __fastcall BuildPrivateDirectorySecurityDescriptor(
        int a1,
        void *a2,
        void *a3,
        char a4,
        PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  ULONG v5; // esi
  NTSTATUS DaclSecurityDescriptor; // ebx
  ULONG v11; // eax
  int v12; // r15d
  int v13; // edi
  int v14; // r14d
  SIZE_T v15; // rbx
  struct _ACL *Heap; // rax
  struct _ACL *v17; // rdi
  unsigned __int8 DaclDefaulted; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+61h] [rbp-30h] BYREF
  ULONG AclRevision; // [rsp+64h] [rbp-2Dh] BYREF
  PACL Dacl; // [rsp+68h] [rbp-29h] BYREF
  PSID pSid; // [rsp+70h] [rbp-21h] BYREF
  PSID Sid; // [rsp+78h] [rbp-19h] BYREF
  int v24; // [rsp+80h] [rbp-11h]
  PVOID Ace; // [rsp+88h] [rbp-9h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+90h] [rbp-1h] BYREF
  __int64 Information; // [rsp+98h] [rbp+7h] BYREF
  int v28; // [rsp+A0h] [rbp+Fh]

  v5 = 0;
  Ace = 0;
  AclRevision = 0;
  Information = 0;
  v28 = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclPresent[0] = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  if ( a1 )
    return 3221225485LL;
  pSid = 0;
  Sid = 0;
  DaclSecurityDescriptor = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( DaclSecurityDescriptor >= 0 )
  {
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(a2, DaclPresent, &Dacl, &DaclDefaulted);
    if ( DaclSecurityDescriptor >= 0 )
    {
      DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
      if ( DaclSecurityDescriptor >= 0 )
      {
        DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &AclRevision, 4u, AclRevisionInformation);
        if ( DaclSecurityDescriptor >= 0 )
        {
          v11 = RtlLengthSid(a3);
          v24 = HIDWORD(Information) + 16 + 2 * v11;
          v12 = a4 & 1;
          if ( (a4 & 1) != 0 )
          {
            DaclSecurityDescriptor = RtlAllocateAndInitializeSid(
                                       &IdentifierAuthority,
                                       2u,
                                       0x20u,
                                       0x220u,
                                       0,
                                       0,
                                       0,
                                       0,
                                       0,
                                       0,
                                       &pSid);
            if ( DaclSecurityDescriptor < 0 )
              goto LABEL_27;
            v13 = 1;
            v5 = RtlLengthSid(pSid);
          }
          else
          {
            v13 = 0;
          }
          v14 = a4 & 2;
          if ( !v14 )
            goto LABEL_14;
          DaclSecurityDescriptor = RtlAllocateAndInitializeSid(
                                     &IdentifierAuthority,
                                     1u,
                                     0xCu,
                                     0,
                                     0,
                                     0,
                                     0,
                                     0,
                                     0,
                                     0,
                                     &Sid);
          if ( DaclSecurityDescriptor >= 0 )
          {
            ++v13;
            v5 += RtlLengthSid(Sid);
LABEL_14:
            v15 = (v24 + 8 * v13 + v5 + 3) & 0xFFFFFFFC;
            Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
            v17 = Heap;
            if ( Heap )
            {
              memset_0(Heap, 0, v15);
              DaclSecurityDescriptor = RtlCreateAcl(v17, v15, AclRevision);
              if ( DaclSecurityDescriptor < 0
                || (DaclSecurityDescriptor = RtlGetAce(Dacl, 0, &Ace), DaclSecurityDescriptor < 0)
                || (DaclSecurityDescriptor = RtlAddAce(v17, AclRevision, 0, Ace, HIDWORD(Information) - 8),
                    DaclSecurityDescriptor < 0)
                || (DaclSecurityDescriptor = RtlAddAccessAllowedAce(v17, AclRevision, 0xF000Fu, a3),
                    DaclSecurityDescriptor < 0)
                || (DaclSecurityDescriptor = RtlAddAccessAllowedAceEx(v17, AclRevision, 0xBu, 0x10000000u, a3),
                    DaclSecurityDescriptor < 0)
                || v12
                && (DaclSecurityDescriptor = RtlAddAccessAllowedAceEx(v17, AclRevision, 0xBu, 0x10000000u, pSid),
                    DaclSecurityDescriptor < 0)
                || v14
                && (DaclSecurityDescriptor = RtlAddAccessAllowedAceEx(v17, AclRevision, 0xBu, 0xA0000000, Sid),
                    DaclSecurityDescriptor < 0)
                || (DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v17, 0),
                    DaclSecurityDescriptor < 0) )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
              }
            }
            else
            {
              DaclSecurityDescriptor = -1073741801;
            }
          }
        }
      }
    }
  }
LABEL_27:
  if ( pSid )
    RtlFreeSid(pSid);
  if ( Sid )
    RtlFreeSid(Sid);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x1800d4b2c  mov     [rsp-8+arg_0], rbx
0x1800d4b31  push    rbp
0x1800d4b32  push    rsi
0x1800d4b33  push    rdi
0x1800d4b34  push    r12
0x1800d4b36  push    r13
0x1800d4b38  push    r14
0x1800d4b3a  push    r15
0x1800d4b3c  lea     rbp, [rsp-1Fh]
0x1800d4b41  sub     rsp, 0B0h
0x1800d4b48  mov     rax, cs:__security_cookie
0x1800d4b4f  xor     rax, rsp
0x1800d4b52  mov     [rbp+4Fh+var_38], rax
0x1800d4b56  mov     r13, [rbp+4Fh+SecurityDescriptor]
0x1800d4b5a  xor     esi, esi
0x1800d4b5c  xor     eax, eax
0x1800d4b5e  mov     [rbp+4Fh+Ace], rsi
0x1800d4b62  mov     [rbp+4Fh+AclRevision], esi
0x1800d4b65  mov     r14d, r9d
0x1800d4b68  mov     [rbp+4Fh+Information], rax
0x1800d4b6c  mov     r12, r8
0x1800d4b6f  mov     [rbp+4Fh+var_40], eax
0x1800d4b72  mov     rdi, rdx
0x1800d4b75  mov     [rbp+4Fh+Dacl], rsi
0x1800d4b79  mov     [rbp+4Fh+DaclDefaulted], sil
0x1800d4b7d  mov     [rbp+4Fh+DaclPresent], sil
0x1800d4b81  mov     dword ptr [rbp+4Fh+IdentifierAuthority.Value], esi
0x1800d4b84  mov     word ptr [rbp+4Fh+IdentifierAuthority.Value+4], 500h
0x1800d4b8a  test    ecx, ecx
0x1800d4b8c  jz      short loc_1800D4B98
0x1800d4b8e  mov     eax, 0C000000Dh
0x1800d4b93  jmp     loc_1800D4E69
0x1800d4b98  mov     r15d, 1
0x1800d4b9e  mov     [rbp+4Fh+pSid], rsi
0x1800d4ba2  mov     edx, r15d; Revision
0x1800d4ba5  mov     [rbp+4Fh+var_68], rsi
0x1800d4ba9  mov     rcx, r13; SecurityDescriptor
0x1800d4bac  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800d4bb2  mov     ebx, eax
0x1800d4bb4  test    eax, eax
0x1800d4bb6  js      loc_1800D4E49
0x1800d4bbc  lea     r9, [rbp+4Fh+DaclDefaulted]; DaclDefaulted
0x1800d4bc0  mov     rcx, rdi; SecurityDescriptor
0x1800d4bc3  lea     r8, [rbp+4Fh+Dacl]; Dacl
0x1800d4bc7  lea     rdx, [rbp+4Fh+DaclPresent]; DaclPresent
0x1800d4bcb  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800d4bd1  mov     ebx, eax
0x1800d4bd3  test    eax, eax
0x1800d4bd5  js      loc_1800D4E49
0x1800d4bdb  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x1800d4bdf  lea     r9d, [r15+1]; InformationClass
0x1800d4be3  lea     r8d, [r15+0Bh]; InformationLength
0x1800d4be7  lea     rdx, [rbp+4Fh+Information]; Information
0x1800d4beb  call    cs:__imp_RtlQueryInformationAcl
0x1800d4bf1  mov     ebx, eax
0x1800d4bf3  test    eax, eax
0x1800d4bf5  js      loc_1800D4E49
0x1800d4bfb  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x1800d4bff  lea     r8d, [r15+3]; InformationLength
0x1800d4c03  mov     r9d, r15d; InformationClass
0x1800d4c06  lea     rdx, [rbp+4Fh+AclRevision]; Information
0x1800d4c0a  call    cs:__imp_RtlQueryInformationAcl
0x1800d4c10  mov     ebx, eax
0x1800d4c12  test    eax, eax
0x1800d4c14  js      loc_1800D4E49
0x1800d4c1a  mov     rcx, r12; Sid
0x1800d4c1d  call    cs:__imp_RtlLengthSid
0x1800d4c23  mov     ecx, dword ptr [rbp+4Fh+Information+4]
0x1800d4c26  mov     r15d, r14d
0x1800d4c29  add     ecx, 10h
0x1800d4c2c  lea     eax, [rcx+rax*2]
0x1800d4c2f  mov     [rbp+4Fh+var_60], eax
0x1800d4c32  and     r15d, 1
0x1800d4c36  jz      short loc_1800D4C8E
0x1800d4c38  lea     rax, [rbp+4Fh+pSid]
0x1800d4c3c  mov     r9d, 220h; SubAuthority1
0x1800d4c42  mov     [rsp+0E0h+Sid], rax; Sid
0x1800d4c47  lea     rcx, [rbp+4Fh+IdentifierAuthority]; IdentifierAuthority
0x1800d4c4b  mov     [rsp+0E0h+SubAuthority7], esi; SubAuthority7
0x1800d4c4f  mov     r8d, 20h ; ' '; SubAuthority0
0x1800d4c55  mov     [rsp+0E0h+SubAuthority6], esi; SubAuthority6
0x1800d4c59  mov     dl, 2; SubAuthorityCount
0x1800d4c5b  mov     [rsp+0E0h+SubAuthority5], esi; SubAuthority5
0x1800d4c5f  mov     [rsp+0E0h+SubAuthority4], esi; SubAuthority4
0x1800d4c63  mov     [rsp+0E0h+SubAuthority3], esi; SubAuthority3
0x1800d4c67  mov     [rsp+0E0h+SubAuthority2], esi; SubAuthority2
0x1800d4c6b  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800d4c71  mov     ebx, eax
0x1800d4c73  test    eax, eax
0x1800d4c75  js      loc_1800D4E49
0x1800d4c7b  mov     rcx, [rbp+4Fh+pSid]; Sid
0x1800d4c7f  mov     edi, 1
0x1800d4c84  call    cs:__imp_RtlLengthSid
0x1800d4c8a  mov     esi, eax
0x1800d4c8c  jmp     short loc_1800D4C90
0x1800d4c8e  mov     edi, esi
0x1800d4c90  and     r14d, 2
0x1800d4c94  jz      short loc_1800D4CE4
0x1800d4c96  lea     rax, [rbp+4Fh+var_68]
0x1800d4c9a  xor     r9d, r9d; SubAuthority1
0x1800d4c9d  mov     [rsp+0E0h+Sid], rax; Sid
0x1800d4ca2  lea     rcx, [rbp+4Fh+IdentifierAuthority]; IdentifierAuthority
0x1800d4ca6  xor     eax, eax
0x1800d4ca8  mov     dl, 1; SubAuthorityCount
0x1800d4caa  mov     [rsp+0E0h+SubAuthority7], eax; SubAuthority7
0x1800d4cae  mov     [rsp+0E0h+SubAuthority6], eax; SubAuthority6
0x1800d4cb2  mov     [rsp+0E0h+SubAuthority5], eax; SubAuthority5
0x1800d4cb6  mov     [rsp+0E0h+SubAuthority4], eax; SubAuthority4
0x1800d4cba  lea     r8d, [rax+0Ch]; SubAuthority0
0x1800d4cbe  mov     [rsp+0E0h+SubAuthority3], eax; SubAuthority3
0x1800d4cc2  mov     [rsp+0E0h+SubAuthority2], eax; SubAuthority2
0x1800d4cc6  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800d4ccc  mov     ebx, eax
0x1800d4cce  test    eax, eax
0x1800d4cd0  js      loc_1800D4E49
0x1800d4cd6  mov     rcx, [rbp+4Fh+var_68]; Sid
0x1800d4cda  inc     edi
0x1800d4cdc  call    cs:__imp_RtlLengthSid
0x1800d4ce2  add     esi, eax
0x1800d4ce4  mov     eax, [rbp+4Fh+var_60]
0x1800d4ce7  lea     ebx, [rsi+3]
0x1800d4cea  mov     rcx, gs:60h
0x1800d4cf3  xor     edx, edx; Flags
0x1800d4cf5  lea     eax, [rax+rdi*8]
0x1800d4cf8  mov     rcx, [rcx+30h]; HeapHandle
0x1800d4cfc  add     ebx, eax
0x1800d4cfe  and     ebx, 0FFFFFFFCh
0x1800d4d01  mov     r8d, ebx; Size
0x1800d4d04  call    cs:__imp_RtlAllocateHeap
0x1800d4d0a  mov     rdi, rax
0x1800d4d0d  test    rax, rax
0x1800d4d10  jnz     short loc_1800D4D1C
0x1800d4d12  mov     ebx, 0C0000017h
0x1800d4d17  jmp     loc_1800D4E49
0x1800d4d1c  mov     r8, rbx; Size
0x1800d4d1f  xor     edx, edx; Val
0x1800d4d21  mov     rcx, rdi; void *
0x1800d4d24  call    memset_0
0x1800d4d29  mov     r8d, [rbp+4Fh+AclRevision]; AclRevision
0x1800d4d2d  mov     edx, ebx; AclSize
0x1800d4d2f  mov     rcx, rdi; Acl
0x1800d4d32  call    cs:__imp_RtlCreateAcl
0x1800d4d38  mov     ebx, eax
0x1800d4d3a  test    eax, eax
0x1800d4d3c  js      loc_1800D4E31
0x1800d4d42  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x1800d4d46  lea     r8, [rbp+4Fh+Ace]; Ace
0x1800d4d4a  xor     edx, edx; AceIndex
0x1800d4d4c  call    cs:__imp_RtlGetAce
0x1800d4d52  mov     ebx, eax
0x1800d4d54  test    eax, eax
0x1800d4d56  js      loc_1800D4E31
0x1800d4d5c  mov     eax, dword ptr [rbp+4Fh+Information+4]
0x1800d4d5f  xor     r8d, r8d; StartingAceIndex
0x1800d4d62  mov     r9, [rbp+4Fh+Ace]; AceList
0x1800d4d66  add     eax, 0FFFFFFF8h
0x1800d4d69  mov     edx, [rbp+4Fh+AclRevision]; AceRevision
0x1800d4d6c  mov     rcx, rdi; Acl
0x1800d4d6f  mov     [rsp+0E0h+SubAuthority2], eax; AceListLength
0x1800d4d73  call    cs:__imp_RtlAddAce
0x1800d4d79  mov     ebx, eax
0x1800d4d7b  test    eax, eax
0x1800d4d7d  js      loc_1800D4E31
0x1800d4d83  mov     edx, [rbp+4Fh+AclRevision]; Revision
0x1800d4d86  mov     r9, r12; Sid
0x1800d4d89  mov     r8d, 0F000Fh; AccessMask
0x1800d4d8f  mov     rcx, rdi; Acl
0x1800d4d92  call    cs:__imp_RtlAddAccessAllowedAce
0x1800d4d98  mov     ebx, eax
0x1800d4d9a  test    eax, eax
0x1800d4d9c  js      loc_1800D4E31
0x1800d4da2  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x1800d4da5  mov     r9d, 10000000h; AccessMask
0x1800d4dab  mov     qword ptr [rsp+0E0h+SubAuthority2], r12; pSid
0x1800d4db0  mov     rcx, rdi; pAcl
0x1800d4db3  mov     r12d, 0Bh
0x1800d4db9  mov     r8d, r12d; AceFlags
0x1800d4dbc  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1800d4dc2  mov     ebx, eax
0x1800d4dc4  test    eax, eax
0x1800d4dc6  js      short loc_1800D4E31
0x1800d4dc8  test    r15d, r15d
0x1800d4dcb  jz      short loc_1800D4DF1
0x1800d4dcd  mov     rax, [rbp+4Fh+pSid]
0x1800d4dd1  mov     r9d, 10000000h; AccessMask
0x1800d4dd7  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x1800d4dda  mov     r8d, r12d; AceFlags
0x1800d4ddd  mov     rcx, rdi; pAcl
0x1800d4de0  mov     qword ptr [rsp+0E0h+SubAuthority2], rax; pSid
0x1800d4de5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1800d4deb  mov     ebx, eax
0x1800d4ded  test    eax, eax
0x1800d4def  js      short loc_1800D4E31
0x1800d4df1  test    r14d, r14d
0x1800d4df4  jz      short loc_1800D4E1A
0x1800d4df6  mov     rax, [rbp+4Fh+var_68]
0x1800d4dfa  mov     r9d, 0A0000000h; AccessMask
0x1800d4e00  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x1800d4e03  mov     r8d, r12d; AceFlags
0x1800d4e06  mov     rcx, rdi; pAcl
0x1800d4e09  mov     qword ptr [rsp+0E0h+SubAuthority2], rax; pSid
0x1800d4e0e  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1800d4e14  mov     ebx, eax
0x1800d4e16  test    eax, eax
0x1800d4e18  js      short loc_1800D4E31
0x1800d4e1a  xor     r9d, r9d; DaclDefaulted
0x1800d4e1d  mov     r8, rdi; Dacl
0x1800d4e20  mov     dl, 1; DaclPresent
0x1800d4e22  mov     rcx, r13; SecurityDescriptor
0x1800d4e25  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800d4e2b  mov     ebx, eax
0x1800d4e2d  test    eax, eax
0x1800d4e2f  jns     short loc_1800D4E49
0x1800d4e31  mov     rcx, gs:60h
0x1800d4e3a  mov     r8, rdi; P
0x1800d4e3d  xor     edx, edx; Flags
0x1800d4e3f  mov     rcx, [rcx+30h]; HeapHandle
0x1800d4e43  call    cs:__imp_RtlFreeHeap
0x1800d4e49  mov     rcx, [rbp+4Fh+pSid]; Sid
0x1800d4e4d  test    rcx, rcx
0x1800d4e50  jz      short loc_1800D4E58
0x1800d4e52  call    cs:__imp_RtlFreeSid
0x1800d4e58  mov     rcx, [rbp+4Fh+var_68]; Sid
0x1800d4e5c  test    rcx, rcx
0x1800d4e5f  jz      short loc_1800D4E67
0x1800d4e61  call    cs:__imp_RtlFreeSid
0x1800d4e67  mov     eax, ebx
0x1800d4e69  mov     rcx, [rbp+4Fh+var_38]
0x1800d4e6d  xor     rcx, rsp; StackCookie
0x1800d4e70  call    __security_check_cookie
0x1800d4e75  mov     rbx, [rsp+0E0h+arg_0]
0x1800d4e7d  add     rsp, 0B0h
0x1800d4e84  pop     r15
0x1800d4e86  pop     r14
0x1800d4e88  pop     r13
0x1800d4e8a  pop     r12
0x1800d4e8c  pop     rdi
0x1800d4e8d  pop     rsi
0x1800d4e8e  pop     rbp
0x1800d4e8f  retn
```
