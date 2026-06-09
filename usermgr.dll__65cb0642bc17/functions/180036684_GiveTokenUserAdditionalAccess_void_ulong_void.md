# GiveTokenUserAdditionalAccess(void *,ulong,void *)

- ea: `0x180036684`
- end: `0x1800369df`
- name: `?GiveTokenUserAdditionalAccess@@YAJPEAXK0@Z`
- size: `859`
- prototype: `__int64 __fastcall(HANDLE handle, unsigned int, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c650`
- `0x1800b38ec`

## callees

- `0x18000acdc`
- `0x180036684`
- `0x18004e4e8`
- `0x18004e508`
- `0x18006f1c9`
- `0x1800de450`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800368a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800368ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800368a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800368ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800367be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800367be`
- `ntdll!RtlAddAccessAllowedAce` at `0x180036854`
- `ntdll!RtlAddAccessAllowedAce` at `0x180036854`
- `ntdll!RtlAddAce` at `0x180036832`
- `ntdll!RtlAddAce` at `0x180036832`
- `ntdll!RtlCreateAcl` at `0x1800367ec`
- `ntdll!RtlCreateAcl` at `0x1800367ec`
- `ntdll!RtlQueryInformationAcl` at `0x180036767`
- `ntdll!RtlQueryInformationAcl` at `0x18003678b`
- `ntdll!RtlQueryInformationAcl` at `0x180036767`
- `ntdll!RtlQueryInformationAcl` at `0x18003678b`
- `ntdll!RtlLengthSid` at `0x18003670b`
- `ntdll!RtlLengthSid` at `0x18003670b`
- `ntdll!RtlGetAce` at `0x180036808`
- `ntdll!RtlGetAce` at `0x180036808`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180036745`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180036745`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18003688f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18003688f`

## string_xrefs

- `0x1800368dd`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x1800368f2`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180036907`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18003691c`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180036931`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180036946`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18003695b`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180036970`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180036985`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18003699d`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x1800369b5`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x1800369cd`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GiveTokenUserAdditionalAccess(HANDLE handle, __int64 a2, void *a3)
{
  ULONG v5; // ebx
  DWORD SecurityInfo; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  ULONG v9; // ebx
  struct _ACL *v10; // rax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  DWORD v15; // eax
  int ppsidGroup; // [rsp+20h] [rbp-39h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-39h]
  int ppsidGroupb; // [rsp+20h] [rbp-39h]
  unsigned int ppsidGroupc; // [rsp+20h] [rbp-39h]
  ULONG AclRevision; // [rsp+40h] [rbp-19h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-11h] BYREF
  PACL Acl; // [rsp+50h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+58h] [rbp-1h] BYREF
  PVOID Ace[3]; // [rsp+60h] [rbp+7h] BYREF
  char v26; // [rsp+78h] [rbp+1Fh]
  __int64 Information; // [rsp+80h] [rbp+27h] BYREF
  int v28; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  Acl = 0;
  pDacl = 0;
  hMem = 0;
  Information = 0;
  v28 = 0;
  AclRevision = 0;
  Ace[0] = 0;
  if ( !handle )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)0x80070057LL,
      ppsidGroup);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)0x80070057LL,
      ppsidGroup);
  Ace[1] = &pDacl;
  Ace[2] = &hMem;
  v26 = 1;
  v5 = RtlLengthSid(a3);
  SecurityInfo = GetSecurityInfo(handle, SE_KERNEL_OBJECT, 4u, 0, 0, &Acl, 0, &hMem);
  if ( SecurityInfo )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)SecurityInfo,
      ppsidGroupa);
  v7 = RtlQueryInformationAcl(Acl, &Information, 0xCu, AclSizeInformation);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v7,
      ppsidGroupa);
  v8 = RtlQueryInformationAcl(Acl, &AclRevision, 4u, AclRevisionInformation);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x2AE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v8,
      ppsidGroupa);
  v9 = (HIDWORD(Information) + 11 + v5) & 0xFFFFFFFC;
  if ( v9 > 0xFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)0x80010139LL,
      ppsidGroupa);
  v10 = (struct _ACL *)LocalAlloc(0, v9);
  pDacl = v10;
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)0x8007000ELL,
      ppsidGroupa);
  memset_0(v10, 0, v9);
  v11 = RtlCreateAcl(pDacl, v9, AclRevision);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v11,
      ppsidGroupa);
  v12 = RtlGetAce(Acl, 0, Ace);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v12,
      ppsidGroupa);
  v13 = RtlAddAce(pDacl, AclRevision, 0, Ace[0], HIDWORD(Information) - 8);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x2C8,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v13,
      ppsidGroupb);
  v14 = RtlAddAccessAllowedAce(pDacl, AclRevision, 0xF01FFu, a3);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v14,
      ppsidGroupb);
  v15 = SetSecurityInfo(handle, SE_KERNEL_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v15 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)v15,
      ppsidGroupc);
  LocalFree(pDacl);
  LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180036684  mov     [rsp-8+arg_8], rbx
0x180036689  mov     [rsp-8+arg_18], rsi
0x18003668e  push    rbp
0x18003668f  push    rdi
0x180036690  push    r14
0x180036692  lea     rbp, [rsp-47h]
0x180036697  sub     rsp, 0A0h
0x18003669e  mov     rax, cs:__security_cookie
0x1800366a5  xor     rax, rsp
0x1800366a8  mov     [rbp+57h+var_20], rax
0x1800366ac  mov     rdi, r8
0x1800366af  mov     r14, rcx
0x1800366b2  mov     [rbp+57h+Acl], 0
0x1800366ba  mov     [rbp+57h+pDacl], 0
0x1800366c2  mov     [rbp+57h+hMem], 0
0x1800366ca  xor     eax, eax
0x1800366cc  mov     [rbp+57h+Information], rax
0x1800366d0  mov     [rbp+57h+var_28], eax
0x1800366d3  mov     [rbp+57h+AclRevision], eax
0x1800366d6  mov     [rbp+57h+Ace], rax
0x1800366da  mov     rcx, [rbp+5Fh]; this
0x1800366de  test    r14, r14
0x1800366e1  jz      loc_180036997
0x1800366e7  mov     rcx, [rbp+5Fh]; this
0x1800366eb  test    r8, r8
0x1800366ee  jz      loc_1800369AF
0x1800366f4  lea     rax, [rbp+57h+pDacl]
0x1800366f8  mov     [rbp+57h+var_48], rax
0x1800366fc  lea     rax, [rbp+57h+hMem]
0x180036700  mov     [rbp+57h+var_40], rax
0x180036704  mov     [rbp+57h+var_38], 1
0x180036708  mov     rcx, r8; Sid
0x18003670b  call    cs:__imp_RtlLengthSid
0x180036711  mov     ebx, eax
0x180036713  lea     rax, [rbp+57h+hMem]
0x180036717  mov     [rsp+0B0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18003671c  mov     [rsp+0B0h+ppSacl], 0; ppSacl
0x180036725  lea     rax, [rbp+57h+Acl]
0x180036729  mov     [rsp+0B0h+ppDacl], rax; ppDacl
0x18003672e  mov     [rsp+0B0h+ppsidGroup], 0; int
0x180036737  xor     r9d, r9d; ppsidOwner
0x18003673a  lea     edx, [r9+6]; ObjectType
0x18003673e  lea     r8d, [r9+4]; SecurityInfo
0x180036742  mov     rcx, r14; handle
0x180036745  call    cs:__imp_GetSecurityInfo
0x18003674b  mov     rcx, [rbp+5Fh]; this
0x18003674f  test    eax, eax
0x180036751  jnz     loc_1800368EF
0x180036757  lea     r9d, [rax+2]; InformationClass
0x18003675b  lea     r8d, [rax+0Ch]; InformationLength
0x18003675f  lea     rdx, [rbp+57h+Information]; Information
0x180036763  mov     rcx, [rbp+57h+Acl]; Acl
0x180036767  call    cs:__imp_RtlQueryInformationAcl
0x18003676d  mov     rcx, [rbp+5Fh]; this
0x180036771  test    eax, eax
0x180036773  js      loc_180036919
0x180036779  mov     r9d, 1; InformationClass
0x18003677f  lea     r8d, [r9+3]; InformationLength
0x180036783  lea     rdx, [rbp+57h+AclRevision]; Information
0x180036787  mov     rcx, [rbp+57h+Acl]; Acl
0x18003678b  call    cs:__imp_RtlQueryInformationAcl
0x180036791  mov     rcx, [rbp+5Fh]; this
0x180036795  test    eax, eax
0x180036797  js      loc_18003692E
0x18003679d  mov     eax, dword ptr [rbp+57h+Information+4]
0x1800367a0  add     eax, 0Bh
0x1800367a3  add     ebx, eax
0x1800367a5  and     ebx, 0FFFFFFFCh
0x1800367a8  mov     rcx, [rbp+5Fh]; this
0x1800367ac  cmp     ebx, 0FFFFh
0x1800367b2  ja      loc_1800368D7
0x1800367b8  mov     esi, ebx
0x1800367ba  mov     edx, ebx; uBytes
0x1800367bc  xor     ecx, ecx; uFlags
0x1800367be  call    cs:__imp_LocalAlloc
0x1800367c4  mov     [rbp+57h+pDacl], rax
0x1800367c8  mov     rcx, [rbp+5Fh]; this
0x1800367cc  test    rax, rax
0x1800367cf  jz      loc_1800369C7
0x1800367d5  mov     r8d, esi; Size
0x1800367d8  xor     edx, edx; Val
0x1800367da  mov     rcx, rax; void *
0x1800367dd  call    memset_0
0x1800367e2  mov     r8d, [rbp+57h+AclRevision]; AclRevision
0x1800367e6  mov     edx, ebx; AclSize
0x1800367e8  mov     rcx, [rbp+57h+pDacl]; Acl
0x1800367ec  call    cs:__imp_RtlCreateAcl
0x1800367f2  mov     rcx, [rbp+5Fh]; this
0x1800367f6  test    eax, eax
0x1800367f8  js      loc_180036943
0x1800367fe  lea     r8, [rbp+57h+Ace]; Ace
0x180036802  xor     edx, edx; AceIndex
0x180036804  mov     rcx, [rbp+57h+Acl]; Acl
0x180036808  call    cs:__imp_RtlGetAce
0x18003680e  mov     rcx, [rbp+5Fh]; this
0x180036812  test    eax, eax
0x180036814  js      loc_180036958
0x18003681a  mov     eax, dword ptr [rbp+57h+Information+4]
0x18003681d  add     eax, 0FFFFFFF8h
0x180036820  mov     dword ptr [rsp+0B0h+ppsidGroup], eax; int
0x180036824  mov     r9, [rbp+57h+Ace]; AceList
0x180036828  xor     r8d, r8d; StartingAceIndex
0x18003682b  mov     edx, [rbp+57h+AclRevision]; AceRevision
0x18003682e  mov     rcx, [rbp+57h+pDacl]; Acl
0x180036832  call    cs:__imp_RtlAddAce
0x180036838  mov     rcx, [rbp+5Fh]; this
0x18003683c  test    eax, eax
0x18003683e  js      loc_18003696D
0x180036844  mov     r9, rdi; Sid
0x180036847  mov     r8d, 0F01FFh; AccessMask
0x18003684d  mov     edx, [rbp+57h+AclRevision]; Revision
0x180036850  mov     rcx, [rbp+57h+pDacl]; Acl
0x180036854  call    cs:__imp_RtlAddAccessAllowedAce
0x18003685a  mov     rcx, [rbp+5Fh]; this
0x18003685e  test    eax, eax
0x180036860  js      loc_180036982
0x180036866  mov     [rsp+0B0h+ppSacl], 0; pSacl
0x18003686f  mov     rax, [rbp+57h+pDacl]
0x180036873  mov     [rsp+0B0h+ppDacl], rax; pDacl
0x180036878  mov     [rsp+0B0h+ppsidGroup], 0; unsigned int
0x180036881  xor     r9d, r9d; psidOwner
0x180036884  lea     edx, [r9+6]; ObjectType
0x180036888  lea     r8d, [r9+4]; SecurityInfo
0x18003688c  mov     rcx, r14; handle
0x18003688f  call    cs:__imp_SetSecurityInfo
0x180036895  mov     rcx, [rbp+5Fh]; this
0x180036899  test    eax, eax
0x18003689b  jnz     short loc_180036904
0x18003689d  mov     rcx, [rbp+57h+pDacl]; hMem
0x1800368a1  call    cs:__imp_LocalFree
0x1800368a7  mov     rcx, [rbp+57h+hMem]; hMem
0x1800368ab  call    cs:__imp_LocalFree
0x1800368b1  xor     eax, eax
0x1800368b3  mov     rcx, [rbp+57h+var_20]
0x1800368b7  xor     rcx, rsp; StackCookie
0x1800368ba  call    __security_check_cookie
0x1800368bf  lea     r11, [rsp+0B0h+var_10]
0x1800368c7  mov     rbx, [r11+28h]
0x1800368cb  mov     rsi, [r11+38h]
0x1800368cf  mov     rsp, r11
0x1800368d2  pop     r14
0x1800368d4  pop     rdi
0x1800368d5  pop     rbp
0x1800368d6  retn
0x1800368d7  mov     r9d, 80010139h; char *
0x1800368dd  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800368e4  mov     edx, 2B2h; void *
0x1800368e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800368ef  mov     r9d, eax; char *
0x1800368f2  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800368f9  mov     edx, 2A1h; void *
0x1800368fe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180036904  mov     r9d, eax; char *
0x180036907  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18003690e  mov     edx, 2D8h; void *
0x180036913  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180036919  mov     r9d, eax; char *
0x18003691c  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180036923  mov     edx, 2A8h; void *
0x180036928  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18003692e  mov     r9d, eax; char *
0x180036931  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180036938  mov     edx, 2AEh; void *
0x18003693d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036943  mov     r9d, eax; char *
0x180036946  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18003694d  mov     edx, 2BCh; void *
0x180036952  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036958  mov     r9d, eax; char *
0x18003695b  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180036962  mov     edx, 2C1h; void *
0x180036967  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18003696d  mov     r9d, eax; char *
0x180036970  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180036977  mov     edx, 2C8h; void *
0x18003697c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036982  mov     r9d, eax; char *
0x180036985  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18003698c  mov     edx, 2CEh; void *
0x180036991  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036997  mov     r9d, 80070057h; char *
0x18003699d  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800369a4  mov     edx, 28Dh; void *
0x1800369a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800369af  mov     r9d, 80070057h; char *
0x1800369b5  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800369bc  mov     edx, 28Eh; void *
0x1800369c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800369c7  mov     r9d, 8007000Eh; char *
0x1800369cd  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800369d4  mov     edx, 2B5h; void *
0x1800369d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
