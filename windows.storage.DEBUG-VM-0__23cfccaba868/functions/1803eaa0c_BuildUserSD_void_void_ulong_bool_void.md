# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x1803eaa0c`
- end: `0x1803eac58`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `588`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803ea070`

## callees

- `0x1800432f0`
- `0x1800c2ec0`
- `0x18034f504`
- `0x1803a4cb0`
- `0x1803eaa0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803eab62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803eab62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803eab51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803eab51`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1803eac23`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1803eac23`
- `ntdll!RtlAddAccessAllowedAce` at `0x1803eac07`
- `ntdll!RtlAddAccessAllowedAce` at `0x1803eac07`
- `ntdll!RtlAddAce` at `0x1803eabea`
- `ntdll!RtlAddAce` at `0x1803eabea`
- `ntdll!RtlGetAce` at `0x1803eabc2`
- `ntdll!RtlGetAce` at `0x1803eabc2`
- `ntdll!RtlCreateAcl` at `0x1803eab9c`
- `ntdll!RtlCreateAcl` at `0x1803eab9c`
- `ntdll!RtlLengthSid` at `0x1803eab40`
- `ntdll!RtlLengthSid` at `0x1803eab40`
- `ntdll!RtlQueryInformationAcl` at `0x1803eaafc`
- `ntdll!RtlQueryInformationAcl` at `0x1803eab29`
- `ntdll!RtlQueryInformationAcl` at `0x1803eaafc`
- `ntdll!RtlQueryInformationAcl` at `0x1803eab29`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1803eaa55`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1803eaa55`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1803eaa95`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1803eaa95`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1803eaaaf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1803eaaaf`

## string_xrefs

- `0x1803eaa68`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803eab74`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803eac3a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

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
  ULONG AceListLength; // [rsp+20h] [rbp-50h]
  PACL Dacl; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-38h] BYREF
  PVOID Ace; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+49h] [rbp-27h] BYREF
  ULONG AclRevision; // [rsp+4Ch] [rbp-24h] BYREF
  __int64 Information; // [rsp+50h] [rbp-20h] BYREF
  int v29; // [rsp+58h] [rbp-18h]
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
  v29 = 0;
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
    MemoryFree(v17);
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
0x1803eaa0c  push    rbp
0x1803eaa0e  push    rbx
0x1803eaa0f  push    rsi
0x1803eaa10  push    rdi
0x1803eaa11  push    r12
0x1803eaa13  push    r14
0x1803eaa15  push    r15
0x1803eaa17  mov     rbp, rsp
0x1803eaa1a  sub     rsp, 70h
0x1803eaa1e  mov     rax, cs:__security_cookie
0x1803eaa25  xor     rax, rsp
0x1803eaa28  mov     [rbp+var_10], rax
0x1803eaa2c  mov     r12, [rbp+SecurityDescriptor]
0x1803eaa30  mov     r14, r9
0x1803eaa33  mov     esi, r8d
0x1803eaa36  mov     [rbp+DaclPresent], 0
0x1803eaa3a  mov     r15, rdx
0x1803eaa3d  mov     [rbp+Dacl], 0
0x1803eaa45  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1803eaa49  mov     [rbp+DaclDefaulted], 0
0x1803eaa4d  lea     r8, [rbp+Dacl]; Dacl
0x1803eaa51  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1803eaa55  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1803eaa5b  test    eax, eax
0x1803eaa5d  jns     short loc_1803EAA79
0x1803eaa5f  mov     edx, 29h ; ')'; void *
0x1803eaa64  mov     rcx, [rbp+38h]; this
0x1803eaa68  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1803eaa6f  mov     r9d, eax; char *
0x1803eaa72  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1803eaa77  jmp     short loc_1803EAACC
0x1803eaa79  xor     ebx, ebx
0x1803eaa7b  mov     rcx, [rbp+Dacl]; Acl
0x1803eaa7f  movzx   eax, word ptr [rcx+4]
0x1803eaa83  cmp     ebx, eax
0x1803eaa85  jnb     short loc_1803EAAE7
0x1803eaa87  lea     r8, [rbp+pAce]; pAce
0x1803eaa8b  mov     [rbp+pAce], 0
0x1803eaa93  mov     edx, ebx; dwAceIndex
0x1803eaa95  call    cs:__imp_GetAce
0x1803eaa9b  test    eax, eax
0x1803eaa9d  jz      short loc_1803EAAC2
0x1803eaa9f  mov     rdi, [rbp+pAce]
0x1803eaaa3  cmp     byte ptr [rdi], 0
0x1803eaaa6  jnz     short loc_1803EAAC2
0x1803eaaa8  lea     rcx, [rdi+8]; pSid1
0x1803eaaac  mov     rdx, r15; pSid2
0x1803eaaaf  call    cs:__imp_EqualSid
0x1803eaab5  test    eax, eax
0x1803eaab7  jz      short loc_1803EAAC2
0x1803eaab9  mov     eax, [rdi+4]
0x1803eaabc  and     eax, esi
0x1803eaabe  cmp     eax, esi
0x1803eaac0  jz      short loc_1803EAAC6
0x1803eaac2  inc     ebx
0x1803eaac4  jmp     short loc_1803EAA7B
0x1803eaac6  mov     byte ptr [r14], 1
0x1803eaaca  xor     eax, eax
0x1803eaacc  mov     rcx, [rbp+var_10]
0x1803eaad0  xor     rcx, rsp; StackCookie
0x1803eaad3  call    __security_check_cookie
0x1803eaad8  add     rsp, 70h
0x1803eaadc  pop     r15
0x1803eaade  pop     r14
0x1803eaae0  pop     r12
0x1803eaae2  pop     rdi
0x1803eaae3  pop     rsi
0x1803eaae4  pop     rbx
0x1803eaae5  pop     rbp
0x1803eaae6  retn
0x1803eaae7  xor     eax, eax
0x1803eaae9  lea     rdx, [rbp+Information]; Information
0x1803eaaed  mov     [rbp+Information], rax
0x1803eaaf1  mov     [rbp+var_18], eax
0x1803eaaf4  lea     r9d, [rax+2]; InformationClass
0x1803eaaf8  lea     r8d, [rax+0Ch]; InformationLength
0x1803eaafc  call    cs:__imp_RtlQueryInformationAcl
0x1803eab02  test    eax, eax
0x1803eab04  jns     short loc_1803EAB10
0x1803eab06  mov     edx, 3Dh ; '='
0x1803eab0b  jmp     loc_1803EAA64
0x1803eab10  mov     rcx, [rbp+Dacl]; Acl
0x1803eab14  lea     rdx, [rbp+AclRevision]; Information
0x1803eab18  mov     r9d, 1; InformationClass
0x1803eab1e  mov     [rbp+AclRevision], 0
0x1803eab25  lea     r8d, [r9+3]; InformationLength
0x1803eab29  call    cs:__imp_RtlQueryInformationAcl
0x1803eab2f  test    eax, eax
0x1803eab31  jns     short loc_1803EAB3D
0x1803eab33  mov     edx, 40h ; '@'
0x1803eab38  jmp     loc_1803EAA64
0x1803eab3d  mov     rcx, r15; Sid
0x1803eab40  call    cs:__imp_RtlLengthSid
0x1803eab46  mov     r14d, dword ptr [rbp+Information+4]
0x1803eab4a  add     r14d, 8
0x1803eab4e  add     r14d, eax
0x1803eab51  call    cs:__imp_GetProcessHeap
0x1803eab57  mov     r8d, r14d; dwBytes
0x1803eab5a  mov     edx, 8; dwFlags
0x1803eab5f  mov     rcx, rax; hHeap
0x1803eab62  call    cs:__imp_HeapAlloc
0x1803eab68  mov     rdi, rax
0x1803eab6b  test    rax, rax
0x1803eab6e  jnz     short loc_1803EAB92
0x1803eab70  mov     rcx, [rbp+38h]; this
0x1803eab74  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1803eab7b  mov     ebx, 8007000Eh
0x1803eab80  lea     edx, [rax+47h]; void *
0x1803eab83  mov     r9d, ebx; char *
0x1803eab86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803eab8b  mov     eax, ebx
0x1803eab8d  jmp     loc_1803EAACC
0x1803eab92  mov     r8d, [rbp+AclRevision]; AclRevision
0x1803eab96  mov     edx, r14d; AclSize
0x1803eab99  mov     rcx, rdi; Acl
0x1803eab9c  call    cs:__imp_RtlCreateAcl
0x1803eaba2  test    eax, eax
0x1803eaba4  jns     short loc_1803EABB0
0x1803eaba6  mov     edx, 49h ; 'I'
0x1803eabab  jmp     loc_1803EAC36
0x1803eabb0  mov     rcx, [rbp+Dacl]; Acl
0x1803eabb4  lea     r8, [rbp+Ace]; Ace
0x1803eabb8  xor     edx, edx; AceIndex
0x1803eabba  mov     [rbp+Ace], 0
0x1803eabc2  call    cs:__imp_RtlGetAce
0x1803eabc8  test    eax, eax
0x1803eabca  jns     short loc_1803EABD3
0x1803eabcc  mov     edx, 4Ch ; 'L'
0x1803eabd1  jmp     short loc_1803EAC36
0x1803eabd3  mov     eax, dword ptr [rbp+Information+4]
0x1803eabd6  xor     r8d, r8d; StartingAceIndex
0x1803eabd9  mov     r9, [rbp+Ace]; AceList
0x1803eabdd  add     eax, 0FFFFFFF8h
0x1803eabe0  mov     edx, [rbp+AclRevision]; AceRevision
0x1803eabe3  mov     rcx, rdi; Acl
0x1803eabe6  mov     [rsp+70h+AceListLength], eax; int
0x1803eabea  call    cs:__imp_RtlAddAce
0x1803eabf0  test    eax, eax
0x1803eabf2  jns     short loc_1803EABFB
0x1803eabf4  mov     edx, 4Eh ; 'N'
0x1803eabf9  jmp     short loc_1803EAC36
0x1803eabfb  mov     edx, [rbp+AclRevision]; Revision
0x1803eabfe  mov     r9, r15; Sid
0x1803eac01  mov     r8d, esi; AccessMask
0x1803eac04  mov     rcx, rdi; Acl
0x1803eac07  call    cs:__imp_RtlAddAccessAllowedAce
0x1803eac0d  test    eax, eax
0x1803eac0f  jns     short loc_1803EAC18
0x1803eac11  mov     edx, 51h ; 'Q'
0x1803eac16  jmp     short loc_1803EAC36
0x1803eac18  xor     r9d, r9d; DaclDefaulted
0x1803eac1b  mov     r8, rdi; Dacl
0x1803eac1e  mov     dl, 1; DaclPresent
0x1803eac20  mov     rcx, r12; SecurityDescriptor
0x1803eac23  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1803eac29  test    eax, eax
0x1803eac2b  jns     loc_1803EAACA
0x1803eac31  mov     edx, 53h ; 'S'; void *
0x1803eac36  mov     rcx, [rbp+38h]; this
0x1803eac3a  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1803eac41  mov     r9d, eax; char *
0x1803eac44  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1803eac49  mov     rcx, rdi; void *
0x1803eac4c  mov     ebx, eax
0x1803eac4e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1803eac53  jmp     loc_1803EAB8B
```
