# CShareWithListItemDevice::OnEvent(DirectUI::Event *)

- ea: `0x18000bb90`
- end: `0x18000bc1f`
- name: `?OnEvent@CShareWithListItemDevice@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `143`
- prototype: `void __fastcall(CShareWithListItemDevice *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ba80`
- `0x18000bb90`
- `0x1800100ac`
- `0x18001e010`

## import_xrefs

- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000bbba`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18000bbba`
- `DUI70!StrToID` at `0x18000bbd0`
- `DUI70!StrToID` at `0x18000bbd0`

## string_xrefs

- `0x18000bbc9`: `RemovePlayerLink`

## pseudocode

```c
void __fastcall CShareWithListItemDevice::OnEvent(CShareWithListItemDevice *this, struct DirectUI::Event *a2)
{
  __int16 v4; // si
  __int64 v5; // rcx
  char v6; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 5) == 1 )
  {
    v4 = *(_WORD *)(*(_QWORD *)a2 + 144LL);
    if ( *(_QWORD *)DirectUI::Button::Click(&v6) == *((_QWORD *)a2 + 1)
      && (unsigned __int16)StrToID(L"RemovePlayerLink") == v4 )
    {
      v5 = *((_QWORD *)this + 10);
      g_bfSqm_USAGE |= 0x400u;
      (*(void (__fastcall **)(__int64, CShareWithListItemDevice *))(*(_QWORD *)v5 + 360LL))(v5, this);
      CShareWithListItemDevice::_OnRemove(this);
      *((_BYTE *)a2 + 16) = 1;
    }
  }
  CShareWithListItemBase::OnEvent(this, a2);
}

```

## disassembly

```asm
0x18000bb90  mov     [rsp+arg_0], rbx
0x18000bb95  mov     [rsp+arg_10], rsi
0x18000bb9a  push    rdi
0x18000bb9b  sub     rsp, 20h
0x18000bb9f  cmp     dword ptr [rdx+14h], 1
0x18000bba3  mov     rbx, rdx
0x18000bba6  mov     rdi, rcx
0x18000bba9  jnz     short loc_18000BC05
0x18000bbab  mov     rax, [rdx]
0x18000bbae  lea     rcx, [rsp+28h+arg_8]
0x18000bbb3  movzx   esi, word ptr [rax+90h]
0x18000bbba  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18000bbc0  mov     r8, [rax]
0x18000bbc3  cmp     r8, [rbx+8]
0x18000bbc7  jnz     short loc_18000BC05
0x18000bbc9  lea     rcx, aRemoveplayerli; "RemovePlayerLink"
0x18000bbd0  call    cs:__imp_StrToID
0x18000bbd6  cmp     ax, si
0x18000bbd9  jnz     short loc_18000BC05
0x18000bbdb  mov     rcx, [rdi+50h]
0x18000bbdf  mov     rdx, rdi
0x18000bbe2  bts     cs:?g_bfSqm_USAGE@@3KA, 0Ah; ulong g_bfSqm_USAGE
0x18000bbea  mov     rax, [rcx]
0x18000bbed  mov     rax, [rax+168h]
0x18000bbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf9  mov     rcx, rdi; this
0x18000bbfc  call    ?_OnRemove@CShareWithListItemDevice@@AEAAJXZ; CShareWithListItemDevice::_OnRemove(void)
0x18000bc01  mov     byte ptr [rbx+10h], 1
0x18000bc05  mov     rdx, rbx; struct DirectUI::Event *
0x18000bc08  mov     rcx, rdi; this
0x18000bc0b  mov     rbx, [rsp+28h+arg_0]
0x18000bc10  mov     rsi, [rsp+28h+arg_10]
0x18000bc15  add     rsp, 20h
0x18000bc19  pop     rdi
0x18000bc1a  jmp     ?OnEvent@CShareWithListItemBase@@UEAAXPEAUEvent@DirectUI@@@Z; CShareWithListItemBase::OnEvent(DirectUI::Event *)
```
