# WdcResourceMonitor::InPlaceActivate(IOleClientSite *,HWND__ *,tagRECT const *)

- ea: `0x18006c530`
- end: `0x18006c672`
- name: `?InPlaceActivate@WdcResourceMonitor@@AEAAJPEAUIOleClientSite@@PEAUHWND__@@PEBUtagRECT@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(WdcResourceMonitor *__hidden this, struct IOleClientSite *, HWND, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180074490`

## callees

- `0x18000b854`
- `0x18006c530`
- `0x18006defc`
- `0x180073298`
- `0x180086010`

## import_xrefs

- `USER32!ShowWindow` at `0x18006c5f1`
- `USER32!ShowWindow` at `0x18006c5f1`
- `USER32!PostMessageW` at `0x18006c637`
- `USER32!PostMessageW` at `0x18006c65d`
- `USER32!PostMessageW` at `0x18006c637`
- `USER32!PostMessageW` at `0x18006c65d`
- `DUI70!InitProcessPriv` at `0x18006c578`
- `DUI70!InitProcessPriv` at `0x18006c578`
- `DUI70!InitThread` at `0x18006c5af`
- `DUI70!InitThread` at `0x18006c5af`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18006c5df`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18006c5df`

## pseudocode

```c
__int64 __fastcall WdcResourceMonitor::InPlaceActivate(
        WdcResourceMonitor *this,
        struct IOleClientSite *a2,
        HWND a3,
        const struct tagRECT *a4)
{
  HWND v4; // rbp
  int inited; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rsi
  HWND HWND; // rax
  HWND v10; // rax
  HWND v11; // rax
  int v13; // [rsp+20h] [rbp-28h]
  struct DirectUI::NativeHWNDHost *v14; // [rsp+58h] [rbp+10h] BYREF
  int v15; // [rsp+68h] [rbp+20h] BYREF
  int v16; // [rsp+6Ch] [rbp+24h]

  v16 = HIDWORD(a4);
  *((_DWORD *)this + 22) = 1;
  v4 = a3;
  v15 = 0;
  v14 = 0;
  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  v7 = inited;
  if ( inited < 0 )
    goto LABEL_2;
  inited = InitThread(2);
  v7 = inited;
  if ( inited < 0 )
    goto LABEL_2;
  WdcGraph::RegisterWindow();
  v8 = (_QWORD *)((char *)this + 24);
  inited = WdcMonitor::Create(v4, &v14, (struct WdcMonitor **)this + 3);
  v7 = inited;
  if ( inited < 0
    || (HWND = DirectUI::NativeHWNDHost::GetHWND(v14),
        *((_QWORD *)this + 10) = HWND,
        ShowWindow(HWND, 5),
        inited = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this + 2) + 24LL))((char *)this + 16, &v15),
        v7 = inited,
        inited < 0) )
  {
LABEL_2:
    v13 = inited;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\resourcemonitor.cpp",
      "WdcResourceMonitor::InPlaceActivate",
      0,
      L"FAILURE: 0x%08x",
      v13);
  }
  else
  {
    v10 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 360LL))(*v8);
    PostMessageW(v10, 0x201u, 1u, 0);
    v11 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 360LL))(*v8);
    PostMessageW(v11, 0x202u, 0, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x18006c530  mov     rax, rsp
0x18006c533  mov     [rax+8], rbx
0x18006c537  mov     [rax+20h], r9
0x18006c53b  mov     [rax+10h], rdx
0x18006c53f  push    rbp
0x18006c540  push    rsi
0x18006c541  push    rdi
0x18006c542  sub     rsp, 30h
0x18006c546  mov     r9b, 1
0x18006c549  mov     dword ptr [rcx+58h], 1
0x18006c550  mov     rbp, r8
0x18006c553  mov     dword ptr [rax+20h], 0
0x18006c55a  mov     rdi, rcx
0x18006c55d  mov     qword ptr [rax+10h], 0
0x18006c565  mov     r8b, r9b
0x18006c568  mov     byte ptr [rax-28h], 1
0x18006c56c  lea     rdx, __ImageBase
0x18006c573  mov     ecx, 0Eh
0x18006c578  call    cs:__imp_InitProcessPriv
0x18006c57e  mov     ebx, eax
0x18006c580  test    eax, eax
0x18006c582  jns     short loc_18006C5AA
0x18006c584  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18006c58b  mov     [rsp+48h+var_28], eax
0x18006c58f  xor     r8d, r8d; int
0x18006c592  lea     rdx, aWdcresourcemon_7; "WdcResourceMonitor::InPlaceActivate"
0x18006c599  lea     rcx, aBaseDiagnosisP_10; "base\\diagnosis\\pdui\\perfmon\\mon\\re"...
0x18006c5a0  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006c5a5  jmp     loc_18006C663
0x18006c5aa  mov     ecx, 2
0x18006c5af  call    cs:__imp_InitThread
0x18006c5b5  mov     ebx, eax
0x18006c5b7  test    eax, eax
0x18006c5b9  js      short loc_18006C584
0x18006c5bb  call    ?RegisterWindow@WdcGraph@@SAJXZ; WdcGraph::RegisterWindow(void)
0x18006c5c0  lea     rsi, [rdi+18h]
0x18006c5c4  mov     rcx, rbp; HWND
0x18006c5c7  mov     r8, rsi; struct WdcMonitor **
0x18006c5ca  lea     rdx, [rsp+48h+arg_8]; struct DirectUI::NativeHWNDHost **
0x18006c5cf  call    ?Create@WdcMonitor@@SAJPEAUHWND__@@PEAPEAVNativeHWNDHost@DirectUI@@PEAPEAV1@@Z; WdcMonitor::Create(HWND__ *,DirectUI::NativeHWNDHost * *,WdcMonitor * *)
0x18006c5d4  mov     ebx, eax
0x18006c5d6  test    eax, eax
0x18006c5d8  js      short loc_18006C584
0x18006c5da  mov     rcx, [rsp+48h+arg_8]
0x18006c5df  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x18006c5e5  mov     rcx, rax; hWnd
0x18006c5e8  mov     [rdi+50h], rax
0x18006c5ec  mov     edx, 5; nCmdShow
0x18006c5f1  call    cs:__imp_ShowWindow
0x18006c5f7  lea     rcx, [rdi+10h]
0x18006c5fb  mov     rax, [rcx]
0x18006c5fe  lea     rdx, [rsp+48h+arg_18]
0x18006c603  mov     rax, [rax+18h]
0x18006c607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c60c  mov     ebx, eax
0x18006c60e  test    eax, eax
0x18006c610  js      loc_18006C584
0x18006c616  mov     rcx, [rsi]
0x18006c619  mov     rax, [rcx]
0x18006c61c  mov     rax, [rax+168h]
0x18006c623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c628  xor     r9d, r9d; lParam
0x18006c62b  mov     rcx, rax; hWnd
0x18006c62e  mov     edx, 201h; Msg
0x18006c633  lea     r8d, [r9+1]; wParam
0x18006c637  call    cs:__imp_PostMessageW
0x18006c63d  mov     rcx, [rsi]
0x18006c640  mov     rax, [rcx]
0x18006c643  mov     rax, [rax+168h]
0x18006c64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c64f  mov     rcx, rax; hWnd
0x18006c652  xor     r9d, r9d; lParam
0x18006c655  xor     r8d, r8d; wParam
0x18006c658  mov     edx, 202h; Msg
0x18006c65d  call    cs:__imp_PostMessageW
0x18006c663  mov     eax, ebx
0x18006c665  mov     rbx, [rsp+48h+arg_0]
0x18006c66a  add     rsp, 30h
0x18006c66e  pop     rdi
0x18006c66f  pop     rsi
0x18006c670  pop     rbp
0x18006c671  retn
```
