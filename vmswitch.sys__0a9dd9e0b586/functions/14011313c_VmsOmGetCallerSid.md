# VmsOmGetCallerSid

- ea: `0x14011313c`
- end: `0x140113370`
- name: `VmsOmGetCallerSid`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401136a0`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x140046f1c`
- `0x14008497c`
- `0x14011313c`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1401131d3`
- `ntoskrnl!SeQueryInformationToken` at `0x1401131d3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401132e2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401132e2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113174`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140113174`
- `ntoskrnl!RtlCopySid` at `0x1401132a2`
- `ntoskrnl!RtlCopySid` at `0x1401132a2`
- `ntoskrnl!RtlLengthSid` at `0x14011322b`
- `ntoskrnl!RtlLengthSid` at `0x14011328e`
- `ntoskrnl!RtlLengthSid` at `0x14011322b`
- `ntoskrnl!RtlLengthSid` at `0x14011328e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401132f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113316`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401132f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140113316`
- `ntoskrnl!ExAllocatePool2` at `0x140113246`
- `ntoskrnl!ExAllocatePool2` at `0x140113246`

## string_xrefs

- `0x1401131a5`: `token != NULL`
- `0x1401131f2`: `userToken`

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
0x14011313c  mov     [rsp-28h+arg_0], rbx
0x140113141  mov     [rsp-28h+arg_10], rsi
0x140113146  push    rbp
0x140113147  push    rdi
0x140113148  push    r12
0x14011314a  push    r14
0x14011314c  push    r15
0x14011314e  mov     rbp, rsp
0x140113151  sub     rsp, 60h
0x140113155  xorps   xmm0, xmm0
0x140113158  mov     [rbp+TokenInformation], 0
0x140113160  mov     r15, rcx
0x140113163  xor     r14b, r14b
0x140113166  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14011316a  xor     edi, edi
0x14011316c  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140113170  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140113174  call    cs:__imp_SeCaptureSubjectContext
0x14011317b  nop     dword ptr [rax+rax+00h]
0x140113180  mov     rax, [rbp+SubjectContext.ClientToken]
0x140113184  lea     r12, WPP_8ba27d42bb8b3f236fd12e8dd774299f_Traceguids
0x14011318b  mov     rbx, [rbp+SubjectContext.PrimaryToken]
0x14011318f  lea     esi, [rdi+13h]
0x140113192  test    rax, rax
0x140113195  cmovnz  rbx, rax
0x140113199  test    rbx, rbx
0x14011319c  jnz     short loc_1401131C7
0x14011319e  mov     rcx, cs:VmsIfrLog
0x1401131a5  lea     rax, aTokenNull; "token != NULL"
0x1401131ac  mov     [rsp+60h+var_38], rax
0x1401131b1  lea     r9d, [rdi+0Ah]
0x1401131b5  mov     r8d, esi
0x1401131b8  mov     [rsp+60h+var_40], r12
0x1401131bd  call    WPP_RECORDER_SF_s
0x1401131c2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "token != ((void *)0)")
0x1401131c7  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1401131cb  mov     edx, 1; TokenInformationClass
0x1401131d0  mov     rcx, rbx; Token
0x1401131d3  call    cs:__imp_SeQueryInformationToken
0x1401131da  nop     dword ptr [rax+rax+00h]
0x1401131df  mov     ebx, eax
0x1401131e1  test    eax, eax
0x1401131e3  js      loc_1401132DE
0x1401131e9  mov     rcx, [rbp+TokenInformation]
0x1401131ed  test    rcx, rcx
0x1401131f0  jnz     short loc_140113228
0x1401131f2  lea     rax, aUsertoken; "userToken"
0x1401131f9  mov     r8d, esi
0x1401131fc  lea     r9d, [rcx+0Bh]
0x140113200  mov     [rsp+60h+var_38], rax
0x140113205  mov     rcx, cs:VmsIfrLog
0x14011320c  mov     [rsp+60h+var_40], r12
0x140113211  call    WPP_RECORDER_SF_s
0x140113216  mov     rcx, [rbp+TokenInformation]
0x14011321a  test    rcx, rcx
0x14011321d  jnz     short loc_140113228
0x14011321f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "userToken")
0x140113224  mov     rcx, [rbp+TokenInformation]
0x140113228  mov     rcx, [rcx]; Sid
0x14011322b  call    cs:__imp_RtlLengthSid
0x140113232  nop     dword ptr [rax+rax+00h]
0x140113237  mov     edx, eax
0x140113239  mov     ecx, 40h ; '@'
0x14011323e  mov     r8d, 624F7356h
0x140113244  mov     esi, eax
0x140113246  call    cs:__imp_ExAllocatePool2
0x14011324d  nop     dword ptr [rax+rax+00h]
0x140113252  mov     rdi, rax
0x140113255  test    rax, rax
0x140113258  jnz     short loc_140113284
0x14011325a  mov     ebx, 0C000009Ah
0x14011325f  mov     rcx, cs:VmsIfrLog
0x140113266  lea     r9d, [rax+0Ch]
0x14011326a  mov     [rsp+60h+var_30], ebx
0x14011326e  lea     r8d, [rax+14h]
0x140113272  mov     dword ptr [rsp+60h+var_38], esi
0x140113276  mov     dl, 2
0x140113278  mov     [rsp+60h+var_40], r12
0x14011327d  call    WPP_RECORDER_SF_ld
0x140113282  jmp     short loc_1401132EE
0x140113284  mov     rax, [rbp+TokenInformation]
0x140113288  mov     rbx, [rax]
0x14011328b  mov     rcx, rbx; Sid
0x14011328e  call    cs:__imp_RtlLengthSid
0x140113295  nop     dword ptr [rax+rax+00h]
0x14011329a  mov     r8, rbx; SourceSid
0x14011329d  mov     rdx, rdi; DestinationSid
0x1401132a0  mov     ecx, eax; DestinationSidLength
0x1401132a2  call    cs:__imp_RtlCopySid
0x1401132a9  nop     dword ptr [rax+rax+00h]
0x1401132ae  mov     ebx, eax
0x1401132b0  test    eax, eax
0x1401132b2  jns     short loc_1401132DB
0x1401132b4  mov     rcx, cs:VmsIfrLog
0x1401132bb  mov     r9d, 0Dh
0x1401132c1  mov     [rsp+60h+var_30], eax
0x1401132c5  mov     dl, 2
0x1401132c7  mov     dword ptr [rsp+60h+var_38], esi
0x1401132cb  mov     [rsp+60h+var_40], r12
0x1401132d0  lea     r8d, [r9+7]
0x1401132d4  call    WPP_RECORDER_SF_ld
0x1401132d9  jmp     short loc_1401132EE
0x1401132db  mov     r14b, 1
0x1401132de  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1401132e2  call    cs:__imp_SeReleaseSubjectContext
0x1401132e9  nop     dword ptr [rax+rax+00h]
0x1401132ee  mov     rcx, [rbp+TokenInformation]; P
0x1401132f2  test    rcx, rcx
0x1401132f5  jz      short loc_140113305
0x1401132f7  xor     edx, edx; Tag
0x1401132f9  call    cs:__imp_ExFreePoolWithTag
0x140113300  nop     dword ptr [rax+rax+00h]
0x140113305  test    ebx, ebx
0x140113307  jns     short loc_140113322
0x140113309  test    rdi, rdi
0x14011330c  jz      short loc_140113322
0x14011330e  mov     edx, 624F7356h; Tag
0x140113313  mov     rcx, rdi; P
0x140113316  call    cs:__imp_ExFreePoolWithTag
0x14011331d  nop     dword ptr [rax+rax+00h]
0x140113322  test    r14b, r14b
0x140113325  jz      short loc_14011332A
0x140113327  mov     [r15], rdi
0x14011332a  test    ebx, ebx
0x14011332c  jns     short loc_140113354
0x14011332e  mov     rcx, cs:VmsIfrLog
0x140113335  mov     r9d, 0Eh
0x14011333b  mov     [rsp+60h+var_30], ebx
0x14011333f  mov     dl, 2
0x140113341  mov     [rsp+60h+var_38], r15
0x140113346  mov     [rsp+60h+var_40], r12
0x14011334b  lea     r8d, [r9+6]
0x14011334f  call    WPP_RECORDER_SF_id
0x140113354  lea     r11, [rsp+60h+var_s0]
0x140113359  mov     eax, ebx
0x14011335b  mov     rbx, [r11+30h]
0x14011335f  mov     rsi, [r11+40h]
0x140113363  mov     rsp, r11
0x140113366  pop     r15
0x140113368  pop     r14
0x14011336a  pop     r12
0x14011336c  pop     rdi
0x14011336d  pop     rbp
0x14011336e  retn
```
