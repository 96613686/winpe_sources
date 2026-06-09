# VmsOmGetCallerSid

- ea: `0x1401130cc`
- end: `0x140113300`
- name: `VmsOmGetCallerSid`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140113630`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x140046f1c`
- `0x14008497c`
- `0x1401130cc`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x140113163`
- `ntoskrnl!SeQueryInformationToken` at `0x140113163`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140113272`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140113272`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113104`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113104`
- `ntoskrnl!RtlCopySid` at `0x140113232`
- `ntoskrnl!RtlCopySid` at `0x140113232`
- `ntoskrnl!RtlLengthSid` at `0x1401131bb`
- `ntoskrnl!RtlLengthSid` at `0x14011321e`
- `ntoskrnl!RtlLengthSid` at `0x1401131bb`
- `ntoskrnl!RtlLengthSid` at `0x14011321e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113289`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401132a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113289`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401132a6`
- `ntoskrnl!ExAllocatePool2` at `0x1401131d6`
- `ntoskrnl!ExAllocatePool2` at `0x1401131d6`

## string_xrefs

- `0x140113135`: `token != NULL`
- `0x140113182`: `userToken`

## pseudocode

```c
__int64 __fastcall VmsOmGetCallerSid(_QWORD *a1)
{
  char v2; // r14
  void *Pool2; // rdi
  int v4; // edx
  void *PrimaryToken; // rbx
  int v6; // edx
  NTSTATUS v7; // ebx
  PSID *v8; // rcx
  ULONG v9; // eax
  char v10; // si
  int v11; // edx
  int v12; // edx
  PSID v13; // rbx
  ULONG v14; // eax
  NTSTATUS v15; // eax
  int v16; // edx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+40h] [rbp-20h] BYREF
  PVOID TokenInformation; // [rsp+98h] [rbp+38h] BYREF

  TokenInformation = 0;
  v2 = 0;
  Pool2 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  if ( !PrimaryToken )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v4,
      19,
      10,
      (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
      (__int64)"token != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v7 = SeQueryInformationToken(PrimaryToken, TokenUser, &TokenInformation);
  if ( v7 >= 0 )
  {
    v8 = (PSID *)TokenInformation;
    if ( !TokenInformation )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v6,
        19,
        11,
        (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids,
        (__int64)"userToken");
      v8 = (PSID *)TokenInformation;
      if ( !TokenInformation )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v8 = (PSID *)TokenInformation;
      }
    }
    v9 = RtlLengthSid(*v8);
    v10 = v9;
    Pool2 = (void *)ExAllocatePool2(64, v9, 1649374038);
    if ( !Pool2 )
    {
      v7 = -1073741670;
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_ld(VmsIfrLog, v11, 20, 12, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, v10, 154);
      goto LABEL_15;
    }
    v13 = *(PSID *)TokenInformation;
    v14 = RtlLengthSid(*(PSID *)TokenInformation);
    v15 = RtlCopySid(v14, Pool2, v13);
    v7 = v15;
    if ( v15 < 0 )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_ld(VmsIfrLog, v16, 20, 13, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, v10, v15);
      goto LABEL_15;
    }
    v2 = 1;
  }
  SeReleaseSubjectContext(&SubjectContext);
LABEL_15:
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v7 < 0 && Pool2 )
    ExFreePoolWithTag(Pool2, 0x624F7356u);
  if ( v2 )
    *a1 = Pool2;
  if ( v7 < 0 )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v12, 20, 14, (__int64)WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids, (char)a1, v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1401130cc  mov     [rsp-28h+arg_0], rbx
0x1401130d1  mov     [rsp-28h+arg_10], rsi
0x1401130d6  push    rbp
0x1401130d7  push    rdi
0x1401130d8  push    r12
0x1401130da  push    r14
0x1401130dc  push    r15
0x1401130de  mov     rbp, rsp
0x1401130e1  sub     rsp, 60h
0x1401130e5  xorps   xmm0, xmm0
0x1401130e8  mov     [rbp+TokenInformation], 0
0x1401130f0  mov     r15, rcx
0x1401130f3  xor     r14b, r14b
0x1401130f6  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1401130fa  xor     edi, edi
0x1401130fc  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140113100  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140113104  call    cs:__imp_SeCaptureSubjectContext
0x14011310b  nop     dword ptr [rax+rax+00h]
0x140113110  mov     rax, [rbp+SubjectContext.ClientToken]
0x140113114  lea     r12, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011311b  mov     rbx, [rbp+SubjectContext.PrimaryToken]
0x14011311f  lea     esi, [rdi+13h]
0x140113122  test    rax, rax
0x140113125  cmovnz  rbx, rax
0x140113129  test    rbx, rbx
0x14011312c  jnz     short loc_140113157
0x14011312e  mov     rcx, cs:VmsIfrLog
0x140113135  lea     rax, aTokenNull; "token != NULL"
0x14011313c  mov     [rsp+60h+var_38], rax
0x140113141  lea     r9d, [rdi+0Ah]
0x140113145  mov     r8d, esi
0x140113148  mov     [rsp+60h+var_40], r12
0x14011314d  call    WPP_RECORDER_SF_s
0x140113152  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "token != ((void *)0)")
0x140113157  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14011315b  mov     edx, 1; TokenInformationClass
0x140113160  mov     rcx, rbx; Token
0x140113163  call    cs:__imp_SeQueryInformationToken
0x14011316a  nop     dword ptr [rax+rax+00h]
0x14011316f  mov     ebx, eax
0x140113171  test    eax, eax
0x140113173  js      loc_14011326E
0x140113179  mov     rcx, [rbp+TokenInformation]
0x14011317d  test    rcx, rcx
0x140113180  jnz     short loc_1401131B8
0x140113182  lea     rax, aUsertoken; "userToken"
0x140113189  mov     r8d, esi
0x14011318c  lea     r9d, [rcx+0Bh]
0x140113190  mov     [rsp+60h+var_38], rax
0x140113195  mov     rcx, cs:VmsIfrLog
0x14011319c  mov     [rsp+60h+var_40], r12
0x1401131a1  call    WPP_RECORDER_SF_s
0x1401131a6  mov     rcx, [rbp+TokenInformation]
0x1401131aa  test    rcx, rcx
0x1401131ad  jnz     short loc_1401131B8
0x1401131af  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "userToken")
0x1401131b4  mov     rcx, [rbp+TokenInformation]
0x1401131b8  mov     rcx, [rcx]; Sid
0x1401131bb  call    cs:__imp_RtlLengthSid
0x1401131c2  nop     dword ptr [rax+rax+00h]
0x1401131c7  mov     edx, eax
0x1401131c9  mov     ecx, 40h ; '@'
0x1401131ce  mov     r8d, 624F7356h
0x1401131d4  mov     esi, eax
0x1401131d6  call    cs:__imp_ExAllocatePool2
0x1401131dd  nop     dword ptr [rax+rax+00h]
0x1401131e2  mov     rdi, rax
0x1401131e5  test    rax, rax
0x1401131e8  jnz     short loc_140113214
0x1401131ea  mov     ebx, 0C000009Ah
0x1401131ef  mov     rcx, cs:VmsIfrLog
0x1401131f6  lea     r9d, [rax+0Ch]
0x1401131fa  mov     [rsp+60h+var_30], ebx
0x1401131fe  lea     r8d, [rax+14h]
0x140113202  mov     dword ptr [rsp+60h+var_38], esi
0x140113206  mov     dl, 2
0x140113208  mov     [rsp+60h+var_40], r12
0x14011320d  call    WPP_RECORDER_SF_ld
0x140113212  jmp     short loc_14011327E
0x140113214  mov     rax, [rbp+TokenInformation]
0x140113218  mov     rbx, [rax]
0x14011321b  mov     rcx, rbx; Sid
0x14011321e  call    cs:__imp_RtlLengthSid
0x140113225  nop     dword ptr [rax+rax+00h]
0x14011322a  mov     r8, rbx; SourceSid
0x14011322d  mov     rdx, rdi; DestinationSid
0x140113230  mov     ecx, eax; DestinationSidLength
0x140113232  call    cs:__imp_RtlCopySid
0x140113239  nop     dword ptr [rax+rax+00h]
0x14011323e  mov     ebx, eax
0x140113240  test    eax, eax
0x140113242  jns     short loc_14011326B
0x140113244  mov     rcx, cs:VmsIfrLog
0x14011324b  mov     r9d, 0Dh
0x140113251  mov     [rsp+60h+var_30], eax
0x140113255  mov     dl, 2
0x140113257  mov     dword ptr [rsp+60h+var_38], esi
0x14011325b  mov     [rsp+60h+var_40], r12
0x140113260  lea     r8d, [r9+7]
0x140113264  call    WPP_RECORDER_SF_ld
0x140113269  jmp     short loc_14011327E
0x14011326b  mov     r14b, 1
0x14011326e  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140113272  call    cs:__imp_SeReleaseSubjectContext
0x140113279  nop     dword ptr [rax+rax+00h]
0x14011327e  mov     rcx, [rbp+TokenInformation]; P
0x140113282  test    rcx, rcx
0x140113285  jz      short loc_140113295
0x140113287  xor     edx, edx; Tag
0x140113289  call    cs:__imp_ExFreePoolWithTag
0x140113290  nop     dword ptr [rax+rax+00h]
0x140113295  test    ebx, ebx
0x140113297  jns     short loc_1401132B2
0x140113299  test    rdi, rdi
0x14011329c  jz      short loc_1401132B2
0x14011329e  mov     edx, 624F7356h; Tag
0x1401132a3  mov     rcx, rdi; P
0x1401132a6  call    cs:__imp_ExFreePoolWithTag
0x1401132ad  nop     dword ptr [rax+rax+00h]
0x1401132b2  test    r14b, r14b
0x1401132b5  jz      short loc_1401132BA
0x1401132b7  mov     [r15], rdi
0x1401132ba  test    ebx, ebx
0x1401132bc  jns     short loc_1401132E4
0x1401132be  mov     rcx, cs:VmsIfrLog
0x1401132c5  mov     r9d, 0Eh
0x1401132cb  mov     [rsp+60h+var_30], ebx
0x1401132cf  mov     dl, 2
0x1401132d1  mov     [rsp+60h+var_38], r15
0x1401132d6  mov     [rsp+60h+var_40], r12
0x1401132db  lea     r8d, [r9+6]
0x1401132df  call    WPP_RECORDER_SF_id
0x1401132e4  lea     r11, [rsp+60h+var_s0]
0x1401132e9  mov     eax, ebx
0x1401132eb  mov     rbx, [r11+30h]
0x1401132ef  mov     rsi, [r11+40h]
0x1401132f3  mov     rsp, r11
0x1401132f6  pop     r15
0x1401132f8  pop     r14
0x1401132fa  pop     r12
0x1401132fc  pop     rdi
0x1401132fd  pop     rbp
0x1401132fe  retn
```
