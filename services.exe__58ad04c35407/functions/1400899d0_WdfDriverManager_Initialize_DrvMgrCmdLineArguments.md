# WdfDriverManager::Initialize(DrvMgrCmdLineArguments *)

- ea: `0x1400899d0`
- end: `0x140089e9f`
- name: `?Initialize@WdfDriverManager@@QEAAKPEAVDrvMgrCmdLineArguments@@@Z`
- size: `1231`
- prototype: `unsigned int(WdfDriverManager *__hidden this, struct DrvMgrCmdLineArguments *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14008868c`

## callees

- `0x140001910`
- `0x140003e54`
- `0x140004c58`
- `0x14001b180`
- `0x14001f99c`
- `0x140038698`
- `0x140043490`
- `0x1400459ec`
- `0x1400575b0`
- `0x1400899d0`
- `0x14008a01c`
- `0x14008a910`
- `0x14008af2c`
- `0x14008b14c`
- `0x14008b6e8`
- `0x140091f24`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140089d9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140089d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089d1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140089c85`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140089c85`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140089ce6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140089ce6`
- `ntdll!RtlNtStatusToDosError` at `0x140089dce`
- `ntdll!RtlNtStatusToDosError` at `0x140089dce`
- `ntdll!DbgPrint` at `0x140089a53`
- `ntdll!DbgPrint` at `0x140089a53`
- `WUDFPlatform!WdfGetLpcInterface` at `0x140089bb0`
- `WUDFPlatform!WdfGetLpcInterface` at `0x140089bb0`

## pseudocode

```c
__int64 __fastcall WdfDriverManager::Initialize(WdfDriverManager *this, struct DrvMgrCmdLineArguments *a2)
{
  WdfDriverManager *v2; // rdi
  int LpcInterface; // ebx
  NTSTATUS v5; // ecx
  int started; // eax
  const struct std::nothrow_t *v7; // rdx
  __int64 v8; // rcx
  unsigned int RegistrySettings; // ebx
  __int64 v10; // r8
  void *v11; // rax
  void *v12; // rbx
  void *v13; // rax
  void *v14; // rbx
  void *v15; // rax
  void *v16; // rbx
  int v17; // ebp
  _QWORD *v18; // r14
  __int64 v19; // rbp
  PTP_POOL Threadpool; // rax
  DWORD LastError; // eax
  __int64 v22; // rdx
  ULONG v23; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_CLEANUP_GROUP v25; // rcx
  __int64 v26; // rax
  HANDLE EventW; // rax
  int Instance; // eax
  __int64 v30; // [rsp+38h] [rbp-50h] BYREF

  v2 = DrvMgrExt;
  LpcInterface = *((_DWORD *)DrvMgrExt + 4);
  if ( LpcInterface < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->u.APC.hThread,
        24,
        &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids,
        (unsigned int)LpcInterface);
    }
LABEL_6:
    v5 = LpcInterface;
LABEL_52:
    v23 = RtlNtStatusToDosError(v5);
LABEL_53:
    RegistrySettings = v23;
    if ( !v23 )
    {
LABEL_57:
      if ( (Microsoft_Windows_DriverFrameworks_UserModeEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(v8, EVENT_DM_START_OK_V2, v10, 1, &v30);
      return RegistrySettings;
    }
    goto LABEL_60;
  }
  started = WdfDriverManager::StartActivityLog(DrvMgrExt);
  if ( started < 0 )
    DbgPrint("WudfSvc: Failed to start activity log (%x)\n", started);
  RegistrySettings = WdfDriverManager::LoadRegistrySettings(v2);
  if ( RegistrySettings )
    goto LABEL_60;
  v11 = operator new(0x78u, v7);
  v12 = v11;
  if ( v11 )
  {
    WdfObject::WdfObject(v11, L"ListObjectNoName", 0);
    *((_QWORD *)v12 + 12) = 0;
    *(_QWORD *)v12 = &WdfObjectList<WdfProcess,WdfProcessParameters>::`vftable';
    *((_DWORD *)v12 + 22) = 1;
    *((_DWORD *)v12 + 26) = 1698975061;
    *((_QWORD *)v12 + 14) = 64;
  }
  else
  {
    v12 = 0;
  }
  *((_QWORD *)v2 + 11) = v12;
  if ( !v12 )
    goto LABEL_14;
  v5 = *((_DWORD *)v12 + 4);
  if ( v5 < 0 )
    goto LABEL_52;
  v13 = operator new(0x78u, v7);
  v14 = v13;
  if ( v13 )
  {
    WdfObject::WdfObject(v13, L"ListObjectNoName", 0);
    *((_QWORD *)v14 + 12) = 0;
    *(_QWORD *)v14 = &WdfObjectList<WdfDevNode,WdfDevNodeParameters>::`vftable';
    *((_DWORD *)v14 + 22) = 1;
    *((_DWORD *)v14 + 26) = 1698975061;
    *((_QWORD *)v14 + 14) = 64;
  }
  else
  {
    v14 = 0;
  }
  *((_QWORD *)v2 + 12) = v14;
  if ( !v14 )
    goto LABEL_14;
  v5 = *((_DWORD *)v14 + 4);
  if ( v5 < 0 )
    goto LABEL_52;
  v15 = operator new(0x78u, v7);
  v16 = v15;
  if ( v15 )
  {
    WdfObject::WdfObject(v15, L"ListObjectNoName", 0);
    *((_QWORD *)v16 + 12) = 0;
    *(_QWORD *)v16 = &WdfObjectList<WdfServiceKey,WdfServiceKeyParameters>::`vftable';
    *((_DWORD *)v16 + 22) = 1;
    *((_DWORD *)v16 + 26) = 1698975061;
    *((_QWORD *)v16 + 14) = 64;
  }
  else
  {
    v16 = 0;
  }
  *((_QWORD *)v2 + 13) = v16;
  if ( !v16 )
  {
LABEL_14:
    RegistrySettings = 14;
    goto LABEL_60;
  }
  v17 = *((_DWORD *)v16 + 4);
  if ( v17 < 0 )
  {
    WdfObject::ReleaseWait((WdfObject *)v16, (unsigned int)v7);
    v5 = v17;
    *((_QWORD *)v2 + 13) = 0;
    goto LABEL_52;
  }
  v18 = (_QWORD *)((char *)v2 + 208);
  LpcInterface = WdfGetLpcInterface((char *)v2 + 208);
  if ( LpcInterface < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 25, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids);
    }
    goto LABEL_6;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v18 + 24LL))(*v18, 4);
  LpcInterface = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v18 + 32LL))(
                   *v18,
                   v19,
                   (__int64)v2 + 112);
  if ( LpcInterface < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
    {
      WPP_SF_Sd(
        WPP_GLOBAL_Control->u.APC.hThread,
        26,
        (unsigned int)&WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids,
        v19,
        LpcInterface);
    }
    goto LABEL_6;
  }
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)v2 + 33) = Threadpool;
  if ( !Threadpool )
  {
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_43;
    }
    LastError = GetLastError();
    v22 = 27;
    goto LABEL_42;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)v2 + 34) = ThreadpoolCleanupGroup;
  v25 = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_43;
    }
    LastError = GetLastError();
    v22 = 28;
LABEL_42:
    WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, v22, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, LastError);
LABEL_43:
    v23 = GetLastError();
    goto LABEL_53;
  }
  v26 = *((_QWORD *)v2 + 33);
  *((_QWORD *)v2 + 37) = v25;
  *((_QWORD *)v2 + 36) = v26;
  *((_DWORD *)v2 + 70) = 3;
  *((_QWORD *)v2 + 39) = 0;
  *((_QWORD *)v2 + 40) = 0;
  *((_QWORD *)v2 + 41) = 0;
  *((_DWORD *)v2 + 84) = 0;
  *((_DWORD *)v2 + 85) = 1;
  *((_DWORD *)v2 + 86) = 72;
  *((_QWORD *)v2 + 38) = 0;
  *((_DWORD *)v2 + 88) = 1;
  EventW = CreateEventW(0, 0, 1, 0);
  *((_QWORD *)v2 + 27) = EventW;
  if ( !EventW )
    goto LABEL_43;
  DrvMgrExt = v2;
  Instance = DrvMgrLpcNotification::CreateInstance(a2, (struct DrvMgrLpcNotification **)v2 + 17);
  if ( Instance < 0 )
  {
    v5 = Instance;
    goto LABEL_52;
  }
  if ( WdfDriverManager::PostRestartDeviceWorkItem(v2, 0) == 1 )
  {
    RegistrySettings = 0;
    goto LABEL_57;
  }
  RegistrySettings = 31;
LABEL_60:
  if ( (unsigned int)dword_1400BA378 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA378, 0x200000000000LL, v10) )
  {
    v30 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>((__int64)&dword_1400BA378);
  }
  if ( (Microsoft_Windows_DriverFrameworks_UserModeEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v8, v7, RegistrySettings);
  return RegistrySettings;
}

```

## disassembly

```asm
0x1400899d0  push    rbx
0x1400899d2  push    rbp
0x1400899d3  push    rsi
0x1400899d4  push    rdi
0x1400899d5  push    r14
0x1400899d7  push    r15
0x1400899d9  sub     rsp, 58h
0x1400899dd  mov     rax, cs:__security_cookie
0x1400899e4  xor     rax, rsp
0x1400899e7  mov     [rsp+88h+var_40], rax
0x1400899ec  mov     rdi, cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA; WdfDriverManager * DrvMgrExt
0x1400899f3  mov     r15, rdx
0x1400899f6  mov     ebx, [rdi+10h]
0x1400899f9  test    ebx, ebx
0x1400899fb  jns     short loc_140089A3E
0x1400899fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089a04  lea     rax, WPP_GLOBAL_Control
0x140089a0b  mov     esi, 1
0x140089a10  cmp     rcx, rax
0x140089a13  jz      short loc_140089A37
0x140089a15  test    [rcx+44h], sil
0x140089a19  jz      short loc_140089A37
0x140089a1b  cmp     byte ptr [rcx+41h], 2
0x140089a1f  jb      short loc_140089A37
0x140089a21  mov     rcx, [rcx+38h]
0x140089a25  lea     edx, [rsi+17h]
0x140089a28  mov     r9d, ebx
0x140089a2b  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x140089a32  call    WPP_SF_d
0x140089a37  mov     ecx, ebx
0x140089a39  jmp     loc_140089DCE
0x140089a3e  mov     rcx, rdi; this
0x140089a41  call    ?StartActivityLog@WdfDriverManager@@AEAAJXZ; WdfDriverManager::StartActivityLog(void)
0x140089a46  test    eax, eax
0x140089a48  jns     short loc_140089A59
0x140089a4a  mov     edx, eax
0x140089a4c  lea     rcx, aWudfsvcFailedT; "WudfSvc: Failed to start activity log ("...
0x140089a53  call    cs:__imp_DbgPrint
0x140089a59  mov     rcx, rdi; this
0x140089a5c  call    ?LoadRegistrySettings@WdfDriverManager@@AEAAKXZ; WdfDriverManager::LoadRegistrySettings(void)
0x140089a61  mov     ebx, eax
0x140089a63  test    eax, eax
0x140089a65  jnz     loc_140089E19
0x140089a6b  lea     ebp, [rax+78h]
0x140089a6e  mov     ecx, ebp; Size
0x140089a70  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x140089a75  lea     esi, [rbp-77h]
0x140089a78  mov     rbx, rax
0x140089a7b  lea     r14, aListobjectnona; "ListObjectNoName"
0x140089a82  test    rax, rax
0x140089a85  jz      short loc_140089ABB
0x140089a87  xor     r8d, r8d
0x140089a8a  mov     rdx, r14
0x140089a8d  mov     rcx, rax
0x140089a90  call    ??0WdfObject@@QEAA@PEBGPEAV0@EW4RdType@@@Z; WdfObject::WdfObject(ushort const *,WdfObject *,uchar,RdType)
0x140089a95  lea     rax, ??_7?$WdfObjectList@VWdfProcess@@VWdfProcessParameters@@@@6B@; const WdfObjectList<WdfProcess,WdfProcessParameters>::`vftable'
0x140089a9c  mov     qword ptr [rbx+60h], 0
0x140089aa4  mov     [rbx], rax
0x140089aa7  mov     [rbx+58h], esi
0x140089aaa  mov     dword ptr [rbx+68h], 65444D55h
0x140089ab1  mov     qword ptr [rbx+70h], 40h ; '@'
0x140089ab9  jmp     short loc_140089ABD
0x140089abb  xor     ebx, ebx
0x140089abd  mov     [rdi+58h], rbx
0x140089ac1  test    rbx, rbx
0x140089ac4  jnz     short loc_140089AD0
0x140089ac6  mov     ebx, 0Eh
0x140089acb  jmp     loc_140089E19
0x140089ad0  mov     ecx, [rbx+10h]
0x140089ad3  test    ecx, ecx
0x140089ad5  js      loc_140089DCE
0x140089adb  mov     rcx, rbp; Size
0x140089ade  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x140089ae3  mov     rbx, rax
0x140089ae6  test    rax, rax
0x140089ae9  jz      short loc_140089B1F
0x140089aeb  xor     r8d, r8d
0x140089aee  mov     rdx, r14
0x140089af1  mov     rcx, rax
0x140089af4  call    ??0WdfObject@@QEAA@PEBGPEAV0@EW4RdType@@@Z; WdfObject::WdfObject(ushort const *,WdfObject *,uchar,RdType)
0x140089af9  lea     rax, ??_7?$WdfObjectList@VWdfDevNode@@VWdfDevNodeParameters@@@@6B@; const WdfObjectList<WdfDevNode,WdfDevNodeParameters>::`vftable'
0x140089b00  mov     qword ptr [rbx+60h], 0
0x140089b08  mov     [rbx], rax
0x140089b0b  mov     [rbx+58h], esi
0x140089b0e  mov     dword ptr [rbx+68h], 65444D55h
0x140089b15  mov     qword ptr [rbx+70h], 40h ; '@'
0x140089b1d  jmp     short loc_140089B21
0x140089b1f  xor     ebx, ebx
0x140089b21  mov     [rdi+60h], rbx
0x140089b25  test    rbx, rbx
0x140089b28  jz      short loc_140089AC6
0x140089b2a  mov     ecx, [rbx+10h]
0x140089b2d  test    ecx, ecx
0x140089b2f  js      loc_140089DCE
0x140089b35  mov     rcx, rbp; Size
0x140089b38  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x140089b3d  mov     rbx, rax
0x140089b40  test    rax, rax
0x140089b43  jz      short loc_140089B79
0x140089b45  xor     r8d, r8d
0x140089b48  mov     rdx, r14
0x140089b4b  mov     rcx, rax
0x140089b4e  call    ??0WdfObject@@QEAA@PEBGPEAV0@EW4RdType@@@Z; WdfObject::WdfObject(ushort const *,WdfObject *,uchar,RdType)
0x140089b53  lea     rax, ??_7?$WdfObjectList@VWdfServiceKey@@VWdfServiceKeyParameters@@@@6B@; const WdfObjectList<WdfServiceKey,WdfServiceKeyParameters>::`vftable'
0x140089b5a  mov     qword ptr [rbx+60h], 0
0x140089b62  mov     [rbx], rax
0x140089b65  mov     [rbx+58h], esi
0x140089b68  mov     dword ptr [rbx+68h], 65444D55h
0x140089b6f  mov     qword ptr [rbx+70h], 40h ; '@'
0x140089b77  jmp     short loc_140089B7B
0x140089b79  xor     ebx, ebx
0x140089b7b  mov     [rdi+68h], rbx
0x140089b7f  test    rbx, rbx
0x140089b82  jz      loc_140089AC6
0x140089b88  mov     ebp, [rbx+10h]
0x140089b8b  test    ebp, ebp
0x140089b8d  jns     short loc_140089BA6
0x140089b8f  mov     rcx, rbx; this
0x140089b92  call    ?ReleaseWait@WdfObject@@QEAAXK@Z; WdfObject::ReleaseWait(ulong)
0x140089b97  mov     ecx, ebp
0x140089b99  mov     qword ptr [rdi+68h], 0
0x140089ba1  jmp     loc_140089DCE
0x140089ba6  lea     r14, [rdi+0D0h]
0x140089bad  mov     rcx, r14
0x140089bb0  call    cs:__imp_WdfGetLpcInterface
0x140089bb6  mov     ebx, eax
0x140089bb8  test    eax, eax
0x140089bba  jns     short loc_140089C01
0x140089bbc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089bc3  lea     rax, WPP_GLOBAL_Control
0x140089bca  cmp     rcx, rax
0x140089bcd  jz      loc_140089A37
0x140089bd3  test    [rcx+44h], sil
0x140089bd7  jz      loc_140089A37
0x140089bdd  cmp     byte ptr [rcx+41h], 5
0x140089be1  jb      loc_140089A37
0x140089be7  mov     rcx, [rcx+38h]
0x140089beb  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x140089bf2  mov     edx, 19h
0x140089bf7  call    WPP_SF_
0x140089bfc  jmp     loc_140089A37
0x140089c01  mov     rcx, [r14]
0x140089c04  mov     edx, 4
0x140089c09  mov     rax, [rcx]
0x140089c0c  mov     rax, [rax+18h]
0x140089c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089c15  mov     r9, [r14]
0x140089c18  lea     r8, [rdi+70h]
0x140089c1c  mov     rbp, rax
0x140089c1f  mov     rdx, rbp
0x140089c22  mov     rcx, [r9]
0x140089c25  mov     rax, [rcx+20h]
0x140089c29  mov     rcx, r9
0x140089c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089c31  mov     ebx, eax
0x140089c33  test    eax, eax
0x140089c35  jns     short loc_140089C83
0x140089c37  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089c3e  lea     rax, WPP_GLOBAL_Control
0x140089c45  cmp     rcx, rax
0x140089c48  jz      loc_140089A37
0x140089c4e  test    [rcx+44h], sil
0x140089c52  jz      loc_140089A37
0x140089c58  cmp     byte ptr [rcx+41h], 2
0x140089c5c  jb      loc_140089A37
0x140089c62  mov     rcx, [rcx+38h]
0x140089c66  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x140089c6d  mov     edx, 1Ah
0x140089c72  mov     dword ptr [rsp+88h+var_68], ebx
0x140089c76  mov     r9, rbp
0x140089c79  call    WPP_SF_Sd
0x140089c7e  jmp     loc_140089A37
0x140089c83  xor     ecx, ecx; reserved
0x140089c85  call    cs:__imp_CreateThreadpool
0x140089c8b  mov     [rdi+108h], rax
0x140089c92  test    rax, rax
0x140089c95  jnz     short loc_140089CE6
0x140089c97  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089c9e  lea     rax, WPP_GLOBAL_Control
0x140089ca5  cmp     rcx, rax
0x140089ca8  jz      short loc_140089CDB
0x140089caa  test    [rcx+44h], sil
0x140089cae  jz      short loc_140089CDB
0x140089cb0  cmp     byte ptr [rcx+41h], 2
0x140089cb4  jb      short loc_140089CDB
0x140089cb6  call    cs:__imp_GetLastError
0x140089cbc  mov     edx, 1Bh
0x140089cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140089cc8  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x140089ccf  mov     r9d, eax
0x140089cd2  mov     rcx, [rcx+38h]
0x140089cd6  call    WPP_SF_d
0x140089cdb  call    cs:__imp_GetLastError
0x140089ce1  jmp     loc_140089DD4
0x140089ce6  call    cs:__imp_CreateThreadpoolCleanupGroup
0x140089cec  mov     [rdi+110h], rax
0x140089cf3  mov     rcx, rax
0x140089cf6  test    rax, rax
0x140089cf9  jnz     short loc_140089D27
0x140089cfb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140089d02  lea     rax, WPP_GLOBAL_Control
0x140089d09  cmp     rcx, rax
0x140089d0c  jz      short loc_140089CDB
0x140089d0e  test    [rcx+44h], sil
0x140089d12  jz      short loc_140089CDB
0x140089d14  cmp     byte ptr [rcx+41h], 2
0x140089d18  jb      short loc_140089CDB
0x140089d1a  call    cs:__imp_GetLastError
0x140089d20  mov     edx, 1Ch
0x140089d25  jmp     short loc_140089CC1
0x140089d27  mov     rax, [rdi+108h]
0x140089d2e  xor     r9d, r9d; lpName
0x140089d31  mov     [rdi+128h], rcx
0x140089d38  mov     r8d, esi; bInitialState
0x140089d3b  xor     ecx, ecx; lpEventAttributes
0x140089d3d  mov     [rdi+120h], rax
0x140089d44  xor     edx, edx; bManualReset
0x140089d46  mov     dword ptr [rdi+118h], 3
0x140089d50  mov     qword ptr [rdi+138h], 0
0x140089d5b  mov     qword ptr [rdi+140h], 0
0x140089d66  mov     qword ptr [rdi+148h], 0
0x140089d71  mov     dword ptr [rdi+150h], 0
0x140089d7b  mov     [rdi+154h], esi
0x140089d81  mov     dword ptr [rdi+158h], 48h ; 'H'
0x140089d8b  mov     qword ptr [rdi+130h], 0
0x140089d96  mov     [rdi+160h], esi
0x140089d9c  call    cs:__imp_CreateEventW
0x140089da2  mov     [rdi+0D8h], rax
0x140089da9  test    rax, rax
0x140089dac  jz      loc_140089CDB
0x140089db2  lea     rdx, [rdi+88h]; struct DrvMgrLpcNotification **
0x140089db9  mov     cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA, rdi; WdfDriverManager * DrvMgrExt
0x140089dc0  mov     rcx, r15; struct DrvMgrCmdLineArguments *
0x140089dc3  call    ?CreateInstance@DrvMgrLpcNotification@@SAJPEAVDrvMgrCmdLineArguments@@PEAPEAV1@@Z; DrvMgrLpcNotification::CreateInstance(DrvMgrCmdLineArguments *,DrvMgrLpcNotification * *)
0x140089dc8  test    eax, eax
0x140089dca  jns     short loc_140089DDC
0x140089dcc  mov     ecx, eax; Status
0x140089dce  call    cs:__imp_RtlNtStatusToDosError
0x140089dd4  mov     ebx, eax
0x140089dd6  test    eax, eax
0x140089dd8  jnz     short loc_140089E19
0x140089dda  jmp     short loc_140089DEC
0x140089ddc  xor     edx, edx; struct WdfDevNode *
0x140089dde  mov     rcx, rdi; this
0x140089de1  call    ?PostRestartDeviceWorkItem@WdfDriverManager@@QEAAHPEAVWdfDevNode@@@Z; WdfDriverManager::PostRestartDeviceWorkItem(WdfDevNode *)
0x140089de6  cmp     eax, esi
0x140089de8  jnz     short loc_140089E14
0x140089dea  xor     ebx, ebx
0x140089dec  test    cs:Microsoft_Windows_DriverFrameworks_UserModeEnableBits, sil
0x140089df3  jz      loc_140089E83
0x140089df9  lea     rax, [rsp+88h+var_50]
0x140089dfe  mov     r9d, esi
0x140089e01  lea     rdx, EVENT_DM_START_OK_V2
0x140089e08  mov     [rsp+88h+var_68], rax
0x140089e0d  call    McGenEventWrite_EventWriteTransfer
0x140089e12  jmp     short loc_140089E83
0x140089e14  mov     ebx, 1Fh
0x140089e19  mov     eax, cs:dword_1400BA378
0x140089e1f  cmp     eax, 5
0x140089e22  jbe     short loc_140089E72
0x140089e24  mov     rdx, 200000000000h
0x140089e2e  lea     rcx, dword_1400BA378
0x140089e35  call    _tlgKeywordOn
0x140089e3a  test    al, al
0x140089e3c  jz      short loc_140089E72
0x140089e3e  lea     rax, [rsp+88h+var_58]
0x140089e43  mov     [rsp+88h+var_58], ebx
0x140089e47  mov     [rsp+88h+var_60], rax
0x140089e4c  lea     rdx, byte_1400AF95F
0x140089e53  lea     rax, [rsp+88h+var_50]
0x140089e58  mov     [rsp+88h+var_50], 1000800h
0x140089e61  lea     rcx, dword_1400BA378
0x140089e68  mov     [rsp+88h+var_68], rax
0x140089e6d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140089e72  test    cs:Microsoft_Windows_DriverFrameworks_UserModeEnableBits, 2
0x140089e79  jz      short loc_140089E83
0x140089e7b  mov     r8d, ebx
0x140089e7e  call    McTemplateU0q_EventWriteTransfer
0x140089e83  mov     eax, ebx
0x140089e85  mov     rcx, [rsp+88h+var_40]
0x140089e8a  xor     rcx, rsp; StackCookie
0x140089e8d  call    __security_check_cookie
0x140089e92  add     rsp, 58h
0x140089e96  pop     r15
0x140089e98  pop     r14
0x140089e9a  pop     rdi
0x140089e9b  pop     rsi
0x140089e9c  pop     rbp
0x140089e9d  pop     rbx
0x140089e9e  retn
```
