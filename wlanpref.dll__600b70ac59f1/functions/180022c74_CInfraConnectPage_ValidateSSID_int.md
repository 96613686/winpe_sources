# CInfraConnectPage::ValidateSSID(int)

- ea: `0x180022c74`
- end: `0x180022dd2`
- name: `?ValidateSSID@CInfraConnectPage@@AEAAHH@Z`
- size: `350`
- prototype: `__int64 __fastcall(CInfraConnectPage *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180021c98`

## callees

- `0x180020800`
- `0x180022738`
- `0x180022c74`
- `0x18002d840`

## import_xrefs

- `USER32!GetDlgItem` at `0x180022dab`
- `USER32!GetDlgItem` at `0x180022dab`
- `USER32!SetFocus` at `0x180022db4`
- `USER32!SetFocus` at `0x180022db4`
- `wlanapi!WlanStringToSsid` at `0x180022cc8`
- `wlanapi!WlanStringToSsid` at `0x180022cc8`

## pseudocode

```c
__int64 __fastcall CInfraConnectPage::ValidateSSID(HWND *this)
{
  _WORD *v1; // rsi
  signed int v2; // eax
  unsigned int v4; // ebx
  int v5; // ecx
  bool v6; // sf
  unsigned int v7; // r8d
  CTooltip *v8; // rcx
  HWND DlgItem; // rax
  _OWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  int v12; // [rsp+50h] [rbp-38h]

  v1 = this + 50;
  v2 = 0;
  v12 = 0;
  v4 = 0;
  memset(v11, 0, sizeof(v11));
  if ( this == (HWND *)-400LL )
  {
    v2 = -2147024809;
LABEL_19:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        31,
        WPP_1064fdabddc73196039d87943bb008b3_Traceguids,
        (unsigned int)v2);
    }
    v7 = 10918;
    v8 = (CTooltip *)(this + 47);
    goto LABEL_24;
  }
  if ( *v1 )
  {
    v2 = WlanStringToSsid(this + 50, v11);
    if ( v2 == 24 )
    {
      v2 = 0;
      v5 = 1;
    }
    else
    {
      v5 = 0;
      v6 = v2 < 0;
      if ( v2 <= 0 )
        goto LABEL_9;
      v2 = (unsigned __int16)v2 | 0x80070000;
    }
  }
  else
  {
    v5 = 2;
  }
  v6 = v2 < 0;
LABEL_9:
  if ( v6 )
    goto LABEL_19;
  if ( v5 == 1 )
  {
    v7 = 10214;
  }
  else if ( v5 == 2 )
  {
    v7 = 10213;
  }
  else
  {
    v7 = 0;
    v4 = 1;
  }
  if ( !v4 )
  {
    v8 = (CTooltip *)(this + 47);
    if ( v7 == 10214 )
    {
      CTooltip::ShowErrBalloon(v8, 0x283Fu, 0x27E6u, 0x2ABDu, v1);
LABEL_25:
      DlgItem = GetDlgItem(this[13], 10303);
      SetFocus(DlgItem);
      return v4;
    }
LABEL_24:
    CTooltip::ShowErrBalloon(v8, 0x283Fu, v7, 0x2ABDu);
    goto LABEL_25;
  }
  return v4;
}

```

## disassembly

```asm
0x180022c74  push    rbx
0x180022c76  push    rbp
0x180022c77  push    rsi
0x180022c78  push    rdi
0x180022c79  sub     rsp, 68h
0x180022c7d  mov     rax, cs:__security_cookie
0x180022c84  xor     rax, rsp
0x180022c87  mov     [rsp+88h+var_30], rax
0x180022c8c  xor     ebp, ebp
0x180022c8e  lea     rsi, [rcx+190h]
0x180022c95  xor     eax, eax
0x180022c97  xorps   xmm0, xmm0
0x180022c9a  mov     [rsp+88h+var_38], eax
0x180022c9e  mov     rdi, rcx
0x180022ca1  mov     ebx, ebp
0x180022ca3  movups  [rsp+88h+var_58], xmm0
0x180022ca8  movups  [rsp+88h+var_48], xmm0
0x180022cad  test    rsi, rsi
0x180022cb0  jz      loc_180022D40
0x180022cb6  cmp     [rsi], bp
0x180022cb9  jnz     short loc_180022CC0
0x180022cbb  lea     ecx, [rbp+2]
0x180022cbe  jmp     short loc_180022CEA
0x180022cc0  lea     rdx, [rsp+88h+var_58]
0x180022cc5  mov     rcx, rsi
0x180022cc8  call    cs:__imp_WlanStringToSsid
0x180022cce  cmp     eax, 18h
0x180022cd1  jnz     short loc_180022CDC
0x180022cd3  mov     eax, ebp
0x180022cd5  mov     ecx, 1
0x180022cda  jmp     short loc_180022CEA
0x180022cdc  mov     ecx, ebp
0x180022cde  test    eax, eax
0x180022ce0  jle     short loc_180022CEC
0x180022ce2  movzx   eax, ax
0x180022ce5  or      eax, 80070000h
0x180022cea  test    eax, eax
0x180022cec  js      short loc_180022D45
0x180022cee  mov     eax, 27E6h
0x180022cf3  cmp     ecx, 1
0x180022cf6  jnz     short loc_180022CFD
0x180022cf8  mov     r8d, eax
0x180022cfb  jmp     short loc_180022D12
0x180022cfd  cmp     ecx, 2
0x180022d00  jnz     short loc_180022D0A
0x180022d02  mov     r8d, 27E5h
0x180022d08  jmp     short loc_180022D12
0x180022d0a  mov     r8d, ebp
0x180022d0d  mov     ebx, 1
0x180022d12  test    ebx, ebx
0x180022d14  jnz     loc_180022DBA
0x180022d1a  lea     rcx, [rdi+178h]; this
0x180022d21  cmp     r8d, eax
0x180022d24  jnz     short loc_180022D92
0x180022d26  mov     r9d, 2ABDh; unsigned int
0x180022d2c  mov     [rsp+88h+var_68], rsi
0x180022d31  mov     r8d, eax; unsigned int
0x180022d34  mov     edx, 283Fh; unsigned int
0x180022d39  call    ?ShowErrBalloon@CTooltip@@QEAAXIIIZZ; CTooltip::ShowErrBalloon(uint,uint,uint,...)
0x180022d3e  jmp     short loc_180022DA2
0x180022d40  mov     eax, 80070057h
0x180022d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d4c  lea     rdx, WPP_GLOBAL_Control
0x180022d53  cmp     rcx, rdx
0x180022d56  jz      short loc_180022D85
0x180022d58  cmp     byte ptr [rcx+91h], 1
0x180022d5f  jb      short loc_180022D85
0x180022d61  test    byte ptr [rcx+94h], 1
0x180022d68  jz      short loc_180022D85
0x180022d6a  mov     rcx, [rcx+88h]
0x180022d71  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180022d78  mov     edx, 1Fh
0x180022d7d  mov     r9d, eax
0x180022d80  call    WPP_SF_d
0x180022d85  mov     r8d, 2AA6h; unsigned int
0x180022d8b  lea     rcx, [rdi+178h]; this
0x180022d92  mov     edx, 283Fh; unsigned int
0x180022d97  mov     r9d, 2ABDh; unsigned int
0x180022d9d  call    ?ShowErrBalloon@CTooltip@@QEAAXIIIZZ; CTooltip::ShowErrBalloon(uint,uint,uint,...)
0x180022da2  mov     rcx, [rdi+68h]; hDlg
0x180022da6  mov     edx, 283Fh; nIDDlgItem
0x180022dab  call    cs:__imp_GetDlgItem
0x180022db1  mov     rcx, rax; hWnd
0x180022db4  call    cs:__imp_SetFocus
0x180022dba  mov     eax, ebx
0x180022dbc  mov     rcx, [rsp+88h+var_30]
0x180022dc1  xor     rcx, rsp; StackCookie
0x180022dc4  call    __security_check_cookie
0x180022dc9  add     rsp, 68h
0x180022dcd  pop     rdi
0x180022dce  pop     rsi
0x180022dcf  pop     rbp
0x180022dd0  pop     rbx
0x180022dd1  retn
```
