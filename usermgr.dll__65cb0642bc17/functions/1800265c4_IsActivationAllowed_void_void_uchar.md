# IsActivationAllowed(void *,void *,uchar *)

- ea: `0x1800265c4`
- end: `0x180026889`
- name: `?IsActivationAllowed@@YAKPEAX0PEAE@Z`
- size: `709`
- prototype: `unsigned int __fastcall(HANDLE hExistingToken, void *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035c50`

## callees

- `0x1800265c4`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002662b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026687`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002662b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026687`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180026763`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180026763`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180026854`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180026854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002687e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002687e`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180026800`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180026800`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800266c2`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18002678a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800267ac`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800267e0`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800266c2`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18002678a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800267ac`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800267e0`
- `ntdll!RtlIsMultiSessionSku` at `0x1800266d8`
- `ntdll!RtlIsMultiSessionSku` at `0x1800266d8`

## pseudocode

```c
__int64 __fastcall IsActivationAllowed(HANDLE hExistingToken, void *a2, unsigned __int8 *a3)
{
  HANDLE v5; // r14
  __int64 v6; // rsi
  DWORD LastError; // ebx
  WINBOOL pfResult; // [rsp+30h] [rbp-40h] BYREF
  int v14; // [rsp+34h] [rbp-3Ch] BYREF
  int TokenInformation; // [rsp+38h] [rbp-38h] BYREF
  int v16; // [rsp+3Ch] [rbp-34h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-30h] BYREF
  DWORD v18; // [rsp+44h] [rbp-2Ch] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+50h] [rbp-20h] BYREF

  v5 = hExistingToken;
  v16 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  hObject = 0;
  if ( !SuccessfulInit )
    return 50;
  if ( !GetTokenInformation(hExistingToken, TokenType, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_25;
  if ( TokenInformation != 1 )
    goto LABEL_4;
  if ( !DuplicateTokenEx(v5, 8u, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
  {
LABEL_25:
    LastError = GetLastError();
    goto LABEL_17;
  }
  v5 = hObject;
LABEL_4:
  pfResult = 0;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  v14 = 0;
  v18 = 0;
  *a3 = 0;
  v6 = (__int64)v5;
  if ( !v5 )
    v6 = -6;
  *(_OWORD *)&RequiredPrivileges.PrivilegeCount = 0;
  if ( !GetTokenInformation((HANDLE)v6, TokenIsAppContainer, &v14, 4u, &v18) )
    goto LABEL_21;
  if ( a2 )
  {
    if ( !(unsigned int)CheckTokenMembershipEx(v6, a2, 0, &pfResult) )
      goto LABEL_21;
  }
  LastError = 0;
  if ( !pfResult )
  {
    if ( !(unsigned int)CheckTokenMembershipEx(v6, &CapActivateGroupSidBuffer, v14 != 0, &pfResult) )
      goto LABEL_21;
    if ( !pfResult )
    {
      if ( !(unsigned __int8)RtlIsMultiSessionSku()
        && !(unsigned int)CheckTokenMembershipEx(v6, &DefaultAliasWellKnownSid, v14 != 0, &pfResult) )
      {
        goto LABEL_21;
      }
      if ( !pfResult )
      {
        RequiredPrivileges.PrivilegeCount = 1;
        RequiredPrivileges.Control = 1;
        RequiredPrivileges.Privilege[0].Luid = (LUID)29LL;
        RequiredPrivileges.Privilege[0].Attributes = 0;
        if ( !PrivilegeCheck((HANDLE)v6, &RequiredPrivileges, &pfResult) )
          goto LABEL_21;
        if ( !pfResult )
          goto LABEL_15;
      }
    }
  }
  if ( v14 )
  {
    if ( (unsigned int)CheckTokenCapability(v6, &CapActivateSidBuffer, &pfResult) )
    {
      if ( !pfResult )
        goto LABEL_15;
      goto LABEL_14;
    }
LABEL_21:
    LastError = GetLastError();
    goto LABEL_15;
  }
LABEL_14:
  *a3 = 1;
LABEL_15:
  if ( !LastError && !*a3 )
  {
    if ( (unsigned int)CheckTokenMembershipEx(v5, a2, 1, &v16) )
    {
      if ( v16 )
        *a3 = 1;
      goto LABEL_17;
    }
    goto LABEL_25;
  }
LABEL_17:
  if ( hObject )
    CloseHandle(hObject);
  return LastError;
}

```

## disassembly

```asm
0x1800265c4  mov     [rsp-38h+arg_18], rbx
0x1800265c9  push    rbp
0x1800265ca  push    rsi
0x1800265cb  push    rdi
0x1800265cc  push    r12
0x1800265ce  push    r13
0x1800265d0  push    r14
0x1800265d2  push    r15
0x1800265d4  mov     rbp, rsp
0x1800265d7  sub     rsp, 70h
0x1800265db  mov     rax, cs:__security_cookie
0x1800265e2  xor     rax, rsp
0x1800265e5  mov     [rbp+var_8], rax
0x1800265e9  xor     r13d, r13d
0x1800265ec  mov     r15, r8
0x1800265ef  cmp     cs:?SuccessfulInit@@3KA, r13d; ulong SuccessfulInit
0x1800265f6  mov     r12, rdx
0x1800265f9  mov     r14, rcx
0x1800265fc  mov     [rbp+var_34], r13d
0x180026600  mov     [rbp+TokenInformation], r13d
0x180026604  mov     [rbp+var_30], r13d
0x180026608  mov     [rbp+hObject], r13
0x18002660c  jz      loc_18002681F
0x180026612  lea     edi, [r13+4]
0x180026616  lea     rax, [rbp+var_30]
0x18002661a  mov     r9d, edi; TokenInformationLength
0x18002661d  lea     ebx, [rdi+4]
0x180026620  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180026625  mov     edx, ebx; TokenInformationClass
0x180026627  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002662b  call    cs:__imp_GetTokenInformation
0x180026631  test    eax, eax
0x180026633  jz      loc_1800267BA
0x180026639  cmp     [rbp+TokenInformation], 1
0x18002663d  jz      loc_180026838
0x180026643  xor     eax, eax
0x180026645  mov     [rbp+pfResult], r13d
0x180026649  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18002664c  lea     r8, [rbp+var_3C]; TokenInformation
0x180026650  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180026657  mov     [rbp+var_3C], r13d
0x18002665b  xorps   xmm0, xmm0
0x18002665e  mov     [rbp+var_2C], r13d
0x180026662  test    r14, r14
0x180026665  mov     [r15], r13b
0x180026668  mov     rsi, r14
0x18002666b  mov     r9d, edi; TokenInformationLength
0x18002666e  cmovz   rsi, rax
0x180026672  mov     edx, 1Dh; TokenInformationClass
0x180026677  lea     rax, [rbp+var_2C]
0x18002667b  mov     rcx, rsi; TokenHandle
0x18002667e  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180026683  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x180026687  call    cs:__imp_GetTokenInformation
0x18002668d  mov     edi, eax
0x18002668f  test    eax, eax
0x180026691  jz      loc_180026773
0x180026697  test    r12, r12
0x18002669a  jnz     loc_18002677D
0x1800266a0  mov     ebx, r13d
0x1800266a3  cmp     [rbp+pfResult], r13d
0x1800266a7  jnz     short loc_1800266EC
0x1800266a9  cmp     [rbp+var_3C], r13d
0x1800266ad  lea     r9, [rbp+pfResult]
0x1800266b1  mov     r8d, r13d
0x1800266b4  lea     rdx, ?CapActivateGroupSidBuffer@@3PAEA; uchar near * CapActivateGroupSidBuffer
0x1800266bb  setnz   r8b
0x1800266bf  mov     rcx, rsi
0x1800266c2  call    cs:__imp_CheckTokenMembershipEx
0x1800266c8  mov     edi, eax
0x1800266ca  test    eax, eax
0x1800266cc  jz      loc_180026773
0x1800266d2  cmp     [rbp+pfResult], r13d
0x1800266d6  jnz     short loc_1800266EC
0x1800266d8  call    cs:__imp_RtlIsMultiSessionSku
0x1800266de  test    al, al
0x1800266e0  jz      loc_1800267C7
0x1800266e6  cmp     [rbp+pfResult], r13d
0x1800266ea  jz      short loc_18002673E
0x1800266ec  cmp     [rbp+var_3C], r13d
0x1800266f0  jnz     loc_1800267F2
0x1800266f6  mov     byte ptr [r15], 1
0x1800266fa  test    edi, edi
0x1800266fc  jz      short loc_180026773
0x1800266fe  test    ebx, ebx
0x180026700  jnz     short loc_18002670B
0x180026702  cmp     [r15], r13b
0x180026705  jz      loc_18002679C
0x18002670b  mov     rcx, [rbp+hObject]; hObject
0x18002670f  test    rcx, rcx
0x180026712  jnz     loc_18002687E
0x180026718  mov     eax, ebx
0x18002671a  mov     rcx, [rbp+var_8]
0x18002671e  xor     rcx, rsp; StackCookie
0x180026721  call    __security_check_cookie
0x180026726  mov     rbx, [rsp+70h+arg_18]
0x18002672e  add     rsp, 70h
0x180026732  pop     r15
0x180026734  pop     r14
0x180026736  pop     r13
0x180026738  pop     r12
0x18002673a  pop     rdi
0x18002673b  pop     rsi
0x18002673c  pop     rbp
0x18002673d  retn
0x18002673e  lea     r8, [rbp+pfResult]; pfResult
0x180026742  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180026749  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18002674d  mov     [rbp+RequiredPrivileges.Control], 1
0x180026754  mov     rcx, rsi; ClientToken
0x180026757  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 1Dh
0x18002675f  mov     [rbp+RequiredPrivileges.Privilege.Attributes], r13d
0x180026763  call    cs:__imp_PrivilegeCheck
0x180026769  mov     edi, eax
0x18002676b  test    eax, eax
0x18002676d  jnz     loc_180026829
0x180026773  call    cs:__imp_GetLastError
0x180026779  mov     ebx, eax
0x18002677b  jmp     short loc_1800266FE
0x18002677d  lea     r9, [rbp+pfResult]
0x180026781  xor     r8d, r8d
0x180026784  mov     rdx, r12
0x180026787  mov     rcx, rsi
0x18002678a  call    cs:__imp_CheckTokenMembershipEx
0x180026790  mov     edi, eax
0x180026792  test    eax, eax
0x180026794  jnz     loc_1800266A0
0x18002679a  jmp     short loc_180026773
0x18002679c  lea     r9, [rbp+var_34]
0x1800267a0  mov     r8d, 1
0x1800267a6  mov     rdx, r12
0x1800267a9  mov     rcx, r14
0x1800267ac  call    cs:__imp_CheckTokenMembershipEx
0x1800267b2  test    eax, eax
0x1800267b4  jnz     loc_18002686B
0x1800267ba  call    cs:__imp_GetLastError
0x1800267c0  mov     ebx, eax
0x1800267c2  jmp     loc_18002670B
0x1800267c7  cmp     [rbp+var_3C], r13d
0x1800267cb  lea     r9, [rbp+pfResult]
0x1800267cf  mov     r8d, r13d
0x1800267d2  lea     rdx, ?DefaultAliasWellKnownSid@@3PAEA; uchar near * DefaultAliasWellKnownSid
0x1800267d9  setnz   r8b
0x1800267dd  mov     rcx, rsi
0x1800267e0  call    cs:__imp_CheckTokenMembershipEx
0x1800267e6  mov     edi, eax
0x1800267e8  test    eax, eax
0x1800267ea  jnz     loc_1800266E6
0x1800267f0  jmp     short loc_180026773
0x1800267f2  lea     r8, [rbp+pfResult]
0x1800267f6  mov     rcx, rsi
0x1800267f9  lea     rdx, ?CapActivateSidBuffer@@3PAEA; uchar near * CapActivateSidBuffer
0x180026800  call    cs:__imp_CheckTokenCapability
0x180026806  mov     edi, eax
0x180026808  test    eax, eax
0x18002680a  jz      loc_180026773
0x180026810  cmp     [rbp+pfResult], r13d
0x180026814  jnz     loc_1800266F6
0x18002681a  jmp     loc_1800266FE
0x18002681f  mov     eax, 32h ; '2'
0x180026824  jmp     loc_18002671A
0x180026829  cmp     [rbp+pfResult], r13d
0x18002682d  jz      loc_1800266FE
0x180026833  jmp     loc_1800266EC
0x180026838  lea     rax, [rbp+hObject]
0x18002683c  mov     r9d, 2; ImpersonationLevel
0x180026842  mov     [rsp+70h+phNewToken], rax; phNewToken
0x180026847  xor     r8d, r8d; lpTokenAttributes
0x18002684a  mov     edx, ebx; dwDesiredAccess
0x18002684c  mov     dword ptr [rsp+70h+ReturnLength], r9d; TokenType
0x180026851  mov     rcx, r14; hExistingToken
0x180026854  call    cs:__imp_DuplicateTokenEx
0x18002685a  test    eax, eax
0x18002685c  jz      loc_1800267BA
0x180026862  mov     r14, [rbp+hObject]
0x180026866  jmp     loc_180026643
0x18002686b  cmp     [rbp+var_34], r13d
0x18002686f  jz      loc_18002670B
0x180026875  mov     byte ptr [r15], 1
0x180026879  jmp     loc_18002670B
0x18002687e  call    cs:__imp_CloseHandle
0x180026884  jmp     loc_180026718
```
