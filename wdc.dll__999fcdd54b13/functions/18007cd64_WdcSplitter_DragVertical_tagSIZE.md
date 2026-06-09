# WdcSplitter::DragVertical(tagSIZE *)

- ea: `0x18007cd64`
- end: `0x18007ce4b`
- name: `?DragVertical@WdcSplitter@@AEAAJPEAUtagSIZE@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(WdcSplitter *__hidden this, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007d050`

## callees

- `0x18000b854`
- `0x18007cd64`
- `0x180086010`

## import_xrefs

- `USER32!UpdateWindow` at `0x18007ce15`
- `USER32!UpdateWindow` at `0x18007ce15`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007ce38`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007ce38`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18007cdc1`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x18007cdc1`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x18007ce22`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x18007ce22`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x18007cda1`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x18007cda1`

## pseudocode

```c
__int64 __fastcall WdcSplitter::DragVertical(WdcSplitter *this, struct tagSIZE *a2)
{
  bool v2; // zf
  unsigned int v5; // edi
  LONG cy; // ecx
  const struct tagSIZE *Extent; // rax
  int v8; // eax
  __int64 v9; // rcx
  HWND v10; // rax
  struct DirectUI::Value *v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2->cy == 0;
  v12 = 0;
  if ( v2 )
    return 0;
  cy = *((_DWORD *)this + 59);
  if ( cy != -1 )
    goto LABEL_6;
  Extent = DirectUI::Element::GetExtent(*((DirectUI::Element **)this + 27), &v12);
  if ( Extent )
  {
    cy = Extent->cy;
    *((_DWORD *)this + 59) = cy;
LABEL_6:
    v8 = DirectUI::Element::SetHeight(*((DirectUI::Element **)this + 27), cy + a2->cy);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v9 = *((_QWORD *)this + 30);
      if ( v9 )
      {
        v10 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 360LL))(v9);
        UpdateWindow(v10);
      }
      *((_DWORD *)this + 59) = DirectUI::Element::GetHeight(*((DirectUI::Element **)this + 27));
    }
    else
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\splitter.cpp",
        "WdcSplitter::DragVertical",
        0,
        L"FAILURE: 0x%08x",
        v8);
    }
    goto LABEL_12;
  }
  v5 = -2147467259;
LABEL_12:
  if ( v12 )
    DirectUI::Value::Release(v12);
  return v5;
}

```

## disassembly

```asm
0x18007cd64  mov     [rsp+arg_0], rbx
0x18007cd69  push    rdi
0x18007cd6a  sub     rsp, 30h
0x18007cd6e  cmp     dword ptr [rdx+4], 0
0x18007cd72  mov     rdi, rdx
0x18007cd75  mov     rbx, rcx
0x18007cd78  mov     [rsp+38h+arg_8], 0
0x18007cd81  jnz     short loc_18007CD8A
0x18007cd83  xor     edi, edi
0x18007cd85  jmp     loc_18007CE3E
0x18007cd8a  mov     ecx, [rcx+0ECh]
0x18007cd90  cmp     ecx, 0FFFFFFFFh
0x18007cd93  jnz     short loc_18007CDB5
0x18007cd95  mov     rcx, [rbx+0D8h]
0x18007cd9c  lea     rdx, [rsp+38h+arg_8]
0x18007cda1  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x18007cda7  test    rax, rax
0x18007cdaa  jz      short loc_18007CDF0
0x18007cdac  mov     ecx, [rax+4]
0x18007cdaf  mov     [rbx+0ECh], ecx
0x18007cdb5  mov     edx, [rdi+4]
0x18007cdb8  add     edx, ecx
0x18007cdba  mov     rcx, [rbx+0D8h]
0x18007cdc1  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x18007cdc7  mov     edi, eax
0x18007cdc9  test    eax, eax
0x18007cdcb  jns     short loc_18007CDF7
0x18007cdcd  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18007cdd4  mov     [rsp+38h+var_18], eax
0x18007cdd8  xor     r8d, r8d; int
0x18007cddb  lea     rdx, aWdcsplitterDra; "WdcSplitter::DragVertical"
0x18007cde2  lea     rcx, aBaseDiagnosisP_38; "base\\diagnosis\\pdui\\perfmon\\mon\\sp"...
0x18007cde9  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18007cdee  jmp     short loc_18007CE2E
0x18007cdf0  mov     edi, 80004005h
0x18007cdf5  jmp     short loc_18007CE2E
0x18007cdf7  mov     rcx, [rbx+0F0h]
0x18007cdfe  test    rcx, rcx
0x18007ce01  jz      short loc_18007CE1B
0x18007ce03  mov     rax, [rcx]
0x18007ce06  mov     rax, [rax+168h]
0x18007ce0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce12  mov     rcx, rax; hWnd
0x18007ce15  call    cs:__imp_UpdateWindow
0x18007ce1b  mov     rcx, [rbx+0D8h]
0x18007ce22  call    cs:__imp_?GetHeight@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetHeight(void)
0x18007ce28  mov     [rbx+0ECh], eax
0x18007ce2e  mov     rcx, [rsp+38h+arg_8]
0x18007ce33  test    rcx, rcx
0x18007ce36  jz      short loc_18007CE3E
0x18007ce38  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007ce3e  mov     rbx, [rsp+38h+arg_0]
0x18007ce43  mov     eax, edi
0x18007ce45  add     rsp, 30h
0x18007ce49  pop     rdi
0x18007ce4a  retn
```
