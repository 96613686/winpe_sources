# Smb2ValidateWindowsHelloForBusinessAuthentication

- ea: `0x14006a208`
- end: `0x14006a5ae`
- name: `Smb2ValidateWindowsHelloForBusinessAuthentication`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140092240`

## callees

- `0x140015960`
- `0x14002019c`
- `0x1400224b8`
- `0x140069b14`
- `0x14006a208`
- `0x140077650`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006a54a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a569`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a54a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a569`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a425`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a448`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a425`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006a448`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a35b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a3a6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a479`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a4c4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a35b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a3a6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a479`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14006a4c4`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006a585`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006a585`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006a2b6`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006a2b6`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a305`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a3be`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a305`
- `ntoskrnl!SeQueryInformationToken` at `0x14006a3be`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a335`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a404`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a335`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14006a404`
- `srvnet!SrvLibIsNetwork` at `0x14006a240`
- `srvnet!SrvLibIsNetwork` at `0x14006a240`

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
    WPP_SF_d(v23->AttachedDevice, v24, &WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids, v6);
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
    WPP_SF_(v8->AttachedDevice, v9, &WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids);
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
          &WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
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
          &WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids,
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
0x14006a208  push    rbp
0x14006a20a  push    rbx
0x14006a20b  push    rdi
0x14006a20c  push    r12
0x14006a20e  push    r13
0x14006a210  push    r14
0x14006a212  push    r15
0x14006a214  mov     rbp, rsp
0x14006a217  sub     rsp, 50h
0x14006a21b  xor     r14d, r14d
0x14006a21e  mov     [rbp+TokenInformation], r14
0x14006a222  mov     [rbp+P], r14
0x14006a226  call    Smb2ImpersonateSecurityContext
0x14006a22b  mov     r9d, eax
0x14006a22e  test    eax, eax
0x14006a230  js      loc_14006A4FE
0x14006a236  lea     ebx, [r14+1]
0x14006a23a  mov     r15b, bl
0x14006a23d  mov     [rbp+arg_8], bl
0x14006a240  call    cs:__imp_SrvLibIsNetwork
0x14006a247  nop     dword ptr [rax+rax+00h]
0x14006a24c  test    al, al
0x14006a24e  jnz     short loc_14006A295
0x14006a250  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a257  lea     rdi, WPP_GLOBAL_Control
0x14006a25e  cmp     rcx, rdi
0x14006a261  jz      loc_14006A53A
0x14006a267  test    dword ptr [rcx+2Ch], 20000h
0x14006a26e  jz      loc_14006A53A
0x14006a274  cmp     [rcx+29h], bl
0x14006a277  jb      loc_14006A53A
0x14006a27d  lea     edx, [rbx+2Bh]
0x14006a280  mov     rcx, [rcx+18h]
0x14006a284  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a28b  call    WPP_SF_
0x14006a290  jmp     loc_14006A53A
0x14006a295  mov     [rbp+CopyOnOpen], r14b
0x14006a299  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x14006a29d  mov     [rbp+EffectiveOnly], r14b
0x14006a2a1  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x14006a2a5  mov     [rbp+ImpersonationLevel], r14d
0x14006a2a9  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x14006a2ad  mov     rcx, gs:188h; Thread
0x14006a2b6  call    cs:__imp_PsReferenceImpersonationToken
0x14006a2bd  nop     dword ptr [rax+rax+00h]
0x14006a2c2  mov     r14, rax
0x14006a2c5  test    rax, rax
0x14006a2c8  jnz     short loc_14006A2FC
0x14006a2ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a2d1  lea     rdi, WPP_GLOBAL_Control
0x14006a2d8  cmp     rcx, rdi
0x14006a2db  jz      loc_14006A53A
0x14006a2e1  test    dword ptr [rcx+2Ch], 20000h
0x14006a2e8  jz      loc_14006A53A
0x14006a2ee  cmp     [rcx+29h], bl
0x14006a2f1  jb      loc_14006A53A
0x14006a2f7  lea     edx, [rax+2Dh]
0x14006a2fa  jmp     short loc_14006A280
0x14006a2fc  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14006a300  mov     edx, ebx; TokenInformationClass
0x14006a302  mov     rcx, r14; Token
0x14006a305  call    cs:__imp_SeQueryInformationToken
0x14006a30c  nop     dword ptr [rax+rax+00h]
0x14006a311  lea     rdi, WPP_GLOBAL_Control
0x14006a318  test    eax, eax
0x14006a31a  jnz     loc_14006A3B2
0x14006a320  mov     rdx, [rbp+TokenInformation]
0x14006a324  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a328  xorps   xmm0, xmm0
0x14006a32b  mov     r8b, bl; AllocateDestinationString
0x14006a32e  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14006a332  mov     rdx, [rdx]; Sid
0x14006a335  call    cs:__imp_RtlConvertSidToUnicodeString
0x14006a33c  nop     dword ptr [rax+rax+00h]
0x14006a341  mov     r9d, eax
0x14006a344  test    eax, eax
0x14006a346  js      short loc_14006A36C
0x14006a348  mov     rcx, [rbp+UnicodeString.Buffer]
0x14006a34c  call    Smb2IsUserOrGroupInExceptionList
0x14006a351  test    al, al
0x14006a353  jz      short loc_14006A39B
0x14006a355  xor     ebx, ebx
0x14006a357  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a35b  call    cs:__imp_RtlFreeUnicodeString
0x14006a362  nop     dword ptr [rax+rax+00h]
0x14006a367  jmp     loc_14006A53F
0x14006a36c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a373  cmp     rcx, rdi
0x14006a376  jz      short loc_14006A39B
0x14006a378  test    dword ptr [rcx+2Ch], 20000h
0x14006a37f  jz      short loc_14006A39B
0x14006a381  cmp     [rcx+29h], bl
0x14006a384  jb      short loc_14006A39B
0x14006a386  mov     rcx, [rcx+18h]
0x14006a38a  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a391  mov     edx, 2Eh ; '.'
0x14006a396  call    WPP_SF_d
0x14006a39b  cmp     [rbp+UnicodeString.Buffer], 0
0x14006a3a0  jz      short loc_14006A3B2
0x14006a3a2  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a3a6  call    cs:__imp_RtlFreeUnicodeString
0x14006a3ad  nop     dword ptr [rax+rax+00h]
0x14006a3b2  lea     r8, [rbp+P]; TokenInformation
0x14006a3b6  mov     edx, 2; TokenInformationClass
0x14006a3bb  mov     rcx, r14; Token
0x14006a3be  call    cs:__imp_SeQueryInformationToken
0x14006a3c5  nop     dword ptr [rax+rax+00h]
0x14006a3ca  mov     r9d, eax
0x14006a3cd  test    eax, eax
0x14006a3cf  jnz     loc_14006A4DD
0x14006a3d5  xor     r13b, r13b
0x14006a3d8  xor     r12b, r12b
0x14006a3db  xorps   xmm0, xmm0
0x14006a3de  xor     r15d, r15d
0x14006a3e1  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14006a3e5  mov     rcx, [rbp+P]
0x14006a3e9  cmp     r15d, [rcx]
0x14006a3ec  jnb     loc_14006A4D6
0x14006a3f2  mov     edx, r15d
0x14006a3f5  mov     r8b, bl; AllocateDestinationString
0x14006a3f8  add     rdx, rdx
0x14006a3fb  mov     rdx, [rcx+rdx*8+8]; Sid
0x14006a400  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a404  call    cs:__imp_RtlConvertSidToUnicodeString
0x14006a40b  nop     dword ptr [rax+rax+00h]
0x14006a410  mov     r9d, eax
0x14006a413  test    eax, eax
0x14006a415  js      short loc_14006A487
0x14006a417  mov     r8b, bl; CaseInSensitive
0x14006a41a  lea     rdx, String2; String2
0x14006a421  lea     rcx, [rbp+UnicodeString]; String1
0x14006a425  call    cs:__imp_RtlEqualUnicodeString
0x14006a42c  nop     dword ptr [rax+rax+00h]
0x14006a431  test    al, al
0x14006a433  jz      short loc_14006A43A
0x14006a435  mov     r13b, bl
0x14006a438  jmp     short loc_14006A463
0x14006a43a  mov     r8b, bl; CaseInSensitive
0x14006a43d  lea     rdx, stru_14003F230; String2
0x14006a444  lea     rcx, [rbp+UnicodeString]; String1
0x14006a448  call    cs:__imp_RtlEqualUnicodeString
0x14006a44f  nop     dword ptr [rax+rax+00h]
0x14006a454  test    al, al
0x14006a456  movzx   r12d, r12b
0x14006a45a  cmovnz  r12d, ebx
0x14006a45e  test    r13b, r13b
0x14006a461  jz      short loc_14006A468
0x14006a463  test    r12b, r12b
0x14006a466  jnz     short loc_14006A4BE
0x14006a468  mov     rcx, [rbp+UnicodeString.Buffer]
0x14006a46c  call    Smb2IsUserOrGroupInExceptionList
0x14006a471  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a475  test    al, al
0x14006a477  jnz     short loc_14006A4C2
0x14006a479  call    cs:__imp_RtlFreeUnicodeString
0x14006a480  nop     dword ptr [rax+rax+00h]
0x14006a485  jmp     short loc_14006A4B6
0x14006a487  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a48e  cmp     rcx, rdi
0x14006a491  jz      short loc_14006A4B6
0x14006a493  test    dword ptr [rcx+2Ch], 20000h
0x14006a49a  jz      short loc_14006A4B6
0x14006a49c  cmp     [rcx+29h], bl
0x14006a49f  jb      short loc_14006A4B6
0x14006a4a1  mov     rcx, [rcx+18h]
0x14006a4a5  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a4ac  mov     edx, 2Fh ; '/'
0x14006a4b1  call    WPP_SF_d
0x14006a4b6  add     r15d, ebx
0x14006a4b9  jmp     loc_14006A3E5
0x14006a4be  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14006a4c2  xor     ebx, ebx
0x14006a4c4  call    cs:__imp_RtlFreeUnicodeString
0x14006a4cb  nop     dword ptr [rax+rax+00h]
0x14006a4d0  mov     r15b, [rbp+arg_8]
0x14006a4d4  jmp     short loc_14006A53F
0x14006a4d6  mov     ebx, 0C05D000Ah
0x14006a4db  jmp     short loc_14006A4D0
0x14006a4dd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a4e4  cmp     rcx, rdi
0x14006a4e7  jz      short loc_14006A53A
0x14006a4e9  test    dword ptr [rcx+2Ch], 20000h
0x14006a4f0  jz      short loc_14006A53A
0x14006a4f2  cmp     [rcx+29h], bl
0x14006a4f5  jb      short loc_14006A53A
0x14006a4f7  mov     edx, 30h ; '0'
0x14006a4fc  jmp     short loc_14006A52A
0x14006a4fe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a505  lea     rdi, WPP_GLOBAL_Control
0x14006a50c  xor     r15b, r15b
0x14006a50f  cmp     rcx, rdi
0x14006a512  jz      short loc_14006A53A
0x14006a514  test    dword ptr [rcx+2Ch], 20000h
0x14006a51b  jz      short loc_14006A53A
0x14006a51d  mov     ebx, 1
0x14006a522  cmp     [rcx+29h], bl
0x14006a525  jb      short loc_14006A53A
0x14006a527  lea     edx, [rbx+30h]
0x14006a52a  mov     rcx, [rcx+18h]
0x14006a52e  lea     r8, WPP_10a5358526963fec2a0dab82e9006e3d_Traceguids
0x14006a535  call    WPP_SF_d
0x14006a53a  mov     ebx, 0C00000C4h
0x14006a53f  mov     rcx, [rbp+TokenInformation]; P
0x14006a543  test    rcx, rcx
0x14006a546  jz      short loc_14006A55E
0x14006a548  xor     edx, edx; Tag
0x14006a54a  call    cs:__imp_ExFreePoolWithTag
0x14006a551  nop     dword ptr [rax+rax+00h]
0x14006a556  mov     [rbp+TokenInformation], 0
0x14006a55e  mov     rcx, [rbp+P]; P
0x14006a562  test    rcx, rcx
0x14006a565  jz      short loc_14006A57D
0x14006a567  xor     edx, edx; Tag
0x14006a569  call    cs:__imp_ExFreePoolWithTag
0x14006a570  nop     dword ptr [rax+rax+00h]
0x14006a575  mov     [rbp+P], 0
0x14006a57d  test    r14, r14
0x14006a580  jz      short loc_14006A591
0x14006a582  mov     rcx, r14; ImpersonationToken
0x14006a585  call    cs:__imp_PsDereferenceImpersonationToken
0x14006a58c  nop     dword ptr [rax+rax+00h]
0x14006a591  test    r15b, r15b
0x14006a594  jz      short loc_14006A59B
0x14006a596  call    Smb2Revert
0x14006a59b  mov     eax, ebx
0x14006a59d  add     rsp, 50h
0x14006a5a1  pop     r15
0x14006a5a3  pop     r14
0x14006a5a5  pop     r13
0x14006a5a7  pop     r12
0x14006a5a9  pop     rdi
0x14006a5aa  pop     rbx
0x14006a5ab  pop     rbp
0x14006a5ac  retn
```
