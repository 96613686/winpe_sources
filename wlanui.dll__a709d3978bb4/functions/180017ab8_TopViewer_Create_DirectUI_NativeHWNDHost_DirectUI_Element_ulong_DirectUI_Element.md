# TopViewer::Create(DirectUI::NativeHWNDHost *,DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x180017ab8`
- end: `0x180017bba`
- name: `?Create@TopViewer@@SAJPEAVNativeHWNDHost@DirectUI@@PEAVElement@3@PEAKPEAPEAV43@@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct DirectUI::NativeHWNDHost *, struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017fcc`

## callees

- `0x180017ab8`
- `0x180018194`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180017ae8`
- `KERNEL32!HeapAlloc` at `0x180017ae8`
- `KERNEL32!GetProcessHeap` at `0x180017ad4`
- `KERNEL32!GetProcessHeap` at `0x180017ad4`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180017b9b`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180017b9b`
- `DUI70!??0HWNDElement@DirectUI@@QEAA@XZ` at `0x180017afd`
- `DUI70!??0HWNDElement@DirectUI@@QEAA@XZ` at `0x180017afd`

## pseudocode

```c
__int64 __fastcall TopViewer::Create(
        HWND *a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        struct DirectUI::Element **a4)
{
  HANDLE ProcessHeap; // rax
  DirectUI::HWNDElement *v7; // rax
  DirectUI::HWNDElement *v8; // rbx
  struct DirectUI::Element *v9; // r8
  struct DirectUI::Layout *v10; // r9
  int v11; // esi

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (DirectUI::HWNDElement *)HeapAlloc(ProcessHeap, 8u, 0x380u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  DirectUI::HWNDElement::HWNDElement(v7);
  *((_QWORD *)v8 + 33) = 0;
  *(_QWORD *)v8 = &TopViewer::`vftable'{for `DirectUI::HWNDElement'};
  *((_QWORD *)v8 + 35) = 0;
  *((_QWORD *)v8 + 32) = &TopViewer::`vftable'{for `ITouchKeyboardNotificationCallback'};
  *((_QWORD *)v8 + 102) = 0;
  *((_QWORD *)v8 + 106) = &CTouchKeyboardNotifications::`vftable';
  *((_QWORD *)v8 + 104) = 0;
  *((_QWORD *)v8 + 107) = 0;
  *((_BYTE *)v8 + 864) = 0;
  *((_QWORD *)v8 + 109) = 0;
  *((_QWORD *)v8 + 110) = 0;
  *((_QWORD *)v8 + 111) = 0;
  v11 = TopViewer::Initialize(v8, a1, v9, v10);
  if ( v11 < 0 )
  {
    DirectUI::Element::Destroy(v8, 1);
    return (unsigned int)v11;
  }
  else
  {
    *a4 = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x180017ab8  mov     [rsp+arg_0], rbx
0x180017abd  mov     [rsp+arg_8], rsi
0x180017ac2  push    rdi
0x180017ac3  sub     rsp, 20h
0x180017ac7  mov     rdi, r9
0x180017aca  mov     qword ptr [r9], 0
0x180017ad1  mov     rsi, rcx
0x180017ad4  call    cs:__imp_GetProcessHeap
0x180017ada  mov     edx, 8; dwFlags
0x180017adf  mov     r8d, 380h; dwBytes
0x180017ae5  mov     rcx, rax; hHeap
0x180017ae8  call    cs:__imp_HeapAlloc
0x180017aee  mov     rbx, rax
0x180017af1  test    rax, rax
0x180017af4  jz      loc_180017BA5
0x180017afa  mov     rcx, rax
0x180017afd  call    cs:__imp_??0HWNDElement@DirectUI@@QEAA@XZ; DirectUI::HWNDElement::HWNDElement(void)
0x180017b03  mov     qword ptr [rbx+108h], 0
0x180017b0e  lea     rax, ??_7TopViewer@@6BHWNDElement@DirectUI@@@; const TopViewer::`vftable'{for `DirectUI::HWNDElement'}
0x180017b15  mov     [rbx], rax
0x180017b18  mov     rdx, rsi; struct DirectUI::NativeHWNDHost *
0x180017b1b  mov     qword ptr [rbx+118h], 0
0x180017b26  lea     rax, ??_7TopViewer@@6BITouchKeyboardNotificationCallback@@@; const TopViewer::`vftable'{for `ITouchKeyboardNotificationCallback'}
0x180017b2d  mov     [rbx+100h], rax
0x180017b34  mov     rcx, rbx; this
0x180017b37  mov     qword ptr [rbx+330h], 0
0x180017b42  lea     rax, ??_7CTouchKeyboardNotifications@@6B@; const CTouchKeyboardNotifications::`vftable'
0x180017b49  mov     [rbx+350h], rax
0x180017b50  xor     eax, eax
0x180017b52  mov     qword ptr [rbx+340h], 0
0x180017b5d  mov     qword ptr [rbx+358h], 0
0x180017b68  mov     byte ptr [rbx+360h], 0
0x180017b6f  mov     [rbx+368h], rax
0x180017b76  mov     [rbx+370h], rax
0x180017b7d  mov     [rbx+378h], rax
0x180017b84  call    ?Initialize@TopViewer@@QEAAJPEAVNativeHWNDHost@DirectUI@@PEAVElement@3@PEAK@Z; TopViewer::Initialize(DirectUI::NativeHWNDHost *,DirectUI::Element *,ulong *)
0x180017b89  mov     esi, eax
0x180017b8b  test    eax, eax
0x180017b8d  js      short loc_180017B96
0x180017b8f  mov     [rdi], rbx
0x180017b92  xor     eax, eax
0x180017b94  jmp     short loc_180017BAA
0x180017b96  mov     dl, 1
0x180017b98  mov     rcx, rbx
0x180017b9b  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180017ba1  mov     eax, esi
0x180017ba3  jmp     short loc_180017BAA
0x180017ba5  mov     eax, 8007000Eh
0x180017baa  mov     rbx, [rsp+28h+arg_0]
0x180017baf  mov     rsi, [rsp+28h+arg_8]
0x180017bb4  add     rsp, 20h
0x180017bb8  pop     rdi
0x180017bb9  retn
```
