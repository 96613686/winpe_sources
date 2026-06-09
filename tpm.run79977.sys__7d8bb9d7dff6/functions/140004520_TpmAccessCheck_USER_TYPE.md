# TpmAccessCheck(_USER_TYPE)

- ea: `0x140004520`
- end: `0x140004634`
- name: `?TpmAccessCheck@@YAJW4_USER_TYPE@@@Z`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003ad0`
- `0x140003c30`
- `0x140013bf0`

## callees

- `0x140004520`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140004554`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004554`
- `ntoskrnl!ExGetPreviousMode` at `0x140004560`
- `ntoskrnl!ExGetPreviousMode` at `0x140004560`
- `ntoskrnl!SeAccessCheck` at `0x1400045b0`
- `ntoskrnl!SeAccessCheck` at `0x1400045b0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400045c4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400045c4`

## pseudocode

```c
__int64 __fastcall TpmAccessCheck(int a1)
{
  __int64 *v1; // rbx
  KPROCESSOR_MODE AccessMode; // al
  BOOLEAN v3; // bl
  unsigned int v4; // ecx
  int v6; // ecx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+10h] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( a1 == 2 )
  {
    v1 = qword_14003B9F0;
  }
  else
  {
    v6 = a1 - 1;
    if ( v6 )
    {
      if ( v6 != 2 )
        return 3221225485LL;
      v1 = qword_14003D000;
    }
    else
    {
      v1 = qword_14003D048;
    }
  }
  SeCaptureSubjectContext(&SubjectContext);
  AccessMode = ExGetPreviousMode();
  v3 = SeAccessCheck(v1, &SubjectContext, 0, 1u, 0, 0, &GenericMapping, AccessMode, &GrantedAccess, &AccessStatus);
  SeReleaseSubjectContext(&SubjectContext);
  v4 = AccessStatus;
  if ( !v3 && (AccessStatus == -1073741790 || (AccessStatus & 0xC0000000) != 0xC0000000) )
    return (unsigned int)-1071050748;
  return v4;
}

```

## disassembly

```asm
0x140004520  mov     rax, rsp
0x140004523  mov     [rax+18h], rbx
0x140004527  push    rdi
0x140004528  sub     rsp, 70h
0x14000452c  xor     edi, edi
0x14000452e  xorps   xmm0, xmm0
0x140004531  mov     [rax+8], edi
0x140004534  mov     [rax+10h], edi
0x140004537  movups  xmmword ptr [rax-28h], xmm0
0x14000453b  movups  xmmword ptr [rax-18h], xmm0
0x14000453f  cmp     ecx, 2
0x140004542  jnz     loc_1400045FB
0x140004548  lea     rbx, qword_14003B9F0
0x14000454f  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x140004554  call    cs:__imp_SeCaptureSubjectContext
0x14000455b  nop     dword ptr [rax+rax+00h]
0x140004560  call    cs:__imp_ExGetPreviousMode
0x140004567  nop     dword ptr [rax+rax+00h]
0x14000456c  lea     rcx, [rsp+78h+arg_0]
0x140004574  mov     r9d, 1; DesiredAccess
0x14000457a  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x14000457f  lea     rdx, [rsp+78h+SubjectContext]; SubjectSecurityContext
0x140004584  lea     rcx, [rsp+78h+arg_8]
0x14000458c  xor     r8d, r8d; SubjectContextLocked
0x14000458f  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x140004594  mov     rcx, rbx; SecurityDescriptor
0x140004597  mov     [rsp+78h+AccessMode], al; AccessMode
0x14000459b  lea     rax, GenericMapping
0x1400045a2  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1400045a7  mov     [rsp+78h+Privileges], rdi; Privileges
0x1400045ac  mov     [rsp+78h+PreviouslyGrantedAccess], edi; PreviouslyGrantedAccess
0x1400045b0  call    cs:__imp_SeAccessCheck
0x1400045b7  nop     dword ptr [rax+rax+00h]
0x1400045bc  lea     rcx, [rsp+78h+SubjectContext]; SubjectContext
0x1400045c1  movzx   ebx, al
0x1400045c4  call    cs:__imp_SeReleaseSubjectContext
0x1400045cb  nop     dword ptr [rax+rax+00h]
0x1400045d0  mov     ecx, [rsp+78h+arg_0]
0x1400045d7  test    bl, bl
0x1400045d9  jz      short loc_1400045EC
0x1400045db  mov     eax, ecx
0x1400045dd  mov     rbx, [rsp+78h+arg_10]
0x1400045e5  add     rsp, 70h
0x1400045e9  pop     rdi
0x1400045ea  retn
0x1400045ec  cmp     ecx, 0C0000022h
0x1400045f2  jnz     short loc_140004624
0x1400045f4  mov     ecx, 0C0291004h
0x1400045f9  jmp     short loc_1400045DB
0x1400045fb  sub     ecx, 1
0x1400045fe  jz      short loc_140004618
0x140004600  cmp     ecx, 2
0x140004603  jz      short loc_14000460C
0x140004605  mov     eax, 0C000000Dh
0x14000460a  jmp     short loc_1400045DD
0x14000460c  lea     rbx, qword_14003D000
0x140004613  jmp     loc_14000454F
0x140004618  lea     rbx, qword_14003D048
0x14000461f  jmp     loc_14000454F
0x140004624  mov     eax, ecx
0x140004626  and     eax, 0C0000000h
0x14000462b  cmp     eax, 0C0000000h
0x140004630  jz      short loc_1400045DB
0x140004632  jmp     short loc_1400045F4
```
