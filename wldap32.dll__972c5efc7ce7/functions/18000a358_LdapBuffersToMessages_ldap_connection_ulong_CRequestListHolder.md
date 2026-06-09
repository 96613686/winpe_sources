# LdapBuffersToMessages(ldap_connection *,ulong,CRequestListHolder *)

- ea: `0x18000a358`
- end: `0x18000adaa`
- name: `?LdapBuffersToMessages@@YAKPEAUldap_connection@@KPEAVCRequestListHolder@@@Z`
- size: `2642`
- prototype: `unsigned int __fastcall(struct ldap_connection *, unsigned int, struct CRequestListHolder *)`
- caller_count: `4`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180006d80`
- `0x180009040`
- `0x180019f88`
- `0x180045b90`

## callees

- `0x1800037a8`
- `0x180003840`
- `0x180006510`
- `0x180006bc0`
- `0x180008710`
- `0x18000a280`
- `0x18000a358`
- `0x18000b440`
- `0x180014460`
- `0x1800190b0`
- `0x18001ad5c`
- `0x18001ce90`
- `0x18002884c`
- `0x1800299c0`
- `0x18002a9f8`
- `0x18002dad0`
- `0x180032bd8`
- `0x18004c308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a397`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a85d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a8b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a397`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a85d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a8b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a421`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a919`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a421`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a919`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a4da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a4da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000aa58`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000aa58`

## string_xrefs

- `0x18000a4e9`: `ldapBuffersToMsgs thread 0x%x has connection 0x%x as down.\n`
- `0x18000a9bf`: `LdapBuffersToMessages handling completion for 0x%x.\n`

## pseudocode

```c
__int64 __fastcall LdapBuffersToMessages(struct _RTL_CRITICAL_SECTION *a1, int a2, struct CRequestListHolder *a3)
{
  HANDLE *p_LockSemaphore; // r14
  char *LockSemaphore; // r12
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // edi
  bool v10; // zf
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rcx
  unsigned int v13; // r13d
  ULONG_PTR *p_SpinCount; // r15
  DWORD CurrentThreadId; // eax
  _DWORD *v16; // r12
  unsigned int v17; // edi
  unsigned int v18; // edi
  struct ldapmsg *OwningThread; // rsi
  __int64 v20; // rax
  CLdapBer *lm_ber; // r14
  int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // edx
  unsigned int v25; // edi
  unsigned int v26; // eax
  struct ldap_connection *v27; // r8
  unsigned int v28; // edx
  struct ldap_request *LdapRequest; // rax
  struct ldap_request *v30; // rdi
  int v31; // eax
  struct _RTL_CRITICAL_SECTION *v32; // r15
  unsigned int v33; // edx
  __int64 v34; // rbp
  DWORD TickCount; // eax
  int v36; // eax
  ULONG lm_msgid; // esi
  struct _RTL_CRITICAL_SECTION **v38; // [rsp+30h] [rbp-68h]
  ULONG_PTR *v39; // [rsp+38h] [rbp-60h]
  HANDLE *v40; // [rsp+40h] [rbp-58h]
  char *v41; // [rsp+48h] [rbp-50h]
  int v42; // [rsp+A0h] [rbp+8h] BYREF
  int v43; // [rsp+A8h] [rbp+10h]
  struct CRequestListHolder *v44; // [rsp+B0h] [rbp+18h]
  unsigned int v45; // [rsp+B8h] [rbp+20h] BYREF

  v44 = a3;
  v43 = a2;
  p_LockSemaphore = &a1->LockSemaphore;
  v42 = 0;
  LockSemaphore = (char *)a1->LockSemaphore;
  v5 = a1 + 20;
  v6 = a1;
  v41 = LockSemaphore;
  v40 = &a1->LockSemaphore;
  EnterCriticalSection(a1 + 20);
  v7 = DrainPendingCryptoStream((struct ldap_connection *)v6, &v42);
  v8 = 0;
  v9 = v7;
  if ( v7 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
      LDAPClientPrint(
        0x100000,
        "LdapBuffersToMessages : drain crypto returned 0x%x on connection 0x%x\n",
        v7,
        (_DWORD)v6);
    v10 = v42 == 590615;
    *(_WORD *)((char *)&v6[13].SpinCount + 1) = 272;
    if ( !v10 )
      BYTE3(v6[13].SpinCount) = 0;
    goto LABEL_9;
  }
  v9 = 0;
  DebugInfo = (struct _RTL_CRITICAL_SECTION *)v6[1].DebugInfo;
  v38 = (struct _RTL_CRITICAL_SECTION **)DebugInfo;
  if ( DebugInfo == &v6[1] )
  {
LABEL_9:
    LeaveCriticalSection(v5);
    return v9;
  }
  v42 = 0;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
  {
    LDAPClientPrint(0x200000, "LdapBuffersToMessages : searching for messages on connection 0x%x\n", (_DWORD)v6);
    DebugInfo = (struct _RTL_CRITICAL_SECTION *)v38;
    v8 = 0;
  }
  v13 = 0;
  do
  {
    if ( v13 )
      break;
    p_SpinCount = &DebugInfo[-1].SpinCount;
    v39 = &DebugInfo[-1].SpinCount;
    if ( !LODWORD(DebugInfo->OwningThread) )
    {
      if ( g_fTracingOn )
      {
        if ( g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
        {
          LDAPClientPrint(0x200000, "BufferToMessages : connection 0x%x is marked down.\n", (_DWORD)v6);
          v8 = 0;
        }
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
        {
          CurrentThreadId = GetCurrentThreadId();
          LDAPClientPrint(
            128,
            "ldapBuffersToMsgs thread 0x%x has connection 0x%x as down.\n",
            CurrentThreadId,
            (_DWORD)v6);
        }
      }
      LOBYTE(v8) = 1;
      *(_WORD *)((char *)&v6[13].SpinCount + 1) = 272;
      v13 = 81;
      LdapFreeReceiveStructure(p_SpinCount, v8);
      DebugInfo = (struct _RTL_CRITICAL_SECTION *)v38;
      goto LABEL_162;
    }
    if ( g_fTracingOn )
    {
      if ( g_fProviderEnabled && (g_ulTraceFlags & 0x10000) != 0 && LockSemaphore != (char *)p_LockSemaphore )
      {
        LDAPClientPrint(0x10000, "Unencrypted dump of Data received on connection 0x%x\n", (_DWORD)v6);
        DumpBuffer(0x10000, (char *)p_SpinCount + 36, *((unsigned int *)p_SpinCount + 6));
        LDAPClientTraceEvent(0x10000, "End of Unencrypted dump of receive buffer.\n");
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
        LDAPClientPrint(0x200000, "  checking out buffer 0x%x for Connection 0x%x\n", (_DWORD)p_SpinCount, (_DWORD)v6);
    }
    v16 = (_DWORD *)p_SpinCount + 7;
    while ( !v13 )
    {
      v17 = *((_DWORD *)p_SpinCount + 6);
      v16 = (_DWORD *)p_SpinCount + 7;
      if ( v17 <= *((_DWORD *)p_SpinCount + 7) )
        goto LABEL_157;
      v18 = v17 - *v16;
      OwningThread = (struct ldapmsg *)v6[1].OwningThread;
      v45 = 0;
      if ( OwningThread )
      {
        lm_ber = (CLdapBer *)OwningThread->lm_ber;
        v25 = CLdapBer::HrLoadMoreBer(lm_ber, (const unsigned __int8 *)p_SpinCount + (unsigned int)*v16 + 36, v18, &v45);
        if ( v25 )
        {
          v13 = v25;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(0x400000, "BufferToMessages: loadBer2 error of 0x%x for 0x%x.\n", v25, (_DWORD)v6);
          if ( v25 != 90 )
          {
            ldapFree(OwningThread, 1735609676);
            if ( lm_ber )
              CLdapBer::`scalar deleting destructor'(lm_ber, v8);
            v6[1].OwningThread = 0;
          }
          goto LABEL_157;
        }
      }
      else
      {
        OwningThread = (struct ldapmsg *)ldapMalloc(72, 1735609676);
        if ( !OwningThread )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
            LDAPClientPrint(0x4000, "BufferToMessages: unable to allocate message for 0x%x.\n", (_DWORD)v6);
          goto LABEL_144;
        }
        v20 = ldapMalloc(872, 1816347212);
        lm_ber = (CLdapBer *)v20;
        if ( !v20 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
            LDAPClientPrint(0x4000, "BufferToMessages: unable to allocate message for 0x%x.\n", (_DWORD)v6);
          ldapFree(OwningThread, 1735609676);
LABEL_144:
          v13 = 90;
LABEL_157:
          v9 = v42;
          break;
        }
        v22 = (int)v6[25].DebugInfo;
        *(_QWORD *)v20 = 0;
        *(_DWORD *)(v20 + 8) = 0;
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 836) = 0;
        *(_QWORD *)(v20 + 24) = 0;
        *(_BYTE *)(v20 + 856) = 0;
        *(_DWORD *)(v20 + 864) = 0;
        *(_DWORD *)(v20 + 860) = v22 != 2 ? 0xFDE9 : 0;
        *(_DWORD *)(v20 + 32) = 0;
        OwningThread->Connection = *(PLDAP *)&v6[11].LockCount;
        OwningThread->lm_ber = (PVOID)v20;
        v23 = CLdapBer::HrLoadBer(
                (CLdapBer *)v20,
                (const unsigned __int8 *)p_SpinCount + (unsigned int)*v16 + 36,
                v18,
                &v45,
                0,
                0);
        if ( v23 )
        {
          v13 = v23;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(0x400000, "BufferToMessages: loadBer1 error of 0x%x for 0x%x.\n", v23, (_DWORD)v6);
          ldapFree(OwningThread, 1735609676);
          CLdapBer::`scalar deleting destructor'(lm_ber, v24);
          goto LABEL_157;
        }
      }
      if ( *(_DWORD *)lm_ber > *((_DWORD *)lm_ber + 6) || !*(_DWORD *)lm_ber )
      {
        v6[1].OwningThread = OwningThread;
        goto LABEL_137;
      }
      v6[1].OwningThread = 0;
      v26 = LdapInitialDecodeMessage((struct ldap_connection *)v6, OwningThread);
      v13 = v26;
      if ( v26 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
          LDAPClientPrint(0x100000, "LdapBuffersToMessages Connection 0x%x, decoding error of 0x%x\n", (_DWORD)v6, v26);
        goto LABEL_55;
      }
      LdapRequest = FindLdapRequestEx(OwningThread->lm_msgid, v44, v27);
      v30 = LdapRequest;
      if ( !LdapRequest )
      {
        v31 = g_fTracingOn;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
        {
          LDAPClientPrint(
            0x100000,
            "LdapBuffersToMessages Connection 0x%x, request for msgid 0x%x not found.\n",
            (_DWORD)v6,
            OwningThread->lm_msgid);
          v31 = g_fTracingOn;
        }
        if ( !OwningThread->lm_msgid )
        {
          *(_WORD *)((char *)&v6[13].SpinCount + 1) = 272;
          if ( !v31 )
          {
LABEL_55:
            ldapFree(OwningThread, 1735609676);
            CLdapBer::`scalar deleting destructor'(lm_ber, v28);
LABEL_137:
            v9 = v42;
            goto LABEL_138;
          }
          if ( g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
          {
            LDAPClientPrint(
              0x100000,
              "LdapBuffersToMessages Connection 0x%x, msgid 0x%x found.\n",
              (_DWORD)v6,
              OwningThread->lm_msgid);
            v31 = g_fTracingOn;
          }
        }
        if ( v31 && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
          LDAPClientPrint(
            0x100000,
            "LdapBuffersToMessages discarding result msgid 0X%X at 0x%X for lack of request\n",
            OwningThread->lm_msgid,
            (_DWORD)OwningThread);
        goto LABEL_55;
      }
      v32 = (struct _RTL_CRITICAL_SECTION *)((char *)LdapRequest + 48);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)LdapRequest + 48));
      if ( *((_BYTE *)v30 + 184) )
      {
        LeaveCriticalSection(v32);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
          LDAPClientPrint(
            0x100000,
            "LdapBuffersToMessages Connection 0x%x, request 0x%x abandoned.\n",
            (_DWORD)v6,
            OwningThread->lm_msgid);
        EnterCriticalSection(v32);
        --*((_DWORD *)v30 + 4);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", (_DWORD)v30, *((_DWORD *)v30 + 4));
        if ( *((_DWORD *)v30 + 4) )
        {
          LeaveCriticalSection(v32);
        }
        else
        {
          LeaveCriticalSection(v32);
          DereferenceLdapRequest2(v30, 0);
        }
        ldapFree(OwningThread, 1735609676);
        CLdapBer::`scalar deleting destructor'(lm_ber, v33);
        p_SpinCount = v39;
        goto LABEL_137;
      }
      v34 = *((_QWORD *)v30 + 3);
      if ( *((_BYTE *)v30 + 189) )
      {
        OwningThread->ConnectionReferenced = 1;
        v6 = (struct _RTL_CRITICAL_SECTION *)ReferenceLdapConnection(v6);
      }
      if ( OwningThread->lm_msgtype == 100 )
      {
        v10 = g_fTracingOn == 0;
        *((_BYTE *)v30 + 272) = 1;
        if ( !v10 && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
          LDAPClientPrint(0x1000000, "LdapBuffersToMessages handling searchEntry for 0x%x.\n", v30);
      }
      else if ( OwningThread->lm_msgtype == 115 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
          LDAPClientPrint(0x1000000, "LdapBuffersToMessages handling referral for 0x%x.\n", v30);
      }
      else
      {
        DecrementPendingList(v30, v6);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
        {
          LDAPClientPrint(
            0x1000000,
            "LdapBuffersToMessages received message type 0x%x for msgid 0x%X\n",
            OwningThread->lm_msgtype,
            OwningThread->lm_msgid);
          LDAPClientPrint(0x1000000, "LdapBuffersToMessages handling completion for 0x%x.\n", v30);
        }
      }
      if ( v34 )
      {
        while ( *(_QWORD *)(v34 + 16) )
          v34 = *(_QWORD *)(v34 + 16);
      }
      OwningThread->lm_chain = 0;
      OwningThread->lm_next = 0;
      if ( v34 )
        *(_QWORD *)(v34 + 16) = OwningThread;
      else
        *((_QWORD *)v30 + 3) = OwningThread;
      TickCount = GetTickCount();
      v10 = OwningThread->lm_msgtype == 100;
      OwningThread->lm_time = TickCount;
      v36 = v43;
      OwningThread->Request = v30;
      if ( !v10 || v36 != 1 )
      {
        if ( OwningThread->lm_msgtype == 115 )
        {
          if ( *((_BYTE *)v30 + 185) )
            goto LABEL_123;
        }
        else
        {
          if ( OwningThread->lm_msgtype == 100 && v36 != 1 )
            goto LABEL_123;
          if ( !*((_WORD *)v30 + 91) )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000) != 0 )
              LDAPClientPrint(
                4096,
                "LdapBuffersToMessages marking eom for request 0x%x, message 0x%x, msgid 0x%x\n",
                (_DWORD)v30,
                (_DWORD)OwningThread,
                OwningThread->lm_msgid);
            OwningThread->lm_eom = 1;
LABEL_123:
            lm_msgid = OwningThread->lm_msgid;
            LeaveCriticalSection(v32);
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
              LDAPClientPrint(
                1024,
                "%s CheckForWaiters: msgId = 0x%x, Connection = 0x%x\n",
                "LdapBuffersToMessages:3539",
                lm_msgid,
                (_DWORD)v6);
            CheckForWaiters(lm_msgid, 0, v6);
            goto LABEL_128;
          }
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
            LDAPClientPrint(
              0x200000,
              "LdapBuffersToMessages request 0x%x has 0x%x outstanding\n",
              (_DWORD)v30,
              *((unsigned __int16 *)v30 + 91));
        }
      }
      LeaveCriticalSection(v32);
LABEL_128:
      EnterCriticalSection(v32);
      --*((_DWORD *)v30 + 4);
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
        LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", (_DWORD)v30, *((_DWORD *)v30 + 4));
      if ( *((_DWORD *)v30 + 4) )
      {
        LeaveCriticalSection(v32);
      }
      else
      {
        LeaveCriticalSection(v32);
        DereferenceLdapRequest2(v30, 0);
      }
      p_SpinCount = v39;
      v9 = ++v42;
LABEL_138:
      *v16 += v45;
    }
    DebugInfo = *v38;
    v38 = (struct _RTL_CRITICAL_SECTION **)*v38;
    if ( *((_DWORD *)p_SpinCount + 6) == *v16 || v13 != 90 )
    {
      LOBYTE(v8) = 1;
      LdapFreeReceiveStructure(p_SpinCount, v8);
      DebugInfo = (struct _RTL_CRITICAL_SECTION *)v38;
    }
    LockSemaphore = v41;
    p_LockSemaphore = v40;
LABEL_162:
    v8 = 0;
  }
  while ( DebugInfo != &v6[1] );
  v6[15].SpinCount += v9;
  _InterlockedAdd64(&qword_1800661F0, v9);
  if ( v9 )
    SetConnectionError(v6, v13);
  LeaveCriticalSection(v6 + 20);
  return v13;
}

```

## disassembly

```asm
0x18000a358  mov     rax, rsp
0x18000a35b  mov     [rax+18h], r8
0x18000a35f  mov     [rax+10h], edx
0x18000a362  push    rbx
0x18000a363  push    rbp
0x18000a364  push    rsi
0x18000a365  push    rdi
0x18000a366  push    r12
0x18000a368  push    r13
0x18000a36a  push    r14
0x18000a36c  push    r15
0x18000a36e  sub     rsp, 58h
0x18000a372  lea     r14, [rcx+18h]
0x18000a376  mov     dword ptr [rax+8], 0
0x18000a37d  mov     r12, [r14]
0x18000a380  lea     rsi, [rcx+320h]
0x18000a387  mov     rbx, rcx
0x18000a38a  mov     [rsp+98h+var_50], r12
0x18000a38f  mov     rcx, rsi; lpCriticalSection
0x18000a392  mov     [rsp+98h+var_58], r14
0x18000a397  call    cs:__imp_EnterCriticalSection
0x18000a39e  nop     dword ptr [rax+rax+00h]
0x18000a3a3  lea     rdx, [rsp+98h+arg_0]; int *
0x18000a3ab  mov     rcx, rbx; struct ldap_connection *
0x18000a3ae  call    ?DrainPendingCryptoStream@@YAKPEAUldap_connection@@PEAJ@Z; DrainPendingCryptoStream(ldap_connection *,long *)
0x18000a3b3  xor     edx, edx
0x18000a3b5  mov     edi, eax
0x18000a3b7  test    eax, eax
0x18000a3b9  jz      short loc_18000A40B
0x18000a3bb  cmp     cs:g_fTracingOn, edx
0x18000a3c1  jz      short loc_18000A3ED
0x18000a3c3  cmp     cs:g_fProviderEnabled, edx
0x18000a3c9  jz      short loc_18000A3ED
0x18000a3cb  mov     ecx, 100000h
0x18000a3d0  test    cs:g_ulTraceFlags, rcx
0x18000a3d7  jz      short loc_18000A3ED
0x18000a3d9  mov     r9, rbx
0x18000a3dc  lea     rdx, aLdapbufferstom_0; "LdapBuffersToMessages : drain crypto re"...
0x18000a3e3  mov     r8d, eax
0x18000a3e6  call    LDAPClientPrint
0x18000a3eb  xor     edx, edx
0x18000a3ed  cmp     [rsp+98h+arg_0], 90317h
0x18000a3f8  mov     word ptr [rbx+229h], 110h
0x18000a401  jz      short loc_18000A41E
0x18000a403  mov     [rbx+22Bh], dl
0x18000a409  jmp     short loc_18000A41E
0x18000a40b  lea     rax, [rbx+28h]
0x18000a40f  mov     edi, edx
0x18000a411  mov     rcx, [rax]
0x18000a414  mov     [rsp+98h+var_68], rcx
0x18000a419  cmp     rcx, rax
0x18000a41c  jnz     short loc_18000A434
0x18000a41e  mov     rcx, rsi; lpCriticalSection
0x18000a421  call    cs:__imp_LeaveCriticalSection
0x18000a428  nop     dword ptr [rax+rax+00h]
0x18000a42d  mov     eax, edi
0x18000a42f  jmp     loc_18000AD98
0x18000a434  cmp     cs:g_fTracingOn, edx
0x18000a43a  mov     esi, 200000h
0x18000a43f  mov     [rsp+98h+arg_0], edx
0x18000a446  jz      short loc_18000A471
0x18000a448  cmp     cs:g_fProviderEnabled, edx
0x18000a44e  jz      short loc_18000A471
0x18000a450  test    cs:g_ulTraceFlags, rsi
0x18000a457  jz      short loc_18000A471
0x18000a459  mov     r8, rbx
0x18000a45c  lea     rdx, aLdapbufferstom_6; "LdapBuffersToMessages : searching for m"...
0x18000a463  mov     ecx, esi
0x18000a465  call    LDAPClientPrint
0x18000a46a  mov     rcx, [rsp+98h+var_68]
0x18000a46f  xor     edx, edx
0x18000a471  mov     r13d, edx
0x18000a474  mov     ebp, 100000h
0x18000a479  test    r13d, r13d
0x18000a47c  jnz     loc_18000AD62
0x18000a482  lea     r15, [rcx-8]
0x18000a486  mov     [rsp+98h+var_60], r15
0x18000a48b  cmp     [r15+18h], edx
0x18000a48f  jnz     loc_18000A520
0x18000a495  cmp     cs:g_fTracingOn, edx
0x18000a49b  jz      short loc_18000A4FD
0x18000a49d  cmp     cs:g_fProviderEnabled, edx
0x18000a4a3  jz      short loc_18000A4C1
0x18000a4a5  test    cs:g_ulTraceFlags, rsi
0x18000a4ac  jz      short loc_18000A4C1
0x18000a4ae  mov     r8, rbx
0x18000a4b1  lea     rdx, aBuffertomessag; "BufferToMessages : connection 0x%x is m"...
0x18000a4b8  mov     ecx, esi
0x18000a4ba  call    LDAPClientPrint
0x18000a4bf  xor     edx, edx
0x18000a4c1  cmp     cs:g_fTracingOn, edx
0x18000a4c7  jz      short loc_18000A4FD
0x18000a4c9  cmp     cs:g_fProviderEnabled, edx
0x18000a4cf  jz      short loc_18000A4FD
0x18000a4d1  test    byte ptr cs:g_ulTraceFlags, 80h
0x18000a4d8  jz      short loc_18000A4FD
0x18000a4da  call    cs:__imp_GetCurrentThreadId
0x18000a4e1  nop     dword ptr [rax+rax+00h]
0x18000a4e6  mov     r9, rbx
0x18000a4e9  lea     rdx, aLdapbufferstom_7; "ldapBuffersToMsgs thread 0x%x has conne"...
0x18000a4f0  mov     r8d, eax
0x18000a4f3  mov     ecx, 80h
0x18000a4f8  call    LDAPClientPrint
0x18000a4fd  mov     dl, 1
0x18000a4ff  mov     word ptr [rbx+229h], 110h
0x18000a508  mov     rcx, r15
0x18000a50b  mov     r13d, 51h ; 'Q'
0x18000a511  call    LdapFreeReceiveStructure
0x18000a516  mov     rcx, [rsp+98h+var_68]
0x18000a51b  jmp     loc_18000AD50
0x18000a520  cmp     cs:g_fTracingOn, edx
0x18000a526  jz      loc_18000A5B1
0x18000a52c  cmp     cs:g_fProviderEnabled, edx
0x18000a532  jz      short loc_18000A57D
0x18000a534  test    cs:g_ulTraceFlags, 10000h
0x18000a53f  jz      short loc_18000A57D
0x18000a541  cmp     r12, r14
0x18000a544  jz      short loc_18000A57D
0x18000a546  mov     r8, rbx
0x18000a549  lea     rdx, aUnencryptedDum; "Unencrypted dump of Data received on co"...
0x18000a550  mov     ecx, 10000h
0x18000a555  call    LDAPClientPrint
0x18000a55a  mov     r8d, [r15+18h]
0x18000a55e  lea     rdx, [r15+24h]
0x18000a562  mov     ecx, 10000h
0x18000a567  call    DumpBuffer
0x18000a56c  lea     rdx, aEndOfUnencrypt_0; "End of Unencrypted dump of receive buff"...
0x18000a573  mov     ecx, 10000h
0x18000a578  call    LDAPClientTraceEvent
0x18000a57d  xor     r14d, r14d
0x18000a580  cmp     cs:g_fTracingOn, r14d
0x18000a587  jz      short loc_18000A5B4
0x18000a589  cmp     cs:g_fProviderEnabled, r14d
0x18000a590  jz      short loc_18000A5B4
0x18000a592  test    cs:g_ulTraceFlags, rsi
0x18000a599  jz      short loc_18000A5B4
0x18000a59b  mov     r9, rbx
0x18000a59e  lea     rdx, aCheckingOutBuf; "  checking out buffer 0x%x for Connecti"...
0x18000a5a5  mov     r8, r15
0x18000a5a8  mov     ecx, esi
0x18000a5aa  call    LDAPClientPrint
0x18000a5af  jmp     short loc_18000A5B4
0x18000a5b1  xor     r14d, r14d
0x18000a5b4  lea     r12, [r15+1Ch]
0x18000a5b8  test    r13d, r13d
0x18000a5bb  jnz     loc_18000AD15
0x18000a5c1  mov     edi, [r15+18h]
0x18000a5c5  lea     r12, [r15+1Ch]
0x18000a5c9  cmp     edi, [r12]
0x18000a5cd  jbe     loc_18000AD0E
0x18000a5d3  sub     edi, [r12]
0x18000a5d7  mov     rsi, [rbx+38h]
0x18000a5db  mov     [rsp+98h+arg_18], r14d
0x18000a5e3  test    rsi, rsi
0x18000a5e6  jnz     loc_18000A6EE
0x18000a5ec  mov     edx, 67734D4Ch
0x18000a5f1  lea     ecx, [rsi+48h]
0x18000a5f4  call    ldapMalloc
0x18000a5f9  mov     rsi, rax
0x18000a5fc  test    rax, rax
0x18000a5ff  jz      loc_18000AC81
0x18000a605  mov     edx, 6C43424Ch
0x18000a60a  mov     ecx, 368h
0x18000a60f  call    ldapMalloc
0x18000a614  xor     r8d, r8d
0x18000a617  mov     r14, rax
0x18000a61a  test    rax, rax
0x18000a61d  jz      loc_18000AC35
0x18000a623  mov     ecx, [rbx+3E8h]
0x18000a629  lea     r9, [rsp+98h+arg_18]; unsigned int *
0x18000a631  mov     [rax], r8
0x18000a634  sub     ecx, 2
0x18000a637  mov     [rax+8], r8d
0x18000a63b  neg     ecx
0x18000a63d  mov     [rax+10h], r8
0x18000a641  mov     rcx, r14; this
0x18000a644  mov     [rax+344h], r8
0x18000a64b  mov     [rax+18h], r8
0x18000a64f  mov     [rax+358h], r8b
0x18000a656  mov     [rax+360h], r8d
0x18000a65d  sbb     eax, eax
0x18000a65f  and     eax, 0FDE9h
0x18000a664  mov     [rsp+98h+var_70], r8b; unsigned __int8
0x18000a669  mov     [r14+35Ch], eax
0x18000a670  mov     [r14+20h], r8d
0x18000a674  mov     rax, [rbx+1C0h]
0x18000a67b  mov     [rsi+28h], rax
0x18000a67f  mov     [rsi+8], r14
0x18000a683  mov     edx, [r12]
0x18000a687  add     rdx, 24h ; '$'
0x18000a68b  mov     [rsp+98h+var_78], r8b; unsigned __int8
0x18000a690  add     rdx, r15; Src
0x18000a693  mov     r8d, edi; unsigned int
0x18000a696  call    ?HrLoadBer@CLdapBer@@QEAAKPEBEKPEAKEE@Z; CLdapBer::HrLoadBer(uchar const *,ulong,ulong *,uchar,uchar)
0x18000a69b  xor     edi, edi
0x18000a69d  test    eax, eax
0x18000a69f  jz      short loc_18000A71E
0x18000a6a1  cmp     cs:g_fTracingOn, edi
0x18000a6a7  mov     r13d, eax
0x18000a6aa  jz      short loc_18000A6D4
0x18000a6ac  cmp     cs:g_fProviderEnabled, edi
0x18000a6b2  jz      short loc_18000A6D4
0x18000a6b4  mov     ecx, 400000h
0x18000a6b9  test    cs:g_ulTraceFlags, rcx
0x18000a6c0  jz      short loc_18000A6D4
0x18000a6c2  mov     r9, rbx
0x18000a6c5  lea     rdx, aBuffertomessag_1; "BufferToMessages: loadBer1 error of 0x%"...
0x18000a6cc  mov     r8d, eax
0x18000a6cf  call    LDAPClientPrint
0x18000a6d4  mov     edx, 67734D4Ch
0x18000a6d9  mov     rcx, rsi
0x18000a6dc  call    ldapFree
0x18000a6e1  mov     rcx, r14; this
0x18000a6e4  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18000a6e9  jmp     loc_18000AD0E
0x18000a6ee  mov     edx, [r12]
0x18000a6f2  lea     r9, [rsp+98h+arg_18]; unsigned int *
0x18000a6fa  mov     r14, [rsi+8]
0x18000a6fe  add     rdx, 24h ; '$'
0x18000a702  add     rdx, r15; Src
0x18000a705  mov     r8d, edi; Size
0x18000a708  mov     rcx, r14; this
0x18000a70b  call    ?HrLoadMoreBer@CLdapBer@@QEAAKPEBEKPEAK@Z; CLdapBer::HrLoadMoreBer(uchar const *,ulong,ulong *)
0x18000a710  mov     edi, eax
0x18000a712  xor     eax, eax
0x18000a714  test    edi, edi
0x18000a716  jnz     loc_18000ACB4
0x18000a71c  xor     edi, edi
0x18000a71e  mov     eax, [r14]
0x18000a721  cmp     eax, [r14+18h]
0x18000a725  ja      loc_18000AC17
0x18000a72b  test    eax, eax
0x18000a72d  jz      loc_18000AC17
0x18000a733  mov     rdx, rsi; struct ldapmsg *
0x18000a736  mov     [rbx+38h], rdi
0x18000a73a  mov     rcx, rbx; struct ldap_connection *
0x18000a73d  call    ?LdapInitialDecodeMessage@@YAKPEAUldap_connection@@PEAUldapmsg@@@Z; LdapInitialDecodeMessage(ldap_connection *,ldapmsg *)
0x18000a742  mov     r13d, eax
0x18000a745  test    eax, eax
0x18000a747  jz      short loc_18000A790
0x18000a749  cmp     cs:g_fTracingOn, edi
0x18000a74f  jz      short loc_18000A776
0x18000a751  cmp     cs:g_fProviderEnabled, edi
0x18000a757  jz      short loc_18000A776
0x18000a759  test    cs:g_ulTraceFlags, rbp
0x18000a760  jz      short loc_18000A776
0x18000a762  mov     r9d, eax
0x18000a765  lea     rdx, aLdapbufferstom_14; "LdapBuffersToMessages Connection 0x%x, "...
0x18000a76c  mov     r8, rbx
0x18000a76f  mov     ecx, ebp
0x18000a771  call    LDAPClientPrint
0x18000a776  mov     edx, 67734D4Ch
0x18000a77b  mov     rcx, rsi
0x18000a77e  call    ldapFree
0x18000a783  mov     rcx, r14; this
0x18000a786  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18000a78b  jmp     loc_18000AC1B
0x18000a790  mov     rdx, [rsp+98h+arg_10]; struct CRequestListHolder *
0x18000a798  mov     ecx, [rsi]; int
0x18000a79a  call    ?FindLdapRequestEx@@YAPEAUldap_request@@JPEAVCRequestListHolder@@PEAUldap_connection@@@Z; FindLdapRequestEx(long,CRequestListHolder *,ldap_connection *)
0x18000a79f  mov     rdi, rax
0x18000a7a2  test    rax, rax
0x18000a7a5  jnz     loc_18000A856
0x18000a7ab  mov     eax, cs:g_fTracingOn
0x18000a7b1  test    eax, eax
0x18000a7b3  jz      short loc_18000A7E0
0x18000a7b5  cmp     cs:g_fProviderEnabled, edi
0x18000a7bb  jz      short loc_18000A7E0
0x18000a7bd  test    cs:g_ulTraceFlags, rbp
0x18000a7c4  jz      short loc_18000A7E0
0x18000a7c6  mov     r9d, [rsi]
0x18000a7c9  lea     rdx, aLdapbufferstom_10; "LdapBuffersToMessages Connection 0x%x, "...
0x18000a7d0  mov     r8, rbx
0x18000a7d3  mov     ecx, ebp
0x18000a7d5  call    LDAPClientPrint
0x18000a7da  mov     eax, cs:g_fTracingOn
0x18000a7e0  cmp     [rsi], edi
0x18000a7e2  jnz     short loc_18000A81C
0x18000a7e4  mov     word ptr [rbx+229h], 110h
0x18000a7ed  test    eax, eax
0x18000a7ef  jz      short loc_18000A776
0x18000a7f1  cmp     cs:g_fProviderEnabled, edi
0x18000a7f7  jz      short loc_18000A81C
0x18000a7f9  test    cs:g_ulTraceFlags, rbp
0x18000a800  jz      short loc_18000A81C
0x18000a802  mov     r9d, [rsi]
0x18000a805  lea     rdx, aLdapbufferstom; "LdapBuffersToMessages Connection 0x%x, "...
0x18000a80c  mov     r8, rbx
0x18000a80f  mov     ecx, ebp
0x18000a811  call    LDAPClientPrint
0x18000a816  mov     eax, cs:g_fTracingOn
0x18000a81c  test    eax, eax
0x18000a81e  jz      loc_18000A776
0x18000a824  cmp     cs:g_fProviderEnabled, edi
0x18000a82a  jz      loc_18000A776
0x18000a830  test    cs:g_ulTraceFlags, rbp
0x18000a837  jz      loc_18000A776
0x18000a83d  mov     r8d, [rsi]
0x18000a840  lea     rdx, aLdapbufferstom_4; "LdapBuffersToMessages discarding result"...
0x18000a847  mov     r9, rsi
  ... truncated ...
```
