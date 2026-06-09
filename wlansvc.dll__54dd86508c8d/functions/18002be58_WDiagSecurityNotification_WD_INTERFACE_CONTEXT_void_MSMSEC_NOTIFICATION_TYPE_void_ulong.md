# WDiagSecurityNotification(_WD_INTERFACE_CONTEXT *,void *,MSMSEC_NOTIFICATION_TYPE,void *,ulong)

- ea: `0x18002be58`
- end: `0x18002c966`
- name: `?WDiagSecurityNotification@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXW4MSMSEC_NOTIFICATION_TYPE@@1K@Z`
- size: `2830`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010f20`

## callees

- `0x180011530`
- `0x18001e950`
- `0x180029ed4`
- `0x18002ac84`
- `0x18002afc4`
- `0x18002bde8`
- `0x18002be58`
- `0x18002c96c`
- `0x18005f3d0`
- `0x18008ac38`
- `0x1800dc258`
- `0x1801c7b38`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bec9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bf44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bec9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bf44`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bed6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bf51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bed6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bf51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bebd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bf38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c8ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bebd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bf38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c8ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002be9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002be9c`

## string_xrefs

- `0x18002bee0`: `WDiagSecurityNotification`
- `0x18002bf6c`: `WDiagSecurityNotification`
- `0x18002c05a`: `WDiagSecurityNotification`
- `0x18002c380`: `WDiagSecurityNotification`
- `0x18002c392`: `WDiagSecurityNotification`
- `0x18002c426`: `WDiagSecurityNotification`
- `0x18002c883`: `WDiagSecurityNotification`
- `0x18002c5bb`: `UPDATE`

## pseudocode

```c
__int64 __fastcall WDiagSecurityNotification(__int64 a1, void *a2, int a3, __int64 a4)
{
  __int64 v4; // r15
  __int64 v8; // rbx
  ULONGLONG v9; // r14
  DWORD CurrentThreadId; // edi
  struct _PM_PROFILE *v11; // r8
  struct _DOT11_SSID *v12; // r9
  struct _WD_CONNECTION_CONTEXT *MatchingConnection; // rax
  struct _WD_CONNECTION_CONTEXT *v14; // r13
  char *v15; // rdi
  DWORD v16; // esi
  int v17; // r8d
  int v18; // eax
  int v19; // ecx
  PVOID *v20; // r12
  unsigned int v21; // r8d
  unsigned int v22; // esi
  PVOID *v23; // rcx
  int v25; // ecx
  int v26; // eax
  const char *v27; // r9
  unsigned int v28; // eax
  char v29; // al
  char v30; // al
  enum _DOT11_BSS_TYPE v31; // [rsp+20h] [rbp-A8h]
  int v32; // [rsp+28h] [rbp-A0h]
  char v33[8]; // [rsp+80h] [rbp-48h]
  ULONGLONG TickCount64; // [rsp+88h] [rbp-40h]

  v4 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 70, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  v8 = a1 + 3352;
  TickCount64 = GetTickCount64();
  v9 = TickCount64;
  *(_QWORD *)v33 = a1 + 3352;
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 3360));
  WaitForSingleObject(*(HANDLE *)(a1 + 3440), 0xFFFFFFFF);
  if ( (*(_BYTE *)(a1 + 3448) & 4) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      a1 + 24,
      *(_DWORD *)(a1 + 3456),
      *(_QWORD *)(a1 + 3464),
      *(_DWORD *)(a1 + 3460),
      CurrentThreadId,
      (__int64)"WDiagSecurityNotification",
      92);
  }
  *(_DWORD *)(a1 + 3448) |= 4u;
  *(_DWORD *)(a1 + 3456) = CurrentThreadId;
  *(_DWORD *)(a1 + 3460) = 1628;
  *(_QWORD *)(a1 + 3464) = "WDiagSecurityNotification";
  MatchingConnection = FindMatchingConnection((struct _WD_INTERFACE_CONTEXT *)a1, a2, v11, v12, v31, 1u, 2u);
  v14 = MatchingConnection;
  if ( MatchingConnection )
  {
    v15 = (char *)MatchingConnection + 3920;
    v16 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
    WaitForSingleObject(*((HANDLE *)v15 + 11), 0xFFFFFFFF);
    if ( (v15[96] & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v15,
        *((_DWORD *)v15 + 26),
        *((_QWORD *)v15 + 14),
        *((_DWORD *)v15 + 27),
        v16,
        (__int64)"WDiagSecurityNotification",
        109);
    }
    *((_DWORD *)v15 + 24) |= 4u;
    *((_QWORD *)v15 + 14) = "WDiagSecurityNotification";
    *((_DWORD *)v15 + 26) = v16;
    *((_DWORD *)v15 + 27) = 1645;
    v18 = *((_DWORD *)v14 + 299);
    if ( (v18 & 8) == 0 && (v18 & 4) != 0 )
    {
      *((_DWORD *)v14 + 299) = v18 | 8;
      WDiagGetTime((LPFILETIME)v14 + 210);
      *((_QWORD *)v14 + 212) = TickCount64;
    }
    switch ( a3 )
    {
      case 65537:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
        {
          v32 = *(_DWORD *)(v4 + 4);
          WPP_SF_ddDdDDDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            *(unsigned __int8 *)(v4 + 12),
            *(unsigned __int8 *)(v4 + 11),
            *(unsigned int *)(v4 + 16),
            *(_DWORD *)v4);
        }
        *((_DWORD *)v14 + 436) = *(_DWORD *)(v4 + 16);
        *((_DWORD *)v14 + 441) = *(_DWORD *)v4;
        *((_DWORD *)v14 + 442) = *(_DWORD *)(v4 + 4);
        if ( *(_DWORD *)(v4 + 16) == 4 )
        {
          *((_DWORD *)v14 + 434) = *(_DWORD *)(v4 + 20);
          *((_DWORD *)v14 + 437) = *(_DWORD *)(v4 + 24);
        }
        break;
      case 65538:
        v19 = *((_DWORD *)v14 + 841) - *(_DWORD *)v4;
        if ( !v19 )
          v19 = *((unsigned __int16 *)v14 + 1684) - *(unsigned __int16 *)(v4 + 4);
        if ( v19 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
          {
            WPP_SF_DDDDDDDDDDDD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              73,
              *(unsigned __int8 *)(v4 + 4),
              *((unsigned __int8 *)v14 + 3364),
              *((_BYTE *)v14 + 3365),
              *((_BYTE *)v14 + 3366),
              *((_BYTE *)v14 + 3367),
              *((_BYTE *)v14 + 3368),
              *((_BYTE *)v14 + 3369),
              *(_BYTE *)v4,
              *(_BYTE *)(v4 + 1),
              *(_BYTE *)(v4 + 2),
              *(_BYTE *)(v4 + 3),
              *(_BYTE *)(v4 + 4),
              *(_BYTE *)(v4 + 5));
            v4 = a4;
            v9 = TickCount64;
          }
          *((_DWORD *)v14 + 841) = *(_DWORD *)v4;
          *((_WORD *)v14 + 1684) = *(_WORD *)(v4 + 4);
          WDiagGetTime((LPFILETIME)v14 + 210);
          *((_QWORD *)v14 + 212) = v9;
          *((_QWORD *)v14 + 226) = 0;
          *((_QWORD *)v14 + 225) = 0;
        }
        if ( *(_DWORD *)(v4 + 20) == 2 )
        {
          *((_DWORD *)v14 + 299) &= ~0x10u;
          *((_DWORD *)v14 + 430) |= 1u;
        }
        else
        {
          if ( *(_DWORD *)(v4 + 20) != 3 )
          {
            if ( *(_DWORD *)(v4 + 20) == 4 )
            {
              ++*((_DWORD *)v14 + 454);
              *((_DWORD *)v14 + 430) |= 0x1000u;
              *((_DWORD *)v14 + 299) |= 0x10u;
              *((_DWORD *)v14 + 435) = 0;
              WDiagGetTime((LPFILETIME)v14 + 211);
              *((_QWORD *)v14 + 213) = v9;
            }
            else if ( *(_DWORD *)(v4 + 20) == 5 )
            {
              *((_DWORD *)v14 + 430) |= 0x2000u;
              *((_DWORD *)v14 + 435) = *(_DWORD *)(v4 + 32);
              *((_DWORD *)v14 + 437) = *(_DWORD *)(v4 + 36);
              v20 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u
                || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0 )
              {
                goto LABEL_16;
              }
              WPP_SF_DD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                74,
                &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids,
                *(unsigned int *)(v4 + 32));
            }
LABEL_15:
            v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
            if ( *(_DWORD *)(v4 + 24) )
            {
              *((_DWORD *)v14 + 430) |= 0x100u;
              v20 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( *(_DWORD *)(v4 + 28) )
            {
              *((_DWORD *)v14 + 430) |= 0x200u;
              v20 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v20 != &WPP_GLOBAL_Control )
            {
              if ( *((_BYTE *)v20 + 225) >= 3u && (*((_BYTE *)v20 + 228) & 4) != 0 )
              {
                v25 = *(_DWORD *)(v4 + 20);
                v26 = v25;
                if ( v25 > 6 )
                  v26 = 6;
                WPP_SF_dDDDdS(
                  (unsigned int)v20[27],
                  (unsigned int)&g_strMsmSecState,
                  v17,
                  *(_DWORD *)(v4 + 12),
                  *(_DWORD *)(v4 + 16),
                  *(_DWORD *)(v4 + 24),
                  *(_DWORD *)(v4 + 28),
                  v25,
                  (__int64)(&g_strMsmSecState)[v26]);
                v20 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v20 != &WPP_GLOBAL_Control && *((_BYTE *)v20 + 225) >= 3u && (*((_BYTE *)v20 + 228) & 4) != 0 )
              {
                WPP_SF_DDDDDDDDDDDD(
                  (unsigned int)v20[27],
                  76,
                  *(unsigned __int8 *)(v4 + 3),
                  *(unsigned __int8 *)(a4 + 6),
                  *(_BYTE *)(v4 + 7),
                  *(_BYTE *)(v4 + 8),
                  *(_BYTE *)(v4 + 9),
                  *(_BYTE *)(v4 + 10),
                  *(_BYTE *)(v4 + 11),
                  *(_BYTE *)v4,
                  *(_BYTE *)(v4 + 1),
                  *(_BYTE *)(v4 + 2),
                  *(_BYTE *)(v4 + 3),
                  *(_BYTE *)(v4 + 4),
                  *(_BYTE *)(v4 + 5));
                v20 = (PVOID *)WPP_GLOBAL_Control;
                v4 = a4;
              }
            }
            v21 = *(_DWORD *)(v4 + 40);
            if ( v21 )
            {
              v28 = WDiagOneXResultUpdate(v14, (struct _ONEX_RESULT_UPDATE_DATA *)(v4 + 56), v21, 0);
              v20 = (PVOID *)WPP_GLOBAL_Control;
              v15 = (char *)v14 + 3920;
              v8 = *(_QWORD *)v33;
              v22 = v28;
LABEL_24:
              if ( (v15[96] & 4) == 0
                && v20 != &WPP_GLOBAL_Control
                && *((_BYTE *)v20 + 225)
                && (*((_BYTE *)v20 + 228) & 0x40) != 0 )
              {
                v29 = GetCurrentThreadId();
                WPP_SF_qqDsdDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  (char)v15,
                  v32,
                  *((_QWORD *)v15 + 16),
                  *((_DWORD *)v15 + 30),
                  v29,
                  (__int64)"WDiagSecurityNotification",
                  115);
              }
              *((_DWORD *)v15 + 30) = 1907;
              *((_DWORD *)v15 + 26) = 0;
              *((_QWORD *)v15 + 16) = "WDiagSecurityNotification";
              *((_DWORD *)v15 + 24) &= ~4u;
              LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
              if ( (*(_BYTE *)(v8 + 96) & 4) == 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 225)
                && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
              {
                v30 = GetCurrentThreadId();
                WPP_SF_qqDsdDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  v8,
                  v32,
                  *(_QWORD *)(v8 + 128),
                  *(_DWORD *)(v8 + 120),
                  v30,
                  (__int64)"WDiagSecurityNotification",
                  116);
              }
              *(_DWORD *)(v8 + 96) &= ~4u;
              *(_DWORD *)(v8 + 120) = 1908;
              *(_QWORD *)(v8 + 128) = "WDiagSecurityNotification";
              *(_DWORD *)(v8 + 104) = 0;
              LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
              v23 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_27;
            }
            v8 = *(_QWORD *)v33;
            v15 = (char *)v14 + 3920;
LABEL_23:
            v22 = 0;
            goto LABEL_24;
          }
          *((_DWORD *)v14 + 430) |= 0x800u;
          ++*((_DWORD *)v14 + 453);
        }
        WDiagGetTime((LPFILETIME)v14 + 214);
        goto LABEL_15;
      case 65539:
      case 65540:
      case 65541:
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u
          || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0 )
        {
          goto LABEL_23;
        }
        if ( a3 == 65539 )
        {
          v27 = "ADD";
        }
        else
        {
          v27 = "DEL";
          if ( a3 != 65541 )
            v27 = "UPDATE";
        }
        WPP_SF_sDDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          *(unsigned __int8 *)(v4 + 3),
          *(unsigned __int8 *)(v4 + 2),
          (_DWORD)v27,
          *(_BYTE *)v4,
          *(_BYTE *)(v4 + 1),
          *(_BYTE *)(v4 + 2),
          *(_BYTE *)(v4 + 3),
          *(_BYTE *)(v4 + 4),
          *(_BYTE *)(v4 + 5));
        break;
      default:
        if ( (unsigned int)(a3 - 65542) < 2 )
        {
          if ( v4 && !*((_DWORD *)v14 + 434) )
            *((_DWORD *)v14 + 434) = *(_DWORD *)(v4 + 12);
          v20 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0 )
          {
            goto LABEL_23;
          }
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 78, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
        }
        break;
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  WDiagReleaseExLock((void *)a1, (struct _WDIAG_RW_LOCK *)(a1 + 3352), "WDiagSecurityNotification", 0x665u);
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 71, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
    v23 = (PVOID *)WPP_GLOBAL_Control;
  }
  v22 = 1168;
LABEL_27:
  if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 57) & 0x200) != 0 )
    WPP_SF_(v23[27], 79, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  return v22;
}

```

## disassembly

```asm
0x18002be58  mov     [rsp+arg_8], rbx
0x18002be5d  mov     [rsp+arg_18], r9
0x18002be62  mov     [rsp+arg_0], rcx
0x18002be67  push    rbp
0x18002be68  push    rsi
0x18002be69  push    rdi
0x18002be6a  push    r12
0x18002be6c  push    r13
0x18002be6e  push    r14
0x18002be70  push    r15
0x18002be72  sub     rsp, 90h
0x18002be79  mov     r15, r9
0x18002be7c  mov     ebp, r8d
0x18002be7f  mov     rsi, rdx
0x18002be82  mov     r12, rcx
0x18002be85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be8c  lea     r13, WPP_GLOBAL_Control
0x18002be93  cmp     rcx, r13
0x18002be96  jnz     loc_18002C2ED
0x18002be9c  call    cs:__imp_GetTickCount64
0x18002bea2  lea     rbx, [r12+0D18h]
0x18002beaa  mov     [rsp+0C8h+var_40], rax
0x18002beb2  mov     r14, rax
0x18002beb5  mov     qword ptr [rsp+0C8h+var_48], rbx
0x18002bebd  call    cs:__imp_GetCurrentThreadId
0x18002bec3  lea     rcx, [rbx+8]; lpCriticalSection
0x18002bec7  mov     edi, eax
0x18002bec9  call    cs:__imp_EnterCriticalSection
0x18002becf  mov     rcx, [rbx+58h]; hHandle
0x18002bed3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002bed6  call    cs:__imp_WaitForSingleObject
0x18002bedc  test    byte ptr [rbx+60h], 4
0x18002bee0  lea     rax, aWdiagsecurityn; "WDiagSecurityNotification"
0x18002bee7  jnz     loc_18002C31A
0x18002beed  or      dword ptr [rbx+60h], 4
0x18002bef1  mov     rdx, rsi; void *
0x18002bef4  mov     [rsp+0C8h+var_98], 2; unsigned int
0x18002befc  mov     rcx, r12; struct _WD_INTERFACE_CONTEXT *
0x18002beff  mov     dword ptr [rsp+0C8h+var_A0], 1; int
0x18002bf07  mov     [rbx+68h], edi
0x18002bf0a  mov     dword ptr [rbx+6Ch], 65Ch
0x18002bf11  mov     [rbx+70h], rax
0x18002bf15  call    ?FindMatchingConnection@@YAPEAU_WD_CONNECTION_CONTEXT@@PEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_PM_PROFILE@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@KK@Z; FindMatchingConnection(_WD_INTERFACE_CONTEXT *,void *,_PM_PROFILE *,_DOT11_SSID *,_DOT11_BSS_TYPE,ulong,ulong)
0x18002bf1a  mov     r13, rax
0x18002bf1d  test    rax, rax
0x18002bf20  jz      loc_18002C38C
0x18002bf26  mov     [rsp+0C8h+arg_20], 0
0x18002bf31  lea     rdi, [rax+0F50h]
0x18002bf38  call    cs:__imp_GetCurrentThreadId
0x18002bf3e  lea     rcx, [rdi+8]; lpCriticalSection
0x18002bf42  mov     esi, eax
0x18002bf44  call    cs:__imp_EnterCriticalSection
0x18002bf4a  mov     rcx, [rdi+58h]; hHandle
0x18002bf4e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002bf51  call    cs:__imp_WaitForSingleObject
0x18002bf57  test    byte ptr [rdi+60h], 4
0x18002bf5b  jnz     loc_18002C3F2
0x18002bf61  lea     r12, WPP_GLOBAL_Control
0x18002bf68  or      dword ptr [rdi+60h], 4
0x18002bf6c  lea     rax, aWdiagsecurityn; "WDiagSecurityNotification"
0x18002bf73  mov     [rdi+70h], rax
0x18002bf77  mov     [rdi+68h], esi
0x18002bf7a  mov     dword ptr [rdi+6Ch], 66Dh
0x18002bf81  mov     eax, [r13+4ACh]
0x18002bf88  test    al, 8
0x18002bf8a  jz      loc_18002C46B
0x18002bf90  mov     ecx, ebp
0x18002bf92  sub     ecx, 10001h
0x18002bf98  jz      loc_18002C156
0x18002bf9e  sub     ecx, 1
0x18002bfa1  jnz     loc_18002C495
0x18002bfa7  mov     ecx, [r13+0D24h]
0x18002bfae  sub     ecx, [r15]
0x18002bfb1  jnz     short loc_18002BFC2
0x18002bfb3  movzx   ecx, word ptr [r13+0D28h]
0x18002bfbb  movzx   eax, word ptr [r15+4]
0x18002bfc0  sub     ecx, eax
0x18002bfc2  test    ecx, ecx
0x18002bfc4  jnz     loc_18002C0F8
0x18002bfca  mov     ecx, [r15+14h]
0x18002bfce  sub     ecx, 2
0x18002bfd1  jz      loc_18002C0D7
0x18002bfd7  sub     ecx, 1
0x18002bfda  jz      loc_18002C1A4
0x18002bfe0  sub     ecx, 1
0x18002bfe3  jz      loc_18002C723
0x18002bfe9  cmp     ecx, 1
0x18002bfec  jz      loc_18002C6A5
0x18002bff2  lea     r14, WPP_GLOBAL_Control
0x18002bff9  mov     r12, cs:WPP_GLOBAL_Control
0x18002c000  cmp     dword ptr [r15+18h], 0
0x18002c005  jnz     loc_18002C75E
0x18002c00b  cmp     dword ptr [r15+1Ch], 0
0x18002c010  jnz     loc_18002C773
0x18002c016  cmp     r12, r14
0x18002c019  jnz     loc_18002C1B9
0x18002c01f  mov     r8d, [r15+28h]; unsigned int
0x18002c023  test    r8d, r8d
0x18002c026  jnz     loc_18002C788
0x18002c02c  mov     rbx, qword ptr [rsp+0C8h+var_48]
0x18002c034  lea     rdi, [r13+0F50h]
0x18002c03b  mov     esi, [rsp+0C8h+arg_20]
0x18002c042  test    byte ptr [rdi+60h], 4
0x18002c046  mov     r15d, 773h
0x18002c04c  jz      loc_18002C84F
0x18002c052  mov     [rdi+78h], r15d
0x18002c056  lea     rcx, [rdi+8]; lpCriticalSection
0x18002c05a  lea     r15, aWdiagsecurityn; "WDiagSecurityNotification"
0x18002c061  mov     dword ptr [rdi+68h], 0
0x18002c068  mov     ebp, 0FFFFFFFBh
0x18002c06d  mov     [rdi+80h], r15
0x18002c074  and     [rdi+60h], ebp
0x18002c077  call    cs:__imp_LeaveCriticalSection
0x18002c07d  test    byte ptr [rbx+60h], 4
0x18002c081  mov     edi, 774h
0x18002c086  jz      loc_18002C8C4
0x18002c08c  and     [rbx+60h], ebp
0x18002c08f  lea     rcx, [rbx+8]; lpCriticalSection
0x18002c093  mov     [rbx+78h], edi
0x18002c096  mov     [rbx+80h], r15
0x18002c09d  mov     dword ptr [rbx+68h], 0
0x18002c0a4  call    cs:__imp_LeaveCriticalSection
0x18002c0aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0b1  cmp     rcx, r14
0x18002c0b4  jnz     loc_18002C939
0x18002c0ba  mov     rbx, [rsp+0C8h+arg_8]
0x18002c0c2  mov     eax, esi
0x18002c0c4  add     rsp, 90h
0x18002c0cb  pop     r15
0x18002c0cd  pop     r14
0x18002c0cf  pop     r13
0x18002c0d1  pop     r12
0x18002c0d3  pop     rdi
0x18002c0d4  pop     rsi
0x18002c0d5  pop     rbp
0x18002c0d6  retn
0x18002c0d7  and     dword ptr [r13+4ACh], 0FFFFFFEFh
0x18002c0df  or      dword ptr [r13+6B8h], 1
0x18002c0e7  lea     rcx, [r13+6B0h]; lpFileTime
0x18002c0ee  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18002c0f3  jmp     loc_18002BFF2
0x18002c0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0ff  cmp     rcx, r12
0x18002c102  jz      short loc_18002C111
0x18002c104  cmp     byte ptr [rcx+0E1h], 3
0x18002c10b  jnb     loc_18002C5F3
0x18002c111  mov     eax, [r15]
0x18002c114  lea     rcx, [r13+690h]; lpFileTime
0x18002c11b  mov     [r13+0D24h], eax
0x18002c122  movzx   eax, word ptr [r15+4]
0x18002c127  mov     [r13+0D28h], ax
0x18002c12f  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18002c134  mov     [r13+6A0h], r14
0x18002c13b  mov     qword ptr [r13+710h], 0
0x18002c146  mov     qword ptr [r13+708h], 0
0x18002c151  jmp     loc_18002BFCA
0x18002c156  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c15d  lea     r14, WPP_GLOBAL_Control
0x18002c164  cmp     rcx, r14
0x18002c167  jnz     loc_18002C7B4
0x18002c16d  mov     eax, [r15+10h]
0x18002c171  mov     [r13+6D0h], eax
0x18002c178  mov     eax, [r15]
0x18002c17b  mov     [r13+6E4h], eax
0x18002c182  mov     eax, [r15+4]
0x18002c186  mov     [r13+6E8h], eax
0x18002c18d  cmp     dword ptr [r15+10h], 4
0x18002c192  jz      loc_18002C834
0x18002c198  mov     r12, cs:WPP_GLOBAL_Control
0x18002c19f  jmp     loc_18002C03B
0x18002c1a4  bts     dword ptr [r13+6B8h], 0Bh
0x18002c1ad  inc     dword ptr [r13+714h]
0x18002c1b4  jmp     loc_18002C0E7
0x18002c1b9  cmp     byte ptr [r12+0E1h], 3
0x18002c1c2  jb      short loc_18002C225
0x18002c1c4  test    byte ptr [r12+0E4h], 4
0x18002c1cd  jz      short loc_18002C225
0x18002c1cf  mov     ecx, [r15+14h]
0x18002c1d3  mov     edx, 6
0x18002c1d8  mov     r9d, [r15+0Ch]
0x18002c1dc  cmp     ecx, edx
0x18002c1de  mov     eax, ecx
0x18002c1e0  cmovg   eax, edx
0x18002c1e3  lea     rdx, ?g_strMsmSecState@@3PAPEAGA; ushort * near * g_strMsmSecState
0x18002c1ea  cdqe
0x18002c1ec  mov     rax, [rdx+rax*8]
0x18002c1f0  mov     qword ptr [rsp+0C8h+var_88], rax
0x18002c1f5  mov     eax, [r15+1Ch]
0x18002c1f9  mov     dword ptr [rsp+0C8h+var_90], ecx
0x18002c1fd  mov     rcx, [r12+0D8h]
0x18002c205  mov     [rsp+0C8h+var_98], eax
0x18002c209  mov     eax, [r15+18h]
0x18002c20d  mov     dword ptr [rsp+0C8h+var_A0], eax
0x18002c211  mov     eax, [r15+10h]
0x18002c215  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18002c219  call    WPP_SF_dDDDdS
0x18002c21e  mov     r12, cs:WPP_GLOBAL_Control
0x18002c225  cmp     r12, r14
0x18002c228  jz      loc_18002C01F
0x18002c22e  cmp     byte ptr [r12+0E1h], 3
0x18002c237  jb      loc_18002C01F
0x18002c23d  test    byte ptr [r12+0E4h], 4
0x18002c246  jz      loc_18002C01F
0x18002c24c  movzx   ecx, byte ptr [r15+4]
0x18002c251  movzx   eax, byte ptr [r15+5]
0x18002c256  movzx   r8d, byte ptr [r15+3]
0x18002c25b  movzx   r10d, byte ptr [r15+2]
0x18002c260  movzx   r11d, byte ptr [r15+1]
0x18002c265  movzx   ebx, byte ptr [r15]
0x18002c269  mov     rdx, [rsp+0C8h+arg_18]
0x18002c271  movzx   edi, byte ptr [r15+0Bh]
0x18002c276  movzx   esi, byte ptr [r15+0Ah]
0x18002c27b  movzx   ebp, byte ptr [r15+9]
0x18002c280  movzx   r14d, byte ptr [r15+8]
0x18002c285  movzx   r15d, byte ptr [r15+7]
0x18002c28a  movzx   r9d, byte ptr [rdx+6]
0x18002c28f  mov     edx, 4Ch ; 'L'
0x18002c294  mov     [rsp+0C8h+var_58], eax
0x18002c298  mov     [rsp+0C8h+var_60], ecx
0x18002c29c  mov     rcx, [r12+0D8h]
0x18002c2a4  mov     [rsp+0C8h+var_68], r8d
0x18002c2a9  mov     [rsp+0C8h+var_70], r10d
0x18002c2ae  mov     dword ptr [rsp+0C8h+var_78], r11d
0x18002c2b3  mov     dword ptr [rsp+0C8h+var_80], ebx
0x18002c2b7  mov     dword ptr [rsp+0C8h+var_88], edi
0x18002c2bb  mov     dword ptr [rsp+0C8h+var_90], esi
0x18002c2bf  mov     [rsp+0C8h+var_98], ebp
0x18002c2c3  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x18002c2c8  mov     dword ptr [rsp+0C8h+var_A8], r15d
0x18002c2cd  call    WPP_SF_DDDDDDDDDDDD
0x18002c2d2  mov     r12, cs:WPP_GLOBAL_Control
0x18002c2d9  lea     r14, WPP_GLOBAL_Control
0x18002c2e0  mov     r15, [rsp+0C8h+arg_18]
0x18002c2e8  jmp     loc_18002C01F
0x18002c2ed  test    dword ptr [rcx+0E4h], 200h
0x18002c2f7  jz      loc_18002BE9C
0x18002c2fd  mov     rcx, [rcx+0D8h]
0x18002c304  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002c30b  mov     edx, 46h ; 'F'
0x18002c310  call    WPP_SF_
0x18002c315  jmp     loc_18002BE9C
0x18002c31a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c321  cmp     rcx, r13
0x18002c324  jz      loc_18002BEED
0x18002c32a  cmp     byte ptr [rcx+0E1h], 1
0x18002c331  jb      loc_18002BEED
0x18002c337  test    byte ptr [rcx+0E4h], 40h
0x18002c33e  jz      loc_18002BEED
0x18002c344  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002c34b  mov     r9, r12
0x18002c34e  mov     dword ptr [rsp+0C8h+var_78], 65Ch; char
0x18002c356  mov     [rsp+0C8h+var_80], rax; __int64
0x18002c35b  mov     eax, [rbx+6Ch]
0x18002c35e  mov     dword ptr [rsp+0C8h+var_88], edi; char
0x18002c362  mov     dword ptr [rsp+0C8h+var_90], eax; char
0x18002c366  mov     rax, [rbx+70h]
0x18002c36a  mov     qword ptr [rsp+0C8h+var_98], rax; __int64
0x18002c36f  mov     eax, [rbx+68h]
0x18002c372  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x18002c376  mov     qword ptr [rsp+0C8h+var_A8], rbx; char
0x18002c37b  call    WPP_SF_qqdsddsd
0x18002c380  lea     rax, aWdiagsecurityn; "WDiagSecurityNotification"
0x18002c387  jmp     loc_18002BEED
0x18002c38c  mov     r9d, 665h; unsigned int
0x18002c392  lea     r8, aWdiagsecurityn; "WDiagSecurityNotification"
0x18002c399  mov     rdx, rbx; struct _WDIAG_RW_LOCK *
0x18002c39c  mov     rcx, r12; void *
0x18002c39f  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002c3a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3ab  lea     r14, WPP_GLOBAL_Control
0x18002c3b2  cmp     rcx, r14
0x18002c3b5  jz      short loc_18002C3E8
0x18002c3b7  cmp     byte ptr [rcx+0E1h], 1
0x18002c3be  jb      short loc_18002C3E8
0x18002c3c0  test    byte ptr [rcx+0E4h], 10h
0x18002c3c7  jz      short loc_18002C3E8
0x18002c3c9  mov     rcx, [rcx+0D8h]
0x18002c3d0  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002c3d7  mov     edx, 47h ; 'G'
0x18002c3dc  call    WPP_SF_
0x18002c3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3e8  mov     esi, 490h
0x18002c3ed  jmp     loc_18002C0B1
0x18002c3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3f9  lea     r12, WPP_GLOBAL_Control
0x18002c400  cmp     rcx, r12
0x18002c403  jz      loc_18002BF68
0x18002c409  cmp     byte ptr [rcx+0E1h], 1
0x18002c410  jb      loc_18002BF68
0x18002c416  test    byte ptr [rcx+0E4h], 40h
0x18002c41d  jz      loc_18002BF68
0x18002c423  mov     eax, [rdi+6Ch]
0x18002c426  lea     rdx, aWdiagsecurityn; "WDiagSecurityNotification"
0x18002c42d  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002c434  mov     r9, r13
0x18002c437  mov     dword ptr [rsp+0C8h+var_78], 66Dh; char
0x18002c43f  mov     [rsp+0C8h+var_80], rdx; __int64
0x18002c444  mov     dword ptr [rsp+0C8h+var_88], esi; char
0x18002c448  mov     dword ptr [rsp+0C8h+var_90], eax; char
0x18002c44c  mov     rax, [rdi+70h]
  ... truncated ...
```
