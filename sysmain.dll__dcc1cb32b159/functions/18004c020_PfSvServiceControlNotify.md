# PfSvServiceControlNotify

- ea: `0x18004c020`
- end: `0x18004c61a`
- name: `PfSvServiceControlNotify`
- size: `1530`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004bf80`

## callees

- `0x18003c814`
- `0x18003cbe4`
- `0x18003cffc`
- `0x18004c020`
- `0x180052364`
- `0x18005e868`
- `0x180067e34`
- `0x180069fa4`
- `0x180070b6c`
- `0x180083494`
- `0x1800900a4`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c2fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c384`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c2fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c384`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004c31c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004c31c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004c32c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004c32c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c5ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c5ea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18004c516`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18004c516`

## pseudocode

```c
__int64 __fastcall PfSvServiceControlNotify(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // r9
  PSID *v4; // r12
  int v7; // r13d
  unsigned int v8; // r14d
  int v9; // r10d
  BOOL v10; // r11d
  int v11; // eax
  int UnbiasedTickCount; // eax
  __int64 v13; // r9
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  unsigned __int32 v16; // eax
  signed __int32 v17; // ett
  LPCRITICAL_SECTION v18; // r10
  __int64 v19; // rdx
  unsigned int SessionUserInfo; // eax
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  int v22; // r15d
  __int64 v23; // rbx
  int v24; // eax
  DWORD LengthSid; // eax
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  __int64 v27; // rax
  struct _RTL_CRITICAL_SECTION *v28; // r10
  unsigned int v29; // edx
  __int64 v30; // rbx
  struct _RTL_CRITICAL_SECTION *v31; // rcx
  struct _RTL_CRITICAL_SECTION *v32; // r10
  __int64 v33; // rcx
  unsigned int v34; // edi
  unsigned int v35; // edi
  unsigned int v36; // edi
  unsigned int v37; // edi
  unsigned int v38; // edi
  struct _RTL_CRITICAL_SECTION *v39; // r10
  LPCRITICAL_SECTION v40; // r10
  __int64 CurrentTime; // [rsp+20h] [rbp-60h] BYREF
  __int128 v43; // [rsp+28h] [rbp-58h] BYREF
  __int128 v44; // [rsp+38h] [rbp-48h] BYREF
  struct _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+48h] [rbp-38h] BYREF
  __int128 v46; // [rsp+58h] [rbp-28h] BYREF
  __int128 *v47; // [rsp+68h] [rbp-18h]

  v3 = *(_QWORD *)&PfSvcGlobals;
  v4 = 0;
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  v47 = 0;
  CurrentTime = 0;
  v7 = a1;
  v43 = 0;
  v44 = 0;
  v46 = 0;
  if ( !*(_QWORD *)&PfSvcGlobals )
    return 21;
  v8 = 120;
  if ( (_DWORD)a1 == 1 )
    goto LABEL_37;
  v9 = 4;
  switch ( (_DWORD)a1 )
  {
    case 5:
      *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1600LL) |= 0x20u;
LABEL_37:
      *(_DWORD *)(v3 + 1600) |= 0x80u;
      v19 = *(_QWORD *)(v3 + 3656);
      if ( v19 )
      {
        PfSvServiceThreadSetPriority(v3, v19, 0);
        v3 = *(_QWORD *)&PfSvcGlobals;
      }
      v8 = 0;
      break;
    case 0xB:
      v8 = PfDiVolumeNotify();
      goto LABEL_57;
    case 0xD:
      if ( a2 != 32787 )
        goto LABEL_58;
      if ( *(_QWORD *)a3 == *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1
        && *(_QWORD *)(a3 + 8) == *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4 )
      {
        if ( *(_DWORD *)(a3 + 16) != 4 )
          goto LABEL_34;
        v9 = 1;
        v10 = *(_DWORD *)(a3 + 20) != 0;
      }
      else if ( *(_QWORD *)a3 == *(_QWORD *)&GUID_SESSION_USER_PRESENCE.Data1
             && *(_QWORD *)(a3 + 8) == *(_QWORD *)GUID_SESSION_USER_PRESENCE.Data4 )
      {
        if ( *(_DWORD *)(a3 + 16) != 4 )
          goto LABEL_34;
        v10 = *(_DWORD *)(a3 + 20) == 0;
      }
      else
      {
        if ( *(_QWORD *)a3 != *(_QWORD *)&GUID_GLOBAL_USER_PRESENCE.Data1
          || *(_QWORD *)(a3 + 8) != *(_QWORD *)GUID_GLOBAL_USER_PRESENCE.Data4
          || *(_DWORD *)(a3 + 16) != 4 )
        {
          goto LABEL_34;
        }
        v11 = *(_DWORD *)(a3 + 20);
        v9 = 2;
        v10 = v11 == 0;
        if ( v11 )
        {
          UnbiasedTickCount = PfsGetUnbiasedTickCount();
          *(_DWORD *)(v13 + 1608) = UnbiasedTickCount;
          v3 = *(_QWORD *)&PfSvcGlobals;
        }
      }
      LODWORD(a1) = *(_DWORD *)(v3 + 1604);
      do
      {
        v14 = a1;
        if ( v9 == 1 )
          LODWORD(a1) = a1 + 0x10000;
        if ( v10 )
          v15 = v9 | a1;
        else
          v15 = ~v9 & a1;
        v17 = v14;
        v16 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 1604), v15, v14);
        a1 = v16;
      }
      while ( v17 != v16 );
      if ( v9 == 1 )
      {
        PfSvCSStateChangeNotify(*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1604LL) & 1);
LABEL_33:
        v3 = *(_QWORD *)&PfSvcGlobals;
        goto LABEL_34;
      }
      if ( ((v9 - 2) & 0xFFFFFFFD) != 0 )
        goto LABEL_33;
      v3 = *(_QWORD *)&PfSvcGlobals;
      if ( *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4056LL) )
      {
        CurrentTime = PfsActionItemGetCurrentTime(v16);
        PfsActionItemQueueEx(v18, 0x28u, (unsigned __int64 *)&CurrentTime, 0);
        goto LABEL_33;
      }
LABEL_34:
      v8 = 0;
      goto LABEL_58;
  }
  if ( v7 != 14 )
    goto LABEL_58;
  if ( !*(_QWORD *)(v3 + 1696) && (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 324LL) & 0x3100) == 0 )
    return 21;
  if ( ((a2 - 1) & 0xFFFFFFFA) != 0 )
    return 0;
  SessionUserInfo = PfSvGetSessionUserInfo(*(unsigned int *)(a3 + 4), &CurrentTime);
  v4 = (PSID *)CurrentTime;
  v8 = SessionUserInfo;
  PfSvSessionChangeLogEvent(a2, CurrentTime, *(unsigned int *)(a3 + 4));
  if ( v4 )
  {
    switch ( a2 )
    {
      case 1u:
        goto LABEL_49;
      case 2u:
        v21 = *(struct _RTL_CRITICAL_SECTION **)&PfSvcGlobals;
        v22 = 72;
        v23 = *(_QWORD *)&PfSvcGlobals + 1856LL;
        goto LABEL_50;
      case 5u:
LABEL_49:
        v21 = *(struct _RTL_CRITICAL_SECTION **)&PfSvcGlobals;
        v22 = 71;
        v23 = *(_QWORD *)&PfSvcGlobals + 1840LL;
LABEL_50:
        EnterCriticalSection(v21 + 45);
        v24 = *(_DWORD *)(a3 + 4) & 0x3FFFFFFF;
        *(_DWORD *)v23 = v24;
        if ( a2 == 5 )
          *(_DWORD *)v23 = v24 | 0x80000000;
        LengthSid = GetLengthSid(*v4);
        CopySid(LengthSid, *(PSID *)(v23 + 8), *v4);
        v26 = *(struct _RTL_CRITICAL_SECTION **)&PfSvcGlobals;
        *(_DWORD *)v23 |= 0x40000000u;
        LeaveCriticalSection(v26 + 45);
        v27 = ((__int64 (*)(void))PfsActionItemGetCurrentTime)();
        v29 = v22;
        goto LABEL_56;
    }
  }
  if ( a2 == 6 )
  {
    v30 = *(_QWORD *)&PfSvcGlobals;
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1800LL));
    v31 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)&PfSvcGlobals + 1800LL);
    *(_DWORD *)(v30 + 1856) = *(_DWORD *)(a3 + 4) & 0x3FFFFFFF | 0x80000000;
    LeaveCriticalSection(v31);
    v27 = ((__int64 (*)(void))PfsActionItemGetCurrentTime)();
    v29 = 72;
LABEL_56:
    CurrentTime = v27;
    PfsActionItemQueueEx(v28 + 43, v29, (unsigned __int64 *)&CurrentTime, 0);
  }
LABEL_57:
  v3 = *(_QWORD *)&PfSvcGlobals;
LABEL_58:
  if ( !*(_QWORD *)(v3 + 1696) )
  {
    v8 = 21;
    goto LABEL_83;
  }
  if ( v7 != 13 )
    goto LABEL_83;
  v44 = 0;
  LODWORD(v44) = a2;
  v43 = 0;
  if ( a2 == 32787 )
  {
    if ( *(_QWORD *)a3 == *(_QWORD *)&GUID_BATTERY_PERCENTAGE_REMAINING.Data1
      && *(_QWORD *)(a3 + 8) == *(_QWORD *)GUID_BATTERY_PERCENTAGE_REMAINING.Data4 )
    {
      CurrentTime = PfsActionItemGetCurrentTime(a1);
      PfsActionItemQueueEx(v32 + 43, 9u, (unsigned __int64 *)&CurrentTime, 0);
    }
  }
  else if ( a2 == 10 )
  {
    CurrentTime = PfsActionItemGetCurrentTime(a1);
    PfsActionItemQueueEx(v39 + 43, 9u, (unsigned __int64 *)&CurrentTime, 0);
    if ( GetSystemPowerStatus(&SystemPowerStatus) )
    {
      WORD4(v44) = *(_WORD *)&SystemPowerStatus.ACLineStatus;
      BYTE10(v44) = SystemPowerStatus.BatteryLifePercent;
    }
    else
    {
      *((_QWORD *)&v44 + 1) = 0;
    }
    goto LABEL_66;
  }
  *((_QWORD *)&v44 + 1) = a3;
LABEL_66:
  *(_QWORD *)&v43 = v43 & 0xFFFFFFFFFFFE0000uLL | 0x1000B;
  *(_QWORD *)&v43 = v43 | 0x20000;
  v33 = *(_QWORD *)&PfSvcGlobals;
  DWORD2(v43) = *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 240LL)
              + ((unsigned __int64)((((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                   * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64) >> 10);
  v34 = a2 - 2;
  if ( v34 && (v35 = v34 - 1) != 0 )
  {
    v36 = v35 - 3;
    if ( (!v36 || (v37 = v36 - 1) == 0 || (v38 = v37 - 1) == 0 || v38 == 10)
      && *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 3760LL) == 2 )
    {
      *((_QWORD *)&v44 + 1) |= 1uLL;
    }
  }
  else
  {
    CurrentTime = PfsActionItemGetCurrentTime(*(_QWORD *)&PfSvcGlobals);
    PfsActionItemQueueEx(v40, 0x13u, (unsigned __int64 *)&CurrentTime, 0);
    v33 = *(_QWORD *)&PfSvcGlobals;
  }
  v8 = 0;
  if ( (*(_BYTE *)(v33 + 460) & 0x40) != 0 )
  {
    PfLgpTraceEvent(v33 + 384, 21, &v44, 16);
    v33 = *(_QWORD *)&PfSvcGlobals;
  }
  if ( (*(_DWORD *)(v33 + 244) & 0x100) == 0 )
    goto LABEL_84;
  v47 = &v43;
  v46 = 0x400000000001uLL;
  PfSvServiceCommandSend(v33 + 1616, &v46, 24);
LABEL_83:
  v33 = *(_QWORD *)&PfSvcGlobals;
LABEL_84:
  if ( v4 )
    HeapFree(*(HANDLE *)(v33 + 88), 0, v4);
  return v8;
}

```

## disassembly

```asm
0x18004c020  mov     [rsp-38h+arg_0], rbx
0x18004c025  push    rbp
0x18004c026  push    rsi
0x18004c027  push    rdi
0x18004c028  push    r12
0x18004c02a  push    r13
0x18004c02c  push    r14
0x18004c02e  push    r15
0x18004c030  mov     rbp, rsp
0x18004c033  sub     rsp, 80h
0x18004c03a  mov     rax, cs:__security_cookie
0x18004c041  xor     rax, rsp
0x18004c044  mov     [rbp+var_10], rax
0x18004c048  mov     r9, cs:PfSvcGlobals
0x18004c04f  xor     eax, eax
0x18004c051  xor     r12d, r12d
0x18004c054  mov     qword ptr [rbp+SystemPowerStatus.ACLineStatus], rax
0x18004c058  mov     [rbp+SystemPowerStatus.BatteryFullLifeTime], eax
0x18004c05b  xorps   xmm0, xmm0
0x18004c05e  mov     [rbp+var_18], rax
0x18004c062  xorps   xmm1, xmm1
0x18004c065  mov     [rbp+var_60], r12
0x18004c069  mov     rsi, r8
0x18004c06c  mov     edi, edx
0x18004c06e  mov     r13d, ecx
0x18004c071  movups  [rbp+var_58], xmm0
0x18004c075  movups  [rbp+var_48], xmm0
0x18004c079  movups  [rbp+var_28], xmm1
0x18004c07d  test    r9, r9
0x18004c080  jnz     short loc_18004C08D
0x18004c082  mov     r14d, 15h
0x18004c088  jmp     loc_18004C5F0
0x18004c08d  mov     eax, r13d
0x18004c090  mov     r14d, 78h ; 'x'
0x18004c096  sub     eax, 1
0x18004c099  jz      loc_18004C238
0x18004c09f  lea     r10d, [r14-74h]
0x18004c0a3  sub     eax, r10d
0x18004c0a6  jz      loc_18004C230
0x18004c0ac  sub     eax, 6
0x18004c0af  jz      loc_18004C223
0x18004c0b5  cmp     eax, 2
0x18004c0b8  jnz     loc_18004C262
0x18004c0be  cmp     edi, 8013h
0x18004c0c4  jnz     loc_18004C3DD
0x18004c0ca  mov     rax, [r8]
0x18004c0cd  cmp     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18004c0d4  jnz     short loc_18004C101
0x18004c0d6  mov     rax, [r8+8]
0x18004c0da  cmp     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x18004c0e1  jnz     short loc_18004C101
0x18004c0e3  cmp     [r8+10h], r10d
0x18004c0e7  jnz     loc_18004C21B
0x18004c0ed  xor     r11d, r11d
0x18004c0f0  lea     r10d, [r14-77h]
0x18004c0f4  cmp     [r8+14h], r11d
0x18004c0f8  setnz   r11b
0x18004c0fc  jmp     loc_18004C186
0x18004c101  mov     rax, [r8]
0x18004c104  cmp     rax, qword ptr cs:GUID_SESSION_USER_PRESENCE.Data1
0x18004c10b  jnz     short loc_18004C131
0x18004c10d  mov     rax, [r8+8]
0x18004c111  cmp     rax, qword ptr cs:GUID_SESSION_USER_PRESENCE.Data4
0x18004c118  jnz     short loc_18004C131
0x18004c11a  cmp     [r8+10h], r10d
0x18004c11e  jnz     loc_18004C21B
0x18004c124  xor     r11d, r11d
0x18004c127  cmp     [r8+14h], r11d
0x18004c12b  setz    r11b
0x18004c12f  jmp     short loc_18004C186
0x18004c131  mov     rax, [r8]
0x18004c134  cmp     rax, qword ptr cs:GUID_GLOBAL_USER_PRESENCE.Data1
0x18004c13b  jnz     loc_18004C21B
0x18004c141  mov     rax, [r8+8]
0x18004c145  cmp     rax, qword ptr cs:GUID_GLOBAL_USER_PRESENCE.Data4
0x18004c14c  jnz     loc_18004C21B
0x18004c152  cmp     [r8+10h], r10d
0x18004c156  jnz     loc_18004C21B
0x18004c15c  mov     eax, [r8+14h]
0x18004c160  xor     r11d, r11d
0x18004c163  test    eax, eax
0x18004c165  mov     r10d, 2
0x18004c16b  setz    r11b
0x18004c16f  test    eax, eax
0x18004c171  jz      short loc_18004C186
0x18004c173  call    PfsGetUnbiasedTickCount
0x18004c178  mov     [r9+648h], eax
0x18004c17f  mov     r9, cs:PfSvcGlobals
0x18004c186  mov     ecx, [r9+644h]
0x18004c18d  mov     eax, ecx
0x18004c18f  cmp     r10d, 1
0x18004c193  jnz     short loc_18004C19B
0x18004c195  add     ecx, 10000h
0x18004c19b  test    r11d, r11d
0x18004c19e  jz      short loc_18004C1A5
0x18004c1a0  or      ecx, r10d
0x18004c1a3  jmp     short loc_18004C1AC
0x18004c1a5  mov     edx, r10d
0x18004c1a8  not     edx
0x18004c1aa  and     ecx, edx
0x18004c1ac  lock cmpxchg [r9+644h], ecx
0x18004c1b5  mov     ecx, eax
0x18004c1b7  jnz     short loc_18004C18D
0x18004c1b9  cmp     r10d, 1
0x18004c1bd  jnz     short loc_18004C1D6
0x18004c1bf  mov     rax, cs:PfSvcGlobals
0x18004c1c6  mov     ecx, [rax+644h]
0x18004c1cc  and     ecx, r10d
0x18004c1cf  call    PfSvCSStateChangeNotify
0x18004c1d4  jmp     short loc_18004C214
0x18004c1d6  lea     eax, [r10-2]
0x18004c1da  test    eax, 0FFFFFFFDh
0x18004c1df  jnz     short loc_18004C214
0x18004c1e1  mov     r9, cs:PfSvcGlobals
0x18004c1e8  cmp     [r9+0FD8h], r12
0x18004c1ef  jz      short loc_18004C21B
0x18004c1f1  lea     r10, [r9+6B8h]
0x18004c1f8  call    PfsActionItemGetCurrentTime
0x18004c1fd  xor     r9d, r9d
0x18004c200  mov     [rbp+var_60], rax
0x18004c204  lea     r8, [rbp+var_60]
0x18004c208  mov     rcx, r10; lpCriticalSection
0x18004c20b  lea     edx, [r9+28h]
0x18004c20f  call    PfsActionItemQueueEx
0x18004c214  mov     r9, cs:PfSvcGlobals
0x18004c21b  xor     r14d, r14d
0x18004c21e  jmp     loc_18004C3DD
0x18004c223  call    PfDiVolumeNotify
0x18004c228  mov     r14d, eax
0x18004c22b  jmp     loc_18004C3D6
0x18004c230  or      dword ptr [r9+640h], 20h
0x18004c238  bts     dword ptr [r9+640h], 7
0x18004c241  mov     rdx, [r9+0E48h]
0x18004c248  test    rdx, rdx
0x18004c24b  jz      short loc_18004C25F
0x18004c24d  xor     r8d, r8d
0x18004c250  mov     rcx, r9
0x18004c253  call    PfSvServiceThreadSetPriority
0x18004c258  mov     r9, cs:PfSvcGlobals
0x18004c25f  xor     r14d, r14d
0x18004c262  cmp     r13d, 0Eh
0x18004c266  jnz     loc_18004C3DD
0x18004c26c  mov     rax, [r9+6A0h]
0x18004c273  test    rax, rax
0x18004c276  jnz     short loc_18004C28F
0x18004c278  mov     rax, cs:PfSvcGlobals
0x18004c27f  test    dword ptr [rax+144h], 3100h
0x18004c289  jz      loc_18004C082
0x18004c28f  lea     eax, [rdi-1]
0x18004c292  test    eax, 0FFFFFFFAh
0x18004c297  jz      short loc_18004C2A1
0x18004c299  xor     r14d, r14d
0x18004c29c  jmp     loc_18004C5F0
0x18004c2a1  mov     ecx, [rsi+4]
0x18004c2a4  lea     rdx, [rbp+var_60]
0x18004c2a8  call    PfSvGetSessionUserInfo
0x18004c2ad  mov     r12, [rbp+var_60]
0x18004c2b1  mov     ecx, edi
0x18004c2b3  mov     r8d, [rsi+4]
0x18004c2b7  mov     rdx, r12
0x18004c2ba  mov     r14d, eax
0x18004c2bd  call    PfSvSessionChangeLogEvent
0x18004c2c2  test    r12, r12
0x18004c2c5  jz      loc_18004C371
0x18004c2cb  cmp     edi, 1
0x18004c2ce  jz      short loc_18004C2E2
0x18004c2d0  cmp     edi, 2
0x18004c2d3  jz      loc_18004C35B
0x18004c2d9  cmp     edi, 5
0x18004c2dc  jnz     loc_18004C371
0x18004c2e2  mov     rcx, cs:PfSvcGlobals
0x18004c2e9  mov     r15d, 47h ; 'G'
0x18004c2ef  lea     rbx, [rcx+730h]
0x18004c2f6  add     rcx, 708h; lpCriticalSection
0x18004c2fd  call    cs:__imp_EnterCriticalSection
0x18004c303  mov     eax, [rsi+4]
0x18004c306  and     eax, 3FFFFFFFh
0x18004c30b  mov     [rbx], eax
0x18004c30d  cmp     edi, 5
0x18004c310  jnz     short loc_18004C318
0x18004c312  bts     eax, 1Fh
0x18004c316  mov     [rbx], eax
0x18004c318  mov     rcx, [r12]; pSid
0x18004c31c  call    cs:__imp_GetLengthSid
0x18004c322  mov     r8, [r12]; pSourceSid
0x18004c326  mov     ecx, eax; nDestinationSidLength
0x18004c328  mov     rdx, [rbx+8]; pDestinationSid
0x18004c32c  call    cs:__imp_CopySid
0x18004c332  mov     rcx, cs:PfSvcGlobals
0x18004c339  bts     dword ptr [rbx], 1Eh
0x18004c33d  add     rcx, 708h; lpCriticalSection
0x18004c344  call    cs:__imp_LeaveCriticalSection
0x18004c34a  mov     r10, cs:PfSvcGlobals
0x18004c351  call    PfsActionItemGetCurrentTime
0x18004c356  mov     edx, r15d
0x18004c359  jmp     short loc_18004C3BF
0x18004c35b  mov     rcx, cs:PfSvcGlobals
0x18004c362  mov     r15d, 48h ; 'H'
0x18004c368  lea     rbx, [rcx+740h]
0x18004c36f  jmp     short loc_18004C2F6
0x18004c371  cmp     edi, 6
0x18004c374  jnz     short loc_18004C3D6
0x18004c376  mov     rbx, cs:PfSvcGlobals
0x18004c37d  lea     rcx, [rbx+708h]; lpCriticalSection
0x18004c384  call    cs:__imp_EnterCriticalSection
0x18004c38a  mov     eax, [rsi+4]
0x18004c38d  mov     rcx, cs:PfSvcGlobals
0x18004c394  and     eax, 3FFFFFFFh
0x18004c399  bts     eax, 1Fh
0x18004c39d  add     rcx, 708h; lpCriticalSection
0x18004c3a4  mov     [rbx+740h], eax
0x18004c3aa  call    cs:__imp_LeaveCriticalSection
0x18004c3b0  mov     r10, cs:PfSvcGlobals
0x18004c3b7  call    PfsActionItemGetCurrentTime
0x18004c3bc  lea     edx, [rdi+42h]
0x18004c3bf  xor     r9d, r9d
0x18004c3c2  mov     [rbp+var_60], rax
0x18004c3c6  lea     r8, [rbp+var_60]
0x18004c3ca  lea     rcx, [r10+6B8h]; lpCriticalSection
0x18004c3d1  call    PfsActionItemQueueEx
0x18004c3d6  mov     r9, cs:PfSvcGlobals
0x18004c3dd  mov     rax, [r9+6A0h]
0x18004c3e4  test    rax, rax
0x18004c3e7  jnz     short loc_18004C3F2
0x18004c3e9  lea     r14d, [rax+15h]
0x18004c3ed  jmp     loc_18004C5D5
0x18004c3f2  cmp     r13d, 0Dh
0x18004c3f6  jnz     loc_18004C5D5
0x18004c3fc  xorps   xmm0, xmm0
0x18004c3ff  movups  [rbp+var_48], xmm0
0x18004c403  mov     dword ptr [rbp+var_48], edi
0x18004c406  movups  [rbp+var_58], xmm0
0x18004c40a  cmp     edi, 8013h
0x18004c410  jnz     loc_18004C4E3
0x18004c416  mov     rax, [rsi]
0x18004c419  cmp     rax, qword ptr cs:GUID_BATTERY_PERCENTAGE_REMAINING.Data1
0x18004c420  jnz     short loc_18004C456
0x18004c422  mov     rax, [rsi+8]
0x18004c426  cmp     rax, qword ptr cs:GUID_BATTERY_PERCENTAGE_REMAINING.Data4
0x18004c42d  jnz     short loc_18004C456
0x18004c42f  mov     r10, cs:PfSvcGlobals
0x18004c436  call    PfsActionItemGetCurrentTime
0x18004c43b  lea     r8, [rbp+var_60]
0x18004c43f  mov     [rbp+var_60], rax
0x18004c443  lea     edx, [r13-4]
0x18004c447  xor     r9d, r9d
0x18004c44a  lea     rcx, [r10+6B8h]; lpCriticalSection
0x18004c451  call    PfsActionItemQueueEx
0x18004c456  mov     qword ptr [rbp+var_48+8], rsi
0x18004c45a  mov     rax, qword ptr [rbp+var_58]
0x18004c45e  and     rax, 0FFFFFFFFFFFF000Bh
0x18004c464  or      rax, 1000Bh
0x18004c46a  mov     qword ptr [rbp+var_58], rax
0x18004c46e  mov     eax, 7FFE0320h
0x18004c473  mov     ecx, ds:7FFE0004h
0x18004c47a  shl     rcx, 20h
0x18004c47e  mov     rax, [rax]
0x18004c481  bts     qword ptr [rbp+var_58], 11h
0x18004c487  shl     rax, 8
0x18004c48b  mul     rcx
0x18004c48e  mov     rcx, cs:PfSvcGlobals
0x18004c495  shr     rdx, 0Ah
0x18004c499  add     edx, [rcx+0F0h]
0x18004c49f  mov     dword ptr [rbp+var_58+8], edx
0x18004c4a2  sub     edi, 2
0x18004c4a5  jz      loc_18004C544
0x18004c4ab  sub     edi, 1
0x18004c4ae  jz      loc_18004C544
0x18004c4b4  sub     edi, 3
0x18004c4b7  jz      short loc_18004C4CC
0x18004c4b9  sub     edi, 1
0x18004c4bc  jz      short loc_18004C4CC
0x18004c4be  sub     edi, 1
0x18004c4c1  jz      short loc_18004C4CC
0x18004c4c3  cmp     edi, 0Ah
0x18004c4c6  jnz     loc_18004C56E
0x18004c4cc  cmp     dword ptr [rcx+0EB0h], 2
0x18004c4d3  jnz     loc_18004C56E
0x18004c4d9  or      qword ptr [rbp+var_48+8], 1
0x18004c4de  jmp     loc_18004C56E
0x18004c4e3  cmp     edi, 0Ah
0x18004c4e6  jnz     loc_18004C456
0x18004c4ec  mov     r10, cs:PfSvcGlobals
0x18004c4f3  call    PfsActionItemGetCurrentTime
0x18004c4f8  lea     r8, [rbp+var_60]
0x18004c4fc  mov     [rbp+var_60], rax
0x18004c500  lea     edx, [rdi-1]
0x18004c503  xor     r9d, r9d
0x18004c506  lea     rcx, [r10+6B8h]; lpCriticalSection
0x18004c50d  call    PfsActionItemQueueEx
0x18004c512  lea     rcx, [rbp+SystemPowerStatus]; lpSystemPowerStatus
0x18004c516  call    cs:__imp_GetSystemPowerStatus
0x18004c51c  test    eax, eax
0x18004c51e  jz      short loc_18004C537
0x18004c520  mov     al, [rbp+SystemPowerStatus.ACLineStatus]
0x18004c523  mov     byte ptr [rbp+var_48+8], al
0x18004c526  mov     al, [rbp+SystemPowerStatus.BatteryFlag]
0x18004c529  mov     byte ptr [rbp+var_48+9], al
0x18004c52c  mov     al, [rbp+SystemPowerStatus.BatteryLifePercent]
0x18004c52f  mov     byte ptr [rbp+var_48+0Ah], al
  ... truncated ...
```
