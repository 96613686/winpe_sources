# HNIntStartUsing(_HN_CLIENT_CONTEXT * *,ulong *)

- ea: `0x18015a78c`
- end: `0x18015a9ed`
- name: `?HNIntStartUsing@@YAKPEAPEAU_HN_CLIENT_CONTEXT@@PEAK@Z`
- size: `609`
- prototype: `unsigned int(struct _HN_CLIENT_CONTEXT **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800f01a4`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180085c14`
- `0x1800c6774`
- `0x180159350`
- `0x18015a78c`
- `0x18015ad20`
- `0x18015ee58`
- `0x1801bd84c`
- `0x1801d78c8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18015a898`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18015a898`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015a88d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015a986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015a88d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015a986`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015a7fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015a8a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015a7fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015a8a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a819`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a8c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a819`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a8c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015a803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015a8ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015a803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015a8ab`

## pseudocode

```c
__int64 __fastcall HNIntStartUsing(struct _HN_CLIENT_CONTEXT **a1, unsigned int *a2)
{
  struct _HN_CLIENT_CONTEXT *v2; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int updated; // ebx
  __int64 v8; // r8
  int v9; // ebx
  unsigned int HNStartResult; // eax
  char v12; // [rsp+80h] [rbp+8h] BYREF
  void *v13; // [rsp+90h] [rbp+18h] BYREF

  v2 = *a1;
  v12 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, &WPP_2595c600eb193998e02ecaaebdc12d46_Traceguids);
  }
  VlibNotifySoftAPFirstUsed(&v12);
  EnterCriticalSection(&g_HNMgrContext);
  dword_1802A2F18 = GetCurrentThreadId();
  WaitForSingleObject(hHandle, 0xFFFFFFFF);
  if ( !v2 )
  {
    updated = HNIntClientContextInit(a2, &v13);
    if ( updated )
      goto LABEL_25;
    v2 = (struct _HN_CLIENT_CONTEXT *)v13;
    if ( !v13 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v8);
    *a1 = v2;
  }
  v9 = 50;
  while ( *(&xmmword_1802A30A8 + 2) )
  {
    if ( !v12 || xmmword_1802A30A8 || !v9 )
    {
      if ( *(&xmmword_1802A30A8 + 2) && xmmword_1802A30A8 )
      {
        updated = HNIntUpdateDefaultSSID(a2);
        if ( !updated )
        {
          updated = HNIntChangeStatus(a2, 0x11u, 0, 0, 0, 0, 0, 1, 1u, 1, 0);
          if ( !updated )
            ++*(_DWORD *)v2;
        }
        goto LABEL_25;
      }
      break;
    }
    dword_1802A2F18 = xmmword_1802A30A8;
    --v9;
    LeaveCriticalSection(&g_HNMgrContext);
    Sleep(0x64u);
    EnterCriticalSection(&g_HNMgrContext);
    dword_1802A2F18 = GetCurrentThreadId();
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
  }
  *a2 = 12;
  updated = 5023;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 41, &WPP_2595c600eb193998e02ecaaebdc12d46_Traceguids, 5023);
  }
LABEL_25:
  dword_1802A2F18 = 0;
  LeaveCriticalSection(&g_HNMgrContext);
  if ( dword_1802A354C )
  {
    HNStartResult = HNUtilsSqmGetHNStartResult(updated, *a2);
    WlanAcmSqmHostedNetworkStart(HNStartResult);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, &WPP_2595c600eb193998e02ecaaebdc12d46_Traceguids, updated);
  }
  return updated;
}

```

## disassembly

```asm
0x18015a78c  mov     rax, rsp
0x18015a78f  mov     [rax+10h], rbx
0x18015a793  mov     [rax+20h], rsi
0x18015a797  push    rdi
0x18015a798  push    r12
0x18015a79a  push    r14
0x18015a79c  sub     rsp, 60h
0x18015a7a0  mov     rdi, [rcx]
0x18015a7a3  mov     rsi, rdx
0x18015a7a6  mov     r14, rcx
0x18015a7a9  mov     byte ptr [rax+8], 0
0x18015a7ad  mov     qword ptr [rax+18h], 0
0x18015a7b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18015a7bc  lea     r12, WPP_GLOBAL_Control
0x18015a7c3  cmp     rcx, r12
0x18015a7c6  jz      short loc_18015A7E9
0x18015a7c8  cmp     byte ptr [rcx+69h], 4
0x18015a7cc  jb      short loc_18015A7E9
0x18015a7ce  test    byte ptr [rcx+6Ch], 1
0x18015a7d2  jz      short loc_18015A7E9
0x18015a7d4  mov     rcx, [rcx+60h]
0x18015a7d8  lea     r8, WPP_2595c600eb193998e02ecaaebdc12d46_Traceguids
0x18015a7df  mov     edx, 28h ; '('
0x18015a7e4  call    WPP_SF_
0x18015a7e9  lea     rcx, [rsp+78h+arg_0]
0x18015a7f1  call    VlibNotifySoftAPFirstUsed
0x18015a7f6  lea     rcx, ?g_HNMgrContext@@3U_HN_MGR_CONTEXT@@A; lpCriticalSection
0x18015a7fd  call    cs:__imp_EnterCriticalSection
0x18015a803  call    cs:__imp_GetCurrentThreadId
0x18015a809  mov     rcx, cs:hHandle; hHandle
0x18015a810  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18015a813  mov     cs:dword_1802A2F18, eax
0x18015a819  call    cs:__imp_WaitForSingleObject
0x18015a81f  test    rdi, rdi
0x18015a822  jnz     short loc_18015A853
0x18015a824  lea     rdx, [rsp+78h+arg_10]; void **
0x18015a82c  mov     rcx, rsi; unsigned int *
0x18015a82f  call    ?HNIntClientContextInit@@YAKPEAKPEAPEAX@Z; HNIntClientContextInit(ulong *,void * *)
0x18015a834  mov     ebx, eax
0x18015a836  test    eax, eax
0x18015a838  jnz     loc_18015A975
0x18015a83e  mov     rdi, [rsp+78h+arg_10]
0x18015a846  test    rdi, rdi
0x18015a849  jnz     short loc_18015A850
0x18015a84b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hNewCtxt")
0x18015a850  mov     [r14], rdi
0x18015a853  mov     ebx, 32h ; '2'
0x18015a858  mov     ecx, dword ptr cs:xmmword_1802A30A8+8
0x18015a85e  mov     eax, dword ptr cs:xmmword_1802A30A8
0x18015a864  test    ecx, ecx
0x18015a866  jz      loc_18015A93A
0x18015a86c  cmp     [rsp+78h+arg_0], 0
0x18015a874  jz      short loc_18015A8C9
0x18015a876  test    eax, eax
0x18015a878  jnz     short loc_18015A8C9
0x18015a87a  test    ebx, ebx
0x18015a87c  jz      short loc_18015A8C9
0x18015a87e  lea     rcx, ?g_HNMgrContext@@3U_HN_MGR_CONTEXT@@A; lpCriticalSection
0x18015a885  mov     cs:dword_1802A2F18, eax
0x18015a88b  dec     ebx
0x18015a88d  call    cs:__imp_LeaveCriticalSection
0x18015a893  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18015a898  call    cs:__imp_Sleep
0x18015a89e  lea     rcx, ?g_HNMgrContext@@3U_HN_MGR_CONTEXT@@A; lpCriticalSection
0x18015a8a5  call    cs:__imp_EnterCriticalSection
0x18015a8ab  call    cs:__imp_GetCurrentThreadId
0x18015a8b1  mov     rcx, cs:hHandle; hHandle
0x18015a8b8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18015a8bb  mov     cs:dword_1802A2F18, eax
0x18015a8c1  call    cs:__imp_WaitForSingleObject
0x18015a8c7  jmp     short loc_18015A858
0x18015a8c9  test    ecx, ecx
0x18015a8cb  jz      short loc_18015A93A
0x18015a8cd  test    eax, eax
0x18015a8cf  jz      short loc_18015A93A
0x18015a8d1  mov     rcx, rsi; unsigned int *
0x18015a8d4  call    ?HNIntUpdateDefaultSSID@@YAKPEAK@Z; HNIntUpdateDefaultSSID(ulong *)
0x18015a8d9  mov     ebx, eax
0x18015a8db  test    eax, eax
0x18015a8dd  jnz     loc_18015A975
0x18015a8e3  mov     [rsp+78h+var_28], 0; void *
0x18015a8ec  lea     edx, [rax+11h]; unsigned int
0x18015a8ef  mov     [rsp+78h+var_30], 1; int
0x18015a8f7  xor     r9d, r9d; struct _GUID *
0x18015a8fa  mov     [rsp+78h+var_38], 1; unsigned int
0x18015a902  xor     r8d, r8d; struct _GUID *
0x18015a905  mov     [rsp+78h+var_40], 1; int
0x18015a90d  mov     rcx, rsi; unsigned int *
0x18015a910  mov     [rsp+78h+var_48], 0; struct _GUID *
0x18015a919  mov     [rsp+78h+var_50], 0; struct _GUID *
0x18015a922  mov     [rsp+78h+var_58], 0; struct _GUID *
0x18015a92b  call    ?HNIntChangeStatus@@YAKPEAKKPEAU_GUID@@1111HKHPEAX@Z; HNIntChangeStatus(ulong *,ulong,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *,int,ulong,int,void *)
0x18015a930  mov     ebx, eax
0x18015a932  test    eax, eax
0x18015a934  jnz     short loc_18015A975
0x18015a936  inc     dword ptr [rdi]
0x18015a938  jmp     short loc_18015A975
0x18015a93a  mov     dword ptr [rsi], 0Ch
0x18015a940  mov     ebx, 139Fh
0x18015a945  mov     rcx, cs:WPP_GLOBAL_Control
0x18015a94c  cmp     rcx, r12
0x18015a94f  jz      short loc_18015A975
0x18015a951  cmp     byte ptr [rcx+69h], 1
0x18015a955  jb      short loc_18015A975
0x18015a957  test    byte ptr [rcx+6Ch], 1
0x18015a95b  jz      short loc_18015A975
0x18015a95d  mov     rcx, [rcx+60h]
0x18015a961  lea     r8, WPP_2595c600eb193998e02ecaaebdc12d46_Traceguids
0x18015a968  mov     edx, 29h ; ')'
0x18015a96d  mov     r9d, ebx
0x18015a970  call    WPP_SF_d
0x18015a975  lea     rcx, ?g_HNMgrContext@@3U_HN_MGR_CONTEXT@@A; lpCriticalSection
0x18015a97c  mov     cs:dword_1802A2F18, 0
0x18015a986  call    cs:__imp_LeaveCriticalSection
0x18015a98c  cmp     cs:dword_1802A354C, 0
0x18015a993  jz      short loc_18015A9A5
0x18015a995  mov     edx, [rsi]
0x18015a997  mov     ecx, ebx
0x18015a999  call    ?HNUtilsSqmGetHNStartResult@@YA?AW4_WLAN_ACM_SQM_HOSTED_NETWORK_START_RESULT@@KK@Z; HNUtilsSqmGetHNStartResult(ulong,ulong)
0x18015a99e  mov     ecx, eax
0x18015a9a0  call    WlanAcmSqmHostedNetworkStart
0x18015a9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18015a9ac  cmp     rcx, r12
0x18015a9af  jz      short loc_18015A9D5
0x18015a9b1  cmp     byte ptr [rcx+69h], 4
0x18015a9b5  jb      short loc_18015A9D5
0x18015a9b7  test    byte ptr [rcx+6Ch], 1
0x18015a9bb  jz      short loc_18015A9D5
0x18015a9bd  mov     rcx, [rcx+60h]
0x18015a9c1  lea     r8, WPP_2595c600eb193998e02ecaaebdc12d46_Traceguids
0x18015a9c8  mov     edx, 2Ah ; '*'
0x18015a9cd  mov     r9d, ebx
0x18015a9d0  call    WPP_SF_d
0x18015a9d5  lea     r11, [rsp+78h+var_18]
0x18015a9da  mov     eax, ebx
0x18015a9dc  mov     rbx, [r11+28h]
0x18015a9e0  mov     rsi, [r11+38h]
0x18015a9e4  mov     rsp, r11
0x18015a9e7  pop     r14
0x18015a9e9  pop     r12
0x18015a9eb  pop     rdi
0x18015a9ec  retn
```
