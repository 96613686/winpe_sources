# Windows::Internal::HostingContainerTitleBarElement::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x1800a23e0`
- end: `0x1800a2505`
- name: `?_SelfLayoutUpdateDesiredSize@HostingContainerTitleBarElement@Internal@Windows@@EEAA?AUtagSIZE@@HHPEAVSurface@DirectUI@@@Z`
- size: `293`
- prototype: `struct tagSIZE __fastcall(Windows::Internal::HostingContainerTitleBarElement *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800a23e0`

## import_xrefs

- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x1800a2401`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x1800a2418`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x1800a2401`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x1800a2418`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800a2455`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800a2455`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a249e`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a24e2`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a249e`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a24e2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a2441`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a247a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a24c3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a2441`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a247a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a24c3`
- `DUI70!StrToID` at `0x1800a242f`
- `DUI70!StrToID` at `0x1800a2468`
- `DUI70!StrToID` at `0x1800a24b1`
- `DUI70!StrToID` at `0x1800a242f`
- `DUI70!StrToID` at `0x1800a2468`
- `DUI70!StrToID` at `0x1800a24b1`

## pseudocode

```c
struct tagSIZE __fastcall Windows::Internal::HostingContainerTitleBarElement::_SelfLayoutUpdateDesiredSize(
        Windows::Internal::HostingContainerTitleBarElement *this,
        _DWORD *a2,
        int a3,
        struct DirectUI::Surface *a4)
{
  unsigned int v4; // esi
  unsigned int Height; // eax
  unsigned __int16 v9; // ax
  DirectUI::Element *Descendent; // rax
  unsigned __int16 v11; // ax
  DirectUI::Element *v12; // rax
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  char v16; // [rsp+58h] [rbp+10h] BYREF

  v4 = (unsigned int)a4;
  *a2 = a3;
  if ( (int)a4 >= DirectUI::Element::GetHeight(this) )
    Height = DirectUI::Element::GetHeight(this);
  else
    Height = v4;
  a2[1] = Height;
  v9 = StrToID(L"Title");
  Descendent = DirectUI::Element::FindDescendent(this, v9);
  DirectUI::Element::SetLayoutPos(Descendent, 4);
  v11 = StrToID(L"CenteredTitle");
  v12 = DirectUI::Element::FindDescendent(this, v11);
  DirectUI::Element::_UpdateDesiredSize(v12, (unsigned int)&v16, a3, (struct DirectUI::Surface *)v4);
  v13 = StrToID(L"Progress");
  v14 = DirectUI::Element::FindDescendent(this, v13);
  DirectUI::Element::_UpdateDesiredSize(v14, (unsigned int)&v16, a3, (struct DirectUI::Surface *)v4);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x1800a23e0  mov     [rsp+arg_0], rbx
0x1800a23e5  mov     [rsp+arg_10], rbp
0x1800a23ea  push    rsi
0x1800a23eb  push    rdi
0x1800a23ec  push    r14
0x1800a23ee  sub     rsp, 30h
0x1800a23f2  mov     esi, r9d
0x1800a23f5  mov     [rdx], r8d
0x1800a23f8  mov     ebp, r8d
0x1800a23fb  mov     r14, rdx
0x1800a23fe  mov     rdi, rcx
0x1800a2401  call    cs:__imp_?GetHeight@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetHeight(void)
0x1800a2408  nop     dword ptr [rax+rax+00h]
0x1800a240d  cmp     esi, eax
0x1800a240f  jge     short loc_1800A2415
0x1800a2411  mov     eax, esi
0x1800a2413  jmp     short loc_1800A2424
0x1800a2415  mov     rcx, rdi
0x1800a2418  call    cs:__imp_?GetHeight@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetHeight(void)
0x1800a241f  nop     dword ptr [rax+rax+00h]
0x1800a2424  lea     rcx, aTitle_0; "Title"
0x1800a242b  mov     [r14+4], eax
0x1800a242f  call    cs:__imp_StrToID
0x1800a2436  nop     dword ptr [rax+rax+00h]
0x1800a243b  movzx   edx, ax
0x1800a243e  mov     rcx, rdi
0x1800a2441  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a2448  nop     dword ptr [rax+rax+00h]
0x1800a244d  mov     rcx, rax
0x1800a2450  mov     edx, 4
0x1800a2455  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800a245c  nop     dword ptr [rax+rax+00h]
0x1800a2461  lea     rcx, aCenteredtitle; "CenteredTitle"
0x1800a2468  call    cs:__imp_StrToID
0x1800a246f  nop     dword ptr [rax+rax+00h]
0x1800a2474  movzx   edx, ax
0x1800a2477  mov     rcx, rdi
0x1800a247a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a2481  nop     dword ptr [rax+rax+00h]
0x1800a2486  mov     rbx, [rsp+48h+arg_20]
0x1800a248b  lea     rdx, [rsp+48h+arg_8]
0x1800a2490  mov     rcx, rax
0x1800a2493  mov     [rsp+48h+var_28], rbx
0x1800a2498  mov     r9d, esi
0x1800a249b  mov     r8d, ebp
0x1800a249e  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x1800a24a5  nop     dword ptr [rax+rax+00h]
0x1800a24aa  lea     rcx, aProgress; "Progress"
0x1800a24b1  call    cs:__imp_StrToID
0x1800a24b8  nop     dword ptr [rax+rax+00h]
0x1800a24bd  movzx   edx, ax
0x1800a24c0  mov     rcx, rdi
0x1800a24c3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a24ca  nop     dword ptr [rax+rax+00h]
0x1800a24cf  mov     r9d, esi
0x1800a24d2  mov     [rsp+48h+var_28], rbx
0x1800a24d7  mov     rcx, rax
0x1800a24da  lea     rdx, [rsp+48h+arg_8]
0x1800a24df  mov     r8d, ebp
0x1800a24e2  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x1800a24e9  nop     dword ptr [rax+rax+00h]
0x1800a24ee  mov     rbx, [rsp+48h+arg_0]
0x1800a24f3  mov     rax, r14
0x1800a24f6  mov     rbp, [rsp+48h+arg_10]
0x1800a24fb  add     rsp, 30h
0x1800a24ff  pop     r14
0x1800a2501  pop     rdi
0x1800a2502  pop     rsi
0x1800a2503  retn
```
