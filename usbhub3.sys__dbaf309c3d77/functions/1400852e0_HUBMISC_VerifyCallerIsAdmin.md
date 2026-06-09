# HUBMISC_VerifyCallerIsAdmin

- ea: `0x1400852e0`
- end: `0x1400853a9`
- name: `HUBMISC_VerifyCallerIsAdmin`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14007ab24`
- `0x14007d6cc`
- `0x14007d848`

## callees

- `0x1400067ac`
- `0x1400852e0`

## import_xrefs

- `ntoskrnl!SeTokenIsAdmin` at `0x140085362`
- `ntoskrnl!SeTokenIsAdmin` at `0x140085362`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140085386`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140085386`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140085375`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140085375`
- `ntoskrnl!SeLockSubjectContext` at `0x14008530f`
- `ntoskrnl!SeLockSubjectContext` at `0x14008530f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400852fe`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400852fe`

## pseudocode

```c
__int64 __fastcall HUBMISC_VerifyCallerIsAdmin(int a1)
{
  int v2; // edx
  void *PrimaryToken; // rbx
  BOOLEAN IsAdmin; // bl
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+30h] [rbp-28h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  if ( !PrimaryToken && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 2;
    WPP_RECORDER_SF_(a1, v2, 3, 99, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
  }
  IsAdmin = SeTokenIsAdmin(PrimaryToken);
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  return IsAdmin == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x1400852e0  mov     rax, rsp
0x1400852e3  mov     [rax+8], rbx
0x1400852e7  push    rdi
0x1400852e8  sub     rsp, 50h
0x1400852ec  xorps   xmm0, xmm0
0x1400852ef  mov     rdi, rcx
0x1400852f2  lea     rcx, [rax-28h]; SubjectContext
0x1400852f6  movups  xmmword ptr [rax-28h], xmm0
0x1400852fa  movups  xmmword ptr [rax-18h], xmm0
0x1400852fe  call    cs:__imp_SeCaptureSubjectContext
0x140085305  nop     dword ptr [rax+rax+00h]
0x14008530a  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x14008530f  call    cs:__imp_SeLockSubjectContext
0x140085316  nop     dword ptr [rax+rax+00h]
0x14008531b  mov     rax, [rsp+58h+SubjectContext.ClientToken]
0x140085320  mov     rbx, [rsp+58h+SubjectContext.PrimaryToken]
0x140085325  test    rax, rax
0x140085328  cmovnz  rbx, rax
0x14008532c  test    rbx, rbx
0x14008532f  jnz     short loc_14008535F
0x140085331  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140085338  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008533f  jz      short loc_14008535F
0x140085341  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140085348  mov     dl, 2
0x14008534a  lea     r9d, [rbx+63h]
0x14008534e  mov     [rsp+58h+var_38], rax
0x140085353  lea     r8d, [rbx+3]
0x140085357  mov     rcx, rdi
0x14008535a  call    WPP_RECORDER_SF_
0x14008535f  mov     rcx, rbx; Token
0x140085362  call    cs:__imp_SeTokenIsAdmin
0x140085369  nop     dword ptr [rax+rax+00h]
0x14008536e  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x140085373  mov     bl, al
0x140085375  call    cs:__imp_SeUnlockSubjectContext
0x14008537c  nop     dword ptr [rax+rax+00h]
0x140085381  lea     rcx, [rsp+58h+SubjectContext]; SubjectContext
0x140085386  call    cs:__imp_SeReleaseSubjectContext
0x14008538d  nop     dword ptr [rax+rax+00h]
0x140085392  neg     bl
0x140085394  mov     rbx, [rsp+58h+arg_0]
0x140085399  sbb     eax, eax
0x14008539b  not     eax
0x14008539d  and     eax, 0C0000001h
0x1400853a2  add     rsp, 50h
0x1400853a6  pop     rdi
0x1400853a7  retn
```
