# SqliteDatabase::UpdateHandlerInternal(INotificationHandler *)

- ea: `0x18000bb9c`
- end: `0x18000c07f`
- name: `?UpdateHandlerInternal@SqliteDatabase@@AEAAXPEAUINotificationHandler@@@Z`
- size: `1251`
- prototype: `void __fastcall(SqliteDatabase *__hidden this, struct INotificationHandler *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a840`

## callees

- `0x180004e38`
- `0x18000bb9c`
- `0x18000c088`
- `0x18000e598`
- `0x18000e5f4`
- `0x18001575c`
- `0x18001592c`
- `0x18002b744`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000becf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000becf`
- `winsqlite3!sqlite3_bind_null` at `0x18000bcb0`
- `winsqlite3!sqlite3_bind_null` at `0x18000bcb0`
- `winsqlite3!sqlite3_bind_text16` at `0x18000bc46`
- `winsqlite3!sqlite3_bind_text16` at `0x18000bd5d`
- `winsqlite3!sqlite3_bind_text16` at `0x18000bdc9`
- `winsqlite3!sqlite3_bind_text16` at `0x18000be35`
- `winsqlite3!sqlite3_bind_text16` at `0x18000bc46`
- `winsqlite3!sqlite3_bind_text16` at `0x18000bd5d`
- `winsqlite3!sqlite3_bind_text16` at `0x18000bdc9`
- `winsqlite3!sqlite3_bind_text16` at `0x18000be35`

## string_xrefs

- `0x18000bbde`: `UPDATE [NotificationHandler] SET [HandlerType]=?, [WNFEventName]=?, [SystemDataPropertySet]=?, [ModifiedTime]=datetime('now'), [ParentId]=?, [ContainerSid]=? WHERE [PrimaryId]=?`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall SqliteDatabase::UpdateHandlerInternal(SqliteDatabase *this, struct INotificationHandler *a2)
{
  __int64 v3; // rax
  int v4; // eax
  signed int v5; // eax
  int v6; // eax
  signed int v7; // eax
  __int64 (__fastcall *v8)(struct INotificationHandler *, struct IStream **); // rbx
  int v9; // eax
  int v10; // eax
  signed int v11; // eax
  int v12; // eax
  signed int v13; // eax
  int v14; // eax
  signed int v15; // eax
  struct IStream *v16; // rcx
  int v17; // [rsp+20h] [rbp-69h]
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  __int64 v19; // [rsp+38h] [rbp-51h]
  __int64 v20; // [rsp+40h] [rbp-49h]
  LPVOID v21; // [rsp+48h] [rbp-41h] BYREF
  __int64 v22; // [rsp+50h] [rbp-39h]
  __int64 v23; // [rsp+58h] [rbp-31h]
  LPVOID v24; // [rsp+60h] [rbp-29h] BYREF
  __int64 v25; // [rsp+68h] [rbp-21h]
  __int64 v26; // [rsp+70h] [rbp-19h]
  LPVOID v27; // [rsp+78h] [rbp-11h] BYREF
  __int64 v28; // [rsp+80h] [rbp-9h]
  __int64 v29; // [rsp+88h] [rbp-1h]
  __int128 v30; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v31[16]; // [rsp+A0h] [rbp+17h] BYREF
  struct Statement *v32; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  struct IStream *v34; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v35; // [rsp+F8h] [rbp+6Fh] BYREF

  v30 = 0;
  v3 = *((_QWORD *)this + 7);
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v30 = *((_OWORD *)this + 3);
  AutoAddToCache::AutoAddToCache(
    v31,
    &v30,
    "UPDATE [NotificationHandler] SET [HandlerType]=?, [WNFEventName]=?, [SystemDataPropertySet]=?, [ModifiedTime]=dateti"
    "me('now'), [ParentId]=?, [ContainerSid]=? WHERE [PrimaryId]=?");
  v27 = 0;
  v28 = -1;
  v29 = -1;
  v4 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 48LL))(a2, &v27);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v4,
      v17);
  if ( !*(_QWORD *)v32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      v17);
  v5 = sqlite3_bind_text16(*(_QWORD *)v32, 1, v27, 0xFFFFFFFFLL);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x87AF0000;
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v5,
      -1);
  v35 = 0;
  v6 = (*(__int64 (__fastcall **)(struct INotificationHandler *, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v35);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v6,
      -1);
  if ( v35 )
  {
    Statement::Bind(v32, 2, v35);
  }
  else
  {
    if ( !*(_QWORD *)v32 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        -1);
    v7 = sqlite3_bind_null(*(_QWORD *)v32, (unsigned int)(v35 + 2));
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x87AF0000;
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)(unsigned int)v7,
        -1);
  }
  v34 = 0;
  v8 = *(__int64 (__fastcall **)(struct INotificationHandler *, struct IStream **))(*(_QWORD *)a2 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v9 = v8(a2, &v34);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB32,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v9,
      -1);
  BindStream(v32, 3, v34);
  v24 = 0;
  v25 = -1;
  v26 = -1;
  v10 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &v24);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB36,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v10,
      -1);
  if ( !*(_QWORD *)v32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v11 = sqlite3_bind_text16(*(_QWORD *)v32, 4, v24, 0xFFFFFFFFLL);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x87AF0000;
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v11,
      -1);
  v21 = 0;
  v22 = -1;
  v23 = -1;
  v12 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 104LL))(a2, &v21);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v12,
      -1);
  if ( !*(_QWORD *)v32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v13 = sqlite3_bind_text16(*(_QWORD *)v32, 5, v21, 0xFFFFFFFFLL);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x87AF0000;
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v13,
      -1);
  pv = 0;
  v19 = -1;
  v20 = -1;
  v14 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, &pv);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v14,
      -1);
  if ( !*(_QWORD *)v32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v15 = sqlite3_bind_text16(*(_QWORD *)v32, 6, pv, 0xFFFFFFFFLL);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x87AF0000;
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v15,
      -1);
  Statement::FetchNoRow(v32);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v19 = 0;
  v20 = 0;
  if ( v21 )
  {
    CoTaskMemFree(v21);
    v21 = 0;
  }
  v22 = 0;
  v23 = 0;
  if ( v24 )
  {
    CoTaskMemFree(v24);
    v24 = 0;
  }
  v25 = 0;
  v26 = 0;
  v16 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( v27 )
  {
    CoTaskMemFree(v27);
    v27 = 0;
  }
  v28 = 0;
  v29 = 0;
  AutoAddToCache::~AutoAddToCache((AutoAddToCache *)v31);
}

```

## disassembly

```asm
0x18000bb9c  mov     [rsp-8+arg_10], rbx
0x18000bba1  push    rbp
0x18000bba2  push    rsi
0x18000bba3  push    rdi
0x18000bba4  push    r14
0x18000bba6  push    r15
0x18000bba8  lea     rbp, [rsp-37h]
0x18000bbad  sub     rsp, 0C0h
0x18000bbb4  mov     rdi, rdx
0x18000bbb7  xorps   xmm0, xmm0
0x18000bbba  movdqu  [rbp+57h+var_50], xmm0
0x18000bbbf  mov     rax, [rcx+38h]
0x18000bbc3  xor     esi, esi
0x18000bbc5  test    rax, rax
0x18000bbc8  jz      short loc_18000BBCE
0x18000bbca  lock inc dword ptr [rax+8]
0x18000bbce  mov     rax, [rcx+30h]
0x18000bbd2  mov     qword ptr [rbp+57h+var_50], rax
0x18000bbd6  mov     rax, [rcx+38h]
0x18000bbda  mov     qword ptr [rbp+57h+var_50+8], rax
0x18000bbde  lea     r8, aUpdateNotifica_1; "UPDATE [NotificationHandler] SET [Handl"...
0x18000bbe5  lea     rdx, [rbp+57h+var_50]
0x18000bbe9  lea     rcx, [rbp+57h+var_40]
0x18000bbed  call    ??0AutoAddToCache@@QEAA@V?$shared_ptr@VDatabase@@@std@@PEBD@Z; AutoAddToCache::AutoAddToCache(std::shared_ptr<Database>,char const *)
0x18000bbf2  nop
0x18000bbf3  mov     [rbp+57h+var_68], rsi
0x18000bbf7  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000bbfb  mov     [rbp+57h+var_60], r14
0x18000bbff  mov     [rbp+57h+var_58], r14
0x18000bc03  mov     rax, [rdi]
0x18000bc06  lea     rdx, [rbp+57h+var_68]
0x18000bc0a  mov     rcx, rdi
0x18000bc0d  mov     rax, [rax+30h]
0x18000bc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc16  mov     rcx, [rbp+5Fh]; this
0x18000bc1a  test    eax, eax
0x18000bc1c  js      loc_18000BF6D
0x18000bc22  mov     rax, [rbp+57h+var_30]
0x18000bc26  mov     rcx, [rax]
0x18000bc29  mov     rax, [rbp+5Fh]
0x18000bc2d  test    rcx, rcx
0x18000bc30  jz      loc_18000BF01
0x18000bc36  mov     qword ptr [rsp+0E0h+var_C0], r14; int
0x18000bc3b  mov     r9d, r14d
0x18000bc3e  mov     r8, [rbp+57h+var_68]
0x18000bc42  lea     edx, [r14+2]
0x18000bc46  call    cs:__imp_sqlite3_bind_text16
0x18000bc4c  mov     r15d, 87AF0000h
0x18000bc52  test    eax, eax
0x18000bc54  jle     short loc_18000BC5C
0x18000bc56  movzx   eax, ax
0x18000bc59  or      eax, r15d
0x18000bc5c  mov     rcx, [rbp+5Fh]; this
0x18000bc60  test    eax, eax
0x18000bc62  js      loc_18000BF82
0x18000bc68  mov     [rbp+57h+arg_8], rsi
0x18000bc6c  mov     rax, [rdi]
0x18000bc6f  lea     rdx, [rbp+57h+arg_8]
0x18000bc73  mov     rcx, rdi
0x18000bc76  mov     rax, [rax+40h]
0x18000bc7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc7f  mov     rcx, [rbp+5Fh]; this
0x18000bc83  test    eax, eax
0x18000bc85  js      loc_18000BF97
0x18000bc8b  mov     r8, [rbp+57h+arg_8]; __int64
0x18000bc8f  mov     rcx, [rbp+57h+var_30]; this
0x18000bc93  test    r8, r8
0x18000bc96  jnz     loc_18000C06F
0x18000bc9c  mov     rcx, [rcx]
0x18000bc9f  mov     rax, [rbp+5Fh]
0x18000bca3  test    rcx, rcx
0x18000bca6  jz      loc_18000C03F
0x18000bcac  lea     edx, [r8+2]
0x18000bcb0  call    cs:__imp_sqlite3_bind_null
0x18000bcb6  test    eax, eax
0x18000bcb8  jle     short loc_18000BCC0
0x18000bcba  movzx   eax, ax
0x18000bcbd  or      eax, r15d
0x18000bcc0  mov     rcx, [rbp+5Fh]; this
0x18000bcc4  test    eax, eax
0x18000bcc6  js      loc_18000C05A
0x18000bccc  mov     [rbp+57h+arg_0], rsi
0x18000bcd0  mov     rax, [rdi]
0x18000bcd3  mov     rbx, [rax+50h]
0x18000bcd7  lea     rcx, [rbp+57h+arg_0]
0x18000bcdb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000bce0  lea     rdx, [rbp+57h+arg_0]
0x18000bce4  mov     rcx, rdi
0x18000bce7  mov     rax, rbx
0x18000bcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcef  mov     rcx, [rbp+5Fh]; this
0x18000bcf3  test    eax, eax
0x18000bcf5  js      loc_18000BFAC
0x18000bcfb  mov     r8, [rbp+57h+arg_0]; struct IStream *
0x18000bcff  mov     edx, 3; int
0x18000bd04  mov     rcx, [rbp+57h+var_30]; struct Statement *
0x18000bd08  call    ?BindStream@@YAXPEAVStatement@@HPEAUIStream@@@Z; BindStream(Statement *,int,IStream *)
0x18000bd0d  mov     [rbp+57h+var_80], rsi
0x18000bd11  mov     [rbp+57h+var_78], r14
0x18000bd15  mov     [rbp+57h+var_70], r14
0x18000bd19  mov     rax, [rdi]
0x18000bd1c  lea     rdx, [rbp+57h+var_80]
0x18000bd20  mov     rcx, rdi
0x18000bd23  mov     rax, [rax+28h]
0x18000bd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd2c  mov     rcx, [rbp+5Fh]; this
0x18000bd30  test    eax, eax
0x18000bd32  js      loc_18000BFC1
0x18000bd38  mov     rax, [rbp+57h+var_30]
0x18000bd3c  mov     rcx, [rax]
0x18000bd3f  mov     rax, [rbp+5Fh]
0x18000bd43  test    rcx, rcx
0x18000bd46  jz      loc_18000BF1C
0x18000bd4c  mov     qword ptr [rsp+0E0h+var_C0], r14; int
0x18000bd51  mov     r9d, r14d
0x18000bd54  mov     r8, [rbp+57h+var_80]
0x18000bd58  mov     edx, 4
0x18000bd5d  call    cs:__imp_sqlite3_bind_text16
0x18000bd63  test    eax, eax
0x18000bd65  jle     short loc_18000BD6D
0x18000bd67  movzx   eax, ax
0x18000bd6a  or      eax, r15d
0x18000bd6d  mov     rcx, [rbp+5Fh]; this
0x18000bd71  test    eax, eax
0x18000bd73  js      loc_18000BFD6
0x18000bd79  mov     [rbp+57h+var_98], rsi
0x18000bd7d  mov     [rbp+57h+var_90], r14
0x18000bd81  mov     [rbp+57h+var_88], r14
0x18000bd85  mov     rax, [rdi]
0x18000bd88  lea     rdx, [rbp+57h+var_98]
0x18000bd8c  mov     rcx, rdi
0x18000bd8f  mov     rax, [rax+68h]
0x18000bd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd98  mov     rcx, [rbp+5Fh]; this
0x18000bd9c  test    eax, eax
0x18000bd9e  js      loc_18000BFEB
0x18000bda4  mov     rax, [rbp+57h+var_30]
0x18000bda8  mov     rcx, [rax]
0x18000bdab  mov     rax, [rbp+5Fh]
0x18000bdaf  test    rcx, rcx
0x18000bdb2  jz      loc_18000BF37
0x18000bdb8  mov     qword ptr [rsp+0E0h+var_C0], r14; int
0x18000bdbd  mov     r9d, r14d
0x18000bdc0  mov     r8, [rbp+57h+var_98]
0x18000bdc4  mov     edx, 5
0x18000bdc9  call    cs:__imp_sqlite3_bind_text16
0x18000bdcf  test    eax, eax
0x18000bdd1  jle     short loc_18000BDD9
0x18000bdd3  movzx   eax, ax
0x18000bdd6  or      eax, r15d
0x18000bdd9  mov     rcx, [rbp+5Fh]; this
0x18000bddd  test    eax, eax
0x18000bddf  js      loc_18000C000
0x18000bde5  mov     [rbp+57h+pv], rsi
0x18000bde9  mov     [rbp+57h+var_A8], r14
0x18000bded  mov     [rbp+57h+var_A0], r14
0x18000bdf1  mov     rax, [rdi]
0x18000bdf4  lea     rdx, [rbp+57h+pv]
0x18000bdf8  mov     rcx, rdi
0x18000bdfb  mov     rax, [rax+18h]
0x18000bdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be04  mov     rcx, [rbp+5Fh]; this
0x18000be08  test    eax, eax
0x18000be0a  js      loc_18000C015
0x18000be10  mov     rax, [rbp+57h+var_30]
0x18000be14  mov     rcx, [rax]
0x18000be17  mov     rax, [rbp+5Fh]
0x18000be1b  test    rcx, rcx
0x18000be1e  jz      loc_18000BF52
0x18000be24  mov     qword ptr [rsp+0E0h+var_C0], r14; int
0x18000be29  mov     r9d, r14d
0x18000be2c  mov     r8, [rbp+57h+pv]
0x18000be30  mov     edx, 6
0x18000be35  call    cs:__imp_sqlite3_bind_text16
0x18000be3b  test    eax, eax
0x18000be3d  jle     short loc_18000BE45
0x18000be3f  movzx   eax, ax
0x18000be42  or      eax, r15d
0x18000be45  mov     rcx, [rbp+5Fh]; this
0x18000be49  test    eax, eax
0x18000be4b  js      loc_18000C02A
0x18000be51  mov     rcx, [rbp+57h+var_30]; this
0x18000be55  call    ?FetchNoRow@Statement@@QEAAXXZ; Statement::FetchNoRow(void)
0x18000be5a  nop
0x18000be5b  mov     rcx, [rbp+57h+pv]; pv
0x18000be5f  test    rcx, rcx
0x18000be62  jz      short loc_18000BE6E
0x18000be64  call    cs:__imp_CoTaskMemFree
0x18000be6a  mov     [rbp+57h+pv], rsi
0x18000be6e  mov     [rbp+57h+var_A8], rsi
0x18000be72  mov     [rbp+57h+var_A0], rsi
0x18000be76  mov     rcx, [rbp+57h+var_98]; pv
0x18000be7a  test    rcx, rcx
0x18000be7d  jz      short loc_18000BE89
0x18000be7f  call    cs:__imp_CoTaskMemFree
0x18000be85  mov     [rbp+57h+var_98], rsi
0x18000be89  mov     [rbp+57h+var_90], rsi
0x18000be8d  mov     [rbp+57h+var_88], rsi
0x18000be91  mov     rcx, [rbp+57h+var_80]; pv
0x18000be95  test    rcx, rcx
0x18000be98  jz      short loc_18000BEA4
0x18000be9a  call    cs:__imp_CoTaskMemFree
0x18000bea0  mov     [rbp+57h+var_80], rsi
0x18000bea4  mov     [rbp+57h+var_78], rsi
0x18000bea8  mov     [rbp+57h+var_70], rsi
0x18000beac  mov     rcx, [rbp+57h+arg_0]
0x18000beb0  test    rcx, rcx
0x18000beb3  jz      short loc_18000BEC6
0x18000beb5  mov     [rbp+57h+arg_0], rsi
0x18000beb9  mov     rax, [rcx]
0x18000bebc  mov     rax, [rax+10h]
0x18000bec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bec5  nop
0x18000bec6  mov     rcx, [rbp+57h+var_68]; pv
0x18000beca  test    rcx, rcx
0x18000becd  jz      short loc_18000BED9
0x18000becf  call    cs:__imp_CoTaskMemFree
0x18000bed5  mov     [rbp+57h+var_68], rsi
0x18000bed9  mov     [rbp+57h+var_60], rsi
0x18000bedd  mov     [rbp+57h+var_58], rsi
0x18000bee1  lea     rcx, [rbp+57h+var_40]; this
0x18000bee5  call    ??1AutoAddToCache@@QEAA@XZ; AutoAddToCache::~AutoAddToCache(void)
0x18000beea  mov     rbx, [rsp+0E0h+arg_10]
0x18000bef2  add     rsp, 0C0h
0x18000bef9  pop     r15
0x18000befb  pop     r14
0x18000befd  pop     rdi
0x18000befe  pop     rsi
0x18000beff  pop     rbp
0x18000bf00  retn
0x18000bf01  mov     r9d, 8007139Fh; char *
0x18000bf07  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bf0e  mov     edx, 100h; void *
0x18000bf13  mov     rcx, rax; this
0x18000bf16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bf1c  mov     r9d, 8007139Fh; char *
0x18000bf22  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bf29  mov     edx, 100h; void *
0x18000bf2e  mov     rcx, rax; this
0x18000bf31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bf37  mov     r9d, 8007139Fh; char *
0x18000bf3d  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bf44  mov     edx, 100h; void *
0x18000bf49  mov     rcx, rax; this
0x18000bf4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bf52  mov     r9d, 8007139Fh; char *
0x18000bf58  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bf5f  mov     edx, 100h; void *
0x18000bf64  mov     rcx, rax; this
0x18000bf67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bf6d  mov     r9d, eax; char *
0x18000bf70  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bf77  mov     edx, 0B2Ah; void *
0x18000bf7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bf82  mov     r9d, eax; char *
0x18000bf85  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bf8c  mov     edx, 101h; void *
0x18000bf91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bf97  mov     r9d, eax; char *
0x18000bf9a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bfa1  mov     edx, 0B2Eh; void *
0x18000bfa6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bfac  mov     r9d, eax; char *
0x18000bfaf  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bfb6  mov     edx, 0B32h; void *
0x18000bfbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bfc1  mov     r9d, eax; char *
0x18000bfc4  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bfcb  mov     edx, 0B36h; void *
0x18000bfd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bfd6  mov     r9d, eax; char *
0x18000bfd9  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bfe0  mov     edx, 101h; void *
0x18000bfe5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bfeb  mov     r9d, eax; char *
0x18000bfee  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000bff5  mov     edx, 0B3Ah; void *
0x18000bffa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c000  mov     r9d, eax; char *
0x18000c003  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c00a  mov     edx, 101h; void *
0x18000c00f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c015  mov     r9d, eax; char *
0x18000c018  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c01f  mov     edx, 0B3Eh; void *
0x18000c024  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c02a  mov     r9d, eax; char *
0x18000c02d  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c034  mov     edx, 101h; void *
0x18000c039  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c03f  mov     r9d, 8007139Fh; char *
0x18000c045  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c04c  mov     edx, 65h ; 'e'; void *
0x18000c051  mov     rcx, rax; this
0x18000c054  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c05a  mov     r9d, eax; char *
0x18000c05d  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000c064  mov     edx, 66h ; 'f'; void *
0x18000c069  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c06f  mov     edx, 2; int
  ... truncated ...
```
