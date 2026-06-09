# SystemParametersInfoAsync_WorkerThread(void *)

- ea: `0x1800036c0`
- end: `0x180003af7`
- name: `?SystemParametersInfoAsync_WorkerThread@@YAKPEAX@Z`
- size: `1079`
- prototype: `unsigned int __fastcall(struct SPIS_INFO *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800035f4`
- `0x18003188c`

## callees

- `0x1800036c0`
- `0x180003b00`
- `0x1800089c0`
- `0x180030930`
- `0x180030988`
- `0x180032f78`
- `0x18003300c`
- `0x180033044`
- `0x180033cd0`
- `0x1800358c0`
- `0x18003dbb8`
- `0x18005f784`
- `0x18005fa38`
- `0x18005fe60`
- `0x18005fed8`
- `0x18005ff70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003ac1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a95`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800036f7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800036f7`
- `USER32!SetThreadDpiAwarenessContext` at `0x180003712`
- `USER32!SetThreadDpiAwarenessContext` at `0x180003712`
- `USER32!GetSystemMetrics` at `0x18000382e`
- `USER32!GetSystemMetrics` at `0x1800039dd`
- `USER32!GetSystemMetrics` at `0x18000382e`
- `USER32!GetSystemMetrics` at `0x1800039dd`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800038bf`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800039ae`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800038bf`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800039ae`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180003909`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180003909`

## string_xrefs

- `0x1800038db`: `=%ws, uiAction= %d, uiParam=%d, ThreadDpiAwarenessContext=0x%x`

## pseudocode

```c
__int64 __fastcall SystemParametersInfoAsync_WorkerThread(struct SPIS_INFO *a1)
{
  HMODULE LibraryW; // r14
  int v3; // r15d
  int v4; // eax
  const wchar_t *v5; // rsi
  int v6; // ebx
  int v7; // ebx
  double IconMetricsRatio; // xmm0_8
  int SystemMetrics; // ebx
  int RegSpacingMetric; // ebx
  unsigned int DpiForDefaultMonitor; // ebx
  __int64 ThreadDpiAwarenessContext; // rax
  __int64 v13; // rcx
  int v14; // ebx
  double v15; // xmm0_8
  __int64 v16; // rbx
  __int64 v17; // rbx
  void *v18; // rcx
  CDimmedWindow *v19; // rcx
  __int64 v21; // [rsp+40h] [rbp-268h] BYREF
  _BYTE v22[16]; // [rsp+48h] [rbp-260h] BYREF
  int v23; // [rsp+58h] [rbp-250h] BYREF
  int v24; // [rsp+5Ch] [rbp-24Ch]
  HMODULE v25; // [rsp+60h] [rbp-248h]
  unsigned __int16 v26[256]; // [rsp+70h] [rbp-238h] BYREF

  LibraryW = LoadLibraryW(L"desk.cpl");
  v25 = LibraryW;
  if ( !a1 )
    goto LABEL_25;
  SetThreadDpiAwarenessContext(*((_QWORD *)a1 + 4));
  v21 = 0;
  v23 = 11;
  v3 = 38;
  v24 = 38;
  v4 = *((_DWORD *)a1 + 1);
  switch ( v4 )
  {
    case 4131:
      v5 = L"FlatMenu";
      break;
    case 42:
      v5 = L"NonClientMetrics";
      break;
    case 34:
      v5 = L"IconTitleLogFont";
      break;
    default:
      if ( v4 != 13 )
      {
        if ( v4 != 24 )
        {
          v5 = &Default;
          break;
        }
        v23 = 12;
        v3 = 39;
        v24 = 39;
      }
      v5 = L"IconVerticalSpacing";
      if ( v4 != 24 )
        v5 = L"IconHorizontalSpacing";
      tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::start(
        &v21,
        v22);
      v6 = *((_DWORD *)a1 + 1);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                               &v21,
                               v22)
                + 288LL) = v6;
      tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
      v7 = *((_DWORD *)a1 + 2);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                               &v21,
                               v22)
                + 292LL) = v7;
      tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
      IconMetricsRatio = IconSpacingMetrics::GetIconMetricsRatio((IconSpacingMetrics *)&v23);
      *(double *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                               &v21,
                               v22)
                + 272LL) = IconMetricsRatio;
      tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
      SystemMetrics = GetSystemMetrics(v3);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                               &v21,
                               v22)
                + 320LL) = SystemMetrics;
      tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
      RegSpacingMetric = IconSpacingMetrics::GetRegSpacingMetric((IconSpacingMetrics *)&v23);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                               &v21,
                               v22)
                + 328LL) = RegSpacingMetric;
      tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
      DpiForDefaultMonitor = GetDpiForDefaultMonitor();
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                               &v21,
                               v22)
                + 336LL) = DpiForDefaultMonitor;
      tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
      *((_DWORD *)a1 + 2) = IconSpacingMetrics::GetCorrectSpacing((IconSpacingMetrics *)&v23, *((_DWORD *)a1 + 2));
      break;
  }
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  StringCchPrintfW(
    v26,
    0x100u,
    L"=%ws, uiAction= %d, uiParam=%d, ThreadDpiAwarenessContext=0x%x",
    v5,
    *((_DWORD *)a1 + 1),
    *((_DWORD *)a1 + 2),
    ThreadDpiAwarenessContext);
  ThemesTelemetry::SystemMetrics<unsigned short const (&)[39],unsigned short (&)[256]>(v13, v26);
  ClassicSystemParametersInfoW(
    *((unsigned int *)a1 + 1),
    *((unsigned int *)a1 + 2),
    *((_QWORD *)a1 + 2),
    *((unsigned int *)a1 + 3));
  if ( (*((_DWORD *)a1 + 1) == 13 || *((_DWORD *)a1 + 1) == 24)
    && (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator bool(&v21) )
  {
    v14 = *((_DWORD *)a1 + 2);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                             &v21,
                             v22)
              + 296LL) = v14;
    tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
    v15 = IconSpacingMetrics::GetIconMetricsRatio((IconSpacingMetrics *)&v23);
    *(double *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                             &v21,
                             v22)
              + 280LL) = v15;
    tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
    v16 = *((_QWORD *)a1 + 4);
    *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                             &v21,
                             v22)
              + 304LL) = v16;
    tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
    v17 = GetThreadDpiAwarenessContext();
    *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                             &v21,
                             v22)
              + 312LL) = v17;
    tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
    LODWORD(v17) = GetSystemMetrics(v3);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                             &v21,
                             v22)
              + 324LL) = v17;
    tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
    LODWORD(v17) = IconSpacingMetrics::GetRegSpacingMetric((IconSpacingMetrics *)&v23);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                             &v21,
                             v22)
              + 332LL) = v17;
    tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
    LODWORD(v17) = GetDpiForDefaultMonitor();
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(
                             &v21,
                             v22)
              + 340LL) = v17;
    tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(v22);
    tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::complete(&v21);
  }
  RunThemeUiDpiAwarenessMatchesTest(a1);
  if ( *(_DWORD *)a1 )
  {
    v18 = (void *)*((_QWORD *)a1 + 2);
    if ( v18 )
      LocalFree(v18);
  }
  v19 = (CDimmedWindow *)*((_QWORD *)a1 + 3);
  if ( v19 )
    CDimmedWindow::Release(v19);
  LocalFree(a1);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>,wil::err_returncode_policy>(&v21);
LABEL_25:
  if ( LibraryW )
    FreeLibrary(LibraryW);
  return 0;
}

```

## disassembly

```asm
0x1800036c0  mov     rax, rsp
0x1800036c3  mov     [rax+10h], rbx
0x1800036c7  mov     [rax+18h], rsi
0x1800036cb  push    rdi
0x1800036cc  push    r14
0x1800036ce  push    r15
0x1800036d0  sub     rsp, 290h
0x1800036d7  movaps  xmmword ptr [rax-28h], xmm6
0x1800036db  mov     rax, cs:__security_cookie
0x1800036e2  xor     rax, rsp
0x1800036e5  mov     [rsp+2A8h+var_38], rax
0x1800036ed  mov     rdi, rcx
0x1800036f0  lea     rcx, LibFileName; "desk.cpl"
0x1800036f7  call    cs:__imp_LoadLibraryW
0x1800036fd  mov     r14, rax
0x180003700  mov     [rsp+2A8h+var_248], rax
0x180003705  test    rdi, rdi
0x180003708  jz      loc_180003AB9
0x18000370e  mov     rcx, [rdi+20h]
0x180003712  call    cs:__imp_SetThreadDpiAwarenessContext
0x180003718  nop
0x180003719  mov     [rsp+2A8h+var_268], 0
0x180003722  mov     [rsp+2A8h+var_250], 0Bh
0x18000372a  mov     r15d, 26h ; '&'
0x180003730  mov     [rsp+2A8h+var_24C], r15d
0x180003735  mov     eax, [rdi+4]
0x180003738  cmp     eax, 1023h
0x18000373d  jnz     short loc_18000374B
0x18000373f  lea     rsi, aFlatmenu; "FlatMenu"
0x180003746  jmp     loc_1800038BF
0x18000374b  cmp     eax, 2Ah ; '*'
0x18000374e  jnz     short loc_18000375C
0x180003750  lea     rsi, aNonclientmetri; "NonClientMetrics"
0x180003757  jmp     loc_1800038BF
0x18000375c  cmp     eax, 22h ; '"'
0x18000375f  jnz     short loc_18000376D
0x180003761  lea     rsi, aIcontitlelogfo; "IconTitleLogFont"
0x180003768  jmp     loc_1800038BF
0x18000376d  cmp     eax, 0Dh
0x180003770  jz      short loc_18000378C
0x180003772  cmp     eax, 18h
0x180003775  jnz     loc_180003AA8
0x18000377b  mov     [rsp+2A8h+var_250], 0Ch
0x180003783  lea     r15d, [rax+0Fh]
0x180003787  mov     [rsp+2A8h+var_24C], r15d
0x18000378c  lea     rcx, aIconhorizontal; "IconHorizontalSpacing"
0x180003793  lea     rsi, aIconverticalsp; "IconVerticalSpacing"
0x18000379a  cmp     eax, 18h
0x18000379d  cmovnz  rsi, rcx
0x1800037a1  lea     rdx, [rsp+2A8h+var_260]
0x1800037a6  lea     rcx, [rsp+2A8h+var_268]
0x1800037ab  call    ?start@?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::start(void)
0x1800037b0  mov     ebx, [rdi+4]
0x1800037b3  lea     rdx, [rsp+2A8h+var_260]
0x1800037b8  lea     rcx, [rsp+2A8h+var_268]
0x1800037bd  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x1800037c2  mov     rcx, [rax]
0x1800037c5  mov     [rcx+120h], ebx
0x1800037cb  lea     rcx, [rsp+2A8h+var_260]
0x1800037d0  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x1800037d5  mov     ebx, [rdi+8]
0x1800037d8  lea     rdx, [rsp+2A8h+var_260]
0x1800037dd  lea     rcx, [rsp+2A8h+var_268]
0x1800037e2  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x1800037e7  mov     rcx, [rax]
0x1800037ea  mov     [rcx+124h], ebx
0x1800037f0  lea     rcx, [rsp+2A8h+var_260]
0x1800037f5  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x1800037fa  lea     rcx, [rsp+2A8h+var_250]; this
0x1800037ff  call    ?GetIconMetricsRatio@IconSpacingMetrics@@QEBANXZ; IconSpacingMetrics::GetIconMetricsRatio(void)
0x180003804  movaps  xmm6, xmm0
0x180003807  lea     rdx, [rsp+2A8h+var_260]
0x18000380c  lea     rcx, [rsp+2A8h+var_268]
0x180003811  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x180003816  mov     rcx, [rax]
0x180003819  movsd   qword ptr [rcx+110h], xmm6
0x180003821  lea     rcx, [rsp+2A8h+var_260]
0x180003826  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x18000382b  mov     ecx, r15d; nIndex
0x18000382e  call    cs:__imp_GetSystemMetrics
0x180003834  mov     ebx, eax
0x180003836  lea     rdx, [rsp+2A8h+var_260]
0x18000383b  lea     rcx, [rsp+2A8h+var_268]
0x180003840  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x180003845  mov     rcx, [rax]
0x180003848  mov     [rcx+140h], ebx
0x18000384e  lea     rcx, [rsp+2A8h+var_260]
0x180003853  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x180003858  lea     rcx, [rsp+2A8h+var_250]; this
0x18000385d  call    ?GetRegSpacingMetric@IconSpacingMetrics@@QEBAHXZ; IconSpacingMetrics::GetRegSpacingMetric(void)
0x180003862  mov     ebx, eax
0x180003864  lea     rdx, [rsp+2A8h+var_260]
0x180003869  lea     rcx, [rsp+2A8h+var_268]
0x18000386e  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x180003873  mov     rcx, [rax]
0x180003876  mov     [rcx+148h], ebx
0x18000387c  lea     rcx, [rsp+2A8h+var_260]
0x180003881  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x180003886  call    ?GetDpiForDefaultMonitor@@YAIXZ; GetDpiForDefaultMonitor(void)
0x18000388b  mov     ebx, eax
0x18000388d  lea     rdx, [rsp+2A8h+var_260]
0x180003892  lea     rcx, [rsp+2A8h+var_268]
0x180003897  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x18000389c  mov     rcx, [rax]
0x18000389f  mov     [rcx+150h], ebx
0x1800038a5  lea     rcx, [rsp+2A8h+var_260]
0x1800038aa  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x1800038af  mov     edx, [rdi+8]; unsigned int
0x1800038b2  lea     rcx, [rsp+2A8h+var_250]; this
0x1800038b7  call    ?GetCorrectSpacing@IconSpacingMetrics@@QEBAII@Z; IconSpacingMetrics::GetCorrectSpacing(uint)
0x1800038bc  mov     [rdi+8], eax
0x1800038bf  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800038c5  mov     [rsp+2A8h+var_278], rax
0x1800038ca  mov     eax, [rdi+8]
0x1800038cd  mov     [rsp+2A8h+var_280], eax
0x1800038d1  mov     eax, [rdi+4]
0x1800038d4  mov     [rsp+2A8h+var_288], eax
0x1800038d8  mov     r9, rsi
0x1800038db  lea     r8, aWsUiactionDUip; "=%ws, uiAction= %d, uiParam=%d, ThreadD"...
0x1800038e2  mov     edx, 100h; unsigned __int64
0x1800038e7  lea     rcx, [rsp+2A8h+var_238]; unsigned __int16 *
0x1800038ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800038f1  lea     rdx, [rsp+2A8h+var_238]
0x1800038f6  call    ??$SystemMetrics@AEAY0CH@$$CBGAEAY0BAA@G@ThemesTelemetry@@SAXAEAY0CH@$$CBGAEAY0BAA@G@Z; ThemesTelemetry::SystemMetrics<ushort const (&)[39],ushort (&)[256]>(ushort const (&)[39],ushort (&)[256])
0x1800038fb  mov     r9d, [rdi+0Ch]
0x1800038ff  mov     r8, [rdi+10h]
0x180003903  mov     edx, [rdi+8]
0x180003906  mov     ecx, [rdi+4]
0x180003909  call    cs:__imp_ClassicSystemParametersInfoW
0x18000390f  cmp     dword ptr [rdi+4], 0Dh
0x180003913  jz      short loc_18000391F
0x180003915  cmp     dword ptr [rdi+4], 18h
0x180003919  jnz     loc_180003A68
0x18000391f  lea     rcx, [rsp+2A8h+var_268]
0x180003924  call    ??B?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator bool(void)
0x180003929  test    al, al
0x18000392b  jz      loc_180003A68
0x180003931  mov     ebx, [rdi+8]
0x180003934  lea     rdx, [rsp+2A8h+var_260]
0x180003939  lea     rcx, [rsp+2A8h+var_268]
0x18000393e  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x180003943  mov     rcx, [rax]
0x180003946  mov     [rcx+128h], ebx
0x18000394c  lea     rcx, [rsp+2A8h+var_260]
0x180003951  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x180003956  lea     rcx, [rsp+2A8h+var_250]; this
0x18000395b  call    ?GetIconMetricsRatio@IconSpacingMetrics@@QEBANXZ; IconSpacingMetrics::GetIconMetricsRatio(void)
0x180003960  movaps  xmm6, xmm0
0x180003963  lea     rdx, [rsp+2A8h+var_260]
0x180003968  lea     rcx, [rsp+2A8h+var_268]
0x18000396d  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x180003972  mov     rcx, [rax]
0x180003975  movsd   qword ptr [rcx+118h], xmm6
0x18000397d  lea     rcx, [rsp+2A8h+var_260]
0x180003982  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x180003987  mov     rbx, [rdi+20h]
0x18000398b  lea     rdx, [rsp+2A8h+var_260]
0x180003990  lea     rcx, [rsp+2A8h+var_268]
0x180003995  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x18000399a  mov     rcx, [rax]
0x18000399d  mov     [rcx+130h], rbx
0x1800039a4  lea     rcx, [rsp+2A8h+var_260]
0x1800039a9  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x1800039ae  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800039b4  mov     rbx, rax
0x1800039b7  lea     rdx, [rsp+2A8h+var_260]
0x1800039bc  lea     rcx, [rsp+2A8h+var_268]
0x1800039c1  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x1800039c6  mov     rcx, [rax]
0x1800039c9  mov     [rcx+138h], rbx
0x1800039d0  lea     rcx, [rsp+2A8h+var_260]
0x1800039d5  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x1800039da  mov     ecx, r15d; nIndex
0x1800039dd  call    cs:__imp_GetSystemMetrics
0x1800039e3  mov     ebx, eax
0x1800039e5  lea     rdx, [rsp+2A8h+var_260]
0x1800039ea  lea     rcx, [rsp+2A8h+var_268]
0x1800039ef  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x1800039f4  mov     rcx, [rax]
0x1800039f7  mov     [rcx+144h], ebx
0x1800039fd  lea     rcx, [rsp+2A8h+var_260]
0x180003a02  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x180003a07  lea     rcx, [rsp+2A8h+var_250]; this
0x180003a0c  call    ?GetRegSpacingMetric@IconSpacingMetrics@@QEBAHXZ; IconSpacingMetrics::GetRegSpacingMetric(void)
0x180003a11  mov     ebx, eax
0x180003a13  lea     rdx, [rsp+2A8h+var_260]
0x180003a18  lea     rcx, [rsp+2A8h+var_268]
0x180003a1d  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x180003a22  mov     rcx, [rax]
0x180003a25  mov     [rcx+14Ch], ebx
0x180003a2b  lea     rcx, [rsp+2A8h+var_260]
0x180003a30  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x180003a35  call    ?GetDpiForDefaultMonitor@@YAIXZ; GetDpiForDefaultMonitor(void)
0x180003a3a  mov     ebx, eax
0x180003a3c  lea     rdx, [rsp+2A8h+var_260]
0x180003a41  lea     rcx, [rsp+2A8h+var_268]
0x180003a46  call    ??C?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::operator->(void)
0x180003a4b  mov     rcx, [rax]
0x180003a4e  mov     [rcx+154h], ebx
0x180003a54  lea     rcx, [rsp+2A8h+var_260]
0x180003a59  call    ??1?$test_data_control@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::~test_data_control<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>(void)
0x180003a5e  lea     rcx, [rsp+2A8h+var_268]
0x180003a63  call    ?complete@?$tip_test@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>>::complete(void)
0x180003a68  mov     rcx, rdi; struct SPIS_INFO *
0x180003a6b  call    ?RunThemeUiDpiAwarenessMatchesTest@@YAXPEBUSPIS_INFO@@@Z; RunThemeUiDpiAwarenessMatchesTest(SPIS_INFO const *)
0x180003a70  cmp     dword ptr [rdi], 0
0x180003a73  jz      short loc_180003A84
0x180003a75  mov     rcx, [rdi+10h]; hMem
0x180003a79  test    rcx, rcx
0x180003a7c  jz      short loc_180003A84
0x180003a7e  call    cs:__imp_LocalFree
0x180003a84  mov     rcx, [rdi+18h]; this
0x180003a88  test    rcx, rcx
0x180003a8b  jz      short loc_180003A92
0x180003a8d  call    ?Release@CDimmedWindow@@QEAAKXZ; CDimmedWindow::Release(void)
0x180003a92  mov     rcx, rdi; hMem
0x180003a95  call    cs:__imp_LocalFree
0x180003a9b  lea     rcx, [rsp+2A8h+var_268]
0x180003aa0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ThemeUiIconSpacingMetricsUpdatedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ThemeUiIconSpacingMetricsUpdatedTest,_tip_ThemeUiIconSpacingMetricsUpdatedTest>,wil::err_returncode_policy>(void)
0x180003aa5  nop
0x180003aa6  jmp     short loc_180003AB9
0x180003aa8  lea     rsi, Default
0x180003aaf  jmp     loc_1800038BF
0x180003ab4  mov     r14, [rsp+2A8h+var_248]
0x180003ab9  test    r14, r14
0x180003abc  jz      short loc_180003AC7
0x180003abe  mov     rcx, r14; hLibModule
0x180003ac1  call    cs:__imp_FreeLibrary
0x180003ac7  xor     eax, eax
0x180003ac9  mov     rcx, [rsp+2A8h+var_38]
0x180003ad1  xor     rcx, rsp; StackCookie
0x180003ad4  call    __security_check_cookie
0x180003ad9  lea     r11, [rsp+2A8h+var_18]
0x180003ae1  mov     rbx, [r11+28h]
0x180003ae5  mov     rsi, [r11+30h]
0x180003ae9  movaps  xmm6, xmmword ptr [r11-10h]
0x180003aee  mov     rsp, r11
0x180003af1  pop     r15
0x180003af3  pop     r14
0x180003af5  pop     rdi
0x180003af6  retn
```
