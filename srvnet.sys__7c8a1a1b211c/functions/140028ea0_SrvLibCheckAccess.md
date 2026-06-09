# SrvLibCheckAccess

- ea: `0x140028ea0`
- end: `0x140028f72`
- name: `SrvLibCheckAccess`
- size: `210`
- prototype: `__int64 __fastcall(int, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140009d80`
- `0x140028ea0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140028ede`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140028ede`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028f56`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028f56`
- `ntoskrnl!SeFreePrivileges` at `0x140028f46`
- `ntoskrnl!SeFreePrivileges` at `0x140028f46`

## pseudocode

```c
__int64 __fastcall SrvLibCheckAccess(__int64 a1, int a2, __int64 a3)
{
  __int64 v7; // [rsp+60h] [rbp+7h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+68h] [rbp+Fh] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+70h] [rbp+17h] BYREF
  __int64 v10; // [rsp+D8h] [rbp+7Fh] BYREF

  LODWORD(v7) = 0;
  Privileges = 0;
  LODWORD(v10) = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  if ( (unsigned __int8)SrvLibSeAccessCheck(
                          a1,
                          (__int64)&SubjectContext,
                          0,
                          a2,
                          0,
                          (__int64)&Privileges,
                          a3,
                          1,
                          (__int64)&v7,
                          0,
                          (__int64)&v10) )
    LODWORD(v10) = 0;
  if ( Privileges )
    SeFreePrivileges(Privileges);
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140028ea0  push    rbp
0x140028ea2  push    rbx
0x140028ea3  push    rsi
0x140028ea4  push    rdi
0x140028ea5  lea     rbp, [rsp-3Fh]
0x140028eaa  sub     rsp, 98h
0x140028eb1  xorps   xmm0, xmm0
0x140028eb4  mov     dword ptr [rbp+57h+var_50], 0
0x140028ebb  mov     rsi, rcx
0x140028ebe  mov     [rbp+57h+Privileges], 0
0x140028ec6  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140028eca  mov     dword ptr [rbp+57h+arg_18], 0
0x140028ed1  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140028ed5  mov     rbx, r8
0x140028ed8  mov     edi, edx
0x140028eda  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x140028ede  call    cs:__imp_SeCaptureSubjectContext
0x140028ee5  nop     dword ptr [rax+rax+00h]
0x140028eea  lea     rax, [rbp+57h+arg_18]
0x140028eee  mov     r9d, edi; int
0x140028ef1  mov     [rsp+0B0h+var_60], rax; __int64
0x140028ef6  lea     rdx, [rbp+57h+SubjectContext]; int
0x140028efa  mov     [rsp+0B0h+var_68], 0; void *
0x140028f03  lea     rax, [rbp+57h+var_50]
0x140028f07  mov     [rsp+0B0h+var_70], rax; __int64
0x140028f0c  xor     r8d, r8d; int
0x140028f0f  mov     [rsp+0B0h+var_78], 1; char
0x140028f14  lea     rax, [rbp+57h+Privileges]
0x140028f18  mov     [rsp+0B0h+var_80], rbx; __int64
0x140028f1d  mov     rcx, rsi; int
0x140028f20  mov     [rsp+0B0h+var_88], rax; __int64
0x140028f25  mov     [rsp+0B0h+var_90], 0; int
0x140028f2d  call    SrvLibSeAccessCheck
0x140028f32  test    al, al
0x140028f34  jz      short loc_140028F3D
0x140028f36  mov     dword ptr [rbp+57h+arg_18], 0
0x140028f3d  mov     rcx, [rbp+57h+Privileges]; Privileges
0x140028f41  test    rcx, rcx
0x140028f44  jz      short loc_140028F52
0x140028f46  call    cs:__imp_SeFreePrivileges
0x140028f4d  nop     dword ptr [rax+rax+00h]
0x140028f52  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140028f56  call    cs:__imp_SeReleaseSubjectContext
0x140028f5d  nop     dword ptr [rax+rax+00h]
0x140028f62  mov     eax, dword ptr [rbp+57h+arg_18]
0x140028f65  add     rsp, 98h
0x140028f6c  pop     rdi
0x140028f6d  pop     rsi
0x140028f6e  pop     rbx
0x140028f6f  pop     rbp
0x140028f70  retn
```
