# WdcGraph::Render(void)

- ea: `0x18000694c`
- end: `0x180006a6b`
- name: `?Render@WdcGraph@@QEAAJXZ`
- size: `287`
- prototype: `__int64 __fastcall(WdcGraph *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800211ec`
- `0x180077260`

## callees

- `0x18000694c`
- `0x180006a80`
- `0x18000b854`
- `0x180086010`

## import_xrefs

- `USER32!UpdateWindow` at `0x18000699a`
- `USER32!UpdateWindow` at `0x18000699a`
- `USER32!InvalidateRect` at `0x180006975`
- `USER32!InvalidateRect` at `0x180006975`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180006a42`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180006a42`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180006a5a`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180006a5a`

## pseudocode

```c
__int64 __fastcall WdcGraph::Render(WdcGraph *this)
{
  HWND v2; // rax
  __int64 v3; // rax
  HWND v4; // rax
  unsigned int v5; // ebx
  WdcStringMap *v6; // rcx
  unsigned int v7; // esi
  int v9; // eax
  int v10; // [rsp+20h] [rbp-18h]
  __int64 v11; // [rsp+20h] [rbp-18h]
  unsigned __int16 *v12; // [rsp+40h] [rbp+8h] BYREF

  v2 = (HWND)(*(__int64 (__fastcall **)(WdcGraph *))(*(_QWORD *)this + 360LL))(this);
  InvalidateRect(v2, 0, 0);
  v3 = *(_QWORD *)this;
  *((_DWORD *)this + 116) = 1;
  v4 = (HWND)(*(__int64 (__fastcall **)(WdcGraph *))(v3 + 360))(this);
  UpdateWindow(v4);
  v5 = 0;
  v12 = 0;
  if ( *((_QWORD *)this + 54) )
  {
    v6 = (WdcStringMap *)(32LL * *((int *)this + 99));
    v7 = *(_DWORD *)((char *)v6 + *((_QWORD *)this + 48) + 8);
    if ( *((_DWORD *)this + 110) != v7 )
    {
      v9 = WdcStringMap::LoadStringW(v6, v7, &v12);
      v5 = v9;
      if ( v9 < 0
        || (v9 = DirectUI::Element::SetContentString(*((DirectUI::Element **)this + 54), v12), v5 = v9, v9 < 0) )
      {
        v10 = v9;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\graph.cpp",
          "WdcGraph::SetScaleLabel",
          0,
          L"FAILURE: 0x%08x",
          v10);
        LODWORD(v11) = v5;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\graph.cpp",
          "WdcGraph::Render",
          0,
          L"FAILURE: 0x%08x",
          v11);
      }
      else
      {
        DirectUI::Element::SetAccName(*((DirectUI::Element **)this + 54), v12);
        *((_DWORD *)this + 110) = v7;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000694c  mov     [rsp+arg_8], rbx
0x180006951  mov     [rsp+arg_10], rsi
0x180006956  push    rdi
0x180006957  sub     rsp, 30h
0x18000695b  mov     rax, [rcx]
0x18000695e  mov     rdi, rcx
0x180006961  mov     rax, [rax+168h]
0x180006968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000696d  mov     rcx, rax; hWnd
0x180006970  xor     r8d, r8d; bErase
0x180006973  xor     edx, edx; lpRect
0x180006975  call    cs:__imp_InvalidateRect
0x18000697b  mov     rax, [rdi]
0x18000697e  mov     rcx, rdi
0x180006981  mov     dword ptr [rdi+1D0h], 1
0x18000698b  mov     rax, [rax+168h]
0x180006992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006997  mov     rcx, rax; hWnd
0x18000699a  call    cs:__imp_UpdateWindow
0x1800069a0  xor     ebx, ebx
0x1800069a2  mov     [rsp+38h+arg_0], rbx
0x1800069a7  cmp     [rdi+1B0h], rbx
0x1800069ae  jz      short loc_1800069CE
0x1800069b0  movsxd  rcx, dword ptr [rdi+18Ch]
0x1800069b7  mov     rax, [rdi+180h]
0x1800069be  shl     rcx, 5; this
0x1800069c2  mov     esi, [rcx+rax+8]
0x1800069c6  cmp     [rdi+1B8h], esi
0x1800069cc  jnz     short loc_1800069E0
0x1800069ce  mov     rsi, [rsp+38h+arg_10]
0x1800069d3  mov     eax, ebx
0x1800069d5  mov     rbx, [rsp+38h+arg_8]
0x1800069da  add     rsp, 30h
0x1800069de  pop     rdi
0x1800069df  retn
0x1800069e0  lea     r8, [rsp+38h+arg_0]; unsigned __int16 **
0x1800069e5  mov     edx, esi; unsigned int
0x1800069e7  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x1800069ec  mov     ebx, eax
0x1800069ee  test    eax, eax
0x1800069f0  jns     short loc_180006A36
0x1800069f2  xor     r8d, r8d; int
0x1800069f5  mov     dword ptr [rsp+38h+var_18], eax
0x1800069f9  lea     rdx, aWdcgraphSetsca; "WdcGraph::SetScaleLabel"
0x180006a00  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180006a07  lea     rcx, aBaseDiagnosisP_49; "base\\diagnosis\\pdui\\perfmon\\mon\\gr"...
0x180006a0e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180006a13  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180006a1a  mov     dword ptr [rsp+38h+var_18], ebx
0x180006a1e  xor     r8d, r8d; int
0x180006a21  lea     rdx, aWdcgraphRender; "WdcGraph::Render"
0x180006a28  lea     rcx, aBaseDiagnosisP_49; "base\\diagnosis\\pdui\\perfmon\\mon\\gr"...
0x180006a2f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180006a34  jmp     short loc_1800069CE
0x180006a36  mov     rdx, [rsp+38h+arg_0]
0x180006a3b  mov     rcx, [rdi+1B0h]
0x180006a42  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180006a48  mov     ebx, eax
0x180006a4a  test    eax, eax
0x180006a4c  js      short loc_1800069F2
0x180006a4e  mov     rdx, [rsp+38h+arg_0]
0x180006a53  mov     rcx, [rdi+1B0h]
0x180006a5a  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180006a60  mov     [rdi+1B8h], esi
0x180006a66  jmp     loc_1800069CE
```
