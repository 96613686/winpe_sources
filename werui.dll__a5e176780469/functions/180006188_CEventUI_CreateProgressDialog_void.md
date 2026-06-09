# CEventUI::CreateProgressDialog(void)

- ea: `0x180006188`
- end: `0x180006339`
- name: `?CreateProgressDialog@CEventUI@@AEAAJXZ`
- size: `433`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007e10`

## callees

- `0x180006188`
- `0x18000e11c`
- `0x180016c1e`

## import_xrefs

- `COMCTL32!TaskDialogIndirect` at `0x18000631e`
- `COMCTL32!TaskDialogIndirect` at `0x18000631e`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006300`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180006300`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800062bd`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800062dd`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800062bd`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800062dd`

## pseudocode

```c
HRESULT __fastcall CEventUI::CreateProgressDialog(CEventUI *this)
{
  bool v2; // zf
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  int v12; // eax
  __int64 v13; // rcx
  HWND v14; // rcx
  int v16; // [rsp+20h] [rbp-59h] BYREF
  __int64 v17; // [rsp+24h] [rbp-55h]
  _OWORD v18[10]; // [rsp+30h] [rbp-49h] BYREF

  v16 = 2;
  v17 = 283;
  memset_0(v18, 0, sizeof(v18));
  v2 = *((_DWORD *)this + 241) == 0;
  v3 = v18[1];
  *(_OWORD *)((char *)this + 772) = v18[0];
  v4 = v18[2];
  *(_OWORD *)((char *)this + 788) = v3;
  v5 = v18[3];
  *(_OWORD *)((char *)this + 804) = v4;
  v6 = v18[4];
  *(_OWORD *)((char *)this + 820) = v5;
  v7 = v18[5];
  *(_OWORD *)((char *)this + 836) = v6;
  v8 = v18[6];
  *(_OWORD *)((char *)this + 852) = v7;
  v9 = v18[7];
  *(_OWORD *)((char *)this + 868) = v8;
  v10 = v18[8];
  *(_OWORD *)((char *)this + 884) = v9;
  v11 = v18[9];
  *(_OWORD *)((char *)this + 900) = v10;
  *(_OWORD *)((char *)this + 916) = v11;
  *((_QWORD *)this + 98) = &_ImageBase;
  v12 = 8;
  *((_DWORD *)this + 198) = 8;
  *((_DWORD *)this + 193) = 160;
  if ( !v2 )
  {
    v12 = 32776;
    *((_DWORD *)this + 198) = 32776;
  }
  if ( *((_DWORD *)this + 44) != 9 )
    *((_DWORD *)this + 198) = v12 | 0x400;
  v13 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 102) = 280;
  *((_QWORD *)this + 103) = 281;
  *((_DWORD *)this + 208) = 1;
  *((_QWORD *)this + 115) = this;
  *((_QWORD *)this + 100) = v13 + 400;
  *(_QWORD *)((char *)this + 836) = &v16;
  *((_QWORD *)this + 114) = CEventUI::Static_ProgressDlgProc;
  if ( IsWindow(*(HWND *)(v13 + 2200)) )
    *((_QWORD *)this + 97) = *(_QWORD *)(*((_QWORD *)this + 3) + 2200LL);
  if ( !IsWindow(*((HWND *)this + 13)) )
    return TaskDialogIndirect((const TASKDIALOGCONFIG *)((char *)this + 772), 0, 0, 0);
  v14 = (HWND)*((_QWORD *)this + 13);
  *((_DWORD *)this + 235) = 1;
  SendMessageW(v14, 0x465u, 0, (LPARAM)this + 772);
  CInitialConsentUI::WaitForFinish((CEventUI *)((char *)this + 216));
  return 0;
}

```

## disassembly

```asm
0x180006188  mov     [rsp-8+arg_0], rbx
0x18000618d  mov     [rsp-8+arg_8], rdi
0x180006192  push    rbp
0x180006193  lea     rbp, [rsp-57h]
0x180006198  sub     rsp, 0D0h
0x18000619f  mov     rbx, rcx
0x1800061a2  mov     [rbp+57h+var_B0], 2
0x1800061a9  lea     rcx, [rbp+57h+var_A0]; void *
0x1800061ad  mov     [rbp+57h+var_AC], 11Bh
0x1800061b5  xor     edx, edx; Val
0x1800061b7  mov     r8d, 0A0h; Size
0x1800061bd  call    memset_0
0x1800061c2  cmp     dword ptr [rbx+3C4h], 0
0x1800061c9  lea     rdi, [rbx+304h]
0x1800061d0  movups  xmm0, [rbp+57h+var_A0]
0x1800061d4  lea     rax, __ImageBase
0x1800061db  movups  xmm1, [rbp+57h+var_90]
0x1800061df  movups  xmmword ptr [rdi], xmm0
0x1800061e2  movups  xmm0, [rbp+57h+var_80]
0x1800061e6  movups  xmmword ptr [rdi+10h], xmm1
0x1800061ea  movups  xmm1, [rbp+57h+var_70]
0x1800061ee  movups  xmmword ptr [rdi+20h], xmm0
0x1800061f2  movups  xmm0, [rbp+57h+var_60]
0x1800061f6  movups  xmmword ptr [rdi+30h], xmm1
0x1800061fa  movups  xmm1, [rbp+57h+var_50]
0x1800061fe  movups  xmmword ptr [rdi+40h], xmm0
0x180006202  movups  xmm0, [rbp+57h+var_40]
0x180006206  movups  xmmword ptr [rdi+50h], xmm1
0x18000620a  movups  xmm1, [rbp+57h+var_30]
0x18000620e  movups  xmmword ptr [rdi+60h], xmm0
0x180006212  movups  xmm0, [rbp+57h+var_20]
0x180006216  movups  xmmword ptr [rdi+70h], xmm1
0x18000621a  movups  xmm1, [rbp+57h+var_10]
0x18000621e  movups  xmmword ptr [rdi+80h], xmm0
0x180006225  movups  xmmword ptr [rdi+90h], xmm1
0x18000622c  mov     [rbx+310h], rax
0x180006233  mov     eax, 8
0x180006238  mov     [rbx+318h], eax
0x18000623e  mov     dword ptr [rdi], 0A0h
0x180006244  jz      short loc_180006251
0x180006246  mov     eax, 8008h
0x18000624b  mov     [rbx+318h], eax
0x180006251  cmp     dword ptr [rbx+0B0h], 9
0x180006258  jz      short loc_180006264
0x18000625a  bts     eax, 0Ah
0x18000625e  mov     [rbx+318h], eax
0x180006264  mov     rcx, [rbx+18h]
0x180006268  mov     qword ptr [rbx+330h], 118h
0x180006273  mov     qword ptr [rbx+338h], 119h
0x18000627e  mov     dword ptr [rbx+340h], 1
0x180006288  lea     rax, [rcx+190h]
0x18000628f  mov     [rbx+398h], rbx
0x180006296  mov     [rbx+320h], rax
0x18000629d  lea     rax, [rbp+57h+var_B0]
0x1800062a1  mov     [rbx+344h], rax
0x1800062a8  lea     rax, ?Static_ProgressDlgProc@CEventUI@@CAJPEAUHWND__@@I_K_J2@Z; CEventUI::Static_ProgressDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x1800062af  mov     [rbx+390h], rax
0x1800062b6  mov     rcx, [rcx+898h]; hWnd
0x1800062bd  call    cs:__imp_IsWindow
0x1800062c3  test    eax, eax
0x1800062c5  jz      short loc_1800062D9
0x1800062c7  mov     rax, [rbx+18h]
0x1800062cb  mov     rcx, [rax+898h]
0x1800062d2  mov     [rbx+308h], rcx
0x1800062d9  mov     rcx, [rbx+68h]; hWnd
0x1800062dd  call    cs:__imp_IsWindow
0x1800062e3  xor     r8d, r8d; pnRadioButton
0x1800062e6  test    eax, eax
0x1800062e8  jz      short loc_180006316
0x1800062ea  mov     rcx, [rbx+68h]; hWnd
0x1800062ee  mov     r9, rdi; lParam
0x1800062f1  mov     edx, 465h; Msg
0x1800062f6  mov     dword ptr [rbx+3ACh], 1
0x180006300  call    cs:__imp_SendMessageW
0x180006306  lea     rcx, [rbx+0D8h]; this
0x18000630d  call    ?WaitForFinish@CInitialConsentUI@@QEAAJXZ; CInitialConsentUI::WaitForFinish(void)
0x180006312  xor     eax, eax
0x180006314  jmp     short loc_180006324
0x180006316  xor     r9d, r9d; pfVerificationFlagChecked
0x180006319  xor     edx, edx; pnButton
0x18000631b  mov     rcx, rdi; pTaskConfig
0x18000631e  call    cs:__imp_TaskDialogIndirect
0x180006324  lea     r11, [rsp+0D0h+var_s0]
0x18000632c  mov     rbx, [r11+10h]
0x180006330  mov     rdi, [r11+18h]
0x180006334  mov     rsp, r11
0x180006337  pop     rbp
0x180006338  retn
```
