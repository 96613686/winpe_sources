# PROXYPORT::PROXYPORT(unsigned __int64)

- ea: `0x140193890`
- end: `0x140193cde`
- name: `??0PROXYPORT@@QEAA@_K@Z`
- size: `1102`
- prototype: `PROXYPORT *__fastcall(PROXYPORT *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400f6a78`

## callees

- `0x140193890`
- `0x140193ce4`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140193a8a`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140193a8a`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140193bf2`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140193bf2`
- `ntoskrnl!SeQueryInformationToken` at `0x140193c1b`
- `ntoskrnl!SeQueryInformationToken` at `0x140193c3e`
- `ntoskrnl!SeQueryInformationToken` at `0x140193c1b`
- `ntoskrnl!SeQueryInformationToken` at `0x140193c3e`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140193a2b`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140193a2b`
- `ntoskrnl!ZwCreateSection` at `0x1401939ff`
- `ntoskrnl!ZwCreateSection` at `0x1401939ff`
- `ntoskrnl!swprintf_s` at `0x140193afb`
- `ntoskrnl!swprintf_s` at `0x140193afb`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140193c7e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140193c7e`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140193a68`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140193a68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193baf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140193baf`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140193a4e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140193a4e`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140193935`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140193935`
- `ntoskrnl!PsGetCurrentProcess` at `0x140193a3f`
- `ntoskrnl!PsGetCurrentProcess` at `0x140193a3f`
- `ntoskrnl!ZwClose` at `0x140193ca4`
- `ntoskrnl!ZwClose` at `0x140193ca4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140193b0f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140193b0f`
- `ntoskrnl!ObfDereferenceObject` at `0x140193cbb`
- `ntoskrnl!ObfDereferenceObject` at `0x140193cbb`
- `win32kbase!Win32AllocPoolZInit` at `0x140193967`
- `win32kbase!Win32AllocPoolZInit` at `0x140193967`
- `win32kbase!Win32FreePool` at `0x140193cca`
- `win32kbase!Win32FreePool` at `0x140193cca`

## pseudocode

```c
PROXYPORT *__fastcall PROXYPORT::PROXYPORT(PROXYPORT *this)
{
  int v2; // r15d
  __int64 v3; // rax
  struct _KPROCESS *CurrentProcess; // rax
  PACCESS_TOKEN v5; // rdi
  int v6; // r14d
  NTSTATUS v7; // esi
  int v8; // eax
  int v9; // edi
  void *v11; // rcx
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  ULONG AllocationAttributes[2]; // [rsp+28h] [rbp-D8h]
  HANDLE FileHandle; // [rsp+30h] [rbp-D0h]
  unsigned __int8 EffectiveOnly; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+41h] [rbp-BFh] BYREF
  PVOID TokenInformation; // [rsp+44h] [rbp-BCh] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  struct _LUID AuthenticationId; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+68h] [rbp-98h] BYREF
  void *v23; // [rsp+70h] [rbp-90h] BYREF
  struct _PORT_VIEW SectionHandle; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE v27; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t Dst[264]; // [rsp+100h] [rbp+0h] BYREF

  v23 = 0;
  v19 = 0;
  MaximumSize.QuadPart = 0;
  *(_QWORD *)&v27.Length = 0;
  *(_DWORD *)&v27.ContextTrackingMode = 0;
  memset(&SectionHandle, 0, sizeof(SectionHandle));
  HIDWORD(TokenInformation) = 0;
  DestinationString = 0;
  memset_0(Dst, 0, 0x208u);
  *(_QWORD *)this = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( ZwQueryInformationProcess(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         ProcessSessionInformation,
         (char *)&TokenInformation + 4,
         4u,
         0) >= 0 )
  {
    v2 = HIDWORD(TokenInformation);
    v27.Length = 0;
    v27.ImpersonationLevel = SecurityImpersonation;
    *(_WORD *)&v27.ContextTrackingMode = 257;
    v3 = Win32AllocPoolZInit(80, 1953525831);
    *(_QWORD *)this = v3;
    if ( v3 )
    {
      *(_DWORD *)(v3 + 76) = 0;
      *(_QWORD *)(*(_QWORD *)this + 32LL) = 0;
      *(_QWORD *)(*(_QWORD *)this + 40LL) = 0;
      *(_QWORD *)(*(_QWORD *)this + 48LL) = 0;
      *(_DWORD *)(*(_QWORD *)this + 72LL) = 0;
      **(_QWORD **)this = 0;
      *(_QWORD *)(*(_QWORD *)this + 56LL) = 0;
      *(_QWORD *)(*(_QWORD *)this + 64LL) = 0;
      MaximumSize.QuadPart = 0x400000;
      SectionHandle.SectionHandle = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwCreateSection(&SectionHandle.SectionHandle, 6u, &ObjectAttributes, &MaximumSize, 4u, 0x8000000u, 0) < 0 )
        goto LABEL_21;
      P = 0;
      AuthenticationId = 0;
      LODWORD(TokenInformation) = 0;
      if ( !(unsigned __int8)PsIsThreadImpersonating(KeGetCurrentThread())
        || (CopyOnOpen[0] = 0,
            EffectiveOnly = 0,
            ImpersonationLevel = SecurityAnonymous,
            v6 = 1,
            (v5 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel)) == 0) )
      {
        CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
        v5 = PsReferencePrimaryToken(CurrentProcess);
        v6 = 0;
      }
      v7 = SeQueryAuthenticationIdToken(v5, &AuthenticationId);
      if ( v7 >= 0 )
      {
        v7 = SeQueryInformationToken(v5, TokenIntegrityLevel, &TokenInformation);
        if ( v7 >= 0 )
          v7 = SeQueryInformationToken(v5, TokenUser, &P);
      }
      if ( v6 )
        PsDereferenceImpersonationToken(v5);
      else
        PsDereferencePrimaryToken(v5);
      if ( v7 < 0 )
        goto LABEL_21;
      v8 = (int)TokenInformation;
      SectionHandle.Length = 48;
      SectionHandle.SectionOffset = 0;
      SectionHandle.ViewSize = 0x400000;
      *(_OWORD *)&SectionHandle.ViewBase = 0;
      if ( (unsigned int)TokenInformation < 0x2000 )
      {
        v8 = 0x2000;
        LODWORD(TokenInformation) = 0x2000;
      }
      LODWORD(FileHandle) = AuthenticationId.HighPart;
      AllocationAttributes[0] = AuthenticationId.LowPart;
      LODWORD(ReturnLength) = v2;
      swprintf_s(
        Dst,
        0x104u,
        L"%s_%x_%x_%x_%x",
        L"\\RPC Control\\UmpdProxy",
        ReturnLength,
        *(_QWORD *)AllocationAttributes,
        FileHandle,
        v8);
      RtlInitUnicodeString(&DestinationString, Dst);
      v9 = PROXYPORT::SecureConnectPort(
             *(void ***)this,
             &DestinationString,
             &v27,
             &SectionHandle,
             &v23,
             *(void **)P,
             &v19);
      if ( v9 >= 0 )
      {
        *(_QWORD *)(*(_QWORD *)this + 8LL) = SectionHandle.SectionHandle;
        *(_QWORD *)(*(_QWORD *)this + 16LL) = v23;
        *(_QWORD *)(*(_QWORD *)this + 40LL) = SectionHandle.ViewBase;
        *(_QWORD *)(*(_QWORD *)this + 48LL) = SectionHandle.ViewSize;
        *(_QWORD *)(*(_QWORD *)this + 56LL) = SectionHandle.ViewRemoteBase;
        *(_QWORD *)(*(_QWORD *)this + 64LL) = *(_QWORD *)(*(_QWORD *)this + 40LL) - *(_QWORD *)(*(_QWORD *)this + 56LL);
        *(_DWORD *)(*(_QWORD *)this + 76LL) = 1;
      }
      ExFreePoolWithTag(P, 0);
      if ( v9 < 0 )
      {
LABEL_21:
        if ( SectionHandle.SectionHandle )
          ZwClose(SectionHandle.SectionHandle);
        v11 = **(void ***)this;
        if ( v11 )
          ObfDereferenceObject(v11);
        Win32FreePool(*(void **)this);
        *(_QWORD *)this = 0;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x140193890  mov     [rsp-8+arg_8], rbx
0x140193895  mov     [rsp-8+arg_10], rsi
0x14019389a  push    rbp
0x14019389b  push    rdi
0x14019389c  push    r12
0x14019389e  push    r14
0x1401938a0  push    r15
0x1401938a2  lea     rbp, [rsp-220h]
0x1401938aa  sub     rsp, 320h
0x1401938b1  mov     rax, cs:__security_cookie
0x1401938b8  xor     rax, rsp
0x1401938bb  mov     [rbp+240h+var_30], rax
0x1401938c2  xorps   xmm0, xmm0
0x1401938c5  xor     r12d, r12d
0x1401938c8  xor     eax, eax
0x1401938ca  mov     [rsp+340h+var_2D0], r12
0x1401938cf  mov     rbx, rcx
0x1401938d2  mov     [rsp+340h+var_2F0], r12d
0x1401938d7  lea     rcx, [rbp+240h+Dst]; void *
0x1401938db  mov     qword ptr [rsp+340h+MaximumSize], r12
0x1401938e0  xor     edx, edx; Val
0x1401938e2  mov     qword ptr [rbp+240h+var_258.Length], rax
0x1401938e6  mov     r8d, 208h; Size
0x1401938ec  mov     dword ptr [rbp+240h+var_258.ContextTrackingMode], eax
0x1401938ef  movups  xmmword ptr [rsp+340h+SectionHandle], xmm0
0x1401938f4  mov     dword ptr [rsp+340h+TokenInformation+4], r12d
0x1401938f9  movups  [rbp+240h+var_2B8], xmm0
0x1401938fd  movups  [rbp+240h+var_2A8], xmm0
0x140193901  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x140193905  call    memset_0
0x14019390a  xorps   xmm0, xmm0
0x14019390d  mov     [rbx], r12
0x140193910  lea     edi, [r12+4]
0x140193915  mov     [rsp+340h+ReturnLength], r12; ReturnLength
0x14019391a  mov     r9d, edi; ProcessInformationLength
0x14019391d  lea     edx, [rdi+14h]; ProcessInformationClass
0x140193920  lea     r8, [rsp+340h+TokenInformation+4]; ProcessInformation
0x140193925  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140193929  movups  xmmword ptr [rbp+240h+ObjectAttributes.Length], xmm0
0x14019392d  movups  xmmword ptr [rbp+240h+ObjectAttributes.ObjectName], xmm0
0x140193931  movups  xmmword ptr [rbp+240h+ObjectAttributes.SecurityDescriptor], xmm0
0x140193935  call    cs:__imp_ZwQueryInformationProcess
0x14019393c  nop     dword ptr [rax+rax+00h]
0x140193941  test    eax, eax
0x140193943  js      loc_140193BC3
0x140193949  mov     r15d, dword ptr [rsp+340h+TokenInformation+4]
0x14019394e  lea     ecx, [rdi+4Ch]
0x140193951  mov     edx, 74707047h
0x140193956  mov     [rbp+240h+var_258.Length], r12d
0x14019395a  mov     [rbp+240h+var_258.ImpersonationLevel], 2
0x140193961  mov     word ptr [rbp+240h+var_258.ContextTrackingMode], 101h
0x140193967  call    cs:__imp_Win32AllocPoolZInit
0x14019396e  nop     dword ptr [rax+rax+00h]
0x140193973  mov     [rbx], rax
0x140193976  test    rax, rax
0x140193979  jz      loc_140193BC3
0x14019397f  mov     [rax+4Ch], r12d
0x140193983  lea     r9, [rsp+340h+MaximumSize]; MaximumSize
0x140193988  mov     rax, [rbx]
0x14019398b  lea     r8, [rbp+240h+ObjectAttributes]; ObjectAttributes
0x14019398f  xorps   xmm0, xmm0
0x140193992  mov     [rsp+340h+FileHandle], r12; FileHandle
0x140193997  mov     [rsp+340h+AllocationAttributes], 8000000h; AllocationAttributes
0x14019399f  lea     edx, [rdi+2]; DesiredAccess
0x1401939a2  lea     rcx, [rbp+240h+SectionHandle+8]; SectionHandle
0x1401939a6  mov     dword ptr [rsp+340h+ReturnLength], edi; SectionPageProtection
0x1401939aa  mov     [rax+20h], r12
0x1401939ae  mov     rax, [rbx]
0x1401939b1  mov     [rax+28h], r12
0x1401939b5  mov     rax, [rbx]
0x1401939b8  mov     [rax+30h], r12
0x1401939bc  mov     rax, [rbx]
0x1401939bf  mov     [rax+48h], r12d
0x1401939c3  mov     rax, [rbx]
0x1401939c6  mov     [rax], r12
0x1401939c9  mov     rax, [rbx]
0x1401939cc  mov     [rax+38h], r12
0x1401939d0  mov     rax, [rbx]
0x1401939d3  mov     [rax+40h], r12
0x1401939d7  mov     qword ptr [rsp+340h+MaximumSize], 400000h
0x1401939e0  mov     [rbp+240h+SectionHandle+8], r12
0x1401939e4  mov     [rbp+240h+ObjectAttributes.Length], 30h ; '0'
0x1401939eb  mov     [rbp+240h+ObjectAttributes.RootDirectory], r12
0x1401939ef  mov     [rbp+240h+ObjectAttributes.Attributes], 200h
0x1401939f6  mov     [rbp+240h+ObjectAttributes.ObjectName], r12
0x1401939fa  movdqu  xmmword ptr [rbp+240h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401939ff  call    cs:__imp_ZwCreateSection
0x140193a06  nop     dword ptr [rax+rax+00h]
0x140193a0b  test    eax, eax
0x140193a0d  js      loc_140193C9B
0x140193a13  mov     [rsp+340h+P], r12
0x140193a18  mov     qword ptr [rsp+340h+AuthenticationId.LowPart], r12
0x140193a1d  mov     dword ptr [rsp+340h+TokenInformation], r12d
0x140193a22  mov     rcx, gs:188h
0x140193a2b  call    cs:__imp_PsIsThreadImpersonating
0x140193a32  nop     dword ptr [rax+rax+00h]
0x140193a37  test    al, al
0x140193a39  jnz     loc_140193C51
0x140193a3f  call    cs:__imp_PsGetCurrentProcess
0x140193a46  nop     dword ptr [rax+rax+00h]
0x140193a4b  mov     rcx, rax; Process
0x140193a4e  call    cs:__imp_PsReferencePrimaryToken
0x140193a55  nop     dword ptr [rax+rax+00h]
0x140193a5a  mov     rdi, rax
0x140193a5d  mov     r14d, r12d
0x140193a60  lea     rdx, [rsp+340h+AuthenticationId]; AuthenticationId
0x140193a65  mov     rcx, rdi; Token
0x140193a68  call    cs:__imp_SeQueryAuthenticationIdToken
0x140193a6f  nop     dword ptr [rax+rax+00h]
0x140193a74  mov     esi, eax
0x140193a76  test    eax, eax
0x140193a78  jns     loc_140193C0E
0x140193a7e  mov     rcx, rdi; ImpersonationToken
0x140193a81  test    r14d, r14d
0x140193a84  jnz     loc_140193BF2
0x140193a8a  call    cs:__imp_PsDereferencePrimaryToken
0x140193a91  nop     dword ptr [rax+rax+00h]
0x140193a96  test    esi, esi
0x140193a98  js      loc_140193C9B
0x140193a9e  mov     eax, dword ptr [rsp+340h+TokenInformation]
0x140193aa2  mov     ecx, 2000h
0x140193aa7  mov     dword ptr [rsp+340h+SectionHandle], 30h ; '0'
0x140193aaf  xorps   xmm0, xmm0
0x140193ab2  mov     dword ptr [rbp+240h+var_2B8], r12d
0x140193ab6  mov     qword ptr [rbp+240h+var_2B8+8], 400000h
0x140193abe  movdqu  [rbp+240h+var_2A8], xmm0
0x140193ac3  cmp     eax, ecx
0x140193ac5  jb      loc_140193C03
0x140193acb  mov     [rsp+340h+var_308], eax
0x140193acf  lea     r9, aRpcControlUmpd; "\\RPC Control\\UmpdProxy"
0x140193ad6  mov     eax, [rsp+340h+AuthenticationId.HighPart]
0x140193ada  lea     r8, aSXXXX; "%s_%x_%x_%x_%x"
0x140193ae1  mov     dword ptr [rsp+340h+FileHandle], eax
0x140193ae5  lea     rcx, [rbp+240h+Dst]; Dst
0x140193ae9  mov     eax, [rsp+340h+AuthenticationId.LowPart]
0x140193aed  mov     edx, 104h; SizeInWords
0x140193af2  mov     [rsp+340h+AllocationAttributes], eax
0x140193af6  mov     dword ptr [rsp+340h+ReturnLength], r15d
0x140193afb  call    cs:__imp_swprintf_s
0x140193b02  nop     dword ptr [rax+rax+00h]
0x140193b07  lea     rdx, [rbp+240h+Dst]; SourceString
0x140193b0b  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x140193b0f  call    cs:__imp_RtlInitUnicodeString
0x140193b16  nop     dword ptr [rax+rax+00h]
0x140193b1b  lea     rax, [rsp+340h+var_2F0]
0x140193b20  mov     [rsp+340h+FileHandle], rax; unsigned int *
0x140193b25  lea     r9, [rsp+340h+SectionHandle]; struct _PORT_VIEW *
0x140193b2a  mov     rax, [rsp+340h+P]
0x140193b2f  lea     r8, [rbp+240h+var_258]; struct _SECURITY_QUALITY_OF_SERVICE *
0x140193b33  lea     rdx, [rbp+240h+DestinationString]; struct _UNICODE_STRING *
0x140193b37  mov     rcx, [rax]
0x140193b3a  lea     rax, [rsp+340h+var_2D0]
0x140193b3f  mov     qword ptr [rsp+340h+AllocationAttributes], rcx; void *
0x140193b44  mov     rcx, [rbx]; void **
0x140193b47  mov     [rsp+340h+ReturnLength], rax; void **
0x140193b4c  call    ?SecureConnectPort@PROXYPORT@@SAJPEAPEAXPEAU_UNICODE_STRING@@PEAU_SECURITY_QUALITY_OF_SERVICE@@PEAU_PORT_VIEW@@0PEAXPEAK@Z; PROXYPORT::SecureConnectPort(void * *,_UNICODE_STRING *,_SECURITY_QUALITY_OF_SERVICE *,_PORT_VIEW *,void * *,void *,ulong *)
0x140193b51  mov     edi, eax
0x140193b53  test    eax, eax
0x140193b55  js      short loc_140193BA8
0x140193b57  mov     rdx, [rbx]
0x140193b5a  mov     rcx, [rbp+240h+SectionHandle+8]
0x140193b5e  mov     [rdx+8], rcx
0x140193b62  mov     rdx, [rbx]
0x140193b65  mov     rcx, [rsp+340h+var_2D0]
0x140193b6a  mov     [rdx+10h], rcx
0x140193b6e  mov     rdx, [rbx]
0x140193b71  mov     rcx, qword ptr [rbp+240h+var_2A8]
0x140193b75  mov     [rdx+28h], rcx
0x140193b79  mov     rdx, [rbx]
0x140193b7c  mov     rcx, qword ptr [rbp+240h+var_2B8+8]
0x140193b80  mov     [rdx+30h], rcx
0x140193b84  mov     rcx, [rbx]
0x140193b87  mov     rax, qword ptr [rbp+240h+var_2A8+8]
0x140193b8b  mov     [rcx+38h], rax
0x140193b8f  mov     rdx, [rbx]
0x140193b92  mov     rcx, [rdx+28h]
0x140193b96  sub     rcx, [rdx+38h]
0x140193b9a  mov     [rdx+40h], rcx
0x140193b9e  mov     rax, [rbx]
0x140193ba1  mov     dword ptr [rax+4Ch], 1
0x140193ba8  mov     rcx, [rsp+340h+P]; P
0x140193bad  xor     edx, edx; Tag
0x140193baf  call    cs:__imp_ExFreePoolWithTag
0x140193bb6  nop     dword ptr [rax+rax+00h]
0x140193bbb  test    edi, edi
0x140193bbd  js      loc_140193C9B
0x140193bc3  mov     rax, rbx
0x140193bc6  mov     rcx, [rbp+240h+var_30]
0x140193bcd  xor     rcx, rsp; StackCookie
0x140193bd0  call    __security_check_cookie
0x140193bd5  lea     r11, [rsp+340h+var_20]
0x140193bdd  mov     rbx, [r11+38h]
0x140193be1  mov     rsi, [r11+40h]
0x140193be5  mov     rsp, r11
0x140193be8  pop     r15
0x140193bea  pop     r14
0x140193bec  pop     r12
0x140193bee  pop     rdi
0x140193bef  pop     rbp
0x140193bf0  retn
0x140193bf2  call    cs:__imp_PsDereferenceImpersonationToken
0x140193bf9  nop     dword ptr [rax+rax+00h]
0x140193bfe  jmp     loc_140193A96
0x140193c03  mov     eax, ecx
0x140193c05  mov     dword ptr [rsp+340h+TokenInformation], ecx
0x140193c09  jmp     loc_140193ACB
0x140193c0e  lea     r8, [rsp+340h+TokenInformation]; TokenInformation
0x140193c13  mov     edx, 19h; TokenInformationClass
0x140193c18  mov     rcx, rdi; Token
0x140193c1b  call    cs:__imp_SeQueryInformationToken
0x140193c22  nop     dword ptr [rax+rax+00h]
0x140193c27  mov     esi, eax
0x140193c29  test    eax, eax
0x140193c2b  js      loc_140193A7E
0x140193c31  lea     r8, [rsp+340h+P]; TokenInformation
0x140193c36  mov     edx, 1; TokenInformationClass
0x140193c3b  mov     rcx, rdi; Token
0x140193c3e  call    cs:__imp_SeQueryInformationToken
0x140193c45  nop     dword ptr [rax+rax+00h]
0x140193c4a  mov     esi, eax
0x140193c4c  jmp     loc_140193A7E
0x140193c51  mov     [rsp+340h+CopyOnOpen], r12b
0x140193c56  lea     r9, [rsp+340h+ImpersonationLevel]; ImpersonationLevel
0x140193c5b  mov     [rsp+340h+EffectiveOnly], r12b
0x140193c60  lea     r8, [rsp+340h+EffectiveOnly]; EffectiveOnly
0x140193c65  mov     [rsp+340h+ImpersonationLevel], r12d
0x140193c6a  lea     rdx, [rsp+340h+CopyOnOpen]; CopyOnOpen
0x140193c6f  mov     rcx, gs:188h; Thread
0x140193c78  mov     r14d, 1
0x140193c7e  call    cs:__imp_PsReferenceImpersonationToken
0x140193c85  nop     dword ptr [rax+rax+00h]
0x140193c8a  mov     rdi, rax
0x140193c8d  test    rax, rax
0x140193c90  jnz     loc_140193A60
0x140193c96  jmp     loc_140193A3F
0x140193c9b  mov     rcx, [rbp+240h+SectionHandle+8]; Handle
0x140193c9f  test    rcx, rcx
0x140193ca2  jz      short loc_140193CB0
0x140193ca4  call    cs:__imp_ZwClose
0x140193cab  nop     dword ptr [rax+rax+00h]
0x140193cb0  mov     rcx, [rbx]
0x140193cb3  mov     rcx, [rcx]; Object
0x140193cb6  test    rcx, rcx
0x140193cb9  jz      short loc_140193CC7
0x140193cbb  call    cs:__imp_ObfDereferenceObject
0x140193cc2  nop     dword ptr [rax+rax+00h]
0x140193cc7  mov     rcx, [rbx]
0x140193cca  call    cs:__imp_Win32FreePool
0x140193cd1  nop     dword ptr [rax+rax+00h]
0x140193cd6  mov     [rbx], r12
0x140193cd9  jmp     loc_140193BC3
```
