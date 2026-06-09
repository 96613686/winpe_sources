# CACSecurityPage::OnIHVKeyExtSettingsButton(ushort,ushort,HWND__ *,int &)

- ea: `0x18000a4b4`
- end: `0x18000a687`
- name: `?OnIHVKeyExtSettingsButton@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `467`
- prototype: `__int64 __usercall@<rax>(CACSecurityPage *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x180006134`
- `0x1800082f8`
- `0x18000833c`
- `0x180008388`
- `0x180008498`
- `0x18000a4b4`
- `0x18000cdc4`
- `0x18001d010`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x18000a503`
- `USER32!IsWindowEnabled` at `0x18000a503`
- `USER32!IsWindowVisible` at `0x18000a4e6`
- `USER32!IsWindowVisible` at `0x18000a4e6`
- `USER32!GetDlgItem` at `0x18000a4dd`
- `USER32!GetDlgItem` at `0x18000a4fa`
- `USER32!GetDlgItem` at `0x18000a4dd`
- `USER32!GetDlgItem` at `0x18000a4fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a641`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a662`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a641`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a662`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnIHVKeyExtSettingsButton(HWND *this, __int64 a2, __int16 a3, OLECHAR *a4, int *a5)
{
  HWND DlgItem; // rax
  HWND v7; // rax
  bool v8; // zf
  int *v9; // r14
  int v10; // edi
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rdi
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rax
  BOOL v13; // ecx
  struct _AUI_AUTH_INFO *v14; // rdi
  __int64 v15; // rsi
  unsigned __int16 *CurrentIHVSecurityProfile; // rax
  int v17; // edi
  OLECHAR *v18; // rbp
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // r9
  __int64 v20; // rdi
  int v22; // [rsp+80h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  bstrString = a4;
  LOWORD(v22) = a3;
  DlgItem = GetDlgItem(this[1], 1124);
  if ( !IsWindowVisible(DlgItem) )
    return 0;
  v7 = GetDlgItem(this[1], 1124);
  if ( !IsWindowEnabled(v7) )
    return 0;
  v8 = this[154] == 0;
  v9 = a5;
  bstrString = 0;
  v22 = 0;
  *a5 = 0;
  if ( v8 )
  {
    v10 = -2147467259;
  }
  else
  {
    CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
    CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
    if ( !CurrentlySelectedAuth )
      goto LABEL_22;
    v13 = 0;
    if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
      v13 = *(_DWORD *)CurrentlySelectedAuth == 0;
    if ( CurrentlySelectedCipher && !*(_DWORD *)CurrentlySelectedCipher || v13 )
    {
      v14 = CACSecurityPage::GetCurrentlySelectedAuth(this);
      v15 = *(_QWORD *)((char *)this[154] + (*((_DWORD *)v14 + 2) != 0 ? 8 : 0) + 32);
      if ( v15 && *(_DWORD *)(v15 + 8) )
      {
        CurrentIHVSecurityProfile = CACSecurityPage::GetCurrentIHVSecurityProfile((CACSecurityPage *)this);
        v17 = *((_DWORD *)v14 + 4);
        v18 = CurrentIHVSecurityProfile;
        UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams((CACSecurityPage *)this);
        if ( v17 )
          v20 = (unsigned int)(v17 - *(_DWORD *)(v15 + 36));
        else
          v20 = 0;
        v10 = (*(__int64 (__fastcall **)(_QWORD, HWND, OLECHAR *, struct _DOT11EXT_IHV_PARAMS *, BSTR *, int *))(**(_QWORD **)(*(_QWORD *)v15 + 8 * v20) + 32LL))(
                *(_QWORD *)(*(_QWORD *)v15 + 8 * v20),
                this[1],
                v18,
                UpdatedIHVParams,
                &bstrString,
                &v22);
        if ( v10 >= 0 && v22 )
          CACSecurityPage::SetNewIHVSecurityProfileData((CACSecurityPage *)this, bstrString);
        if ( v18 )
          SysFreeString(v18);
      }
      else
      {
        v10 = -2147467263;
      }
    }
    else
    {
LABEL_22:
      v10 = -2147418113;
    }
    if ( bstrString )
      SysFreeString(bstrString);
  }
  *v9 = 1;
  return LresFromHr(v10);
}

```

## disassembly

```asm
0x18000a4b4  mov     [rsp+arg_0], rbx
0x18000a4b9  mov     [rsp+bstrString], r9
0x18000a4be  mov     word ptr [rsp+arg_10], r8w
0x18000a4c4  push    rbp
0x18000a4c5  push    rsi
0x18000a4c6  push    rdi
0x18000a4c7  push    r12
0x18000a4c9  push    r14
0x18000a4cb  sub     rsp, 40h
0x18000a4cf  mov     rbx, rcx
0x18000a4d2  mov     edi, 464h
0x18000a4d7  mov     rcx, [rcx+8]; hDlg
0x18000a4db  mov     edx, edi; nIDDlgItem
0x18000a4dd  call    cs:__imp_GetDlgItem
0x18000a4e3  mov     rcx, rax; hWnd
0x18000a4e6  call    cs:__imp_IsWindowVisible
0x18000a4ec  test    eax, eax
0x18000a4ee  jz      loc_18000A674
0x18000a4f4  mov     rcx, [rbx+8]; hDlg
0x18000a4f8  mov     edx, edi; nIDDlgItem
0x18000a4fa  call    cs:__imp_GetDlgItem
0x18000a500  mov     rcx, rax; hWnd
0x18000a503  call    cs:__imp_IsWindowEnabled
0x18000a509  test    eax, eax
0x18000a50b  jz      loc_18000A674
0x18000a511  cmp     qword ptr [rbx+4D0h], 0
0x18000a519  mov     r12d, 1
0x18000a51f  mov     r14, [rsp+68h+arg_20]
0x18000a527  mov     [rsp+68h+bstrString], 0
0x18000a533  mov     [rsp+68h+arg_10], 0
0x18000a53e  mov     dword ptr [r14], 0
0x18000a545  jnz     short loc_18000A551
0x18000a547  mov     edi, 80004005h
0x18000a54c  jmp     loc_18000A668
0x18000a551  mov     rcx, rbx; this
0x18000a554  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000a559  mov     rcx, rbx; this
0x18000a55c  mov     rdi, rax
0x18000a55f  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000a564  test    rax, rax
0x18000a567  jz      loc_18000A650
0x18000a56d  xor     ecx, ecx
0x18000a56f  cmp     [rax+0Ch], ecx
0x18000a572  jz      short loc_18000A57A
0x18000a574  cmp     [rax], ecx
0x18000a576  cmovz   ecx, r12d
0x18000a57a  test    rdi, rdi
0x18000a57d  jz      short loc_18000A584
0x18000a57f  cmp     dword ptr [rdi], 0
0x18000a582  jz      short loc_18000A58C
0x18000a584  test    ecx, ecx
0x18000a586  jz      loc_18000A650
0x18000a58c  mov     rcx, rbx; this
0x18000a58f  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000a594  mov     rdi, rax
0x18000a597  mov     ecx, [rax+8]
0x18000a59a  neg     ecx
0x18000a59c  mov     rcx, [rbx+4D0h]
0x18000a5a3  sbb     rdx, rdx
0x18000a5a6  and     edx, 8
0x18000a5a9  mov     rsi, [rdx+rcx+20h]
0x18000a5ae  test    rsi, rsi
0x18000a5b1  jz      loc_18000A649
0x18000a5b7  cmp     dword ptr [rsi+8], 0
0x18000a5bb  jbe     loc_18000A649
0x18000a5c1  mov     rcx, rbx; this
0x18000a5c4  call    ?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ; CACSecurityPage::GetCurrentIHVSecurityProfile(void)
0x18000a5c9  mov     edi, [rdi+10h]
0x18000a5cc  mov     rcx, rbx; this
0x18000a5cf  mov     rbp, rax
0x18000a5d2  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000a5d7  mov     r9, rax
0x18000a5da  test    edi, edi
0x18000a5dc  jz      short loc_18000A5E3
0x18000a5de  sub     edi, [rsi+24h]
0x18000a5e1  jmp     short loc_18000A5E5
0x18000a5e3  xor     edi, edi
0x18000a5e5  mov     rax, [rsi]
0x18000a5e8  lea     rdx, [rsp+68h+arg_10]
0x18000a5f0  mov     [rsp+68h+var_40], rdx
0x18000a5f5  mov     r8, rbp
0x18000a5f8  lea     rdx, [rsp+68h+bstrString]
0x18000a600  mov     [rsp+68h+var_48], rdx
0x18000a605  mov     rcx, [rax+rdi*8]
0x18000a609  mov     rdx, [rbx+8]
0x18000a60d  mov     rax, [rcx]
0x18000a610  mov     rax, [rax+20h]
0x18000a614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a619  mov     edi, eax
0x18000a61b  test    eax, eax
0x18000a61d  js      short loc_18000A639
0x18000a61f  cmp     [rsp+68h+arg_10], 0
0x18000a627  jz      short loc_18000A639
0x18000a629  mov     rdx, [rsp+68h+bstrString]; unsigned __int16 *
0x18000a631  mov     rcx, rbx; this
0x18000a634  call    ?SetNewIHVSecurityProfileData@CACSecurityPage@@AEAA_JPEAG@Z; CACSecurityPage::SetNewIHVSecurityProfileData(ushort *)
0x18000a639  test    rbp, rbp
0x18000a63c  jz      short loc_18000A655
0x18000a63e  mov     rcx, rbp; bstrString
0x18000a641  call    cs:__imp_SysFreeString
0x18000a647  jmp     short loc_18000A655
0x18000a649  mov     edi, 80004001h
0x18000a64e  jmp     short loc_18000A655
0x18000a650  mov     edi, 8000FFFFh
0x18000a655  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18000a65d  test    rcx, rcx
0x18000a660  jz      short loc_18000A668
0x18000a662  call    cs:__imp_SysFreeString
0x18000a668  mov     ecx, edi; int
0x18000a66a  mov     [r14], r12d
0x18000a66d  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000a672  jmp     short loc_18000A676
0x18000a674  xor     eax, eax
0x18000a676  mov     rbx, [rsp+68h+arg_0]
0x18000a67b  add     rsp, 40h
0x18000a67f  pop     r14
0x18000a681  pop     r12
0x18000a683  pop     rdi
0x18000a684  pop     rsi
0x18000a685  pop     rbp
0x18000a686  retn
```
