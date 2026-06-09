# VmpCheckSecurity(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x1400109d4`
- end: `0x140010ad1`
- name: `?VmpCheckSecurity@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x140010a86`
- `ntoskrnl!SeAccessCheck` at `0x140010a86`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140010a2e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140010a2e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140010aaa`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140017164`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140010aaa`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140017164`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140010a99`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140017154`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140010a99`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140017154`
- `ntoskrnl!SeLockSubjectContext` at `0x140010a14`
- `ntoskrnl!SeLockSubjectContext` at `0x140010a14`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140010a03`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140010a03`

## pseudocode

```c
__int64 __fastcall VmpCheckSecurity(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  __int64 result; // rax
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+90h] [rbp+18h] BYREF
  DWORD GrantedAccess; // [rsp+98h] [rbp+20h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessStatus = 0;
  GrantedAccess = 0;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AccessStatus = -1073741790;
  LOBYTE(a2) = a2->RequestorMode;
  GenericMapping = IoGetFileObjectGenericMapping();
  LOBYTE(a2) = SeAccessCheck(
                 *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)a1 + 272LL),
                 &SubjectContext,
                 1u,
                 1u,
                 0,
                 0,
                 GenericMapping,
                 (KPROCESSOR_MODE)a2,
                 &GrantedAccess,
                 &AccessStatus);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  result = 0;
  if ( !(_BYTE)a2 )
    return (unsigned int)AccessStatus;
  return result;
}

```

## disassembly

```asm
0x1400109d4  mov     rax, rsp
0x1400109d7  mov     [rax+8], rbx
0x1400109db  push    rdi
0x1400109dc  sub     rsp, 70h
0x1400109e0  mov     rbx, rdx
0x1400109e3  mov     rdi, rcx
0x1400109e6  xorps   xmm0, xmm0
0x1400109e9  movups  xmmword ptr [rax-28h], xmm0
0x1400109ed  movups  xmmword ptr [rax-18h], xmm0
0x1400109f1  mov     dword ptr [rax+18h], 0
0x1400109f8  mov     dword ptr [rax+20h], 0
0x1400109ff  lea     rcx, [rax-28h]; SubjectContext
0x140010a03  call    cs:__imp_SeCaptureSubjectContext
0x140010a0a  nop     dword ptr [rax+rax+00h]
0x140010a0f  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140010a14  call    cs:__imp_SeLockSubjectContext
0x140010a1b  nop     dword ptr [rax+rax+00h]
0x140010a20  mov     [rsp+78h+arg_10], 0C0000022h
0x140010a2b  mov     bl, [rbx+40h]
0x140010a2e  call    cs:__imp_IoGetFileObjectGenericMapping
0x140010a35  nop     dword ptr [rax+rax+00h]
0x140010a3a  mov     rcx, [rdi]
0x140010a3d  lea     rdx, [rsp+78h+arg_10]
0x140010a45  mov     [rsp+78h+AccessStatus], rdx; AccessStatus
0x140010a4a  lea     rdx, [rsp+78h+arg_18]
0x140010a52  mov     [rsp+78h+GrantedAccess], rdx; GrantedAccess
0x140010a57  mov     [rsp+78h+AccessMode], bl; AccessMode
0x140010a5b  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x140010a60  mov     [rsp+78h+Privileges], 0; Privileges
0x140010a69  mov     [rsp+78h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140010a71  mov     r9d, 1; DesiredAccess
0x140010a77  mov     r8b, r9b; SubjectContextLocked
0x140010a7a  lea     rdx, [rsp+78h+SubjectContext]; SubjectSecurityContext
0x140010a7f  mov     rcx, [rcx+110h]; SecurityDescriptor
0x140010a86  call    cs:__imp_SeAccessCheck
0x140010a8d  nop     dword ptr [rax+rax+00h]
0x140010a92  mov     bl, al
0x140010a94  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140010a99  call    cs:__imp_SeUnlockSubjectContext
0x140010aa0  nop     dword ptr [rax+rax+00h]
0x140010aa5  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140010aaa  call    cs:__imp_SeReleaseSubjectContext
0x140010ab1  nop     dword ptr [rax+rax+00h]
0x140010ab6  xor     eax, eax
0x140010ab8  test    bl, bl
0x140010aba  cmovz   eax, [rsp+78h+arg_10]
0x140010ac2  mov     rbx, [rsp+78h+arg_0]
0x140010aca  add     rsp, 70h
0x140010ace  pop     rdi
0x140010acf  retn
0x140017147  push    rbp
0x140017149  sub     rsp, 50h
0x14001714d  mov     rbp, rdx
0x140017150  lea     rcx, [rbp+50h]; SubjectContext
0x140017154  call    cs:__imp_SeUnlockSubjectContext
0x14001715b  nop     dword ptr [rax+rax+00h]
0x140017160  lea     rcx, [rbp+50h]; SubjectContext
0x140017164  call    cs:__imp_SeReleaseSubjectContext
0x14001716b  nop     dword ptr [rax+rax+00h]
0x140017170  nop
0x140017171  add     rsp, 50h
0x140017175  pop     rbp
0x140017176  retn
```
