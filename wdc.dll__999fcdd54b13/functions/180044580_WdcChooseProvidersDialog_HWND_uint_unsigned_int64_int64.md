# WdcChooseProvidersDialog(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180044580`
- end: `0x180044b96`
- name: `?WdcChooseProvidersDialog@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1558`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18003b0ac`
- `0x180040730`
- `0x180044580`
- `0x1800462e0`
- `0x1800685ac`
- `0x180086010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800449bd`
- `KERNEL32!CreateThread` at `0x1800449bd`
- `KERNEL32!CloseHandle` at `0x180044a9e`
- `KERNEL32!CloseHandle` at `0x180044a9e`
- `KERNEL32!GetLastError` at `0x1800449cb`
- `KERNEL32!GetLastError` at `0x1800449cb`
- `USER32!EndDialog` at `0x180044604`
- `USER32!EndDialog` at `0x1800448a4`
- `USER32!EndDialog` at `0x180044a6f`
- `USER32!EndDialog` at `0x180044604`
- `USER32!EndDialog` at `0x1800448a4`
- `USER32!EndDialog` at `0x180044a6f`
- `USER32!NotifyWinEvent` at `0x18004485c`
- `USER32!NotifyWinEvent` at `0x18004485c`
- `USER32!SetDlgItemTextW` at `0x18004482f`
- `USER32!SetDlgItemTextW` at `0x18004483b`
- `USER32!SetDlgItemTextW` at `0x18004482f`
- `USER32!SetDlgItemTextW` at `0x18004483b`
- `USER32!GetWindowLongPtrW` at `0x180044685`
- `USER32!GetWindowLongPtrW` at `0x180044685`
- `USER32!SetWindowLongPtrW` at `0x1800448d3`
- `USER32!SetWindowLongPtrW` at `0x1800448d3`
- `USER32!EnableWindow` at `0x18004496c`
- `USER32!EnableWindow` at `0x18004496c`
- `USER32!SetWindowTextW` at `0x180044915`
- `USER32!SetWindowTextW` at `0x18004494a`
- `USER32!SetWindowTextW` at `0x180044915`
- `USER32!SetWindowTextW` at `0x18004494a`
- `USER32!SendMessageW` at `0x18004469e`
- `USER32!SendMessageW` at `0x1800446cd`
- `USER32!SendMessageW` at `0x180044724`
- `USER32!SendMessageW` at `0x180044a24`
- `USER32!SendMessageW` at `0x180044acd`
- `USER32!SendMessageW` at `0x180044aea`
- `USER32!SendMessageW` at `0x180044b12`
- `USER32!SendMessageW` at `0x180044b45`
- `USER32!SendMessageW` at `0x180044b80`
- `USER32!SendMessageW` at `0x18004469e`
- `USER32!SendMessageW` at `0x1800446cd`
- `USER32!SendMessageW` at `0x180044724`
- `USER32!SendMessageW` at `0x180044a24`
- `USER32!SendMessageW` at `0x180044acd`
- `USER32!SendMessageW` at `0x180044aea`
- `USER32!SendMessageW` at `0x180044b12`
- `USER32!SendMessageW` at `0x180044b45`
- `USER32!SendMessageW` at `0x180044b80`
- `USER32!GetDlgItem` at `0x18004466f`
- `USER32!GetDlgItem` at `0x180044809`
- `USER32!GetDlgItem` at `0x1800448bf`
- `USER32!GetDlgItem` at `0x18004493e`
- `USER32!GetDlgItem` at `0x180044ab6`
- `USER32!GetDlgItem` at `0x18004466f`
- `USER32!GetDlgItem` at `0x180044809`
- `USER32!GetDlgItem` at `0x1800448bf`
- `USER32!GetDlgItem` at `0x18004493e`
- `USER32!GetDlgItem` at `0x180044ab6`
- `USER32!LoadStringW` at `0x180044909`
- `USER32!LoadStringW` at `0x180044930`
- `USER32!LoadStringW` at `0x180044909`
- `USER32!LoadStringW` at `0x180044930`
- `OLEAUT32!__imp_SysAllocString` at `0x18004476b`
- `OLEAUT32!__imp_SysAllocString` at `0x18004476b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004475b`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a82`
- `OLEAUT32!__imp_SysFreeString` at `0x18004475b`
- `OLEAUT32!__imp_SysFreeString` at `0x180044a82`

## pseudocode

```c
__int64 __fastcall WdcChooseProvidersDialog(HWND hDlg, int a2, __int16 a3, _DWORD *a4)
{
  WCHAR *v4; // rdi
  void *v9; // r15
  const char *v10; // rdx
  int v11; // r8d
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  unsigned int v16; // r13d
  LONG_PTR v17; // rbx
  int String; // eax
  OLECHAR *v19; // rax
  const unsigned __int16 *v20; // rsi
  HWND v21; // rsi
  HWND v22; // r12
  const char *v23; // rdx
  int v24; // r8d
  HINSTANCE v25; // rcx
  HWND v26; // rax
  HANDLE v27; // rax
  signed int LastError; // eax
  HWND DlgItem; // rsi
  unsigned int v30; // ebx
  unsigned int v31; // r14d
  __int64 dwCreationFlags; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h]
  DWORD ThreadId; // [rsp+40h] [rbp-C0h] BYREF
  LONG_PTR WindowLongPtrW; // [rsp+48h] [rbp-B8h]
  HWND hWnd; // [rsp+50h] [rbp-B0h]
  HWND hwnd; // [rsp+58h] [rbp-A8h]
  LRESULT v39; // [rsp+60h] [rbp-A0h]
  LPARAM lParam; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+7Ch] [rbp-84h]
  int v42; // [rsp+80h] [rbp-80h]
  WCHAR *v43; // [rsp+88h] [rbp-78h]
  int v44; // [rsp+90h] [rbp-70h]
  LPARAM v45; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v46[32]; // [rsp+D8h] [rbp-28h] BYREF
  int v47; // [rsp+F8h] [rbp-8h]
  int v48; // [rsp+188h] [rbp+88h] BYREF

  v4 = 0;
  ThreadId = 0;
  v48 = 0;
  v9 = 0;
  memset_0(&v45, 0, 0x58u);
  bstrString = 0;
  v33 = 0;
  v12 = a2 - 16;
  if ( !v12 )
    goto LABEL_7;
  v13 = v12 - 62;
  if ( !v13 )
  {
    if ( a4[4] != -101 )
    {
      if ( a4[4] != -3 )
        return 0;
      SendMessageW(hDlg, 0x111u, 1u, 0);
      goto LABEL_8;
    }
    v4 = (WCHAR *)WdcAlloc(0x800u, v10, v11);
    if ( v4 )
    {
      *v4 = 0;
      DlgItem = GetDlgItem(hDlg, 3102);
      if ( (unsigned int)SendMessageW(DlgItem, 0x1032u, 0, 0) > 1 )
      {
        v30 = 0;
        v31 = SendMessageW(DlgItem, 0x1004u, 0, 0);
        if ( v31 )
        {
          do
          {
            if ( (SendMessageW(DlgItem, 0x102Cu, v30, 2) & 2) != 0 )
            {
              memset_0(v46, 0, 0x50u);
              LODWORD(v45) = 4;
              HIDWORD(v45) = v30;
              if ( (unsigned int)SendMessageW(DlgItem, 0x104Bu, 0, (LPARAM)&v45) )
              {
                if ( v47 )
                {
                  memset_0(&lParam, 0, 0x58u);
                  v42 = 2;
                  v41 = 0;
                  SendMessageW(DlgItem, 0x102Bu, v30, (LPARAM)&lParam);
                }
              }
            }
            ++v30;
          }
          while ( v30 < v31 );
        }
      }
      goto LABEL_8;
    }
    goto LABEL_55;
  }
  v14 = v13 - 194;
  if ( !v14 )
  {
    v22 = GetDlgItem(hDlg, 3102);
    SetWindowLongPtrW(hDlg, -21, (LONG_PTR)a4);
    v4 = (WCHAR *)WdcAlloc(0x800u, v23, v24);
    if ( v4 )
    {
      v25 = g_hInstance;
      *v4 = 0;
      LoadStringW(v25, 0x2BCu, v4, 1024);
      SetWindowTextW(hDlg, v4);
      LoadStringW(g_hInstance, 0x2BEu, v4, 1024);
      v26 = GetDlgItem(hDlg, 3101);
      SetWindowTextW(v26, v4);
      String = WdcListSetup(v22, 0, 0);
      LOWORD(v17) = String;
      if ( String >= 0 )
      {
        EnableWindow(v22, 0);
        String = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)a4 + 3) + 56LL))(*((_QWORD *)a4 + 3), &v48);
        LOWORD(v17) = String;
        if ( String >= 0 )
        {
          *(_QWORD *)a4 = hDlg;
          a4[2] = v48 > 0;
          v27 = CreateThread(0, 0, WdcChooseProvidersLoad, a4, 0, &ThreadId);
          v9 = v27;
          if ( v27 && v27 != (HANDLE)-1LL )
          {
LABEL_62:
            CloseHandle(v9);
            goto LABEL_8;
          }
          LastError = GetLastError();
          LODWORD(v17) = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              LODWORD(v17) = (unsigned __int16)LastError | 0x80070000;
            if ( (int)v17 >= 0 )
              goto LABEL_8;
          }
          else
          {
            LODWORD(v17) = -2147467259;
          }
          String = v17;
        }
      }
LABEL_48:
      LODWORD(dwCreationFlags) = String;
      goto LABEL_56;
    }
LABEL_55:
    LODWORD(dwCreationFlags) = -2147024882;
    LOWORD(v17) = 14;
LABEL_56:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
      "WdcChooseProvidersDialog",
      0,
      L"FAILURE: 0x%08x",
      dwCreationFlags);
LABEL_57:
    EndDialog(hDlg, (unsigned __int16)v17);
LABEL_58:
    if ( bstrString )
      SysFreeString(bstrString);
    if ( !v9 || v9 == (void *)-1LL )
      goto LABEL_8;
    goto LABEL_62;
  }
  if ( v14 != 1 )
    goto LABEL_8;
  if ( a3 == 1 )
  {
    v4 = (WCHAR *)WdcAlloc(0x800u, v10, v11);
    if ( !v4 )
      goto LABEL_55;
    *v4 = 0;
    hWnd = GetDlgItem(hDlg, 3102);
    WindowLongPtrW = GetWindowLongPtrW(hDlg, -21);
    v39 = SendMessageW(hWnd, 0x1004u, 0, 0);
    if ( (_DWORD)v39 )
    {
      v16 = 0;
      LODWORD(v17) = 0;
      while ( 1 )
      {
        if ( (SendMessageW(hWnd, 0x102Cu, v16, 2) & 2) != 0 )
        {
          if ( v33 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
            v33 = 0;
          }
          memset_0(&lParam, 0, 0x58u);
          v44 = 1024;
          v43 = v4;
          SendMessageW(hWnd, 0x1073u, v16, (LPARAM)&lParam);
          String = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(WindowLongPtrW + 24) + 112LL))(
                     *(_QWORD *)(WindowLongPtrW + 24),
                     &v33);
          LOWORD(v17) = String;
          if ( String < 0 )
            goto LABEL_48;
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          v19 = SysAllocString(v4);
          v20 = v19;
          if ( !v19 )
          {
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
              "WdcAssignString",
              0,
              L"FAILURE: 0x%08x",
              -2147024882);
            goto LABEL_55;
          }
          bstrString = v19;
          v17 = WindowLongPtrW;
          (*(void (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)v33 + 168LL))(
            v33,
            v19,
            *(_QWORD *)(WindowLongPtrW + 16));
          String = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v17 + 24) + 80LL))(
                     *(_QWORD *)(v17 + 24),
                     v33);
          LOWORD(v17) = String;
          if ( String < 0 )
            goto LABEL_48;
          String = WdcLoadString(0x2742u, v4, 0x400u);
          LOWORD(v17) = String;
          if ( String < 0 )
            goto LABEL_48;
          String = StringCchCatW(v4, 0x400u, v20);
          LODWORD(v17) = String;
          if ( String < 0 )
            goto LABEL_48;
          v21 = *(HWND *)(WindowLongPtrW + 32);
          hwnd = GetDlgItem(v21, 5222);
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef>::GetImpl'::`2'::impl) )
          {
            String = SetDlgItemTextW(v21, 5222, v4);
            LODWORD(v17) = String;
            if ( String < 0 )
              goto LABEL_48;
LABEL_30:
            NotifyWinEvent(0x8019u, hwnd, -4, 0);
            goto LABEL_31;
          }
          if ( SetDlgItemTextW(v21, 5222, v4) )
            goto LABEL_30;
        }
LABEL_31:
        if ( ++v16 >= (unsigned int)v39 )
          goto LABEL_35;
      }
    }
    LODWORD(v17) = 0;
LABEL_35:
    EndDialog(hDlg, 0);
    if ( (int)v17 >= 0 )
      goto LABEL_58;
    goto LABEL_57;
  }
  if ( a3 == 2 )
LABEL_7:
    EndDialog(hDlg, 1223);
LABEL_8:
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v4 )
    WdcFree(v4, v10, v11);
  return 0;
}

```

## disassembly

```asm
0x180044580  push    rbp
0x180044582  push    rbx
0x180044583  push    rsi
0x180044584  push    rdi
0x180044585  push    r12
0x180044587  push    r13
0x180044589  push    r14
0x18004458b  push    r15
0x18004458d  lea     rbp, [rsp-38h]
0x180044592  sub     rsp, 138h
0x180044599  xor     edi, edi
0x18004459b  mov     r12, r8
0x18004459e  mov     ebx, edx
0x1800445a0  mov     [rsp+170h+ThreadId], edi
0x1800445a4  mov     r14, rcx
0x1800445a7  mov     [rbp+70h+arg_8], edi
0x1800445ad  xor     edx, edx; Val
0x1800445af  lea     rcx, [rbp+70h+var_A0]; void *
0x1800445b3  lea     r13d, [rdi+58h]
0x1800445b7  mov     rsi, r9
0x1800445ba  mov     r8d, r13d; Size
0x1800445bd  xor     r15d, r15d
0x1800445c0  call    memset_0
0x1800445c5  xor     eax, eax
0x1800445c7  mov     [rsp+170h+bstrString], rax
0x1800445cc  mov     [rsp+170h+var_140], rax
0x1800445d1  sub     ebx, 10h
0x1800445d4  jz      short loc_1800445FC
0x1800445d6  sub     ebx, 3Eh ; '>'
0x1800445d9  jz      loc_180044A05
0x1800445df  sub     ebx, 0C2h
0x1800445e5  jz      loc_1800448B7
0x1800445eb  cmp     ebx, 1
0x1800445ee  jnz     short loc_18004460A
0x1800445f0  movzx   ecx, r12w
0x1800445f4  sub     ecx, ebx
0x1800445f6  jz      short loc_18004464C
0x1800445f8  cmp     ecx, ebx
0x1800445fa  jnz     short loc_18004460A
0x1800445fc  mov     edx, 4C7h; nResult
0x180044601  mov     rcx, r14; hDlg
0x180044604  call    cs:__imp_EndDialog
0x18004460a  mov     rcx, [rsp+170h+var_140]
0x18004460f  test    rcx, rcx
0x180044612  jz      short loc_180044629
0x180044614  mov     rax, [rcx]
0x180044617  mov     rax, [rax+10h]
0x18004461b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044620  mov     [rsp+170h+var_140], 0
0x180044629  test    rdi, rdi
0x18004462c  jz      short loc_180044636
0x18004462e  mov     rcx, rdi; void *
0x180044631  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180044636  xor     eax, eax
0x180044638  add     rsp, 138h
0x18004463f  pop     r15
0x180044641  pop     r14
0x180044643  pop     r13
0x180044645  pop     r12
0x180044647  pop     rdi
0x180044648  pop     rsi
0x180044649  pop     rbx
0x18004464a  pop     rbp
0x18004464b  retn
0x18004464c  mov     ecx, 800h; dwBytes
0x180044651  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180044656  mov     rdi, rax
0x180044659  test    rax, rax
0x18004465c  jz      loc_180044A41
0x180044662  xor     eax, eax
0x180044664  mov     edx, 0C1Eh; nIDDlgItem
0x180044669  mov     rcx, r14; hDlg
0x18004466c  mov     [rdi], ax
0x18004466f  call    cs:__imp_GetDlgItem
0x180044675  mov     edx, 0FFFFFFEBh; nIndex
0x18004467a  mov     rcx, r14; hWnd
0x18004467d  mov     rbx, rax
0x180044680  mov     [rsp+170h+hWnd], rax
0x180044685  call    cs:__imp_GetWindowLongPtrW
0x18004468b  xor     r9d, r9d; lParam
0x18004468e  xor     r8d, r8d; wParam
0x180044691  mov     edx, 1004h; Msg
0x180044696  mov     [rsp+170h+var_128], rax
0x18004469b  mov     rcx, rbx; hWnd
0x18004469e  call    cs:__imp_SendMessageW
0x1800446a4  mov     [rsp+170h+var_110], rax
0x1800446a9  test    eax, eax
0x1800446ab  jz      loc_18004489D
0x1800446b1  xor     r13d, r13d
0x1800446b4  xor     ebx, ebx
0x1800446b6  lea     r12d, [r13+2]
0x1800446ba  mov     rcx, [rsp+170h+hWnd]; hWnd
0x1800446bf  mov     r9, r12; lParam
0x1800446c2  mov     r8d, r13d; wParam
0x1800446c5  mov     edx, 102Ch; Msg
0x1800446ca  mov     esi, r13d
0x1800446cd  call    cs:__imp_SendMessageW
0x1800446d3  test    r12b, al
0x1800446d6  jz      loc_180044862
0x1800446dc  mov     rcx, [rsp+170h+var_140]
0x1800446e1  test    rcx, rcx
0x1800446e4  jz      short loc_1800446F7
0x1800446e6  mov     rax, [rcx]
0x1800446e9  mov     rax, [rax+10h]
0x1800446ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446f2  mov     [rsp+170h+var_140], r15
0x1800446f7  xor     edx, edx; Val
0x1800446f9  lea     rcx, [rsp+170h+lParam]; void *
0x1800446fe  lea     r8d, [rdx+58h]; Size
0x180044702  call    memset_0
0x180044707  mov     rcx, [rsp+170h+hWnd]; hWnd
0x18004470c  lea     r9, [rsp+170h+lParam]; lParam
0x180044711  mov     r8, rsi; wParam
0x180044714  mov     [rbp+70h+var_E0], 400h
0x18004471b  mov     edx, 1073h; Msg
0x180044720  mov     [rbp+70h+var_E8], rdi
0x180044724  call    cs:__imp_SendMessageW
0x18004472a  mov     rcx, [rsp+170h+var_128]
0x18004472f  lea     rdx, [rsp+170h+var_140]
0x180044734  mov     rcx, [rcx+18h]
0x180044738  mov     rax, [rcx]
0x18004473b  mov     rax, [rax+70h]
0x18004473f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044744  mov     ebx, eax
0x180044746  test    eax, eax
0x180044748  js      loc_1800449F3
0x18004474e  mov     rbx, [rsp+170h+bstrString]
0x180044753  test    rbx, rbx
0x180044756  jz      short loc_180044768
0x180044758  mov     rcx, rbx; bstrString
0x18004475b  call    cs:__imp_SysFreeString
0x180044761  xor     eax, eax
0x180044763  mov     [rsp+170h+bstrString], rax
0x180044768  mov     rcx, rdi; psz
0x18004476b  call    cs:__imp_SysAllocString
0x180044771  mov     rsi, rax
0x180044774  test    rax, rax
0x180044777  jz      loc_180044872
0x18004477d  mov     [rsp+170h+bstrString], rax
0x180044782  mov     rcx, [rsp+170h+var_140]
0x180044787  mov     rbx, [rsp+170h+var_128]
0x18004478c  mov     rdx, [rcx]
0x18004478f  mov     r8, [rbx+10h]
0x180044793  mov     rax, [rdx+0A8h]
0x18004479a  mov     rdx, rsi
0x18004479d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447a2  mov     rcx, [rbx+18h]
0x1800447a6  mov     rdx, [rsp+170h+var_140]
0x1800447ab  mov     rax, [rcx]
0x1800447ae  mov     rax, [rax+50h]
0x1800447b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447b7  mov     ebx, eax
0x1800447b9  test    eax, eax
0x1800447bb  js      loc_1800449F3
0x1800447c1  mov     r8d, 400h; cchBufferMax
0x1800447c7  mov     rdx, rdi; lpBuffer
0x1800447ca  mov     ecx, 2742h; uID
0x1800447cf  call    ?WdcLoadString@@YAJKPEAG_K@Z; WdcLoadString(ulong,ushort *,unsigned __int64)
0x1800447d4  mov     ebx, eax
0x1800447d6  test    eax, eax
0x1800447d8  js      loc_1800449F3
0x1800447de  mov     r8, rsi; unsigned __int16 *
0x1800447e1  mov     edx, 400h; unsigned __int64
0x1800447e6  mov     rcx, rdi; unsigned __int16 *
0x1800447e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800447ee  mov     ebx, eax
0x1800447f0  test    eax, eax
0x1800447f2  js      loc_1800449F3
0x1800447f8  mov     rax, [rsp+170h+var_128]
0x1800447fd  mov     edx, 1466h; nIDDlgItem
0x180044802  mov     rsi, [rax+20h]
0x180044806  mov     rcx, rsi; hDlg
0x180044809  call    cs:__imp_GetDlgItem
0x18004480f  mov     [rsp+170h+hwnd], rax
0x180044814  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef> `wil::Feature<__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef>::GetImpl(void)'::`2'::impl
0x18004481b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_a0ea56ca7a084596b5c3508f4de343ef>::__private_IsEnabled(void)
0x180044820  mov     r8, rdi; lpString
0x180044823  mov     edx, 1466h; nIDDlgItem
0x180044828  mov     rcx, rsi; hDlg
0x18004482b  test    al, al
0x18004482d  jz      short loc_18004483B
0x18004482f  call    cs:__imp_SetDlgItemTextW
0x180044835  test    eax, eax
0x180044837  jz      short loc_180044862
0x180044839  jmp     short loc_18004484B
0x18004483b  call    cs:__imp_SetDlgItemTextW
0x180044841  mov     ebx, eax
0x180044843  test    eax, eax
0x180044845  js      loc_1800449F3
0x18004484b  mov     rdx, [rsp+170h+hwnd]; hwnd
0x180044850  xor     r9d, r9d; idChild
0x180044853  mov     ecx, 8019h; event
0x180044858  lea     r8d, [r9-4]; idObject
0x18004485c  call    cs:__imp_NotifyWinEvent
0x180044862  inc     r13d
0x180044865  cmp     r13d, dword ptr [rsp+170h+var_110]
0x18004486a  jb      loc_1800446BA
0x180044870  jmp     short loc_18004489F
0x180044872  mov     esi, 8007000Eh
0x180044877  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18004487e  xor     r8d, r8d; int
0x180044881  mov     dword ptr [rsp+170h+dwCreationFlags], esi
0x180044885  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18004488c  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180044893  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180044898  jmp     loc_180044A46
0x18004489d  xor     ebx, ebx
0x18004489f  xor     edx, edx; nResult
0x1800448a1  mov     rcx, r14; hDlg
0x1800448a4  call    cs:__imp_EndDialog
0x1800448aa  test    ebx, ebx
0x1800448ac  jns     loc_180044A75
0x1800448b2  jmp     loc_180044A69
0x1800448b7  mov     edx, 0C1Eh; nIDDlgItem
0x1800448bc  mov     rcx, r14; hDlg
0x1800448bf  call    cs:__imp_GetDlgItem
0x1800448c5  mov     r8, rsi; dwNewLong
0x1800448c8  mov     edx, 0FFFFFFEBh; nIndex
0x1800448cd  mov     rcx, r14; hWnd
0x1800448d0  mov     r12, rax
0x1800448d3  call    cs:__imp_SetWindowLongPtrW
0x1800448d9  mov     ecx, 800h; dwBytes
0x1800448de  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800448e3  mov     rdi, rax
0x1800448e6  test    rax, rax
0x1800448e9  jz      loc_180044A41
0x1800448ef  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800448f6  xor     eax, eax
0x1800448f8  mov     r9d, 400h; cchBufferMax
0x1800448fe  mov     [rdi], ax
0x180044901  mov     r8, rdi; lpBuffer
0x180044904  mov     edx, 2BCh; uID
0x180044909  call    cs:__imp_LoadStringW
0x18004490f  mov     rdx, rdi; lpString
0x180044912  mov     rcx, r14; hWnd
0x180044915  call    cs:__imp_SetWindowTextW
0x18004491b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180044922  mov     r9d, 400h; cchBufferMax
0x180044928  mov     r8, rdi; lpBuffer
0x18004492b  mov     edx, 2BEh; uID
0x180044930  call    cs:__imp_LoadStringW
0x180044936  mov     edx, 0C1Dh; nIDDlgItem
0x18004493b  mov     rcx, r14; hDlg
0x18004493e  call    cs:__imp_GetDlgItem
0x180044944  mov     rcx, rax; hWnd
0x180044947  mov     rdx, rdi; lpString
0x18004494a  call    cs:__imp_SetWindowTextW
0x180044950  xor     r8d, r8d; unsigned int
0x180044953  xor     edx, edx; struct tagLVCOLUMNW *
0x180044955  mov     rcx, r12; hWnd
0x180044958  call    ?WdcListSetup@@YAJPEAUHWND__@@PEBUtagLVCOLUMNW@@I@Z; WdcListSetup(HWND__ *,tagLVCOLUMNW const *,uint)
0x18004495d  mov     ebx, eax
0x18004495f  test    eax, eax
0x180044961  js      loc_1800449F3
0x180044967  xor     edx, edx; bEnable
0x180044969  mov     rcx, r12; hWnd
0x18004496c  call    cs:__imp_EnableWindow
0x180044972  mov     rcx, [rsi+18h]
0x180044976  lea     rdx, [rbp+70h+arg_8]
0x18004497d  mov     rax, [rcx]
0x180044980  mov     rax, [rax+38h]
0x180044984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044989  mov     ebx, eax
0x18004498b  test    eax, eax
0x18004498d  js      short loc_1800449F3
0x18004498f  xor     eax, eax
0x180044991  mov     [rsi], r14
0x180044994  cmp     [rbp+70h+arg_8], eax
0x18004499a  lea     r8, ?WdcChooseProvidersLoad@@YAKPEAX@Z; lpStartAddress
0x1800449a1  mov     r9, rsi; lpParameter
0x1800449a4  setnle  al
0x1800449a7  xor     edx, edx; dwStackSize
0x1800449a9  mov     [rsi+8], eax
0x1800449ac  xor     ecx, ecx; lpThreadAttributes
0x1800449ae  lea     rax, [rsp+170h+ThreadId]
0x1800449b3  mov     [rsp+170h+lpThreadId], rax; lpThreadId
0x1800449b8  mov     dword ptr [rsp+170h+dwCreationFlags], r15d; dwCreationFlags
0x1800449bd  call    cs:__imp_CreateThread
0x1800449c3  mov     r15, rax
0x1800449c6  test    rax, rax
0x1800449c9  jnz     short loc_1800449F9
0x1800449cb  call    cs:__imp_GetLastError
0x1800449d1  mov     ebx, eax
0x1800449d3  test    eax, eax
0x1800449d5  jz      short loc_1800449EC
0x1800449d7  jle     short loc_1800449E2
0x1800449d9  movzx   ebx, ax
0x1800449dc  or      ebx, 80070000h
0x1800449e2  test    ebx, ebx
0x1800449e4  jns     loc_18004460A
0x1800449ea  jmp     short loc_1800449F1
0x1800449ec  mov     ebx, 80004005h
0x1800449f1  mov     eax, ebx
0x1800449f3  mov     dword ptr [rsp+170h+dwCreationFlags], eax
0x1800449f7  jmp     short loc_180044A4C
0x1800449f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800449fd  jnz     loc_180044A9B
0x180044a03  jmp     short loc_1800449CB
0x180044a05  cmp     dword ptr [rsi+10h], 0FFFFFF9Bh
0x180044a09  jz      short loc_180044A2F
  ... truncated ...
```
