# CIdentityWebWizardDUICtrl::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x180071cf8`
- end: `0x180071dc9`
- name: `?Create@CIdentityWebWizardDUICtrl@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z`
- size: `209`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003df18`
- `0x180071f10`

## callees

- `0x180071a88`
- `0x180071cf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071d11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071d11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071d25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071d25`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180071d91`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180071d91`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180071da0`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180071da0`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180071d82`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180071d82`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180071d69`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180071d69`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180071d74`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180071d74`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180071dae`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180071dae`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x180071d53`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x180071d53`

## string_xrefs

- `0x180071d5f`: `ReadingPaneModuleHost`

## pseudocode

```c
__int64 __fastcall CIdentityWebWizardDUICtrl::Create(
        struct DirectUI::Element *a1,
        unsigned int *a2,
        struct DirectUI::Element **a3)
{
  HANDLE ProcessHeap; // rax
  CIdentityWebWizardDUICtrl *v7; // rax
  DirectUI::HWNDHost *v8; // rbx
  int v9; // edi

  *a3 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (CIdentityWebWizardDUICtrl *)HeapAlloc(ProcessHeap, 8u, 0x1D0u);
  v8 = v7;
  if ( v7 )
  {
    CIdentityWebWizardDUICtrl::CIdentityWebWizardDUICtrl(v7);
    v9 = DirectUI::HWNDHost::Initialize(v8, 0x19u, 3u, a1, a2);
    if ( v9 >= 0 )
    {
      DirectUI::Element::SetID(v8, L"ReadingPaneModuleHost");
      DirectUI::Element::SetAccessible(v8, 1);
      DirectUI::Element::SetAccRole(v8, 16);
      DirectUI::Element::SetHeight(v8, *((_DWORD *)v8 + 87));
      DirectUI::Element::SetWidth(v8, *((_DWORD *)v8 + 86));
      DirectUI::Element::SetLayoutPos(v8, 4);
      *a3 = v8;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180071cf8  push    rbx
0x180071cfa  push    rbp
0x180071cfb  push    rsi
0x180071cfc  push    rdi
0x180071cfd  sub     rsp, 38h
0x180071d01  mov     rsi, r8
0x180071d04  mov     qword ptr [r8], 0
0x180071d0b  mov     rdi, rdx
0x180071d0e  mov     rbp, rcx
0x180071d11  call    cs:__imp_GetProcessHeap
0x180071d17  mov     edx, 8; dwFlags
0x180071d1c  mov     r8d, 1D0h; dwBytes
0x180071d22  mov     rcx, rax; hHeap
0x180071d25  call    cs:__imp_HeapAlloc
0x180071d2b  mov     rbx, rax
0x180071d2e  test    rax, rax
0x180071d31  jz      loc_180071DB9
0x180071d37  mov     rcx, rax; this
0x180071d3a  call    ??0CIdentityWebWizardDUICtrl@@QEAA@XZ; CIdentityWebWizardDUICtrl::CIdentityWebWizardDUICtrl(void)
0x180071d3f  mov     edx, 19h
0x180071d44  mov     [rsp+58h+var_38], rdi
0x180071d49  mov     r9, rbp
0x180071d4c  mov     rcx, rbx
0x180071d4f  lea     r8d, [rdx-16h]
0x180071d53  call    cs:__imp_?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z; DirectUI::HWNDHost::Initialize(uint,uint,DirectUI::Element *,ulong *)
0x180071d59  mov     edi, eax
0x180071d5b  test    eax, eax
0x180071d5d  js      short loc_180071DBE
0x180071d5f  lea     rdx, aReadingpanemod; "ReadingPaneModuleHost"
0x180071d66  mov     rcx, rbx
0x180071d69  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x180071d6f  mov     dl, 1
0x180071d71  mov     rcx, rbx
0x180071d74  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x180071d7a  mov     edx, 10h
0x180071d7f  mov     rcx, rbx
0x180071d82  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x180071d88  mov     edx, [rbx+15Ch]
0x180071d8e  mov     rcx, rbx
0x180071d91  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x180071d97  mov     edx, [rbx+158h]
0x180071d9d  mov     rcx, rbx
0x180071da0  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x180071da6  mov     edx, 4
0x180071dab  mov     rcx, rbx
0x180071dae  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180071db4  mov     [rsi], rbx
0x180071db7  jmp     short loc_180071DBE
0x180071db9  mov     edi, 8007000Eh
0x180071dbe  mov     eax, edi
0x180071dc0  add     rsp, 38h
0x180071dc4  pop     rdi
0x180071dc5  pop     rsi
0x180071dc6  pop     rbp
0x180071dc7  pop     rbx
0x180071dc8  retn
```
