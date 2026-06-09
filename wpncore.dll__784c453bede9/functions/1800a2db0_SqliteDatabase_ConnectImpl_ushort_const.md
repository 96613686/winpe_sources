# SqliteDatabase::ConnectImpl(ushort const *)

- ea: `0x1800a2db0`
- end: `0x1800a308f`
- name: `?ConnectImpl@SqliteDatabase@@AEAAJPEBG@Z`
- size: `735`
- prototype: `__int64 __fastcall(SqliteDatabase *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f07d0`

## callees

- `0x1800060a8`
- `0x180007ec4`
- `0x180009198`
- `0x18000941c`
- `0x18000abb0`
- `0x18000b674`
- `0x18000b698`
- `0x18000e5f4`
- `0x180016900`
- `0x18002bf64`
- `0x1800372d0`
- `0x180047938`
- `0x180049644`
- `0x18004f21c`
- `0x180065b08`
- `0x18009574c`
- `0x18009d30c`
- `0x1800a2db0`
- `0x1800a3098`
- `0x1800a30e0`
- `0x1800a3180`
- `0x1800a3d1c`
- `0x1800a3d74`
- `0x1800ba0d0`
- `0x1800f01e8`
- `0x1800f0200`
- `0x1800f02f0`
- `0x1800f08e4`
- `0x1800f0f34`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800a2fa7`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800a2fcb`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800a2fa7`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800a2fcb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2fbd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2fbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2dd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2dd0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a2e5d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a2e5d`

## string_xrefs

- `0x1800a301f`: `CREATE TABLE [NotificationHandler] ( [RecordId] INTEGER PRIMARY KEY, [PrimaryId] TEXT NOT NULL COLLATE NOCASE, [WNSId] TEXT COLLATE NOCASE, [HandlerType] TEXT, [WNFEventName] INT64, [SystemDataPropertySet] BLOB, [CreatedTime] DATETIME, [ModifiedTime] DATETIME, [ParentId] TEXT COLLATE NOCASE, [ContainerSid] TEXT COLLATE NOCASE); CREATE UNIQUE INDEX [byHandlerName] ON [NotificationHandler] ([PrimaryId]); CREATE TABLE[HandlerSettings]( [HandlerId] INTEGER CONSTRAINT[SettingsToHandler] REFERENCES[No`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SqliteDatabase::ConnectImpl(SqliteDatabase *this, LPCWSTR lpFileName)
{
  char *v4; // rbx
  _DWORD *v5; // rbx
  char v6; // r14
  Database **v7; // rbx
  const char *v8; // rdx
  int PragmaINT32; // eax
  const char *v10; // rdx
  bool v11; // zf
  __int64 v12; // rax
  int i; // esi
  Database *v14; // rcx
  const char *v15; // rdx
  int v16; // edx
  int v17; // edx
  wil *v18; // rcx
  unsigned int j; // esi
  int v20; // edx
  int v21; // edx
  int v23; // edi
  const char *v24; // r9
  int v25[2]; // [rsp+20h] [rbp-58h] BYREF
  char *v26; // [rsp+28h] [rbp-50h] BYREF
  std::_Ref_count_base *v27; // [rsp+30h] [rbp-48h]
  _BYTE v28[64]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v31; // [rsp+80h] [rbp+8h]
  _DWORD *v32; // [rsp+90h] [rbp+18h] BYREF
  char *FileName; // [rsp+98h] [rbp+20h] BYREF

  v4 = (char *)this + 152;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  *(_QWORD *)v25 = v4;
  try
  {
    v5 = operator new(0xA0u);
    v32 = v5;
    v6 = 1;
    v5[2] = 1;
    v5[3] = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<Database>::`vftable';
    *((_QWORD *)v5 + 2) = 0;
    v5[6] = 0;
    StatementCache::StatementCache((StatementCache *)(v5 + 8));
    v26 = (char *)(v5 + 4);
    v27 = (std::_Ref_count_base *)v5;
    v7 = (Database **)((char *)this + 48);
    std::shared_ptr<Statement>::operator=((char *)this + 48, &v26);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    std::wstring::assign((char *)this + 64, lpFileName);
    if ( GetFileAttributesW(lpFileName) != -1 )
    {
      Database::Open(*v7, lpFileName, 0);
      PragmaINT32 = Database::GetPragmaINT32(*v7, v8);
      LODWORD(v32) = PragmaINT32;
      v11 = PragmaINT32 == 0;
      if ( PragmaINT32 > 0 )
      {
        if ( PragmaINT32 < 8 )
        {
          Database::SetPragma(*v7, v10, 0);
          v12 = lambda_d115484a6c913f7ac89f9e4d5df34e5c_::_lambda_d115484a6c913f7ac89f9e4d5df34e5c_(&v26, this, &v32);
          wil::ScopeExit__lambda_d115484a6c913f7ac89f9e4d5df34e5c___(v28, v12);
          Database::BeginTransaction(*v7);
          for ( i = (int)v32; ; ++i )
          {
            v14 = *v7;
            if ( i >= 8 )
              break;
            Database::Execute(v14, off_18015C580[i - 1]);
          }
          Database::Commit(v14);
          wil::details::ScopeExitFn__lambda_d115484a6c913f7ac89f9e4d5df34e5c___::Dismiss(v28);
          Database::SetPragma(*v7, v15, 1);
          Database::SetBusyTimeout(*v7, v16);
          Database::SetFileChunkSize(*v7, v17);
          Database::SetPragma(*v7, "user_version", 8);
          wil::details::ScopeExitFn__lambda_d115484a6c913f7ac89f9e4d5df34e5c___::_ScopeExitFn__lambda_d115484a6c913f7ac89f9e4d5df34e5c___(v28);
          PragmaINT32 = (int)v32;
        }
        v11 = PragmaINT32 == 0;
      }
      if ( !v11 && SqliteDatabase::ValidateDB(this) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID54436891>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID54436891>::GetImpl'::`2'::impl) )
          SqliteDatabase::PutRawTypeNotificationLimit(this);
        SqliteDatabase::DumpBackup(this);
        goto LABEL_34;
      }
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 48LL))((char *)this + 32);
      ConvertUtf16ToUtf8(&FileName, lpFileName);
      if ( remove(FileName) )
      {
        for ( j = 0; j < 5; ++j )
        {
          Sleep(0x7D0u);
          if ( !remove(FileName) )
            goto LABEL_22;
        }
      }
      else
      {
LABEL_22:
        v6 = 0;
      }
      if ( v6 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1F0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)0x8000FFFFLL,
          v25[0]);
      wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(&FileName, 0);
    }
    Database::Open(*v7, lpFileName, 12898);
    Database::Execute(
      *v7,
      "CREATE TABLE [NotificationHandler] ( [RecordId] INTEGER PRIMARY KEY, [PrimaryId] TEXT NOT NULL COLLATE NOCASE, [WN"
      "SId] TEXT COLLATE NOCASE, [HandlerType] TEXT, [WNFEventName] INT64, [SystemDataPropertySet] BLOB, [CreatedTime] DA"
      "TETIME, [ModifiedTime] DATETIME, [ParentId] TEXT COLLATE NOCASE, [ContainerSid] TEXT COLLATE NOCASE); CREATE UNIQU"
      "E INDEX [byHandlerName] ON [NotificationHandler] ([PrimaryId]); CREATE TABLE[HandlerSettings]( [HandlerId] INTEGER"
      " CONSTRAINT[SettingsToHandler] REFERENCES[NotificationHandler]([RecordId]) ON DELETE CASCADE ON UPDATE CASCADE, [S"
      "ettingKey] TEXT NOT NULL, [Value] INT, CONSTRAINT[] PRIMARY KEY([SettingKey], [HandlerId]) ON CONFLICT REPLACE); C"
      "REATE INDEX[bySetting] ON[HandlerSettings] ([SettingKey], [Value]); CREATE TABLE[Notification]( [Order] INTEGER NO"
      "T NULL PRIMARY KEY, [Id] INTEGER NOT NULL, [HandlerId] INTEGER CONSTRAINT[NotificationToHandler] REFERENCES[Notifi"
      "cationHandler]([RecordId]) ON DELETE CASCADE ON UPDATE CASCADE, [ActivityId] GUID,[Type] TEXT NOT NULL, [Payload] "
      "BLOB, [Tag] TEXT, [Group] TEXT, [ExpiryTime] INT64, [ArrivalTime] INT64, [DataVersion] INT64 DEFAULT '0', [Payload"
      "Type] TEXT NOT NULL, [BootId] INT64 DEFAULT '0', [ExpiresOnReboot] BOOLEAN DEFAULT 'FALSE', UNIQUE([Id]) ON CONFLI"
      "CT REPLACE); CREATE INDEX [notificationById] ON [Notification] ([Id]); CREATE INDEX [notificationByApp] ON [Notifi"
      "cation] ([HandlerId]); CREATE INDEX [notificationByActivityId] ON [Notification] ([ActivityId]); CREATE INDEX [not"
      "ificationByAppByType] ON [Notification] ([HandlerId], [Type]); CREATE INDEX [notificationByTagGroup] ON [Notificat"
      "ion] ([HandlerId], [Type], [Group], [Tag]); CREATE INDEX [notificationByType] ON [Notification] ([Type]); CREATE I"
      "NDEX [notificationExpired] ON [Notification] ([ExpiryTime] DESC); CREATE TABLE[WNSPushChannel]( [ChannelId] TEXT N"
      "OT NULL, [HandlerId] INTEGER REFERENCES[NotificationHandler]([RecordId]) ON DELETE CASCADE ON UPDATE CASCADE, [Uri"
      "] TEXT, [ExpiryTime] INT64, [CreatedTime] INT64, [DeviceVersion] INT64 DEFAULT '0', CONSTRAINT[] PRIMARY KEY([Chan"
      "nelId]) ON CONFLICT REPLACE); CREATE INDEX[channelByApp] ON [WNSPushChannel] ([HandlerId]); CREATE INDEX[channelEx"
      "pired] ON [WNSPushChannel] ([ExpiryTime] DESC); CREATE TABLE[Metadata]( [Key] TEXT, [Value] INT64, CONSTRAINT[] PR"
      "IMARY KEY([Key]) ON CONFLICT REPLACE); CREATE TABLE[NotificationData]( [NotificationId] INTEGER CONSTRAINT[DataToN"
      "otification] REFERENCES[Notification]([Id]) ON DELETE CASCADE ON UPDATE CASCADE, [Key] TEXT NOT NULL, [Value] TEXT"
      ", CONSTRAINT[] PRIMARY KEY([Key], [NotificationId]) ON CONFLICT REPLACE); CREATE TABLE[HandlerAssets]( [HandlerId]"
      " INTEGER CONSTRAINT[AssetsToHandler] REFERENCES[NotificationHandler]([RecordId]) ON DELETE CASCADE ON UPDATE CASCA"
      "DE, [AssetKey] TEXT NOT NULL, [AssetValue] TEXT, CONSTRAINT[] PRIMARY KEY([AssetKey], [HandlerId]) ON CONFLICT REP"
      "LACE); CREATE TABLE[TransientTable]( [OfflineCacheCount] INTEGER, [NotificationId] INTEGER CONSTRAINT[TransientToN"
      "otification] REFERENCES[Notification]([Id]) ON DELETE CASCADE ON UPDATE CASCADE, [OfflineBundleId] TEXT, [ServerCa"
      "cheRollover] BOOLEAN DEFAULT 'FALSE', [CrossDeviceMatchId] TEXT, [SuppressPopup] BOOLEAN DEFAULT 'FALSE', [IsMirro"
      "ringDisabled] BOOLEAN DEFAULT 'FALSE', [RecurrenceId] GUID, [MessageId] GUID, [Priority] INTEGER NOT NULL, [CV] TE"
      "XT);CREATE TABLE[TimedNotification]( [TimerEventId] GUID NOT NULL, [BBIWorkId] GUID NOT NULL, [WnfStateName] INT64"
      " NOT NULL, [HandlerId] INTEGER REFERENCES[NotificationHandler]([RecordId]) ON DELETE CASCADE ON UPDATE CASCADE, [N"
      "otificationType] INTEGER NOT NULL, [Url] TEXT, CONSTRAINT[] PRIMARY KEY([TimerEventId]) ON CONFLICT REPLACE); ");
    Database::SetBusyTimeout(*v7, v20);
    Database::SetFileChunkSize(*v7, v21);
    Database::SetPragma(*v7, "user_version", 8);
    SqliteDatabase::SetupLimits(this);
    SqliteDatabase::ReloadBackup(this);
  }
  catch ( ... )
  {
    v23 = wil::ResultFromCaughtException(v18);
    if ( IsHresultSqliteCorruption(v23) )
      SqliteDatabase::RepairCorruption(this);
    SqliteDatabase::LogDbFailure(this, "SqliteDatabase::ConnectImpl", v23);
    v31 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x210,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
            v24);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v25);
    return v31;
  }
LABEL_34:
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v25);
  return 0;
}

```

## disassembly

```asm
0x1800a2db0  mov     [rsp+arg_0], rcx
0x1800a2db5  push    rbx
0x1800a2db6  push    rsi
0x1800a2db7  push    rdi
0x1800a2db8  push    r14
0x1800a2dba  push    r15
0x1800a2dbc  sub     rsp, 50h
0x1800a2dc0  mov     r15, rdx
0x1800a2dc3  mov     rdi, rcx
0x1800a2dc6  lea     rbx, [rcx+98h]
0x1800a2dcd  mov     rcx, rbx; lpCriticalSection
0x1800a2dd0  call    cs:__imp_EnterCriticalSection
0x1800a2dd6  mov     qword ptr [rsp+78h+var_58], rbx; int
0x1800a2ddb  mov     ecx, 0A0h; Size
0x1800a2de0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a2de5  mov     rbx, rax
0x1800a2de8  mov     [rsp+78h+arg_10], rax
0x1800a2df0  mov     r14d, 1
0x1800a2df6  mov     [rax+8], r14d
0x1800a2dfa  mov     [rax+0Ch], r14d
0x1800a2dfe  lea     rax, ??_7?$_Ref_count_obj2@VDatabase@@@std@@6B@; const std::_Ref_count_obj2<Database>::`vftable'
0x1800a2e05  mov     [rbx], rax
0x1800a2e08  lea     rsi, [rbx+10h]
0x1800a2e0c  mov     qword ptr [rsi], 0
0x1800a2e13  mov     dword ptr [rsi+8], 0
0x1800a2e1a  lea     rcx, [rsi+10h]; this
0x1800a2e1e  call    ??0StatementCache@@QEAA@XZ; StatementCache::StatementCache(void)
0x1800a2e23  nop
0x1800a2e24  mov     [rsp+78h+var_50], rsi
0x1800a2e29  mov     [rsp+78h+var_48], rbx
0x1800a2e2e  lea     rbx, [rdi+30h]
0x1800a2e32  lea     rdx, [rsp+78h+var_50]
0x1800a2e37  mov     rcx, rbx
0x1800a2e3a  call    ??4?$shared_ptr@VStatement@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Statement>::operator=(std::shared_ptr<Statement> &&)
0x1800a2e3f  mov     rcx, [rsp+78h+var_48]; this
0x1800a2e44  test    rcx, rcx
0x1800a2e47  jz      short loc_1800A2E4E
0x1800a2e49  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a2e4e  lea     rcx, [rdi+40h]
0x1800a2e52  mov     rdx, r15
0x1800a2e55  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800a2e5a  mov     rcx, r15; lpFileName
0x1800a2e5d  call    cs:__imp_GetFileAttributesW
0x1800a2e63  cmp     eax, 0FFFFFFFFh
0x1800a2e66  jz      loc_1800A300E
0x1800a2e6c  xor     r8d, r8d
0x1800a2e6f  mov     rdx, r15
0x1800a2e72  mov     rcx, [rbx]
0x1800a2e75  call    ?Open@Database@@QEAAXPEBGW4OpenFlags@1@@Z; Database::Open(ushort const *,Database::OpenFlags)
0x1800a2e7a  mov     rcx, [rbx]; this
0x1800a2e7d  call    ?GetPragmaINT32@Database@@QEAAHPEBD@Z; Database::GetPragmaINT32(char const *)
0x1800a2e82  mov     dword ptr [rsp+78h+arg_10], eax
0x1800a2e89  test    eax, eax
0x1800a2e8b  jle     loc_1800A2F4B
0x1800a2e91  cmp     eax, 8
0x1800a2e94  jge     loc_1800A2F49
0x1800a2e9a  xor     r8d, r8d; bool
0x1800a2e9d  mov     rcx, [rbx]; this
0x1800a2ea0  call    ?SetPragma@Database@@QEAAXPEBD_N@Z; Database::SetPragma(char const *,bool)
0x1800a2ea5  lea     r8, [rsp+78h+arg_10]
0x1800a2ead  mov     rdx, rdi
0x1800a2eb0  lea     rcx, [rsp+78h+var_50]
0x1800a2eb5  call    _lambda_d115484a6c913f7ac89f9e4d5df34e5c____lambda_d115484a6c913f7ac89f9e4d5df34e5c_
0x1800a2eba  mov     rdx, rax
0x1800a2ebd  lea     rcx, [rsp+78h+var_40]
0x1800a2ec2  call    wil__ScopeExit__lambda_d115484a6c913f7ac89f9e4d5df34e5c___
0x1800a2ec7  nop
0x1800a2ec8  mov     rcx, [rbx]
0x1800a2ecb  call    ?BeginTransaction@Database@@QEAAXW4BeginTransactionLock@1@@Z; Database::BeginTransaction(Database::BeginTransactionLock)
0x1800a2ed0  mov     esi, dword ptr [rsp+78h+arg_10]
0x1800a2ed7  mov     rcx, [rbx]; this
0x1800a2eda  cmp     esi, 8
0x1800a2edd  jge     short loc_1800A2EF8
0x1800a2edf  movsxd  rdx, esi
0x1800a2ee2  lea     rax, off_18015C580; "CREATE TABLE [NotificationHandler_Copy]"...
0x1800a2ee9  mov     rdx, [rax+rdx*8-8]; char *
0x1800a2eee  call    ?Execute@Database@@QEAAXPEBD@Z; Database::Execute(char const *)
0x1800a2ef3  add     esi, r14d
0x1800a2ef6  jmp     short loc_1800A2ED7
0x1800a2ef8  call    ?Commit@Database@@QEAAXXZ; Database::Commit(void)
0x1800a2efd  lea     rcx, [rsp+78h+var_40]
0x1800a2f02  call    wil__details__ScopeExitFn__lambda_d115484a6c913f7ac89f9e4d5df34e5c_____Dismiss
0x1800a2f07  mov     r8b, r14b; bool
0x1800a2f0a  mov     rcx, [rbx]; this
0x1800a2f0d  call    ?SetPragma@Database@@QEAAXPEBD_N@Z; Database::SetPragma(char const *,bool)
0x1800a2f12  mov     rcx, [rbx]; this
0x1800a2f15  call    ?SetBusyTimeout@Database@@QEAAXH@Z; Database::SetBusyTimeout(int)
0x1800a2f1a  mov     rcx, [rbx]; this
0x1800a2f1d  call    ?SetFileChunkSize@Database@@QEAAXH@Z; Database::SetFileChunkSize(int)
0x1800a2f22  mov     r8d, 8; __int64
0x1800a2f28  lea     rdx, aUserVersion; "user_version"
0x1800a2f2f  mov     rcx, [rbx]; this
0x1800a2f32  call    ?SetPragma@Database@@QEAAXPEBD_J@Z; Database::SetPragma(char const *,__int64)
0x1800a2f37  nop
0x1800a2f38  lea     rcx, [rsp+78h+var_40]
0x1800a2f3d  call    wil__details__ScopeExitFn__lambda_d115484a6c913f7ac89f9e4d5df34e5c______ScopeExitFn__lambda_d115484a6c913f7ac89f9e4d5df34e5c___
0x1800a2f42  mov     eax, dword ptr [rsp+78h+arg_10]
0x1800a2f49  test    eax, eax
0x1800a2f4b  jz      short loc_1800A2F7E
0x1800a2f4d  mov     rcx, rdi; this
0x1800a2f50  call    ?ValidateDB@SqliteDatabase@@AEAA_NXZ; SqliteDatabase::ValidateDB(void)
0x1800a2f55  test    al, al
0x1800a2f57  jz      short loc_1800A2F7E
0x1800a2f59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID54436891@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID54436891@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID54436891> `wil::Feature<__WilFeatureTraits_Feature_ID54436891>::GetImpl(void)'::`2'::impl
0x1800a2f60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID54436891@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID54436891>::__private_IsEnabled(void)
0x1800a2f65  test    al, al
0x1800a2f67  jz      short loc_1800A2F71
0x1800a2f69  mov     rcx, rdi; this
0x1800a2f6c  call    ?PutRawTypeNotificationLimit@SqliteDatabase@@AEAAXXZ; SqliteDatabase::PutRawTypeNotificationLimit(void)
0x1800a2f71  mov     rcx, rdi; this
0x1800a2f74  call    ?DumpBackup@SqliteDatabase@@AEAAXXZ; SqliteDatabase::DumpBackup(void)
0x1800a2f79  jmp     loc_1800A3064
0x1800a2f7e  lea     rcx, [rdi+20h]
0x1800a2f82  mov     rax, [rcx]
0x1800a2f85  mov     rax, [rax+30h]
0x1800a2f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f8e  mov     rdx, r15
0x1800a2f91  lea     rcx, [rsp+78h+FileName]
0x1800a2f99  call    ?ConvertUtf16ToUtf8@@YA?AV?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@PEBG@Z; ConvertUtf16ToUtf8(ushort const *)
0x1800a2f9e  nop
0x1800a2f9f  mov     rcx, [rsp+78h+FileName]; FileName
0x1800a2fa7  call    cs:__imp_remove
0x1800a2fad  test    eax, eax
0x1800a2faf  jz      short loc_1800A2FDA
0x1800a2fb1  xor     esi, esi
0x1800a2fb3  cmp     esi, 5
0x1800a2fb6  jnb     short loc_1800A2FDD
0x1800a2fb8  mov     ecx, 7D0h; dwMilliseconds
0x1800a2fbd  call    cs:__imp_Sleep
0x1800a2fc3  mov     rcx, [rsp+78h+FileName]; FileName
0x1800a2fcb  call    cs:__imp_remove
0x1800a2fd1  test    eax, eax
0x1800a2fd3  jz      short loc_1800A2FDA
0x1800a2fd5  add     esi, r14d
0x1800a2fd8  jmp     short loc_1800A2FB3
0x1800a2fda  xor     r14b, r14b
0x1800a2fdd  mov     rcx, [rsp+78h]; this
0x1800a2fe2  test    r14b, r14b
0x1800a2fe5  jz      short loc_1800A2FFF
0x1800a2fe7  mov     r9d, 8000FFFFh; char *
0x1800a2fed  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a2ff4  mov     edx, 1F0h; void *
0x1800a2ff9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2fff  xor     edx, edx
0x1800a3001  lea     rcx, [rsp+78h+FileName]
0x1800a3009  call    ?reset@?$unique_ptr@U_GUID@@Uprocess_heap_deleter@wil@@@wistd@@QEAAXPEAU_GUID@@@Z; wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(_GUID *)
0x1800a300e  mov     r8d, 3262h
0x1800a3014  mov     rdx, r15
0x1800a3017  mov     rcx, [rbx]
0x1800a301a  call    ?Open@Database@@QEAAXPEBGW4OpenFlags@1@@Z; Database::Open(ushort const *,Database::OpenFlags)
0x1800a301f  lea     rdx, aCreateTableNot; "CREATE TABLE [NotificationHandler] ( [R"...
0x1800a3026  mov     rcx, [rbx]; this
0x1800a3029  call    ?Execute@Database@@QEAAXPEBD@Z; Database::Execute(char const *)
0x1800a302e  mov     rcx, [rbx]; this
0x1800a3031  call    ?SetBusyTimeout@Database@@QEAAXH@Z; Database::SetBusyTimeout(int)
0x1800a3036  mov     rcx, [rbx]; this
0x1800a3039  call    ?SetFileChunkSize@Database@@QEAAXH@Z; Database::SetFileChunkSize(int)
0x1800a303e  mov     r8d, 8; __int64
0x1800a3044  lea     rdx, aUserVersion; "user_version"
0x1800a304b  mov     rcx, [rbx]; this
0x1800a304e  call    ?SetPragma@Database@@QEAAXPEBD_J@Z; Database::SetPragma(char const *,__int64)
0x1800a3053  mov     rcx, rdi; this
0x1800a3056  call    ?SetupLimits@SqliteDatabase@@AEAAXXZ; SqliteDatabase::SetupLimits(void)
0x1800a305b  mov     rcx, rdi; this
0x1800a305e  call    ?ReloadBackup@SqliteDatabase@@AEAAXXZ; SqliteDatabase::ReloadBackup(void)
0x1800a3063  nop
0x1800a3064  lea     rcx, [rsp+78h+var_58]; this
0x1800a3069  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800a306e  xor     eax, eax
0x1800a3070  jmp     short loc_1800A3083
0x1800a3072  lea     rcx, [rsp+78h+var_58]; this
0x1800a3077  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800a307c  mov     eax, dword ptr [rsp+78h+arg_0]
0x1800a3083  add     rsp, 50h
0x1800a3087  pop     r15
0x1800a3089  pop     r14
0x1800a308b  pop     rdi
0x1800a308c  pop     rsi
0x1800a308d  pop     rbx
0x1800a308e  retn
```
