# TopViewer::Initialize(DirectUI::NativeHWNDHost *,DirectUI::Element *,ulong *)

- ea: `0x180018194`
- end: `0x1800182a0`
- name: `?Initialize@TopViewer@@QEAAJPEAVNativeHWNDHost@DirectUI@@PEAVElement@3@PEAK@Z`
- size: `268`
- prototype: `__int64 __fastcall(TopViewer *__hidden this, struct DirectUI::NativeHWNDHost *, struct DirectUI::Element *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017ab8`

## callees

- `0x180018194`
- `0x18001bbb4`

## import_xrefs

- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x18001827c`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x18001827c`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x180018268`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x180018268`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x18001828d`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x18001828d`
- `DUI70!?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x1800181c8`
- `DUI70!?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x1800181c8`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x180018249`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x180018249`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800181f2`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800181f2`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001820a`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001820a`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800181dd`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800181dd`
- `DUI70!?DoubleBuffered@Element@DirectUI@@QEAAX_N@Z` at `0x180018254`
- `DUI70!?DoubleBuffered@Element@DirectUI@@QEAAX_N@Z` at `0x180018254`

## pseudocode

```c
__int64 __fastcall TopViewer::Initialize(
        TopViewer *this,
        HWND *a2,
        struct DirectUI::Element *a3,
        struct DirectUI::Layout *a4)
{
  int v5; // ebx
  DirectUI::NativeHWNDHost *v6; // rcx
  struct DirectUI::Layout *v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = a4;
  *((_QWORD *)this + 35) = a2;
  v5 = DirectUI::HWNDElement::Initialize(this, a2[1], 0, 0, 0, 0);
  if ( v5 >= 0 )
  {
    v5 = DirectUI::Element::SetVisible(this, 1);
    if ( v5 >= 0 )
    {
      v5 = DirectUI::Element::SetAccessible(this, 1);
      if ( v5 >= 0 )
      {
        v5 = DirectUI::Element::SetActive(this, 3);
        if ( v5 >= 0 )
        {
          CTouchKeyboardNotifications::SubscribeToNotifications(
            (char *)this + 848,
            ((unsigned __int64)this + 256) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
          v6 = (DirectUI::NativeHWNDHost *)*((_QWORD *)this + 35);
          *((_DWORD *)this + 210) = 0;
          DirectUI::NativeHWNDHost::Host(v6, this);
          DirectUI::Element::DoubleBuffered(this, 1);
          v8 = 0;
          v5 = DirectUI::FillLayout::Create(&v8);
          if ( v5 >= 0 )
          {
            v5 = DirectUI::Element::SetLayout(this, v8);
            if ( v5 < 0 )
              DirectUI::Layout::Destroy(v8);
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018194  mov     rax, rsp
0x180018197  mov     [rax+8], rbx
0x18001819b  mov     [rax+20h], r9
0x18001819f  push    rdi
0x1800181a0  sub     rsp, 30h
0x1800181a4  mov     [rcx+118h], rdx
0x1800181ab  xor     r9d, r9d
0x1800181ae  mov     rdx, [rdx+8]
0x1800181b2  xor     r8d, r8d
0x1800181b5  mov     qword ptr [rax-10h], 0
0x1800181bd  mov     rdi, rcx
0x1800181c0  mov     qword ptr [rax-18h], 0
0x1800181c8  call    cs:__imp_?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z; DirectUI::HWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x1800181ce  mov     ebx, eax
0x1800181d0  test    eax, eax
0x1800181d2  js      loc_180018293
0x1800181d8  mov     dl, 1
0x1800181da  mov     rcx, rdi
0x1800181dd  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800181e3  mov     ebx, eax
0x1800181e5  test    eax, eax
0x1800181e7  js      loc_180018293
0x1800181ed  mov     dl, 1
0x1800181ef  mov     rcx, rdi
0x1800181f2  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x1800181f8  mov     ebx, eax
0x1800181fa  test    eax, eax
0x1800181fc  js      loc_180018293
0x180018202  mov     edx, 3
0x180018207  mov     rcx, rdi
0x18001820a  call    cs:__imp_?SetActive@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetActive(int)
0x180018210  mov     ebx, eax
0x180018212  test    eax, eax
0x180018214  js      short loc_180018293
0x180018216  lea     rcx, [rdi+100h]
0x18001821d  mov     rax, rdi
0x180018220  neg     rax
0x180018223  sbb     rdx, rdx
0x180018226  and     rdx, rcx
0x180018229  lea     rcx, [rdi+350h]
0x180018230  call    ?SubscribeToNotifications@CTouchKeyboardNotifications@@QEAAJPEAUITouchKeyboardNotificationCallback@@W4TouchKeyboardNotificationsDesired@@@Z; CTouchKeyboardNotifications::SubscribeToNotifications(ITouchKeyboardNotificationCallback *,TouchKeyboardNotificationsDesired)
0x180018235  mov     rcx, [rdi+118h]
0x18001823c  mov     rdx, rdi
0x18001823f  mov     dword ptr [rdi+348h], 0
0x180018249  call    cs:__imp_?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z; DirectUI::NativeHWNDHost::Host(DirectUI::Element *)
0x18001824f  mov     dl, 1
0x180018251  mov     rcx, rdi
0x180018254  call    cs:__imp_?DoubleBuffered@Element@DirectUI@@QEAAX_N@Z; DirectUI::Element::DoubleBuffered(bool)
0x18001825a  lea     rcx, [rsp+38h+arg_18]
0x18001825f  mov     [rsp+38h+arg_18], 0
0x180018268  call    cs:__imp_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z; DirectUI::FillLayout::Create(DirectUI::Layout * *)
0x18001826e  mov     ebx, eax
0x180018270  test    eax, eax
0x180018272  js      short loc_180018293
0x180018274  mov     rdx, [rsp+38h+arg_18]
0x180018279  mov     rcx, rdi
0x18001827c  call    cs:__imp_?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z; DirectUI::Element::SetLayout(DirectUI::Layout *)
0x180018282  mov     ebx, eax
0x180018284  test    eax, eax
0x180018286  jns     short loc_180018293
0x180018288  mov     rcx, [rsp+38h+arg_18]
0x18001828d  call    cs:__imp_?Destroy@Layout@DirectUI@@QEAAXXZ; DirectUI::Layout::Destroy(void)
0x180018293  mov     eax, ebx
0x180018295  mov     rbx, [rsp+38h+arg_0]
0x18001829a  add     rsp, 30h
0x18001829e  pop     rdi
0x18001829f  retn
```
