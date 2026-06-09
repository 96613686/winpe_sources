# CACSecurityPage::RefreshControls(void)

- ea: `0x18000c824`
- end: `0x18000cd40`
- name: `?RefreshControls@CACSecurityPage@@AEAA_JXZ`
- size: `1308`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `6`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009dd0`
- `0x18000a29c`
- `0x18000a690`
- `0x18000a7f8`
- `0x18000b078`
- `0x18000c290`

## callees

- `0x1800060a0`
- `0x180006134`
- `0x180007010`
- `0x180007070`
- `0x180008074`
- `0x18000833c`
- `0x180008388`
- `0x180008cdc`
- `0x180009278`
- `0x18000c824`
- `0x18000cf08`
- `0x18000d240`
- `0x18000d2b4`
- `0x18000d3c4`
- `0x18001bf40`

## import_xrefs

- `USER32!ShowWindow` at `0x18000ca6d`
- `USER32!ShowWindow` at `0x18000ca95`
- `USER32!ShowWindow` at `0x18000cb61`
- `USER32!ShowWindow` at `0x18000cb7b`
- `USER32!ShowWindow` at `0x18000cb99`
- `USER32!ShowWindow` at `0x18000ccb7`
- `USER32!ShowWindow` at `0x18000cccf`
- `USER32!ShowWindow` at `0x18000ca6d`
- `USER32!ShowWindow` at `0x18000ca95`
- `USER32!ShowWindow` at `0x18000cb61`
- `USER32!ShowWindow` at `0x18000cb7b`
- `USER32!ShowWindow` at `0x18000cb99`
- `USER32!ShowWindow` at `0x18000ccb7`
- `USER32!ShowWindow` at `0x18000cccf`
- `USER32!IsWindowEnabled` at `0x18000cbd7`
- `USER32!IsWindowEnabled` at `0x18000cbd7`
- `USER32!EnableWindow` at `0x18000c965`
- `USER32!EnableWindow` at `0x18000c980`
- `USER32!EnableWindow` at `0x18000c99b`
- `USER32!EnableWindow` at `0x18000c9b6`
- `USER32!EnableWindow` at `0x18000ca4b`
- `USER32!EnableWindow` at `0x18000ca81`
- `USER32!EnableWindow` at `0x18000c965`
- `USER32!EnableWindow` at `0x18000c980`
- `USER32!EnableWindow` at `0x18000c99b`
- `USER32!EnableWindow` at `0x18000c9b6`
- `USER32!EnableWindow` at `0x18000ca4b`
- `USER32!EnableWindow` at `0x18000ca81`
- `USER32!GetDlgItem` at `0x18000c953`
- `USER32!GetDlgItem` at `0x18000c974`
- `USER32!GetDlgItem` at `0x18000c98f`
- `USER32!GetDlgItem` at `0x18000c9aa`
- `USER32!GetDlgItem` at `0x18000ca40`
- `USER32!GetDlgItem` at `0x18000ca62`
- `USER32!GetDlgItem` at `0x18000cae0`
- `USER32!GetDlgItem` at `0x18000cb0b`
- `USER32!GetDlgItem` at `0x18000cb36`
- `USER32!GetDlgItem` at `0x18000cb56`
- `USER32!GetDlgItem` at `0x18000cb70`
- `USER32!GetDlgItem` at `0x18000cb8e`
- `USER32!GetDlgItem` at `0x18000cbce`
- `USER32!GetDlgItem` at `0x18000cbe8`
- `USER32!GetDlgItem` at `0x18000cc0c`
- `USER32!GetDlgItem` at `0x18000cca7`
- `USER32!GetDlgItem` at `0x18000ccc4`
- `USER32!GetDlgItem` at `0x18000c953`
- `USER32!GetDlgItem` at `0x18000c974`
- `USER32!GetDlgItem` at `0x18000c98f`
- `USER32!GetDlgItem` at `0x18000c9aa`
- `USER32!GetDlgItem` at `0x18000ca40`
- `USER32!GetDlgItem` at `0x18000ca62`
- `USER32!GetDlgItem` at `0x18000cae0`
- `USER32!GetDlgItem` at `0x18000cb0b`
- `USER32!GetDlgItem` at `0x18000cb36`
- `USER32!GetDlgItem` at `0x18000cb56`
- `USER32!GetDlgItem` at `0x18000cb70`
- `USER32!GetDlgItem` at `0x18000cb8e`
- `USER32!GetDlgItem` at `0x18000cbce`
- `USER32!GetDlgItem` at `0x18000cbe8`
- `USER32!GetDlgItem` at `0x18000cc0c`
- `USER32!GetDlgItem` at `0x18000cca7`
- `USER32!GetDlgItem` at `0x18000ccc4`
- `USER32!SendMessageW` at `0x18000cb27`
- `USER32!SendMessageW` at `0x18000cb47`
- `USER32!SendMessageW` at `0x18000cbfc`
- `USER32!SendMessageW` at `0x18000cb27`
- `USER32!SendMessageW` at `0x18000cb47`
- `USER32!SendMessageW` at `0x18000cbfc`
- `wlanapi!FreeMSMSecConfig` at `0x18000cd16`
- `wlanapi!FreeMSMSecConfig` at `0x18000cd16`
- `wlanapi!MSMSecCreateDefaultProfileStatic` at `0x18000c8c1`
- `wlanapi!MSMSecCreateDefaultProfileStatic` at `0x18000c8c1`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::RefreshControls(CACSecurityPage *this)
{
  __int64 v2; // rax
  __int64 v3; // r13
  signed int inited; // esi
  unsigned int *v5; // rbx
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // r14
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rax
  _DWORD *v8; // rcx
  struct _AUI_CIPHER_INFO *v9; // r15
  int v10; // eax
  CACSecurityPage *v11; // rcx
  __int64 v12; // r8
  _DWORD *v13; // rax
  int v14; // r12d
  int v15; // ebx
  HWND DlgItem; // rax
  HWND v17; // rax
  HWND v18; // rax
  HWND v19; // rax
  EapControls *v20; // rcx
  int v21; // ebx
  HWND v22; // rax
  int v23; // ebx
  HWND v24; // rax
  int v25; // eax
  int v26; // eax
  BOOL v27; // eax
  unsigned int v28; // eax
  int v29; // ecx
  HWND v30; // rax
  WPARAM v31; // r14
  HWND v32; // rax
  HWND v33; // rax
  HWND v34; // rax
  HWND v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  struct _AUI_EAP_METHOD_INFO *ItemDataPtr; // r15
  HWND v39; // rax
  CACSecurityPage *v40; // rcx
  HWND v41; // rax
  int v42; // ebx
  HWND v43; // rax
  __int64 v44; // r14
  __int64 v45; // r8
  _BYTE *v46; // rbx
  __int64 v47; // r8
  int v48; // edx
  HWND v49; // rax
  HWND v50; // rax
  __int64 v52; // [rsp+20h] [rbp-48h] BYREF
  __int64 v53; // [rsp+28h] [rbp-40h] BYREF
  __int128 v54; // [rsp+30h] [rbp-38h] BYREF
  __int128 v55; // [rsp+40h] [rbp-28h] BYREF
  int v56; // [rsp+50h] [rbp-18h]

  v52 = 0;
  v54 = 0;
  v56 = 0;
  v2 = *((_QWORD *)this + 5);
  v55 = 0;
  v53 = 0;
  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 552) + 32LL) + 424LL);
  if ( !v3 )
  {
    inited = -2147023690;
    return LresFromHr(inited);
  }
  v5 = *(unsigned int **)(v3 + 24);
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
  v8 = (_DWORD *)*((_QWORD *)this + 3);
  v9 = CurrentlySelectedCipher;
  LODWORD(v54) = *v8;
  *((_QWORD *)&v54 + 1) = v8 + 1;
  v10 = MSMSecCreateDefaultProfileStatic(1, &v54, &v52);
  inited = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      inited = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_56;
  }
  v12 = v52;
  if ( !CurrentlySelectedAuth )
  {
    LODWORD(v55) = 1;
    CurrentlySelectedAuth = (struct _AUI_AUTH_INFO *)&v55;
    if ( v5 )
    {
      DWORD1(v55) = CACSecurityPage::Auth2AUIAuth(v11, *v5, v52);
      DWORD2(v55) = *(_DWORD *)(v3 + 32);
    }
    else
    {
      v13 = *(_DWORD **)(v52 + 24);
      DWORD2(v55) = 0;
      v11 = (CACSecurityPage *)(unsigned int)*v13;
      DWORD1(v55) = *v13;
    }
  }
  if ( !v9 )
  {
    v9 = (struct _AUI_CIPHER_INFO *)&v53;
    if ( !v5 )
      v5 = *(unsigned int **)(v12 + 24);
    HIDWORD(v53) = v5[1];
  }
  v14 = CACSecurityPage::NeedsKey(v11, CurrentlySelectedAuth, v9);
  v15 = *((_DWORD *)CurrentlySelectedAuth + 2);
  if ( !*((_DWORD *)this + 23) )
  {
    DlgItem = GetDlgItem(*((HWND *)this + 1), 1110);
    EnableWindow(DlgItem, 1);
    v17 = GetDlgItem(*((HWND *)this + 1), 1111);
    EnableWindow(v17, 1);
    v18 = GetDlgItem(*((HWND *)this + 1), 1112);
    EnableWindow(v18, 1);
    v19 = GetDlgItem(*((HWND *)this + 1), 1113);
    EnableWindow(v19, 1);
  }
  v20 = (EapControls *)*((_QWORD *)this + 167);
  if ( v15 )
  {
    inited = EapControls::InitOneXUIControls(v20);
    EapControls::EnableControls(*((EapControls **)this + 167), 1);
    EapControls::ShowControls(*((EapControls **)this + 167), 1);
    if ( inited < 0 )
      goto LABEL_56;
  }
  else
  {
    inited = 0;
    EapControls::EnableControls(v20, 0);
    EapControls::ShowControls(*((EapControls **)this + 167), 0);
  }
  NetworkKeyControls::ShowControls(*((NetworkKeyControls **)this + 166), v14 != 0);
  v21 = CACSecurityPage::ShowIHVConfigureButton(this);
  v22 = GetDlgItem(*((HWND *)this + 1), 1124);
  EnableWindow(v22, v21);
  v23 = CACSecurityPage::ShowIHVConfigureButton(this);
  v24 = GetDlgItem(*((HWND *)this + 1), 1124);
  ShowWindow(v24, v23);
  v25 = CACSecurityPage::ShowAddlSettingButton(this);
  EnableWindow(*((HWND *)this + 10), v25);
  v26 = CACSecurityPage::ShowAddlSettingButton(this);
  ShowWindow(*((HWND *)this + 10), v26);
  v27 = 0;
  if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
    v27 = *(_DWORD *)CurrentlySelectedAuth == 0;
  if ( (!v9 || *(_DWORD *)v9) && !v27 )
  {
    v28 = *((_DWORD *)CurrentlySelectedAuth + 1);
    if ( v28 <= 9 && (v29 = 656, _bittest(&v29, v28)) )
    {
      v30 = GetDlgItem(*((HWND *)this + 1), 1115);
      v31 = 64;
    }
    else
    {
      if ( (v28 != 1 || *((_DWORD *)v9 + 1) != 257) && v28 != 2 )
        goto LABEL_32;
      v30 = GetDlgItem(*((HWND *)this + 1), 1115);
      v31 = 26;
    }
    SendMessageW(v30, 0xC5u, v31, 0);
    v32 = GetDlgItem(*((HWND *)this + 1), 1116);
    SendMessageW(v32, 0xC5u, v31, 0);
  }
LABEL_32:
  v33 = GetDlgItem(*((HWND *)this + 1), 1131);
  ShowWindow(v33, 0);
  v34 = GetDlgItem(*((HWND *)this + 1), 1132);
  ShowWindow(v34, 0);
  v35 = GetDlgItem(*((HWND *)this + 1), 1130);
  ShowWindow(v35, 0);
  v36 = *((_QWORD *)this + 169);
  if ( v36 )
  {
    v37 = *(_QWORD *)(v36 + 24);
    if ( v37 )
    {
      if ( *(_DWORD *)(v37 + 108) )
        goto LABEL_56;
    }
  }
  ItemDataPtr = 0;
  v39 = GetDlgItem(*((HWND *)this + 1), 1119);
  if ( IsWindowEnabled(v39) )
  {
    v41 = GetDlgItem(*((HWND *)this + 1), 1119);
    v42 = SendMessageW(v41, 0x147u, 0, 0);
    v43 = GetDlgItem(*((HWND *)this + 1), 1119);
    ItemDataPtr = (struct _AUI_EAP_METHOD_INFO *)ComboBox_GetItemDataPtr(v43, v42);
  }
  v44 = *((_QWORD *)this + 169);
  if ( v44 )
  {
    v45 = *(_QWORD *)(v44 + 24);
    if ( v45 )
    {
      if ( *(_DWORD *)(v45 + 88)
        && !(unsigned int)CACSecurityPage::AreEAPMethodDiffer(
                            v40,
                            ItemDataPtr,
                            *(struct _AUI_EAP_METHOD_INFO **)(v45 + 80)) )
      {
        goto LABEL_56;
      }
    }
  }
  v46 = (_BYTE *)*((_QWORD *)this + 156);
  if ( v46 )
  {
    if ( (*v46 & 2) != 0
      && !(unsigned int)CACSecurityPage::AreEAPMethodDiffer(
                          v40,
                          ItemDataPtr,
                          *(struct _AUI_EAP_METHOD_INFO **)(*((_QWORD *)this + 167) + 48LL)) )
    {
      goto LABEL_56;
    }
  }
  if ( v44 )
  {
    v47 = *(_QWORD *)(v44 + 24);
    if ( v47 )
    {
      if ( *(_DWORD *)(v47 + 88)
        && (unsigned int)CACSecurityPage::AreEAPMethodDiffer(
                           v40,
                           ItemDataPtr,
                           *(struct _AUI_EAP_METHOD_INFO **)(v47 + 80)) )
      {
        v48 = 1132;
LABEL_49:
        v49 = GetDlgItem(*((HWND *)this + 1), v48);
        ShowWindow(v49, 5);
        v50 = GetDlgItem(*((HWND *)this + 1), 1130);
        ShowWindow(v50, 5);
        goto LABEL_56;
      }
    }
  }
  if ( v46
    && (*v46 & 2) != 0
    && (*v46 & 8) == 0
    && (*v46 & 0x10) == 0
    && (unsigned int)CACSecurityPage::AreEAPMethodDiffer(
                       v40,
                       ItemDataPtr,
                       *(struct _AUI_EAP_METHOD_INFO **)(*((_QWORD *)this + 167) + 48LL)) )
  {
    v48 = 1131;
    goto LABEL_49;
  }
LABEL_56:
  if ( v52 )
    FreeMSMSecConfig(&v52);
  return LresFromHr(inited);
}

```

## disassembly

```asm
0x18000c824  push    rbp
0x18000c826  push    rbx
0x18000c827  push    rsi
0x18000c828  push    rdi
0x18000c829  push    r12
0x18000c82b  push    r13
0x18000c82d  push    r14
0x18000c82f  push    r15
0x18000c831  mov     rbp, rsp
0x18000c834  sub     rsp, 68h
0x18000c838  mov     rax, cs:__security_cookie
0x18000c83f  xor     rax, rsp
0x18000c842  mov     [rbp+var_10], rax
0x18000c846  xor     eax, eax
0x18000c848  xor     r12d, r12d
0x18000c84b  mov     [rbp+var_48], r12
0x18000c84f  xorps   xmm0, xmm0
0x18000c852  movups  [rbp+var_38], xmm0
0x18000c856  mov     [rbp+var_18], eax
0x18000c859  mov     rdi, rcx
0x18000c85c  mov     rax, [rcx+28h]
0x18000c860  movups  [rbp+var_28], xmm0
0x18000c864  mov     [rbp+var_40], r12
0x18000c868  mov     rcx, [rax+228h]
0x18000c86f  mov     rax, [rcx+20h]
0x18000c873  mov     r13, [rax+1A8h]
0x18000c87a  test    r13, r13
0x18000c87d  jnz     short loc_18000C889
0x18000c87f  mov     esi, 800704B6h
0x18000c884  jmp     loc_18000CD1C
0x18000c889  mov     rbx, [r13+18h]
0x18000c88d  mov     rcx, rdi; this
0x18000c890  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000c895  mov     rcx, rdi; this
0x18000c898  mov     r14, rax
0x18000c89b  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000c8a0  mov     rcx, [rdi+18h]
0x18000c8a4  lea     r8, [rbp+var_48]
0x18000c8a8  mov     r15, rax
0x18000c8ab  lea     rdx, [rbp+var_38]
0x18000c8af  mov     eax, [rcx]
0x18000c8b1  mov     dword ptr [rbp+var_38], eax
0x18000c8b4  lea     rax, [rcx+4]
0x18000c8b8  mov     ecx, 1
0x18000c8bd  mov     qword ptr [rbp+var_38+8], rax
0x18000c8c1  call    cs:__imp_MSMSecCreateDefaultProfileStatic
0x18000c8c7  mov     esi, eax
0x18000c8c9  test    eax, eax
0x18000c8cb  jz      short loc_18000C8E1
0x18000c8cd  jle     loc_18000CD0C
0x18000c8d3  movzx   esi, ax
0x18000c8d6  or      esi, 80070000h
0x18000c8dc  jmp     loc_18000CD0C
0x18000c8e1  mov     r8, [rbp+var_48]
0x18000c8e5  test    r14, r14
0x18000c8e8  jnz     short loc_18000C91A
0x18000c8ea  mov     dword ptr [rbp+var_28], 1
0x18000c8f1  lea     r14, [rbp+var_28]
0x18000c8f5  test    rbx, rbx
0x18000c8f8  jz      short loc_18000C90D
0x18000c8fa  mov     edx, [rbx]
0x18000c8fc  call    ?Auth2AUIAuth@CACSecurityPage@@AEAA?AW4AUI_DOT11_AUTH_ALGORITHM@@W4_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::Auth2AUIAuth(_DOT11_AUTH_ALGORITHM)
0x18000c901  mov     dword ptr [rbp+var_28+4], eax
0x18000c904  mov     eax, [r13+20h]
0x18000c908  mov     dword ptr [rbp+var_28+8], eax
0x18000c90b  jmp     short loc_18000C91A
0x18000c90d  mov     rax, [r8+18h]
0x18000c911  mov     dword ptr [rbp+var_28+8], r12d
0x18000c915  mov     ecx, [rax]; this
0x18000c917  mov     dword ptr [rbp+var_28+4], ecx
0x18000c91a  test    r15, r15
0x18000c91d  jnz     short loc_18000C932
0x18000c91f  lea     r15, [rbp+var_40]
0x18000c923  test    rbx, rbx
0x18000c926  jnz     short loc_18000C92C
0x18000c928  mov     rbx, [r8+18h]
0x18000c92c  mov     eax, [rbx+4]
0x18000c92f  mov     dword ptr [rbp+var_40+4], eax
0x18000c932  mov     r8, r15; struct _AUI_CIPHER_INFO *
0x18000c935  mov     rdx, r14; struct _AUI_AUTH_INFO *
0x18000c938  call    ?NeedsKey@CACSecurityPage@@AEAAHPEAU_AUI_AUTH_INFO@@PEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::NeedsKey(_AUI_AUTH_INFO *,_AUI_CIPHER_INFO *)
0x18000c93d  cmp     dword ptr [rdi+5Ch], 0
0x18000c941  mov     r12d, eax
0x18000c944  mov     ebx, [r14+8]
0x18000c948  jnz     short loc_18000C9BE
0x18000c94a  mov     rcx, [rdi+8]; hDlg
0x18000c94e  mov     edx, 456h; nIDDlgItem
0x18000c953  call    cs:__imp_GetDlgItem
0x18000c959  mov     r13d, 1
0x18000c95f  mov     rcx, rax; hWnd
0x18000c962  mov     edx, r13d; bEnable
0x18000c965  call    cs:__imp_EnableWindow
0x18000c96b  mov     rcx, [rdi+8]; hDlg
0x18000c96f  mov     edx, 457h; nIDDlgItem
0x18000c974  call    cs:__imp_GetDlgItem
0x18000c97a  mov     rcx, rax; hWnd
0x18000c97d  mov     edx, r13d; bEnable
0x18000c980  call    cs:__imp_EnableWindow
0x18000c986  mov     rcx, [rdi+8]; hDlg
0x18000c98a  mov     edx, 458h; nIDDlgItem
0x18000c98f  call    cs:__imp_GetDlgItem
0x18000c995  mov     rcx, rax; hWnd
0x18000c998  mov     edx, r13d; bEnable
0x18000c99b  call    cs:__imp_EnableWindow
0x18000c9a1  mov     rcx, [rdi+8]; hDlg
0x18000c9a5  mov     edx, 459h; nIDDlgItem
0x18000c9aa  call    cs:__imp_GetDlgItem
0x18000c9b0  mov     rcx, rax; hWnd
0x18000c9b3  mov     edx, r13d; bEnable
0x18000c9b6  call    cs:__imp_EnableWindow
0x18000c9bc  jmp     short loc_18000C9C4
0x18000c9be  mov     r13d, 1
0x18000c9c4  mov     rcx, [rdi+538h]; this
0x18000c9cb  test    ebx, ebx
0x18000c9cd  jnz     short loc_18000C9E8
0x18000c9cf  xor     edx, edx; int
0x18000c9d1  xor     esi, esi
0x18000c9d3  call    ?EnableControls@EapControls@@QEAAXH@Z; EapControls::EnableControls(int)
0x18000c9d8  mov     rcx, [rdi+538h]; this
0x18000c9df  xor     edx, edx; int
0x18000c9e1  call    ?ShowControls@EapControls@@QEAAXH@Z; EapControls::ShowControls(int)
0x18000c9e6  jmp     short loc_18000CA15
0x18000c9e8  call    ?InitOneXUIControls@EapControls@@QEAAJXZ; EapControls::InitOneXUIControls(void)
0x18000c9ed  mov     rcx, [rdi+538h]; this
0x18000c9f4  mov     edx, r13d; int
0x18000c9f7  mov     esi, eax
0x18000c9f9  call    ?EnableControls@EapControls@@QEAAXH@Z; EapControls::EnableControls(int)
0x18000c9fe  mov     rcx, [rdi+538h]; this
0x18000ca05  mov     edx, r13d; int
0x18000ca08  call    ?ShowControls@EapControls@@QEAAXH@Z; EapControls::ShowControls(int)
0x18000ca0d  test    esi, esi
0x18000ca0f  js      loc_18000CD09
0x18000ca15  mov     rcx, [rdi+530h]; this
0x18000ca1c  xor     edx, edx
0x18000ca1e  test    r12d, r12d
0x18000ca21  setnz   dl; int
0x18000ca24  call    ?ShowControls@NetworkKeyControls@@QEAAXH@Z; NetworkKeyControls::ShowControls(int)
0x18000ca29  mov     rcx, rdi; this
0x18000ca2c  call    ?ShowIHVConfigureButton@CACSecurityPage@@AEAAHXZ; CACSecurityPage::ShowIHVConfigureButton(void)
0x18000ca31  mov     rcx, [rdi+8]; hDlg
0x18000ca35  mov     r12d, 464h
0x18000ca3b  mov     edx, r12d; nIDDlgItem
0x18000ca3e  mov     ebx, eax
0x18000ca40  call    cs:__imp_GetDlgItem
0x18000ca46  mov     rcx, rax; hWnd
0x18000ca49  mov     edx, ebx; bEnable
0x18000ca4b  call    cs:__imp_EnableWindow
0x18000ca51  mov     rcx, rdi; this
0x18000ca54  call    ?ShowIHVConfigureButton@CACSecurityPage@@AEAAHXZ; CACSecurityPage::ShowIHVConfigureButton(void)
0x18000ca59  mov     rcx, [rdi+8]; hDlg
0x18000ca5d  mov     edx, r12d; nIDDlgItem
0x18000ca60  mov     ebx, eax
0x18000ca62  call    cs:__imp_GetDlgItem
0x18000ca68  mov     rcx, rax; hWnd
0x18000ca6b  mov     edx, ebx; nCmdShow
0x18000ca6d  call    cs:__imp_ShowWindow
0x18000ca73  mov     rcx, rdi; this
0x18000ca76  call    ?ShowAddlSettingButton@CACSecurityPage@@AEAAHXZ; CACSecurityPage::ShowAddlSettingButton(void)
0x18000ca7b  mov     rcx, [rdi+50h]; hWnd
0x18000ca7f  mov     edx, eax; bEnable
0x18000ca81  call    cs:__imp_EnableWindow
0x18000ca87  mov     rcx, rdi; this
0x18000ca8a  call    ?ShowAddlSettingButton@CACSecurityPage@@AEAAHXZ; CACSecurityPage::ShowAddlSettingButton(void)
0x18000ca8f  mov     rcx, [rdi+50h]; hWnd
0x18000ca93  mov     edx, eax; nCmdShow
0x18000ca95  call    cs:__imp_ShowWindow
0x18000ca9b  xor     r12d, r12d
0x18000ca9e  mov     eax, r12d
0x18000caa1  cmp     [r14+0Ch], r12d
0x18000caa5  jz      short loc_18000CAAE
0x18000caa7  cmp     [r14], r12d
0x18000caaa  cmovz   eax, r13d
0x18000caae  test    r15, r15
0x18000cab1  jz      short loc_18000CABC
0x18000cab3  cmp     [r15], r12d
0x18000cab6  jz      loc_18000CB4D
0x18000cabc  test    eax, eax
0x18000cabe  jnz     loc_18000CB4D
0x18000cac4  mov     eax, [r14+4]
0x18000cac8  cmp     eax, 9
0x18000cacb  ja      short loc_18000CAEE
0x18000cacd  mov     ecx, 290h
0x18000cad2  bt      ecx, eax
0x18000cad5  jnb     short loc_18000CAEE
0x18000cad7  mov     rcx, [rdi+8]; hDlg
0x18000cadb  mov     edx, 45Bh; nIDDlgItem
0x18000cae0  call    cs:__imp_GetDlgItem
0x18000cae6  mov     r14d, 40h ; '@'
0x18000caec  jmp     short loc_18000CB17
0x18000caee  cmp     eax, r13d
0x18000caf1  jnz     short loc_18000CAFD
0x18000caf3  cmp     dword ptr [r15+4], 101h
0x18000cafb  jz      short loc_18000CB02
0x18000cafd  cmp     eax, 2
0x18000cb00  jnz     short loc_18000CB4D
0x18000cb02  mov     rcx, [rdi+8]; hDlg
0x18000cb06  mov     edx, 45Bh; nIDDlgItem
0x18000cb0b  call    cs:__imp_GetDlgItem
0x18000cb11  mov     r14d, 1Ah
0x18000cb17  mov     ebx, 0C5h
0x18000cb1c  xor     r9d, r9d; lParam
0x18000cb1f  mov     edx, ebx; Msg
0x18000cb21  mov     r8, r14; wParam
0x18000cb24  mov     rcx, rax; hWnd
0x18000cb27  call    cs:__imp_SendMessageW
0x18000cb2d  mov     rcx, [rdi+8]; hDlg
0x18000cb31  mov     edx, 45Ch; nIDDlgItem
0x18000cb36  call    cs:__imp_GetDlgItem
0x18000cb3c  xor     r9d, r9d; lParam
0x18000cb3f  mov     r8, r14; wParam
0x18000cb42  mov     rcx, rax; hWnd
0x18000cb45  mov     edx, ebx; Msg
0x18000cb47  call    cs:__imp_SendMessageW
0x18000cb4d  mov     rcx, [rdi+8]; hDlg
0x18000cb51  mov     edx, 46Bh; nIDDlgItem
0x18000cb56  call    cs:__imp_GetDlgItem
0x18000cb5c  mov     rcx, rax; hWnd
0x18000cb5f  xor     edx, edx; nCmdShow
0x18000cb61  call    cs:__imp_ShowWindow
0x18000cb67  mov     rcx, [rdi+8]; hDlg
0x18000cb6b  mov     edx, 46Ch; nIDDlgItem
0x18000cb70  call    cs:__imp_GetDlgItem
0x18000cb76  mov     rcx, rax; hWnd
0x18000cb79  xor     edx, edx; nCmdShow
0x18000cb7b  call    cs:__imp_ShowWindow
0x18000cb81  mov     rcx, [rdi+8]; hDlg
0x18000cb85  mov     r13d, 46Ah
0x18000cb8b  mov     edx, r13d; nIDDlgItem
0x18000cb8e  call    cs:__imp_GetDlgItem
0x18000cb94  mov     rcx, rax; hWnd
0x18000cb97  xor     edx, edx; nCmdShow
0x18000cb99  call    cs:__imp_ShowWindow
0x18000cb9f  mov     rax, [rdi+548h]
0x18000cba6  test    rax, rax
0x18000cba9  jz      short loc_18000CBBE
0x18000cbab  mov     rax, [rax+18h]
0x18000cbaf  test    rax, rax
0x18000cbb2  jz      short loc_18000CBBE
0x18000cbb4  cmp     [rax+6Ch], r12d
0x18000cbb8  jnz     loc_18000CD0C
0x18000cbbe  mov     rcx, [rdi+8]; hDlg
0x18000cbc2  mov     r14d, 45Fh
0x18000cbc8  mov     edx, r14d; nIDDlgItem
0x18000cbcb  mov     r15, r12
0x18000cbce  call    cs:__imp_GetDlgItem
0x18000cbd4  mov     rcx, rax; hWnd
0x18000cbd7  call    cs:__imp_IsWindowEnabled
0x18000cbdd  test    eax, eax
0x18000cbdf  jz      short loc_18000CC1F
0x18000cbe1  mov     rcx, [rdi+8]; hDlg
0x18000cbe5  mov     edx, r14d; nIDDlgItem
0x18000cbe8  call    cs:__imp_GetDlgItem
0x18000cbee  xor     r9d, r9d; lParam
0x18000cbf1  xor     r8d, r8d; wParam
0x18000cbf4  mov     rcx, rax; hWnd
0x18000cbf7  mov     edx, 147h; Msg
0x18000cbfc  call    cs:__imp_SendMessageW
0x18000cc02  mov     rcx, [rdi+8]; hDlg
0x18000cc06  mov     edx, r14d; nIDDlgItem
0x18000cc09  mov     rbx, rax
0x18000cc0c  call    cs:__imp_GetDlgItem
0x18000cc12  mov     rcx, rax; HWND
0x18000cc15  mov     edx, ebx; int
0x18000cc17  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000cc1c  mov     r15, rax
0x18000cc1f  mov     r14, [rdi+548h]
0x18000cc26  test    r14, r14
0x18000cc29  jz      short loc_18000CC4E
0x18000cc2b  mov     r8, [r14+18h]
0x18000cc2f  test    r8, r8
0x18000cc32  jz      short loc_18000CC4E
0x18000cc34  cmp     [r8+58h], r12d
0x18000cc38  jz      short loc_18000CC4E
0x18000cc3a  mov     r8, [r8+50h]; struct _AUI_EAP_METHOD_INFO *
0x18000cc3e  mov     rdx, r15; struct _AUI_EAP_METHOD_INFO *
0x18000cc41  call    ?AreEAPMethodDiffer@CACSecurityPage@@AEAAHPEAU_AUI_EAP_METHOD_INFO@@0@Z; CACSecurityPage::AreEAPMethodDiffer(_AUI_EAP_METHOD_INFO *,_AUI_EAP_METHOD_INFO *)
0x18000cc46  test    eax, eax
0x18000cc48  jz      loc_18000CD0C
0x18000cc4e  mov     rbx, [rdi+4E0h]
0x18000cc55  test    rbx, rbx
0x18000cc58  jz      short loc_18000CC7A
0x18000cc5a  test    byte ptr [rbx], 2
0x18000cc5d  jz      short loc_18000CC7A
0x18000cc5f  mov     r8, [rdi+538h]
0x18000cc66  mov     rdx, r15; struct _AUI_EAP_METHOD_INFO *
0x18000cc69  mov     r8, [r8+30h]; struct _AUI_EAP_METHOD_INFO *
0x18000cc6d  call    ?AreEAPMethodDiffer@CACSecurityPage@@AEAAHPEAU_AUI_EAP_METHOD_INFO@@0@Z; CACSecurityPage::AreEAPMethodDiffer(_AUI_EAP_METHOD_INFO *,_AUI_EAP_METHOD_INFO *)
0x18000cc72  test    eax, eax
0x18000cc74  jz      loc_18000CD0C
0x18000cc7a  test    r14, r14
0x18000cc7d  jz      short loc_18000CCD7
0x18000cc7f  mov     r8, [r14+18h]
0x18000cc83  test    r8, r8
0x18000cc86  jz      short loc_18000CCD7
0x18000cc88  cmp     [r8+58h], r12d
0x18000cc8c  jz      short loc_18000CCD7
0x18000cc8e  mov     r8, [r8+50h]; struct _AUI_EAP_METHOD_INFO *
0x18000cc92  mov     rdx, r15; struct _AUI_EAP_METHOD_INFO *
0x18000cc95  call    ?AreEAPMethodDiffer@CACSecurityPage@@AEAAHPEAU_AUI_EAP_METHOD_INFO@@0@Z; CACSecurityPage::AreEAPMethodDiffer(_AUI_EAP_METHOD_INFO *,_AUI_EAP_METHOD_INFO *)
0x18000cc9a  test    eax, eax
  ... truncated ...
```
