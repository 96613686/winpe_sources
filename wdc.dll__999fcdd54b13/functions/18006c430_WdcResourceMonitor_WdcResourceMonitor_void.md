# WdcResourceMonitor::~WdcResourceMonitor(void)

- ea: `0x18006c430`
- end: `0x18006c4e5`
- name: `??1WdcResourceMonitor@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(WdcResourceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006c6f0`

## callees

- `0x18006c430`
- `0x180086010`

## import_xrefs

- `USER32!DestroyWindow` at `0x18006c462`
- `USER32!DestroyWindow` at `0x18006c462`
- `DUI70!UnInitProcessPriv` at `0x18006c4d2`
- `DUI70!UnInitProcessPriv` at `0x18006c4d2`
- `DUI70!UnInitThread` at `0x18006c4c5`
- `DUI70!UnInitThread` at `0x18006c4c5`

## pseudocode

```c
void __fastcall WdcResourceMonitor::~WdcResourceMonitor(WdcResourceMonitor *this)
{
  HWND v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &WdcResourceMonitor::`vftable'{for `IViewObject2'};
  *((_QWORD *)this + 1) = &WdcResourceMonitor::`vftable'{for `IOleObject'};
  *((_QWORD *)this + 2) = &WdcResourceMonitor::`vftable'{for `IResourceMonitor'};
  v2 = (HWND)*((_QWORD *)this + 10);
  if ( v2 )
    DestroyWindow(v2);
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 6) = 0;
  }
  v4 = *((_QWORD *)this + 7);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 7) = 0;
  }
  v5 = *((_QWORD *)this + 8);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 8) = 0;
  }
  if ( *((_DWORD *)this + 22) )
  {
    UnInitThread();
    UnInitProcessPriv(&_ImageBase);
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_uObjects);
}

```

## disassembly

```asm
0x18006c430  push    rbx
0x18006c432  sub     rsp, 20h
0x18006c436  lea     rax, ??_7WdcResourceMonitor@@6BIViewObject2@@@; const WdcResourceMonitor::`vftable'{for `IViewObject2'}
0x18006c43d  mov     rbx, rcx
0x18006c440  mov     [rcx], rax
0x18006c443  lea     rax, ??_7WdcResourceMonitor@@6BIOleObject@@@; const WdcResourceMonitor::`vftable'{for `IOleObject'}
0x18006c44a  mov     [rcx+8], rax
0x18006c44e  lea     rax, ??_7WdcResourceMonitor@@6BIResourceMonitor@@@; const WdcResourceMonitor::`vftable'{for `IResourceMonitor'}
0x18006c455  mov     [rcx+10h], rax
0x18006c459  mov     rcx, [rcx+50h]; hWnd
0x18006c45d  test    rcx, rcx
0x18006c460  jz      short loc_18006C468
0x18006c462  call    cs:__imp_DestroyWindow
0x18006c468  mov     rcx, [rbx+30h]
0x18006c46c  test    rcx, rcx
0x18006c46f  jz      short loc_18006C485
0x18006c471  mov     rax, [rcx]
0x18006c474  mov     rax, [rax+10h]
0x18006c478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c47d  mov     qword ptr [rbx+30h], 0
0x18006c485  mov     rcx, [rbx+38h]
0x18006c489  test    rcx, rcx
0x18006c48c  jz      short loc_18006C4A2
0x18006c48e  mov     rax, [rcx]
0x18006c491  mov     rax, [rax+10h]
0x18006c495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c49a  mov     qword ptr [rbx+38h], 0
0x18006c4a2  mov     rcx, [rbx+40h]
0x18006c4a6  test    rcx, rcx
0x18006c4a9  jz      short loc_18006C4BF
0x18006c4ab  mov     rax, [rcx]
0x18006c4ae  mov     rax, [rax+10h]
0x18006c4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c4b7  mov     qword ptr [rbx+40h], 0
0x18006c4bf  cmp     dword ptr [rbx+58h], 0
0x18006c4c3  jz      short loc_18006C4D8
0x18006c4c5  call    cs:__imp_UnInitThread
0x18006c4cb  lea     rcx, __ImageBase
0x18006c4d2  call    cs:__imp_UnInitProcessPriv
0x18006c4d8  lock dec cs:?g_uObjects@@3KA; ulong g_uObjects
0x18006c4df  add     rsp, 20h
0x18006c4e3  pop     rbx
0x18006c4e4  retn
```
