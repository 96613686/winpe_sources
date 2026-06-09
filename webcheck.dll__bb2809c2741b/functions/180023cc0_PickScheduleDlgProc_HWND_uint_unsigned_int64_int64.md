# PickScheduleDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180023cc0`
- end: `0x180023f9c`
- name: `?PickScheduleDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `732`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x18001ba40`
- `0x180023220`
- `0x180023920`
- `0x180023b54`
- `0x180023cc0`
- `0x180023fa4`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x180023d8c`
- `IEFRAME!__imp_SHRestricted2W` at `0x180023e65`
- `IEFRAME!__imp_SHRestricted2W` at `0x180023d8c`
- `IEFRAME!__imp_SHRestricted2W` at `0x180023e65`
- `USER32!ShowWindow` at `0x180023db1`
- `USER32!ShowWindow` at `0x180023dc8`
- `USER32!ShowWindow` at `0x180023db1`
- `USER32!ShowWindow` at `0x180023dc8`
- `USER32!EnableWindow` at `0x180023e38`
- `USER32!EnableWindow` at `0x180023e4e`
- `USER32!EnableWindow` at `0x180023e82`
- `USER32!EnableWindow` at `0x180023e38`
- `USER32!EnableWindow` at `0x180023e4e`
- `USER32!EnableWindow` at `0x180023e82`
- `USER32!IsDlgButtonChecked` at `0x180023ed8`
- `USER32!IsDlgButtonChecked` at `0x180023ef8`
- `USER32!IsDlgButtonChecked` at `0x180023ed8`
- `USER32!IsDlgButtonChecked` at `0x180023ef8`
- `USER32!GetDlgItem` at `0x180023da6`
- `USER32!GetDlgItem` at `0x180023dbd`
- `USER32!GetDlgItem` at `0x180023df3`
- `USER32!GetDlgItem` at `0x180023e2d`
- `USER32!GetDlgItem` at `0x180023e43`
- `USER32!GetDlgItem` at `0x180023e77`
- `USER32!GetDlgItem` at `0x180023f0a`
- `USER32!GetDlgItem` at `0x180023f3a`
- `USER32!GetDlgItem` at `0x180023da6`
- `USER32!GetDlgItem` at `0x180023dbd`
- `USER32!GetDlgItem` at `0x180023df3`
- `USER32!GetDlgItem` at `0x180023e2d`
- `USER32!GetDlgItem` at `0x180023e43`
- `USER32!GetDlgItem` at `0x180023e77`
- `USER32!GetDlgItem` at `0x180023f0a`
- `USER32!GetDlgItem` at `0x180023f3a`
- `USER32!GetWindowLongPtrW` at `0x180023ce6`
- `USER32!GetWindowLongPtrW` at `0x180023ce6`
- `USER32!SetWindowLongPtrW` at `0x180023d5d`
- `USER32!SetWindowLongPtrW` at `0x180023d5d`
- `USER32!SendMessageW` at `0x180023e07`
- `USER32!SendMessageW` at `0x180023f51`
- `USER32!SendMessageW` at `0x180023e07`
- `USER32!SendMessageW` at `0x180023f51`
- `USER32!CheckRadioButton` at `0x180023e1b`
- `USER32!CheckRadioButton` at `0x180023e1b`

## pseudocode

```c
__int64 __fastcall PickScheduleDlgProc(HWND hDlg, int a2, unsigned __int16 a3, LONG_PTR a4)
{
  LONG_PTR WindowLongPtrW; // rax
  struct _PROPSHEETPAGEW *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rbp
  __int64 v12; // rbx
  int v13; // esi
  int v14; // esi
  int v15; // esi
  __int64 v16; // r13
  int v17; // ebx
  int v18; // ebp
  int v19; // r15d
  HWND v20; // rax
  HWND v21; // rax
  int v22; // eax
  WPARAM v23; // rbx
  HWND v24; // rax
  HWND v25; // rax
  HWND v26; // rax
  int v27; // edx
  HWND v28; // rax
  __int128 v29; // xmm0
  HWND v30; // rax
  struct PICKSCHED_LIST_DATA *v31; // rax
  HWND DlgItem; // rbp
  int v33; // edi
  int v34; // esi
  struct PICKSCHED_LIST_DATA *Data; // rax
  int v37; // [rsp+58h] [rbp+10h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
  v9 = (struct _PROPSHEETPAGEW *)WindowLongPtrW;
  if ( WindowLongPtrW )
  {
    v10 = *(_QWORD *)(WindowLongPtrW + 48);
    if ( v10 )
    {
      v11 = *(_QWORD *)(v10 + 8);
      goto LABEL_6;
    }
  }
  else
  {
    v10 = 0;
  }
  v11 = 0;
LABEL_6:
  v12 = 0;
  v13 = a2 - 2;
  if ( !v13 )
  {
    DlgItem = GetDlgItem(hDlg, 2135);
    v33 = 0;
    v34 = SendMessageW(DlgItem, 0x146u, 0, 0);
    if ( v34 > 0 )
    {
      do
      {
        Data = PickSchedList_GetData(DlgItem, (unsigned int)v33);
        if ( Data )
          operator delete(Data);
        ++v33;
      }
      while ( v33 < v34 );
      return 0;
    }
    return v12;
  }
  v14 = v13 - 76;
  if ( !v14 )
  {
    if ( *(_DWORD *)(a4 + 16) == -208 || *(_DWORD *)(a4 + 16) == -207 )
    {
      if ( IsDlgButtonChecked(hDlg, 2132) && v11 )
      {
        v29 = NOTFCOOKIE_SCHEDULE_GROUP_MANUAL;
      }
      else
      {
        if ( !IsDlgButtonChecked(hDlg, 2134) )
          return 1;
        v30 = GetDlgItem(hDlg, 2135);
        v31 = PickSchedList_GetData(v30, 0xFFFFFFFF);
        if ( !v31 || !v11 )
          return 1;
        v29 = *(_OWORD *)v31;
      }
      *(_OWORD *)(v11 + 132) = v29;
      return 1;
    }
    if ( *(_DWORD *)(a4 + 16) == -200 )
    {
      SetWizButtons(hDlg, *(_QWORD *)(WindowLongPtrW + 16), (const struct WizInfo *)v10);
      return 1;
    }
    return v12;
  }
  v15 = v14 - 194;
  if ( !v15 )
  {
    SetWindowLongPtrW(hDlg, 16, a4);
    v16 = *(_QWORD *)(a4 + 48);
    v37 = -1;
    v17 = PickSched_FillSchedList(hDlg, *(struct OOEBuf **)(v16 + 8), &v37);
    v18 = SHRestricted2W(1342177290, 0, 0);
    v19 = 2132;
    if ( v17 )
    {
      if ( !v18 )
      {
        v22 = v37;
        if ( v37 == -1 )
        {
          v22 = 0;
          v37 = 0;
        }
        else
        {
          v19 = 2134;
        }
        v23 = v22;
        v24 = GetDlgItem(hDlg, 2135);
        SendMessageW(v24, 0x14Eu, v23, 0);
      }
    }
    else
    {
      v20 = GetDlgItem(hDlg, 2134);
      ShowWindow(v20, 0);
      v21 = GetDlgItem(hDlg, 2135);
      ShowWindow(v21, 0);
    }
    CheckRadioButton(hDlg, 2132, 2134, v19);
    if ( v18 )
    {
      v25 = GetDlgItem(hDlg, 2133);
      EnableWindow(v25, 0);
      v26 = GetDlgItem(hDlg, 2134);
      EnableWindow(v26, 0);
      v27 = 2135;
    }
    else
    {
      if ( !(unsigned int)SHRestricted2W(1342177294, 0, 0) )
      {
LABEL_25:
        v10 = v16;
        v9 = (struct _PROPSHEETPAGEW *)a4;
LABEL_26:
        HandleScheduleButtons(hDlg, v9, (struct WizInfo *)v10);
        return 1;
      }
      v27 = 2133;
    }
    v28 = GetDlgItem(hDlg, v27);
    EnableWindow(v28, 0);
    goto LABEL_25;
  }
  if ( v15 == 1 && (a3 == 2132 || (unsigned int)a3 - 2133 <= 1) )
    goto LABEL_26;
  return v12;
}

```

## disassembly

```asm
0x180023cc0  mov     [rsp+arg_0], rbx
0x180023cc5  mov     [rsp+arg_10], rbp
0x180023cca  push    rsi
0x180023ccb  push    rdi
0x180023ccc  push    r13
0x180023cce  push    r14
0x180023cd0  push    r15
0x180023cd2  sub     rsp, 20h
0x180023cd6  mov     esi, edx
0x180023cd8  mov     r14, r9
0x180023cdb  mov     edx, 10h; nIndex
0x180023ce0  mov     r15, r8
0x180023ce3  mov     rdi, rcx
0x180023ce6  call    cs:__imp_GetWindowLongPtrW
0x180023cec  mov     rdx, rax
0x180023cef  test    rax, rax
0x180023cf2  jz      short loc_180023D03
0x180023cf4  mov     r8, [rax+30h]
0x180023cf8  test    r8, r8
0x180023cfb  jz      short loc_180023D06
0x180023cfd  mov     rbp, [r8+8]
0x180023d01  jmp     short loc_180023D08
0x180023d03  xor     r8d, r8d; struct WizInfo *
0x180023d06  xor     ebp, ebp
0x180023d08  xor     ebx, ebx
0x180023d0a  sub     esi, 2
0x180023d0d  jz      loc_180023F32
0x180023d13  sub     esi, 4Ch ; 'L'
0x180023d16  jz      loc_180023E98
0x180023d1c  sub     esi, 0C2h
0x180023d22  jz      short loc_180023D52
0x180023d24  cmp     esi, 1
0x180023d27  jnz     loc_180023F82
0x180023d2d  movzx   ecx, r15w
0x180023d31  sub     ecx, 854h
0x180023d37  jz      loc_180023E8E
0x180023d3d  sub     ecx, esi
0x180023d3f  jz      loc_180023E8E
0x180023d45  cmp     ecx, esi
0x180023d47  jnz     loc_180023F82
0x180023d4d  jmp     loc_180023E8E
0x180023d52  mov     r8, r14; dwNewLong
0x180023d55  mov     edx, 10h; nIndex
0x180023d5a  mov     rcx, rdi; hWnd
0x180023d5d  call    cs:__imp_SetWindowLongPtrW
0x180023d63  mov     r13, [r14+30h]
0x180023d67  lea     r8, [rsp+48h+arg_8]; int *
0x180023d6c  mov     [rsp+48h+arg_8], 0FFFFFFFFh
0x180023d74  mov     rcx, rdi; hDlg
0x180023d77  mov     rdx, [r13+8]; struct OOEBuf *
0x180023d7b  call    ?PickSched_FillSchedList@@YAHPEAUHWND__@@PEAUOOEBuf@@PEAH@Z; PickSched_FillSchedList(HWND__ *,OOEBuf *,int *)
0x180023d80  xor     r8d, r8d
0x180023d83  xor     edx, edx
0x180023d85  mov     ecx, 5000000Ah
0x180023d8a  mov     ebx, eax
0x180023d8c  call    cs:__imp_SHRestricted2W
0x180023d92  mov     esi, 856h
0x180023d97  mov     ebp, eax
0x180023d99  lea     r15d, [rsi-2]
0x180023d9d  test    ebx, ebx
0x180023d9f  jnz     short loc_180023DD0
0x180023da1  mov     edx, esi; nIDDlgItem
0x180023da3  mov     rcx, rdi; hDlg
0x180023da6  call    cs:__imp_GetDlgItem
0x180023dac  mov     rcx, rax; hWnd
0x180023daf  xor     edx, edx; nCmdShow
0x180023db1  call    cs:__imp_ShowWindow
0x180023db7  lea     edx, [rsi+1]; nIDDlgItem
0x180023dba  mov     rcx, rdi; hDlg
0x180023dbd  call    cs:__imp_GetDlgItem
0x180023dc3  mov     rcx, rax; hWnd
0x180023dc6  xor     edx, edx; nCmdShow
0x180023dc8  call    cs:__imp_ShowWindow
0x180023dce  jmp     short loc_180023E0D
0x180023dd0  test    ebp, ebp
0x180023dd2  jnz     short loc_180023E0D
0x180023dd4  mov     eax, [rsp+48h+arg_8]
0x180023dd8  cmp     eax, 0FFFFFFFFh
0x180023ddb  jnz     short loc_180023DE5
0x180023ddd  xor     eax, eax
0x180023ddf  mov     [rsp+48h+arg_8], eax
0x180023de3  jmp     short loc_180023DE8
0x180023de5  mov     r15d, esi
0x180023de8  mov     edx, 857h; nIDDlgItem
0x180023ded  movsxd  rbx, eax
0x180023df0  mov     rcx, rdi; hDlg
0x180023df3  call    cs:__imp_GetDlgItem
0x180023df9  xor     r9d, r9d; lParam
0x180023dfc  mov     r8, rbx; wParam
0x180023dff  mov     rcx, rax; hWnd
0x180023e02  mov     edx, 14Eh; Msg
0x180023e07  call    cs:__imp_SendMessageW
0x180023e0d  mov     r9d, r15d; nIDCheckButton
0x180023e10  mov     r8d, esi; nIDLastButton
0x180023e13  mov     edx, 854h; nIDFirstButton
0x180023e18  mov     rcx, rdi; hDlg
0x180023e1b  call    cs:__imp_CheckRadioButton
0x180023e21  test    ebp, ebp
0x180023e23  jz      short loc_180023E5B
0x180023e25  mov     edx, 855h; nIDDlgItem
0x180023e2a  mov     rcx, rdi; hDlg
0x180023e2d  call    cs:__imp_GetDlgItem
0x180023e33  mov     rcx, rax; hWnd
0x180023e36  xor     edx, edx; bEnable
0x180023e38  call    cs:__imp_EnableWindow
0x180023e3e  mov     edx, esi; nIDDlgItem
0x180023e40  mov     rcx, rdi; hDlg
0x180023e43  call    cs:__imp_GetDlgItem
0x180023e49  mov     rcx, rax; hWnd
0x180023e4c  xor     edx, edx; bEnable
0x180023e4e  call    cs:__imp_EnableWindow
0x180023e54  mov     edx, 857h
0x180023e59  jmp     short loc_180023E74
0x180023e5b  xor     r8d, r8d
0x180023e5e  xor     edx, edx
0x180023e60  mov     ecx, 5000000Eh
0x180023e65  call    cs:__imp_SHRestricted2W
0x180023e6b  test    eax, eax
0x180023e6d  jz      short loc_180023E88
0x180023e6f  mov     edx, 855h; nIDDlgItem
0x180023e74  mov     rcx, rdi; hDlg
0x180023e77  call    cs:__imp_GetDlgItem
0x180023e7d  mov     rcx, rax; hWnd
0x180023e80  xor     edx, edx; bEnable
0x180023e82  call    cs:__imp_EnableWindow
0x180023e88  mov     r8, r13; struct WizInfo *
0x180023e8b  mov     rdx, r14; struct _PROPSHEETPAGEW *
0x180023e8e  mov     rcx, rdi; hWnd
0x180023e91  call    ?HandleScheduleButtons@@YAXPEAUHWND__@@PEAU_PROPSHEETPAGEW@@PEAUWizInfo@@@Z; HandleScheduleButtons(HWND__ *,_PROPSHEETPAGEW *,WizInfo *)
0x180023e96  jmp     short loc_180023EC6
0x180023e98  cmp     dword ptr [r14+10h], 0FFFFFF30h
0x180023ea0  jz      short loc_180023ED0
0x180023ea2  cmp     dword ptr [r14+10h], 0FFFFFF31h
0x180023eaa  jz      short loc_180023ED0
0x180023eac  cmp     dword ptr [r14+10h], 0FFFFFF38h
0x180023eb4  jnz     loc_180023F82
0x180023eba  mov     rdx, [rax+10h]; __int64
0x180023ebe  mov     rcx, rdi; hWnd
0x180023ec1  call    ?SetWizButtons@@YAXPEAUHWND__@@_JPEBUWizInfo@@@Z; SetWizButtons(HWND__ *,__int64,WizInfo const *)
0x180023ec6  mov     ebx, 1
0x180023ecb  jmp     loc_180023F82
0x180023ed0  mov     edx, 854h; nIDButton
0x180023ed5  mov     rcx, rdi; hDlg
0x180023ed8  call    cs:__imp_IsDlgButtonChecked
0x180023ede  test    eax, eax
0x180023ee0  jz      short loc_180023EF0
0x180023ee2  test    rbp, rbp
0x180023ee5  jz      short loc_180023EF0
0x180023ee7  movups  xmm0, cs:NOTFCOOKIE_SCHEDULE_GROUP_MANUAL
0x180023eee  jmp     short loc_180023F28
0x180023ef0  mov     edx, 856h; nIDButton
0x180023ef5  mov     rcx, rdi; hDlg
0x180023ef8  call    cs:__imp_IsDlgButtonChecked
0x180023efe  test    eax, eax
0x180023f00  jz      short loc_180023EC6
0x180023f02  mov     edx, 857h; nIDDlgItem
0x180023f07  mov     rcx, rdi; hDlg
0x180023f0a  call    cs:__imp_GetDlgItem
0x180023f10  mov     rcx, rax; hWnd
0x180023f13  or      edx, 0FFFFFFFFh; wParam
0x180023f16  call    ?PickSchedList_GetData@@YAPEAUPICKSCHED_LIST_DATA@@PEAUHWND__@@H@Z; PickSchedList_GetData(HWND__ *,int)
0x180023f1b  test    rax, rax
0x180023f1e  jz      short loc_180023EC6
0x180023f20  test    rbp, rbp
0x180023f23  jz      short loc_180023EC6
0x180023f25  movups  xmm0, xmmword ptr [rax]
0x180023f28  movdqu  xmmword ptr [rbp+84h], xmm0
0x180023f30  jmp     short loc_180023EC6
0x180023f32  mov     edx, 857h; nIDDlgItem
0x180023f37  mov     rcx, rdi; hDlg
0x180023f3a  call    cs:__imp_GetDlgItem
0x180023f40  xor     r9d, r9d; lParam
0x180023f43  xor     r8d, r8d; wParam
0x180023f46  mov     rcx, rax; hWnd
0x180023f49  mov     edx, 146h; Msg
0x180023f4e  mov     rbp, rax
0x180023f51  call    cs:__imp_SendMessageW
0x180023f57  xor     edi, edi
0x180023f59  mov     rsi, rax
0x180023f5c  test    eax, eax
0x180023f5e  jle     short loc_180023F82
0x180023f60  lea     ebx, [rdi+1]
0x180023f63  mov     edx, edi; wParam
0x180023f65  mov     rcx, rbp; hWnd
0x180023f68  call    ?PickSchedList_GetData@@YAPEAUPICKSCHED_LIST_DATA@@PEAUHWND__@@H@Z; PickSchedList_GetData(HWND__ *,int)
0x180023f6d  test    rax, rax
0x180023f70  jz      short loc_180023F7A
0x180023f72  mov     rcx, rax; lpMem
0x180023f75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023f7a  add     edi, ebx
0x180023f7c  cmp     edi, esi
0x180023f7e  jl      short loc_180023F63
0x180023f80  xor     ebx, ebx
0x180023f82  mov     rbp, [rsp+48h+arg_10]
0x180023f87  mov     rax, rbx
0x180023f8a  mov     rbx, [rsp+48h+arg_0]
0x180023f8f  add     rsp, 20h
0x180023f93  pop     r15
0x180023f95  pop     r14
0x180023f97  pop     r13
0x180023f99  pop     rdi
0x180023f9a  pop     rsi
0x180023f9b  retn
```
