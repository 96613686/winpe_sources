# FrameProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)

- ea: `0x180053680`
- end: `0x180053701`
- name: `?CreateDUI@FrameProvider@@UEAAJPEAVIXElementCP@DirectUI@@PEAPEAUHWND__@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, struct DirectUI::IXElementCP *, HWND *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180053680`
- `0x180054bf0`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x1800536e2`
- `KERNEL32!DeactivateActCtx` at `0x1800536e2`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x1800536b3`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x1800536b3`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x1800536ca`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x1800536ca`

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
0x180053680  mov     rax, rsp
0x180053683  mov     [rax+8], rbx
0x180053687  mov     [rax+10h], rsi
0x18005368b  push    rdi
0x18005368c  sub     rsp, 20h
0x180053690  mov     rsi, rcx
0x180053693  mov     qword ptr [rax+20h], 0
0x18005369b  lea     rcx, [rax+20h]
0x18005369f  mov     rbx, r8
0x1800536a2  mov     rdi, rdx
0x1800536a5  call    SHActivateContext
0x1800536aa  mov     r8, rbx
0x1800536ad  mov     rdx, rdi
0x1800536b0  mov     rcx, rsi
0x1800536b3  call    cs:__imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x1800536ba  nop     dword ptr [rax+rax+00h]
0x1800536bf  mov     ebx, eax
0x1800536c1  test    eax, eax
0x1800536c3  js      short loc_1800536D6
0x1800536c5  mov     dl, 1
0x1800536c7  mov     rcx, rsi
0x1800536ca  call    cs:__imp_?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z; DirectUI::XProvider::SetHandleEnterKey(bool)
0x1800536d1  nop     dword ptr [rax+rax+00h]
0x1800536d6  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x1800536db  test    rdx, rdx
0x1800536de  jz      short loc_1800536EE
0x1800536e0  xor     ecx, ecx; dwFlags
0x1800536e2  call    cs:__imp_DeactivateActCtx
0x1800536e9  nop     dword ptr [rax+rax+00h]
0x1800536ee  mov     rsi, [rsp+28h+arg_8]
0x1800536f3  mov     eax, ebx
0x1800536f5  mov     rbx, [rsp+28h+arg_0]
0x1800536fa  add     rsp, 20h
0x1800536fe  pop     rdi
0x1800536ff  retn
```
