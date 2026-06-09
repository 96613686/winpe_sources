# CACSecurityPage::OnIHVSecuritySelection(ushort,ushort,HWND__ *,int &)

- ea: `0x18000a690`
- end: `0x18000a7f0`
- name: `?OnIHVSecuritySelection@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `352`
- prototype: `__int64 __usercall@<rax>(CACSecurityPage *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x180006134`
- `0x1800082f8`
- `0x18000833c`
- `0x180008498`
- `0x18000a690`
- `0x18000c824`
- `0x18000cdc4`
- `0x180011188`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x18000a726`
- `USER32!IsWindowEnabled` at `0x18000a726`
- `USER32!IsWindowVisible` at `0x18000a709`
- `USER32!IsWindowVisible` at `0x18000a709`
- `USER32!GetDlgItem` at `0x18000a700`
- `USER32!GetDlgItem` at `0x18000a71d`
- `USER32!GetDlgItem` at `0x18000a700`
- `USER32!GetDlgItem` at `0x18000a71d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7d3`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnIHVSecuritySelection(HWND *this, __int16 a2, __int64 a3, HWND a4, int *a5)
{
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rax
  int v8; // edi
  unsigned int v9; // r14d
  HWND DlgItem; // rax
  HWND v11; // rax
  HWND v12; // rax
  unsigned __int16 *CurrentIHVSecurityProfile; // rbp
  IHVExtHelper *v14; // rbx
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // rax
  int v17; // [rsp+70h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+20h] BYREF

  bstrString = 0;
  v17 = 0;
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
  v8 = CurrentlySelectedAuth == 0 ? 0xD : 0;
  if ( a2 == 1 )
  {
    v9 = *((_DWORD *)CurrentlySelectedAuth + 4);
    DlgItem = GetDlgItem(this[1], 15078);
    if ( IsWindowVisible(DlgItem) )
    {
      v11 = GetDlgItem(this[1], 15078);
      if ( IsWindowEnabled(v11) )
      {
        v12 = this[154];
        if ( v12 )
        {
          if ( *(_DWORD *)(*((_QWORD *)v12 + 4) + 8LL) )
          {
            CurrentIHVSecurityProfile = CACSecurityPage::GetCurrentIHVSecurityProfile((CACSecurityPage *)this);
            v14 = (IHVExtHelper *)*((_QWORD *)this[154] + 4);
            UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams((CACSecurityPage *)this);
            v8 = IHVExtHelper::IHVExtHlpSetSelected(
                   v14,
                   CurrentIHVSecurityProfile,
                   UpdatedIHVParams,
                   &bstrString,
                   &v17,
                   v9);
            if ( v8 >= 0 )
            {
              if ( v17 )
                CACSecurityPage::SetNewIHVSecurityProfileData((CACSecurityPage *)this, bstrString);
              CACSecurityPage::RefreshControls((CACSecurityPage *)this);
              *a5 = 1;
            }
            if ( CurrentIHVSecurityProfile )
              SysFreeString(CurrentIHVSecurityProfile);
          }
        }
      }
    }
  }
  else
  {
    *a5 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return LresFromHr(v8);
}

```

## disassembly

```asm
0x18000a690  mov     rax, rsp
0x18000a693  mov     [rax+8], rbx
0x18000a697  mov     [rax+20h], r9
0x18000a69b  mov     [rax+18h], r8w
0x18000a6a0  push    rbp
0x18000a6a1  push    rsi
0x18000a6a2  push    rdi
0x18000a6a3  push    r12
0x18000a6a5  push    r14
0x18000a6a7  sub     rsp, 30h
0x18000a6ab  movzx   ebx, dx
0x18000a6ae  mov     qword ptr [rax+20h], 0
0x18000a6b6  mov     rsi, rcx
0x18000a6b9  mov     dword ptr [rax+18h], 0
0x18000a6c0  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000a6c5  mov     r8, rax
0x18000a6c8  mov     r12d, 1
0x18000a6ce  neg     r8
0x18000a6d1  sbb     edi, edi
0x18000a6d3  not     edi
0x18000a6d5  and     edi, 0Dh
0x18000a6d8  cmp     bx, r12w
0x18000a6dc  jz      short loc_18000A6F1
0x18000a6de  mov     rax, [rsp+58h+arg_20]
0x18000a6e6  mov     dword ptr [rax], 0
0x18000a6ec  jmp     loc_18000A7C9
0x18000a6f1  mov     rcx, [rsi+8]; hDlg
0x18000a6f5  mov     ebx, 3AE6h
0x18000a6fa  mov     r14d, [rax+10h]
0x18000a6fe  mov     edx, ebx; nIDDlgItem
0x18000a700  call    cs:__imp_GetDlgItem
0x18000a706  mov     rcx, rax; hWnd
0x18000a709  call    cs:__imp_IsWindowVisible
0x18000a70f  test    eax, eax
0x18000a711  jz      loc_18000A7C9
0x18000a717  mov     rcx, [rsi+8]; hDlg
0x18000a71b  mov     edx, ebx; nIDDlgItem
0x18000a71d  call    cs:__imp_GetDlgItem
0x18000a723  mov     rcx, rax; hWnd
0x18000a726  call    cs:__imp_IsWindowEnabled
0x18000a72c  test    eax, eax
0x18000a72e  jz      loc_18000A7C9
0x18000a734  mov     rax, [rsi+4D0h]
0x18000a73b  test    rax, rax
0x18000a73e  jz      loc_18000A7C9
0x18000a744  mov     rax, [rax+20h]
0x18000a748  cmp     dword ptr [rax+8], 0
0x18000a74c  jbe     short loc_18000A7C9
0x18000a74e  mov     rcx, rsi; this
0x18000a751  call    ?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ; CACSecurityPage::GetCurrentIHVSecurityProfile(void)
0x18000a756  mov     rcx, [rsi+4D0h]
0x18000a75d  mov     rbp, rax
0x18000a760  mov     rbx, [rcx+20h]
0x18000a764  mov     rcx, rsi; this
0x18000a767  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000a76c  lea     rcx, [rsp+58h+arg_10]
0x18000a771  mov     [rsp+58h+var_30], r14d; unsigned int
0x18000a776  mov     [rsp+58h+var_38], rcx; int *
0x18000a77b  lea     r9, [rsp+58h+bstrString]; unsigned __int16 **
0x18000a780  mov     rcx, rbx; this
0x18000a783  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000a786  mov     rdx, rbp; unsigned __int16 *
0x18000a789  call    ?IHVExtHlpSetSelected@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@PEAPEAGPEAHK@Z; IHVExtHelper::IHVExtHlpSetSelected(ushort *,_DOT11EXT_IHV_PARAMS *,ushort * *,int *,ulong)
0x18000a78e  mov     edi, eax
0x18000a790  test    eax, eax
0x18000a792  js      short loc_18000A7BB
0x18000a794  cmp     [rsp+58h+arg_10], 0
0x18000a799  jz      short loc_18000A7A8
0x18000a79b  mov     rdx, [rsp+58h+bstrString]; unsigned __int16 *
0x18000a7a0  mov     rcx, rsi; this
0x18000a7a3  call    ?SetNewIHVSecurityProfileData@CACSecurityPage@@AEAA_JPEAG@Z; CACSecurityPage::SetNewIHVSecurityProfileData(ushort *)
0x18000a7a8  mov     rcx, rsi; this
0x18000a7ab  call    ?RefreshControls@CACSecurityPage@@AEAA_JXZ; CACSecurityPage::RefreshControls(void)
0x18000a7b0  mov     rcx, [rsp+58h+arg_20]
0x18000a7b8  mov     [rcx], r12d
0x18000a7bb  test    rbp, rbp
0x18000a7be  jz      short loc_18000A7C9
0x18000a7c0  mov     rcx, rbp; bstrString
0x18000a7c3  call    cs:__imp_SysFreeString
0x18000a7c9  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18000a7ce  test    rcx, rcx
0x18000a7d1  jz      short loc_18000A7D9
0x18000a7d3  call    cs:__imp_SysFreeString
0x18000a7d9  mov     ecx, edi; int
0x18000a7db  mov     rbx, [rsp+58h+arg_0]
0x18000a7e0  add     rsp, 30h
0x18000a7e4  pop     r14
0x18000a7e6  pop     r12
0x18000a7e8  pop     rdi
0x18000a7e9  pop     rsi
0x18000a7ea  pop     rbp
0x18000a7eb  jmp     ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
```
