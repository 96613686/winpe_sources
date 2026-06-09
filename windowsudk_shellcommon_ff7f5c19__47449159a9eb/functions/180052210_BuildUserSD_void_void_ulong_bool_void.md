# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x180052210`
- end: `0x18005245c`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `588`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005200c`

## callees

- `0x1800512e0`
- `0x180052210`
- `0x1800e2bc4`
- `0x1800e34bc`
- `0x18015cb00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052355`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052355`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052366`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052366`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180052299`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180052299`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800522b3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800522b3`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005240b`
- `ntdll!RtlAddAccessAllowedAce` at `0x18005240b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180052427`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180052427`
- `ntdll!RtlCreateAcl` at `0x1800523a0`
- `ntdll!RtlCreateAcl` at `0x1800523a0`
- `ntdll!RtlLengthSid` at `0x180052344`
- `ntdll!RtlLengthSid` at `0x180052344`
- `ntdll!RtlQueryInformationAcl` at `0x180052300`
- `ntdll!RtlQueryInformationAcl` at `0x18005232d`
- `ntdll!RtlQueryInformationAcl` at `0x180052300`
- `ntdll!RtlQueryInformationAcl` at `0x18005232d`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180052259`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180052259`
- `ntdll!RtlAddAce` at `0x1800523ee`
- `ntdll!RtlAddAce` at `0x1800523ee`
- `ntdll!RtlGetAce` at `0x1800523c6`
- `ntdll!RtlGetAce` at `0x1800523c6`

## string_xrefs

- `0x18005226c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180052378`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18005243e`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
__int64 __fastcall BuildUserSD(void *a1, void *a2, ACCESS_MASK a3, bool *a4, PSECURITY_DESCRIPTOR SecurityDescriptor)
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
  unsigned int v18; // ebx
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
0x180052210  push    rbp
0x180052212  push    rbx
0x180052213  push    rsi
0x180052214  push    rdi
0x180052215  push    r12
0x180052217  push    r14
0x180052219  push    r15
0x18005221b  mov     rbp, rsp
0x18005221e  sub     rsp, 70h
0x180052222  mov     rax, cs:__security_cookie
0x180052229  xor     rax, rsp
0x18005222c  mov     [rbp+var_10], rax
0x180052230  mov     r12, [rbp+SecurityDescriptor]
0x180052234  mov     r14, r9
0x180052237  mov     esi, r8d
0x18005223a  mov     [rbp+DaclPresent], 0
0x18005223e  mov     r15, rdx
0x180052241  mov     [rbp+Dacl], 0
0x180052249  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x18005224d  mov     [rbp+DaclDefaulted], 0
0x180052251  lea     r8, [rbp+Dacl]; Dacl
0x180052255  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x180052259  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18005225f  test    eax, eax
0x180052261  jns     short loc_18005227D
0x180052263  mov     edx, 29h ; ')'; void *
0x180052268  mov     rcx, [rbp+38h]; this
0x18005226c  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180052273  mov     r9d, eax; char *
0x180052276  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005227b  jmp     short loc_1800522D0
0x18005227d  xor     ebx, ebx
0x18005227f  mov     rcx, [rbp+Dacl]; Acl
0x180052283  movzx   eax, word ptr [rcx+4]
0x180052287  cmp     ebx, eax
0x180052289  jnb     short loc_1800522EB
0x18005228b  lea     r8, [rbp+pAce]; pAce
0x18005228f  mov     [rbp+pAce], 0
0x180052297  mov     edx, ebx; dwAceIndex
0x180052299  call    cs:__imp_GetAce
0x18005229f  test    eax, eax
0x1800522a1  jz      short loc_1800522C6
0x1800522a3  mov     rdi, [rbp+pAce]
0x1800522a7  cmp     byte ptr [rdi], 0
0x1800522aa  jnz     short loc_1800522C6
0x1800522ac  lea     rcx, [rdi+8]; pSid1
0x1800522b0  mov     rdx, r15; pSid2
0x1800522b3  call    cs:__imp_EqualSid
0x1800522b9  test    eax, eax
0x1800522bb  jz      short loc_1800522C6
0x1800522bd  mov     eax, [rdi+4]
0x1800522c0  and     eax, esi
0x1800522c2  cmp     eax, esi
0x1800522c4  jz      short loc_1800522CA
0x1800522c6  inc     ebx
0x1800522c8  jmp     short loc_18005227F
0x1800522ca  mov     byte ptr [r14], 1
0x1800522ce  xor     eax, eax
0x1800522d0  mov     rcx, [rbp+var_10]
0x1800522d4  xor     rcx, rsp; StackCookie
0x1800522d7  call    __security_check_cookie
0x1800522dc  add     rsp, 70h
0x1800522e0  pop     r15
0x1800522e2  pop     r14
0x1800522e4  pop     r12
0x1800522e6  pop     rdi
0x1800522e7  pop     rsi
0x1800522e8  pop     rbx
0x1800522e9  pop     rbp
0x1800522ea  retn
0x1800522eb  xor     eax, eax
0x1800522ed  lea     rdx, [rbp+Information]; Information
0x1800522f1  mov     [rbp+Information], rax
0x1800522f5  mov     [rbp+var_18], eax
0x1800522f8  lea     r9d, [rax+2]; InformationClass
0x1800522fc  lea     r8d, [rax+0Ch]; InformationLength
0x180052300  call    cs:__imp_RtlQueryInformationAcl
0x180052306  test    eax, eax
0x180052308  jns     short loc_180052314
0x18005230a  mov     edx, 3Dh ; '='
0x18005230f  jmp     loc_180052268
0x180052314  mov     rcx, [rbp+Dacl]; Acl
0x180052318  lea     rdx, [rbp+AclRevision]; Information
0x18005231c  mov     r9d, 1; InformationClass
0x180052322  mov     [rbp+AclRevision], 0
0x180052329  lea     r8d, [r9+3]; InformationLength
0x18005232d  call    cs:__imp_RtlQueryInformationAcl
0x180052333  test    eax, eax
0x180052335  jns     short loc_180052341
0x180052337  mov     edx, 40h ; '@'
0x18005233c  jmp     loc_180052268
0x180052341  mov     rcx, r15; Sid
0x180052344  call    cs:__imp_RtlLengthSid
0x18005234a  mov     r14d, dword ptr [rbp+Information+4]
0x18005234e  add     r14d, 8
0x180052352  add     r14d, eax
0x180052355  call    cs:__imp_GetProcessHeap
0x18005235b  mov     r8d, r14d; dwBytes
0x18005235e  mov     edx, 8; dwFlags
0x180052363  mov     rcx, rax; hHeap
0x180052366  call    cs:__imp_HeapAlloc
0x18005236c  mov     rdi, rax
0x18005236f  test    rax, rax
0x180052372  jnz     short loc_180052396
0x180052374  mov     rcx, [rbp+38h]; this
0x180052378  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18005237f  mov     ebx, 8007000Eh
0x180052384  lea     edx, [rax+47h]; void *
0x180052387  mov     r9d, ebx; char *
0x18005238a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005238f  mov     eax, ebx
0x180052391  jmp     loc_1800522D0
0x180052396  mov     r8d, [rbp+AclRevision]; AclRevision
0x18005239a  mov     edx, r14d; AclSize
0x18005239d  mov     rcx, rdi; Acl
0x1800523a0  call    cs:__imp_RtlCreateAcl
0x1800523a6  test    eax, eax
0x1800523a8  jns     short loc_1800523B4
0x1800523aa  mov     edx, 49h ; 'I'
0x1800523af  jmp     loc_18005243A
0x1800523b4  mov     rcx, [rbp+Dacl]; Acl
0x1800523b8  lea     r8, [rbp+Ace]; Ace
0x1800523bc  xor     edx, edx; AceIndex
0x1800523be  mov     [rbp+Ace], 0
0x1800523c6  call    cs:__imp_RtlGetAce
0x1800523cc  test    eax, eax
0x1800523ce  jns     short loc_1800523D7
0x1800523d0  mov     edx, 4Ch ; 'L'
0x1800523d5  jmp     short loc_18005243A
0x1800523d7  mov     eax, dword ptr [rbp+Information+4]
0x1800523da  xor     r8d, r8d; StartingAceIndex
0x1800523dd  mov     r9, [rbp+Ace]; AceList
0x1800523e1  add     eax, 0FFFFFFF8h
0x1800523e4  mov     edx, [rbp+AclRevision]; AceRevision
0x1800523e7  mov     rcx, rdi; Acl
0x1800523ea  mov     [rsp+70h+AceListLength], eax; int
0x1800523ee  call    cs:__imp_RtlAddAce
0x1800523f4  test    eax, eax
0x1800523f6  jns     short loc_1800523FF
0x1800523f8  mov     edx, 4Eh ; 'N'
0x1800523fd  jmp     short loc_18005243A
0x1800523ff  mov     edx, [rbp+AclRevision]; Revision
0x180052402  mov     r9, r15; Sid
0x180052405  mov     r8d, esi; AccessMask
0x180052408  mov     rcx, rdi; Acl
0x18005240b  call    cs:__imp_RtlAddAccessAllowedAce
0x180052411  test    eax, eax
0x180052413  jns     short loc_18005241C
0x180052415  mov     edx, 51h ; 'Q'
0x18005241a  jmp     short loc_18005243A
0x18005241c  xor     r9d, r9d; DaclDefaulted
0x18005241f  mov     r8, rdi; Dacl
0x180052422  mov     dl, 1; DaclPresent
0x180052424  mov     rcx, r12; SecurityDescriptor
0x180052427  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18005242d  test    eax, eax
0x18005242f  jns     loc_1800522CE
0x180052435  mov     edx, 53h ; 'S'; void *
0x18005243a  mov     rcx, [rbp+38h]; this
0x18005243e  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180052445  mov     r9d, eax; char *
0x180052448  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005244d  mov     rcx, rdi; this
0x180052450  mov     ebx, eax
0x180052452  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180052457  jmp     loc_18005238F
```
