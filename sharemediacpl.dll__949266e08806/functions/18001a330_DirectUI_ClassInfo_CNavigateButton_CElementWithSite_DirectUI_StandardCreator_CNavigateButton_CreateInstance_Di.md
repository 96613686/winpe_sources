# DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18001a330`
- end: `0x18001a3de`
- name: `?CreateInstance@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001a330`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001a349`
- `KERNEL32!GetProcessHeap` at `0x18001a349`
- `KERNEL32!HeapAlloc` at `0x18001a35d`
- `KERNEL32!HeapAlloc` at `0x18001a35d`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18001a3a5`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18001a3a5`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x18001a36e`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x18001a36e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a3c6`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a3c6`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001a3bc`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001a3bc`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  HANDLE ProcessHeap; // rax
  DirectUI::Element *v8; // rax
  DirectUI::Element *v9; // rdi
  int v10; // ebx

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (DirectUI::Element *)HeapAlloc(ProcessHeap, 8u, 0xE0u);
  v9 = v8;
  if ( v8 )
  {
    DirectUI::Element::Element(v8);
    *(_QWORD *)v9 = &CNavigateButton::`vftable'{for `DirectUI::Element'};
    *((_QWORD *)v9 + 25) = &CElementWithSite::`vftable'{for `IUnknown'};
    *((_QWORD *)v9 + 26) = &CElementWithSite::`vftable';
    v10 = DirectUI::Element::Initialize(v9, 0, a2, a3);
    if ( v10 < 0 )
    {
      DirectUI::Element::Destroy(v9, 0);
    }
    else
    {
      *a4 = v9;
      DirectUI::Element::SetActive(v9, 1);
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
0x18001a330  push    rbx
0x18001a332  push    rbp
0x18001a333  push    rsi
0x18001a334  push    rdi
0x18001a335  sub     rsp, 28h
0x18001a339  mov     rsi, r9
0x18001a33c  mov     qword ptr [r9], 0
0x18001a343  mov     rbx, r8
0x18001a346  mov     rbp, rdx
0x18001a349  call    cs:__imp_GetProcessHeap
0x18001a34f  mov     edx, 8; dwFlags
0x18001a354  mov     r8d, 0E0h; dwBytes
0x18001a35a  mov     rcx, rax; hHeap
0x18001a35d  call    cs:__imp_HeapAlloc
0x18001a363  mov     rdi, rax
0x18001a366  test    rax, rax
0x18001a369  jz      short loc_18001A3CE
0x18001a36b  mov     rcx, rax
0x18001a36e  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x18001a374  lea     rax, ??_7CNavigateButton@@6BElement@DirectUI@@@; const CNavigateButton::`vftable'{for `DirectUI::Element'}
0x18001a37b  mov     r9, rbx
0x18001a37e  mov     [rdi], rax
0x18001a381  mov     r8, rbp
0x18001a384  lea     rax, ??_7CElementWithSite@@6BIUnknown@@@; const CElementWithSite::`vftable'{for `IUnknown'}
0x18001a38b  xor     edx, edx
0x18001a38d  mov     [rdi+0C8h], rax
0x18001a394  mov     rcx, rdi
0x18001a397  lea     rax, ??_7CElementWithSite@@6B@; const CElementWithSite::`vftable'
0x18001a39e  mov     [rdi+0D0h], rax
0x18001a3a5  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x18001a3ab  mov     ebx, eax
0x18001a3ad  mov     rcx, rdi
0x18001a3b0  test    eax, eax
0x18001a3b2  js      short loc_18001A3C4
0x18001a3b4  mov     edx, 1
0x18001a3b9  mov     [rsi], rdi
0x18001a3bc  call    cs:__imp_?SetActive@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetActive(int)
0x18001a3c2  jmp     short loc_18001A3D3
0x18001a3c4  xor     edx, edx
0x18001a3c6  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18001a3cc  jmp     short loc_18001A3D3
0x18001a3ce  mov     ebx, 8007000Eh
0x18001a3d3  mov     eax, ebx
0x18001a3d5  add     rsp, 28h
0x18001a3d9  pop     rdi
0x18001a3da  pop     rsi
0x18001a3db  pop     rbp
0x18001a3dc  pop     rbx
0x18001a3dd  retn
```
