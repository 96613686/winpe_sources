# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x1803f9610`
- end: `0x1803f98ab`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `667`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803f8c20`

## callees

- `0x180038f50`
- `0x1801884f8`
- `0x18035fa60`
- `0x1803b1f60`
- `0x1803f9610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803f9791`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803f9791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f977a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f977a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1803f9870`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1803f9870`
- `ntdll!RtlAddAccessAllowedAce` at `0x1803f984e`
- `ntdll!RtlAddAccessAllowedAce` at `0x1803f984e`
- `ntdll!RtlAddAce` at `0x1803f982b`
- `ntdll!RtlAddAce` at `0x1803f982b`
- `ntdll!RtlGetAce` at `0x1803f97fd`
- `ntdll!RtlGetAce` at `0x1803f97fd`
- `ntdll!RtlCreateAcl` at `0x1803f97d1`
- `ntdll!RtlCreateAcl` at `0x1803f97d1`
- `ntdll!RtlLengthSid` at `0x1803f9763`
- `ntdll!RtlLengthSid` at `0x1803f9763`
- `ntdll!RtlQueryInformationAcl` at `0x1803f9713`
- `ntdll!RtlQueryInformationAcl` at `0x1803f9746`
- `ntdll!RtlQueryInformationAcl` at `0x1803f9713`
- `ntdll!RtlQueryInformationAcl` at `0x1803f9746`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1803f9659`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1803f9659`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1803f969f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1803f969f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1803f96bf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1803f96bf`

## string_xrefs

- `0x1803f9672`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803f97a9`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803f988d`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

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
0x1803f9610  push    rbp
0x1803f9612  push    rbx
0x1803f9613  push    rsi
0x1803f9614  push    rdi
0x1803f9615  push    r12
0x1803f9617  push    r14
0x1803f9619  push    r15
0x1803f961b  mov     rbp, rsp
0x1803f961e  sub     rsp, 70h
0x1803f9622  mov     rax, cs:__security_cookie
0x1803f9629  xor     rax, rsp
0x1803f962c  mov     [rbp+var_10], rax
0x1803f9630  mov     r12, [rbp+SecurityDescriptor]
0x1803f9634  mov     r14, r9
0x1803f9637  mov     esi, r8d
0x1803f963a  mov     [rbp+DaclPresent], 0
0x1803f963e  mov     r15, rdx
0x1803f9641  mov     [rbp+Dacl], 0
0x1803f9649  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1803f964d  mov     [rbp+DaclDefaulted], 0
0x1803f9651  lea     r8, [rbp+Dacl]; Dacl
0x1803f9655  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1803f9659  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1803f9660  nop     dword ptr [rax+rax+00h]
0x1803f9665  test    eax, eax
0x1803f9667  jns     short loc_1803F9683
0x1803f9669  mov     edx, 29h ; ')'; void *
0x1803f966e  mov     rcx, [rbp+38h]; this
0x1803f9672  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1803f9679  mov     r9d, eax; char *
0x1803f967c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1803f9681  jmp     short loc_1803F96E2
0x1803f9683  xor     ebx, ebx
0x1803f9685  mov     rcx, [rbp+Dacl]; Acl
0x1803f9689  movzx   eax, word ptr [rcx+4]
0x1803f968d  cmp     ebx, eax
0x1803f968f  jnb     short loc_1803F96FE
0x1803f9691  lea     r8, [rbp+pAce]; pAce
0x1803f9695  mov     [rbp+pAce], 0
0x1803f969d  mov     edx, ebx; dwAceIndex
0x1803f969f  call    cs:__imp_GetAce
0x1803f96a6  nop     dword ptr [rax+rax+00h]
0x1803f96ab  test    eax, eax
0x1803f96ad  jz      short loc_1803F96D8
0x1803f96af  mov     rdi, [rbp+pAce]
0x1803f96b3  cmp     byte ptr [rdi], 0
0x1803f96b6  jnz     short loc_1803F96D8
0x1803f96b8  lea     rcx, [rdi+8]; pSid1
0x1803f96bc  mov     rdx, r15; pSid2
0x1803f96bf  call    cs:__imp_EqualSid
0x1803f96c6  nop     dword ptr [rax+rax+00h]
0x1803f96cb  test    eax, eax
0x1803f96cd  jz      short loc_1803F96D8
0x1803f96cf  mov     eax, [rdi+4]
0x1803f96d2  and     eax, esi
0x1803f96d4  cmp     eax, esi
0x1803f96d6  jz      short loc_1803F96DC
0x1803f96d8  inc     ebx
0x1803f96da  jmp     short loc_1803F9685
0x1803f96dc  mov     byte ptr [r14], 1
0x1803f96e0  xor     eax, eax
0x1803f96e2  mov     rcx, [rbp+var_10]
0x1803f96e6  xor     rcx, rsp; StackCookie
0x1803f96e9  call    __security_check_cookie
0x1803f96ee  add     rsp, 70h
0x1803f96f2  pop     r15
0x1803f96f4  pop     r14
0x1803f96f6  pop     r12
0x1803f96f8  pop     rdi
0x1803f96f9  pop     rsi
0x1803f96fa  pop     rbx
0x1803f96fb  pop     rbp
0x1803f96fc  retn
0x1803f96fe  xor     eax, eax
0x1803f9700  lea     rdx, [rbp+Information]; Information
0x1803f9704  mov     [rbp+Information], rax
0x1803f9708  mov     [rbp+var_18], eax
0x1803f970b  lea     r9d, [rax+2]; InformationClass
0x1803f970f  lea     r8d, [rax+0Ch]; InformationLength
0x1803f9713  call    cs:__imp_RtlQueryInformationAcl
0x1803f971a  nop     dword ptr [rax+rax+00h]
0x1803f971f  test    eax, eax
0x1803f9721  jns     short loc_1803F972D
0x1803f9723  mov     edx, 3Dh ; '='
0x1803f9728  jmp     loc_1803F966E
0x1803f972d  mov     rcx, [rbp+Dacl]; Acl
0x1803f9731  lea     rdx, [rbp+AclRevision]; Information
0x1803f9735  mov     r9d, 1; InformationClass
0x1803f973b  mov     [rbp+AclRevision], 0
0x1803f9742  lea     r8d, [r9+3]; InformationLength
0x1803f9746  call    cs:__imp_RtlQueryInformationAcl
0x1803f974d  nop     dword ptr [rax+rax+00h]
0x1803f9752  test    eax, eax
0x1803f9754  jns     short loc_1803F9760
0x1803f9756  mov     edx, 40h ; '@'
0x1803f975b  jmp     loc_1803F966E
0x1803f9760  mov     rcx, r15; Sid
0x1803f9763  call    cs:__imp_RtlLengthSid
0x1803f976a  nop     dword ptr [rax+rax+00h]
0x1803f976f  mov     r14d, dword ptr [rbp+Information+4]
0x1803f9773  add     r14d, 8
0x1803f9777  add     r14d, eax
0x1803f977a  call    cs:__imp_GetProcessHeap
0x1803f9781  nop     dword ptr [rax+rax+00h]
0x1803f9786  mov     r8d, r14d; dwBytes
0x1803f9789  mov     edx, 8; dwFlags
0x1803f978e  mov     rcx, rax; hHeap
0x1803f9791  call    cs:__imp_HeapAlloc
0x1803f9798  nop     dword ptr [rax+rax+00h]
0x1803f979d  mov     rdi, rax
0x1803f97a0  test    rax, rax
0x1803f97a3  jnz     short loc_1803F97C7
0x1803f97a5  mov     rcx, [rbp+38h]; this
0x1803f97a9  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1803f97b0  mov     ebx, 8007000Eh
0x1803f97b5  lea     edx, [rax+47h]; void *
0x1803f97b8  mov     r9d, ebx; char *
0x1803f97bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803f97c0  mov     eax, ebx
0x1803f97c2  jmp     loc_1803F96E2
0x1803f97c7  mov     r8d, [rbp+AclRevision]; AclRevision
0x1803f97cb  mov     edx, r14d; AclSize
0x1803f97ce  mov     rcx, rdi; Acl
0x1803f97d1  call    cs:__imp_RtlCreateAcl
0x1803f97d8  nop     dword ptr [rax+rax+00h]
0x1803f97dd  test    eax, eax
0x1803f97df  jns     short loc_1803F97EB
0x1803f97e1  mov     edx, 49h ; 'I'
0x1803f97e6  jmp     loc_1803F9889
0x1803f97eb  mov     rcx, [rbp+Dacl]; Acl
0x1803f97ef  lea     r8, [rbp+Ace]; Ace
0x1803f97f3  xor     edx, edx; AceIndex
0x1803f97f5  mov     [rbp+Ace], 0
0x1803f97fd  call    cs:__imp_RtlGetAce
0x1803f9804  nop     dword ptr [rax+rax+00h]
0x1803f9809  test    eax, eax
0x1803f980b  jns     short loc_1803F9814
0x1803f980d  mov     edx, 4Ch ; 'L'
0x1803f9812  jmp     short loc_1803F9889
0x1803f9814  mov     eax, dword ptr [rbp+Information+4]
0x1803f9817  xor     r8d, r8d; StartingAceIndex
0x1803f981a  mov     r9, [rbp+Ace]; AceList
0x1803f981e  add     eax, 0FFFFFFF8h
0x1803f9821  mov     edx, [rbp+AclRevision]; AceRevision
0x1803f9824  mov     rcx, rdi; Acl
0x1803f9827  mov     [rsp+70h+AceListLength], eax; int
0x1803f982b  call    cs:__imp_RtlAddAce
0x1803f9832  nop     dword ptr [rax+rax+00h]
0x1803f9837  test    eax, eax
0x1803f9839  jns     short loc_1803F9842
0x1803f983b  mov     edx, 4Eh ; 'N'
0x1803f9840  jmp     short loc_1803F9889
0x1803f9842  mov     edx, [rbp+AclRevision]; Revision
0x1803f9845  mov     r9, r15; Sid
0x1803f9848  mov     r8d, esi; AccessMask
0x1803f984b  mov     rcx, rdi; Acl
0x1803f984e  call    cs:__imp_RtlAddAccessAllowedAce
0x1803f9855  nop     dword ptr [rax+rax+00h]
0x1803f985a  test    eax, eax
0x1803f985c  jns     short loc_1803F9865
0x1803f985e  mov     edx, 51h ; 'Q'
0x1803f9863  jmp     short loc_1803F9889
0x1803f9865  xor     r9d, r9d; DaclDefaulted
0x1803f9868  mov     r8, rdi; Dacl
0x1803f986b  mov     dl, 1; DaclPresent
0x1803f986d  mov     rcx, r12; SecurityDescriptor
0x1803f9870  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1803f9877  nop     dword ptr [rax+rax+00h]
0x1803f987c  test    eax, eax
0x1803f987e  jns     loc_1803F96E0
0x1803f9884  mov     edx, 53h ; 'S'; void *
0x1803f9889  mov     rcx, [rbp+38h]; this
0x1803f988d  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1803f9894  mov     r9d, eax; char *
0x1803f9897  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1803f989c  mov     rcx, rdi; void *
0x1803f989f  mov     ebx, eax
0x1803f98a1  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1803f98a6  jmp     loc_1803F97C0
```
