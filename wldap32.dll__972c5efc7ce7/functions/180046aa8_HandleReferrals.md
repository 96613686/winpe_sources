# HandleReferrals

- ea: `0x180046aa8`
- end: `0x180046f42`
- name: `HandleReferrals`
- size: `1178`
- prototype: `__int64 __fastcall(struct ldap_connection *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000bf40`

## callees

- `0x1800037a8`
- `0x180008660`
- `0x1800147f0`
- `0x180046038`
- `0x180046aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046d31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046d31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046d7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ecb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046d7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ecb`

## string_xrefs

- `0x180046e5b`: `HandleReferrals reopening request 0x%x.\n`
- `0x180046e87`: `HandleReferrals failed to reopen request 0x%x.\n`
- `0x180046ebc`: `HandleReferrals failed to reopen request 0x%x.\n`

## pseudocode

```c
__int64 __fastcall HandleReferrals(struct ldap_connection *a1, LDAPMessage **a2, __int64 a3, unsigned int a4)
{
  int v5; // r8d
  LDAPMessage **v6; // rax
  struct ldap_connection *v7; // r11
  LDAPMessage *v8; // rbp
  LDAPMessage *v9; // r14
  LDAPMessage *v10; // r13
  LDAPMessage *v11; // rcx
  LDAPMessage *v12; // r15
  LDAPMessage *v13; // rdi
  LDAPMessage *v14; // rdx
  LDAPMessage *v15; // r9
  LDAPMessage *lm_chain; // r10
  int v17; // esi
  LDAPMessage *v18; // r12
  unsigned int v19; // eax
  int v20; // ecx
  int v21; // eax
  unsigned int v22; // esi
  struct _RTL_CRITICAL_SECTION *v23; // rdi
  __int64 v24; // rax
  bool v25; // zf

  v5 = g_fTracingOn;
  v6 = a2;
  v7 = a1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
  {
    LDAPClientPrint(0x800000, "HandleReferrels looking at request 0x%x, number 0x%x\n", a3, *(_DWORD *)(a3 + 108));
    v5 = g_fTracingOn;
    v7 = a1;
    v6 = a2;
  }
  if ( !*(_BYTE *)(a3 + 185) )
    goto LABEL_91;
  v11 = *v6;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( !*v6 )
    goto LABEL_89;
  do
  {
    lm_chain = v11->lm_chain;
    if ( v11->lm_eom == 1 )
      v12 = v11;
    v11->lm_chain = 0;
    if ( v11->lm_chased == 1 || v11->lm_msgtype == 100 || v11->lm_msgtype != 115 && v11->lm_returncode - 9 > 1 )
    {
      if ( v11->lm_msgtype == 101 )
      {
        if ( v10 )
          v15->lm_chain = v11;
        else
          v10 = v11;
        v15 = v11;
      }
      else
      {
        if ( v8 )
          v9->lm_chain = v11;
        else
          v8 = v11;
        v9 = v11;
      }
    }
    else
    {
      if ( v13 )
        v14->lm_chain = v11;
      else
        v13 = v11;
      v14 = v11;
    }
    v11 = lm_chain;
  }
  while ( lm_chain );
  if ( !v13 )
  {
LABEL_89:
    if ( v5 && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(
        0x800000,
        "HandleReferrels no referrals for request 0x%x, number 0x%x\n",
        a3,
        *(_DWORD *)(a3 + 108));
    goto LABEL_91;
  }
  v17 = 0;
  do
  {
    v18 = v13->lm_chain;
    v13->lm_chain = 0;
    v13->lm_chased = 1;
    v19 = HandleReferral(v7, v13, (struct ldap_request *)a3, a4);
    if ( v19 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(
          0x800000,
          "HandleReferrels chasing referral for 0x%x, number 0x%x returned 0x%x\n",
          a3,
          *(_DWORD *)(a3 + 108),
          v19);
      if ( v8 )
        v9->lm_chain = v13;
      else
        v8 = v13;
      v9 = v13;
    }
    else
    {
      v20 = g_fTracingOn;
      ++v17;
      v21 = g_fProviderEnabled;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      {
        LDAPClientPrint(
          0x800000,
          "HandleReferrels successfully chased referral for 0x%x, number 0x%x\n",
          a3,
          *(_DWORD *)(a3 + 108));
        v20 = g_fTracingOn;
        v21 = g_fProviderEnabled;
      }
      if ( v12 == v13 )
      {
        if ( v20 && v21 )
        {
          if ( (g_ulTraceFlags & 0x800000) != 0 )
          {
            LDAPClientPrint(0x800000, "HandleReferrals unmarking EOM for request 0x%x\n", a3);
          }
          else if ( (g_ulTraceFlags & 0x1000) != 0 )
          {
            LDAPClientPrint(4096, "HandleReferrals unmarking EOM for request 0x%x, msg 0x%x\n", a3, (_DWORD)v12);
          }
        }
        v12->lm_eom = 0;
        v12 = 0;
      }
      ldap_msgfree(v13);
    }
    v7 = a1;
    v13 = v18;
  }
  while ( v18 );
  if ( !v17 )
  {
LABEL_91:
    v22 = 82;
    if ( v9 )
      v9->lm_chain = v10;
    else
      v8 = v10;
    goto LABEL_94;
  }
  v22 = 0;
  if ( v9 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a3 + 48));
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferrals putting messages back on request 0x%x\n", a3);
    v9->lm_chain = *(struct ldapmsg **)(a3 + 24);
    *(_QWORD *)(a3 + 24) = v8;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a3 + 48));
  }
  if ( v12 )
  {
    if ( g_fTracingOn && g_fProviderEnabled )
    {
      if ( (g_ulTraceFlags & 0x800000) != 0 )
      {
        LDAPClientPrint(0x800000, "HandleReferrals unmarking EOM for request 0x%x\n", a3);
      }
      else if ( g_fProviderEnabled && (g_ulTraceFlags & 0x1000) != 0 )
      {
        LDAPClientPrint(4096, "HandleReferrals unmarking EOM for request 0x%x, message 0x%x\n", a3, (_DWORD)v12);
      }
    }
    v12->lm_eom = 0;
  }
  if ( *(_BYTE *)(a3 + 188) == 1 )
  {
    v23 = (struct _RTL_CRITICAL_SECTION *)(a3 + 48);
    EnterCriticalSection((LPCRITICAL_SECTION)(a3 + 48));
    if ( *(_BYTE *)(a3 + 188) == 1 && *(_WORD *)(a3 + 182) )
    {
      v24 = ReferenceLdapRequest(a3);
      if ( v24 )
      {
        v25 = g_fTracingOn == 0;
        *(_BYTE *)(v24 + 188) = 0;
        if ( !v25 && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
          LDAPClientPrint(0x1000000, "HandleReferrals reopening request 0x%x.\n", v24);
      }
      else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
      {
        LDAPClientPrint(0x1000000, "HandleReferrals failed to reopen request 0x%x.\n", a3);
      }
      v23 = (struct _RTL_CRITICAL_SECTION *)(a3 + 48);
    }
    else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
    {
      LDAPClientPrint(0x1000000, "HandleReferrals failed to reopen request 0x%x.\n", a3);
    }
    LeaveCriticalSection(v23);
  }
  ldap_msgfree(v10);
  v8 = 0;
LABEL_94:
  *a2 = v8;
  return v22;
}

```

## disassembly

```asm
0x180046aa8  mov     [rsp+arg_18], r9d
0x180046aad  mov     [rsp+arg_8], rdx
0x180046ab2  mov     [rsp+arg_0], rcx
0x180046ab7  push    rbx
0x180046ab8  push    rbp
0x180046ab9  push    rsi
0x180046aba  push    rdi
0x180046abb  push    r12
0x180046abd  push    r13
0x180046abf  push    r14
0x180046ac1  push    r15
0x180046ac3  sub     rsp, 38h
0x180046ac7  xor     r12d, r12d
0x180046aca  mov     rbx, r8
0x180046acd  mov     r8d, cs:g_fTracingOn
0x180046ad4  mov     rax, rdx
0x180046ad7  mov     r11, rcx
0x180046ada  mov     ebp, r12d
0x180046add  mov     r14d, r12d
0x180046ae0  mov     r13d, r12d
0x180046ae3  mov     esi, 800000h
0x180046ae8  test    r8d, r8d
0x180046aeb  jz      short loc_180046B2B
0x180046aed  cmp     cs:g_fProviderEnabled, r12d
0x180046af4  jz      short loc_180046B2B
0x180046af6  test    cs:g_ulTraceFlags, rsi
0x180046afd  jz      short loc_180046B2B
0x180046aff  mov     r9d, [rbx+6Ch]
0x180046b03  lea     rdx, aHandlereferrel_0; "HandleReferrels looking at request 0x%x"...
0x180046b0a  mov     r8, rbx
0x180046b0d  mov     ecx, esi
0x180046b0f  call    LDAPClientPrint
0x180046b14  mov     r8d, cs:g_fTracingOn
0x180046b1b  mov     r11, [rsp+78h+arg_0]
0x180046b23  mov     rax, [rsp+78h+arg_8]
0x180046b2b  cmp     [rbx+0B9h], r12b
0x180046b32  jz      loc_180046F10
0x180046b38  mov     rcx, [rax]
0x180046b3b  mov     r15, r12
0x180046b3e  mov     rdi, r12
0x180046b41  mov     rdx, r12
0x180046b44  mov     r9, r12
0x180046b47  test    rcx, rcx
0x180046b4a  jz      loc_180046EE4
0x180046b50  cmp     byte ptr [rcx+3Fh], 1
0x180046b54  mov     r10, [rcx+10h]
0x180046b58  cmovz   r15, rcx
0x180046b5c  mov     [rcx+10h], r12
0x180046b60  cmp     byte ptr [rcx+3Eh], 1
0x180046b64  jz      short loc_180046B90
0x180046b66  cmp     dword ptr [rcx+4], 64h ; 'd'
0x180046b6a  jz      short loc_180046B90
0x180046b6c  cmp     dword ptr [rcx+4], 73h ; 's'
0x180046b70  jz      short loc_180046B7D
0x180046b72  mov     eax, [rcx+38h]
0x180046b75  sub     eax, 9
0x180046b78  cmp     eax, 1
0x180046b7b  ja      short loc_180046B90
0x180046b7d  test    rdi, rdi
0x180046b80  jnz     short loc_180046B87
0x180046b82  mov     rdi, rcx
0x180046b85  jmp     short loc_180046B8B
0x180046b87  mov     [rdx+10h], rcx
0x180046b8b  mov     rdx, rcx
0x180046b8e  jmp     short loc_180046BBA
0x180046b90  cmp     dword ptr [rcx+4], 65h ; 'e'
0x180046b94  jnz     short loc_180046BA9
0x180046b96  test    r13, r13
0x180046b99  jnz     short loc_180046BA0
0x180046b9b  mov     r13, rcx
0x180046b9e  jmp     short loc_180046BA4
0x180046ba0  mov     [r9+10h], rcx
0x180046ba4  mov     r9, rcx
0x180046ba7  jmp     short loc_180046BBA
0x180046ba9  test    rbp, rbp
0x180046bac  jnz     short loc_180046BB3
0x180046bae  mov     rbp, rcx
0x180046bb1  jmp     short loc_180046BB7
0x180046bb3  mov     [r14+10h], rcx
0x180046bb7  mov     r14, rcx
0x180046bba  mov     rcx, r10
0x180046bbd  test    r10, r10
0x180046bc0  jnz     short loc_180046B50
0x180046bc2  mov     [rsp+78h+res], r13
0x180046bca  test    rdi, rdi
0x180046bcd  jz      loc_180046EE4
0x180046bd3  mov     r13d, [rsp+78h+arg_18]
0x180046bdb  mov     esi, r12d
0x180046bde  mov     r12, [rdi+10h]
0x180046be2  mov     r9d, r13d; unsigned int
0x180046be5  mov     r8, rbx; struct ldap_request *
0x180046be8  mov     qword ptr [rdi+10h], 0
0x180046bf0  mov     rdx, rdi; struct ldapmsg *
0x180046bf3  mov     byte ptr [rdi+3Eh], 1
0x180046bf7  mov     rcx, r11; struct ldap_connection *
0x180046bfa  call    ?HandleReferral@@YAKPEAUldap_connection@@PEAUldapmsg@@PEAUldap_request@@K@Z; HandleReferral(ldap_connection *,ldapmsg *,ldap_request *,ulong)
0x180046bff  test    eax, eax
0x180046c01  jnz     loc_180046CB6
0x180046c07  mov     ecx, cs:g_fTracingOn
0x180046c0d  inc     esi
0x180046c0f  mov     eax, cs:g_fProviderEnabled
0x180046c15  test    ecx, ecx
0x180046c17  jz      short loc_180046C4E
0x180046c19  test    eax, eax
0x180046c1b  jz      short loc_180046C4E
0x180046c1d  test    cs:g_ulTraceFlags, 800000h
0x180046c28  jz      short loc_180046C4E
0x180046c2a  mov     r9d, [rbx+6Ch]
0x180046c2e  lea     rdx, aHandlereferrel_1; "HandleReferrels successfully chased ref"...
0x180046c35  mov     r8, rbx
0x180046c38  mov     ecx, 800000h
0x180046c3d  call    LDAPClientPrint
0x180046c42  mov     ecx, cs:g_fTracingOn
0x180046c48  mov     eax, cs:g_fProviderEnabled
0x180046c4e  cmp     r15, rdi
0x180046c51  jnz     short loc_180046CAC
0x180046c53  test    ecx, ecx
0x180046c55  jz      short loc_180046CA4
0x180046c57  test    eax, eax
0x180046c59  jz      short loc_180046CA4
0x180046c5b  test    cs:g_ulTraceFlags, 800000h
0x180046c66  jz      short loc_180046C7E
0x180046c68  mov     r8, rbx
0x180046c6b  lea     rdx, aHandlereferral_10; "HandleReferrals unmarking EOM for reque"...
0x180046c72  mov     ecx, 800000h
0x180046c77  call    LDAPClientPrint
0x180046c7c  jmp     short loc_180046CA4
0x180046c7e  test    eax, eax
0x180046c80  jz      short loc_180046CA4
0x180046c82  mov     eax, 1000h
0x180046c87  test    cs:g_ulTraceFlags, rax
0x180046c8e  jz      short loc_180046CA4
0x180046c90  mov     r9, r15
0x180046c93  lea     rdx, aHandlereferral_23; "HandleReferrals unmarking EOM for reque"...
0x180046c9a  mov     r8, rbx
0x180046c9d  mov     ecx, eax
0x180046c9f  call    LDAPClientPrint
0x180046ca4  mov     byte ptr [r15+3Fh], 0
0x180046ca9  xor     r15d, r15d
0x180046cac  mov     rcx, rdi; res
0x180046caf  call    ldap_msgfree
0x180046cb4  jmp     short loc_180046CFE
0x180046cb6  cmp     cs:g_fTracingOn, 0
0x180046cbd  jz      short loc_180046CED
0x180046cbf  cmp     cs:g_fProviderEnabled, 0
0x180046cc6  jz      short loc_180046CED
0x180046cc8  mov     ecx, 800000h
0x180046ccd  test    cs:g_ulTraceFlags, rcx
0x180046cd4  jz      short loc_180046CED
0x180046cd6  mov     r9d, [rbx+6Ch]
0x180046cda  lea     rdx, aHandlereferrel; "HandleReferrels chasing referral for 0x"...
0x180046ce1  mov     r8, rbx
0x180046ce4  mov     [rsp+78h+var_58], eax
0x180046ce8  call    LDAPClientPrint
0x180046ced  test    rbp, rbp
0x180046cf0  jnz     short loc_180046CF7
0x180046cf2  mov     rbp, rdi
0x180046cf5  jmp     short loc_180046CFB
0x180046cf7  mov     [r14+10h], rdi
0x180046cfb  mov     r14, rdi
0x180046cfe  mov     r11, [rsp+78h+arg_0]
0x180046d06  mov     rdi, r12
0x180046d09  test    r12, r12
0x180046d0c  jnz     loc_180046BDE
0x180046d12  mov     r13, [rsp+78h+res]
0x180046d1a  xor     r12d, r12d
0x180046d1d  test    esi, esi
0x180046d1f  jz      loc_180046F10
0x180046d25  mov     esi, r12d
0x180046d28  test    r14, r14
0x180046d2b  jz      short loc_180046D8A
0x180046d2d  lea     rcx, [rbx+30h]; lpCriticalSection
0x180046d31  call    cs:__imp_EnterCriticalSection
0x180046d38  nop     dword ptr [rax+rax+00h]
0x180046d3d  cmp     cs:g_fTracingOn, r12d
0x180046d44  jz      short loc_180046D6E
0x180046d46  cmp     cs:g_fProviderEnabled, r12d
0x180046d4d  jz      short loc_180046D6E
0x180046d4f  mov     eax, 800000h
0x180046d54  test    cs:g_ulTraceFlags, rax
0x180046d5b  jz      short loc_180046D6E
0x180046d5d  mov     r8, rbx
0x180046d60  lea     rdx, aHandlereferral_29; "HandleReferrals putting messages back o"...
0x180046d67  mov     ecx, eax
0x180046d69  call    LDAPClientPrint
0x180046d6e  mov     rax, [rbx+18h]
0x180046d72  lea     rcx, [rbx+30h]; lpCriticalSection
0x180046d76  mov     [r14+10h], rax
0x180046d7a  mov     [rbx+18h], rbp
0x180046d7e  call    cs:__imp_LeaveCriticalSection
0x180046d85  nop     dword ptr [rax+rax+00h]
0x180046d8a  test    r15, r15
0x180046d8d  jz      short loc_180046DF1
0x180046d8f  cmp     cs:g_fTracingOn, r12d
0x180046d96  jz      short loc_180046DED
0x180046d98  cmp     cs:g_fProviderEnabled, r12d
0x180046d9f  jz      short loc_180046DED
0x180046da1  mov     eax, 800000h
0x180046da6  test    cs:g_ulTraceFlags, rax
0x180046dad  jz      short loc_180046DC2
0x180046daf  mov     r8, rbx
0x180046db2  lea     rdx, aHandlereferral_10; "HandleReferrals unmarking EOM for reque"...
0x180046db9  mov     ecx, eax
0x180046dbb  call    LDAPClientPrint
0x180046dc0  jmp     short loc_180046DED
0x180046dc2  cmp     cs:g_fProviderEnabled, r12d
0x180046dc9  jz      short loc_180046DED
0x180046dcb  mov     eax, 1000h
0x180046dd0  test    cs:g_ulTraceFlags, rax
0x180046dd7  jz      short loc_180046DED
0x180046dd9  mov     r9, r15
0x180046ddc  lea     rdx, aHandlereferral_24; "HandleReferrals unmarking EOM for reque"...
0x180046de3  mov     r8, rbx
0x180046de6  mov     ecx, eax
0x180046de8  call    LDAPClientPrint
0x180046ded  mov     [r15+3Fh], r12b
0x180046df1  cmp     byte ptr [rbx+0BCh], 1
0x180046df8  jnz     loc_180046ED7
0x180046dfe  lea     rdi, [rbx+30h]
0x180046e02  mov     rcx, rdi; lpCriticalSection
0x180046e05  call    cs:__imp_EnterCriticalSection
0x180046e0c  nop     dword ptr [rax+rax+00h]
0x180046e11  cmp     byte ptr [rbx+0BCh], 1
0x180046e18  jnz     short loc_180046E99
0x180046e1a  cmp     [rbx+0B6h], r12w
0x180046e22  jbe     short loc_180046E99
0x180046e24  mov     rcx, rbx
0x180046e27  call    ReferenceLdapRequest
0x180046e2c  test    rax, rax
0x180046e2f  jz      short loc_180046E64
0x180046e31  cmp     cs:g_fTracingOn, r12d
0x180046e38  mov     [rax+0BCh], r12b
0x180046e3f  jz      short loc_180046E93
0x180046e41  cmp     cs:g_fProviderEnabled, r12d
0x180046e48  jz      short loc_180046E93
0x180046e4a  mov     ecx, 1000000h
0x180046e4f  test    cs:g_ulTraceFlags, rcx
0x180046e56  jz      short loc_180046E93
0x180046e58  mov     r8, rax
0x180046e5b  lea     rdx, aHandlereferral_21; "HandleReferrals reopening request 0x%x."...
0x180046e62  jmp     short loc_180046E8E
0x180046e64  cmp     cs:g_fTracingOn, r12d
0x180046e6b  jz      short loc_180046E93
0x180046e6d  cmp     cs:g_fProviderEnabled, r12d
0x180046e74  jz      short loc_180046E93
0x180046e76  mov     ecx, 1000000h
0x180046e7b  test    cs:g_ulTraceFlags, rcx
0x180046e82  jz      short loc_180046E93
0x180046e84  mov     r8, rbx
0x180046e87  lea     rdx, aHandlereferral_18; "HandleReferrals failed to reopen reques"...
0x180046e8e  call    LDAPClientPrint
0x180046e93  lea     rdi, [rbx+30h]
0x180046e97  jmp     short loc_180046EC8
0x180046e99  cmp     cs:g_fTracingOn, r12d
0x180046ea0  jz      short loc_180046EC8
0x180046ea2  cmp     cs:g_fProviderEnabled, r12d
0x180046ea9  jz      short loc_180046EC8
0x180046eab  mov     ecx, 1000000h
0x180046eb0  test    cs:g_ulTraceFlags, rcx
0x180046eb7  jz      short loc_180046EC8
0x180046eb9  mov     r8, rbx
0x180046ebc  lea     rdx, aHandlereferral_18; "HandleReferrals failed to reopen reques"...
0x180046ec3  call    LDAPClientPrint
0x180046ec8  mov     rcx, rdi; lpCriticalSection
0x180046ecb  call    cs:__imp_LeaveCriticalSection
0x180046ed2  nop     dword ptr [rax+rax+00h]
0x180046ed7  mov     rcx, r13; res
0x180046eda  call    ldap_msgfree
0x180046edf  mov     rbp, r12
0x180046ee2  jmp     short loc_180046F23
0x180046ee4  test    r8d, r8d
0x180046ee7  jz      short loc_180046F10
0x180046ee9  cmp     cs:g_fProviderEnabled, r12d
0x180046ef0  jz      short loc_180046F10
0x180046ef2  test    cs:g_ulTraceFlags, rsi
0x180046ef9  jz      short loc_180046F10
0x180046efb  mov     r9d, [rbx+6Ch]
0x180046eff  lea     rdx, aHandlereferrel_2; "HandleReferrels no referrals for reques"...
0x180046f06  mov     r8, rbx
0x180046f09  mov     ecx, esi
0x180046f0b  call    LDAPClientPrint
0x180046f10  mov     esi, 52h ; 'R'
0x180046f15  test    r14, r14
0x180046f18  jz      short loc_180046F20
0x180046f1a  mov     [r14+10h], r13
0x180046f1e  jmp     short loc_180046F23
0x180046f20  mov     rbp, r13
0x180046f23  mov     rax, [rsp+78h+arg_8]
0x180046f2b  mov     [rax], rbp
0x180046f2e  mov     eax, esi
0x180046f30  add     rsp, 38h
0x180046f34  pop     r15
0x180046f36  pop     r14
0x180046f38  pop     r13
0x180046f3a  pop     r12
0x180046f3c  pop     rdi
0x180046f3d  pop     rsi
0x180046f3e  pop     rbp
0x180046f3f  pop     rbx
0x180046f40  retn
  ... truncated ...
```
