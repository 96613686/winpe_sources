# CInfraConnectPage::OnSetActive(void)

- ea: `0x180021a70`
- end: `0x180021c8f`
- name: `?OnSetActive@CInfraConnectPage@@QEAA_JXZ`
- size: `543`
- prototype: `__int64 __fastcall(CInfraConnectPage *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000883c`

## callees

- `0x1800079b0`
- `0x180020800`
- `0x180021194`
- `0x1800213d4`
- `0x180021a70`
- `0x180022080`
- `0x180022208`
- `0x180022a54`
- `0x180023054`

## import_xrefs

- `USER32!PostMessageW` at `0x180021af4`
- `USER32!PostMessageW` at `0x180021b09`
- `USER32!PostMessageW` at `0x180021af4`
- `USER32!PostMessageW` at `0x180021b09`
- `USER32!ShowWindow` at `0x180021bb1`
- `USER32!ShowWindow` at `0x180021bb1`
- `USER32!GetParent` at `0x180021ac2`
- `USER32!GetParent` at `0x180021ac2`
- `wlanapi!WlanCloseHandle` at `0x180021b85`
- `wlanapi!WlanCloseHandle` at `0x180021b85`
- `wlanapi!WlanGetSecuritySettings` at `0x180021b60`
- `wlanapi!WlanGetSecuritySettings` at `0x180021b60`
- `wlanapi!WlanFreeMemory` at `0x180021b94`
- `wlanapi!WlanFreeMemory` at `0x180021b94`
- `wlanapi!WlanOpenHandle` at `0x180021b3d`
- `wlanapi!WlanOpenHandle` at `0x180021b3d`

## pseudocode

```c
GUID *__fastcall CInfraConnectPage::OnSetActive(HWND *this)
{
  HWND Parent; // rdi
  HWND v3; // r14
  bool v4; // di
  DWORD SecuritySettings; // ebx
  int v6; // ebx
  GUID *v7; // rdi
  _BYTE v9[16]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pdwGrantedAccess; // [rsp+70h] [rbp+30h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+78h] [rbp+38h] BYREF
  void *phClientHandle; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR pstrCurrentSDDL; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  Parent = GetParent(this[13]);
  v3 = *(HWND *)ATL::CWindow::GetDlgItem(this + 13, v9, 10335);
  PostMessageW(Parent, 0x470u, 0, 19);
  PostMessageW(Parent, 0x48Au, 0x13u, 22);
  pstrCurrentSDDL = 0;
  phClientHandle = 0;
  pdwGrantedAccess = 0;
  pdwNegotiatedVersion = 0;
  v4 = 0;
  SecuritySettings = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( !SecuritySettings )
  {
    SecuritySettings = WlanGetSecuritySettings(
                         phClientHandle,
                         wlan_secure_add_new_all_user_profiles,
                         0,
                         &pstrCurrentSDDL,
                         &pdwGrantedAccess);
    if ( !SecuritySettings )
      v4 = (~pdwGrantedAccess & 0x70023) == 0;
  }
  if ( phClientHandle )
    WlanCloseHandle(phClientHandle, 0);
  if ( pstrCurrentSDDL )
    WlanFreeMemory(pstrCurrentSDDL);
  if ( !SecuritySettings && (v4 || !*((_BYTE *)this + 1507)) )
    ShowWindow(v3, 0);
  CInfraConnectPage::RepositionControls((CInfraConnectPage *)this);
  CInfraConnectPage::SetData((CInfraConnectPage *)this);
  v6 = CInfraConnectPage::InitializeAuthCipherPairs((CInfraConnectPage *)this);
  if ( v6 < 0 )
  {
    *((_DWORD *)this[189] + 15) = v6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145)
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        11,
        WPP_1064fdabddc73196039d87943bb008b3_Traceguids,
        (unsigned int)v6);
    }
  }
  else
  {
    CInfraConnectPage::InitAuthCipherCombos((CInfraConnectPage *)this);
  }
  CInfraConnectPage::UpdatePasswordToolTipText((CInfraConnectPage *)this);
  v7 = &CLSID_InfraErrorPage;
  *((_BYTE *)this + 1501) = 0;
  if ( v6 >= 0 )
    v7 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 12, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x180021a70  push    rbp
0x180021a72  push    rbx
0x180021a73  push    rsi
0x180021a74  push    rdi
0x180021a75  push    r14
0x180021a77  mov     rbp, rsp
0x180021a7a  sub     rsp, 40h
0x180021a7e  mov     rsi, rcx
0x180021a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a88  lea     rax, WPP_GLOBAL_Control
0x180021a8f  cmp     rcx, rax
0x180021a92  jz      short loc_180021ABE
0x180021a94  cmp     byte ptr [rcx+91h], 4
0x180021a9b  jb      short loc_180021ABE
0x180021a9d  test    byte ptr [rcx+94h], 1
0x180021aa4  jz      short loc_180021ABE
0x180021aa6  mov     rcx, [rcx+88h]
0x180021aad  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180021ab4  mov     edx, 0Ah
0x180021ab9  call    WPP_SF_
0x180021abe  mov     rcx, [rsi+68h]; hWnd
0x180021ac2  call    cs:__imp_GetParent
0x180021ac8  mov     r8d, 285Fh
0x180021ace  lea     rdx, [rbp+var_10]
0x180021ad2  lea     rcx, [rsi+68h]
0x180021ad6  mov     rdi, rax
0x180021ad9  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180021ade  mov     ebx, 13h
0x180021ae3  xor     r8d, r8d; wParam
0x180021ae6  mov     r9d, ebx; lParam
0x180021ae9  mov     edx, 470h; Msg
0x180021aee  mov     rcx, rdi; hWnd
0x180021af1  mov     r14, [rax]
0x180021af4  call    cs:__imp_PostMessageW
0x180021afa  lea     r9d, [rbx+3]; lParam
0x180021afe  mov     r8d, ebx; wParam
0x180021b01  mov     edx, 48Ah; Msg
0x180021b06  mov     rcx, rdi; hWnd
0x180021b09  call    cs:__imp_PostMessageW
0x180021b0f  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180021b13  mov     [rbp+pstrCurrentSDDL], 0
0x180021b1b  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180021b1f  mov     [rbp+phClientHandle], 0
0x180021b27  xor     edx, edx; pReserved
0x180021b29  mov     [rbp+arg_0], 0
0x180021b30  lea     ecx, [rbx-11h]; dwClientVersion
0x180021b33  mov     [rbp+pdwNegotiatedVersion], 0
0x180021b3a  xor     dil, dil
0x180021b3d  call    cs:__imp_WlanOpenHandle
0x180021b43  mov     ebx, eax
0x180021b45  test    eax, eax
0x180021b47  jnz     short loc_180021B7A
0x180021b49  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180021b4d  lea     rax, [rbp+arg_0]
0x180021b51  lea     r9, [rbp+pstrCurrentSDDL]; pstrCurrentSDDL
0x180021b55  mov     [rsp+40h+pdwGrantedAccess], rax; pdwGrantedAccess
0x180021b5a  xor     r8d, r8d; pValueType
0x180021b5d  lea     edx, [rbx+9]; SecurableObject
0x180021b60  call    cs:__imp_WlanGetSecuritySettings
0x180021b66  mov     ebx, eax
0x180021b68  test    eax, eax
0x180021b6a  jnz     short loc_180021B7A
0x180021b6c  mov     eax, [rbp+arg_0]
0x180021b6f  not     eax
0x180021b71  test    eax, 70023h
0x180021b76  setz    dil
0x180021b7a  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180021b7e  test    rcx, rcx
0x180021b81  jz      short loc_180021B8B
0x180021b83  xor     edx, edx; pReserved
0x180021b85  call    cs:__imp_WlanCloseHandle
0x180021b8b  mov     rcx, [rbp+pstrCurrentSDDL]; pMemory
0x180021b8f  test    rcx, rcx
0x180021b92  jz      short loc_180021B9A
0x180021b94  call    cs:__imp_WlanFreeMemory
0x180021b9a  test    ebx, ebx
0x180021b9c  jnz     short loc_180021BB7
0x180021b9e  test    dil, dil
0x180021ba1  jnz     short loc_180021BAC
0x180021ba3  cmp     [rsi+5E3h], dil
0x180021baa  jnz     short loc_180021BB7
0x180021bac  xor     edx, edx; nCmdShow
0x180021bae  mov     rcx, r14; hWnd
0x180021bb1  call    cs:__imp_ShowWindow
0x180021bb7  mov     rcx, rsi; this
0x180021bba  call    ?RepositionControls@CInfraConnectPage@@AEAAXXZ; CInfraConnectPage::RepositionControls(void)
0x180021bbf  mov     rcx, rsi; this
0x180021bc2  call    ?SetData@CInfraConnectPage@@AEAAXXZ; CInfraConnectPage::SetData(void)
0x180021bc7  mov     rcx, rsi; this
0x180021bca  call    ?InitializeAuthCipherPairs@CInfraConnectPage@@AEAAJXZ; CInfraConnectPage::InitializeAuthCipherPairs(void)
0x180021bcf  mov     ebx, eax
0x180021bd1  test    eax, eax
0x180021bd3  js      short loc_180021BE6
0x180021bd5  mov     rcx, rsi; this
0x180021bd8  call    ?InitAuthCipherCombos@CInfraConnectPage@@AEAAXXZ; CInfraConnectPage::InitAuthCipherCombos(void)
0x180021bdd  lea     r14, WPP_GLOBAL_Control
0x180021be4  jmp     short loc_180021C30
0x180021be6  mov     rax, [rsi+5E8h]
0x180021bed  mov     [rax+3Ch], ebx
0x180021bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bf7  lea     r14, WPP_GLOBAL_Control
0x180021bfe  cmp     rcx, r14
0x180021c01  jz      short loc_180021C30
0x180021c03  cmp     byte ptr [rcx+91h], 1
0x180021c0a  jb      short loc_180021C30
0x180021c0c  test    byte ptr [rcx+94h], 1
0x180021c13  jz      short loc_180021C30
0x180021c15  mov     rcx, [rcx+88h]
0x180021c1c  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180021c23  mov     edx, 0Bh
0x180021c28  mov     r9d, ebx
0x180021c2b  call    WPP_SF_d
0x180021c30  mov     rcx, rsi; this
0x180021c33  call    ?UpdatePasswordToolTipText@CInfraConnectPage@@AEAAXXZ; CInfraConnectPage::UpdatePasswordToolTipText(void)
0x180021c38  xor     eax, eax
0x180021c3a  lea     rdi, CLSID_InfraErrorPage
0x180021c41  test    ebx, ebx
0x180021c43  mov     [rsi+5DDh], al
0x180021c49  cmovns  rdi, rax
0x180021c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c54  cmp     rcx, r14
0x180021c57  jz      short loc_180021C81
0x180021c59  cmp     byte ptr [rcx+91h], 4
0x180021c60  jb      short loc_180021C81
0x180021c62  test    byte ptr [rcx+94h], 1
0x180021c69  jz      short loc_180021C81
0x180021c6b  mov     rcx, [rcx+88h]
0x180021c72  lea     edx, [rax+0Ch]
0x180021c75  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180021c7c  call    WPP_SF_
0x180021c81  mov     rax, rdi
0x180021c84  add     rsp, 40h
0x180021c88  pop     r14
0x180021c8a  pop     rdi
0x180021c8b  pop     rsi
0x180021c8c  pop     rbx
0x180021c8d  pop     rbp
0x180021c8e  retn
```
