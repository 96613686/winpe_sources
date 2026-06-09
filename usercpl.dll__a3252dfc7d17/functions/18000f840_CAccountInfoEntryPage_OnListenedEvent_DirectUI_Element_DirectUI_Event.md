# CAccountInfoEntryPage::OnListenedEvent(DirectUI::Element *,DirectUI::Event *)

- ea: `0x18000f840`
- end: `0x18000f925`
- name: `?OnListenedEvent@CAccountInfoEntryPage@@UEAAXPEAVElement@DirectUI@@PEAUEvent@3@@Z`
- size: `229`
- prototype: `void __fastcall(CAccountInfoEntryPage *__hidden this, struct DirectUI::Element *, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f840`
- `0x18000fcf8`
- `0x18001017c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f90f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f90f`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000f867`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000f87e`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000f867`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000f87e`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000f8da`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000f8eb`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000f8da`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000f8eb`
- `DUI70!StrToID` at `0x18000f8a2`
- `DUI70!StrToID` at `0x18000f8a2`

## pseudocode

```c
void __fastcall CAccountInfoEntryPage::OnListenedEvent(
        CAccountInfoEntryPage *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Event *a3)
{
  __int64 v5; // rdx
  __int16 v6; // bx
  CAccountInfoEntryPage *v7; // rcx
  HWND v8; // rdx
  void *v9; // rcx
  unsigned __int16 *v10; // rcx
  LPVOID pv; // [rsp+40h] [rbp+20h] BYREF
  unsigned __int16 *v12; // [rsp+48h] [rbp+28h] BYREF

  if ( *((_DWORD *)a3 + 5) == 1
    && *((_QWORD *)a3 + 1) == *(_QWORD *)DirectUI::Button::Click(&pv, a2)
    && *((_QWORD *)a3 + 1) == *(_QWORD *)DirectUI::Button::Click(&pv, v5) )
  {
    v6 = *(_WORD *)(*(_QWORD *)a3 + 144LL);
    if ( v6 == (unsigned __int16)StrToID(L"browsebutton") )
    {
      v8 = (HWND)*((_QWORD *)this + 207);
      v12 = 0;
      pv = 0;
      if ( (int)CAccountInfoEntryPage::_BrowseForUserAndDomain(v7, v8, &v12, (unsigned __int16 **)&pv) >= 0 )
      {
        DirectUI::Element::SetContentString(*((DirectUI::Element **)this + 209), v12);
        DirectUI::Element::SetContentString(*((DirectUI::Element **)this + 213), (const unsigned __int16 *)pv);
        CAccountInfoEntryPage::_SetNextButton(this);
      }
      v9 = pv;
      pv = 0;
      CoTaskMemFree(v9);
      v10 = v12;
      v12 = 0;
      CoTaskMemFree(v10);
    }
  }
}

```

## disassembly

```asm
0x18000f840  mov     [rsp-8+arg_0], rbx
0x18000f845  mov     [rsp-8+arg_8], rdi
0x18000f84a  push    rbp
0x18000f84b  mov     rbp, rsp
0x18000f84e  sub     rsp, 20h
0x18000f852  cmp     dword ptr [r8+14h], 1
0x18000f857  mov     rbx, r8
0x18000f85a  mov     rdi, rcx
0x18000f85d  jnz     loc_18000F915
0x18000f863  lea     rcx, [rbp+pv]
0x18000f867  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18000f86d  mov     rax, [rax]
0x18000f870  cmp     [rbx+8], rax
0x18000f874  jnz     loc_18000F915
0x18000f87a  lea     rcx, [rbp+pv]
0x18000f87e  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18000f884  mov     rcx, [rax]
0x18000f887  cmp     [rbx+8], rcx
0x18000f88b  jnz     loc_18000F915
0x18000f891  mov     rax, [rbx]
0x18000f894  lea     rcx, aBrowsebutton; "browsebutton"
0x18000f89b  movzx   ebx, word ptr [rax+90h]
0x18000f8a2  call    cs:__imp_StrToID
0x18000f8a8  cmp     bx, ax
0x18000f8ab  jnz     short loc_18000F915
0x18000f8ad  mov     rdx, [rdi+678h]; HWND
0x18000f8b4  lea     r9, [rbp+pv]; unsigned __int16 **
0x18000f8b8  xor     ebx, ebx
0x18000f8ba  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18000f8be  mov     [rbp+arg_18], rbx
0x18000f8c2  mov     [rbp+pv], rbx
0x18000f8c6  call    ?_BrowseForUserAndDomain@CAccountInfoEntryPage@@AEAAJPEAUHWND__@@PEAPEAG1@Z; CAccountInfoEntryPage::_BrowseForUserAndDomain(HWND__ *,ushort * *,ushort * *)
0x18000f8cb  test    eax, eax
0x18000f8cd  js      short loc_18000F8F9
0x18000f8cf  mov     rdx, [rbp+arg_18]
0x18000f8d3  mov     rcx, [rdi+688h]
0x18000f8da  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18000f8e0  mov     rdx, [rbp+pv]
0x18000f8e4  mov     rcx, [rdi+6A8h]
0x18000f8eb  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18000f8f1  mov     rcx, rdi; this
0x18000f8f4  call    ?_SetNextButton@CAccountInfoEntryPage@@AEAAXXZ; CAccountInfoEntryPage::_SetNextButton(void)
0x18000f8f9  mov     rcx, [rbp+pv]; pv
0x18000f8fd  mov     [rbp+pv], rbx
0x18000f901  call    cs:__imp_CoTaskMemFree
0x18000f907  mov     rcx, [rbp+arg_18]; pv
0x18000f90b  mov     [rbp+arg_18], rbx
0x18000f90f  call    cs:__imp_CoTaskMemFree
0x18000f915  mov     rbx, [rsp+20h+arg_0]
0x18000f91a  mov     rdi, [rsp+20h+arg_8]
0x18000f91f  add     rsp, 20h
0x18000f923  pop     rbp
0x18000f924  retn
```
