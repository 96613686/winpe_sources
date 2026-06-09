# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x1800959e4`
- end: `0x180095c30`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `588`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800957e0`

## callees

- `0x180010c04`
- `0x180034b2c`
- `0x18008a030`
- `0x1800959e4`
- `0x18009e664`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095b29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095b29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095b3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095b3a`
- `ntdll!RtlGetAce` at `0x180095b9a`
- `ntdll!RtlGetAce` at `0x180095b9a`
- `ntdll!RtlCreateAcl` at `0x180095b74`
- `ntdll!RtlCreateAcl` at `0x180095b74`
- `ntdll!RtlLengthSid` at `0x180095b18`
- `ntdll!RtlLengthSid` at `0x180095b18`
- `ntdll!RtlQueryInformationAcl` at `0x180095ad4`
- `ntdll!RtlQueryInformationAcl` at `0x180095b01`
- `ntdll!RtlQueryInformationAcl` at `0x180095ad4`
- `ntdll!RtlQueryInformationAcl` at `0x180095b01`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180095a2d`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180095a2d`
- `ntdll!RtlAddAccessAllowedAce` at `0x180095bdf`
- `ntdll!RtlAddAccessAllowedAce` at `0x180095bdf`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180095bfb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180095bfb`
- `ntdll!RtlAddAce` at `0x180095bc2`
- `ntdll!RtlAddAce` at `0x180095bc2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180095a6d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180095a6d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180095a87`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180095a87`

## string_xrefs

- `0x180095a40`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180095b4c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180095c12`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall BuildUserSD(void *a1, void *a2, ACCESS_MASK a3, bool *a4, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  NTSTATUS DaclSecurityDescriptor; // eax
  __int64 v9; // rdx
  DWORD i; // ebx
  _DWORD *v12; // rdi
  ULONG v13; // eax
  ULONG v14; // r14d
  HANDLE ProcessHeap; // rax
  struct _ACL *v16; // rax
  struct _ACL *v17; // rdi
  int v18; // ebx
  NTSTATUS Acl; // eax
  __int64 v20; // rdx
  void *v21; // rdx
  ULONG AceListLength; // [rsp+20h] [rbp-50h]
  unsigned __int8 DaclDefaulted; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+31h] [rbp-3Fh] BYREF
  ULONG AclRevision; // [rsp+34h] [rbp-3Ch] BYREF
  PACL Dacl; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  PVOID Ace; // [rsp+48h] [rbp-28h] BYREF
  __int64 Information; // [rsp+50h] [rbp-20h] BYREF
  int v30; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  DaclPresent[0] = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(a1, DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 41;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  for ( i = 0; i < Dacl->AceCount; ++i )
  {
    pAce = 0;
    if ( GetAce(Dacl, i, &pAce) )
    {
      v12 = pAce;
      if ( !*(_BYTE *)pAce && EqualSid((char *)pAce + 8, a2) && (a3 & v12[1]) == a3 )
      {
        *a4 = 1;
        return 0;
      }
    }
  }
  Information = 0;
  v30 = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 61;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  AclRevision = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &AclRevision, 4u, AclRevisionInformation);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 64;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  v13 = RtlLengthSid(a2);
  v14 = v13 + HIDWORD(Information) + 8;
  ProcessHeap = GetProcessHeap();
  v16 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v14);
  v17 = v16;
  if ( v16 )
  {
    Acl = RtlCreateAcl(v16, v14, AclRevision);
    if ( Acl >= 0 )
    {
      Ace = 0;
      Acl = RtlGetAce(Dacl, 0, &Ace);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAce(v17, AclRevision, 0, Ace, HIDWORD(Information) - 8);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v17, AclRevision, a3, a2);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v17, 0);
            if ( Acl >= 0 )
              return 0;
            v20 = 83;
          }
          else
          {
            v20 = 81;
          }
        }
        else
        {
          v20 = 78;
        }
      }
      else
      {
        v20 = 76;
      }
    }
    else
    {
      v20 = 73;
    }
    v18 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v20,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)Acl,
            AceListLength);
    wil::details::FreeProcessHeap((wil::details *)v17, v21);
  }
  else
  {
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)0x8007000ELL,
      AceListLength);
  }
  return v18;
}

```

## disassembly

```asm
0x1800959e4  push    rbp
0x1800959e6  push    rbx
0x1800959e7  push    rsi
0x1800959e8  push    rdi
0x1800959e9  push    r12
0x1800959eb  push    r14
0x1800959ed  push    r15
0x1800959ef  mov     rbp, rsp
0x1800959f2  sub     rsp, 70h
0x1800959f6  mov     rax, cs:__security_cookie
0x1800959fd  xor     rax, rsp
0x180095a00  mov     [rbp+var_10], rax
0x180095a04  mov     r12, [rbp+SecurityDescriptor]
0x180095a08  mov     r14, r9
0x180095a0b  mov     esi, r8d
0x180095a0e  mov     [rbp+DaclPresent], 0
0x180095a12  mov     r15, rdx
0x180095a15  mov     [rbp+Dacl], 0
0x180095a1d  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x180095a21  mov     [rbp+DaclDefaulted], 0
0x180095a25  lea     r8, [rbp+Dacl]; Dacl
0x180095a29  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x180095a2d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180095a33  test    eax, eax
0x180095a35  jns     short loc_180095A51
0x180095a37  mov     edx, 29h ; ')'; void *
0x180095a3c  mov     rcx, [rbp+38h]; this
0x180095a40  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180095a47  mov     r9d, eax; char *
0x180095a4a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180095a4f  jmp     short loc_180095AA4
0x180095a51  xor     ebx, ebx
0x180095a53  mov     rcx, [rbp+Dacl]; Acl
0x180095a57  movzx   eax, word ptr [rcx+4]
0x180095a5b  cmp     ebx, eax
0x180095a5d  jnb     short loc_180095ABF
0x180095a5f  lea     r8, [rbp+pAce]; pAce
0x180095a63  mov     [rbp+pAce], 0
0x180095a6b  mov     edx, ebx; dwAceIndex
0x180095a6d  call    cs:__imp_GetAce
0x180095a73  test    eax, eax
0x180095a75  jz      short loc_180095A9A
0x180095a77  mov     rdi, [rbp+pAce]
0x180095a7b  cmp     byte ptr [rdi], 0
0x180095a7e  jnz     short loc_180095A9A
0x180095a80  lea     rcx, [rdi+8]; pSid1
0x180095a84  mov     rdx, r15; pSid2
0x180095a87  call    cs:__imp_EqualSid
0x180095a8d  test    eax, eax
0x180095a8f  jz      short loc_180095A9A
0x180095a91  mov     eax, [rdi+4]
0x180095a94  and     eax, esi
0x180095a96  cmp     eax, esi
0x180095a98  jz      short loc_180095A9E
0x180095a9a  inc     ebx
0x180095a9c  jmp     short loc_180095A53
0x180095a9e  mov     byte ptr [r14], 1
0x180095aa2  xor     eax, eax
0x180095aa4  mov     rcx, [rbp+var_10]
0x180095aa8  xor     rcx, rsp; StackCookie
0x180095aab  call    __security_check_cookie
0x180095ab0  add     rsp, 70h
0x180095ab4  pop     r15
0x180095ab6  pop     r14
0x180095ab8  pop     r12
0x180095aba  pop     rdi
0x180095abb  pop     rsi
0x180095abc  pop     rbx
0x180095abd  pop     rbp
0x180095abe  retn
0x180095abf  xor     eax, eax
0x180095ac1  lea     rdx, [rbp+Information]; Information
0x180095ac5  mov     [rbp+Information], rax
0x180095ac9  mov     [rbp+var_18], eax
0x180095acc  lea     r9d, [rax+2]; InformationClass
0x180095ad0  lea     r8d, [rax+0Ch]; InformationLength
0x180095ad4  call    cs:__imp_RtlQueryInformationAcl
0x180095ada  test    eax, eax
0x180095adc  jns     short loc_180095AE8
0x180095ade  mov     edx, 3Dh ; '='
0x180095ae3  jmp     loc_180095A3C
0x180095ae8  mov     rcx, [rbp+Dacl]; Acl
0x180095aec  lea     rdx, [rbp+AclRevision]; Information
0x180095af0  mov     r9d, 1; InformationClass
0x180095af6  mov     [rbp+AclRevision], 0
0x180095afd  lea     r8d, [r9+3]; InformationLength
0x180095b01  call    cs:__imp_RtlQueryInformationAcl
0x180095b07  test    eax, eax
0x180095b09  jns     short loc_180095B15
0x180095b0b  mov     edx, 40h ; '@'
0x180095b10  jmp     loc_180095A3C
0x180095b15  mov     rcx, r15; Sid
0x180095b18  call    cs:__imp_RtlLengthSid
0x180095b1e  mov     r14d, dword ptr [rbp+Information+4]
0x180095b22  add     r14d, 8
0x180095b26  add     r14d, eax
0x180095b29  call    cs:__imp_GetProcessHeap
0x180095b2f  mov     r8d, r14d; dwBytes
0x180095b32  mov     edx, 8; dwFlags
0x180095b37  mov     rcx, rax; hHeap
0x180095b3a  call    cs:__imp_HeapAlloc
0x180095b40  mov     rdi, rax
0x180095b43  test    rax, rax
0x180095b46  jnz     short loc_180095B6A
0x180095b48  mov     rcx, [rbp+38h]; this
0x180095b4c  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180095b53  mov     ebx, 8007000Eh
0x180095b58  lea     edx, [rax+47h]; void *
0x180095b5b  mov     r9d, ebx; char *
0x180095b5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095b63  mov     eax, ebx
0x180095b65  jmp     loc_180095AA4
0x180095b6a  mov     r8d, [rbp+AclRevision]; AclRevision
0x180095b6e  mov     edx, r14d; AclSize
0x180095b71  mov     rcx, rdi; Acl
0x180095b74  call    cs:__imp_RtlCreateAcl
0x180095b7a  test    eax, eax
0x180095b7c  jns     short loc_180095B88
0x180095b7e  mov     edx, 49h ; 'I'
0x180095b83  jmp     loc_180095C0E
0x180095b88  mov     rcx, [rbp+Dacl]; Acl
0x180095b8c  lea     r8, [rbp+Ace]; Ace
0x180095b90  xor     edx, edx; AceIndex
0x180095b92  mov     [rbp+Ace], 0
0x180095b9a  call    cs:__imp_RtlGetAce
0x180095ba0  test    eax, eax
0x180095ba2  jns     short loc_180095BAB
0x180095ba4  mov     edx, 4Ch ; 'L'
0x180095ba9  jmp     short loc_180095C0E
0x180095bab  mov     eax, dword ptr [rbp+Information+4]
0x180095bae  xor     r8d, r8d; StartingAceIndex
0x180095bb1  mov     r9, [rbp+Ace]; AceList
0x180095bb5  add     eax, 0FFFFFFF8h
0x180095bb8  mov     edx, [rbp+AclRevision]; AceRevision
0x180095bbb  mov     rcx, rdi; Acl
0x180095bbe  mov     [rsp+70h+AceListLength], eax; int
0x180095bc2  call    cs:__imp_RtlAddAce
0x180095bc8  test    eax, eax
0x180095bca  jns     short loc_180095BD3
0x180095bcc  mov     edx, 4Eh ; 'N'
0x180095bd1  jmp     short loc_180095C0E
0x180095bd3  mov     edx, [rbp+AclRevision]; Revision
0x180095bd6  mov     r9, r15; Sid
0x180095bd9  mov     r8d, esi; AccessMask
0x180095bdc  mov     rcx, rdi; Acl
0x180095bdf  call    cs:__imp_RtlAddAccessAllowedAce
0x180095be5  test    eax, eax
0x180095be7  jns     short loc_180095BF0
0x180095be9  mov     edx, 51h ; 'Q'
0x180095bee  jmp     short loc_180095C0E
0x180095bf0  xor     r9d, r9d; DaclDefaulted
0x180095bf3  mov     r8, rdi; Dacl
0x180095bf6  mov     dl, 1; DaclPresent
0x180095bf8  mov     rcx, r12; SecurityDescriptor
0x180095bfb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180095c01  test    eax, eax
0x180095c03  jns     loc_180095AA2
0x180095c09  mov     edx, 53h ; 'S'; void *
0x180095c0e  mov     rcx, [rbp+38h]; this
0x180095c12  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180095c19  mov     r9d, eax; char *
0x180095c1c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180095c21  mov     rcx, rdi; this
0x180095c24  mov     ebx, eax
0x180095c26  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180095c2b  jmp     loc_180095B63
```
