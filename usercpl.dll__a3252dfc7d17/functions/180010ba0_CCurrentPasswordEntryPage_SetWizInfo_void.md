# CCurrentPasswordEntryPage::SetWizInfo(void)

- ea: `0x180010ba0`
- end: `0x180010ecd`
- name: `?SetWizInfo@CCurrentPasswordEntryPage@@MEAAJXZ`
- size: `813`
- prototype: `__int64 __fastcall(CCurrentPasswordEntryPage *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006f2c`
- `0x180010ba0`
- `0x18001247c`
- `0x1800124c4`
- `0x18002503c`
- `0x180069000`
- `0x1800692f4`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010be8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010c0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010cae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010be8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010c0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010cae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010e8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010e9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010e8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010e9b`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180010c6c`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180010c6c`
- `DUI70!?SetMaxLength@Edit@DirectUI@@QEAAJH@Z` at `0x180010c56`
- `DUI70!?SetMaxLength@Edit@DirectUI@@QEAAJH@Z` at `0x180010c56`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010e30`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010e67`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010e30`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010e67`
- `DUI70!StrToID` at `0x180010c31`
- `DUI70!StrToID` at `0x180010e16`
- `DUI70!StrToID` at `0x180010e4d`
- `DUI70!StrToID` at `0x180010c31`
- `DUI70!StrToID` at `0x180010e16`
- `DUI70!StrToID` at `0x180010e4d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010c3d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010e22`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010e59`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010c3d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010e22`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010e59`
- `USER32!SendMessageW` at `0x180010dda`
- `USER32!SendMessageW` at `0x180010dda`

## pseudocode

```c
__int64 __fastcall CCurrentPasswordEntryPage::SetWizInfo(WCHAR *this)
{
  __int64 v1; // r14
  signed int CurrentLoggedInInfo; // edi
  DirectUI::Element *v4; // rbx
  unsigned __int16 v5; // ax
  DirectUI::Edit *Descendent; // rax
  DirectUI::Element *v7; // r15
  UINT v8; // edx
  __int64 v9; // r13
  int String; // ebx
  void *v11; // rcx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rdx
  WCHAR *v14; // rax
  WCHAR *v15; // rdx
  HWND v16; // rax
  CUserAccountWizardBase *v17; // rcx
  DirectUI::Element *v18; // rbx
  unsigned __int16 v19; // ax
  DirectUI::Element *v20; // rax
  DirectUI::Element *v21; // rbx
  unsigned __int16 v22; // ax
  DirectUI::Element *v23; // rax
  int v24; // r9d
  void *v25; // rcx
  struct IPropertyStore *v26; // rcx
  struct IPropertyStore *v28; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[256]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v31[256]; // [rsp+230h] [rbp+130h] BYREF

  v1 = 256;
  if ( LoadStringW(g_hinst, 0xB3u, this + 52, 256) )
    CurrentLoggedInInfo = LoadStringW(g_hinst, 0xB4u, this + 308, 512) == 0 ? 0x80004005 : 0;
  else
    CurrentLoggedInInfo = -2147467259;
  v4 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v5 = StrToID(L"passwordbox");
  Descendent = DirectUI::Element::FindDescendent(v4, v5);
  v7 = Descendent;
  if ( CurrentLoggedInInfo >= 0 )
  {
    CurrentLoggedInInfo = DirectUI::Edit::SetMaxLength(Descendent, 127);
    if ( CurrentLoggedInInfo >= 0 )
    {
      CurrentLoggedInInfo = DirectUI::Element::AddListener(v7, (struct DirectUI::IElementListener *)this);
      if ( CurrentLoggedInInfo >= 0 )
      {
        if ( *((_DWORD *)this + 22) == 1 )
        {
          v8 = 182;
        }
        else
        {
          if ( *((_DWORD *)this + 22) != 3 )
            return (unsigned int)-2147418113;
          v8 = 183;
        }
        if ( LoadStringW(g_hinst, v8, Buffer, 256) )
        {
          CurrentLoggedInInfo = 0;
          if ( *((_DWORD *)this + 22) == 3 )
          {
            v9 = *((_QWORD *)this + 12);
            if ( (int)SHGetConnectedIdentityProviderForCurrentUser((GUID *)(v9 + 6652)) >= 0 )
            {
              v28 = 0;
              String = SHGetIdentityProviderPropertyStore((const struct _GUID *)(v9 + 6652), &v28);
              if ( String >= 0 )
              {
                v11 = *(void **)(v9 + 6672);
                *(_QWORD *)(v9 + 6672) = 0;
                CoTaskMemFree(v11);
                String = IPropertyStore_GetString(v28, &PKEY_IdentityProvider_Name, v9 + 6672);
              }
              if ( v28 )
                ((void (__fastcall *)(struct IPropertyStore *))v28->lpVtbl->Release)(v28);
              if ( String >= 0 )
              {
                CurrentLoggedInInfo = StringCchPrintfW(
                                        v31,
                                        0x100u,
                                        Buffer,
                                        *(_QWORD *)(*((_QWORD *)this + 12) + 6672LL));
                if ( CurrentLoggedInInfo >= 0 )
                {
                  v12 = 2147483646;
                  v13 = v31;
                  v14 = Buffer;
                  do
                  {
                    if ( !v12 )
                      break;
                    if ( !*v13 )
                      break;
                    *v14++ = *v13++;
                    --v12;
                    --v1;
                  }
                  while ( v1 );
                  v15 = v14 - 1;
                  if ( v1 )
                    v15 = v14;
                  CurrentLoggedInInfo = v1 == 0 ? 0x8007007A : 0;
                  *v15 = 0;
                }
              }
            }
          }
          v16 = (HWND)(*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v7 + 360LL))(v7);
          SendMessageW(v16, 0x1501u, 1u, (LPARAM)Buffer);
          if ( CurrentLoggedInInfo >= 0 )
          {
            v17 = (CUserAccountWizardBase *)*((_QWORD *)this + 12);
            v28 = 0;
            pv = 0;
            CurrentLoggedInInfo = CUserAccountWizardBase::GetCurrentLoggedInInfo(
                                    v17,
                                    (unsigned __int16 **)&v28,
                                    (unsigned __int16 **)&pv);
            if ( CurrentLoggedInInfo >= 0 )
            {
              v18 = (DirectUI::Element *)*((_QWORD *)this + 8);
              v19 = StrToID(L"username");
              v20 = DirectUI::Element::FindDescendent(v18, v19);
              CurrentLoggedInInfo = DirectUI::Element::SetContentString(v20, (const unsigned __int16 *)v28);
              if ( CurrentLoggedInInfo >= 0 && *((_DWORD *)this + 22) == 3 )
              {
                v21 = (DirectUI::Element *)*((_QWORD *)this + 8);
                v22 = StrToID(L"connectedinfosubtitle");
                v23 = DirectUI::Element::FindDescendent(v21, v22);
                CurrentLoggedInInfo = DirectUI::Element::SetContentString(v23, (const unsigned __int16 *)pv);
                CWizardPageBase::CollapseExpand((CWizardPageBase *)this, L"connectedinfosubtitle", 1, v24);
              }
            }
            v25 = pv;
            pv = 0;
            CoTaskMemFree(v25);
            v26 = v28;
            v28 = 0;
            CoTaskMemFree(v26);
          }
        }
        else
        {
          return (unsigned int)-2147467259;
        }
      }
    }
  }
  return (unsigned int)CurrentLoggedInInfo;
}

```

## disassembly

```asm
0x180010ba0  push    rbp
0x180010ba2  push    rbx
0x180010ba3  push    rsi
0x180010ba4  push    rdi
0x180010ba5  push    r12
0x180010ba7  push    r13
0x180010ba9  push    r14
0x180010bab  push    r15
0x180010bad  lea     rbp, [rsp-348h]
0x180010bb5  sub     rsp, 448h
0x180010bbc  mov     rax, cs:__security_cookie
0x180010bc3  xor     rax, rsp
0x180010bc6  mov     [rbp+380h+var_50], rax
0x180010bcd  mov     r14d, 100h
0x180010bd3  lea     r8, [rcx+68h]; lpBuffer
0x180010bd7  mov     rsi, rcx
0x180010bda  mov     r9d, r14d; cchBufferMax
0x180010bdd  mov     rcx, cs:g_hinst; hInstance
0x180010be4  lea     edx, [r14-4Dh]; uID
0x180010be8  call    cs:__imp_LoadStringW
0x180010bee  xor     r12d, r12d
0x180010bf1  test    eax, eax
0x180010bf3  jz      short loc_180010C21
0x180010bf5  mov     rcx, cs:g_hinst; hInstance
0x180010bfc  lea     r8, [rsi+268h]; lpBuffer
0x180010c03  lea     edx, [r14-4Ch]; uID
0x180010c07  mov     r9d, 200h; cchBufferMax
0x180010c0d  call    cs:__imp_LoadStringW
0x180010c13  neg     eax
0x180010c15  sbb     edi, edi
0x180010c17  not     edi
0x180010c19  and     edi, 80004005h
0x180010c1f  jmp     short loc_180010C26
0x180010c21  mov     edi, 80004005h
0x180010c26  mov     rbx, [rsi+40h]
0x180010c2a  lea     rcx, aPasswordbox; "passwordbox"
0x180010c31  call    cs:__imp_StrToID
0x180010c37  movzx   edx, ax
0x180010c3a  mov     rcx, rbx
0x180010c3d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010c43  mov     r15, rax
0x180010c46  test    edi, edi
0x180010c48  js      loc_180010EA8
0x180010c4e  mov     edx, 7Fh
0x180010c53  mov     rcx, rax
0x180010c56  call    cs:__imp_?SetMaxLength@Edit@DirectUI@@QEAAJH@Z; DirectUI::Edit::SetMaxLength(int)
0x180010c5c  mov     edi, eax
0x180010c5e  test    eax, eax
0x180010c60  js      loc_180010EA8
0x180010c66  mov     rdx, rsi
0x180010c69  mov     rcx, r15
0x180010c6c  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180010c72  mov     edi, eax
0x180010c74  test    eax, eax
0x180010c76  js      loc_180010EA8
0x180010c7c  mov     ecx, [rsi+58h]
0x180010c7f  sub     ecx, 1
0x180010c82  jz      short loc_180010C9A
0x180010c84  cmp     ecx, 2
0x180010c87  jz      short loc_180010C93
0x180010c89  mov     edi, 8000FFFFh
0x180010c8e  jmp     loc_180010EA8
0x180010c93  mov     edx, 0B7h
0x180010c98  jmp     short loc_180010C9F
0x180010c9a  mov     edx, 0B6h; uID
0x180010c9f  mov     rcx, cs:g_hinst; hInstance
0x180010ca6  lea     r8, [rsp+480h+Buffer]; lpBuffer
0x180010cab  mov     r9d, r14d; cchBufferMax
0x180010cae  call    cs:__imp_LoadStringW
0x180010cb4  test    eax, eax
0x180010cb6  jz      loc_180010EA3
0x180010cbc  cmp     dword ptr [rsi+58h], 3
0x180010cc0  mov     edi, r12d
0x180010cc3  jnz     loc_180010DB5
0x180010cc9  mov     r13, [rsi+60h]
0x180010ccd  lea     rbx, [r13+19FCh]
0x180010cd4  mov     rcx, rbx; pguid
0x180010cd7  call    ?SHGetConnectedIdentityProviderForCurrentUser@@YAJPEAU_GUID@@@Z; SHGetConnectedIdentityProviderForCurrentUser(_GUID *)
0x180010cdc  test    eax, eax
0x180010cde  js      loc_180010DB5
0x180010ce4  lea     rdx, [rsp+480h+var_460]; struct IPropertyStore **
0x180010ce9  mov     [rsp+480h+var_460], r12
0x180010cee  mov     rcx, rbx; struct _GUID *
0x180010cf1  call    ?SHGetIdentityProviderPropertyStore@@YAJAEBU_GUID@@PEAPEAUIPropertyStore@@@Z; SHGetIdentityProviderPropertyStore(_GUID const &,IPropertyStore * *)
0x180010cf6  mov     ebx, eax
0x180010cf8  test    eax, eax
0x180010cfa  js      short loc_180010D25
0x180010cfc  lea     rbx, [r13+1A10h]
0x180010d03  mov     rcx, [rbx]; pv
0x180010d06  mov     [rbx], r12
0x180010d09  call    cs:__imp_CoTaskMemFree
0x180010d0f  mov     rcx, [rsp+480h+var_460]
0x180010d14  lea     rdx, PKEY_IdentityProvider_Name
0x180010d1b  mov     r8, rbx
0x180010d1e  call    IPropertyStore_GetString
0x180010d23  mov     ebx, eax
0x180010d25  mov     rcx, [rsp+480h+var_460]
0x180010d2a  test    rcx, rcx
0x180010d2d  jz      short loc_180010D3B
0x180010d2f  mov     rax, [rcx]
0x180010d32  mov     rax, [rax+10h]
0x180010d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d3b  test    ebx, ebx
0x180010d3d  js      short loc_180010DB5
0x180010d3f  mov     r9, [rsi+60h]
0x180010d43  lea     r8, [rsp+480h+Buffer]; unsigned __int16 *
0x180010d48  mov     rdx, r14; unsigned __int64
0x180010d4b  lea     rcx, [rbp+380h+var_250]; unsigned __int16 *
0x180010d52  mov     r9, [r9+1A10h]
0x180010d59  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010d5e  mov     edi, eax
0x180010d60  test    eax, eax
0x180010d62  js      short loc_180010DB5
0x180010d64  mov     ecx, 7FFFFFFEh
0x180010d69  lea     rdx, [rbp+380h+var_250]
0x180010d70  lea     rax, [rsp+480h+Buffer]
0x180010d75  test    rcx, rcx
0x180010d78  jz      short loc_180010D99
0x180010d7a  movzx   r8d, word ptr [rdx]
0x180010d7e  test    r8w, r8w
0x180010d82  jz      short loc_180010D99
0x180010d84  mov     [rax], r8w
0x180010d88  add     rdx, 2
0x180010d8c  add     rax, 2
0x180010d90  dec     rcx
0x180010d93  sub     r14, 1
0x180010d97  jnz     short loc_180010D75
0x180010d99  test    r14, r14
0x180010d9c  lea     rdx, [rax-2]
0x180010da0  cmovnz  rdx, rax
0x180010da4  neg     r14
0x180010da7  sbb     edi, edi
0x180010da9  not     edi
0x180010dab  and     edi, 8007007Ah
0x180010db1  mov     [rdx], r12w
0x180010db5  mov     rax, [r15]
0x180010db8  mov     rcx, r15
0x180010dbb  mov     rax, [rax+168h]
0x180010dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dc7  mov     rcx, rax; hWnd
0x180010dca  lea     r9, [rsp+480h+Buffer]; lParam
0x180010dcf  mov     edx, 1501h; Msg
0x180010dd4  mov     r8d, 1; wParam
0x180010dda  call    cs:__imp_SendMessageW
0x180010de0  test    edi, edi
0x180010de2  js      loc_180010EA8
0x180010de8  mov     rcx, [rsi+60h]; this
0x180010dec  lea     r8, [rsp+480h+pv]; unsigned __int16 **
0x180010df1  lea     rdx, [rsp+480h+var_460]; unsigned __int16 **
0x180010df6  mov     [rsp+480h+var_460], r12
0x180010dfb  mov     [rsp+480h+pv], r12
0x180010e00  call    ?GetCurrentLoggedInInfo@CUserAccountWizardBase@@QEAAJPEAPEAG0@Z; CUserAccountWizardBase::GetCurrentLoggedInInfo(ushort * *,ushort * *)
0x180010e05  mov     edi, eax
0x180010e07  test    eax, eax
0x180010e09  js      short loc_180010E81
0x180010e0b  mov     rbx, [rsi+40h]
0x180010e0f  lea     rcx, pszStr2; "username"
0x180010e16  call    cs:__imp_StrToID
0x180010e1c  movzx   edx, ax
0x180010e1f  mov     rcx, rbx
0x180010e22  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010e28  mov     rdx, [rsp+480h+var_460]
0x180010e2d  mov     rcx, rax
0x180010e30  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180010e36  mov     edi, eax
0x180010e38  test    eax, eax
0x180010e3a  js      short loc_180010E81
0x180010e3c  cmp     dword ptr [rsi+58h], 3
0x180010e40  jnz     short loc_180010E81
0x180010e42  mov     rbx, [rsi+40h]
0x180010e46  lea     rcx, aConnectedinfos_0; "connectedinfosubtitle"
0x180010e4d  call    cs:__imp_StrToID
0x180010e53  movzx   edx, ax
0x180010e56  mov     rcx, rbx
0x180010e59  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010e5f  mov     rdx, [rsp+480h+pv]
0x180010e64  mov     rcx, rax
0x180010e67  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180010e6d  mov     r8b, 1; bool
0x180010e70  lea     rdx, aConnectedinfos_0; "connectedinfosubtitle"
0x180010e77  mov     rcx, rsi; this
0x180010e7a  mov     edi, eax
0x180010e7c  call    ?CollapseExpand@CWizardPageBase@@QEAAXPEBG_NH@Z; CWizardPageBase::CollapseExpand(ushort const *,bool,int)
0x180010e81  mov     rcx, [rsp+480h+pv]; pv
0x180010e86  mov     [rsp+480h+pv], r12
0x180010e8b  call    cs:__imp_CoTaskMemFree
0x180010e91  mov     rcx, [rsp+480h+var_460]; pv
0x180010e96  mov     [rsp+480h+var_460], r12
0x180010e9b  call    cs:__imp_CoTaskMemFree
0x180010ea1  jmp     short loc_180010EA8
0x180010ea3  mov     edi, 80004005h
0x180010ea8  mov     eax, edi
0x180010eaa  mov     rcx, [rbp+380h+var_50]
0x180010eb1  xor     rcx, rsp; StackCookie
0x180010eb4  call    __security_check_cookie
0x180010eb9  add     rsp, 448h
0x180010ec0  pop     r15
0x180010ec2  pop     r14
0x180010ec4  pop     r13
0x180010ec6  pop     r12
0x180010ec8  pop     rdi
0x180010ec9  pop     rsi
0x180010eca  pop     rbx
0x180010ecb  pop     rbp
0x180010ecc  retn
```
