# CZipWiz::_PerformExtraction(int)

- ea: `0x1800429f0`
- end: `0x180042cff`
- name: `?_PerformExtraction@CZipWiz@@AEAAJH@Z`
- size: `783`
- prototype: `__int64 __fastcall(struct IUnknown *this, int, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024cb4`

## callees

- `0x18002a740`
- `0x180036f50`
- `0x18003ef3c`
- `0x1800405b4`
- `0x180041fbc`
- `0x180042074`
- `0x1800425b4`
- `0x1800429f0`
- `0x180047cc8`
- `0x1800486f0`
- `0x1800488c8`
- `0x180071010`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x180042c97`
- `SHELL32!SHFileOperationW` at `0x180042c97`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180042afc`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180042afc`
- `SHELL32!__imp_ILFree` at `0x180042c0a`
- `SHELL32!__imp_ILFree` at `0x180042c0a`
- `SHELL32!__imp_SHCreateDirectory` at `0x180042a77`
- `SHELL32!__imp_SHCreateDirectory` at `0x180042a77`
- `SHLWAPI!PathRemoveBackslashW` at `0x180042c61`
- `SHLWAPI!PathRemoveBackslashW` at `0x180042c61`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042ad8`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042bcc`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042c53`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042ad8`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042bcc`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180042c53`
- `USER32!GetParent` at `0x180042b1b`
- `USER32!GetParent` at `0x180042b49`
- `USER32!GetParent` at `0x180042bd9`
- `USER32!GetParent` at `0x180042b1b`
- `USER32!GetParent` at `0x180042b49`
- `USER32!GetParent` at `0x180042bd9`
- `USER32!PostMessageW` at `0x180042bf0`
- `USER32!PostMessageW` at `0x180042bf0`
- `USER32!SendMessageW` at `0x180042b5d`
- `USER32!SendMessageW` at `0x180042b5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CZipWiz::_PerformExtraction(struct IUnknown *this, int a2, int a3, int a4)
{
  struct IUnknownVtbl *lpVtbl; // r8
  int FullDataObjectFromZip; // eax
  int v8; // ebx
  int v9; // eax
  char IsEnabled; // al
  __int64 v11; // rcx
  struct IUnknownVtbl *v12; // rdx
  struct IUnknownVtbl *v13; // rcx
  HWND Parent; // rax
  HWND v15; // rax
  unsigned int v16; // r8d
  const struct _POINTL *v17; // r9
  char v18; // al
  __int64 v19; // rcx
  struct IUnknownVtbl *v20; // rdx
  HWND v21; // rax
  char v22; // al
  __int64 v23; // rcx
  struct IUnknownVtbl *v24; // rdx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  struct IDataObject *v29; // [rsp+30h] [rbp-49h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-41h] BYREF
  struct _SHFILEOPSTRUCTW FileOp; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v32; // [rsp+78h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR ppidl; // [rsp+80h] [rbp+7h] BYREF

  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&ShellTraceId_ZipFolder_WizardExtractAll_Start, a3, a4, &ppidl);
  lpVtbl = this[133].lpVtbl;
  v29 = 0;
  FullDataObjectFromZip = CZipWiz::_GetFullDataObjectFromZip(
                            (CZipWiz *)this,
                            (const unsigned __int16 *)&this[1].lpVtbl + 2,
                            (HWND)lpVtbl,
                            &v29);
  v8 = FullDataObjectFromZip;
  if ( FullDataObjectFromZip >= 0 )
  {
    DataObj_SetAsyncMode(v29);
    if ( !a2 )
      goto LABEL_12;
    v9 = SHCreateDirectory(0, (PCWSTR)&this[66].lpVtbl + 2);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( v8 != -2147023673 )
      {
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
        v12 = this[133].lpVtbl;
        if ( IsEnabled )
          MessageBoxHelper::ShellMessageBoxTextScaled___2(v11, v12, 10101);
        else
          ShellMessageBoxW(g_hmodThisDll, (HWND)v12, (LPCWSTR)0x2775, (LPCWSTR)0x2747, 0x30u);
      }
    }
    else
    {
LABEL_12:
      ppidl.Ptr = 0;
      v8 = SHILCreateFromPath((PCWSTR)&this[66].lpVtbl + 2, (LPITEMIDLIST *)&ppidl, 0);
      if ( v8 < 0 )
      {
        v22 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
        v24 = this[133].lpVtbl;
        if ( v22 )
          MessageBoxHelper::ShellMessageBoxTextScaled___2(v23, v24, 10424);
        else
          ShellMessageBoxW(g_hmodThisDll, (HWND)v24, (LPCWSTR)0x28B8, (LPCWSTR)0x2747, 0x10u);
      }
      else
      {
        v13 = this[133].lpVtbl;
        punk = 0;
        Parent = GetParent((HWND)v13);
        v8 = SHGetUIObjectFromFullPIDL(ppidl.Ptr, Parent, &GUID_00000122_0000_0000_c000_000000000046, &punk);
        if ( v8 >= 0 )
        {
          v15 = GetParent((HWND)this[133].lpVtbl);
          SendMessageW(v15, 0x470u, 0, 0);
          v32 = 1;
          v8 = SHSimulateDropWithSite(punk, v29, v16, v17, &v32, this);
          if ( v8 == -2147417803 )
          {
            v18 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
            v20 = this[133].lpVtbl;
            if ( v18 )
              MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____0(v19, v20);
            else
              ShellMessageBoxW(
                g_hmodThisDll,
                (HWND)v20,
                (LPCWSTR)0x28BB,
                (LPCWSTR)0x2747,
                0x30u,
                (char *)&this[1].lpVtbl + 4);
          }
          v21 = GetParent((HWND)this[133].lpVtbl);
          PostMessageW(v21, 0x470u, 0, 2);
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        }
        ILFree((LPITEMIDLIST)ppidl.Ptr);
        if ( v8 >= 0 )
          goto LABEL_26;
      }
      if ( a2 )
      {
        PathRemoveBackslashW((LPWSTR)&this[66].lpVtbl + 2);
        FileOp.hwnd = 0;
        *(_QWORD *)&FileOp.wFunc = 3;
        *(_OWORD *)&FileOp.hNameMappings = 0;
        FileOp.pFrom = (PCZZWSTR)&this[66].lpVtbl + 2;
        FileOp.pTo = 0;
        *(_QWORD *)&FileOp.fFlags = 1044;
        SHFileOperationW(&FileOp);
      }
    }
LABEL_26:
    ((void (__fastcall *)(struct IDataObject *))v29->lpVtbl->Release)(v29);
    goto LABEL_28;
  }
  DisplayUnZipErrorSource(
    0,
    (HWND)this[133].lpVtbl,
    FullDataObjectFromZip,
    (const unsigned __int16 *)&this[1].lpVtbl + 2);
LABEL_28:
  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v25, (int)&ShellTraceId_ZipFolder_WizardExtractAll_Stop, v26, v27, &ppidl);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800429f0  push    rbp
0x1800429f2  push    rbx
0x1800429f3  push    rsi
0x1800429f4  push    rdi
0x1800429f5  push    r14
0x1800429f7  push    r15
0x1800429f9  lea     rbp, [rsp-2Fh]
0x1800429fe  sub     rsp, 0A8h
0x180042a05  mov     rax, cs:__security_cookie
0x180042a0c  xor     rax, rsp
0x180042a0f  mov     [rbp+57h+var_40], rax
0x180042a13  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, 1
0x180042a1a  mov     r15d, edx
0x180042a1d  mov     rdi, rcx
0x180042a20  jz      short loc_180042A37
0x180042a22  lea     rax, [rbp+57h+ppidl]
0x180042a26  lea     rdx, ShellTraceId_ZipFolder_WizardExtractAll_Start; int
0x180042a2d  mov     qword ptr [rsp+0D0h+fuStyle], rax; PEVENT_DATA_DESCRIPTOR
0x180042a32  call    McGenEventWrite_EventWriteTransfer
0x180042a37  mov     r8, [rdi+428h]; HWND
0x180042a3e  lea     rsi, [rdi+0Ch]
0x180042a42  mov     rdx, rsi; unsigned __int16 *
0x180042a45  mov     [rbp+57h+var_A0], 0
0x180042a4d  lea     r9, [rbp+57h+var_A0]; struct IDataObject **
0x180042a51  call    ?_GetFullDataObjectFromZip@CZipWiz@@AEAAJPEBGPEAUHWND__@@PEAPEAUIDataObject@@@Z; CZipWiz::_GetFullDataObjectFromZip(ushort const *,HWND__ *,IDataObject * *)
0x180042a56  mov     ebx, eax
0x180042a58  test    eax, eax
0x180042a5a  js      loc_180042CAF
0x180042a60  mov     rcx, [rbp+57h+var_A0]
0x180042a64  call    DataObj_SetAsyncMode
0x180042a69  test    r15d, r15d
0x180042a6c  jz      short loc_180042AE3
0x180042a6e  lea     rdx, [rdi+214h]; pszPath
0x180042a75  xor     ecx, ecx; hwnd
0x180042a77  call    cs:__imp_SHCreateDirectory
0x180042a7d  mov     ebx, eax
0x180042a7f  test    eax, eax
0x180042a81  jle     short loc_180042A8C
0x180042a83  movzx   ebx, ax
0x180042a86  or      ebx, 80070000h
0x180042a8c  test    ebx, ebx
0x180042a8e  jns     short loc_180042AE3
0x180042a90  cmp     ebx, 800704C7h
0x180042a96  jz      loc_180042C9D
0x180042a9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180042aa3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180042aa8  mov     rdx, [rdi+428h]; hWnd
0x180042aaf  mov     r8d, 2775h; lpcText
0x180042ab5  mov     [rsp+0D0h+fuStyle], 30h ; '0'; fuStyle
0x180042abd  test    al, al
0x180042abf  jz      short loc_180042ACB
0x180042ac1  call    MessageBoxHelper__ShellMessageBoxTextScaled___2
0x180042ac6  jmp     loc_180042C9D
0x180042acb  mov     rcx, cs:g_hmodThisDll; hAppInst
0x180042ad2  mov     r9d, 2747h; lpcTitle
0x180042ad8  call    cs:__imp_ShellMessageBoxW
0x180042ade  jmp     loc_180042C9D
0x180042ae3  lea     r14, [rdi+214h]
0x180042aea  mov     qword ptr [rbp+57h+ppidl], 0
0x180042af2  mov     rcx, r14; pszPath
0x180042af5  lea     rdx, [rbp+57h+ppidl]; ppidl
0x180042af9  xor     r8d, r8d; rgfInOut
0x180042afc  call    cs:__imp_SHILCreateFromPath
0x180042b02  mov     ebx, eax
0x180042b04  test    eax, eax
0x180042b06  js      loc_180042C1A
0x180042b0c  mov     rcx, [rdi+428h]; hWnd
0x180042b13  mov     [rbp+57h+punk], 0
0x180042b1b  call    cs:__imp_GetParent
0x180042b21  mov     rcx, qword ptr [rbp+57h+ppidl]
0x180042b25  lea     r9, [rbp+57h+punk]
0x180042b29  mov     rdx, rax
0x180042b2c  lea     r8, _GUID_00000122_0000_0000_c000_000000000046
0x180042b33  call    SHGetUIObjectFromFullPIDL
0x180042b38  mov     ebx, eax
0x180042b3a  test    eax, eax
0x180042b3c  js      loc_180042C06
0x180042b42  mov     rcx, [rdi+428h]; hWnd
0x180042b49  call    cs:__imp_GetParent
0x180042b4f  xor     r9d, r9d; lParam
0x180042b52  xor     r8d, r8d; wParam
0x180042b55  mov     rcx, rax; hWnd
0x180042b58  mov     edx, 470h; Msg
0x180042b5d  call    cs:__imp_SendMessageW
0x180042b63  mov     rdx, [rbp+57h+var_A0]; struct IDataObject *
0x180042b67  lea     rax, [rbp+57h+var_58]
0x180042b6b  mov     rcx, [rbp+57h+punk]; punk
0x180042b6f  mov     [rsp+0D0h+var_A8], rdi; struct IUnknown *
0x180042b74  mov     qword ptr [rsp+0D0h+fuStyle], rax; unsigned int *
0x180042b79  mov     [rbp+57h+var_58], 1
0x180042b80  call    ?SHSimulateDropWithSite@@YAJPEAUIDropTarget@@PEAUIDataObject@@KPEBU_POINTL@@PEAKPEAUIUnknown@@@Z; SHSimulateDropWithSite(IDropTarget *,IDataObject *,ulong,_POINTL const *,ulong *,IUnknown *)
0x180042b85  mov     ebx, eax
0x180042b87  cmp     eax, 80010135h
0x180042b8c  jnz     short loc_180042BD2
0x180042b8e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180042b95  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180042b9a  mov     rdx, [rdi+428h]; hWnd
0x180042ba1  mov     [rsp+0D0h+var_A8], rsi
0x180042ba6  test    al, al
0x180042ba8  jz      short loc_180042BB1
0x180042baa  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short____0
0x180042baf  jmp     short loc_180042BD2
0x180042bb1  mov     rcx, cs:g_hmodThisDll; hAppInst
0x180042bb8  mov     r9d, 2747h; lpcTitle
0x180042bbe  mov     r8d, 28BBh; lpcText
0x180042bc4  mov     [rsp+0D0h+fuStyle], 30h ; '0'; fuStyle
0x180042bcc  call    cs:__imp_ShellMessageBoxW
0x180042bd2  mov     rcx, [rdi+428h]; hWnd
0x180042bd9  call    cs:__imp_GetParent
0x180042bdf  mov     r9d, 2; lParam
0x180042be5  xor     r8d, r8d; wParam
0x180042be8  mov     rcx, rax; hWnd
0x180042beb  mov     edx, 470h; Msg
0x180042bf0  call    cs:__imp_PostMessageW
0x180042bf6  mov     rcx, [rbp+57h+punk]
0x180042bfa  mov     rax, [rcx]
0x180042bfd  mov     rax, [rax+10h]
0x180042c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c06  mov     rcx, qword ptr [rbp+57h+ppidl]; pidl
0x180042c0a  call    cs:__imp_ILFree
0x180042c10  test    ebx, ebx
0x180042c12  jns     loc_180042C9D
0x180042c18  jmp     short loc_180042C59
0x180042c1a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180042c21  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180042c26  mov     rdx, [rdi+428h]; hWnd
0x180042c2d  mov     r8d, 28B8h; lpcText
0x180042c33  mov     [rsp+0D0h+fuStyle], 10h; fuStyle
0x180042c3b  test    al, al
0x180042c3d  jz      short loc_180042C46
0x180042c3f  call    MessageBoxHelper__ShellMessageBoxTextScaled___2
0x180042c44  jmp     short loc_180042C59
0x180042c46  mov     rcx, cs:g_hmodThisDll; hAppInst
0x180042c4d  mov     r9d, 2747h; lpcTitle
0x180042c53  call    cs:__imp_ShellMessageBoxW
0x180042c59  test    r15d, r15d
0x180042c5c  jz      short loc_180042C9D
0x180042c5e  mov     rcx, r14; pszPath
0x180042c61  call    cs:__imp_PathRemoveBackslashW
0x180042c67  xorps   xmm0, xmm0
0x180042c6a  mov     [rbp+57h+FileOp.hwnd], 0
0x180042c72  lea     rcx, [rbp+57h+FileOp]; lpFileOp
0x180042c76  mov     qword ptr [rbp+57h+FileOp.wFunc], 3
0x180042c7e  movdqu  xmmword ptr [rbp+57h+FileOp.hNameMappings], xmm0
0x180042c83  mov     [rbp+57h+FileOp.pFrom], r14
0x180042c87  mov     [rbp+57h+FileOp.pTo], 0
0x180042c8f  mov     qword ptr [rbp+57h+FileOp.fFlags], 414h
0x180042c97  call    cs:__imp_SHFileOperationW
0x180042c9d  mov     rcx, [rbp+57h+var_A0]
0x180042ca1  mov     rax, [rcx]
0x180042ca4  mov     rax, [rax+10h]
0x180042ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cad  jmp     short loc_180042CC3
0x180042caf  mov     rdx, [rdi+428h]; HWND
0x180042cb6  mov     r9, rsi; unsigned __int16 *
0x180042cb9  mov     r8d, eax; int
0x180042cbc  xor     ecx, ecx; int
0x180042cbe  call    ?DisplayUnZipErrorSource@@YAXHPEAUHWND__@@JPEBG@Z; DisplayUnZipErrorSource(int,HWND__ *,long,ushort const *)
0x180042cc3  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, 1
0x180042cca  jz      short loc_180042CE1
0x180042ccc  lea     rax, [rbp+57h+ppidl]
0x180042cd0  lea     rdx, ShellTraceId_ZipFolder_WizardExtractAll_Stop; int
0x180042cd7  mov     qword ptr [rsp+0D0h+fuStyle], rax; PEVENT_DATA_DESCRIPTOR
0x180042cdc  call    McGenEventWrite_EventWriteTransfer
0x180042ce1  mov     eax, ebx
0x180042ce3  mov     rcx, [rbp+57h+var_40]
0x180042ce7  xor     rcx, rsp; StackCookie
0x180042cea  call    __security_check_cookie
0x180042cef  add     rsp, 0A8h
0x180042cf6  pop     r15
0x180042cf8  pop     r14
0x180042cfa  pop     rdi
0x180042cfb  pop     rsi
0x180042cfc  pop     rbx
0x180042cfd  pop     rbp
0x180042cfe  retn
```
