# CCRichEdit::CreateHWND(HWND__ *)

- ea: `0x18000c040`
- end: `0x18000c06d`
- name: `?CreateHWND@CCRichEdit@@UEAAPEAUHWND__@@PEAU2@@Z`
- size: `45`
- prototype: `HWND __fastcall(CCRichEdit *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?CreateAccNameLabel@HWNDHost@DirectUI@@IEAAPEAUHWND__@@PEAU3@@Z` at `0x18000c050`
- `DUI70!?CreateAccNameLabel@HWNDHost@DirectUI@@IEAAPEAUHWND__@@PEAU3@@Z` at `0x18000c050`
- `DUI70!?CreateHWND@CCBase@DirectUI@@UEAAPEAUHWND__@@PEAU3@@Z` at `0x18000c066`

## pseudocode

```c
HWND __fastcall CCRichEdit::CreateHWND(CCRichEdit *this, HWND a2)
{
  DirectUI::HWNDHost::CreateAccNameLabel(this, a2);
  return DirectUI::CCBase::CreateHWND(this, a2);
}

```

## disassembly

```asm
0x18000c040  mov     [rsp+arg_0], rbx
0x18000c045  push    rdi
0x18000c046  sub     rsp, 20h
0x18000c04a  mov     rbx, rdx
0x18000c04d  mov     rdi, rcx
0x18000c050  call    cs:__imp_?CreateAccNameLabel@HWNDHost@DirectUI@@IEAAPEAUHWND__@@PEAU3@@Z; DirectUI::HWNDHost::CreateAccNameLabel(HWND__ *)
0x18000c056  mov     rdx, rbx
0x18000c059  mov     rcx, rdi
0x18000c05c  mov     rbx, [rsp+28h+arg_0]
0x18000c061  add     rsp, 20h
0x18000c065  pop     rdi
0x18000c066  jmp     cs:__imp_?CreateHWND@CCBase@DirectUI@@UEAAPEAUHWND__@@PEAU3@@Z; DirectUI::CCBase::CreateHWND(HWND__ *)
```
