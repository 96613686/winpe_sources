# FrameProvider::~FrameProvider(void)

- ea: `0x180053518`
- end: `0x1800535c6`
- name: `??1FrameProvider@@MEAA@XZ`
- size: `174`
- prototype: `void __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800535d0`

## callees

- `0x180008c98`
- `0x180053518`
- `0x180057010`

## import_xrefs

- `DUI70!UnInitProcessPriv` at `0x18005359f`
- `DUI70!UnInitProcessPriv` at `0x18005359f`
- `DUI70!UnInitThread` at `0x18005358c`
- `DUI70!UnInitThread` at `0x18005358c`
- `DUI70!??1XProvider@DirectUI@@UEAA@XZ` at `0x1800535ba`

## pseudocode

```c
void __fastcall FrameProvider::~FrameProvider(FrameProvider *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &FrameProvider::`vftable'{for `DirectUI::XProvider'};
  *((_QWORD *)this + 5) = &FrameProvider::`vftable'{for `IDUIElementProviderInit'};
  *((_QWORD *)this + 6) = &FrameProvider::`vftable'{for `IFrameNotificationClient'};
  *((_QWORD *)this + 7) = &FrameProvider::`vftable'{for `IFrameShellViewClient'};
  *((_QWORD *)this + 8) = &FrameProvider::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 9) = &FrameProvider::`vftable'{for `IServiceProvider'};
  SafeRelease<IUnknown>((char *)this + 80);
  v2 = *((_QWORD *)this + 78);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((int *)this + 154) >= 0 )
  {
    UnInitThread();
    UnInitProcessPriv(&_ImageBase);
  }
  _InterlockedDecrement(&g_cLocks);
  DirectUI::XProvider::~XProvider(this);
}

```

## disassembly

```asm
0x180053518  push    rbx
0x18005351a  sub     rsp, 20h
0x18005351e  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x180053525  mov     rbx, rcx
0x180053528  mov     [rcx], rax
0x18005352b  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x180053532  mov     [rcx+28h], rax
0x180053536  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x18005353d  mov     [rcx+30h], rax
0x180053541  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x180053548  mov     [rcx+38h], rax
0x18005354c  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x180053553  mov     [rcx+40h], rax
0x180053557  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x18005355e  mov     [rcx+48h], rax
0x180053562  add     rcx, 50h ; 'P'
0x180053566  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x18005356b  mov     rcx, [rbx+270h]
0x180053572  test    rcx, rcx
0x180053575  jz      short loc_180053583
0x180053577  mov     rax, [rcx]
0x18005357a  mov     rax, [rax+10h]
0x18005357e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053583  cmp     dword ptr [rbx+268h], 0
0x18005358a  jl      short loc_1800535AB
0x18005358c  call    cs:__imp_UnInitThread
0x180053593  nop     dword ptr [rax+rax+00h]
0x180053598  lea     rcx, __ImageBase
0x18005359f  call    cs:__imp_UnInitProcessPriv
0x1800535a6  nop     dword ptr [rax+rax+00h]
0x1800535ab  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x1800535b2  mov     rcx, rbx
0x1800535b5  add     rsp, 20h
0x1800535b9  pop     rbx
0x1800535ba  jmp     cs:__imp_??1XProvider@DirectUI@@UEAA@XZ; DirectUI::XProvider::~XProvider(void)
```
