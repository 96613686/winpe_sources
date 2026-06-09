# CPspGeneral::updateUI(CSettings const *)

- ea: `0x180007ddc`
- end: `0x180007fbe`
- name: `?updateUI@CPspGeneral@@IEAAXPEBVCSettings@@@Z`
- size: `482`
- prototype: `void __fastcall(CPspGeneral *__hidden this, const struct CSettings *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1800076a0`
- `0x180007940`
- `0x180007a50`
- `0x180007b30`
- `0x180007c00`
- `0x180007cd0`

## callees

- `0x180004710`
- `0x180007ddc`

## import_xrefs

- `USER32!CheckDlgButton` at `0x180007e78`
- `USER32!CheckDlgButton` at `0x180007ef4`
- `USER32!CheckDlgButton` at `0x180007e78`
- `USER32!CheckDlgButton` at `0x180007ef4`
- `USER32!GetDlgItem` at `0x180007e8b`
- `USER32!GetDlgItem` at `0x180007ea9`
- `USER32!GetDlgItem` at `0x180007f03`
- `USER32!GetDlgItem` at `0x180007e8b`
- `USER32!GetDlgItem` at `0x180007ea9`
- `USER32!GetDlgItem` at `0x180007f03`
- `USER32!EnableWindow` at `0x180007e96`
- `USER32!EnableWindow` at `0x180007eb4`
- `USER32!EnableWindow` at `0x180007f2c`
- `USER32!EnableWindow` at `0x180007e96`
- `USER32!EnableWindow` at `0x180007eb4`
- `USER32!EnableWindow` at `0x180007f2c`

## pseudocode

```c
void __fastcall CPspGeneral::updateUI(CPspGeneral *this, const struct CSettings *a2)
{
  char v3; // al
  const struct CSettings *v4; // rsi
  char v5; // cl
  BOOL v6; // r14d
  bool v7; // dl
  char v8; // r12
  int v9; // r15d
  int v10; // eax
  char v11; // di
  int v12; // ebx
  HWND DlgItem; // rax
  int v14; // ebx
  HWND v15; // rax
  char v16; // al
  bool v17; // r13
  char v18; // di
  char v19; // bl
  HWND v20; // rax
  BOOL v21; // r8d
  __int64 v22; // rax
  _OWORD *v23; // rcx
  __int128 v24; // xmm1
  char v25; // [rsp+60h] [rbp+8h]
  int v26; // [rsp+68h] [rbp+10h]

  *((_BYTE *)this + 49) = 0;
  v3 = *((_BYTE *)a2 + 4);
  v4 = a2;
  v5 = *((_BYTE *)this + 1096);
  v6 = 1;
  v7 = v3 != v5;
  if ( v3 != *((_BYTE *)this + 1644) )
    *((_BYTE *)this + 49) = 1;
  v8 = *((_BYTE *)v4 + 4);
  v25 = *((_BYTE *)this + 2192);
  if ( v8 )
    v9 = *(_DWORD *)v4;
  else
    v9 = 0;
  if ( v5 )
    v10 = *((_DWORD *)this + 273);
  else
    v10 = 0;
  v11 = v7;
  if ( v9 != v10 )
    v11 = 1;
  if ( v9 != *((_DWORD *)this + 410) )
    *((_BYTE *)this + 49) = 1;
  v26 = *((_DWORD *)this + 547);
  CheckDlgButton(*((HWND *)this + 1), 20001, *((_BYTE *)v4 + 4) != 0);
  v12 = *((unsigned __int8 *)v4 + 4);
  DlgItem = GetDlgItem(*((HWND *)this + 1), 20002);
  EnableWindow(DlgItem, v12);
  v14 = *((unsigned __int8 *)v4 + 4);
  v15 = GetDlgItem(*((HWND *)this + 1), 20003);
  EnableWindow(v15, v14);
  v16 = *((_BYTE *)v4 + 6);
  v17 = v11;
  if ( v16 != *((_BYTE *)this + 1098) )
    v17 = 1;
  if ( v16 != *((_BYTE *)this + 1646) )
    *((_BYTE *)this + 49) = 1;
  v18 = *((_BYTE *)v4 + 6);
  v19 = *((_BYTE *)this + 2194);
  CheckDlgButton(*((HWND *)this + 1), 20005, v18 != 0);
  v20 = GetDlgItem(*((HWND *)this + 1), 20004);
  v21 = 1;
  if ( v9 == v26 )
    v21 = v8 != v25;
  if ( v18 == v19 )
    v6 = v21;
  EnableWindow(v20, v6);
  v22 = 4;
  v23 = (_OWORD *)((char *)this + 1092);
  do
  {
    *v23 = *(_OWORD *)v4;
    v23[1] = *((_OWORD *)v4 + 1);
    v23[2] = *((_OWORD *)v4 + 2);
    v23[3] = *((_OWORD *)v4 + 3);
    v23[4] = *((_OWORD *)v4 + 4);
    v23[5] = *((_OWORD *)v4 + 5);
    v23[6] = *((_OWORD *)v4 + 6);
    v24 = *((_OWORD *)v4 + 7);
    v4 = (const struct CSettings *)((char *)v4 + 128);
    v23[7] = v24;
    v23 += 8;
    --v22;
  }
  while ( v22 );
  *v23 = *(_OWORD *)v4;
  v23[1] = *((_OWORD *)v4 + 1);
  *((_DWORD *)v23 + 8) = *((_DWORD *)v4 + 8);
  CPropertyPage::SetModified(this, v17);
}

```

## disassembly

```asm
0x180007ddc  mov     [rsp+arg_10], rbx
0x180007de1  push    rbp
0x180007de2  push    rsi
0x180007de3  push    rdi
0x180007de4  push    r12
0x180007de6  push    r13
0x180007de8  push    r14
0x180007dea  push    r15
0x180007dec  sub     rsp, 20h
0x180007df0  mov     rbp, rcx
0x180007df3  mov     byte ptr [rcx+31h], 0
0x180007df7  mov     al, [rdx+4]
0x180007dfa  mov     rsi, rdx
0x180007dfd  mov     cl, [rcx+448h]
0x180007e03  mov     r14d, 1
0x180007e09  cmp     al, cl
0x180007e0b  setnz   dl
0x180007e0e  cmp     al, [rbp+66Ch]
0x180007e14  jz      short loc_180007E1A
0x180007e16  mov     [rbp+31h], r14b
0x180007e1a  mov     r12b, [rsi+4]
0x180007e1e  mov     al, [rbp+890h]
0x180007e24  mov     [rsp+58h+arg_0], al
0x180007e28  test    r12b, r12b
0x180007e2b  jz      short loc_180007E32
0x180007e2d  mov     r15d, [rsi]
0x180007e30  jmp     short loc_180007E35
0x180007e32  xor     r15d, r15d
0x180007e35  test    cl, cl
0x180007e37  jz      short loc_180007E41
0x180007e39  mov     eax, [rbp+444h]
0x180007e3f  jmp     short loc_180007E43
0x180007e41  xor     eax, eax
0x180007e43  cmp     r15d, eax
0x180007e46  movzx   edi, dl
0x180007e49  cmovnz  edi, r14d
0x180007e4d  cmp     r15d, [rbp+668h]
0x180007e54  jz      short loc_180007E5A
0x180007e56  mov     [rbp+31h], r14b
0x180007e5a  mov     eax, [rbp+88Ch]
0x180007e60  xor     r8d, r8d
0x180007e63  cmp     [rsi+4], r8b
0x180007e67  mov     edx, 4E21h; nIDButton
0x180007e6c  mov     rcx, [rbp+8]; hDlg
0x180007e70  setnz   r8b; uCheck
0x180007e74  mov     [rsp+58h+arg_8], eax
0x180007e78  call    cs:__imp_CheckDlgButton
0x180007e7e  mov     rcx, [rbp+8]; hDlg
0x180007e82  mov     edx, 4E22h; nIDDlgItem
0x180007e87  movzx   ebx, byte ptr [rsi+4]
0x180007e8b  call    cs:__imp_GetDlgItem
0x180007e91  mov     rcx, rax; hWnd
0x180007e94  mov     edx, ebx; bEnable
0x180007e96  call    cs:__imp_EnableWindow
0x180007e9c  mov     rcx, [rbp+8]; hDlg
0x180007ea0  mov     edx, 4E23h; nIDDlgItem
0x180007ea5  movzx   ebx, byte ptr [rsi+4]
0x180007ea9  call    cs:__imp_GetDlgItem
0x180007eaf  mov     rcx, rax; hWnd
0x180007eb2  mov     edx, ebx; bEnable
0x180007eb4  call    cs:__imp_EnableWindow
0x180007eba  mov     al, [rsi+6]
0x180007ebd  cmp     al, [rbp+44Ah]
0x180007ec3  movzx   r13d, dil
0x180007ec7  cmovnz  r13d, r14d
0x180007ecb  cmp     al, [rbp+66Eh]
0x180007ed1  jz      short loc_180007ED7
0x180007ed3  mov     [rbp+31h], r14b
0x180007ed7  mov     dil, [rsi+6]
0x180007edb  xor     r8d, r8d
0x180007ede  mov     rcx, [rbp+8]; hDlg
0x180007ee2  test    dil, dil
0x180007ee5  mov     bl, [rbp+892h]
0x180007eeb  mov     edx, 4E25h; nIDButton
0x180007ef0  setnz   r8b; uCheck
0x180007ef4  call    cs:__imp_CheckDlgButton
0x180007efa  mov     rcx, [rbp+8]; hDlg
0x180007efe  mov     edx, 4E24h; nIDDlgItem
0x180007f03  call    cs:__imp_GetDlgItem
0x180007f09  xor     ecx, ecx
0x180007f0b  mov     r8d, r14d
0x180007f0e  cmp     r12b, [rsp+58h+arg_0]
0x180007f13  setnz   cl
0x180007f16  cmp     r15d, [rsp+58h+arg_8]
0x180007f1b  cmovz   r8d, ecx
0x180007f1f  cmp     dil, bl
0x180007f22  mov     rcx, rax; hWnd
0x180007f25  cmovz   r14d, r8d
0x180007f29  mov     edx, r14d; bEnable
0x180007f2c  call    cs:__imp_EnableWindow
0x180007f32  mov     eax, 4
0x180007f37  lea     rcx, [rbp+444h]
0x180007f3e  lea     edx, [rax+7Ch]
0x180007f41  movups  xmm0, xmmword ptr [rsi]
0x180007f44  movups  xmmword ptr [rcx], xmm0
0x180007f47  movups  xmm1, xmmword ptr [rsi+10h]
0x180007f4b  movups  xmmword ptr [rcx+10h], xmm1
0x180007f4f  movups  xmm0, xmmword ptr [rsi+20h]
0x180007f53  movups  xmmword ptr [rcx+20h], xmm0
0x180007f57  movups  xmm1, xmmword ptr [rsi+30h]
0x180007f5b  movups  xmmword ptr [rcx+30h], xmm1
0x180007f5f  movups  xmm0, xmmword ptr [rsi+40h]
0x180007f63  movups  xmmword ptr [rcx+40h], xmm0
0x180007f67  movups  xmm1, xmmword ptr [rsi+50h]
0x180007f6b  movups  xmmword ptr [rcx+50h], xmm1
0x180007f6f  movups  xmm0, xmmword ptr [rsi+60h]
0x180007f73  movups  xmmword ptr [rcx+60h], xmm0
0x180007f77  movups  xmm1, xmmword ptr [rsi+70h]
0x180007f7b  add     rsi, rdx
0x180007f7e  movups  xmmword ptr [rcx+70h], xmm1
0x180007f82  add     rcx, rdx
0x180007f85  sub     rax, 1
0x180007f89  jnz     short loc_180007F41
0x180007f8b  movups  xmm0, xmmword ptr [rsi]
0x180007f8e  mov     dl, r13b; bool
0x180007f91  movups  xmmword ptr [rcx], xmm0
0x180007f94  movups  xmm1, xmmword ptr [rsi+10h]
0x180007f98  movups  xmmword ptr [rcx+10h], xmm1
0x180007f9c  mov     eax, [rsi+20h]
0x180007f9f  mov     [rcx+20h], eax
0x180007fa2  mov     rcx, rbp; this
0x180007fa5  mov     rbx, [rsp+58h+arg_10]
0x180007faa  add     rsp, 20h
0x180007fae  pop     r15
0x180007fb0  pop     r14
0x180007fb2  pop     r13
0x180007fb4  pop     r12
0x180007fb6  pop     rdi
0x180007fb7  pop     rsi
0x180007fb8  pop     rbp
0x180007fb9  jmp     ?SetModified@CPropertyPage@@QEAAX_N@Z; CPropertyPage::SetModified(bool)
```
