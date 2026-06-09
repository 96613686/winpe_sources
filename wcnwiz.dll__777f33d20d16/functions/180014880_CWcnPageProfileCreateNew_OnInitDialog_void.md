# CWcnPageProfileCreateNew::OnInitDialog(void)

- ea: `0x180014880`
- end: `0x180014cd3`
- name: `?OnInitDialog@CWcnPageProfileCreateNew@@QEAAXXZ`
- size: `1107`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180009be4`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x180011bb8`
- `0x1800141d4`
- `0x180014880`
- `0x180015db4`
- `0x18001b9a4`
- `0x18001d818`
- `0x18002de1c`

## import_xrefs

- `USER32!SetWindowTextW` at `0x18001495e`
- `USER32!SetWindowTextW` at `0x1800149c3`
- `USER32!SetWindowTextW` at `0x18001495e`
- `USER32!SetWindowTextW` at `0x1800149c3`
- `USER32!SendMessageW` at `0x18001492a`
- `USER32!SendMessageW` at `0x1800149fe`
- `USER32!SendMessageW` at `0x180014a82`
- `USER32!SendMessageW` at `0x180014b05`
- `USER32!SendMessageW` at `0x180014b33`
- `USER32!SendMessageW` at `0x18001492a`
- `USER32!SendMessageW` at `0x1800149fe`
- `USER32!SendMessageW` at `0x180014a82`
- `USER32!SendMessageW` at `0x180014b05`
- `USER32!SendMessageW` at `0x180014b33`
- `USER32!GetDlgItem` at `0x1800149ec`
- `USER32!GetDlgItem` at `0x180014a6f`
- `USER32!GetDlgItem` at `0x180014b1f`
- `USER32!GetDlgItem` at `0x180014c3a`
- `USER32!GetDlgItem` at `0x1800149ec`
- `USER32!GetDlgItem` at `0x180014a6f`
- `USER32!GetDlgItem` at `0x180014b1f`
- `USER32!GetDlgItem` at `0x180014c3a`
- `GDI32!GetObjectW` at `0x180014a0e`
- `GDI32!GetObjectW` at `0x180014a92`
- `GDI32!GetObjectW` at `0x180014a0e`
- `GDI32!GetObjectW` at `0x180014a92`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::OnInitDialog(CWcnPageProfileCreateNew *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  int ControlHandles; // eax
  int v5; // edi
  _QWORD *v6; // r10
  __int64 v7; // rdx
  _BYTE *v8; // rdi
  HWND v9; // rcx
  BOOL v10; // eax
  const char *v11; // rax
  __int64 v12; // r10
  HWND v13; // rcx
  HWND DlgItem; // rax
  void *v15; // rax
  int Font; // eax
  HWND v17; // rax
  void *v18; // rax
  int v19; // eax
  void *v20; // rcx
  WPARAM v21; // r8
  WPARAM v22; // rdi
  HWND v23; // rax
  int IconMetric; // eax
  void *v25; // rcx
  int v26; // eax
  void *v27; // rcx
  int v28; // eax
  void *v29; // rcx
  int v30; // eax
  HWND v31; // rax
  __int64 v32; // r8
  unsigned int v33; // eax
  __int64 v34; // r10
  LONG pv; // [rsp+30h] [rbp-A8h] BYREF
  int cWidth; // [rsp+34h] [rbp-A4h]
  unsigned __int8 v37; // [rsp+4Bh] [rbp-8Dh]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 10, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  ControlHandles = CWcnPageProfileCreateNew::GetControlHandles(this);
  v5 = ControlHandles;
  if ( ControlHandles < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_52;
    v7 = 11;
    goto LABEL_50;
  }
  SendMessageW(*((HWND *)this + 37), 0xC5u, 0x20u, 0);
  if ( *((_WORD *)this + 184) )
  {
    v9 = (HWND)*((_QWORD *)this + 37);
    v8 = (char *)this + 666;
    *((_BYTE *)this + 666) = 1;
    v10 = SetWindowTextW(v9, (LPCWSTR)this + 184);
    *((_BYTE *)this + 666) = 0;
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v11 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v12 + 16), 12, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v11);
      }
      CWcnPageProfileCreateNew::SuggestDefaultProfileName(this);
    }
  }
  else
  {
    CWcnPageProfileCreateNew::SuggestDefaultProfileName(this);
    v8 = (char *)this + 666;
  }
  if ( *((_WORD *)this + 248) )
  {
    v13 = (HWND)*((_QWORD *)this + 39);
    *v8 = 1;
    SetWindowTextW(v13, (LPCWSTR)this + 248);
    *v8 = 0;
  }
  else
  {
    *((_DWORD *)this + 52) = -1;
  }
  memset_0(&pv, 0, 0x5Cu);
  DlgItem = GetDlgItem(*((HWND *)this + 21), 1412);
  v15 = (void *)SendMessageW(DlgItem, 0x31u, 0, 0);
  GetObjectW(v15, 92, &pv);
  Font = WcnSysCreateFont(pv, cWidth, 0, 1u, 400, (HFONT *)this + 28);
  if ( Font < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
      (unsigned int)Font);
  v17 = GetDlgItem(*((HWND *)this + 21), 1082);
  v18 = (void *)SendMessageW(v17, 0x31u, 0, 0);
  GetObjectW(v18, 92, &pv);
  v19 = WcnSysCreateFont(pv, cWidth, 1u, v37, 700, (HFONT *)this + 29);
  if ( v19 < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
        (unsigned int)v19);
  }
  v21 = *((_QWORD *)this + 28);
  if ( v21 )
    SendMessageW(*((HWND *)this + 39), 0x30u, v21, 1);
  v22 = *((_QWORD *)this + 29);
  if ( v22 )
  {
    v23 = GetDlgItem(*((HWND *)this + 21), 2952);
    SendMessageW(v23, 0x30u, v22, 1);
  }
  IconMetric = IsolationAwareLoadIconMetric(v20, 105, 0, (char *)this + 648);
  if ( IconMetric < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
        (unsigned int)IconMetric);
  }
  v26 = IsolationAwareLoadIconMetric(v25, 107, 0, (char *)this + 640);
  if ( v26 < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
        (unsigned int)v26);
  }
  v28 = IsolationAwareLoadIconMetric(v27, 106, 0, (char *)this + 632);
  if ( v28 < 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
        (unsigned int)v28);
  }
  v30 = IsolationAwareLoadIconMetric(v29, 32518, 0, (char *)this + 656);
  if ( v30 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
      (unsigned int)v30);
  v31 = GetDlgItem(*((HWND *)this + 21), 2918);
  ControlHandles = CWcnToggleButton::Init((struct tagRECT *)this + 15, v31, v32);
  v5 = ControlHandles;
  if ( ControlHandles >= 0 )
    goto LABEL_51;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v7 = 19;
LABEL_50:
    WPP_SF_d(v6[2], v7, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, (unsigned int)ControlHandles);
LABEL_51:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_52:
  if ( v6 != &WPP_GLOBAL_Control && (v5 < 0 || *((_BYTE *)v6 + 25) >= 6u) )
  {
    v33 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v34 + 16), 20, (unsigned int)WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v33, v5);
  }
}

```

## disassembly

```asm
0x180014880  push    rbx
0x180014882  push    rbp
0x180014883  push    rsi
0x180014884  push    rdi
0x180014885  push    r14
0x180014887  push    r15
0x180014889  sub     rsp, 0A8h
0x180014890  mov     rax, cs:__security_cookie
0x180014897  xor     rax, rsp
0x18001489a  mov     [rsp+0D8h+var_48], rax
0x1800148a2  mov     rbx, rcx
0x1800148a5  mov     r10, cs:WPP_GLOBAL_Control
0x1800148ac  lea     r14, WPP_GLOBAL_Control
0x1800148b3  lea     r15, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x1800148ba  cmp     r10, r14
0x1800148bd  jz      short loc_1800148E4
0x1800148bf  cmp     byte ptr [r10+19h], 6
0x1800148c4  jb      short loc_1800148E4
0x1800148c6  mov     ecx, 1; int
0x1800148cb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800148d0  mov     rcx, [r10+10h]
0x1800148d4  mov     edx, 0Ah
0x1800148d9  mov     r9, rax
0x1800148dc  mov     r8, r15
0x1800148df  call    WPP_SF_s
0x1800148e4  mov     rcx, rbx; this
0x1800148e7  call    ?GetControlHandles@CWcnPageProfileCreateNew@@AEAAJXZ; CWcnPageProfileCreateNew::GetControlHandles(void)
0x1800148ec  xor     ebp, ebp
0x1800148ee  mov     edi, eax
0x1800148f0  test    eax, eax
0x1800148f2  jns     short loc_180014917
0x1800148f4  mov     r10, cs:WPP_GLOBAL_Control
0x1800148fb  cmp     r10, r14
0x1800148fe  jz      loc_180014CB3
0x180014904  cmp     byte ptr [r10+19h], 2
0x180014909  jb      loc_180014C83
0x18001490f  lea     edx, [rbp+0Bh]
0x180014912  jmp     loc_180014C6D
0x180014917  mov     rcx, [rbx+128h]; hWnd
0x18001491e  xor     r9d, r9d; lParam
0x180014921  mov     edx, 0C5h; Msg
0x180014926  lea     r8d, [r9+20h]; wParam
0x18001492a  call    cs:__imp_SendMessageW
0x180014930  lea     rdx, [rbx+170h]; lpString
0x180014937  cmp     [rdx], bp
0x18001493a  jnz     short loc_18001494D
0x18001493c  mov     rcx, rbx; this
0x18001493f  call    ?SuggestDefaultProfileName@CWcnPageProfileCreateNew@@QEAAJXZ; CWcnPageProfileCreateNew::SuggestDefaultProfileName(void)
0x180014944  lea     rdi, [rbx+29Ah]
0x18001494b  jmp     short loc_1800149A1
0x18001494d  mov     rcx, [rbx+128h]; hWnd
0x180014954  lea     rdi, [rbx+29Ah]
0x18001495b  mov     byte ptr [rdi], 1
0x18001495e  call    cs:__imp_SetWindowTextW
0x180014964  mov     [rdi], bpl
0x180014967  test    eax, eax
0x180014969  jnz     short loc_1800149A1
0x18001496b  mov     r10, cs:WPP_GLOBAL_Control
0x180014972  cmp     r10, r14
0x180014975  jz      short loc_180014999
0x180014977  cmp     byte ptr [r10+19h], 3
0x18001497c  jb      short loc_180014999
0x18001497e  xor     ecx, ecx; int
0x180014980  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014985  mov     rcx, [r10+10h]
0x180014989  mov     edx, 0Ch
0x18001498e  mov     r9, rax
0x180014991  mov     r8, r15
0x180014994  call    WPP_SF_s
0x180014999  mov     rcx, rbx; this
0x18001499c  call    ?SuggestDefaultProfileName@CWcnPageProfileCreateNew@@QEAAJXZ; CWcnPageProfileCreateNew::SuggestDefaultProfileName(void)
0x1800149a1  lea     rdx, [rbx+1F0h]; lpString
0x1800149a8  cmp     [rdx], bp
0x1800149ab  jnz     short loc_1800149B9
0x1800149ad  mov     dword ptr [rbx+0D0h], 0FFFFFFFFh
0x1800149b7  jmp     short loc_1800149CC
0x1800149b9  mov     rcx, [rbx+138h]; hWnd
0x1800149c0  mov     byte ptr [rdi], 1
0x1800149c3  call    cs:__imp_SetWindowTextW
0x1800149c9  mov     [rdi], bpl
0x1800149cc  mov     edi, 5Ch ; '\'
0x1800149d1  lea     rcx, [rsp+0D8h+pv]; void *
0x1800149d6  mov     r8d, edi; Size
0x1800149d9  xor     edx, edx; Val
0x1800149db  call    memset_0
0x1800149e0  mov     rcx, [rbx+0A8h]; hDlg
0x1800149e7  mov     edx, 584h; nIDDlgItem
0x1800149ec  call    cs:__imp_GetDlgItem
0x1800149f2  xor     r9d, r9d; lParam
0x1800149f5  lea     edx, [rdi-2Bh]; Msg
0x1800149f8  mov     rcx, rax; hWnd
0x1800149fb  xor     r8d, r8d; wParam
0x1800149fe  call    cs:__imp_SendMessageW
0x180014a04  lea     r8, [rsp+0D8h+pv]; pv
0x180014a09  mov     edx, edi; c
0x180014a0b  mov     rcx, rax; h
0x180014a0e  call    cs:__imp_GetObjectW
0x180014a14  mov     edx, [rsp+0D8h+cWidth]; cWidth
0x180014a18  lea     rsi, [rbx+0E0h]
0x180014a1f  mov     ecx, [rsp+0D8h+pv]; cHeight
0x180014a23  mov     r9b, 1; unsigned __int8
0x180014a26  mov     [rsp+0D8h+var_B0], rsi; HFONT *
0x180014a2b  xor     r8d, r8d; unsigned __int8
0x180014a2e  mov     [rsp+0D8h+var_B8], 190h; int
0x180014a36  call    ?WcnSysCreateFont@@YAJJJEEJPEAPEAUHFONT__@@@Z; WcnSysCreateFont(long,long,uchar,uchar,long,HFONT__ * *)
0x180014a3b  test    eax, eax
0x180014a3d  jns     short loc_180014A63
0x180014a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a46  cmp     rcx, r14
0x180014a49  jz      short loc_180014A63
0x180014a4b  cmp     byte ptr [rcx+19h], 3
0x180014a4f  jb      short loc_180014A63
0x180014a51  mov     rcx, [rcx+10h]
0x180014a55  lea     edx, [rdi-4Fh]
0x180014a58  mov     r9d, eax
0x180014a5b  mov     r8, r15
0x180014a5e  call    WPP_SF_d
0x180014a63  mov     rcx, [rbx+0A8h]; hDlg
0x180014a6a  mov     edx, 43Ah; nIDDlgItem
0x180014a6f  call    cs:__imp_GetDlgItem
0x180014a75  xor     r9d, r9d; lParam
0x180014a78  xor     r8d, r8d; wParam
0x180014a7b  mov     rcx, rax; hWnd
0x180014a7e  lea     edx, [r9+31h]; Msg
0x180014a82  call    cs:__imp_SendMessageW
0x180014a88  lea     r8, [rsp+0D8h+pv]; pv
0x180014a8d  mov     edx, edi; c
0x180014a8f  mov     rcx, rax; h
0x180014a92  call    cs:__imp_GetObjectW
0x180014a98  mov     r9b, [rsp+0D8h+var_8D]; unsigned __int8
0x180014a9d  lea     rdi, [rbx+0E8h]
0x180014aa4  mov     edx, [rsp+0D8h+cWidth]; cWidth
0x180014aa8  mov     r8b, 1; unsigned __int8
0x180014aab  mov     ecx, [rsp+0D8h+pv]; cHeight
0x180014aaf  mov     [rsp+0D8h+var_B0], rdi; HFONT *
0x180014ab4  mov     [rsp+0D8h+var_B8], 2BCh; int
0x180014abc  call    ?WcnSysCreateFont@@YAJJJEEJPEAPEAUHFONT__@@@Z; WcnSysCreateFont(long,long,uchar,uchar,long,HFONT__ * *)
0x180014ac1  test    eax, eax
0x180014ac3  jns     short loc_180014AEB
0x180014ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014acc  cmp     rcx, r14
0x180014acf  jz      short loc_180014AEB
0x180014ad1  cmp     byte ptr [rcx+19h], 3
0x180014ad5  jb      short loc_180014AEB
0x180014ad7  mov     rcx, [rcx+10h]
0x180014adb  mov     edx, 0Eh
0x180014ae0  mov     r9d, eax
0x180014ae3  mov     r8, r15
0x180014ae6  call    WPP_SF_d
0x180014aeb  mov     r8, [rsi]; wParam
0x180014aee  mov     esi, 30h ; '0'
0x180014af3  test    r8, r8
0x180014af6  jz      short loc_180014B0B
0x180014af8  mov     rcx, [rbx+138h]; hWnd
0x180014aff  lea     r9d, [rsi-2Fh]; lParam
0x180014b03  mov     edx, esi; Msg
0x180014b05  call    cs:__imp_SendMessageW
0x180014b0b  mov     rdi, [rdi]
0x180014b0e  test    rdi, rdi
0x180014b11  jz      short loc_180014B39
0x180014b13  mov     rcx, [rbx+0A8h]; hDlg
0x180014b1a  mov     edx, 0B88h; nIDDlgItem
0x180014b1f  call    cs:__imp_GetDlgItem
0x180014b25  mov     r9d, 1; lParam
0x180014b2b  mov     r8, rdi; wParam
0x180014b2e  mov     rcx, rax; hWnd
0x180014b31  mov     edx, esi; Msg
0x180014b33  call    cs:__imp_SendMessageW
0x180014b39  xor     r8d, r8d
0x180014b3c  lea     r9, [rbx+288h]
0x180014b43  lea     edx, [r8+69h]
0x180014b47  call    IsolationAwareLoadIconMetric
0x180014b4c  test    eax, eax
0x180014b4e  jns     short loc_180014B76
0x180014b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b57  cmp     rcx, r14
0x180014b5a  jz      short loc_180014B76
0x180014b5c  cmp     byte ptr [rcx+19h], 3
0x180014b60  jb      short loc_180014B76
0x180014b62  mov     rcx, [rcx+10h]
0x180014b66  mov     edx, 0Fh
0x180014b6b  mov     r9d, eax
0x180014b6e  mov     r8, r15
0x180014b71  call    WPP_SF_d
0x180014b76  xor     r8d, r8d
0x180014b79  lea     r9, [rbx+280h]
0x180014b80  lea     edx, [r8+6Bh]
0x180014b84  call    IsolationAwareLoadIconMetric
0x180014b89  test    eax, eax
0x180014b8b  jns     short loc_180014BB3
0x180014b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b94  cmp     rcx, r14
0x180014b97  jz      short loc_180014BB3
0x180014b99  cmp     byte ptr [rcx+19h], 3
0x180014b9d  jb      short loc_180014BB3
0x180014b9f  mov     rcx, [rcx+10h]
0x180014ba3  mov     edx, 10h
0x180014ba8  mov     r9d, eax
0x180014bab  mov     r8, r15
0x180014bae  call    WPP_SF_d
0x180014bb3  xor     r8d, r8d
0x180014bb6  lea     r9, [rbx+278h]
0x180014bbd  lea     edx, [r8+6Ah]
0x180014bc1  call    IsolationAwareLoadIconMetric
0x180014bc6  test    eax, eax
0x180014bc8  jns     short loc_180014BF0
0x180014bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd1  cmp     rcx, r14
0x180014bd4  jz      short loc_180014BF0
0x180014bd6  cmp     byte ptr [rcx+19h], 3
0x180014bda  jb      short loc_180014BF0
0x180014bdc  mov     rcx, [rcx+10h]
0x180014be0  mov     edx, 11h
0x180014be5  mov     r9d, eax
0x180014be8  mov     r8, r15
0x180014beb  call    WPP_SF_d
0x180014bf0  lea     r9, [rbx+290h]
0x180014bf7  xor     r8d, r8d
0x180014bfa  mov     edx, 7F06h
0x180014bff  call    IsolationAwareLoadIconMetric
0x180014c04  test    eax, eax
0x180014c06  jns     short loc_180014C2E
0x180014c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c0f  cmp     rcx, r14
0x180014c12  jz      short loc_180014C2E
0x180014c14  cmp     byte ptr [rcx+19h], 3
0x180014c18  jb      short loc_180014C2E
0x180014c1a  mov     rcx, [rcx+10h]
0x180014c1e  mov     edx, 12h
0x180014c23  mov     r9d, eax
0x180014c26  mov     r8, r15
0x180014c29  call    WPP_SF_d
0x180014c2e  mov     rcx, [rbx+0A8h]; hDlg
0x180014c35  mov     edx, 0B66h; nIDDlgItem
0x180014c3a  call    cs:__imp_GetDlgItem
0x180014c40  mov     rdx, rax; HWND
0x180014c43  lea     rcx, [rbx+0F0h]; this
0x180014c4a  call    ?Init@CWcnToggleButton@@QEAAJPEAUHWND__@@@Z; CWcnToggleButton::Init(HWND__ *)
0x180014c4f  mov     edi, eax
0x180014c51  test    eax, eax
0x180014c53  jns     short loc_180014C7C
0x180014c55  mov     r10, cs:WPP_GLOBAL_Control
0x180014c5c  cmp     r10, r14
0x180014c5f  jz      short loc_180014CB3
0x180014c61  cmp     byte ptr [r10+19h], 3
0x180014c66  jb      short loc_180014C83
0x180014c68  mov     edx, 13h
0x180014c6d  mov     rcx, [r10+10h]
0x180014c71  mov     r9d, eax
0x180014c74  mov     r8, r15
0x180014c77  call    WPP_SF_d
0x180014c7c  mov     r10, cs:WPP_GLOBAL_Control
0x180014c83  cmp     r10, r14
0x180014c86  jz      short loc_180014CB3
0x180014c88  test    edi, edi
0x180014c8a  js      short loc_180014C93
0x180014c8c  cmp     byte ptr [r10+19h], 6
0x180014c91  jb      short loc_180014CB3
0x180014c93  or      ecx, 0FFFFFFFFh; int
0x180014c96  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014c9b  mov     rcx, [r10+10h]
0x180014c9f  mov     edx, 14h
0x180014ca4  mov     r9, rax
0x180014ca7  mov     [rsp+0D8h+var_B8], edi
0x180014cab  mov     r8, r15
0x180014cae  call    WPP_SF_sd
0x180014cb3  mov     rcx, [rsp+0D8h+var_48]
0x180014cbb  xor     rcx, rsp; StackCookie
0x180014cbe  call    __security_check_cookie
0x180014cc3  add     rsp, 0A8h
0x180014cca  pop     r15
0x180014ccc  pop     r14
0x180014cce  pop     rdi
0x180014ccf  pop     rsi
0x180014cd0  pop     rbp
0x180014cd1  pop     rbx
0x180014cd2  retn
```
