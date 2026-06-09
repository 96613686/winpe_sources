# CConfirmPasswordPage::Initialize(ITaskFlowControl *)

- ea: `0x180040240`
- end: `0x18004049c`
- name: `?Initialize@CConfirmPasswordPage@@UEAAJPEAUITaskFlowControl@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(CConfirmPasswordPage *__hidden this, struct ITaskFlowControl *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18003ab6c`
- `0x18003bdf0`
- `0x18003d010`
- `0x180040240`
- `0x180063bc8`
- `0x180074f14`
- `0x18007510c`
- `0x180075150`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800402ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004038f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800402ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004038f`
- `DUI70!?SetMaxLength@TouchEditBase@DirectUI@@QEAAJH@Z` at `0x1800403d9`
- `DUI70!?SetMaxLength@TouchEditBase@DirectUI@@QEAAJH@Z` at `0x1800403d9`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004039c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004042b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004043b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004039c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004042b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004043b`
- `DUI70!StrToID` at `0x1800403bb`
- `DUI70!StrToID` at `0x1800403e6`
- `DUI70!StrToID` at `0x1800403bb`
- `DUI70!StrToID` at `0x1800403e6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800403c7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800403f2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800403c7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800403f2`

## string_xrefs

- `0x18004040a`: `idSkipLink`

## pseudocode

```c
__int64 __fastcall CConfirmPasswordPage::Initialize(CConfirmPasswordPage *this, struct ITaskFlowControl *a2)
{
  int v3; // esi
  struct DirectUI::Element *Element; // rax
  __int64 v5; // rcx
  struct DirectUI::Element *v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rdx
  struct DirectUI::Element *v9; // rax
  __int64 v10; // rcx
  struct DirectUI::Element *v11; // rbx
  struct DirectUI::Element *v12; // rax
  DirectUI::Element *v13; // rbx
  DirectUI::Element *v14; // rbx
  unsigned __int16 v15; // ax
  DirectUI::TouchEditBase *Descendent; // rax
  unsigned __int16 v17; // ax
  struct DirectUI::Element *v18; // rax
  DirectUI::Element *v19; // rax
  _QWORD *v20; // rbx
  __int64 v21; // rcx
  LPVOID v22; // rdx
  void *v24; // [rsp+20h] [rbp-10h]
  int v25; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF

  *((_QWORD *)this + 3) = a2;
  (*(void (__fastcall **)(struct ITaskFlowControl *))(*(_QWORD *)a2 + 8LL))(a2);
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
  Element = CBaseTaskFlowPage::_FindElement(this, L"idDescription");
  v5 = *((_QWORD *)this + 6);
  v6 = Element;
  v25 = 0;
  if ( (*(int (__fastcall **)(__int64, int *, _QWORD, _QWORD))(*(_QWORD *)v5 + 56LL))(v5, &v25, 0, 0) >= 0 )
  {
    pv = 0;
    v8 = v3 ? *((unsigned int *)`CConfirmPasswordPage::Initialize'::`8'::rguPageTextResIds + v25) : 3350LL;
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
                g_hinst,
                v8,
                v7,
                (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
                v24,
                (char *)&pv) >= 0 )
    {
      SetElementContentStringAndAccName(v6, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
  }
  v9 = CBaseTaskFlowPage::_FindElement(this, L"idUsername");
  v10 = *((_QWORD *)this + 6);
  v11 = v9;
  v26 = 0;
  if ( (*(int (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v10 + 32LL))(v10, &v26) >= 0 )
  {
    SetElementContentStringAndAccName(v11, v26);
    CoTaskMemFree(v26);
  }
  v12 = CBaseTaskFlowPage::_FindElement(this, L"idEmailAddress");
  v13 = (DirectUI::Element *)element_cast<DirectUI::RichText>(v12);
  if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 6) + 40LL))(
         *((_QWORD *)this + 6),
         &v26) < 0 )
  {
    DirectUI::Element::SetLayoutPos(v13, -3);
  }
  else
  {
    SetElementContentStringAndAccName(v13, v26);
    CoTaskMemFree(v26);
  }
  v14 = CBaseTaskFlowPage::_FindElement(this, L"idPassword");
  v15 = StrToID(L"idTFEditBox");
  Descendent = DirectUI::Element::FindDescendent(v14, v15);
  *((_QWORD *)this + 7) = Descendent;
  DirectUI::TouchEditBase::SetMaxLength(Descendent, 256);
  v17 = StrToID(L"idTFEditStatus");
  *((_QWORD *)this + 8) = DirectUI::Element::FindDescendent(v14, v17);
  SetTaskFlowEditAccNameFromLabel(v14);
  if ( v25 == 7 )
  {
    v18 = CBaseTaskFlowPage::_FindElement(this, L"idSkipLink");
    v19 = (DirectUI::Element *)element_cast<DirectUI::TouchHyperLink>((__int64)v18);
    *((_QWORD *)this + 9) = v19;
    DirectUI::Element::SetLayoutPos(v19, -1);
    if ( !v3 )
      DirectUI::Element::SetLayoutPos(v14, -3);
  }
  Microsoft::WRL::Details::Make<CCapsLockWarningBehavior,>(&pv);
  v20 = pv;
  if ( pv )
  {
    v21 = *((_QWORD *)this + 7);
    v22 = pv;
    *((_QWORD *)pv + 3) = *((_QWORD *)this + 8);
    v20[2] = v21;
    (*(void (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)(v21 + 80) + 176LL))(*(_QWORD *)(v21 + 80), v22);
    (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
  }
  return 0;
}

```

## disassembly

```asm
0x180040240  mov     [rsp-18h+arg_18], rbx
0x180040245  push    rbp
0x180040246  push    rsi
0x180040247  push    rdi
0x180040248  mov     rbp, rsp
0x18004024b  sub     rsp, 30h
0x18004024f  mov     [rcx+18h], rdx
0x180040253  mov     rdi, rcx
0x180040256  mov     rax, [rdx]
0x180040259  mov     rcx, rdx
0x18004025c  mov     rax, [rax+8]
0x180040260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040265  mov     rcx, [rdi+30h]
0x180040269  mov     rax, [rcx]
0x18004026c  mov     rax, [rax+18h]
0x180040270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040275  lea     rdx, aIddescription; "idDescription"
0x18004027c  mov     rcx, rdi; this
0x18004027f  mov     esi, eax
0x180040281  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x180040286  mov     rcx, [rdi+30h]
0x18004028a  mov     rbx, rax
0x18004028d  mov     [rbp+arg_0], 0
0x180040294  xor     r9d, r9d
0x180040297  xor     r8d, r8d
0x18004029a  mov     rdx, [rcx]
0x18004029d  mov     rax, [rdx+38h]
0x1800402a1  lea     rdx, [rbp+arg_0]
0x1800402a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402aa  test    eax, eax
0x1800402ac  js      short loc_180040305
0x1800402ae  mov     [rbp+pv], 0
0x1800402b6  test    esi, esi
0x1800402b8  jz      short loc_1800402CA
0x1800402ba  movsxd  rax, [rbp+arg_0]
0x1800402be  lea     rdx, ?rguPageTextResIds@?7??Initialize@CConfirmPasswordPage@@UEAAJPEAUITaskFlowControl@@@Z@4PAIA; uint near * `CConfirmPasswordPage::Initialize(ITaskFlowControl *)'::`8'::rguPageTextResIds
0x1800402c5  mov     edx, [rdx+rax*4]
0x1800402c8  jmp     short loc_1800402CF
0x1800402ca  mov     edx, 0D16h; int
0x1800402cf  mov     rcx, cs:g_hinst; int
0x1800402d6  lea     rax, [rbp+pv]
0x1800402da  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x1800402e1  mov     [rsp+30h+var_8], rax; void *
0x1800402e6  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800402eb  test    eax, eax
0x1800402ed  js      short loc_180040305
0x1800402ef  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800402f3  mov     rcx, rbx; struct DirectUI::Element *
0x1800402f6  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x1800402fb  mov     rcx, [rbp+pv]; pv
0x1800402ff  call    cs:__imp_CoTaskMemFree
0x180040305  lea     rdx, aIdusername; "idUsername"
0x18004030c  mov     rcx, rdi; this
0x18004030f  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x180040314  mov     rcx, [rdi+30h]
0x180040318  mov     rbx, rax
0x18004031b  mov     [rbp+arg_8], 0
0x180040323  mov     rdx, [rcx]
0x180040326  mov     rax, [rdx+20h]
0x18004032a  lea     rdx, [rbp+arg_8]
0x18004032e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040333  test    eax, eax
0x180040335  js      short loc_18004034D
0x180040337  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18004033b  mov     rcx, rbx; struct DirectUI::Element *
0x18004033e  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x180040343  mov     rcx, [rbp+arg_8]; pv
0x180040347  call    cs:__imp_CoTaskMemFree
0x18004034d  lea     rdx, aIdemailaddress; "idEmailAddress"
0x180040354  mov     rcx, rdi; this
0x180040357  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x18004035c  mov     rcx, rax
0x18004035f  call    ??$element_cast@VRichText@DirectUI@@@@YAPEAVRichText@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::RichText>(DirectUI::Element *)
0x180040364  mov     rcx, [rdi+30h]
0x180040368  mov     rbx, rax
0x18004036b  mov     rdx, [rcx]
0x18004036e  mov     rax, [rdx+28h]
0x180040372  lea     rdx, [rbp+arg_8]
0x180040376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004037b  mov     rcx, rbx; struct DirectUI::Element *
0x18004037e  test    eax, eax
0x180040380  js      short loc_180040397
0x180040382  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180040386  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18004038b  mov     rcx, [rbp+arg_8]; pv
0x18004038f  call    cs:__imp_CoTaskMemFree
0x180040395  jmp     short loc_1800403A2
0x180040397  mov     edx, 0FFFFFFFDh
0x18004039c  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800403a2  lea     rdx, aIdpassword; "idPassword"
0x1800403a9  mov     rcx, rdi; this
0x1800403ac  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x1800403b1  lea     rcx, aIdtfeditbox; "idTFEditBox"
0x1800403b8  mov     rbx, rax
0x1800403bb  call    cs:__imp_StrToID
0x1800403c1  movzx   edx, ax
0x1800403c4  mov     rcx, rbx
0x1800403c7  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800403cd  mov     rcx, rax
0x1800403d0  mov     [rdi+38h], rax
0x1800403d4  mov     edx, 100h
0x1800403d9  call    cs:__imp_?SetMaxLength@TouchEditBase@DirectUI@@QEAAJH@Z; DirectUI::TouchEditBase::SetMaxLength(int)
0x1800403df  lea     rcx, aIdtfeditstatus; "idTFEditStatus"
0x1800403e6  call    cs:__imp_StrToID
0x1800403ec  movzx   edx, ax
0x1800403ef  mov     rcx, rbx
0x1800403f2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800403f8  mov     rcx, rbx; struct DirectUI::Element *
0x1800403fb  mov     [rdi+40h], rax
0x1800403ff  call    ?SetTaskFlowEditAccNameFromLabel@@YAXPEAVElement@DirectUI@@@Z; SetTaskFlowEditAccNameFromLabel(DirectUI::Element *)
0x180040404  cmp     [rbp+arg_0], 7
0x180040408  jnz     short loc_180040441
0x18004040a  lea     rdx, aIdskiplink; "idSkipLink"
0x180040411  mov     rcx, rdi; this
0x180040414  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x180040419  mov     rcx, rax
0x18004041c  call    ??$element_cast@VTouchHyperLink@DirectUI@@@@YAPEAVTouchHyperLink@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::TouchHyperLink>(DirectUI::Element *)
0x180040421  or      edx, 0FFFFFFFFh
0x180040424  mov     [rdi+48h], rax
0x180040428  mov     rcx, rax
0x18004042b  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180040431  test    esi, esi
0x180040433  jnz     short loc_180040441
0x180040435  lea     edx, [rsi-3]
0x180040438  mov     rcx, rbx
0x18004043b  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180040441  lea     rcx, [rbp+pv]
0x180040445  call    ??$Make@VCCapsLockWarningBehavior@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCapsLockWarningBehavior@@@12@XZ; Microsoft::WRL::Details::Make<CCapsLockWarningBehavior,>(void)
0x18004044a  mov     rbx, [rbp+pv]
0x18004044e  test    rbx, rbx
0x180040451  jz      short loc_18004048D
0x180040453  mov     rcx, [rdi+38h]
0x180040457  mov     rdx, rbx
0x18004045a  mov     rax, [rdi+40h]
0x18004045e  mov     [rbx+18h], rax
0x180040462  mov     [rbx+10h], rcx
0x180040466  mov     rcx, [rcx+50h]
0x18004046a  mov     rax, [rcx]
0x18004046d  mov     rax, [rax+0B0h]
0x180040474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040479  test    rbx, rbx
0x18004047c  jz      short loc_18004048D
0x18004047e  mov     rax, [rbx]
0x180040481  mov     rcx, rbx
0x180040484  mov     rax, [rax+10h]
0x180040488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004048d  mov     rbx, [rsp+30h+arg_18]
0x180040492  xor     eax, eax
0x180040494  add     rsp, 30h
0x180040498  pop     rdi
0x180040499  pop     rsi
0x18004049a  pop     rbp
0x18004049b  retn
```
