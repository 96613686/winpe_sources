# FrameProvider::~FrameProvider(void)

- ea: `0x180017158`
- end: `0x180017207`
- name: `??1FrameProvider@@MEAA@XZ`
- size: `175`
- prototype: `void __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180017210`

## callees

- `0x18000366c`
- `0x180017158`
- `0x18001e010`

## import_xrefs

- `DUI70!UnInitProcessPriv` at `0x1800171ed`
- `DUI70!UnInitProcessPriv` at `0x1800171ed`
- `DUI70!UnInitThread` at `0x1800171e0`
- `DUI70!UnInitThread` at `0x1800171e0`
- `DUI70!??1XProvider@DirectUI@@UEAA@XZ` at `0x180017200`

## pseudocode

```c
void __fastcall FrameProvider::~FrameProvider(FrameProvider *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &FrameProvider::`vftable'{for `DirectUI::XProvider'};
  *((_QWORD *)this + 5) = &FrameProvider::`vftable'{for `IDUIElementProviderInit'};
  *((_QWORD *)this + 6) = &FrameProvider::`vftable'{for `IFrameNotificationClient'};
  *((_QWORD *)this + 7) = &FrameProvider::`vftable'{for `IFrameShellViewClient'};
  *((_QWORD *)this + 8) = &FrameProvider::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 9) = &FrameProvider::`vftable'{for `IServiceProvider'};
  v2 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 78);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *((int *)this + 154) >= 0 )
  {
    UnInitThread();
    UnInitProcessPriv(&_ImageBase);
  }
  DllRelease();
  DirectUI::XProvider::~XProvider(this);
}

```

## disassembly

```asm
0x180017158  push    rbx
0x18001715a  sub     rsp, 20h
0x18001715e  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x180017165  mov     rbx, rcx
0x180017168  mov     [rcx], rax
0x18001716b  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x180017172  mov     [rcx+28h], rax
0x180017176  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x18001717d  mov     [rcx+30h], rax
0x180017181  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x180017188  mov     [rcx+38h], rax
0x18001718c  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x180017193  mov     [rcx+40h], rax
0x180017197  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x18001719e  mov     [rcx+48h], rax
0x1800171a2  mov     rcx, [rcx+50h]
0x1800171a6  mov     qword ptr [rbx+50h], 0
0x1800171ae  test    rcx, rcx
0x1800171b1  jz      short loc_1800171BF
0x1800171b3  mov     rax, [rcx]
0x1800171b6  mov     rax, [rax+10h]
0x1800171ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171bf  mov     rcx, [rbx+270h]
0x1800171c6  test    rcx, rcx
0x1800171c9  jz      short loc_1800171D7
0x1800171cb  mov     rax, [rcx]
0x1800171ce  mov     rax, [rax+10h]
0x1800171d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171d7  cmp     dword ptr [rbx+268h], 0
0x1800171de  jl      short loc_1800171F3
0x1800171e0  call    cs:__imp_UnInitThread
0x1800171e6  lea     rcx, __ImageBase
0x1800171ed  call    cs:__imp_UnInitProcessPriv
0x1800171f3  call    DllRelease
0x1800171f8  mov     rcx, rbx
0x1800171fb  add     rsp, 20h
0x1800171ff  pop     rbx
0x180017200  jmp     cs:__imp_??1XProvider@DirectUI@@UEAA@XZ; DirectUI::XProvider::~XProvider(void)
```
