# CLibrarySharingFilterDlg::UpdateStateOfDialogItemsByDevice(CDeviceSettings *)

- ea: `0x180006d34`
- end: `0x1800071f2`
- name: `?UpdateStateOfDialogItemsByDevice@CLibrarySharingFilterDlg@@IEAAJPEAVCDeviceSettings@@@Z`
- size: `1214`
- prototype: `int(CLibrarySharingFilterDlg *__hidden this, struct CDeviceSettings *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180005660`
- `0x18000571c`
- `0x1800059a8`
- `0x180005bbc`

## callees

- `0x18000291e`
- `0x180003860`
- `0x180004ce8`
- `0x180006d34`
- `0x1800166a0`

## import_xrefs

- `USER32!InvalidateRect` at `0x180007194`
- `USER32!InvalidateRect` at `0x180007194`
- `USER32!GetSysColor` at `0x18000716e`
- `USER32!GetSysColor` at `0x18000716e`
- `USER32!EnableWindow` at `0x180006e0c`
- `USER32!EnableWindow` at `0x180006e4d`
- `USER32!EnableWindow` at `0x180006eac`
- `USER32!EnableWindow` at `0x180006f0b`
- `USER32!EnableWindow` at `0x180006f4c`
- `USER32!EnableWindow` at `0x180006f91`
- `USER32!EnableWindow` at `0x180006fd2`
- `USER32!EnableWindow` at `0x18000719f`
- `USER32!EnableWindow` at `0x180006e0c`
- `USER32!EnableWindow` at `0x180006e4d`
- `USER32!EnableWindow` at `0x180006eac`
- `USER32!EnableWindow` at `0x180006f0b`
- `USER32!EnableWindow` at `0x180006f4c`
- `USER32!EnableWindow` at `0x180006f91`
- `USER32!EnableWindow` at `0x180006fd2`
- `USER32!EnableWindow` at `0x18000719f`
- `USER32!SendDlgItemMessageW` at `0x180006dfa`
- `USER32!SendDlgItemMessageW` at `0x180006e3b`
- `USER32!SendDlgItemMessageW` at `0x180006e7c`
- `USER32!SendDlgItemMessageW` at `0x180006e99`
- `USER32!SendDlgItemMessageW` at `0x180006edb`
- `USER32!SendDlgItemMessageW` at `0x180006ef8`
- `USER32!SendDlgItemMessageW` at `0x180006f3a`
- `USER32!SendDlgItemMessageW` at `0x180006f7f`
- `USER32!SendDlgItemMessageW` at `0x180006fc0`
- `USER32!SendDlgItemMessageW` at `0x180007005`
- `USER32!SendDlgItemMessageW` at `0x1800070a2`
- `USER32!SendDlgItemMessageW` at `0x180006dfa`
- `USER32!SendDlgItemMessageW` at `0x180006e3b`
- `USER32!SendDlgItemMessageW` at `0x180006e7c`
- `USER32!SendDlgItemMessageW` at `0x180006e99`
- `USER32!SendDlgItemMessageW` at `0x180006edb`
- `USER32!SendDlgItemMessageW` at `0x180006ef8`
- `USER32!SendDlgItemMessageW` at `0x180006f3a`
- `USER32!SendDlgItemMessageW` at `0x180006f7f`
- `USER32!SendDlgItemMessageW` at `0x180006fc0`
- `USER32!SendDlgItemMessageW` at `0x180007005`
- `USER32!SendDlgItemMessageW` at `0x1800070a2`
- `USER32!SendMessageW` at `0x18000703d`
- `USER32!SendMessageW` at `0x180007076`
- `USER32!SendMessageW` at `0x1800070d6`
- `USER32!SendMessageW` at `0x18000712e`
- `USER32!SendMessageW` at `0x180007157`
- `USER32!SendMessageW` at `0x180007186`
- `USER32!SendMessageW` at `0x18000703d`
- `USER32!SendMessageW` at `0x180007076`
- `USER32!SendMessageW` at `0x1800070d6`
- `USER32!SendMessageW` at `0x18000712e`
- `USER32!SendMessageW` at `0x180007157`
- `USER32!SendMessageW` at `0x180007186`
- `USER32!GetDlgItem` at `0x180006dd2`
- `USER32!GetDlgItem` at `0x180006e1b`
- `USER32!GetDlgItem` at `0x180006e5c`
- `USER32!GetDlgItem` at `0x180006ebb`
- `USER32!GetDlgItem` at `0x180006f1a`
- `USER32!GetDlgItem` at `0x180006f5f`
- `USER32!GetDlgItem` at `0x180006fa0`
- `USER32!GetDlgItem` at `0x180006fe1`
- `USER32!GetDlgItem` at `0x18000701e`
- `USER32!GetDlgItem` at `0x1800070ba`
- `USER32!GetDlgItem` at `0x180006dd2`
- `USER32!GetDlgItem` at `0x180006e1b`
- `USER32!GetDlgItem` at `0x180006e5c`
- `USER32!GetDlgItem` at `0x180006ebb`
- `USER32!GetDlgItem` at `0x180006f1a`
- `USER32!GetDlgItem` at `0x180006f5f`
- `USER32!GetDlgItem` at `0x180006fa0`
- `USER32!GetDlgItem` at `0x180006fe1`
- `USER32!GetDlgItem` at `0x18000701e`
- `USER32!GetDlgItem` at `0x1800070ba`

## pseudocode

```c
__int64 __fastcall CLibrarySharingFilterDlg::UpdateStateOfDialogItemsByDevice(HWND *this, struct CDeviceSettings *a2)
{
  _QWORD *v4; // rcx
  int v5; // r12d
  BOOL v6; // ebx
  HWND DlgItem; // rsi
  LRESULT v8; // rax
  HWND v9; // rsi
  LRESULT v10; // rax
  HWND v11; // rsi
  LRESULT v12; // rax
  BOOL v13; // edx
  HWND v14; // rsi
  LRESULT v15; // rax
  BOOL v16; // edx
  HWND v17; // rsi
  LRESULT v18; // rax
  HWND v19; // rsi
  LRESULT v20; // rax
  HWND v21; // rsi
  LRESULT v22; // rax
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v23; // rdx
  HWND v24; // rsi
  int v25; // r14d
  HWND v26; // rax
  HWND v27; // r15
  int v28; // r13d
  HWND v29; // rax
  HWND v30; // rdi
  int v31; // r15d
  unsigned int v32; // r14d
  __int64 v33; // r12
  int v34; // eax
  int v35; // ecx
  int v36; // edi
  DWORD SysColor; // eax
  __int64 v39; // [rsp+30h] [rbp-79h] BYREF
  int v40; // [rsp+38h] [rbp-71h]
  int v41; // [rsp+3Ch] [rbp-6Dh]
  int v42; // [rsp+40h] [rbp-69h]
  __int64 v43; // [rsp+44h] [rbp-65h]
  int v44; // [rsp+4Ch] [rbp-5Dh]
  __int64 v45; // [rsp+50h] [rbp-59h]
  LPARAM v46; // [rsp+60h] [rbp-49h] BYREF
  int v47; // [rsp+6Ch] [rbp-3Dh]
  int v48; // [rsp+70h] [rbp-39h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( a2 )
  {
    v6 = 1;
    v44 = 0;
    v39 = 1;
    v43 = 1;
    v40 = 1;
    v42 = 1;
    v41 = 1;
    v45 = 0;
    if ( CDeviceSettings::GetWMPDeviceSettings(a2, (struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)&v39) < 0 )
    {
LABEL_46:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_47;
    }
    DlgItem = GetDlgItem(this[1], 307);
    if ( DlgItem )
    {
      v8 = SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0);
      EnableWindow(DlgItem, v8 != 1);
    }
    v9 = GetDlgItem(this[1], 308);
    if ( v9 )
    {
      v10 = SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0);
      EnableWindow(v9, v10 != 1);
    }
    v11 = GetDlgItem(this[1], 309);
    if ( v11 )
    {
      if ( SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0) == 1
        || (v12 = SendDlgItemMessageW(this[1], 307, 0xF0u, 0, 0), v13 = 1, v12 == 1) )
      {
        v13 = 0;
      }
      EnableWindow(v11, v13);
    }
    v14 = GetDlgItem(this[1], 310);
    if ( v14 )
    {
      if ( SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0) == 1
        || (v15 = SendDlgItemMessageW(this[1], 307, 0xF0u, 0, 0), v16 = 1, v15 == 1) )
      {
        v16 = 0;
      }
      EnableWindow(v14, v16);
    }
    v17 = GetDlgItem(this[1], 318);
    if ( v17 )
    {
      v18 = SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0);
      EnableWindow(v17, v18 != 1);
    }
    v19 = GetDlgItem(this[1], 311);
    if ( v19 )
    {
      v20 = SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0);
      EnableWindow(v19, v20 != 1);
    }
    v21 = GetDlgItem(this[1], 312);
    if ( v21 )
    {
      v22 = SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0);
      EnableWindow(v21, v22 == 0);
    }
    v24 = GetDlgItem(this[1], 313);
    if ( !v24 )
    {
LABEL_45:
      HMEHelpers::CleanupWMPDeviceSettings((HMEHelpers *)&v39, v23);
      goto LABEL_46;
    }
    if ( SendDlgItemMessageW(this[1], 311, 0xF0u, 0, 0) == 1 )
    {
      v26 = GetDlgItem(this[1], 313);
      v27 = v26;
      v25 = 1;
      if ( v26 )
      {
        v28 = SendMessageW(v26, 0x1004u, 0, 0);
        if ( v28 > 0 )
        {
          do
          {
            memset_0(&v46, 0, 0x58u);
            v48 = 61440;
            v47 = 0x2000;
            SendMessageW(v27, 0x102Bu, (unsigned int)v5++, (LPARAM)&v46);
          }
          while ( v5 < v28 );
        }
      }
    }
    else
    {
      v25 = 0;
    }
    if ( SendDlgItemMessageW(this[1], 315, 0xF0u, 0, 0) == 1 )
    {
      v29 = GetDlgItem(this[1], 313);
      v30 = v29;
      if ( v29 )
      {
        v31 = SendMessageW(v29, 0x1004u, 0, 0);
        v32 = 0;
        if ( v31 > 0 )
        {
          v33 = v45;
          do
          {
            memset_0(&v46, 0, 0x58u);
            v48 = 61440;
            v47 = *(_DWORD *)(32LL * v32 + v33 + 24) != 0 ? 0x2000 : 4096;
            SendMessageW(v30, 0x102Bu, v32++, (LPARAM)&v46);
          }
          while ( (int)v32 < v31 );
        }
      }
    }
    else if ( !v25 )
    {
LABEL_40:
      v34 = SendMessageW(v24, 0x1023u, 0, 0);
      v35 = 8;
      v36 = v34;
      if ( !v6 )
        v35 = 17;
      SysColor = GetSysColor(v35);
      if ( v36 != SysColor )
      {
        SendMessageW(v24, 0x1024u, 0, SysColor);
        InvalidateRect(v24, 0, 0);
      }
      EnableWindow(v24, v6);
      goto LABEL_45;
    }
    v6 = 0;
    goto LABEL_40;
  }
LABEL_47:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 85, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180006d34  push    rbp
0x180006d36  push    rbx
0x180006d37  push    rsi
0x180006d38  push    rdi
0x180006d39  push    r12
0x180006d3b  push    r13
0x180006d3d  push    r14
0x180006d3f  push    r15
0x180006d41  lea     rbp, [rsp-1Fh]
0x180006d46  sub     rsp, 0C8h
0x180006d4d  mov     rsi, rdx
0x180006d50  mov     rdi, rcx
0x180006d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d5a  lea     rax, WPP_GLOBAL_Control
0x180006d61  cmp     rcx, rax
0x180006d64  jz      short loc_180006D88
0x180006d66  test    byte ptr [rcx+1Ch], 20h
0x180006d6a  jz      short loc_180006D88
0x180006d6c  mov     rcx, [rcx+10h]
0x180006d70  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006d77  mov     edx, 54h ; 'T'
0x180006d7c  call    WPP_SF_
0x180006d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d88  xor     r12d, r12d
0x180006d8b  test    rsi, rsi
0x180006d8e  jz      loc_1800071B5
0x180006d94  lea     ebx, [r12+1]
0x180006d99  mov     [rbp+57h+var_B8], r12
0x180006d9d  lea     rdx, [rbp+57h+var_D0]; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180006da1  mov     [rbp+57h+var_D0], rbx
0x180006da5  mov     rcx, rsi; this
0x180006da8  mov     [rbp+57h+var_BC], ebx
0x180006dab  mov     [rbp+57h+var_C8], ebx
0x180006dae  mov     [rbp+57h+var_C0], ebx
0x180006db1  mov     [rbp+57h+var_C4], ebx
0x180006db4  mov     [rbp+57h+var_B0], r12
0x180006db8  call    ?GetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; CDeviceSettings::GetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006dbd  test    eax, eax
0x180006dbf  js      loc_1800071AE
0x180006dc5  mov     rcx, [rdi+8]; hDlg
0x180006dc9  mov     r15d, 133h
0x180006dcf  mov     edx, r15d; nIDDlgItem
0x180006dd2  call    cs:__imp_GetDlgItem
0x180006dd8  lea     r14d, [r15-43h]
0x180006ddc  mov     rsi, rax
0x180006ddf  lea     r13d, [r15+8]
0x180006de3  test    rax, rax
0x180006de6  jz      short loc_180006E12
0x180006de8  mov     rcx, [rdi+8]; hDlg
0x180006dec  xor     r9d, r9d; wParam
0x180006def  mov     r8d, r14d; Msg
0x180006df2  mov     [rsp+100h+lParam], r12; lParam
0x180006df7  mov     edx, r13d; nIDDlgItem
0x180006dfa  call    cs:__imp_SendDlgItemMessageW
0x180006e00  mov     edx, r12d
0x180006e03  mov     rcx, rsi; hWnd
0x180006e06  cmp     rax, rbx
0x180006e09  setnz   dl; bEnable
0x180006e0c  call    cs:__imp_EnableWindow
0x180006e12  mov     rcx, [rdi+8]; hDlg
0x180006e16  mov     edx, 134h; nIDDlgItem
0x180006e1b  call    cs:__imp_GetDlgItem
0x180006e21  mov     rsi, rax
0x180006e24  test    rax, rax
0x180006e27  jz      short loc_180006E53
0x180006e29  mov     rcx, [rdi+8]; hDlg
0x180006e2d  xor     r9d, r9d; wParam
0x180006e30  mov     r8d, r14d; Msg
0x180006e33  mov     [rsp+100h+lParam], r12; lParam
0x180006e38  mov     edx, r13d; nIDDlgItem
0x180006e3b  call    cs:__imp_SendDlgItemMessageW
0x180006e41  mov     edx, r12d
0x180006e44  mov     rcx, rsi; hWnd
0x180006e47  cmp     rax, rbx
0x180006e4a  setnz   dl; bEnable
0x180006e4d  call    cs:__imp_EnableWindow
0x180006e53  mov     rcx, [rdi+8]; hDlg
0x180006e57  mov     edx, 135h; nIDDlgItem
0x180006e5c  call    cs:__imp_GetDlgItem
0x180006e62  mov     rsi, rax
0x180006e65  test    rax, rax
0x180006e68  jz      short loc_180006EB2
0x180006e6a  mov     rcx, [rdi+8]; hDlg
0x180006e6e  xor     r9d, r9d; wParam
0x180006e71  mov     r8d, r14d; Msg
0x180006e74  mov     [rsp+100h+lParam], r12; lParam
0x180006e79  mov     edx, r13d; nIDDlgItem
0x180006e7c  call    cs:__imp_SendDlgItemMessageW
0x180006e82  cmp     rax, rbx
0x180006e85  jz      short loc_180006EA6
0x180006e87  mov     rcx, [rdi+8]; hDlg
0x180006e8b  xor     r9d, r9d; wParam
0x180006e8e  mov     r8d, r14d; Msg
0x180006e91  mov     [rsp+100h+lParam], r12; lParam
0x180006e96  mov     edx, r15d; nIDDlgItem
0x180006e99  call    cs:__imp_SendDlgItemMessageW
0x180006e9f  mov     edx, ebx
0x180006ea1  cmp     rax, rbx
0x180006ea4  jnz     short loc_180006EA9
0x180006ea6  mov     edx, r12d; bEnable
0x180006ea9  mov     rcx, rsi; hWnd
0x180006eac  call    cs:__imp_EnableWindow
0x180006eb2  mov     rcx, [rdi+8]; hDlg
0x180006eb6  mov     edx, 136h; nIDDlgItem
0x180006ebb  call    cs:__imp_GetDlgItem
0x180006ec1  mov     rsi, rax
0x180006ec4  test    rax, rax
0x180006ec7  jz      short loc_180006F11
0x180006ec9  mov     rcx, [rdi+8]; hDlg
0x180006ecd  xor     r9d, r9d; wParam
0x180006ed0  mov     r8d, r14d; Msg
0x180006ed3  mov     [rsp+100h+lParam], r12; lParam
0x180006ed8  mov     edx, r13d; nIDDlgItem
0x180006edb  call    cs:__imp_SendDlgItemMessageW
0x180006ee1  cmp     rax, rbx
0x180006ee4  jz      short loc_180006F05
0x180006ee6  mov     rcx, [rdi+8]; hDlg
0x180006eea  xor     r9d, r9d; wParam
0x180006eed  mov     r8d, r14d; Msg
0x180006ef0  mov     [rsp+100h+lParam], r12; lParam
0x180006ef5  mov     edx, r15d; nIDDlgItem
0x180006ef8  call    cs:__imp_SendDlgItemMessageW
0x180006efe  mov     edx, ebx
0x180006f00  cmp     rax, rbx
0x180006f03  jnz     short loc_180006F08
0x180006f05  mov     edx, r12d; bEnable
0x180006f08  mov     rcx, rsi; hWnd
0x180006f0b  call    cs:__imp_EnableWindow
0x180006f11  mov     rcx, [rdi+8]; hDlg
0x180006f15  mov     edx, 13Eh; nIDDlgItem
0x180006f1a  call    cs:__imp_GetDlgItem
0x180006f20  mov     rsi, rax
0x180006f23  test    rax, rax
0x180006f26  jz      short loc_180006F52
0x180006f28  mov     rcx, [rdi+8]; hDlg
0x180006f2c  xor     r9d, r9d; wParam
0x180006f2f  mov     r8d, r14d; Msg
0x180006f32  mov     [rsp+100h+lParam], r12; lParam
0x180006f37  mov     edx, r13d; nIDDlgItem
0x180006f3a  call    cs:__imp_SendDlgItemMessageW
0x180006f40  mov     edx, r12d
0x180006f43  mov     rcx, rsi; hWnd
0x180006f46  cmp     rax, rbx
0x180006f49  setnz   dl; bEnable
0x180006f4c  call    cs:__imp_EnableWindow
0x180006f52  mov     rcx, [rdi+8]; hDlg
0x180006f56  mov     r15d, 137h
0x180006f5c  mov     edx, r15d; nIDDlgItem
0x180006f5f  call    cs:__imp_GetDlgItem
0x180006f65  mov     rsi, rax
0x180006f68  test    rax, rax
0x180006f6b  jz      short loc_180006F97
0x180006f6d  mov     rcx, [rdi+8]; hDlg
0x180006f71  xor     r9d, r9d; wParam
0x180006f74  mov     r8d, r14d; Msg
0x180006f77  mov     [rsp+100h+lParam], r12; lParam
0x180006f7c  mov     edx, r13d; nIDDlgItem
0x180006f7f  call    cs:__imp_SendDlgItemMessageW
0x180006f85  mov     edx, r12d
0x180006f88  mov     rcx, rsi; hWnd
0x180006f8b  cmp     rax, rbx
0x180006f8e  setnz   dl; bEnable
0x180006f91  call    cs:__imp_EnableWindow
0x180006f97  mov     rcx, [rdi+8]; hDlg
0x180006f9b  mov     edx, 138h; nIDDlgItem
0x180006fa0  call    cs:__imp_GetDlgItem
0x180006fa6  mov     rsi, rax
0x180006fa9  test    rax, rax
0x180006fac  jz      short loc_180006FD8
0x180006fae  mov     rcx, [rdi+8]; hDlg
0x180006fb2  xor     r9d, r9d; wParam
0x180006fb5  mov     r8d, r14d; Msg
0x180006fb8  mov     [rsp+100h+lParam], r12; lParam
0x180006fbd  mov     edx, r13d; nIDDlgItem
0x180006fc0  call    cs:__imp_SendDlgItemMessageW
0x180006fc6  mov     edx, r12d
0x180006fc9  mov     rcx, rsi; hWnd
0x180006fcc  test    rax, rax
0x180006fcf  setz    dl; bEnable
0x180006fd2  call    cs:__imp_EnableWindow
0x180006fd8  mov     rcx, [rdi+8]; hDlg
0x180006fdc  mov     edx, 139h; nIDDlgItem
0x180006fe1  call    cs:__imp_GetDlgItem
0x180006fe7  mov     rsi, rax
0x180006fea  test    rax, rax
0x180006fed  jz      loc_1800071A5
0x180006ff3  mov     rcx, [rdi+8]; hDlg
0x180006ff7  xor     r9d, r9d; wParam
0x180006ffa  mov     r8d, r14d; Msg
0x180006ffd  mov     [rsp+100h+lParam], r12; lParam
0x180007002  mov     edx, r15d; nIDDlgItem
0x180007005  call    cs:__imp_SendDlgItemMessageW
0x18000700b  cmp     rax, rbx
0x18000700e  jz      short loc_180007015
0x180007010  mov     r14d, r12d
0x180007013  jmp     short loc_18000708D
0x180007015  mov     rcx, [rdi+8]; hDlg
0x180007019  mov     edx, 139h; nIDDlgItem
0x18000701e  call    cs:__imp_GetDlgItem
0x180007024  mov     r15, rax
0x180007027  mov     r14d, ebx
0x18000702a  test    rax, rax
0x18000702d  jz      short loc_18000708D
0x18000702f  xor     r9d, r9d; lParam
0x180007032  xor     r8d, r8d; wParam
0x180007035  mov     edx, 1004h; Msg
0x18000703a  mov     rcx, rax; hWnd
0x18000703d  call    cs:__imp_SendMessageW
0x180007043  mov     r13, rax
0x180007046  test    eax, eax
0x180007048  jle     short loc_180007087
0x18000704a  xor     edx, edx; Val
0x18000704c  lea     rcx, [rbp+57h+var_A0]; void *
0x180007050  lea     r8d, [rdx+58h]; Size
0x180007054  call    memset_0
0x180007059  mov     r8d, r12d; wParam
0x18000705c  lea     r9, [rbp+57h+var_A0]; lParam
0x180007060  mov     edx, 102Bh; Msg
0x180007065  mov     [rbp+57h+var_90], 0F000h
0x18000706c  mov     rcx, r15; hWnd
0x18000706f  mov     [rbp+57h+var_94], 2000h
0x180007076  call    cs:__imp_SendMessageW
0x18000707c  add     r12d, ebx
0x18000707f  cmp     r12d, r13d
0x180007082  jl      short loc_18000704A
0x180007084  xor     r12d, r12d
0x180007087  mov     r13d, 13Bh
0x18000708d  mov     rcx, [rdi+8]; hDlg
0x180007091  xor     r9d, r9d; wParam
0x180007094  mov     r8d, 0F0h; Msg
0x18000709a  mov     [rsp+100h+lParam], r12; lParam
0x18000709f  mov     edx, r13d; nIDDlgItem
0x1800070a2  call    cs:__imp_SendDlgItemMessageW
0x1800070a8  cmp     rax, rbx
0x1800070ab  jnz     loc_180007141
0x1800070b1  mov     rcx, [rdi+8]; hDlg
0x1800070b5  mov     edx, 139h; nIDDlgItem
0x1800070ba  call    cs:__imp_GetDlgItem
0x1800070c0  mov     rdi, rax
0x1800070c3  test    rax, rax
0x1800070c6  jz      short loc_180007146
0x1800070c8  xor     r9d, r9d; lParam
0x1800070cb  xor     r8d, r8d; wParam
0x1800070ce  mov     edx, 1004h; Msg
0x1800070d3  mov     rcx, rax; hWnd
0x1800070d6  call    cs:__imp_SendMessageW
0x1800070dc  mov     r15, rax
0x1800070df  mov     r14d, r12d
0x1800070e2  test    eax, eax
0x1800070e4  jle     short loc_180007146
0x1800070e6  mov     r12, [rbp+57h+var_B0]
0x1800070ea  mov     r13d, 1000h
0x1800070f0  xor     edx, edx; Val
0x1800070f2  lea     rcx, [rbp+57h+var_A0]; void *
0x1800070f6  lea     r8d, [rdx+58h]; Size
0x1800070fa  call    memset_0
0x1800070ff  mov     [rbp+57h+var_90], 0F000h
0x180007106  lea     r9, [rbp+57h+var_A0]; lParam
0x18000710a  mov     eax, r14d
0x18000710d  mov     edx, 102Bh; Msg
0x180007112  shl     rax, 5
0x180007116  mov     r8d, r14d; wParam
0x180007119  mov     eax, [rax+r12+18h]
0x18000711e  neg     eax
0x180007120  sbb     ecx, ecx
0x180007122  and     ecx, r13d
0x180007125  add     ecx, r13d
0x180007128  mov     [rbp+57h+var_94], ecx
0x18000712b  mov     rcx, rdi; hWnd
0x18000712e  call    cs:__imp_SendMessageW
0x180007134  add     r14d, ebx
0x180007137  cmp     r14d, r15d
0x18000713a  jl      short loc_1800070F0
0x18000713c  xor     r12d, r12d
0x18000713f  jmp     short loc_180007146
0x180007141  test    r14d, r14d
0x180007144  jz      short loc_180007149
0x180007146  mov     ebx, r12d
0x180007149  xor     r9d, r9d; lParam
0x18000714c  xor     r8d, r8d; wParam
0x18000714f  mov     edx, 1023h; Msg
0x180007154  mov     rcx, rsi; hWnd
0x180007157  call    cs:__imp_SendMessageW
0x18000715d  mov     ecx, 8
0x180007162  mov     rdi, rax
0x180007165  test    ebx, ebx
0x180007167  jnz     short loc_18000716E
0x180007169  mov     ecx, 11h; nIndex
0x18000716e  call    cs:__imp_GetSysColor
0x180007174  cmp     edi, eax
0x180007176  jz      short loc_18000719A
0x180007178  mov     r9d, eax; lParam
0x18000717b  xor     r8d, r8d; wParam
0x18000717e  mov     edx, 1024h; Msg
0x180007183  mov     rcx, rsi; hWnd
0x180007186  call    cs:__imp_SendMessageW
0x18000718c  xor     r8d, r8d; bErase
0x18000718f  xor     edx, edx; lpRect
0x180007191  mov     rcx, rsi; hWnd
0x180007194  call    cs:__imp_InvalidateRect
  ... truncated ...
```
