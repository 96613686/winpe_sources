# DirectUI::ClassInfo<HSBSlider,DirectUI::CCTrackBar,DirectUI::StandardCreator<HSBSlider>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18000efd0`
- end: `0x18000f103`
- name: `?CreateInstance@?$ClassInfo@VHSBSlider@@VCCTrackBar@DirectUI@@V?$StandardCreator@VHSBSlider@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000efd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f003`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f003`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000efe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000efe9`
- `GDI32!CreateCompatibleDC` at `0x18000f04a`
- `GDI32!CreateCompatibleDC` at `0x18000f04a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f0e4`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f0e4`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x18000f0c8`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x18000f0c8`
- `DUI70!??0CCTrackBar@DirectUI@@QEAA@XZ` at `0x18000f01e`
- `DUI70!??0CCTrackBar@DirectUI@@QEAA@XZ` at `0x18000f01e`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<HSBSlider,DirectUI::CCTrackBar,DirectUI::StandardCreator<HSBSlider>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::CCTrackBar **a4)
{
  HANDLE ProcessHeap; // rax
  DirectUI::CCTrackBar *v8; // rax
  DirectUI::CCTrackBar *v9; // rbx
  HDC CompatibleDC; // rax
  int v11; // edi

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (DirectUI::CCTrackBar *)HeapAlloc(ProcessHeap, 8u, 0x1B0u);
  v9 = v8;
  if ( v8 )
  {
    DirectUI::CCTrackBar::CCTrackBar(v8);
    *(_QWORD *)v9 = &HSBSlider::`vftable';
    *((_DWORD *)v9 + 106) = -1;
    *((_DWORD *)v9 + 107) = 0;
    CompatibleDC = CreateCompatibleDC(0);
    *((_QWORD *)v9 + 52) = 0;
    *((_QWORD *)v9 + 51) = CompatibleDC;
    *((_QWORD *)v9 + 50) = 0;
    *(_QWORD *)((char *)v9 + 356) = 0;
    *(_QWORD *)((char *)v9 + 372) = 0;
    *(_QWORD *)((char *)v9 + 380) = 0;
    *(_QWORD *)((char *)v9 + 388) = 0;
    *((_DWORD *)v9 + 88) = 44;
    *(_QWORD *)((char *)v9 + 364) = 2097153;
    v11 = DirectUI::HWNDHost::Initialize(v9, 0x19u, 3u, a2, a3);
    if ( v11 < 0 )
      DirectUI::Element::Destroy(v9, 0);
    else
      *a4 = v9;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000efd0  push    rbx
0x18000efd2  push    rbp
0x18000efd3  push    rsi
0x18000efd4  push    rdi
0x18000efd5  sub     rsp, 38h
0x18000efd9  mov     rsi, r9
0x18000efdc  mov     qword ptr [r9], 0
0x18000efe3  mov     rdi, r8
0x18000efe6  mov     rbp, rdx
0x18000efe9  call    cs:__imp_GetProcessHeap
0x18000eff0  nop     dword ptr [rax+rax+00h]
0x18000eff5  mov     edx, 8; dwFlags
0x18000effa  mov     r8d, 1B0h; dwBytes
0x18000f000  mov     rcx, rax; hHeap
0x18000f003  call    cs:__imp_HeapAlloc
0x18000f00a  nop     dword ptr [rax+rax+00h]
0x18000f00f  mov     rbx, rax
0x18000f012  test    rax, rax
0x18000f015  jz      loc_18000F0F2
0x18000f01b  mov     rcx, rax
0x18000f01e  call    cs:__imp_??0CCTrackBar@DirectUI@@QEAA@XZ; DirectUI::CCTrackBar::CCTrackBar(void)
0x18000f025  nop     dword ptr [rax+rax+00h]
0x18000f02a  lea     rax, ??_7HSBSlider@@6B@; const HSBSlider::`vftable'
0x18000f031  xor     ecx, ecx; hdc
0x18000f033  mov     [rbx], rax
0x18000f036  mov     dword ptr [rbx+1A8h], 0FFFFFFFFh
0x18000f040  mov     dword ptr [rbx+1ACh], 0
0x18000f04a  call    cs:__imp_CreateCompatibleDC
0x18000f051  nop     dword ptr [rax+rax+00h]
0x18000f056  mov     qword ptr [rbx+1A0h], 0
0x18000f061  mov     edx, 19h
0x18000f066  mov     [rbx+198h], rax
0x18000f06d  mov     r9, rbp
0x18000f070  mov     qword ptr [rbx+190h], 0
0x18000f07b  mov     rcx, rbx
0x18000f07e  mov     qword ptr [rbx+164h], 0
0x18000f089  mov     qword ptr [rbx+174h], 0
0x18000f094  lea     r8d, [rdx-16h]
0x18000f098  mov     qword ptr [rbx+17Ch], 0
0x18000f0a3  mov     qword ptr [rbx+184h], 0
0x18000f0ae  mov     dword ptr [rbx+160h], 2Ch ; ','
0x18000f0b8  mov     qword ptr [rbx+16Ch], 200001h
0x18000f0c3  mov     [rsp+58h+var_38], rdi
0x18000f0c8  call    cs:__imp_?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z; DirectUI::HWNDHost::Initialize(uint,uint,DirectUI::Element *,ulong *)
0x18000f0cf  nop     dword ptr [rax+rax+00h]
0x18000f0d4  mov     edi, eax
0x18000f0d6  test    eax, eax
0x18000f0d8  js      short loc_18000F0DF
0x18000f0da  mov     [rsi], rbx
0x18000f0dd  jmp     short loc_18000F0F7
0x18000f0df  xor     edx, edx
0x18000f0e1  mov     rcx, rbx
0x18000f0e4  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000f0eb  nop     dword ptr [rax+rax+00h]
0x18000f0f0  jmp     short loc_18000F0F7
0x18000f0f2  mov     edi, 8007000Eh
0x18000f0f7  mov     eax, edi
0x18000f0f9  add     rsp, 38h
0x18000f0fd  pop     rdi
0x18000f0fe  pop     rsi
0x18000f0ff  pop     rbp
0x18000f100  pop     rbx
0x18000f101  retn
```
