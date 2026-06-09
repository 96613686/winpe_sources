# WdcSplitter::DragHorizontal(tagSIZE *)

- ea: `0x18007cc50`
- end: `0x18007cd5c`
- name: `?DragHorizontal@WdcSplitter@@AEAAJPEAUtagSIZE@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(LONG *this, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007d050`

## callees

- `0x18000b854`
- `0x18007cc50`
- `0x180086010`

## import_xrefs

- `USER32!UpdateWindow` at `0x18007cd25`
- `USER32!UpdateWindow` at `0x18007cd25`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007cd44`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007cd44`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007cc7a`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18007cc7a`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x18007cca4`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x18007cca4`
- `DUI70!?GetWidth@Element@DirectUI@@QEAAHXZ` at `0x18007cd2e`
- `DUI70!?GetWidth@Element@DirectUI@@QEAAHXZ` at `0x18007cd2e`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18007ccd1`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18007ccd1`

## pseudocode

```c
__int64 __fastcall WdcSplitter::DragHorizontal(LONG *this, struct tagSIZE *a2)
{
  bool v2; // zf
  unsigned int v5; // ebx
  LONG cx; // eax
  DirectUI::Element **v7; // rsi
  const struct tagSIZE *Extent; // rax
  int v9; // eax
  int v10; // edx
  int v11; // eax
  __int64 v12; // rcx
  HWND v13; // rax
  struct DirectUI::Value *v15; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2->cx == 0;
  v15 = 0;
  if ( v2 )
    return 0;
  if ( DirectUI::Element::IsRTL((DirectUI::Element *)this) )
    a2->cx = -a2->cx;
  cx = this[59];
  v7 = (DirectUI::Element **)(this + 54);
  if ( cx != -1 )
    goto LABEL_8;
  Extent = DirectUI::Element::GetExtent(*v7, &v15);
  if ( Extent )
  {
    cx = Extent->cx;
    this[59] = cx;
LABEL_8:
    v9 = cx - a2->cx;
    v10 = 120;
    if ( v9 >= 120 )
    {
      v10 = v9;
      if ( v9 > 600 )
        v10 = 600;
    }
    v11 = DirectUI::Element::SetWidth(*v7, v10);
    v5 = v11;
    if ( v11 >= 0 )
    {
      v12 = *((_QWORD *)this + 30);
      if ( v12 )
      {
        v13 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 360LL))(v12);
        UpdateWindow(v13);
      }
      this[59] = DirectUI::Element::GetWidth(*v7);
    }
    else
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\splitter.cpp",
        "WdcSplitter::DragHorizontal",
        0,
        L"FAILURE: 0x%08x",
        v11);
    }
    goto LABEL_17;
  }
  v5 = -2147467259;
LABEL_17:
  if ( v15 )
    DirectUI::Value::Release(v15);
  return v5;
}

```

## disassembly

```asm
0x18007cc50  mov     [rsp+arg_0], rbx
0x18007cc55  mov     [rsp+arg_10], rsi
0x18007cc5a  push    rdi
0x18007cc5b  sub     rsp, 30h
0x18007cc5f  cmp     dword ptr [rdx], 0
0x18007cc62  mov     rbx, rdx
0x18007cc65  mov     rdi, rcx
0x18007cc68  mov     [rsp+38h+arg_8], 0
0x18007cc71  jnz     short loc_18007CC7A
0x18007cc73  xor     ebx, ebx
0x18007cc75  jmp     loc_18007CD4A
0x18007cc7a  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x18007cc80  test    al, al
0x18007cc82  jz      short loc_18007CC8A
0x18007cc84  mov     eax, [rbx]
0x18007cc86  neg     eax
0x18007cc88  mov     [rbx], eax
0x18007cc8a  mov     eax, [rdi+0ECh]
0x18007cc90  lea     rsi, [rdi+0D8h]
0x18007cc97  cmp     eax, 0FFFFFFFFh
0x18007cc9a  jnz     short loc_18007CCB7
0x18007cc9c  mov     rcx, [rsi]
0x18007cc9f  lea     rdx, [rsp+38h+arg_8]
0x18007cca4  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x18007ccaa  test    rax, rax
0x18007ccad  jz      short loc_18007CD00
0x18007ccaf  mov     eax, [rax]
0x18007ccb1  mov     [rdi+0ECh], eax
0x18007ccb7  sub     eax, [rbx]
0x18007ccb9  mov     edx, 78h ; 'x'
0x18007ccbe  cmp     eax, edx
0x18007ccc0  jl      short loc_18007CCCE
0x18007ccc2  mov     ecx, 258h
0x18007ccc7  mov     edx, eax
0x18007ccc9  cmp     eax, ecx
0x18007cccb  cmovg   edx, ecx
0x18007ccce  mov     rcx, [rsi]
0x18007ccd1  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18007ccd7  mov     ebx, eax
0x18007ccd9  test    eax, eax
0x18007ccdb  jns     short loc_18007CD07
0x18007ccdd  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18007cce4  mov     [rsp+38h+var_18], eax
0x18007cce8  xor     r8d, r8d; int
0x18007cceb  lea     rdx, aWdcsplitterDra_0; "WdcSplitter::DragHorizontal"
0x18007ccf2  lea     rcx, aBaseDiagnosisP_38; "base\\diagnosis\\pdui\\perfmon\\mon\\sp"...
0x18007ccf9  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18007ccfe  jmp     short loc_18007CD3A
0x18007cd00  mov     ebx, 80004005h
0x18007cd05  jmp     short loc_18007CD3A
0x18007cd07  mov     rcx, [rdi+0F0h]
0x18007cd0e  test    rcx, rcx
0x18007cd11  jz      short loc_18007CD2B
0x18007cd13  mov     rax, [rcx]
0x18007cd16  mov     rax, [rax+168h]
0x18007cd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd22  mov     rcx, rax; hWnd
0x18007cd25  call    cs:__imp_UpdateWindow
0x18007cd2b  mov     rcx, [rsi]
0x18007cd2e  call    cs:__imp_?GetWidth@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetWidth(void)
0x18007cd34  mov     [rdi+0ECh], eax
0x18007cd3a  mov     rcx, [rsp+38h+arg_8]
0x18007cd3f  test    rcx, rcx
0x18007cd42  jz      short loc_18007CD4A
0x18007cd44  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007cd4a  mov     rsi, [rsp+38h+arg_10]
0x18007cd4f  mov     eax, ebx
0x18007cd51  mov     rbx, [rsp+38h+arg_0]
0x18007cd56  add     rsp, 30h
0x18007cd5a  pop     rdi
0x18007cd5b  retn
```
