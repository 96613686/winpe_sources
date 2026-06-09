# LdapResendRequests(ldap_connection *)

- ea: `0x18003ae3c`
- end: `0x18003b43f`
- name: `?LdapResendRequests@@YAKPEAUldap_connection@@@Z`
- size: `1539`
- prototype: `unsigned int __fastcall(struct ldap_connection *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b448`

## callees

- `0x1800037a8`
- `0x180008660`
- `0x180008710`
- `0x18000b440`
- `0x18000df44`
- `0x180014460`
- `0x18001ce90`
- `0x1800236f0`
- `0x1800299c0`
- `0x18002a91c`
- `0x18003ada4`
- `0x18003ae3c`
- `0x180048734`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aed0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003afcf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b047`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b1b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b2e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aed0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003afcf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b047`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b1b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b2e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003af33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b02d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b092`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b11e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b2c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b333`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b352`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003af33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b02d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b092`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b11e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b2c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b333`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b352`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b24b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b405`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b24b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b405`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003b3d9`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003b3d9`
- `ntdll!RtlReleaseResource` at `0x18003af46`
- `ntdll!RtlReleaseResource` at `0x18003b131`
- `ntdll!RtlReleaseResource` at `0x18003b383`
- `ntdll!RtlReleaseResource` at `0x18003af46`
- `ntdll!RtlReleaseResource` at `0x18003b131`
- `ntdll!RtlReleaseResource` at `0x18003b383`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ae7b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003afc0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003b1a2`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ae7b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003afc0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003b1a2`

## string_xrefs

- `0x18003b019`: `LdapResendRequest: Skipping over paged/abandoned/completed requests 0x%x\n`
- `0x18003b25a`: `ldapResentRequests thread 0x%x simulated down message for connection 0x%x\n`
- `0x18003b414`: `ldapResentRequests thread 0x%x has connection 0x%x as down.\n`

## pseudocode

```c
__int64 __fastcall LdapResendRequests(struct ldap_connection *a1)
{
  struct ldap_connection *v1; // r15
  unsigned int v2; // edi
  _QWORD *v3; // r14
  unsigned int v4; // ebp
  __int64 *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  int v9; // r12d
  struct CLdapBer *v10; // rsi
  CLdapBer *v11; // rsi
  unsigned int v12; // edx
  __int64 v13; // rsi
  unsigned __int16 v14; // r13
  unsigned __int16 v15; // r15
  struct CLdapBer *v16; // rbp
  unsigned int v17; // edx
  CLdapBer *v18; // rbp
  int v19; // esi
  DWORD CurrentThreadId; // eax
  __int64 v21; // rax
  _QWORD *v22; // rbx
  DWORD v23; // eax
  unsigned int v26; // [rsp+78h] [rbp+10h]
  __int64 **v27; // [rsp+80h] [rbp+18h]
  _QWORD *v28; // [rsp+88h] [rbp+20h]

  v1 = a1;
  v28 = 0;
  v2 = 0;
  v26 = 0;
  v3 = 0;
  v4 = 0;
  RtlAcquireResourceExclusive(&RequestListLock, 1u);
  v5 = (__int64 *)GlobalListRequests;
  v27 = (__int64 **)GlobalListRequests;
  if ( (__int64 *)GlobalListRequests != &GlobalListRequests )
  {
    while ( 1 )
    {
      v6 = ReferenceLdapRequest(v5);
      v7 = v6;
      if ( v6 )
        break;
      v5 = (__int64 *)*v5;
      v27 = (__int64 **)v5;
LABEL_78:
      if ( v5 == &GlobalListRequests )
      {
        v3 = v28;
        goto LABEL_80;
      }
    }
    v8 = (struct _RTL_CRITICAL_SECTION *)(v6 + 48);
    v2 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
    if ( v1 == *(struct ldap_connection **)(v7 + 32) )
    {
      if ( *(_BYTE *)(v7 + 271) || *(_BYTE *)(v7 + 184) || !*(_WORD *)(v7 + 182) )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
          LDAPClientPrint(128, "LdapResendRequest: Skipping over paged/abandoned/completed requests 0x%x\n", v7);
        LeaveCriticalSection(v8);
        v5 = (__int64 *)*v5;
        v27 = (__int64 **)v5;
        EnterCriticalSection(v8);
        --*(_DWORD *)(v7 + 16);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v7, *(_DWORD *)(v7 + 16));
        if ( *(_DWORD *)(v7 + 16) )
        {
LABEL_77:
          LeaveCriticalSection(v8);
          goto LABEL_78;
        }
        goto LABEL_76;
      }
      v9 = *(_DWORD *)(v7 + 108);
      v10 = (struct CLdapBer *)_InterlockedExchange64((volatile __int64 *)(v7 + 160), 0);
      if ( v10 )
      {
        FreeMessagesFromConnection((struct ldap_request *)v7, v1);
        LeaveCriticalSection(v8);
        RtlReleaseResource(&RequestListLock);
        if ( *(_BYTE *)(v7 + 190) || *(_DWORD *)(v7 + 276) < 0x14u )
        {
          ++*(_DWORD *)(v7 + 276);
          v2 = LdapSend(v1, v10, 0);
        }
        else
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
            LDAPClientPrint(128, "LdapResendRequest: Request 0x%x has too many resends\n", v7);
          v2 = 81;
        }
        v11 = (CLdapBer *)_InterlockedExchange64((volatile __int64 *)(v7 + 160), (__int64)v10);
        RtlAcquireResourceExclusive(&RequestListLock, 1u);
        EnterCriticalSection(v8);
        if ( v11 )
          CLdapBer::`scalar deleting destructor'(v11, v12);
      }
      else
      {
        v2 = 91;
      }
    }
    else
    {
      v9 = 0;
    }
    v13 = *(_QWORD *)(v7 + 168);
    if ( v13 )
    {
      if ( !v2 )
      {
        v14 = *(_WORD *)(v7 + 176);
        v15 = 0;
        if ( !v14 )
        {
LABEL_70:
          v1 = a1;
          goto LABEL_71;
        }
        while ( !v2 )
        {
          if ( *(struct ldap_connection **)v13 == a1 )
          {
            v16 = (struct CLdapBer *)_InterlockedExchange64((volatile __int64 *)(v13 + 40), 0);
            if ( v16 )
            {
              if ( !v9 )
                FreeMessagesFromConnection((struct ldap_request *)v7, a1);
              LeaveCriticalSection(v8);
              RtlReleaseResource(&RequestListLock);
              if ( *(_BYTE *)(v7 + 190) || *(_DWORD *)(v13 + 56) < 0x14u )
              {
                ++*(_DWORD *)(v13 + 56);
                v2 = LdapSend(a1, v16, 0);
              }
              else
              {
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
                  LDAPClientPrint(
                    128,
                    "LdapResendRequest: Referral 0x%x for request 0x%x has too many resends\n",
                    v13,
                    v7);
                v2 = 81;
              }
              RtlAcquireResourceExclusive(&RequestListLock, 1u);
              EnterCriticalSection(v8);
              v18 = (CLdapBer *)_InterlockedExchange64((volatile __int64 *)(v13 + 40), (__int64)v16);
              if ( v18 )
                CLdapBer::`scalar deleting destructor'(v18, v17);
            }
            else
            {
              v2 = 91;
            }
            v9 = *(_DWORD *)(v7 + 108);
          }
          ++v15;
          v13 += 64;
          if ( v15 >= v14 )
          {
            v4 = v26;
            v1 = a1;
            goto LABEL_53;
          }
        }
        v4 = v26;
      }
    }
    else
    {
LABEL_53:
      if ( !v2 )
        goto LABEL_71;
    }
    if ( *(_BYTE *)(v7 + 186) != 99 && v2 == 91 )
    {
      v2 = 0;
      goto LABEL_70;
    }
    v1 = a1;
    v19 = SimulateErrorMessage(a1, v7);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
    {
      CurrentThreadId = GetCurrentThreadId();
      LDAPClientPrint(
        128,
        "ldapResentRequests thread 0x%x simulated down message for connection 0x%x\n",
        CurrentThreadId,
        (_DWORD)a1);
    }
    if ( v19 )
      *(_BYTE *)(v7 + 184) = 1;
    v21 = ldapMalloc(16, 1682525516);
    if ( v21 )
    {
      *(_QWORD *)v21 = v28;
      *(_DWORD *)(v21 + 8) = v9;
      v28 = (_QWORD *)v21;
    }
    ClearPendingListForRequest(v7);
    if ( !v4 )
      v4 = v2;
    v26 = v4;
LABEL_71:
    LeaveCriticalSection(v8);
    v5 = *v27;
    v27 = (__int64 **)*v27;
    EnterCriticalSection(v8);
    --*(_DWORD *)(v7 + 16);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v7, *(_DWORD *)(v7 + 16));
    if ( *(_DWORD *)(v7 + 16) )
      goto LABEL_77;
LABEL_76:
    LeaveCriticalSection(v8);
    DereferenceLdapRequest2(v7, 1);
    goto LABEL_78;
  }
LABEL_80:
  RtlReleaseResource(&RequestListLock);
  if ( v3 )
  {
    do
    {
      v22 = v3;
      v3 = (_QWORD *)*v3;
      CheckForWaiters(*((unsigned int *)v22 + 2), 0, v1);
      ldapFree(v22, 1682525516);
    }
    while ( v3 );
    if ( GlobalParallelRecvMode )
      PostQueuedCompletionStatus(*((HANDLE *)v1 + 112), 0, 0xFFFFFFFFFFFFFFFFuLL, 0);
    else
      LdapWakeupSelect();
  }
  if ( v2 == 81 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
  {
    v23 = GetCurrentThreadId();
    LDAPClientPrint(128, "ldapResentRequests thread 0x%x has connection 0x%x as down.\n", v23, (_DWORD)v1);
  }
  if ( !v4 )
    return v2;
  return v4;
}

```

## disassembly

```asm
0x18003ae3c  mov     [rsp+arg_0], rcx
0x18003ae41  push    rbx
0x18003ae42  push    rbp
0x18003ae43  push    rsi
0x18003ae44  push    rdi
0x18003ae45  push    r12
0x18003ae47  push    r13
0x18003ae49  push    r14
0x18003ae4b  push    r15
0x18003ae4d  sub     rsp, 28h
0x18003ae51  xor     r13d, r13d
0x18003ae54  mov     r15, rcx
0x18003ae57  lea     rcx, RequestListLock; Resource
0x18003ae5e  mov     [rsp+68h+arg_18], r13
0x18003ae66  mov     edi, r13d
0x18003ae69  mov     [rsp+68h+arg_8], r13d
0x18003ae6e  mov     r14d, r13d
0x18003ae71  mov     ebp, r13d
0x18003ae74  lea     r12d, [r13+1]
0x18003ae78  mov     dl, r12b; Wait
0x18003ae7b  call    cs:__imp_RtlAcquireResourceExclusive
0x18003ae82  nop     dword ptr [rax+rax+00h]
0x18003ae87  mov     rsi, cs:GlobalListRequests
0x18003ae8e  lea     rax, GlobalListRequests
0x18003ae95  mov     [rsp+68h+arg_10], rsi
0x18003ae9d  cmp     rsi, rax
0x18003aea0  jz      loc_18003B37C
0x18003aea6  mov     rcx, rsi
0x18003aea9  call    ReferenceLdapRequest
0x18003aeae  mov     rbx, rax
0x18003aeb1  test    rax, rax
0x18003aeb4  jnz     short loc_18003AEC6
0x18003aeb6  mov     rsi, [rsi]
0x18003aeb9  mov     [rsp+68h+arg_10], rsi
0x18003aec1  jmp     loc_18003B364
0x18003aec6  lea     r14, [rax+30h]
0x18003aeca  mov     edi, r13d
0x18003aecd  mov     rcx, r14; lpCriticalSection
0x18003aed0  call    cs:__imp_EnterCriticalSection
0x18003aed7  nop     dword ptr [rax+rax+00h]
0x18003aedc  cmp     r15, [rbx+20h]
0x18003aee0  jnz     loc_18003B0B4
0x18003aee6  cmp     [rbx+10Fh], r13b
0x18003aeed  jnz     loc_18003AFFB
0x18003aef3  cmp     [rbx+0B8h], r13b
0x18003aefa  jnz     loc_18003AFFB
0x18003af00  cmp     [rbx+0B6h], r13w
0x18003af08  jz      loc_18003AFFB
0x18003af0e  mov     r12d, [rbx+6Ch]
0x18003af12  mov     rsi, r13
0x18003af15  xchg    rsi, [rbx+0A0h]
0x18003af1c  test    rsi, rsi
0x18003af1f  jz      loc_18003AFF1
0x18003af25  mov     rdx, r15; struct ldap_connection *
0x18003af28  mov     rcx, rbx; struct ldap_request *
0x18003af2b  call    ?FreeMessagesFromConnection@@YAKPEAUldap_request@@PEAUldap_connection@@@Z; FreeMessagesFromConnection(ldap_request *,ldap_connection *)
0x18003af30  mov     rcx, r14; lpCriticalSection
0x18003af33  call    cs:__imp_LeaveCriticalSection
0x18003af3a  nop     dword ptr [rax+rax+00h]
0x18003af3f  lea     rcx, RequestListLock; Resource
0x18003af46  call    cs:__imp_RtlReleaseResource
0x18003af4d  nop     dword ptr [rax+rax+00h]
0x18003af52  cmp     [rbx+0BEh], r13b
0x18003af59  jnz     short loc_18003AF9A
0x18003af5b  cmp     dword ptr [rbx+114h], 14h
0x18003af62  jb      short loc_18003AF9A
0x18003af64  cmp     cs:g_fTracingOn, r13d
0x18003af6b  jz      short loc_18003AF93
0x18003af6d  cmp     cs:g_fProviderEnabled, r13d
0x18003af74  jz      short loc_18003AF93
0x18003af76  test    byte ptr cs:g_ulTraceFlags, 80h
0x18003af7d  jz      short loc_18003AF93
0x18003af7f  mov     r8, rbx
0x18003af82  lea     rdx, aLdapresendrequ_1; "LdapResendRequest: Request 0x%x has too"...
0x18003af89  mov     ecx, 80h
0x18003af8e  call    LDAPClientPrint
0x18003af93  mov     edi, 51h ; 'Q'
0x18003af98  jmp     short loc_18003AFB0
0x18003af9a  inc     dword ptr [rbx+114h]
0x18003afa0  xor     r8d, r8d; struct CLdapBer *
0x18003afa3  mov     rdx, rsi; struct CLdapBer *
0x18003afa6  mov     rcx, r15; struct ldap_connection *
0x18003afa9  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18003afae  mov     edi, eax
0x18003afb0  xchg    rsi, [rbx+0A0h]
0x18003afb7  mov     dl, 1; Wait
0x18003afb9  lea     rcx, RequestListLock; Resource
0x18003afc0  call    cs:__imp_RtlAcquireResourceExclusive
0x18003afc7  nop     dword ptr [rax+rax+00h]
0x18003afcc  mov     rcx, r14; lpCriticalSection
0x18003afcf  call    cs:__imp_EnterCriticalSection
0x18003afd6  nop     dword ptr [rax+rax+00h]
0x18003afdb  test    rsi, rsi
0x18003afde  jz      loc_18003B0B7
0x18003afe4  mov     rcx, rsi; this
0x18003afe7  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003afec  jmp     loc_18003B0B7
0x18003aff1  mov     edi, 5Bh ; '['
0x18003aff6  jmp     loc_18003B0B7
0x18003affb  cmp     cs:g_fTracingOn, r13d
0x18003b002  jz      short loc_18003B02A
0x18003b004  cmp     cs:g_fProviderEnabled, r13d
0x18003b00b  jz      short loc_18003B02A
0x18003b00d  test    byte ptr cs:g_ulTraceFlags, 80h
0x18003b014  jz      short loc_18003B02A
0x18003b016  mov     r8, rbx
0x18003b019  lea     rdx, aLdapresendrequ_0; "LdapResendRequest: Skipping over paged/"...
0x18003b020  mov     ecx, 80h
0x18003b025  call    LDAPClientPrint
0x18003b02a  mov     rcx, r14; lpCriticalSection
0x18003b02d  call    cs:__imp_LeaveCriticalSection
0x18003b034  nop     dword ptr [rax+rax+00h]
0x18003b039  mov     rsi, [rsi]
0x18003b03c  mov     rcx, r14; lpCriticalSection
0x18003b03f  mov     [rsp+68h+arg_10], rsi
0x18003b047  call    cs:__imp_EnterCriticalSection
0x18003b04e  nop     dword ptr [rax+rax+00h]
0x18003b053  dec     dword ptr [rbx+10h]
0x18003b056  cmp     cs:g_fTracingOn, r13d
0x18003b05d  jz      short loc_18003B089
0x18003b05f  cmp     cs:g_fProviderEnabled, r13d
0x18003b066  jz      short loc_18003B089
0x18003b068  test    byte ptr cs:g_ulTraceFlags, 4
0x18003b06f  jz      short loc_18003B089
0x18003b071  mov     r9d, [rbx+10h]
0x18003b075  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x18003b07c  mov     r8, rbx
0x18003b07f  mov     ecx, 4
0x18003b084  call    LDAPClientPrint
0x18003b089  mov     rcx, r14; lpCriticalSection
0x18003b08c  cmp     [rbx+10h], r13d
0x18003b090  jnz     short loc_18003B0A3
0x18003b092  call    cs:__imp_LeaveCriticalSection
0x18003b099  nop     dword ptr [rax+rax+00h]
0x18003b09e  jmp     loc_18003B345
0x18003b0a3  call    cs:__imp_LeaveCriticalSection
0x18003b0aa  nop     dword ptr [rax+rax+00h]
0x18003b0af  jmp     loc_18003B364
0x18003b0b4  mov     r12d, r13d
0x18003b0b7  mov     rsi, [rbx+0A8h]
0x18003b0be  test    rsi, rsi
0x18003b0c1  jz      loc_18003B1F7
0x18003b0c7  test    edi, edi
0x18003b0c9  jnz     loc_18003B208
0x18003b0cf  movzx   r13d, word ptr [rbx+0B0h]
0x18003b0d7  xor     r15d, r15d
0x18003b0da  xor     eax, eax
0x18003b0dc  cmp     ax, r13w
0x18003b0e0  jnb     loc_18003B2BB
0x18003b0e6  test    edi, edi
0x18003b0e8  jnz     loc_18003B201
0x18003b0ee  mov     rax, [rsp+68h+arg_0]
0x18003b0f3  cmp     [rsi], rax
0x18003b0f6  jnz     loc_18003B1D9
0x18003b0fc  xor     ebp, ebp
0x18003b0fe  xchg    rbp, [rsi+28h]
0x18003b102  test    rbp, rbp
0x18003b105  jz      loc_18003B1D0
0x18003b10b  test    r12d, r12d
0x18003b10e  jnz     short loc_18003B11B
0x18003b110  mov     rdx, rax; struct ldap_connection *
0x18003b113  mov     rcx, rbx; struct ldap_request *
0x18003b116  call    ?FreeMessagesFromConnection@@YAKPEAUldap_request@@PEAUldap_connection@@@Z; FreeMessagesFromConnection(ldap_request *,ldap_connection *)
0x18003b11b  mov     rcx, r14; lpCriticalSection
0x18003b11e  call    cs:__imp_LeaveCriticalSection
0x18003b125  nop     dword ptr [rax+rax+00h]
0x18003b12a  lea     rcx, RequestListLock; Resource
0x18003b131  call    cs:__imp_RtlReleaseResource
0x18003b138  nop     dword ptr [rax+rax+00h]
0x18003b13d  xor     eax, eax
0x18003b13f  cmp     [rbx+0BEh], al
0x18003b145  jnz     short loc_18003B184
0x18003b147  cmp     dword ptr [rsi+38h], 14h
0x18003b14b  jb      short loc_18003B184
0x18003b14d  cmp     cs:g_fTracingOn, eax
0x18003b153  jz      short loc_18003B17D
0x18003b155  cmp     cs:g_fProviderEnabled, eax
0x18003b15b  jz      short loc_18003B17D
0x18003b15d  test    byte ptr cs:g_ulTraceFlags, 80h
0x18003b164  jz      short loc_18003B17D
0x18003b166  mov     r9, rbx
0x18003b169  lea     rdx, aLdapresendrequ; "LdapResendRequest: Referral 0x%x for re"...
0x18003b170  mov     r8, rsi
0x18003b173  mov     ecx, 80h
0x18003b178  call    LDAPClientPrint
0x18003b17d  mov     edi, 51h ; 'Q'
0x18003b182  jmp     short loc_18003B199
0x18003b184  inc     dword ptr [rsi+38h]
0x18003b187  xor     r8d, r8d; struct CLdapBer *
0x18003b18a  mov     rcx, [rsp+68h+arg_0]; struct ldap_connection *
0x18003b18f  mov     rdx, rbp; struct CLdapBer *
0x18003b192  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18003b197  mov     edi, eax
0x18003b199  mov     dl, 1; Wait
0x18003b19b  lea     rcx, RequestListLock; Resource
0x18003b1a2  call    cs:__imp_RtlAcquireResourceExclusive
0x18003b1a9  nop     dword ptr [rax+rax+00h]
0x18003b1ae  mov     rcx, r14; lpCriticalSection
0x18003b1b1  call    cs:__imp_EnterCriticalSection
0x18003b1b8  nop     dword ptr [rax+rax+00h]
0x18003b1bd  xchg    rbp, [rsi+28h]
0x18003b1c1  test    rbp, rbp
0x18003b1c4  jz      short loc_18003B1D5
0x18003b1c6  mov     rcx, rbp; this
0x18003b1c9  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18003b1ce  jmp     short loc_18003B1D5
0x18003b1d0  mov     edi, 5Bh ; '['
0x18003b1d5  mov     r12d, [rbx+6Ch]
0x18003b1d9  inc     r15w
0x18003b1dd  add     rsi, 40h ; '@'
0x18003b1e1  cmp     r15w, r13w
0x18003b1e5  jb      loc_18003B0E6
0x18003b1eb  mov     ebp, [rsp+68h+arg_8]
0x18003b1ef  xor     r13d, r13d
0x18003b1f2  mov     r15, [rsp+68h+arg_0]
0x18003b1f7  test    edi, edi
0x18003b1f9  jz      loc_18003B2C3
0x18003b1ff  jmp     short loc_18003B208
0x18003b201  mov     ebp, [rsp+68h+arg_8]
0x18003b205  xor     r13d, r13d
0x18003b208  cmp     byte ptr [rbx+0BAh], 63h ; 'c'
0x18003b20f  jz      short loc_18003B21E
0x18003b211  cmp     edi, 5Bh ; '['
0x18003b214  jnz     short loc_18003B21E
0x18003b216  mov     edi, r13d
0x18003b219  jmp     loc_18003B2BE
0x18003b21e  mov     r15, [rsp+68h+arg_0]
0x18003b223  mov     rdx, rbx
0x18003b226  mov     rcx, r15
0x18003b229  call    SimulateErrorMessage
0x18003b22e  cmp     cs:g_fTracingOn, r13d
0x18003b235  mov     esi, eax
0x18003b237  jz      short loc_18003B26E
0x18003b239  cmp     cs:g_fProviderEnabled, r13d
0x18003b240  jz      short loc_18003B26E
0x18003b242  test    byte ptr cs:g_ulTraceFlags, 80h
0x18003b249  jz      short loc_18003B26E
0x18003b24b  call    cs:__imp_GetCurrentThreadId
0x18003b252  nop     dword ptr [rax+rax+00h]
0x18003b257  mov     r9, r15
0x18003b25a  lea     rdx, aLdapresentrequ; "ldapResentRequests thread 0x%x simulate"...
0x18003b261  mov     r8d, eax
0x18003b264  mov     ecx, 80h
0x18003b269  call    LDAPClientPrint
0x18003b26e  test    esi, esi
0x18003b270  jz      short loc_18003B279
0x18003b272  mov     byte ptr [rbx+0B8h], 1
0x18003b279  mov     edx, 64494D4Ch
0x18003b27e  mov     ecx, 10h
0x18003b283  call    ldapMalloc
0x18003b288  test    rax, rax
0x18003b28b  jz      short loc_18003B2A4
0x18003b28d  mov     rcx, [rsp+68h+arg_18]
0x18003b295  mov     [rax], rcx
0x18003b298  mov     [rax+8], r12d
0x18003b29c  mov     [rsp+68h+arg_18], rax
0x18003b2a4  mov     rcx, rbx
0x18003b2a7  call    ClearPendingListForRequest
0x18003b2ac  test    edi, edi
0x18003b2ae  jz      short loc_18003B2C3
0x18003b2b0  test    ebp, ebp
0x18003b2b2  cmovz   ebp, edi
0x18003b2b5  mov     [rsp+68h+arg_8], ebp
0x18003b2b9  jmp     short loc_18003B2C3
0x18003b2bb  xor     r13d, r13d
0x18003b2be  mov     r15, [rsp+68h+arg_0]
0x18003b2c3  mov     rcx, r14; lpCriticalSection
0x18003b2c6  call    cs:__imp_LeaveCriticalSection
0x18003b2cd  nop     dword ptr [rax+rax+00h]
0x18003b2d2  mov     rsi, [rsp+68h+arg_10]
0x18003b2da  mov     rcx, r14; lpCriticalSection
0x18003b2dd  mov     rsi, [rsi]
0x18003b2e0  mov     [rsp+68h+arg_10], rsi
0x18003b2e8  call    cs:__imp_EnterCriticalSection
0x18003b2ef  nop     dword ptr [rax+rax+00h]
0x18003b2f4  dec     dword ptr [rbx+10h]
0x18003b2f7  cmp     cs:g_fTracingOn, r13d
0x18003b2fe  jz      short loc_18003B32A
0x18003b300  cmp     cs:g_fProviderEnabled, r13d
0x18003b307  jz      short loc_18003B32A
0x18003b309  test    byte ptr cs:g_ulTraceFlags, 4
0x18003b310  jz      short loc_18003B32A
0x18003b312  mov     r9d, [rbx+10h]
0x18003b316  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x18003b31d  mov     r8, rbx
0x18003b320  mov     ecx, 4
0x18003b325  call    LDAPClientPrint
0x18003b32a  mov     rcx, r14; lpCriticalSection
0x18003b32d  cmp     [rbx+10h], r13d
0x18003b331  jnz     short loc_18003B352
0x18003b333  call    cs:__imp_LeaveCriticalSection
0x18003b33a  nop     dword ptr [rax+rax+00h]
0x18003b33f  mov     r12d, 1
0x18003b345  mov     edx, r12d
0x18003b348  mov     rcx, rbx
0x18003b34b  call    DereferenceLdapRequest2
0x18003b350  jmp     short loc_18003B364
0x18003b352  call    cs:__imp_LeaveCriticalSection
0x18003b359  nop     dword ptr [rax+rax+00h]
0x18003b35e  mov     r12d, 1
  ... truncated ...
```
