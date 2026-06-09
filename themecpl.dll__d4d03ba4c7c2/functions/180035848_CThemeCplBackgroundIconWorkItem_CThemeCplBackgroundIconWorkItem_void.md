# CThemeCplBackgroundIconWorkItem::~CThemeCplBackgroundIconWorkItem(void)

- ea: `0x180035848`
- end: `0x1800358ef`
- name: `??1CThemeCplBackgroundIconWorkItem@@MEAA@XZ`
- size: `167`
- prototype: `void __fastcall(CThemeCplBackgroundIconWorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800359f0`

## callees

- `0x180035848`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800358d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800358d6`
- `GDI32!DeleteObject` at `0x180035871`
- `GDI32!DeleteObject` at `0x180035871`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x1800358b5`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x1800358b5`

## pseudocode

```c
void __fastcall CThemeCplBackgroundIconWorkItem::~CThemeCplBackgroundIconWorkItem(
        CThemeCplBackgroundIconWorkItem *this)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rcx
  DirectUI::Element *v4; // rcx

  *(_QWORD *)this = &CThemeCplBackgroundIconWorkItem::`vftable'{for `CFrameWorkItem'};
  v2 = (unsigned __int64)this + 64;
  *((_QWORD *)this + 8) = &CThemeCplBackgroundIconWorkItem::`vftable'{for `DirectUI::IElementListener'};
  DeleteObject(*((HGDIOBJ *)this + 11));
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (DirectUI::Element *)*((_QWORD *)this + 9);
  if ( v4 && *((_BYTE *)this + 96) )
    DirectUI::Element::RemoveListener(
      v4,
      (struct DirectUI::IElementListener *)(v2 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  _InterlockedDecrement(&g_cLocks);
  *(_QWORD *)this = &CFrameWorkItem::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180035848  mov     [rsp+arg_0], rbx
0x18003584d  push    rdi
0x18003584e  sub     rsp, 20h
0x180035852  mov     rbx, rcx
0x180035855  lea     rax, ??_7CThemeCplBackgroundIconWorkItem@@6BCFrameWorkItem@@@; const CThemeCplBackgroundIconWorkItem::`vftable'{for `CFrameWorkItem'}
0x18003585c  mov     [rcx], rax
0x18003585f  lea     rdi, [rcx+40h]
0x180035863  lea     rax, ??_7CThemeCplBackgroundIconWorkItem@@6BIElementListener@DirectUI@@@; const CThemeCplBackgroundIconWorkItem::`vftable'{for `DirectUI::IElementListener'}
0x18003586a  mov     [rdi], rax
0x18003586d  mov     rcx, [rcx+58h]; ho
0x180035871  call    cs:__imp_DeleteObject
0x180035878  nop     dword ptr [rax+rax+00h]
0x18003587d  mov     rcx, [rbx+50h]
0x180035881  mov     qword ptr [rbx+50h], 0
0x180035889  test    rcx, rcx
0x18003588c  jz      short loc_18003589A
0x18003588e  mov     rax, [rcx]
0x180035891  mov     rax, [rax+10h]
0x180035895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003589a  mov     rcx, [rbx+48h]
0x18003589e  test    rcx, rcx
0x1800358a1  jz      short loc_1800358C1
0x1800358a3  cmp     byte ptr [rbx+60h], 0
0x1800358a7  jz      short loc_1800358C1
0x1800358a9  mov     rax, rbx
0x1800358ac  neg     rax
0x1800358af  sbb     rdx, rdx
0x1800358b2  and     rdx, rdi
0x1800358b5  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x1800358bc  nop     dword ptr [rax+rax+00h]
0x1800358c1  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x1800358c8  lea     rax, ??_7CFrameWorkItem@@6B@; const CFrameWorkItem::`vftable'
0x1800358cf  mov     [rbx], rax
0x1800358d2  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800358d6  call    cs:__imp_DeleteCriticalSection
0x1800358dd  nop     dword ptr [rax+rax+00h]
0x1800358e2  nop
0x1800358e3  mov     rbx, [rsp+28h+arg_0]
0x1800358e8  add     rsp, 20h
0x1800358ec  pop     rdi
0x1800358ed  retn
```
