# BaseClientNotifyHandler::InitializeNewHandler(__MIDL___MIDL_itf_unistore_0000_0000_0010 const *)

- ea: `0x1800231ac`
- end: `0x1800233ec`
- name: `?InitializeNewHandler@BaseClientNotifyHandler@@QEAAJPEBU__MIDL___MIDL_itf_unistore_0000_0000_0010@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(PVOID pv, const struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180022f30`
- `0x180023c30`

## callees

- `0x1800231ac`
- `0x1800233f4`
- `0x18002993c`
- `0x1800703c0`
- `0x1800ab230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800231c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800231c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023284`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023284`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002333a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002333a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002321b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002321b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180023376`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180023376`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800233da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800233da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800232f3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800232f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180023277`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180023277`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180023390`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180023390`
- `UserDataPlatformHelperUtil!SetPoolThreadBasePriority` at `0x18002335f`
- `UserDataPlatformHelperUtil!SetPoolThreadBasePriority` at `0x18002335f`

## pseudocode

```c
__int64 __fastcall BaseClientNotifyHandler::InitializeNewHandler(
        char *pv,
        const struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *a2)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // esi
  struct _TP_CALLBACK_ENVIRON_V3 *v7; // rsi
  struct _TP_POOL **v8; // r14
  struct _TP_CALLBACK_ENVIRON_V3 *v9; // r8
  PTP_WAIT *v10; // r14
  PTP_WAIT ThreadpoolWait; // rsi
  struct _LIST_ENTRY *v12; // rdx
  signed int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // edi
  __int64 v17; // r9
  PTP_POOL Threadpool; // rax
  signed int LastError; // eax
  signed int v20; // eax
  int v21; // eax
  __int64 v22; // r8
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  struct _TP_CLEANUP_GROUP *v24; // rcx
  PTP_CLEANUP_GROUP v25; // rsi
  struct _TP_POOL *v26; // rcx

  EnterCriticalSection(&g_clientNotifyLock);
  *((_DWORD *)pv + 17) = (*((_DWORD *)a2 + 1) & 0x20) == 0;
  *((_DWORD *)pv + 18) = *((_DWORD *)a2 + 4);
  if ( (*((_BYTE *)a2 + 4) & 0x10) != 0 )
  {
    Threadpool = CreateThreadpool(0);
    v8 = (struct _TP_POOL **)(pv + 152);
    tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),0>::reset(pv + 152, Threadpool);
    if ( !*((_QWORD *)pv + 19) )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      v17 = 121;
      goto LABEL_18;
    }
    v21 = SetPoolThreadBasePriority(*v8, -2);
    if ( v21 < 0 )
      Log_UnistoreHREvent_7((unsigned int)v21, 0, v22, 123);
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    v24 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)pv + 20);
    v25 = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup == v24 )
    {
      v25 = (PTP_CLEANUP_GROUP)*((_QWORD *)pv + 20);
    }
    else
    {
      if ( v24 )
        CloseThreadpoolCleanupGroup(v24);
      *((_QWORD *)pv + 20) = v25;
    }
    if ( !v25 )
    {
      v20 = GetLastError();
      v16 = v20;
      if ( v20 > 0 )
        v16 = (unsigned __int16)v20 | 0x80070000;
      v17 = 126;
      goto LABEL_18;
    }
    v7 = (struct _TP_CALLBACK_ENVIRON_V3 *)(pv + 80);
    *((_DWORD *)pv + 20) = 3;
    *((_QWORD *)pv + 14) = 0;
    *((_QWORD *)pv + 15) = 0;
    *((_QWORD *)pv + 16) = 0;
    *((_DWORD *)pv + 34) = 0;
    *((_DWORD *)pv + 35) = 1;
    *((_DWORD *)pv + 36) = 72;
    *((_QWORD *)pv + 12) = *((_QWORD *)pv + 20);
    *((_QWORD *)pv + 13) = 0;
    v26 = *v8;
    *((_QWORD *)pv + 11) = *v8;
    SetThreadpoolThreadMaximum(v26, 1u);
  }
  else
  {
    v4 = EnsureNotificationThreadPoolInitialized();
    v6 = v4;
    if ( v4 < 0 )
    {
      Log_UnistoreHREvent_7((unsigned int)v4, 1, v5, 137);
      v16 = v6;
LABEL_15:
      LeaveCriticalSection(&g_clientNotifyLock);
      return v16;
    }
    v7 = (struct _TP_CALLBACK_ENVIRON_V3 *)(pv + 80);
    v8 = (struct _TP_POOL **)(pv + 152);
  }
  v9 = (struct _TP_CALLBACK_ENVIRON_V3 *)&dword_18010D830;
  if ( *v8 )
    v9 = v7;
  v10 = (PTP_WAIT *)(pv + 32);
  ThreadpoolWait = CreateThreadpoolWait(BaseClientNotifyHandler::TpCallback, pv, v9);
  if ( ThreadpoolWait == *((PTP_WAIT *)pv + 4) )
  {
    ThreadpoolWait = *v10;
  }
  else
  {
    tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(pv + 32);
    *v10 = ThreadpoolWait;
  }
  if ( !ThreadpoolWait )
  {
    v14 = GetLastError();
    v16 = v14;
    if ( v14 > 0 )
      v16 = (unsigned __int16)v14 | 0x80070000;
    v17 = 144;
LABEL_18:
    Log_UnistoreHREvent_7(v16, 0, v15, v17);
    goto LABEL_15;
  }
  v12 = off_18010A0E8;
  if ( off_18010A0E8->Flink != &g_adviseList )
    __fastfail(3u);
  *((_QWORD *)pv + 6) = &g_adviseList;
  *((_QWORD *)pv + 7) = v12;
  v12->Flink = (struct _LIST_ENTRY *)(pv + 48);
  off_18010A0E8 = (struct _LIST_ENTRY *)(pv + 48);
  SetThreadpoolWait(*v10, *((HANDLE *)pv + 5), 0);
  LeaveCriticalSection(&g_clientNotifyLock);
  return 0;
}

```

## disassembly

```asm
0x1800231ac  push    rbx
0x1800231ae  push    rsi
0x1800231af  push    rdi
0x1800231b0  push    r14
0x1800231b2  sub     rsp, 38h
0x1800231b6  mov     rdi, rcx
0x1800231b9  mov     rbx, rdx
0x1800231bc  lea     rcx, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800231c3  call    cs:__imp_EnterCriticalSection
0x1800231c9  mov     eax, [rbx+4]
0x1800231cc  shr     eax, 5
0x1800231cf  not     eax
0x1800231d1  and     eax, 1
0x1800231d4  mov     [rdi+44h], eax
0x1800231d7  mov     eax, [rbx+10h]
0x1800231da  mov     [rdi+48h], eax
0x1800231dd  test    byte ptr [rbx+4], 10h
0x1800231e1  jnz     loc_1800232F1
0x1800231e7  call    ?EnsureNotificationThreadPoolInitialized@@YAJXZ; EnsureNotificationThreadPoolInitialized(void)
0x1800231ec  xor     ebx, ebx
0x1800231ee  mov     esi, eax
0x1800231f0  test    eax, eax
0x1800231f2  js      loc_1800232B3
0x1800231f8  lea     rsi, [rdi+50h]
0x1800231fc  lea     r14, [rdi+98h]
0x180023203  cmp     [r14], rbx
0x180023206  lea     r8, dword_18010D830
0x18002320d  mov     rdx, rdi; pv
0x180023210  lea     rcx, ?TpCallback@BaseClientNotifyHandler@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180023217  cmovnz  r8, rsi; pcbe
0x18002321b  call    cs:__imp_CreateThreadpoolWait
0x180023221  lea     r14, [rdi+20h]
0x180023225  mov     rsi, rax
0x180023228  cmp     rax, [r14]
0x18002322b  jz      loc_1800232D8
0x180023231  mov     rcx, r14
0x180023234  call    ?_Delete@?$auto_xxx@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(void)
0x180023239  mov     [r14], rsi
0x18002323c  test    rsi, rsi
0x18002323f  jz      short loc_180023296
0x180023241  mov     rdx, cs:off_18010A0E8
0x180023248  lea     r8, ?g_adviseList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_adviseList
0x18002324f  cmp     [rdx], r8
0x180023252  jnz     loc_1800233E5
0x180023258  lea     rax, [rdi+30h]
0x18002325c  mov     [rax], r8
0x18002325f  xor     r8d, r8d; pftTimeout
0x180023262  mov     [rax+8], rdx
0x180023266  mov     [rdx], rax
0x180023269  mov     cs:off_18010A0E8, rax
0x180023270  mov     rdx, [rdi+28h]; h
0x180023274  mov     rcx, [r14]; pwa
0x180023277  call    cs:__imp_SetThreadpoolWait
0x18002327d  lea     rcx, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180023284  call    cs:__imp_LeaveCriticalSection
0x18002328a  xor     eax, eax
0x18002328c  add     rsp, 38h
0x180023290  pop     r14
0x180023292  pop     rdi
0x180023293  pop     rsi
0x180023294  pop     rbx
0x180023295  retn
0x180023296  call    cs:__imp_GetLastError
0x18002329c  mov     edi, eax
0x18002329e  test    eax, eax
0x1800232a0  jle     short loc_1800232AB
0x1800232a2  movzx   edi, ax
0x1800232a5  or      edi, 80070000h
0x1800232ab  mov     r9d, 90h
0x1800232b1  jmp     short loc_1800232E6
0x1800232b3  mov     edx, 1
0x1800232b8  mov     r9d, 89h
0x1800232be  mov     ecx, esi
0x1800232c0  call    Log_UnistoreHREvent_7
0x1800232c5  mov     edi, esi
0x1800232c7  lea     rcx, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800232ce  call    cs:__imp_LeaveCriticalSection
0x1800232d4  mov     eax, edi
0x1800232d6  jmp     short loc_18002328C
0x1800232d8  mov     rsi, [r14]
0x1800232db  jmp     loc_18002323C
0x1800232e0  mov     r9d, 79h ; 'y'
0x1800232e6  xor     edx, edx
0x1800232e8  mov     ecx, edi
0x1800232ea  call    Log_UnistoreHREvent_7
0x1800232ef  jmp     short loc_1800232C7
0x1800232f1  xor     ecx, ecx; reserved
0x1800232f3  call    cs:__imp_CreateThreadpool
0x1800232f9  lea     r14, [rdi+98h]
0x180023300  mov     rdx, rax
0x180023303  mov     rcx, r14
0x180023306  call    ?reset@?$auto_xxx@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@Z$0A@@tlx@@QEAAXPEAU_TP_POOL@@@Z; tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),0>::reset(_TP_POOL *)
0x18002330b  xor     ebx, ebx
0x18002330d  cmp     [r14], rbx
0x180023310  jnz     short loc_180023357
0x180023312  call    cs:__imp_GetLastError
0x180023318  mov     edi, eax
0x18002331a  test    eax, eax
0x18002331c  jle     short loc_1800232E0
0x18002331e  movzx   edi, ax
0x180023321  or      edi, 80070000h
0x180023327  jmp     short loc_1800232E0
0x180023329  test    rcx, rcx
0x18002332c  jnz     short loc_180023390
0x18002332e  mov     [rdi+0A0h], rsi
0x180023335  test    rsi, rsi
0x180023338  jnz     short loc_180023398
0x18002333a  call    cs:__imp_GetLastError
0x180023340  mov     edi, eax
0x180023342  test    eax, eax
0x180023344  jle     short loc_18002334F
0x180023346  movzx   edi, ax
0x180023349  or      edi, 80070000h
0x18002334f  mov     r9d, 7Eh ; '~'
0x180023355  jmp     short loc_1800232E6
0x180023357  mov     rcx, [r14]
0x18002335a  mov     edx, 0FFFFFFFEh
0x18002335f  call    cs:__imp_?SetPoolThreadBasePriority@@YAJPEAU_TP_POOL@@J@Z; SetPoolThreadBasePriority(_TP_POOL *,long)
0x180023365  test    eax, eax
0x180023367  jns     short loc_180023376
0x180023369  xor     edx, edx
0x18002336b  mov     ecx, eax
0x18002336d  lea     r9d, [rdx+7Bh]
0x180023371  call    Log_UnistoreHREvent_7
0x180023376  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002337c  mov     rcx, [rdi+0A0h]; ptpcg
0x180023383  mov     rsi, rax
0x180023386  cmp     rax, rcx
0x180023389  jnz     short loc_180023329
0x18002338b  mov     rsi, rcx
0x18002338e  jmp     short loc_180023335
0x180023390  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180023396  jmp     short loc_18002332E
0x180023398  lea     rsi, [rdi+50h]
0x18002339c  mov     edx, 1; cthrdMost
0x1800233a1  mov     dword ptr [rsi], 3
0x1800233a7  mov     [rsi+20h], rbx
0x1800233ab  mov     [rsi+28h], rbx
0x1800233af  mov     [rsi+30h], rbx
0x1800233b3  mov     [rsi+38h], ebx
0x1800233b6  mov     dword ptr [rsi+3Ch], 1
0x1800233bd  mov     dword ptr [rsi+40h], 48h ; 'H'
0x1800233c4  mov     rax, [rdi+0A0h]
0x1800233cb  mov     [rdi+60h], rax
0x1800233cf  mov     [rdi+68h], rbx
0x1800233d3  mov     rcx, [r14]; ptpp
0x1800233d6  mov     [rdi+58h], rcx
0x1800233da  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800233e0  jmp     loc_180023203
0x1800233e5  mov     ecx, 3
0x1800233ea  int     29h; Win8: RtlFailFast(ecx)
```
