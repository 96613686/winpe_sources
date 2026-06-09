# CUAMSettingsPageElement::_CustomizeErrorStateDUI(bool)

- ea: `0x180029a1c`
- end: `0x180029ca0`
- name: `?_CustomizeErrorStateDUI@CUAMSettingsPageElement@@AEAAX_N@Z`
- size: `644`
- prototype: `void __fastcall(CUAMSettingsPageElement *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027dd0`
- `0x1800296e0`

## callees

- `0x180024948`
- `0x180029a1c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029a9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029a9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029bd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029bd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c65`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029bdd`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029c5c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029c77`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029c82`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029bdd`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029c5c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029c77`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029c82`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029bbc`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029c07`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029c50`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029bbc`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029c07`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029c50`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029bc8`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029c13`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029bc8`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029c13`
- `DUI70!StrToID` at `0x180029a42`
- `DUI70!StrToID` at `0x180029a5e`
- `DUI70!StrToID` at `0x180029a42`
- `DUI70!StrToID` at `0x180029a5e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180029a4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180029a6a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180029a4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180029a6a`
- `USER32!GetSystemMetrics` at `0x180029c2c`
- `USER32!GetSystemMetrics` at `0x180029c2c`

## string_xrefs

- `0x180029a54`: `idUAMSettingsPageErrorStateLink`

## pseudocode

```c
void __fastcall CUAMSettingsPageElement::_CustomizeErrorStateDUI(CUAMSettingsPageElement *this, char a2)
{
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rdi
  unsigned __int16 v6; // ax
  DirectUI::Element *v7; // rsi
  HRESULT v8; // ebx
  LPVOID v9; // rcx
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r14
  const unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rbx
  int v18; // edx
  unsigned __int16 *v19; // rbx
  _DWORD v20[12]; // [rsp+30h] [rbp-19h]
  _DWORD v21[12]; // [rsp+60h] [rbp+17h]
  LPVOID ppv; // [rsp+C0h] [rbp+77h] BYREF

  v4 = StrToID(L"idUAMSettingsPageErrorText");
  Descendent = DirectUI::Element::FindDescendent(this, v4);
  v6 = StrToID(L"idUAMSettingsPageErrorStateLink");
  v7 = DirectUI::Element::FindDescendent(this, v6);
  if ( a2 )
  {
    ppv = 0;
    v8 = CoCreateInstance(&CLSID_ConnectedAccountStateChange, 0, 1u, &GUID_b5b0b6cf_ea52_4922_9376_695634758329, &ppv);
    if ( v8 >= 0 )
      v8 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)ppv + 32LL))(ppv, (char *)this + 248);
    v9 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    if ( v8 < 0 )
      goto LABEL_19;
  }
  v10 = *((_DWORD *)this + 62);
  if ( v10 <= 0 || v10 >= 12 )
  {
LABEL_19:
    if ( GetSystemMetrics(67) )
    {
      v19 = (unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 2195);
      DirectUI::Element::SetContentString(Descendent, v19);
      DirectUI::Element::SetLayoutPos(Descendent, -1);
      LocalFree(v19);
      return;
    }
    DirectUI::Element::SetLayoutPos(Descendent, -3);
    v18 = -3;
    goto LABEL_16;
  }
  v11 = v10 - 1;
  v20[0] = 2901;
  v20[1] = 2903;
  v20[2] = 2905;
  v20[3] = 2907;
  v20[4] = 2909;
  v20[5] = 2911;
  v20[6] = 2913;
  v20[7] = 2915;
  v20[8] = 2917;
  v20[9] = 2919;
  v20[10] = 2921;
  v12 = LOWORD(v20[v11]);
  v21[0] = 2902;
  v21[1] = 2904;
  v21[2] = 2906;
  v21[3] = 2908;
  v21[4] = 2910;
  v21[5] = 2912;
  v21[6] = 2914;
  v21[7] = 2916;
  v21[8] = 2918;
  v21[9] = 2920;
  v21[10] = 2922;
  v13 = v11;
  v14 = (const unsigned __int16 *)ShellConstructMessageStringW(g_hinst, v12);
  v15 = (unsigned __int16 *)v14;
  if ( v14 )
  {
    DirectUI::Element::SetContentString(Descendent, v14);
    DirectUI::Element::SetAccName(Descendent, v15);
    LocalFree(v15);
    DirectUI::Element::SetLayoutPos(Descendent, -1);
  }
  v16 = (const unsigned __int16 *)ShellConstructMessageStringW(g_hinst, LOWORD(v21[v13]));
  v17 = (unsigned __int16 *)v16;
  if ( v16 )
  {
    DirectUI::Element::SetContentString(v7, v16);
    DirectUI::Element::SetAccName(v7, v17);
    LocalFree(v17);
    v18 = -1;
LABEL_16:
    DirectUI::Element::SetLayoutPos(v7, v18);
  }
}

```

## disassembly

```asm
0x180029a1c  mov     [rsp-8+arg_0], rbx
0x180029a21  mov     [rsp-8+arg_8], rsi
0x180029a26  push    rbp
0x180029a27  push    rdi
0x180029a28  push    r14
0x180029a2a  lea     rbp, [rsp-47h]
0x180029a2f  sub     rsp, 90h
0x180029a36  mov     r14, rcx
0x180029a39  mov     bl, dl
0x180029a3b  lea     rcx, aIduamsettingsp_1; "idUAMSettingsPageErrorText"
0x180029a42  call    cs:__imp_StrToID
0x180029a48  movzx   edx, ax
0x180029a4b  mov     rcx, r14
0x180029a4e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180029a54  lea     rcx, aIduamsettingsp_0; "idUAMSettingsPageErrorStateLink"
0x180029a5b  mov     rdi, rax
0x180029a5e  call    cs:__imp_StrToID
0x180029a64  movzx   edx, ax
0x180029a67  mov     rcx, r14
0x180029a6a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180029a70  mov     rsi, rax
0x180029a73  test    bl, bl
0x180029a75  jz      short loc_180029AE6
0x180029a77  xor     edx, edx; pUnkOuter
0x180029a79  mov     [rbp+57h+arg_10], 0
0x180029a81  lea     rax, [rbp+57h+arg_10]
0x180029a85  lea     r9, _GUID_b5b0b6cf_ea52_4922_9376_695634758329; riid
0x180029a8c  mov     [rsp+0A0h+ppv], rax; ppv
0x180029a91  lea     rcx, CLSID_ConnectedAccountStateChange; rclsid
0x180029a98  lea     r8d, [rdx+1]; dwClsContext
0x180029a9c  call    cs:__imp_CoCreateInstance
0x180029aa2  mov     ebx, eax
0x180029aa4  test    eax, eax
0x180029aa6  js      short loc_180029AC1
0x180029aa8  mov     rcx, [rbp+57h+arg_10]
0x180029aac  lea     rdx, [r14+0F8h]
0x180029ab3  mov     rax, [rcx]
0x180029ab6  mov     rax, [rax+20h]
0x180029aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029abf  mov     ebx, eax
0x180029ac1  mov     rcx, [rbp+57h+arg_10]
0x180029ac5  test    rcx, rcx
0x180029ac8  jz      short loc_180029ADE
0x180029aca  mov     [rbp+57h+arg_10], 0
0x180029ad2  mov     rax, [rcx]
0x180029ad5  mov     rax, [rax+10h]
0x180029ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ade  test    ebx, ebx
0x180029ae0  js      loc_180029C27
0x180029ae6  mov     eax, [r14+0F8h]
0x180029aed  test    eax, eax
0x180029aef  jle     loc_180029C27
0x180029af5  cmp     eax, 0Ch
0x180029af8  jge     loc_180029C27
0x180029afe  mov     rcx, cs:g_hinst
0x180029b05  dec     eax
0x180029b07  mov     [rbp+57h+var_70], 0B55h
0x180029b0e  mov     [rbp+57h+var_6C], 0B57h
0x180029b15  mov     [rbp+57h+var_68], 0B59h
0x180029b1c  mov     [rbp+57h+var_64], 0B5Bh
0x180029b23  mov     [rbp+57h+var_60], 0B5Dh
0x180029b2a  mov     [rbp+57h+var_5C], 0B5Fh
0x180029b31  mov     [rbp+57h+var_58], 0B61h
0x180029b38  mov     [rbp+57h+var_54], 0B63h
0x180029b3f  mov     [rbp+57h+var_50], 0B65h
0x180029b46  mov     [rbp+57h+var_4C], 0B67h
0x180029b4d  mov     [rbp+57h+var_48], 0B69h
0x180029b54  movzx   edx, word ptr [rbp+rax*4+57h+var_70]
0x180029b59  mov     [rbp+57h+var_40], 0B56h
0x180029b60  mov     [rbp+57h+var_3C], 0B58h
0x180029b67  mov     [rbp+57h+var_38], 0B5Ah
0x180029b6e  mov     [rbp+57h+var_34], 0B5Ch
0x180029b75  mov     [rbp+57h+var_30], 0B5Eh
0x180029b7c  mov     [rbp+57h+var_2C], 0B60h
0x180029b83  mov     [rbp+57h+var_28], 0B62h
0x180029b8a  mov     [rbp+57h+var_24], 0B64h
0x180029b91  mov     [rbp+57h+var_20], 0B66h
0x180029b98  mov     [rbp+57h+var_1C], 0B68h
0x180029b9f  mov     [rbp+57h+var_18], 0B6Ah
0x180029ba6  mov     r14d, eax
0x180029ba9  call    ShellConstructMessageStringW
0x180029bae  mov     rbx, rax
0x180029bb1  test    rax, rax
0x180029bb4  jz      short loc_180029BE3
0x180029bb6  mov     rdx, rax
0x180029bb9  mov     rcx, rdi
0x180029bbc  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180029bc2  mov     rdx, rbx
0x180029bc5  mov     rcx, rdi
0x180029bc8  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180029bce  mov     rcx, rbx; hMem
0x180029bd1  call    cs:__imp_LocalFree
0x180029bd7  or      edx, 0FFFFFFFFh
0x180029bda  mov     rcx, rdi
0x180029bdd  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180029be3  movzx   edx, word ptr [rbp+r14*4+57h+var_40]
0x180029be9  mov     rcx, cs:g_hinst
0x180029bf0  call    ShellConstructMessageStringW
0x180029bf5  mov     rbx, rax
0x180029bf8  test    rax, rax
0x180029bfb  jz      loc_180029C88
0x180029c01  mov     rdx, rax
0x180029c04  mov     rcx, rsi
0x180029c07  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180029c0d  mov     rdx, rbx
0x180029c10  mov     rcx, rsi
0x180029c13  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180029c19  mov     rcx, rbx; hMem
0x180029c1c  call    cs:__imp_LocalFree
0x180029c22  or      edx, 0FFFFFFFFh
0x180029c25  jmp     short loc_180029C7F
0x180029c27  mov     ecx, 43h ; 'C'; nIndex
0x180029c2c  call    cs:__imp_GetSystemMetrics
0x180029c32  test    eax, eax
0x180029c34  jz      short loc_180029C6D
0x180029c36  mov     rcx, cs:g_hinst
0x180029c3d  mov     edx, 893h
0x180029c42  call    ShellConstructMessageStringW
0x180029c47  mov     rdx, rax
0x180029c4a  mov     rcx, rdi
0x180029c4d  mov     rbx, rax
0x180029c50  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180029c56  or      edx, 0FFFFFFFFh
0x180029c59  mov     rcx, rdi
0x180029c5c  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180029c62  mov     rcx, rbx; hMem
0x180029c65  call    cs:__imp_LocalFree
0x180029c6b  jmp     short loc_180029C88
0x180029c6d  mov     ebx, 0FFFFFFFDh
0x180029c72  mov     rcx, rdi
0x180029c75  mov     edx, ebx
0x180029c77  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180029c7d  mov     edx, ebx
0x180029c7f  mov     rcx, rsi
0x180029c82  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180029c88  lea     r11, [rsp+0A0h+var_10]
0x180029c90  mov     rbx, [r11+20h]
0x180029c94  mov     rsi, [r11+28h]
0x180029c98  mov     rsp, r11
0x180029c9b  pop     r14
0x180029c9d  pop     rdi
0x180029c9e  pop     rbp
0x180029c9f  retn
```
