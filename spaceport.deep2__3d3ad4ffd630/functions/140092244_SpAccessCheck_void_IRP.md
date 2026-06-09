# SpAccessCheck(void *,_IRP *)

- ea: `0x140092244`
- end: `0x14009233a`
- name: `?SpAccessCheck@@YAJPEAXPEAU_IRP@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, struct _IRP *)`
- caller_count: `10`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002de54`
- `0x140092340`
- `0x140092394`
- `0x140092fbc`
- `0x140097d58`
- `0x14009882c`
- `0x140098cd8`
- `0x14009905c`
- `0x1400997a8`
- `0x14009a4d4`

## callees

- `0x140092244`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x1400922e5`
- `ntoskrnl!SeAccessCheck` at `0x1400922e5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140092294`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140092294`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140092309`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400ba954`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140092309`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400ba954`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400922f8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400ba944`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400922f8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400ba944`
- `ntoskrnl!SeLockSubjectContext` at `0x140092284`
- `ntoskrnl!SeLockSubjectContext` at `0x140092284`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140092273`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140092273`

## pseudocode

```c
__int64 __fastcall SpAccessCheck(PSECURITY_DESCRIPTOR SecurityDescriptor, struct _IRP *a2)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+90h] [rbp+18h] BYREF
  DWORD GrantedAccess; // [rsp+98h] [rbp+20h] BYREF

  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessStatus = 0;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  LOBYTE(a2) = a2->RequestorMode;
  GenericMapping = IoGetFileObjectGenericMapping();
  LOBYTE(a2) = SeAccessCheck(
                 SecurityDescriptor,
                 &SubjectContext,
                 1u,
                 3u,
                 0,
                 0,
                 GenericMapping,
                 (KPROCESSOR_MODE)a2,
                 &GrantedAccess,
                 &AccessStatus);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  if ( (_BYTE)a2 )
    return 0;
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x140092244  mov     rax, rsp
0x140092247  mov     [rax+8], rbx
0x14009224b  push    rdi
0x14009224c  sub     rsp, 70h
0x140092250  mov     rbx, rdx
0x140092253  mov     rdi, rcx
0x140092256  mov     dword ptr [rax+20h], 0
0x14009225d  xorps   xmm0, xmm0
0x140092260  movups  xmmword ptr [rax-28h], xmm0
0x140092264  movups  xmmword ptr [rax-18h], xmm0
0x140092268  mov     dword ptr [rax+18h], 0
0x14009226f  lea     rcx, [rax-28h]; SubjectContext
0x140092273  call    cs:__imp_SeCaptureSubjectContext
0x14009227a  nop     dword ptr [rax+rax+00h]
0x14009227f  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140092284  call    cs:__imp_SeLockSubjectContext
0x14009228b  nop     dword ptr [rax+rax+00h]
0x140092290  nop
0x140092291  mov     bl, [rbx+40h]
0x140092294  call    cs:__imp_IoGetFileObjectGenericMapping
0x14009229b  nop     dword ptr [rax+rax+00h]
0x1400922a0  lea     rcx, [rsp+78h+arg_10]
0x1400922a8  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x1400922ad  lea     rcx, [rsp+78h+arg_18]
0x1400922b5  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x1400922ba  mov     [rsp+78h+AccessMode], bl; AccessMode
0x1400922be  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1400922c3  mov     [rsp+78h+Privileges], 0; Privileges
0x1400922cc  mov     [rsp+78h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400922d4  mov     r9d, 3; DesiredAccess
0x1400922da  mov     r8b, 1; SubjectContextLocked
0x1400922dd  lea     rdx, [rsp+78h+SubjectContext]; SubjectSecurityContext
0x1400922e2  mov     rcx, rdi; SecurityDescriptor
0x1400922e5  call    cs:__imp_SeAccessCheck
0x1400922ec  nop     dword ptr [rax+rax+00h]
0x1400922f1  mov     bl, al
0x1400922f3  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x1400922f8  call    cs:__imp_SeUnlockSubjectContext
0x1400922ff  nop     dword ptr [rax+rax+00h]
0x140092304  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140092309  call    cs:__imp_SeReleaseSubjectContext
0x140092310  nop     dword ptr [rax+rax+00h]
0x140092315  test    bl, bl
0x140092317  jz      short loc_140092324
0x140092319  mov     [rsp+78h+arg_10], 0
0x140092324  mov     eax, [rsp+78h+arg_10]
0x14009232b  mov     rbx, [rsp+78h+arg_0]
0x140092333  add     rsp, 70h
0x140092337  pop     rdi
0x140092338  retn
0x1400ba937  push    rbp
0x1400ba939  sub     rsp, 50h
0x1400ba93d  mov     rbp, rdx
0x1400ba940  lea     rcx, [rbp+50h]; SubjectContext
0x1400ba944  call    cs:__imp_SeUnlockSubjectContext
0x1400ba94b  nop     dword ptr [rax+rax+00h]
0x1400ba950  lea     rcx, [rbp+50h]; SubjectContext
0x1400ba954  call    cs:__imp_SeReleaseSubjectContext
0x1400ba95b  nop     dword ptr [rax+rax+00h]
0x1400ba960  nop
0x1400ba961  add     rsp, 50h
0x1400ba965  pop     rbp
0x1400ba966  retn
```
