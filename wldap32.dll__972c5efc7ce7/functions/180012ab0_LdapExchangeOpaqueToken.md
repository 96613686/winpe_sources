# LdapExchangeOpaqueToken

- ea: `0x180012ab0`
- end: `0x180013608`
- name: `LdapExchangeOpaqueToken`
- size: `2904`
- prototype: `__int64 __usercall@<rax>(struct ldap_connection *@<rcx>, __int64, size_t Size, __int64, struct berval **, __int64, __int64, __int64, char, char, __int64)`
- caller_count: `6`
- callee_count: `29`
- tags: ``

## callers

- `0x1800164a0`
- `0x180017854`
- `0x180049f10`
- `0x18004a120`
- `0x18004a270`
- `0x18004a470`

## callees

- `0x1800014e0`
- `0x180001790`
- `0x1800018d0`
- `0x1800030f0`
- `0x1800037a8`
- `0x180004e60`
- `0x180008710`
- `0x18000cad0`
- `0x18000df44`
- `0x180010ef0`
- `0x180011020`
- `0x180011c80`
- `0x180011f50`
- `0x180012ab0`
- `0x180014060`
- `0x180014600`
- `0x1800147f0`
- `0x180014b60`
- `0x18001fb78`
- `0x180020320`
- `0x180029d28`
- `0x18002a284`
- `0x18002a9f8`
- `0x18002b020`
- `0x18002cb90`
- `0x18002dbac`
- `0x18002df60`
- `0x180034510`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012d39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012d39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012f60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012fbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012f60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012fbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133ee`

## string_xrefs

- `0x180013289`: `LdapExchangeOpaqueToken: Unsupported authentication type %d.\n`
- `0x180013452`: `Bailing out of LdapExchangeOpaqueToken because server returned 0x%x\n`
- `0x1800133fd`: `ldapExchangeOpaque thread 0x%x has connection 0x%x as down.\n`

## pseudocode

```c
__int64 __fastcall LdapExchangeOpaqueToken(
        struct ldap_connection *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        void *a5,
        size_t Size,
        __int64 a7,
        struct berval **a8,
        struct ldapcontrolW **a9,
        struct ldapcontrolW **a10,
        _DWORD *a11,
        char a12,
        char a13,
        _BYTE *a14)
{
  int v15; // ecx
  LDAPMessage *v19; // rcx
  __int64 v20; // rdx
  __int64 Request; // rax
  __int64 v22; // rbx
  ULONG inserted; // esi
  char v24; // r15
  char v25; // r13
  unsigned int v26; // eax
  void *v27; // rdx
  int v28; // r13d
  void *v29; // rcx
  bool v30; // zf
  int v31; // eax
  unsigned int v32; // r8d
  ULONG v33; // eax
  struct ldapmsg *v34; // rdx
  CLdapBer *lm_ber; // r15
  unsigned int v36; // eax
  int v37; // edx
  CLdapBer *v38; // rcx
  unsigned int v39; // r9d
  unsigned int ValueWithAlloc; // eax
  struct _RTL_CRITICAL_SECTION *v41; // rcx
  const CHAR *v43; // rdx
  unsigned int v44; // eax
  DWORD CurrentThreadId; // eax
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  struct ldapmsg *v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h]
  struct ldapcontrolW **v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  struct ldapcontrolW **v52; // [rsp+78h] [rbp-88h]
  _BYTE *v53; // [rsp+80h] [rbp-80h]
  _DWORD *v54; // [rsp+88h] [rbp-78h]
  __int64 v55; // [rsp+90h] [rbp-70h] BYREF
  int v56; // [rsp+98h] [rbp-68h]
  __int64 v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  int v59; // [rsp+B0h] [rbp-50h]
  __int64 v60; // [rsp+3D4h] [rbp+2D4h]
  char v61; // [rsp+3E8h] [rbp+2E8h]
  int v62; // [rsp+3ECh] [rbp+2ECh]
  int v63; // [rsp+3F0h] [rbp+2F0h]

  Src = a5;
  v15 = 65001;
  v49 = a7;
  v30 = *((_DWORD *)a1 + 250) == 2;
  v52 = a9;
  if ( v30 )
    v15 = 0;
  v50 = a10;
  v54 = a11;
  v62 = v15;
  v19 = (LDAPMessage *)*((_QWORD *)a1 + 86);
  v53 = a14;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v60 = 0;
  v58 = 0;
  v61 = 0;
  v63 = 0;
  v59 = 0;
  v48 = 0;
  v51 = 0;
  ldap_msgfree(v19);
  LOBYTE(v20) = 96;
  *((_QWORD *)a1 + 86) = 0;
  Request = LdapCreateRequest(a1, v20);
  v22 = Request;
  if ( !Request )
  {
    CLdapBer::~CLdapBer((CLdapBer *)&v55);
    return 90;
  }
  *(_BYTE *)(Request + 185) = 0;
  *(_BYTE *)(Request + 187) = 1;
  if ( a2 == 4230 )
    goto LABEL_5;
  if ( a2 <= 0x886 )
  {
    if ( a2 != 2182 )
    {
      if ( a2 == 131 )
        goto LABEL_66;
      if ( a2 != 646 )
      {
        if ( a2 == 1158 )
          goto LABEL_66;
LABEL_98:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientPrint(0x10000000, "LdapExchangeOpaqueToken: Unsupported authentication type %d.\n", a2);
        inserted = 7;
        goto LABEL_49;
      }
    }
LABEL_5:
    inserted = 83;
    if ( CLdapBer::HrStartWriteSequence((CLdapBer *)&v55, 0x30u)
      || CLdapBer::HrAddValue((CLdapBer *)&v55, *(_DWORD *)(v22 + 108), 2u)
      || CLdapBer::HrStartWriteSequence((CLdapBer *)&v55, 0x60u)
      || CLdapBer::HrAddValue((CLdapBer *)&v55, *((_DWORD *)a1 + 250), 2u) )
    {
      goto LABEL_49;
    }
    if ( *((_DWORD *)a1 + 174) )
    {
      v24 = -117;
      if ( CLdapBer::HrAddValue((CLdapBer *)&v55, MultiByteStr, 4u) )
        goto LABEL_49;
    }
    else
    {
      if ( CLdapBer::HrAddValue((CLdapBer *)&v55, a4, 4u) )
        goto LABEL_49;
      v24 = -118;
    }
    v25 = v63;
    if ( v63 )
      v63 = 0;
    else
      v25 = v24;
    if ( (int)Size + 6 < (unsigned int)Size )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbValue 0x%x\n", Size);
      goto LABEL_49;
    }
    if ( CLdapBer::HrEnsureBuffer((CLdapBer *)&v55, Size + 6, 0) )
      goto LABEL_49;
    *(_BYTE *)(HIDWORD(v55) + v57) = v25;
    v26 = ++HIDWORD(v55);
    if ( (unsigned int)Size > 0x7F )
    {
      if ( (unsigned int)Size > 0x7FFF )
      {
        if ( (unsigned int)Size >= 0x7FFFFFFF )
        {
          v28 = -2147024809;
          goto LABEL_17;
        }
        *(_BYTE *)(v26 + v57) = -124;
        ++HIDWORD(v55);
        *(_BYTE *)(HIDWORD(v55) + v57) = BYTE3(Size);
        ++HIDWORD(v55);
        *(_BYTE *)(HIDWORD(v55) + v57) = BYTE2(Size);
      }
      else
      {
        *(_BYTE *)(v26 + v57) = -126;
      }
      ++HIDWORD(v55);
      *(_BYTE *)(HIDWORD(v55) + v57) = BYTE1(Size);
      v26 = ++HIDWORD(v55);
    }
    v27 = Src;
    v28 = 0;
    *(_BYTE *)(v26 + v57) = Size;
    v29 = (void *)(v57 + (unsigned int)++HIDWORD(v55));
    memcpy_0(v29, v27, (unsigned int)Size);
    HIDWORD(v55) += Size;
    LODWORD(v55) = HIDWORD(v55);
LABEL_17:
    v30 = v28 == 0;
    goto LABEL_18;
  }
  if ( a2 != 16518 )
  {
    if ( a2 != 8326 )
      goto LABEL_98;
    goto LABEL_5;
  }
LABEL_66:
  inserted = 83;
  if ( CLdapBer::HrStartWriteSequence((CLdapBer *)&v55, 0x30u)
    || CLdapBer::HrAddValue((CLdapBer *)&v55, *(_DWORD *)(v22 + 108), 2u)
    || CLdapBer::HrStartWriteSequence((CLdapBer *)&v55, 0x60u)
    || CLdapBer::HrAddValue((CLdapBer *)&v55, *((_DWORD *)a1 + 250), 2u)
    || CLdapBer::HrAddValue((CLdapBer *)&v55, a4, 4u)
    || CLdapBer::HrStartWriteSequence((CLdapBer *)&v55, 0xA3u) )
  {
    goto LABEL_49;
  }
  if ( !a3 )
  {
    if ( a2 == 1158 )
    {
      if ( *((_BYTE *)a1 + 198) == 1 )
      {
        v43 = "GSS-SPNEGO";
LABEL_76:
        v44 = CLdapBer::HrAddValue((CLdapBer *)&v55, v43, 4u);
        goto LABEL_77;
      }
    }
    else
    {
      v43 = "DIGEST-MD5";
      if ( a2 == 16518 )
        goto LABEL_76;
    }
    v43 = "GSSAPI";
    goto LABEL_76;
  }
  v44 = CLdapBer::HrAddValue((CLdapBer *)&v55, a3, 4u);
LABEL_77:
  if ( v44 || CLdapBer::HrAddBinaryValue((CLdapBer *)&v55, (unsigned __int8 *)Src, Size, 4u) )
    goto LABEL_49;
  v30 = CLdapBer::HrEndWriteSequence((CLdapBer *)&v55) == 0;
LABEL_18:
  if ( !v30 || CLdapBer::HrEndWriteSequence((CLdapBer *)&v55) || CLdapBer::HrEndWriteSequence((CLdapBer *)&v55) )
    goto LABEL_49;
  if ( v52 || v50 )
  {
    LdapCheckControls((struct ldap_request *)v22, v52, v50, a13, 0);
    if ( *((_DWORD *)a1 + 250) != 2 )
    {
      if ( *(_QWORD *)(v22 + 200) )
      {
        inserted = InsertServerControls((struct ldap_request *)v22, a1, (struct CLdapBer *)&v55);
        if ( inserted )
          goto LABEL_49;
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 14);
  AddToPendingList(v22, a1);
  inserted = LdapSend(a1, (struct CLdapBer *)&v55, 0);
  if ( inserted )
  {
    DecrementPendingList(v22, a1);
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 14);
    goto LABEL_49;
  }
  if ( v53 )
    *v53 = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 14);
  if ( a12 )
  {
    *v54 = *(_DWORD *)(v22 + 108);
    goto LABEL_49;
  }
  v31 = *((_DWORD *)a1 + 253);
  if ( v31 )
    v32 = 1000 * v31;
  else
    v32 = 30000;
  v33 = LdapWaitForResponseFromServer(a1, (struct ldap_request *)v22, v32, 0, &v48, 1);
  v34 = v48;
  inserted = v33;
  *((_QWORD *)a1 + 86) = v48;
  if ( !v33 )
  {
    if ( !v34 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
      {
        CurrentThreadId = GetCurrentThreadId();
        LDAPClientPrint(
          128,
          "ldapExchangeOpaque thread 0x%x has connection 0x%x as down.\n",
          CurrentThreadId,
          (_DWORD)a1);
      }
      inserted = 81;
      goto LABEL_49;
    }
    goto LABEL_31;
  }
  if ( v34 )
  {
LABEL_31:
    inserted = v48->lm_returncode;
    if ( inserted && inserted != 14 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(0x10000000, "Bailing out of LdapExchangeOpaqueToken because server returned 0x%x\n", inserted);
      goto LABEL_49;
    }
    lm_ber = (CLdapBer *)v48->lm_ber;
    if ( lm_ber )
    {
      if ( a2 != 1158 )
      {
        if ( a2 == 646 || a2 == 2182 || a2 == 8326 || a2 == 4230 )
        {
          inserted = 84;
          v39 = 4;
          v38 = (CLdapBer *)v48->lm_ber;
          goto LABEL_46;
        }
        if ( a2 != 16518 && !a8 )
        {
LABEL_48:
          ++*((_DWORD *)a1 + 174);
          inserted = 0;
          goto LABEL_49;
        }
      }
      inserted = 84;
      if ( !CLdapBer::HrSkipElement((CLdapBer *)v48->lm_ber) && !CLdapBer::HrSkipElement(lm_ber) )
      {
        v36 = *((_DWORD *)lm_ber + 1);
        if ( *(_DWORD *)lm_ber <= v36 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
            LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", *(_DWORD *)lm_ber, v36);
          goto LABEL_48;
        }
        v37 = *(unsigned __int8 *)(*((_QWORD *)lm_ber + 2) + v36);
        LODWORD(Src) = v37;
        if ( v37 == 131 )
        {
          if ( CLdapBer::HrSkipElement(lm_ber) || CLdapBer::HrPeekTag(lm_ber, (unsigned int *)&Src) )
            goto LABEL_49;
          v37 = (int)Src;
        }
        if ( v37 == 133 )
        {
          if ( CLdapBer::HrSkipElement(lm_ber) || CLdapBer::HrPeekTag(lm_ber, (unsigned int *)&Src) )
            goto LABEL_49;
          v37 = (int)Src;
        }
        if ( v37 == 134 )
        {
          if ( CLdapBer::HrSkipElement(lm_ber) || CLdapBer::HrPeekTag(lm_ber, (unsigned int *)&Src) )
            goto LABEL_49;
          v37 = (int)Src;
        }
        if ( v37 != 167 )
        {
          if ( v37 != 135 )
            goto LABEL_49;
          v38 = lm_ber;
          if ( a8 )
          {
            ValueWithAlloc = CLdapBer::HrGetValueWithAlloc(lm_ber, a8, 1u);
LABEL_47:
            if ( ValueWithAlloc )
              goto LABEL_49;
            goto LABEL_48;
          }
          v39 = 135;
LABEL_46:
          ValueWithAlloc = CLdapBer::HrGetBinaryValuePointer(
                             v38,
                             (unsigned __int8 **)(*(_QWORD *)(v49 + 8) + 8LL),
                             *(unsigned int **)(v49 + 8),
                             v39,
                             0);
          goto LABEL_47;
        }
        if ( !CLdapBer::HrStartReadSequence(lm_ber, 0xA7u, 0)
          && !CLdapBer::HrPeekTag(lm_ber, (unsigned int *)&Src)
          && (_DWORD)Src == 163
          && !CLdapBer::HrStartReadSequence(lm_ber, 0xA3u, 0)
          && !CLdapBer::HrSkipElement(lm_ber)
          && !(a8
             ? CLdapBer::HrGetValueWithAlloc(lm_ber, a8, 1u)
             : CLdapBer::HrGetBinaryValuePointer(
                 lm_ber,
                 (unsigned __int8 **)(*(_QWORD *)(v49 + 8) + 8LL),
                 *(unsigned int **)(v49 + 8),
                 4u,
                 0)) )
        {
          goto LABEL_48;
        }
      }
    }
LABEL_49:
    if ( v48 )
    {
      LdapParseResult(a1, v48, 0, 0, &v51, 0, 0, 0, 0);
      InsertErrorMessage(a1, v51);
    }
  }
  CloseLdapRequest(v22);
  EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 48));
  --*(_DWORD *)(v22 + 16);
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v22, *(_DWORD *)(v22 + 16));
  v41 = (struct _RTL_CRITICAL_SECTION *)(v22 + 48);
  if ( *(_DWORD *)(v22 + 16) )
  {
    LeaveCriticalSection(v41);
  }
  else
  {
    LeaveCriticalSection(v41);
    DereferenceLdapRequest2(v22, 0);
  }
  if ( inserted || a8 )
  {
    ldap_msgfree(*((LDAPMessage **)a1 + 86));
    *((_QWORD *)a1 + 86) = 0;
  }
  CLdapBer::~CLdapBer((CLdapBer *)&v55);
  return inserted;
}

```

## disassembly

```asm
0x180012ab0  push    rbp
0x180012ab2  push    rbx
0x180012ab3  push    rdi
0x180012ab4  push    r12
0x180012ab6  push    r13
0x180012ab8  push    r14
0x180012aba  push    r15
0x180012abc  lea     rbp, [rsp-320h]
0x180012ac4  sub     rsp, 420h
0x180012acb  mov     rax, cs:__security_cookie
0x180012ad2  xor     rax, rsp
0x180012ad5  mov     [rbp+350h+var_50], rax
0x180012adc  mov     rax, [rbp+350h+arg_20]
0x180012ae3  xor     ebx, ebx
0x180012ae5  mov     r12, [rbp+350h+arg_38]
0x180012aec  mov     rdi, rcx
0x180012aef  mov     [rsp+450h+Src], rax
0x180012af4  mov     ecx, 0FDE9h
0x180012af9  mov     rax, [rbp+350h+arg_30]
0x180012b00  mov     r13, r9
0x180012b03  mov     [rsp+450h+var_3F0], rax
0x180012b08  mov     r15, r8
0x180012b0b  mov     rax, [rbp+350h+arg_40]
0x180012b12  mov     r14d, edx
0x180012b15  cmp     dword ptr [rdi+3E8h], 2
0x180012b1c  mov     [rsp+450h+var_3D8], rax
0x180012b21  mov     rax, [rbp+350h+arg_48]
0x180012b28  cmovz   ecx, ebx
0x180012b2b  mov     [rsp+450h+var_3E8], rax
0x180012b30  mov     rax, [rbp+350h+arg_50]
0x180012b37  mov     [rbp+350h+var_3C8], rax
0x180012b3b  mov     rax, [rbp+350h+arg_68]
0x180012b42  mov     [rbp+350h+var_64], ecx
0x180012b48  mov     rcx, [rdi+2B0h]; res
0x180012b4f  mov     [rbp+350h+var_3D0], rax
0x180012b53  mov     [rbp+350h+var_3C0], rbx
0x180012b57  mov     [rbp+350h+var_3B8], ebx
0x180012b5a  mov     [rbp+350h+var_3B0], rbx
0x180012b5e  mov     [rbp+350h+var_7C], rbx
0x180012b65  mov     [rbp+350h+var_3A8], rbx
0x180012b69  mov     [rbp+350h+var_68], bl
0x180012b6f  mov     [rbp+350h+var_60], ebx
0x180012b75  mov     [rbp+350h+var_3A0], ebx
0x180012b78  mov     [rsp+450h+var_3F8], rbx
0x180012b7d  mov     [rsp+450h+var_3E0], rbx
0x180012b82  call    ldap_msgfree
0x180012b87  mov     dl, 60h ; '`'
0x180012b89  mov     [rdi+2B0h], rbx
0x180012b90  mov     rcx, rdi
0x180012b93  call    LdapCreateRequest
0x180012b98  mov     rbx, rax
0x180012b9b  test    rax, rax
0x180012b9e  jz      loc_1800131C9
0x180012ba4  mov     [rsp+450h+var_38], rsi
0x180012bac  mov     byte ptr [rax+0B9h], 0
0x180012bb3  mov     byte ptr [rax+0BBh], 1
0x180012bba  cmp     r14d, 1086h
0x180012bc1  jnz     loc_18001301F
0x180012bc7  mov     edx, 30h ; '0'; unsigned int
0x180012bcc  lea     rcx, [rbp+350h+var_3C0]; this
0x180012bd0  mov     esi, 53h ; 'S'
0x180012bd5  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x180012bda  test    eax, eax
0x180012bdc  jnz     loc_180012EE0
0x180012be2  mov     edx, [rbx+6Ch]; int
0x180012be5  lea     rcx, [rbp+350h+var_3C0]; this
0x180012be9  mov     r8d, 2; unsigned int
0x180012bef  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x180012bf4  test    eax, eax
0x180012bf6  jnz     loc_180012EE0
0x180012bfc  mov     edx, 60h ; '`'; unsigned int
0x180012c01  lea     rcx, [rbp+350h+var_3C0]; this
0x180012c05  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x180012c0a  test    eax, eax
0x180012c0c  jnz     loc_180012EE0
0x180012c12  mov     edx, [rdi+3E8h]; int
0x180012c18  lea     rcx, [rbp+350h+var_3C0]; this
0x180012c1c  mov     r8d, 2; unsigned int
0x180012c22  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x180012c27  test    eax, eax
0x180012c29  jnz     loc_180012EE0
0x180012c2f  lea     rcx, [rbp+350h+var_3C0]; this
0x180012c33  mov     r8d, 4; unsigned int
0x180012c39  cmp     [rdi+2B8h], eax
0x180012c3f  jz      loc_1800132DB
0x180012c45  lea     rdx, MultiByteStr; lpMultiByteStr
0x180012c4c  mov     r15d, 8Bh
0x180012c52  call    ?HrAddValue@CLdapBer@@QEAAKPEBDK@Z; CLdapBer::HrAddValue(char const *,ulong)
0x180012c57  test    eax, eax
0x180012c59  jnz     loc_180012EE0
0x180012c5f  mov     r13d, [rbp+350h+var_60]
0x180012c66  test    r13d, r13d
0x180012c69  jnz     loc_1800132F6
0x180012c6f  mov     r13d, r15d
0x180012c72  mov     r15d, dword ptr [rbp+350h+Size]
0x180012c79  lea     edx, [r15+6]; unsigned int
0x180012c7d  cmp     edx, r15d
0x180012c80  jb      loc_180013305
0x180012c86  xor     r8d, r8d; int
0x180012c89  lea     rcx, [rbp+350h+var_3C0]; this
0x180012c8d  call    ?HrEnsureBuffer@CLdapBer@@AEAAKKH@Z; CLdapBer::HrEnsureBuffer(ulong,int)
0x180012c92  test    eax, eax
0x180012c94  jnz     loc_180012EE0
0x180012c9a  mov     ecx, dword ptr [rbp+350h+var_3C0+4]
0x180012c9d  mov     rax, [rbp+350h+var_3B0]
0x180012ca1  mov     [rcx+rax], r13b
0x180012ca5  mov     eax, dword ptr [rbp+350h+var_3C0+4]
0x180012ca8  inc     eax
0x180012caa  mov     dword ptr [rbp+350h+var_3C0+4], eax
0x180012cad  cmp     r15d, 7Fh
0x180012cb1  ja      loc_180012FE4
0x180012cb7  mov     rdx, [rsp+450h+Src]; Src
0x180012cbc  mov     r8, r15; Size
0x180012cbf  mov     ecx, eax
0x180012cc1  xor     r13d, r13d
0x180012cc4  mov     rax, [rbp+350h+var_3B0]
0x180012cc8  mov     [rcx+rax], r15b
0x180012ccc  mov     eax, dword ptr [rbp+350h+var_3C0+4]
0x180012ccf  inc     eax
0x180012cd1  mov     ecx, eax
0x180012cd3  add     rcx, [rbp+350h+var_3B0]; void *
0x180012cd7  mov     dword ptr [rbp+350h+var_3C0+4], eax
0x180012cda  call    memcpy_0
0x180012cdf  mov     eax, dword ptr [rbp+350h+var_3C0+4]
0x180012ce2  add     eax, r15d
0x180012ce5  mov     dword ptr [rbp+350h+var_3C0+4], eax
0x180012ce8  mov     dword ptr [rbp+350h+var_3C0], eax
0x180012ceb  test    r13d, r13d
0x180012cee  jnz     loc_180012EE0
0x180012cf4  lea     rcx, [rbp+350h+var_3C0]; this
0x180012cf8  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180012cfd  test    eax, eax
0x180012cff  jnz     loc_180012EE0
0x180012d05  lea     rcx, [rbp+350h+var_3C0]; this
0x180012d09  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180012d0e  test    eax, eax
0x180012d10  jnz     loc_180012EE0
0x180012d16  mov     rdx, [rsp+450h+var_3D8]; struct ldapcontrolW **
0x180012d1b  mov     r8, [rsp+450h+var_3E8]; struct ldapcontrolW **
0x180012d20  test    rdx, rdx
0x180012d23  jnz     loc_180013349
0x180012d29  test    r8, r8
0x180012d2c  jnz     loc_180013349
0x180012d32  lea     rcx, [rdi+230h]; lpCriticalSection
0x180012d39  call    cs:__imp_EnterCriticalSection
0x180012d40  nop     dword ptr [rax+rax+00h]
0x180012d45  mov     rdx, rdi
0x180012d48  mov     rcx, rbx
0x180012d4b  call    AddToPendingList
0x180012d50  xor     r8d, r8d; struct CLdapBer *
0x180012d53  lea     rdx, [rbp+350h+var_3C0]; struct CLdapBer *
0x180012d57  mov     rcx, rdi; struct ldap_connection *
0x180012d5a  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x180012d5f  mov     esi, eax
0x180012d61  test    eax, eax
0x180012d63  jnz     loc_18001339A
0x180012d69  mov     rax, [rbp+350h+var_3D0]
0x180012d6d  test    rax, rax
0x180012d70  jnz     loc_1800133BD
0x180012d76  lea     rcx, [rdi+230h]; lpCriticalSection
0x180012d7d  call    cs:__imp_LeaveCriticalSection
0x180012d84  nop     dword ptr [rax+rax+00h]
0x180012d89  cmp     [rbp+350h+arg_58], 0
0x180012d90  jnz     loc_1800133C5
0x180012d96  mov     eax, [rdi+3F4h]
0x180012d9c  test    eax, eax
0x180012d9e  jz      loc_180012FCB
0x180012da4  imul    r8d, eax, 3E8h; unsigned int
0x180012dab  lea     rax, [rsp+450h+var_3F8]
0x180012db0  mov     [rsp+450h+var_428], 1; char
0x180012db5  xor     r9d, r9d; unsigned int
0x180012db8  mov     [rsp+450h+var_430], rax; struct ldapmsg **
0x180012dbd  mov     rdx, rbx; struct ldap_request *
0x180012dc0  mov     rcx, rdi; struct ldap_connection *
0x180012dc3  call    ?LdapWaitForResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z; LdapWaitForResponseFromServer(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)
0x180012dc8  mov     rdx, [rsp+450h+var_3F8]
0x180012dcd  mov     esi, eax
0x180012dcf  mov     [rdi+2B0h], rdx
0x180012dd6  test    eax, eax
0x180012dd8  jnz     loc_180012FD6
0x180012dde  test    rdx, rdx
0x180012de1  jz      loc_1800133D3
0x180012de7  mov     rax, [rsp+450h+var_3F8]
0x180012dec  mov     esi, [rax+38h]
0x180012def  test    esi, esi
0x180012df1  jnz     loc_18001341B
0x180012df7  mov     rax, [rsp+450h+var_3F8]
0x180012dfc  mov     r15, [rax+8]
0x180012e00  test    r15, r15
0x180012e03  jz      loc_180012EE0
0x180012e09  cmp     r14d, 486h
0x180012e10  jnz     loc_180012EA2
0x180012e16  mov     rcx, r15; this
0x180012e19  mov     esi, 54h ; 'T'
0x180012e1e  call    ?HrSkipElement@CLdapBer@@QEAAKXZ; CLdapBer::HrSkipElement(void)
0x180012e23  test    eax, eax
0x180012e25  jnz     loc_180012EE0
0x180012e2b  mov     rcx, r15; this
0x180012e2e  call    ?HrSkipElement@CLdapBer@@QEAAKXZ; CLdapBer::HrSkipElement(void)
0x180012e33  test    eax, eax
0x180012e35  jnz     loc_180012EE0
0x180012e3b  mov     eax, [r15+4]
0x180012e3f  mov     r8d, [r15]
0x180012e42  cmp     r8d, eax
0x180012e45  jbe     loc_1800131E7
0x180012e4b  mov     ecx, eax
0x180012e4d  mov     rax, [r15+10h]
0x180012e51  movzx   edx, byte ptr [rax+rcx]
0x180012e55  mov     dword ptr [rsp+450h+Src], edx
0x180012e59  cmp     edx, 83h
0x180012e5f  jz      loc_1800134B7
0x180012e65  cmp     edx, 85h
0x180012e6b  jz      loc_1800134E5
0x180012e71  cmp     edx, 86h
0x180012e77  jz      loc_180013145
0x180012e7d  cmp     edx, 0A7h
0x180012e83  jz      loc_180013513
0x180012e89  cmp     edx, 87h
0x180012e8f  jnz     short loc_180012EE0
0x180012e91  mov     rcx, r15; this
0x180012e94  test    r12, r12
0x180012e97  jnz     loc_180013173
0x180012e9d  mov     r9d, edx
0x180012ea0  jmp     short loc_180012EBD
0x180012ea2  cmp     r14d, 286h
0x180012ea9  jnz     loc_180013468
0x180012eaf  mov     esi, 54h ; 'T'
0x180012eb4  mov     r9d, 4; unsigned int
0x180012eba  mov     rcx, r15; this
0x180012ebd  mov     r8, [rsp+450h+var_3F0]
0x180012ec2  mov     byte ptr [rsp+450h+var_430], 0; char
0x180012ec7  mov     r8, [r8+8]; unsigned int *
0x180012ecb  lea     rdx, [r8+8]; unsigned __int8 **
0x180012ecf  call    ?HrGetBinaryValuePointer@CLdapBer@@QEAAKPEAPEAEPEAKKE@Z; CLdapBer::HrGetBinaryValuePointer(uchar * *,ulong *,ulong,uchar)
0x180012ed4  test    eax, eax
0x180012ed6  jnz     short loc_180012EE0
0x180012ed8  inc     dword ptr [rdi+2B8h]
0x180012ede  xor     esi, esi
0x180012ee0  mov     rdx, [rsp+450h+var_3F8]
0x180012ee5  test    rdx, rdx
0x180012ee8  jz      short loc_180012F2E
0x180012eea  mov     [rsp+450h+var_410], 0
0x180012ef2  lea     rax, [rsp+450h+var_3E0]
0x180012ef7  mov     [rsp+450h+var_418], 0
0x180012efc  xor     r9d, r9d
0x180012eff  mov     [rsp+450h+var_420], 0
0x180012f08  xor     r8d, r8d
0x180012f0b  mov     qword ptr [rsp+450h+var_428], 0
0x180012f14  mov     rcx, rdi
0x180012f17  mov     [rsp+450h+var_430], rax
0x180012f1c  call    LdapParseResult
0x180012f21  mov     rdx, [rsp+450h+var_3E0]
0x180012f26  mov     rcx, rdi
0x180012f29  call    InsertErrorMessage
0x180012f2e  mov     rcx, rbx
0x180012f31  call    CloseLdapRequest
0x180012f36  lea     rcx, [rbx+30h]; lpCriticalSection
0x180012f3a  call    cs:__imp_EnterCriticalSection
0x180012f41  nop     dword ptr [rax+rax+00h]
0x180012f46  dec     dword ptr [rbx+10h]
0x180012f49  cmp     cs:g_fTracingOn, 0
0x180012f50  jnz     loc_1800135B5
0x180012f56  cmp     dword ptr [rbx+10h], 0
0x180012f5a  lea     rcx, [rbx+30h]; lpCriticalSection
0x180012f5e  jnz     short loc_180012FBD
0x180012f60  call    cs:__imp_LeaveCriticalSection
0x180012f67  nop     dword ptr [rax+rax+00h]
0x180012f6c  xor     edx, edx
0x180012f6e  mov     rcx, rbx
0x180012f71  call    DereferenceLdapRequest2
0x180012f76  test    esi, esi
0x180012f78  jnz     loc_1800135EC
0x180012f7e  test    r12, r12
0x180012f81  jnz     loc_1800135EC
0x180012f87  lea     rcx, [rbp+350h+var_3C0]; this
0x180012f8b  call    ??1CLdapBer@@QEAA@XZ; CLdapBer::~CLdapBer(void)
0x180012f90  mov     eax, esi
0x180012f92  mov     rsi, [rsp+450h+var_38]
0x180012f9a  mov     rcx, [rbp+350h+var_50]
0x180012fa1  xor     rcx, rsp; StackCookie
0x180012fa4  call    __security_check_cookie
0x180012fa9  add     rsp, 420h
0x180012fb0  pop     r15
0x180012fb2  pop     r14
0x180012fb4  pop     r13
0x180012fb6  pop     r12
0x180012fb8  pop     rdi
0x180012fb9  pop     rbx
0x180012fba  pop     rbp
0x180012fbb  retn
0x180012fbd  call    cs:__imp_LeaveCriticalSection
0x180012fc4  nop     dword ptr [rax+rax+00h]
0x180012fc9  jmp     short loc_180012F76
0x180012fcb  mov     r8d, 7530h
0x180012fd1  jmp     loc_180012DAB
0x180012fd6  test    rdx, rdx
0x180012fd9  jz      loc_180012F2E
0x180012fdf  jmp     loc_180012DE7
0x180012fe4  cmp     r15d, 7FFFh
0x180012feb  ja      loc_180013183
  ... truncated ...
```
