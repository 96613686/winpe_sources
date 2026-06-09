# VerifyAccessToExclusion

- ea: `0x1400b19d0`
- end: `0x1400b1bef`
- name: `VerifyAccessToExclusion`
- size: `543`
- prototype: `__int64 __fastcall(__int64, struct _KPROCESS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b197c`

## callees

- `0x1400b19d0`
- `0x1400b461c`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400b1bc0`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400b1bc0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b1bac`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b1bac`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400b1b9c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400b1b9c`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x1400b1b8c`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x1400b1b8c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b1a90`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b1a90`
- `ntoskrnl!SeAccessCheck` at `0x1400b1ad9`
- `ntoskrnl!SeAccessCheck` at `0x1400b1ad9`
- `ntoskrnl!SeLockSubjectContext` at `0x1400b1a84`
- `ntoskrnl!SeLockSubjectContext` at `0x1400b1a84`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400b1a74`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400b1a74`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b1af2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b1b09`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b1b3f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b1af2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b1b09`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b1b3f`
- `NETIO!NsiReferenceDefaultObjectSecurity` at `0x1400b1a28`
- `NETIO!NsiReferenceDefaultObjectSecurity` at `0x1400b1a28`

## pseudocode

```c
__int64 __fastcall VerifyAccessToExclusion(__int64 a1, struct _KPROCESS *a2)
{
  __int64 result; // rax
  struct _KPROCESS *v4; // rdx
  void *v6; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v8; // bl
  ACCESS_MASK PreviouslyGrantedAccess[2]; // [rsp+20h] [rbp-89h]
  int AccessStatus; // [rsp+48h] [rbp-61h]
  _BYTE v11[4]; // [rsp+60h] [rbp-49h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-45h] BYREF
  int v13; // [rsp+68h] [rbp-41h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING v15; // [rsp+90h] [rbp-19h] BYREF
  struct _UNICODE_STRING v16; // [rsp+A0h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp+7h] BYREF
  wchar_t pszDest[20]; // [rsp+C0h] [rbp+17h] BYREF

  result = 0;
  v4 = *(struct _KPROCESS **)(a1 + 40);
  v13 = 0;
  if ( a2 != v4 )
  {
    if ( a2 )
    {
      if ( v4 )
      {
        return 3221225506LL;
      }
      else
      {
        v6 = (void *)NsiReferenceDefaultObjectSecurity();
        if ( v6 )
        {
          v11[0] = 0;
          GrantedAccess = 0;
          v15 = 0;
          v16 = 0;
          memset(&SubjectContext, 0, sizeof(SubjectContext));
          DestinationString = 0;
          SeCaptureSubjectContextEx(0, a2, &SubjectContext);
          SeLockSubjectContext(&SubjectContext);
          GenericMapping = IoGetFileObjectGenericMapping();
          v8 = SeAccessCheck(v6, &SubjectContext, 1u, 3u, 0, 0, GenericMapping, 1, &GrantedAccess, &v13);
          RtlInitUnicodeString(&DestinationString, L"TCP/IP");
          RtlInitUnicodeString(&v16, L"InternetPortReservation");
          PreviouslyGrantedAccess[0] = *(unsigned __int16 *)(a1 + 10);
          RtlStringCbPrintfW(
            pszDest,
            0x28u,
            L"Ports %u-%u",
            *(unsigned __int16 *)(a1 + 8),
            *(_QWORD *)PreviouslyGrantedAccess);
          RtlInitUnicodeString(&v15, pszDest);
          LOBYTE(AccessStatus) = v8;
          SeOpenObjectAuditAlarmForNonObObject(
            &DestinationString,
            0,
            &v16,
            &v15,
            v6,
            &SubjectContext,
            3,
            GrantedAccess,
            0,
            AccessStatus,
            v11);
          SeUnlockSubjectContext(&SubjectContext);
          SeReleaseSubjectContext(&SubjectContext);
          ObDereferenceSecurityDescriptor(v6, 1);
          return (unsigned int)v13;
        }
        else
        {
          return 3221225687LL;
        }
      }
    }
    else
    {
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400b19d0  mov     [rsp-8+arg_10], rbx
0x1400b19d5  push    rbp
0x1400b19d6  push    rsi
0x1400b19d7  push    rdi
0x1400b19d8  lea     rbp, [rsp-47h]
0x1400b19dd  sub     rsp, 0F0h
0x1400b19e4  mov     rax, cs:__security_cookie
0x1400b19eb  xor     rax, rsp
0x1400b19ee  mov     [rbp+57h+var_18], rax
0x1400b19f2  mov     rbx, rdx
0x1400b19f5  xor     eax, eax
0x1400b19f7  mov     rdx, [rcx+28h]
0x1400b19fb  mov     rsi, rcx
0x1400b19fe  mov     [rbp+57h+var_98], eax
0x1400b1a01  cmp     rbx, rdx
0x1400b1a04  jz      loc_1400B1BCF
0x1400b1a0a  test    rbx, rbx
0x1400b1a0d  jnz     short loc_1400B1A19
0x1400b1a0f  mov     eax, 0C000000Dh
0x1400b1a14  jmp     loc_1400B1BCF
0x1400b1a19  test    rdx, rdx
0x1400b1a1c  jz      short loc_1400B1A28
0x1400b1a1e  mov     eax, 0C0000022h
0x1400b1a23  jmp     loc_1400B1BCF
0x1400b1a28  call    cs:__imp_NsiReferenceDefaultObjectSecurity
0x1400b1a2f  nop     dword ptr [rax+rax+00h]
0x1400b1a34  mov     rdi, rax
0x1400b1a37  test    rax, rax
0x1400b1a3a  jnz     short loc_1400B1A46
0x1400b1a3c  mov     eax, 0C00000D7h
0x1400b1a41  jmp     loc_1400B1BCF
0x1400b1a46  xorps   xmm0, xmm0
0x1400b1a49  mov     [rbp+57h+var_A0], 0
0x1400b1a4d  xorps   xmm1, xmm1
0x1400b1a50  mov     [rbp+57h+var_9C], 0
0x1400b1a57  lea     r8, [rbp+57h+SubjectContext]; SubjectContext
0x1400b1a5b  mov     rdx, rbx; Process
0x1400b1a5e  xor     ecx, ecx; Thread
0x1400b1a60  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1400b1a64  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x1400b1a68  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1400b1a6c  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1400b1a70  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400b1a74  call    cs:__imp_SeCaptureSubjectContextEx
0x1400b1a7b  nop     dword ptr [rax+rax+00h]
0x1400b1a80  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400b1a84  call    cs:__imp_SeLockSubjectContext
0x1400b1a8b  nop     dword ptr [rax+rax+00h]
0x1400b1a90  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400b1a97  nop     dword ptr [rax+rax+00h]
0x1400b1a9c  lea     rcx, [rbp+57h+var_98]
0x1400b1aa0  mov     r9d, 3; DesiredAccess
0x1400b1aa6  mov     [rsp+100h+AccessStatus], rcx; AccessStatus
0x1400b1aab  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400b1aaf  lea     rcx, [rbp+57h+var_9C]
0x1400b1ab3  mov     r8b, 1; SubjectContextLocked
0x1400b1ab6  mov     [rsp+100h+GrantedAccess], rcx; GrantedAccess
0x1400b1abb  mov     rcx, rdi; SecurityDescriptor
0x1400b1abe  mov     [rsp+100h+AccessMode], 1; AccessMode
0x1400b1ac3  mov     [rsp+100h+GenericMapping], rax; GenericMapping
0x1400b1ac8  mov     [rsp+100h+Privileges], 0; Privileges
0x1400b1ad1  mov     [rsp+100h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400b1ad9  call    cs:__imp_SeAccessCheck
0x1400b1ae0  nop     dword ptr [rax+rax+00h]
0x1400b1ae5  lea     rdx, aTcpIp; "TCP/IP"
0x1400b1aec  mov     bl, al
0x1400b1aee  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400b1af2  call    cs:__imp_RtlInitUnicodeString
0x1400b1af9  nop     dword ptr [rax+rax+00h]
0x1400b1afe  lea     rdx, aInternetportre; "InternetPortReservation"
0x1400b1b05  lea     rcx, [rbp+57h+var_60]; DestinationString
0x1400b1b09  call    cs:__imp_RtlInitUnicodeString
0x1400b1b10  nop     dword ptr [rax+rax+00h]
0x1400b1b15  movzx   eax, word ptr [rsi+0Ah]
0x1400b1b19  lea     r8, aPortsUU; "Ports %u-%u"
0x1400b1b20  movzx   r9d, word ptr [rsi+8]
0x1400b1b25  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400b1b29  mov     edx, 28h ; '('; cbDest
0x1400b1b2e  mov     [rsp+100h+PreviouslyGrantedAccess], eax
0x1400b1b32  call    RtlStringCbPrintfW
0x1400b1b37  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1400b1b3b  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1400b1b3f  call    cs:__imp_RtlInitUnicodeString
0x1400b1b46  nop     dword ptr [rax+rax+00h]
0x1400b1b4b  lea     rax, [rbp+57h+var_A0]
0x1400b1b4f  xor     edx, edx
0x1400b1b51  mov     [rsp+100h+var_B0], rax
0x1400b1b56  lea     r9, [rbp+57h+var_70]
0x1400b1b5a  mov     eax, [rbp+57h+var_9C]
0x1400b1b5d  lea     r8, [rbp+57h+var_60]
0x1400b1b61  mov     byte ptr [rsp+100h+AccessStatus], bl
0x1400b1b65  lea     rcx, [rbp+57h+DestinationString]
0x1400b1b69  mov     [rsp+100h+GrantedAccess], 0
0x1400b1b72  mov     dword ptr [rsp+100h+AccessMode], eax
0x1400b1b76  lea     rax, [rbp+57h+SubjectContext]
0x1400b1b7a  mov     dword ptr [rsp+100h+GenericMapping], 3
0x1400b1b82  mov     [rsp+100h+Privileges], rax
0x1400b1b87  mov     qword ptr [rsp+100h+PreviouslyGrantedAccess], rdi
0x1400b1b8c  call    cs:__imp_SeOpenObjectAuditAlarmForNonObObject
0x1400b1b93  nop     dword ptr [rax+rax+00h]
0x1400b1b98  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400b1b9c  call    cs:__imp_SeUnlockSubjectContext
0x1400b1ba3  nop     dword ptr [rax+rax+00h]
0x1400b1ba8  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400b1bac  call    cs:__imp_SeReleaseSubjectContext
0x1400b1bb3  nop     dword ptr [rax+rax+00h]
0x1400b1bb8  mov     edx, 1
0x1400b1bbd  mov     rcx, rdi
0x1400b1bc0  call    cs:__imp_ObDereferenceSecurityDescriptor
0x1400b1bc7  nop     dword ptr [rax+rax+00h]
0x1400b1bcc  mov     eax, [rbp+57h+var_98]
0x1400b1bcf  mov     rcx, [rbp+57h+var_18]
0x1400b1bd3  xor     rcx, rsp; StackCookie
0x1400b1bd6  call    __security_check_cookie
0x1400b1bdb  mov     rbx, [rsp+100h+arg_10]
0x1400b1be3  add     rsp, 0F0h
0x1400b1bea  pop     rdi
0x1400b1beb  pop     rsi
0x1400b1bec  pop     rbp
0x1400b1bed  retn
```
