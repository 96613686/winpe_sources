# SSOControls::UpdateUIValues(void)

- ea: `0x1800145c4`
- end: `0x180014674`
- name: `?UpdateUIValues@SSOControls@@QEAAXXZ`
- size: `176`
- prototype: `void __fastcall(SSOControls *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180013570`
- `0x180013800`

## callees

- `0x180014190`

## import_xrefs

- `USER32!CheckRadioButton` at `0x18001460a`
- `USER32!CheckRadioButton` at `0x18001460a`
- `USER32!CheckDlgButton` at `0x1800145e9`
- `USER32!CheckDlgButton` at `0x18001463a`
- `USER32!CheckDlgButton` at `0x180014654`
- `USER32!CheckDlgButton` at `0x1800145e9`
- `USER32!CheckDlgButton` at `0x18001463a`
- `USER32!CheckDlgButton` at `0x180014654`
- `USER32!SetDlgItemInt` at `0x180014620`
- `USER32!SetDlgItemInt` at `0x180014620`

## pseudocode

```c
void __fastcall SSOControls::UpdateUIValues(SSOControls *this)
{
  bool v2; // zf
  HWND v3; // rcx
  int v4; // ecx
  __int64 v5; // rax

  v2 = *((_DWORD *)this + 6) == 0;
  v3 = *(HWND *)(*((_QWORD *)this + 2) + 8LL);
  *((_QWORD *)this + 1) = v3;
  CheckDlgButton(v3, 16004, !v2);
  CheckRadioButton(*((HWND *)this + 1), 16005, 16006, 16006 - (*((_DWORD *)this + 8) != 1));
  SetDlgItemInt(*((HWND *)this + 1), 16008, *((_DWORD *)this + 9), 0);
  CheckDlgButton(*((HWND *)this + 1), 16010, *((_DWORD *)this + 10) != 0);
  CheckDlgButton(*((HWND *)this + 1), 16012, *((_DWORD *)this + 11) != 0);
  v4 = *((_DWORD *)this + 6);
  v5 = *((_QWORD *)this + 2);
  *((_DWORD *)this + 7) = v4;
  *(_DWORD *)(v5 + 64) = v4;
  SSOControls::RefreshControls(this);
}

```

## disassembly

```asm
0x1800145c4  push    rbx
0x1800145c6  sub     rsp, 20h
0x1800145ca  mov     rax, [rcx+10h]
0x1800145ce  mov     rbx, rcx
0x1800145d1  xor     r8d, r8d
0x1800145d4  mov     edx, 3E84h; nIDButton
0x1800145d9  cmp     [rbx+18h], r8d
0x1800145dd  mov     rcx, [rax+8]; hDlg
0x1800145e1  setnz   r8b; uCheck
0x1800145e5  mov     [rbx+8], rcx
0x1800145e9  call    cs:__imp_CheckDlgButton
0x1800145ef  mov     eax, [rbx+20h]
0x1800145f2  mov     r8d, 3E86h; nIDLastButton
0x1800145f8  mov     rcx, [rbx+8]; hDlg
0x1800145fc  dec     eax
0x1800145fe  neg     eax
0x180014600  sbb     r9d, r9d
0x180014603  lea     edx, [r8-1]; nIDFirstButton
0x180014607  add     r9d, r8d; nIDCheckButton
0x18001460a  call    cs:__imp_CheckRadioButton
0x180014610  mov     r8d, [rbx+24h]; uValue
0x180014614  xor     r9d, r9d; bSigned
0x180014617  mov     rcx, [rbx+8]; hDlg
0x18001461b  mov     edx, 3E88h; nIDDlgItem
0x180014620  call    cs:__imp_SetDlgItemInt
0x180014626  mov     rcx, [rbx+8]; hDlg
0x18001462a  xor     r8d, r8d
0x18001462d  cmp     [rbx+28h], r8d
0x180014631  mov     edx, 3E8Ah; nIDButton
0x180014636  setnz   r8b; uCheck
0x18001463a  call    cs:__imp_CheckDlgButton
0x180014640  mov     rcx, [rbx+8]; hDlg
0x180014644  xor     r8d, r8d
0x180014647  cmp     [rbx+2Ch], r8d
0x18001464b  mov     edx, 3E8Ch; nIDButton
0x180014650  setnz   r8b; uCheck
0x180014654  call    cs:__imp_CheckDlgButton
0x18001465a  mov     ecx, [rbx+18h]
0x18001465d  mov     rax, [rbx+10h]
0x180014661  mov     [rbx+1Ch], ecx
0x180014664  mov     [rax+40h], ecx
0x180014667  mov     rcx, rbx; this
0x18001466a  add     rsp, 20h
0x18001466e  pop     rbx
0x18001466f  jmp     ?RefreshControls@SSOControls@@QEAAXXZ; SSOControls::RefreshControls(void)
```
