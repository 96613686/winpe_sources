# CACSecurityPage::OnApply(int,tagNMHDR *,int &)

- ea: `0x180009380`
- end: `0x180009be3`
- name: `?OnApply@CACSecurityPage@@QEAA_JHPEAUtagNMHDR@@AEAH@Z`
- size: `2147`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, int, struct tagNMHDR *, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x1800060a0`
- `0x180006134`
- `0x180006f98`
- `0x180007010`
- `0x180007df0`
- `0x180007f60`
- `0x1800082f8`
- `0x18000833c`
- `0x180008388`
- `0x180008498`
- `0x180009278`
- `0x1800092d0`
- `0x180009380`
- `0x180009bec`
- `0x18000cdc4`
- `0x180011188`
- `0x1800119c8`
- `0x180012af8`
- `0x180012d1c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000946e`
- `KERNEL32!HeapAlloc` at `0x1800099dc`
- `KERNEL32!HeapAlloc` at `0x1800099fe`
- `KERNEL32!HeapAlloc` at `0x18000946e`
- `KERNEL32!HeapAlloc` at `0x1800099dc`
- `KERNEL32!HeapAlloc` at `0x1800099fe`
- `KERNEL32!GetProcessHeap` at `0x18000945d`
- `KERNEL32!GetProcessHeap` at `0x1800097f2`
- `KERNEL32!GetProcessHeap` at `0x1800099b6`
- `KERNEL32!GetProcessHeap` at `0x1800099ca`
- `KERNEL32!GetProcessHeap` at `0x1800099ec`
- `KERNEL32!GetProcessHeap` at `0x180009bae`
- `KERNEL32!GetProcessHeap` at `0x18000945d`
- `KERNEL32!GetProcessHeap` at `0x1800097f2`
- `KERNEL32!GetProcessHeap` at `0x1800099b6`
- `KERNEL32!GetProcessHeap` at `0x1800099ca`
- `KERNEL32!GetProcessHeap` at `0x1800099ec`
- `KERNEL32!GetProcessHeap` at `0x180009bae`
- `KERNEL32!HeapFree` at `0x180009800`
- `KERNEL32!HeapFree` at `0x1800099c4`
- `KERNEL32!HeapFree` at `0x180009bbc`
- `KERNEL32!HeapFree` at `0x180009800`
- `KERNEL32!HeapFree` at `0x1800099c4`
- `KERNEL32!HeapFree` at `0x180009bbc`
- `USER32!GetWindowTextW` at `0x18000949c`
- `USER32!GetWindowTextW` at `0x18000949c`
- `USER32!GetWindowTextLengthW` at `0x18000944c`
- `USER32!GetWindowTextLengthW` at `0x18000944c`
- `USER32!IsWindowEnabled` at `0x180009569`
- `USER32!IsWindowEnabled` at `0x180009569`
- `USER32!GetDlgItem` at `0x180009560`
- `USER32!GetDlgItem` at `0x18000957a`
- `USER32!GetDlgItem` at `0x18000959e`
- `USER32!GetDlgItem` at `0x180009639`
- `USER32!GetDlgItem` at `0x18000965d`
- `USER32!GetDlgItem` at `0x180009560`
- `USER32!GetDlgItem` at `0x18000957a`
- `USER32!GetDlgItem` at `0x18000959e`
- `USER32!GetDlgItem` at `0x180009639`
- `USER32!GetDlgItem` at `0x18000965d`
- `USER32!SendMessageW` at `0x18000958e`
- `USER32!SendMessageW` at `0x18000964d`
- `USER32!SendMessageW` at `0x180009937`
- `USER32!SendMessageW` at `0x180009958`
- `USER32!SendMessageW` at `0x18000958e`
- `USER32!SendMessageW` at `0x18000964d`
- `USER32!SendMessageW` at `0x180009937`
- `USER32!SendMessageW` at `0x180009958`
- `wlanapi!WpFreeMemory` at `0x1800098e0`
- `wlanapi!WpFreeMemory` at `0x180009b76`
- `wlanapi!WpFreeMemory` at `0x1800098e0`
- `wlanapi!WpFreeMemory` at `0x180009b76`
- `wlanapi!WpAllocMemory` at `0x1800094f7`
- `wlanapi!WpAllocMemory` at `0x1800094f7`
- `wlanapi!ConvertPassPhraseKeyStringToBuffer` at `0x1800094dc`
- `wlanapi!ConvertPassPhraseKeyStringToBuffer` at `0x180009543`
- `wlanapi!ConvertPassPhraseKeyStringToBuffer` at `0x1800094dc`
- `wlanapi!ConvertPassPhraseKeyStringToBuffer` at `0x180009543`
- `wlanapi!MSMSecProfileValidForSafeMode` at `0x180009a79`
- `wlanapi!MSMSecProfileValidForSafeMode` at `0x180009a79`
- `OLEAUT32!__imp_SysFreeString` at `0x18000973f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000974e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000973f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000974e`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnApply(CACSecurityPage *this, __int64 a2, struct tagNMHDR *a3, int *a4)
{
  signed int v4; // edi
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // r15
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rax
  CACSecurityPage *v8; // rcx
  __int64 v9; // r8
  struct _AUI_CIPHER_INFO *v10; // r13
  BOOL v11; // eax
  __int64 v12; // r10
  unsigned int v13; // r12d
  __int64 v14; // r10
  HANDLE ProcessHeap; // rax
  void *v16; // rax
  LPVOID v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rbx
  signed int v21; // eax
  __int64 v22; // r8
  unsigned int v23; // ebx
  HWND v24; // rax
  HWND v25; // rax
  int v26; // ebx
  HWND v27; // rax
  __int64 v28; // rdx
  BOOL v29; // eax
  __int64 v30; // rcx
  __int64 v31; // r14
  BOOL v32; // eax
  BSTR v33; // rcx
  HWND DlgItem; // rax
  int v35; // ebx
  HWND v36; // rax
  BOOL v37; // eax
  __int64 v38; // r12
  IHVExtHelper *v39; // r12
  unsigned int v40; // ebx
  unsigned __int16 *CurrentIHVSecurityProfile; // r13
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // rax
  __int64 v43; // r12
  __int64 v44; // rbx
  __int64 v45; // rax
  _BYTE *v46; // rcx
  __int64 v47; // rdx
  void *v48; // rbx
  HANDLE v49; // rax
  __int64 v50; // rbx
  OneXControls *v51; // rcx
  SSOControls *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rcx
  BOOL v56; // eax
  __int64 v57; // rbx
  _DWORD *v58; // rdi
  HANDLE v59; // rax
  HANDLE v60; // rax
  _DWORD *v61; // rax
  HANDLE v62; // rax
  int v63; // eax
  int v64; // r8d
  unsigned int v65; // edx
  __int64 v66; // r10
  int v67; // eax
  FastRoamingControls *v68; // rcx
  _DWORD *v69; // r11
  unsigned int v70; // eax
  int v71; // ecx
  void *v72; // rbx
  HANDLE v73; // rax
  unsigned int v75; // [rsp+40h] [rbp-40h]
  int v76; // [rsp+44h] [rbp-3Ch] BYREF
  int v77; // [rsp+48h] [rbp-38h]
  int v78; // [rsp+4Ch] [rbp-34h] BYREF
  struct _AUI_EAP_METHOD_INFO *ItemDataPtr; // [rsp+50h] [rbp-30h]
  LPVOID lpMem; // [rsp+58h] [rbp-28h]
  BSTR bstrString; // [rsp+60h] [rbp-20h] BYREF
  __int64 v82; // [rsp+68h] [rbp-18h]
  __int64 v83; // [rsp+70h] [rbp-10h]
  struct _AUI_CIPHER_INFO *v84; // [rsp+78h] [rbp-8h]
  unsigned int WindowTextLengthW; // [rsp+C8h] [rbp+48h]
  unsigned int v86; // [rsp+D0h] [rbp+50h] BYREF
  int v87; // [rsp+D4h] [rbp+54h]
  unsigned int v88; // [rsp+D8h] [rbp+58h]

  v87 = HIDWORD(a3);
  v4 = 0;
  *a4 = 1;
  lpMem = 0;
  v86 = 0;
  v76 = 0;
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
  v84 = CurrentlySelectedCipher;
  v10 = CurrentlySelectedCipher;
  if ( !CurrentlySelectedAuth || !CurrentlySelectedCipher )
  {
    if ( *((_DWORD *)this + 23) )
      goto LABEL_134;
    CACSecurityPage::DisplayErrorMessage(this, 0x43A2u, 0);
    LOWORD(v4) = 87;
    goto LABEL_133;
  }
  v77 = 0;
  v11 = 0;
  WindowTextLengthW = 0;
  v82 = 0;
  ItemDataPtr = 0;
  if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
    v11 = *(_DWORD *)CurrentlySelectedAuth == 0;
  if ( !*(_DWORD *)v10 || v11 )
  {
    v75 = 0;
    v88 = 0;
    if ( *((_DWORD *)CurrentlySelectedAuth + 2) )
    {
      DlgItem = GetDlgItem(*((HWND *)this + 1), 1119);
      v35 = SendMessageW(DlgItem, 0x147u, 0, 0);
      v36 = GetDlgItem(*((HWND *)this + 1), 1119);
      ItemDataPtr = (struct _AUI_EAP_METHOD_INFO *)ComboBox_GetItemDataPtr(v36, v35);
    }
  }
  else
  {
    v12 = *((_QWORD *)this + 166);
    v13 = *((_DWORD *)v10 + 1);
    v75 = *((_DWORD *)CurrentlySelectedAuth + 1);
    v88 = v13;
    if ( *(_DWORD *)(v12 + 68) && (unsigned int)CACSecurityPage::NeedsKey(v8, CurrentlySelectedAuth, v10) )
    {
      WindowTextLengthW = GetWindowTextLengthW(*(HWND *)(v14 + 40));
      ProcessHeap = GetProcessHeap();
      v16 = HeapAlloc(ProcessHeap, 8u, 2LL * (WindowTextLengthW + 1));
      lpMem = v16;
      v17 = v16;
      if ( !v16 )
      {
        LOWORD(v4) = 8;
        goto LABEL_133;
      }
      v18 = *((_QWORD *)this + 166);
      v77 = 1;
      GetWindowTextW(*(HWND *)(v18 + 40), (LPWSTR)v16, WindowTextLengthW + 1);
      v20 = (unsigned int)CACSecurityPage::AUIAuth2Auth(v19, v75);
      v21 = ConvertPassPhraseKeyStringToBuffer(v17, WindowTextLengthW, v20, v13, 0, &v86, &v76, 0);
      v4 = 0;
      if ( v21 != 234 )
        v4 = v21;
      if ( v4 )
        goto LABEL_120;
      v82 = WpAllocMemory(v86);
      if ( !v82 )
      {
        LOWORD(v4) = 14;
LABEL_133:
        v4 = (unsigned __int16)v4 | 0x80070000;
        goto LABEL_134;
      }
      v22 = (unsigned int)v20;
      v23 = WindowTextLengthW;
      v17 = lpMem;
      v4 = ConvertPassPhraseKeyStringToBuffer(lpMem, WindowTextLengthW, v22, v13, v82, &v86, &v76, 0);
      if ( v4 )
        goto LABEL_121;
    }
    v24 = GetDlgItem(*((HWND *)this + 1), 1119);
    if ( IsWindowEnabled(v24) )
    {
      v25 = GetDlgItem(*((HWND *)this + 1), 1119);
      v26 = SendMessageW(v25, 0x147u, 0, 0);
      v27 = GetDlgItem(*((HWND *)this + 1), 1119);
      ItemDataPtr = (struct _AUI_EAP_METHOD_INFO *)ComboBox_GetItemDataPtr(v27, v26);
    }
  }
  v28 = *(_QWORD *)(*((_QWORD *)this + 5) + 552LL);
  v29 = 0;
  v83 = v28;
  v30 = *(_QWORD *)(v28 + 32);
  v31 = *(_QWORD *)(v30 + 424);
  if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
    v29 = *(_DWORD *)CurrentlySelectedAuth == 0;
  if ( !*(_DWORD *)v10 )
    v29 = 1;
  *(_DWORD *)(v30 + 432) = v29;
  v32 = 0;
  if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
    v32 = *(_DWORD *)CurrentlySelectedAuth == 0;
  v33 = (BSTR)((!*(_DWORD *)v10 || v32) && *((_DWORD *)CurrentlySelectedAuth + 2));
  *(_DWORD *)(*(_QWORD *)(v28 + 32) + 436LL) = (_DWORD)v33;
  v37 = 0;
  if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
    v37 = *(_DWORD *)CurrentlySelectedAuth == 0;
  if ( *(_DWORD *)v10 && !v37 )
  {
    v43 = v28;
  }
  else
  {
    v38 = *((_QWORD *)this + 154);
    bstrString = 0;
    v78 = 0;
    if ( !v38
      || (v39 = *(IHVExtHelper **)((*(_DWORD *)(*(_QWORD *)(v28 + 32) + 436LL) != 0 ? 8 : 0) + v38 + 32)) == 0
      || !*((_DWORD *)v39 + 2) )
    {
      v4 = 1003;
      goto LABEL_127;
    }
    v40 = *((_DWORD *)CurrentlySelectedAuth + 4);
    CurrentIHVSecurityProfile = CACSecurityPage::GetCurrentIHVSecurityProfile(this);
    UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams(this);
    if ( (int)IHVExtHelper::IHVExtHlpSetSelected(
                v39,
                CurrentIHVSecurityProfile,
                UpdatedIHVParams,
                &bstrString,
                &v78,
                v40) >= 0
      && v78 )
    {
      CACSecurityPage::SetNewIHVSecurityProfileData(this, bstrString);
    }
    if ( CurrentIHVSecurityProfile )
      SysFreeString(CurrentIHVSecurityProfile);
    v33 = bstrString;
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    v43 = v83;
    if ( !*(_DWORD *)(*(_QWORD *)(v83 + 32) + 436LL) )
      goto LABEL_119;
    v10 = v84;
  }
  v44 = *((_QWORD *)this + 156);
  if ( v44
    && (*(_BYTE *)v44 & 2) != 0
    && (!*((_DWORD *)CurrentlySelectedAuth + 2)
     || (unsigned int)CACSecurityPage::AreEAPMethodDiffer(
                        (CACSecurityPage *)v33,
                        ItemDataPtr,
                        *(struct _AUI_EAP_METHOD_INFO **)(*((_QWORD *)this + 167) + 48LL))) )
  {
    v9 = 1;
    *(_DWORD *)(v44 + 4) = 1;
    v45 = *((_QWORD *)this + 156);
    v46 = *(_BYTE **)(v45 + 48);
    if ( v46 )
    {
      v47 = ((2580 * *(_DWORD *)(v45 + 40)) & 0xFFFFFFF0) + 16;
      if ( ((2580 * *(_DWORD *)(v45 + 40)) & 0xFFFFFFF0) != 0xFFFFFFF0 )
      {
        do
        {
          *v46++ = 0;
          --v47;
        }
        while ( v47 );
      }
      v48 = *(void **)(*((_QWORD *)this + 156) + 48LL);
      v49 = GetProcessHeap();
      HeapFree(v49, 0, v48);
    }
    *(_QWORD *)(*((_QWORD *)this + 156) + 48LL) = 0;
    *(_DWORD *)(*((_QWORD *)this + 156) + 40LL) = 0;
  }
  v50 = *((_QWORD *)this + 169);
  if ( v50 && *((_DWORD *)CurrentlySelectedAuth + 2) && !*(_DWORD *)(v50 + 40) )
  {
    if ( *(_DWORD *)(v50 + 56) )
    {
      v51 = *(OneXControls **)(v50 + 24);
      if ( v51 )
LABEL_67:
        OneXControls::CommitAdditionalSettings(v51, ItemDataPtr, *(struct _AUI_CREDS_INFO **)(v50 + 96));
    }
    else
    {
      v52 = *(SSOControls **)(v50 + 16);
      if ( !v52 || (int)SSOControls::CommitAdditionalSettings(v52) >= 0 )
      {
        v51 = *(OneXControls **)(v50 + 24);
        if ( v51 )
          goto LABEL_67;
      }
    }
  }
  v53 = *((_QWORD *)this + 156);
  if ( v53 && *(_DWORD *)(v53 + 4) && !*(_DWORD *)(v53 + 40) && !*(_QWORD *)(v53 + 48) )
    *(_OWORD *)(v53 + 8) = *(_OWORD *)**(_QWORD **)(*((_QWORD *)this + 167) + 48LL);
  if ( v77 )
  {
    *(_DWORD *)v31 = *(_DWORD *)v31 & 0xFFFFFFFC | (2 * (v76 & 1));
    v54 = *(_QWORD *)(v31 + 72);
    *(_DWORD *)(v31 + 64) = v86;
    if ( v54 )
      WpFreeMemory(v54);
    *(_QWORD *)(v31 + 72) = v82;
  }
  if ( !*((_DWORD *)this + 23) )
  {
    if ( (unsigned int)NetworkKeyControls::NeedsKeyIndex(*((NetworkKeyControls **)this + 166)) )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 166) + 72LL) )
      {
        *(_DWORD *)v31 &= ~4u;
        if ( (unsigned int)SendMessageW(*(HWND *)(*((_QWORD *)this + 166) + 56LL), 0x147u, 0, 0) )
        {
          *(_DWORD *)v31 |= 4u;
          *(_DWORD *)(v31 + 56) = SendMessageW(*(HWND *)(*((_QWORD *)this + 166) + 56LL), 0x147u, 0, 0);
        }
      }
    }
    else
    {
      *(_DWORD *)v31 &= ~4u;
    }
    *(_DWORD *)(v31 + 32) = *((_DWORD *)CurrentlySelectedAuth + 2);
    v56 = 0;
    if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
      v56 = *(_DWORD *)CurrentlySelectedAuth == 0;
    if ( !*(_DWORD *)v10 || v56 )
    {
LABEL_102:
      v4 = EapControls::OnApply(
             *((EapControls **)this + 167),
             ItemDataPtr,
             (struct DOT11_MSMSEC_CONNECTION_PROFILE *)v31);
      if ( !v4 )
      {
        v66 = *((_QWORD *)this + 168);
        if ( !v66 )
          goto LABEL_111;
        v67 = *((_DWORD *)CurrentlySelectedAuth + 1);
        if ( v67 != 6 )
        {
          if ( v67 == 7 )
          {
LABEL_106:
            if ( *((_DWORD *)v10 + 1) == 4 )
              goto LABEL_107;
LABEL_111:
            v70 = *((_DWORD *)CurrentlySelectedAuth + 1);
            if ( v70 > 0xB || (v71 = 2368, !_bittest(&v71, v70)) )
              *(_DWORD *)v31 &= 0xFFFFFF07;
            v4 = 0;
            goto LABEL_134;
          }
          if ( v67 != 11 && v67 != 8 )
          {
            if ( v67 != 9 )
              goto LABEL_111;
            goto LABEL_106;
          }
        }
LABEL_107:
        if ( !*(_DWORD *)(v66 + 16) )
        {
          v68 = *(FastRoamingControls **)(v66 + 248);
          v69 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v66 + 40) + 552LL) + 32LL) + 424LL);
          if ( !v68 || (int)FastRoamingControls::CommitAdditionalSettings(v68) >= 0 )
            *v69 ^= (*v69 ^ (*(_DWORD *)(v66 + 60) << 12)) & 0x1000;
        }
        goto LABEL_111;
      }
      goto LABEL_119;
    }
    if ( *(_DWORD *)(v31 + 16) && (v57 = v31 + 24, (v58 = *(_DWORD **)(v31 + 24)) != 0) )
    {
      if ( *(_DWORD *)(v31 + 16) != 1 || v88 != 4 )
      {
LABEL_95:
        *(_DWORD *)(v31 + 16) = (v88 == 4) + 1;
        v63 = CACSecurityPage::AUIAuth2Auth(v55, v75);
        v65 = v88;
        *v58 = v63;
        *(_DWORD *)(*(_QWORD *)v57 + 4LL) = v65;
        if ( *(_DWORD *)(v31 + 16) == 2 )
        {
          *(_DWORD *)(*(_QWORD *)v57 + 8LL) = v63;
          if ( v65 == 4 )
            *(_DWORD *)(*(_QWORD *)v57 + 12LL) = 8;
          else
            *(_DWORD *)(v31 + 16) = v64;
        }
        if ( (*(_DWORD *)v31 & 0x1000) != 0
          && !(unsigned int)MSMSecProfileValidForSafeMode(v31, *(unsigned int *)(v43 + 16)) )
        {
          *(_DWORD *)v31 &= ~0x1000u;
        }
        goto LABEL_102;
      }
      *(_DWORD *)(v31 + 16) = 2;
      v59 = GetProcessHeap();
      HeapFree(v59, 0, v58);
      v60 = GetProcessHeap();
      v61 = HeapAlloc(v60, 8u, 0x10u);
    }
    else
    {
      *(_DWORD *)(v31 + 16) = 2;
      v62 = GetProcessHeap();
      v61 = HeapAlloc(v62, 8u, 0x10u);
      v57 = v31 + 24;
    }
    *(_QWORD *)v57 = v61;
    v58 = v61;
    if ( !v61 )
    {
      v4 = 8;
      goto LABEL_127;
    }
    goto LABEL_95;
  }
LABEL_119:
  v17 = lpMem;
LABEL_120:
  v23 = WindowTextLengthW;
LABEL_121:
  if ( v4 == 11 )
  {
    if ( v77 )
      CACSecurityPage::DisplayNetworkKeyErrorMessage(this, v75, v9, v17, v23);
  }
  else if ( !v4 )
  {
    goto LABEL_134;
  }
LABEL_127:
  if ( v82 )
    WpFreeMemory(v82);
  if ( v4 > 0 )
    goto LABEL_133;
LABEL_134:
  v72 = lpMem;
  if ( lpMem )
  {
    v73 = GetProcessHeap();
    HeapFree(v73, 0, v72);
  }
  return LresFromHr(v4);
}

```

## disassembly

```asm
0x180009380  mov     [rsp-38h+arg_0], rbx
0x180009385  mov     [rsp-38h+arg_10], r8
0x18000938a  mov     [rsp-38h+arg_8], edx
0x18000938e  push    rbp
0x18000938f  push    rsi
0x180009390  push    rdi
0x180009391  push    r12
0x180009393  push    r13
0x180009395  push    r14
0x180009397  push    r15
0x180009399  mov     rbp, rsp
0x18000939c  sub     rsp, 80h
0x1800093a3  xor     edi, edi
0x1800093a5  mov     r12d, 1
0x1800093ab  mov     [r9], r12d
0x1800093ae  mov     rsi, rcx
0x1800093b1  mov     [rbp+lpMem], rdi
0x1800093b5  mov     dword ptr [rbp+arg_10], edi
0x1800093b8  mov     [rbp+var_3C], edi
0x1800093bb  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x1800093c0  mov     rcx, rsi; this
0x1800093c3  mov     r15, rax
0x1800093c6  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x1800093cb  mov     [rbp+var_8], rax
0x1800093cf  mov     r13, rax
0x1800093d2  test    r15, r15
0x1800093d5  jz      loc_180009B82
0x1800093db  test    rax, rax
0x1800093de  jz      loc_180009B82
0x1800093e4  xor     ebx, ebx
0x1800093e6  mov     [rbp+var_38], edi
0x1800093e9  xor     eax, eax
0x1800093eb  mov     [rbp+arg_8], ebx
0x1800093ee  mov     [rbp+var_18], rbx
0x1800093f2  mov     [rbp+var_30], rbx
0x1800093f6  cmp     [r15+0Ch], eax
0x1800093fa  jz      short loc_180009403
0x1800093fc  cmp     [r15], eax
0x1800093ff  cmovz   eax, r12d
0x180009403  cmp     [r13+0], ebx
0x180009407  jz      loc_180009620
0x18000940d  test    eax, eax
0x18000940f  jnz     loc_180009620
0x180009415  mov     r10, [rsi+530h]
0x18000941c  mov     eax, [r15+4]
0x180009420  mov     r12d, [r13+4]
0x180009424  mov     [rbp+var_40], eax
0x180009427  mov     [rbp+arg_18], r12d
0x18000942b  cmp     [r10+44h], ebx
0x18000942f  jz      loc_180009553
0x180009435  mov     r8, r13; struct _AUI_CIPHER_INFO *
0x180009438  mov     rdx, r15; struct _AUI_AUTH_INFO *
0x18000943b  call    ?NeedsKey@CACSecurityPage@@AEAAHPEAU_AUI_AUTH_INFO@@PEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::NeedsKey(_AUI_AUTH_INFO *,_AUI_CIPHER_INFO *)
0x180009440  test    eax, eax
0x180009442  jz      loc_180009553
0x180009448  mov     rcx, [r10+28h]; hWnd
0x18000944c  call    cs:__imp_GetWindowTextLengthW
0x180009452  mov     [rbp+arg_8], eax
0x180009455  lea     edi, [rax+1]
0x180009458  mov     ebx, edi
0x18000945a  add     rbx, rbx
0x18000945d  call    cs:__imp_GetProcessHeap
0x180009463  mov     r8, rbx; dwBytes
0x180009466  mov     edx, 8; dwFlags
0x18000946b  mov     rcx, rax; hHeap
0x18000946e  call    cs:__imp_HeapAlloc
0x180009474  mov     [rbp+lpMem], rax
0x180009478  mov     r14, rax
0x18000947b  test    rax, rax
0x18000947e  jz      loc_180009616
0x180009484  mov     rcx, [rsi+530h]
0x18000948b  mov     r8d, edi; nMaxCount
0x18000948e  mov     rdx, rax; lpString
0x180009491  mov     [rbp+var_38], 1
0x180009498  mov     rcx, [rcx+28h]; hWnd
0x18000949c  call    cs:__imp_GetWindowTextW
0x1800094a2  mov     edx, [rbp+var_40]
0x1800094a5  call    ?AUIAuth2Auth@CACSecurityPage@@AEAA?AW4_DOT11_AUTH_ALGORITHM@@W4AUI_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::AUIAuth2Auth(AUI_DOT11_AUTH_ALGORITHM)
0x1800094aa  mov     edx, [rbp+arg_8]
0x1800094ad  mov     ebx, eax
0x1800094af  mov     [rsp+80h+var_48], 0
0x1800094b8  lea     rax, [rbp+var_3C]
0x1800094bc  mov     [rsp+80h+var_50], rax
0x1800094c1  mov     r9d, r12d
0x1800094c4  lea     rax, [rbp+arg_10]
0x1800094c8  mov     r8d, ebx
0x1800094cb  mov     qword ptr [rsp+80h+var_58], rax
0x1800094d0  mov     rcx, r14
0x1800094d3  mov     [rsp+80h+var_60], 0
0x1800094dc  call    cs:__imp_ConvertPassPhraseKeyStringToBuffer
0x1800094e2  xor     edi, edi
0x1800094e4  cmp     eax, 0EAh
0x1800094e9  cmovnz  edi, eax
0x1800094ec  test    edi, edi
0x1800094ee  jnz     loc_180009B3D
0x1800094f4  mov     ecx, dword ptr [rbp+arg_10]
0x1800094f7  call    cs:__imp_WpAllocMemory
0x1800094fd  mov     [rbp+var_18], rax
0x180009501  mov     r14, rax
0x180009504  test    rax, rax
0x180009507  jnz     short loc_180009511
0x180009509  lea     edi, [rax+0Eh]
0x18000950c  jmp     loc_180009B9C
0x180009511  mov     [rsp+80h+var_48], 0
0x18000951a  lea     rax, [rbp+var_3C]
0x18000951e  mov     [rsp+80h+var_50], rax
0x180009523  mov     r8d, ebx
0x180009526  mov     ebx, [rbp+arg_8]
0x180009529  lea     rax, [rbp+arg_10]
0x18000952d  mov     qword ptr [rsp+80h+var_58], rax
0x180009532  mov     r9d, r12d
0x180009535  mov     [rsp+80h+var_60], r14
0x18000953a  mov     edx, ebx
0x18000953c  mov     r14, [rbp+lpMem]
0x180009540  mov     rcx, r14
0x180009543  call    cs:__imp_ConvertPassPhraseKeyStringToBuffer
0x180009549  mov     edi, eax
0x18000954b  test    eax, eax
0x18000954d  jnz     loc_180009B40
0x180009553  mov     rcx, [rsi+8]; hDlg
0x180009557  mov     r14d, 45Fh
0x18000955d  mov     edx, r14d; nIDDlgItem
0x180009560  call    cs:__imp_GetDlgItem
0x180009566  mov     rcx, rax; hWnd
0x180009569  call    cs:__imp_IsWindowEnabled
0x18000956f  test    eax, eax
0x180009571  jz      short loc_1800095B2
0x180009573  mov     rcx, [rsi+8]; hDlg
0x180009577  mov     edx, r14d; nIDDlgItem
0x18000957a  call    cs:__imp_GetDlgItem
0x180009580  xor     r9d, r9d; lParam
0x180009583  xor     r8d, r8d; wParam
0x180009586  mov     rcx, rax; hWnd
0x180009589  mov     edx, 147h; Msg
0x18000958e  call    cs:__imp_SendMessageW
0x180009594  mov     rcx, [rsi+8]; hDlg
0x180009598  mov     edx, r14d; nIDDlgItem
0x18000959b  mov     rbx, rax
0x18000959e  call    cs:__imp_GetDlgItem
0x1800095a4  mov     rcx, rax; HWND
0x1800095a7  mov     edx, ebx; int
0x1800095a9  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x1800095ae  mov     [rbp+var_30], rax
0x1800095b2  mov     r12d, 1
0x1800095b8  mov     rax, [rsi+28h]
0x1800095bc  mov     rdx, [rax+228h]
0x1800095c3  xor     eax, eax
0x1800095c5  mov     [rbp+var_10], rdx
0x1800095c9  mov     rcx, [rdx+20h]
0x1800095cd  mov     r14, [rcx+1A8h]
0x1800095d4  cmp     [r15+0Ch], eax
0x1800095d8  jz      short loc_1800095E1
0x1800095da  cmp     [r15], eax
0x1800095dd  cmovz   eax, r12d
0x1800095e1  cmp     dword ptr [r13+0], 0
0x1800095e6  cmovz   eax, r12d
0x1800095ea  mov     [rcx+1B0h], eax
0x1800095f0  xor     eax, eax
0x1800095f2  cmp     [r15+0Ch], eax
0x1800095f6  jz      short loc_1800095FF
0x1800095f8  cmp     [r15], eax
0x1800095fb  cmovz   eax, r12d
0x1800095ff  cmp     dword ptr [r13+0], 0
0x180009604  jz      short loc_18000960A
0x180009606  test    eax, eax
0x180009608  jz      short loc_180009676
0x18000960a  cmp     dword ptr [r15+8], 0
0x18000960f  jz      short loc_180009676
0x180009611  mov     ecx, r12d
0x180009614  jmp     short loc_180009678
0x180009616  mov     edi, 8
0x18000961b  jmp     loc_180009B9C
0x180009620  mov     [rbp+var_40], ebx
0x180009623  mov     [rbp+arg_18], ebx
0x180009626  cmp     [r15+8], ebx
0x18000962a  jz      short loc_1800095B8
0x18000962c  mov     rcx, [rsi+8]; hDlg
0x180009630  mov     r14d, 45Fh
0x180009636  mov     edx, r14d; nIDDlgItem
0x180009639  call    cs:__imp_GetDlgItem
0x18000963f  xor     r9d, r9d; lParam
0x180009642  xor     r8d, r8d; wParam
0x180009645  mov     rcx, rax; hWnd
0x180009648  mov     edx, 147h; Msg
0x18000964d  call    cs:__imp_SendMessageW
0x180009653  mov     rcx, [rsi+8]; hDlg
0x180009657  mov     edx, r14d; nIDDlgItem
0x18000965a  mov     rbx, rax
0x18000965d  call    cs:__imp_GetDlgItem
0x180009663  mov     rcx, rax; HWND
0x180009666  mov     edx, ebx; int
0x180009668  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000966d  mov     [rbp+var_30], rax
0x180009671  jmp     loc_1800095B8
0x180009676  xor     ecx, ecx; this
0x180009678  mov     rax, [rdx+20h]
0x18000967c  mov     [rax+1B4h], ecx
0x180009682  xor     eax, eax
0x180009684  cmp     [r15+0Ch], eax
0x180009688  jz      short loc_180009691
0x18000968a  cmp     [r15], eax
0x18000968d  cmovz   eax, r12d
0x180009691  cmp     dword ptr [r13+0], 0
0x180009696  jz      short loc_1800096A0
0x180009698  test    eax, eax
0x18000969a  jz      loc_180009778
0x1800096a0  mov     r12, [rsi+4D0h]
0x1800096a7  mov     [rbp+bstrString], 0
0x1800096af  mov     [rbp+var_34], 0
0x1800096b6  test    r12, r12
0x1800096b9  jz      loc_180009B65
0x1800096bf  mov     rax, [rdx+20h]
0x1800096c3  mov     ecx, [rax+1B4h]
0x1800096c9  neg     ecx
0x1800096cb  sbb     rax, rax
0x1800096ce  and     eax, 8
0x1800096d1  mov     r12, [rax+r12+20h]
0x1800096d6  test    r12, r12
0x1800096d9  jz      loc_180009B65
0x1800096df  cmp     dword ptr [r12+8], 0
0x1800096e5  jbe     loc_180009B65
0x1800096eb  mov     ebx, [r15+10h]
0x1800096ef  mov     rcx, rsi; this
0x1800096f2  call    ?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ; CACSecurityPage::GetCurrentIHVSecurityProfile(void)
0x1800096f7  mov     rcx, rsi; this
0x1800096fa  mov     r13, rax
0x1800096fd  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x180009702  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x180009705  mov     [rsp+80h+var_58], ebx; unsigned int
0x180009709  lea     rax, [rbp+var_34]
0x18000970d  mov     rdx, r13; unsigned __int16 *
0x180009710  lea     r9, [rbp+bstrString]; unsigned __int16 **
0x180009714  mov     [rsp+80h+var_60], rax; int *
0x180009719  mov     rcx, r12; this
0x18000971c  call    ?IHVExtHlpSetSelected@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@PEAPEAGPEAHK@Z; IHVExtHelper::IHVExtHlpSetSelected(ushort *,_DOT11EXT_IHV_PARAMS *,ushort * *,int *,ulong)
0x180009721  test    eax, eax
0x180009723  js      short loc_180009737
0x180009725  cmp     [rbp+var_34], 0
0x180009729  jz      short loc_180009737
0x18000972b  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18000972f  mov     rcx, rsi; this
0x180009732  call    ?SetNewIHVSecurityProfileData@CACSecurityPage@@AEAA_JPEAG@Z; CACSecurityPage::SetNewIHVSecurityProfileData(ushort *)
0x180009737  test    r13, r13
0x18000973a  jz      short loc_180009745
0x18000973c  mov     rcx, r13; bstrString
0x18000973f  call    cs:__imp_SysFreeString
0x180009745  mov     rcx, [rbp+bstrString]; bstrString
0x180009749  test    rcx, rcx
0x18000974c  jz      short loc_18000975C
0x18000974e  call    cs:__imp_SysFreeString
0x180009754  mov     [rbp+bstrString], 0
0x18000975c  mov     r12, [rbp+var_10]
0x180009760  mov     rax, [r12+20h]
0x180009765  cmp     dword ptr [rax+1B4h], 0
0x18000976c  jz      loc_180009B39
0x180009772  mov     r13, [rbp+var_8]
0x180009776  jmp     short loc_18000977B
0x180009778  mov     r12, rdx
0x18000977b  mov     rbx, [rsi+4E0h]
0x180009782  test    rbx, rbx
0x180009785  jz      loc_180009823
0x18000978b  test    byte ptr [rbx], 2
0x18000978e  jz      loc_180009823
0x180009794  cmp     dword ptr [r15+8], 0
0x180009799  jz      short loc_1800097B3
0x18000979b  mov     r8, [rsi+538h]
0x1800097a2  mov     rdx, [rbp+var_30]; struct _AUI_EAP_METHOD_INFO *
0x1800097a6  mov     r8, [r8+30h]; struct _AUI_EAP_METHOD_INFO *
0x1800097aa  call    ?AreEAPMethodDiffer@CACSecurityPage@@AEAAHPEAU_AUI_EAP_METHOD_INFO@@0@Z; CACSecurityPage::AreEAPMethodDiffer(_AUI_EAP_METHOD_INFO *,_AUI_EAP_METHOD_INFO *)
0x1800097af  test    eax, eax
0x1800097b1  jz      short loc_180009823
0x1800097b3  mov     r8d, 1
0x1800097b9  mov     [rbx+4], r8d
0x1800097bd  mov     rax, [rsi+4E0h]
0x1800097c4  mov     rcx, [rax+30h]
0x1800097c8  test    rcx, rcx
0x1800097cb  jz      short loc_180009806
0x1800097cd  imul    edx, [rax+28h], 0A14h
0x1800097d4  and     edx, 0FFFFFFF0h
0x1800097d7  add     edx, 10h
0x1800097da  jz      short loc_1800097E7
0x1800097dc  mov     byte ptr [rcx], 0
0x1800097df  add     rcx, r8
0x1800097e2  sub     rdx, r8
0x1800097e5  jnz     short loc_1800097DC
0x1800097e7  mov     rax, [rsi+4E0h]
0x1800097ee  mov     rbx, [rax+30h]
0x1800097f2  call    cs:__imp_GetProcessHeap
0x1800097f8  mov     r8, rbx; lpMem
0x1800097fb  xor     edx, edx; dwFlags
0x1800097fd  mov     rcx, rax; hHeap
0x180009800  call    cs:__imp_HeapFree
0x180009806  mov     rax, [rsi+4E0h]
0x18000980d  mov     qword ptr [rax+30h], 0
0x180009815  mov     rax, [rsi+4E0h]
0x18000981c  mov     dword ptr [rax+28h], 0
0x180009823  mov     rbx, [rsi+548h]
0x18000982a  test    rbx, rbx
0x18000982d  jz      short loc_180009882
0x18000982f  cmp     dword ptr [r15+8], 0
  ... truncated ...
```
