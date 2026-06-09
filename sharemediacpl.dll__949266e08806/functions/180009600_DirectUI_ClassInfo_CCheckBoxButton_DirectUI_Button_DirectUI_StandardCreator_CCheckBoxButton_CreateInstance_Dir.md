# DirectUI::ClassInfo<CCheckBoxButton,DirectUI::Button,DirectUI::StandardCreator<CCheckBoxButton>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x180009600`
- end: `0x180009698`
- name: `?CreateInstance@?$ClassInfo@VCCheckBoxButton@@VButton@DirectUI@@V?$StandardCreator@VCCheckBoxButton@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009600`
- `0x18000e39c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009619`
- `KERNEL32!GetProcessHeap` at `0x180009619`
- `KERNEL32!HeapAlloc` at `0x18000962d`
- `KERNEL32!HeapAlloc` at `0x18000962d`
- `DUI70!??0Button@DirectUI@@QEAA@XZ` at `0x18000963e`
- `DUI70!??0Button@DirectUI@@QEAA@XZ` at `0x18000963e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009680`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009680`
- `DUI70!?Initialize@Button@DirectUI@@QEAAJIPEAVElement@2@PEAK@Z` at `0x18000965c`
- `DUI70!?Initialize@Button@DirectUI@@QEAAJIPEAVElement@2@PEAK@Z` at `0x18000965c`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CCheckBoxButton,DirectUI::Button,DirectUI::StandardCreator<CCheckBoxButton>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Button **a4)
{
  HANDLE ProcessHeap; // rax
  DirectUI::Button *v8; // rax
  DirectUI::Button *v9; // rdi
  int ChildElements; // ebx

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (DirectUI::Button *)HeapAlloc(ProcessHeap, 8u, 0xE0u);
  v9 = v8;
  if ( v8 )
  {
    DirectUI::Button::Button(v8);
    *(_QWORD *)v9 = &CCheckBoxButton::`vftable';
    ChildElements = DirectUI::Button::Initialize(v9, 3u, a2, a3);
    if ( ChildElements >= 0 )
      ChildElements = CCheckBoxButton::_CreateChildElements((struct DirectUI::Element **)v9);
    if ( ChildElements < 0 )
      DirectUI::Element::Destroy(v9, 0);
    else
      *a4 = v9;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)ChildElements;
}

```

## disassembly

```asm
0x180009600  push    rbx
0x180009602  push    rbp
0x180009603  push    rsi
0x180009604  push    rdi
0x180009605  sub     rsp, 28h
0x180009609  mov     rsi, r9
0x18000960c  mov     qword ptr [r9], 0
0x180009613  mov     rbx, r8
0x180009616  mov     rbp, rdx
0x180009619  call    cs:__imp_GetProcessHeap
0x18000961f  mov     edx, 8; dwFlags
0x180009624  mov     r8d, 0E0h; dwBytes
0x18000962a  mov     rcx, rax; hHeap
0x18000962d  call    cs:__imp_HeapAlloc
0x180009633  mov     rdi, rax
0x180009636  test    rax, rax
0x180009639  jz      short loc_180009688
0x18000963b  mov     rcx, rax
0x18000963e  call    cs:__imp_??0Button@DirectUI@@QEAA@XZ; DirectUI::Button::Button(void)
0x180009644  lea     rax, ??_7CCheckBoxButton@@6B@; const CCheckBoxButton::`vftable'
0x18000964b  mov     r9, rbx
0x18000964e  mov     r8, rbp
0x180009651  mov     [rdi], rax
0x180009654  mov     edx, 3
0x180009659  mov     rcx, rdi
0x18000965c  call    cs:__imp_?Initialize@Button@DirectUI@@QEAAJIPEAVElement@2@PEAK@Z; DirectUI::Button::Initialize(uint,DirectUI::Element *,ulong *)
0x180009662  mov     ebx, eax
0x180009664  test    eax, eax
0x180009666  js      short loc_180009672
0x180009668  mov     rcx, rdi; this
0x18000966b  call    ?_CreateChildElements@CCheckBoxButton@@AEAAJXZ; CCheckBoxButton::_CreateChildElements(void)
0x180009670  mov     ebx, eax
0x180009672  test    ebx, ebx
0x180009674  js      short loc_18000967B
0x180009676  mov     [rsi], rdi
0x180009679  jmp     short loc_18000968D
0x18000967b  xor     edx, edx
0x18000967d  mov     rcx, rdi
0x180009680  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180009686  jmp     short loc_18000968D
0x180009688  mov     ebx, 8007000Eh
0x18000968d  mov     eax, ebx
0x18000968f  add     rsp, 28h
0x180009693  pop     rdi
0x180009694  pop     rsi
0x180009695  pop     rbp
0x180009696  pop     rbx
0x180009697  retn
```
