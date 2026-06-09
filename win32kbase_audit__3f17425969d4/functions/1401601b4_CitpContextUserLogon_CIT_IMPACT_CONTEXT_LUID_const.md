# CitpContextUserLogon(_CIT_IMPACT_CONTEXT *,_LUID const *)

- ea: `0x1401601b4`
- end: `0x1401603dd`
- name: `?CitpContextUserLogon@@YAJPEAU_CIT_IMPACT_CONTEXT@@PEBU_LUID@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct _CIT_IMPACT_CONTEXT *, const struct _LUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c1c0c`

## callees

- `0x14007b930`
- `0x14007efd0`
- `0x1401601b4`
- `0x140160674`
- `0x14019029c`
- `0x1401b10e8`
- `0x1402388e0`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401601f6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401601f6`
- `ntoskrnl!ZwClose` at `0x140160331`
- `ntoskrnl!ZwClose` at `0x140160331`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14016028b`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14016028b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140160205`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140160205`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140160224`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140160224`
- `ntoskrnl!RtlLengthSid` at `0x1401602e0`
- `ntoskrnl!RtlLengthSid` at `0x1401602e0`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14016038b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14016038b`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401602c3`
- `ntoskrnl!ZwQueryInformationToken` at `0x1401602c3`
- `WIN32K!W32GetUserSessionState` at `0x140160251`
- `WIN32K!W32GetUserSessionState` at `0x140160251`

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
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(a1);
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
    UserSessionState = W32GetUserSessionState(v9, v6);
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
0x1401601b4  mov     [rsp-8+arg_8], rbx
0x1401601b9  mov     [rsp-8+arg_10], rsi
0x1401601be  push    rbp
0x1401601bf  push    rdi
0x1401601c0  push    r13
0x1401601c2  push    r14
0x1401601c4  push    r15
0x1401601c6  lea     rbp, [rsp-37h]
0x1401601cb  sub     rsp, 0C0h
0x1401601d2  mov     rax, cs:__security_cookie
0x1401601d9  xor     rax, rsp
0x1401601dc  mov     [rbp+57h+var_30], rax
0x1401601e0  mov     rsi, rdx
0x1401601e3  mov     [rbp+57h+TokenHandle], 0
0x1401601eb  mov     r13, rcx
0x1401601ee  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 0
0x1401601f6  call    cs:__imp_PsGetCurrentProcess
0x1401601fd  nop     dword ptr [rax+rax+00h]
0x140160202  mov     rcx, rax; Process
0x140160205  call    cs:__imp_PsReferencePrimaryToken
0x14016020c  nop     dword ptr [rax+rax+00h]
0x140160211  mov     rdi, rax
0x140160214  test    rax, rax
0x140160217  jz      loc_140160374
0x14016021d  lea     rdx, [rbp+57h+AuthenticationId]; AuthenticationId
0x140160221  mov     rcx, rax; Token
0x140160224  call    cs:__imp_SeQueryAuthenticationIdToken
0x14016022b  nop     dword ptr [rax+rax+00h]
0x140160230  mov     ebx, eax
0x140160232  test    eax, eax
0x140160234  js      loc_140160399
0x14016023a  mov     eax, [rsi]
0x14016023c  cmp     [rbp+57h+AuthenticationId.LowPart], eax
0x14016023f  jnz     loc_1401603D3
0x140160245  mov     eax, [rsi+4]
0x140160248  cmp     [rbp+57h+AuthenticationId.HighPart], eax
0x14016024b  jnz     loc_1401603D3
0x140160251  call    cs:__imp_W32GetUserSessionState
0x140160258  nop     dword ptr [rax+rax+00h]
0x14016025d  mov     r11, [rax+4A30h]
0x140160264  lea     rcx, [r11+4]; struct _CIT_PARAMETERS *
0x140160268  call    ?CitpParametersCompute@@YAXPEAU_CIT_PARAMETERS@@@Z; CitpParametersCompute(_CIT_PARAMETERS *)
0x14016026d  cmp     byte ptr [r11+18h], 0
0x140160272  jz      loc_1401603AB
0x140160278  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14016027c  mov     edx, 8; DesiredAccess
0x140160281  mov     r8d, 200h; HandleAttributes
0x140160287  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14016028b  call    cs:__imp_ZwOpenProcessTokenEx
0x140160292  nop     dword ptr [rax+rax+00h]
0x140160297  mov     ebx, eax
0x140160299  test    eax, eax
0x14016029b  js      loc_1401603BE
0x1401602a1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1401602a5  lea     rax, [rbp+57h+var_B0]
0x1401602a9  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1401602af  mov     [rbp+57h+var_B0], 0
0x1401602b6  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1401602ba  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1401602bf  lea     edx, [r9-57h]; TokenInformationClass
0x1401602c3  call    cs:__imp_ZwQueryInformationToken
0x1401602ca  nop     dword ptr [rax+rax+00h]
0x1401602cf  mov     ebx, eax
0x1401602d1  test    eax, eax
0x1401602d3  js      loc_1401603A1
0x1401602d9  mov     r14, [rbp+57h+TokenInformation]
0x1401602dd  mov     rcx, r14; Sid
0x1401602e0  call    cs:__imp_RtlLengthSid
0x1401602e7  nop     dword ptr [rax+rax+00h]
0x1401602ec  mov     edx, eax; unsigned __int64
0x1401602ee  mov     r8d, 49637355h; unsigned int
0x1401602f4  mov     ecx, 100h; unsigned __int64
0x1401602f9  mov     r15d, eax
0x1401602fc  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140160301  mov     rbx, rax
0x140160304  test    rax, rax
0x140160307  jz      loc_1401603C6
0x14016030d  mov     r8d, r15d; Size
0x140160310  mov     rdx, r14; Src
0x140160313  mov     rcx, rax; void *
0x140160316  call    memmove
0x14016031b  mov     rax, [rsi]
0x14016031e  mov     [r13+60h], rbx
0x140160322  xor     ebx, ebx
0x140160324  mov     [r13+68h], rax
0x140160328  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x14016032c  test    rcx, rcx
0x14016032f  jz      short loc_14016033D
0x140160331  call    cs:__imp_ZwClose
0x140160338  nop     dword ptr [rax+rax+00h]
0x14016033d  test    rdi, rdi
0x140160340  jnz     short loc_140160388
0x140160342  xor     ecx, ecx; Buffer
0x140160344  call    GreDeleteFastMutex
0x140160349  mov     eax, ebx
0x14016034b  mov     rcx, [rbp+57h+var_30]
0x14016034f  xor     rcx, rsp; StackCookie
0x140160352  call    __security_check_cookie
0x140160357  lea     r11, [rsp+0E0h+var_20]
0x14016035f  mov     rbx, [r11+38h]
0x140160363  mov     rsi, [r11+40h]
0x140160367  mov     rsp, r11
0x14016036a  pop     r15
0x14016036c  pop     r14
0x14016036e  pop     r13
0x140160370  pop     rdi
0x140160371  pop     rbp
0x140160372  retn
0x140160374  mov     ebx, 0C000007Ch
0x140160379  mov     r8d, 28Fh; unsigned int
0x14016037f  mov     ecx, ebx; int
0x140160381  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x140160386  jmp     short loc_140160328
0x140160388  mov     rcx, rdi; PrimaryToken
0x14016038b  call    cs:__imp_PsDereferencePrimaryToken
0x140160392  nop     dword ptr [rax+rax+00h]
0x140160397  jmp     short loc_140160342
0x140160399  mov     r8d, 296h
0x14016039f  jmp     short loc_1401603A7
0x1401603a1  mov     r8d, 2C5h
0x1401603a7  mov     ecx, eax
0x1401603a9  jmp     short loc_140160381
0x1401603ab  lea     rcx, [rbp+57h+var_98]; struct _CIT_IMPACT_CONTEXT **
0x1401603af  call    ?CitpCleanupGlobalImpactContext@@YAXPEAPEAU_CIT_IMPACT_CONTEXT@@@Z; CitpCleanupGlobalImpactContext(_CIT_IMPACT_CONTEXT * *)
0x1401603b4  mov     ebx, 0C00000BBh
0x1401603b9  jmp     loc_140160328
0x1401603be  mov     r8d, 2B5h
0x1401603c4  jmp     short loc_1401603A7
0x1401603c6  mov     ebx, 0C000009Ah
0x1401603cb  mov     r8d, 2D3h
0x1401603d1  jmp     short loc_14016037F
0x1401603d3  mov     ebx, 0C00000EDh
0x1401603d8  jmp     loc_140160328
```
