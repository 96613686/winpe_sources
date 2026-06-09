# CPlApplet

- ea: `0x18001f740`
- end: `0x18001f978`
- name: `CPlApplet`
- size: `568`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d4dc`
- `0x18001a7fc`
- `0x18001ac7c`
- `0x18001f740`
- `0x18001fc94`
- `0x180020e4c`
- `0x180026fdc`
- `0x180027360`
- `0x180028470`
- `0x18002fa78`
- `0x1800300fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f7f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f812`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f7f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001f812`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001f791`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001f791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f79e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8f0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18001f7bf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18001f7bf`
- `USER32!LoadIconW` at `0x18001f7d6`
- `USER32!LoadIconW` at `0x18001f7d6`
- `USER32!SetProcessDPIAware` at `0x18001f831`
- `USER32!SetProcessDPIAware` at `0x18001f831`

## pseudocode

```c
__int64 __fastcall CPlApplet(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // ebx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  DWORD LastError; // eax
  HICON IconW; // rax
  HINSTANCE v14; // rcx
  _DWORD *v15; // rax
  CSearchOptionsDialog *v16; // rdi
  HINSTANCE v17; // rcx
  void *v18; // rdi
  INITCOMMONCONTROLSEX v20; // [rsp+20h] [rbp-48h]
  INITCOMMONCONTROLSEX picce; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  v7 = a2 - 1;
  if ( !v7 )
  {
    picce.dwSize = 8;
    picce.dwICC = 49153;
    return InitCommonControlsEx(&picce);
  }
  v8 = v7 - 1;
  if ( !v8 )
    return 1;
  v9 = v8 - 1;
  if ( !v9 )
  {
    *(_QWORD *)(a4 + 12) = 0;
    *(_DWORD *)a4 = 201;
    *(_DWORD *)(a4 + 4) = 601;
    *(_DWORD *)(a4 + 8) = 602;
    return v6;
  }
  v10 = v9 - 2;
  if ( !v10 )
    goto LABEL_7;
  v11 = v10 - 3;
  if ( !v11 )
  {
    IconW = LoadIconW(Globals, (LPCWSTR)0xC9);
    v14 = Globals;
    *(_QWORD *)(a4 + 20) = IconW;
    LoadStringW(v14, 0x259u, (LPWSTR)(a4 + 28), 32);
    LoadStringW(Globals, 0x25Au, (LPWSTR)(a4 + 92), 64);
    *(_DWORD *)(a4 + 8) = 0;
    *(_DWORD *)a4 = 476;
    *(_QWORD *)(a4 + 12) = 0;
    *(_WORD *)(a4 + 220) = 0;
    return v6;
  }
  if ( v11 == 2 )
  {
LABEL_7:
    v6 = 1;
    hObject = CreateMutexW(0, 1, L"Search Admin Control Panel");
    LastError = GetLastError();
    if ( hObject )
    {
      SetProcessDPIAware();
      v15 = operator new(0x48u);
      if ( v15 )
      {
        *(_QWORD *)v15 = 0;
        v15[2] = 0;
        *((_QWORD *)v15 + 2) = 0;
        *((_QWORD *)v15 + 3) = 0;
        *((_QWORD *)v15 + 4) = 0;
        *((_QWORD *)v15 + 5) = 0;
        *((_QWORD *)v15 + 6) = 0;
        *((_QWORD *)v15 + 8) = 0;
        qword_180041E50 = v15;
        if ( (int)CMSSearchStateMonitor::Start((CMSSearchStateMonitor *)v15) >= 0 )
        {
          picce = 0;
          if ( (int)CSearchOptionsDialog::s_CreateInstance((struct CSearchOptionsDialog **)&picce) >= 0 )
          {
            v16 = (CSearchOptionsDialog *)picce;
            v17 = Globals;
            v20 = picce;
            *(_QWORD *)(*(_QWORD *)&picce + 8LL) = hWnd;
            if ( !SHFusionDialogBoxParam(
                    v17,
                    (LPCWSTR)0x65,
                    hWnd,
                    (DLGPROC)CSearchOptionsDialog::s_DialogProc,
                    *(_QWORD *)&v20) )
              ResultFromKnownLastError();
            SearchOptionsTelemetry::LaunchSearchOptions();
            CSearchOptionsDialog::~CSearchOptionsDialog(v16);
            operator delete(v16);
          }
        }
      }
      else
      {
        qword_180041E50 = 0;
      }
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      v18 = qword_180041E50;
      if ( qword_180041E50 )
      {
        CMSSAdmin::~CMSSAdmin((CMSSAdmin *)((char *)qword_180041E50 + 16));
        operator delete(v18);
      }
    }
    else if ( LastError == 183 )
    {
      SetForegroundWindow(hWnd);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001f740  push    rbx
0x18001f742  push    rbp
0x18001f743  push    rsi
0x18001f744  push    rdi
0x18001f745  sub     rsp, 48h
0x18001f749  xor     ebp, ebp
0x18001f74b  mov     rdi, r9
0x18001f74e  mov     rsi, rcx
0x18001f751  mov     ebx, ebp
0x18001f753  sub     edx, 1
0x18001f756  jz      loc_18001F945
0x18001f75c  sub     edx, 1
0x18001f75f  jz      loc_18001F93E
0x18001f765  sub     edx, 1
0x18001f768  jz      loc_18001F921
0x18001f76e  sub     edx, 2
0x18001f771  jz      short loc_18001F781
0x18001f773  sub     edx, 3
0x18001f776  jz      short loc_18001F7CA
0x18001f778  cmp     edx, 2
0x18001f77b  jnz     loc_18001F96D
0x18001f781  mov     ebx, 1
0x18001f786  lea     r8, aSearchAdminCon; "Search Admin Control Panel"
0x18001f78d  mov     edx, ebx; bInitialOwner
0x18001f78f  xor     ecx, ecx; lpMutexAttributes
0x18001f791  call    cs:__imp_CreateMutexW
0x18001f797  mov     cs:hObject, rax
0x18001f79e  call    cs:__imp_GetLastError
0x18001f7a4  cmp     cs:hObject, rbp
0x18001f7ab  jnz     loc_18001F831
0x18001f7b1  cmp     eax, 0B7h
0x18001f7b6  jnz     loc_18001F96D
0x18001f7bc  mov     rcx, rsi; hWnd
0x18001f7bf  call    cs:__imp_SetForegroundWindow
0x18001f7c5  jmp     loc_18001F96D
0x18001f7ca  mov     rcx, cs:Globals; hInstance
0x18001f7d1  mov     edx, 0C9h; lpIconName
0x18001f7d6  call    cs:__imp_LoadIconW
0x18001f7dc  mov     rcx, cs:Globals; hInstance
0x18001f7e3  lea     r8, [rdi+1Ch]; lpBuffer
0x18001f7e7  mov     edx, 259h; uID
0x18001f7ec  mov     [rdi+14h], rax
0x18001f7f0  mov     r9d, 20h ; ' '; cchBufferMax
0x18001f7f6  call    cs:__imp_LoadStringW
0x18001f7fc  mov     rcx, cs:Globals; hInstance
0x18001f803  lea     r8, [rdi+5Ch]; lpBuffer
0x18001f807  mov     edx, 25Ah; uID
0x18001f80c  mov     r9d, 40h ; '@'; cchBufferMax
0x18001f812  call    cs:__imp_LoadStringW
0x18001f818  mov     [rdi+8], ebp
0x18001f81b  mov     dword ptr [rdi], 1DCh
0x18001f821  mov     [rdi+0Ch], rbp
0x18001f825  mov     [rdi+0DCh], bp
0x18001f82c  jmp     loc_18001F96D
0x18001f831  call    cs:__imp_SetProcessDPIAware
0x18001f837  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001f83c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f841  test    rax, rax
0x18001f844  jz      loc_18001F8DD
0x18001f84a  mov     [rax], rbp
0x18001f84d  mov     rcx, rax; this
0x18001f850  mov     [rax+8], ebp
0x18001f853  mov     [rax+10h], rbp
0x18001f857  mov     [rax+18h], rbp
0x18001f85b  mov     [rax+20h], rbp
0x18001f85f  mov     [rax+28h], rbp
0x18001f863  mov     [rax+30h], rbp
0x18001f867  mov     [rax+40h], rbp
0x18001f86b  mov     cs:qword_180041E50, rax
0x18001f872  call    ?Start@CMSSearchStateMonitor@@QEAAJXZ; CMSSearchStateMonitor::Start(void)
0x18001f877  test    eax, eax
0x18001f879  js      short loc_18001F8E4
0x18001f87b  lea     rcx, [rsp+68h+picce]; struct CSearchOptionsDialog **
0x18001f880  mov     qword ptr [rsp+68h+picce.dwSize], rbp
0x18001f885  call    ?s_CreateInstance@CSearchOptionsDialog@@SAJPEAPEAV1@@Z; CSearchOptionsDialog::s_CreateInstance(CSearchOptionsDialog * *)
0x18001f88a  test    eax, eax
0x18001f88c  js      short loc_18001F8E4
0x18001f88e  mov     rdi, qword ptr [rsp+68h+picce.dwSize]
0x18001f893  lea     r9, ?s_DialogProc@CSearchOptionsDialog@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18001f89a  mov     rcx, cs:Globals; hInstance
0x18001f8a1  mov     r8, rsi; hWndParent
0x18001f8a4  mov     edx, 65h ; 'e'; lpTemplateName
0x18001f8a9  mov     [rsp+68h+var_48], rdi; LPARAM
0x18001f8ae  mov     [rdi+8], rsi
0x18001f8b2  call    SHFusionDialogBoxParam
0x18001f8b7  test    rax, rax
0x18001f8ba  jnz     short loc_18001F8C1
0x18001f8bc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001f8c1  call    ?LaunchSearchOptions@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::LaunchSearchOptions(void)
0x18001f8c6  mov     rcx, rdi; this
0x18001f8c9  call    ??1CSearchOptionsDialog@@QEAA@XZ; CSearchOptionsDialog::~CSearchOptionsDialog(void)
0x18001f8ce  mov     edx, 6F8h; unsigned __int64
0x18001f8d3  mov     rcx, rdi; void *
0x18001f8d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f8db  jmp     short loc_18001F8E4
0x18001f8dd  mov     cs:qword_180041E50, rbp
0x18001f8e4  mov     rcx, cs:hObject; hObject
0x18001f8eb  test    rcx, rcx
0x18001f8ee  jz      short loc_18001F8FD
0x18001f8f0  call    cs:__imp_CloseHandle
0x18001f8f6  mov     cs:hObject, rbp
0x18001f8fd  mov     rdi, cs:qword_180041E50
0x18001f904  test    rdi, rdi
0x18001f907  jz      short loc_18001F96D
0x18001f909  lea     rcx, [rdi+10h]; this
0x18001f90d  call    ??1CMSSAdmin@@QEAA@XZ; CMSSAdmin::~CMSSAdmin(void)
0x18001f912  mov     edx, 48h ; 'H'; unsigned __int64
0x18001f917  mov     rcx, rdi; void *
0x18001f91a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f91f  jmp     short loc_18001F96D
0x18001f921  mov     [r9+0Ch], rbp
0x18001f925  mov     dword ptr [r9], 0C9h
0x18001f92c  mov     dword ptr [r9+4], 259h
0x18001f934  mov     dword ptr [r9+8], 25Ah
0x18001f93c  jmp     short loc_18001F96D
0x18001f93e  mov     ebx, 1
0x18001f943  jmp     short loc_18001F96D
0x18001f945  lea     rcx, [rsp+68h+picce]; picce
0x18001f94a  mov     [rsp+68h+picce.dwSize], 8
0x18001f952  mov     [rsp+68h+picce.dwICC], 0C001h
0x18001f95a  call    InitCommonControlsEx
0x18001f95f  mov     ecx, ebx
0x18001f961  test    eax, eax
0x18001f963  mov     ebx, 1
0x18001f968  cmovnz  ecx, ebx
0x18001f96b  mov     ebx, ecx
0x18001f96d  mov     eax, ebx
0x18001f96f  add     rsp, 48h
0x18001f973  pop     rdi
0x18001f974  pop     rsi
0x18001f975  pop     rbp
0x18001f976  pop     rbx
0x18001f977  retn
```
