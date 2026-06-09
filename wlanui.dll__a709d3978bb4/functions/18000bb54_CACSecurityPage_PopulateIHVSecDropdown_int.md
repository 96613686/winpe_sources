# CACSecurityPage::PopulateIHVSecDropdown(int)

- ea: `0x18000bb54`
- end: `0x18000bd7f`
- name: `?PopulateIHVSecDropdown@CACSecurityPage@@AEAAJH@Z`
- size: `555`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180005e64`
- `0x1800060d4`
- `0x18000739c`
- `0x180007404`
- `0x1800078f4`
- `0x180007ae4`
- `0x1800082f8`
- `0x18000bb54`
- `0x180010ef0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000bd3e`
- `KERNEL32!GetProcessHeap` at `0x18000bd3e`
- `KERNEL32!HeapFree` at `0x18000bd4c`
- `KERNEL32!HeapFree` at `0x18000bd4c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd5a`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::PopulateIHVSecDropdown(CACSecurityPage *this, int a2)
{
  __int64 v2; // rax
  unsigned int v5; // r14d
  int v6; // r12d
  LPARAM v7; // rsi
  unsigned __int16 *CurrentIHVSecurityProfile; // r15
  unsigned int v9; // ebp
  __int64 v10; // rdx
  int v11; // r14d
  __int64 v12; // r8
  unsigned int v13; // r14d
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  LPARAM v17; // rbx
  __int64 v18; // rcx
  LPARAM AuthInfo; // rax
  HWND v20; // rcx
  int v21; // eax
  LPARAM v22; // rbx
  HWND v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rax
  unsigned __int64 v27; // rcx
  _DWORD *v28; // rax
  unsigned int v29; // edx
  struct _AUI_CIPHER_INFO *CipherInfo; // rbx
  HANDLE ProcessHeap; // rax
  LPARAM lParam; // [rsp+30h] [rbp-48h] BYREF
  LPARAM v34; // [rsp+38h] [rbp-40h]
  int v35; // [rsp+80h] [rbp+8h]
  unsigned int v36; // [rsp+90h] [rbp+18h]
  unsigned int v37; // [rsp+98h] [rbp+20h]

  v2 = *((_QWORD *)this + 154);
  lParam = 0;
  if ( !v2 || !*(_DWORD *)(v2 + 52) )
    return 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  CurrentIHVSecurityProfile = CACSecurityPage::GetCurrentIHVSecurityProfile(this);
  v9 = 0;
  v36 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 32LL) + 8LL);
  if ( v36 )
  {
    do
    {
      v10 = *((_QWORD *)this + 154);
      v11 = *(_DWORD *)(*(_QWORD *)(v10 + 32) + 36LL);
      lParam = 0;
      v12 = *(_QWORD *)(v10 + 32);
      v13 = v9 + v11;
      if ( v13 )
        v14 = v13 - *(_DWORD *)(v12 + 36);
      else
        v14 = 0;
      v15 = *(_QWORD *)(*(_QWORD *)v12 + 8LL * v14);
      v16 = (*(__int64 (__fastcall **)(__int64, LPARAM *))(*(_QWORD *)v15 + 24LL))(v15, &lParam);
      v17 = lParam;
      v37 = v16;
      AuthInfo = CACSecurityPage::CreateAuthInfo(v18, 0, 0, 0, 1, v13);
      v20 = (HWND)*((_QWORD *)this + 8);
      v34 = AuthInfo;
      v21 = ComboBox_AddItem(v20, v17, AuthInfo);
      v22 = v34;
      v35 = v21;
      if ( !v7 )
      {
        v7 = v34;
        v6 = v21;
      }
      if ( a2
        && (unsigned int)IHVExtHelper::IHVExtHlpGetSelected(
                           *(IHVExtHelper **)(*((_QWORD *)this + 154) + 32LL),
                           CurrentIHVSecurityProfile,
                           v13) )
      {
        v6 = v35;
        v7 = v22;
      }
      ++v9;
    }
    while ( v9 < v36 );
    v5 = v37;
  }
  if ( a2 )
  {
    v23 = (HWND)*((_QWORD *)this + 8);
    *((_DWORD *)this + 14) = *(_DWORD *)((-(__int64)(*(_DWORD *)v7 != 0) & 0xFFFFFFFFFFFFFFF4uLL) + v7 + 16);
    ComboBox_SetCurSelNotify(v23, v6);
    v24 = *(_QWORD *)(*((_QWORD *)this + 154) + 32LL);
    v25 = *(_DWORD *)(v7 + 16);
    if ( v25 )
      v26 = (unsigned int)(v25 - *(_DWORD *)(v24 + 36));
    else
      v26 = 0;
    v27 = *(_QWORD *)(v24 + 24);
    if ( v27
      && *(_QWORD *)v27
      && (v28 = *(_DWORD **)(v27 + 8 * v26), v27 = (unsigned int)v28[5], (unsigned int)v27 < v28[4]) )
    {
      v29 = v27 + v28[6];
    }
    else
    {
      v29 = 0;
    }
    CipherInfo = CACSecurityPage::CreateCipherInfo((CACSecurityPage *)v27, v29, 0);
    if ( !*(_DWORD *)(v7 + 12) || *(_DWORD *)v7 )
      CACSecurityPage::DisplayCiphersForMSAuth(this, (struct _AUI_AUTH_INFO *)v7, 1, CipherInfo);
    else
      CACSecurityPage::DisplayCiphersForIHVAuth((HWND *)this, (struct _AUI_AUTH_INFO *)v7, 1, CipherInfo, 0);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, CipherInfo);
  }
  if ( CurrentIHVSecurityProfile )
    SysFreeString(CurrentIHVSecurityProfile);
  return v5;
}

```

## disassembly

```asm
0x18000bb54  mov     [rsp+arg_8], rbx
0x18000bb59  push    rbp
0x18000bb5a  push    rsi
0x18000bb5b  push    rdi
0x18000bb5c  push    r12
0x18000bb5e  push    r13
0x18000bb60  push    r14
0x18000bb62  push    r15
0x18000bb64  sub     rsp, 40h
0x18000bb68  mov     rax, [rcx+4D0h]
0x18000bb6f  mov     r13d, edx
0x18000bb72  mov     [rsp+78h+lParam], 0
0x18000bb7b  mov     rdi, rcx
0x18000bb7e  test    rax, rax
0x18000bb81  jz      loc_18000BD65
0x18000bb87  cmp     dword ptr [rax+34h], 0
0x18000bb8b  jz      loc_18000BD65
0x18000bb91  xor     r14d, r14d
0x18000bb94  xor     r12d, r12d
0x18000bb97  xor     esi, esi
0x18000bb99  call    ?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ; CACSecurityPage::GetCurrentIHVSecurityProfile(void)
0x18000bb9e  mov     r15, rax
0x18000bba1  xor     ebp, ebp
0x18000bba3  mov     rax, [rdi+4D0h]
0x18000bbaa  mov     rcx, [rax+20h]
0x18000bbae  mov     eax, [rcx+8]
0x18000bbb1  mov     [rsp+78h+arg_10], eax
0x18000bbb8  test    eax, eax
0x18000bbba  jz      loc_18000BC98
0x18000bbc0  mov     rdx, [rdi+4D0h]
0x18000bbc7  mov     rax, [rdx+20h]
0x18000bbcb  mov     r14d, [rax+24h]
0x18000bbcf  mov     [rsp+78h+lParam], 0
0x18000bbd8  mov     r8, [rdx+20h]
0x18000bbdc  add     r14d, ebp
0x18000bbdf  jz      short loc_18000BBEA
0x18000bbe1  mov     eax, r14d
0x18000bbe4  sub     eax, [r8+24h]
0x18000bbe8  jmp     short loc_18000BBEC
0x18000bbea  xor     eax, eax
0x18000bbec  mov     ecx, eax
0x18000bbee  lea     rdx, [rsp+78h+lParam]
0x18000bbf3  mov     rax, [r8]
0x18000bbf6  mov     rcx, [rax+rcx*8]
0x18000bbfa  mov     rax, [rcx]
0x18000bbfd  mov     rax, [rax+18h]
0x18000bc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc06  mov     rbx, [rsp+78h+lParam]
0x18000bc0b  xor     r9d, r9d
0x18000bc0e  xor     r8d, r8d
0x18000bc11  mov     [rsp+78h+var_50], r14d
0x18000bc16  xor     edx, edx
0x18000bc18  mov     [rsp+78h+arg_18], eax
0x18000bc1f  mov     [rsp+78h+var_58], 1
0x18000bc27  call    ?CreateAuthInfo@CACSecurityPage@@AEAAPEAU_AUI_AUTH_INFO@@HW4AUI_DOT11_AUTH_ALGORITHM@@HHK@Z; CACSecurityPage::CreateAuthInfo(int,AUI_DOT11_AUTH_ALGORITHM,int,int,ulong)
0x18000bc2c  mov     rcx, [rdi+40h]; hWnd
0x18000bc30  mov     r8, rax; LPARAM
0x18000bc33  mov     rdx, rbx; lParam
0x18000bc36  mov     [rsp+78h+var_40], rax
0x18000bc3b  call    ?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z; ComboBox_AddItem(HWND__ *,ushort const *,void *)
0x18000bc40  mov     rbx, [rsp+78h+var_40]
0x18000bc45  mov     [rsp+78h+arg_0], eax
0x18000bc4c  test    rsi, rsi
0x18000bc4f  jnz     short loc_18000BC57
0x18000bc51  mov     rsi, rbx
0x18000bc54  mov     r12d, eax
0x18000bc57  test    r13d, r13d
0x18000bc5a  jz      short loc_18000BC81
0x18000bc5c  mov     rcx, [rdi+4D0h]
0x18000bc63  mov     r8d, r14d; unsigned int
0x18000bc66  mov     rdx, r15; unsigned __int16 *
0x18000bc69  mov     rcx, [rcx+20h]; this
0x18000bc6d  call    ?IHVExtHlpGetSelected@IHVExtHelper@@QEAAHPEAGK@Z; IHVExtHelper::IHVExtHlpGetSelected(ushort *,ulong)
0x18000bc72  test    eax, eax
0x18000bc74  jz      short loc_18000BC81
0x18000bc76  mov     r12d, [rsp+78h+arg_0]
0x18000bc7e  mov     rsi, rbx
0x18000bc81  inc     ebp
0x18000bc83  cmp     ebp, [rsp+78h+arg_10]
0x18000bc8a  jb      loc_18000BBC0
0x18000bc90  mov     r14d, [rsp+78h+arg_18]
0x18000bc98  test    r13d, r13d
0x18000bc9b  jz      loc_18000BD52
0x18000bca1  mov     eax, [rsi]
0x18000bca3  mov     edx, r12d; int
0x18000bca6  mov     rcx, [rdi+40h]; hWnd
0x18000bcaa  neg     eax
0x18000bcac  sbb     rax, rax
0x18000bcaf  and     rax, 0FFFFFFFFFFFFFFF4h
0x18000bcb3  mov     eax, [rax+rsi+10h]
0x18000bcb7  mov     [rdi+38h], eax
0x18000bcba  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x18000bcbf  mov     rax, [rdi+4D0h]
0x18000bcc6  mov     rcx, [rax+20h]
0x18000bcca  mov     eax, [rsi+10h]
0x18000bccd  test    eax, eax
0x18000bccf  jz      short loc_18000BCD6
0x18000bcd1  sub     eax, [rcx+24h]
0x18000bcd4  jmp     short loc_18000BCD8
0x18000bcd6  xor     eax, eax
0x18000bcd8  mov     rcx, [rcx+18h]; this
0x18000bcdc  test    rcx, rcx
0x18000bcdf  jz      short loc_18000BCFA
0x18000bce1  cmp     qword ptr [rcx], 0
0x18000bce5  jz      short loc_18000BCFA
0x18000bce7  mov     rax, [rcx+rax*8]
0x18000bceb  mov     ecx, [rax+14h]
0x18000bcee  cmp     ecx, [rax+10h]
0x18000bcf1  jnb     short loc_18000BCFA
0x18000bcf3  mov     edx, [rax+18h]
0x18000bcf6  add     edx, ecx
0x18000bcf8  jmp     short loc_18000BCFC
0x18000bcfa  xor     edx, edx; unsigned int
0x18000bcfc  xor     r8d, r8d; int
0x18000bcff  call    ?CreateCipherInfo@CACSecurityPage@@AEAAPEAU_AUI_CIPHER_INFO@@KH@Z; CACSecurityPage::CreateCipherInfo(ulong,int)
0x18000bd04  mov     rbx, rax
0x18000bd07  xor     eax, eax
0x18000bd09  cmp     [rsi+0Ch], eax
0x18000bd0c  jz      short loc_18000BD2A
0x18000bd0e  cmp     [rsi], eax
0x18000bd10  jnz     short loc_18000BD2A
0x18000bd12  mov     r9, rbx; struct _AUI_CIPHER_INFO *
0x18000bd15  mov     [rsp+78h+var_58], eax; int
0x18000bd19  lea     r8d, [rax+1]; int
0x18000bd1d  mov     rdx, rsi; struct _AUI_AUTH_INFO *
0x18000bd20  mov     rcx, rdi; this
0x18000bd23  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x18000bd28  jmp     short loc_18000BD3E
0x18000bd2a  mov     r9, rbx; struct _AUI_CIPHER_INFO *
0x18000bd2d  mov     r8d, 1; int
0x18000bd33  mov     rdx, rsi; struct _AUI_AUTH_INFO *
0x18000bd36  mov     rcx, rdi; this
0x18000bd39  call    ?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)
0x18000bd3e  call    cs:__imp_GetProcessHeap
0x18000bd44  mov     r8, rbx; lpMem
0x18000bd47  xor     edx, edx; dwFlags
0x18000bd49  mov     rcx, rax; hHeap
0x18000bd4c  call    cs:__imp_HeapFree
0x18000bd52  test    r15, r15
0x18000bd55  jz      short loc_18000BD60
0x18000bd57  mov     rcx, r15; bstrString
0x18000bd5a  call    cs:__imp_SysFreeString
0x18000bd60  mov     eax, r14d
0x18000bd63  jmp     short loc_18000BD67
0x18000bd65  xor     eax, eax
0x18000bd67  mov     rbx, [rsp+78h+arg_8]
0x18000bd6f  add     rsp, 40h
0x18000bd73  pop     r15
0x18000bd75  pop     r14
0x18000bd77  pop     r13
0x18000bd79  pop     r12
0x18000bd7b  pop     rdi
0x18000bd7c  pop     rsi
0x18000bd7d  pop     rbp
0x18000bd7e  retn
```
