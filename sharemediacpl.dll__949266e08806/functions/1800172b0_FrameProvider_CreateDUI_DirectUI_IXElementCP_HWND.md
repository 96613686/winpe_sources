# FrameProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)

- ea: `0x1800172b0`
- end: `0x18001731e`
- name: `?CreateDUI@FrameProvider@@UEAAJPEAVIXElementCP@DirectUI@@PEAPEAUHWND__@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, struct DirectUI::IXElementCP *, HWND *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001614c`
- `0x1800172b0`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180017306`
- `KERNEL32!DeactivateActCtx` at `0x180017306`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x1800172e3`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x1800172e3`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x1800172f4`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x1800172f4`

## pseudocode

```c
__int64 __fastcall FrameProvider::CreateDUI(FrameProvider *this, struct DirectUI::IXElementCP *a2, HWND *a3)
{
  int DUI; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+20h] BYREF

  ulCookie = 0;
  SHActivateContext(&ulCookie);
  DUI = DirectUI::XProvider::CreateDUI(this, a2, a3);
  if ( DUI >= 0 )
    DirectUI::XProvider::SetHandleEnterKey(this, 1);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return (unsigned int)DUI;
}

```

## disassembly

```asm
0x1800172b0  mov     rax, rsp
0x1800172b3  mov     [rax+8], rbx
0x1800172b7  mov     [rax+10h], rsi
0x1800172bb  push    rdi
0x1800172bc  sub     rsp, 20h
0x1800172c0  mov     rsi, rcx
0x1800172c3  mov     qword ptr [rax+20h], 0
0x1800172cb  lea     rcx, [rax+20h]
0x1800172cf  mov     rbx, r8
0x1800172d2  mov     rdi, rdx
0x1800172d5  call    SHActivateContext
0x1800172da  mov     r8, rbx
0x1800172dd  mov     rdx, rdi
0x1800172e0  mov     rcx, rsi
0x1800172e3  call    cs:__imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x1800172e9  mov     ebx, eax
0x1800172eb  test    eax, eax
0x1800172ed  js      short loc_1800172FA
0x1800172ef  mov     dl, 1
0x1800172f1  mov     rcx, rsi
0x1800172f4  call    cs:__imp_?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z; DirectUI::XProvider::SetHandleEnterKey(bool)
0x1800172fa  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x1800172ff  test    rdx, rdx
0x180017302  jz      short loc_18001730C
0x180017304  xor     ecx, ecx; dwFlags
0x180017306  call    cs:__imp_DeactivateActCtx
0x18001730c  mov     rsi, [rsp+28h+arg_8]
0x180017311  mov     eax, ebx
0x180017313  mov     rbx, [rsp+28h+arg_0]
0x180017318  add     rsp, 20h
0x18001731c  pop     rdi
0x18001731d  retn
```
