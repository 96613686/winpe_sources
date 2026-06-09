# WdcChooseProvidersLoad(void *)

- ea: `0x180044ba0`
- end: `0x180044f55`
- name: `?WdcChooseProvidersLoad@@YAKPEAX@Z`
- size: `949`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18003a3c0`
- `0x18003b0ac`
- `0x180042edc`
- `0x180044ba0`
- `0x180066e18`
- `0x180084e10`
- `0x180086010`

## import_xrefs

- `USER32!EnableWindow` at `0x180044ee2`
- `USER32!EnableWindow` at `0x180044ee2`
- `USER32!GetClientRect` at `0x180044eb9`
- `USER32!GetClientRect` at `0x180044eb9`
- `USER32!SetWindowTextW` at `0x180044eac`
- `USER32!SetWindowTextW` at `0x180044eac`
- `USER32!SendMessageW` at `0x180044d0e`
- `USER32!SendMessageW` at `0x180044d4b`
- `USER32!SendMessageW` at `0x180044e1d`
- `USER32!SendMessageW` at `0x180044e6b`
- `USER32!SendMessageW` at `0x180044ecf`
- `USER32!SendMessageW` at `0x180044d0e`
- `USER32!SendMessageW` at `0x180044d4b`
- `USER32!SendMessageW` at `0x180044e1d`
- `USER32!SendMessageW` at `0x180044e6b`
- `USER32!SendMessageW` at `0x180044ecf`
- `USER32!GetDlgItem` at `0x180044c01`
- `USER32!GetDlgItem` at `0x180044ea0`
- `USER32!GetDlgItem` at `0x180044c01`
- `USER32!GetDlgItem` at `0x180044ea0`
- `USER32!LoadStringW` at `0x180044e90`
- `USER32!LoadStringW` at `0x180044e90`
- `ole32!CoUninitialize` at `0x180044eed`
- `ole32!CoUninitialize` at `0x180044eed`
- `ole32!CoInitialize` at `0x180044c0c`
- `ole32!CoInitialize` at `0x180044c0c`
- `ole32!CoCreateInstance` at `0x180044c67`
- `ole32!CoCreateInstance` at `0x180044c67`

## pseudocode

```c
__int64 __fastcall WdcChooseProvidersLoad(HWND *Parameter)
{
  WCHAR *v2; // rsi
  HWND v3; // rax
  __int64 v4; // rdi
  HWND DlgItem; // r15
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int v8; // r14d
  HRESULT Instance; // eax
  int v10; // eax
  int v11; // r14d
  const char *v12; // rdx
  int v13; // r8d
  int v14; // r12d
  __int64 v15; // rax
  HINSTANCE v16; // rcx
  HWND v17; // rax
  const char *v18; // rdx
  int v19; // r8d
  LPVOID *ppv; // [rsp+20h] [rbp-B9h]
  struct IUnknown *v22; // [rsp+48h] [rbp-91h] BYREF
  HWND hDlg; // [rsp+50h] [rbp-89h]
  LPARAM lParam; // [rsp+60h] [rbp-79h] BYREF
  char v25[32]; // [rsp+68h] [rbp-71h] BYREF
  __int64 v26; // [rsp+88h] [rbp-51h]
  __int128 Buf1; // [rsp+C0h] [rbp-19h] BYREF
  struct tagRECT Rect; // [rsp+D0h] [rbp-9h] BYREF

  v2 = 0;
  memset_0(&lParam, 0, 0x58u);
  v3 = *Parameter;
  v22 = 0;
  hDlg = v3;
  v4 = 0;
  Rect = 0;
  Buf1 = 0;
  DlgItem = GetDlgItem(v3, 3102);
  v6 = CoInitialize(0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 0;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
      "WdcChooseProvidersLoad",
      0,
      L"FAILURE: 0x%08x",
      v6);
    goto LABEL_29;
  }
  Instance = CoCreateInstance(
               &CLSID_TraceDataProviderCollection,
               0,
               0x15u,
               &IID_ITraceDataProviderCollection,
               (LPVOID *)&v22);
  v7 = Instance;
  if ( Instance < 0
    || (Instance = WdcCoSetSecurity(v22), v7 = Instance, Instance < 0)
    || (Instance = ((__int64 (__fastcall *)(struct IUnknown *, HWND))v22->lpVtbl[5].QueryInterface)(v22, Parameter[2]),
        v7 = Instance,
        Instance < 0) )
  {
LABEL_4:
    LODWORD(ppv) = Instance;
  }
  else
  {
    v10 = WdcForEach<ITraceDataProvider,ITraceDataProviderCollection>(
            v22,
            WdcDataCollectorNode::AddEventProvider,
            4,
            DlgItem,
            Parameter[2],
            0,
            v22);
    v7 = v10;
    if ( v10 < 0 )
    {
      LODWORD(ppv) = v10;
      goto LABEL_5;
    }
    v11 = 0;
    v14 = SendMessageW(DlgItem, 0x1004u, 0, 0);
    if ( v14 > 0 )
    {
      do
      {
        memset_0(v25, 0, 0x50u);
        LODWORD(lParam) = 4;
        HIDWORD(lParam) = v11;
        if ( !(unsigned int)SendMessageW(DlgItem, 0x104Bu, 0, (LPARAM)&lParam) )
          continue;
        v15 = v26;
        if ( !v26 )
          continue;
        if ( v4 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          v15 = v26;
        }
        v4 = v15;
        Instance = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v15 + 72LL))(v15, &Buf1);
        v7 = Instance;
        if ( Instance < 0 )
          goto LABEL_4;
        if ( !memcmp_0(&Buf1, &SystemTraceControlGuid, 0x10u)
          || !memcmp_0(&Buf1, CKCLGuid, 0x10u)
          || !memcmp_0(&Buf1, CritSecGuid, 0x10u)
          || !memcmp_0(&Buf1, HeapGuid, 0x10u) )
        {
          v26 = 1;
          if ( *((_DWORD *)Parameter + 2) )
          {
            SendMessageW(DlgItem, 0x1008u, v11, 0);
            --v14;
            continue;
          }
        }
        else
        {
          v26 = 0;
        }
        SendMessageW(DlgItem, 0x104Cu, 0, (LPARAM)&lParam);
        ++v11;
      }
      while ( v11 < v14 );
    }
    v2 = (WCHAR *)WdcAlloc(0x800u, v12, v13);
    if ( v2 )
    {
      v16 = g_hInstance;
      *v2 = 0;
      LoadStringW(v16, 0x2BDu, v2, 1024);
      v17 = GetDlgItem(hDlg, 3101);
      SetWindowTextW(v17, v2);
      GetClientRect(DlgItem, &Rect);
      SendMessageW(DlgItem, 0x101Eu, 0, LOWORD(Rect.right));
      goto LABEL_28;
    }
    v7 = -2147024882;
    LODWORD(ppv) = -2147024882;
  }
LABEL_5:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
    "WdcChooseProvidersLoad",
    0,
    L"FAILURE: 0x%08x",
    ppv);
LABEL_28:
  v8 = 1;
LABEL_29:
  EnableWindow(DlgItem, 1);
  if ( v8 )
    CoUninitialize();
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v22 )
  {
    ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v2 )
    WdcFree(v2, v18, v19);
  return v7;
}

```

## disassembly

```asm
0x180044ba0  push    rbp
0x180044ba2  push    rbx
0x180044ba3  push    rsi
0x180044ba4  push    rdi
0x180044ba5  push    r12
0x180044ba7  push    r13
0x180044ba9  push    r14
0x180044bab  push    r15
0x180044bad  lea     rbp, [rsp-1Fh]
0x180044bb2  sub     rsp, 0F8h
0x180044bb9  mov     rax, cs:__security_cookie
0x180044bc0  xor     rax, rsp
0x180044bc3  mov     [rbp+57h+var_50], rax
0x180044bc7  mov     r13, rcx
0x180044bca  xor     esi, esi
0x180044bcc  xor     edx, edx; Val
0x180044bce  lea     rcx, [rbp+57h+lParam]; void *
0x180044bd2  lea     r8d, [rsi+58h]; Size
0x180044bd6  call    memset_0
0x180044bdb  mov     rax, [r13+0]
0x180044bdf  xorps   xmm0, xmm0
0x180044be2  xorps   xmm1, xmm1
0x180044be5  mov     [rsp+130h+var_E8], rsi
0x180044bea  mov     rcx, rax; hDlg
0x180044bed  mov     [rsp+130h+hDlg], rax
0x180044bf2  mov     edx, 0C1Eh; nIDDlgItem
0x180044bf7  xor     edi, edi
0x180044bf9  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180044bfd  movups  [rbp+57h+Buf1], xmm1
0x180044c01  call    cs:__imp_GetDlgItem
0x180044c07  xor     ecx, ecx; pvReserved
0x180044c09  mov     r15, rax
0x180044c0c  call    cs:__imp_CoInitialize
0x180044c12  mov     ebx, eax
0x180044c14  test    eax, eax
0x180044c16  jns     short loc_180044C41
0x180044c18  xor     r14d, r14d
0x180044c1b  mov     dword ptr [rsp+130h+ppv], eax
0x180044c1f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180044c26  xor     r8d, r8d; int
0x180044c29  lea     rdx, aWdcchooseprovi_0; "WdcChooseProvidersLoad"
0x180044c30  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x180044c37  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180044c3c  jmp     loc_180044EDA
0x180044c41  xor     edx, edx; pUnkOuter
0x180044c43  mov     [rsp+130h+var_F0], 1
0x180044c4b  lea     rax, [rsp+130h+var_E8]
0x180044c50  lea     r9, IID_ITraceDataProviderCollection; riid
0x180044c57  mov     [rsp+130h+ppv], rax; ppv
0x180044c5c  lea     rcx, CLSID_TraceDataProviderCollection; rclsid
0x180044c63  lea     r8d, [rdx+15h]; dwClsContext
0x180044c67  call    cs:__imp_CoCreateInstance
0x180044c6d  mov     ebx, eax
0x180044c6f  test    eax, eax
0x180044c71  jns     short loc_180044C99
0x180044c73  mov     dword ptr [rsp+130h+ppv], eax
0x180044c77  xor     r8d, r8d; int
0x180044c7a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180044c81  lea     rdx, aWdcchooseprovi_0; "WdcChooseProvidersLoad"
0x180044c88  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x180044c8f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180044c94  jmp     loc_180044ED5
0x180044c99  mov     rcx, [rsp+130h+var_E8]; struct IUnknown *
0x180044c9e  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x180044ca3  mov     ebx, eax
0x180044ca5  test    eax, eax
0x180044ca7  js      short loc_180044C73
0x180044ca9  mov     rcx, [rsp+130h+var_E8]
0x180044cae  mov     rdx, [r13+10h]
0x180044cb2  mov     rax, [rcx]
0x180044cb5  mov     rax, [rax+78h]
0x180044cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cbe  mov     ebx, eax
0x180044cc0  test    eax, eax
0x180044cc2  js      short loc_180044C73
0x180044cc4  mov     rcx, [rsp+130h+var_E8]
0x180044cc9  lea     rdx, ?AddEventProvider@WdcDataCollectorNode@@SAJPEAU_WDC_ENUM_CALL@@@Z; WdcDataCollectorNode::AddEventProvider(_WDC_ENUM_CALL *)
0x180044cd0  mov     rax, [r13+10h]
0x180044cd4  mov     r9, r15
0x180044cd7  mov     [rsp+130h+var_100], rcx
0x180044cdc  mov     r8d, 4
0x180044ce2  mov     [rsp+130h+var_108], rsi
0x180044ce7  mov     [rsp+130h+ppv], rax
0x180044cec  call    ??$WdcForEach@UITraceDataProvider@@UITraceDataProviderCollection@@@@YAJPEAUITraceDataProviderCollection@@P6AJPEAU_WDC_ENUM_CALL@@@ZKZZ; WdcForEach<ITraceDataProvider,ITraceDataProviderCollection>(ITraceDataProviderCollection *,long (*)(_WDC_ENUM_CALL *),ulong,...)
0x180044cf1  xor     r8d, r8d; wParam
0x180044cf4  mov     ebx, eax
0x180044cf6  test    eax, eax
0x180044cf8  jns     short loc_180044D03
0x180044cfa  mov     dword ptr [rsp+130h+ppv], eax
0x180044cfe  jmp     loc_180044C7A
0x180044d03  xor     r9d, r9d; lParam
0x180044d06  mov     edx, 1004h; Msg
0x180044d0b  mov     rcx, r15; hWnd
0x180044d0e  call    cs:__imp_SendMessageW
0x180044d14  xor     r14d, r14d
0x180044d17  mov     r12, rax
0x180044d1a  test    eax, eax
0x180044d1c  jle     loc_180044E2F
0x180044d22  xor     edx, edx; Val
0x180044d24  lea     rcx, [rbp+57h+var_C8]; void *
0x180044d28  lea     r8d, [rdx+50h]; Size
0x180044d2c  call    memset_0
0x180044d31  lea     r9, [rbp+57h+lParam]; lParam
0x180044d35  mov     dword ptr [rbp+57h+lParam], 4
0x180044d3c  xor     r8d, r8d; wParam
0x180044d3f  mov     dword ptr [rbp+57h+lParam+4], r14d
0x180044d43  mov     edx, 104Bh; Msg
0x180044d48  mov     rcx, r15; hWnd
0x180044d4b  call    cs:__imp_SendMessageW
0x180044d51  test    eax, eax
0x180044d53  jz      loc_180044E26
0x180044d59  mov     rax, [rbp+57h+var_A8]
0x180044d5d  test    rax, rax
0x180044d60  jz      loc_180044E26
0x180044d66  test    rdi, rdi
0x180044d69  jz      short loc_180044D7E
0x180044d6b  mov     rax, [rdi]
0x180044d6e  mov     rcx, rdi
0x180044d71  mov     rax, [rax+10h]
0x180044d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d7a  mov     rax, [rbp+57h+var_A8]
0x180044d7e  mov     rdi, rax
0x180044d81  lea     rdx, [rbp+57h+Buf1]
0x180044d85  mov     rax, [rax]
0x180044d88  mov     rcx, rdi
0x180044d8b  mov     rax, [rax+48h]
0x180044d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d94  mov     ebx, eax
0x180044d96  test    eax, eax
0x180044d98  js      loc_180044C73
0x180044d9e  mov     r8d, 10h; Size
0x180044da4  lea     rdx, SystemTraceControlGuid; Buf2
0x180044dab  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180044daf  call    memcmp_0
0x180044db4  test    eax, eax
0x180044db6  jz      loc_180044E4F
0x180044dbc  mov     r8d, 10h; Size
0x180044dc2  lea     rdx, CKCLGuid; Buf2
0x180044dc9  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180044dcd  call    memcmp_0
0x180044dd2  test    eax, eax
0x180044dd4  jz      short loc_180044E4F
0x180044dd6  mov     r8d, 10h; Size
0x180044ddc  lea     rdx, CritSecGuid; Buf2
0x180044de3  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180044de7  call    memcmp_0
0x180044dec  test    eax, eax
0x180044dee  jz      short loc_180044E4F
0x180044df0  mov     r8d, 10h; Size
0x180044df6  lea     rdx, HeapGuid; Buf2
0x180044dfd  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180044e01  call    memcmp_0
0x180044e06  test    eax, eax
0x180044e08  jz      short loc_180044E4F
0x180044e0a  mov     [rbp+57h+var_A8], rsi
0x180044e0e  lea     r9, [rbp+57h+lParam]; lParam
0x180044e12  xor     r8d, r8d; wParam
0x180044e15  mov     edx, 104Ch; Msg
0x180044e1a  mov     rcx, r15; hWnd
0x180044e1d  call    cs:__imp_SendMessageW
0x180044e23  inc     r14d
0x180044e26  cmp     r14d, r12d
0x180044e29  jl      loc_180044D22
0x180044e2f  mov     ecx, 800h; dwBytes
0x180044e34  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180044e39  mov     rsi, rax
0x180044e3c  test    rax, rax
0x180044e3f  jnz     short loc_180044E76
0x180044e41  mov     ebx, 8007000Eh
0x180044e46  mov     dword ptr [rsp+130h+ppv], ebx
0x180044e4a  jmp     loc_180044C77
0x180044e4f  mov     [rbp+57h+var_A8], 1
0x180044e57  cmp     [r13+8], esi
0x180044e5b  jz      short loc_180044E0E
0x180044e5d  movsxd  r8, r14d; wParam
0x180044e60  xor     r9d, r9d; lParam
0x180044e63  mov     edx, 1008h; Msg
0x180044e68  mov     rcx, r15; hWnd
0x180044e6b  call    cs:__imp_SendMessageW
0x180044e71  dec     r12d
0x180044e74  jmp     short loc_180044E26
0x180044e76  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180044e7d  xor     eax, eax
0x180044e7f  mov     r9d, 400h; cchBufferMax
0x180044e85  mov     [rsi], ax
0x180044e88  mov     r8, rsi; lpBuffer
0x180044e8b  mov     edx, 2BDh; uID
0x180044e90  call    cs:__imp_LoadStringW
0x180044e96  mov     rcx, [rsp+130h+hDlg]; hDlg
0x180044e9b  mov     edx, 0C1Dh; nIDDlgItem
0x180044ea0  call    cs:__imp_GetDlgItem
0x180044ea6  mov     rcx, rax; hWnd
0x180044ea9  mov     rdx, rsi; lpString
0x180044eac  call    cs:__imp_SetWindowTextW
0x180044eb2  lea     rdx, [rbp+57h+Rect]; lpRect
0x180044eb6  mov     rcx, r15; hWnd
0x180044eb9  call    cs:__imp_GetClientRect
0x180044ebf  movzx   r9d, word ptr [rbp+57h+Rect.right]; lParam
0x180044ec4  xor     r8d, r8d; wParam
0x180044ec7  mov     edx, 101Eh; Msg
0x180044ecc  mov     rcx, r15; hWnd
0x180044ecf  call    cs:__imp_SendMessageW
0x180044ed5  mov     r14d, [rsp+130h+var_F0]
0x180044eda  mov     edx, 1; bEnable
0x180044edf  mov     rcx, r15; hWnd
0x180044ee2  call    cs:__imp_EnableWindow
0x180044ee8  test    r14d, r14d
0x180044eeb  jz      short loc_180044EF3
0x180044eed  call    cs:__imp_CoUninitialize
0x180044ef3  test    rdi, rdi
0x180044ef6  jz      short loc_180044F07
0x180044ef8  mov     rax, [rdi]
0x180044efb  mov     rcx, rdi
0x180044efe  mov     rax, [rax+10h]
0x180044f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f07  mov     rcx, [rsp+130h+var_E8]
0x180044f0c  test    rcx, rcx
0x180044f0f  jz      short loc_180044F26
0x180044f11  mov     rax, [rcx]
0x180044f14  mov     rax, [rax+10h]
0x180044f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f1d  mov     [rsp+130h+var_E8], 0
0x180044f26  test    rsi, rsi
0x180044f29  jz      short loc_180044F33
0x180044f2b  mov     rcx, rsi; void *
0x180044f2e  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180044f33  mov     eax, ebx
0x180044f35  mov     rcx, [rbp+57h+var_50]
0x180044f39  xor     rcx, rsp; StackCookie
0x180044f3c  call    __security_check_cookie
0x180044f41  add     rsp, 0F8h
0x180044f48  pop     r15
0x180044f4a  pop     r14
0x180044f4c  pop     r13
0x180044f4e  pop     r12
0x180044f50  pop     rdi
0x180044f51  pop     rsi
0x180044f52  pop     rbx
0x180044f53  pop     rbp
0x180044f54  retn
```
