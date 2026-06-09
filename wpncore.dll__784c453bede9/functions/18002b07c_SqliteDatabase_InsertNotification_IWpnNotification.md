# SqliteDatabase::InsertNotification(IWpnNotification *)

- ea: `0x18002b07c`
- end: `0x18002b6cd`
- name: `?InsertNotification@SqliteDatabase@@AEAAXPEAUIWpnNotification@@@Z`
- size: `1617`
- prototype: `void(SqliteDatabase *__hidden this, struct IWpnNotification *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009980`

## callees

- `0x180004e38`
- `0x18000c088`
- `0x18000e598`
- `0x18000e5f4`
- `0x18001575c`
- `0x18001592c`
- `0x180029750`
- `0x180029f44`
- `0x18002b07c`
- `0x18002b6d4`
- `0x18002b744`
- `0x18002b7a8`
- `0x18002ee38`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b54a`
- `winsqlite3!sqlite3_bind_blob` at `0x18002b315`
- `winsqlite3!sqlite3_bind_blob` at `0x18002b315`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall SqliteDatabase::InsertNotification(SqliteDatabase *this, struct IWpnNotification *a2)
{
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  __int64 (__fastcall *v7)(struct IWpnNotification *, struct IStream **); // rbx
  int v8; // eax
  int v9; // eax
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // r8
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  signed int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  NotificationCollection *v21; // rbx
  int v22; // eax
  struct IStream *v23; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  struct IStream *v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  NotificationCollection *v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[16]; // [rsp+60h] [rbp-A0h] BYREF
  struct Statement *v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v37; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v40; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v43; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]
  GUID v49; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *(_OWORD *)v30 = 0;
  v4 = *((_QWORD *)this + 7);
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v30[0] = *((NotificationCollection **)this + 6);
  v30[1] = *((NotificationCollection **)this + 7);
  AutoAddToCache::AutoAddToCache(
    v31,
    v30,
    "INSERT INTO [Notification] ([Id], [HandlerId], [Type], [Payload], [Tag], [Group], [ExpiryTime], [ArrivalTime], [Acti"
    "vityId], [PayloadType], [BootId], [ExpiresOnReboot]) SELECT ?, [RecordId], ?, ?, ?, ?, ?, ?, ?, ?, ?, ? FROM [Notifi"
    "cationHandler] WHERE [PrimaryId]=?");
  v25 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IWpnNotification *, int *))(*(_QWORD *)a2 + 24LL))(a2, &v25);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v5,
      v24);
  Statement::Bind(v32, 1, v25);
  v46 = 0;
  v47 = -1;
  v48 = -1;
  v6 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 40LL))(a2, &v46);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v6,
      v24);
  Statement::Bind(v32, 2, v46);
  v27 = 0;
  v7 = *(__int64 (__fastcall **)(struct IWpnNotification *, struct IStream **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v8 = v7(a2, &v27);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v8,
      v24);
  BindStream(v32, 3, v27);
  v43 = 0;
  v44 = -1;
  v45 = -1;
  v9 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 56LL))(a2, &v43);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7DD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v9,
      v24);
  v10 = (unsigned __int16 *)&word_180124798;
  v11 = (unsigned __int16 *)&word_180124798;
  if ( v43 )
    v11 = v43;
  Statement::Bind(v32, 4, v11);
  v40 = 0;
  v41 = -1;
  v42 = -1;
  v12 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 64LL))(a2, &v40);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v12,
      v24);
  if ( v40 )
    v10 = v40;
  Statement::Bind(v32, 5, v10);
  v28 = 0;
  v13 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v28);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v13,
      v24);
  Statement::Bind(v32, 6, v28);
  v29 = 0;
  v14 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a2 + 88LL))(a2, &v29);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v14,
      v24);
  Statement::Bind(v32, 7, v29);
  v49 = GUID_NULL;
  v15 = (*(__int64 (__fastcall **)(struct IWpnNotification *, GUID *))(*(_QWORD *)a2 + 112LL))(a2, &v49);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7ED,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v15,
      v24);
  if ( !*(_QWORD *)v32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      v24);
  v16 = sqlite3_bind_blob(*(_QWORD *)v32, 8, &v49, 16);
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x87AF0000;
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v16,
      -1);
  v37 = 0;
  v38 = -1;
  v39 = -1;
  v17 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 120LL))(a2, &v37);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v17,
      -1);
  Statement::Bind(v32, 9, v37);
  v33 = 0;
  v18 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a2 + 136LL))(a2, &v33);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v18,
      -1);
  Statement::Bind(v32, 10, v33);
  v26 = 0;
  v19 = (*(__int64 (__fastcall **)(struct IWpnNotification *, int *))(*(_QWORD *)a2 + 128LL))(a2, &v26);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v19,
      -1);
  Statement::Bind(v32, 11, v26);
  pv = 0;
  v35 = -1;
  v36 = -1;
  v20 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a2 + 32LL))(a2, &pv);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7FD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v20,
      -1);
  Statement::Bind(v32, 12, (const unsigned __int16 *)pv);
  Statement::FetchNoRow(v32);
  if ( *((_QWORD *)this + 12) )
  {
    Microsoft::WRL::Details::Make<NotificationCollection,>(v30);
    v21 = v30[0];
    if ( !v30[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x805,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)0x8007000ELL,
        -1);
    NotificationCollection::add_Notification(v30[0], a2);
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64))(**((_QWORD **)this + 12) + 24LL))(
            *((_QWORD *)this + 12),
            1,
            ((unsigned __int64)v21 + 32) & -(__int64)(v21 != 0));
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x807,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v22,
        -1);
    if ( v21 )
      (*(void (__fastcall **)(NotificationCollection *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v35 = 0;
  v36 = 0;
  if ( v37 )
  {
    CoTaskMemFree(v37);
    v37 = 0;
  }
  v38 = 0;
  v39 = 0;
  if ( v40 )
  {
    CoTaskMemFree(v40);
    v40 = 0;
  }
  v41 = 0;
  v42 = 0;
  if ( v43 )
  {
    CoTaskMemFree(v43);
    v43 = 0;
  }
  v44 = 0;
  v45 = 0;
  v23 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( v46 )
  {
    CoTaskMemFree(v46);
    v46 = 0;
  }
  v47 = 0;
  v48 = 0;
  AutoAddToCache::~AutoAddToCache((AutoAddToCache *)v31);
}

```

## disassembly

```asm
0x18002b07c  mov     [rsp-8+arg_10], rbx
0x18002b081  push    rbp
0x18002b082  push    rsi
0x18002b083  push    rdi
0x18002b084  push    r14
0x18002b086  push    r15
0x18002b088  lea     rbp, [rsp-20h]
0x18002b08d  sub     rsp, 120h
0x18002b094  mov     rax, cs:__security_cookie
0x18002b09b  xor     rax, rsp
0x18002b09e  mov     [rbp+40h+var_30], rax
0x18002b0a2  mov     rdi, rdx
0x18002b0a5  mov     rsi, rcx
0x18002b0a8  xorps   xmm0, xmm0
0x18002b0ab  movdqu  xmmword ptr [rsp+140h+var_F0], xmm0
0x18002b0b1  mov     rax, [rcx+38h]
0x18002b0b5  xor     r14d, r14d
0x18002b0b8  test    rax, rax
0x18002b0bb  jz      short loc_18002B0C1
0x18002b0bd  lock inc dword ptr [rax+8]
0x18002b0c1  mov     rax, [rcx+30h]
0x18002b0c5  mov     [rsp+140h+var_F0], rax
0x18002b0ca  mov     rax, [rcx+38h]
0x18002b0ce  mov     [rsp+140h+var_F0+8], rax
0x18002b0d3  lea     r8, aInsertIntoNoti; "INSERT INTO [Notification] ([Id], [Hand"...
0x18002b0da  lea     rdx, [rsp+140h+var_F0]
0x18002b0df  lea     rcx, [rsp+140h+var_E0]
0x18002b0e4  call    ??0AutoAddToCache@@QEAA@V?$shared_ptr@VDatabase@@@std@@PEBD@Z; AutoAddToCache::AutoAddToCache(std::shared_ptr<Database>,char const *)
0x18002b0e9  nop
0x18002b0ea  mov     [rsp+140h+var_110], r14d
0x18002b0ef  mov     rax, [rdi]
0x18002b0f2  lea     rdx, [rsp+140h+var_110]
0x18002b0f7  mov     rcx, rdi
0x18002b0fa  mov     rax, [rax+18h]
0x18002b0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b103  mov     rcx, [rbp+48h]; this
0x18002b107  test    eax, eax
0x18002b109  js      loc_18002B5A4
0x18002b10f  mov     r8d, [rsp+140h+var_110]; int
0x18002b114  mov     edx, 1; int
0x18002b119  mov     rcx, [rsp+140h+var_D0]; this
0x18002b11e  call    ?Bind@Statement@@QEAAXHH@Z; Statement::Bind(int,int)
0x18002b123  mov     [rbp+40h+var_58], r14
0x18002b127  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002b12b  mov     [rbp+40h+var_50], r15
0x18002b12f  mov     [rbp+40h+var_48], r15
0x18002b133  mov     rax, [rdi]
0x18002b136  lea     rdx, [rbp+40h+var_58]
0x18002b13a  mov     rcx, rdi
0x18002b13d  mov     rax, [rax+28h]
0x18002b141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b146  mov     rcx, [rbp+48h]; this
0x18002b14a  test    eax, eax
0x18002b14c  js      loc_18002B5B9
0x18002b152  mov     r8, [rbp+40h+var_58]; unsigned __int16 *
0x18002b156  lea     edx, [r15+3]; int
0x18002b15a  mov     rcx, [rsp+140h+var_D0]; this
0x18002b15f  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x18002b164  mov     [rsp+140h+var_108], r14
0x18002b169  mov     rax, [rdi]
0x18002b16c  mov     rbx, [rax+30h]
0x18002b170  lea     rcx, [rsp+140h+var_108]
0x18002b175  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b17a  lea     rdx, [rsp+140h+var_108]
0x18002b17f  mov     rcx, rdi
0x18002b182  mov     rax, rbx
0x18002b185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b18a  mov     rcx, [rbp+48h]; this
0x18002b18e  test    eax, eax
0x18002b190  js      loc_18002B5CE
0x18002b196  mov     r8, [rsp+140h+var_108]; struct IStream *
0x18002b19b  lea     edx, [r15+4]; int
0x18002b19f  mov     rcx, [rsp+140h+var_D0]; struct Statement *
0x18002b1a4  call    ?BindStream@@YAXPEAVStatement@@HPEAUIStream@@@Z; BindStream(Statement *,int,IStream *)
0x18002b1a9  mov     [rbp+40h+var_70], r14
0x18002b1ad  mov     [rbp+40h+var_68], r15
0x18002b1b1  mov     [rbp+40h+var_60], r15
0x18002b1b5  mov     rax, [rdi]
0x18002b1b8  lea     rdx, [rbp+40h+var_70]
0x18002b1bc  mov     rcx, rdi
0x18002b1bf  mov     rax, [rax+38h]
0x18002b1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1c8  mov     rcx, [rbp+48h]; this
0x18002b1cc  test    eax, eax
0x18002b1ce  js      loc_18002B5E3
0x18002b1d4  mov     rax, [rbp+40h+var_70]
0x18002b1d8  lea     rbx, word_180124798
0x18002b1df  mov     r8, rbx
0x18002b1e2  test    rax, rax
0x18002b1e5  cmovnz  r8, rax; unsigned __int16 *
0x18002b1e9  lea     edx, [r15+5]; int
0x18002b1ed  mov     rcx, [rsp+140h+var_D0]; this
0x18002b1f2  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x18002b1f7  mov     [rbp+40h+var_88], r14
0x18002b1fb  mov     [rbp+40h+var_80], r15
0x18002b1ff  mov     [rbp+40h+var_78], r15
0x18002b203  mov     rax, [rdi]
0x18002b206  lea     rdx, [rbp+40h+var_88]
0x18002b20a  mov     rcx, rdi
0x18002b20d  mov     rax, [rax+40h]
0x18002b211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b216  mov     rcx, [rbp+48h]; this
0x18002b21a  test    eax, eax
0x18002b21c  js      loc_18002B5F8
0x18002b222  mov     rax, [rbp+40h+var_88]
0x18002b226  test    rax, rax
0x18002b229  cmovnz  rbx, rax
0x18002b22d  mov     r8, rbx; unsigned __int16 *
0x18002b230  lea     edx, [r15+6]; int
0x18002b234  mov     rcx, [rsp+140h+var_D0]; this
0x18002b239  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x18002b23e  mov     [rsp+140h+var_100], r14
0x18002b243  mov     rax, [rdi]
0x18002b246  lea     rdx, [rsp+140h+var_100]
0x18002b24b  mov     rcx, rdi
0x18002b24e  mov     rax, [rax+48h]
0x18002b252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b257  mov     rcx, [rbp+48h]; this
0x18002b25b  test    eax, eax
0x18002b25d  js      loc_18002B60D
0x18002b263  mov     r8d, dword ptr [rsp+140h+var_100+4]
0x18002b268  shl     r8, 20h
0x18002b26c  mov     eax, dword ptr [rsp+140h+var_100]
0x18002b270  or      r8, rax; __int64
0x18002b273  lea     edx, [r15+7]; int
0x18002b277  mov     rcx, [rsp+140h+var_D0]; this
0x18002b27c  call    ?Bind@Statement@@QEAAXH_J@Z; Statement::Bind(int,__int64)
0x18002b281  mov     [rsp+140h+var_F8], r14
0x18002b286  mov     rax, [rdi]
0x18002b289  lea     rdx, [rsp+140h+var_F8]
0x18002b28e  mov     rcx, rdi
0x18002b291  mov     rax, [rax+58h]
0x18002b295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b29a  mov     rcx, [rbp+48h]; this
0x18002b29e  test    eax, eax
0x18002b2a0  js      loc_18002B622
0x18002b2a6  mov     r8d, dword ptr [rsp+140h+var_F8+4]
0x18002b2ab  shl     r8, 20h
0x18002b2af  mov     eax, dword ptr [rsp+140h+var_F8]
0x18002b2b3  or      r8, rax; __int64
0x18002b2b6  lea     edx, [r15+8]; int
0x18002b2ba  mov     rcx, [rsp+140h+var_D0]; this
0x18002b2bf  call    ?Bind@Statement@@QEAAXH_J@Z; Statement::Bind(int,__int64)
0x18002b2c4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002b2cb  movdqu  [rbp+40h+var_40], xmm0
0x18002b2d0  mov     rax, [rdi]
0x18002b2d3  lea     rdx, [rbp+40h+var_40]
0x18002b2d7  mov     rcx, rdi
0x18002b2da  mov     rax, [rax+70h]
0x18002b2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2e3  mov     rcx, [rbp+48h]; this
0x18002b2e7  test    eax, eax
0x18002b2e9  js      loc_18002B637
0x18002b2ef  mov     rax, [rsp+140h+var_D0]
0x18002b2f4  mov     rcx, [rax]
0x18002b2f7  mov     rax, [rbp+48h]
0x18002b2fb  test    rcx, rcx
0x18002b2fe  jz      loc_18002B589
0x18002b304  mov     qword ptr [rsp+140h+var_120], r15; int
0x18002b309  lea     r9d, [r15+11h]
0x18002b30d  lea     r8, [rbp+40h+var_40]
0x18002b311  lea     edx, [r15+9]
0x18002b315  call    cs:__imp_sqlite3_bind_blob
0x18002b31b  test    eax, eax
0x18002b31d  jle     short loc_18002B327
0x18002b31f  movzx   eax, ax
0x18002b322  or      eax, 87AF0000h
0x18002b327  mov     rcx, [rbp+48h]; this
0x18002b32b  test    eax, eax
0x18002b32d  js      loc_18002B64C
0x18002b333  mov     [rbp+40h+var_A0], r14
0x18002b337  mov     [rbp+40h+var_98], r15
0x18002b33b  mov     [rbp+40h+var_90], r15
0x18002b33f  mov     rax, [rdi]
0x18002b342  lea     rdx, [rbp+40h+var_A0]
0x18002b346  mov     rcx, rdi
0x18002b349  mov     rax, [rax+78h]
0x18002b34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b352  mov     rcx, [rbp+48h]; this
0x18002b356  test    eax, eax
0x18002b358  js      loc_18002B661
0x18002b35e  mov     r8, [rbp+40h+var_A0]; unsigned __int16 *
0x18002b362  mov     edx, 9; int
0x18002b367  mov     rcx, [rsp+140h+var_D0]; this
0x18002b36c  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x18002b371  mov     [rbp+40h+var_C0], r14
0x18002b375  mov     rax, [rdi]
0x18002b378  lea     rdx, [rbp+40h+var_C0]
0x18002b37c  mov     rcx, rdi
0x18002b37f  mov     rax, [rax+88h]
0x18002b386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b38b  mov     rcx, [rbp+48h]; this
0x18002b38f  test    eax, eax
0x18002b391  js      loc_18002B676
0x18002b397  mov     r8, [rbp+40h+var_C0]; __int64
0x18002b39b  mov     edx, 0Ah; int
0x18002b3a0  mov     rcx, [rsp+140h+var_D0]; this
0x18002b3a5  call    ?Bind@Statement@@QEAAXH_J@Z; Statement::Bind(int,__int64)
0x18002b3aa  mov     [rsp+140h+var_10C], r14d
0x18002b3af  mov     rax, [rdi]
0x18002b3b2  lea     rdx, [rsp+140h+var_10C]
0x18002b3b7  mov     rcx, rdi
0x18002b3ba  mov     rax, [rax+80h]
0x18002b3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3c6  mov     rcx, [rbp+48h]; this
0x18002b3ca  test    eax, eax
0x18002b3cc  js      loc_18002B68B
0x18002b3d2  mov     r8d, [rsp+140h+var_10C]; int
0x18002b3d7  mov     edx, 0Bh; int
0x18002b3dc  mov     rcx, [rsp+140h+var_D0]; this
0x18002b3e1  call    ?Bind@Statement@@QEAAXHH@Z; Statement::Bind(int,int)
0x18002b3e6  mov     [rbp+40h+pv], r14
0x18002b3ea  mov     [rbp+40h+var_B0], r15
0x18002b3ee  mov     [rbp+40h+var_A8], r15
0x18002b3f2  mov     rax, [rdi]
0x18002b3f5  lea     rdx, [rbp+40h+pv]
0x18002b3f9  mov     rcx, rdi
0x18002b3fc  mov     rax, [rax+20h]
0x18002b400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b405  mov     rcx, [rbp+48h]; this
0x18002b409  test    eax, eax
0x18002b40b  js      loc_18002B6A0
0x18002b411  mov     r8, [rbp+40h+pv]; unsigned __int16 *
0x18002b415  mov     edx, 0Ch; int
0x18002b41a  mov     rcx, [rsp+140h+var_D0]; this
0x18002b41f  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x18002b424  mov     rcx, [rsp+140h+var_D0]; this
0x18002b429  call    ?FetchNoRow@Statement@@QEAAXXZ; Statement::FetchNoRow(void)
0x18002b42e  cmp     [rsi+60h], r14
0x18002b432  jz      loc_18002B4B9
0x18002b438  lea     rcx, [rsp+140h+var_F0]
0x18002b43d  call    ??$Make@VNotificationCollection@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VNotificationCollection@@@12@XZ; Microsoft::WRL::Details::Make<NotificationCollection,>(void)
0x18002b442  nop
0x18002b443  mov     rcx, [rbp+48h]; this
0x18002b447  mov     rbx, [rsp+140h+var_F0]
0x18002b44c  test    rbx, rbx
0x18002b44f  jz      loc_18002B6B5
0x18002b455  mov     rdx, rdi; struct IWpnNotification *
0x18002b458  mov     rcx, rbx; this
0x18002b45b  call    ?add_Notification@NotificationCollection@@QEAAJPEAUIWpnNotification@@@Z; NotificationCollection::add_Notification(IWpnNotification *)
0x18002b460  mov     rcx, [rsi+60h]
0x18002b464  mov     r10, [rcx]
0x18002b467  mov     rax, rbx
0x18002b46a  lea     r9, [rbx+20h]
0x18002b46e  neg     rax
0x18002b471  sbb     r8, r8
0x18002b474  and     r8, r9
0x18002b477  xor     r9d, r9d
0x18002b47a  lea     edx, [r9+1]
0x18002b47e  mov     rax, [r10+18h]
0x18002b482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b487  mov     rcx, [rbp+48h]; this
0x18002b48b  test    eax, eax
0x18002b48d  jns     short loc_18002B4A4
0x18002b48f  mov     r9d, eax; char *
0x18002b492  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002b499  mov     edx, 807h; void *
0x18002b49e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b4a3  nop
0x18002b4a4  test    rbx, rbx
0x18002b4a7  jz      short loc_18002B4B9
0x18002b4a9  mov     rax, [rbx]
0x18002b4ac  mov     rcx, rbx
0x18002b4af  mov     rax, [rax+10h]
0x18002b4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4b8  nop
0x18002b4b9  mov     rcx, [rbp+40h+pv]; pv
0x18002b4bd  test    rcx, rcx
0x18002b4c0  jz      short loc_18002B4CC
0x18002b4c2  call    cs:__imp_CoTaskMemFree
0x18002b4c8  mov     [rbp+40h+pv], r14
0x18002b4cc  mov     [rbp+40h+var_B0], r14
0x18002b4d0  mov     [rbp+40h+var_A8], r14
0x18002b4d4  mov     rcx, [rbp+40h+var_A0]; pv
0x18002b4d8  test    rcx, rcx
0x18002b4db  jz      short loc_18002B4E7
0x18002b4dd  call    cs:__imp_CoTaskMemFree
0x18002b4e3  mov     [rbp+40h+var_A0], r14
0x18002b4e7  mov     [rbp+40h+var_98], r14
0x18002b4eb  mov     [rbp+40h+var_90], r14
0x18002b4ef  mov     rcx, [rbp+40h+var_88]; pv
0x18002b4f3  test    rcx, rcx
0x18002b4f6  jz      short loc_18002B502
0x18002b4f8  call    cs:__imp_CoTaskMemFree
0x18002b4fe  mov     [rbp+40h+var_88], r14
0x18002b502  mov     [rbp+40h+var_80], r14
0x18002b506  mov     [rbp+40h+var_78], r14
0x18002b50a  mov     rcx, [rbp+40h+var_70]; pv
0x18002b50e  test    rcx, rcx
0x18002b511  jz      short loc_18002B51D
0x18002b513  call    cs:__imp_CoTaskMemFree
0x18002b519  mov     [rbp+40h+var_70], r14
0x18002b51d  mov     [rbp+40h+var_68], r14
0x18002b521  mov     [rbp+40h+var_60], r14
0x18002b525  mov     rcx, [rsp+140h+var_108]
0x18002b52a  test    rcx, rcx
0x18002b52d  jz      short loc_18002B541
0x18002b52f  mov     [rsp+140h+var_108], r14
0x18002b534  mov     rax, [rcx]
0x18002b537  mov     rax, [rax+10h]
  ... truncated ...
```
