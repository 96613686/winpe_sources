# DirectUI::ClassInfo<CShareWithListItemBase,DirectUI::Element,DirectUI::StandardCreator<CShareWithListItemBase>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x1800096a0`
- end: `0x180009775`
- name: `?CreateInstance@?$ClassInfo@VCShareWithListItemBase@@VElement@DirectUI@@V?$StandardCreator@VCShareWithListItemBase@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003860`
- `0x180003888`
- `0x180007da4`
- `0x1800096a0`
- `0x18000a960`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800096e9`
- `KERNEL32!GetProcessHeap` at `0x1800096e9`
- `KERNEL32!HeapAlloc` at `0x1800096fd`
- `KERNEL32!HeapAlloc` at `0x1800096fd`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009731`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009731`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CShareWithListItemBase,DirectUI::Element,DirectUI::StandardCreator<CShareWithListItemBase>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        CShareWithListItemBase **a4)
{
  HANDLE ProcessHeap; // rax
  CShareWithListItemBase *v8; // rax
  CShareWithListItemBase *v9; // rdi
  int v10; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (CShareWithListItemBase *)HeapAlloc(ProcessHeap, 8u, 0xF8u);
  v9 = v8;
  if ( v8 )
  {
    CShareWithListItemBase::CShareWithListItemBase(v8);
    v10 = CShareWithListItemBase::Initialize(v9, a2, a3);
    if ( v10 < 0 )
      DirectUI::Element::Destroy(v9, 0);
    else
      *a4 = v9;
  }
  else
  {
    v10 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      164,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800096a0  push    rbx
0x1800096a2  push    rbp
0x1800096a3  push    rsi
0x1800096a4  push    rdi
0x1800096a5  push    r14
0x1800096a7  sub     rsp, 20h
0x1800096ab  mov     rsi, r9
0x1800096ae  mov     rbx, r8
0x1800096b1  mov     rbp, rdx
0x1800096b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096bb  lea     r14, WPP_GLOBAL_Control
0x1800096c2  cmp     rcx, r14
0x1800096c5  jz      short loc_1800096E2
0x1800096c7  test    byte ptr [rcx+1Ch], 20h
0x1800096cb  jz      short loc_1800096E2
0x1800096cd  mov     rcx, [rcx+10h]
0x1800096d1  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x1800096d8  mov     edx, 0A3h
0x1800096dd  call    WPP_SF_
0x1800096e2  mov     qword ptr [rsi], 0
0x1800096e9  call    cs:__imp_GetProcessHeap
0x1800096ef  mov     edx, 8; dwFlags
0x1800096f4  mov     r8d, 0F8h; dwBytes
0x1800096fa  mov     rcx, rax; hHeap
0x1800096fd  call    cs:__imp_HeapAlloc
0x180009703  mov     rdi, rax
0x180009706  test    rax, rax
0x180009709  jz      short loc_180009739
0x18000970b  mov     rcx, rax; this
0x18000970e  call    ??0CShareWithListItemBase@@QEAA@XZ; CShareWithListItemBase::CShareWithListItemBase(void)
0x180009713  mov     r8, rbx; unsigned int *
0x180009716  mov     rdx, rbp; struct DirectUI::Element *
0x180009719  mov     rcx, rdi; this
0x18000971c  call    ?Initialize@CShareWithListItemBase@@QEAAJPEAVElement@DirectUI@@PEAK@Z; CShareWithListItemBase::Initialize(DirectUI::Element *,ulong *)
0x180009721  mov     ebx, eax
0x180009723  test    eax, eax
0x180009725  js      short loc_18000972C
0x180009727  mov     [rsi], rdi
0x18000972a  jmp     short loc_18000973E
0x18000972c  xor     edx, edx
0x18000972e  mov     rcx, rdi
0x180009731  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180009737  jmp     short loc_18000973E
0x180009739  mov     ebx, 8007000Eh
0x18000973e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009745  cmp     rcx, r14
0x180009748  jz      short loc_180009768
0x18000974a  test    byte ptr [rcx+1Ch], 20h
0x18000974e  jz      short loc_180009768
0x180009750  mov     rcx, [rcx+10h]
0x180009754  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000975b  mov     edx, 0A4h
0x180009760  mov     r9d, ebx
0x180009763  call    WPP_SF_d
0x180009768  mov     eax, ebx
0x18000976a  add     rsp, 20h
0x18000976e  pop     r14
0x180009770  pop     rdi
0x180009771  pop     rsi
0x180009772  pop     rbp
0x180009773  pop     rbx
0x180009774  retn
```
