# LdapCheckControls

- ea: `0x180020320`
- end: `0x1800207e6`
- name: `LdapCheckControls`
- size: `1222`
- prototype: `__int64 __fastcall(struct ldap_request *, struct ldapcontrolW **, struct ldapcontrolW **, unsigned __int8, unsigned int)`
- caller_count: `9`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012ab0`
- `0x180015640`
- `0x1800308f8`
- `0x180039f4c`
- `0x18003c254`
- `0x18003e250`
- `0x18003edf4`
- `0x180040440`
- `0x180046f48`

## callees

- `0x1800037a8`
- `0x180015338`
- `0x180020320`
- `0x180020910`
- `0x1800227d8`
- `0x180024580`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180020406`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800204c9`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180020592`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180020406`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800204c9`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180020592`

## pseudocode

```c
__int64 __fastcall LdapCheckControls(
        struct ldap_request *a1,
        struct ldapcontrolW **a2,
        struct ldapcontrolW **a3,
        unsigned __int8 a4,
        unsigned int a5)
{
  char v5; // si
  unsigned __int8 v6; // bp
  struct ldapcontrolW **v8; // r12
  __m128i v10; // xmm6
  LDAPControlW **v11; // rcx
  char v13; // al
  struct ldapcontrolW *v14; // rbx
  struct ldapcontrolW **v15; // rdi
  bool v16; // zf
  __m128i *bv_val; // rax
  const wchar_t ***i; // r14
  const wchar_t **v19; // rbx
  char v20; // di
  bool v21; // zf
  const wchar_t *v22; // rcx
  int v23; // ecx
  __m128i *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // ebx
  char v27; // [rsp+C0h] [rbp+8h]

  v5 = 0;
  v6 = a4;
  v8 = a2;
  v10 = 0;
  if ( *((_BYTE *)a1 + 270) )
  {
    ldap_controls_freeW(*((LDAPControlW ***)a1 + 25));
    v11 = (LDAPControlW **)*((_QWORD *)a1 + 26);
    *((_QWORD *)a1 + 25) = 0;
    ldap_controls_freeW(v11);
    *((_QWORD *)a1 + 26) = 0;
    *((_BYTE *)a1 + 270) = 0;
  }
  if ( !v8 && !a3 && !a5 )
    return 0;
  v13 = 0;
  v27 = 0;
  if ( v8 )
  {
    v14 = *v8;
    if ( *v8 )
    {
      v15 = v8;
      do
      {
        if ( v6 )
          v16 = (unsigned __int8)ldapWStringsIdentical(v14->ldctl_oid, -1, L"1.2.840.113556.1.4.2330", -1) == 1;
        else
          v16 = CompareStringA(0x400u, 1u, (PCNZCH)v14->ldctl_oid, -1, "1.2.840.113556.1.4.2330", -1) == 2;
        if ( v16 && v14->ldctl_value.bv_len == 16 && (bv_val = (__m128i *)v14->ldctl_value.bv_val) != 0 )
        {
          v10 = *bv_val;
          v13 = 1;
          v27 = 1;
        }
        else
        {
          v13 = v27;
        }
        v14 = *++v15;
      }
      while ( *v15 );
      v8 = a2;
    }
  }
  if ( !a3 )
  {
LABEL_57:
    if ( v13 )
    {
      StringCchPrintfA(
        (STRSAFE_LPSTR)a1 + 112,
        0x25u,
        "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
        _mm_cvtsi128_si32(v10),
        _mm_extract_epi16(v10, 2),
        _mm_extract_epi16(v10, 3),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 8)),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 9)),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 10)),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 11)),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 12)),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 13)),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 14)),
        (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v10, 15)));
      v6 = a4;
    }
    v25 = a5;
    *((_BYTE *)a1 + 270) = 1;
    if ( v8 || (v26 = 0, a5) )
    {
      v26 = LdapDupControls(a1, (struct ldapcontrolW ***)a1 + 25, v8, v6, a5);
      if ( v26 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
          LDAPClientPrint(0x8000, "LdapCheckControls could not duplicate server control, error 0x%x\n", v26);
        return v26;
      }
      v25 = a5;
    }
    if ( a3 )
    {
      v26 = LdapDupControls(a1, (struct ldapcontrolW ***)a1 + 26, a3, v6, v25);
      if ( v26 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
          LDAPClientPrint(0x8000, "LdapCheckControls could not duplicate client control, error 0x%x\n", v26);
      }
    }
    return v26;
  }
  for ( i = (const wchar_t ***)a3; ; ++i )
  {
    v19 = *i;
    if ( !*i )
    {
      v13 = v27;
      goto LABEL_57;
    }
    v20 = 0;
    if ( v6 )
    {
      if ( (unsigned __int8)ldapWStringsIdentical(*v19, -1, L"1.2.840.113556.1.4.616", -1) != 1 )
      {
        v21 = (unsigned __int8)ldapWStringsIdentical(*v19, -1, L"1.2.840.113556.1.4.2330", -1) == 1;
        goto LABEL_42;
      }
    }
    else if ( CompareStringA(0x400u, 1u, (PCNZCH)*v19, -1, "1.2.840.113556.1.4.616", -1) != 2 )
    {
      v21 = CompareStringA(0x400u, 1u, (PCNZCH)*v19, -1, "1.2.840.113556.1.4.2330", -1) == 2;
LABEL_42:
      if ( v21 )
      {
        v5 = 1;
        if ( *((_DWORD *)v19 + 2) == 16 && (v24 = (__m128i *)v19[2]) != 0 )
        {
          v10 = *v24;
          v27 = 1;
        }
        else
        {
          v5 = 0;
        }
      }
      goto LABEL_47;
    }
    v20 = 1;
    if ( *((_DWORD *)v19 + 2) == 4 && (v22 = v19[2]) != 0 )
    {
      v23 = *(_DWORD *)v22;
      if ( v23 == 1 )
      {
        *((_BYTE *)a1 + 185) = 96;
      }
      else if ( v23 )
      {
        if ( (v23 & 0x60) == v23 )
          *((_BYTE *)a1 + 185) = v23;
        else
          v20 = 0;
      }
      else
      {
        *((_BYTE *)a1 + 185) = 0;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(
          0x800000,
          "LdapCheckControls set referrals to 0x%x for request 0x%x\n",
          *((unsigned __int8 *)a1 + 185),
          (_DWORD)a1);
    }
    else
    {
      v20 = 0;
    }
LABEL_47:
    if ( *((_BYTE *)v19 + 24) && !v20 && !v5 )
      break;
    v5 = 0;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
    LDAPClientPrint(0x8000000, "LdapCheckControls does not support client control '%S'\n", *v19);
  return 12;
}

```

## disassembly

```asm
0x180020320  mov     rax, rsp
0x180020323  mov     [rax+18h], rbx
0x180020327  mov     [rax+20h], r9b
0x18002032b  mov     [rax+10h], rdx
0x18002032f  push    rbp
0x180020330  push    rsi
0x180020331  push    rdi
0x180020332  push    r12
0x180020334  push    r13
0x180020336  push    r14
0x180020338  push    r15
0x18002033a  sub     rsp, 80h
0x180020341  xor     esi, esi
0x180020343  movaps  xmmword ptr [rax-48h], xmm6
0x180020347  mov     bpl, r9b
0x18002034a  mov     r13, r8
0x18002034d  mov     r12, rdx
0x180020350  mov     r15, rcx
0x180020353  xorps   xmm6, xmm6
0x180020356  cmp     [rcx+10Eh], sil
0x18002035d  jz      short loc_18002038C
0x18002035f  mov     rcx, [rcx+0C8h]; Control
0x180020366  call    ldap_controls_freeW
0x18002036b  mov     rcx, [r15+0D0h]; Control
0x180020372  mov     [r15+0C8h], rsi
0x180020379  call    ldap_controls_freeW
0x18002037e  mov     [r15+0D0h], rsi
0x180020385  mov     [r15+10Eh], sil
0x18002038c  test    r12, r12
0x18002038f  jnz     short loc_1800203A6
0x180020391  test    r13, r13
0x180020394  jnz     short loc_1800203A6
0x180020396  cmp     [rsp+0B8h+arg_20], esi
0x18002039d  jnz     short loc_1800203A6
0x18002039f  xor     eax, eax
0x1800203a1  jmp     loc_1800207C5
0x1800203a6  or      ecx, 0FFFFFFFFh
0x1800203a9  mov     al, sil
0x1800203ac  mov     [rsp+0B8h+arg_0], al
0x1800203b3  test    r12, r12
0x1800203b6  jz      loc_180020456
0x1800203bc  mov     rbx, [r12]
0x1800203c0  test    rbx, rbx
0x1800203c3  jz      loc_180020456
0x1800203c9  mov     rdi, r12
0x1800203cc  lea     r12, a12840113556142; "1.2.840.113556.1.4.2330"
0x1800203d3  mov     r9d, ecx; cchCount2
0x1800203d6  test    bpl, bpl
0x1800203d9  jz      short loc_1800203F0
0x1800203db  mov     edx, ecx; cchCount1
0x1800203dd  lea     r8, a12840113556142_0; "1.2.840.113556.1.4.2330"
0x1800203e4  mov     rcx, [rbx]; lpString1
0x1800203e7  call    ldapWStringsIdentical
0x1800203ec  cmp     al, 1
0x1800203ee  jmp     short loc_180020415
0x1800203f0  mov     r8, [rbx]; lpString1
0x1800203f3  mov     edx, 1; dwCmpFlags
0x1800203f8  mov     [rsp+0B8h+cchCount2], ecx; cchCount2
0x1800203fc  mov     ecx, 400h; Locale
0x180020401  mov     [rsp+0B8h+lpString2], r12; lpString2
0x180020406  call    cs:__imp_CompareStringA
0x18002040d  nop     dword ptr [rax+rax+00h]
0x180020412  cmp     eax, 2
0x180020415  jnz     short loc_180020434
0x180020417  cmp     dword ptr [rbx+8], 10h
0x18002041b  jnz     short loc_180020434
0x18002041d  mov     rax, [rbx+10h]
0x180020421  test    rax, rax
0x180020424  jz      short loc_180020434
0x180020426  movups  xmm6, xmmword ptr [rax]
0x180020429  mov     al, 1
0x18002042b  mov     [rsp+0B8h+arg_0], al
0x180020432  jmp     short loc_18002043B
0x180020434  mov     al, [rsp+0B8h+arg_0]
0x18002043b  add     rdi, 8
0x18002043f  mov     ecx, 0FFFFFFFFh
0x180020444  mov     rbx, [rdi]
0x180020447  test    rbx, rbx
0x18002044a  jnz     short loc_1800203D3
0x18002044c  mov     r12, [rsp+0B8h+arg_8]
0x180020454  or      ecx, ecx
0x180020456  test    r13, r13
0x180020459  jz      loc_180020623
0x18002045f  mov     r14, r13
0x180020462  mov     rbx, [r14]
0x180020465  test    rbx, rbx
0x180020468  jz      loc_18002061C
0x18002046e  mov     dil, sil
0x180020471  mov     r9d, ecx; cchCount2
0x180020474  test    bpl, bpl
0x180020477  jz      short loc_1800204AC
0x180020479  mov     edx, ecx; cchCount1
0x18002047b  lea     r8, a12840113556146; "1.2.840.113556.1.4.616"
0x180020482  mov     rcx, [rbx]; lpString1
0x180020485  call    ldapWStringsIdentical
0x18002048a  cmp     al, 1
0x18002048c  jz      short loc_1800204DE
0x18002048e  mov     rcx, [rbx]; lpString1
0x180020491  lea     r8, a12840113556142_0; "1.2.840.113556.1.4.2330"
0x180020498  or      eax, 0FFFFFFFFh
0x18002049b  mov     r9d, eax; cchCount2
0x18002049e  mov     edx, eax; cchCount1
0x1800204a0  call    ldapWStringsIdentical
0x1800204a5  cmp     al, 1
0x1800204a7  jmp     loc_1800205A1
0x1800204ac  mov     r8, [rbx]; lpString1
0x1800204af  lea     rax, a12840113556146_0; "1.2.840.113556.1.4.616"
0x1800204b6  mov     [rsp+0B8h+cchCount2], ecx; cchCount2
0x1800204ba  mov     edx, 1; dwCmpFlags
0x1800204bf  mov     ecx, 400h; Locale
0x1800204c4  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800204c9  call    cs:__imp_CompareStringA
0x1800204d0  nop     dword ptr [rax+rax+00h]
0x1800204d5  cmp     eax, 2
0x1800204d8  jnz     loc_180020571
0x1800204de  cmp     dword ptr [rbx+8], 4
0x1800204e2  mov     dil, 1
0x1800204e5  jnz     loc_18002056C
0x1800204eb  mov     rcx, [rbx+10h]
0x1800204ef  test    rcx, rcx
0x1800204f2  jz      short loc_18002056C
0x1800204f4  mov     ecx, [rcx]
0x1800204f6  cmp     ecx, 1
0x1800204f9  jnz     short loc_180020505
0x1800204fb  mov     byte ptr [r15+0B9h], 60h ; '`'
0x180020503  jmp     short loc_180020527
0x180020505  test    ecx, ecx
0x180020507  jnz     short loc_180020512
0x180020509  mov     [r15+0B9h], cl
0x180020510  jmp     short loc_180020527
0x180020512  mov     eax, ecx
0x180020514  and     eax, 60h
0x180020517  cmp     eax, ecx
0x180020519  jz      short loc_180020520
0x18002051b  xor     dil, dil
0x18002051e  jmp     short loc_180020527
0x180020520  mov     [r15+0B9h], cl
0x180020527  cmp     cs:g_fTracingOn, 0
0x18002052e  jz      loc_1800205C5
0x180020534  cmp     cs:g_fProviderEnabled, 0
0x18002053b  jz      loc_1800205C5
0x180020541  test    cs:g_ulTraceFlags, 800000h
0x18002054c  jz      short loc_1800205C5
0x18002054e  movzx   r8d, byte ptr [r15+0B9h]
0x180020556  lea     rdx, aLdapcheckcontr_2; "LdapCheckControls set referrals to 0x%x"...
0x18002055d  mov     r9, r15
0x180020560  mov     ecx, 800000h
0x180020565  call    LDAPClientPrint
0x18002056a  jmp     short loc_1800205C5
0x18002056c  xor     dil, dil
0x18002056f  jmp     short loc_1800205C5
0x180020571  mov     r8, [rbx]; lpString1
0x180020574  lea     rcx, a12840113556142; "1.2.840.113556.1.4.2330"
0x18002057b  or      eax, 0FFFFFFFFh
0x18002057e  mov     [rsp+0B8h+cchCount2], eax; cchCount2
0x180020582  mov     r9d, eax; cchCount1
0x180020585  mov     [rsp+0B8h+lpString2], rcx; lpString2
0x18002058a  mov     ecx, 400h; Locale
0x18002058f  lea     edx, [rax+2]; dwCmpFlags
0x180020592  call    cs:__imp_CompareStringA
0x180020599  nop     dword ptr [rax+rax+00h]
0x18002059e  cmp     eax, 2
0x1800205a1  jnz     short loc_1800205C5
0x1800205a3  cmp     dword ptr [rbx+8], 10h
0x1800205a7  mov     sil, 1
0x1800205aa  jnz     short loc_1800205C2
0x1800205ac  mov     rax, [rbx+10h]
0x1800205b0  test    rax, rax
0x1800205b3  jz      short loc_1800205C2
0x1800205b5  movups  xmm6, xmmword ptr [rax]
0x1800205b8  mov     [rsp+0B8h+arg_0], sil
0x1800205c0  jmp     short loc_1800205C5
0x1800205c2  xor     sil, sil
0x1800205c5  cmp     byte ptr [rbx+18h], 0
0x1800205c9  jz      short loc_1800205D5
0x1800205cb  test    dil, dil
0x1800205ce  jnz     short loc_1800205D5
0x1800205d0  test    sil, sil
0x1800205d3  jz      short loc_1800205E3
0x1800205d5  add     r14, 8
0x1800205d9  xor     esi, esi
0x1800205db  or      ecx, 0FFFFFFFFh
0x1800205de  jmp     loc_180020462
0x1800205e3  cmp     cs:g_fTracingOn, 0
0x1800205ea  jz      short loc_180020612
0x1800205ec  cmp     cs:g_fProviderEnabled, 0
0x1800205f3  jz      short loc_180020612
0x1800205f5  mov     ecx, 8000000h
0x1800205fa  test    cs:g_ulTraceFlags, rcx
0x180020601  jz      short loc_180020612
0x180020603  mov     r8, [rbx]
0x180020606  lea     rdx, aLdapcheckcontr_0; "LdapCheckControls does not support clie"...
0x18002060d  call    LDAPClientPrint
0x180020612  mov     eax, 0Ch
0x180020617  jmp     loc_1800207C5
0x18002061c  mov     al, [rsp+0B8h+arg_0]
0x180020623  test    al, al
0x180020625  jz      loc_18002070B
0x18002062b  movdqa  xmm0, xmm6
0x18002062f  lea     rcx, [r15+70h]; pszDest
0x180020633  psrldq  xmm0, 0Fh
0x180020638  movd    eax, xmm0
0x18002063c  movdqa  xmm0, xmm6
0x180020640  psrldq  xmm0, 0Eh
0x180020645  pextrw  r8d, xmm6, 3
0x18002064b  movzx   r14d, al
0x18002064f  movd    eax, xmm0
0x180020653  movdqa  xmm0, xmm6
0x180020657  psrldq  xmm0, 0Dh
0x18002065c  mov     [rsp+0B8h+var_50], r14d
0x180020661  movzx   ebp, al
0x180020664  movd    eax, xmm0
0x180020668  movdqa  xmm0, xmm6
0x18002066c  psrldq  xmm0, 0Ch
0x180020671  mov     [rsp+0B8h+var_58], ebp
0x180020675  movzx   esi, al
0x180020678  movd    eax, xmm0
0x18002067c  movdqa  xmm0, xmm6
0x180020680  psrldq  xmm0, 0Bh
0x180020685  mov     [rsp+0B8h+var_60], esi
0x180020689  movzx   edi, al
0x18002068c  movd    eax, xmm0
0x180020690  movdqa  xmm0, xmm6
0x180020694  psrldq  xmm0, 0Ah
0x180020699  mov     [rsp+0B8h+var_68], edi
0x18002069d  movzx   ebx, al
0x1800206a0  movd    eax, xmm0
0x1800206a4  movdqa  xmm0, xmm6
0x1800206a8  mov     [rsp+0B8h+var_70], ebx
0x1800206ac  psrldq  xmm0, 9
0x1800206b1  movzx   r11d, al
0x1800206b5  movd    eax, xmm0
0x1800206b9  movdqa  xmm0, xmm6
0x1800206bd  mov     [rsp+0B8h+var_78], r11d
0x1800206c2  pextrw  edx, xmm6, 2
0x1800206c7  movzx   r10d, al
0x1800206cb  mov     [rsp+0B8h+var_80], r10d
0x1800206d0  psrldq  xmm0, 8
0x1800206d5  movd    eax, xmm0
0x1800206d9  movzx   r9d, al
0x1800206dd  mov     [rsp+0B8h+var_88], r9d
0x1800206e2  mov     [rsp+0B8h+cchCount2], r8d
0x1800206e7  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x1800206ee  mov     dword ptr [rsp+0B8h+lpString2], edx
0x1800206f2  mov     edx, 25h ; '%'; cchDest
0x1800206f7  movd    r9d, xmm6
0x1800206fc  call    StringCchPrintfA
0x180020701  mov     bpl, [rsp+0B8h+arg_18]
0x180020709  xor     esi, esi
0x18002070b  mov     eax, [rsp+0B8h+arg_20]
0x180020712  mov     byte ptr [r15+10Eh], 1
0x18002071a  test    r12, r12
0x18002071d  jnz     short loc_180020725
0x18002071f  mov     ebx, esi
0x180020721  test    eax, eax
0x180020723  jz      short loc_180020772
0x180020725  lea     rdx, [r15+0C8h]; struct ldapcontrolW ***
0x18002072c  mov     dword ptr [rsp+0B8h+lpString2], eax; unsigned int
0x180020730  mov     r9b, bpl; unsigned __int8
0x180020733  mov     r8, r12; struct ldapcontrolW **
0x180020736  mov     rcx, r15; struct ldap_request *
0x180020739  call    ?LdapDupControls@@YAKPEAUldap_request@@PEAPEAPEAUldapcontrolW@@PEAPEAU2@EK@Z; LdapDupControls(ldap_request *,ldapcontrolW * * *,ldapcontrolW * *,uchar,ulong)
0x18002073e  mov     ebx, eax
0x180020740  test    eax, eax
0x180020742  jz      short loc_18002076B
0x180020744  cmp     cs:g_fTracingOn, esi
0x18002074a  jz      short loc_1800207C3
0x18002074c  cmp     cs:g_fProviderEnabled, esi
0x180020752  jz      short loc_1800207C3
0x180020754  mov     ecx, 8000h
0x180020759  test    cs:g_ulTraceFlags, rcx
0x180020760  jz      short loc_1800207C3
0x180020762  lea     rdx, aLdapcheckcontr_1; "LdapCheckControls could not duplicate s"...
0x180020769  jmp     short loc_1800207BB
0x18002076b  mov     eax, [rsp+0B8h+arg_20]
0x180020772  test    r13, r13
0x180020775  jz      short loc_1800207C3
0x180020777  lea     rdx, [r15+0D0h]; struct ldapcontrolW ***
0x18002077e  mov     dword ptr [rsp+0B8h+lpString2], eax; unsigned int
0x180020782  mov     r9b, bpl; unsigned __int8
0x180020785  mov     r8, r13; struct ldapcontrolW **
0x180020788  mov     rcx, r15; struct ldap_request *
0x18002078b  call    ?LdapDupControls@@YAKPEAUldap_request@@PEAPEAPEAUldapcontrolW@@PEAPEAU2@EK@Z; LdapDupControls(ldap_request *,ldapcontrolW * * *,ldapcontrolW * *,uchar,ulong)
0x180020790  mov     ebx, eax
0x180020792  test    eax, eax
0x180020794  jz      short loc_1800207C3
0x180020796  cmp     cs:g_fTracingOn, esi
0x18002079c  jz      short loc_1800207C3
0x18002079e  cmp     cs:g_fProviderEnabled, esi
0x1800207a4  jz      short loc_1800207C3
0x1800207a6  mov     ecx, 8000h
0x1800207ab  test    cs:g_ulTraceFlags, rcx
0x1800207b2  jz      short loc_1800207C3
0x1800207b4  lea     rdx, aLdapcheckcontr; "LdapCheckControls could not duplicate c"...
0x1800207bb  mov     r8d, ebx
0x1800207be  call    LDAPClientPrint
0x1800207c3  mov     eax, ebx
0x1800207c5  mov     rbx, [rsp+0B8h+arg_10]
0x1800207cd  movaps  xmm6, [rsp+0B8h+var_48]
0x1800207d2  add     rsp, 80h
  ... truncated ...
```
