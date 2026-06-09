# LdapWaitForResponseFromServerParallelWithConnectionLock(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar,int)

- ea: `0x180019f88`
- end: `0x18001a727`
- name: `?LdapWaitForResponseFromServerParallelWithConnectionLock@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@EH@Z`
- size: `1951`
- prototype: `unsigned int __usercall@<eax>(struct ldap_connection *@<rcx>, struct ldap_request *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct ldapmsg **, unsigned __int8, int)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800198b4`
- `0x1800327b4`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x180008070`
- `0x18000a358`
- `0x18000b440`
- `0x180019f88`
- `0x18001a730`
- `0x18001a758`
- `0x1800235b0`
- `0x18003b448`
- `0x180045b90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a474`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a474`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a48a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a4f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a48a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a4f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019fec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a32c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a59d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019fec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a32c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a59d`

## string_xrefs

- `0x18001a119`: `%s Got the cached result for request: 0x%x\n`
- `0x18001a09b`: `%s Request has no pending responses - perhaps a cached result to process\n`
- `0x18001a41e`: `%s Connection is down, attempting to auto-reconnect conn:0x%p host:%S port:%lu error:%lu\n`

## pseudocode

```c
__int64 __fastcall LdapWaitForResponseFromServerParallelWithConnectionLock(
        struct ldap_connection *a1,
        struct ldap_request *a2,
        unsigned int a3,
        unsigned int a4,
        struct ldapmsg **a5,
        unsigned __int8 a6,
        int a7)
{
  const wchar_t *v7; // rsi
  int v8; // ebx
  char v12; // al
  int v13; // ebx
  unsigned int v14; // r15d
  unsigned int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // r12d
  unsigned __int64 v20; // rax
  int v21; // r12d
  __int64 v22; // rsi
  __int64 v23; // r14
  unsigned __int64 v24; // rax
  const wchar_t *v25; // [rsp+58h] [rbp-71h]
  unsigned int v26; // [rsp+60h] [rbp-69h]
  __int128 v27; // [rsp+68h] [rbp-61h] BYREF
  __int64 v28; // [rsp+78h] [rbp-51h]
  ULONGLONG TickCount64; // [rsp+80h] [rbp-49h]
  __int128 v30; // [rsp+88h] [rbp-41h] BYREF
  __int64 v31; // [rsp+98h] [rbp-31h]
  __int64 v32; // [rsp+A8h] [rbp-21h]
  __int64 v33; // [rsp+B0h] [rbp-19h]
  __int128 v34; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-1h]
  int v36; // [rsp+118h] [rbp+4Fh]

  v7 = L"NULL";
  v8 = *((unsigned __int16 *)a1 + 253);
  if ( *((_QWORD *)a1 + 54) )
    v7 = (const wchar_t *)*((_QWORD *)a1 + 54);
  v32 = *((_QWORD *)a1 + 78);
  v33 = *((_QWORD *)a1 + 79);
  v25 = v7;
  DWORD2(v27) = 8;
  TickCount64 = GetTickCount64();
  *(_QWORD *)&v27 = 0;
  v28 = 0;
  if ( *((_BYTE *)a1 + 554) || *((_BYTE *)a1 + 552) != 1 || *((_BYTE *)a1 + 553) != 8 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientPrint(
        0x10000000,
        "%s Connection is no longer in a valid state\n",
        "LdapWaitForResponseFromServerParallelWithConnectionLock:1177");
    return 81;
  }
  if ( a2 )
  {
    v12 = *((_BYTE *)a2 + 188);
    if ( v12 == 1 || *((_BYTE *)a2 + 184) == 1 )
    {
      v14 = (v12 != 0) + 88;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(
          0x10000000,
          "%s request is no longer in a valid state error:%d\n",
          "LdapWaitForResponseFromServerParallelWithConnectionLock:1192",
          v14);
      goto LABEL_29;
    }
    if ( !*((_WORD *)a2 + 91) && !*((_DWORD *)a2 + 38) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(
          0x10000000,
          "%s Request has no pending responses - perhaps a cached result to process\n",
          "LdapWaitForResponseFromServerParallelWithConnectionLock:1203");
      if ( *((_BYTE *)a2 + 274)
        && (v13 = LdapBuffersToMessages((struct _RTL_CRITICAL_SECTION *)a1, a4, (struct CRequestListHolder *)&v27),
            CRequestListHolder::FreeAll((CRequestListHolder *)&v27),
            !v13)
        && a5
        && (LdapGetResponseFromServer(a1, a2, a4, a5), *a5) )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
          LDAPClientPrint(
            1024,
            "%s Got the cached result for request: 0x%x\n",
            "LdapWaitForResponseFromServerParallelWithConnectionLock:1217",
            (_DWORD)a2);
        v14 = 0;
      }
      else
      {
        v14 = 89;
      }
LABEL_29:
      CRequestListHolder::~CRequestListHolder((CRequestListHolder *)&v27);
      return v14;
    }
  }
  v36 = v8;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
    LDAPClientPrint(
      1024,
      "%s Processing socket data for connection conn:0x%p host:%S port:%lu\n",
      "LdapWaitForResponseFromServerParallelWithConnectionLock:1234",
      a1,
      v7,
      v8);
  if ( a5 )
    *a5 = 0;
  while ( 2 )
  {
    while ( 2 )
    {
      v16 = a3;
      v30 = v27;
      v31 = v28;
      while ( 2 )
      {
        v26 = v16;
        do
        {
          v17 = DrainWinsockParallel(a1, v16);
          if ( v17 == 258 )
            goto LABEL_68;
          if ( v17 == 995 )
            goto LABEL_109;
          for ( ; !v17; v17 = DrainWinsockParallel(a1, 0) )
            ;
          v18 = 0;
          if ( v17 != 258 )
            v18 = v17;
          if ( v18 == 995 )
          {
LABEL_109:
            v18 = 88;
            goto LABEL_69;
          }
          v19 = LdapBuffersToMessages((struct _RTL_CRITICAL_SECTION *)a1, a4, (struct CRequestListHolder *)&v30);
          CRequestListHolder::FreeAll((CRequestListHolder *)&v30);
          if ( v19 && !v18 )
            v18 = v19;
          if ( !a5 )
            goto LABEL_69;
          LdapGetResponseFromServer(a1, a2, a4, a5);
          if ( !*a5 )
            goto LABEL_54;
          v18 = 0;
          if ( !a2 || !*((_BYTE *)a2 + 273) )
            goto LABEL_69;
          v34 = v30;
          v35 = v31;
          v18 = CacheRootDseResult(
                  (struct _RTL_CRITICAL_SECTION *)a1,
                  (__int64)a2,
                  a4,
                  (struct CRequestListHolder *)&v34,
                  a5);
          if ( !v18 )
          {
            if ( *a5 )
              goto LABEL_69;
LABEL_54:
            if ( !a2 )
              goto LABEL_57;
          }
          if ( !*((_WORD *)a2 + 91) && !*((_DWORD *)a2 + 38) )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
              LDAPClientPrint(0x10000000, "%s Request has no pending responses\n", "DrainWinsockParallelHelper:1087");
            v18 = 89;
            goto LABEL_69;
          }
LABEL_57:
          if ( a7 )
          {
            v18 = 9;
            goto LABEL_69;
          }
          if ( v18 )
            goto LABEL_69;
          v16 = v26;
        }
        while ( a3 == -1 );
        if ( a3 )
        {
          v20 = GetTickCount64() - TickCount64;
          if ( v20 < a3 )
          {
            v16 = a3 - v20;
            continue;
          }
          goto LABEL_68;
        }
        break;
      }
      if ( !*a5 )
LABEL_68:
        v18 = 85;
LABEL_69:
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
        LDAPClientPrint(
          1024,
          "%s DrainWinsockParallelHelper finished error:%lu\n",
          "DrainWinsockParallelHelper:1141",
          v18);
      if ( v31 )
        ldapFree(v31, 1718960716);
      if ( v18 && *((_BYTE *)a1 + 554) )
      {
        if ( a6 )
          goto LABEL_91;
        v21 = 0;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
          LDAPClientPrint(
            0x2000000,
            "%s Connection is down, attempting to auto-reconnect conn:0x%p host:%S port:%lu error:%lu\n",
            "LdapWaitForResponseFromServerParallelWithConnectionLock:1272",
            a1,
            v7,
            v36,
            v18);
        EnterCriticalSection((LPCRITICAL_SECTION)a1 + 14);
        if ( *((_BYTE *)a1 + 553) == 16 && *((_BYTE *)a1 + 555) == 1 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
          *((_BYTE *)a1 + 553) = 4;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
          v18 = LdapAutoReconnect(a1);
          if ( !v18 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
              LDAPClientPrint(
                0x2000000,
                "%s Auto-reconnect successful conn:0x%p host:%S port:%lu\n",
                "LdapWaitForResponseFromServerParallelWithConnectionLock:1296",
                a1,
                v7,
                v36);
            v21 = 1;
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 14);
        if ( !v21 )
          goto LABEL_91;
        continue;
      }
      break;
    }
    if ( v18 == 88 && a2 && (!*((_BYTE *)a2 + 184) || !*((_BYTE *)a2 + 188)) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
        LDAPClientPrint(
          1024,
          "%s Another Request on this connection was abandoned, continue to drain data from the socket conn:0x%p host:%S port:%lu\n",
          "LdapWaitForResponseFromServerParallelWithConnectionLock:1317",
          a1,
          v7,
          v36);
      continue;
    }
    break;
  }
LABEL_91:
  if ( g_fTracingOn )
  {
    v22 = *((_QWORD *)a1 + 78) - v32;
    v23 = *((_QWORD *)a1 + 79) - v33;
    if ( g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
      LDAPClientPrint(
        1024,
        "%s finished processing socket data for connection conn:0x%p host:%S port:%lu totalMessages:%I64u totalBytes:%I64u error:%lu\n",
        "LdapWaitForResponseFromServerParallelWithConnectionLock:1341",
        a1,
        v25,
        v36,
        v23,
        v22,
        v18);
    if ( g_fTracingOn )
    {
      if ( g_fProviderEnabled )
      {
        if ( (g_ulTraceFlags & 0x20000000) != 0 )
        {
          v24 = GetTickCount64() - TickCount64;
          if ( v24 > 0xFA )
            LDAPClientPrint(
              0x20000000,
              "%s (took %lu ms) finished processing socket data for connection conn:0x%p host:%S port:%lu totalMessages:%"
              "I64u totalBytes:%I64u error:%lu\n",
              "LdapWaitForResponseFromServerParallelWithConnectionLock:1357",
              v24,
              a1,
              v25,
              v36,
              v23,
              v22,
              v18);
        }
      }
    }
  }
  if ( v18 && *((_BYTE *)a1 + 554) )
  {
    v18 = 81;
    SetConnectionError(a1, 81);
  }
  if ( v28 )
    ldapFree(v28, 1718960716);
  return v18;
}

```

## disassembly

```asm
0x180019f88  mov     rax, rsp
0x180019f8b  mov     [rax+10h], rbx
0x180019f8f  mov     [rax+20h], r9d
0x180019f93  mov     [rax+18h], r8d
0x180019f97  push    rbp
0x180019f98  push    rsi
0x180019f99  push    rdi
0x180019f9a  push    r12
0x180019f9c  push    r13
0x180019f9e  push    r14
0x180019fa0  push    r15
0x180019fa2  lea     rbp, [rax-47h]
0x180019fa6  sub     rsp, 0D0h
0x180019fad  mov     rax, [rcx+1B0h]
0x180019fb4  lea     rsi, aNull; "NULL"
0x180019fbb  movzx   ebx, word ptr [rcx+1FAh]
0x180019fc2  test    rax, rax
0x180019fc5  mov     r15d, r9d
0x180019fc8  mov     r14, rdx
0x180019fcb  cmovnz  rsi, rax
0x180019fcf  mov     rdi, rcx
0x180019fd2  mov     rax, [rcx+270h]
0x180019fd9  mov     [rbp+3Fh+var_60], rax
0x180019fdd  mov     rax, [rcx+278h]
0x180019fe4  mov     [rbp+3Fh+var_58], rax
0x180019fe8  mov     [rbp+3Fh+var_B0], rsi
0x180019fec  call    cs:__imp_GetTickCount64
0x180019ff3  nop     dword ptr [rax+rax+00h]
0x180019ff8  xor     edx, edx
0x180019ffa  mov     dword ptr [rbp+3Fh+var_A0+8], 8
0x18001a001  mov     [rbp+3Fh+var_88], rax
0x18001a005  mov     qword ptr [rbp+3Fh+var_A0], rdx
0x18001a009  mov     [rbp+3Fh+var_90], rdx
0x18001a00d  cmp     [rdi+22Ah], dl
0x18001a013  jnz     loc_18001A6C0
0x18001a019  cmp     byte ptr [rdi+228h], 1
0x18001a020  jnz     loc_18001A6C0
0x18001a026  cmp     byte ptr [rdi+229h], 8
0x18001a02d  jnz     loc_18001A6C0
0x18001a033  test    r14, r14
0x18001a036  jz      loc_18001A185
0x18001a03c  mov     al, [r14+0BCh]
0x18001a043  cmp     al, 1
0x18001a045  jz      loc_18001A132
0x18001a04b  cmp     byte ptr [r14+0B8h], 1
0x18001a053  jz      loc_18001A132
0x18001a059  cmp     [r14+0B6h], dx
0x18001a061  jnz     loc_18001A185
0x18001a067  cmp     [r14+98h], edx
0x18001a06e  jnz     loc_18001A185
0x18001a074  cmp     cs:g_fTracingOn, edx
0x18001a07a  jz      short loc_18001A0A9
0x18001a07c  cmp     cs:g_fProviderEnabled, edx
0x18001a082  jz      short loc_18001A0A9
0x18001a084  mov     esi, 10000000h
0x18001a089  test    cs:g_ulTraceFlags, rsi
0x18001a090  jz      short loc_18001A0A9
0x18001a092  lea     r8, aLdapwaitforres_12; "LdapWaitForResponseFromServerParallelWi"...
0x18001a099  mov     ecx, esi
0x18001a09b  lea     rdx, aSRequestHasNoP; "%s Request has no pending responses - p"...
0x18001a0a2  call    LDAPClientPrint
0x18001a0a7  xor     edx, edx
0x18001a0a9  cmp     [r14+112h], dl
0x18001a0b0  jz      short loc_18001A12A
0x18001a0b2  lea     r8, [rbp+3Fh+var_A0]; struct CRequestListHolder *
0x18001a0b6  mov     edx, r15d; unsigned int
0x18001a0b9  mov     rcx, rdi; struct ldap_connection *
0x18001a0bc  call    ?LdapBuffersToMessages@@YAKPEAUldap_connection@@KPEAVCRequestListHolder@@@Z; LdapBuffersToMessages(ldap_connection *,ulong,CRequestListHolder *)
0x18001a0c1  lea     rcx, [rbp+3Fh+var_A0]; this
0x18001a0c5  mov     ebx, eax
0x18001a0c7  call    ?FreeAll@CRequestListHolder@@QEAAXXZ; CRequestListHolder::FreeAll(void)
0x18001a0cc  xor     esi, esi
0x18001a0ce  test    ebx, ebx
0x18001a0d0  jnz     short loc_18001A12A
0x18001a0d2  mov     rbx, [rbp+3Fh+arg_20]
0x18001a0d6  test    rbx, rbx
0x18001a0d9  jz      short loc_18001A12A
0x18001a0db  mov     r9, rbx; struct ldapmsg **
0x18001a0de  mov     r8d, r15d; unsigned int
0x18001a0e1  mov     rdx, r14; struct ldap_request *
0x18001a0e4  mov     rcx, rdi; struct ldap_connection *
0x18001a0e7  call    ?LdapGetResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KPEAPEAUldapmsg@@@Z; LdapGetResponseFromServer(ldap_connection *,ldap_request *,ulong,ldapmsg * *)
0x18001a0ec  cmp     [rbx], rsi
0x18001a0ef  jz      short loc_18001A12A
0x18001a0f1  cmp     cs:g_fTracingOn, esi
0x18001a0f7  jz      short loc_18001A125
0x18001a0f9  cmp     cs:g_fProviderEnabled, esi
0x18001a0ff  jz      short loc_18001A125
0x18001a101  mov     ecx, 400h
0x18001a106  test    cs:g_ulTraceFlags, rcx
0x18001a10d  jz      short loc_18001A125
0x18001a10f  mov     r9, r14
0x18001a112  lea     r8, aLdapwaitforres_3; "LdapWaitForResponseFromServerParallelWi"...
0x18001a119  lea     rdx, aSGotTheCachedR; "%s Got the cached result for request: 0"...
0x18001a120  call    LDAPClientPrint
0x18001a125  mov     r15d, esi
0x18001a128  jmp     short loc_18001A174
0x18001a12a  mov     r15d, 59h ; 'Y'
0x18001a130  jmp     short loc_18001A174
0x18001a132  neg     al
0x18001a134  sbb     r15d, r15d
0x18001a137  neg     r15d
0x18001a13a  add     r15d, 58h ; 'X'
0x18001a13e  cmp     cs:g_fTracingOn, edx
0x18001a144  jz      short loc_18001A174
0x18001a146  cmp     cs:g_fProviderEnabled, edx
0x18001a14c  jz      short loc_18001A174
0x18001a14e  mov     esi, 10000000h
0x18001a153  test    cs:g_ulTraceFlags, rsi
0x18001a15a  jz      short loc_18001A174
0x18001a15c  mov     r9d, r15d
0x18001a15f  lea     r8, aLdapwaitforres_2; "LdapWaitForResponseFromServerParallelWi"...
0x18001a166  lea     rdx, aSRequestIsNoLo; "%s request is no longer in a valid stat"...
0x18001a16d  mov     ecx, esi
0x18001a16f  call    LDAPClientPrint
0x18001a174  lea     rcx, [rbp+3Fh+var_A0]; this
0x18001a178  call    ??1CRequestListHolder@@QEAA@XZ; CRequestListHolder::~CRequestListHolder(void)
0x18001a17d  mov     eax, r15d
0x18001a180  jmp     loc_18001A70B
0x18001a185  cmp     cs:g_fTracingOn, edx
0x18001a18b  mov     r13d, 400h
0x18001a191  mov     [rbp+3Fh+arg_0], ebx
0x18001a194  jz      short loc_18001A1CB
0x18001a196  cmp     cs:g_fProviderEnabled, edx
0x18001a19c  jz      short loc_18001A1CB
0x18001a19e  test    cs:g_ulTraceFlags, r13
0x18001a1a5  jz      short loc_18001A1CB
0x18001a1a7  mov     dword ptr [rsp+100h+var_D8], ebx
0x18001a1ab  lea     r8, aLdapwaitforres_22; "LdapWaitForResponseFromServerParallelWi"...
0x18001a1b2  mov     r9, rdi
0x18001a1b5  mov     [rsp+100h+var_E0], rsi
0x18001a1ba  lea     rdx, aSProcessingSoc; "%s Processing socket data for connectio"...
0x18001a1c1  mov     ecx, r13d
0x18001a1c4  call    LDAPClientPrint
0x18001a1c9  xor     edx, edx
0x18001a1cb  mov     r12, [rbp+3Fh+arg_20]
0x18001a1cf  test    r12, r12
0x18001a1d2  jz      short loc_18001A1D8
0x18001a1d4  mov     [r12], rdx
0x18001a1d8  mov     esi, 10000000h
0x18001a1dd  mov     r15d, 59h ; 'Y'
0x18001a1e3  movups  xmm0, [rbp+3Fh+var_A0]
0x18001a1e7  mov     ecx, [rbp+3Fh+arg_10]
0x18001a1ea  movsd   xmm1, [rbp+3Fh+var_90]
0x18001a1ef  movaps  [rbp+3Fh+var_80], xmm0
0x18001a1f3  movsd   [rbp+3Fh+var_70], xmm1
0x18001a1f8  mov     [rbp+3Fh+var_A8], ecx
0x18001a1fb  mov     edx, ecx; unsigned int
0x18001a1fd  mov     rcx, rdi; struct ldap_connection *
0x18001a200  call    ?DrainWinsockParallel@@YAKPEAUldap_connection@@K@Z; DrainWinsockParallel(ldap_connection *,ulong)
0x18001a205  xor     edx, edx
0x18001a207  cmp     eax, 102h
0x18001a20c  jz      loc_18001A384
0x18001a212  cmp     eax, 3E3h
0x18001a217  jz      loc_18001A63B
0x18001a21d  test    eax, eax
0x18001a21f  jnz     short loc_18001A237
0x18001a221  xor     edx, edx; unsigned int
0x18001a223  mov     rcx, rdi; struct ldap_connection *
0x18001a226  call    ?DrainWinsockParallel@@YAKPEAUldap_connection@@K@Z; DrainWinsockParallel(ldap_connection *,ulong)
0x18001a22b  test    eax, eax
0x18001a22d  jz      short loc_18001A221
0x18001a22f  xor     edx, edx
0x18001a231  mov     r13d, 400h
0x18001a237  cmp     eax, 102h
0x18001a23c  mov     ebx, edx
0x18001a23e  cmovnz  ebx, eax
0x18001a241  cmp     ebx, 3E3h
0x18001a247  jz      loc_18001A63B
0x18001a24d  mov     edx, [rbp+3Fh+arg_18]; unsigned int
0x18001a250  lea     r8, [rbp+3Fh+var_80]; struct CRequestListHolder *
0x18001a254  mov     rcx, rdi; struct ldap_connection *
0x18001a257  call    ?LdapBuffersToMessages@@YAKPEAUldap_connection@@KPEAVCRequestListHolder@@@Z; LdapBuffersToMessages(ldap_connection *,ulong,CRequestListHolder *)
0x18001a25c  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a260  mov     r12d, eax
0x18001a263  call    ?FreeAll@CRequestListHolder@@QEAAXXZ; CRequestListHolder::FreeAll(void)
0x18001a268  xor     edx, edx
0x18001a26a  test    r12d, r12d
0x18001a26d  jz      short loc_18001A275
0x18001a26f  test    ebx, ebx
0x18001a271  cmovz   ebx, r12d
0x18001a275  mov     r12, [rbp+3Fh+arg_20]
0x18001a279  test    r12, r12
0x18001a27c  jz      loc_18001A389
0x18001a282  mov     r8d, [rbp+3Fh+arg_18]; unsigned int
0x18001a286  mov     r9, r12; struct ldapmsg **
0x18001a289  mov     rdx, r14; struct ldap_request *
0x18001a28c  mov     rcx, rdi; struct ldap_connection *
0x18001a28f  call    ?LdapGetResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KPEAPEAUldapmsg@@@Z; LdapGetResponseFromServer(ldap_connection *,ldap_request *,ulong,ldapmsg * *)
0x18001a294  xor     edx, edx
0x18001a296  cmp     [r12], rdx
0x18001a29a  jz      short loc_18001A2F0
0x18001a29c  mov     ebx, edx
0x18001a29e  test    r14, r14
0x18001a2a1  jz      loc_18001A389
0x18001a2a7  cmp     [r14+111h], dl
0x18001a2ae  jz      loc_18001A389
0x18001a2b4  movaps  xmm0, [rbp+3Fh+var_80]
0x18001a2b8  lea     r9, [rbp+3Fh+var_50]
0x18001a2bc  movsd   xmm1, [rbp+3Fh+var_70]
0x18001a2c1  mov     rdx, r14
0x18001a2c4  mov     r8d, [rbp+3Fh+arg_18]
0x18001a2c8  mov     rcx, rdi
0x18001a2cb  movaps  [rbp+3Fh+var_50], xmm0
0x18001a2cf  movsd   [rbp+3Fh+var_40], xmm1
0x18001a2d4  mov     [rsp+100h+var_E0], r12
0x18001a2d9  call    ?CacheRootDseResult@@YAKPEAUldap_connection@@PEAUldap_request@@KVCRequestListHolder@@PEAPEAUldapmsg@@@Z; CacheRootDseResult(ldap_connection *,ldap_request *,ulong,CRequestListHolder,ldapmsg * *)
0x18001a2de  xor     edx, edx
0x18001a2e0  mov     ebx, eax
0x18001a2e2  test    eax, eax
0x18001a2e4  jnz     short loc_18001A2F5
0x18001a2e6  cmp     [r12], rdx
0x18001a2ea  jnz     loc_18001A389
0x18001a2f0  test    r14, r14
0x18001a2f3  jz      short loc_18001A308
0x18001a2f5  cmp     [r14+0B6h], dx
0x18001a2fd  jnz     short loc_18001A308
0x18001a2ff  cmp     [r14+98h], edx
0x18001a306  jz      short loc_18001A34D
0x18001a308  cmp     [rbp+3Fh+arg_30], edx
0x18001a30b  jnz     loc_18001A631
0x18001a311  test    ebx, ebx
0x18001a313  jnz     short loc_18001A389
0x18001a315  mov     eax, [rbp+3Fh+arg_10]
0x18001a318  mov     ecx, [rbp+3Fh+var_A8]
0x18001a31b  cmp     eax, 0FFFFFFFFh
0x18001a31e  jz      loc_18001A1FB
0x18001a324  test    eax, eax
0x18001a326  jz      loc_18001A622
0x18001a32c  call    cs:__imp_GetTickCount64
0x18001a333  nop     dword ptr [rax+rax+00h]
0x18001a338  sub     rax, [rbp+3Fh+var_88]
0x18001a33c  mov     edx, [rbp+3Fh+arg_10]
0x18001a33f  cmp     rax, rdx
0x18001a342  jnb     short loc_18001A382
0x18001a344  mov     ecx, edx
0x18001a346  sub     ecx, eax
0x18001a348  jmp     loc_18001A1F8
0x18001a34d  cmp     cs:g_fTracingOn, edx
0x18001a353  jz      short loc_18001A37D
0x18001a355  cmp     cs:g_fProviderEnabled, edx
0x18001a35b  jz      short loc_18001A37D
0x18001a35d  test    cs:g_ulTraceFlags, rsi
0x18001a364  jz      short loc_18001A37D
0x18001a366  lea     r8, aDrainwinsockpa_0; "DrainWinsockParallelHelper:1087"
0x18001a36d  mov     ecx, esi
0x18001a36f  lea     rdx, aSRequestHasNoP_0; "%s Request has no pending responses\n"
0x18001a376  call    LDAPClientPrint
0x18001a37b  xor     edx, edx
0x18001a37d  mov     ebx, r15d
0x18001a380  jmp     short loc_18001A389
0x18001a382  xor     edx, edx
0x18001a384  mov     ebx, 55h ; 'U'
0x18001a389  cmp     cs:g_fTracingOn, edx
0x18001a38f  jz      short loc_18001A3BD
0x18001a391  cmp     cs:g_fProviderEnabled, edx
0x18001a397  jz      short loc_18001A3BD
0x18001a399  test    cs:g_ulTraceFlags, r13
0x18001a3a0  jz      short loc_18001A3BD
0x18001a3a2  mov     r9d, ebx
0x18001a3a5  lea     r8, aDrainwinsockpa; "DrainWinsockParallelHelper:1141"
0x18001a3ac  lea     rdx, aSDrainwinsockp; "%s DrainWinsockParallelHelper finished "...
0x18001a3b3  mov     ecx, r13d
0x18001a3b6  call    LDAPClientPrint
0x18001a3bb  xor     edx, edx
0x18001a3bd  mov     rcx, [rbp+3Fh+var_70]
0x18001a3c1  test    rcx, rcx
0x18001a3c4  jz      short loc_18001A3D2
0x18001a3c6  mov     edx, 6675424Ch
0x18001a3cb  call    ldapFree
0x18001a3d0  xor     edx, edx
0x18001a3d2  test    ebx, ebx
0x18001a3d4  jz      loc_18001A645
0x18001a3da  cmp     [rdi+22Ah], dl
0x18001a3e0  jz      loc_18001A645
0x18001a3e6  cmp     [rbp+3Fh+arg_28], dl
0x18001a3e9  jnz     loc_18001A510
0x18001a3ef  cmp     cs:g_fTracingOn, edx
0x18001a3f5  mov     r12d, edx
0x18001a3f8  jz      short loc_18001A43A
0x18001a3fa  cmp     cs:g_fProviderEnabled, edx
0x18001a400  jz      short loc_18001A43A
0x18001a402  mov     ecx, 2000000h
0x18001a407  test    cs:g_ulTraceFlags, rcx
0x18001a40e  jz      short loc_18001A43A
0x18001a410  mov     eax, [rbp+3Fh+arg_0]
0x18001a413  lea     r8, aLdapwaitforres_15; "LdapWaitForResponseFromServerParallelWi"...
0x18001a41a  mov     dword ptr [rsp+100h+var_D0], ebx
0x18001a41e  lea     rdx, aSConnectionIsD; "%s Connection is down, attempting to au"...
0x18001a425  mov     dword ptr [rsp+100h+var_D8], eax
0x18001a429  mov     r9, rdi
0x18001a42c  mov     rax, [rbp+3Fh+var_B0]
0x18001a430  mov     [rsp+100h+var_E0], rax
0x18001a435  call    LDAPClientPrint
0x18001a43a  lea     r13, [rdi+230h]
0x18001a441  mov     rcx, r13; lpCriticalSection
0x18001a444  call    cs:__imp_EnterCriticalSection
0x18001a44b  nop     dword ptr [rax+rax+00h]
0x18001a450  cmp     byte ptr [rdi+229h], 10h
0x18001a457  jnz     loc_18001A4F0
  ... truncated ...
```
