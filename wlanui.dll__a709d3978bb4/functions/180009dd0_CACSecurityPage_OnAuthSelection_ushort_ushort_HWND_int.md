# CACSecurityPage::OnAuthSelection(ushort,ushort,HWND__ *,int &)

- ea: `0x180009dd0`
- end: `0x180009f31`
- name: `?OnAuthSelection@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `353`
- prototype: `__int64 __usercall@<rax>(CACSecurityPage *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x180006134`
- `0x1800078f4`
- `0x180007ae4`
- `0x18000833c`
- `0x180008388`
- `0x180009dd0`
- `0x18000c824`
- `0x18000cd48`
- `0x18000d714`
- `0x18000d834`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x180009e63`
- `USER32!IsWindowEnabled` at `0x180009e63`
- `USER32!IsWindowVisible` at `0x180009e4a`
- `USER32!IsWindowVisible` at `0x180009e4a`
- `USER32!SetFocus` at `0x180009df7`
- `USER32!SetFocus` at `0x180009df7`
- `USER32!GetDlgItem` at `0x180009e41`
- `USER32!GetDlgItem` at `0x180009e5a`
- `USER32!GetDlgItem` at `0x180009e41`
- `USER32!GetDlgItem` at `0x180009e5a`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnAuthSelection(CACSecurityPage *this, __int16 a2, __int64 a3, HWND a4, int *a5)
{
  int v6; // ebp
  HWND DlgItem; // rax
  HWND v9; // rax
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rax
  struct _AUI_AUTH_INFO *v11; // rsi
  int v12; // r14d
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rax
  BOOL v14; // ecx

  if ( a2 == 3 )
  {
    if ( *((_DWORD *)this + 156) )
    {
      SetFocus(*(HWND *)(*((_QWORD *)this + 166) + 40LL));
      v6 = 1;
    }
    else
    {
      v6 = 0;
    }
    *a5 = v6;
    return 0;
  }
  if ( a2 != 1 )
  {
    *a5 = 0;
    return 0;
  }
  DlgItem = GetDlgItem(*((HWND *)this + 1), 1111);
  if ( !IsWindowVisible(DlgItem) )
    return 0;
  v9 = GetDlgItem(*((HWND *)this + 1), 1111);
  if ( !IsWindowEnabled(v9) )
    return 0;
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth((HWND *)this);
  v11 = CurrentlySelectedAuth;
  if ( CurrentlySelectedAuth )
  {
    if ( !*((_DWORD *)CurrentlySelectedAuth + 3) || *(_DWORD *)CurrentlySelectedAuth )
      CACSecurityPage::DisplayCiphersForMSAuth(this, CurrentlySelectedAuth, 0, 0);
    else
      CACSecurityPage::DisplayCiphersForIHVAuth((HWND *)this, CurrentlySelectedAuth, 0, 0, 0);
  }
  v12 = *(_DWORD *)((char *)v11 + (-(__int64)(*(_DWORD *)v11 != 0) & 0xFFFFFFFFFFFFFFF4uLL) + 16);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher((HWND *)this);
  if ( !v11 )
    goto LABEL_23;
  v14 = 0;
  if ( *((_DWORD *)v11 + 3) )
    v14 = *(_DWORD *)v11 == 0;
  if ( CurrentlySelectedCipher && !*(_DWORD *)CurrentlySelectedCipher || v14 )
    CACSecurityPage::UpdateIHVProfileOnAuthEncr(this);
  else
LABEL_23:
    CACSecurityPage::UpdateMSProfileOnAuthEncr(this);
  if ( *((_DWORD *)this + 14) != v12 )
  {
    NetworkKeyControls::ResetNetworkKeyField(*((NetworkKeyControls **)this + 166));
    *((_DWORD *)this + 14) = v12;
  }
  CACSecurityPage::RefreshControls(this);
  *a5 = 1;
  return LresFromHr(0);
}

```

## disassembly

```asm
0x180009dd0  push    rbp
0x180009dd2  push    rsi
0x180009dd3  push    rdi
0x180009dd4  push    r14
0x180009dd6  sub     rsp, 38h
0x180009dda  mov     rdi, rcx
0x180009ddd  cmp     dx, 3
0x180009de1  jnz     short loc_180009E1C
0x180009de3  cmp     dword ptr [rcx+270h], 0
0x180009dea  jz      short loc_180009E04
0x180009dec  mov     rcx, [rcx+530h]
0x180009df3  mov     rcx, [rcx+28h]; hWnd
0x180009df7  call    cs:__imp_SetFocus
0x180009dfd  mov     ebp, 1
0x180009e02  jmp     short loc_180009E06
0x180009e04  xor     ebp, ebp
0x180009e06  mov     rax, [rsp+58h+arg_20]
0x180009e0e  mov     [rax], ebp
0x180009e10  xor     eax, eax
0x180009e12  add     rsp, 38h
0x180009e16  pop     r14
0x180009e18  pop     rdi
0x180009e19  pop     rsi
0x180009e1a  pop     rbp
0x180009e1b  retn
0x180009e1c  mov     ebp, 1
0x180009e21  cmp     dx, bp
0x180009e24  jz      short loc_180009E36
0x180009e26  mov     rax, [rsp+58h+arg_20]
0x180009e2e  mov     dword ptr [rax], 0
0x180009e34  jmp     short loc_180009E10
0x180009e36  mov     rcx, [rcx+8]; hDlg
0x180009e3a  mov     esi, 457h
0x180009e3f  mov     edx, esi; nIDDlgItem
0x180009e41  call    cs:__imp_GetDlgItem
0x180009e47  mov     rcx, rax; hWnd
0x180009e4a  call    cs:__imp_IsWindowVisible
0x180009e50  test    eax, eax
0x180009e52  jz      short loc_180009E10
0x180009e54  mov     rcx, [rdi+8]; hDlg
0x180009e58  mov     edx, esi; nIDDlgItem
0x180009e5a  call    cs:__imp_GetDlgItem
0x180009e60  mov     rcx, rax; hWnd
0x180009e63  call    cs:__imp_IsWindowEnabled
0x180009e69  test    eax, eax
0x180009e6b  jz      short loc_180009E10
0x180009e6d  mov     rcx, rdi; this
0x180009e70  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x180009e75  mov     rsi, rax
0x180009e78  test    rax, rax
0x180009e7b  jz      short loc_180009EB4
0x180009e7d  cmp     dword ptr [rax+0Ch], 0
0x180009e81  jz      short loc_180009EA3
0x180009e83  cmp     dword ptr [rax], 0
0x180009e86  jnz     short loc_180009EA3
0x180009e88  xor     r9d, r9d; struct _AUI_CIPHER_INFO *
0x180009e8b  mov     [rsp+58h+var_38], 0; int
0x180009e93  xor     r8d, r8d; int
0x180009e96  mov     rdx, rax; struct _AUI_AUTH_INFO *
0x180009e99  mov     rcx, rdi; this
0x180009e9c  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x180009ea1  jmp     short loc_180009EB4
0x180009ea3  xor     r9d, r9d; struct _AUI_CIPHER_INFO *
0x180009ea6  xor     r8d, r8d; int
0x180009ea9  mov     rdx, rsi; struct _AUI_AUTH_INFO *
0x180009eac  mov     rcx, rdi; this
0x180009eaf  call    ?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)
0x180009eb4  mov     eax, [rsi]
0x180009eb6  neg     eax
0x180009eb8  sbb     rcx, rcx
0x180009ebb  and     rcx, 0FFFFFFFFFFFFFFF4h
0x180009ebf  mov     r14d, [rcx+rsi+10h]
0x180009ec4  mov     rcx, rdi; this
0x180009ec7  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x180009ecc  test    rsi, rsi
0x180009ecf  jz      short loc_180009EF5
0x180009ed1  xor     ecx, ecx
0x180009ed3  cmp     [rsi+0Ch], ecx
0x180009ed6  jz      short loc_180009EDD
0x180009ed8  cmp     [rsi], ecx
0x180009eda  cmovz   ecx, ebp
0x180009edd  test    rax, rax
0x180009ee0  jz      short loc_180009EE7
0x180009ee2  cmp     dword ptr [rax], 0
0x180009ee5  jz      short loc_180009EEB
0x180009ee7  test    ecx, ecx
0x180009ee9  jz      short loc_180009EF5
0x180009eeb  mov     rcx, rdi; this
0x180009eee  call    ?UpdateIHVProfileOnAuthEncr@CACSecurityPage@@AEAAXXZ; CACSecurityPage::UpdateIHVProfileOnAuthEncr(void)
0x180009ef3  jmp     short loc_180009EFD
0x180009ef5  mov     rcx, rdi; this
0x180009ef8  call    ?UpdateMSProfileOnAuthEncr@CACSecurityPage@@AEAAXXZ; CACSecurityPage::UpdateMSProfileOnAuthEncr(void)
0x180009efd  cmp     [rdi+38h], r14d
0x180009f01  jz      short loc_180009F13
0x180009f03  mov     rcx, [rdi+530h]; this
0x180009f0a  call    ?ResetNetworkKeyField@NetworkKeyControls@@QEAAXXZ; NetworkKeyControls::ResetNetworkKeyField(void)
0x180009f0f  mov     [rdi+38h], r14d
0x180009f13  mov     rcx, rdi; this
0x180009f16  call    ?RefreshControls@CACSecurityPage@@AEAA_JXZ; CACSecurityPage::RefreshControls(void)
0x180009f1b  mov     rax, [rsp+58h+arg_20]
0x180009f23  xor     ecx, ecx; int
0x180009f25  mov     [rax], ebp
0x180009f27  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x180009f2c  jmp     loc_180009E12
```
