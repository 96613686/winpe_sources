# CSWbemObjectObjectPath::get_DisplayName(ushort * *)

- ea: `0x18000d3f0`
- end: `0x18000d872`
- name: `?get_DisplayName@CSWbemObjectObjectPath@@UEAAJPEAPEAG@Z`
- size: `1154`
- prototype: `__int64 __fastcall(CSWbemObjectObjectPath *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003170`
- `0x1800050dc`
- `0x180006300`
- `0x18000d2c0`
- `0x18000d3f0`
- `0x18000d878`
- `0x18000d950`
- `0x18000d980`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000d624`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d704`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d624`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d704`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d7a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d7a7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000d4b9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000d4b9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d638`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d857`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d866`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d638`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d857`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000d866`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemObjectObjectPath::get_DisplayName(CSWbemServices **this, unsigned __int16 **a2)
{
  int v4; // ebx
  unsigned __int16 *SecurityString; // r14
  CSWbemServices *v6; // rcx
  __int64 v7; // rsi
  unsigned __int16 *LocaleString; // rbp
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r13
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r15
  __int64 v17; // rdi
  __int64 v18; // rcx
  const wchar_t *v19; // r8
  __int64 v20; // r9
  unsigned __int16 *v21; // rdx
  wchar_t v22; // ax
  unsigned __int16 *v23; // rcx
  BSTR v24; // rdx
  __int64 v25; // rcx
  unsigned __int16 *v26; // rax
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rbx
  unsigned __int16 *i; // r8
  OLECHAR v30; // ax
  unsigned __int16 *v31; // rdx
  __int64 v32; // rcx
  unsigned __int16 *v33; // rax
  unsigned __int64 v34; // rax
  __int64 v35; // rcx
  const wchar_t *v36; // rdx
  unsigned __int64 v37; // r8
  unsigned __int16 *v38; // r9
  wchar_t v39; // ax
  unsigned __int16 *v40; // rcx
  struct CSWbemSecurity *SecurityInfo; // rax
  CSWbemSecurity *v42; // rbx
  __int64 v43; // rax
  const OLECHAR *v44; // rcx
  unsigned __int16 *v45; // rbp
  struct CSWbemPrivilegeSet *PrivilegeSet; // rdi
  BSTR bstrString; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v48; // [rsp+38h] [rbp-40h] BYREF
  enum WbemImpersonationLevelEnum v50; // [rsp+90h] [rbp+18h] BYREF
  enum WbemAuthenticationLevelEnum v51; // [rsp+98h] [rbp+20h] BYREF

  ResetLastErrors();
  if ( !a2 )
  {
    v4 = -2147217400;
    goto LABEL_85;
  }
  v4 = -2147217407;
  bstrString = 0;
  if ( (*((unsigned int (__fastcall **)(CSWbemServices **, BSTR *))*this + 7))(this, &bstrString) )
  {
LABEL_85:
    CDispatchHelp::RaiseException((CDispatchHelp *)(this + 5), v4);
    return (unsigned int)v4;
  }
  SecurityString = 0;
  v6 = this[4];
  v7 = -1;
  if ( v6 )
  {
    SecurityInfo = CSWbemServices::GetSecurityInfo(v6);
    v42 = SecurityInfo;
    if ( SecurityInfo )
    {
      v43 = *((_QWORD *)SecurityInfo + 15);
      if ( v43 )
        v44 = *(const OLECHAR **)(v43 + 296);
      else
        v44 = 0;
      v45 = SysAllocString(v44);
      v48 = v45;
      v51 = wbemAuthenticationLevelDefault;
      v50 = 0;
      if ( (*(int (__fastcall **)(CSWbemSecurity *, enum WbemAuthenticationLevelEnum *))(*(_QWORD *)v42 + 72LL))(
             v42,
             &v51) >= 0
        && (*(int (__fastcall **)(CSWbemSecurity *, enum WbemImpersonationLevelEnum *))(*(_QWORD *)v42 + 56LL))(
             v42,
             &v50) >= 0 )
      {
        PrivilegeSet = CSWbemSecurity::GetPrivilegeSet(v42);
        if ( PrivilegeSet )
        {
          SecurityString = CWbemParseDN::GetSecurityString(
                             1,
                             v51,
                             1,
                             v50,
                             PrivilegeSet,
                             (const unsigned __int16 **)&v48);
          (*(void (__fastcall **)(struct CSWbemPrivilegeSet *))(*(_QWORD *)PrivilegeSet + 16LL))(PrivilegeSet);
        }
      }
      SysFreeString(v45);
      (*(void (__fastcall **)(CSWbemSecurity *))(*(_QWORD *)v42 + 16LL))(v42);
    }
    LocaleString = CWbemParseDN::GetLocaleString(*((unsigned __int16 **)this[4] + 6));
    if ( SecurityString )
    {
      v9 = -1;
      do
        ++v9;
      while ( SecurityString[v9] );
      goto LABEL_6;
    }
  }
  else
  {
    LocaleString = 0;
  }
  v9 = 0;
LABEL_6:
  if ( LocaleString )
  {
    v10 = -1;
    do
      ++v10;
    while ( LocaleString[v10] );
  }
  else
  {
    v10 = 0;
  }
  v11 = -1;
  do
    ++v11;
  while ( bstrString[v11] );
  v12 = v11 + v9 + v10 + 9;
  if ( (SecurityString || LocaleString) && v11 )
    ++v12;
  v13 = v12 + 1;
  v14 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v12 + 1, 2u));
  v15 = v14;
  if ( !v14 )
  {
    v4 = -2147217402;
    goto LABEL_16;
  }
  v17 = 2147483646;
  if ( v12 != -1 )
  {
    if ( v13 > 0x7FFFFFFF )
    {
      *v14 = 0;
    }
    else
    {
      v18 = 2147483646;
      v19 = L"WINMGMTS:";
      v20 = v12 + 1;
      v21 = v14;
      do
      {
        if ( !v18 )
          break;
        v22 = *v19;
        if ( !*v19 )
          break;
        ++v19;
        *v21++ = v22;
        --v18;
        --v20;
      }
      while ( v20 );
      v23 = v21 - 1;
      if ( v20 )
        v23 = v21;
      *v23 = 0;
    }
  }
  if ( SecurityString )
    StringCchCatW(v15, v12 + 1, SecurityString);
  if ( LocaleString )
    StringCchCatW(v15, v12 + 1, LocaleString);
  v24 = bstrString;
  if ( SecurityString || LocaleString )
  {
    do
      ++v7;
    while ( bstrString[v7] );
    if ( v7 && v12 != -1 )
    {
      if ( v13 > 0x7FFFFFFF )
        goto LABEL_56;
      v32 = v12 + 1;
      v33 = v15;
      while ( *v33 )
      {
        ++v33;
        if ( !--v32 )
        {
          v34 = 0;
          goto LABEL_64;
        }
      }
      v34 = v13 - v32;
LABEL_64:
      if ( v32 )
      {
        v35 = 2147483646;
        v36 = L"!";
        v37 = v13 - v34;
        v38 = &v15[v34];
        if ( v13 != v34 )
        {
          do
          {
            if ( !v35 )
              break;
            v39 = *v36;
            if ( !*v36 )
              break;
            ++v36;
            *v38++ = v39;
            --v35;
            --v37;
          }
          while ( v37 );
        }
        v40 = v38 - 1;
        if ( v37 )
          v40 = v38;
        *v40 = 0;
        v25 = v12 + 1;
        v24 = bstrString;
LABEL_43:
        v26 = v15;
        while ( *v26 )
        {
          ++v26;
          if ( !--v25 )
          {
            v27 = 0;
            goto LABEL_48;
          }
        }
        v27 = v13 - v25;
LABEL_48:
        if ( v25 )
        {
          v28 = v13 - v27;
          for ( i = &v15[v27]; v28; --v28 )
          {
            if ( !v17 )
              break;
            v30 = *v24;
            if ( !*v24 )
              break;
            ++v24;
            *i++ = v30;
            --v17;
          }
          v31 = i - 1;
          if ( v28 )
            v31 = i;
          *v31 = 0;
        }
        goto LABEL_56;
      }
    }
  }
  v25 = v12 + 1;
  if ( v12 != -1 && v13 <= 0x7FFFFFFF )
    goto LABEL_43;
LABEL_56:
  v15[v12] = 0;
  *a2 = SysAllocString(v15);
  CWin32DefaultArena::WbemMemFree(v15);
  v4 = 0;
LABEL_16:
  if ( SecurityString )
    CWin32DefaultArena::WbemMemFree(SecurityString);
  if ( LocaleString )
    CWin32DefaultArena::WbemMemFree(LocaleString);
  SysFreeString(bstrString);
  if ( v4 < 0 )
    goto LABEL_85;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d3f0  mov     [rsp+arg_0], rbx
0x18000d3f5  mov     [rsp+arg_8], rdx
0x18000d3fa  push    rbp
0x18000d3fb  push    rsi
0x18000d3fc  push    rdi
0x18000d3fd  push    r12
0x18000d3ff  push    r13
0x18000d401  push    r14
0x18000d403  push    r15
0x18000d405  sub     rsp, 40h
0x18000d409  mov     rbx, rdx
0x18000d40c  mov     r12, rcx
0x18000d40f  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18000d414  test    rbx, rbx
0x18000d417  jz      loc_18000D7F0
0x18000d41d  mov     ebx, 80041001h
0x18000d422  mov     [rsp+78h+bstrString], 0
0x18000d42b  mov     rax, [r12]
0x18000d42f  lea     rdx, [rsp+78h+bstrString]
0x18000d434  mov     rcx, r12
0x18000d437  mov     rax, [rax+38h]
0x18000d43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d440  test    eax, eax
0x18000d442  jnz     loc_18000D7F5
0x18000d448  xor     r14d, r14d
0x18000d44b  mov     rcx, [r12+20h]; this
0x18000d450  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000d457  test    rcx, rcx
0x18000d45a  jnz     loc_18000D6DF
0x18000d460  xor     ebp, ebp
0x18000d462  xor     ecx, ecx
0x18000d464  test    rbp, rbp
0x18000d467  jz      loc_18000D50B
0x18000d46d  mov     rax, rsi
0x18000d470  inc     rax
0x18000d473  cmp     word ptr [rbp+rax*2+0], 0
0x18000d479  jnz     short loc_18000D470
0x18000d47b  mov     r8, [rsp+78h+bstrString]
0x18000d480  mov     rdx, rsi
0x18000d483  inc     rdx
0x18000d486  cmp     word ptr [r8+rdx*2], 0
0x18000d48c  jnz     short loc_18000D483
0x18000d48e  lea     r13, [rax+9]
0x18000d492  add     r13, rcx
0x18000d495  add     r13, rdx
0x18000d498  test    r14, r14
0x18000d49b  jz      short loc_18000D512
0x18000d49d  test    rdx, rdx
0x18000d4a0  jnz     loc_18000D80D
0x18000d4a6  lea     rbx, [r13+1]
0x18000d4aa  mov     eax, 2
0x18000d4af  mul     rbx
0x18000d4b2  cmovb   rax, rsi
0x18000d4b6  mov     rcx, rax
0x18000d4b9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000d4bf  mov     r15, rax
0x18000d4c2  test    rax, rax
0x18000d4c5  jnz     short loc_18000D519
0x18000d4c7  mov     ebx, 80041006h
0x18000d4cc  test    r14, r14
0x18000d4cf  jnz     loc_18000D854
0x18000d4d5  test    rbp, rbp
0x18000d4d8  jnz     loc_18000D863
0x18000d4de  mov     rcx, [rsp+78h+bstrString]; bstrString
0x18000d4e3  call    cs:__imp_SysFreeString
0x18000d4e9  test    ebx, ebx
0x18000d4eb  js      loc_18000D7F5
0x18000d4f1  mov     eax, ebx
0x18000d4f3  mov     rbx, [rsp+78h+arg_0]
0x18000d4fb  add     rsp, 40h
0x18000d4ff  pop     r15
0x18000d501  pop     r14
0x18000d503  pop     r13
0x18000d505  pop     r12
0x18000d507  pop     rdi
0x18000d508  pop     rsi
0x18000d509  pop     rbp
0x18000d50a  retn
0x18000d50b  xor     eax, eax
0x18000d50d  jmp     loc_18000D47B
0x18000d512  test    rbp, rbp
0x18000d515  jz      short loc_18000D4A6
0x18000d517  jmp     short loc_18000D49D
0x18000d519  mov     edi, 7FFFFFFEh
0x18000d51e  test    rbx, rbx
0x18000d521  jz      short loc_18000D572
0x18000d523  cmp     rbx, 7FFFFFFFh
0x18000d52a  ja      loc_18000D815
0x18000d530  mov     ecx, edi
0x18000d532  lea     r8, aWinmgmts_0; "WINMGMTS:"
0x18000d539  mov     r9, rbx
0x18000d53c  mov     rdx, r15
0x18000d53f  nop
0x18000d540  test    rcx, rcx
0x18000d543  jz      short loc_18000D562
0x18000d545  movzx   eax, word ptr [r8]
0x18000d549  test    ax, ax
0x18000d54c  jz      short loc_18000D562
0x18000d54e  add     r8, 2
0x18000d552  mov     [rdx], ax
0x18000d555  add     rdx, 2
0x18000d559  dec     rcx
0x18000d55c  sub     r9, 1
0x18000d560  jnz     short loc_18000D540
0x18000d562  lea     rcx, [rdx-2]
0x18000d566  test    r9, r9
0x18000d569  cmovnz  rcx, rdx
0x18000d56d  xor     eax, eax
0x18000d56f  mov     [rcx], ax
0x18000d572  test    r14, r14
0x18000d575  jnz     loc_18000D820
0x18000d57b  test    rbp, rbp
0x18000d57e  jnz     loc_18000D833
0x18000d584  mov     rdx, [rsp+78h+bstrString]
0x18000d589  test    r14, r14
0x18000d58c  jz      loc_18000D846
0x18000d592  inc     rsi
0x18000d595  cmp     word ptr [rdx+rsi*2], 0
0x18000d59a  jnz     short loc_18000D592
0x18000d59c  test    rsi, rsi
0x18000d59f  jnz     loc_18000D646
0x18000d5a5  mov     rcx, rbx
0x18000d5a8  test    rbx, rbx
0x18000d5ab  jz      short loc_18000D61A
0x18000d5ad  cmp     rbx, 7FFFFFFFh
0x18000d5b4  ja      short loc_18000D61A
0x18000d5b6  mov     rax, r15
0x18000d5b9  nop     dword ptr [rax+00000000h]
0x18000d5c0  cmp     word ptr [rax], 0
0x18000d5c4  jz      short loc_18000D5D4
0x18000d5c6  add     rax, 2
0x18000d5ca  sub     rcx, 1
0x18000d5ce  jnz     short loc_18000D5C0
0x18000d5d0  xor     eax, eax
0x18000d5d2  jmp     short loc_18000D5DA
0x18000d5d4  mov     rax, rbx
0x18000d5d7  sub     rax, rcx
0x18000d5da  test    rcx, rcx
0x18000d5dd  jz      short loc_18000D61A
0x18000d5df  sub     rbx, rax
0x18000d5e2  lea     r8, [r15+rax*2]
0x18000d5e6  jz      short loc_18000D60A
0x18000d5e8  test    rdi, rdi
0x18000d5eb  jz      short loc_18000D60A
0x18000d5ed  movzx   eax, word ptr [rdx]
0x18000d5f0  test    ax, ax
0x18000d5f3  jz      short loc_18000D60A
0x18000d5f5  add     rdx, 2
0x18000d5f9  mov     [r8], ax
0x18000d5fd  add     r8, 2
0x18000d601  dec     rdi
0x18000d604  sub     rbx, 1
0x18000d608  jnz     short loc_18000D5E8
0x18000d60a  lea     rdx, [r8-2]
0x18000d60e  test    rbx, rbx
0x18000d611  cmovnz  rdx, r8
0x18000d615  xor     eax, eax
0x18000d617  mov     [rdx], ax
0x18000d61a  xor     eax, eax
0x18000d61c  mov     [r15+r13*2], ax
0x18000d621  mov     rcx, r15; psz
0x18000d624  call    cs:__imp_SysAllocString
0x18000d62a  mov     rcx, [rsp+78h+arg_8]
0x18000d632  mov     [rcx], rax
0x18000d635  mov     rcx, r15
0x18000d638  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000d63e  nop
0x18000d63f  xor     ebx, ebx
0x18000d641  jmp     loc_18000D4CC
0x18000d646  test    rbx, rbx
0x18000d649  jz      loc_18000D5A5
0x18000d64f  cmp     rbx, 7FFFFFFFh
0x18000d656  ja      short loc_18000D61A
0x18000d658  mov     rcx, rbx
0x18000d65b  mov     rax, r15
0x18000d65e  xchg    ax, ax
0x18000d660  cmp     word ptr [rax], 0
0x18000d664  jz      short loc_18000D674
0x18000d666  add     rax, 2
0x18000d66a  sub     rcx, 1
0x18000d66e  jnz     short loc_18000D660
0x18000d670  xor     eax, eax
0x18000d672  jmp     short loc_18000D67A
0x18000d674  mov     rax, rbx
0x18000d677  sub     rax, rcx
0x18000d67a  test    rcx, rcx
0x18000d67d  jz      loc_18000D5A5
0x18000d683  mov     rcx, rdi
0x18000d686  lea     rdx, asc_18003AEE8; "!"
0x18000d68d  mov     r8, rbx
0x18000d690  sub     r8, rax
0x18000d693  lea     r9, [r15+rax*2]
0x18000d697  jz      short loc_18000D6C2
0x18000d699  nop     dword ptr [rax+00000000h]
0x18000d6a0  test    rcx, rcx
0x18000d6a3  jz      short loc_18000D6C2
0x18000d6a5  movzx   eax, word ptr [rdx]
0x18000d6a8  test    ax, ax
0x18000d6ab  jz      short loc_18000D6C2
0x18000d6ad  add     rdx, 2
0x18000d6b1  mov     [r9], ax
0x18000d6b5  add     r9, 2
0x18000d6b9  dec     rcx
0x18000d6bc  sub     r8, 1
0x18000d6c0  jnz     short loc_18000D6A0
0x18000d6c2  lea     rcx, [r9-2]
0x18000d6c6  test    r8, r8
0x18000d6c9  cmovnz  rcx, r9
0x18000d6cd  xor     eax, eax
0x18000d6cf  mov     [rcx], ax
0x18000d6d2  mov     rcx, rbx
0x18000d6d5  mov     rdx, [rsp+78h+bstrString]
0x18000d6da  jmp     loc_18000D5B6
0x18000d6df  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x18000d6e4  mov     rbx, rax
0x18000d6e7  test    rax, rax
0x18000d6ea  jz      loc_18000D7BC
0x18000d6f0  mov     rax, [rax+78h]
0x18000d6f4  test    rax, rax
0x18000d6f7  jz      loc_18000D806
0x18000d6fd  mov     rcx, [rax+128h]; psz
0x18000d704  call    cs:__imp_SysAllocString
0x18000d70a  mov     rbp, rax
0x18000d70d  mov     [rsp+78h+var_40], rax
0x18000d712  mov     [rsp+78h+arg_18], r14d
0x18000d71a  mov     [rsp+78h+arg_10], r14d
0x18000d722  mov     rax, [rbx]
0x18000d725  lea     rdx, [rsp+78h+arg_18]
0x18000d72d  mov     rcx, rbx
0x18000d730  mov     rax, [rax+48h]
0x18000d734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d739  test    eax, eax
0x18000d73b  js      short loc_18000D7A4
0x18000d73d  mov     rax, [rbx]
0x18000d740  lea     rdx, [rsp+78h+arg_10]
0x18000d748  mov     rcx, rbx
0x18000d74b  mov     rax, [rax+38h]
0x18000d74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d754  test    eax, eax
0x18000d756  js      short loc_18000D7A4
0x18000d758  mov     rcx, rbx; this
0x18000d75b  call    ?GetPrivilegeSet@CSWbemSecurity@@QEAAPEAVCSWbemPrivilegeSet@@XZ; CSWbemSecurity::GetPrivilegeSet(void)
0x18000d760  mov     rdi, rax
0x18000d763  test    rax, rax
0x18000d766  jz      short loc_18000D7A4
0x18000d768  lea     rax, [rsp+78h+var_40]
0x18000d76d  mov     [rsp+78h+var_50], rax; unsigned __int16 **
0x18000d772  mov     [rsp+78h+var_58], rdi; struct CSWbemPrivilegeSet *
0x18000d777  mov     r9d, [rsp+78h+arg_10]; enum WbemImpersonationLevelEnum
0x18000d77f  mov     r8b, 1; bool
0x18000d782  mov     edx, [rsp+78h+arg_18]; enum WbemAuthenticationLevelEnum
0x18000d789  movzx   ecx, r8b; bool
0x18000d78d  call    ?GetSecurityString@CWbemParseDN@@SAPEAG_NW4WbemAuthenticationLevelEnum@@0W4WbemImpersonationLevelEnum@@AEAVCSWbemPrivilegeSet@@AEAPEAG@Z; CWbemParseDN::GetSecurityString(bool,WbemAuthenticationLevelEnum,bool,WbemImpersonationLevelEnum,CSWbemPrivilegeSet &,ushort * &)
0x18000d792  mov     r14, rax
0x18000d795  mov     rax, [rdi]
0x18000d798  mov     rcx, rdi
0x18000d79b  mov     rax, [rax+10h]
0x18000d79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7a4  mov     rcx, rbp; bstrString
0x18000d7a7  call    cs:__imp_SysFreeString
0x18000d7ad  mov     rax, [rbx]
0x18000d7b0  mov     rcx, rbx
0x18000d7b3  mov     rax, [rax+10h]
0x18000d7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7bc  mov     rcx, [r12+20h]
0x18000d7c1  mov     rcx, [rcx+30h]; unsigned __int16 *
0x18000d7c5  call    ?GetLocaleString@CWbemParseDN@@SAPEAGPEAG@Z; CWbemParseDN::GetLocaleString(ushort *)
0x18000d7ca  mov     rbp, rax
0x18000d7cd  test    r14, r14
0x18000d7d0  jz      loc_18000D462
0x18000d7d6  mov     rcx, rsi
0x18000d7d9  nop     dword ptr [rax+00000000h]
0x18000d7e0  inc     rcx
0x18000d7e3  cmp     word ptr [r14+rcx*2], 0
0x18000d7e9  jnz     short loc_18000D7E0
0x18000d7eb  jmp     loc_18000D464
0x18000d7f0  mov     ebx, 80041008h
0x18000d7f5  lea     rcx, [r12+28h]; this
0x18000d7fa  mov     edx, ebx; int
0x18000d7fc  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18000d801  jmp     loc_18000D4F1
0x18000d806  xor     ecx, ecx
0x18000d808  jmp     loc_18000D704
0x18000d80d  inc     r13
0x18000d810  jmp     loc_18000D4A6
0x18000d815  xor     eax, eax
0x18000d817  mov     [r15], ax
0x18000d81b  jmp     loc_18000D572
0x18000d820  mov     r8, r14; unsigned __int16 *
0x18000d823  mov     rdx, rbx; unsigned __int64
0x18000d826  mov     rcx, r15; unsigned __int16 *
0x18000d829  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d82e  jmp     loc_18000D57B
0x18000d833  mov     r8, rbp; unsigned __int16 *
0x18000d836  mov     rdx, rbx; unsigned __int64
0x18000d839  mov     rcx, r15; unsigned __int16 *
0x18000d83c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d841  jmp     loc_18000D584
0x18000d846  test    rbp, rbp
0x18000d849  jz      loc_18000D5A5
  ... truncated ...
```
