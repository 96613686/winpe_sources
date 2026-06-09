# CAdvancedOptions::Show(HWND__ *,INDEXER_REBUILD_REASON *,int *)

- ea: `0x18000bab4`
- end: `0x18000bdc0`
- name: `?Show@CAdvancedOptions@@QEAAJPEAUHWND__@@PEAW4INDEXER_REBUILD_REASON@@PEAH@Z`
- size: `780`
- prototype: `__int64 __fastcall(CAdvancedOptions *__hidden this, HWND, enum INDEXER_REBUILD_REASON *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bdd0`

## callees

- `0x180005cc0`
- `0x18000687c`
- `0x18000bab4`
- `0x18000c5c0`
- `0x18000fd48`
- `0x180011ff0`
- `0x18001a7fc`
- `0x18001ac7c`
- `0x1800204fc`
- `0x18002055c`
- `0x18002c5b4`
- `0x18002c64c`
- `0x18002c7bc`
- `0x18002fc5c`
- `0x18003014c`

## import_xrefs

- `SHELL32!__imp_SHAddFromPropSheetExtArray` at `0x18000bd05`
- `SHELL32!__imp_SHAddFromPropSheetExtArray` at `0x18000bd05`
- `SHELL32!__imp_SHCreatePropSheetExtArray` at `0x18000bce5`
- `SHELL32!__imp_SHCreatePropSheetExtArray` at `0x18000bce5`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x18000bd1b`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x18000bd31`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x18000bd1b`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x18000bd31`

## pseudocode

```c
__int64 __fastcall CAdvancedOptions::Show(struct IUnknown **this, HWND a2, enum INDEXER_REBUILD_REASON *a3, int *a4)
{
  int IsServiceRunning; // r15d
  int inited; // ebx
  struct IGatherManagerAdmin3 *v8; // rdx
  struct IUnknown *v9; // rdx
  int v10; // r12d
  LPVOID v11; // rax
  void *v12; // rdi
  struct _PSP *v13; // rax
  struct CFileTypesPage *v14; // rbx
  int v15; // esi
  struct _PSP *v16; // rax
  HPSXA v17; // rax
  HPSXA v18; // rsi
  struct CFileTypesPage *v20; // [rsp+20h] [rbp-E0h] BYREF
  enum INDEXER_REBUILD_REASON *v21; // [rsp+28h] [rbp-D8h]
  int *v22; // [rsp+30h] [rbp-D0h]
  PROPSHEETHEADERW_V2 lParam; // [rsp+40h] [rbp-C0h] BYREF
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v25[14]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v26[800]; // [rsp+180h] [rbp+80h] BYREF

  v22 = a4;
  v21 = a3;
  IsServiceRunning = 0;
  v25[11] = 0;
  v25[0] = &CServiceMonitorCPL::`vftable';
  inited = CServiceMonitorBase::InitializeServiceListening((CServiceMonitorBase *)v25, L"WSearch");
  if ( inited >= 0 )
  {
    IsServiceRunning = CServiceMonitorBase::IsServiceRunning((CServiceMonitorBase *)v25);
    CServiceMonitorBase::UninitializeServiceListening((CServiceMonitorBase *)v25);
    if ( IsServiceRunning )
    {
      inited = CMSSAdmin::InitGatherAdmin((CMSSAdmin *)(this + 3), v8);
      if ( inited >= 0 )
        inited = CMSSAdmin::InitIndexerPlugin(this + 3, v9);
    }
  }
  v10 = 0;
  if ( inited >= 0 )
    v10 = IsServiceRunning;
  memset_0(&lParam, 0, sizeof(lParam));
  memset_0(v26, 0, sizeof(v26));
  lParam.hwndParent = a2;
  lParam.hInstance = Globals;
  lParam.ppsp = (LPCPROPSHEETPAGEW)v26;
  *(_QWORD *)&lParam.dwSize = 0x200008000000060LL;
  lParam.pszCaption = (LPCWSTR)620;
  v11 = operator new(0x460u);
  v12 = v11;
  if ( v11 )
  {
    *((_QWORD *)v11 + 1) = this;
    *((_QWORD *)v11 + 5) = 0;
    *((_DWORD *)v11 + 12) = 0;
    *((_QWORD *)v11 + 8) = 0;
    *((_DWORD *)v11 + 13) = 1;
    *((_QWORD *)v11 + 7) = 1;
    *((_DWORD *)v11 + 18) = 1;
    *((_DWORD *)v11 + 19) = v10;
    *((_WORD *)v11 + 40) = 0;
    *((_WORD *)v11 + 300) = 0;
    memset_0(&constPropSheetPagePointer, 0, sizeof(constPropSheetPagePointer));
    constPropSheetPagePointer.hInstance = Globals;
    constPropSheetPagePointer.pfnDlgProc = (DLGPROC)CIndexSettingsPage::s_DialogProc;
    constPropSheetPagePointer.dwSize = 104;
    constPropSheetPagePointer.pszTemplate = (LPCWSTR)103;
    constPropSheetPagePointer.lParam = (LPARAM)v12;
    v13 = CreatePropertySheetPageW(&constPropSheetPagePointer);
    if ( v13 )
      CAdvancedOptions::_AddPropSheetPage(v13, (LPARAM)&lParam);
    v14 = 0;
    v20 = 0;
    if ( v10 )
    {
      v15 = CFileTypesPage::s_CreateInstance((struct CAdvancedOptions *)this, &v20);
      if ( v15 < 0 )
      {
        v14 = v20;
LABEL_18:
        operator delete(v12);
        goto LABEL_21;
      }
      memset_0(&constPropSheetPagePointer, 0, sizeof(constPropSheetPagePointer));
      v14 = v20;
      constPropSheetPagePointer.hInstance = Globals;
      constPropSheetPagePointer.pfnDlgProc = (DLGPROC)CFileTypesPage::s_DialogProc;
      constPropSheetPagePointer.dwSize = 104;
      constPropSheetPagePointer.pszTemplate = (LPCWSTR)104;
      constPropSheetPagePointer.lParam = (LPARAM)v20;
      v16 = CreatePropertySheetPageW(&constPropSheetPagePointer);
      if ( v16 )
        CAdvancedOptions::_AddPropSheetPage(v16, (LPARAM)&lParam);
      v17 = SHCreatePropSheetExtArray(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Controls Folder\\Search\\IndexingOptions",
              0x62u);
      v18 = v17;
      if ( v17 )
      {
        SHAddFromPropSheetExtArray(v17, CAdvancedOptions::_AddPropSheetPage, (LPARAM)&lParam);
        SHReplaceFromPropSheetExtArray(v18, 0x64u, CAdvancedOptions::_AddPropSheetPage, (LPARAM)&lParam);
        SHReplaceFromPropSheetExtArray(v18, 0x65u, CAdvancedOptions::_AddPropSheetPage, (LPARAM)&lParam);
      }
    }
    v15 = -2147467259;
    if ( PropertySheetW(&lParam) >= 0 )
      v15 = 0;
    goto LABEL_18;
  }
  v15 = -2147024882;
  v14 = 0;
LABEL_21:
  if ( v14 )
  {
    CFileTypesManager::~CFileTypesManager((struct CFileTypesPage *)((char *)v14 + 56));
    operator delete(v14);
  }
  *(_DWORD *)v21 = *(_DWORD *)this;
  *v22 = *((_DWORD *)this + 3);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000bab4  push    rbp
0x18000bab6  push    rbx
0x18000bab7  push    rsi
0x18000bab8  push    rdi
0x18000bab9  push    r12
0x18000babb  push    r13
0x18000babd  push    r14
0x18000babf  push    r15
0x18000bac1  lea     rbp, [rsp-3B8h]
0x18000bac9  sub     rsp, 4B8h
0x18000bad0  mov     rax, cs:__security_cookie
0x18000bad7  xor     rax, rsp
0x18000bada  mov     [rbp+3F0h+var_50], rax
0x18000bae1  mov     r13, rdx
0x18000bae4  mov     [rsp+4F0h+var_4C0], r9
0x18000bae9  mov     r14, rcx
0x18000baec  mov     [rsp+4F0h+var_4C8], r8
0x18000baf1  lea     rax, ??_7CServiceMonitorCPL@@6B@; const CServiceMonitorCPL::`vftable'
0x18000baf8  xor     r15d, r15d
0x18000bafb  lea     rdx, ServiceName; "WSearch"
0x18000bb02  mov     [rbp+3F0h+var_388], r15
0x18000bb06  lea     rcx, [rbp+3F0h+var_3E0]; this
0x18000bb0a  mov     [rbp+3F0h+var_3E0], rax
0x18000bb0e  call    ?InitializeServiceListening@CServiceMonitorBase@@QEAAJPEBG@Z; CServiceMonitorBase::InitializeServiceListening(ushort const *)
0x18000bb13  mov     ebx, eax
0x18000bb15  test    eax, eax
0x18000bb17  js      short loc_18000BB4D
0x18000bb19  lea     rcx, [rbp+3F0h+var_3E0]; this
0x18000bb1d  call    ?IsServiceRunning@CServiceMonitorBase@@QEAAHXZ; CServiceMonitorBase::IsServiceRunning(void)
0x18000bb22  lea     rcx, [rbp+3F0h+var_3E0]; this
0x18000bb26  mov     r15d, eax
0x18000bb29  call    ?UninitializeServiceListening@CServiceMonitorBase@@QEAAXXZ; CServiceMonitorBase::UninitializeServiceListening(void)
0x18000bb2e  test    r15d, r15d
0x18000bb31  jz      short loc_18000BB4D
0x18000bb33  lea     rcx, [r14+18h]; this
0x18000bb37  call    ?InitGatherAdmin@CMSSAdmin@@QEAAJPEAUIGatherManagerAdmin3@@@Z; CMSSAdmin::InitGatherAdmin(IGatherManagerAdmin3 *)
0x18000bb3c  mov     ebx, eax
0x18000bb3e  test    eax, eax
0x18000bb40  js      short loc_18000BB4D
0x18000bb42  lea     rcx, [r14+18h]; this
0x18000bb46  call    ?InitIndexerPlugin@CMSSAdmin@@QEAAJXZ; CMSSAdmin::InitIndexerPlugin(void)
0x18000bb4b  mov     ebx, eax
0x18000bb4d  xor     esi, esi
0x18000bb4f  lea     rcx, [rsp+4F0h+lParam]; void *
0x18000bb54  test    ebx, ebx
0x18000bb56  cmovns  esi, ebx
0x18000bb59  xor     r12d, r12d
0x18000bb5c  test    ebx, ebx
0x18000bb5e  mov     ebx, 60h ; '`'
0x18000bb63  mov     r8d, ebx; Size
0x18000bb66  cmovns  r12d, r15d
0x18000bb6a  xor     edx, edx; Val
0x18000bb6c  call    memset_0
0x18000bb71  xor     edx, edx; Val
0x18000bb73  lea     rcx, [rbp+3F0h+var_370]; void *
0x18000bb7a  mov     r8d, 320h; Size
0x18000bb80  call    memset_0
0x18000bb85  mov     rax, cs:Globals
0x18000bb8c  mov     [rsp+4F0h+var_4A8], r13
0x18000bb91  xor     r13d, r13d
0x18000bb94  mov     [rsp+4F0h+var_4A0], rax
0x18000bb99  lea     rax, [rbp+3F0h+var_370]
0x18000bba0  mov     [rsp+4F0h+var_478], rax
0x18000bba5  mov     dword ptr [rsp+4F0h+lParam], ebx
0x18000bba9  mov     dword ptr [rsp+4F0h+lParam+4], 2000080h
0x18000bbb1  mov     [rsp+4F0h+var_490], 26Ch
0x18000bbba  test    esi, esi
0x18000bbbc  js      loc_18000BD68
0x18000bbc2  mov     ecx, 460h; unsigned __int64
0x18000bbc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bbcc  mov     rdi, rax
0x18000bbcf  test    rax, rax
0x18000bbd2  jz      loc_18000BD63
0x18000bbd8  mov     [rax+8], r14
0x18000bbdc  lea     r15d, [rbx+8]
0x18000bbe0  mov     [rax+28h], r13
0x18000bbe4  lea     rcx, [rbp+3F0h+constPropSheetPagePointer]; void *
0x18000bbe8  mov     [rax+30h], r13d
0x18000bbec  mov     r8d, r15d; Size
0x18000bbef  lea     eax, [rbx-5Fh]
0x18000bbf2  mov     [rdi+40h], r13
0x18000bbf6  xor     edx, edx; Val
0x18000bbf8  mov     [rdi+34h], eax
0x18000bbfb  mov     [rdi+38h], rax
0x18000bbff  mov     [rdi+48h], eax
0x18000bc02  mov     [rdi+4Ch], r12d
0x18000bc06  mov     [rdi+50h], r13w
0x18000bc0b  mov     [rdi+258h], r13w
0x18000bc13  call    memset_0
0x18000bc18  mov     rax, cs:Globals
0x18000bc1f  lea     rcx, [rbp+3F0h+constPropSheetPagePointer]; constPropSheetPagePointer
0x18000bc23  mov     [rbp+3F0h+constPropSheetPagePointer.hInstance], rax
0x18000bc27  lea     rax, ?s_DialogProc@CIndexSettingsPage@@CA_JPEAUHWND__@@I_K_J@Z; CIndexSettingsPage::s_DialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000bc2e  mov     [rbp+3F0h+constPropSheetPagePointer.pfnDlgProc], rax
0x18000bc32  mov     [rbp+3F0h+constPropSheetPagePointer.dwSize], r15d
0x18000bc36  mov     qword ptr [rbp+3F0h+constPropSheetPagePointer.10h], 67h ; 'g'
0x18000bc3e  mov     [rbp+3F0h+constPropSheetPagePointer.lParam], rdi
0x18000bc42  call    CreatePropertySheetPageW
0x18000bc47  test    rax, rax
0x18000bc4a  jz      short loc_18000BC59
0x18000bc4c  lea     rdx, [rsp+4F0h+lParam]; LPARAM
0x18000bc51  mov     rcx, rax; HPROPSHEETPAGE
0x18000bc54  call    ?_AddPropSheetPage@CAdvancedOptions@@CAHPEAU_PSP@@_J@Z; CAdvancedOptions::_AddPropSheetPage(_PSP *,__int64)
0x18000bc59  mov     rbx, r13
0x18000bc5c  mov     [rsp+4F0h+var_4D0], rbx
0x18000bc61  test    r12d, r12d
0x18000bc64  jz      loc_18000BD37
0x18000bc6a  lea     rdx, [rsp+4F0h+var_4D0]; struct CFileTypesPage **
0x18000bc6f  mov     rcx, r14; struct CAdvancedOptions *
0x18000bc72  call    ?s_CreateInstance@CFileTypesPage@@SAJPEAVCAdvancedOptions@@PEAPEAV1@@Z; CFileTypesPage::s_CreateInstance(CAdvancedOptions *,CFileTypesPage * *)
0x18000bc77  mov     esi, eax
0x18000bc79  test    eax, eax
0x18000bc7b  js      loc_18000BD5C
0x18000bc81  mov     r8, r15; Size
0x18000bc84  lea     rcx, [rbp+3F0h+constPropSheetPagePointer]; void *
0x18000bc88  xor     edx, edx; Val
0x18000bc8a  call    memset_0
0x18000bc8f  mov     rax, cs:Globals
0x18000bc96  lea     rcx, [rbp+3F0h+constPropSheetPagePointer]; constPropSheetPagePointer
0x18000bc9a  mov     rbx, [rsp+4F0h+var_4D0]
0x18000bc9f  mov     [rbp+3F0h+constPropSheetPagePointer.hInstance], rax
0x18000bca3  lea     rax, ?s_DialogProc@CFileTypesPage@@CA_JPEAUHWND__@@I_K_J@Z; CFileTypesPage::s_DialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000bcaa  mov     [rbp+3F0h+constPropSheetPagePointer.pfnDlgProc], rax
0x18000bcae  mov     [rbp+3F0h+constPropSheetPagePointer.dwSize], r15d
0x18000bcb2  mov     qword ptr [rbp+3F0h+constPropSheetPagePointer.10h], r15
0x18000bcb6  mov     [rbp+3F0h+constPropSheetPagePointer.lParam], rbx
0x18000bcba  call    CreatePropertySheetPageW
0x18000bcbf  test    rax, rax
0x18000bcc2  jz      short loc_18000BCD1
0x18000bcc4  lea     rdx, [rsp+4F0h+lParam]; LPARAM
0x18000bcc9  mov     rcx, rax; HPROPSHEETPAGE
0x18000bccc  call    ?_AddPropSheetPage@CAdvancedOptions@@CAHPEAU_PSP@@_J@Z; CAdvancedOptions::_AddPropSheetPage(_PSP *,__int64)
0x18000bcd1  mov     r8d, 62h ; 'b'; max_iface
0x18000bcd7  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000bcde  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bce5  call    cs:__imp_SHCreatePropSheetExtArray
0x18000bceb  mov     rsi, rax
0x18000bcee  test    rax, rax
0x18000bcf1  jz      short loc_18000BD37
0x18000bcf3  lea     r15, ?_AddPropSheetPage@CAdvancedOptions@@CAHPEAU_PSP@@_J@Z; CAdvancedOptions::_AddPropSheetPage(_PSP *,__int64)
0x18000bcfa  mov     rcx, rax; hpsxa
0x18000bcfd  mov     rdx, r15; lpfnAddPage
0x18000bd00  lea     r8, [rsp+4F0h+lParam]; lParam
0x18000bd05  call    cs:__imp_SHAddFromPropSheetExtArray
0x18000bd0b  lea     r9, [rsp+4F0h+lParam]; lParam
0x18000bd10  mov     r8, r15; lpfnReplaceWith
0x18000bd13  mov     edx, 64h ; 'd'; uPageID
0x18000bd18  mov     rcx, rsi; hpsxa
0x18000bd1b  call    cs:__imp_SHReplaceFromPropSheetExtArray
0x18000bd21  lea     r9, [rsp+4F0h+lParam]; lParam
0x18000bd26  mov     r8, r15; lpfnReplaceWith
0x18000bd29  mov     edx, 65h ; 'e'; uPageID
0x18000bd2e  mov     rcx, rsi; hpsxa
0x18000bd31  call    cs:__imp_SHReplaceFromPropSheetExtArray
0x18000bd37  lea     rcx, [rsp+4F0h+lParam]; LPCPROPSHEETHEADERW
0x18000bd3c  call    PropertySheetW
0x18000bd41  test    rax, rax
0x18000bd44  mov     esi, 80004005h
0x18000bd49  cmovns  esi, r13d
0x18000bd4d  mov     edx, 460h; unsigned __int64
0x18000bd52  mov     rcx, rdi; void *
0x18000bd55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bd5a  jmp     short loc_18000BD6B
0x18000bd5c  mov     rbx, [rsp+4F0h+var_4D0]
0x18000bd61  jmp     short loc_18000BD4D
0x18000bd63  mov     esi, 8007000Eh
0x18000bd68  mov     rbx, r13
0x18000bd6b  test    rbx, rbx
0x18000bd6e  jz      short loc_18000BD86
0x18000bd70  lea     rcx, [rbx+38h]; this
0x18000bd74  call    ??1CFileTypesManager@@QEAA@XZ; CFileTypesManager::~CFileTypesManager(void)
0x18000bd79  mov     edx, 2E0h; unsigned __int64
0x18000bd7e  mov     rcx, rbx; void *
0x18000bd81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bd86  mov     eax, [r14]
0x18000bd89  mov     rcx, [rsp+4F0h+var_4C8]
0x18000bd8e  mov     [rcx], eax
0x18000bd90  mov     eax, [r14+0Ch]
0x18000bd94  mov     rcx, [rsp+4F0h+var_4C0]
0x18000bd99  mov     [rcx], eax
0x18000bd9b  mov     eax, esi
0x18000bd9d  mov     rcx, [rbp+3F0h+var_50]
0x18000bda4  xor     rcx, rsp; StackCookie
0x18000bda7  call    __security_check_cookie
0x18000bdac  add     rsp, 4B8h
0x18000bdb3  pop     r15
0x18000bdb5  pop     r14
0x18000bdb7  pop     r13
0x18000bdb9  pop     r12
0x18000bdbb  pop     rdi
0x18000bdbc  pop     rsi
0x18000bdbd  pop     rbx
0x18000bdbe  pop     rbp
0x18000bdbf  retn
```
