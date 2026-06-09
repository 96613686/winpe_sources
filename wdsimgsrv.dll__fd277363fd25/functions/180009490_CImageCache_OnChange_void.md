# CImageCache::OnChange(void)

- ea: `0x180009490`
- end: `0x1800096b0`
- name: `?OnChange@CImageCache@@QEAAKXZ`
- size: `544`
- prototype: `unsigned int __fastcall(CImageCache *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006b10`
- `0x180008f9c`
- `0x1800096b8`
- `0x18000c69c`

## callees

- `0x1800026f8`
- `0x1800028a8`
- `0x1800029e8`
- `0x180006e20`
- `0x18000818c`
- `0x180008364`
- `0x180009460`
- `0x180009490`
- `0x18000ad88`
- `0x18000aeac`
- `0x180013030`
- `0x180017010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009683`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009683`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180009515`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180009515`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180009633`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180009655`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180009633`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180009655`
- `WdsImage!WdsImgOpenImageStore` at `0x1800094f4`
- `WdsImage!WdsImgOpenImageStore` at `0x1800094f4`
- `WdsImage!WdsImgClose` at `0x18000966a`
- `WdsImage!WdsImgClose` at `0x18000966a`

## string_xrefs

- `0x18000953a`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000958d`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x1800095cb`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x1800094d1`: `Image Cache: Refreshing...`
- `0x180009564`: `Image Cache: Total %u Images Found.`

## pseudocode

```c
__int64 __fastcall CImageCache::OnChange(CImageCache *this, __int64 a2, int a3)
{
  struct _GUID *v4; // rbx
  unsigned int v5; // esi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 Item; // rsi
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // r9
  int Action; // eax
  int v15; // [rsp+20h] [rbp-50h]
  _BYTE v16[16]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h] BYREF
  struct _GUID *v18; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+58h] [rbp-18h]
  unsigned int v20; // [rsp+5Ch] [rbp-14h]
  void *v21; // [rsp+90h] [rbp+20h] BYREF
  __int64 v22; // [rsp+98h] [rbp+28h] BYREF

  v21 = 0;
  CAutoWriterLock::CAutoWriterLock((CAutoWriterLock *)v16, this, a3);
  v4 = 0;
  v19 = 0;
  v20 = 0;
  v18 = 0;
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(L"Image Cache: Refreshing...");
  CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear((char *)this + 128);
  v5 = WdsImgOpenImageStore(*((_QWORD *)this + 15), &v21);
  if ( (int)ElValidateHr_0(v5, v6, v7, 415) >= 0 )
  {
    Item = CImageCache::EnumImageGroups(this, v21);
    if ( !(unsigned int)ElValidateWin32_0(Item, v9, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 421) )
    {
      if ( g_ErrLibTraceFunction )
        g_ErrLibTraceFunction(L"Image Cache: Total %u Images Found.", *((unsigned int *)this + 35));
      while ( (unsigned int)v4 < *((_DWORD *)this + 35) )
      {
        v22 = 0;
        Item = (unsigned int)CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(
                               (char *)this + 128,
                               (unsigned int)v4,
                               &v22);
        if ( (unsigned int)ElValidateWin32_0(Item, v10, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 438)
          || *(_DWORD *)(v22 + 44)
          && (v17 = *(_OWORD *)(v22 + 48),
              Item = (unsigned int)CDynArray<_GUID,CDeallocateNone>::AddItem(&v18, &v17),
              (unsigned int)ElValidateWin32_0(Item, v11, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 443)) )
        {
          v4 = v18;
          goto LABEL_15;
        }
        LODWORD(v4) = (_DWORD)v4 + 1;
      }
      CAutoWriterLock::Unlock((CAutoWriterLock *)v16);
      v4 = v18;
      CWdsMetadataStoreManagementClient::RegisterKnownObjectsOfType((CImageCache *)((char *)this + 160), v18, v20, v12);
    }
  }
  else
  {
    LODWORD(Item) = WIN32_FROM_HRESULT(v5);
  }
LABEL_15:
  Action = CTrackErrState::NextAction((CImageCache *)((char *)this + 156), Item);
  if ( Action == 1 )
  {
    v15 = Item;
    CEventLog::Log((CEventLog *)g_EventLog, 0xC106010C, 1, 5, v15);
  }
  else if ( Action == 2 )
  {
    CEventLog::Log((CEventLog *)g_EventLog, 0x106010Du, 0);
  }
  if ( v21 )
  {
    WdsImgClose();
    v21 = 0;
  }
  if ( v4 )
    operator delete[](v4);
  CAutoWriterLock::Unlock((CAutoWriterLock *)v16);
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x180009490  mov     [rsp-18h+arg_10], rbx
0x180009495  mov     [rsp-18h+arg_18], rsi
0x18000949a  push    rbp
0x18000949b  push    rdi
0x18000949c  push    r14
0x18000949e  mov     rbp, rsp
0x1800094a1  sub     rsp, 70h
0x1800094a5  and     [rbp+arg_0], 0
0x1800094aa  mov     rdi, rcx
0x1800094ad  mov     rdx, rcx; struct CMRSWLock *
0x1800094b0  lea     rcx, [rbp+var_40]; this
0x1800094b4  call    ??0CAutoWriterLock@@QEAA@PEAVCMRSWLock@@H@Z; CAutoWriterLock::CAutoWriterLock(CMRSWLock *,int)
0x1800094b9  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800094c0  xor     ebx, ebx
0x1800094c2  and     [rbp+var_18], ebx
0x1800094c5  and     [rbp+var_14], ebx
0x1800094c8  mov     [rbp+var_20], rbx
0x1800094cc  test    rax, rax
0x1800094cf  jz      short loc_1800094DD
0x1800094d1  lea     rcx, aImageCacheRefr; "Image Cache: Refreshing..."
0x1800094d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094dd  lea     r14, [rdi+80h]
0x1800094e4  mov     rcx, r14
0x1800094e7  call    ?Clear@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear(void)
0x1800094ec  mov     rcx, [rdi+78h]
0x1800094f0  lea     rdx, [rbp+arg_0]
0x1800094f4  call    cs:__imp_WdsImgOpenImageStore
0x1800094fb  nop     dword ptr [rax+rax+00h]
0x180009500  mov     ecx, eax
0x180009502  mov     r9d, 19Fh
0x180009508  mov     esi, eax
0x18000950a  call    ElValidateHr_0
0x18000950f  test    eax, eax
0x180009511  jns     short loc_180009528
0x180009513  mov     ecx, esi
0x180009515  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000951c  nop     dword ptr [rax+rax+00h]
0x180009521  mov     esi, eax
0x180009523  jmp     loc_180009609
0x180009528  mov     rdx, [rbp+arg_0]; void *
0x18000952c  mov     rcx, rdi; this
0x18000952f  call    ?EnumImageGroups@CImageCache@@AEAAKPEAX@Z; CImageCache::EnumImageGroups(void *)
0x180009534  mov     r9d, 1A5h
0x18000953a  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180009541  mov     ecx, eax
0x180009543  mov     esi, eax
0x180009545  call    ElValidateWin32_0
0x18000954a  test    eax, eax
0x18000954c  jnz     loc_180009609
0x180009552  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180009559  test    rax, rax
0x18000955c  jz      short loc_180009570
0x18000955e  mov     edx, [rdi+8Ch]
0x180009564  lea     rcx, aImageCacheTota; "Image Cache: Total %u Images Found."
0x18000956b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009570  cmp     ebx, [rdi+8Ch]
0x180009576  jnb     short loc_1800095E9
0x180009578  and     [rbp+arg_8], 0
0x18000957d  lea     r8, [rbp+arg_8]
0x180009581  mov     edx, ebx
0x180009583  mov     rcx, r14
0x180009586  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x18000958b  mov     ecx, eax
0x18000958d  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180009594  mov     r9d, 1B6h
0x18000959a  mov     esi, eax
0x18000959c  call    ElValidateWin32_0
0x1800095a1  test    eax, eax
0x1800095a3  jnz     short loc_1800095E3
0x1800095a5  mov     rax, [rbp+arg_8]
0x1800095a9  cmp     dword ptr [rax+2Ch], 0
0x1800095ad  jz      short loc_1800095DF
0x1800095af  movups  xmm0, xmmword ptr [rax+30h]
0x1800095b3  lea     rdx, [rbp+var_30]
0x1800095b7  lea     rcx, [rbp+var_20]
0x1800095bb  movdqu  [rbp+var_30], xmm0
0x1800095c0  call    ?AddItem@?$CDynArray@U_GUID@@VCDeallocateNone@@@@QEAAKU_GUID@@@Z; CDynArray<_GUID,CDeallocateNone>::AddItem(_GUID)
0x1800095c5  mov     r9d, 1BBh
0x1800095cb  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x1800095d2  mov     ecx, eax
0x1800095d4  mov     esi, eax
0x1800095d6  call    ElValidateWin32_0
0x1800095db  test    eax, eax
0x1800095dd  jnz     short loc_1800095E3
0x1800095df  inc     ebx
0x1800095e1  jmp     short loc_180009570
0x1800095e3  mov     rbx, [rbp+var_20]
0x1800095e7  jmp     short loc_180009609
0x1800095e9  lea     rcx, [rbp+var_40]; this
0x1800095ed  call    ?Unlock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Unlock(void)
0x1800095f2  mov     rbx, [rbp+var_20]
0x1800095f6  lea     rcx, [rdi+0A0h]; this
0x1800095fd  mov     r8d, [rbp+var_14]; unsigned int
0x180009601  mov     rdx, rbx; struct _GUID *
0x180009604  call    ?RegisterKnownObjectsOfType@CWdsMetadataStoreManagementClient@@QEAAKPEAU_GUID@@KPEBG@Z; CWdsMetadataStoreManagementClient::RegisterKnownObjectsOfType(_GUID *,ulong,ushort const *)
0x180009609  lea     rcx, [rdi+9Ch]; this
0x180009610  mov     edx, esi; unsigned int
0x180009612  call    ?NextAction@CTrackErrState@@QEAAHK@Z; CTrackErrState::NextAction(ulong)
0x180009617  cmp     eax, 1
0x18000961a  jnz     short loc_180009641
0x18000961c  mov     edx, 0C106010Ch
0x180009621  mov     [rsp+70h+var_50], esi
0x180009625  lea     r9d, [rax+4]
0x180009629  mov     r8d, eax
0x18000962c  lea     rcx, ?g_EventLog@@3VCEventLog@@A; CEventLog g_EventLog
0x180009633  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000963a  nop     dword ptr [rax+rax+00h]
0x18000963f  jmp     short loc_180009661
0x180009641  cmp     eax, 2
0x180009644  jnz     short loc_180009661
0x180009646  xor     r8d, r8d
0x180009649  lea     rcx, ?g_EventLog@@3VCEventLog@@A; CEventLog g_EventLog
0x180009650  mov     edx, 106010Dh
0x180009655  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000965c  nop     dword ptr [rax+rax+00h]
0x180009661  mov     rcx, [rbp+arg_0]
0x180009665  test    rcx, rcx
0x180009668  jz      short loc_18000967B
0x18000966a  call    cs:__imp_WdsImgClose
0x180009671  nop     dword ptr [rax+rax+00h]
0x180009676  and     [rbp+arg_0], 0
0x18000967b  test    rbx, rbx
0x18000967e  jz      short loc_18000968F
0x180009680  mov     rcx, rbx
0x180009683  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000968a  nop     dword ptr [rax+rax+00h]
0x18000968f  lea     rcx, [rbp+var_40]; this
0x180009693  call    ?Unlock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Unlock(void)
0x180009698  lea     r11, [rsp+70h+var_s0]
0x18000969d  mov     eax, esi
0x18000969f  mov     rbx, [r11+30h]
0x1800096a3  mov     rsi, [r11+38h]
0x1800096a7  mov     rsp, r11
0x1800096aa  pop     r14
0x1800096ac  pop     rdi
0x1800096ad  pop     rbp
0x1800096ae  retn
```
