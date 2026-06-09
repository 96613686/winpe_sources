# CShareWithListItemUsers::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x180009460`
- end: `0x1800095ed`
- name: `?Create@CShareWithListItemUsers@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z`
- size: `397`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800087c0`
- `0x1800097a0`

## callees

- `0x180003860`
- `0x180003888`
- `0x180007da4`
- `0x180009460`
- `0x18000a960`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800094ae`
- `KERNEL32!GetProcessHeap` at `0x1800094ae`
- `KERNEL32!HeapAlloc` at `0x1800094c2`
- `KERNEL32!HeapAlloc` at `0x1800094c2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800095ab`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800095ab`

## pseudocode

```c
__int64 __fastcall CShareWithListItemUsers::Create(
        struct DirectUI::Element *a1,
        unsigned int *a2,
        struct DirectUI::Element **a3)
{
  HANDLE ProcessHeap; // rax
  CShareWithListItemBase *v7; // rax
  CShareWithListItemBase *v8; // rdi
  _QWORD *v9; // rcx
  unsigned int v10; // eax
  int v11; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  *a3 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (CShareWithListItemBase *)HeapAlloc(ProcessHeap, 8u, 0xF8u);
  v8 = v7;
  if ( v7 )
  {
    CShareWithListItemBase::CShareWithListItemBase(v7);
    *(_QWORD *)v8 = &CShareWithListItemUsers::`vftable'{for `DirectUI::Element'};
    *((_QWORD *)v8 + 25) = &CShareWithListItemBase::`vftable'{for `DirectUI::IElementListener'};
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    *((_DWORD *)v8 + 58) = 1;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
        WPP_SF_(v9[2], 217, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    }
    v10 = CShareWithListItemBase::Initialize(v8, a1, a2);
    v11 = v10;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v10);
    if ( v11 < 0 )
      DirectUI::Element::Destroy(v8, 0);
    else
      *a3 = v8;
  }
  else
  {
    v11 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      216,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180009460  push    rbx
0x180009462  push    rbp
0x180009463  push    rsi
0x180009464  push    rdi
0x180009465  push    r12
0x180009467  push    r15
0x180009469  sub     rsp, 28h
0x18000946d  mov     rsi, r8
0x180009470  mov     rbx, rdx
0x180009473  mov     rbp, rcx
0x180009476  mov     rcx, cs:WPP_GLOBAL_Control
0x18000947d  lea     r15, WPP_GLOBAL_Control
0x180009484  lea     r12, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000948b  cmp     rcx, r15
0x18000948e  jz      short loc_1800094A7
0x180009490  test    byte ptr [rcx+1Ch], 20h
0x180009494  jz      short loc_1800094A7
0x180009496  mov     rcx, [rcx+10h]
0x18000949a  mov     edx, 0D7h
0x18000949f  mov     r8, r12
0x1800094a2  call    WPP_SF_
0x1800094a7  mov     qword ptr [rsi], 0
0x1800094ae  call    cs:__imp_GetProcessHeap
0x1800094b4  mov     edx, 8; dwFlags
0x1800094b9  mov     r8d, 0F8h; dwBytes
0x1800094bf  mov     rcx, rax; hHeap
0x1800094c2  call    cs:__imp_HeapAlloc
0x1800094c8  mov     rdi, rax
0x1800094cb  test    rax, rax
0x1800094ce  jz      loc_1800095B3
0x1800094d4  mov     rcx, rax; this
0x1800094d7  call    ??0CShareWithListItemBase@@QEAA@XZ; CShareWithListItemBase::CShareWithListItemBase(void)
0x1800094dc  lea     rax, ??_7CShareWithListItemUsers@@6BElement@DirectUI@@@; const CShareWithListItemUsers::`vftable'{for `DirectUI::Element'}
0x1800094e3  mov     [rdi], rax
0x1800094e6  lea     rax, ??_7CShareWithListItemBase@@6BIElementListener@DirectUI@@@; const CShareWithListItemBase::`vftable'{for `DirectUI::IElementListener'}
0x1800094ed  mov     [rdi+0C8h], rax
0x1800094f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094fb  cmp     rcx, r15
0x1800094fe  jz      short loc_180009517
0x180009500  test    byte ptr [rcx+1Ch], 20h
0x180009504  jz      short loc_180009517
0x180009506  mov     rcx, [rcx+10h]
0x18000950a  mov     edx, 0D5h
0x18000950f  mov     r8, r12
0x180009512  call    WPP_SF_
0x180009517  mov     dword ptr [rdi+0E8h], 1
0x180009521  mov     rcx, cs:WPP_GLOBAL_Control
0x180009528  cmp     rcx, r15
0x18000952b  jz      short loc_180009567
0x18000952d  test    byte ptr [rcx+1Ch], 20h
0x180009531  jz      short loc_18000954B
0x180009533  mov     rcx, [rcx+10h]
0x180009537  mov     edx, 0D6h
0x18000953c  mov     r8, r12
0x18000953f  call    WPP_SF_
0x180009544  mov     rcx, cs:WPP_GLOBAL_Control
0x18000954b  cmp     rcx, r15
0x18000954e  jz      short loc_180009567
0x180009550  test    byte ptr [rcx+1Ch], 20h
0x180009554  jz      short loc_180009567
0x180009556  mov     rcx, [rcx+10h]
0x18000955a  mov     edx, 0D9h
0x18000955f  mov     r8, r12
0x180009562  call    WPP_SF_
0x180009567  mov     r8, rbx; unsigned int *
0x18000956a  mov     rdx, rbp; struct DirectUI::Element *
0x18000956d  mov     rcx, rdi; this
0x180009570  call    ?Initialize@CShareWithListItemBase@@QEAAJPEAVElement@DirectUI@@PEAK@Z; CShareWithListItemBase::Initialize(DirectUI::Element *,ulong *)
0x180009575  mov     ebx, eax
0x180009577  mov     rcx, cs:WPP_GLOBAL_Control
0x18000957e  cmp     rcx, r15
0x180009581  jz      short loc_18000959D
0x180009583  test    byte ptr [rcx+1Ch], 20h
0x180009587  jz      short loc_18000959D
0x180009589  mov     rcx, [rcx+10h]
0x18000958d  mov     edx, 0DAh
0x180009592  mov     r9d, eax
0x180009595  mov     r8, r12
0x180009598  call    WPP_SF_d
0x18000959d  test    ebx, ebx
0x18000959f  js      short loc_1800095A6
0x1800095a1  mov     [rsi], rdi
0x1800095a4  jmp     short loc_1800095B8
0x1800095a6  xor     edx, edx
0x1800095a8  mov     rcx, rdi
0x1800095ab  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800095b1  jmp     short loc_1800095B8
0x1800095b3  mov     ebx, 8007000Eh
0x1800095b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095bf  cmp     rcx, r15
0x1800095c2  jz      short loc_1800095DE
0x1800095c4  test    byte ptr [rcx+1Ch], 20h
0x1800095c8  jz      short loc_1800095DE
0x1800095ca  mov     rcx, [rcx+10h]
0x1800095ce  mov     edx, 0D8h
0x1800095d3  mov     r9d, ebx
0x1800095d6  mov     r8, r12
0x1800095d9  call    WPP_SF_d
0x1800095de  mov     eax, ebx
0x1800095e0  add     rsp, 28h
0x1800095e4  pop     r15
0x1800095e6  pop     r12
0x1800095e8  pop     rdi
0x1800095e9  pop     rsi
0x1800095ea  pop     rbp
0x1800095eb  pop     rbx
0x1800095ec  retn
```
