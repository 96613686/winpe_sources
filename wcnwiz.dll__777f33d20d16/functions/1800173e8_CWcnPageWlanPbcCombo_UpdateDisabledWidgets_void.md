# CWcnPageWlanPbcCombo::_UpdateDisabledWidgets(void)

- ea: `0x1800173e8`
- end: `0x18001749c`
- name: `?_UpdateDisabledWidgets@CWcnPageWlanPbcCombo@@AEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CWcnPageWlanPbcCombo *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800165cc`
- `0x180016a60`

## callees

- `0x18000fc10`
- `0x1800172f8`
- `0x1800173e8`
- `0x1800174a4`

## import_xrefs

- `USER32!PostMessageW` at `0x18001748b`
- `USER32!PostMessageW` at `0x18001748b`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x18001745a`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x18001745a`

## pseudocode

```c
void __fastcall CWcnPageWlanPbcCombo::_UpdateDisabledWidgets(CWcnPageWlanPbcCombo *this)
{
  WPARAM v1; // rdi
  unsigned int v3; // edx
  __int64 v4; // r8
  unsigned int v5; // r9d
  HWND *Parent; // rax
  char v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  if ( *((_BYTE *)this + 511)
    || *((_BYTE *)this + 509) && *((_BYTE *)this + 510)
    || !CWcnPageWlanPbcCombo::_ReadPassword(this) )
  {
    v3 = *((_DWORD *)this + 132);
    v4 = *((unsigned int *)this + 133);
    v5 = *((_DWORD *)this + 134);
  }
  else
  {
    v3 = 806;
    v4 = 10801;
    v5 = 0;
  }
  CWcnPageWlanPbcCombo::_UpdateWcnWidgets((DirectUI::Element **)this, v3, (unsigned int *)v4, v5);
  if ( CWcnPageWlanPbcCombo::_ReadPassword(this) && DirectUI::Element::HasContent(*((DirectUI::Element **)this + 71)) )
    v1 = 2;
  Parent = (HWND *)ATL::CWindow::GetParent((char *)this + 152, &v7);
  PostMessageW(*Parent, 0x48Bu, v1, 2);
}

```

## disassembly

```asm
0x1800173e8  mov     [rsp+arg_8], rbx
0x1800173ed  push    rdi
0x1800173ee  sub     rsp, 20h
0x1800173f2  xor     edi, edi
0x1800173f4  mov     rbx, rcx
0x1800173f7  cmp     [rcx+1FFh], dil
0x1800173fe  jnz     short loc_18001742B
0x180017400  cmp     [rcx+1FDh], dil
0x180017407  jz      short loc_180017412
0x180017409  cmp     [rcx+1FEh], dil
0x180017410  jnz     short loc_18001742B
0x180017412  call    ?_ReadPassword@CWcnPageWlanPbcCombo@@AEAA_NXZ; CWcnPageWlanPbcCombo::_ReadPassword(void)
0x180017417  test    al, al
0x180017419  jz      short loc_18001742B
0x18001741b  mov     edx, 326h
0x180017420  mov     r8d, 2A31h
0x180017426  mov     r9d, edi
0x180017429  jmp     short loc_18001743F
0x18001742b  mov     edx, [rbx+210h]; unsigned int
0x180017431  mov     r8d, [rbx+214h]; unsigned int
0x180017438  mov     r9d, [rbx+218h]; unsigned int
0x18001743f  mov     rcx, rbx; this
0x180017442  call    ?_UpdateWcnWidgets@CWcnPageWlanPbcCombo@@AEAAXIII@Z; CWcnPageWlanPbcCombo::_UpdateWcnWidgets(uint,uint,uint)
0x180017447  mov     rcx, rbx; this
0x18001744a  call    ?_ReadPassword@CWcnPageWlanPbcCombo@@AEAA_NXZ; CWcnPageWlanPbcCombo::_ReadPassword(void)
0x18001744f  test    al, al
0x180017451  jz      short loc_180017469
0x180017453  mov     rcx, [rbx+238h]
0x18001745a  call    cs:__imp_?HasContent@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasContent(void)
0x180017460  test    al, al
0x180017462  jz      short loc_180017469
0x180017464  mov     edi, 2
0x180017469  lea     rcx, [rbx+98h]
0x180017470  lea     rdx, [rsp+28h+arg_0]
0x180017475  call    ?GetParent@CWindow@ATL@@QEBA?AV12@XZ; ATL::CWindow::GetParent(void)
0x18001747a  mov     r9d, 2; lParam
0x180017480  mov     r8, rdi; wParam
0x180017483  mov     edx, 48Bh; Msg
0x180017488  mov     rcx, [rax]; hWnd
0x18001748b  call    cs:__imp_PostMessageW
0x180017491  mov     rbx, [rsp+28h+arg_8]
0x180017496  add     rsp, 20h
0x18001749a  pop     rdi
0x18001749b  retn
```
