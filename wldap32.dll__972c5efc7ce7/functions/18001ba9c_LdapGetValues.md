# LdapGetValues

- ea: `0x18001ba9c`
- end: `0x18001c2c8`
- name: `LdapGetValues`
- size: `2092`
- prototype: `__int64 __usercall@<rax>(struct ldap_connection *@<rcx>, char, __int64)`
- caller_count: `7`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800057a0`
- `0x18000b860`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18001b970`
- `0x18002ae10`
- `0x1800488d0`

## callees

- `0x1800014e0`
- `0x180001820`
- `0x1800022c0`
- `0x180002770`
- `0x1800030f0`
- `0x1800032d0`
- `0x1800037a8`
- `0x180005134`
- `0x1800061a0`
- `0x180006510`
- `0x18000b440`
- `0x180014460`
- `0x18001ba9c`
- `0x18001ce90`
- `0x18001e2c0`
- `0x180020910`
- `0x18002df60`
- `0x180031c98`
- `0x180034510`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb25`

## string_xrefs

- `0x18001bbdd`: `LdapGetValues AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n`
- `0x18001bba2`: `LdapGetValues could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n`
- `0x18001bc31`: `LdapGetValues no per-thread entry, connection 0x%x, thread 0x%x.\n`
- `0x18001bdec`: `LdapGetValues 1 connection 0x%x received protocol error 0x%x .\n`
- `0x18001bcef`: `LdapGetValues 2 connection 0x%x received protocol error 0x%x .\n`
- `0x18001be3c`: `LdapGetValues 8 connection 0x%x received protocol error 0x%x .\n`

## pseudocode

```c
__int64 __fastcall LdapGetValues(struct ldap_connection *a1, __int64 a2, const WCHAR *a3, char a4, char a5, PCHAR **a6)
{
  PCHAR *v6; // r14
  DWORD CurrentThreadId; // edi
  CLdapBer *v12; // rbx
  unsigned int v13; // r13d
  __int64 CurrentPerThreadEntry; // rbx
  unsigned int Value; // ebx
  const WCHAR *i; // rbx
  __int64 v17; // r15
  unsigned int Sequence; // eax
  unsigned int v19; // edx
  int v20; // eax
  unsigned int Attribute; // eax
  unsigned int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // r9d
  __int64 v25; // rdi
  void *v26; // r12
  unsigned __int64 v27; // rcx
  void *v28; // rax
  void *v29; // rbx
  unsigned int ValueWithAlloc; // eax
  unsigned int v31; // eax
  const char *v32; // r8
  unsigned __int64 v33; // rcx
  void *v34; // rax
  void *v35; // rbx
  unsigned __int64 v36; // rcx
  void *v37; // rax
  void *v38; // rbx
  unsigned __int8 v39; // [rsp+20h] [rbp-E0h]
  struct berval *v41; // [rsp+38h] [rbp-C8h] BYREF
  CLdapBer *v42; // [rsp+40h] [rbp-C0h]
  unsigned int v43; // [rsp+48h] [rbp-B8h]
  PCHAR **v44; // [rsp+50h] [rbp-B0h]
  WCHAR String1[800]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  LODWORD(v41) = 0;
  v44 = a6;
  v43 = *((_DWORD *)a1 + 272);
  *a6 = 0;
  if ( !a2 )
    return 89;
  if ( *(_DWORD *)(a2 + 4) != 100 )
  {
    SetConnectionError(a1, 84);
    return 84;
  }
  CurrentThreadId = GetCurrentThreadId();
  SetConnectionError(a1, 0);
  v12 = *(CLdapBer **)(a2 + 8);
  v42 = v12;
  v13 = 2;
  if ( CLdapBer::HrPeekTag(v12, (unsigned int *)&v41) == 16 || (_DWORD)v41 != 49 )
    goto LABEL_38;
  CurrentPerThreadEntry = GetCurrentPerThreadEntry();
  if ( CurrentPerThreadEntry )
  {
LABEL_24:
    EnterCriticalSection(&PerThreadListLock);
    for ( i = *(const WCHAR **)(CurrentPerThreadEntry + 32);
          i && *((struct ldap_connection **)i + 2) != a1;
          i = *(const WCHAR **)i )
    {
      ;
    }
    LeaveCriticalSection(&PerThreadListLock);
    if ( i && (unsigned __int8)ldapWStringsIdentical(i + 420, -1, a3, -1) == 1 )
    {
      v17 = 0;
LABEL_31:
      Sequence = CLdapBer::HrStartReadSequence(v42, 0x31u, 0);
      Value = Sequence;
      if ( Sequence )
      {
LABEL_32:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientPrint(0x400000, "LdapGetValues 2 connection 0x%x received protocol error 0x%x .\n", a1, Sequence);
LABEL_36:
        SetConnectionError(a1, 84);
        goto LABEL_114;
      }
      v25 = 0;
      v26 = 0;
      v19 = -1;
      if ( a4 )
      {
        while ( 1 )
        {
          v41 = 0;
          if ( !v26 || (unsigned int)v25 >= v13 - 1 )
          {
            v13 *= 2;
            v27 = 8LL * v13;
            if ( v27 > 0xFFFFFFFF )
              goto LABEL_108;
            v28 = (void *)ldapMalloc(v27, 1819039308);
            v29 = v28;
            if ( !v28 )
              goto LABEL_108;
            if ( v26 )
            {
              memcpy_0(v28, v26, 8LL * (unsigned int)v25);
              ldapFree(v26, 1819039308);
            }
            v26 = v29;
          }
          ValueWithAlloc = CLdapBer::HrGetValueWithAlloc(v42, &v41, 0);
          Value = ValueWithAlloc;
          if ( ValueWithAlloc )
            goto LABEL_70;
          v19 = -1;
          *((_QWORD *)v26 + v25) = v41;
          v25 = (unsigned int)(v25 + 1);
          if ( !*((_BYTE *)a1 + 644) )
          {
            v31 = v43;
            if ( (unsigned int)v25 >= v43 )
              break;
          }
        }
        if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x200000) == 0 )
          goto LABEL_75;
        v32 = "LdapGetValues:563";
      }
      else
      {
        if ( !a5 )
        {
          while ( 1 )
          {
            v41 = 0;
            if ( !v26 || (unsigned int)v25 >= v13 - 1 )
            {
              v13 *= 2;
              v36 = 8LL * v13;
              if ( v36 > 0xFFFFFFFF || (v37 = (void *)ldapMalloc(v36, 1819039308), (v38 = v37) == 0) )
              {
LABEL_108:
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
                  LDAPClientPrint(
                    0x4000,
                    "LdapGetValues 3 connection 0x%x could not allocate memory for result table size 0x%x .\n",
                    (_DWORD)a1,
                    v13);
                Value = 90;
                if ( v26 )
                  goto LABEL_113;
                goto LABEL_114;
              }
              if ( v26 )
              {
                memcpy_0(v37, v26, 8LL * (unsigned int)v25);
                ldapFree(v26, 1819039308);
              }
              v26 = v38;
            }
            ValueWithAlloc = CLdapBer::HrGetValueWithAlloc(v42, (char **)&v41, 0);
            Value = ValueWithAlloc;
            if ( ValueWithAlloc )
              break;
            v19 = -1;
            *((_QWORD *)v26 + v25) = v41;
            v25 = (unsigned int)(v25 + 1);
            if ( !*((_BYTE *)a1 + 644) )
            {
              v31 = v43;
              if ( (unsigned int)v25 >= v43 )
              {
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
                {
                  v32 = "LdapGetValues:749";
                  goto LABEL_107;
                }
                goto LABEL_75;
              }
            }
          }
LABEL_70:
          if ( ValueWithAlloc == 90 )
          {
LABEL_113:
            *((_QWORD *)v26 + v25) = 0;
            v6 = (PCHAR *)v26;
            goto LABEL_114;
          }
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
            LDAPClientPrint(
              0x200000,
              "LdapGetValues 4 connection 0x%x received error 0x%x .\n",
              (_DWORD)a1,
              ValueWithAlloc);
          goto LABEL_75;
        }
        while ( 1 )
        {
          v41 = 0;
          if ( !v26 || (unsigned int)v25 >= v13 - 1 )
          {
            v13 *= 2;
            v33 = 8LL * v13;
            if ( v33 > 0xFFFFFFFF )
              goto LABEL_108;
            v34 = (void *)ldapMalloc(v33, 1819039308);
            v35 = v34;
            if ( !v34 )
              goto LABEL_108;
            if ( v26 )
            {
              memcpy_0(v34, v26, 8LL * (unsigned int)v25);
              ldapFree(v26, 1819039308);
            }
            v26 = v35;
          }
          ValueWithAlloc = CLdapBer::HrGetValueWithAlloc(v42, (unsigned __int16 **)&v41, 0);
          Value = ValueWithAlloc;
          if ( ValueWithAlloc )
            goto LABEL_70;
          v19 = -1;
          *((_QWORD *)v26 + v25) = v41;
          v25 = (unsigned int)(v25 + 1);
          if ( !*((_BYTE *)a1 + 644) )
          {
            v31 = v43;
            if ( (unsigned int)v25 >= v43 )
              break;
          }
        }
        if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x200000) == 0 )
        {
LABEL_75:
          v6 = (PCHAR *)v26;
          if ( v26 )
            *((_QWORD *)v26 + v25) = 0;
          Value = CLdapBer::HrEndReadSequence(v42);
LABEL_114:
          if ( !v17 )
            goto LABEL_122;
          goto LABEL_121;
        }
        v32 = "LdapGetValues:657";
      }
LABEL_107:
      LDAPClientPrint(
        0x200000,
        "%s LdapGetValues exceeded Max value range size. conn:0x%x resultCount: %lu maxResults: %lu\n",
        v32,
        (_DWORD)a1,
        v25,
        v31);
      goto LABEL_75;
    }
    v12 = v42;
LABEL_38:
    v17 = ldapMalloc(872, 1816347212);
    if ( !v17 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
        LDAPClientPrint(0x4000, "LdapGetValues connection 0x%x could not allocate message.\n", (_DWORD)a1);
      Value = 90;
      goto LABEL_129;
    }
    v20 = *((_DWORD *)a1 + 250);
    *(_QWORD *)v17 = 0;
    *(_DWORD *)(v17 + 8) = 0;
    *(_QWORD *)(v17 + 16) = 0;
    *(_QWORD *)(v17 + 836) = 0;
    *(_QWORD *)(v17 + 24) = 0;
    *(_BYTE *)(v17 + 856) = 0;
    *(_DWORD *)(v17 + 864) = 0;
    *(_DWORD *)(v17 + 860) = v20 != 2 ? 0xFDE9 : 0;
    *(_DWORD *)(v17 + 32) = 0;
    *(_DWORD *)v17 = *(_DWORD *)v12;
    *(_DWORD *)(v17 + 8) = *((_DWORD *)v12 + 2);
    *(_QWORD *)(v17 + 16) = *((_QWORD *)v12 + 2);
    *(_DWORD *)(v17 + 4) = 0;
    *(_QWORD *)(v17 + 836) = 0;
    *(_DWORD *)(v17 + 24) = *((_DWORD *)v12 + 6);
    *(_DWORD *)(v17 + 28) = *((_DWORD *)v12 + 7);
    *(_BYTE *)(v17 + 856) = 1;
    *(_DWORD *)(v17 + 32) = 0;
    Attribute = LdapGoToFirstAttribute(a1, (struct CLdapBer *)v17);
    Value = Attribute;
    if ( !Attribute )
    {
      v42 = (CLdapBer *)v17;
      while ( !Value )
      {
        v22 = CLdapBer::HrStartReadSequence((CLdapBer *)v17, 0x30u, 0);
        Value = v22;
        if ( v22 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(
              0x400000,
              "LdapGetValues 8 connection 0x%x received protocol error 0x%x .\n",
              (_DWORD)a1,
              v22);
        }
        else
        {
          Value = CLdapBer::HrGetValue((CLdapBer *)v17, String1, v23, v24, v39);
          if ( !Value )
          {
            if ( (unsigned __int8)ldapWStringsIdentical(String1, -1, a3, -1) == 1 )
              goto LABEL_31;
            Sequence = CLdapBer::HrEndReadSequence((CLdapBer *)v17);
            Value = Sequence;
            if ( Sequence )
              goto LABEL_32;
          }
        }
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "LdapGetValues connection 0x%x did not find attribute '%S'.\n", (_DWORD)a1, a3);
      SetConnectionError(a1, Value);
LABEL_121:
      CLdapBer::`scalar deleting destructor'((CLdapBer *)v17, v19);
LABEL_122:
      if ( Value != 90 )
      {
LABEL_130:
        SetConnectionError(a1, Value);
        *v44 = v6;
        return Value;
      }
LABEL_129:
      ldap_value_free(v6);
      v6 = 0;
      goto LABEL_130;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(0x400000, "LdapGetValues 1 connection 0x%x received protocol error 0x%x .\n", a1, Attribute);
    goto LABEL_36;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
    LDAPClientPrint(
      0x400000,
      "LdapGetValues could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n",
      (_DWORD)a1,
      CurrentThreadId);
  if ( (unsigned int)AddPerThreadEntry(CurrentThreadId) )
  {
    CurrentPerThreadEntry = GetCurrentPerThreadEntry();
    if ( !CurrentPerThreadEntry )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(
          0x400000,
          "LdapGetValues no per-thread entry, connection 0x%x, thread 0x%x.\n",
          (_DWORD)a1,
          CurrentThreadId);
      Value = 82;
      SetConnectionError(a1, 82);
      return Value;
    }
    goto LABEL_24;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
    LDAPClientPrint(
      0x400000,
      "LdapGetValues AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n",
      (_DWORD)a1,
      CurrentThreadId);
  SetConnectionError(a1, 90);
  return 90;
}

```

## disassembly

```asm
0x18001ba9c  mov     [rsp-8+arg_18], rbx
0x18001baa1  push    rbp
0x18001baa2  push    rsi
0x18001baa3  push    rdi
0x18001baa4  push    r12
0x18001baa6  push    r13
0x18001baa8  push    r14
0x18001baaa  push    r15
0x18001baac  lea     rbp, [rsp-5B0h]
0x18001bab4  sub     rsp, 6B0h
0x18001babb  mov     rax, cs:__security_cookie
0x18001bac2  xor     rax, rsp
0x18001bac5  mov     [rbp+5E0h+var_40], rax
0x18001bacc  xor     r14d, r14d
0x18001bacf  mov     [rsp+6E0h+var_6B0], r9b
0x18001bad4  mov     dword ptr [rsp+6E0h+var_6A8], r14d
0x18001bad9  mov     rsi, rcx
0x18001badc  mov     rcx, [rbp+5E0h+arg_28]
0x18001bae3  mov     r12, r8
0x18001bae6  mov     [rsp+6E0h+var_690], rcx
0x18001baeb  mov     rbx, rdx
0x18001baee  mov     eax, [rsi+440h]
0x18001baf4  mov     [rsp+6E0h+var_698], eax
0x18001baf8  mov     [rcx], r14
0x18001bafb  test    rdx, rdx
0x18001bafe  jnz     short loc_18001BB08
0x18001bb00  lea     eax, [rdx+59h]
0x18001bb03  jmp     loc_18001C29D
0x18001bb08  cmp     dword ptr [rdx+4], 64h ; 'd'
0x18001bb0c  jz      short loc_18001BB25
0x18001bb0e  mov     edx, 54h ; 'T'
0x18001bb13  mov     rcx, rsi
0x18001bb16  call    SetConnectionError
0x18001bb1b  mov     eax, 54h ; 'T'
0x18001bb20  jmp     loc_18001C29D
0x18001bb25  call    cs:__imp_GetCurrentThreadId
0x18001bb2c  nop     dword ptr [rax+rax+00h]
0x18001bb31  xor     edx, edx
0x18001bb33  mov     rcx, rsi
0x18001bb36  mov     edi, eax
0x18001bb38  call    SetConnectionError
0x18001bb3d  mov     rbx, [rbx+8]
0x18001bb41  lea     rdx, [rsp+6E0h+var_6A8]; unsigned int *
0x18001bb46  mov     rcx, rbx; this
0x18001bb49  mov     [rsp+6E0h+var_6A0], rbx
0x18001bb4e  call    ?HrPeekTag@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrPeekTag(ulong *)
0x18001bb53  mov     r13d, 2
0x18001bb59  mov     r15d, 400000h
0x18001bb5f  cmp     eax, 10h
0x18001bb62  jz      loc_18001BD1A
0x18001bb68  cmp     dword ptr [rsp+6E0h+var_6A8], 31h ; '1'
0x18001bb6d  jnz     loc_18001BD1A
0x18001bb73  call    GetCurrentPerThreadEntry
0x18001bb78  mov     rbx, rax
0x18001bb7b  test    rax, rax
0x18001bb7e  jnz     loc_18001BC57
0x18001bb84  cmp     cs:g_fTracingOn, r14d
0x18001bb8b  jz      short loc_18001BBB4
0x18001bb8d  cmp     cs:g_fProviderEnabled, r14d
0x18001bb94  jz      short loc_18001BBB4
0x18001bb96  test    cs:g_ulTraceFlags, r15
0x18001bb9d  jz      short loc_18001BBB4
0x18001bb9f  mov     r9d, edi
0x18001bba2  lea     rdx, aLdapgetvaluesC_0; "LdapGetValues could not find ThreadEntr"...
0x18001bba9  mov     r8, rsi
0x18001bbac  mov     ecx, r15d
0x18001bbaf  call    LDAPClientPrint
0x18001bbb4  mov     ecx, edi
0x18001bbb6  call    AddPerThreadEntry
0x18001bbbb  test    eax, eax
0x18001bbbd  jnz     short loc_18001BC06
0x18001bbbf  cmp     cs:g_fTracingOn, r14d
0x18001bbc6  jz      short loc_18001BBEF
0x18001bbc8  cmp     cs:g_fProviderEnabled, r14d
0x18001bbcf  jz      short loc_18001BBEF
0x18001bbd1  test    cs:g_ulTraceFlags, r15
0x18001bbd8  jz      short loc_18001BBEF
0x18001bbda  mov     r9d, edi
0x18001bbdd  lea     rdx, aLdapgetvaluesA; "LdapGetValues AddPerThreadEntry failed,"...
0x18001bbe4  mov     r8, rsi
0x18001bbe7  mov     ecx, r15d
0x18001bbea  call    LDAPClientPrint
0x18001bbef  mov     edx, 5Ah ; 'Z'
0x18001bbf4  mov     rcx, rsi
0x18001bbf7  call    SetConnectionError
0x18001bbfc  mov     eax, 5Ah ; 'Z'
0x18001bc01  jmp     loc_18001C29D
0x18001bc06  call    GetCurrentPerThreadEntry
0x18001bc0b  mov     rbx, rax
0x18001bc0e  test    rax, rax
0x18001bc11  jnz     short loc_18001BC57
0x18001bc13  cmp     cs:g_fTracingOn, r14d
0x18001bc1a  jz      short loc_18001BC43
0x18001bc1c  cmp     cs:g_fProviderEnabled, r14d
0x18001bc23  jz      short loc_18001BC43
0x18001bc25  test    cs:g_ulTraceFlags, r15
0x18001bc2c  jz      short loc_18001BC43
0x18001bc2e  mov     r9d, edi
0x18001bc31  lea     rdx, aLdapgetvaluesN; "LdapGetValues no per-thread entry, conn"...
0x18001bc38  mov     r8, rsi
0x18001bc3b  mov     ecx, r15d
0x18001bc3e  call    LDAPClientPrint
0x18001bc43  mov     ebx, 52h ; 'R'
0x18001bc48  mov     rcx, rsi
0x18001bc4b  mov     edx, ebx
0x18001bc4d  call    SetConnectionError
0x18001bc52  jmp     loc_18001C29B
0x18001bc57  lea     rcx, PerThreadListLock; lpCriticalSection
0x18001bc5e  call    cs:__imp_EnterCriticalSection
0x18001bc65  nop     dword ptr [rax+rax+00h]
0x18001bc6a  mov     rbx, [rbx+20h]
0x18001bc6e  jmp     short loc_18001BC79
0x18001bc70  cmp     [rbx+10h], rsi
0x18001bc74  jz      short loc_18001BC7E
0x18001bc76  mov     rbx, [rbx]
0x18001bc79  test    rbx, rbx
0x18001bc7c  jnz     short loc_18001BC70
0x18001bc7e  lea     rcx, PerThreadListLock; lpCriticalSection
0x18001bc85  call    cs:__imp_LeaveCriticalSection
0x18001bc8c  nop     dword ptr [rax+rax+00h]
0x18001bc91  test    rbx, rbx
0x18001bc94  jz      short loc_18001BD15
0x18001bc96  or      eax, 0FFFFFFFFh
0x18001bc99  lea     rcx, [rbx+348h]; lpString1
0x18001bca0  mov     r9d, eax; cchCount2
0x18001bca3  mov     edx, eax; cchCount1
0x18001bca5  mov     r8, r12; lpString2
0x18001bca8  call    ldapWStringsIdentical
0x18001bcad  cmp     al, 1
0x18001bcaf  jnz     short loc_18001BD15
0x18001bcb1  mov     r15, r14
0x18001bcb4  mov     edi, 400000h
0x18001bcb9  mov     rcx, [rsp+6E0h+var_6A0]; this
0x18001bcbe  xor     r8d, r8d; unsigned __int8
0x18001bcc1  lea     edx, [r8+31h]; unsigned int
0x18001bcc5  call    ?HrStartReadSequence@CLdapBer@@QEAAKKE@Z; CLdapBer::HrStartReadSequence(ulong,uchar)
0x18001bcca  mov     ebx, eax
0x18001bccc  test    eax, eax
0x18001bcce  jz      loc_18001BE96
0x18001bcd4  cmp     cs:g_fTracingOn, r14d
0x18001bcdb  jz      short loc_18001BD03
0x18001bcdd  cmp     cs:g_fProviderEnabled, r14d
0x18001bce4  jz      short loc_18001BD03
0x18001bce6  test    cs:g_ulTraceFlags, rdi
0x18001bced  jz      short loc_18001BD03
0x18001bcef  lea     rdx, aLdapgetvalues2; "LdapGetValues 2 connection 0x%x receive"...
0x18001bcf6  mov     r9d, eax
0x18001bcf9  mov     r8, rsi
0x18001bcfc  mov     ecx, edi
0x18001bcfe  call    LDAPClientPrint
0x18001bd03  mov     edx, 54h ; 'T'
0x18001bd08  mov     rcx, rsi
0x18001bd0b  call    SetConnectionError
0x18001bd10  jmp     loc_18001C1FB
0x18001bd15  mov     rbx, [rsp+6E0h+var_6A0]
0x18001bd1a  mov     edx, 6C43424Ch
0x18001bd1f  mov     ecx, 368h
0x18001bd24  call    ldapMalloc
0x18001bd29  mov     r15, rax
0x18001bd2c  test    rax, rax
0x18001bd2f  jz      loc_18001C24A
0x18001bd35  mov     eax, [rsi+3E8h]
0x18001bd3b  mov     rdx, r15; struct CLdapBer *
0x18001bd3e  mov     [r15], r14
0x18001bd41  sub     eax, r13d
0x18001bd44  mov     [r15+8], r14d
0x18001bd48  neg     eax
0x18001bd4a  mov     [r15+10h], r14
0x18001bd4e  mov     rcx, rsi; struct ldap_connection *
0x18001bd51  mov     [r15+344h], r14
0x18001bd58  sbb     eax, eax
0x18001bd5a  mov     [r15+18h], r14
0x18001bd5e  and     eax, 0FDE9h
0x18001bd63  mov     [r15+358h], r14b
0x18001bd6a  mov     [r15+360h], r14d
0x18001bd71  mov     [r15+35Ch], eax
0x18001bd78  mov     [r15+20h], r14d
0x18001bd7c  mov     eax, [rbx]
0x18001bd7e  mov     [r15], eax
0x18001bd81  mov     eax, [rbx+8]
0x18001bd84  mov     [r15+8], eax
0x18001bd88  mov     rax, [rbx+10h]
0x18001bd8c  mov     [r15+10h], rax
0x18001bd90  mov     [r15+4], r14d
0x18001bd94  mov     [r15+344h], r14
0x18001bd9b  mov     eax, [rbx+18h]
0x18001bd9e  mov     [r15+18h], eax
0x18001bda2  mov     eax, [rbx+1Ch]
0x18001bda5  mov     [r15+1Ch], eax
0x18001bda9  mov     byte ptr [r15+358h], 1
0x18001bdb1  mov     [r15+20h], r14d
0x18001bdb5  call    ?LdapGoToFirstAttribute@@YAKPEAUldap_connection@@PEAVCLdapBer@@@Z; LdapGoToFirstAttribute(ldap_connection *,CLdapBer *)
0x18001bdba  mov     ebx, eax
0x18001bdbc  test    eax, eax
0x18001bdbe  jz      short loc_18001BDF8
0x18001bdc0  cmp     cs:g_fTracingOn, r14d
0x18001bdc7  jz      loc_18001BD03
0x18001bdcd  cmp     cs:g_fProviderEnabled, r14d
0x18001bdd4  jz      loc_18001BD03
0x18001bdda  mov     edi, 400000h
0x18001bddf  test    cs:g_ulTraceFlags, rdi
0x18001bde6  jz      loc_18001BD03
0x18001bdec  lea     rdx, aLdapgetvalues1; "LdapGetValues 1 connection 0x%x receive"...
0x18001bdf3  jmp     loc_18001BCF6
0x18001bdf8  mov     [rsp+6E0h+var_6A0], r15
0x18001bdfd  mov     edi, 400000h
0x18001be02  test    ebx, ebx
0x18001be04  jnz     loc_18001C202
0x18001be0a  xor     r8d, r8d; unsigned __int8
0x18001be0d  lea     edx, [rbx+30h]; unsigned int
0x18001be10  mov     rcx, r15; this
0x18001be13  call    ?HrStartReadSequence@CLdapBer@@QEAAKKE@Z; CLdapBer::HrStartReadSequence(ulong,uchar)
0x18001be18  mov     ebx, eax
0x18001be1a  test    eax, eax
0x18001be1c  jz      short loc_18001BE4F
0x18001be1e  cmp     cs:g_fTracingOn, r14d
0x18001be25  jz      short loc_18001BE02
0x18001be27  cmp     cs:g_fProviderEnabled, r14d
0x18001be2e  jz      short loc_18001BE02
0x18001be30  test    cs:g_ulTraceFlags, rdi
0x18001be37  jz      short loc_18001BE02
0x18001be39  mov     r9d, eax
0x18001be3c  lea     rdx, aLdapgetvalues8; "LdapGetValues 8 connection 0x%x receive"...
0x18001be43  mov     r8, rsi
0x18001be46  mov     ecx, edi
0x18001be48  call    LDAPClientPrint
0x18001be4d  jmp     short loc_18001BE02
0x18001be4f  lea     rdx, [rsp+6E0h+String1]; unsigned __int16 *
0x18001be54  mov     rcx, r15; this
0x18001be57  call    ?HrGetValue@CLdapBer@@QEAAKPEAGKKE@Z; CLdapBer::HrGetValue(ushort *,ulong,ulong,uchar)
0x18001be5c  mov     ebx, eax
0x18001be5e  test    eax, eax
0x18001be60  jnz     short loc_18001BE02
0x18001be62  or      eax, 0FFFFFFFFh
0x18001be65  lea     rcx, [rsp+6E0h+String1]; lpString1
0x18001be6a  mov     r9d, eax; cchCount2
0x18001be6d  mov     edx, eax; cchCount1
0x18001be6f  mov     r8, r12; lpString2
0x18001be72  call    ldapWStringsIdentical
0x18001be77  cmp     al, 1
0x18001be79  jz      loc_18001BCB9
0x18001be7f  mov     rcx, r15; this
0x18001be82  call    ?HrEndReadSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndReadSequence(void)
0x18001be87  mov     ebx, eax
0x18001be89  test    eax, eax
0x18001be8b  jz      loc_18001BE02
0x18001be91  jmp     loc_18001BCD4
0x18001be96  xor     edi, edi
0x18001be98  xor     r12d, r12d
0x18001be9b  mov     edx, 0FFFFFFFFh
0x18001bea0  cmp     [rsp+6E0h+var_6B0], dil
0x18001bea5  jz      loc_18001BFD6
0x18001beab  mov     [rsp+6E0h+var_6A8], r14
0x18001beb0  test    r12, r12
0x18001beb3  jz      short loc_18001BEBD
0x18001beb5  lea     eax, [r13-1]
0x18001beb9  cmp     edi, eax
0x18001bebb  jb      short loc_18001BF0D
0x18001bebd  add     r13d, r13d
0x18001bec0  mov     ecx, r13d
0x18001bec3  shl     rcx, 3
0x18001bec7  cmp     rcx, rdx
0x18001beca  ja      loc_18001C1B8
0x18001bed0  mov     edx, 6C6C564Ch
0x18001bed5  call    ldapMalloc
0x18001beda  mov     rbx, rax
0x18001bedd  test    rax, rax
0x18001bee0  jz      loc_18001C1B8
0x18001bee6  test    r12, r12
0x18001bee9  jz      short loc_18001BF0A
0x18001beeb  mov     r8d, edi
0x18001beee  mov     rdx, r12; Src
0x18001bef1  shl     r8, 3; Size
0x18001bef5  mov     rcx, rax; void *
0x18001bef8  call    memcpy_0
0x18001befd  mov     edx, 6C6C564Ch
0x18001bf02  mov     rcx, r12
0x18001bf05  call    ldapFree
0x18001bf0a  mov     r12, rbx
0x18001bf0d  mov     rcx, [rsp+6E0h+var_6A0]; this
0x18001bf12  lea     rdx, [rsp+6E0h+var_6A8]; struct berval **
0x18001bf17  xor     r8d, r8d; unsigned __int8
0x18001bf1a  call    ?HrGetValueWithAlloc@CLdapBer@@QEAAKPEAPEAUberval@@E@Z; CLdapBer::HrGetValueWithAlloc(berval * *,uchar)
0x18001bf1f  mov     ebx, eax
0x18001bf21  test    eax, eax
0x18001bf23  jnz     short loc_18001BF7A
0x18001bf25  mov     rax, [rsp+6E0h+var_6A8]
0x18001bf2a  mov     edx, 0FFFFFFFFh
0x18001bf2f  mov     [r12+rdi*8], rax
0x18001bf33  inc     edi
0x18001bf35  cmp     [rsi+284h], r14b
0x18001bf3c  jnz     loc_18001BEAB
0x18001bf42  mov     eax, [rsp+6E0h+var_698]
0x18001bf46  cmp     edi, eax
0x18001bf48  jb      loc_18001BEAB
0x18001bf4e  cmp     cs:g_fTracingOn, r14d
0x18001bf55  jz      short loc_18001BFB5
0x18001bf57  cmp     cs:g_fProviderEnabled, r14d
0x18001bf5e  jz      short loc_18001BFB5
0x18001bf60  mov     ecx, 200000h
  ... truncated ...
```
