# CACSecurityPage::OnEncrSelection(ushort,ushort,HWND__ *,int &)

- ea: `0x18000a29c`
- end: `0x18000a4ab`
- name: `?OnEncrSelection@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `527`
- prototype: `__int64 __usercall@<rax>(CACSecurityPage *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x1800082f8`
- `0x18000833c`
- `0x180008388`
- `0x180008498`
- `0x18000a29c`
- `0x18000c824`
- `0x18000cdc4`
- `0x18000d714`
- `0x18000d834`
- `0x180010f64`
- `0x18001d010`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x18000a327`
- `USER32!IsWindowEnabled` at `0x18000a327`
- `USER32!IsWindowVisible` at `0x18000a30a`
- `USER32!IsWindowVisible` at `0x18000a30a`
- `USER32!GetDlgItem` at `0x18000a301`
- `USER32!GetDlgItem` at `0x18000a31e`
- `USER32!GetDlgItem` at `0x18000a301`
- `USER32!GetDlgItem` at `0x18000a31e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a459`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a46c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a459`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a46c`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnEncrSelection(HWND *this, __int16 a2, __int64 a3, HWND a4, int *a5)
{
  OLECHAR *CurrentIHVSecurityProfile; // r15
  HWND DlgItem; // rax
  HWND v9; // rax
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rbx
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rsi
  BOOL v12; // ecx
  int v13; // ebp
  bool v14; // cf
  int v15; // ebx
  __int64 v16; // r14
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // r12
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // ebp
  unsigned int v22; // r9d
  int v24; // [rsp+80h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  bstrString = 0;
  v24 = 0;
  CurrentIHVSecurityProfile = CACSecurityPage::GetCurrentIHVSecurityProfile((CACSecurityPage *)this);
  if ( a2 != 1 )
  {
    *a5 = 0;
    return 0;
  }
  DlgItem = GetDlgItem(this[1], 1112);
  if ( IsWindowVisible(DlgItem) )
  {
    v9 = GetDlgItem(this[1], 1112);
    if ( IsWindowEnabled(v9) )
    {
      CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
      CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher((CACSecurityPage *)this);
      if ( !CurrentlySelectedAuth )
        goto LABEL_25;
      v12 = 0;
      if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
        v12 = *(_DWORD *)CurrentlySelectedAuth == 0;
      if ( (!CurrentlySelectedCipher || *(_DWORD *)CurrentlySelectedCipher) && !v12 )
      {
LABEL_25:
        CACSecurityPage::UpdateMSProfileOnAuthEncr((CACSecurityPage *)this);
LABEL_26:
        CACSecurityPage::RefreshControls((CACSecurityPage *)this);
        *a5 = 1;
        return 0;
      }
      CACSecurityPage::UpdateIHVProfileOnAuthEncr((CACSecurityPage *)this);
      v13 = *((_DWORD *)CurrentlySelectedCipher + 1);
      v14 = *((_DWORD *)CurrentlySelectedAuth + 2) != 0;
      v15 = *((_DWORD *)CurrentlySelectedAuth + 4);
      v16 = *(_QWORD *)((char *)this[154] + (v14 ? 8 : 0) + 32);
      UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams((CACSecurityPage *)this);
      if ( v15 )
        v18 = (unsigned int)(v15 - *(_DWORD *)(v16 + 36));
      else
        v18 = 0;
      v19 = 0;
      v20 = *(_QWORD *)(*(_QWORD *)(v16 + 24) + 8 * v18);
      v21 = v13 - *(_DWORD *)(v20 + 24);
      if ( v21 < *(_DWORD *)(v20 + 16) )
        v19 = *(_QWORD *)(v20 + 8) + 16LL * v21;
      *(_DWORD *)(v20 + 20) = v21;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, OLECHAR *, struct _DOT11EXT_IHV_PARAMS *, __int64, BSTR *, int *))(**(_QWORD **)(*(_QWORD *)v16 + 8 * v18) + 72LL))(
             *(_QWORD *)(*(_QWORD *)v16 + 8 * v18),
             0,
             CurrentIHVSecurityProfile,
             UpdatedIHVParams,
             v19,
             &bstrString,
             &v24) >= 0 )
      {
        if ( !v24 )
        {
LABEL_21:
          if ( CurrentIHVSecurityProfile )
            SysFreeString(CurrentIHVSecurityProfile);
          if ( bstrString )
            SysFreeString(bstrString);
          goto LABEL_26;
        }
        v22 = *(_DWORD *)(v16 + 36);
        *(_DWORD *)(v16 + 32) = 1;
        IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo((IHVExtHelper *)v16, bstrString, UpdatedIHVParams, v22);
      }
      if ( v24 )
        CACSecurityPage::SetNewIHVSecurityProfileData((CACSecurityPage *)this, bstrString);
      goto LABEL_21;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a29c  mov     rax, rsp
0x18000a29f  mov     [rax+8], rbx
0x18000a2a3  mov     [rax+10h], rbp
0x18000a2a7  mov     [rax+20h], r9
0x18000a2ab  mov     [rax+18h], r8w
0x18000a2b0  push    rsi
0x18000a2b1  push    rdi
0x18000a2b2  push    r12
0x18000a2b4  push    r14
0x18000a2b6  push    r15
0x18000a2b8  sub     rsp, 40h
0x18000a2bc  movzx   ebx, dx
0x18000a2bf  mov     qword ptr [rax+20h], 0
0x18000a2c7  mov     rdi, rcx
0x18000a2ca  mov     dword ptr [rax+18h], 0
0x18000a2d1  call    ?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ; CACSecurityPage::GetCurrentIHVSecurityProfile(void)
0x18000a2d6  mov     r15, rax
0x18000a2d9  mov     eax, 1
0x18000a2de  cmp     bx, ax
0x18000a2e1  jz      short loc_18000A2F6
0x18000a2e3  mov     rax, [rsp+68h+arg_20]
0x18000a2eb  mov     dword ptr [rax], 0
0x18000a2f1  jmp     loc_18000A492
0x18000a2f6  mov     rcx, [rdi+8]; hDlg
0x18000a2fa  mov     ebx, 458h
0x18000a2ff  mov     edx, ebx; nIDDlgItem
0x18000a301  call    cs:__imp_GetDlgItem
0x18000a307  mov     rcx, rax; hWnd
0x18000a30a  call    cs:__imp_IsWindowVisible
0x18000a310  test    eax, eax
0x18000a312  jz      loc_18000A492
0x18000a318  mov     rcx, [rdi+8]; hDlg
0x18000a31c  mov     edx, ebx; nIDDlgItem
0x18000a31e  call    cs:__imp_GetDlgItem
0x18000a324  mov     rcx, rax; hWnd
0x18000a327  call    cs:__imp_IsWindowEnabled
0x18000a32d  test    eax, eax
0x18000a32f  jz      loc_18000A492
0x18000a335  mov     rcx, rdi; this
0x18000a338  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000a33d  mov     rcx, rdi; this
0x18000a340  mov     rbx, rax
0x18000a343  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000a348  mov     rsi, rax
0x18000a34b  test    rbx, rbx
0x18000a34e  jz      loc_18000A474
0x18000a354  xor     ecx, ecx
0x18000a356  cmp     [rbx+0Ch], ecx
0x18000a359  jz      short loc_18000A363
0x18000a35b  cmp     [rbx], ecx
0x18000a35d  lea     eax, [rcx+1]
0x18000a360  cmovz   ecx, eax
0x18000a363  test    rsi, rsi
0x18000a366  jz      short loc_18000A36D
0x18000a368  cmp     dword ptr [rsi], 0
0x18000a36b  jz      short loc_18000A375
0x18000a36d  test    ecx, ecx
0x18000a36f  jz      loc_18000A474
0x18000a375  mov     rcx, rdi; this
0x18000a378  call    ?UpdateIHVProfileOnAuthEncr@CACSecurityPage@@AEAAXXZ; CACSecurityPage::UpdateIHVProfileOnAuthEncr(void)
0x18000a37d  mov     eax, [rbx+8]
0x18000a380  mov     ebp, [rsi+4]
0x18000a383  neg     eax
0x18000a385  mov     rax, [rdi+4D0h]
0x18000a38c  mov     ebx, [rbx+10h]
0x18000a38f  sbb     rcx, rcx
0x18000a392  and     ecx, 8
0x18000a395  mov     r14, [rcx+rax+20h]
0x18000a39a  mov     rcx, rdi; this
0x18000a39d  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000a3a2  mov     r12, rax
0x18000a3a5  test    ebx, ebx
0x18000a3a7  jz      short loc_18000A3AF
0x18000a3a9  sub     ebx, [r14+24h]
0x18000a3ad  jmp     short loc_18000A3B1
0x18000a3af  xor     ebx, ebx
0x18000a3b1  mov     rax, [r14+18h]
0x18000a3b5  xor     edx, edx
0x18000a3b7  mov     rcx, [rax+rbx*8]
0x18000a3bb  sub     ebp, [rcx+18h]
0x18000a3be  cmp     ebp, [rcx+10h]
0x18000a3c1  jnb     short loc_18000A3CD
0x18000a3c3  mov     edx, ebp
0x18000a3c5  shl     rdx, 4
0x18000a3c9  add     rdx, [rcx+8]
0x18000a3cd  mov     [rcx+14h], ebp
0x18000a3d0  lea     r8, [rsp+68h+arg_10]
0x18000a3d8  mov     rax, [r14]
0x18000a3db  mov     r9, r12
0x18000a3de  mov     [rsp+68h+var_38], r8
0x18000a3e3  lea     r8, [rsp+68h+bstrString]
0x18000a3eb  mov     [rsp+68h+var_40], r8
0x18000a3f0  mov     r8, r15
0x18000a3f3  mov     [rsp+68h+var_48], rdx
0x18000a3f8  xor     edx, edx
0x18000a3fa  mov     rcx, [rax+rbx*8]
0x18000a3fe  mov     rax, [rcx]
0x18000a401  mov     rax, [rax+48h]
0x18000a405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a40a  test    eax, eax
0x18000a40c  js      short loc_18000A437
0x18000a40e  cmp     [rsp+68h+arg_10], 0
0x18000a416  jz      short loc_18000A451
0x18000a418  mov     r9d, [r14+24h]; unsigned int
0x18000a41c  mov     r8, r12; struct _DOT11EXT_IHV_PARAMS *
0x18000a41f  mov     dword ptr [r14+20h], 1
0x18000a427  mov     rcx, r14; this
0x18000a42a  mov     rdx, [rsp+68h+bstrString]; unsigned __int16 *
0x18000a432  call    ?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z; IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)
0x18000a437  cmp     [rsp+68h+arg_10], 0
0x18000a43f  jz      short loc_18000A451
0x18000a441  mov     rdx, [rsp+68h+bstrString]; unsigned __int16 *
0x18000a449  mov     rcx, rdi; this
0x18000a44c  call    ?SetNewIHVSecurityProfileData@CACSecurityPage@@AEAA_JPEAG@Z; CACSecurityPage::SetNewIHVSecurityProfileData(ushort *)
0x18000a451  test    r15, r15
0x18000a454  jz      short loc_18000A45F
0x18000a456  mov     rcx, r15; bstrString
0x18000a459  call    cs:__imp_SysFreeString
0x18000a45f  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18000a467  test    rcx, rcx
0x18000a46a  jz      short loc_18000A47C
0x18000a46c  call    cs:__imp_SysFreeString
0x18000a472  jmp     short loc_18000A47C
0x18000a474  mov     rcx, rdi; this
0x18000a477  call    ?UpdateMSProfileOnAuthEncr@CACSecurityPage@@AEAAXXZ; CACSecurityPage::UpdateMSProfileOnAuthEncr(void)
0x18000a47c  mov     rcx, rdi; this
0x18000a47f  call    ?RefreshControls@CACSecurityPage@@AEAA_JXZ; CACSecurityPage::RefreshControls(void)
0x18000a484  mov     rax, [rsp+68h+arg_20]
0x18000a48c  mov     dword ptr [rax], 1
0x18000a492  mov     rbx, [rsp+68h+arg_0]
0x18000a497  xor     eax, eax
0x18000a499  mov     rbp, [rsp+68h+arg_8]
0x18000a49e  add     rsp, 40h
0x18000a4a2  pop     r15
0x18000a4a4  pop     r14
0x18000a4a6  pop     r12
0x18000a4a8  pop     rdi
0x18000a4a9  pop     rsi
0x18000a4aa  retn
```
