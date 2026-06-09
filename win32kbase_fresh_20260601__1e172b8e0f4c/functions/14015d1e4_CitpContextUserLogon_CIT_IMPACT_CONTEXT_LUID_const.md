# CitpContextUserLogon(_CIT_IMPACT_CONTEXT *,_LUID const *)

- ea: `0x14015d1e4`
- end: `0x14015d40d`
- name: `?CitpContextUserLogon@@YAJPEAU_CIT_IMPACT_CONTEXT@@PEBU_LUID@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct _CIT_IMPACT_CONTEXT *, const struct _LUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005eb4c`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x14015d1e4`
- `0x14015d6a4`
- `0x14018d9dc`
- `0x1401b0434`
- `0x140238b10`
- `0x140239180`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14015d226`
- `ntoskrnl!PsGetCurrentProcess` at `0x14015d226`
- `ntoskrnl!ZwClose` at `0x14015d361`
- `ntoskrnl!ZwClose` at `0x14015d361`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14015d2bb`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14015d2bb`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14015d235`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14015d235`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14015d254`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14015d254`
- `ntoskrnl!RtlLengthSid` at `0x14015d310`
- `ntoskrnl!RtlLengthSid` at `0x14015d310`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14015d3bb`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14015d3bb`
- `ntoskrnl!ZwQueryInformationToken` at `0x14015d2f3`
- `ntoskrnl!ZwQueryInformationToken` at `0x14015d2f3`
- `WIN32K!W32GetUserSessionState` at `0x14015d281`
- `WIN32K!W32GetUserSessionState` at `0x14015d281`

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
  __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 UserSessionState; // rax
  __int64 v13; // r11
  PSID v14; // r14
  ULONG v15; // r15d
  void *v16; // rax
  void *v17; // rbx
  __int64 v18; // rax
  unsigned int v20; // r8d
  int v21; // ecx
  ULONG ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  struct _LUID AuthenticationId; // [rsp+38h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-49h] BYREF
  struct _CIT_IMPACT_CONTEXT *v25; // [rsp+48h] [rbp-41h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-39h] BYREF

  TokenHandle = 0;
  AuthenticationId = 0;
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  v5 = PsReferencePrimaryToken(CurrentProcess);
  v7 = v5;
  if ( !v5 )
  {
    v11 = -1073741700;
    v20 = 655;
LABEL_16:
    v21 = v11;
LABEL_17:
    CitpLogFailureWorker(v21, v6, v20);
    goto LABEL_10;
  }
  v8 = SeQueryAuthenticationIdToken(v5, &AuthenticationId);
  v11 = v8;
  if ( v8 < 0 )
  {
    v20 = 662;
    goto LABEL_20;
  }
  if ( AuthenticationId.LowPart == a2->LowPart && AuthenticationId.HighPart == a2->HighPart )
  {
    UserSessionState = W32GetUserSessionState(v9, v6, v10);
    CitpParametersCompute((struct _CIT_PARAMETERS *)(*(_QWORD *)(UserSessionState + 18992) + 4LL));
    if ( *(_BYTE *)(v13 + 24) )
    {
      v8 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &TokenHandle);
      v11 = v8;
      if ( v8 < 0 )
      {
        v20 = 693;
      }
      else
      {
        ReturnLength = 0;
        v8 = ZwQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength);
        v11 = v8;
        if ( v8 >= 0 )
        {
          v14 = TokenInformation[0];
          v15 = RtlLengthSid(TokenInformation[0]);
          v16 = Win32AllocPoolZInitImpl(0x100u, v15, 0x49637355u);
          v17 = v16;
          if ( v16 )
          {
            memmove(v16, v14, v15);
            v18 = (__int64)*a2;
            *((_QWORD *)a1 + 12) = v17;
            v11 = 0;
            *((_QWORD *)a1 + 13) = v18;
            goto LABEL_10;
          }
          v11 = -1073741670;
          v20 = 723;
          goto LABEL_16;
        }
        v20 = 709;
      }
LABEL_20:
      v21 = v8;
      goto LABEL_17;
    }
    CitpCleanupGlobalImpactContext(&v25);
    v11 = -1073741637;
  }
  else
  {
    v11 = -1073741587;
  }
LABEL_10:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( v7 )
    PsDereferencePrimaryToken(v7);
  GreDeleteFastMutex(0);
  return v11;
}

```

## disassembly

```asm
0x14015d1e4  mov     [rsp-8+arg_8], rbx
0x14015d1e9  mov     [rsp-8+arg_10], rsi
0x14015d1ee  push    rbp
0x14015d1ef  push    rdi
0x14015d1f0  push    r13
0x14015d1f2  push    r14
0x14015d1f4  push    r15
0x14015d1f6  lea     rbp, [rsp-37h]
0x14015d1fb  sub     rsp, 0C0h
0x14015d202  mov     rax, cs:__security_cookie
0x14015d209  xor     rax, rsp
0x14015d20c  mov     [rbp+57h+var_30], rax
0x14015d210  mov     rsi, rdx
0x14015d213  mov     [rbp+57h+TokenHandle], 0
0x14015d21b  mov     r13, rcx
0x14015d21e  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 0
0x14015d226  call    cs:__imp_PsGetCurrentProcess
0x14015d22d  nop     dword ptr [rax+rax+00h]
0x14015d232  mov     rcx, rax; Process
0x14015d235  call    cs:__imp_PsReferencePrimaryToken
0x14015d23c  nop     dword ptr [rax+rax+00h]
0x14015d241  mov     rdi, rax
0x14015d244  test    rax, rax
0x14015d247  jz      loc_14015D3A4
0x14015d24d  lea     rdx, [rbp+57h+AuthenticationId]; AuthenticationId
0x14015d251  mov     rcx, rax; Token
0x14015d254  call    cs:__imp_SeQueryAuthenticationIdToken
0x14015d25b  nop     dword ptr [rax+rax+00h]
0x14015d260  mov     ebx, eax
0x14015d262  test    eax, eax
0x14015d264  js      loc_14015D3C9
0x14015d26a  mov     eax, [rsi]
0x14015d26c  cmp     [rbp+57h+AuthenticationId.LowPart], eax
0x14015d26f  jnz     loc_14015D403
0x14015d275  mov     eax, [rsi+4]
0x14015d278  cmp     [rbp+57h+AuthenticationId.HighPart], eax
0x14015d27b  jnz     loc_14015D403
0x14015d281  call    cs:__imp_W32GetUserSessionState
0x14015d288  nop     dword ptr [rax+rax+00h]
0x14015d28d  mov     r11, [rax+4A30h]
0x14015d294  lea     rcx, [r11+4]; struct _CIT_PARAMETERS *
0x14015d298  call    ?CitpParametersCompute@@YAXPEAU_CIT_PARAMETERS@@@Z; CitpParametersCompute(_CIT_PARAMETERS *)
0x14015d29d  cmp     byte ptr [r11+18h], 0
0x14015d2a2  jz      loc_14015D3DB
0x14015d2a8  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14015d2ac  mov     edx, 8; DesiredAccess
0x14015d2b1  mov     r8d, 200h; HandleAttributes
0x14015d2b7  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14015d2bb  call    cs:__imp_ZwOpenProcessTokenEx
0x14015d2c2  nop     dword ptr [rax+rax+00h]
0x14015d2c7  mov     ebx, eax
0x14015d2c9  test    eax, eax
0x14015d2cb  js      loc_14015D3EE
0x14015d2d1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14015d2d5  lea     rax, [rbp+57h+var_B0]
0x14015d2d9  mov     r9d, 58h ; 'X'; TokenInformationLength
0x14015d2df  mov     [rbp+57h+var_B0], 0
0x14015d2e6  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14015d2ea  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x14015d2ef  lea     edx, [r9-57h]; TokenInformationClass
0x14015d2f3  call    cs:__imp_ZwQueryInformationToken
0x14015d2fa  nop     dword ptr [rax+rax+00h]
0x14015d2ff  mov     ebx, eax
0x14015d301  test    eax, eax
0x14015d303  js      loc_14015D3D1
0x14015d309  mov     r14, [rbp+57h+TokenInformation]
0x14015d30d  mov     rcx, r14; Sid
0x14015d310  call    cs:__imp_RtlLengthSid
0x14015d317  nop     dword ptr [rax+rax+00h]
0x14015d31c  mov     edx, eax; unsigned __int64
0x14015d31e  mov     r8d, 49637355h; unsigned int
0x14015d324  mov     ecx, 100h; unsigned __int64
0x14015d329  mov     r15d, eax
0x14015d32c  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14015d331  mov     rbx, rax
0x14015d334  test    rax, rax
0x14015d337  jz      loc_14015D3F6
0x14015d33d  mov     r8d, r15d; Size
0x14015d340  mov     rdx, r14; Src
0x14015d343  mov     rcx, rax; void *
0x14015d346  call    memmove
0x14015d34b  mov     rax, [rsi]
0x14015d34e  mov     [r13+60h], rbx
0x14015d352  xor     ebx, ebx
0x14015d354  mov     [r13+68h], rax
0x14015d358  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x14015d35c  test    rcx, rcx
0x14015d35f  jz      short loc_14015D36D
0x14015d361  call    cs:__imp_ZwClose
0x14015d368  nop     dword ptr [rax+rax+00h]
0x14015d36d  test    rdi, rdi
0x14015d370  jnz     short loc_14015D3B8
0x14015d372  xor     ecx, ecx; Buffer
0x14015d374  call    GreDeleteFastMutex
0x14015d379  mov     eax, ebx
0x14015d37b  mov     rcx, [rbp+57h+var_30]
0x14015d37f  xor     rcx, rsp; StackCookie
0x14015d382  call    __security_check_cookie
0x14015d387  lea     r11, [rsp+0E0h+var_20]
0x14015d38f  mov     rbx, [r11+38h]
0x14015d393  mov     rsi, [r11+40h]
0x14015d397  mov     rsp, r11
0x14015d39a  pop     r15
0x14015d39c  pop     r14
0x14015d39e  pop     r13
0x14015d3a0  pop     rdi
0x14015d3a1  pop     rbp
0x14015d3a2  retn
0x14015d3a4  mov     ebx, 0C000007Ch
0x14015d3a9  mov     r8d, 28Fh; unsigned int
0x14015d3af  mov     ecx, ebx; int
0x14015d3b1  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x14015d3b6  jmp     short loc_14015D358
0x14015d3b8  mov     rcx, rdi; PrimaryToken
0x14015d3bb  call    cs:__imp_PsDereferencePrimaryToken
0x14015d3c2  nop     dword ptr [rax+rax+00h]
0x14015d3c7  jmp     short loc_14015D372
0x14015d3c9  mov     r8d, 296h
0x14015d3cf  jmp     short loc_14015D3D7
0x14015d3d1  mov     r8d, 2C5h
0x14015d3d7  mov     ecx, eax
0x14015d3d9  jmp     short loc_14015D3B1
0x14015d3db  lea     rcx, [rbp+57h+var_98]; struct _CIT_IMPACT_CONTEXT **
0x14015d3df  call    ?CitpCleanupGlobalImpactContext@@YAXPEAPEAU_CIT_IMPACT_CONTEXT@@@Z; CitpCleanupGlobalImpactContext(_CIT_IMPACT_CONTEXT * *)
0x14015d3e4  mov     ebx, 0C00000BBh
0x14015d3e9  jmp     loc_14015D358
0x14015d3ee  mov     r8d, 2B5h
0x14015d3f4  jmp     short loc_14015D3D7
0x14015d3f6  mov     ebx, 0C000009Ah
0x14015d3fb  mov     r8d, 2D3h
0x14015d401  jmp     short loc_14015D3AF
0x14015d403  mov     ebx, 0C00000EDh
0x14015d408  jmp     loc_14015D358
```
