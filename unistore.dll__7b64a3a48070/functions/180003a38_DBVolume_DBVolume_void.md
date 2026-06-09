# DBVolume::~DBVolume(void)

- ea: `0x180003a38`
- end: `0x180003b24`
- name: `??1DBVolume@@UEAA@XZ`
- size: `236`
- prototype: `void __fastcall(DBVolume *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003a00`

## callees

- `0x180003a38`
- `0x180003b2c`
- `0x180003fb0`
- `0x180004130`
- `0x1800041e4`
- `0x180004440`
- `0x18001c2e0`
- `0x180078a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003a9c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ab5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003a9c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b1c`

## pseudocode

```c
void __fastcall DBVolume::~DBVolume(DBVolume *this)
{
  __int64 v2; // rbx
  DBVolume::TablePrimaryKeyRecord *v3; // rsi
  HKEY v4; // rcx
  struct _TP_TIMER *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &DBVolume::`vftable';
  DBVolume::Unmount(this);
  v2 = 54;
  v3 = (DBVolume *)((char *)this + 3712);
  do
  {
    v3 = (DBVolume::TablePrimaryKeyRecord *)((char *)v3 - 64);
    DBVolume::TablePrimaryKeyRecord::~TablePrimaryKeyRecord(v3);
    --v2;
  }
  while ( v2 );
  v4 = (HKEY)*((_QWORD *)this + 31);
  if ( v4 )
    RegCloseKey(v4);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((char *)this + 240);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
  if ( v5 )
    CloseThreadpoolTimer(v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  utl::list<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::clear((char *)this + 128);
  utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_ClearList((char *)this + 88);
  v6 = (void *)*((_QWORD *)this + 13);
  if ( v6 )
    operator delete(v6);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((char *)this + 72);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 40);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((char *)this + 24);
  *(_QWORD *)this = &CUSUnknownImpl<IDBVolume>::`vftable';
}

```

## disassembly

```asm
0x180003a38  mov     [rsp+arg_0], rbx
0x180003a3d  mov     [rsp+arg_8], rsi
0x180003a42  push    rdi
0x180003a43  sub     rsp, 20h
0x180003a47  lea     rax, ??_7DBVolume@@6B@; const DBVolume::`vftable'
0x180003a4e  mov     rdi, rcx
0x180003a51  mov     [rcx], rax
0x180003a54  call    ?Unmount@DBVolume@@EEAAJXZ; DBVolume::Unmount(void)
0x180003a59  mov     ebx, 36h ; '6'
0x180003a5e  lea     rsi, [rdi+0E80h]
0x180003a65  sub     rsi, 40h ; '@'
0x180003a69  mov     rcx, rsi; this
0x180003a6c  call    ??1TablePrimaryKeyRecord@DBVolume@@QEAA@XZ; DBVolume::TablePrimaryKeyRecord::~TablePrimaryKeyRecord(void)
0x180003a71  sub     rbx, 1
0x180003a75  jnz     short loc_180003A65
0x180003a77  mov     rcx, [rdi+0F8h]; hKey
0x180003a7e  test    rcx, rcx
0x180003a81  jz      short loc_180003A89
0x180003a83  call    cs:__imp_RegCloseKey
0x180003a89  lea     rcx, [rdi+0F0h]; void *
0x180003a90  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180003a95  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180003a9c  call    cs:__imp_DeleteCriticalSection
0x180003aa2  mov     rcx, [rdi+0C0h]; pti
0x180003aa9  test    rcx, rcx
0x180003aac  jnz     short loc_180003B1C
0x180003aae  lea     rcx, [rdi+98h]; lpCriticalSection
0x180003ab5  call    cs:__imp_DeleteCriticalSection
0x180003abb  lea     rcx, [rdi+80h]
0x180003ac2  call    ?clear@?$list@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@V?$allocator@U?$pair@UCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::pair<CallerId,ATL::CComPtr<IDBSession>>,utl::allocator<utl::pair<CallerId,ATL::CComPtr<IDBSession>>>>::clear(void)
0x180003ac7  lea     rcx, [rdi+58h]
0x180003acb  call    ?_ClearList@?$_HashTable@UCallerId@@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@U?$hash@UCallerId@@@3@U?$equal_to@UCallerId@@@3@V?$allocator@U?$pair@$$CBUCallerId@@V?$CComPtr@VIDBSession@@@ATL@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<CallerId,utl::pair<CallerId const,ATL::CComPtr<IDBSession>>,utl::hash<CallerId>,utl::equal_to<CallerId>,utl::allocator<utl::pair<CallerId const,ATL::CComPtr<IDBSession>>>,0>::_ClearList(void)
0x180003ad0  mov     rcx, [rdi+68h]; Block
0x180003ad4  test    rcx, rcx
0x180003ad7  jnz     short loc_180003B0E
0x180003ad9  lea     rcx, [rdi+48h]; void *
0x180003add  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180003ae2  lea     rcx, [rdi+28h]
0x180003ae6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180003aeb  lea     rcx, [rdi+18h]; void *
0x180003aef  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180003af4  mov     rbx, [rsp+28h+arg_0]
0x180003af9  lea     rax, ??_7?$CUSUnknownImpl@VIDBVolume@@@@6B@; const CUSUnknownImpl<IDBVolume>::`vftable'
0x180003b00  mov     rsi, [rsp+28h+arg_8]
0x180003b05  mov     [rdi], rax
0x180003b08  add     rsp, 20h
0x180003b0c  pop     rdi
0x180003b0d  retn
0x180003b0e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180003b15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003b1a  jmp     short loc_180003AD9
0x180003b1c  call    cs:__imp_CloseThreadpoolTimer
0x180003b22  jmp     short loc_180003AAE
```
