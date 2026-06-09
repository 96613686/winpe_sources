# CThemeCplCore::~CThemeCplCore(void)

- ea: `0x1800358f8`
- end: `0x1800359df`
- name: `??1CThemeCplCore@@QEAA@XZ`
- size: `231`
- prototype: `void __fastcall(CThemeCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180036a80`

## callees

- `0x180002650`
- `0x180008c98`
- `0x18000fb80`
- `0x18001fe90`
- `0x1800358f8`
- `0x180039534`

## import_xrefs

- `SHELL32!__imp_?UpdateWallpaperTransition@@YAJW4WALLPAPER_TRANSITION_TYPE@@_J@Z` at `0x180035975`
- `SHELL32!__imp_?UpdateWallpaperTransition@@YAJW4WALLPAPER_TRANSITION_TYPE@@_J@Z` at `0x180035975`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180035996`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180035996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800359a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800359a9`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180035950`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180035950`

## pseudocode

```c
void __fastcall CThemeCplCore::~CThemeCplCore(CThemeCplCore *this)
{
  void *v2; // rdi
  DirectUI::Element *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CThemeCplCore::`vftable'{for `IUnknown'};
  *((_QWORD *)this + 1) = &CThemeCplCore::`vftable'{for `DirectUI::IElementListener'};
  v2 = (void *)*((_QWORD *)this + 32);
  if ( v2 )
  {
    CColorSwatchStore::FlushSwatchData(*((CColorSwatchStore **)this + 32));
    operator delete(v2, (const struct std::nothrow_t *)8);
  }
  v3 = (DirectUI::Element *)*((_QWORD *)this + 21);
  if ( v3 )
  {
    DirectUI::Element::RemoveListener(v3, (CThemeCplCore *)((char *)this + 8));
    *((_QWORD *)this + 21) = 0;
  }
  if ( *((_BYTE *)this + 296) )
    UpdateWallpaperTransition(1, 0);
  v4 = (void *)*((_QWORD *)this + 38);
  if ( v4 )
  {
    if ( *((_BYTE *)this + 312) )
      ReleaseMutex(v4);
    CloseHandle(*((HANDLE *)this + 38));
  }
  SafeRelease<IUnknown>((char *)this + 40);
  CThemeGalleryData::~CThemeGalleryData((CThemeCplCore *)((char *)this + 120));
  CGallery::~CGallery((CThemeCplCore *)((char *)this + 48));
}

```

## disassembly

```asm
0x1800358f8  mov     [rsp+arg_0], rbx
0x1800358fd  mov     [rsp+arg_8], rsi
0x180035902  push    rdi
0x180035903  sub     rsp, 20h
0x180035907  mov     rbx, rcx
0x18003590a  lea     rax, ??_7CThemeCplCore@@6BIUnknown@@@; const CThemeCplCore::`vftable'{for `IUnknown'}
0x180035911  mov     [rcx], rax
0x180035914  lea     rax, ??_7CThemeCplCore@@6BIElementListener@DirectUI@@@; const CThemeCplCore::`vftable'{for `DirectUI::IElementListener'}
0x18003591b  mov     [rcx+8], rax
0x18003591f  mov     rdi, [rcx+100h]
0x180035926  test    rdi, rdi
0x180035929  jz      short loc_180035940
0x18003592b  mov     rcx, rdi; this
0x18003592e  call    ?FlushSwatchData@CColorSwatchStore@@QEAAXXZ; CColorSwatchStore::FlushSwatchData(void)
0x180035933  mov     edx, 8; struct std::nothrow_t *
0x180035938  mov     rcx, rdi; void *
0x18003593b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035940  mov     rcx, [rbx+0A8h]
0x180035947  test    rcx, rcx
0x18003594a  jz      short loc_180035967
0x18003594c  lea     rdx, [rbx+8]
0x180035950  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180035957  nop     dword ptr [rax+rax+00h]
0x18003595c  mov     qword ptr [rbx+0A8h], 0
0x180035967  cmp     byte ptr [rbx+128h], 0
0x18003596e  jz      short loc_180035981
0x180035970  xor     edx, edx
0x180035972  lea     ecx, [rdx+1]
0x180035975  call    cs:__imp_?UpdateWallpaperTransition@@YAJW4WALLPAPER_TRANSITION_TYPE@@_J@Z; UpdateWallpaperTransition(WALLPAPER_TRANSITION_TYPE,__int64)
0x18003597c  nop     dword ptr [rax+rax+00h]
0x180035981  mov     rcx, [rbx+130h]; hMutex
0x180035988  test    rcx, rcx
0x18003598b  jz      short loc_1800359B5
0x18003598d  cmp     byte ptr [rbx+138h], 0
0x180035994  jz      short loc_1800359A2
0x180035996  call    cs:__imp_ReleaseMutex
0x18003599d  nop     dword ptr [rax+rax+00h]
0x1800359a2  mov     rcx, [rbx+130h]; hObject
0x1800359a9  call    cs:__imp_CloseHandle
0x1800359b0  nop     dword ptr [rax+rax+00h]
0x1800359b5  lea     rcx, [rbx+28h]
0x1800359b9  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x1800359be  lea     rcx, [rbx+78h]; this
0x1800359c2  call    ??1CThemeGalleryData@@QEAA@XZ; CThemeGalleryData::~CThemeGalleryData(void)
0x1800359c7  lea     rcx, [rbx+30h]; this
0x1800359cb  mov     rbx, [rsp+28h+arg_0]
0x1800359d0  mov     rsi, [rsp+28h+arg_8]
0x1800359d5  add     rsp, 20h
0x1800359d9  pop     rdi
0x1800359da  jmp     ??1CGallery@@QEAA@XZ; CGallery::~CGallery(void)
```
