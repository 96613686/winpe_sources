# LookupSidInTable

- ea: `0x180004f20`
- end: `0x180005723`
- name: `LookupSidInTable`
- size: `2051`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, PSID Sid@<rdx>, __int64, char, __int64)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180002fa0`
- `0x180003190`
- `0x180004260`
- `0x180005d00`
- `0x180006540`
- `0x180006680`
- `0x180008010`

## callees

- `0x180004f20`
- `0x180005730`
- `0x18000cbf8`
- `0x1800231e8`
- `0x18004f902`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180005162`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800051ed`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000520b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180005230`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000528a`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800052a4`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800052fc`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180005162`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800051ed`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000520b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180005230`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000528a`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800052a4`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800052fc`
- `ntdll!RtlValidSid` at `0x18000508c`
- `ntdll!RtlValidSid` at `0x180005443`
- `ntdll!RtlValidSid` at `0x18000508c`
- `ntdll!RtlValidSid` at `0x180005443`
- `ntdll!RtlEqualSid` at `0x180005000`
- `ntdll!RtlEqualSid` at `0x1800053d0`
- `ntdll!RtlEqualSid` at `0x180005000`
- `ntdll!RtlEqualSid` at `0x1800053d0`
- `ntdll!RtlSubAuthoritySid` at `0x1800050ea`
- `ntdll!RtlSubAuthoritySid` at `0x1800051a0`
- `ntdll!RtlSubAuthoritySid` at `0x180005389`
- `ntdll!RtlSubAuthoritySid` at `0x1800055ac`
- `ntdll!RtlSubAuthoritySid` at `0x180005704`
- `ntdll!RtlSubAuthoritySid` at `0x1800050ea`
- `ntdll!RtlSubAuthoritySid` at `0x1800051a0`
- `ntdll!RtlSubAuthoritySid` at `0x180005389`
- `ntdll!RtlSubAuthoritySid` at `0x1800055ac`
- `ntdll!RtlSubAuthoritySid` at `0x180005704`
- `ntdll!RtlSubAuthorityCountSid` at `0x180004f9a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800050dd`
- `ntdll!RtlSubAuthorityCountSid` at `0x180005192`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000537c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000559a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800056f6`
- `ntdll!RtlSubAuthorityCountSid` at `0x180004f9a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800050dd`
- `ntdll!RtlSubAuthorityCountSid` at `0x180005192`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000537c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000559a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800056f6`
- `ntdll!RtlLengthSid` at `0x1800050b6`
- `ntdll!RtlLengthSid` at `0x18000535d`
- `ntdll!RtlLengthSid` at `0x18000547a`
- `ntdll!RtlLengthSid` at `0x180005521`
- `ntdll!RtlLengthSid` at `0x180005562`
- `ntdll!RtlLengthSid` at `0x1800056b6`
- `ntdll!RtlLengthSid` at `0x1800050b6`
- `ntdll!RtlLengthSid` at `0x18000535d`
- `ntdll!RtlLengthSid` at `0x18000547a`
- `ntdll!RtlLengthSid` at `0x180005521`
- `ntdll!RtlLengthSid` at `0x180005562`
- `ntdll!RtlLengthSid` at `0x1800056b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000546c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000546c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056c6`

## pseudocode

```c
__int64 *__fastcall LookupSidInTable(wchar_t *String1, PSID Sid, _BYTE *a3, _BYTE *a4, __int64 a5, char a6, PSID *a7)
{
  _BYTE *v7; // rbp
  _BYTE *v8; // rdi
  PSID v9; // r14
  const wchar_t *v10; // r13
  unsigned int v11; // ebx
  BOOL v12; // r15d
  char v13; // r12
  __int64 v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // rcx
  __int64 *v17; // rdi
  void *v18; // rdx
  ULONG v19; // eax
  __int64 *v20; // rcx
  PUCHAR v21; // rax
  __int64 *v22; // rsi
  __int64 *result; // rax
  PUCHAR v24; // rax
  int v25; // edx
  unsigned int i; // esi
  __int64 v27; // rbx
  int v28; // eax
  unsigned __int8 *v29; // rbx
  int v30; // eax
  ULONG v31; // eax
  PUCHAR v32; // rax
  PULONG v33; // rax
  ULONG v34; // eax
  int v35; // eax
  int v36; // eax
  ULONG v37; // eax
  __int64 v38; // rax
  PSID v39; // rcx
  ULONG v40; // eax
  __int64 v41; // rax
  PUCHAR v42; // rax
  __int64 *v43; // rbx
  ULONG v44; // edi
  HLOCAL v45; // rax
  PUCHAR v46; // rax
  int v47; // [rsp+20h] [rbp-58h]
  BOOL v48; // [rsp+24h] [rbp-54h]
  int String1b; // [rsp+80h] [rbp+8h]

  v7 = a4;
  v8 = a3;
  v9 = Sid;
  v10 = String1;
  if ( __PAIR128__((unsigned __int64)String1, (unsigned __int64)Sid) == 0 )
    return 0;
  v11 = 0;
  v12 = 0;
  *a7 = 0;
  v48 = 0;
  if ( String1 )
  {
    v13 = 0;
    if ( _wcsnicmp(String1, L"EA", 2u) )
    {
      if ( _wcsnicmp(v10, L"SA", 2u) )
      {
        if ( _wcsnicmp(v10, L"RO", 2u) )
          v12 = _wcsnicmp(v10, L"EK", 2u) == 0;
        else
          v12 = 1;
      }
      else
      {
        v12 = 1;
        v48 = 1;
      }
    }
    else
    {
      v12 = 1;
    }
  }
  else
  {
    v13 = 1;
    if ( *RtlSubAuthorityCountSid(Sid) )
    {
      v24 = RtlSubAuthorityCountSid(v9);
      v14 = *RtlSubAuthoritySid(v9, (unsigned int)*v24 - 1);
      if ( (unsigned int)(v14 - 498) <= 0x1D )
      {
        v25 = 540016641;
        if ( _bittest(&v25, v14 - 498) )
        {
          v12 = 1;
          v48 = v14 == 518;
        }
      }
    }
  }
  if ( v7 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 0xF )
      {
LABEL_76:
        v9 = Sid;
        v11 = 0;
        v10 = String1;
        v8 = a3;
        break;
      }
      v27 = 104LL * i;
      if ( v13 )
      {
        v28 = 0;
      }
      else
      {
        if ( _wcsnicmp(String1, (const wchar_t *)(v27 + a5 + 2), *(unsigned int *)(v27 + a5 + 12)) )
          continue;
        v28 = 1;
      }
      v29 = (unsigned __int8 *)(a5 + v27);
      v47 = v28;
      v14 = *v29;
      if ( !(_BYTE)v14 || !*((_QWORD *)v29 + 2) )
      {
        v30 = *((_DWORD *)v29 + 7);
        if ( v30 )
        {
          if ( v30 != 7 || !a3 )
            goto LABEL_76;
          v7 = a3;
        }
        *((_QWORD *)v29 + 2) = v29 + 32;
        if ( v7[1] < 0xFu )
        {
          v31 = RtlLengthSid(v7);
          memcpy_0(*((void **)v29 + 2), v7, v31);
          ++*(_BYTE *)(*((_QWORD *)v29 + 2) + 1LL);
          v32 = RtlSubAuthorityCountSid(v7);
          v33 = RtlSubAuthoritySid(*((PSID *)v29 + 2), *v32);
          v14 = 104LL * i;
          LOBYTE(v14) = 1;
          *v33 = *(_DWORD *)(104LL * i + a5 + 24);
          *(_BYTE *)(104LL * i + a5) = 1;
        }
        v7 = a4;
        v28 = v47;
      }
      if ( v13 )
      {
        if ( (_BYTE)v14 == 1 )
        {
          v14 = *(_QWORD *)(104LL * i + a5 + 16);
          if ( v14 )
          {
            if ( RtlEqualSid((PSID)v14, Sid) )
              return (__int64 *)v29;
          }
        }
      }
      else if ( v28 )
      {
        result = 0;
        if ( (_BYTE)v14 == 1 )
          return (__int64 *)v29;
        return result;
      }
    }
  }
  v15 = 68;
  LOBYTE(v14) = 1;
  String1b = 68;
  InitializeSidLookupTable(v14);
  if ( v12 && !v8 && !a6 && (!RootDomInited || !RtlValidSid(RootDomSidBuf)) )
    SddlpGetRootDomainSid();
  do
  {
    if ( !v12 )
    {
      if ( v7 )
      {
        v16 = 104LL * v11;
        if ( !*(_DWORD *)((char *)&qword_180079EE0[3] + v16 + 4) )
          goto LABEL_44;
      }
    }
    v17 = &qword_180079EE0[13 * v11];
    if ( *(_BYTE *)v17 )
    {
      v18 = (void *)v17[2];
      if ( v18 )
        goto LABEL_10;
    }
    if ( *((_DWORD *)v17 + 7) == 7 && v12 )
    {
      if ( a3 )
      {
        if ( a3[1] >= 0xFu )
          goto LABEL_14;
        EnterCriticalSection(&SddlSidLookupCritical);
        v34 = RtlLengthSid(a3);
        memcpy_0((void *)v17[2], a3, v34);
        v20 = (__int64 *)a3;
      }
      else
      {
        if ( a6 || !RootDomInited || !RtlValidSid(RootDomSidBuf) || *(_BYTE *)v17 && v17[2] )
          goto LABEL_14;
        EnterCriticalSection(&SddlSidLookupCritical);
        v19 = RtlLengthSid(RootDomSidBuf);
        memcpy_0((void *)v17[2], RootDomSidBuf, v19);
        v20 = RootDomSidBuf;
      }
      ++*(_BYTE *)(v17[2] + 1);
      v21 = RtlSubAuthorityCountSid(v20);
      *RtlSubAuthoritySid((PSID)v17[2], *v21) = *((_DWORD *)v17 + 6);
      *(_BYTE *)v17 = 1;
      LeaveCriticalSection(&SddlSidLookupCritical);
    }
LABEL_14:
    if ( !v13 )
      goto LABEL_33;
    if ( !*(_BYTE *)v17 )
      goto LABEL_12;
    v18 = (void *)v17[2];
    if ( !v18 )
      goto LABEL_12;
LABEL_10:
    if ( v13 )
    {
      if ( RtlEqualSid(v9, v18) )
        goto LABEL_31;
      goto LABEL_12;
    }
LABEL_33:
    if ( !_wcsnicmp(v10, (const wchar_t *)v17 + 1, *((unsigned int *)v17 + 3)) )
    {
      if ( *(_BYTE *)v17 && v17[2] )
      {
LABEL_31:
        v22 = &qword_180079EE0[13 * v11];
        goto LABEL_32;
      }
      v35 = *((_DWORD *)v17 + 7);
      if ( v35 && v35 != 3 )
      {
LABEL_35:
        v9 = Sid;
LABEL_12:
        v7 = a4;
LABEL_43:
        v15 = String1b;
        goto LABEL_44;
      }
      EnterCriticalSection(&SddlSidLookupCritical);
      if ( !LOBYTE(qword_180079EE0[13 * v11]) || !v17[2] )
      {
        CacheDomainAndDnsDomainSids();
        v17[2] = (__int64)(v17 + 4);
        v36 = *((_DWORD *)v17 + 7);
        if ( v36 )
        {
          if ( v36 != 3 || !gbDomainSidCached )
            goto LABEL_97;
          v37 = RtlLengthSid(Src);
          memcpy_0((void *)qword_180079EE0[13 * v11 + 2], Src, v37);
          v38 = qword_180079EE0[13 * v11 + 2];
          ++*(_BYTE *)(v38 + 1);
          v39 = Src;
          goto LABEL_95;
        }
        if ( gbDnsDomainSidCached )
        {
          v40 = RtlLengthSid(::Sid);
          memcpy_0((void *)qword_180079EE0[13 * v11 + 2], ::Sid, v40);
          v41 = qword_180079EE0[13 * v11 + 2];
          ++*(_BYTE *)(v41 + 1);
          v39 = ::Sid;
LABEL_95:
          v42 = RtlSubAuthorityCountSid(v39);
          *RtlSubAuthoritySid((PSID)qword_180079EE0[13 * v11 + 2], *v42) = qword_180079EE0[13 * v11 + 3];
          LOBYTE(qword_180079EE0[13 * v11]) = 1;
        }
      }
LABEL_97:
      LeaveCriticalSection(&SddlSidLookupCritical);
      if ( LOBYTE(qword_180079EE0[13 * v11]) && qword_180079EE0[13 * v11 + 2] )
        goto LABEL_31;
      v9 = Sid;
      goto LABEL_12;
    }
    if ( !v12 )
      goto LABEL_35;
    if ( !a6 )
      goto LABEL_35;
    if ( a3 )
      goto LABEL_35;
    v16 = (__int64)qword_180079EE0;
    if ( !LOBYTE(qword_180079EE0[13 * v11]) || !v17[2] )
      goto LABEL_35;
    v9 = Sid;
    v7 = a4;
    if ( _wcsnicmp(L"DA", (const wchar_t *)v17 + 1, *((unsigned int *)v17 + 3)) )
      goto LABEL_43;
    v15 = v11;
    String1b = v11;
LABEL_44:
    ++v11;
  }
  while ( v11 < 0x44 );
  if ( !v12 || !a6 || a3 || v15 >= 0x44 )
    goto LABEL_46;
  if ( v48 )
  {
    if ( v13 )
    {
      *a7 = v9;
    }
    else
    {
      v43 = &qword_180079EE0[13 * v15];
      v16 = v43[2];
      if ( v16 )
      {
        v44 = RtlLengthSid((PSID)v16);
        v45 = LocalAlloc(0x40u, v44 + 1);
        *a7 = v45;
        if ( v45 )
        {
          _mm_lfence();
          memcpy_0(v45, (const void *)v43[2], v44);
          v46 = RtlSubAuthorityCountSid((PSID)v43[2]);
          *RtlSubAuthoritySid(*a7, (unsigned int)*v46 - 1) = 518;
        }
      }
    }
LABEL_46:
    v22 = 0;
  }
  else
  {
    v22 = &qword_180079EE0[13 * v15];
  }
LABEL_32:
  LOBYTE(v16) = 2;
  InitializeSidLookupTable(v16);
  return v22;
}

```

## disassembly

```asm
0x180004f20  mov     [rsp+arg_18], r9
0x180004f25  mov     [rsp+Sid], r8
0x180004f2a  mov     [rsp+Sid2], rdx
0x180004f2f  mov     [rsp+String1], rcx
0x180004f34  push    rbp
0x180004f35  push    rdi
0x180004f36  push    r13
0x180004f38  push    r14
0x180004f3a  sub     rsp, 58h
0x180004f3e  mov     rbp, r9
0x180004f41  mov     rdi, r8
0x180004f44  mov     r14, rdx
0x180004f47  mov     r13, rcx
0x180004f4a  test    rcx, rcx
0x180004f4d  jnz     short loc_180004F58
0x180004f4f  test    rdx, rdx
0x180004f52  jz      loc_180005182
0x180004f58  mov     [rsp+78h+var_28], rbx
0x180004f5d  xor     ebx, ebx
0x180004f5f  mov     [rsp+78h+var_30], rsi
0x180004f64  mov     rsi, [rsp+78h+arg_30]
0x180004f6c  mov     [rsp+78h+var_38], r12
0x180004f71  mov     [rsp+78h+var_40], r15
0x180004f76  mov     r15d, ebx
0x180004f79  mov     [rsp+78h+var_50], rbx
0x180004f7e  mov     [rsi], rbx
0x180004f81  mov     esi, 1
0x180004f86  mov     [rsp+78h+var_54], ebx
0x180004f8a  test    r13, r13
0x180004f8d  jnz     loc_1800051DD
0x180004f93  mov     rcx, r14; Sid
0x180004f96  movzx   r12d, sil
0x180004f9a  call    cs:__imp_RtlSubAuthorityCountSid
0x180004fa0  cmp     [rax], bl
0x180004fa2  ja      loc_18000518F
0x180004fa8  test    rbp, rbp
0x180004fab  jnz     loc_1800052C5
0x180004fb1  mov     esi, 44h ; 'D'
0x180004fb6  mov     cl, 1
0x180004fb8  mov     dword ptr [rsp+78h+String1], esi
0x180004fbf  call    InitializeSidLookupTable
0x180004fc4  test    r15d, r15d
0x180004fc7  jnz     loc_18000541D
0x180004fcd  lea     rdi, qword_180079EE0
0x180004fd4  test    r15d, r15d
0x180004fd7  jz      short loc_180005043
0x180004fd9  mov     ebp, ebx
0x180004fdb  imul    rax, rbp, 68h ; 'h'
0x180004fdf  lea     rsi, [rax+rdi]
0x180004fe3  add     rdi, rax
0x180004fe6  cmp     byte ptr [rsi], 0
0x180004fe9  jz      short loc_180005022
0x180004feb  mov     rdx, [rdi+10h]; Sid2
0x180004fef  test    rdx, rdx
0x180004ff2  jz      short loc_180005022
0x180004ff4  test    r12b, r12b
0x180004ff7  jz      loc_180005157
0x180004ffd  mov     rcx, r14; Sid1
0x180005000  call    cs:__imp_RtlEqualSid
0x180005006  lea     rdi, qword_180079EE0
0x18000500d  test    al, al
0x18000500f  jnz     loc_180005125
0x180005015  mov     rbp, [rsp+78h+arg_18]
0x18000501d  jmp     loc_180005255
0x180005022  cmp     dword ptr [rdi+1Ch], 7
0x180005026  jz      short loc_18000505E
0x180005028  test    r12b, r12b
0x18000502b  jz      loc_180005157
0x180005031  cmp     byte ptr [rsi], 0
0x180005034  jnz     loc_1800054A1
0x18000503a  lea     rdi, qword_180079EE0
0x180005041  jmp     short loc_180005015
0x180005043  test    rbp, rbp
0x180005046  jz      short loc_180004FD9
0x180005048  mov     eax, ebx
0x18000504a  imul    rcx, rax, 68h ; 'h'
0x18000504e  cmp     dword ptr [rcx+rdi+1Ch], 0
0x180005053  jz      loc_18000525C
0x180005059  jmp     loc_180004FD9
0x18000505e  test    r15d, r15d
0x180005061  jz      short loc_180005028
0x180005063  mov     rax, [rsp+78h+Sid]
0x18000506b  test    rax, rax
0x18000506e  jnz     loc_18000545B
0x180005074  cmp     [rsp+78h+arg_28], al
0x18000507b  jnz     short loc_180005028
0x18000507d  cmp     cs:RootDomInited, eax
0x180005083  jz      short loc_180005028
0x180005085  lea     rcx, RootDomSidBuf; Sid
0x18000508c  call    cs:__imp_RtlValidSid
0x180005092  test    al, al
0x180005094  jz      short loc_180005028
0x180005096  cmp     byte ptr [rsi], 0
0x180005099  jz      short loc_1800050A2
0x18000509b  cmp     qword ptr [rdi+10h], 0
0x1800050a0  jnz     short loc_180005028
0x1800050a2  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x1800050a9  call    cs:__imp_EnterCriticalSection
0x1800050af  lea     rcx, RootDomSidBuf; Sid
0x1800050b6  call    cs:__imp_RtlLengthSid
0x1800050bc  mov     rcx, [rdi+10h]; void *
0x1800050c0  lea     rdx, RootDomSidBuf; Src
0x1800050c7  mov     r8d, eax; Size
0x1800050ca  call    memcpy_0
0x1800050cf  lea     rcx, RootDomSidBuf; Sid
0x1800050d6  mov     rax, [rdi+10h]
0x1800050da  inc     byte ptr [rax+1]
0x1800050dd  call    cs:__imp_RtlSubAuthorityCountSid
0x1800050e3  mov     rcx, [rdi+10h]; Sid
0x1800050e7  movzx   edx, byte ptr [rax]; SubAuthority
0x1800050ea  call    cs:__imp_RtlSubAuthoritySid
0x1800050f0  mov     ecx, [rdi+18h]
0x1800050f3  mov     [rax], ecx
0x1800050f5  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x1800050fc  mov     byte ptr [rsi], 1
0x1800050ff  call    cs:__imp_LeaveCriticalSection
0x180005105  jmp     loc_180005028
0x18000510a  cmp     byte ptr [rsi], 0
0x18000510d  jz      loc_1800054B3
0x180005113  cmp     qword ptr [rdi+10h], 0
0x180005118  jz      loc_1800054B3
0x18000511e  lea     rdi, qword_180079EE0
0x180005125  mov     eax, ebx
0x180005127  imul    rsi, rax, 68h ; 'h'
0x18000512b  add     rsi, rdi
0x18000512e  mov     cl, 2
0x180005130  call    InitializeSidLookupTable
0x180005135  mov     rax, rsi
0x180005138  mov     r12, [rsp+78h+var_38]
0x18000513d  mov     rsi, [rsp+78h+var_30]
0x180005142  mov     rbx, [rsp+78h+var_28]
0x180005147  mov     r15, [rsp+78h+var_40]
0x18000514c  add     rsp, 58h
0x180005150  pop     r14
0x180005152  pop     r13
0x180005154  pop     rdi
0x180005155  pop     rbp
0x180005156  retn
0x180005157  mov     r8d, [rdi+0Ch]; MaxCount
0x18000515b  lea     rdx, [rsi+2]; String2
0x18000515f  mov     rcx, r13; String1
0x180005162  call    cs:__imp__wcsnicmp
0x180005168  test    eax, eax
0x18000516a  jz      short loc_18000510A
0x18000516c  test    r15d, r15d
0x18000516f  jnz     loc_18000560A
0x180005175  mov     r14, [rsp+78h+Sid2]
0x18000517d  jmp     loc_18000503A
0x180005182  xor     eax, eax
0x180005184  add     rsp, 58h
0x180005188  pop     r14
0x18000518a  pop     r13
0x18000518c  pop     rdi
0x18000518d  pop     rbp
0x18000518e  retn
0x18000518f  mov     rcx, r14; Sid
0x180005192  call    cs:__imp_RtlSubAuthorityCountSid
0x180005198  mov     rcx, r14; Sid
0x18000519b  movzx   edx, byte ptr [rax]
0x18000519e  dec     edx; SubAuthority
0x1800051a0  call    cs:__imp_RtlSubAuthoritySid
0x1800051a6  mov     ecx, [rax]; String1
0x1800051a8  lea     eax, [rcx-1F2h]
0x1800051ae  cmp     eax, 1Dh
0x1800051b1  ja      loc_180004FA8
0x1800051b7  mov     edx, 20300001h
0x1800051bc  bt      edx, eax
0x1800051bf  jnb     loc_180004FA8
0x1800051c5  mov     r15d, esi
0x1800051c8  cmp     ecx, 206h
0x1800051ce  jnz     loc_180004FA8
0x1800051d4  mov     [rsp+78h+var_54], esi
0x1800051d8  jmp     loc_180004FA8
0x1800051dd  mov     r8d, 2; MaxCount
0x1800051e3  lea     rdx, aEa; "EA"
0x1800051ea  xor     r12b, r12b
0x1800051ed  call    cs:__imp__wcsnicmp
0x1800051f3  test    eax, eax
0x1800051f5  jz      loc_1800052B5
0x1800051fb  mov     r8d, 2; MaxCount
0x180005201  lea     rdx, aSa; "SA"
0x180005208  mov     rcx, r13; String1
0x18000520b  call    cs:__imp__wcsnicmp
0x180005211  test    eax, eax
0x180005213  jnz     short loc_18000527A
0x180005215  mov     r15d, esi
0x180005218  mov     [rsp+78h+var_54], esi
0x18000521c  jmp     loc_180004FA8
0x180005221  mov     r8d, [rdi+0Ch]; MaxCount
0x180005225  lea     rdx, [rsi+2]; String2
0x180005229  lea     rcx, aDa; "DA"
0x180005230  call    cs:__imp__wcsnicmp
0x180005236  mov     r14, [rsp+78h+Sid2]
0x18000523e  lea     rdi, qword_180079EE0
0x180005245  mov     rbp, [rsp+78h+arg_18]
0x18000524d  test    eax, eax
0x18000524f  jz      loc_18000564C
0x180005255  mov     esi, dword ptr [rsp+78h+String1]
0x18000525c  inc     ebx
0x18000525e  cmp     ebx, 44h ; 'D'
0x180005261  jb      loc_180004FD4
0x180005267  test    r15d, r15d
0x18000526a  jnz     loc_18000565A
0x180005270  mov     rsi, [rsp+78h+var_50]
0x180005275  jmp     loc_18000512E
0x18000527a  mov     r8d, 2; MaxCount
0x180005280  lea     rdx, aRo; "RO"
0x180005287  mov     rcx, r13; String1
0x18000528a  call    cs:__imp__wcsnicmp
0x180005290  test    eax, eax
0x180005292  jz      short loc_1800052BD
0x180005294  mov     r8d, 2; MaxCount
0x18000529a  lea     rdx, aEk; "EK"
0x1800052a1  mov     rcx, r13; String1
0x1800052a4  call    cs:__imp__wcsnicmp
0x1800052aa  test    eax, eax
0x1800052ac  cmovz   r15d, esi
0x1800052b0  jmp     loc_180004FA8
0x1800052b5  mov     r15d, esi
0x1800052b8  jmp     loc_180004FA8
0x1800052bd  mov     r15d, esi
0x1800052c0  jmp     loc_180004FA8
0x1800052c5  mov     r14, [rsp+78h+arg_20]
0x1800052cd  mov     esi, ebx
0x1800052cf  cmp     esi, 0Fh
0x1800052d2  jnb     loc_1800053FE
0x1800052d8  mov     r13d, esi
0x1800052db  imul    rbx, r13, 68h ; 'h'
0x1800052df  test    r12b, r12b
0x1800052e2  jz      short loc_1800052E8
0x1800052e4  xor     eax, eax
0x1800052e6  jmp     short loc_18000530F
0x1800052e8  mov     r8d, [rbx+r14+0Ch]; MaxCount
0x1800052ed  lea     rdx, [r14+2]
0x1800052f1  mov     rcx, [rsp+78h+String1]; String1
0x1800052f9  add     rdx, rbx; String2
0x1800052fc  call    cs:__imp__wcsnicmp
0x180005302  test    eax, eax
0x180005304  jnz     loc_1800053F7
0x18000530a  mov     eax, 1
0x18000530f  add     rbx, r14
0x180005312  mov     [rsp+78h+var_58], eax
0x180005316  movzx   ecx, byte ptr [rbx]
0x180005319  test    cl, cl
0x18000531b  jz      short loc_180005328
0x18000531d  cmp     qword ptr [rbx+10h], 0
0x180005322  jnz     loc_1800053B0
0x180005328  mov     eax, [rbx+1Ch]
0x18000532b  test    eax, eax
0x18000532d  jz      short loc_18000534C
0x18000532f  cmp     eax, 7
0x180005332  jnz     loc_1800053FE
0x180005338  mov     rax, [rsp+78h+Sid]
0x180005340  test    rax, rax
0x180005343  jz      loc_1800053FE
0x180005349  mov     rbp, rax
0x18000534c  lea     rax, [rbx+20h]
0x180005350  mov     [rbx+10h], rax
0x180005354  cmp     byte ptr [rbp+1], 0Fh
0x180005358  jnb     short loc_1800053A4
0x18000535a  mov     rcx, rbp; Sid
0x18000535d  call    cs:__imp_RtlLengthSid
0x180005363  mov     rcx, [rbx+10h]; void *
0x180005367  mov     rdx, rbp; Src
0x18000536a  mov     r8d, eax; Size
0x18000536d  call    memcpy_0
0x180005372  mov     rax, [rbx+10h]
0x180005376  mov     rcx, rbp; Sid
0x180005379  inc     byte ptr [rax+1]
0x18000537c  call    cs:__imp_RtlSubAuthorityCountSid
0x180005382  mov     rcx, [rbx+10h]; Sid
0x180005386  movzx   edx, byte ptr [rax]; SubAuthority
0x180005389  call    cs:__imp_RtlSubAuthoritySid
0x18000538f  imul    rcx, r13, 68h ; 'h'
0x180005393  mov     edx, [rcx+r14+18h]
0x180005398  mov     cl, 1
0x18000539a  mov     [rax], edx
0x18000539c  imul    rax, r13, 68h ; 'h'
0x1800053a0  mov     [rax+r14], cl
0x1800053a4  mov     rbp, [rsp+78h+arg_18]
0x1800053ac  mov     eax, [rsp+78h+var_58]
0x1800053b0  test    r12b, r12b
0x1800053b3  jz      short loc_1800053E2
0x1800053b5  cmp     cl, 1
0x1800053b8  jnz     short loc_1800053F7
0x1800053ba  imul    rax, r13, 68h ; 'h'
0x1800053be  mov     rcx, [rax+r14+10h]; Sid1
0x1800053c3  test    rcx, rcx
0x1800053c6  jz      short loc_1800053F7
0x1800053c8  mov     rdx, [rsp+78h+Sid2]; Sid2
0x1800053d0  call    cs:__imp_RtlEqualSid
0x1800053d6  test    al, al
0x1800053d8  jz      short loc_1800053F7
0x1800053da  mov     rax, rbx
0x1800053dd  jmp     loc_180005138
0x1800053e2  test    eax, eax
0x1800053e4  jz      short loc_1800053F7
0x1800053e6  mov     rax, [rsp+78h+var_50]
0x1800053eb  cmp     cl, 1
0x1800053ee  cmovz   rax, rbx
  ... truncated ...
```
