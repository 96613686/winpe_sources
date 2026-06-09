# DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18001a290`
- end: `0x18001a31f`
- name: `?CreateInstance@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001a290`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001a2a9`
- `KERNEL32!GetProcessHeap` at `0x18001a2a9`
- `KERNEL32!HeapAlloc` at `0x18001a2bd`
- `KERNEL32!HeapAlloc` at `0x18001a2bd`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18001a2e9`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18001a2e9`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x18001a2ce`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x18001a2ce`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a307`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a307`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001a2fd`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001a2fd`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  HANDLE ProcessHeap; // rax
  DirectUI::Element *v8; // rax
  DirectUI::Element *v9; // rbx
  int v10; // edi

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (DirectUI::Element *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v9 = v8;
  if ( v8 )
  {
    DirectUI::Element::Element(v8);
    *(_QWORD *)v9 = &CFocusIndicator::`vftable';
    v10 = DirectUI::Element::Initialize(v9, 0, a2, a3);
    if ( v10 < 0 )
    {
      DirectUI::Element::Destroy(v9, 0);
    }
    else
    {
      *a4 = v9;
      return (unsigned int)DirectUI::Element::SetActive(v9, 0);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a290  push    rbx
0x18001a292  push    rbp
0x18001a293  push    rsi
0x18001a294  push    rdi
0x18001a295  sub     rsp, 28h
0x18001a299  mov     rsi, r9
0x18001a29c  mov     qword ptr [r9], 0
0x18001a2a3  mov     rdi, r8
0x18001a2a6  mov     rbp, rdx
0x18001a2a9  call    cs:__imp_GetProcessHeap
0x18001a2af  mov     edx, 8; dwFlags
0x18001a2b4  mov     r8d, 0C8h; dwBytes
0x18001a2ba  mov     rcx, rax; hHeap
0x18001a2bd  call    cs:__imp_HeapAlloc
0x18001a2c3  mov     rbx, rax
0x18001a2c6  test    rax, rax
0x18001a2c9  jz      short loc_18001A30F
0x18001a2cb  mov     rcx, rax
0x18001a2ce  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x18001a2d4  lea     rax, ??_7CFocusIndicator@@6B@; const CFocusIndicator::`vftable'
0x18001a2db  mov     r9, rdi
0x18001a2de  mov     r8, rbp
0x18001a2e1  mov     [rbx], rax
0x18001a2e4  xor     edx, edx
0x18001a2e6  mov     rcx, rbx
0x18001a2e9  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x18001a2ef  xor     edx, edx
0x18001a2f1  mov     rcx, rbx
0x18001a2f4  mov     edi, eax
0x18001a2f6  test    eax, eax
0x18001a2f8  js      short loc_18001A307
0x18001a2fa  mov     [rsi], rbx
0x18001a2fd  call    cs:__imp_?SetActive@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetActive(int)
0x18001a303  mov     edi, eax
0x18001a305  jmp     short loc_18001A314
0x18001a307  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18001a30d  jmp     short loc_18001A314
0x18001a30f  mov     edi, 8007000Eh
0x18001a314  mov     eax, edi
0x18001a316  add     rsp, 28h
0x18001a31a  pop     rdi
0x18001a31b  pop     rsi
0x18001a31c  pop     rbp
0x18001a31d  pop     rbx
0x18001a31e  retn
```
