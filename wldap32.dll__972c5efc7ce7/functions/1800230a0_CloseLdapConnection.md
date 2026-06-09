# CloseLdapConnection

- ea: `0x1800230a0`
- end: `0x1800235a8`
- name: `CloseLdapConnection`
- size: `1288`
- prototype: `__int64 __fastcall(struct ldap_connection *)`
- caller_count: `6`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008710`
- `0x18000b990`
- `0x180025cc8`
- `0x180026b50`
- `0x18002e6d4`
- `0x180042684`

## callees

- `0x1800037a8`
- `0x180008660`
- `0x180008710`
- `0x18000adb0`
- `0x18000b440`
- `0x18000df44`
- `0x180010ef0`
- `0x180011c80`
- `0x180014060`
- `0x180014460`
- `0x18001ce90`
- `0x1800230a0`
- `0x1800235b0`
- `0x180023620`
- `0x1800236f0`
- `0x180029780`
- `0x18002a284`
- `0x18002d714`
- `0x180048390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800230be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023252`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800233fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800234e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002354f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800230be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023252`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800233fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800234e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002354f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023119`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023279`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023451`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023527`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023565`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002358a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023119`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023279`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023451`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023527`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023565`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002358a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023191`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023191`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180023145`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180023145`
- `ntdll!RtlReleaseResource` at `0x1800233df`
- `ntdll!RtlReleaseResource` at `0x180023486`
- `ntdll!RtlReleaseResource` at `0x1800234c8`
- `ntdll!RtlReleaseResource` at `0x1800233df`
- `ntdll!RtlReleaseResource` at `0x180023486`
- `ntdll!RtlReleaseResource` at `0x1800234c8`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002336b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800234a2`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002336b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800234a2`

## pseudocode

```c
void __fastcall CloseLdapConnection(struct ldap_connection *a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  __int64 *v3; // rdi
  __int64 *v4; // rcx
  __int64 v5; // rdi
  int v6; // eax
  int v7; // esi
  unsigned int v8; // edx
  unsigned int v9; // eax
  __int64 *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  struct ldap_request *v14; // rax
  __int64 v15; // [rsp+20h] [rbp-68h] BYREF
  int v16; // [rsp+28h] [rbp-60h]
  __int64 v17; // [rsp+30h] [rbp-58h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 512);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
  if ( *((_BYTE *)a1 + 552) == 1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
      LDAPClientPrint(0x2000000, "Closing connection at %lx\n", (_DWORD)a1);
    *((_BYTE *)a1 + 552) = 2;
    LeaveCriticalSection(v1);
    if ( GlobalParallelRecvMode )
      PostQueuedCompletionStatus(*((HANDLE *)a1 + 112), 0, 0xFFFFFFFFFFFFFFFFuLL, 0);
    else
      LdapWakeupSelect();
    if ( !GlobalParallelRecvMode )
    {
      EnterCriticalSection(&WaiterLock);
      v3 = (__int64 *)GlobalListWaiters;
      while ( v3 != &GlobalListWaiters )
      {
        v4 = v3;
        v3 = (__int64 *)*v3;
        if ( (struct ldap_connection *)v4[2] == a1 )
        {
          *((_BYTE *)v4 + 40) = 1;
          SetEvent((HANDLE)v4[3]);
        }
      }
      LeaveCriticalSection(&WaiterLock);
    }
    if ( *((_QWORD *)a1 + 113) != -1 && *((_BYTE *)a1 + 645) == 1 && *((_BYTE *)a1 + 553) == 8 )
    {
      v5 = ldapMalloc(872, 1816347212);
      if ( v5 )
      {
        v6 = *((_DWORD *)a1 + 250) - 2;
        *(_QWORD *)v5 = 0;
        *(_DWORD *)(v5 + 8) = 0;
        *(_QWORD *)(v5 + 16) = 0;
        *(_QWORD *)(v5 + 836) = 0;
        *(_QWORD *)(v5 + 24) = 0;
        *(_BYTE *)(v5 + 856) = 0;
        *(_QWORD *)(v5 + 860) = v6 != 0 ? 0xFDE9 : 0;
        *(_DWORD *)(v5 + 32) = 0;
        do
        {
          if ( ((GlobalMessageNumber + 1) & 0xFE000000) != 0 )
          {
            EnterCriticalSection(&MessageNumberLock);
            if ( ((GlobalMessageNumber + 1) & 0xFE000000) != 0 )
              GlobalMessageNumber = 0;
            LeaveCriticalSection(&MessageNumberLock);
          }
          v7 = _InterlockedIncrement(&GlobalMessageNumber);
        }
        while ( (v7 & 0xFE000000) != 0 );
        *((_DWORD *)a1 + 260) = v7;
        if ( !CLdapBer::HrStartWriteSequence((CLdapBer *)v5, 0x30u)
          && !CLdapBer::HrAddValue((CLdapBer *)v5, v7, 2u)
          && !CLdapBer::HrAddTag((CLdapBer *)v5, v8)
          && !CLdapBer::HrEndWriteSequence((CLdapBer *)v5) )
        {
          v9 = LdapSend(a1, (struct CLdapBer *)v5, 0);
          if ( v9 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
              LDAPClientPrint(0x100000, "LdapCloseConn connection 0x%x send with error of 0x%x.\n", (_DWORD)a1, v9);
          }
        }
        CLdapBer::`scalar deleting destructor'((CLdapBer *)v5, v8);
      }
      else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
      {
        LDAPClientPrint(0x4000, "LdapCloseConn connection 0x%x could not allocate unbind.\n", (_DWORD)a1);
      }
    }
    CloseCredentials(a1);
    RtlAcquireResourceExclusive(&RequestListLock, 1u);
    v10 = (__int64 *)GlobalListRequests;
    v15 = 0;
    v16 = 8;
    v17 = 0;
    if ( (__int64 *)GlobalListRequests != &GlobalListRequests )
    {
      while ( 1 )
      {
        v11 = ReferenceLdapRequest(v10);
        v12 = v11;
        if ( v11 )
          break;
        v10 = (__int64 *)*v10;
LABEL_56:
        if ( v10 == &GlobalListRequests )
        {
          v1 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 512);
          goto LABEL_58;
        }
      }
      if ( *(struct ldap_connection **)(v11 + 32) != a1 || *(_BYTE *)(v11 + 188) )
      {
        v10 = (__int64 *)*v10;
        v14 = DereferenceLdapRequestEx((struct ldap_request *)v11);
        v12 = (__int64)v14;
        if ( !v14 || CRequestListHolder::Add((CRequestListHolder *)&v15, v14) )
          goto LABEL_56;
        RtlReleaseResource(&RequestListLock);
      }
      else
      {
        RtlReleaseResource(&RequestListLock);
        CloseLdapRequest(v12);
        EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 48));
        --*(_DWORD *)(v12 + 16);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v12, *(_DWORD *)(v12 + 16));
        v13 = (struct _RTL_CRITICAL_SECTION *)(v12 + 48);
        if ( *(_DWORD *)(v12 + 16) )
        {
          LeaveCriticalSection(v13);
LABEL_55:
          RtlAcquireResourceExclusive(&RequestListLock, 1u);
          v10 = (__int64 *)GlobalListRequests;
          goto LABEL_56;
        }
        LeaveCriticalSection(v13);
      }
      DereferenceLdapRequest2((__int64 *)v12, 0);
      goto LABEL_55;
    }
LABEL_58:
    RtlReleaseResource(&RequestListLock);
    CRequestListHolder::FreeAll((CRequestListHolder *)&v15);
    EnterCriticalSection(v1);
    --*(_DWORD *)a1;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)a1, *(_DWORD *)a1);
    if ( *(_DWORD *)a1 )
    {
      LeaveCriticalSection(v1);
    }
    else
    {
      LeaveCriticalSection(v1);
      DereferenceLdapConnection2((__int64)a1, 1);
    }
    EnterCriticalSection(v1);
    *((_BYTE *)a1 + 552) = 3;
    LeaveCriticalSection(v1);
    if ( v17 )
      ldapFree(v17, 1718960716);
  }
  else
  {
    LeaveCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x1800230a0  push    rbx
0x1800230a2  push    rbp
0x1800230a3  push    rsi
0x1800230a4  push    rdi
0x1800230a5  push    r12
0x1800230a7  push    r13
0x1800230a9  push    r14
0x1800230ab  push    r15
0x1800230ad  sub     rsp, 48h
0x1800230b1  lea     rbp, [rcx+200h]
0x1800230b8  mov     rbx, rcx
0x1800230bb  mov     rcx, rbp; lpCriticalSection
0x1800230be  call    cs:__imp_EnterCriticalSection
0x1800230c5  nop     dword ptr [rax+rax+00h]
0x1800230ca  mov     r12d, 1
0x1800230d0  cmp     [rbx+228h], r12b
0x1800230d7  jnz     loc_180023587
0x1800230dd  xor     r14d, r14d
0x1800230e0  cmp     cs:g_fTracingOn, r14d
0x1800230e7  jz      short loc_18002310F
0x1800230e9  cmp     cs:g_fProviderEnabled, r14d
0x1800230f0  jz      short loc_18002310F
0x1800230f2  mov     ecx, 2000000h
0x1800230f7  test    cs:g_ulTraceFlags, rcx
0x1800230fe  jz      short loc_18002310F
0x180023100  mov     r8, rbx
0x180023103  lea     rdx, aClosingConnect; "Closing connection at %lx\n"
0x18002310a  call    LDAPClientPrint
0x18002310f  mov     rcx, rbp; lpCriticalSection
0x180023112  mov     byte ptr [rbx+228h], 2
0x180023119  call    cs:__imp_LeaveCriticalSection
0x180023120  nop     dword ptr [rax+rax+00h]
0x180023125  cmp     cs:GlobalParallelRecvMode, r14d
0x18002312c  jnz     short loc_180023135
0x18002312e  call    LdapWakeupSelect
0x180023133  jmp     short loc_180023151
0x180023135  mov     rcx, [rbx+380h]; CompletionPort
0x18002313c  xor     r9d, r9d; lpOverlapped
0x18002313f  or      r8, 0FFFFFFFFFFFFFFFFh; dwCompletionKey
0x180023143  xor     edx, edx; dwNumberOfBytesTransferred
0x180023145  call    cs:__imp_PostQueuedCompletionStatus
0x18002314c  nop     dword ptr [rax+rax+00h]
0x180023151  cmp     cs:GlobalParallelRecvMode, r14d
0x180023158  jnz     short loc_1800231B5
0x18002315a  lea     rcx, WaiterLock; lpCriticalSection
0x180023161  call    cs:__imp_EnterCriticalSection
0x180023168  nop     dword ptr [rax+rax+00h]
0x18002316d  mov     rdi, cs:GlobalListWaiters
0x180023174  lea     rsi, GlobalListWaiters
0x18002317b  jmp     short loc_18002319D
0x18002317d  lea     rcx, [rdi]
0x180023180  mov     rdi, [rdi]
0x180023183  cmp     [rcx+10h], rbx
0x180023187  jnz     short loc_18002319D
0x180023189  mov     [rcx+28h], r12b
0x18002318d  mov     rcx, [rcx+18h]; hEvent
0x180023191  call    cs:__imp_SetEvent
0x180023198  nop     dword ptr [rax+rax+00h]
0x18002319d  cmp     rdi, rsi
0x1800231a0  jnz     short loc_18002317D
0x1800231a2  lea     rcx, WaiterLock; lpCriticalSection
0x1800231a9  call    cs:__imp_LeaveCriticalSection
0x1800231b0  nop     dword ptr [rax+rax+00h]
0x1800231b5  cmp     qword ptr [rbx+388h], 0FFFFFFFFFFFFFFFFh
0x1800231bd  jz      loc_180023356
0x1800231c3  cmp     [rbx+285h], r12b
0x1800231ca  jnz     loc_180023356
0x1800231d0  cmp     byte ptr [rbx+229h], 8
0x1800231d7  jnz     loc_180023356
0x1800231dd  mov     edx, 6C43424Ch
0x1800231e2  mov     ecx, 368h
0x1800231e7  call    ldapMalloc
0x1800231ec  mov     rdi, rax
0x1800231ef  test    rax, rax
0x1800231f2  jz      loc_180023327
0x1800231f8  mov     eax, [rbx+3E8h]
0x1800231fe  mov     r15d, 0FE000000h
0x180023204  sub     eax, 2
0x180023207  mov     [rdi], r14
0x18002320a  neg     eax
0x18002320c  mov     [rdi+8], r14d
0x180023210  mov     [rdi+10h], r14
0x180023214  sbb     eax, eax
0x180023216  mov     [rdi+344h], r14
0x18002321d  and     eax, 0FDE9h
0x180023222  mov     [rdi+18h], r14
0x180023226  mov     [rdi+358h], r14b
0x18002322d  mov     [rdi+360h], r14d
0x180023234  mov     [rdi+35Ch], eax
0x18002323a  mov     [rdi+20h], r14d
0x18002323e  mov     eax, cs:GlobalMessageNumber
0x180023244  inc     eax
0x180023246  test    r15d, eax
0x180023249  jz      short loc_180023285
0x18002324b  lea     rcx, MessageNumberLock; lpCriticalSection
0x180023252  call    cs:__imp_EnterCriticalSection
0x180023259  nop     dword ptr [rax+rax+00h]
0x18002325e  mov     eax, cs:GlobalMessageNumber
0x180023264  inc     eax
0x180023266  test    r15d, eax
0x180023269  jz      short loc_180023272
0x18002326b  mov     cs:GlobalMessageNumber, r14d
0x180023272  lea     rcx, MessageNumberLock; lpCriticalSection
0x180023279  call    cs:__imp_LeaveCriticalSection
0x180023280  nop     dword ptr [rax+rax+00h]
0x180023285  mov     esi, r12d
0x180023288  lock xadd cs:GlobalMessageNumber, esi
0x180023290  add     esi, r12d
0x180023293  test    r15d, esi
0x180023296  jnz     short loc_18002323E
0x180023298  mov     edx, 30h ; '0'; unsigned int
0x18002329d  mov     [rbx+410h], esi
0x1800232a3  mov     rcx, rdi; this
0x1800232a6  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800232ab  test    eax, eax
0x1800232ad  jnz     short loc_18002331D
0x1800232af  lea     r8d, [rax+2]; unsigned int
0x1800232b3  mov     edx, esi; int
0x1800232b5  mov     rcx, rdi; this
0x1800232b8  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x1800232bd  test    eax, eax
0x1800232bf  jnz     short loc_18002331D
0x1800232c1  mov     rcx, rdi; this
0x1800232c4  call    ?HrAddTag@CLdapBer@@QEAAKK@Z; CLdapBer::HrAddTag(ulong)
0x1800232c9  test    eax, eax
0x1800232cb  jnz     short loc_18002331D
0x1800232cd  mov     rcx, rdi; this
0x1800232d0  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x1800232d5  test    eax, eax
0x1800232d7  jnz     short loc_18002331D
0x1800232d9  xor     r8d, r8d; struct CLdapBer *
0x1800232dc  mov     rdx, rdi; struct CLdapBer *
0x1800232df  mov     rcx, rbx; struct ldap_connection *
0x1800232e2  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x1800232e7  test    eax, eax
0x1800232e9  jz      short loc_18002331D
0x1800232eb  cmp     cs:g_fTracingOn, r14d
0x1800232f2  jz      short loc_18002331D
0x1800232f4  cmp     cs:g_fProviderEnabled, r14d
0x1800232fb  jz      short loc_18002331D
0x1800232fd  mov     ecx, 100000h
0x180023302  test    cs:g_ulTraceFlags, rcx
0x180023309  jz      short loc_18002331D
0x18002330b  mov     r9d, eax
0x18002330e  lea     rdx, aLdapcloseconnC; "LdapCloseConn connection 0x%x send with"...
0x180023315  mov     r8, rbx
0x180023318  call    LDAPClientPrint
0x18002331d  mov     rcx, rdi; this
0x180023320  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x180023325  jmp     short loc_180023356
0x180023327  cmp     cs:g_fTracingOn, r14d
0x18002332e  jz      short loc_180023356
0x180023330  cmp     cs:g_fProviderEnabled, r14d
0x180023337  jz      short loc_180023356
0x180023339  mov     ecx, 4000h
0x18002333e  test    cs:g_ulTraceFlags, rcx
0x180023345  jz      short loc_180023356
0x180023347  mov     r8, rbx
0x18002334a  lea     rdx, aLdapcloseconnC_0; "LdapCloseConn connection 0x%x could not"...
0x180023351  call    LDAPClientPrint
0x180023356  mov     rcx, rbx
0x180023359  call    CloseCredentials
0x18002335e  lea     r15, RequestListLock
0x180023365  mov     dl, r12b; Wait
0x180023368  mov     rcx, r15; Resource
0x18002336b  call    cs:__imp_RtlAcquireResourceExclusive
0x180023372  nop     dword ptr [rax+rax+00h]
0x180023377  mov     rsi, cs:GlobalListRequests
0x18002337e  lea     rax, GlobalListRequests
0x180023385  mov     [rsp+88h+var_68], r14
0x18002338a  mov     r13d, 4
0x180023390  mov     [rsp+88h+var_60], 8
0x180023398  mov     [rsp+88h+var_58], r14
0x18002339d  cmp     rsi, rax
0x1800233a0  jz      loc_1800234C5
0x1800233a6  lea     rbp, GlobalListRequests
0x1800233ad  mov     rcx, rsi
0x1800233b0  call    ReferenceLdapRequest
0x1800233b5  mov     rdi, rax
0x1800233b8  test    rax, rax
0x1800233bb  jnz     short loc_1800233C5
0x1800233bd  mov     rsi, [rsi]
0x1800233c0  jmp     loc_1800234B5
0x1800233c5  cmp     [rax+20h], rbx
0x1800233c9  jnz     loc_18002345F
0x1800233cf  cmp     [rax+0BCh], r14b
0x1800233d6  jnz     loc_18002345F
0x1800233dc  mov     rcx, r15; Resource
0x1800233df  call    cs:__imp_RtlReleaseResource
0x1800233e6  nop     dword ptr [rax+rax+00h]
0x1800233eb  mov     rcx, rdi
0x1800233ee  call    CloseLdapRequest
0x1800233f3  lea     rsi, [rdi+30h]
0x1800233f7  mov     rcx, rsi; lpCriticalSection
0x1800233fa  call    cs:__imp_EnterCriticalSection
0x180023401  nop     dword ptr [rax+rax+00h]
0x180023406  dec     dword ptr [rdi+10h]
0x180023409  cmp     cs:g_fTracingOn, r14d
0x180023410  jz      short loc_18002343A
0x180023412  cmp     cs:g_fProviderEnabled, r14d
0x180023419  jz      short loc_18002343A
0x18002341b  test    byte ptr cs:g_ulTraceFlags, r13b
0x180023422  jz      short loc_18002343A
0x180023424  mov     r9d, [rdi+10h]
0x180023428  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x18002342f  mov     r8, rdi
0x180023432  mov     ecx, r13d
0x180023435  call    LDAPClientPrint
0x18002343a  mov     rcx, rsi; lpCriticalSection
0x18002343d  cmp     [rdi+10h], r14d
0x180023441  jnz     short loc_180023451
0x180023443  call    cs:__imp_LeaveCriticalSection
0x18002344a  nop     dword ptr [rax+rax+00h]
0x18002344f  jmp     short loc_180023492
0x180023451  call    cs:__imp_LeaveCriticalSection
0x180023458  nop     dword ptr [rax+rax+00h]
0x18002345d  jmp     short loc_18002349C
0x18002345f  mov     rsi, [rsi]
0x180023462  mov     rcx, rdi; struct ldap_request *
0x180023465  call    ?DereferenceLdapRequestEx@@YAPEAUldap_request@@PEAU1@@Z; DereferenceLdapRequestEx(ldap_request *)
0x18002346a  mov     rdi, rax
0x18002346d  test    rax, rax
0x180023470  jz      short loc_1800234B5
0x180023472  mov     rdx, rax; struct ldap_request *
0x180023475  lea     rcx, [rsp+88h+var_68]; this
0x18002347a  call    ?Add@CRequestListHolder@@QEAA_NPEAUldap_request@@@Z; CRequestListHolder::Add(ldap_request *)
0x18002347f  test    al, al
0x180023481  jnz     short loc_1800234B5
0x180023483  mov     rcx, r15; Resource
0x180023486  call    cs:__imp_RtlReleaseResource
0x18002348d  nop     dword ptr [rax+rax+00h]
0x180023492  xor     edx, edx
0x180023494  mov     rcx, rdi
0x180023497  call    DereferenceLdapRequest2
0x18002349c  mov     dl, r12b; Wait
0x18002349f  mov     rcx, r15; Resource
0x1800234a2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800234a9  nop     dword ptr [rax+rax+00h]
0x1800234ae  mov     rsi, cs:GlobalListRequests
0x1800234b5  cmp     rsi, rbp
0x1800234b8  jnz     loc_1800233AD
0x1800234be  lea     rbp, [rbx+200h]
0x1800234c5  mov     rcx, r15; Resource
0x1800234c8  call    cs:__imp_RtlReleaseResource
0x1800234cf  nop     dword ptr [rax+rax+00h]
0x1800234d4  lea     rcx, [rsp+88h+var_68]; this
0x1800234d9  call    ?FreeAll@CRequestListHolder@@QEAAXXZ; CRequestListHolder::FreeAll(void)
0x1800234de  mov     rcx, rbp; lpCriticalSection
0x1800234e1  call    cs:__imp_EnterCriticalSection
0x1800234e8  nop     dword ptr [rax+rax+00h]
0x1800234ed  dec     dword ptr [rbx]
0x1800234ef  cmp     cs:g_fTracingOn, r14d
0x1800234f6  jz      short loc_18002351F
0x1800234f8  cmp     cs:g_fProviderEnabled, r14d
0x1800234ff  jz      short loc_18002351F
0x180023501  test    byte ptr cs:g_ulTraceFlags, r13b
0x180023508  jz      short loc_18002351F
0x18002350a  mov     r9d, [rbx]
0x18002350d  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180023514  mov     r8, rbx
0x180023517  mov     ecx, r13d
0x18002351a  call    LDAPClientPrint
0x18002351f  mov     rcx, rbp; lpCriticalSection
0x180023522  cmp     [rbx], r14d
0x180023525  jnz     short loc_180023540
0x180023527  call    cs:__imp_LeaveCriticalSection
0x18002352e  nop     dword ptr [rax+rax+00h]
0x180023533  mov     edx, r12d
0x180023536  mov     rcx, rbx
0x180023539  call    DereferenceLdapConnection2
0x18002353e  jmp     short loc_18002354C
0x180023540  call    cs:__imp_LeaveCriticalSection
0x180023547  nop     dword ptr [rax+rax+00h]
0x18002354c  mov     rcx, rbp; lpCriticalSection
0x18002354f  call    cs:__imp_EnterCriticalSection
0x180023556  nop     dword ptr [rax+rax+00h]
0x18002355b  mov     rcx, rbp; lpCriticalSection
0x18002355e  mov     byte ptr [rbx+228h], 3
0x180023565  call    cs:__imp_LeaveCriticalSection
0x18002356c  nop     dword ptr [rax+rax+00h]
0x180023571  mov     rcx, [rsp+88h+var_58]
0x180023576  test    rcx, rcx
0x180023579  jz      short loc_180023596
0x18002357b  mov     edx, 6675424Ch
0x180023580  call    ldapFree
0x180023585  jmp     short loc_180023596
0x180023587  mov     rcx, rbp; lpCriticalSection
0x18002358a  call    cs:__imp_LeaveCriticalSection
0x180023591  nop     dword ptr [rax+rax+00h]
0x180023596  add     rsp, 48h
0x18002359a  pop     r15
0x18002359c  pop     r14
0x18002359e  pop     r13
0x1800235a0  pop     r12
0x1800235a2  pop     rdi
0x1800235a3  pop     rsi
0x1800235a4  pop     rbp
0x1800235a5  pop     rbx
0x1800235a6  retn
```
