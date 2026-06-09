# HandleReferral(ldap_connection *,ldapmsg *,ldap_request *,ulong)

- ea: `0x180046038`
- end: `0x180046a9f`
- name: `?HandleReferral@@YAKPEAUldap_connection@@PEAUldapmsg@@PEAUldap_request@@K@Z`
- size: `2663`
- prototype: `unsigned int __fastcall(struct ldap_connection *, struct ldapmsg *, struct ldap_request *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180046aa8`

## callees

- `0x180001790`
- `0x1800022c0`
- `0x1800030f0`
- `0x1800037a8`
- `0x180003840`
- `0x18000b440`
- `0x180020910`
- `0x180020970`
- `0x180029750`
- `0x18002e6d4`
- `0x180046038`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004606a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004651f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800469b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004606a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004651f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800469b5`

## string_xrefs

- `0x180046a93`: `HandleReferral error 0x%x while reading referral 0x%x\n`

## pseudocode

```c
__int64 __fastcall HandleReferral(
        struct ldap_connection *a1,
        struct ldapmsg *a2,
        struct ldap_request *a3,
        unsigned int a4)
{
  PCNZWCH v5; // r15
  unsigned int v8; // ebx
  ULONGLONG TickCount64; // rax
  CLdapBer *lm_ber; // rbp
  char v12; // al
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // r8
  const WCHAR *v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // eax
  WCHAR v29; // ax
  unsigned __int8 v30; // r8
  unsigned __int16 *v31; // r10
  unsigned __int16 *v32; // r9
  __int64 v33; // rcx
  unsigned __int64 v34; // rax
  WCHAR v35; // cx
  unsigned __int16 v36; // dx
  WCHAR v37; // ax
  const char *v38; // r8
  char v39; // al
  unsigned __int8 v40; // r14
  unsigned int v41; // eax
  unsigned int Sequence; // eax
  unsigned int ValueWithAlloc; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  unsigned int v46; // eax
  __int64 v47; // r8
  int v48; // edx
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // r8
  unsigned int v52; // eax
  __int64 v53; // r8
  int v54; // r11d
  __int64 v55; // rdx
  int v56; // eax
  unsigned __int8 v57; // r8
  unsigned __int16 *v58; // rdi
  unsigned __int16 *v59; // r10
  unsigned __int16 *v60; // r9
  unsigned __int16 v61; // ax
  unsigned __int16 v62; // cx
  unsigned __int16 v63; // dx
  ULONGLONG v64; // rdi
  ULONGLONG v65; // rax
  ULONGLONG v66; // [rsp+40h] [rbp-48h]
  PCNZWCH lpString1; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v68; // [rsp+A8h] [rbp+20h]

  v68 = a4;
  v5 = 0;
  lpString1 = 0;
  v8 = 82;
  TickCount64 = GetTickCount64();
  lm_ber = (CLdapBer *)a2->lm_ber;
  v66 = TickCount64;
  if ( !lm_ber )
  {
    if ( !g_fTracingOn )
      return v8;
    if ( g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral no ber to decode for 0x%x\n", a3);
    goto LABEL_6;
  }
  if ( a2->lm_msgtype == 115 )
  {
LABEL_123:
    v39 = *((_BYTE *)a3 + 185);
    if ( a2->lm_msgtype == 115 )
    {
      if ( (v39 & 0x20) == 0 )
        goto LABEL_15;
      v40 = 1;
    }
    else
    {
      if ( (v39 & 0x40) == 0 )
        goto LABEL_20;
      v40 = 0;
    }
    CLdapBer::Reset(lm_ber, 0);
    v13 = LdapInitialDecodeMessage(a1, a2);
    v8 = v13;
    if ( v13 )
      goto LABEL_25;
    if ( a2->lm_msgtype == 115 )
      goto LABEL_141;
    v14 = CLdapBer::HrSkipElement(lm_ber);
    v8 = v14;
    if ( v14 )
      goto LABEL_30;
    v41 = CLdapBer::HrSkipElement(lm_ber);
    v8 = v41;
    if ( v41 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(0x800000, "HandleReferral error 0x%x while skipping errmsg for 0x%x\n", v41, a3);
      goto LABEL_102;
    }
    Sequence = CLdapBer::HrStartReadSequence(lm_ber, 0xA3u, 0);
    v8 = Sequence;
    if ( Sequence )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(0x800000, "HandleReferral error 0x%x while parsing referral 0x%x\n", Sequence, a3);
      goto LABEL_102;
    }
    while ( 1 )
    {
LABEL_141:
      if ( v5 )
      {
        ldapFree(v5, 1818318412);
        lpString1 = 0;
      }
      ValueWithAlloc = CLdapBer::HrGetValueWithAlloc(lm_ber, (unsigned __int16 **)&lpString1, 0);
      v5 = lpString1;
      if ( ValueWithAlloc || !lpString1 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
          LDAPClientPrint(0x800000, "HandleReferral error 0x%x while reading referral 0x%x\n", ValueWithAlloc, a3);
        goto LABEL_100;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(0x800000, "HandleReferral chasing '%S' for request 0x%x\n", lpString1, (_DWORD)a3);
      v46 = strlenW(v5, v44, v45);
      v48 = 7;
      v49 = v46 <= 7 ? strlenW(v5, 7, v47) : 7;
      if ( ldapWStringsIdentical(v5, v49, L"ldap://", v48) )
        break;
      v52 = strlenW(v5, v50, v51);
      v55 = (unsigned int)(v54 + 8);
      if ( v52 <= (unsigned int)v55 )
        v56 = strlenW(v5, v55, v53);
      else
        v56 = v54 + 8;
      if ( ldapWStringsIdentical(v5, v56, L"ldaps://", v55) )
      {
        v57 = 1;
        v58 = (unsigned __int16 *)(v5 + 8);
LABEL_159:
        v59 = v58;
        v60 = 0;
        while ( 1 )
        {
          v61 = *v58;
          if ( *v58 == 47 || v61 == 58 || !v61 )
            break;
          ++v58;
        }
        if ( *v58 != 58 )
          goto LABEL_198;
        *v58++ = 0;
        v62 = *v58;
        if ( !*v58 )
          goto LABEL_198;
        v63 = 0;
        do
        {
          if ( v62 == 92 || v62 == 47 )
            break;
          if ( (unsigned __int16)(v62 - 48) <= 9u )
            v63 = v62 + 10 * v63 - 48;
          v62 = *++v58;
        }
        while ( *v58 );
        if ( !v63 )
        {
LABEL_198:
          if ( v57 || (v63 = 389, *(_BYTE *)(*((_QWORD *)a3 + 4) + 646LL)) )
            v63 = 636;
        }
        if ( *v58 == 47 || *v58 == 92 )
        {
          *v58 = 0;
          if ( v58[1] )
            v60 = v58 + 1;
        }
        v8 = LdapChaseReferral(a3, a2, v59, v60, v63, v40, v57);
        if ( !v8 )
        {
LABEL_191:
          v8 = 0;
          goto LABEL_102;
        }
        v64 = v68;
        if ( v68 - 1 <= 0xFFFFFFFD )
        {
          v65 = GetTickCount64();
          if ( v65 - v66 >= v64 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
            {
              v38 = "HandleReferral:977";
LABEL_112:
              LDAPClientPrint(0x800000, "%s Timeout exceeded while chasing referrals request:0x%p\n", v38, a3);
            }
LABEL_113:
            v8 = 85;
            goto LABEL_102;
          }
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
            LDAPClientPrint(
              0x800000,
              "%s Remaining timeout after LdapChaseReferral request:0x%p ulTimeoutRemaining:%lu\n",
              "HandleReferral:970",
              a3,
              v64 - (v65 - v66));
        }
      }
    }
    v57 = 0;
    v58 = (unsigned __int16 *)(v5 + 7);
    goto LABEL_159;
  }
  if ( a2->lm_returncode != 9 )
  {
    if ( a2->lm_returncode != 10 )
      goto LABEL_6;
    goto LABEL_123;
  }
  v12 = *((_BYTE *)a3 + 185);
  if ( !*((_BYTE *)a3 + 272) )
  {
    if ( (v12 & 0x40) != 0 )
      goto LABEL_24;
LABEL_20:
    if ( !g_fTracingOn )
      return v8;
    if ( g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral not handling external for 0x%x\n", a3);
    goto LABEL_6;
  }
  if ( (v12 & 0x20) == 0 )
  {
LABEL_15:
    if ( !g_fTracingOn )
      return v8;
    if ( g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral not handling subordinate for 0x%x\n", a3);
    goto LABEL_6;
  }
LABEL_24:
  CLdapBer::Reset(lm_ber, 0);
  v13 = LdapInitialDecodeMessage(a1, a2);
  v8 = v13;
  if ( v13 )
  {
LABEL_25:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral error 0x%x while decoding referral for 0x%x\n", v13, a3);
    goto LABEL_102;
  }
  v14 = CLdapBer::HrSkipElement(lm_ber);
  v8 = v14;
  if ( v14 )
  {
LABEL_30:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral error 0x%x while skipping matchedDN for 0x%x\n", v14, a3);
    goto LABEL_102;
  }
  v15 = CLdapBer::HrGetValueWithAlloc(lm_ber, (unsigned __int16 **)&lpString1, 0);
  v5 = lpString1;
  v8 = v15;
  if ( !v15 && lpString1 )
  {
    if ( (unsigned int)strlenW(lpString1, v16, v17) >= 9
      && ldapWStringsIdentical(v5, 9, L"Referral:", 9)
      && (v20 = v5 + 10, v5[9]) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(0x800000, "HandleReferral chasing '%S' for request 0x%x\n", v5 + 10, (_DWORD)a3);
      if ( v5 != (PCNZWCH)-20LL )
      {
        while ( 1 )
        {
          if ( !*v20 )
            goto LABEL_100;
          if ( (unsigned int)strlenW(v20, v18, v19) <= 7 )
            v23 = strlenW(v20, v21, v22);
          else
            v23 = 7;
          if ( ldapWStringsIdentical(v20, v23, L"ldap://", 7) )
          {
            v30 = 0;
            v20 += 7;
          }
          else
          {
            if ( (unsigned int)strlenW(v20, v24, v25) <= 8 )
              v28 = strlenW(v20, v26, v27);
            else
              v28 = 8;
            if ( !ldapWStringsIdentical(v20, v28, L"ldaps://", 8) )
            {
              v29 = *v20;
              if ( *v20 == 10 )
                goto LABEL_57;
              do
              {
                if ( !v29 )
                  break;
                v29 = *++v20;
              }
              while ( *v20 != 10 );
              if ( *v20 == 10 )
LABEL_57:
                ++v20;
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
                LDAPClientPrint(0x800000, "HandleReferral non ldap referral skipped for 0x%x\n", (_DWORD)a3);
              goto LABEL_99;
            }
            v30 = 1;
            v20 += 8;
          }
          v31 = (unsigned __int16 *)v20;
          v32 = 0;
          while ( 1 )
          {
            v34 = *v20;
            if ( (_WORD)v34 == 47 )
              break;
            if ( (_WORD)v34 == 92 )
              break;
            if ( (unsigned __int16)v34 <= 0x3Au )
            {
              v33 = 0x400000000000401LL;
              if ( _bittest64(&v33, v34) )
                break;
            }
            ++v20;
          }
          if ( *v20 != 58 )
            goto LABEL_199;
          *v20++ = 0;
          v35 = *v20;
          if ( !*v20 )
            goto LABEL_199;
          v36 = 0;
          do
          {
            if ( v35 == 47 || v35 == 92 || v35 == 10 )
              break;
            if ( (unsigned __int16)(v35 - 48) <= 9u )
              v36 = v35 + 10 * v36 - 48;
            v35 = *++v20;
          }
          while ( *v20 );
          if ( !v36 )
          {
LABEL_199:
            if ( v30 || (v36 = 389, *(_BYTE *)(*((_QWORD *)a3 + 4) + 646LL)) )
              v36 = 636;
          }
          if ( *v20 == 47 || *v20 == 92 )
          {
            *v20++ = 0;
            v37 = *v20;
            if ( *v20 )
            {
              if ( v37 != 10 )
              {
                v32 = (unsigned __int16 *)v20;
                do
                {
                  if ( !v37 )
                    break;
                  v37 = *++v20;
                }
                while ( *v20 != 10 );
                if ( *v20 )
                  *v20++ = 0;
              }
            }
          }
          v8 = LdapChaseReferral(a3, a2, v31, v32, v36, *((_BYTE *)a3 + 272), v30);
          if ( !v8 )
            goto LABEL_191;
          if ( v68 - 1 <= 0xFFFFFFFD )
          {
            v18 = GetTickCount64() - v66;
            if ( v18 >= v68 )
            {
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
              {
                v38 = "HandleReferral:716";
                goto LABEL_112;
              }
              goto LABEL_113;
            }
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
              LDAPClientPrint(
                0x800000,
                "%s Remaining timeout after LdapChaseReferral request:0x%p ulTimeoutRemaining:%lu\n",
                "HandleReferral:709",
                a3,
                v68 - v18);
          }
LABEL_99:
          if ( !v20 )
            goto LABEL_100;
        }
      }
    }
    else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
    {
      LDAPClientPrint(0x800000, "HandleReferral not proper v2 referral for 0x%x\n", (_DWORD)a3);
    }
LABEL_101:
    v8 = 82;
    goto LABEL_102;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
    LDAPClientPrint(0x800000, "HandleReferral error 0x%x while getting referral for 0x%x\n", v15, a3);
LABEL_100:
  if ( !v8 )
    goto LABEL_101;
LABEL_102:
  if ( !v5 )
  {
LABEL_6:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
      LDAPClientPrint(0x800000, "HandleReferral returning error of 0x%x for request 0x%x\n", v8, (_DWORD)a3);
    return v8;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
    LDAPClientPrint(0x800000, "HandleReferral result 0x%x for request 0x%x while handling '%S'\n", v8, (_DWORD)a3, v5);
  ldapFree(v5, 1818318412);
  return v8;
}

```

## disassembly

```asm
0x180046038  mov     rax, rsp
0x18004603b  mov     [rax+8], rbx
0x18004603f  mov     [rax+20h], r9d
0x180046043  push    rbp
0x180046044  push    rsi
0x180046045  push    rdi
0x180046046  push    r12
0x180046048  push    r13
0x18004604a  push    r14
0x18004604c  push    r15
0x18004604e  sub     rsp, 50h
0x180046052  xor     r12d, r12d
0x180046055  mov     rsi, r8
0x180046058  mov     r15d, r12d
0x18004605b  mov     [rax+10h], r12
0x18004605f  mov     r13, rdx
0x180046062  mov     rdi, rcx
0x180046065  mov     ebx, 52h ; 'R'
0x18004606a  call    cs:__imp_GetTickCount64
0x180046071  nop     dword ptr [rax+rax+00h]
0x180046076  mov     rbp, [r13+8]
0x18004607a  mov     [rsp+88h+var_48], rax
0x18004607f  test    rbp, rbp
0x180046082  jnz     loc_18004610C
0x180046088  cmp     cs:g_fTracingOn, r12d
0x18004608f  jz      short loc_1800460F1
0x180046091  cmp     cs:g_fProviderEnabled, r12d
0x180046098  jz      short loc_1800460BB
0x18004609a  test    cs:g_ulTraceFlags, 800000h
0x1800460a5  jz      short loc_1800460BB
0x1800460a7  lea     rdx, aHandlereferral_19; "HandleReferral no ber to decode for 0x%"...
0x1800460ae  mov     r8, rsi
0x1800460b1  mov     ecx, 800000h
0x1800460b6  call    LDAPClientPrint
0x1800460bb  cmp     cs:g_fTracingOn, r12d
0x1800460c2  jz      short loc_1800460F1
0x1800460c4  cmp     cs:g_fProviderEnabled, r12d
0x1800460cb  jz      short loc_1800460F1
0x1800460cd  test    cs:g_ulTraceFlags, 800000h
0x1800460d8  jz      short loc_1800460F1
0x1800460da  mov     r9, rsi
0x1800460dd  lea     rdx, aHandlereferral_9; "HandleReferral returning error of 0x%x "...
0x1800460e4  mov     r8d, ebx
0x1800460e7  mov     ecx, 800000h
0x1800460ec  call    LDAPClientPrint
0x1800460f1  mov     eax, ebx
0x1800460f3  mov     rbx, [rsp+88h+arg_0]
0x1800460fb  add     rsp, 50h
0x1800460ff  pop     r15
0x180046101  pop     r14
0x180046103  pop     r13
0x180046105  pop     r12
0x180046107  pop     rdi
0x180046108  pop     rsi
0x180046109  pop     rbp
0x18004610a  retn
0x18004610c  cmp     dword ptr [r13+4], 73h ; 's'
0x180046111  mov     r14d, 9
0x180046117  jz      loc_1800466D2
0x18004611d  cmp     [r13+38h], r14d
0x180046121  jnz     loc_1800466C2
0x180046127  mov     al, [rsi+0B9h]
0x18004612d  cmp     [rsi+110h], r12b
0x180046134  jz      short loc_18004616D
0x180046136  test    al, 20h
0x180046138  jnz     short loc_1800461A8
0x18004613a  cmp     cs:g_fTracingOn, r12d
0x180046141  jz      short loc_1800460F1
0x180046143  cmp     cs:g_fProviderEnabled, r12d
0x18004614a  jz      loc_1800460BB
0x180046150  test    cs:g_ulTraceFlags, 800000h
0x18004615b  jz      loc_1800460BB
0x180046161  lea     rdx, aHandlereferral; "HandleReferral not handling subordinate"...
0x180046168  jmp     loc_1800460AE
0x18004616d  test    al, 40h
0x18004616f  jnz     short loc_1800461A8
0x180046171  cmp     cs:g_fTracingOn, r12d
0x180046178  jz      loc_1800460F1
0x18004617e  cmp     cs:g_fProviderEnabled, r12d
0x180046185  jz      loc_1800460BB
0x18004618b  test    cs:g_ulTraceFlags, 800000h
0x180046196  jz      loc_1800460BB
0x18004619c  lea     rdx, aHandlereferral_27; "HandleReferral not handling external fo"...
0x1800461a3  jmp     loc_1800460AE
0x1800461a8  xor     edx, edx; unsigned __int8
0x1800461aa  mov     rcx, rbp; this
0x1800461ad  call    ?Reset@CLdapBer@@QEAAXE@Z; CLdapBer::Reset(uchar)
0x1800461b2  mov     rdx, r13; struct ldapmsg *
0x1800461b5  mov     rcx, rdi; struct ldap_connection *
0x1800461b8  call    ?LdapInitialDecodeMessage@@YAKPEAUldap_connection@@PEAUldapmsg@@@Z; LdapInitialDecodeMessage(ldap_connection *,ldapmsg *)
0x1800461bd  mov     ebx, eax
0x1800461bf  test    eax, eax
0x1800461c1  jz      short loc_18004620A
0x1800461c3  cmp     cs:g_fTracingOn, r12d
0x1800461ca  jz      loc_18004659A
0x1800461d0  cmp     cs:g_fProviderEnabled, r12d
0x1800461d7  jz      loc_18004659A
0x1800461dd  test    cs:g_ulTraceFlags, 800000h
0x1800461e8  jz      loc_18004659A
0x1800461ee  lea     rdx, aHandlereferral_20; "HandleReferral error 0x%x while decodin"...
0x1800461f5  mov     r8d, eax
0x1800461f8  mov     r9, rsi
0x1800461fb  mov     ecx, 800000h
0x180046200  call    LDAPClientPrint
0x180046205  jmp     loc_18004659A
0x18004620a  mov     rcx, rbp; this
0x18004620d  call    ?HrSkipElement@CLdapBer@@QEAAKXZ; CLdapBer::HrSkipElement(void)
0x180046212  mov     ebx, eax
0x180046214  test    eax, eax
0x180046216  jz      short loc_18004624C
0x180046218  cmp     cs:g_fTracingOn, r12d
0x18004621f  jz      loc_18004659A
0x180046225  cmp     cs:g_fProviderEnabled, r12d
0x18004622c  jz      loc_18004659A
0x180046232  test    cs:g_ulTraceFlags, 800000h
0x18004623d  jz      loc_18004659A
0x180046243  lea     rdx, aHandlereferral_31; "HandleReferral error 0x%x while skippin"...
0x18004624a  jmp     short loc_1800461F5
0x18004624c  xor     r8d, r8d; unsigned __int8
0x18004624f  lea     rdx, [rsp+88h+lpString1]; unsigned __int16 **
0x180046257  mov     rcx, rbp; this
0x18004625a  call    ?HrGetValueWithAlloc@CLdapBer@@QEAAKPEAPEAGE@Z; CLdapBer::HrGetValueWithAlloc(ushort * *,uchar)
0x18004625f  mov     r15, [rsp+88h+lpString1]
0x180046267  mov     ebx, eax
0x180046269  test    eax, eax
0x18004626b  jnz     loc_18004667B
0x180046271  test    r15, r15
0x180046274  jz      loc_18004667B
0x18004627a  mov     rcx, r15
0x18004627d  call    strlenW
0x180046282  cmp     eax, r14d
0x180046285  jb      loc_180046637
0x18004628b  mov     r9d, r14d; cchCount2
0x18004628e  lea     r8, aReferral; "Referral:"
0x180046295  mov     edx, r14d; cchCount1
0x180046298  mov     rcx, r15; lpString1
0x18004629b  call    ldapWStringsIdentical
0x1800462a0  test    al, al
0x1800462a2  jz      loc_180046637
0x1800462a8  lea     rdi, [r15+14h]
0x1800462ac  cmp     [rdi-2], r12w
0x1800462b1  jz      loc_180046637
0x1800462b7  cmp     cs:g_fTracingOn, r12d
0x1800462be  jz      short loc_1800462E9
0x1800462c0  cmp     cs:g_fProviderEnabled, r12d
0x1800462c7  jz      short loc_1800462E9
0x1800462c9  mov     ecx, 800000h
0x1800462ce  test    cs:g_ulTraceFlags, rcx
0x1800462d5  jz      short loc_1800462E9
0x1800462d7  mov     r9, rsi
0x1800462da  lea     rdx, aHandlereferral_16; "HandleReferral chasing '%S' for request"...
0x1800462e1  mov     r8, rdi
0x1800462e4  call    LDAPClientPrint
0x1800462e9  test    rdi, rdi
0x1800462ec  jz      loc_180046595
0x1800462f2  mov     ebp, 8
0x1800462f7  mov     r12w, 2Fh ; '/'
0x1800462fc  xor     r11d, r11d
0x1800462ff  lea     r14d, [rbp+2]
0x180046303  cmp     [rdi], r11w
0x180046307  jz      loc_18004658E
0x18004630d  mov     rcx, rdi
0x180046310  call    strlenW
0x180046315  cmp     eax, 7
0x180046318  jbe     short loc_180046321
0x18004631a  mov     eax, 7
0x18004631f  jmp     short loc_180046329
0x180046321  mov     rcx, rdi
0x180046324  call    strlenW
0x180046329  mov     r9d, 7; cchCount2
0x18004632f  lea     r8, aLdap_0; "ldap://"
0x180046336  mov     edx, eax; cchCount1
0x180046338  mov     rcx, rdi; lpString1
0x18004633b  call    ldapWStringsIdentical
0x180046340  xor     r11d, r11d
0x180046343  test    al, al
0x180046345  jnz     loc_1800463EC
0x18004634b  mov     rcx, rdi
0x18004634e  call    strlenW
0x180046353  cmp     eax, ebp
0x180046355  jbe     short loc_18004635B
0x180046357  mov     eax, ebp
0x180046359  jmp     short loc_180046363
0x18004635b  mov     rcx, rdi
0x18004635e  call    strlenW
0x180046363  mov     r9d, ebp; cchCount2
0x180046366  lea     r8, aLdaps; "ldaps://"
0x18004636d  mov     edx, eax; cchCount1
0x18004636f  mov     rcx, rdi; lpString1
0x180046372  call    ldapWStringsIdentical
0x180046377  xor     r11d, r11d
0x18004637a  test    al, al
0x18004637c  jnz     short loc_1800463E3
0x18004637e  movzx   eax, word ptr [rdi]
0x180046381  cmp     ax, r14w
0x180046385  jz      short loc_18004639F
0x180046387  test    ax, ax
0x18004638a  jz      short loc_180046399
0x18004638c  add     rdi, 2
0x180046390  movzx   eax, word ptr [rdi]
0x180046393  cmp     ax, r14w
0x180046397  jnz     short loc_180046387
0x180046399  cmp     [rdi], r14w
0x18004639d  jnz     short loc_1800463A3
0x18004639f  add     rdi, 2
0x1800463a3  cmp     cs:g_fTracingOn, r11d
0x1800463aa  jz      loc_180046585
0x1800463b0  cmp     cs:g_fProviderEnabled, r11d
0x1800463b7  jz      loc_180046585
0x1800463bd  mov     ecx, 800000h
0x1800463c2  test    cs:g_ulTraceFlags, rcx
0x1800463c9  jz      loc_180046585
0x1800463cf  mov     r8, rsi
0x1800463d2  lea     rdx, aHandlereferral_32; "HandleReferral non ldap referral skippe"...
0x1800463d9  call    LDAPClientPrint
0x1800463de  jmp     loc_180046582
0x1800463e3  mov     r8b, 1
0x1800463e6  add     rdi, 10h
0x1800463ea  jmp     short loc_1800463F3
0x1800463ec  mov     r8b, r11b
0x1800463ef  add     rdi, 0Eh
0x1800463f3  mov     r10, rdi
0x1800463f6  mov     r9, r11
0x1800463f9  jmp     short loc_18004641B
0x1800463fb  cmp     ax, 5Ch ; '\'
0x1800463ff  jz      short loc_180046424
0x180046401  cmp     ax, 3Ah ; ':'
0x180046405  ja      short loc_180046417
0x180046407  mov     rcx, 400000000000401h
0x180046411  bt      rcx, rax
0x180046415  jb      short loc_180046424
0x180046417  add     rdi, 2
0x18004641b  movzx   eax, word ptr [rdi]
0x18004641e  cmp     ax, r12w
0x180046422  jnz     short loc_1800463FB
0x180046424  cmp     word ptr [rdi], 3Ah ; ':'
0x180046428  jnz     short loc_180046481
0x18004642a  mov     [rdi], r11w
0x18004642e  add     rdi, 2
0x180046432  movzx   ecx, word ptr [rdi]
0x180046435  test    cx, cx
0x180046438  jz      short loc_180046481
0x18004643a  mov     edx, r11d
0x18004643d  mov     ebx, 9
0x180046442  cmp     cx, r12w
0x180046446  jz      short loc_18004647C
0x180046448  cmp     cx, 5Ch ; '\'
0x18004644c  jz      short loc_18004647C
0x18004644e  cmp     cx, r14w
0x180046452  jz      short loc_18004647C
0x180046454  lea     eax, [rcx-30h]
0x180046457  cmp     ax, bx
0x18004645a  ja      short loc_180046470
0x18004645c  movzx   eax, dx
0x18004645f  shl     ax, 2
0x180046463  add     dx, ax
0x180046466  add     dx, dx
0x180046469  sub     dx, 30h ; '0'
0x18004646d  add     dx, cx
0x180046470  add     rdi, 2
0x180046474  movzx   ecx, word ptr [rdi]
0x180046477  test    cx, cx
0x18004647a  jnz     short loc_180046442
0x18004647c  test    dx, dx
0x18004647f  jnz     short loc_18004649D
0x180046481  test    r8b, r8b
0x180046484  jnz     short loc_180046498
0x180046486  mov     rax, [rsi+20h]
0x18004648a  mov     edx, 185h
0x18004648f  cmp     [rax+286h], r11b
0x180046496  jz      short loc_18004649D
0x180046498  mov     edx, 27Ch
0x18004649d  cmp     [rdi], r12w
0x1800464a1  jz      short loc_1800464A9
0x1800464a3  cmp     word ptr [rdi], 5Ch ; '\'
0x1800464a7  jnz     short loc_1800464E2
0x1800464a9  mov     [rdi], r11w
0x1800464ad  add     rdi, 2
0x1800464b1  movzx   eax, word ptr [rdi]
0x1800464b4  test    ax, ax
0x1800464b7  jz      short loc_1800464E2
0x1800464b9  cmp     ax, r14w
0x1800464bd  jz      short loc_1800464E2
0x1800464bf  mov     r9, rdi; unsigned __int16 *
0x1800464c2  test    ax, ax
0x1800464c5  jz      short loc_1800464D4
0x1800464c7  add     rdi, 2
0x1800464cb  movzx   eax, word ptr [rdi]
0x1800464ce  cmp     ax, r14w
0x1800464d2  jnz     short loc_1800464C2
0x1800464d4  cmp     [rdi], r11w
0x1800464d8  jz      short loc_1800464E2
0x1800464da  mov     [rdi], r11w
0x1800464de  add     rdi, 2
0x1800464e2  mov     al, [rsi+110h]
0x1800464e8  mov     rcx, rsi; struct ldap_request *
0x1800464eb  mov     [rsp+88h+var_58], r8b; unsigned __int8
0x1800464f0  mov     r8, r10; unsigned __int16 *
0x1800464f3  mov     [rsp+88h+var_60], al; unsigned __int8
0x1800464f7  mov     [rsp+88h+var_68], dx; unsigned __int16
  ... truncated ...
```
