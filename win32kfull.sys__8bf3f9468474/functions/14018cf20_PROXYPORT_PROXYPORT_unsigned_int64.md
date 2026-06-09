# PROXYPORT::PROXYPORT(unsigned __int64)

- ea: `0x14018cf20`
- end: `0x14018d36e`
- name: `??0PROXYPORT@@QEAA@_K@Z`
- size: `1102`
- prototype: `PROXYPORT *__fastcall(PROXYPORT *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140050858`

## callees

- `0x14018cf20`
- `0x14018d374`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x14018d11a`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14018d11a`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14018d282`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14018d282`
- `ntoskrnl!SeQueryInformationToken` at `0x14018d2ab`
- `ntoskrnl!SeQueryInformationToken` at `0x14018d2ce`
- `ntoskrnl!SeQueryInformationToken` at `0x14018d2ab`
- `ntoskrnl!SeQueryInformationToken` at `0x14018d2ce`
- `ntoskrnl!PsIsThreadImpersonating` at `0x14018d0bb`
- `ntoskrnl!PsIsThreadImpersonating` at `0x14018d0bb`
- `ntoskrnl!ZwCreateSection` at `0x14018d08f`
- `ntoskrnl!ZwCreateSection` at `0x14018d08f`
- `ntoskrnl!swprintf_s` at `0x14018d18b`
- `ntoskrnl!swprintf_s` at `0x14018d18b`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14018d30e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14018d30e`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14018d0f8`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14018d0f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d23f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d23f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14018d0de`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14018d0de`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14018cfc5`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14018cfc5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14018d0cf`
- `ntoskrnl!PsGetCurrentProcess` at `0x14018d0cf`
- `ntoskrnl!ZwClose` at `0x14018d334`
- `ntoskrnl!ZwClose` at `0x14018d334`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018d19f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018d19f`
- `ntoskrnl!ObfDereferenceObject` at `0x14018d34b`
- `ntoskrnl!ObfDereferenceObject` at `0x14018d34b`
- `win32kbase!Win32AllocPoolZInit` at `0x14018cff7`
- `win32kbase!Win32AllocPoolZInit` at `0x14018cff7`
- `win32kbase!Win32FreePool` at `0x14018d35a`
- `win32kbase!Win32FreePool` at `0x14018d35a`

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
  _LUID AuthenticationId; // [rsp+58h] [rbp-A8h] BYREF
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
             *(PSID *)P,
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
0x14018cf20  mov     [rsp-8+arg_8], rbx
0x14018cf25  mov     [rsp-8+arg_10], rsi
0x14018cf2a  push    rbp
0x14018cf2b  push    rdi
0x14018cf2c  push    r12
0x14018cf2e  push    r14
0x14018cf30  push    r15
0x14018cf32  lea     rbp, [rsp-220h]
0x14018cf3a  sub     rsp, 320h
0x14018cf41  mov     rax, cs:__security_cookie
0x14018cf48  xor     rax, rsp
0x14018cf4b  mov     [rbp+240h+var_30], rax
0x14018cf52  xorps   xmm0, xmm0
0x14018cf55  xor     r12d, r12d
0x14018cf58  xor     eax, eax
0x14018cf5a  mov     [rsp+340h+var_2D0], r12
0x14018cf5f  mov     rbx, rcx
0x14018cf62  mov     [rsp+340h+var_2F0], r12d
0x14018cf67  lea     rcx, [rbp+240h+Dst]; void *
0x14018cf6b  mov     qword ptr [rsp+340h+MaximumSize], r12
0x14018cf70  xor     edx, edx; Val
0x14018cf72  mov     qword ptr [rbp+240h+var_258.Length], rax
0x14018cf76  mov     r8d, 208h; Size
0x14018cf7c  mov     dword ptr [rbp+240h+var_258.ContextTrackingMode], eax
0x14018cf7f  movups  xmmword ptr [rsp+340h+SectionHandle], xmm0
0x14018cf84  mov     dword ptr [rsp+340h+TokenInformation+4], r12d
0x14018cf89  movups  [rbp+240h+var_2B8], xmm0
0x14018cf8d  movups  [rbp+240h+var_2A8], xmm0
0x14018cf91  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x14018cf95  call    memset_0
0x14018cf9a  xorps   xmm0, xmm0
0x14018cf9d  mov     [rbx], r12
0x14018cfa0  lea     edi, [r12+4]
0x14018cfa5  mov     [rsp+340h+ReturnLength], r12; ReturnLength
0x14018cfaa  mov     r9d, edi; ProcessInformationLength
0x14018cfad  lea     edx, [rdi+14h]; ProcessInformationClass
0x14018cfb0  lea     r8, [rsp+340h+TokenInformation+4]; ProcessInformation
0x14018cfb5  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14018cfb9  movups  xmmword ptr [rbp+240h+ObjectAttributes.Length], xmm0
0x14018cfbd  movups  xmmword ptr [rbp+240h+ObjectAttributes.ObjectName], xmm0
0x14018cfc1  movups  xmmword ptr [rbp+240h+ObjectAttributes.SecurityDescriptor], xmm0
0x14018cfc5  call    cs:__imp_ZwQueryInformationProcess
0x14018cfcc  nop     dword ptr [rax+rax+00h]
0x14018cfd1  test    eax, eax
0x14018cfd3  js      loc_14018D253
0x14018cfd9  mov     r15d, dword ptr [rsp+340h+TokenInformation+4]
0x14018cfde  lea     ecx, [rdi+4Ch]
0x14018cfe1  mov     edx, 74707047h
0x14018cfe6  mov     [rbp+240h+var_258.Length], r12d
0x14018cfea  mov     [rbp+240h+var_258.ImpersonationLevel], 2
0x14018cff1  mov     word ptr [rbp+240h+var_258.ContextTrackingMode], 101h
0x14018cff7  call    cs:__imp_Win32AllocPoolZInit
0x14018cffe  nop     dword ptr [rax+rax+00h]
0x14018d003  mov     [rbx], rax
0x14018d006  test    rax, rax
0x14018d009  jz      loc_14018D253
0x14018d00f  mov     [rax+4Ch], r12d
0x14018d013  lea     r9, [rsp+340h+MaximumSize]; MaximumSize
0x14018d018  mov     rax, [rbx]
0x14018d01b  lea     r8, [rbp+240h+ObjectAttributes]; ObjectAttributes
0x14018d01f  xorps   xmm0, xmm0
0x14018d022  mov     [rsp+340h+FileHandle], r12; FileHandle
0x14018d027  mov     [rsp+340h+AllocationAttributes], 8000000h; AllocationAttributes
0x14018d02f  lea     edx, [rdi+2]; DesiredAccess
0x14018d032  lea     rcx, [rbp+240h+SectionHandle+8]; SectionHandle
0x14018d036  mov     dword ptr [rsp+340h+ReturnLength], edi; SectionPageProtection
0x14018d03a  mov     [rax+20h], r12
0x14018d03e  mov     rax, [rbx]
0x14018d041  mov     [rax+28h], r12
0x14018d045  mov     rax, [rbx]
0x14018d048  mov     [rax+30h], r12
0x14018d04c  mov     rax, [rbx]
0x14018d04f  mov     [rax+48h], r12d
0x14018d053  mov     rax, [rbx]
0x14018d056  mov     [rax], r12
0x14018d059  mov     rax, [rbx]
0x14018d05c  mov     [rax+38h], r12
0x14018d060  mov     rax, [rbx]
0x14018d063  mov     [rax+40h], r12
0x14018d067  mov     qword ptr [rsp+340h+MaximumSize], 400000h
0x14018d070  mov     [rbp+240h+SectionHandle+8], r12
0x14018d074  mov     [rbp+240h+ObjectAttributes.Length], 30h ; '0'
0x14018d07b  mov     [rbp+240h+ObjectAttributes.RootDirectory], r12
0x14018d07f  mov     [rbp+240h+ObjectAttributes.Attributes], 200h
0x14018d086  mov     [rbp+240h+ObjectAttributes.ObjectName], r12
0x14018d08a  movdqu  xmmword ptr [rbp+240h+ObjectAttributes.SecurityDescriptor], xmm0
0x14018d08f  call    cs:__imp_ZwCreateSection
0x14018d096  nop     dword ptr [rax+rax+00h]
0x14018d09b  test    eax, eax
0x14018d09d  js      loc_14018D32B
0x14018d0a3  mov     [rsp+340h+P], r12
0x14018d0a8  mov     qword ptr [rsp+340h+AuthenticationId.LowPart], r12
0x14018d0ad  mov     dword ptr [rsp+340h+TokenInformation], r12d
0x14018d0b2  mov     rcx, gs:188h
0x14018d0bb  call    cs:__imp_PsIsThreadImpersonating
0x14018d0c2  nop     dword ptr [rax+rax+00h]
0x14018d0c7  test    al, al
0x14018d0c9  jnz     loc_14018D2E1
0x14018d0cf  call    cs:__imp_PsGetCurrentProcess
0x14018d0d6  nop     dword ptr [rax+rax+00h]
0x14018d0db  mov     rcx, rax; Process
0x14018d0de  call    cs:__imp_PsReferencePrimaryToken
0x14018d0e5  nop     dword ptr [rax+rax+00h]
0x14018d0ea  mov     rdi, rax
0x14018d0ed  mov     r14d, r12d
0x14018d0f0  lea     rdx, [rsp+340h+AuthenticationId]; AuthenticationId
0x14018d0f5  mov     rcx, rdi; Token
0x14018d0f8  call    cs:__imp_SeQueryAuthenticationIdToken
0x14018d0ff  nop     dword ptr [rax+rax+00h]
0x14018d104  mov     esi, eax
0x14018d106  test    eax, eax
0x14018d108  jns     loc_14018D29E
0x14018d10e  mov     rcx, rdi; ImpersonationToken
0x14018d111  test    r14d, r14d
0x14018d114  jnz     loc_14018D282
0x14018d11a  call    cs:__imp_PsDereferencePrimaryToken
0x14018d121  nop     dword ptr [rax+rax+00h]
0x14018d126  test    esi, esi
0x14018d128  js      loc_14018D32B
0x14018d12e  mov     eax, dword ptr [rsp+340h+TokenInformation]
0x14018d132  mov     ecx, 2000h
0x14018d137  mov     dword ptr [rsp+340h+SectionHandle], 30h ; '0'
0x14018d13f  xorps   xmm0, xmm0
0x14018d142  mov     dword ptr [rbp+240h+var_2B8], r12d
0x14018d146  mov     qword ptr [rbp+240h+var_2B8+8], 400000h
0x14018d14e  movdqu  [rbp+240h+var_2A8], xmm0
0x14018d153  cmp     eax, ecx
0x14018d155  jb      loc_14018D293
0x14018d15b  mov     [rsp+340h+var_308], eax
0x14018d15f  lea     r9, aRpcControlUmpd; "\\RPC Control\\UmpdProxy"
0x14018d166  mov     eax, [rsp+340h+AuthenticationId.HighPart]
0x14018d16a  lea     r8, aSXXXX; "%s_%x_%x_%x_%x"
0x14018d171  mov     dword ptr [rsp+340h+FileHandle], eax
0x14018d175  lea     rcx, [rbp+240h+Dst]; Dst
0x14018d179  mov     eax, [rsp+340h+AuthenticationId.LowPart]
0x14018d17d  mov     edx, 104h; SizeInWords
0x14018d182  mov     [rsp+340h+AllocationAttributes], eax
0x14018d186  mov     dword ptr [rsp+340h+ReturnLength], r15d
0x14018d18b  call    cs:__imp_swprintf_s
0x14018d192  nop     dword ptr [rax+rax+00h]
0x14018d197  lea     rdx, [rbp+240h+Dst]; SourceString
0x14018d19b  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x14018d19f  call    cs:__imp_RtlInitUnicodeString
0x14018d1a6  nop     dword ptr [rax+rax+00h]
0x14018d1ab  lea     rax, [rsp+340h+var_2F0]
0x14018d1b0  mov     [rsp+340h+FileHandle], rax; unsigned int *
0x14018d1b5  lea     r9, [rsp+340h+SectionHandle]; struct _PORT_VIEW *
0x14018d1ba  mov     rax, [rsp+340h+P]
0x14018d1bf  lea     r8, [rbp+240h+var_258]; struct _SECURITY_QUALITY_OF_SERVICE *
0x14018d1c3  lea     rdx, [rbp+240h+DestinationString]; struct _UNICODE_STRING *
0x14018d1c7  mov     rcx, [rax]
0x14018d1ca  lea     rax, [rsp+340h+var_2D0]
0x14018d1cf  mov     qword ptr [rsp+340h+AllocationAttributes], rcx; void *
0x14018d1d4  mov     rcx, [rbx]; void **
0x14018d1d7  mov     [rsp+340h+ReturnLength], rax; void **
0x14018d1dc  call    ?SecureConnectPort@PROXYPORT@@SAJPEAPEAXPEAU_UNICODE_STRING@@PEAU_SECURITY_QUALITY_OF_SERVICE@@PEAU_PORT_VIEW@@0PEAXPEAK@Z; PROXYPORT::SecureConnectPort(void * *,_UNICODE_STRING *,_SECURITY_QUALITY_OF_SERVICE *,_PORT_VIEW *,void * *,void *,ulong *)
0x14018d1e1  mov     edi, eax
0x14018d1e3  test    eax, eax
0x14018d1e5  js      short loc_14018D238
0x14018d1e7  mov     rdx, [rbx]
0x14018d1ea  mov     rcx, [rbp+240h+SectionHandle+8]
0x14018d1ee  mov     [rdx+8], rcx
0x14018d1f2  mov     rdx, [rbx]
0x14018d1f5  mov     rcx, [rsp+340h+var_2D0]
0x14018d1fa  mov     [rdx+10h], rcx
0x14018d1fe  mov     rdx, [rbx]
0x14018d201  mov     rcx, qword ptr [rbp+240h+var_2A8]
0x14018d205  mov     [rdx+28h], rcx
0x14018d209  mov     rdx, [rbx]
0x14018d20c  mov     rcx, qword ptr [rbp+240h+var_2B8+8]
0x14018d210  mov     [rdx+30h], rcx
0x14018d214  mov     rcx, [rbx]
0x14018d217  mov     rax, qword ptr [rbp+240h+var_2A8+8]
0x14018d21b  mov     [rcx+38h], rax
0x14018d21f  mov     rdx, [rbx]
0x14018d222  mov     rcx, [rdx+28h]
0x14018d226  sub     rcx, [rdx+38h]
0x14018d22a  mov     [rdx+40h], rcx
0x14018d22e  mov     rax, [rbx]
0x14018d231  mov     dword ptr [rax+4Ch], 1
0x14018d238  mov     rcx, [rsp+340h+P]; P
0x14018d23d  xor     edx, edx; Tag
0x14018d23f  call    cs:__imp_ExFreePoolWithTag
0x14018d246  nop     dword ptr [rax+rax+00h]
0x14018d24b  test    edi, edi
0x14018d24d  js      loc_14018D32B
0x14018d253  mov     rax, rbx
0x14018d256  mov     rcx, [rbp+240h+var_30]
0x14018d25d  xor     rcx, rsp; StackCookie
0x14018d260  call    __security_check_cookie
0x14018d265  lea     r11, [rsp+340h+var_20]
0x14018d26d  mov     rbx, [r11+38h]
0x14018d271  mov     rsi, [r11+40h]
0x14018d275  mov     rsp, r11
0x14018d278  pop     r15
0x14018d27a  pop     r14
0x14018d27c  pop     r12
0x14018d27e  pop     rdi
0x14018d27f  pop     rbp
0x14018d280  retn
0x14018d282  call    cs:__imp_PsDereferenceImpersonationToken
0x14018d289  nop     dword ptr [rax+rax+00h]
0x14018d28e  jmp     loc_14018D126
0x14018d293  mov     eax, ecx
0x14018d295  mov     dword ptr [rsp+340h+TokenInformation], ecx
0x14018d299  jmp     loc_14018D15B
0x14018d29e  lea     r8, [rsp+340h+TokenInformation]; TokenInformation
0x14018d2a3  mov     edx, 19h; TokenInformationClass
0x14018d2a8  mov     rcx, rdi; Token
0x14018d2ab  call    cs:__imp_SeQueryInformationToken
0x14018d2b2  nop     dword ptr [rax+rax+00h]
0x14018d2b7  mov     esi, eax
0x14018d2b9  test    eax, eax
0x14018d2bb  js      loc_14018D10E
0x14018d2c1  lea     r8, [rsp+340h+P]; TokenInformation
0x14018d2c6  mov     edx, 1; TokenInformationClass
0x14018d2cb  mov     rcx, rdi; Token
0x14018d2ce  call    cs:__imp_SeQueryInformationToken
0x14018d2d5  nop     dword ptr [rax+rax+00h]
0x14018d2da  mov     esi, eax
0x14018d2dc  jmp     loc_14018D10E
0x14018d2e1  mov     [rsp+340h+CopyOnOpen], r12b
0x14018d2e6  lea     r9, [rsp+340h+ImpersonationLevel]; ImpersonationLevel
0x14018d2eb  mov     [rsp+340h+EffectiveOnly], r12b
0x14018d2f0  lea     r8, [rsp+340h+EffectiveOnly]; EffectiveOnly
0x14018d2f5  mov     [rsp+340h+ImpersonationLevel], r12d
0x14018d2fa  lea     rdx, [rsp+340h+CopyOnOpen]; CopyOnOpen
0x14018d2ff  mov     rcx, gs:188h; Thread
0x14018d308  mov     r14d, 1
0x14018d30e  call    cs:__imp_PsReferenceImpersonationToken
0x14018d315  nop     dword ptr [rax+rax+00h]
0x14018d31a  mov     rdi, rax
0x14018d31d  test    rax, rax
0x14018d320  jnz     loc_14018D0F0
0x14018d326  jmp     loc_14018D0CF
0x14018d32b  mov     rcx, [rbp+240h+SectionHandle+8]; Handle
0x14018d32f  test    rcx, rcx
0x14018d332  jz      short loc_14018D340
0x14018d334  call    cs:__imp_ZwClose
0x14018d33b  nop     dword ptr [rax+rax+00h]
0x14018d340  mov     rcx, [rbx]
0x14018d343  mov     rcx, [rcx]; Object
0x14018d346  test    rcx, rcx
0x14018d349  jz      short loc_14018D357
0x14018d34b  call    cs:__imp_ObfDereferenceObject
0x14018d352  nop     dword ptr [rax+rax+00h]
0x14018d357  mov     rcx, [rbx]
0x14018d35a  call    cs:__imp_Win32FreePool
0x14018d361  nop     dword ptr [rax+rax+00h]
0x14018d366  mov     [rbx], r12
0x14018d369  jmp     loc_14018D253
```
