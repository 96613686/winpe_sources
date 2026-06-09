# ScStartOObeServices(int *)

- ea: `0x14003a2f4`
- end: `0x14003a68f`
- name: `?ScStartOObeServices@@YAKPEAH@Z`
- size: `923`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140039bd4`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140007130`
- `0x140011ba0`
- `0x14001761c`
- `0x14001f99c`
- `0x14001f9c4`
- `0x14002303c`
- `0x140038698`
- `0x14003a2f4`
- `0x140041778`
- `0x1400430b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003a572`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003a572`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003a5c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003a5c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003a3c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003a421`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003a3c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003a421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a57c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a66d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a66d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a5b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a5e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a5b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a5e3`

## pseudocode

```c
__int64 __fastcall ScStartOObeServices(int *a1)
{
  HANDLE EventW; // r15
  __int64 v3; // r8
  unsigned int v4; // eax
  HANDLE v5; // rdi
  DWORD v6; // eax
  DWORD v7; // ebx
  PRPC_ASYNC_STATE v8; // rcx
  __int64 v9; // rdx
  __int64 i; // rbx
  unsigned __int64 v11; // rax
  unsigned int NamedServiceRecord; // eax
  unsigned int v13; // esi
  int started; // eax
  DWORD LastError; // eax
  ULONGLONG TickCount64; // rsi
  ULONGLONG v17; // rax
  __int64 v19; // [rsp+60h] [rbp+30h] BYREF
  struct CServiceRecord *v20; // [rsp+68h] [rbp+38h] BYREF
  HANDLE hEvent; // [rsp+70h] [rbp+40h]

  LODWORD(v19) = 0;
  EventW = 0;
  v20 = 0;
  *a1 = SetupInProgress(0, &v19);
  if ( !(_DWORD)v19 )
  {
    v7 = 0;
    v5 = 0;
    goto LABEL_42;
  }
  v4 = dword_1400BA2A0;
  *a1 = 1;
  if ( v4 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x200000000000LL, v3) )
  {
    hEvent = (HANDLE)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>();
  }
  ScUpdateAndPublishScmGlobalState(0x10u);
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 96, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, (unsigned int)v19);
  hEvent = CreateEventW(0, 1, 0, L"Global\\OOBE_PNP_DONE");
  v5 = hEvent;
  if ( hEvent )
  {
    EventW = CreateEventW(0, 1, 0, L"Global\\OOBE_MACHINE_NAME_DONE");
    if ( EventW )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 99, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v11 = 2;
        if ( (_DWORD)v19 != 2 )
          v11 = 9;
        if ( (unsigned int)i >= v11 )
          break;
        Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v20);
        NamedServiceRecord = ScGetNamedServiceRecord((wchar_t *)(&s_pszServicesForOobe)[i], &v20);
        v13 = NamedServiceRecord;
        if ( !NamedServiceRecord )
          goto LABEL_29;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            100,
            (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
            (unsigned int)(&s_pszServicesForOobe)[i],
            NamedServiceRecord);
        }
        if ( v13 != 1060 )
        {
LABEL_29:
          started = ScStartServiceAndDependencies(v20, 0, 0, 0, 1u, 0);
          if ( started
            && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              101,
              (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
              (unsigned int)(&s_pszServicesForOobe)[i],
              started);
          }
        }
      }
      v5 = hEvent;
      if ( !SetEvent(hEvent) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 102, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, LastError);
        }
      }
      TickCount64 = GetTickCount64();
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      v7 = 0;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      {
        v17 = GetTickCount64();
        WPP_SF_q(WPP_GLOBAL_Control->StubInfo, 103, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v17 - TickCount64);
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v9 = 98;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v9 = 97;
LABEL_12:
      WPP_SF_d(v8->StubInfo, v9, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v6);
    }
  }
LABEL_42:
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x200000000000LL, v3) )
  {
    v19 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>();
  }
  if ( v5 )
    CloseHandle(v5);
  if ( EventW )
    CloseHandle(EventW);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v20);
  return v7;
}

```

## disassembly

```asm
0x14003a2f4  mov     [rsp-28h+arg_18], rbx
0x14003a2f9  push    rbp
0x14003a2fa  push    rsi
0x14003a2fb  push    rdi
0x14003a2fc  push    r14
0x14003a2fe  push    r15
0x14003a300  mov     rbp, rsp
0x14003a303  sub     rsp, 30h
0x14003a307  mov     rbx, rcx
0x14003a30a  mov     dword ptr [rbp+arg_0], 0
0x14003a311  xor     r15d, r15d
0x14003a314  lea     rdx, [rbp+arg_0]
0x14003a318  xor     ecx, ecx
0x14003a31a  mov     [rbp+arg_8], r15
0x14003a31e  call    SetupInProgress
0x14003a323  mov     [rbx], eax
0x14003a325  cmp     dword ptr [rbp+arg_0], r15d
0x14003a329  jz      loc_14003A60B
0x14003a32f  mov     eax, cs:dword_1400BA2A0
0x14003a335  lea     esi, [r15+1]
0x14003a339  mov     [rbx], esi
0x14003a33b  cmp     eax, 5
0x14003a33e  jbe     short loc_14003A37D
0x14003a340  mov     rdx, 200000000000h
0x14003a34a  lea     rcx, dword_1400BA2A0
0x14003a351  call    _tlgKeywordOn
0x14003a356  test    al, al
0x14003a358  jz      short loc_14003A37D
0x14003a35a  lea     rax, [rbp+hEvent]
0x14003a35e  mov     [rbp+hEvent], 1000000h
0x14003a366  xor     r9d, r9d
0x14003a369  mov     qword ptr [rsp+30h+var_10], rax
0x14003a36e  xor     r8d, r8d
0x14003a371  lea     rdx, word_1400AEB9A
0x14003a378  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x14003a37d  mov     cl, 10h; unsigned __int8
0x14003a37f  call    ?ScUpdateAndPublishScmGlobalState@@YAXE@Z; ScUpdateAndPublishScmGlobalState(uchar)
0x14003a384  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a38b  lea     r14, WPP_GLOBAL_Control
0x14003a392  cmp     rcx, r14
0x14003a395  jz      short loc_14003A3B6
0x14003a397  test    byte ptr [rcx+1Ch], 4
0x14003a39b  jz      short loc_14003A3B6
0x14003a39d  mov     r9d, dword ptr [rbp+arg_0]
0x14003a3a1  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003a3a8  mov     rcx, [rcx+10h]
0x14003a3ac  mov     edx, 60h ; '`'
0x14003a3b1  call    WPP_SF_d
0x14003a3b6  lea     r9, aGlobalOobePnpD; "Global\\OOBE_PNP_DONE"
0x14003a3bd  xor     r8d, r8d; bInitialState
0x14003a3c0  mov     edx, esi; bManualReset
0x14003a3c2  xor     ecx, ecx; lpEventAttributes
0x14003a3c4  call    cs:__imp_CreateEventW
0x14003a3ca  mov     [rbp+hEvent], rax
0x14003a3ce  mov     rdi, rax
0x14003a3d1  test    rax, rax
0x14003a3d4  jnz     short loc_14003A413
0x14003a3d6  call    cs:__imp_GetLastError
0x14003a3dc  mov     ebx, eax
0x14003a3de  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a3e5  cmp     rcx, r14
0x14003a3e8  jz      loc_14003A60F
0x14003a3ee  test    [rcx+1Ch], sil
0x14003a3f2  jz      loc_14003A60F
0x14003a3f8  lea     edx, [rdi+61h]
0x14003a3fb  mov     rcx, [rcx+10h]
0x14003a3ff  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003a406  mov     r9d, eax
0x14003a409  call    WPP_SF_d
0x14003a40e  jmp     loc_14003A60F
0x14003a413  lea     r9, aGlobalOobeMach; "Global\\OOBE_MACHINE_NAME_DONE"
0x14003a41a  xor     r8d, r8d; bInitialState
0x14003a41d  mov     edx, esi; bManualReset
0x14003a41f  xor     ecx, ecx; lpEventAttributes
0x14003a421  call    cs:__imp_CreateEventW
0x14003a427  mov     r15, rax
0x14003a42a  test    rax, rax
0x14003a42d  jnz     short loc_14003A457
0x14003a42f  call    cs:__imp_GetLastError
0x14003a435  mov     ebx, eax
0x14003a437  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a43e  cmp     rcx, r14
0x14003a441  jz      loc_14003A60F
0x14003a447  test    [rcx+1Ch], sil
0x14003a44b  jz      loc_14003A60F
0x14003a451  lea     edx, [r15+62h]
0x14003a455  jmp     short loc_14003A3FB
0x14003a457  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a45e  cmp     rcx, r14
0x14003a461  jz      short loc_14003A47E
0x14003a463  test    byte ptr [rcx+1Ch], 4
0x14003a467  jz      short loc_14003A47E
0x14003a469  mov     rcx, [rcx+10h]
0x14003a46d  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003a474  mov     edx, 63h ; 'c'
0x14003a479  call    WPP_SF_
0x14003a47e  xor     ebx, ebx
0x14003a480  lea     rdi, WPP_GLOBAL_Control
0x14003a487  mov     eax, 2
0x14003a48c  mov     r14d, ebx
0x14003a48f  cmp     dword ptr [rbp+arg_0], eax
0x14003a492  lea     ecx, [rax+7]
0x14003a495  cmovnz  eax, ecx
0x14003a498  cmp     r14, rax
0x14003a49b  jnb     loc_14003A56B
0x14003a4a1  lea     rcx, [rbp+arg_8]
0x14003a4a5  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x14003a4aa  lea     rax, ?s_pszServicesForOobe@@3PAPEBGA; ushort const * near * s_pszServicesForOobe
0x14003a4b1  mov     rcx, [rax+rbx*8]; String2
0x14003a4b5  lea     rdx, [rbp+arg_8]; struct CServiceRecord **
0x14003a4b9  call    ?ScGetNamedServiceRecord@@YAKPEBGPEAPEAVCServiceRecord@@@Z; ScGetNamedServiceRecord(ushort const *,CServiceRecord * *)
0x14003a4be  mov     esi, eax
0x14003a4c0  test    eax, eax
0x14003a4c2  jz      short loc_14003A502
0x14003a4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a4cb  cmp     rcx, rdi
0x14003a4ce  jz      short loc_14003A4FA
0x14003a4d0  test    byte ptr [rcx+1Ch], 1
0x14003a4d4  jz      short loc_14003A4FA
0x14003a4d6  mov     rcx, [rcx+10h]
0x14003a4da  lea     r9, ?s_pszServicesForOobe@@3PAPEBGA; ushort const * near * s_pszServicesForOobe
0x14003a4e1  mov     r9, [r9+rbx*8]
0x14003a4e5  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003a4ec  mov     edx, 64h ; 'd'
0x14003a4f1  mov     [rsp+30h+var_10], eax
0x14003a4f5  call    WPP_SF_Sd
0x14003a4fa  cmp     esi, 424h
0x14003a500  jz      short loc_14003A55F
0x14003a502  mov     rcx, [rbp+arg_8]; this
0x14003a506  mov     esi, 1
0x14003a50b  mov     [rsp+30h+var_8], 0; struct CServiceRecord *
0x14003a514  xor     r9d, r9d; unsigned int
0x14003a517  xor     r8d, r8d; struct _STRING_PTRSW *
0x14003a51a  mov     [rsp+30h+var_10], esi; unsigned int
0x14003a51e  xor     edx, edx; unsigned int
0x14003a520  call    ?ScStartServiceAndDependencies@@YAKPEAVCServiceRecord@@KPEAU_STRING_PTRSW@@KK0@Z; ScStartServiceAndDependencies(CServiceRecord *,ulong,_STRING_PTRSW *,ulong,ulong,CServiceRecord *)
0x14003a525  test    eax, eax
0x14003a527  jz      short loc_14003A564
0x14003a529  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a530  cmp     rcx, rdi
0x14003a533  jz      short loc_14003A564
0x14003a535  test    [rcx+1Ch], sil
0x14003a539  jz      short loc_14003A564
0x14003a53b  mov     rcx, [rcx+10h]
0x14003a53f  lea     edx, [rsi+64h]
0x14003a542  mov     [rsp+30h+var_10], eax
0x14003a546  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003a54d  lea     rax, ?s_pszServicesForOobe@@3PAPEBGA; ushort const * near * s_pszServicesForOobe
0x14003a554  mov     r9, [rax+rbx*8]
0x14003a558  call    WPP_SF_Sd
0x14003a55d  jmp     short loc_14003A564
0x14003a55f  mov     esi, 1
0x14003a564  add     ebx, esi
0x14003a566  jmp     loc_14003A487
0x14003a56b  mov     rdi, [rbp+hEvent]
0x14003a56f  mov     rcx, rdi; hEvent
0x14003a572  call    cs:__imp_SetEvent
0x14003a578  test    eax, eax
0x14003a57a  jnz     short loc_14003A5B3
0x14003a57c  call    cs:__imp_GetLastError
0x14003a582  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a589  lea     rdx, WPP_GLOBAL_Control
0x14003a590  cmp     rcx, rdx
0x14003a593  jz      short loc_14003A5B3
0x14003a595  test    [rcx+1Ch], sil
0x14003a599  jz      short loc_14003A5B3
0x14003a59b  mov     rcx, [rcx+10h]
0x14003a59f  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003a5a6  mov     edx, 66h ; 'f'
0x14003a5ab  mov     r9d, eax
0x14003a5ae  call    WPP_SF_d
0x14003a5b3  call    cs:__imp_GetTickCount64
0x14003a5b9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003a5bc  mov     rcx, r15; hHandle
0x14003a5bf  mov     rsi, rax
0x14003a5c2  call    cs:__imp_WaitForSingleObject
0x14003a5c8  xor     ebx, ebx
0x14003a5ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a5d1  lea     rax, WPP_GLOBAL_Control
0x14003a5d8  cmp     rcx, rax
0x14003a5db  jz      short loc_14003A60F
0x14003a5dd  test    byte ptr [rcx+1Ch], 4
0x14003a5e1  jz      short loc_14003A60F
0x14003a5e3  call    cs:__imp_GetTickCount64
0x14003a5e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a5f0  lea     edx, [rbx+67h]
0x14003a5f3  sub     rax, rsi
0x14003a5f6  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x14003a5fd  mov     r9, rax
0x14003a600  mov     rcx, [rcx+10h]
0x14003a604  call    WPP_SF_q
0x14003a609  jmp     short loc_14003A60F
0x14003a60b  xor     ebx, ebx
0x14003a60d  xor     edi, edi
0x14003a60f  mov     eax, cs:dword_1400BA2A0
0x14003a615  cmp     eax, 5
0x14003a618  jbe     short loc_14003A657
0x14003a61a  mov     rdx, 200000000000h
0x14003a624  lea     rcx, dword_1400BA2A0
0x14003a62b  call    _tlgKeywordOn
0x14003a630  test    al, al
0x14003a632  jz      short loc_14003A657
0x14003a634  lea     rax, [rbp+arg_0]
0x14003a638  mov     [rbp+arg_0], 1000000h
0x14003a640  xor     r9d, r9d
0x14003a643  mov     qword ptr [rsp+30h+var_10], rax
0x14003a648  xor     r8d, r8d
0x14003a64b  lea     rdx, byte_1400AEB67
0x14003a652  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x14003a657  test    rdi, rdi
0x14003a65a  jz      short loc_14003A665
0x14003a65c  mov     rcx, rdi; hObject
0x14003a65f  call    cs:__imp_CloseHandle
0x14003a665  test    r15, r15
0x14003a668  jz      short loc_14003A673
0x14003a66a  mov     rcx, r15; hObject
0x14003a66d  call    cs:__imp_CloseHandle
0x14003a673  lea     rcx, [rbp+arg_8]
0x14003a677  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x14003a67c  mov     eax, ebx
0x14003a67e  mov     rbx, [rsp+30h+arg_18]
0x14003a683  add     rsp, 30h
0x14003a687  pop     r15
0x14003a689  pop     r14
0x14003a68b  pop     rdi
0x14003a68c  pop     rsi
0x14003a68d  pop     rbp
0x14003a68e  retn
```
