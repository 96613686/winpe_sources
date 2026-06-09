# CNavigateButton::OnEvent(DirectUI::Event *)

- ea: `0x180051cf0`
- end: `0x180051dc8`
- name: `?OnEvent@CNavigateButton@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `216`
- prototype: `void __fastcall(CNavigateButton *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x1800511f4`
- `0x180051cf0`
- `0x180052130`
- `0x1800522bc`

## import_xrefs

- `DUI70!StrToID` at `0x180051d6a`
- `DUI70!StrToID` at `0x180051d6a`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x180051d0e`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x180051d0e`
- `DUI70!?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x180051dbc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180051da2`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180051da2`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180051d38`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180051d38`

## pseudocode

```c
void __fastcall CNavigateButton::OnEvent(CNavigateButton *this, struct DirectUI::Event *a2)
{
  struct DirectUI::Value *Value; // rbp
  _WORD *v5; // rcx
  __int16 v6; // si
  int v7; // [rsp+58h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 5) == 2 && *((_QWORD *)a2 + 1) == *(_QWORD *)DirectUI::Button::Click(&v7) )
  {
    Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_18005ABE8, 2, 0);
    v5 = (_WORD *)*((_QWORD *)Value + 1);
    if ( v5 && *v5 )
    {
      v6 = *((_WORD *)this + 72);
      if ( v6 && v6 == (unsigned __int16)StrToID(L"ChangeSettingsElement") )
      {
        v7 = 1;
        ControlPanelNavigationTelemetry::SystemPageLinkClick<enum SYSTEMPAGELINK>(&v7);
      }
      CNavigateButton::_Execute((IUnknown **)this);
    }
    else
    {
      CNavigateButton::_Navigate((struct IUnknown **)this);
    }
    DirectUI::Value::Release(Value);
  }
  DirectUI::Element::OnEvent(this, a2);
}

```

## disassembly

```asm
0x180051cf0  push    rbx
0x180051cf2  push    rbp
0x180051cf3  push    rsi
0x180051cf4  push    rdi
0x180051cf5  sub     rsp, 28h
0x180051cf9  cmp     dword ptr [rdx+14h], 2
0x180051cfd  mov     rdi, rdx
0x180051d00  mov     rbx, rcx
0x180051d03  jnz     loc_180051DAE
0x180051d09  lea     rcx, [rsp+48h+arg_8]
0x180051d0e  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x180051d15  nop     dword ptr [rax+rax+00h]
0x180051d1a  mov     r9, [rax]
0x180051d1d  cmp     [rdi+8], r9
0x180051d21  jnz     loc_180051DAE
0x180051d27  xor     r9d, r9d
0x180051d2a  lea     rdx, off_18005ABE8; "ShellExecute"
0x180051d31  mov     rcx, rbx
0x180051d34  lea     r8d, [r9+2]
0x180051d38  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180051d3f  nop     dword ptr [rax+rax+00h]
0x180051d44  mov     rbp, rax
0x180051d47  mov     rcx, [rax+8]
0x180051d4b  xor     eax, eax
0x180051d4d  test    rcx, rcx
0x180051d50  jz      short loc_180051D97
0x180051d52  cmp     [rcx], ax
0x180051d55  jz      short loc_180051D97
0x180051d57  movzx   esi, word ptr [rbx+90h]
0x180051d5e  test    si, si
0x180051d61  jz      short loc_180051D8D
0x180051d63  lea     rcx, aChangesettings; "ChangeSettingsElement"
0x180051d6a  call    cs:__imp_StrToID
0x180051d71  nop     dword ptr [rax+rax+00h]
0x180051d76  cmp     si, ax
0x180051d79  jnz     short loc_180051D8D
0x180051d7b  lea     rcx, [rsp+48h+arg_8]
0x180051d80  mov     [rsp+48h+arg_8], 1
0x180051d88  call    ??$SystemPageLinkClick@W4SYSTEMPAGELINK@@@ControlPanelNavigationTelemetry@@SAX$$QEAW4SYSTEMPAGELINK@@@Z; ControlPanelNavigationTelemetry::SystemPageLinkClick<SYSTEMPAGELINK>(SYSTEMPAGELINK &&)
0x180051d8d  mov     rcx, rbx; this
0x180051d90  call    ?_Execute@CNavigateButton@@AEAAXXZ; CNavigateButton::_Execute(void)
0x180051d95  jmp     short loc_180051D9F
0x180051d97  mov     rcx, rbx; this
0x180051d9a  call    ?_Navigate@CNavigateButton@@AEAAXXZ; CNavigateButton::_Navigate(void)
0x180051d9f  mov     rcx, rbp
0x180051da2  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180051da9  nop     dword ptr [rax+rax+00h]
0x180051dae  mov     rdx, rdi
0x180051db1  mov     rcx, rbx
0x180051db4  add     rsp, 28h
0x180051db8  pop     rdi
0x180051db9  pop     rsi
0x180051dba  pop     rbp
0x180051dbb  pop     rbx
0x180051dbc  jmp     cs:__imp_?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z; DirectUI::Element::OnEvent(DirectUI::Event *)
```
