# CShareWithListItemBase::OnEvent(DirectUI::Event *)

- ea: `0x18000ba80`
- end: `0x18000bb7e`
- name: `?OnEvent@CShareWithListItemBase@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `254`
- prototype: `void __fastcall(CShareWithListItemBase *__hidden this, struct DirectUI::Event *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bb90`
- `0x18000bc30`

## callees

- `0x18000ba80`
- `0x18000e460`
- `0x1800108b8`
- `0x18001e010`

## import_xrefs

- `DUI70!?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18000bb77`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000baae`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000baae`
- `DUI70!StrToID` at `0x18000bac8`
- `DUI70!StrToID` at `0x18000bb04`
- `DUI70!StrToID` at `0x18000bb3f`
- `DUI70!StrToID` at `0x18000bac8`
- `DUI70!StrToID` at `0x18000bb04`
- `DUI70!StrToID` at `0x18000bb3f`

## string_xrefs

- `0x18000bac1`: `ShareItemLink`
- `0x18000bafd`: `CustomizeDeviceLink`

## pseudocode

```c
void __fastcall CShareWithListItemBase::OnEvent(CShareWithListItemBase *this, struct DirectUI::Event *a2)
{
  __int16 v4; // si
  __int64 v5; // rcx
  char CheckedStateProp; // al
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 5) == 1 )
  {
    v4 = *(_WORD *)(*(_QWORD *)a2 + 144LL);
    if ( *(_QWORD *)DirectUI::Button::Click(&v7) == *((_QWORD *)a2 + 1) )
    {
      if ( (unsigned __int16)StrToID(L"ShareItemLink") == v4 )
      {
        (*(void (__fastcall **)(_QWORD, CShareWithListItemBase *))(**((_QWORD **)this + 10) + 360LL))(
          *((_QWORD *)this + 10),
          this);
        (*(void (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 440LL))(this);
        goto LABEL_10;
      }
      if ( (unsigned __int16)StrToID(L"CustomizeDeviceLink") == v4 )
      {
        v5 = *((_QWORD *)this + 10);
        g_bfSqm_USAGE |= 0x20u;
        (*(void (__fastcall **)(__int64, CShareWithListItemBase *))(*(_QWORD *)v5 + 360LL))(v5, this);
        (*(void (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 448LL))(this);
LABEL_10:
        *((_BYTE *)a2 + 16) = 1;
        goto LABEL_11;
      }
      if ( (unsigned __int16)StrToID(L"AllowBlockCheckBox") == v4 )
      {
        CheckedStateProp = CShareWithListItemBase::_GetCheckedStateProp(this);
        CShareWithListItemBase::_SetCheckedStateProp(this, CheckedStateProp != 1);
        goto LABEL_10;
      }
    }
  }
LABEL_11:
  DirectUI::Element::OnEvent(this, a2);
}

```

## disassembly

```asm
0x18000ba80  mov     [rsp+arg_0], rbx
0x18000ba85  mov     [rsp+arg_10], rsi
0x18000ba8a  push    rdi
0x18000ba8b  sub     rsp, 20h
0x18000ba8f  cmp     dword ptr [rdx+14h], 1
0x18000ba93  mov     rbx, rdx
0x18000ba96  mov     rdi, rcx
0x18000ba99  jnz     loc_18000BB62
0x18000ba9f  mov     rax, [rdx]
0x18000baa2  lea     rcx, [rsp+28h+arg_8]
0x18000baa7  movzx   esi, word ptr [rax+90h]
0x18000baae  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18000bab4  mov     r8, [rax]
0x18000bab7  cmp     r8, [rbx+8]
0x18000babb  jnz     loc_18000BB62
0x18000bac1  lea     rcx, aShareitemlink; "ShareItemLink"
0x18000bac8  call    cs:__imp_StrToID
0x18000bace  cmp     ax, si
0x18000bad1  jnz     short loc_18000BAFD
0x18000bad3  mov     rcx, [rdi+50h]
0x18000bad7  mov     rdx, rdi
0x18000bada  mov     rax, [rcx]
0x18000badd  mov     rax, [rax+168h]
0x18000bae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae9  mov     rax, [rdi]
0x18000baec  mov     rax, [rax+1B8h]
0x18000baf3  mov     rcx, rdi
0x18000baf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bafb  jmp     short loc_18000BB5E
0x18000bafd  lea     rcx, aCustomizedevic; "CustomizeDeviceLink"
0x18000bb04  call    cs:__imp_StrToID
0x18000bb0a  cmp     ax, si
0x18000bb0d  jnz     short loc_18000BB38
0x18000bb0f  mov     rcx, [rdi+50h]
0x18000bb13  mov     rdx, rdi
0x18000bb16  or      cs:?g_bfSqm_USAGE@@3KA, 20h; ulong g_bfSqm_USAGE
0x18000bb1d  mov     rax, [rcx]
0x18000bb20  mov     rax, [rax+168h]
0x18000bb27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb2c  mov     rax, [rdi]
0x18000bb2f  mov     rax, [rax+1C0h]
0x18000bb36  jmp     short loc_18000BAF3
0x18000bb38  lea     rcx, aAllowblockchec; "AllowBlockCheckBox"
0x18000bb3f  call    cs:__imp_StrToID
0x18000bb45  cmp     ax, si
0x18000bb48  jnz     short loc_18000BB62
0x18000bb4a  mov     rcx, rdi; this
0x18000bb4d  call    ?_GetCheckedStateProp@CShareWithListItemBase@@IEAA_NXZ; CShareWithListItemBase::_GetCheckedStateProp(void)
0x18000bb52  xor     al, 1
0x18000bb54  mov     rcx, rdi; this
0x18000bb57  mov     dl, al; bool
0x18000bb59  call    ?_SetCheckedStateProp@CShareWithListItemBase@@IEAAX_N@Z; CShareWithListItemBase::_SetCheckedStateProp(bool)
0x18000bb5e  mov     byte ptr [rbx+10h], 1
0x18000bb62  mov     rdx, rbx
0x18000bb65  mov     rcx, rdi
0x18000bb68  mov     rbx, [rsp+28h+arg_0]
0x18000bb6d  mov     rsi, [rsp+28h+arg_10]
0x18000bb72  add     rsp, 20h
0x18000bb76  pop     rdi
0x18000bb77  jmp     cs:__imp_?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z; DirectUI::Element::OnEvent(DirectUI::Event *)
```
