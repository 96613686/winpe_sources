# TSAuditPolicyFailure(_TS_CREDENTIAL *,_TS_CONTEXT *,ushort *)

- ea: `0x1800182f0`
- end: `0x1800186a9`
- name: `?TSAuditPolicyFailure@@YAJPEAU_TS_CREDENTIAL@@PEAU_TS_CONTEXT@@PEAG@Z`
- size: `953`
- prototype: `int(struct _TS_CREDENTIAL *, struct _TS_CONTEXT *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006650`

## callees

- `0x1800032c0`
- `0x180008810`
- `0x18000b550`
- `0x1800182f0`
- `0x1800190bc`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001866a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001866a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001841c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001841c`
- `ntdll!RtlInitUnicodeString` at `0x1800183c4`
- `ntdll!RtlInitUnicodeString` at `0x1800183d1`
- `ntdll!RtlInitUnicodeString` at `0x1800183e2`
- `ntdll!RtlInitUnicodeString` at `0x1800183c4`
- `ntdll!RtlInitUnicodeString` at `0x1800183d1`
- `ntdll!RtlInitUnicodeString` at `0x1800183e2`
- `LSASRV!LsaIAuditInitializeParametersAndWriteEvent` at `0x180018659`
- `LSASRV!LsaIAuditInitializeParametersAndWriteEvent` at `0x180018659`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18001839f`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18001839f`

## string_xrefs

- `0x1800183b9`: `Security`

## pseudocode

```c
__int64 __fastcall TSAuditPolicyFailure(struct _TS_CREDENTIAL *a1, struct _TS_CONTEXT *a2, unsigned __int16 *a3)
{
  _DWORD *v6; // r12
  NTSTATUS v7; // ebx
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rbx
  _WORD *v11; // rsi
  WCHAR *v12; // rax
  WCHAR *v13; // rdi
  __int64 v14; // rax
  _WORD *v15; // rdi
  WCHAR *v16; // rcx
  WCHAR *v17; // rax
  WCHAR *v18; // rdi
  __int64 v19; // rcx
  int v20; // ecx
  char v22[8]; // [rsp+A0h] [rbp-80h] BYREF
  struct _UNICODE_STRING v23; // [rsp+A8h] [rbp-78h] BYREF
  PSID pSid; // [rsp+B8h] [rbp-68h] BYREF
  struct _UNICODE_STRING v25; // [rsp+C0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v26; // [rsp+D0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-40h] BYREF
  _DWORD v28[8]; // [rsp+F0h] [rbp-30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+110h] [rbp-10h] BYREF

  v22[0] = 1;
  memset(v28, 0, sizeof(v28));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  v23 = 0;
  v25 = 0;
  DestinationString = 0;
  v26 = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  v6 = v28;
  if ( ((int (__fastcall *)(_DWORD *))TSGlobalLsaFunctions->GetClientInfo)(v28) < 0 )
    v6 = 0;
  v7 = LsaIAdtAuditingEnabledBySubCategory(112, 0, v6, 0, v22);
  if ( v7 >= 0 )
  {
    if ( v22[0] )
    {
      RtlInitUnicodeString(&DestinationString, L"Security");
      RtlInitUnicodeString(&v25, a3);
      RtlInitUnicodeString(&v26, L"CREDSSP");
      v7 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid);
      if ( v7 >= 0 )
      {
        v8 = *((_DWORD *)a2 + 36);
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            if ( v9 != 1 )
            {
LABEL_11:
              v7 = -1073741811;
              goto LABEL_37;
            }
            v10 = *((_QWORD *)a1 + 18);
          }
          else
          {
            v10 = *((_QWORD *)a2 + 19);
          }
        }
        else
        {
          v10 = *((_QWORD *)a1 + 17);
        }
        if ( !v10 )
          goto LABEL_11;
        v11 = (_WORD *)(v10 + 24);
        if ( *(_DWORD *)v10 == 1 )
        {
          v23.MaximumLength = *v11 + *(_WORD *)(v10 + 8) + 2;
          v12 = (WCHAR *)TSAllocate(v23.MaximumLength);
          v23.Buffer = v12;
          v13 = v12;
          if ( v12 )
          {
            if ( *v11 )
            {
              memcpy_0(v12, *(const void **)(v10 + 32), (unsigned __int16)*v11);
              v14 = (unsigned __int16)*v11;
              v23.Length += v14;
              v15 = (WCHAR *)((char *)v13 + v14);
              if ( !*(_WORD *)(v10 + 8) )
                goto LABEL_34;
              *v15 = 64;
              v13 = v15 + 1;
              v23.Length += 2;
            }
            if ( *(_WORD *)(v10 + 8) )
            {
              v16 = v13;
LABEL_23:
              memcpy_0(v16, *(const void **)(v10 + 16), *(unsigned __int16 *)(v10 + 8));
              v23.Length += *(_WORD *)(v10 + 8);
              goto LABEL_34;
            }
            goto LABEL_34;
          }
        }
        else
        {
          if ( !*v11 || !*(_QWORD *)(v10 + 32) )
          {
            TSGetUpnFromCert(*(const struct _CERT_CONTEXT **)(v10 + 56), &v23);
            goto LABEL_34;
          }
          if ( !*(_WORD *)(v10 + 8) || !*(_QWORD *)(v10 + 16) )
          {
LABEL_34:
            v20 = *((_DWORD *)a2 + 36);
            if ( !v20 || (unsigned int)(v20 - 1) <= 1 )
            {
              v7 = LsaIAuditInitializeParametersAndWriteEvent(2, 5378, 112);
              goto LABEL_37;
            }
            goto LABEL_11;
          }
          v23.MaximumLength = *(_WORD *)(v10 + 8) + *v11 + 2;
          v17 = (WCHAR *)TSAllocate(v23.MaximumLength);
          v23.Buffer = v17;
          v18 = v17;
          if ( v17 )
          {
            memcpy_0(v17, *(const void **)(v10 + 32), (unsigned __int16)*v11);
            v19 = (unsigned __int16)*v11;
            v23.Length += v19;
            *(WCHAR *)((char *)v18 + v19) = 64;
            v23.Length += 2;
            v16 = (WCHAR *)((char *)v18 + v19 + 2);
            goto LABEL_23;
          }
        }
        v23.Length = 0;
        goto LABEL_34;
      }
    }
  }
LABEL_37:
  if ( pSid )
    FreeSid(pSid);
  TSFreeString(&v23);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800182f0  mov     [rsp-38h+arg_18], rbx
0x1800182f5  push    rbp
0x1800182f6  push    rsi
0x1800182f7  push    rdi
0x1800182f8  push    r12
0x1800182fa  push    r13
0x1800182fc  push    r14
0x1800182fe  push    r15
0x180018300  mov     rbp, rsp
0x180018303  sub     rsp, 120h
0x18001830a  mov     rax, cs:__security_cookie
0x180018311  xor     rax, rsp
0x180018314  mov     [rbp+var_8], rax
0x180018318  xor     r13d, r13d
0x18001831b  mov     [rbp+var_80], 1
0x18001831f  mov     [rbp+var_30], r13d
0x180018323  xorps   xmm0, xmm0
0x180018326  mov     dword ptr [rbp+IdentifierAuthority.Value], r13d
0x18001832a  xorps   xmm1, xmm1
0x18001832d  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180018333  mov     rsi, r8
0x180018336  mov     [rbp+pSid], r13
0x18001833a  mov     r14, rdx
0x18001833d  mov     rdi, rcx
0x180018340  movups  xmmword ptr [rbp+var_2C], xmm0
0x180018344  movups  xmmword ptr [rbp+var_2C+0Ch], xmm0
0x180018348  movups  xmmword ptr [rbp+var_78.Length], xmm0
0x18001834c  movups  xmmword ptr [rbp+var_60.Length], xmm1
0x180018350  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180018354  movups  xmmword ptr [rbp+var_50.Length], xmm1
0x180018358  test    rcx, rcx
0x18001835b  jz      loc_18001867D
0x180018361  test    rdx, rdx
0x180018364  jz      loc_18001867D
0x18001836a  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180018371  lea     rcx, [rbp+var_30]
0x180018375  mov     rax, [rax+80h]
0x18001837c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018381  test    eax, eax
0x180018383  lea     r12, [rbp+var_30]
0x180018387  lea     rax, [rbp+var_80]
0x18001838b  cmovs   r12, r13
0x18001838f  mov     qword ptr [rsp+120h+SubAuthority2], rax
0x180018394  xor     edx, edx
0x180018396  xor     r9d, r9d
0x180018399  mov     r8, r12
0x18001839c  lea     ecx, [rdx+70h]
0x18001839f  call    cs:__imp_LsaIAdtAuditingEnabledBySubCategory
0x1800183a5  mov     ebx, eax
0x1800183a7  test    eax, eax
0x1800183a9  js      loc_180018661
0x1800183af  cmp     [rbp+var_80], r13b
0x1800183b3  jz      loc_180018661
0x1800183b9  lea     rdx, aSecurity; "Security"
0x1800183c0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800183c4  call    cs:__imp_RtlInitUnicodeString
0x1800183ca  mov     rdx, rsi; SourceString
0x1800183cd  lea     rcx, [rbp+var_60]; DestinationString
0x1800183d1  call    cs:__imp_RtlInitUnicodeString
0x1800183d7  lea     rdx, aCredssp; "CREDSSP"
0x1800183de  lea     rcx, [rbp+var_50]; DestinationString
0x1800183e2  call    cs:__imp_RtlInitUnicodeString
0x1800183e8  lea     rax, [rbp+pSid]
0x1800183ec  xor     r9d, r9d; SubAuthority1
0x1800183ef  mov     [rsp+120h+Sid], rax; Sid
0x1800183f4  lea     r8d, [r13+12h]; SubAuthority0
0x1800183f8  mov     [rsp+120h+SubAuthority7], r13d; SubAuthority7
0x1800183fd  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180018401  mov     [rsp+120h+SubAuthority6], r13d; SubAuthority6
0x180018406  mov     dl, 1; SubAuthorityCount
0x180018408  mov     [rsp+120h+SubAuthority5], r13d; SubAuthority5
0x18001840d  mov     [rsp+120h+SubAuthority4], r13d; SubAuthority4
0x180018412  mov     [rsp+120h+SubAuthority3], r13d; SubAuthority3
0x180018417  mov     [rsp+120h+SubAuthority2], r13d; SubAuthority2
0x18001841c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180018422  mov     ebx, eax
0x180018424  test    eax, eax
0x180018426  js      loc_180018661
0x18001842c  mov     ecx, [r14+90h]
0x180018433  test    ecx, ecx
0x180018435  jz      short loc_18001845D
0x180018437  sub     ecx, 1
0x18001843a  jz      short loc_180018454
0x18001843c  cmp     ecx, 1
0x18001843f  jz      short loc_18001844B
0x180018441  mov     ebx, 0C000000Dh
0x180018446  jmp     loc_180018661
0x18001844b  mov     rbx, [rdi+90h]
0x180018452  jmp     short loc_180018464
0x180018454  mov     rbx, [r14+98h]
0x18001845b  jmp     short loc_180018464
0x18001845d  mov     rbx, [rdi+88h]
0x180018464  test    rbx, rbx
0x180018467  jz      short loc_180018441
0x180018469  cmp     dword ptr [rbx], 1
0x18001846c  lea     rsi, [rbx+18h]
0x180018470  mov     r15, r13
0x180018473  mov     r10d, 2
0x180018479  jnz     loc_18001850E
0x18001847f  movzx   eax, word ptr [rbx+8]
0x180018483  add     ax, [rsi]
0x180018486  add     ax, r10w
0x18001848a  movzx   ecx, ax; Size
0x18001848d  mov     [rbp+var_78.MaximumLength], cx
0x180018491  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180018496  mov     [rbp+var_78.Buffer], rax
0x18001849a  mov     rdi, rax
0x18001849d  test    rax, rax
0x1800184a0  jz      short loc_180018504
0x1800184a2  cmp     r13w, [rsi]
0x1800184a6  jz      short loc_1800184DB
0x1800184a8  movzx   r8d, word ptr [rsi]; Size
0x1800184ac  mov     rcx, rax; void *
0x1800184af  mov     rdx, [rbx+20h]; Src
0x1800184b3  call    memcpy_0
0x1800184b8  movzx   eax, word ptr [rsi]
0x1800184bb  add     [rbp+var_78.Length], ax
0x1800184bf  add     rdi, rax
0x1800184c2  cmp     r13w, [rbx+8]
0x1800184c7  jz      short loc_1800184FB
0x1800184c9  mov     word ptr [rdi], 40h ; '@'
0x1800184ce  mov     eax, 2
0x1800184d3  add     rdi, 2
0x1800184d7  add     [rbp+var_78.Length], ax
0x1800184db  cmp     r13w, [rbx+8]
0x1800184e0  jz      short loc_1800184FB
0x1800184e2  mov     rcx, rdi; void *
0x1800184e5  mov     rdx, [rbx+10h]; Src
0x1800184e9  movzx   r8d, word ptr [rbx+8]; Size
0x1800184ee  call    memcpy_0
0x1800184f3  movzx   eax, word ptr [rbx+8]
0x1800184f7  add     [rbp+var_78.Length], ax
0x1800184fb  lea     r15, [rbp+var_78]
0x1800184ff  jmp     loc_180018597
0x180018504  mov     [rbp+var_78.Length], r13w
0x180018509  jmp     loc_180018597
0x18001850e  movzx   ecx, word ptr [rsi]
0x180018511  cmp     r13w, cx
0x180018515  jz      short loc_180018580
0x180018517  cmp     [rbx+20h], r13
0x18001851b  jz      short loc_180018580
0x18001851d  cmp     r13w, [rbx+8]
0x180018522  jz      short loc_18001857B
0x180018524  cmp     [rbx+10h], r13
0x180018528  jz      short loc_18001857B
0x18001852a  add     cx, [rbx+8]
0x18001852e  add     cx, r10w
0x180018532  movzx   ecx, cx; Size
0x180018535  mov     [rbp+var_78.MaximumLength], cx
0x180018539  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x18001853e  mov     [rbp+var_78.Buffer], rax
0x180018542  mov     rdi, rax
0x180018545  test    rax, rax
0x180018548  jz      short loc_180018504
0x18001854a  movzx   r8d, word ptr [rsi]; Size
0x18001854e  mov     rcx, rax; void *
0x180018551  mov     rdx, [rbx+20h]; Src
0x180018555  call    memcpy_0
0x18001855a  movzx   ecx, word ptr [rsi]
0x18001855d  mov     eax, 2
0x180018562  add     [rbp+var_78.Length], cx
0x180018566  mov     word ptr [rcx+rdi], 40h ; '@'
0x18001856c  add     rcx, rax
0x18001856f  add     [rbp+var_78.Length], ax
0x180018573  add     rcx, rdi
0x180018576  jmp     loc_1800184E5
0x18001857b  mov     r15, rsi
0x18001857e  jmp     short loc_18001859D
0x180018580  mov     rcx, [rbx+38h]; struct _CERT_CONTEXT *
0x180018584  lea     rdx, [rbp+var_78]; struct _UNICODE_STRING *
0x180018588  call    ?TSGetUpnFromCert@@YAJPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z; TSGetUpnFromCert(_CERT_CONTEXT const *,_UNICODE_STRING *)
0x18001858d  test    eax, eax
0x18001858f  lea     r15, [rbp+var_78]
0x180018593  cmovs   r15, r13
0x180018597  mov     r10d, 2
0x18001859d  mov     ecx, [r14+90h]
0x1800185a4  test    ecx, ecx
0x1800185a6  jz      short loc_1800185C4
0x1800185a8  sub     ecx, 1
0x1800185ab  jz      short loc_1800185BD
0x1800185ad  cmp     ecx, 1
0x1800185b0  jnz     loc_180018441
0x1800185b6  mov     eax, 1FA2h
0x1800185bb  jmp     short loc_1800185C9
0x1800185bd  mov     eax, 1FA1h
0x1800185c2  jmp     short loc_1800185C9
0x1800185c4  mov     eax, 1FA0h
0x1800185c9  mov     [rsp+120h+var_90], eax
0x1800185d0  mov     r9d, 10h
0x1800185d6  mov     [rsp+120h+var_98], 15h
0x1800185e1  lea     rax, [rbp+var_60]
0x1800185e5  mov     [rsp+120h+var_A0], rax
0x1800185ed  mov     edx, 1502h
0x1800185f2  mov     [rsp+120h+var_A8], 1
0x1800185fa  lea     rax, [rbp+var_50]
0x1800185fe  mov     [rsp+120h+var_B0], r15
0x180018603  lea     r8d, [r9+60h]
0x180018607  mov     [rsp+120h+var_B8], 1
0x18001860f  mov     ecx, r10d
0x180018612  mov     [rsp+120h+var_C0], rax
0x180018617  mov     rax, [r12]
0x18001861b  mov     [rsp+120h+var_C8], 1
0x180018623  mov     [rsp+120h+Sid], rax
0x180018628  lea     rax, [rbp+DestinationString]
0x18001862c  mov     [rsp+120h+SubAuthority7], 5
0x180018634  mov     qword ptr [rsp+120h+SubAuthority6], rax
0x180018639  mov     rax, [rbp+pSid]
0x18001863d  mov     [rsp+120h+SubAuthority5], 1
0x180018645  mov     qword ptr [rsp+120h+SubAuthority4], rax
0x18001864a  mov     [rsp+120h+SubAuthority3], 4
0x180018652  mov     word ptr [rsp+120h+SubAuthority2], 7
0x180018659  call    cs:__imp_LsaIAuditInitializeParametersAndWriteEvent
0x18001865f  mov     ebx, eax
0x180018661  mov     rcx, [rbp+pSid]; pSid
0x180018665  test    rcx, rcx
0x180018668  jz      short loc_180018670
0x18001866a  call    cs:__imp_FreeSid
0x180018670  lea     rcx, [rbp+var_78]; struct _UNICODE_STRING *
0x180018674  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x180018679  mov     eax, ebx
0x18001867b  jmp     short loc_180018682
0x18001867d  mov     eax, 0C000000Dh
0x180018682  mov     rcx, [rbp+var_8]
0x180018686  xor     rcx, rsp; StackCookie
0x180018689  call    __security_check_cookie
0x18001868e  mov     rbx, [rsp+120h+arg_18]
0x180018696  add     rsp, 120h
0x18001869d  pop     r15
0x18001869f  pop     r14
0x1800186a1  pop     r13
0x1800186a3  pop     r12
0x1800186a5  pop     rdi
0x1800186a6  pop     rsi
0x1800186a7  pop     rbp
0x1800186a8  retn
```
