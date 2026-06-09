# CNavigateButton::OnEvent(DirectUI::Event *)

- ea: `0x18001b960`
- end: `0x18001ba17`
- name: `?OnEvent@CNavigateButton@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `183`
- prototype: `void __fastcall(CNavigateButton *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180019824`
- `0x18001b960`
- `0x18001ca2c`
- `0x18001cbb4`

## import_xrefs

- `DUI70!?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18001ba10`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18001b97e`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x18001b97e`
- `DUI70!StrToID` at `0x18001b9ca`
- `DUI70!StrToID` at `0x18001b9ca`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001b99e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001b99e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001b9fc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001b9fc`

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
    Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_180020778, 2, 0);
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
0x18001b960  push    rbx
0x18001b962  push    rbp
0x18001b963  push    rsi
0x18001b964  push    rdi
0x18001b965  sub     rsp, 28h
0x18001b969  cmp     dword ptr [rdx+14h], 2
0x18001b96d  mov     rdi, rdx
0x18001b970  mov     rbx, rcx
0x18001b973  jnz     loc_18001BA02
0x18001b979  lea     rcx, [rsp+48h+arg_8]
0x18001b97e  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18001b984  mov     r9, [rax]
0x18001b987  cmp     [rdi+8], r9
0x18001b98b  jnz     short loc_18001BA02
0x18001b98d  xor     r9d, r9d
0x18001b990  lea     rdx, off_180020778; "ShellExecute"
0x18001b997  mov     rcx, rbx
0x18001b99a  lea     r8d, [r9+2]
0x18001b99e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001b9a4  mov     rbp, rax
0x18001b9a7  mov     rcx, [rax+8]
0x18001b9ab  xor     eax, eax
0x18001b9ad  test    rcx, rcx
0x18001b9b0  jz      short loc_18001B9F1
0x18001b9b2  cmp     [rcx], ax
0x18001b9b5  jz      short loc_18001B9F1
0x18001b9b7  movzx   esi, word ptr [rbx+90h]
0x18001b9be  test    si, si
0x18001b9c1  jz      short loc_18001B9E7
0x18001b9c3  lea     rcx, aChangesettings; "ChangeSettingsElement"
0x18001b9ca  call    cs:__imp_StrToID
0x18001b9d0  cmp     si, ax
0x18001b9d3  jnz     short loc_18001B9E7
0x18001b9d5  lea     rcx, [rsp+48h+arg_8]
0x18001b9da  mov     [rsp+48h+arg_8], 1
0x18001b9e2  call    ??$SystemPageLinkClick@W4SYSTEMPAGELINK@@@ControlPanelNavigationTelemetry@@SAX$$QEAW4SYSTEMPAGELINK@@@Z; ControlPanelNavigationTelemetry::SystemPageLinkClick<SYSTEMPAGELINK>(SYSTEMPAGELINK &&)
0x18001b9e7  mov     rcx, rbx; this
0x18001b9ea  call    ?_Execute@CNavigateButton@@AEAAXXZ; CNavigateButton::_Execute(void)
0x18001b9ef  jmp     short loc_18001B9F9
0x18001b9f1  mov     rcx, rbx; this
0x18001b9f4  call    ?_Navigate@CNavigateButton@@AEAAXXZ; CNavigateButton::_Navigate(void)
0x18001b9f9  mov     rcx, rbp
0x18001b9fc  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001ba02  mov     rdx, rdi
0x18001ba05  mov     rcx, rbx
0x18001ba08  add     rsp, 28h
0x18001ba0c  pop     rdi
0x18001ba0d  pop     rsi
0x18001ba0e  pop     rbp
0x18001ba0f  pop     rbx
0x18001ba10  jmp     cs:__imp_?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z; DirectUI::Element::OnEvent(DirectUI::Event *)
```
