# ApplySecurityAttributesToWinsta

- ea: `0x14016df80`
- end: `0x14016e11c`
- name: `ApplySecurityAttributesToWinsta`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400325a4`
- `0x14016df80`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14016dfc5`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14016dfc5`
- `ntoskrnl!SeLockSubjectContext` at `0x14016dfd5`
- `ntoskrnl!SeLockSubjectContext` at `0x14016dfd5`
- `ntoskrnl!ObQueryNameInfo` at `0x14016dfe4`
- `ntoskrnl!ObQueryNameInfo` at `0x14016dfe4`
- `ntoskrnl!ObGetObjectSecurity` at `0x14016e0d1`
- `ntoskrnl!ObGetObjectSecurity` at `0x14016e0d1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016e04c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016e0eb`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016e04c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016e0eb`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016e05c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016e0fb`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016e05c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016e0fb`
- `ntoskrnl!SeAssignSecurity` at `0x14016e027`
- `ntoskrnl!SeAssignSecurity` at `0x14016e027`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14016e03c`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14016e03c`
- `ntoskrnl!ObSetSecurityDescriptorInfo` at `0x14016e093`
- `ntoskrnl!ObSetSecurityDescriptorInfo` at `0x14016e093`
- `ntoskrnl!SeDeassignSecurity` at `0x14016e0a5`
- `ntoskrnl!SeDeassignSecurity` at `0x14016e0a5`

## pseudocode

```c
__int64 __fastcall ApplySecurityAttributesToWinsta(__int64 a1, void *a2)
{
  void *v4; // rcx
  NTSTATUS ObjectSecurity; // ebx
  __int64 v7; // rcx
  PSECURITY_DESCRIPTOR ParentDescriptor; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+48h] [rbp-28h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-20h] BYREF
  BOOLEAN MemoryAllocated; // [rsp+A0h] [rbp+30h] BYREF
  int v12; // [rsp+A8h] [rbp+38h] BYREF

  ParentDescriptor = 0;
  NewDescriptor = 0;
  v12 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  MemoryAllocated = 0;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  v4 = *(void **)ObQueryNameInfo(a1);
  if ( v4 && (ObjectSecurity = ObGetObjectSecurity(v4, &ParentDescriptor, &MemoryAllocated), ObjectSecurity < 0) )
  {
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
  }
  else
  {
    ObjectSecurity = SeAssignSecurity(
                       ParentDescriptor,
                       a2,
                       &NewDescriptor,
                       1u,
                       &SubjectContext,
                       (PGENERIC_MAPPING)&WinStaMapping,
                       PagedPool);
    ObReleaseObjectSecurity(ParentDescriptor, MemoryAllocated);
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
    if ( ObjectSecurity < 0 )
    {
      v7 = (unsigned int)ObjectSecurity;
      if ( ObjectSecurity == -1073741790 )
        v7 = 3221225506LL;
      SetLastNtError(v7);
    }
    else
    {
      v12 = 15;
      ObjectSecurity = ObSetSecurityDescriptorInfo(a1, &v12, NewDescriptor, a1 - 8, 1, &WinStaMapping);
      SeDeassignSecurity(&NewDescriptor);
    }
  }
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x14016df80  mov     [rsp-18h+arg_0], rbx
0x14016df85  mov     [rsp-18h+arg_8], rsi
0x14016df8a  push    rbp
0x14016df8b  push    rdi
0x14016df8c  push    r12
0x14016df8e  mov     rbp, rsp
0x14016df91  sub     rsp, 70h
0x14016df95  xorps   xmm0, xmm0
0x14016df98  mov     [rbp+ParentDescriptor], 0
0x14016dfa0  mov     rdi, rcx
0x14016dfa3  mov     [rbp+NewDescriptor], 0
0x14016dfab  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016dfaf  mov     [rbp+arg_18], 0
0x14016dfb6  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14016dfba  mov     rsi, rdx
0x14016dfbd  mov     [rbp+MemoryAllocated], 0
0x14016dfc1  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14016dfc5  call    cs:__imp_SeCaptureSubjectContext
0x14016dfcc  nop     dword ptr [rax+rax+00h]
0x14016dfd1  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016dfd5  call    cs:__imp_SeLockSubjectContext
0x14016dfdc  nop     dword ptr [rax+rax+00h]
0x14016dfe1  mov     rcx, rdi
0x14016dfe4  call    cs:__imp_ObQueryNameInfo
0x14016dfeb  nop     dword ptr [rax+rax+00h]
0x14016dff0  mov     rcx, [rax]; Object
0x14016dff3  test    rcx, rcx
0x14016dff6  jnz     loc_14016E0C9
0x14016dffc  mov     rcx, [rbp+ParentDescriptor]; ParentDescriptor
0x14016e000  lea     rax, [rbp+SubjectContext]
0x14016e004  mov     [rsp+70h+PoolType], 1; PoolType
0x14016e00c  lea     r12, WinStaMapping
0x14016e013  mov     [rsp+70h+GenericMapping], r12; GenericMapping
0x14016e018  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x14016e01c  mov     r9b, 1; IsDirectoryObject
0x14016e01f  mov     [rsp+70h+var_50], rax; SubjectContext
0x14016e024  mov     rdx, rsi; ExplicitDescriptor
0x14016e027  call    cs:__imp_SeAssignSecurity
0x14016e02e  nop     dword ptr [rax+rax+00h]
0x14016e033  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x14016e036  mov     ebx, eax
0x14016e038  mov     rcx, [rbp+ParentDescriptor]; SecurityDescriptor
0x14016e03c  call    cs:__imp_ObReleaseObjectSecurity
0x14016e043  nop     dword ptr [rax+rax+00h]
0x14016e048  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016e04c  call    cs:__imp_SeUnlockSubjectContext
0x14016e053  nop     dword ptr [rax+rax+00h]
0x14016e058  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016e05c  call    cs:__imp_SeReleaseSubjectContext
0x14016e063  nop     dword ptr [rax+rax+00h]
0x14016e068  test    ebx, ebx
0x14016e06a  js      loc_14016E109
0x14016e070  mov     r8, [rbp+NewDescriptor]
0x14016e074  lea     r9, [rdi-8]
0x14016e078  mov     [rsp+70h+GenericMapping], r12
0x14016e07d  lea     rdx, [rbp+arg_18]
0x14016e081  mov     rcx, rdi
0x14016e084  mov     dword ptr [rsp+70h+var_50], 1
0x14016e08c  mov     [rbp+arg_18], 0Fh
0x14016e093  call    cs:__imp_ObSetSecurityDescriptorInfo
0x14016e09a  nop     dword ptr [rax+rax+00h]
0x14016e09f  lea     rcx, [rbp+NewDescriptor]; SecurityDescriptor
0x14016e0a3  mov     ebx, eax
0x14016e0a5  call    cs:__imp_SeDeassignSecurity
0x14016e0ac  nop     dword ptr [rax+rax+00h]
0x14016e0b1  lea     r11, [rsp+70h+var_s0]
0x14016e0b6  mov     eax, ebx
0x14016e0b8  mov     rbx, [r11+20h]
0x14016e0bc  mov     rsi, [r11+28h]
0x14016e0c0  mov     rsp, r11
0x14016e0c3  pop     r12
0x14016e0c5  pop     rdi
0x14016e0c6  pop     rbp
0x14016e0c7  retn
0x14016e0c9  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x14016e0cd  lea     rdx, [rbp+ParentDescriptor]; SecurityDescriptor
0x14016e0d1  call    cs:__imp_ObGetObjectSecurity
0x14016e0d8  nop     dword ptr [rax+rax+00h]
0x14016e0dd  mov     ebx, eax
0x14016e0df  test    eax, eax
0x14016e0e1  jns     loc_14016DFFC
0x14016e0e7  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016e0eb  call    cs:__imp_SeUnlockSubjectContext
0x14016e0f2  nop     dword ptr [rax+rax+00h]
0x14016e0f7  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016e0fb  call    cs:__imp_SeReleaseSubjectContext
0x14016e102  nop     dword ptr [rax+rax+00h]
0x14016e107  jmp     short loc_14016E0B1
0x14016e109  mov     eax, 0C0000022h
0x14016e10e  mov     ecx, ebx
0x14016e110  cmp     ebx, eax
0x14016e112  cmovz   ecx, eax
0x14016e115  call    SetLastNtError
0x14016e11a  jmp     short loc_14016E0B1
```
