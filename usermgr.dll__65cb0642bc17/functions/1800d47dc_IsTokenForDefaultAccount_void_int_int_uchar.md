# IsTokenForDefaultAccount(void *,int,int,uchar *)

- ea: `0x1800d47dc`
- end: `0x1800d4945`
- name: `?IsTokenForDefaultAccount@@YAJPEAXHHPEAE@Z`
- size: `361`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int, int, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007ef4`
- `0x1800391d4`
- `0x1800ca320`

## callees

- `0x1800088e8`
- `0x180061e1c`
- `0x1800d45b0`
- `0x1800d47dc`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d4851`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d48f4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d4851`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d48f4`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800d4899`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800d4899`
- `ntdll!RtlIsMultiSessionSku` at `0x1800d482d`
- `ntdll!RtlIsMultiSessionSku` at `0x1800d482d`

## string_xrefs

- `0x1800d4864`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x1800d4923`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
__int64 __fastcall IsTokenForDefaultAccount(HANDLE TokenHandle, __int64 a2, int a3, unsigned __int8 *a4)
{
  const char *v7; // r9
  __int64 v8; // rdx
  const unsigned __int16 *v10; // rcx
  int v11; // ebx
  __int64 v12; // rdx
  int ReturnLength; // [rsp+20h] [rbp-79h]
  int v14; // [rsp+30h] [rbp-69h] BYREF
  DWORD v15; // [rsp+34h] [rbp-65h] BYREF
  __int128 TokenInformation; // [rsp+38h] [rbp-61h] BYREF
  __int128 v17; // [rsp+48h] [rbp-51h]
  __int128 v18; // [rsp+58h] [rbp-41h]
  __int64 v19; // [rsp+68h] [rbp-31h]
  void *v20; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v14 = 0;
  v15 = 0;
  TokenInformation = 0;
  v19 = 0;
  v17 = 0;
  *a4 = 0;
  v18 = 0;
  if ( (unsigned __int8)RtlIsMultiSessionSku(TokenHandle) )
    return 0;
  if ( !GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &v15) )
  {
    v8 = 332;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v8,
             (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
             v7);
  }
  if ( DWORD2(v17) == 2 )
  {
    if ( SHIDWORD(v17) >= 1 )
    {
      if ( !(unsigned int)CheckTokenMembershipEx(TokenHandle, &DefaultAliasWellKnownSid, a3 != 0, &v14) )
      {
        v8 = 340;
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)v8,
                 (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                 v7);
      }
      if ( v14 )
        *a4 = 1;
      return 0;
    }
    goto LABEL_18;
  }
  if ( DWORD2(v17) != 1 )
  {
LABEL_18:
    v11 = -2147418113;
    v12 = 355;
    goto LABEL_17;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, &v20, 0x54u, &v15) )
  {
    v8 = 350;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v8,
             (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
             v7);
  }
  v11 = IsDefaultAccountSid(v10, v20, a4);
  if ( v11 >= 0 )
    return 0;
  v12 = 351;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
    (const char *)(unsigned int)v11,
    ReturnLength);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800d47dc  mov     [rsp-8+arg_8], rbx
0x1800d47e1  push    rbp
0x1800d47e2  push    rsi
0x1800d47e3  push    rdi
0x1800d47e4  lea     rbp, [rsp-47h]
0x1800d47e9  sub     rsp, 0E0h
0x1800d47f0  mov     rax, cs:__security_cookie
0x1800d47f7  xor     rax, rsp
0x1800d47fa  mov     [rbp+57h+var_20], rax
0x1800d47fe  xorps   xmm0, xmm0
0x1800d4801  mov     [rbp+57h+var_C0], 0
0x1800d4808  xor     eax, eax
0x1800d480a  mov     [rbp+57h+var_BC], 0
0x1800d4811  movups  [rbp+57h+TokenInformation], xmm0
0x1800d4815  mov     [rbp+57h+var_88], rax
0x1800d4819  mov     rbx, r9
0x1800d481c  movups  [rbp+57h+var_A8], xmm0
0x1800d4820  mov     [r9], al
0x1800d4823  mov     esi, r8d
0x1800d4826  movups  [rbp+57h+var_98], xmm0
0x1800d482a  mov     rdi, rcx
0x1800d482d  call    cs:__imp_RtlIsMultiSessionSku
0x1800d4833  test    al, al
0x1800d4835  jnz     short loc_1800D48B3
0x1800d4837  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800d483d  lea     rax, [rbp+57h+var_BC]
0x1800d4841  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800d4845  mov     qword ptr [rsp+0F0h+ReturnLength], rax; ReturnLength
0x1800d484a  mov     rcx, rdi; TokenHandle
0x1800d484d  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800d4851  call    cs:__imp_GetTokenInformation
0x1800d4857  test    eax, eax
0x1800d4859  jnz     short loc_1800D4872
0x1800d485b  mov     edx, 14Ch; void *
0x1800d4860  mov     rcx, [rbp+5Fh]; this
0x1800d4864  lea     r8, aOnecoreDsSecur_79; "onecore\\ds\\security\\umstartup\\aulog"...
0x1800d486b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d4870  jmp     short loc_1800D48B5
0x1800d4872  cmp     dword ptr [rbp+57h+var_A8+8], 2
0x1800d4876  jnz     short loc_1800D48D4
0x1800d4878  cmp     dword ptr [rbp+57h+var_A8+0Ch], 1
0x1800d487c  jl      loc_1800D4939
0x1800d4882  xor     r8d, r8d
0x1800d4885  lea     r9, [rbp+57h+var_C0]
0x1800d4889  test    esi, esi
0x1800d488b  lea     rdx, ?DefaultAliasWellKnownSid@@3PAEA; uchar near * DefaultAliasWellKnownSid
0x1800d4892  mov     rcx, rdi
0x1800d4895  setnz   r8b
0x1800d4899  call    cs:__imp_CheckTokenMembershipEx
0x1800d489f  test    eax, eax
0x1800d48a1  jnz     short loc_1800D48AA
0x1800d48a3  mov     edx, 154h
0x1800d48a8  jmp     short loc_1800D4860
0x1800d48aa  cmp     [rbp+57h+var_C0], 0
0x1800d48ae  jz      short loc_1800D48B3
0x1800d48b0  mov     byte ptr [rbx], 1
0x1800d48b3  xor     eax, eax
0x1800d48b5  mov     rcx, [rbp+57h+var_20]
0x1800d48b9  xor     rcx, rsp; StackCookie
0x1800d48bc  call    __security_check_cookie
0x1800d48c1  mov     rbx, [rsp+0F0h+arg_8]
0x1800d48c9  add     rsp, 0E0h
0x1800d48d0  pop     rdi
0x1800d48d1  pop     rsi
0x1800d48d2  pop     rbp
0x1800d48d3  retn
0x1800d48d4  cmp     dword ptr [rbp+57h+var_A8+8], 1
0x1800d48d8  jnz     short loc_1800D4939
0x1800d48da  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800d48e0  lea     rax, [rbp+57h+var_BC]
0x1800d48e4  lea     r8, [rbp+57h+var_80]; TokenInformation
0x1800d48e8  mov     qword ptr [rsp+0F0h+ReturnLength], rax; int
0x1800d48ed  mov     rcx, rdi; TokenHandle
0x1800d48f0  lea     edx, [r9-53h]; TokenInformationClass
0x1800d48f4  call    cs:__imp_GetTokenInformation
0x1800d48fa  test    eax, eax
0x1800d48fc  jnz     short loc_1800D4908
0x1800d48fe  mov     edx, 15Eh
0x1800d4903  jmp     loc_1800D4860
0x1800d4908  mov     rdx, [rbp+57h+var_80]; void *
0x1800d490c  mov     r8, rbx; unsigned __int8 *
0x1800d490f  call    ?IsDefaultAccountSid@@YAJPEBGPEAXPEAE@Z; IsDefaultAccountSid(ushort const *,void *,uchar *)
0x1800d4914  mov     ebx, eax
0x1800d4916  test    eax, eax
0x1800d4918  jns     short loc_1800D48B3
0x1800d491a  mov     edx, 15Fh; void *
0x1800d491f  mov     rcx, [rbp+5Fh]; this
0x1800d4923  lea     r8, aOnecoreDsSecur_79; "onecore\\ds\\security\\umstartup\\aulog"...
0x1800d492a  mov     r9d, ebx; char *
0x1800d492d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4932  mov     eax, ebx
0x1800d4934  jmp     loc_1800D48B5
0x1800d4939  mov     ebx, 8000FFFFh
0x1800d493e  mov     edx, 163h
0x1800d4943  jmp     short loc_1800D491F
```
