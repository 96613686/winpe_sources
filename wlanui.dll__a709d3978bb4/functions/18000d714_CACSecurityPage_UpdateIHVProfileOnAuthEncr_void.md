# CACSecurityPage::UpdateIHVProfileOnAuthEncr(void)

- ea: `0x18000d714`
- end: `0x18000d82b`
- name: `?UpdateIHVProfileOnAuthEncr@CACSecurityPage@@AEAAXXZ`
- size: `279`
- prototype: `void __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009dd0`
- `0x18000a29c`

## callees

- `0x1800082f8`
- `0x18000833c`
- `0x180008388`
- `0x180008498`
- `0x18000cdc4`
- `0x18000d714`
- `0x180011188`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d7e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d7f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d7e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d7f9`

## pseudocode

```c
void __fastcall CACSecurityPage::UpdateIHVProfileOnAuthEncr(CACSecurityPage *this)
{
  unsigned __int16 *CurrentIHVSecurityProfile; // rbp
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rbx
  __int64 v4; // r14
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rax
  BOOL v6; // ecx
  int v7; // eax
  unsigned int v8; // ebx
  IHVExtHelper *v9; // rdi
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // rax
  int v11; // [rsp+60h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+10h] BYREF

  bstrString = 0;
  v11 = 0;
  CurrentIHVSecurityProfile = CACSecurityPage::GetCurrentIHVSecurityProfile(this);
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth((HWND *)this);
  v4 = *(_QWORD *)(*((_QWORD *)this + 5) + 552LL);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher((HWND *)this);
  if ( !CurrentlySelectedAuth )
    goto LABEL_14;
  v6 = 0;
  if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
    v6 = *(_DWORD *)CurrentlySelectedAuth == 0;
  if ( CurrentlySelectedCipher && !*(_DWORD *)CurrentlySelectedCipher || v6 )
  {
    v7 = *((_DWORD *)CurrentlySelectedAuth + 2);
    v8 = *((_DWORD *)CurrentlySelectedAuth + 4);
    v9 = *(IHVExtHelper **)((v7 != 0 ? 8 : 0) + *((_QWORD *)this + 154) + 32LL);
    UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams(this);
    IHVExtHelper::IHVExtHlpSetSelected(v9, CurrentIHVSecurityProfile, UpdatedIHVParams, &bstrString, &v11, v8);
    if ( v11 )
      CACSecurityPage::SetNewIHVSecurityProfileData(this, bstrString);
    if ( CurrentIHVSecurityProfile )
      SysFreeString(CurrentIHVSecurityProfile);
    if ( bstrString )
      SysFreeString(bstrString);
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 432LL) = 1;
  }
  else
  {
LABEL_14:
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 432LL) = 0;
  }
}

```

## disassembly

```asm
0x18000d714  mov     [rsp+arg_10], rbx
0x18000d719  push    rbp
0x18000d71a  push    rsi
0x18000d71b  push    rdi
0x18000d71c  push    r12
0x18000d71e  push    r14
0x18000d720  sub     rsp, 30h
0x18000d724  mov     rsi, rcx
0x18000d727  mov     [rsp+58h+bstrString], 0
0x18000d730  mov     [rsp+58h+arg_0], 0
0x18000d738  call    ?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ; CACSecurityPage::GetCurrentIHVSecurityProfile(void)
0x18000d73d  mov     rcx, rsi; this
0x18000d740  mov     rbp, rax
0x18000d743  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000d748  mov     rdx, [rsi+28h]
0x18000d74c  mov     rcx, rsi; this
0x18000d74f  mov     rbx, rax
0x18000d752  mov     r14, [rdx+228h]
0x18000d759  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000d75e  test    rbx, rbx
0x18000d761  jz      loc_18000D80C
0x18000d767  xor     ecx, ecx
0x18000d769  lea     r12d, [rcx+1]
0x18000d76d  cmp     [rbx+0Ch], ecx
0x18000d770  jz      short loc_18000D778
0x18000d772  cmp     [rbx], ecx
0x18000d774  cmovz   ecx, r12d
0x18000d778  test    rax, rax
0x18000d77b  jz      short loc_18000D782
0x18000d77d  cmp     dword ptr [rax], 0
0x18000d780  jz      short loc_18000D78A
0x18000d782  test    ecx, ecx
0x18000d784  jz      loc_18000D80C
0x18000d78a  mov     eax, [rbx+8]
0x18000d78d  mov     ebx, [rbx+10h]
0x18000d790  neg     eax
0x18000d792  mov     rax, [rsi+4D0h]
0x18000d799  sbb     rcx, rcx
0x18000d79c  and     ecx, 8
0x18000d79f  mov     rdi, [rcx+rax+20h]
0x18000d7a4  mov     rcx, rsi; this
0x18000d7a7  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000d7ac  lea     rcx, [rsp+58h+arg_0]
0x18000d7b1  mov     [rsp+58h+var_30], ebx; unsigned int
0x18000d7b5  mov     [rsp+58h+var_38], rcx; int *
0x18000d7ba  lea     r9, [rsp+58h+bstrString]; unsigned __int16 **
0x18000d7bf  mov     rcx, rdi; this
0x18000d7c2  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000d7c5  mov     rdx, rbp; unsigned __int16 *
0x18000d7c8  call    ?IHVExtHlpSetSelected@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@PEAPEAGPEAHK@Z; IHVExtHelper::IHVExtHlpSetSelected(ushort *,_DOT11EXT_IHV_PARAMS *,ushort * *,int *,ulong)
0x18000d7cd  cmp     [rsp+58h+arg_0], 0
0x18000d7d2  jz      short loc_18000D7E1
0x18000d7d4  mov     rdx, [rsp+58h+bstrString]; unsigned __int16 *
0x18000d7d9  mov     rcx, rsi; this
0x18000d7dc  call    ?SetNewIHVSecurityProfileData@CACSecurityPage@@AEAA_JPEAG@Z; CACSecurityPage::SetNewIHVSecurityProfileData(ushort *)
0x18000d7e1  test    rbp, rbp
0x18000d7e4  jz      short loc_18000D7EF
0x18000d7e6  mov     rcx, rbp; bstrString
0x18000d7e9  call    cs:__imp_SysFreeString
0x18000d7ef  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18000d7f4  test    rcx, rcx
0x18000d7f7  jz      short loc_18000D7FF
0x18000d7f9  call    cs:__imp_SysFreeString
0x18000d7ff  mov     rax, [r14+20h]
0x18000d803  mov     [rax+1B0h], r12d
0x18000d80a  jmp     short loc_18000D81A
0x18000d80c  mov     rax, [r14+20h]
0x18000d810  mov     dword ptr [rax+1B0h], 0
0x18000d81a  mov     rbx, [rsp+58h+arg_10]
0x18000d81f  add     rsp, 30h
0x18000d823  pop     r14
0x18000d825  pop     r12
0x18000d827  pop     rdi
0x18000d828  pop     rsi
0x18000d829  pop     rbp
0x18000d82a  retn
```
