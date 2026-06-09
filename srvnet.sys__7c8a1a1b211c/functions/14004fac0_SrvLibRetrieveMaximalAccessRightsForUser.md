# SrvLibRetrieveMaximalAccessRightsForUser

- ea: `0x14004fac0`
- end: `0x14004fbe3`
- name: `SrvLibRetrieveMaximalAccessRightsForUser`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140009d80`
- `0x14004fac0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14004fb02`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14004fb02`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004fb5f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14004fb5f`
- `ntoskrnl!SeFreePrivileges` at `0x14004fbb5`
- `ntoskrnl!SeFreePrivileges` at `0x14004fbb5`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14004fbce`
- `ntoskrnl!PsAssignImpersonationToken` at `0x14004fbce`
- `ksecdd!ImpersonateSecurityContext` at `0x14004fb89`
- `ksecdd!ImpersonateSecurityContext` at `0x14004fb89`

## pseudocode

```c
int __fastcall SrvLibRetrieveMaximalAccessRightsForUser(struct _SecHandle *a1, int a2, __int64 a3, _DWORD *a4, char a5)
{
  int result; // eax
  __int64 v9; // [rsp+60h] [rbp-58h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+68h] [rbp-50h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+70h] [rbp-48h] BYREF

  LODWORD(v9) = 0;
  Privileges = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( a5 )
    goto LABEL_2;
  if ( !a1->dwLower && !a1->dwUpper )
    return -1073741790;
  result = ImpersonateSecurityContext(a1);
  LODWORD(v9) = result;
  if ( result >= 0 )
  {
LABEL_2:
    SeCaptureSubjectContext(&SubjectContext);
    SrvLibSeAccessCheck(
      a2,
      (int)&SubjectContext,
      0,
      0x2000000,
      0,
      (__int64)&Privileges,
      a3,
      1,
      (__int64)a4,
      0,
      (__int64)&v9);
    if ( Privileges )
      SeFreePrivileges(Privileges);
    SeReleaseSubjectContext(&SubjectContext);
    if ( !a5 )
      PsAssignImpersonationToken(KeGetCurrentThread(), 0);
    result = v9;
    if ( (_DWORD)v9 == -1073741790 )
    {
      *a4 = 0;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004fac0  mov     rax, rsp
0x14004fac3  push    rbx
0x14004fac4  push    rbp
0x14004fac5  push    rsi
0x14004fac6  push    rdi
0x14004fac7  push    r14
0x14004fac9  sub     rsp, 90h
0x14004fad0  movzx   ebx, [rsp+0B8h+arg_20]
0x14004fad8  xor     ebp, ebp
0x14004fada  mov     [rax-58h], ebp
0x14004fadd  xorps   xmm0, xmm0
0x14004fae0  mov     [rax-50h], rbp
0x14004fae4  mov     r14, r9
0x14004fae7  mov     rdi, r8
0x14004faea  mov     rsi, rdx
0x14004faed  movups  xmmword ptr [rax-48h], xmm0
0x14004faf1  movups  xmmword ptr [rax-38h], xmm0
0x14004faf5  test    bl, bl
0x14004faf7  jz      loc_14004FBA3
0x14004fafd  lea     rcx, [rsp+0B8h+SubjectContext]; SubjectContext
0x14004fb02  call    cs:__imp_SeCaptureSubjectContext
0x14004fb09  nop     dword ptr [rax+rax+00h]
0x14004fb0e  lea     rax, [rsp+0B8h+var_58]
0x14004fb13  mov     r9d, 2000000h; int
0x14004fb19  mov     [rsp+0B8h+var_68], rax; __int64
0x14004fb1e  lea     rdx, [rsp+0B8h+SubjectContext]; int
0x14004fb23  mov     [rsp+0B8h+var_70], rbp; void *
0x14004fb28  lea     rax, [rsp+0B8h+Privileges]
0x14004fb2d  mov     [rsp+0B8h+var_78], r14; __int64
0x14004fb32  xor     r8d, r8d; int
0x14004fb35  mov     [rsp+0B8h+var_80], 1; char
0x14004fb3a  mov     rcx, rsi; int
0x14004fb3d  mov     [rsp+0B8h+var_88], rdi; __int64
0x14004fb42  mov     [rsp+0B8h+var_90], rax; __int64
0x14004fb47  mov     [rsp+0B8h+var_98], ebp; int
0x14004fb4b  call    SrvLibSeAccessCheck
0x14004fb50  mov     rcx, [rsp+0B8h+Privileges]; Privileges
0x14004fb55  test    rcx, rcx
0x14004fb58  jnz     short loc_14004FBB5
0x14004fb5a  lea     rcx, [rsp+0B8h+SubjectContext]; SubjectContext
0x14004fb5f  call    cs:__imp_SeReleaseSubjectContext
0x14004fb66  nop     dword ptr [rax+rax+00h]
0x14004fb6b  test    bl, bl
0x14004fb6d  jz      short loc_14004FBC3
0x14004fb6f  mov     eax, dword ptr [rsp+0B8h+var_58]
0x14004fb73  cmp     eax, 0C0000022h
0x14004fb78  jz      short loc_14004FBDC
0x14004fb7a  add     rsp, 90h
0x14004fb81  pop     r14
0x14004fb83  pop     rdi
0x14004fb84  pop     rsi
0x14004fb85  pop     rbp
0x14004fb86  pop     rbx
0x14004fb87  retn
0x14004fb89  call    cs:__imp_ImpersonateSecurityContext
0x14004fb90  nop     dword ptr [rax+rax+00h]
0x14004fb95  mov     dword ptr [rsp+0B8h+var_58], eax
0x14004fb99  test    eax, eax
0x14004fb9b  jns     loc_14004FAFD
0x14004fba1  jmp     short loc_14004FB7A
0x14004fba3  cmp     [rcx], rbp
0x14004fba6  jnz     short loc_14004FB89
0x14004fba8  cmp     [rcx+8], rbp
0x14004fbac  jnz     short loc_14004FB89
0x14004fbae  mov     eax, 0C0000022h
0x14004fbb3  jmp     short loc_14004FB7A
0x14004fbb5  call    cs:__imp_SeFreePrivileges
0x14004fbbc  nop     dword ptr [rax+rax+00h]
0x14004fbc1  jmp     short loc_14004FB5A
0x14004fbc3  mov     rcx, gs:188h; Thread
0x14004fbcc  xor     edx, edx; Token
0x14004fbce  call    cs:__imp_PsAssignImpersonationToken
0x14004fbd5  nop     dword ptr [rax+rax+00h]
0x14004fbda  jmp     short loc_14004FB6F
0x14004fbdc  mov     [r14], ebp
0x14004fbdf  mov     eax, ebp
0x14004fbe1  jmp     short loc_14004FB7A
```
