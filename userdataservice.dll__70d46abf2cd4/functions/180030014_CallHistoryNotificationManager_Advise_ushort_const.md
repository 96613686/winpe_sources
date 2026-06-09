# CallHistoryNotificationManager::Advise(ushort const *)

- ea: `0x180030014`
- end: `0x18003017a`
- name: `?Advise@CallHistoryNotificationManager@@QEAAJPEBG@Z`
- size: `358`
- prototype: `__int64 __fastcall(char *pv, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002ee80`

## callees

- `0x180030014`
- `0x180030180`
- `0x1800303cc`
- `0x18005f668`
- `0x18007f340`
- `0x180085ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030034`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030034`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003015d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003015d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030044`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003011d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003011d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003008b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003008b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180030148`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180030148`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180030102`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180030102`

## pseudocode

```c
__int64 __fastcall CallHistoryNotificationManager::Advise(char *pv, const unsigned __int16 *a2)
{
  __int64 v3; // r8
  void *v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // r9
  char *v7; // r14
  int v8; // eax
  struct UdmNotifyControl *v9; // r8
  __int64 v10; // rcx
  void *v11; // rax
  ServiceDataSession *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v17; // rcx
  signed int LastError; // eax
  _DWORD v20[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h]
  __int64 *v22; // [rsp+40h] [rbp-10h]
  HANDLE EventW; // [rsp+80h] [rbp+30h] BYREF
  __int64 v24; // [rsp+88h] [rbp+38h] BYREF

  v24 = (__int64)a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 8));
  EventW = CreateEventW(0, 0, 0, 0);
  v4 = EventW;
  if ( !EventW )
  {
    v5 = -2147467259;
    v6 = 58;
    goto LABEL_12;
  }
  v7 = pv + 48;
  v8 = CreateCallHistorySession(0, (struct CallHistoryDataSession **)pv + 6);
  v5 = v8;
  if ( v8 >= 0 )
  {
    v10 = *(_QWORD *)v7;
    v21 = 1;
    v20[0] = 1;
    v20[1] = 50;
    v11 = *(void **)(v10 + 72);
    *(_QWORD *)(v10 + 72) = v4;
    v12 = *(ServiceDataSession **)v7;
    EventW = v11;
    v22 = &v24;
    v24 = 0xF00000001LL;
    v13 = ServiceDataSession::ControlNotifies(v12, (const struct UdmNotifyControl *)v20, v9);
    v5 = v13;
    if ( v13 < 0 )
    {
      v14 = 1;
      v15 = (unsigned int)v13;
      v6 = 79;
LABEL_7:
      Log_HREvent_15(v15, v14, v3, v6);
LABEL_14:
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&EventW);
      goto LABEL_15;
    }
    ThreadpoolWait = CreateThreadpoolWait(CallHistoryNotificationManager::TpCallback, pv, 0);
    tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>::reset(
      pv + 56,
      ThreadpoolWait);
    v17 = (struct _TP_WAIT *)*((_QWORD *)pv + 7);
    if ( v17 )
    {
      SetThreadpoolWait(v17, *(HANDLE *)(*(_QWORD *)v7 + 72LL), 0);
      v5 = 0;
      goto LABEL_14;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = 85;
LABEL_12:
    v14 = 0;
    v15 = v5;
    goto LABEL_7;
  }
  Log_HREvent_15((unsigned int)v8, 1, v9, 60);
  CloseHandle(v4);
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 8));
  return v5;
}

```

## disassembly

```asm
0x180030014  mov     [rsp-28h+arg_10], rbx
0x180030019  mov     [rsp-28h+arg_8], rdx
0x18003001e  push    rbp
0x18003001f  push    rdi
0x180030020  push    r12
0x180030022  push    r14
0x180030024  push    r15
0x180030026  mov     rbp, rsp
0x180030029  sub     rsp, 50h
0x18003002d  mov     r15, rcx
0x180030030  add     rcx, 8; lpCriticalSection
0x180030034  call    cs:__imp_EnterCriticalSection
0x18003003a  xor     r9d, r9d; lpName
0x18003003d  xor     r8d, r8d; bInitialState
0x180030040  xor     edx, edx; bManualReset
0x180030042  xor     ecx, ecx; lpEventAttributes
0x180030044  call    cs:__imp_CreateEventW
0x18003004a  mov     [rbp+arg_0], rax
0x18003004e  mov     rbx, rax
0x180030051  test    rax, rax
0x180030054  jnz     short loc_180030064
0x180030056  mov     edi, 80004005h
0x18003005b  lea     r9d, [rax+3Ah]
0x18003005f  jmp     loc_180030138
0x180030064  lea     r14, [r15+30h]
0x180030068  xor     ecx, ecx
0x18003006a  mov     rdx, r14
0x18003006d  call    ?CreateCallHistorySession@@YAJUUdmCreateDataSessionControls@@PEAPEAVCallHistoryDataSession@@@Z; CreateCallHistorySession(UdmCreateDataSessionControls,CallHistoryDataSession * *)
0x180030072  mov     edi, eax
0x180030074  test    eax, eax
0x180030076  jns     short loc_180030096
0x180030078  mov     edx, 1
0x18003007d  mov     ecx, eax
0x18003007f  lea     r9d, [rdx+3Bh]
0x180030083  call    Log_HREvent_15
0x180030088  mov     rcx, rbx; hObject
0x18003008b  call    cs:__imp_CloseHandle
0x180030091  jmp     loc_180030159
0x180030096  mov     rcx, [r14]
0x180030099  lea     rdx, [rbp+var_20]; struct UdmNotifyControl *
0x18003009d  mov     [rbp+var_18], 1
0x1800300a5  mov     [rbp+var_20], 1
0x1800300ac  mov     [rbp+var_1C], 32h ; '2'
0x1800300b3  mov     rax, [rcx+48h]
0x1800300b7  mov     [rcx+48h], rbx
0x1800300bb  mov     rcx, [r14]; this
0x1800300be  mov     [rbp+arg_0], rax
0x1800300c2  lea     rax, [rbp+arg_8]
0x1800300c6  mov     [rbp+var_10], rax
0x1800300ca  mov     dword ptr [rbp+arg_8], 1
0x1800300d1  mov     dword ptr [rbp+arg_8+4], 0Fh
0x1800300d8  call    ?ControlNotifies@ServiceDataSession@@QEAAJAEBUUdmNotifyControl@@PEAU2@@Z; ServiceDataSession::ControlNotifies(UdmNotifyControl const &,UdmNotifyControl *)
0x1800300dd  mov     edi, eax
0x1800300df  test    eax, eax
0x1800300e1  jns     short loc_1800300F5
0x1800300e3  mov     edx, 1
0x1800300e8  mov     ecx, eax
0x1800300ea  lea     r9d, [rdx+4Eh]
0x1800300ee  call    Log_HREvent_15
0x1800300f3  jmp     short loc_180030150
0x1800300f5  xor     r8d, r8d; pcbe
0x1800300f8  lea     rcx, ?TpCallback@CallHistoryNotificationManager@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800300ff  mov     rdx, r15; pv
0x180030102  call    cs:__imp_CreateThreadpoolWait
0x180030108  mov     rdx, rax
0x18003010b  lea     rcx, [r15+38h]
0x18003010f  call    ?reset@?$auto_xxx@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@QEAAXPEAU_TP_WAIT@@@Z; tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>::reset(_TP_WAIT *)
0x180030114  mov     rcx, [r15+38h]; pwa
0x180030118  test    rcx, rcx
0x18003011b  jnz     short loc_18003013E
0x18003011d  call    cs:__imp_GetLastError
0x180030123  mov     edi, eax
0x180030125  test    eax, eax
0x180030127  jle     short loc_180030132
0x180030129  movzx   edi, ax
0x18003012c  or      edi, 80070000h
0x180030132  mov     r9d, 55h ; 'U'
0x180030138  xor     edx, edx
0x18003013a  mov     ecx, edi
0x18003013c  jmp     short loc_1800300EE
0x18003013e  mov     rdx, [r14]
0x180030141  xor     r8d, r8d; pftTimeout
0x180030144  mov     rdx, [rdx+48h]; h
0x180030148  call    cs:__imp_SetThreadpoolWait
0x18003014e  xor     edi, edi
0x180030150  lea     rcx, [rbp+arg_0]
0x180030154  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180030159  lea     rcx, [r15+8]; lpCriticalSection
0x18003015d  call    cs:__imp_LeaveCriticalSection
0x180030163  mov     rbx, [rsp+50h+arg_10]
0x18003016b  mov     eax, edi
0x18003016d  add     rsp, 50h
0x180030171  pop     r15
0x180030173  pop     r14
0x180030175  pop     r12
0x180030177  pop     rdi
0x180030178  pop     rbp
0x180030179  retn
```
