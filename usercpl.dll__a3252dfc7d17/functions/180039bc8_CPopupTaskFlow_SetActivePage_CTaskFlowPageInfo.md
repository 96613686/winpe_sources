# CPopupTaskFlow::_SetActivePage(CTaskFlowPageInfo *)

- ea: `0x180039bc8`
- end: `0x180039cd6`
- name: `?_SetActivePage@CPopupTaskFlow@@AEAAJPEAVCTaskFlowPageInfo@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CPopupTaskFlow *__hidden this, struct CTaskFlowPageInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037400`
- `0x180038e40`

## callees

- `0x180026218`
- `0x180036b08`
- `0x180039bc8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c34`
- `DUI70!?SetYScrollable@BaseScrollViewer@DirectUI@@QEAAJ_N@Z` at `0x180039c71`
- `DUI70!?SetYScrollable@BaseScrollViewer@DirectUI@@QEAAJ_N@Z` at `0x180039c71`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180039bee`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180039cc1`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180039bee`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180039cc1`
- `DUI70!StrToID` at `0x180039c49`
- `DUI70!StrToID` at `0x180039c49`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180039c55`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180039c55`

## string_xrefs

- `0x180039c3e`: `taskscrollbarstyle`

## pseudocode

```c
__int64 __fastcall CPopupTaskFlow::_SetActivePage(CPopupTaskFlow *this, struct CTaskFlowPageInfo *a2)
{
  __int64 v2; // rsi
  bool v4; // r14
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // r15
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  struct DirectUI::Element *Descendent; // rax
  __int64 v12; // rcx
  int v13; // ebx
  DirectUI::Element *v14; // rcx
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = a2;
  v4 = 1;
  v5 = *((_QWORD *)a2 + 4);
  DirectUI::Element::SetEnabled(*(DirectUI::Element **)(v5 + 24), 1);
  v6 = *((_QWORD *)this + 6);
  pv = 0;
  v7 = *(_QWORD *)(v6 + 32);
  if ( (int)CoAllocString((const unsigned __int16 *)(v7 + 552), (unsigned __int16 **)&pv) >= 0 )
  {
    (*(void (__fastcall **)(char *, LPVOID))(*((_QWORD *)this + 1) + 64LL))((char *)this + 8, pv);
    CoTaskMemFree(pv);
  }
  v8 = *((_QWORD *)this + 8);
  v9 = *(DirectUI::Element **)(v7 + 24);
  v10 = StrToID(L"taskscrollbarstyle");
  Descendent = DirectUI::Element::FindDescendent(v9, v10);
  if ( Descendent )
    v4 = *((_BYTE *)Descendent + 149) & 1;
  DirectUI::BaseScrollViewer::SetYScrollable(*(DirectUI::BaseScrollViewer **)(v8 + 224), v4);
  *((_BYTE *)this + 84) = 0;
  v12 = *(_QWORD *)(v5 + 1608);
  if ( v12 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
    if ( v13 < 0 )
    {
      *((_QWORD *)this + 6) = v2;
      v14 = *(DirectUI::Element **)(v5 + 24);
LABEL_11:
      DirectUI::Element::SetEnabled(v14, 0);
      return (unsigned int)v13;
    }
  }
  else
  {
    v13 = 0;
  }
  CPopupTaskFlowRoot::NavigateToPage(*((CPopupTaskFlowRoot **)this + 8), *(struct DirectUI::Element **)(v5 + 24));
  if ( v2 )
  {
    v14 = *(DirectUI::Element **)(*(_QWORD *)(v2 + 32) + 24LL);
    goto LABEL_11;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180039bc8  push    rbx
0x180039bca  push    rbp
0x180039bcb  push    rsi
0x180039bcc  push    rdi
0x180039bcd  push    r14
0x180039bcf  push    r15
0x180039bd1  sub     rsp, 28h
0x180039bd5  mov     rsi, [rcx+30h]
0x180039bd9  mov     rdi, rcx
0x180039bdc  mov     [rcx+30h], rdx
0x180039be0  mov     r14b, 1
0x180039be3  mov     rbp, [rdx+20h]
0x180039be7  mov     dl, r14b
0x180039bea  mov     rcx, [rbp+18h]
0x180039bee  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180039bf4  mov     rax, [rdi+30h]
0x180039bf8  lea     rdx, [rsp+58h+pv]; unsigned __int16 **
0x180039bfd  mov     [rsp+58h+pv], 0
0x180039c06  mov     rbx, [rax+20h]
0x180039c0a  lea     rcx, [rbx+228h]; unsigned __int16 *
0x180039c11  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x180039c16  test    eax, eax
0x180039c18  js      short loc_180039C3A
0x180039c1a  mov     rdx, [rsp+58h+pv]
0x180039c1f  lea     rcx, [rdi+8]
0x180039c23  mov     rax, [rcx]
0x180039c26  mov     rax, [rax+40h]
0x180039c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c2f  mov     rcx, [rsp+58h+pv]; pv
0x180039c34  call    cs:__imp_CoTaskMemFree
0x180039c3a  mov     r15, [rdi+40h]
0x180039c3e  lea     rcx, aTaskscrollbars; "taskscrollbarstyle"
0x180039c45  mov     rbx, [rbx+18h]
0x180039c49  call    cs:__imp_StrToID
0x180039c4f  movzx   edx, ax
0x180039c52  mov     rcx, rbx
0x180039c55  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180039c5b  test    rax, rax
0x180039c5e  jz      short loc_180039C67
0x180039c60  and     r14b, [rax+95h]
0x180039c67  mov     rcx, [r15+0E0h]
0x180039c6e  mov     dl, r14b
0x180039c71  call    cs:__imp_?SetYScrollable@BaseScrollViewer@DirectUI@@QEAAJ_N@Z; DirectUI::BaseScrollViewer::SetYScrollable(bool)
0x180039c77  mov     byte ptr [rdi+54h], 0
0x180039c7b  mov     rcx, [rbp+648h]
0x180039c82  test    rcx, rcx
0x180039c85  jz      short loc_180039CA3
0x180039c87  mov     rax, [rcx]
0x180039c8a  mov     rax, [rax+18h]
0x180039c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c93  mov     ebx, eax
0x180039c95  test    eax, eax
0x180039c97  jns     short loc_180039CA5
0x180039c99  mov     [rdi+30h], rsi
0x180039c9d  mov     rcx, [rbp+18h]
0x180039ca1  jmp     short loc_180039CBF
0x180039ca3  xor     ebx, ebx
0x180039ca5  mov     rdx, [rbp+18h]; struct DirectUI::Element *
0x180039ca9  mov     rcx, [rdi+40h]; this
0x180039cad  call    ?NavigateToPage@CPopupTaskFlowRoot@@QEAAJPEAVElement@DirectUI@@@Z; CPopupTaskFlowRoot::NavigateToPage(DirectUI::Element *)
0x180039cb2  test    rsi, rsi
0x180039cb5  jz      short loc_180039CC7
0x180039cb7  mov     rcx, [rsi+20h]
0x180039cbb  mov     rcx, [rcx+18h]
0x180039cbf  xor     edx, edx
0x180039cc1  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180039cc7  mov     eax, ebx
0x180039cc9  add     rsp, 28h
0x180039ccd  pop     r15
0x180039ccf  pop     r14
0x180039cd1  pop     rdi
0x180039cd2  pop     rsi
0x180039cd3  pop     rbp
0x180039cd4  pop     rbx
0x180039cd5  retn
```
