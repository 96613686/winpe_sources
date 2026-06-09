# Smb2ValidateWindowsHelloForBusinessAuthentication

- ea: `0x14006a1b8`
- end: `0x14006a55e`
- name: `Smb2ValidateWindowsHelloForBusinessAuthentication`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x140015960`
- `0x14002019c`
- `0x1400224b8`
- `0x140069ac4`
- `0x14006a1b8`
- `0x140077600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006a4fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a519`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a4fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a519`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a3d5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a3f8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a3d5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a3f8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a30b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a356`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a429`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a474`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a30b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a356`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a429`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a474`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006a535`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006a535`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006a266`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006a266`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a2b5`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a36e`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a2b5`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a36e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a2e5`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a3b4`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a2e5`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a3b4`
- `srvnet!SrvLibIsNetwork` at `0x14006a1f0`
- `srvnet!SrvLibIsNetwork` at `0x14006a1f0`

## pseudocode

```c
__int64 __fastcall Smb2ValidateWindowsHelloForBusinessAuthentication(__int64 a1)
{
  void *v1; // r14
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  char v7; // r15
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  PACCESS_TOKEN v10; // rax
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebx
  unsigned int v15; // eax
  char v16; // r13
  char v17; // r12
  unsigned int v18; // r15d
  NTSTATUS v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+20h] [rbp-30h] BYREF
  PVOID TokenInformation; // [rsp+28h] [rbp-28h] BYREF
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+A8h] [rbp+58h] BYREF

  v1 = 0;
  TokenInformation = 0;
  P = 0;
  v2 = Smb2ImpersonateSecurityContext(a1);
  v6 = (unsigned int)v2;
  if ( v2 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    v7 = 0;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v24 = 49;
LABEL_51:
    WPP_SF_d(v23->AttachedDevice, v24, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids, v6);
    goto LABEL_52;
  }
  v7 = 1;
  if ( !(unsigned __int8)SrvLibIsNetwork(v4, v3, v5, (unsigned int)v2) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v9 = 44;
    goto LABEL_7;
  }
  CopyOnOpen = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  v10 = PsReferenceImpersonationToken(KeGetCurrentThread(), &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v1 = v10;
  if ( !v10 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v9 = 45;
LABEL_7:
    WPP_SF_(v8->AttachedDevice, v9, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids);
LABEL_52:
    v14 = -1073741628;
    goto LABEL_53;
  }
  if ( !SeQueryInformationToken(v10, TokenUser, &TokenInformation) )
  {
    UnicodeString = 0;
    v11 = RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)TokenInformation, 1u);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          46,
          WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
          (unsigned int)v11);
      }
    }
    else if ( (unsigned __int8)Smb2IsUserOrGroupInExceptionList(UnicodeString.Buffer, v12, v13, (unsigned int)v11) )
    {
      v14 = 0;
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_53;
    }
    if ( UnicodeString.Buffer )
      RtlFreeUnicodeString(&UnicodeString);
  }
  v15 = SeQueryInformationToken(v1, TokenGroups, &P);
  v6 = v15;
  if ( v15 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_52;
    }
    v24 = 48;
    goto LABEL_51;
  }
  v16 = 0;
  v17 = 0;
  v18 = 0;
  UnicodeString = 0;
  while ( v18 < *(_DWORD *)P )
  {
    v19 = RtlConvertSidToUnicodeString(&UnicodeString, *((PSID *)P + 2 * v18 + 1), 1u);
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          47,
          WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
          (unsigned int)v19);
      }
      goto LABEL_39;
    }
    if ( RtlEqualUnicodeString(&UnicodeString, &String2, 1u) )
    {
      v16 = 1;
LABEL_32:
      if ( v17 )
        goto LABEL_40;
      goto LABEL_33;
    }
    if ( RtlEqualUnicodeString(&UnicodeString, &stru_14003F230, 1u) )
      v17 = 1;
    if ( v16 )
      goto LABEL_32;
LABEL_33:
    if ( (unsigned __int8)Smb2IsUserOrGroupInExceptionList(UnicodeString.Buffer, v20, v21, v22) )
    {
LABEL_40:
      v14 = 0;
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_41;
    }
    RtlFreeUnicodeString(&UnicodeString);
LABEL_39:
    ++v18;
  }
  v14 = -1067646966;
LABEL_41:
  v7 = 1;
LABEL_53:
  if ( TokenInformation )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    TokenInformation = 0;
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( v1 )
    PsDereferenceImpersonationToken(v1);
  if ( v7 )
    Smb2Revert();
  return v14;
}

```

## disassembly

```asm
0x14006a1b8  push    rbp
0x14006a1ba  push    rbx
0x14006a1bb  push    rdi
0x14006a1bc  push    r12
0x14006a1be  push    r13
0x14006a1c0  push    r14
0x14006a1c2  push    r15
0x14006a1c4  mov     rbp, rsp
0x14006a1c7  sub     rsp, 50h
0x14006a1cb  xor     r14d, r14d
0x14006a1ce  mov     [rbp+TokenInformation], r14
0x14006a1d2  mov     [rbp+P], r14
0x14006a1d6  call    Smb2ImpersonateSecurityContext
0x14006a1db  mov     r9d, eax
0x14006a1de  test    eax, eax
0x14006a1e0  js      loc_14006A4AE
0x14006a1e6  lea     ebx, [r14+1]
0x14006a1ea  mov     r15b, bl
0x14006a1ed  mov     [rbp+arg_8], bl
0x14006a1f0  call    cs:__imp_SrvLibIsNetwork
0x14006a1f7  nop     dword ptr [rax+rax+00h]
0x14006a1fc  test    al, al
0x14006a1fe  jnz     short loc_14006A245
0x14006a200  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a207  lea     rdi, WPP_GLOBAL_Control
0x14006a20e  cmp     rcx, rdi
0x14006a211  jz      loc_14006A4EA
0x14006a217  test    dword ptr [rcx+2Ch], 20000h
0x14006a21e  jz      loc_14006A4EA
0x14006a224  cmp     [rcx+29h], bl
0x14006a227  jb      loc_14006A4EA
0x14006a22d  lea     edx, [rbx+2Bh]
0x14006a230  mov     rcx, [rcx+18h]
0x14006a234  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a23b  call    WPP_SF_
0x14006a240  jmp     loc_14006A4EA
0x14006a245  mov     [rbp+CopyOnOpen], r14b
0x14006a249  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x14006a24d  mov     [rbp+EffectiveOnly], r14b
0x14006a251  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x14006a255  mov     [rbp+ImpersonationLevel], r14d
0x14006a259  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x14006a25d  mov     rcx, gs:188h; Thread
0x14006a266  call    cs:__imp_PsReferenceImpersonationToken
0x14006a26d  nop     dword ptr [rax+rax+00h]
0x14006a272  mov     r14, rax
0x14006a275  test    rax, rax
0x14006a278  jnz     short loc_14006A2AC
0x14006a27a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a281  lea     rdi, WPP_GLOBAL_Control
0x14006a288  cmp     rcx, rdi
0x14006a28b  jz      loc_14006A4EA
0x14006a291  test    dword ptr [rcx+2Ch], 20000h
0x14006a298  jz      loc_14006A4EA
0x14006a29e  cmp     [rcx+29h], bl
0x14006a2a1  jb      loc_14006A4EA
0x14006a2a7  lea     edx, [rax+2Dh]
0x14006a2aa  jmp     short loc_14006A230
0x14006a2ac  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14006a2b0  mov     edx, ebx; TokenInformationClass
0x14006a2b2  mov     rcx, r14; Token
0x14006a2b5  call    cs:__imp_SeQueryInformationToken
0x14006a2bc  nop     dword ptr [rax+rax+00h]
0x14006a2c1  lea     rdi, WPP_GLOBAL_Control
0x14006a2c8  test    eax, eax
0x14006a2ca  jnz     loc_14006A362
0x14006a2d0  mov     rdx, [rbp+TokenInformation]
0x14006a2d4  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a2d8  xorps   xmm0, xmm0
0x14006a2db  mov     r8b, bl; AllocateDestinationString
0x14006a2de  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14006a2e2  mov     rdx, [rdx]; Sid
0x14006a2e5  call    cs:__imp_RtlConvertSidToUnicodeString
0x14006a2ec  nop     dword ptr [rax+rax+00h]
0x14006a2f1  mov     r9d, eax
0x14006a2f4  test    eax, eax
0x14006a2f6  js      short loc_14006A31C
0x14006a2f8  mov     rcx, [rbp+UnicodeString.Buffer]
0x14006a2fc  call    Smb2IsUserOrGroupInExceptionList
0x14006a301  test    al, al
0x14006a303  jz      short loc_14006A34B
0x14006a305  xor     ebx, ebx
0x14006a307  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a30b  call    cs:__imp_RtlFreeUnicodeString
0x14006a312  nop     dword ptr [rax+rax+00h]
0x14006a317  jmp     loc_14006A4EF
0x14006a31c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a323  cmp     rcx, rdi
0x14006a326  jz      short loc_14006A34B
0x14006a328  test    dword ptr [rcx+2Ch], 20000h
0x14006a32f  jz      short loc_14006A34B
0x14006a331  cmp     [rcx+29h], bl
0x14006a334  jb      short loc_14006A34B
0x14006a336  mov     rcx, [rcx+18h]
0x14006a33a  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a341  mov     edx, 2Eh ; '.'
0x14006a346  call    WPP_SF_d
0x14006a34b  cmp     [rbp+UnicodeString.Buffer], 0
0x14006a350  jz      short loc_14006A362
0x14006a352  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a356  call    cs:__imp_RtlFreeUnicodeString
0x14006a35d  nop     dword ptr [rax+rax+00h]
0x14006a362  lea     r8, [rbp+P]; TokenInformation
0x14006a366  mov     edx, 2; TokenInformationClass
0x14006a36b  mov     rcx, r14; Token
0x14006a36e  call    cs:__imp_SeQueryInformationToken
0x14006a375  nop     dword ptr [rax+rax+00h]
0x14006a37a  mov     r9d, eax
0x14006a37d  test    eax, eax
0x14006a37f  jnz     loc_14006A48D
0x14006a385  xor     r13b, r13b
0x14006a388  xor     r12b, r12b
0x14006a38b  xorps   xmm0, xmm0
0x14006a38e  xor     r15d, r15d
0x14006a391  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14006a395  mov     rcx, [rbp+P]
0x14006a399  cmp     r15d, [rcx]
0x14006a39c  jnb     loc_14006A486
0x14006a3a2  mov     edx, r15d
0x14006a3a5  mov     r8b, bl; AllocateDestinationString
0x14006a3a8  add     rdx, rdx
0x14006a3ab  mov     rdx, [rcx+rdx*8+8]; Sid
0x14006a3b0  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a3b4  call    cs:__imp_RtlConvertSidToUnicodeString
0x14006a3bb  nop     dword ptr [rax+rax+00h]
0x14006a3c0  mov     r9d, eax
0x14006a3c3  test    eax, eax
0x14006a3c5  js      short loc_14006A437
0x14006a3c7  mov     r8b, bl; CaseInSensitive
0x14006a3ca  lea     rdx, String2; String2
0x14006a3d1  lea     rcx, [rbp+UnicodeString]; String1
0x14006a3d5  call    cs:__imp_RtlEqualUnicodeString
0x14006a3dc  nop     dword ptr [rax+rax+00h]
0x14006a3e1  test    al, al
0x14006a3e3  jz      short loc_14006A3EA
0x14006a3e5  mov     r13b, bl
0x14006a3e8  jmp     short loc_14006A413
0x14006a3ea  mov     r8b, bl; CaseInSensitive
0x14006a3ed  lea     rdx, stru_14003F230; String2
0x14006a3f4  lea     rcx, [rbp+UnicodeString]; String1
0x14006a3f8  call    cs:__imp_RtlEqualUnicodeString
0x14006a3ff  nop     dword ptr [rax+rax+00h]
0x14006a404  test    al, al
0x14006a406  movzx   r12d, r12b
0x14006a40a  cmovnz  r12d, ebx
0x14006a40e  test    r13b, r13b
0x14006a411  jz      short loc_14006A418
0x14006a413  test    r12b, r12b
0x14006a416  jnz     short loc_14006A46E
0x14006a418  mov     rcx, [rbp+UnicodeString.Buffer]
0x14006a41c  call    Smb2IsUserOrGroupInExceptionList
0x14006a421  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a425  test    al, al
0x14006a427  jnz     short loc_14006A472
0x14006a429  call    cs:__imp_RtlFreeUnicodeString
0x14006a430  nop     dword ptr [rax+rax+00h]
0x14006a435  jmp     short loc_14006A466
0x14006a437  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a43e  cmp     rcx, rdi
0x14006a441  jz      short loc_14006A466
0x14006a443  test    dword ptr [rcx+2Ch], 20000h
0x14006a44a  jz      short loc_14006A466
0x14006a44c  cmp     [rcx+29h], bl
0x14006a44f  jb      short loc_14006A466
0x14006a451  mov     rcx, [rcx+18h]
0x14006a455  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a45c  mov     edx, 2Fh ; '/'
0x14006a461  call    WPP_SF_d
0x14006a466  add     r15d, ebx
0x14006a469  jmp     loc_14006A395
0x14006a46e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a472  xor     ebx, ebx
0x14006a474  call    cs:__imp_RtlFreeUnicodeString
0x14006a47b  nop     dword ptr [rax+rax+00h]
0x14006a480  mov     r15b, [rbp+arg_8]
0x14006a484  jmp     short loc_14006A4EF
0x14006a486  mov     ebx, 0C05D000Ah
0x14006a48b  jmp     short loc_14006A480
0x14006a48d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a494  cmp     rcx, rdi
0x14006a497  jz      short loc_14006A4EA
0x14006a499  test    dword ptr [rcx+2Ch], 20000h
0x14006a4a0  jz      short loc_14006A4EA
0x14006a4a2  cmp     [rcx+29h], bl
0x14006a4a5  jb      short loc_14006A4EA
0x14006a4a7  mov     edx, 30h ; '0'
0x14006a4ac  jmp     short loc_14006A4DA
0x14006a4ae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a4b5  lea     rdi, WPP_GLOBAL_Control
0x14006a4bc  xor     r15b, r15b
0x14006a4bf  cmp     rcx, rdi
0x14006a4c2  jz      short loc_14006A4EA
0x14006a4c4  test    dword ptr [rcx+2Ch], 20000h
0x14006a4cb  jz      short loc_14006A4EA
0x14006a4cd  mov     ebx, 1
0x14006a4d2  cmp     [rcx+29h], bl
0x14006a4d5  jb      short loc_14006A4EA
0x14006a4d7  lea     edx, [rbx+30h]
0x14006a4da  mov     rcx, [rcx+18h]
0x14006a4de  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a4e5  call    WPP_SF_d
0x14006a4ea  mov     ebx, 0C00000C4h
0x14006a4ef  mov     rcx, [rbp+TokenInformation]; P
0x14006a4f3  test    rcx, rcx
0x14006a4f6  jz      short loc_14006A50E
0x14006a4f8  xor     edx, edx; Tag
0x14006a4fa  call    cs:__imp_ExFreePoolWithTag
0x14006a501  nop     dword ptr [rax+rax+00h]
0x14006a506  mov     [rbp+TokenInformation], 0
0x14006a50e  mov     rcx, [rbp+P]; P
0x14006a512  test    rcx, rcx
0x14006a515  jz      short loc_14006A52D
0x14006a517  xor     edx, edx; Tag
0x14006a519  call    cs:__imp_ExFreePoolWithTag
0x14006a520  nop     dword ptr [rax+rax+00h]
0x14006a525  mov     [rbp+P], 0
0x14006a52d  test    r14, r14
0x14006a530  jz      short loc_14006A541
0x14006a532  mov     rcx, r14; ImpersonationToken
0x14006a535  call    cs:__imp_PsDereferenceImpersonationToken
0x14006a53c  nop     dword ptr [rax+rax+00h]
0x14006a541  test    r15b, r15b
0x14006a544  jz      short loc_14006A54B
0x14006a546  call    Smb2Revert
0x14006a54b  mov     eax, ebx
0x14006a54d  add     rsp, 50h
0x14006a551  pop     r15
0x14006a553  pop     r14
0x14006a555  pop     r13
0x14006a557  pop     r12
0x14006a559  pop     rdi
0x14006a55a  pop     rbx
0x14006a55b  pop     rbp
0x14006a55c  retn
```
