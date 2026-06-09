# LdapWaitForResponseFromServerParallel(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar,int)

- ea: `0x1800198b4`
- end: `0x180019f81`
- name: `?LdapWaitForResponseFromServerParallel@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@EH@Z`
- size: `1741`
- prototype: `unsigned int __usercall@<eax>(struct ldap_connection *@<rcx>, struct ldap_request *@<rdx>, DWORD dwMilliseconds@<r8d>, unsigned int@<r9d>, struct ldapmsg **, char, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180018d50`

## callees

- `0x1800037a8`
- `0x180008070`
- `0x1800198b4`
- `0x180019f88`
- `0x18002e14c`
- `0x1800319dc`
- `0x180033014`
- `0x18004c754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001995a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001995a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019b3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019b3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180019a7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180019a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c87c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c87c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800198e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019c3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019cf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019e87`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800198e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019c3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019cf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019e87`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180019bac`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180019bac`

## pseudocode

```c
__int64 __fastcall LdapWaitForResponseFromServerParallel(
        struct ldap_connection *a1,
        struct ldap_request *a2,
        DWORD dwMilliseconds,
        unsigned int a4,
        struct ldapmsg **a5,
        char a6,
        int a7)
{
  unsigned int v7; // r12d
  ULONGLONG TickCount64; // r15
  void *v11; // rdi
  int v12; // esi
  DWORD v13; // eax
  _BOOL8 v14; // r14
  __int64 v16; // rax
  DWORD v17; // esi
  DWORD LastError; // eax
  ULONGLONG v19; // rax
  ULONGLONG v20; // rdi
  unsigned __int64 v21; // rax
  int v22; // ecx
  char v23; // al
  unsigned int v24; // ebx
  ULONGLONG v25; // rax
  unsigned __int64 v26; // rax
  __int64 v27; // [rsp+0h] [rbp-F8h] BYREF
  int v28; // [rsp+40h] [rbp-B8h]
  int v29; // [rsp+48h] [rbp-B0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-A8h]
  __int64 *v31; // [rsp+58h] [rbp-A0h]
  BOOL v32; // [rsp+60h] [rbp-98h] BYREF
  void *v33; // [rsp+68h] [rbp-90h]
  __int128 v34; // [rsp+70h] [rbp-88h] BYREF
  __int128 v35; // [rsp+80h] [rbp-78h]
  ULONGLONG v36; // [rsp+90h] [rbp-68h]
  int v37; // [rsp+98h] [rbp-60h]
  int v38; // [rsp+9Ch] [rbp-5Ch]
  void *v39; // [rsp+A0h] [rbp-58h]
  HANDLE Handles[10]; // [rsp+A8h] [rbp-50h] BYREF
  unsigned int ResponseFromServer; // [rsp+108h] [rbp+10h]
  int v42; // [rsp+108h] [rbp+10h]
  unsigned int v44; // [rsp+110h] [rbp+18h]

  v31 = &v27;
  v7 = dwMilliseconds;
  TickCount64 = GetTickCount64();
  v36 = TickCount64;
  v28 = 0;
  v11 = (void *)*((_QWORD *)a1 + 110);
  v39 = v11;
  v33 = v11;
  v32 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)a1 + 840);
  v29 = 0;
  v34 = 0;
  v35 = 0;
  v12 = 0;
  *a5 = 0;
  LODWORD(v35) = *((_DWORD *)a2 + 27);
  v13 = WaitForSingleObject(v11, 0);
  v14 = v13 == 0;
  v32 = v13 == 0;
  if ( !v13 )
  {
    _InterlockedIncrement64(&qword_180066260);
    goto LABEL_3;
  }
  CAutoCS::LockExclusive((CAutoCS *)&v29);
  v16 = *((_QWORD *)a1 + 111);
  if ( v16 )
    *(_QWORD *)(v16 + 8) = &v34;
  v34 = *((unsigned __int64 *)a1 + 111);
  *((_QWORD *)a1 + 111) = &v34;
  v28 = 1;
  *((_QWORD *)&v35 + 1) = CreateEventA(0, 0, 0, 0);
  CAutoCS::Unlock((CAutoCS *)&v29);
  if ( !*((_QWORD *)&v35 + 1) )
  {
    CAutoCS::Unlock((CAutoCS *)&v29);
    CAutoMutex::Unlock((CAutoMutex *)&v32);
    local_unwind_0(v31, &loc_180019AD2);
    return 82;
  }
  while ( 1 )
  {
LABEL_3:
    ResponseFromServer = LdapGetResponseFromServer(a1, a2, a4, a5);
    if ( *a5 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
        LDAPClientPrint(
          1024,
          "%s Received our data, returning result conn:0x%p\n",
          "LdapWaitForResponseFromServerParallel:1472",
          a1);
      CAutoCS::Unlock((CAutoCS *)&v29);
      CAutoMutex::Unlock((CAutoMutex *)&v32);
      local_unwind_0(v31, &loc_180019A12);
      return ResponseFromServer;
    }
    if ( v14 )
    {
      v44 = LdapWaitForResponseFromServerParallelWithConnectionLock(a1, a2, v7, a4, a5, a6, a7);
      if ( v29 )
      {
        LeaveCriticalSection(lpCriticalSection);
        v29 = 0;
      }
      ReleaseMutex(v11);
      v32 = 0;
      local_unwind_0(v31, &loc_180019B5F);
      return v44;
    }
    v42 = v12 + 1;
    v37 = v12 + 1;
    Handles[0] = *((HANDLE *)&v35 + 1);
    Handles[1] = v11;
    _InterlockedIncrement(&GlobalWaitersCount);
    v17 = WaitForMultipleObjects(2u, Handles, 0, v7);
    _InterlockedDecrement(&GlobalWaitersCount);
    if ( v17 == -1 )
    {
      LastError = GetLastError();
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(
          0x10000000,
          "%s Wait failed for an unexpected reason conn:0x%p error:%d\n",
          "LdapWaitForResponseFromServerParallel:1513",
          a1,
          LastError);
      CAutoCS::Unlock((CAutoCS *)&v29);
      CAutoMutex::Unlock((CAutoMutex *)&v32);
      local_unwind_0(v31, &loc_180019C32);
      return 82;
    }
    v19 = GetTickCount64();
    v20 = v19;
    if ( v17 == 258 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(
          0x10000000,
          "%s Timeout exceeded while acquiring connection lock conn:0x%p lockWaitTime:%I64u\n",
          "LdapWaitForResponseFromServerParallel:1528",
          a1,
          v19 - TickCount64);
      CAutoCS::Unlock((CAutoCS *)&v29);
      CAutoMutex::Unlock((CAutoMutex *)&v32);
      local_unwind_0(v31, &loc_180019CB7);
      return 85;
    }
    LODWORD(v14) = v17 == 1;
    v32 = v14;
    if ( g_fTracingOn )
    {
      if ( g_fProviderEnabled )
      {
        if ( (g_ulTraceFlags & 0x20000000) != 0 )
        {
          v21 = GetTickCount64() - v36;
          if ( v21 > 0xFA )
            LDAPClientPrint(
              0x20000000,
              "%s (took %lu ms) Finished waiting for connection lock and event to be signaled for connection conn:%p lock"
              "WaitTime:%I64u fHasConnLock:%d fEventSignaled:%d\n",
              "LdapWaitForResponseFromServerParallel:1546",
              v21,
              a1,
              v20 - v36,
              v17 == 1,
              v17 == 0);
        }
      }
    }
    if ( !v17 )
    {
      _InterlockedIncrement64(&qword_180066268);
      v22 = g_fTracingOn;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
      {
        LDAPClientPrint(
          1024,
          "%s Event was signaled conn:0x%p waitCount:%lu\n",
          "LdapWaitForResponseFromServerParallel:1561",
          a1,
          v42);
        v22 = g_fTracingOn;
      }
      v23 = *((_BYTE *)a2 + 188);
      if ( v23 || *((_BYTE *)a2 + 184) )
      {
        v24 = (v23 != 0) + 88;
        if ( v22 && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientPrint(
            0x10000000,
            "%s request is no longer in a valid state error:%d\n",
            "LdapWaitForResponseFromServerParallel:1571",
            v24);
        CAutoCS::Unlock((CAutoCS *)&v29);
        CAutoMutex::Unlock((CAutoMutex *)&v32);
        local_unwind_0(v31, &loc_180019E1D);
        return v24;
      }
    }
    if ( v17 == 1 )
    {
      _InterlockedIncrement64(&qword_180066248);
      if ( g_fTracingOn )
      {
        if ( g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
          LDAPClientPrint(
            1024,
            "%s Acquired connection lock conn:0x%p waitCount:%lu\n",
            "LdapWaitForResponseFromServerParallel:1584",
            a1,
            v42);
      }
    }
    if ( dwMilliseconds - 1 > 0xFFFFFFFD )
    {
      TickCount64 = v36;
      goto LABEL_63;
    }
    v25 = GetTickCount64();
    TickCount64 = v36;
    v26 = v25 - v36;
    if ( v26 >= dwMilliseconds )
      break;
    v7 = dwMilliseconds - v26;
    v38 = dwMilliseconds - v26;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
      LDAPClientPrint(
        1024,
        "%s Remaining timeout after wait conn:0x%p ulTimeoutRemaining:%lu\n",
        "LdapWaitForResponseFromServerParallel:1597",
        a1,
        dwMilliseconds - v26);
LABEL_63:
    v11 = v39;
    v12 = v42;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
    LDAPClientPrint(
      0x10000000,
      "%s Timeout exceeded while retrying wait conn:0x%p\n",
      "LdapWaitForResponseFromServerParallel:1604",
      a1);
  CAutoCS::Unlock((CAutoCS *)&v29);
  CAutoMutex::Unlock((CAutoMutex *)&v32);
  local_unwind_0(v31, &loc_180019F5A);
  return 85;
}

```

## disassembly

```asm
0x1800198b4  mov     [rsp+arg_18], r9d
0x1800198b9  mov     [rsp+arg_10], r8d
0x1800198be  mov     [rsp+arg_0], rcx
0x1800198c3  push    rbx
0x1800198c4  push    rsi
0x1800198c5  push    rdi
0x1800198c6  push    r12
0x1800198c8  push    r13
0x1800198ca  push    r14
0x1800198cc  push    r15
0x1800198ce  sub     rsp, 0C0h
0x1800198d5  mov     [rsp+0F8h+var_A0], rsp
0x1800198da  mov     r12d, r8d
0x1800198dd  mov     r13, rdx
0x1800198e0  mov     rbx, rcx
0x1800198e3  call    cs:__imp_GetTickCount64
0x1800198ea  nop     dword ptr [rax+rax+00h]
0x1800198ef  mov     r15, rax
0x1800198f2  mov     [rsp+0F8h+var_68], rax
0x1800198fa  xor     r14d, r14d
0x1800198fd  mov     [rsp+0F8h+var_B8], r14d
0x180019902  mov     rdi, [rbx+370h]
0x180019909  mov     [rsp+0F8h+var_58], rdi
0x180019911  mov     [rsp+0F8h+var_90], rdi
0x180019916  mov     [rsp+0F8h+var_98], r14d
0x18001991b  lea     r10, [rbx+348h]
0x180019922  mov     [rsp+0F8h+lpCriticalSection], r10
0x180019927  mov     [rsp+0F8h+var_B0], r14d
0x18001992c  xorps   xmm0, xmm0
0x18001992f  movups  [rsp+0F8h+var_88], xmm0
0x180019934  movups  [rsp+0F8h+var_78], xmm0
0x18001993c  mov     esi, r14d
0x18001993f  mov     rax, [rsp+0F8h+arg_20]
0x180019947  mov     [rax], r14
0x18001994a  mov     eax, [r13+6Ch]
0x18001994e  mov     dword ptr [rsp+0F8h+var_78], eax
0x180019955  xor     edx, edx; dwMilliseconds
0x180019957  mov     rcx, rdi; hHandle
0x18001995a  call    cs:__imp_WaitForSingleObject
0x180019961  nop     dword ptr [rax+rax+00h]
0x180019966  test    eax, eax
0x180019968  setz    r14b
0x18001996c  mov     [rsp+0F8h+var_98], r14d
0x180019971  test    eax, eax
0x180019973  jnz     loc_180019A2D
0x180019979  lock inc cs:qword_180066260
0x180019981  mov     r9, [rsp+0F8h+arg_20]; struct ldapmsg **
0x180019989  mov     r8d, [rsp+0F8h+arg_18]; unsigned int
0x180019991  mov     rdx, r13; struct ldap_request *
0x180019994  mov     rcx, rbx; struct ldap_connection *
0x180019997  call    ?LdapGetResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KPEAPEAUldapmsg@@@Z; LdapGetResponseFromServer(ldap_connection *,ldap_request *,ulong,ldapmsg * *)
0x18001999c  mov     [rsp+0F8h+arg_8], eax
0x1800199a3  mov     rcx, [rsp+0F8h+arg_20]
0x1800199ab  xor     eax, eax
0x1800199ad  cmp     [rcx], rax
0x1800199b0  jz      loc_180019ADC
0x1800199b6  cmp     cs:g_fTracingOn, eax
0x1800199bc  jz      short loc_1800199EC
0x1800199be  cmp     cs:g_fProviderEnabled, eax
0x1800199c4  jz      short loc_1800199EC
0x1800199c6  mov     eax, 400h
0x1800199cb  test    cs:g_ulTraceFlags, rax
0x1800199d2  jz      short loc_1800199EC
0x1800199d4  mov     r9, rbx
0x1800199d7  lea     r8, aLdapwaitforres_19; "LdapWaitForResponseFromServerParallel:1"...
0x1800199de  lea     rdx, aSReceivedOurDa; "%s Received our data, returning result "...
0x1800199e5  mov     ecx, eax
0x1800199e7  call    LDAPClientPrint
0x1800199ec  lea     rcx, [rsp+0F8h+var_B0]; this
0x1800199f1  call    ?Unlock@CAutoCS@@QEAAXXZ; CAutoCS::Unlock(void)
0x1800199f6  lea     rcx, [rsp+0F8h+var_98]; this
0x1800199fb  call    ?Unlock@CAutoMutex@@QEAAXXZ; CAutoMutex::Unlock(void)
0x180019a00  lea     rdx, loc_180019A12
0x180019a07  mov     rcx, [rsp+0F8h+var_A0]
0x180019a0c  call    _local_unwind_0
0x180019a11  nop
0x180019a12  mov     eax, [rsp+0F8h+arg_8]
0x180019a19  add     rsp, 0C0h
0x180019a20  pop     r15
0x180019a22  pop     r14
0x180019a24  pop     r13
0x180019a26  pop     r12
0x180019a28  pop     rdi
0x180019a29  pop     rsi
0x180019a2a  pop     rbx
0x180019a2b  retn
0x180019a2d  lea     rcx, [rsp+0F8h+var_B0]; this
0x180019a32  call    ?LockExclusive@CAutoCS@@QEAAXXZ; CAutoCS::LockExclusive(void)
0x180019a37  mov     rax, [rbx+378h]
0x180019a3e  test    rax, rax
0x180019a41  jz      short loc_180019A4C
0x180019a43  lea     rcx, [rsp+0F8h+var_88]
0x180019a48  mov     [rax+8], rcx
0x180019a4c  mov     rax, [rbx+378h]
0x180019a53  mov     qword ptr [rsp+0F8h+var_88], rax
0x180019a58  mov     qword ptr [rsp+0F8h+var_88+8], 0
0x180019a61  lea     rax, [rsp+0F8h+var_88]
0x180019a66  mov     [rbx+378h], rax
0x180019a6d  mov     [rsp+0F8h+var_B8], 1
0x180019a75  xor     r9d, r9d; lpName
0x180019a78  xor     r8d, r8d; bInitialState
0x180019a7b  xor     edx, edx; bManualReset
0x180019a7d  xor     ecx, ecx; lpEventAttributes
0x180019a7f  call    cs:__imp_CreateEventA
0x180019a86  nop     dword ptr [rax+rax+00h]
0x180019a8b  mov     qword ptr [rsp+0F8h+var_78+8], rax
0x180019a93  lea     rcx, [rsp+0F8h+var_B0]; this
0x180019a98  call    ?Unlock@CAutoCS@@QEAAXXZ; CAutoCS::Unlock(void)
0x180019a9d  cmp     qword ptr [rsp+0F8h+var_78+8], 0
0x180019aa6  jnz     loc_180019981
0x180019aac  lea     rcx, [rsp+0F8h+var_B0]; this
0x180019ab1  call    ?Unlock@CAutoCS@@QEAAXXZ; CAutoCS::Unlock(void)
0x180019ab6  lea     rcx, [rsp+0F8h+var_98]; this
0x180019abb  call    ?Unlock@CAutoMutex@@QEAAXXZ; CAutoMutex::Unlock(void)
0x180019ac0  lea     rdx, loc_180019AD2
0x180019ac7  mov     rcx, [rsp+0F8h+var_A0]
0x180019acc  call    _local_unwind_0
0x180019ad1  nop
0x180019ad2  mov     eax, 52h ; 'R'
0x180019ad7  jmp     loc_180019A19
0x180019adc  test    r14d, r14d
0x180019adf  jz      loc_180019B6B
0x180019ae5  mov     eax, [rsp+0F8h+arg_30]
0x180019aec  mov     [rsp+0F8h+var_C8], eax; int
0x180019af0  mov     al, [rsp+0F8h+arg_28]
0x180019af7  mov     [rsp+0F8h+var_D0], al; unsigned __int8
0x180019afb  mov     [rsp+0F8h+var_D8], rcx; struct ldapmsg **
0x180019b00  mov     r9d, [rsp+0F8h+arg_18]; unsigned int
0x180019b08  mov     r8d, r12d; unsigned int
0x180019b0b  mov     rdx, r13; struct ldap_request *
0x180019b0e  mov     rcx, rbx; struct ldap_connection *
0x180019b11  call    ?LdapWaitForResponseFromServerParallelWithConnectionLock@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@EH@Z; LdapWaitForResponseFromServerParallelWithConnectionLock(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar,int)
0x180019b16  mov     [rsp+0F8h+arg_10], eax
0x180019b1d  xor     ebx, ebx
0x180019b1f  cmp     [rsp+0F8h+var_B0], ebx
0x180019b23  jz      short loc_180019B3A
0x180019b25  mov     rcx, [rsp+0F8h+lpCriticalSection]; lpCriticalSection
0x180019b2a  call    cs:__imp_LeaveCriticalSection
0x180019b31  nop     dword ptr [rax+rax+00h]
0x180019b36  mov     [rsp+0F8h+var_B0], ebx
0x180019b3a  mov     rcx, rdi; hMutex
0x180019b3d  call    cs:__imp_ReleaseMutex
0x180019b44  nop     dword ptr [rax+rax+00h]
0x180019b49  mov     [rsp+0F8h+var_98], ebx
0x180019b4d  lea     rdx, loc_180019B5F
0x180019b54  mov     rcx, [rsp+0F8h+var_A0]
0x180019b59  call    _local_unwind_0
0x180019b5e  nop
0x180019b5f  mov     eax, [rsp+0F8h+arg_10]
0x180019b66  jmp     loc_180019A19
0x180019b6b  inc     esi
0x180019b6d  mov     [rsp+0F8h+arg_8], esi
0x180019b74  mov     [rsp+0F8h+var_60], esi
0x180019b7b  mov     rax, qword ptr [rsp+0F8h+var_78+8]
0x180019b83  mov     [rsp+0F8h+Handles], rax
0x180019b8b  mov     [rsp+0F8h+var_48], rdi
0x180019b93  lock inc cs:?GlobalWaitersCount@@3JA; long GlobalWaitersCount
0x180019b9a  mov     r9d, r12d; dwMilliseconds
0x180019b9d  xor     r8d, r8d; bWaitAll
0x180019ba0  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180019ba8  lea     ecx, [r8+2]; nCount
0x180019bac  call    cs:__imp_WaitForMultipleObjects
0x180019bb3  nop     dword ptr [rax+rax+00h]
0x180019bb8  mov     esi, eax
0x180019bba  lock dec cs:?GlobalWaitersCount@@3JA; long GlobalWaitersCount
0x180019bc1  cmp     eax, 0FFFFFFFFh
0x180019bc4  jnz     short loc_180019C3C
0x180019bc6  call    cs:__imp_GetLastError
0x180019bcd  nop     dword ptr [rax+rax+00h]
0x180019bd2  cmp     cs:g_fTracingOn, 0
0x180019bd9  jz      short loc_180019C0C
0x180019bdb  cmp     cs:g_fProviderEnabled, 0
0x180019be2  jz      short loc_180019C0C
0x180019be4  mov     ecx, 10000000h
0x180019be9  test    cs:g_ulTraceFlags, rcx
0x180019bf0  jz      short loc_180019C0C
0x180019bf2  mov     dword ptr [rsp+0F8h+var_D8], eax
0x180019bf6  mov     r9, rbx
0x180019bf9  lea     r8, aLdapwaitforres_6; "LdapWaitForResponseFromServerParallel:1"...
0x180019c00  lea     rdx, aSWaitFailedFor; "%s Wait failed for an unexpected reason"...
0x180019c07  call    LDAPClientPrint
0x180019c0c  lea     rcx, [rsp+0F8h+var_B0]; this
0x180019c11  call    ?Unlock@CAutoCS@@QEAAXXZ; CAutoCS::Unlock(void)
0x180019c16  lea     rcx, [rsp+0F8h+var_98]; this
0x180019c1b  call    ?Unlock@CAutoMutex@@QEAAXXZ; CAutoMutex::Unlock(void)
0x180019c20  lea     rdx, loc_180019C32
0x180019c27  mov     rcx, [rsp+0F8h+var_A0]
0x180019c2c  call    _local_unwind_0
0x180019c31  nop
0x180019c32  mov     eax, 52h ; 'R'
0x180019c37  jmp     loc_180019A19
0x180019c3c  call    cs:__imp_GetTickCount64
0x180019c43  nop     dword ptr [rax+rax+00h]
0x180019c48  mov     rdi, rax
0x180019c4b  cmp     esi, 102h
0x180019c51  jnz     short loc_180019CC1
0x180019c53  cmp     cs:g_fTracingOn, 0
0x180019c5a  jz      short loc_180019C91
0x180019c5c  cmp     cs:g_fProviderEnabled, 0
0x180019c63  jz      short loc_180019C91
0x180019c65  mov     ecx, 10000000h
0x180019c6a  test    cs:g_ulTraceFlags, rcx
0x180019c71  jz      short loc_180019C91
0x180019c73  sub     rdi, r15
0x180019c76  mov     [rsp+0F8h+var_D8], rdi
0x180019c7b  mov     r9, rbx
0x180019c7e  lea     r8, aLdapwaitforres_4; "LdapWaitForResponseFromServerParallel:1"...
0x180019c85  lea     rdx, aSTimeoutExceed_1; "%s Timeout exceeded while acquiring con"...
0x180019c8c  call    LDAPClientPrint
0x180019c91  lea     rcx, [rsp+0F8h+var_B0]; this
0x180019c96  call    ?Unlock@CAutoCS@@QEAAXXZ; CAutoCS::Unlock(void)
0x180019c9b  lea     rcx, [rsp+0F8h+var_98]; this
0x180019ca0  call    ?Unlock@CAutoMutex@@QEAAXXZ; CAutoMutex::Unlock(void)
0x180019ca5  lea     rdx, loc_180019CB7
0x180019cac  mov     rcx, [rsp+0F8h+var_A0]
0x180019cb1  call    _local_unwind_0
0x180019cb6  nop
0x180019cb7  mov     eax, 55h ; 'U'
0x180019cbc  jmp     loc_180019A19
0x180019cc1  xor     r15d, r15d
0x180019cc4  test    esi, esi
0x180019cc6  setz    r15b
0x180019cca  xor     r14d, r14d
0x180019ccd  cmp     esi, 1
0x180019cd0  setz    r14b
0x180019cd4  mov     [rsp+0F8h+var_98], r14d
0x180019cd9  cmp     cs:g_fTracingOn, 0
0x180019ce0  jz      short loc_180019D49
0x180019ce2  cmp     cs:g_fProviderEnabled, 0
0x180019ce9  jz      short loc_180019D49
0x180019ceb  test    cs:g_ulTraceFlags, 20000000h
0x180019cf6  jz      short loc_180019D49
0x180019cf8  call    cs:__imp_GetTickCount64
0x180019cff  nop     dword ptr [rax+rax+00h]
0x180019d04  mov     rcx, [rsp+0F8h+var_68]
0x180019d0c  sub     rax, rcx
0x180019d0f  cmp     rax, 0FAh
0x180019d15  jbe     short loc_180019D49
0x180019d17  sub     rdi, rcx
0x180019d1a  mov     [rsp+0F8h+var_C0], r15d
0x180019d1f  mov     [rsp+0F8h+var_C8], r14d
0x180019d24  mov     qword ptr [rsp+0F8h+var_D0], rdi
0x180019d29  mov     [rsp+0F8h+var_D8], rbx
0x180019d2e  mov     r9, rax
0x180019d31  lea     r8, aLdapwaitforres; "LdapWaitForResponseFromServerParallel:1"...
0x180019d38  lea     rdx, aSTookLuMsFinis; "%s (took %lu ms) Finished waiting for c"...
0x180019d3f  mov     ecx, 20000000h
0x180019d44  call    LDAPClientPrint
0x180019d49  mov     edi, [rsp+0F8h+arg_8]
0x180019d50  test    esi, esi
0x180019d52  jnz     loc_180019E29
0x180019d58  lock inc cs:qword_180066268
0x180019d60  mov     ecx, cs:g_fTracingOn
0x180019d66  test    ecx, ecx
0x180019d68  jz      short loc_180019DA2
0x180019d6a  cmp     cs:g_fProviderEnabled, esi
0x180019d70  jz      short loc_180019DA2
0x180019d72  mov     eax, 400h
0x180019d77  test    cs:g_ulTraceFlags, rax
0x180019d7e  jz      short loc_180019DA2
0x180019d80  mov     dword ptr [rsp+0F8h+var_D8], edi
0x180019d84  mov     r9, rbx
0x180019d87  lea     r8, aLdapwaitforres_29; "LdapWaitForResponseFromServerParallel:1"...
0x180019d8e  lea     rdx, aSEventWasSigna; "%s Event was signaled conn:0x%p waitCou"...
0x180019d95  mov     ecx, eax
0x180019d97  call    LDAPClientPrint
0x180019d9c  mov     ecx, cs:g_fTracingOn
0x180019da2  mov     al, [r13+0BCh]
0x180019da9  test    al, al
0x180019dab  jnz     short loc_180019DB6
0x180019dad  cmp     [r13+0B8h], al
0x180019db4  jz      short loc_180019E29
0x180019db6  neg     al
0x180019db8  sbb     ebx, ebx
0x180019dba  neg     ebx
0x180019dbc  add     ebx, 58h ; 'X'
0x180019dbf  test    ecx, ecx
0x180019dc1  jz      short loc_180019DF0
0x180019dc3  cmp     cs:g_fProviderEnabled, 0
0x180019dca  jz      short loc_180019DF0
0x180019dcc  mov     ecx, 10000000h
0x180019dd1  test    cs:g_ulTraceFlags, rcx
0x180019dd8  jz      short loc_180019DF0
0x180019dda  mov     r9d, ebx
0x180019ddd  lea     r8, aLdapwaitforres_18; "LdapWaitForResponseFromServerParallel:1"...
0x180019de4  lea     rdx, aSRequestIsNoLo; "%s request is no longer in a valid stat"...
0x180019deb  call    LDAPClientPrint
0x180019df0  lea     rcx, [rsp+0F8h+var_B0]; this
0x180019df5  call    ?Unlock@CAutoCS@@QEAAXXZ; CAutoCS::Unlock(void)
0x180019dfa  lea     rcx, [rsp+0F8h+var_98]; this
0x180019dff  call    ?Unlock@CAutoMutex@@QEAAXXZ; CAutoMutex::Unlock(void)
0x180019e04  mov     [rsp+0F8h+arg_10], ebx
0x180019e0b  lea     rdx, loc_180019E1D
0x180019e12  mov     rcx, [rsp+0F8h+var_A0]
0x180019e17  call    _local_unwind_0
0x180019e1c  nop
0x180019e1d  mov     eax, [rsp+0F8h+arg_10]
0x180019e24  jmp     loc_180019A19
0x180019e29  test    r14d, r14d
0x180019e2c  jz      short loc_180019E74
  ... truncated ...
```
