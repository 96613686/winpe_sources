# MpRemoveAdminAndNonAdminSidsFromSd

- ea: `0x140080374`
- end: `0x140080825`
- name: `MpRemoveAdminAndNonAdminSidsFromSd`
- size: `1201`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007d7bc`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140011bc0`
- `0x140080374`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140080423`
- `ntoskrnl!RtlInitializeSid` at `0x1400804c2`
- `ntoskrnl!RtlInitializeSid` at `0x14008055d`
- `ntoskrnl!RtlInitializeSid` at `0x140080423`
- `ntoskrnl!RtlInitializeSid` at `0x1400804c2`
- `ntoskrnl!RtlInitializeSid` at `0x14008055d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080468`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080507`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400805a3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400805f4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080468`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080507`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400805a3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400805f4`
- `ntoskrnl!RtlGetAce` at `0x140080723`
- `ntoskrnl!RtlGetAce` at `0x140080723`
- `ntoskrnl!RtlDeleteAce` at `0x140080761`
- `ntoskrnl!RtlDeleteAce` at `0x140080761`
- `ntoskrnl!RtlEqualSid` at `0x14008074a`
- `ntoskrnl!RtlEqualSid` at `0x140080776`
- `ntoskrnl!RtlEqualSid` at `0x14008078e`
- `ntoskrnl!RtlEqualSid` at `0x14008074a`
- `ntoskrnl!RtlEqualSid` at `0x140080776`
- `ntoskrnl!RtlEqualSid` at `0x14008078e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14008064f`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14008064f`

## pseudocode

```c
__int64 __fastcall MpRemoveAdminAndNonAdminSidsFromSd(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  unsigned int DaclSecurityDescriptor; // ebx
  __int64 v4; // rdx
  PULONG v5; // rax
  PULONG v6; // rax
  PULONG v7; // rax
  PULONG v8; // rax
  struct _ACL *v9; // rcx
  unsigned int AceCount; // r15d
  ULONG v11; // edi
  unsigned int i; // esi
  char *v13; // r14
  int v14; // [rsp+20h] [rbp-E0h]
  PACL Dacl; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Ace; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 DaclPresent; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 DaclDefaulted[3]; // [rsp+41h] [rbp-BFh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+44h] [rbp-BCh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+4Ch] [rbp-B4h] BYREF
  _BYTE v21[80]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Sid[80]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE Sid2[80]; // [rsp+100h] [rbp+0h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v19.Value = 0;
  *(_WORD *)&v19.Value[4] = 1280;
  memset(Sid, 0, 0x44u);
  memset(Sid2, 0, 0x44u);
  memset(v21, 0, 0x44u);
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  Dacl = 0;
  if ( !SecurityDescriptor )
    return 3221225485LL;
  DaclSecurityDescriptor = RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  if ( (DaclSecurityDescriptor & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 44;
    goto LABEL_57;
  }
  v5 = RtlSubAuthoritySid(Sid, 0);
  if ( !v5 )
  {
    DaclSecurityDescriptor = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 45;
    goto LABEL_11;
  }
  *v5 = 0;
  DaclSecurityDescriptor = RtlInitializeSid(Sid2, &v19, 1u);
  if ( (DaclSecurityDescriptor & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 46;
    goto LABEL_57;
  }
  v6 = RtlSubAuthoritySid(Sid2, 0);
  if ( !v6 )
  {
    DaclSecurityDescriptor = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 47;
    goto LABEL_11;
  }
  *v6 = 11;
  DaclSecurityDescriptor = RtlInitializeSid(v21, &v19, 2u);
  if ( (DaclSecurityDescriptor & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 48;
    goto LABEL_57;
  }
  v7 = RtlSubAuthoritySid(v21, 0);
  if ( !v7 )
  {
    DaclSecurityDescriptor = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 49;
    goto LABEL_11;
  }
  *v7 = 32;
  v8 = RtlSubAuthoritySid(v21, 1u);
  if ( !v8 )
  {
    DaclSecurityDescriptor = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 50;
    goto LABEL_11;
  }
  *v8 = 544;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, DaclDefaulted);
  if ( (DaclSecurityDescriptor & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 51;
LABEL_57:
    v14 = DaclSecurityDescriptor;
    _mm_lfence();
    goto LABEL_58;
  }
  if ( !DaclPresent )
  {
    DaclSecurityDescriptor = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return DaclSecurityDescriptor;
    v4 = 52;
    goto LABEL_11;
  }
  v9 = Dacl;
  if ( Dacl )
  {
    AceCount = Dacl->AceCount;
    v11 = 0;
    for ( i = 0; i < AceCount; ++i )
    {
      Ace = 0;
      DaclSecurityDescriptor = RtlGetAce(v9, v11, &Ace);
      if ( (DaclSecurityDescriptor & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v4 = 54;
          goto LABEL_57;
        }
        return DaclSecurityDescriptor;
      }
      if ( !*(_BYTE *)Ace )
      {
        v13 = (char *)Ace + 8;
        if ( RtlEqualSid((char *)Ace + 8, Sid) || RtlEqualSid(v13, Sid2) || RtlEqualSid(v13, v21) )
          RtlDeleteAce(Dacl, v11);
        else
          ++v11;
      }
      v9 = Dacl;
    }
    return DaclSecurityDescriptor;
  }
  DaclSecurityDescriptor = -1073741823;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v4 = 53;
LABEL_11:
    v14 = -1073741823;
LABEL_58:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
      KeGetCurrentThread(),
      v14);
  }
  return DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x140080374  mov     [rsp-8+arg_8], rbx
0x140080379  mov     [rsp-8+arg_10], rsi
0x14008037e  mov     [rsp-8+arg_18], rdi
0x140080383  push    rbp
0x140080384  push    r12
0x140080386  push    r13
0x140080388  push    r14
0x14008038a  push    r15
0x14008038c  lea     rbp, [rsp-60h]
0x140080391  sub     rsp, 160h
0x140080398  mov     rax, cs:__security_cookie
0x14008039f  xor     rax, rsp
0x1400803a2  mov     [rbp+80h+var_30], rax
0x1400803a6  xor     r12d, r12d
0x1400803a9  mov     word ptr [rsp+180h+IdentifierAuthority.Value+4], 100h
0x1400803b0  mov     rdi, rcx
0x1400803b3  mov     dword ptr [rsp+180h+IdentifierAuthority.Value], r12d
0x1400803b8  xor     edx, edx; Val
0x1400803ba  mov     dword ptr [rsp+180h+var_13C.Value], r12d
0x1400803bf  lea     rcx, [rbp+80h+Sid]; void *
0x1400803c3  mov     word ptr [rsp+180h+var_13C.Value+4], 500h
0x1400803ca  lea     ebx, [r12+44h]
0x1400803cf  mov     r8d, ebx; Size
0x1400803d2  lea     r13d, [r12+1]
0x1400803d7  call    memset
0x1400803dc  mov     r8d, ebx; Size
0x1400803df  lea     rcx, [rbp+80h+Sid2]; void *
0x1400803e3  xor     edx, edx; Val
0x1400803e5  call    memset
0x1400803ea  mov     r8d, ebx; Size
0x1400803ed  lea     rcx, [rsp+180h+var_120]; void *
0x1400803f2  xor     edx, edx; Val
0x1400803f4  call    memset
0x1400803f9  mov     [rsp+180h+DaclPresent], r12b
0x1400803fe  mov     [rsp+180h+DaclDefaulted], r12b
0x140080403  mov     [rsp+180h+Dacl], r12
0x140080408  test    rdi, rdi
0x14008040b  jnz     short loc_140080417
0x14008040d  mov     eax, 0C000000Dh
0x140080412  jmp     loc_1400807F7
0x140080417  mov     r8b, r13b; SubAuthorityCount
0x14008041a  lea     rdx, [rsp+180h+IdentifierAuthority]; IdentifierAuthority
0x14008041f  lea     rcx, [rbp+80h+Sid]; Sid
0x140080423  call    cs:__imp_RtlInitializeSid
0x14008042a  nop     dword ptr [rax+rax+00h]
0x14008042f  mov     ebx, eax
0x140080431  test    eax, eax
0x140080433  jns     short loc_140080462
0x140080435  mov     rcx, cs:WPP_GLOBAL_Control
0x14008043c  lea     rax, WPP_GLOBAL_Control
0x140080443  cmp     rcx, rax
0x140080446  jz      loc_1400807F5
0x14008044c  mov     ecx, [rcx+2Ch]
0x14008044f  test    r13b, cl
0x140080452  jz      loc_1400807F5
0x140080458  mov     edx, 2Ch ; ','
0x14008045d  jmp     loc_1400807CE
0x140080462  xor     edx, edx; SubAuthority
0x140080464  lea     rcx, [rbp+80h+Sid]; Sid
0x140080468  call    cs:__imp_RtlSubAuthoritySid
0x14008046f  nop     dword ptr [rax+rax+00h]
0x140080474  test    rax, rax
0x140080477  jnz     short loc_1400804B3
0x140080479  mov     ebx, 0C0000001h
0x14008047e  mov     rcx, cs:WPP_GLOBAL_Control
0x140080485  lea     rax, WPP_GLOBAL_Control
0x14008048c  cmp     rcx, rax
0x14008048f  jz      loc_1400807F5
0x140080495  mov     eax, [rcx+2Ch]
0x140080498  test    r13b, al
0x14008049b  jz      loc_1400807F5
0x1400804a1  mov     edx, 2Dh ; '-'
0x1400804a6  mov     [rsp+180h+var_160], 0C0000001h
0x1400804ae  jmp     loc_1400807D5
0x1400804b3  mov     r8b, r13b; SubAuthorityCount
0x1400804b6  mov     [rax], r12d
0x1400804b9  lea     rdx, [rsp+180h+var_13C]; IdentifierAuthority
0x1400804be  lea     rcx, [rbp+80h+Sid2]; Sid
0x1400804c2  call    cs:__imp_RtlInitializeSid
0x1400804c9  nop     dword ptr [rax+rax+00h]
0x1400804ce  mov     ebx, eax
0x1400804d0  test    eax, eax
0x1400804d2  jns     short loc_140080501
0x1400804d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400804db  lea     rax, WPP_GLOBAL_Control
0x1400804e2  cmp     rcx, rax
0x1400804e5  jz      loc_1400807F5
0x1400804eb  mov     eax, [rcx+2Ch]
0x1400804ee  test    r13b, al
0x1400804f1  jz      loc_1400807F5
0x1400804f7  mov     edx, 2Eh ; '.'
0x1400804fc  jmp     loc_1400807CE
0x140080501  xor     edx, edx; SubAuthority
0x140080503  lea     rcx, [rbp+80h+Sid2]; Sid
0x140080507  call    cs:__imp_RtlSubAuthoritySid
0x14008050e  nop     dword ptr [rax+rax+00h]
0x140080513  test    rax, rax
0x140080516  jnz     short loc_14008054A
0x140080518  mov     ebx, 0C0000001h
0x14008051d  mov     rcx, cs:WPP_GLOBAL_Control
0x140080524  lea     rax, WPP_GLOBAL_Control
0x14008052b  cmp     rcx, rax
0x14008052e  jz      loc_1400807F5
0x140080534  mov     eax, [rcx+2Ch]
0x140080537  test    r13b, al
0x14008053a  jz      loc_1400807F5
0x140080540  mov     edx, 2Fh ; '/'
0x140080545  jmp     loc_1400804A6
0x14008054a  mov     r8b, 2; SubAuthorityCount
0x14008054d  mov     dword ptr [rax], 0Bh
0x140080553  lea     rdx, [rsp+180h+var_13C]; IdentifierAuthority
0x140080558  lea     rcx, [rsp+180h+var_120]; Sid
0x14008055d  call    cs:__imp_RtlInitializeSid
0x140080564  nop     dword ptr [rax+rax+00h]
0x140080569  mov     ebx, eax
0x14008056b  test    eax, eax
0x14008056d  jns     short loc_14008059C
0x14008056f  mov     rcx, cs:WPP_GLOBAL_Control
0x140080576  lea     rax, WPP_GLOBAL_Control
0x14008057d  cmp     rcx, rax
0x140080580  jz      loc_1400807F5
0x140080586  mov     eax, [rcx+2Ch]
0x140080589  test    r13b, al
0x14008058c  jz      loc_1400807F5
0x140080592  mov     edx, 30h ; '0'
0x140080597  jmp     loc_1400807CE
0x14008059c  xor     edx, edx; SubAuthority
0x14008059e  lea     rcx, [rsp+180h+var_120]; Sid
0x1400805a3  call    cs:__imp_RtlSubAuthoritySid
0x1400805aa  nop     dword ptr [rax+rax+00h]
0x1400805af  test    rax, rax
0x1400805b2  jnz     short loc_1400805E6
0x1400805b4  mov     ebx, 0C0000001h
0x1400805b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400805c0  lea     rax, WPP_GLOBAL_Control
0x1400805c7  cmp     rcx, rax
0x1400805ca  jz      loc_1400807F5
0x1400805d0  mov     eax, [rcx+2Ch]
0x1400805d3  test    r13b, al
0x1400805d6  jz      loc_1400807F5
0x1400805dc  mov     edx, 31h ; '1'
0x1400805e1  jmp     loc_1400804A6
0x1400805e6  mov     edx, r13d; SubAuthority
0x1400805e9  mov     dword ptr [rax], 20h ; ' '
0x1400805ef  lea     rcx, [rsp+180h+var_120]; Sid
0x1400805f4  call    cs:__imp_RtlSubAuthoritySid
0x1400805fb  nop     dword ptr [rax+rax+00h]
0x140080600  test    rax, rax
0x140080603  jnz     short loc_140080637
0x140080605  mov     ebx, 0C0000001h
0x14008060a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080611  lea     rax, WPP_GLOBAL_Control
0x140080618  cmp     rcx, rax
0x14008061b  jz      loc_1400807F5
0x140080621  mov     eax, [rcx+2Ch]
0x140080624  test    r13b, al
0x140080627  jz      loc_1400807F5
0x14008062d  mov     edx, 32h ; '2'
0x140080632  jmp     loc_1400804A6
0x140080637  lea     r9, [rsp+180h+DaclDefaulted]; DaclDefaulted
0x14008063c  mov     dword ptr [rax], 220h
0x140080642  lea     r8, [rsp+180h+Dacl]; Dacl
0x140080647  mov     rcx, rdi; SecurityDescriptor
0x14008064a  lea     rdx, [rsp+180h+DaclPresent]; DaclPresent
0x14008064f  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140080656  nop     dword ptr [rax+rax+00h]
0x14008065b  mov     ebx, eax
0x14008065d  test    eax, eax
0x14008065f  jns     short loc_14008068E
0x140080661  mov     rcx, cs:WPP_GLOBAL_Control
0x140080668  lea     rax, WPP_GLOBAL_Control
0x14008066f  cmp     rcx, rax
0x140080672  jz      loc_1400807F5
0x140080678  mov     eax, [rcx+2Ch]
0x14008067b  test    r13b, al
0x14008067e  jz      loc_1400807F5
0x140080684  mov     edx, 33h ; '3'
0x140080689  jmp     loc_1400807CE
0x14008068e  cmp     [rsp+180h+DaclPresent], r12b
0x140080693  jnz     short loc_1400806C7
0x140080695  mov     ebx, 0C0000001h
0x14008069a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400806a1  lea     rax, WPP_GLOBAL_Control
0x1400806a8  cmp     rcx, rax
0x1400806ab  jz      loc_1400807F5
0x1400806b1  mov     eax, [rcx+2Ch]
0x1400806b4  test    r13b, al
0x1400806b7  jz      loc_1400807F5
0x1400806bd  mov     edx, 34h ; '4'
0x1400806c2  jmp     loc_1400804A6
0x1400806c7  mov     rcx, [rsp+180h+Dacl]; Acl
0x1400806cc  test    rcx, rcx
0x1400806cf  jnz     short loc_140080703
0x1400806d1  mov     ebx, 0C0000001h
0x1400806d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400806dd  lea     rax, WPP_GLOBAL_Control
0x1400806e4  cmp     rcx, rax
0x1400806e7  jz      loc_1400807F5
0x1400806ed  mov     eax, [rcx+2Ch]
0x1400806f0  test    r13b, al
0x1400806f3  jz      loc_1400807F5
0x1400806f9  mov     edx, 35h ; '5'
0x1400806fe  jmp     loc_1400804A6
0x140080703  movzx   r15d, word ptr [rcx+4]
0x140080708  mov     edi, r12d
0x14008070b  mov     esi, r12d
0x14008070e  cmp     esi, r15d
0x140080711  jnb     loc_1400807F5
0x140080717  lea     r8, [rsp+180h+Ace]; Ace
0x14008071c  mov     [rsp+180h+Ace], r12
0x140080721  mov     edx, edi; AceIndex
0x140080723  call    cs:__imp_RtlGetAce
0x14008072a  nop     dword ptr [rax+rax+00h]
0x14008072f  mov     ebx, eax
0x140080731  test    eax, eax
0x140080733  js      short loc_1400807AE
0x140080735  mov     rax, [rsp+180h+Ace]
0x14008073a  cmp     [rax], r12b
0x14008073d  jnz     short loc_1400807A1
0x14008073f  lea     r14, [rax+8]
0x140080743  mov     rcx, r14; Sid1
0x140080746  lea     rdx, [rbp+80h+Sid]; Sid2
0x14008074a  call    cs:__imp_RtlEqualSid
0x140080751  nop     dword ptr [rax+rax+00h]
0x140080756  test    al, al
0x140080758  jz      short loc_14008076F
0x14008075a  mov     rcx, [rsp+180h+Dacl]; Acl
0x14008075f  mov     edx, edi; AceIndex
0x140080761  call    cs:__imp_RtlDeleteAce
0x140080768  nop     dword ptr [rax+rax+00h]
0x14008076d  jmp     short loc_1400807A1
0x14008076f  lea     rdx, [rbp+80h+Sid2]; Sid2
0x140080773  mov     rcx, r14; Sid1
0x140080776  call    cs:__imp_RtlEqualSid
0x14008077d  nop     dword ptr [rax+rax+00h]
0x140080782  test    al, al
0x140080784  jnz     short loc_14008075A
0x140080786  lea     rdx, [rsp+180h+var_120]; Sid2
0x14008078b  mov     rcx, r14; Sid1
0x14008078e  call    cs:__imp_RtlEqualSid
0x140080795  nop     dword ptr [rax+rax+00h]
0x14008079a  test    al, al
0x14008079c  jnz     short loc_14008075A
0x14008079e  add     edi, r13d
0x1400807a1  mov     rcx, [rsp+180h+Dacl]
0x1400807a6  add     esi, r13d
0x1400807a9  jmp     loc_14008070E
0x1400807ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400807b5  lea     rax, WPP_GLOBAL_Control
0x1400807bc  cmp     rcx, rax
0x1400807bf  jz      short loc_1400807F5
0x1400807c1  mov     eax, [rcx+2Ch]
0x1400807c4  test    r13b, al
0x1400807c7  jz      short loc_1400807F5
0x1400807c9  mov     edx, 36h ; '6'
0x1400807ce  mov     [rsp+180h+var_160], ebx
0x1400807d2  lfence
0x1400807d5  mov     r9, gs:188h
0x1400807de  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x1400807e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400807ec  mov     rcx, [rcx+18h]
0x1400807f0  call    WPP_SF_qD
0x1400807f5  mov     eax, ebx
0x1400807f7  mov     rcx, [rbp+80h+var_30]
0x1400807fb  xor     rcx, rsp; StackCookie
0x1400807fe  call    __security_check_cookie
0x140080803  lea     r11, [rsp+180h+var_20]
0x14008080b  mov     rbx, [r11+38h]
0x14008080f  mov     rsi, [r11+40h]
0x140080813  mov     rdi, [r11+48h]
0x140080817  mov     rsp, r11
0x14008081a  pop     r15
0x14008081c  pop     r14
0x14008081e  pop     r13
0x140080820  pop     r12
0x140080822  pop     rbp
0x140080823  retn
```
