# CShareWithListItemDevice::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x1800092d4`
- end: `0x180009457`
- name: `?Create@CShareWithListItemDevice@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z`
- size: `387`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000822c`
- `0x180009780`

## callees

- `0x180003860`
- `0x180003888`
- `0x180007da4`
- `0x1800092d4`
- `0x18000a960`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009322`
- `KERNEL32!GetProcessHeap` at `0x180009322`
- `KERNEL32!HeapAlloc` at `0x180009336`
- `KERNEL32!HeapAlloc` at `0x180009336`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009415`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009415`

## pseudocode

```c
__int64 __fastcall CShareWithListItemDevice::Create(
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  *a3 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (CShareWithListItemBase *)HeapAlloc(ProcessHeap, 8u, 0xF8u);
  v8 = v7;
  if ( v7 )
  {
    CShareWithListItemBase::CShareWithListItemBase(v7);
    *(_QWORD *)v8 = &CShareWithListItemDevice::`vftable'{for `DirectUI::Element'};
    *((_QWORD *)v8 + 25) = &CShareWithListItemBase::`vftable'{for `DirectUI::IElementListener'};
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v9 + 28) & 0x20) != 0 )
        {
          WPP_SF_(v9[2], 236, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
          WPP_SF_(v9[2], 239, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
      }
    }
    v10 = CShareWithListItemBase::Initialize(v8, a1, a2);
    v11 = v10;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v10);
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
      238,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800092d4  push    rbx
0x1800092d6  push    rbp
0x1800092d7  push    rsi
0x1800092d8  push    rdi
0x1800092d9  push    r12
0x1800092db  push    r15
0x1800092dd  sub     rsp, 28h
0x1800092e1  mov     rsi, r8
0x1800092e4  mov     rbx, rdx
0x1800092e7  mov     rbp, rcx
0x1800092ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092f1  lea     r15, WPP_GLOBAL_Control
0x1800092f8  lea     r12, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x1800092ff  cmp     rcx, r15
0x180009302  jz      short loc_18000931B
0x180009304  test    byte ptr [rcx+1Ch], 20h
0x180009308  jz      short loc_18000931B
0x18000930a  mov     rcx, [rcx+10h]
0x18000930e  mov     edx, 0EDh
0x180009313  mov     r8, r12
0x180009316  call    WPP_SF_
0x18000931b  mov     qword ptr [rsi], 0
0x180009322  call    cs:__imp_GetProcessHeap
0x180009328  mov     edx, 8; dwFlags
0x18000932d  mov     r8d, 0F8h; dwBytes
0x180009333  mov     rcx, rax; hHeap
0x180009336  call    cs:__imp_HeapAlloc
0x18000933c  mov     rdi, rax
0x18000933f  test    rax, rax
0x180009342  jz      loc_18000941D
0x180009348  mov     rcx, rax; this
0x18000934b  call    ??0CShareWithListItemBase@@QEAA@XZ; CShareWithListItemBase::CShareWithListItemBase(void)
0x180009350  lea     rax, ??_7CShareWithListItemDevice@@6BElement@DirectUI@@@; const CShareWithListItemDevice::`vftable'{for `DirectUI::Element'}
0x180009357  mov     [rdi], rax
0x18000935a  lea     rax, ??_7CShareWithListItemBase@@6BIElementListener@DirectUI@@@; const CShareWithListItemBase::`vftable'{for `DirectUI::IElementListener'}
0x180009361  mov     [rdi+0C8h], rax
0x180009368  mov     rcx, cs:WPP_GLOBAL_Control
0x18000936f  cmp     rcx, r15
0x180009372  jz      short loc_1800093D1
0x180009374  test    byte ptr [rcx+1Ch], 20h
0x180009378  jz      short loc_180009392
0x18000937a  mov     rcx, [rcx+10h]
0x18000937e  mov     edx, 0EBh
0x180009383  mov     r8, r12
0x180009386  call    WPP_SF_
0x18000938b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009392  cmp     rcx, r15
0x180009395  jz      short loc_1800093D1
0x180009397  test    byte ptr [rcx+1Ch], 20h
0x18000939b  jz      short loc_1800093B5
0x18000939d  mov     rcx, [rcx+10h]
0x1800093a1  mov     edx, 0ECh
0x1800093a6  mov     r8, r12
0x1800093a9  call    WPP_SF_
0x1800093ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093b5  cmp     rcx, r15
0x1800093b8  jz      short loc_1800093D1
0x1800093ba  test    byte ptr [rcx+1Ch], 20h
0x1800093be  jz      short loc_1800093D1
0x1800093c0  mov     rcx, [rcx+10h]
0x1800093c4  mov     edx, 0EFh
0x1800093c9  mov     r8, r12
0x1800093cc  call    WPP_SF_
0x1800093d1  mov     r8, rbx; unsigned int *
0x1800093d4  mov     rdx, rbp; struct DirectUI::Element *
0x1800093d7  mov     rcx, rdi; this
0x1800093da  call    ?Initialize@CShareWithListItemBase@@QEAAJPEAVElement@DirectUI@@PEAK@Z; CShareWithListItemBase::Initialize(DirectUI::Element *,ulong *)
0x1800093df  mov     ebx, eax
0x1800093e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093e8  cmp     rcx, r15
0x1800093eb  jz      short loc_180009407
0x1800093ed  test    byte ptr [rcx+1Ch], 20h
0x1800093f1  jz      short loc_180009407
0x1800093f3  mov     rcx, [rcx+10h]
0x1800093f7  mov     edx, 0F0h
0x1800093fc  mov     r9d, eax
0x1800093ff  mov     r8, r12
0x180009402  call    WPP_SF_d
0x180009407  test    ebx, ebx
0x180009409  js      short loc_180009410
0x18000940b  mov     [rsi], rdi
0x18000940e  jmp     short loc_180009422
0x180009410  xor     edx, edx
0x180009412  mov     rcx, rdi
0x180009415  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000941b  jmp     short loc_180009422
0x18000941d  mov     ebx, 8007000Eh
0x180009422  mov     rcx, cs:WPP_GLOBAL_Control
0x180009429  cmp     rcx, r15
0x18000942c  jz      short loc_180009448
0x18000942e  test    byte ptr [rcx+1Ch], 20h
0x180009432  jz      short loc_180009448
0x180009434  mov     rcx, [rcx+10h]
0x180009438  mov     edx, 0EEh
0x18000943d  mov     r9d, ebx
0x180009440  mov     r8, r12
0x180009443  call    WPP_SF_d
0x180009448  mov     eax, ebx
0x18000944a  add     rsp, 28h
0x18000944e  pop     r15
0x180009450  pop     r12
0x180009452  pop     rdi
0x180009453  pop     rsi
0x180009454  pop     rbp
0x180009455  pop     rbx
0x180009456  retn
```
