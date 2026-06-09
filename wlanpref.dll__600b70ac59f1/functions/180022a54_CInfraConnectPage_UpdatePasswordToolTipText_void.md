# CInfraConnectPage::UpdatePasswordToolTipText(void)

- ea: `0x180022a54`
- end: `0x180022aed`
- name: `?UpdatePasswordToolTipText@CInfraConnectPage@@AEAAXXZ`
- size: `153`
- prototype: `void __fastcall(CInfraConnectPage *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800219d8`
- `0x180021a70`

## callees

- `0x18000b96c`
- `0x180022a54`
- `0x180022af4`

## import_xrefs

- `USER32!SendMessageW` at `0x180022ab7`
- `USER32!SendMessageW` at `0x180022ab7`

## pseudocode

```c
void __fastcall CInfraConnectPage::UpdatePasswordToolTipText(CInfraConnectPage *this)
{
  int v1; // eax
  unsigned int v3; // edi
  WPARAM v4; // r8

  v1 = *((_DWORD *)this + 373);
  switch ( v1 )
  {
    case 9:
      v3 = 10944;
LABEL_3:
      v4 = 64;
      goto LABEL_10;
    case 7:
      v3 = 10502;
      goto LABEL_3;
    case 4:
      v3 = 10938;
      goto LABEL_3;
  }
  if ( *((_DWORD *)this + 374) != 257 )
    return;
  v3 = 10501;
  v4 = 26;
LABEL_10:
  SendMessageW(*((HWND *)this + 36), 0xC5u, v4, 0);
  CTooltip::SetToolTipTitle((CInfraConnectPage *)((char *)this + 376), 0, 0);
  CTooltip::UpdateTipText((CInfraConnectPage *)((char *)this + 376), 0x2840u, v3);
}

```

## disassembly

```asm
0x180022a54  mov     [rsp+arg_0], rbx
0x180022a59  push    rdi
0x180022a5a  sub     rsp, 20h
0x180022a5e  mov     eax, [rcx+5D4h]
0x180022a64  mov     rbx, rcx
0x180022a67  cmp     eax, 9
0x180022a6a  jnz     short loc_180022A79
0x180022a6c  mov     edi, 2AC0h
0x180022a71  mov     r8d, 40h ; '@'
0x180022a77  jmp     short loc_180022AA8
0x180022a79  cmp     eax, 7
0x180022a7c  jnz     short loc_180022A85
0x180022a7e  mov     edi, 2906h
0x180022a83  jmp     short loc_180022A71
0x180022a85  cmp     eax, 4
0x180022a88  jnz     short loc_180022A91
0x180022a8a  mov     edi, 2ABAh
0x180022a8f  jmp     short loc_180022A71
0x180022a91  cmp     dword ptr [rcx+5D8h], 101h
0x180022a9b  jnz     short loc_180022AE2
0x180022a9d  mov     edi, 2905h
0x180022aa2  mov     r8d, 1Ah; wParam
0x180022aa8  mov     rcx, [rcx+120h]; hWnd
0x180022aaf  xor     r9d, r9d; lParam
0x180022ab2  mov     edx, 0C5h; Msg
0x180022ab7  call    cs:__imp_SendMessageW
0x180022abd  xor     r8d, r8d; unsigned int
0x180022ac0  lea     rcx, [rbx+178h]; this
0x180022ac7  xor     edx, edx; unsigned int
0x180022ac9  call    ?SetToolTipTitle@CTooltip@@QEBAXII@Z; CTooltip::SetToolTipTitle(uint,uint)
0x180022ace  mov     r8d, edi; unsigned int
0x180022ad1  lea     rcx, [rbx+178h]; this
0x180022ad8  mov     edx, 2840h; unsigned int
0x180022add  call    ?UpdateTipText@CTooltip@@QEBAXIIZZ; CTooltip::UpdateTipText(uint,uint,...)
0x180022ae2  mov     rbx, [rsp+28h+arg_0]
0x180022ae7  add     rsp, 20h
0x180022aeb  pop     rdi
0x180022aec  retn
```
