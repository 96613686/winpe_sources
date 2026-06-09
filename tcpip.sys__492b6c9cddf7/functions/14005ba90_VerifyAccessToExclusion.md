# VerifyAccessToExclusion

- ea: `0x14005ba90`
- end: `0x14005bcaf`
- name: `VerifyAccessToExclusion`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005ba3c`

## callees

- `0x14005ba90`
- `0x14005e72c`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005bc80`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005bc80`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005bc6c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005bc6c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005bc5c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005bc5c`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005bc4c`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005bc4c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005bb50`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005bb50`
- `ntoskrnl!SeAccessCheck` at `0x14005bb99`
- `ntoskrnl!SeAccessCheck` at `0x14005bb99`
- `ntoskrnl!SeLockSubjectContext` at `0x14005bb44`
- `ntoskrnl!SeLockSubjectContext` at `0x14005bb44`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005bb34`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005bb34`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bbb2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bbc9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bbff`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bbb2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bbc9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bbff`
- `NETIO!NsiReferenceDefaultObjectSecurity` at `0x14005bae8`
- `NETIO!NsiReferenceDefaultObjectSecurity` at `0x14005bae8`

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
0x14005ba90  mov     [rsp-8+arg_10], rbx
0x14005ba95  push    rbp
0x14005ba96  push    rsi
0x14005ba97  push    rdi
0x14005ba98  lea     rbp, [rsp-47h]
0x14005ba9d  sub     rsp, 0F0h
0x14005baa4  mov     rax, cs:__security_cookie
0x14005baab  xor     rax, rsp
0x14005baae  mov     [rbp+57h+var_18], rax
0x14005bab2  mov     rbx, rdx
0x14005bab5  xor     eax, eax
0x14005bab7  mov     rdx, [rcx+28h]
0x14005babb  mov     rsi, rcx
0x14005babe  mov     [rbp+57h+var_98], eax
0x14005bac1  cmp     rbx, rdx
0x14005bac4  jz      loc_14005BC8F
0x14005baca  test    rbx, rbx
0x14005bacd  jnz     short loc_14005BAD9
0x14005bacf  mov     eax, 0C000000Dh
0x14005bad4  jmp     loc_14005BC8F
0x14005bad9  test    rdx, rdx
0x14005badc  jz      short loc_14005BAE8
0x14005bade  mov     eax, 0C0000022h
0x14005bae3  jmp     loc_14005BC8F
0x14005bae8  call    cs:__imp_NsiReferenceDefaultObjectSecurity
0x14005baef  nop     dword ptr [rax+rax+00h]
0x14005baf4  mov     rdi, rax
0x14005baf7  test    rax, rax
0x14005bafa  jnz     short loc_14005BB06
0x14005bafc  mov     eax, 0C00000D7h
0x14005bb01  jmp     loc_14005BC8F
0x14005bb06  xorps   xmm0, xmm0
0x14005bb09  mov     [rbp+57h+var_A0], 0
0x14005bb0d  xorps   xmm1, xmm1
0x14005bb10  mov     [rbp+57h+var_9C], 0
0x14005bb17  lea     r8, [rbp+57h+SubjectContext]; SubjectContext
0x14005bb1b  mov     rdx, rbx; Process
0x14005bb1e  xor     ecx, ecx; Thread
0x14005bb20  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x14005bb24  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x14005bb28  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14005bb2c  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14005bb30  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005bb34  call    cs:__imp_SeCaptureSubjectContextEx
0x14005bb3b  nop     dword ptr [rax+rax+00h]
0x14005bb40  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005bb44  call    cs:__imp_SeLockSubjectContext
0x14005bb4b  nop     dword ptr [rax+rax+00h]
0x14005bb50  call    cs:__imp_IoGetFileObjectGenericMapping
0x14005bb57  nop     dword ptr [rax+rax+00h]
0x14005bb5c  lea     rcx, [rbp+57h+var_98]
0x14005bb60  mov     r9d, 3; DesiredAccess
0x14005bb66  mov     [rsp+100h+AccessStatus], rcx; AccessStatus
0x14005bb6b  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x14005bb6f  lea     rcx, [rbp+57h+var_9C]
0x14005bb73  mov     r8b, 1; SubjectContextLocked
0x14005bb76  mov     [rsp+100h+GrantedAccess], rcx; GrantedAccess
0x14005bb7b  mov     rcx, rdi; SecurityDescriptor
0x14005bb7e  mov     [rsp+100h+AccessMode], 1; AccessMode
0x14005bb83  mov     [rsp+100h+GenericMapping], rax; GenericMapping
0x14005bb88  mov     [rsp+100h+Privileges], 0; Privileges
0x14005bb91  mov     [rsp+100h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14005bb99  call    cs:__imp_SeAccessCheck
0x14005bba0  nop     dword ptr [rax+rax+00h]
0x14005bba5  lea     rdx, SourceString; "TCP/IP"
0x14005bbac  mov     bl, al
0x14005bbae  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005bbb2  call    cs:__imp_RtlInitUnicodeString
0x14005bbb9  nop     dword ptr [rax+rax+00h]
0x14005bbbe  lea     rdx, aInternetportre; "InternetPortReservation"
0x14005bbc5  lea     rcx, [rbp+57h+var_60]; DestinationString
0x14005bbc9  call    cs:__imp_RtlInitUnicodeString
0x14005bbd0  nop     dword ptr [rax+rax+00h]
0x14005bbd5  movzx   eax, word ptr [rsi+0Ah]
0x14005bbd9  lea     r8, aPortsUU; "Ports %u-%u"
0x14005bbe0  movzx   r9d, word ptr [rsi+8]
0x14005bbe5  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14005bbe9  mov     edx, 28h ; '('; cbDest
0x14005bbee  mov     [rsp+100h+PreviouslyGrantedAccess], eax
0x14005bbf2  call    RtlStringCbPrintfW
0x14005bbf7  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14005bbfb  lea     rcx, [rbp+57h+var_70]; DestinationString
0x14005bbff  call    cs:__imp_RtlInitUnicodeString
0x14005bc06  nop     dword ptr [rax+rax+00h]
0x14005bc0b  lea     rax, [rbp+57h+var_A0]
0x14005bc0f  xor     edx, edx
0x14005bc11  mov     [rsp+100h+var_B0], rax
0x14005bc16  lea     r9, [rbp+57h+var_70]
0x14005bc1a  mov     eax, [rbp+57h+var_9C]
0x14005bc1d  lea     r8, [rbp+57h+var_60]
0x14005bc21  mov     byte ptr [rsp+100h+AccessStatus], bl
0x14005bc25  lea     rcx, [rbp+57h+DestinationString]
0x14005bc29  mov     [rsp+100h+GrantedAccess], 0
0x14005bc32  mov     dword ptr [rsp+100h+AccessMode], eax
0x14005bc36  lea     rax, [rbp+57h+SubjectContext]
0x14005bc3a  mov     dword ptr [rsp+100h+GenericMapping], 3
0x14005bc42  mov     [rsp+100h+Privileges], rax
0x14005bc47  mov     qword ptr [rsp+100h+PreviouslyGrantedAccess], rdi
0x14005bc4c  call    cs:__imp_SeOpenObjectAuditAlarmForNonObObject
0x14005bc53  nop     dword ptr [rax+rax+00h]
0x14005bc58  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005bc5c  call    cs:__imp_SeUnlockSubjectContext
0x14005bc63  nop     dword ptr [rax+rax+00h]
0x14005bc68  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005bc6c  call    cs:__imp_SeReleaseSubjectContext
0x14005bc73  nop     dword ptr [rax+rax+00h]
0x14005bc78  mov     edx, 1
0x14005bc7d  mov     rcx, rdi
0x14005bc80  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14005bc87  nop     dword ptr [rax+rax+00h]
0x14005bc8c  mov     eax, [rbp+57h+var_98]
0x14005bc8f  mov     rcx, [rbp+57h+var_18]
0x14005bc93  xor     rcx, rsp; StackCookie
0x14005bc96  call    __security_check_cookie
0x14005bc9b  mov     rbx, [rsp+100h+arg_10]
0x14005bca3  add     rsp, 0F0h
0x14005bcaa  pop     rdi
0x14005bcab  pop     rsi
0x14005bcac  pop     rbp
0x14005bcad  retn
```
