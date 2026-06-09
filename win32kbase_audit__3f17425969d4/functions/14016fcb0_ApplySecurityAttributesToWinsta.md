# ApplySecurityAttributesToWinsta

- ea: `0x14016fcb0`
- end: `0x14016fe4c`
- name: `ApplySecurityAttributesToWinsta`
- size: `412`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14006f3a4`
- `0x14016fcb0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14016fcf5`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14016fcf5`
- `ntoskrnl!SeLockSubjectContext` at `0x14016fd05`
- `ntoskrnl!SeLockSubjectContext` at `0x14016fd05`
- `ntoskrnl!ObQueryNameInfo` at `0x14016fd14`
- `ntoskrnl!ObQueryNameInfo` at `0x14016fd14`
- `ntoskrnl!ObGetObjectSecurity` at `0x14016fe01`
- `ntoskrnl!ObGetObjectSecurity` at `0x14016fe01`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016fd7c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016fe1b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016fd7c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14016fe1b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016fd8c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016fe2b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016fd8c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14016fe2b`
- `ntoskrnl!SeAssignSecurity` at `0x14016fd57`
- `ntoskrnl!SeAssignSecurity` at `0x14016fd57`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14016fd6c`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14016fd6c`
- `ntoskrnl!ObSetSecurityDescriptorInfo` at `0x14016fdc3`
- `ntoskrnl!ObSetSecurityDescriptorInfo` at `0x14016fdc3`
- `ntoskrnl!SeDeassignSecurity` at `0x14016fdd5`
- `ntoskrnl!SeDeassignSecurity` at `0x14016fdd5`

## pseudocode

```c
__int64 __fastcall ApplySecurityAttributesToWinsta(__int64 a1, void *a2)
{
  void *v4; // rcx
  NTSTATUS ObjectSecurity; // ebx
  NTSTATUS v7; // ecx
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
      v7 = ObjectSecurity;
      if ( ObjectSecurity == -1073741790 )
        v7 = -1073741790;
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
0x14016fcb0  mov     [rsp-18h+arg_0], rbx
0x14016fcb5  mov     [rsp-18h+arg_8], rsi
0x14016fcba  push    rbp
0x14016fcbb  push    rdi
0x14016fcbc  push    r12
0x14016fcbe  mov     rbp, rsp
0x14016fcc1  sub     rsp, 70h
0x14016fcc5  xorps   xmm0, xmm0
0x14016fcc8  mov     [rbp+ParentDescriptor], 0
0x14016fcd0  mov     rdi, rcx
0x14016fcd3  mov     [rbp+NewDescriptor], 0
0x14016fcdb  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016fcdf  mov     [rbp+arg_18], 0
0x14016fce6  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14016fcea  mov     rsi, rdx
0x14016fced  mov     [rbp+MemoryAllocated], 0
0x14016fcf1  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14016fcf5  call    cs:__imp_SeCaptureSubjectContext
0x14016fcfc  nop     dword ptr [rax+rax+00h]
0x14016fd01  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016fd05  call    cs:__imp_SeLockSubjectContext
0x14016fd0c  nop     dword ptr [rax+rax+00h]
0x14016fd11  mov     rcx, rdi
0x14016fd14  call    cs:__imp_ObQueryNameInfo
0x14016fd1b  nop     dword ptr [rax+rax+00h]
0x14016fd20  mov     rcx, [rax]; Object
0x14016fd23  test    rcx, rcx
0x14016fd26  jnz     loc_14016FDF9
0x14016fd2c  mov     rcx, [rbp+ParentDescriptor]; ParentDescriptor
0x14016fd30  lea     rax, [rbp+SubjectContext]
0x14016fd34  mov     [rsp+70h+PoolType], 1; PoolType
0x14016fd3c  lea     r12, WinStaMapping
0x14016fd43  mov     [rsp+70h+GenericMapping], r12; GenericMapping
0x14016fd48  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x14016fd4c  mov     r9b, 1; IsDirectoryObject
0x14016fd4f  mov     [rsp+70h+var_50], rax; SubjectContext
0x14016fd54  mov     rdx, rsi; ExplicitDescriptor
0x14016fd57  call    cs:__imp_SeAssignSecurity
0x14016fd5e  nop     dword ptr [rax+rax+00h]
0x14016fd63  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x14016fd66  mov     ebx, eax
0x14016fd68  mov     rcx, [rbp+ParentDescriptor]; SecurityDescriptor
0x14016fd6c  call    cs:__imp_ObReleaseObjectSecurity
0x14016fd73  nop     dword ptr [rax+rax+00h]
0x14016fd78  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016fd7c  call    cs:__imp_SeUnlockSubjectContext
0x14016fd83  nop     dword ptr [rax+rax+00h]
0x14016fd88  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016fd8c  call    cs:__imp_SeReleaseSubjectContext
0x14016fd93  nop     dword ptr [rax+rax+00h]
0x14016fd98  test    ebx, ebx
0x14016fd9a  js      loc_14016FE39
0x14016fda0  mov     r8, [rbp+NewDescriptor]
0x14016fda4  lea     r9, [rdi-8]
0x14016fda8  mov     [rsp+70h+GenericMapping], r12
0x14016fdad  lea     rdx, [rbp+arg_18]
0x14016fdb1  mov     rcx, rdi
0x14016fdb4  mov     dword ptr [rsp+70h+var_50], 1
0x14016fdbc  mov     [rbp+arg_18], 0Fh
0x14016fdc3  call    cs:__imp_ObSetSecurityDescriptorInfo
0x14016fdca  nop     dword ptr [rax+rax+00h]
0x14016fdcf  lea     rcx, [rbp+NewDescriptor]; SecurityDescriptor
0x14016fdd3  mov     ebx, eax
0x14016fdd5  call    cs:__imp_SeDeassignSecurity
0x14016fddc  nop     dword ptr [rax+rax+00h]
0x14016fde1  lea     r11, [rsp+70h+var_s0]
0x14016fde6  mov     eax, ebx
0x14016fde8  mov     rbx, [r11+20h]
0x14016fdec  mov     rsi, [r11+28h]
0x14016fdf0  mov     rsp, r11
0x14016fdf3  pop     r12
0x14016fdf5  pop     rdi
0x14016fdf6  pop     rbp
0x14016fdf7  retn
0x14016fdf9  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x14016fdfd  lea     rdx, [rbp+ParentDescriptor]; SecurityDescriptor
0x14016fe01  call    cs:__imp_ObGetObjectSecurity
0x14016fe08  nop     dword ptr [rax+rax+00h]
0x14016fe0d  mov     ebx, eax
0x14016fe0f  test    eax, eax
0x14016fe11  jns     loc_14016FD2C
0x14016fe17  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016fe1b  call    cs:__imp_SeUnlockSubjectContext
0x14016fe22  nop     dword ptr [rax+rax+00h]
0x14016fe27  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14016fe2b  call    cs:__imp_SeReleaseSubjectContext
0x14016fe32  nop     dword ptr [rax+rax+00h]
0x14016fe37  jmp     short loc_14016FDE1
0x14016fe39  mov     eax, 0C0000022h
0x14016fe3e  mov     ecx, ebx
0x14016fe40  cmp     ebx, eax
0x14016fe42  cmovz   ecx, eax
0x14016fe45  call    SetLastNtError
0x14016fe4a  jmp     short loc_14016FDE1
```
