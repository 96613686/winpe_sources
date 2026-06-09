# CitpContextUserLogon(_CIT_IMPACT_CONTEXT *,_LUID const *)

- ea: `0x14015dbd4`
- end: `0x14015ddfd`
- name: `?CitpContextUserLogon@@YAJPEAU_CIT_IMPACT_CONTEXT@@PEBU_LUID@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct _CIT_IMPACT_CONTEXT *, const struct _LUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cefec`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x14015dbd4`
- `0x14015e094`
- `0x14018db0c`
- `0x1401afed4`
- `0x140238160`
- `0x140238800`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14015dc16`
- `ntoskrnl!PsGetCurrentProcess` at `0x14015dc16`
- `ntoskrnl!ZwClose` at `0x14015dd51`
- `ntoskrnl!ZwClose` at `0x14015dd51`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14015dcab`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14015dcab`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14015dc25`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14015dc25`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14015dc44`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14015dc44`
- `ntoskrnl!RtlLengthSid` at `0x14015dd00`
- `ntoskrnl!RtlLengthSid` at `0x14015dd00`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14015ddab`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14015ddab`
- `ntoskrnl!ZwQueryInformationToken` at `0x14015dce3`
- `ntoskrnl!ZwQueryInformationToken` at `0x14015dce3`
- `WIN32K!W32GetUserSessionState` at `0x14015dc71`
- `WIN32K!W32GetUserSessionState` at `0x14015dc71`

## pseudocode

```c
__int64 __fastcall CitpContextUserLogon(struct _CIT_IMPACT_CONTEXT *a1, const struct _LUID *a2)
{
  struct _KPROCESS *CurrentProcess; // rax
  PACCESS_TOKEN v5; // rax
  const char *v6; // rdx
  void *v7; // rdi
  NTSTATUS v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 UserSessionState; // rax
  __int64 v12; // r11
  PSID v13; // r14
  ULONG v14; // r15d
  void *v15; // rax
  void *v16; // rbx
  __int64 v17; // rax
  unsigned int v19; // r8d
  int v20; // ecx
  ULONG ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  struct _LUID AuthenticationId; // [rsp+38h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-49h] BYREF
  struct _CIT_IMPACT_CONTEXT *v24; // [rsp+48h] [rbp-41h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-39h] BYREF

  TokenHandle = 0;
  AuthenticationId = 0;
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  v5 = PsReferencePrimaryToken(CurrentProcess);
  v7 = v5;
  if ( !v5 )
  {
    v10 = -1073741700;
    v19 = 655;
LABEL_16:
    v20 = v10;
LABEL_17:
    CitpLogFailureWorker(v20, v6, v19);
    goto LABEL_10;
  }
  v8 = SeQueryAuthenticationIdToken(v5, &AuthenticationId);
  v10 = v8;
  if ( v8 < 0 )
  {
    v19 = 662;
    goto LABEL_20;
  }
  if ( AuthenticationId.LowPart == a2->LowPart && AuthenticationId.HighPart == a2->HighPart )
  {
    UserSessionState = W32GetUserSessionState(v9);
    CitpParametersCompute((struct _CIT_PARAMETERS *)(*(_QWORD *)(UserSessionState + 18992) + 4LL));
    if ( *(_BYTE *)(v12 + 24) )
    {
      v8 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &TokenHandle);
      v10 = v8;
      if ( v8 < 0 )
      {
        v19 = 693;
      }
      else
      {
        ReturnLength = 0;
        v8 = ZwQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength);
        v10 = v8;
        if ( v8 >= 0 )
        {
          v13 = TokenInformation[0];
          v14 = RtlLengthSid(TokenInformation[0]);
          v15 = Win32AllocPoolZInitImpl(0x100u, v14, 0x49637355u);
          v16 = v15;
          if ( v15 )
          {
            memmove(v15, v13, v14);
            v17 = (__int64)*a2;
            *((_QWORD *)a1 + 12) = v16;
            v10 = 0;
            *((_QWORD *)a1 + 13) = v17;
            goto LABEL_10;
          }
          v10 = -1073741670;
          v19 = 723;
          goto LABEL_16;
        }
        v19 = 709;
      }
LABEL_20:
      v20 = v8;
      goto LABEL_17;
    }
    CitpCleanupGlobalImpactContext(&v24);
    v10 = -1073741637;
  }
  else
  {
    v10 = -1073741587;
  }
LABEL_10:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( v7 )
    PsDereferencePrimaryToken(v7);
  GreDeleteFastMutex(0);
  return v10;
}

```

## disassembly

```asm
0x14015dbd4  mov     [rsp-8+arg_8], rbx
0x14015dbd9  mov     [rsp-8+arg_10], rsi
0x14015dbde  push    rbp
0x14015dbdf  push    rdi
0x14015dbe0  push    r13
0x14015dbe2  push    r14
0x14015dbe4  push    r15
0x14015dbe6  lea     rbp, [rsp-37h]
0x14015dbeb  sub     rsp, 0C0h
0x14015dbf2  mov     rax, cs:__security_cookie
0x14015dbf9  xor     rax, rsp
0x14015dbfc  mov     [rbp+57h+var_30], rax
0x14015dc00  mov     rsi, rdx
0x14015dc03  mov     [rbp+57h+TokenHandle], 0
0x14015dc0b  mov     r13, rcx
0x14015dc0e  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 0
0x14015dc16  call    cs:__imp_PsGetCurrentProcess
0x14015dc1d  nop     dword ptr [rax+rax+00h]
0x14015dc22  mov     rcx, rax; Process
0x14015dc25  call    cs:__imp_PsReferencePrimaryToken
0x14015dc2c  nop     dword ptr [rax+rax+00h]
0x14015dc31  mov     rdi, rax
0x14015dc34  test    rax, rax
0x14015dc37  jz      loc_14015DD94
0x14015dc3d  lea     rdx, [rbp+57h+AuthenticationId]; AuthenticationId
0x14015dc41  mov     rcx, rax; Token
0x14015dc44  call    cs:__imp_SeQueryAuthenticationIdToken
0x14015dc4b  nop     dword ptr [rax+rax+00h]
0x14015dc50  mov     ebx, eax
0x14015dc52  test    eax, eax
0x14015dc54  js      loc_14015DDB9
0x14015dc5a  mov     eax, [rsi]
0x14015dc5c  cmp     [rbp+57h+AuthenticationId.LowPart], eax
0x14015dc5f  jnz     loc_14015DDF3
0x14015dc65  mov     eax, [rsi+4]
0x14015dc68  cmp     [rbp+57h+AuthenticationId.HighPart], eax
0x14015dc6b  jnz     loc_14015DDF3
0x14015dc71  call    cs:__imp_W32GetUserSessionState
0x14015dc78  nop     dword ptr [rax+rax+00h]
0x14015dc7d  mov     r11, [rax+4A30h]
0x14015dc84  lea     rcx, [r11+4]; struct _CIT_PARAMETERS *
0x14015dc88  call    ?CitpParametersCompute@@YAXPEAU_CIT_PARAMETERS@@@Z; CitpParametersCompute(_CIT_PARAMETERS *)
0x14015dc8d  cmp     byte ptr [r11+18h], 0
0x14015dc92  jz      loc_14015DDCB
0x14015dc98  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14015dc9c  mov     edx, 8; DesiredAccess
0x14015dca1  mov     r8d, 200h; HandleAttributes
0x14015dca7  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14015dcab  call    cs:__imp_ZwOpenProcessTokenEx
0x14015dcb2  nop     dword ptr [rax+rax+00h]
0x14015dcb7  mov     ebx, eax
0x14015dcb9  test    eax, eax
0x14015dcbb  js      loc_14015DDDE
0x14015dcc1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14015dcc5  lea     rax, [rbp+57h+var_B0]
0x14015dcc9  mov     r9d, 58h ; 'X'; TokenInformationLength
0x14015dccf  mov     [rbp+57h+var_B0], 0
0x14015dcd6  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14015dcda  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x14015dcdf  lea     edx, [r9-57h]; TokenInformationClass
0x14015dce3  call    cs:__imp_ZwQueryInformationToken
0x14015dcea  nop     dword ptr [rax+rax+00h]
0x14015dcef  mov     ebx, eax
0x14015dcf1  test    eax, eax
0x14015dcf3  js      loc_14015DDC1
0x14015dcf9  mov     r14, [rbp+57h+TokenInformation]
0x14015dcfd  mov     rcx, r14; Sid
0x14015dd00  call    cs:__imp_RtlLengthSid
0x14015dd07  nop     dword ptr [rax+rax+00h]
0x14015dd0c  mov     edx, eax; unsigned __int64
0x14015dd0e  mov     r8d, 49637355h; unsigned int
0x14015dd14  mov     ecx, 100h; unsigned __int64
0x14015dd19  mov     r15d, eax
0x14015dd1c  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14015dd21  mov     rbx, rax
0x14015dd24  test    rax, rax
0x14015dd27  jz      loc_14015DDE6
0x14015dd2d  mov     r8d, r15d; Size
0x14015dd30  mov     rdx, r14; Src
0x14015dd33  mov     rcx, rax; void *
0x14015dd36  call    memmove
0x14015dd3b  mov     rax, [rsi]
0x14015dd3e  mov     [r13+60h], rbx
0x14015dd42  xor     ebx, ebx
0x14015dd44  mov     [r13+68h], rax
0x14015dd48  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x14015dd4c  test    rcx, rcx
0x14015dd4f  jz      short loc_14015DD5D
0x14015dd51  call    cs:__imp_ZwClose
0x14015dd58  nop     dword ptr [rax+rax+00h]
0x14015dd5d  test    rdi, rdi
0x14015dd60  jnz     short loc_14015DDA8
0x14015dd62  xor     ecx, ecx; Buffer
0x14015dd64  call    GreDeleteFastMutex
0x14015dd69  mov     eax, ebx
0x14015dd6b  mov     rcx, [rbp+57h+var_30]
0x14015dd6f  xor     rcx, rsp; StackCookie
0x14015dd72  call    __security_check_cookie
0x14015dd77  lea     r11, [rsp+0E0h+var_20]
0x14015dd7f  mov     rbx, [r11+38h]
0x14015dd83  mov     rsi, [r11+40h]
0x14015dd87  mov     rsp, r11
0x14015dd8a  pop     r15
0x14015dd8c  pop     r14
0x14015dd8e  pop     r13
0x14015dd90  pop     rdi
0x14015dd91  pop     rbp
0x14015dd92  retn
0x14015dd94  mov     ebx, 0C000007Ch
0x14015dd99  mov     r8d, 28Fh; unsigned int
0x14015dd9f  mov     ecx, ebx; int
0x14015dda1  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x14015dda6  jmp     short loc_14015DD48
0x14015dda8  mov     rcx, rdi; PrimaryToken
0x14015ddab  call    cs:__imp_PsDereferencePrimaryToken
0x14015ddb2  nop     dword ptr [rax+rax+00h]
0x14015ddb7  jmp     short loc_14015DD62
0x14015ddb9  mov     r8d, 296h
0x14015ddbf  jmp     short loc_14015DDC7
0x14015ddc1  mov     r8d, 2C5h
0x14015ddc7  mov     ecx, eax
0x14015ddc9  jmp     short loc_14015DDA1
0x14015ddcb  lea     rcx, [rbp+57h+var_98]; struct _CIT_IMPACT_CONTEXT **
0x14015ddcf  call    ?CitpCleanupGlobalImpactContext@@YAXPEAPEAU_CIT_IMPACT_CONTEXT@@@Z; CitpCleanupGlobalImpactContext(_CIT_IMPACT_CONTEXT * *)
0x14015ddd4  mov     ebx, 0C00000BBh
0x14015ddd9  jmp     loc_14015DD48
0x14015ddde  mov     r8d, 2B5h
0x14015dde4  jmp     short loc_14015DDC7
0x14015dde6  mov     ebx, 0C000009Ah
0x14015ddeb  mov     r8d, 2D3h
0x14015ddf1  jmp     short loc_14015DD9F
0x14015ddf3  mov     ebx, 0C00000EDh
0x14015ddf8  jmp     loc_14015DD48
```
