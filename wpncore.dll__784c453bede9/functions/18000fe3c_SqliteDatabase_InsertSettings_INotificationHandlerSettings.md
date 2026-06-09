# SqliteDatabase::InsertSettings(INotificationHandlerSettings *)

- ea: `0x18000fe3c`
- end: `0x1800102ea`
- name: `?InsertSettings@SqliteDatabase@@AEAAXPEAUINotificationHandlerSettings@@@Z`
- size: `1198`
- prototype: `void __fastcall(SqliteDatabase *__hidden this, struct INotificationHandlerSettings *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a840`
- `0x18000aa38`
- `0x180087e60`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x18000fe3c`
- `0x180011b10`
- `0x180014340`
- `0x18001592c`
- `0x18001624c`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001024f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001026a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001024f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001026a`
- `winsqlite3!sqlite3_bind_text16` at `0x180010012`
- `winsqlite3!sqlite3_bind_text16` at `0x180010090`
- `winsqlite3!sqlite3_bind_text16` at `0x180010012`
- `winsqlite3!sqlite3_bind_text16` at `0x180010090`
- `winsqlite3!sqlite3_bind_int` at `0x18001004d`
- `winsqlite3!sqlite3_bind_int` at `0x18001004d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SqliteDatabase::InsertSettings(SqliteDatabase *this, struct INotificationHandlerSettings *a2)
{
  __int64 (__fastcall *v4)(struct INotificationHandlerSettings *, __int64 *); // rbx
  int v5; // eax
  int v6; // eax
  void *v7; // rcx
  __int64 v8; // rbx
  int (__fastcall *v9)(__int64, LPVOID *, unsigned int *); // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rax
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16; // rdx
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rbx
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v25; // [rsp+20h] [rbp-49h]
  __int128 v26; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v27[8]; // [rsp+40h] [rbp-29h] BYREF
  volatile signed __int32 *v28; // [rsp+48h] [rbp-21h]
  LPVOID pv; // [rsp+50h] [rbp-19h] BYREF
  __int64 v30; // [rsp+58h] [rbp-11h]
  __int64 v31; // [rsp+60h] [rbp-9h]
  LPVOID v32; // [rsp+68h] [rbp-1h] BYREF
  __int64 v33; // [rsp+70h] [rbp+7h]
  __int64 v34; // [rsp+78h] [rbp+Fh]
  __int128 v35; // [rsp+80h] [rbp+17h] BYREF
  std::_Ref_count_base *v36[2]; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v38; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v39; // [rsp+E0h] [rbp+77h] BYREF
  __int128 *v40; // [rsp+E8h] [rbp+7Fh]

  v39 = 0;
  v4 = *(__int64 (__fastcall **)(struct INotificationHandlerSettings *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  v5 = v4(a2, &v39);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAFD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v5,
      v25);
  v32 = 0;
  v33 = -1;
  v34 = -1;
  v6 = (*(__int64 (__fastcall **)(struct INotificationHandlerSettings *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, &v32);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB00,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v6,
      v25);
  v7 = 0;
  pv = 0;
  v30 = 0;
  v31 = 0;
  v38 = 0;
  while ( 1 )
  {
    v8 = v39;
    v9 = *(int (__fastcall **)(__int64, LPVOID *, unsigned int *))(*(_QWORD *)v39 + 24LL);
    if ( v7 )
    {
      CoTaskMemFree(v7);
      pv = 0;
    }
    v30 = -1;
    v31 = -1;
    if ( v9(v8, &pv, &v38) < 0 )
      break;
    v26 = 0;
    v10 = *((_QWORD *)this + 7);
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v11 = *((_QWORD *)this + 6);
    *(_QWORD *)&v26 = v11;
    v12 = *((_QWORD *)this + 7);
    *((_QWORD *)&v26 + 1) = v12;
    v40 = &v26;
    v35 = 0;
    *(_OWORD *)v36 = 0;
    if ( v12 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
      v12 = *((_QWORD *)&v26 + 1);
      v11 = v26;
    }
    *(_QWORD *)&v35 = v11;
    v13 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
    *((_QWORD *)&v35 + 1) = v12;
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    v14 = Database::PrepareFromCache(
            v35,
            v27,
            "INSERT INTO [HandlerSettings] ([HandlerId], [SettingKey], [Value]) SELECT [RecordId], ?, ? FROM [Notificatio"
            "nHandler] WHERE [PrimaryId]=?");
    v15 = *(std::_Ref_count_base **)v14;
    v16 = *(std::_Ref_count_base **)(v14 + 8);
    *(_QWORD *)v14 = 0;
    *(_QWORD *)(v14 + 8) = 0;
    v36[0] = v15;
    v17 = (volatile signed __int32 *)v36[1];
    v36[1] = v16;
    if ( v17 && _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v17);
    }
    v18 = v28;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v19 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
    if ( *((_QWORD *)&v26 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    if ( !*(_QWORD *)v36[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        v25);
    v20 = sqlite3_bind_text16(*(_QWORD *)v36[0], 1, pv, 0xFFFFFFFFLL);
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x87AF0000;
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)(unsigned int)v20,
        -1);
    if ( !*(_QWORD *)v36[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        -1);
    v21 = sqlite3_bind_int(*(_QWORD *)v36[0], 2, v38);
    if ( v21 > 0 )
      v21 = (unsigned __int16)v21 | 0x87AF0000;
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)(unsigned int)v21,
        -1);
    if ( !*(_QWORD *)v36[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        -1);
    v25 = -1;
    v22 = sqlite3_bind_text16(*(_QWORD *)v36[0], 3, v32, 0xFFFFFFFFLL);
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x87AF0000;
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)(unsigned int)v22,
        -1);
    if ( !*(_QWORD *)v36[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        -1);
    v23 = Statement::dal_step(*(struct sqlite3_stmt **)v36[0]);
    if ( v23 != -2018574235 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)v23,
        -1);
    AutoAddToCache::~AutoAddToCache((AutoAddToCache *)&v35);
    v7 = pv;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v30 = 0;
  v31 = 0;
  if ( v32 )
  {
    CoTaskMemFree(v32);
    v32 = 0;
  }
  v33 = 0;
  v34 = 0;
  v24 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
}

```

## disassembly

```asm
0x18000fe3c  mov     [rsp-8+arg_0], rbx
0x18000fe41  push    rbp
0x18000fe42  push    rsi
0x18000fe43  push    rdi
0x18000fe44  push    r14
0x18000fe46  push    r15
0x18000fe48  lea     rbp, [rsp-37h]
0x18000fe4d  sub     rsp, 0A0h
0x18000fe54  mov     rdi, rdx
0x18000fe57  mov     rsi, rcx
0x18000fe5a  xor     r14d, r14d
0x18000fe5d  mov     [rbp+57h+arg_10], r14
0x18000fe61  mov     rax, [rdx]
0x18000fe64  mov     rbx, [rax+30h]
0x18000fe68  lea     rcx, [rbp+57h+arg_10]
0x18000fe6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fe71  lea     rdx, [rbp+57h+arg_10]
0x18000fe75  mov     rcx, rdi
0x18000fe78  mov     rax, rbx
0x18000fe7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe80  mov     rcx, [rbp+5Fh]; this
0x18000fe84  test    eax, eax
0x18000fe86  js      loc_1800102AD
0x18000fe8c  mov     [rbp+57h+var_58], r14
0x18000fe90  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000fe94  mov     [rbp+57h+var_50], r15
0x18000fe98  mov     [rbp+57h+var_48], r15
0x18000fe9c  mov     rax, [rdi]
0x18000fe9f  lea     rdx, [rbp+57h+var_58]
0x18000fea3  mov     rcx, rdi
0x18000fea6  mov     rax, [rax+18h]
0x18000feaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feaf  mov     rcx, [rbp+5Fh]; this
0x18000feb3  test    eax, eax
0x18000feb5  js      loc_1800102C2
0x18000febb  mov     ecx, r14d; pv
0x18000febe  mov     [rbp+57h+pv], rcx
0x18000fec2  mov     [rbp+57h+var_68], r14
0x18000fec6  mov     [rbp+57h+var_60], r14
0x18000feca  mov     [rbp+57h+arg_8], r14d
0x18000fece  mov     rbx, [rbp+57h+arg_10]
0x18000fed2  mov     rax, [rbx]
0x18000fed5  mov     rdi, [rax+18h]
0x18000fed9  test    rcx, rcx
0x18000fedc  jz      short loc_18000FEE8
0x18000fede  call    cs:__imp_CoTaskMemFree
0x18000fee4  mov     [rbp+57h+pv], r14
0x18000fee8  mov     [rbp+57h+var_68], r15
0x18000feec  mov     [rbp+57h+var_60], r15
0x18000fef0  lea     r8, [rbp+57h+arg_8]
0x18000fef4  lea     rdx, [rbp+57h+pv]
0x18000fef8  mov     rcx, rbx
0x18000fefb  mov     rax, rdi
0x18000fefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff03  test    eax, eax
0x18000ff05  js      loc_180010246
0x18000ff0b  xorps   xmm0, xmm0
0x18000ff0e  movdqu  [rbp+57h+var_90], xmm0
0x18000ff13  mov     rax, [rsi+38h]
0x18000ff17  test    rax, rax
0x18000ff1a  jz      short loc_18000FF20
0x18000ff1c  lock inc dword ptr [rax+8]
0x18000ff20  mov     rcx, [rsi+30h]
0x18000ff24  mov     qword ptr [rbp+57h+var_90], rcx
0x18000ff28  mov     rax, [rsi+38h]
0x18000ff2c  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000ff30  lea     rdx, [rbp+57h+var_90]
0x18000ff34  mov     [rbp+57h+arg_18], rdx
0x18000ff38  movdqu  [rbp+57h+var_40], xmm0
0x18000ff3d  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x18000ff42  test    rax, rax
0x18000ff45  jz      short loc_18000FF53
0x18000ff47  lock inc dword ptr [rax+8]
0x18000ff4b  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18000ff4f  mov     rcx, qword ptr [rbp+57h+var_90]
0x18000ff53  mov     qword ptr [rbp+57h+var_40], rcx
0x18000ff57  mov     rbx, qword ptr [rbp+57h+var_40+8]
0x18000ff5b  mov     qword ptr [rbp+57h+var_40+8], rax
0x18000ff5f  test    rbx, rbx
0x18000ff62  jz      short loc_18000FF75
0x18000ff64  mov     eax, r15d
0x18000ff67  lock xadd [rbx+8], eax
0x18000ff6c  add     eax, r15d
0x18000ff6f  jz      loc_1800101AD
0x18000ff75  lea     r8, aInsertIntoHand_0; "INSERT INTO [HandlerSettings] ([Handler"...
0x18000ff7c  lea     rdx, [rbp+57h+var_80]
0x18000ff80  mov     rcx, qword ptr [rbp+57h+var_40]
0x18000ff84  call    ?PrepareFromCache@Database@@QEAA?AV?$shared_ptr@VStatement@@@std@@PEBD@Z; Database::PrepareFromCache(char const *)
0x18000ff89  mov     rcx, [rax]
0x18000ff8c  mov     rdx, [rax+8]
0x18000ff90  mov     [rax], r14
0x18000ff93  mov     [rax+8], r14
0x18000ff97  mov     [rbp+57h+var_30], rcx
0x18000ff9b  mov     rbx, [rbp+57h+var_30+8]
0x18000ff9f  mov     [rbp+57h+var_30+8], rdx
0x18000ffa3  test    rbx, rbx
0x18000ffa6  jz      short loc_18000FFB9
0x18000ffa8  mov     eax, r15d
0x18000ffab  lock xadd [rbx+8], eax
0x18000ffb0  add     eax, r15d
0x18000ffb3  jz      loc_180010192
0x18000ffb9  mov     rbx, [rbp+57h+var_78]
0x18000ffbd  test    rbx, rbx
0x18000ffc0  jz      short loc_18000FFD3
0x18000ffc2  mov     eax, r15d
0x18000ffc5  lock xadd [rbx+8], eax
0x18000ffca  add     eax, r15d
0x18000ffcd  jz      loc_1800101E0
0x18000ffd3  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x18000ffd7  test    rbx, rbx
0x18000ffda  jz      short loc_18000FFED
0x18000ffdc  mov     eax, r15d
0x18000ffdf  lock xadd [rbx+8], eax
0x18000ffe4  add     eax, r15d
0x18000ffe7  jz      loc_180010213
0x18000ffed  mov     rax, [rbp+57h+var_30]
0x18000fff1  mov     rcx, [rax]
0x18000fff4  mov     rax, [rbp+5Fh]
0x18000fff8  test    rcx, rcx
0x18000fffb  jz      loc_180010138
0x180010001  mov     qword ptr [rsp+0C0h+var_A0], r15; int
0x180010006  mov     r9d, r15d
0x180010009  mov     r8, [rbp+57h+pv]
0x18001000d  mov     edx, 1
0x180010012  call    cs:__imp_sqlite3_bind_text16
0x180010018  test    eax, eax
0x18001001a  jle     short loc_180010024
0x18001001c  movzx   eax, ax
0x18001001f  or      eax, 87AF0000h
0x180010024  mov     rcx, [rbp+5Fh]; this
0x180010028  test    eax, eax
0x18001002a  js      loc_18001017D
0x180010030  mov     rax, [rbp+57h+var_30]
0x180010034  mov     rcx, [rax]
0x180010037  mov     rax, [rbp+5Fh]
0x18001003b  test    rcx, rcx
0x18001003e  jz      loc_18001011D
0x180010044  mov     r8d, [rbp+57h+arg_8]
0x180010048  mov     edx, 2
0x18001004d  call    cs:__imp_sqlite3_bind_int
0x180010053  test    eax, eax
0x180010055  jle     short loc_18001005F
0x180010057  movzx   eax, ax
0x18001005a  or      eax, 87AF0000h
0x18001005f  mov     rcx, [rbp+5Fh]; this
0x180010063  test    eax, eax
0x180010065  js      loc_180010168
0x18001006b  mov     rax, [rbp+57h+var_30]
0x18001006f  mov     rcx, [rax]
0x180010072  mov     rax, [rbp+5Fh]
0x180010076  test    rcx, rcx
0x180010079  jz      loc_180010102
0x18001007f  mov     qword ptr [rsp+0C0h+var_A0], r15; int
0x180010084  mov     r9d, r15d
0x180010087  mov     r8, [rbp+57h+var_58]
0x18001008b  mov     edx, 3
0x180010090  call    cs:__imp_sqlite3_bind_text16
0x180010096  test    eax, eax
0x180010098  jle     short loc_1800100A2
0x18001009a  movzx   eax, ax
0x18001009d  or      eax, 87AF0000h
0x1800100a2  mov     rcx, [rbp+5Fh]; this
0x1800100a6  test    eax, eax
0x1800100a8  js      loc_180010153
0x1800100ae  mov     rax, [rbp+57h+var_30]
0x1800100b2  mov     rcx, [rax]; struct sqlite3_stmt *
0x1800100b5  mov     rax, [rbp+5Fh]
0x1800100b9  test    rcx, rcx
0x1800100bc  jz      short loc_1800100E7
0x1800100be  call    ?dal_step@Statement@@SAJPEAUsqlite3_stmt@@@Z; Statement::dal_step(sqlite3_stmt *)
0x1800100c3  cmp     eax, 87AF0065h
0x1800100c8  jz      loc_1800102D7
0x1800100ce  mov     rcx, [rbp+5Fh]; this
0x1800100d2  mov     r9d, eax; char *
0x1800100d5  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800100dc  mov     edx, 53h ; 'S'; void *
0x1800100e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800100e7  mov     r9d, 8007139Fh; char *
0x1800100ed  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800100f4  mov     edx, 4Ch ; 'L'; void *
0x1800100f9  mov     rcx, rax; this
0x1800100fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010102  mov     r9d, 8007139Fh; char *
0x180010108  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001010f  mov     edx, 100h; void *
0x180010114  mov     rcx, rax; this
0x180010117  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001011d  mov     r9d, 8007139Fh; char *
0x180010123  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001012a  mov     edx, 81h; void *
0x18001012f  mov     rcx, rax; this
0x180010132  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010138  mov     r9d, 8007139Fh; char *
0x18001013e  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010145  mov     edx, 100h; void *
0x18001014a  mov     rcx, rax; this
0x18001014d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010153  mov     r9d, eax; char *
0x180010156  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001015d  mov     edx, 101h; void *
0x180010162  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010168  mov     r9d, eax; char *
0x18001016b  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010172  mov     edx, 82h; void *
0x180010177  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001017d  mov     r9d, eax; char *
0x180010180  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010187  mov     edx, 101h; void *
0x18001018c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010192  mov     rax, [rbx]
0x180010195  mov     rcx, rbx
0x180010198  mov     rax, [rax]
0x18001019b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a0  mov     rcx, rbx; this
0x1800101a3  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800101a8  jmp     loc_18000FFB9
0x1800101ad  mov     rax, [rbx]
0x1800101b0  mov     rcx, rbx
0x1800101b3  mov     rax, [rax]
0x1800101b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101bb  mov     eax, r15d
0x1800101be  lock xadd [rbx+0Ch], eax
0x1800101c3  add     eax, r15d
0x1800101c6  jnz     loc_18000FF75
0x1800101cc  mov     rax, [rbx]
0x1800101cf  mov     rcx, rbx
0x1800101d2  mov     rax, [rax+8]
0x1800101d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101db  jmp     loc_18000FF75
0x1800101e0  mov     rax, [rbx]
0x1800101e3  mov     rcx, rbx
0x1800101e6  mov     rax, [rax]
0x1800101e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101ee  mov     eax, r15d
0x1800101f1  lock xadd [rbx+0Ch], eax
0x1800101f6  add     eax, r15d
0x1800101f9  jnz     loc_18000FFD3
0x1800101ff  mov     rax, [rbx]
0x180010202  mov     rcx, rbx
0x180010205  mov     rax, [rax+8]
0x180010209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001020e  jmp     loc_18000FFD3
0x180010213  mov     rax, [rbx]
0x180010216  mov     rcx, rbx
0x180010219  mov     rax, [rax]
0x18001021c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010221  mov     eax, r15d
0x180010224  lock xadd [rbx+0Ch], eax
0x180010229  add     eax, r15d
0x18001022c  jnz     loc_18000FFED
0x180010232  mov     rax, [rbx]
0x180010235  mov     rcx, rbx
0x180010238  mov     rax, [rax+8]
0x18001023c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010241  jmp     loc_18000FFED
0x180010246  mov     rcx, [rbp+57h+pv]; pv
0x18001024a  test    rcx, rcx
0x18001024d  jz      short loc_180010259
0x18001024f  call    cs:__imp_CoTaskMemFree
0x180010255  mov     [rbp+57h+pv], r14
0x180010259  mov     [rbp+57h+var_68], r14
0x18001025d  mov     [rbp+57h+var_60], r14
0x180010261  mov     rcx, [rbp+57h+var_58]; pv
0x180010265  test    rcx, rcx
0x180010268  jz      short loc_180010274
0x18001026a  call    cs:__imp_CoTaskMemFree
0x180010270  mov     [rbp+57h+var_58], r14
0x180010274  mov     [rbp+57h+var_50], r14
0x180010278  mov     [rbp+57h+var_48], r14
0x18001027c  mov     rcx, [rbp+57h+arg_10]
0x180010280  test    rcx, rcx
0x180010283  jz      short loc_180010296
0x180010285  mov     [rbp+57h+arg_10], r14
0x180010289  mov     rax, [rcx]
0x18001028c  mov     rax, [rax+10h]
0x180010290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010295  nop
0x180010296  mov     rbx, [rsp+0C0h+arg_0]
0x18001029e  add     rsp, 0A0h
0x1800102a5  pop     r15
0x1800102a7  pop     r14
0x1800102a9  pop     rdi
0x1800102aa  pop     rsi
0x1800102ab  pop     rbp
0x1800102ac  retn
0x1800102ad  mov     r9d, eax; char *
0x1800102b0  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800102b7  mov     edx, 0AFDh; void *
0x1800102bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800102c2  mov     r9d, eax; char *
0x1800102c5  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800102cc  mov     edx, 0B00h; void *
0x1800102d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800102d7  lea     rcx, [rbp+57h+var_40]; this
0x1800102db  call    ??1AutoAddToCache@@QEAA@XZ; AutoAddToCache::~AutoAddToCache(void)
0x1800102e0  mov     rcx, [rbp+57h+pv]
0x1800102e4  jmp     loc_18000FECE
```
