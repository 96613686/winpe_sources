# DAV_AUTH_RULES_ENTRY::MatchRule(IHttpUser *,AUTH_ACCOUNT_SID *,ushort const *,ulong,int *)

- ea: `0x1800021c4`
- end: `0x1800025dd`
- name: `?MatchRule@DAV_AUTH_RULES_ENTRY@@QEAAJPEAVIHttpUser@@PEAVAUTH_ACCOUNT_SID@@PEBGKPEAH@Z`
- size: `1049`
- prototype: `__int64 __fastcall(DAV_AUTH_RULES_ENTRY *this, struct IHttpUser *, struct AUTH_ACCOUNT_SID *, wchar_t *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006310`

## callees

- `0x1800021c4`
- `0x180019560`
- `0x180019694`
- `0x18001aa5c`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800023d5`
- `msvcrt!_wcsicmp` at `0x1800023d5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800023aa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800023aa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180002469`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180002469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002479`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002383`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002449`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002383`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002449`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002362`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002429`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002362`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002429`
- `iisutil!PuDbgPrintError` at `0x180002313`
- `iisutil!PuDbgPrintError` at `0x1800024d0`
- `iisutil!PuDbgPrintError` at `0x1800025a2`
- `iisutil!PuDbgPrintError` at `0x180002313`
- `iisutil!PuDbgPrintError` at `0x1800024d0`
- `iisutil!PuDbgPrintError` at `0x1800025a2`

## string_xrefs

- `0x1800022e5`: `GetSidFromToken(user=%ws,token=%p) failed\n`
- `0x1800024bb`: `CheckTokenMembership(user=%ws, role=%ws) failed\n`

## pseudocode

```c
__int64 __fastcall DAV_AUTH_RULES_ENTRY::MatchRule(
        DAV_AUTH_RULES_ENTRY *this,
        struct IHttpUser *a2,
        struct AUTH_ACCOUNT_SID *a3,
        wchar_t *a4,
        unsigned int a5,
        int *a6)
{
  int *v6; // r15
  __int64 v8; // rax
  const wchar_t *v12; // r13
  int v13; // r12d
  void *v14; // rbp
  struct IHttpServer *v15; // rbx
  int SidFromToken; // esi
  unsigned int v18; // r14d
  __int64 v19; // r12
  PSID *v20; // rbp
  int v21; // r14d
  __int64 v22; // r14
  PSID *v23; // rbp
  int v24; // r12d
  signed int LastError; // eax
  unsigned int v26; // edi
  int v27; // [rsp+40h] [rbp-48h]
  HANDLE TokenHandle; // [rsp+48h] [rbp-40h]
  WINBOOL IsMember; // [rsp+90h] [rbp+8h] BYREF
  struct IHttpUser *v30; // [rsp+98h] [rbp+10h]
  struct AUTH_ACCOUNT_SID *v31; // [rsp+A0h] [rbp+18h]

  v31 = a3;
  v30 = a2;
  v6 = a6;
  IsMember = 0;
  v8 = *(_QWORD *)a2;
  *a6 = 0;
  v12 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpUser *))(v8 + 8))(a2);
  if ( *((_DWORD *)this + 28) && !xMatchPathInUrl(a4, a5, *((const unsigned __int16 **)this + 12)) )
    return 0;
  if ( *((_DWORD *)this + 32) || *((_DWORD *)this + 31) && !*v12 )
  {
    *v6 = 1;
    return 0;
  }
  v13 = (*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a2 + 64LL))(a2);
  v27 = v13;
  v14 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a2 + 32LL))(a2);
  TokenHandle = v14;
  if ( !v13 && (!v14 || !*v12) )
    return 0;
  v15 = g_pGlobalInfo;
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
  if ( !v13 && (*((_DWORD *)this + 4) || *((_DWORD *)this + 8)) && !*((_QWORD *)a3 + 6) )
  {
    SidFromToken = AUTH_ACCOUNT_SID::GetSidFromToken(a3, v14);
    if ( SidFromToken < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\auth_rules.cxx",
          390,
          "DAV_AUTH_RULES_ENTRY::MatchRule",
          SidFromToken,
          "GetSidFromToken(user=%ws,token=%p) failed\n",
          v12,
          v14);
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v15 + 32LL))(v15);
      return (unsigned int)SidFromToken;
    }
  }
  v18 = 0;
  v19 = *((_QWORD *)this + 1);
  v20 = (PSID *)*((_QWORD *)this + 5);
  for ( LODWORD(a6) = 0; v18 < *((_DWORD *)this + 4); LODWORD(a6) = v18 )
  {
    if ( v27 )
    {
      if ( !_wcsicmp(v12, *(const wchar_t **)(v19 + 32)) )
        goto LABEL_25;
    }
    else
    {
      if ( !v20[6] )
      {
        v21 = 0;
        CReaderWriterLock3::WriteLock((DAV_AUTH_RULES_ENTRY *)((char *)this + 56));
        if ( !v20[6] )
          v21 = AUTH_ACCOUNT_SID::LookupSidFromName((AUTH_ACCOUNT_SID *)v20, *(const unsigned __int16 **)(v19 + 32));
        CReaderWriterLock3::WriteUnlock((DAV_AUTH_RULES_ENTRY *)((char *)this + 56));
        if ( v21 < 0 )
        {
          (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v15 + 32LL))(v15);
          return (unsigned int)v21;
        }
        v18 = (unsigned int)a6;
      }
      if ( EqualSid(*((PSID *)v31 + 6), v20[6]) )
      {
LABEL_25:
        *v6 = 1;
        goto LABEL_26;
      }
    }
    ++v18;
    v19 += 56;
    v20 += 7;
  }
  v22 = *((_QWORD *)this + 3);
  v23 = (PSID *)*((_QWORD *)this + 6);
  LODWORD(a6) = 0;
  if ( !*((_DWORD *)this + 8) )
  {
LABEL_26:
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v15 + 32LL))(v15);
    return 0;
  }
  while ( v27 )
  {
    v24 = (*(__int64 (__fastcall **)(struct IHttpUser *, _QWORD, WINBOOL *))(*(_QWORD *)v30 + 72LL))(
            v30,
            *(_QWORD *)(v22 + 32),
            &IsMember);
    if ( v24 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\auth_rules.cxx",
          524,
          "DAV_AUTH_RULES_ENTRY::MatchRule",
          v24,
          "IsInRole(user=%ws, role=%ws) failed\n",
          v12,
          *(_QWORD *)(v22 + 32));
LABEL_48:
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v15 + 32LL))(v15);
      return (unsigned int)v24;
    }
LABEL_43:
    if ( IsMember )
      goto LABEL_25;
    v22 += 56;
    v23 += 7;
    LODWORD(a6) = (_DWORD)a6 + 1;
    if ( (unsigned int)a6 >= *((_DWORD *)this + 8) )
      goto LABEL_26;
  }
  if ( !v23[6] )
  {
    v24 = 0;
    CReaderWriterLock3::WriteLock((DAV_AUTH_RULES_ENTRY *)((char *)this + 56));
    if ( !v23[6] )
      v24 = AUTH_ACCOUNT_SID::LookupSidFromName((AUTH_ACCOUNT_SID *)v23, *(const unsigned __int16 **)(v22 + 32));
    CReaderWriterLock3::WriteUnlock((DAV_AUTH_RULES_ENTRY *)((char *)this + 56));
    if ( v24 < 0 )
      goto LABEL_48;
  }
  if ( CheckTokenMembership(TokenHandle, v23[6], &IsMember) )
    goto LABEL_43;
  LastError = GetLastError();
  v26 = LastError;
  if ( LastError > 0 )
    v26 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\auth_rules.cxx",
      497,
      "DAV_AUTH_RULES_ENTRY::MatchRule",
      v26,
      "CheckTokenMembership(user=%ws, role=%ws) failed\n",
      v12,
      *(_QWORD *)(v22 + 32));
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v15 + 32LL))(v15);
  return v26;
}

```

## disassembly

```asm
0x1800021c4  mov     rax, rsp
0x1800021c7  mov     [rax+20h], rbx
0x1800021cb  mov     [rax+18h], r8
0x1800021cf  mov     [rax+10h], rdx
0x1800021d3  push    rbp
0x1800021d4  push    rsi
0x1800021d5  push    rdi
0x1800021d6  push    r12
0x1800021d8  push    r13
0x1800021da  push    r14
0x1800021dc  push    r15
0x1800021de  sub     rsp, 50h
0x1800021e2  mov     r15, [rsp+88h+arg_28]
0x1800021ea  xor     ebp, ebp
0x1800021ec  mov     [rax+8], ebp
0x1800021ef  mov     rdi, rcx
0x1800021f2  mov     rax, [rdx]
0x1800021f5  mov     rcx, rdx
0x1800021f8  mov     rbx, r9
0x1800021fb  mov     rsi, r8
0x1800021fe  mov     r14, rdx
0x180002201  mov     [r15], ebp
0x180002204  mov     rax, [rax+8]
0x180002208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220d  mov     r13, rax
0x180002210  cmp     [rdi+70h], ebp
0x180002213  jbe     short loc_180002231
0x180002215  mov     r8, [rdi+60h]; unsigned __int16 *
0x180002219  mov     rcx, rbx; String1
0x18000221c  mov     edx, [rsp+88h+arg_20]; unsigned int
0x180002223  call    ?xMatchPathInUrl@@YAPEBGPEBGK0@Z; xMatchPathInUrl(ushort const *,ulong,ushort const *)
0x180002228  test    rax, rax
0x18000222b  jz      loc_1800025C3
0x180002231  cmp     [rdi+80h], ebp
0x180002237  jnz     loc_1800025BC
0x18000223d  cmp     [rdi+7Ch], ebp
0x180002240  jz      short loc_18000224D
0x180002242  cmp     [r13+0], bp
0x180002247  jz      loc_1800025BC
0x18000224d  mov     rax, [r14]
0x180002250  mov     rcx, r14
0x180002253  mov     rax, [rax+40h]
0x180002257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225c  mov     rcx, [r14]
0x18000225f  mov     r12d, eax
0x180002262  mov     [rsp+88h+var_48], eax
0x180002266  mov     rax, [rcx+20h]
0x18000226a  mov     rcx, r14
0x18000226d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002272  mov     rbp, rax
0x180002275  mov     [rsp+88h+TokenHandle], rax
0x18000227a  xor     eax, eax
0x18000227c  test    r12d, r12d
0x18000227f  jnz     short loc_180002295
0x180002281  test    rbp, rbp
0x180002284  jz      loc_1800025C3
0x18000228a  cmp     [r13+0], ax
0x18000228f  jz      loc_1800025C3
0x180002295  mov     rbx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000229c  mov     rcx, rbx
0x18000229f  mov     rax, [rbx]
0x1800022a2  mov     rax, [rax+18h]
0x1800022a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ab  xor     ecx, ecx
0x1800022ad  test    r12d, r12d
0x1800022b0  jnz     short loc_18000232F
0x1800022b2  cmp     [rdi+10h], ecx
0x1800022b5  ja      short loc_1800022BC
0x1800022b7  cmp     [rdi+20h], ecx
0x1800022ba  jbe     short loc_18000232F
0x1800022bc  cmp     [rsi+30h], rcx
0x1800022c0  jnz     short loc_18000232F
0x1800022c2  mov     rdx, rbp; void *
0x1800022c5  mov     rcx, rsi; this
0x1800022c8  call    ?GetSidFromToken@AUTH_ACCOUNT_SID@@QEAAJPEAX@Z; AUTH_ACCOUNT_SID::GetSidFromToken(void *)
0x1800022cd  xor     ecx, ecx
0x1800022cf  mov     esi, eax
0x1800022d1  test    eax, eax
0x1800022d3  jns     short loc_18000232F
0x1800022d5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800022dc  jz      short loc_180002319
0x1800022de  mov     rcx, cs:g_pDebug
0x1800022e5  lea     rax, aGetsidfromtoke; "GetSidFromToken(user=%ws,token=%p) fail"...
0x1800022ec  mov     [rsp+88h+var_50], rbp
0x1800022f1  lea     r9, aDavAuthRulesEn; "DAV_AUTH_RULES_ENTRY::MatchRule"
0x1800022f8  mov     [rsp+88h+var_58], r13
0x1800022fd  lea     rdx, aInetsrvIisIisr_1; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x180002304  mov     [rsp+88h+var_60], rax
0x180002309  mov     r8d, 186h
0x18000230f  mov     [rsp+88h+var_68], esi
0x180002313  call    cs:__imp_PuDbgPrintError
0x180002319  mov     rax, [rbx]
0x18000231c  mov     rcx, rbx
0x18000231f  mov     rax, [rax+20h]
0x180002323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002328  mov     eax, esi
0x18000232a  jmp     loc_1800025C5
0x18000232f  mov     r14d, ecx
0x180002332  mov     r12, [rdi+8]
0x180002336  mov     esi, 1
0x18000233b  mov     rbp, [rdi+28h]
0x18000233f  mov     dword ptr [rsp+88h+arg_28], ecx
0x180002346  cmp     [rdi+10h], ecx
0x180002349  jbe     loc_1800023FE
0x18000234f  cmp     [rsp+88h+var_48], ecx
0x180002353  jnz     short loc_1800023CD
0x180002355  cmp     [rbp+30h], rcx
0x180002359  jnz     short loc_18000239A
0x18000235b  mov     r14d, ecx
0x18000235e  lea     rcx, [rdi+38h]
0x180002362  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180002368  cmp     qword ptr [rbp+30h], 0
0x18000236d  jnz     short loc_18000237F
0x18000236f  mov     rdx, [r12+20h]; unsigned __int16 *
0x180002374  mov     rcx, rbp; this
0x180002377  call    ?LookupSidFromName@AUTH_ACCOUNT_SID@@QEAAJPEBG@Z; AUTH_ACCOUNT_SID::LookupSidFromName(ushort const *)
0x18000237c  mov     r14d, eax
0x18000237f  lea     rcx, [rdi+38h]
0x180002383  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002389  test    r14d, r14d
0x18000238c  js      loc_1800024EC
0x180002392  mov     r14d, dword ptr [rsp+88h+arg_28]
0x18000239a  mov     rax, [rsp+88h+arg_10]
0x1800023a2  mov     rdx, [rbp+30h]; pSid2
0x1800023a6  mov     rcx, [rax+30h]; pSid1
0x1800023aa  call    cs:__imp_EqualSid
0x1800023b0  xor     ecx, ecx
0x1800023b2  test    eax, eax
0x1800023b4  jz      short loc_1800023E1
0x1800023b6  mov     [r15], esi
0x1800023b9  mov     rax, [rbx]
0x1800023bc  mov     rcx, rbx
0x1800023bf  mov     rax, [rax+20h]
0x1800023c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c8  jmp     loc_1800025C3
0x1800023cd  mov     rdx, [r12+20h]; String2
0x1800023d2  mov     rcx, r13; String1
0x1800023d5  call    cs:__imp__wcsicmp
0x1800023db  xor     ecx, ecx
0x1800023dd  test    eax, eax
0x1800023df  jz      short loc_1800023B6
0x1800023e1  add     r14d, esi
0x1800023e4  add     r12, 38h ; '8'
0x1800023e8  add     rbp, 38h ; '8'
0x1800023ec  mov     dword ptr [rsp+88h+arg_28], r14d
0x1800023f4  cmp     r14d, [rdi+10h]
0x1800023f8  jb      loc_18000234F
0x1800023fe  mov     r14, [rdi+18h]
0x180002402  mov     rbp, [rdi+30h]
0x180002406  mov     dword ptr [rsp+88h+arg_28], ecx
0x18000240d  cmp     [rdi+20h], ecx
0x180002410  jbe     short loc_1800023B9
0x180002412  cmp     [rsp+88h+var_48], ecx
0x180002416  jnz     loc_180002503
0x18000241c  cmp     [rbp+30h], rcx
0x180002420  jnz     short loc_180002458
0x180002422  mov     r12d, ecx
0x180002425  lea     rcx, [rdi+38h]
0x180002429  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000242f  cmp     qword ptr [rbp+30h], 0
0x180002434  jnz     short loc_180002445
0x180002436  mov     rdx, [r14+20h]; unsigned __int16 *
0x18000243a  mov     rcx, rbp; this
0x18000243d  call    ?LookupSidFromName@AUTH_ACCOUNT_SID@@QEAAJPEBG@Z; AUTH_ACCOUNT_SID::LookupSidFromName(ushort const *)
0x180002442  mov     r12d, eax
0x180002445  lea     rcx, [rdi+38h]
0x180002449  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000244f  test    r12d, r12d
0x180002452  js      loc_1800025A8
0x180002458  mov     rdx, [rbp+30h]; SidToCheck
0x18000245c  lea     r8, [rsp+88h+IsMember]; IsMember
0x180002464  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x180002469  call    cs:__imp_CheckTokenMembership
0x18000246f  xor     ecx, ecx
0x180002471  test    eax, eax
0x180002473  jnz     loc_18000252C
0x180002479  call    cs:__imp_GetLastError
0x18000247f  mov     edi, eax
0x180002481  test    eax, eax
0x180002483  jle     short loc_18000248E
0x180002485  movzx   edi, ax
0x180002488  or      edi, 80070000h
0x18000248e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002495  jz      short loc_1800024D6
0x180002497  mov     rax, [r14+20h]
0x18000249b  lea     r9, aDavAuthRulesEn; "DAV_AUTH_RULES_ENTRY::MatchRule"
0x1800024a2  mov     rcx, cs:g_pDebug
0x1800024a9  lea     rdx, aInetsrvIisIisr_1; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x1800024b0  mov     [rsp+88h+var_50], rax
0x1800024b5  mov     r8d, 1F1h
0x1800024bb  lea     rax, aChecktokenmemb; "CheckTokenMembership(user=%ws, role=%ws"...
0x1800024c2  mov     [rsp+88h+var_58], r13
0x1800024c7  mov     [rsp+88h+var_60], rax
0x1800024cc  mov     [rsp+88h+var_68], edi
0x1800024d0  call    cs:__imp_PuDbgPrintError
0x1800024d6  mov     rcx, [rbx]
0x1800024d9  mov     rax, [rcx+20h]
0x1800024dd  mov     rcx, rbx
0x1800024e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e5  mov     eax, edi
0x1800024e7  jmp     loc_1800025C5
0x1800024ec  mov     rax, [rbx]
0x1800024ef  mov     rcx, rbx
0x1800024f2  mov     rax, [rax+20h]
0x1800024f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024fb  mov     eax, r14d
0x1800024fe  jmp     loc_1800025C5
0x180002503  mov     rcx, [rsp+88h+arg_8]
0x18000250b  lea     r8, [rsp+88h+IsMember]
0x180002513  mov     rdx, [r14+20h]
0x180002517  mov     rax, [rcx]
0x18000251a  mov     rax, [rax+48h]
0x18000251e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002523  xor     ecx, ecx
0x180002525  mov     r12d, eax
0x180002528  test    eax, eax
0x18000252a  js      short loc_18000255F
0x18000252c  cmp     [rsp+88h+IsMember], ecx
0x180002533  jnz     loc_1800023B6
0x180002539  mov     eax, dword ptr [rsp+88h+arg_28]
0x180002540  add     r14, 38h ; '8'
0x180002544  add     eax, esi
0x180002546  add     rbp, 38h ; '8'
0x18000254a  mov     dword ptr [rsp+88h+arg_28], eax
0x180002551  cmp     eax, [rdi+20h]
0x180002554  jb      loc_180002412
0x18000255a  jmp     loc_1800023B9
0x18000255f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002566  jz      short loc_1800025A8
0x180002568  mov     rax, [r14+20h]
0x18000256c  lea     r9, aDavAuthRulesEn; "DAV_AUTH_RULES_ENTRY::MatchRule"
0x180002573  mov     rcx, cs:g_pDebug
0x18000257a  lea     rdx, aInetsrvIisIisr_1; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x180002581  mov     [rsp+88h+var_50], rax
0x180002586  mov     r8d, 20Ch
0x18000258c  lea     rax, aIsinroleUserWs; "IsInRole(user=%ws, role=%ws) failed\n"
0x180002593  mov     [rsp+88h+var_58], r13
0x180002598  mov     [rsp+88h+var_60], rax
0x18000259d  mov     [rsp+88h+var_68], r12d
0x1800025a2  call    cs:__imp_PuDbgPrintError
0x1800025a8  mov     rax, [rbx]
0x1800025ab  mov     rcx, rbx
0x1800025ae  mov     rax, [rax+20h]
0x1800025b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b7  mov     eax, r12d
0x1800025ba  jmp     short loc_1800025C5
0x1800025bc  mov     dword ptr [r15], 1
0x1800025c3  xor     eax, eax
0x1800025c5  mov     rbx, [rsp+88h+arg_18]
0x1800025cd  add     rsp, 50h
0x1800025d1  pop     r15
0x1800025d3  pop     r14
0x1800025d5  pop     r13
0x1800025d7  pop     r12
0x1800025d9  pop     rdi
0x1800025da  pop     rsi
0x1800025db  pop     rbp
0x1800025dc  retn
```
