# CSearchOptionsDialog::_OnNotify(tagNMHEADERW *)

- ea: `0x180027ef8`
- end: `0x180027fe4`
- name: `?_OnNotify@CSearchOptionsDialog@@AEAA_JPEAUtagNMHEADERW@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(CSearchOptionsDialog *__hidden this, struct tagNMHEADERW *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180028520`

## callees

- `0x18001484c`
- `0x180016078`
- `0x180019048`
- `0x18001d004`
- `0x18001d104`
- `0x18002731c`
- `0x180027ef8`

## import_xrefs

- `USER32!GetDlgItem` at `0x180027fac`
- `USER32!GetDlgItem` at `0x180027fac`
- `USER32!InvalidateRect` at `0x180027fbf`
- `USER32!InvalidateRect` at `0x180027fbf`

## string_xrefs

- `0x180027f63`: `MainIdxCplLink`

## pseudocode

```c
_BOOL8 __fastcall CSearchOptionsDialog::_OnNotify(HWND *this, struct tagNMHEADERW *a2)
{
  UINT code; // eax
  __int64 v3; // rdi
  CIndexedLocation *v5; // rcx
  HWND DlgItem; // rax

  code = a2->hdr.code;
  v3 = 0;
  switch ( code )
  {
    case 0xFFFFFEBF:
      DlgItem = GetDlgItem(*this, 405);
      InvalidateRect(DlgItem, 0, 1);
      return a2->pitem->cxy < 2;
    case 0xFFFFFEC0:
      LOBYTE(v3) = a2->pitem->cxy < 5;
      break;
    case 0xFFFFFF99:
      v5 = *(CIndexedLocation **)&a2[1].hdr.code;
      if ( v5 )
        CIndexedLocation::`scalar deleting destructor'(v5, (unsigned int)a2);
      break;
    case 0xFFFFFFF9:
      if ( a2->hdr.idFrom == 405 )
        CIndexedLocationsBasket::OnGetFocus((CIndexedLocationsBasket *)(this + 13));
      break;
    case 0xFFFFFFFC:
    case 0xFFFFFFFE:
      if ( a2->hdr.idFrom == 408 )
      {
        SearchOptionsTelemetry::HowIndexingAffectsSearchesClicked();
        LaunchHSC(L"68dd14f2-a9cb-4134-a076-b8abb011a1f6");
      }
      if ( a2->hdr.idFrom == 412 )
      {
        SearchOptionsTelemetry::TroubleshootIndexingClicked();
        LaunchIndexingTroubleshooter(L"MainIdxCplLink");
      }
      break;
  }
  return v3;
}

```

## disassembly

```asm
0x180027ef8  mov     [rsp+arg_0], rbx
0x180027efd  mov     [rsp+arg_8], rsi
0x180027f02  push    rdi
0x180027f03  sub     rsp, 20h
0x180027f07  mov     eax, [rdx+10h]
0x180027f0a  xor     edi, edi
0x180027f0c  mov     rbx, rdx
0x180027f0f  cmp     eax, 0FFFFFEBFh
0x180027f14  jz      loc_180027FA4
0x180027f1a  cmp     eax, 0FFFFFEC0h
0x180027f1f  jz      short loc_180027F96
0x180027f21  cmp     eax, 0FFFFFF99h
0x180027f24  jz      short loc_180027F86
0x180027f26  cmp     eax, 0FFFFFFF9h
0x180027f29  jz      short loc_180027F71
0x180027f2b  cmp     eax, 0FFFFFFFCh
0x180027f2e  jz      short loc_180027F39
0x180027f30  cmp     eax, 0FFFFFFFEh
0x180027f33  jnz     loc_180027FD1
0x180027f39  cmp     qword ptr [rdx+8], 198h
0x180027f41  jnz     short loc_180027F54
0x180027f43  call    ?HowIndexingAffectsSearchesClicked@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::HowIndexingAffectsSearchesClicked(void)
0x180027f48  lea     rcx, a68dd14f2A9cb41; "68dd14f2-a9cb-4134-a076-b8abb011a1f6"
0x180027f4f  call    ?LaunchHSC@@YAJPEBG@Z; LaunchHSC(ushort const *)
0x180027f54  cmp     qword ptr [rbx+8], 19Ch
0x180027f5c  jnz     short loc_180027FD1
0x180027f5e  call    ?TroubleshootIndexingClicked@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::TroubleshootIndexingClicked(void)
0x180027f63  lea     rcx, aMainidxcpllink; "MainIdxCplLink"
0x180027f6a  call    ?LaunchIndexingTroubleshooter@@YAJPEBG@Z; LaunchIndexingTroubleshooter(ushort const *)
0x180027f6f  jmp     short loc_180027FD1
0x180027f71  cmp     qword ptr [rdx+8], 195h
0x180027f79  jnz     short loc_180027FD1
0x180027f7b  add     rcx, 68h ; 'h'; this
0x180027f7f  call    ?OnGetFocus@CIndexedLocationsBasket@@QEAAJXZ; CIndexedLocationsBasket::OnGetFocus(void)
0x180027f84  jmp     short loc_180027FD1
0x180027f86  mov     rcx, [rdx+38h]; this
0x180027f8a  test    rcx, rcx
0x180027f8d  jz      short loc_180027FD1
0x180027f8f  call    ??_GCIndexedLocation@@QEAAPEAXI@Z; CIndexedLocation::`scalar deleting destructor'(uint)
0x180027f94  jmp     short loc_180027FD1
0x180027f96  mov     rax, [rdx+20h]
0x180027f9a  cmp     dword ptr [rax+4], 5
0x180027f9e  setl    dil
0x180027fa2  jmp     short loc_180027FD1
0x180027fa4  mov     rcx, [rcx]; hDlg
0x180027fa7  mov     edx, 195h; nIDDlgItem
0x180027fac  call    cs:__imp_GetDlgItem
0x180027fb2  mov     esi, 1
0x180027fb7  xor     edx, edx; lpRect
0x180027fb9  mov     rcx, rax; hWnd
0x180027fbc  mov     r8d, esi; bErase
0x180027fbf  call    cs:__imp_InvalidateRect
0x180027fc5  mov     rcx, [rbx+20h]
0x180027fc9  cmp     dword ptr [rcx+4], 2
0x180027fcd  cmovl   rdi, rsi
0x180027fd1  mov     rbx, [rsp+28h+arg_0]
0x180027fd6  mov     rax, rdi
0x180027fd9  mov     rsi, [rsp+28h+arg_8]
0x180027fde  add     rsp, 20h
0x180027fe2  pop     rdi
0x180027fe3  retn
```
