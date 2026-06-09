# CGalleryThumbnailWorkItem::~CGalleryThumbnailWorkItem(void)

- ea: `0x18001ff30`
- end: `0x18001ffd3`
- name: `??1CGalleryThumbnailWorkItem@@MEAA@XZ`
- size: `163`
- prototype: `void __fastcall(CGalleryThumbnailWorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ffe0`

## callees

- `0x180008c98`
- `0x18001ff30`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ffbf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ffbf`
- `GDI32!DeleteObject` at `0x18001ff70`
- `GDI32!DeleteObject` at `0x18001ff70`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x18001ff60`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x18001ff60`

## pseudocode

```c
void __fastcall CGalleryThumbnailWorkItem::~CGalleryThumbnailWorkItem(CGalleryThumbnailWorkItem *this)
{
  struct DirectUI::IElementListener *v2; // rdx
  DirectUI::Element *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CGalleryThumbnailWorkItem::`vftable'{for `CFrameWorkItem'};
  v2 = (CGalleryThumbnailWorkItem *)((char *)this + 64);
  *((_QWORD *)this + 8) = &CGalleryThumbnailWorkItem::`vftable'{for `DirectUI::IElementListener'};
  if ( *((_BYTE *)this + 112) )
  {
    v3 = (DirectUI::Element *)*((_QWORD *)this + 9);
    if ( v3 )
      DirectUI::Element::RemoveListener(v3, v2);
  }
  DeleteObject(*((HGDIOBJ *)this + 11));
  *((_QWORD *)this + 11) = 0;
  SafeRelease<IUnknown>((char *)this + 104);
  v4 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  _InterlockedDecrement(&g_cLocks);
  *(_QWORD *)this = &CFrameWorkItem::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18001ff30  push    rbx
0x18001ff32  sub     rsp, 20h
0x18001ff36  mov     rbx, rcx
0x18001ff39  lea     rax, ??_7CGalleryThumbnailWorkItem@@6BCFrameWorkItem@@@; const CGalleryThumbnailWorkItem::`vftable'{for `CFrameWorkItem'}
0x18001ff40  mov     [rcx], rax
0x18001ff43  lea     rdx, [rcx+40h]
0x18001ff47  lea     rax, ??_7CGalleryThumbnailWorkItem@@6BIElementListener@DirectUI@@@; const CGalleryThumbnailWorkItem::`vftable'{for `DirectUI::IElementListener'}
0x18001ff4e  mov     [rdx], rax
0x18001ff51  cmp     byte ptr [rcx+70h], 0
0x18001ff55  jz      short loc_18001FF6C
0x18001ff57  mov     rcx, [rcx+48h]
0x18001ff5b  test    rcx, rcx
0x18001ff5e  jz      short loc_18001FF6C
0x18001ff60  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x18001ff67  nop     dword ptr [rax+rax+00h]
0x18001ff6c  mov     rcx, [rbx+58h]; ho
0x18001ff70  call    cs:__imp_DeleteObject
0x18001ff77  nop     dword ptr [rax+rax+00h]
0x18001ff7c  mov     qword ptr [rbx+58h], 0
0x18001ff84  lea     rcx, [rbx+68h]
0x18001ff88  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x18001ff8d  mov     rcx, [rbx+78h]
0x18001ff91  mov     qword ptr [rbx+78h], 0
0x18001ff99  test    rcx, rcx
0x18001ff9c  jz      short loc_18001FFAA
0x18001ff9e  mov     rax, [rcx]
0x18001ffa1  mov     rax, [rax+10h]
0x18001ffa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffaa  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x18001ffb1  lea     rax, ??_7CFrameWorkItem@@6B@; const CFrameWorkItem::`vftable'
0x18001ffb8  mov     [rbx], rax
0x18001ffbb  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001ffbf  call    cs:__imp_DeleteCriticalSection
0x18001ffc6  nop     dword ptr [rax+rax+00h]
0x18001ffcb  nop
0x18001ffcc  add     rsp, 20h
0x18001ffd0  pop     rbx
0x18001ffd1  retn
```
