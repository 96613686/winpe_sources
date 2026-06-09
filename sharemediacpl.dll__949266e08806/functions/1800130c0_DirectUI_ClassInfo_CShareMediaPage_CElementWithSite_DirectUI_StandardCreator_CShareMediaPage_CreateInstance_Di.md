# DirectUI::ClassInfo<CShareMediaPage,CElementWithSite,DirectUI::StandardCreator<CShareMediaPage>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x1800130c0`
- end: `0x1800131f1`
- name: `?CreateInstance@?$ClassInfo@VCShareMediaPage@@VCElementWithSite@@V?$StandardCreator@VCShareMediaPage@@@DirectUI@@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003860`
- `0x180003888`
- `0x1800130c0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001310d`
- `KERNEL32!GetProcessHeap` at `0x18001310d`
- `KERNEL32!HeapAlloc` at `0x18001311f`
- `KERNEL32!HeapAlloc` at `0x18001311f`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18001319c`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18001319c`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x180013134`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x180013134`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800131b2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800131b2`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CShareMediaPage,CElementWithSite,DirectUI::StandardCreator<CShareMediaPage>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  int v7; // edi
  HANDLE ProcessHeap; // rax
  DirectUI::Element *v9; // rax
  DirectUI::Element *v10; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids);
  *a4 = 0;
  v7 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = (DirectUI::Element *)HeapAlloc(ProcessHeap, 8u, 0x110u);
  v10 = v9;
  if ( v9 )
  {
    DirectUI::Element::Element(v9);
    *((_QWORD *)v10 + 29) = 0;
    *(_QWORD *)v10 = &CShareMediaPage::`vftable'{for `DirectUI::Element'};
    *((_QWORD *)v10 + 30) = 0;
    *((_QWORD *)v10 + 25) = &CShareMediaPage::`vftable'{for `IUnknown'};
    *((_QWORD *)v10 + 31) = 0;
    *((_QWORD *)v10 + 26) = &CShareMediaPage::`vftable'{for `CElementWithSite'};
    *((_QWORD *)v10 + 28) = &CShareMediaPage::`vftable'{for `IFrameNotificationClient'};
    *((_QWORD *)v10 + 32) = &CShareMediaPage::`vftable';
    v7 = DirectUI::Element::Initialize(v10, 0, a2, a3);
    if ( v7 < 0 )
      DirectUI::Element::Destroy(v10, 1);
    else
      *a4 = v10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800130c0  push    rbx
0x1800130c2  push    rbp
0x1800130c3  push    rsi
0x1800130c4  push    rdi
0x1800130c5  push    r12
0x1800130c7  push    r14
0x1800130c9  sub     rsp, 28h
0x1800130cd  mov     rsi, r9
0x1800130d0  mov     rbp, r8
0x1800130d3  mov     r14, rdx
0x1800130d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130dd  lea     r12, WPP_GLOBAL_Control
0x1800130e4  cmp     rcx, r12
0x1800130e7  jz      short loc_180013104
0x1800130e9  test    byte ptr [rcx+1Ch], 20h
0x1800130ed  jz      short loc_180013104
0x1800130ef  mov     rcx, [rcx+10h]
0x1800130f3  lea     r8, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids
0x1800130fa  mov     edx, 14h
0x1800130ff  call    WPP_SF_
0x180013104  mov     qword ptr [rsi], 0
0x18001310b  xor     edi, edi
0x18001310d  call    cs:__imp_GetProcessHeap
0x180013113  lea     edx, [rdi+8]; dwFlags
0x180013116  mov     r8d, 110h; dwBytes
0x18001311c  mov     rcx, rax; hHeap
0x18001311f  call    cs:__imp_HeapAlloc
0x180013125  mov     rbx, rax
0x180013128  test    rax, rax
0x18001312b  jz      loc_1800131B8
0x180013131  mov     rcx, rax
0x180013134  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x18001313a  lea     rax, ??_7CShareMediaPage@@6BElement@DirectUI@@@; const CShareMediaPage::`vftable'{for `DirectUI::Element'}
0x180013141  mov     [rbx+0E8h], rdi
0x180013148  mov     [rbx], rax
0x18001314b  mov     r9, rbp
0x18001314e  lea     rax, ??_7CShareMediaPage@@6BIUnknown@@@; const CShareMediaPage::`vftable'{for `IUnknown'}
0x180013155  mov     [rbx+0F0h], rdi
0x18001315c  mov     [rbx+0C8h], rax
0x180013163  mov     r8, r14
0x180013166  lea     rax, ??_7CShareMediaPage@@6BCElementWithSite@@@; const CShareMediaPage::`vftable'{for `CElementWithSite'}
0x18001316d  mov     [rbx+0F8h], rdi
0x180013174  mov     [rbx+0D0h], rax
0x18001317b  xor     edx, edx
0x18001317d  lea     rax, ??_7CShareMediaPage@@6BIFrameNotificationClient@@@; const CShareMediaPage::`vftable'{for `IFrameNotificationClient'}
0x180013184  mov     rcx, rbx
0x180013187  mov     [rbx+0E0h], rax
0x18001318e  lea     rax, ??_7CShareMediaPage@@6B@; const CShareMediaPage::`vftable'
0x180013195  mov     [rbx+100h], rax
0x18001319c  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x1800131a2  mov     edi, eax
0x1800131a4  test    eax, eax
0x1800131a6  js      short loc_1800131AD
0x1800131a8  mov     [rsi], rbx
0x1800131ab  jmp     short loc_1800131B8
0x1800131ad  mov     dl, 1
0x1800131af  mov     rcx, rbx
0x1800131b2  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800131b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131bf  cmp     rcx, r12
0x1800131c2  jz      short loc_1800131E2
0x1800131c4  test    byte ptr [rcx+1Ch], 20h
0x1800131c8  jz      short loc_1800131E2
0x1800131ca  mov     rcx, [rcx+10h]
0x1800131ce  lea     r8, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids
0x1800131d5  mov     edx, 15h
0x1800131da  mov     r9d, edi
0x1800131dd  call    WPP_SF_d
0x1800131e2  mov     eax, edi
0x1800131e4  add     rsp, 28h
0x1800131e8  pop     r14
0x1800131ea  pop     r12
0x1800131ec  pop     rdi
0x1800131ed  pop     rsi
0x1800131ee  pop     rbp
0x1800131ef  pop     rbx
0x1800131f0  retn
```
