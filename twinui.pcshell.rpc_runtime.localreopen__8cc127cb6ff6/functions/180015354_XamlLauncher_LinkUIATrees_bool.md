# XamlLauncher::LinkUIATrees(bool)

- ea: `0x180015354`
- end: `0x1800155dc`
- name: `?LinkUIATrees@XamlLauncher@@AEAAX_N@Z`
- size: `648`
- prototype: `void __fastcall(XamlLauncher *__hidden this, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800152f0`
- `0x180015340`
- `0x1804acb70`

## callees

- `0x180015354`
- `0x1800155e4`
- `0x180015804`
- `0x180016e68`
- `0x180031c70`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180015423`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180015440`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18001545f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180015566`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180015423`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180015440`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18001545f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180015566`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1800153b9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1800153ed`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180015490`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1800154c0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1800153b9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1800153ed`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180015490`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1800154c0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180015478`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x1800154d5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18001553e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18001554f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180015478`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x1800154d5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18001553e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18001554f`

## string_xrefs

- `0x180015452`: `NonComponentUIWindow`
- `0x180015548`: `NonComponentUIWindow`

## pseudocode

```c
void __fastcall XamlLauncher::LinkUIATrees(XamlLauncher *this, char a2)
{
  __int64 v3; // rcx
  int (__fastcall *v4)(__int64, HWND *); // rax
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  int v8; // eax
  const char *v9; // r9
  HWND v10[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  int v12; // [rsp+40h] [rbp+10h] BYREF
  int v13; // [rsp+50h] [rbp+20h] BYREF
  HWND hWnd; // [rsp+58h] [rbp+28h] BYREF

  v10[0] = 0;
  v3 = *((_QWORD *)this + 22);
  hWnd = 0;
  if ( v3 && *((_QWORD *)this + 21) )
  {
    v4 = *(int (__fastcall **)(__int64, HWND *))(*(_QWORD *)v3 + 456LL);
    if ( a2 )
    {
      if ( v4(v3, &hWnd) >= 0
        && IsWindow(hWnd)
        && (*(int (__fastcall **)(_QWORD, HWND *))(**((_QWORD **)this + 21) + 320LL))(*((_QWORD *)this + 21), v10) >= 0
        && IsWindow(v10[0]) )
      {
        v12 = (int)hWnd;
        v13 = (int)v10[0];
        StartWindowTelemetry::LinkingUIATrees<unsigned int,unsigned int>(&v13, &v12);
        if ( !SetPropW(hWnd, L"CrossProcessParentHWND", v10[0]) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x749,
            (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncher.cpp",
            v5);
        if ( !SetPropW(v10[0], L"CrossProcessChildHWND", hWnd) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x74A,
            (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncher.cpp",
            v6);
        if ( !SetPropW(hWnd, L"NonComponentUIWindow", HANDLE_FLAG_INHERIT) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x74D,
            (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncher.cpp",
            v7);
        RemovePropW(hWnd, L"UIA_WindowPatternEnabled");
      }
    }
    else
    {
      if ( v4(v3, &hWnd) >= 0 )
      {
        if ( IsWindow(hWnd) )
        {
          RemovePropW(hWnd, L"CrossProcessParentHWND");
          RemovePropW(hWnd, L"NonComponentUIWindow");
          if ( !SetPropW(hWnd, L"UIA_WindowPatternEnabled", HANDLE_FLAG_INHERIT) )
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x761,
              (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncher.cpp",
              v9);
        }
      }
      if ( (*(int (__fastcall **)(_QWORD, HWND *))(**((_QWORD **)this + 21) + 320LL))(*((_QWORD *)this + 21), v10) >= 0
        && IsWindow(v10[0]) )
      {
        RemovePropW(v10[0], L"CrossProcessChildHWND");
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 22) + 472LL))(*((_QWORD *)this + 22));
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x769,
          (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncher.cpp",
          (const char *)(unsigned int)v8,
          (int)v10[0]);
      v12 = (int)hWnd;
      v13 = (int)v10[0];
      StartWindowTelemetry::UnlinkingUIATrees<unsigned int,unsigned int>(&v13, &v12);
    }
  }
}

```

## disassembly

```asm
0x180015354  mov     [rsp-8+arg_8], rdi
0x180015359  push    rbp
0x18001535a  mov     rbp, rsp
0x18001535d  sub     rsp, 30h
0x180015361  mov     rdi, rcx
0x180015364  mov     [rbp+var_10], 0
0x18001536c  mov     rcx, [rcx+0B0h]
0x180015373  mov     [rbp+hWnd], 0
0x18001537b  test    rcx, rcx
0x18001537e  jz      loc_18001550E
0x180015384  cmp     qword ptr [rdi+0A8h], 0
0x18001538c  jz      loc_18001550E
0x180015392  mov     rax, [rcx]
0x180015395  test    dl, dl
0x180015397  lea     rdx, [rbp+hWnd]
0x18001539b  mov     rax, [rax+1C8h]
0x1800153a2  jz      loc_180015483
0x1800153a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ad  test    eax, eax
0x1800153af  js      loc_18001550E
0x1800153b5  mov     rcx, [rbp+hWnd]; hWnd
0x1800153b9  call    cs:__imp_IsWindow
0x1800153bf  test    eax, eax
0x1800153c1  jz      loc_18001550E
0x1800153c7  mov     rcx, [rdi+0A8h]
0x1800153ce  lea     rdx, [rbp+var_10]
0x1800153d2  mov     rax, [rcx]
0x1800153d5  mov     rax, [rax+140h]
0x1800153dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153e1  test    eax, eax
0x1800153e3  js      loc_18001550E
0x1800153e9  mov     rcx, [rbp+var_10]; hWnd
0x1800153ed  call    cs:__imp_IsWindow
0x1800153f3  test    eax, eax
0x1800153f5  jz      loc_18001550E
0x1800153fb  mov     eax, dword ptr [rbp+hWnd]
0x1800153fe  lea     rdx, [rbp+arg_0]
0x180015402  mov     [rbp+arg_0], eax
0x180015405  lea     rcx, [rbp+arg_10]
0x180015409  mov     eax, dword ptr [rbp+var_10]
0x18001540c  mov     [rbp+arg_10], eax
0x18001540f  call    ??$LinkingUIATrees@II@StartWindowTelemetry@@SAX$$QEAI0@Z; StartWindowTelemetry::LinkingUIATrees<uint,uint>(uint &&,uint &&)
0x180015414  mov     r8, [rbp+var_10]; hData
0x180015418  lea     rdx, aCrossprocesspa; "CrossProcessParentHWND"
0x18001541f  mov     rcx, [rbp+hWnd]; hWnd
0x180015423  call    cs:__imp_SetPropW
0x180015429  test    eax, eax
0x18001542b  jz      loc_18001558E
0x180015431  mov     r8, [rbp+hWnd]; hData
0x180015435  lea     rdx, aCrossprocessch; "CrossProcessChildHWND"
0x18001543c  mov     rcx, [rbp+var_10]; hWnd
0x180015440  call    cs:__imp_SetPropW
0x180015446  test    eax, eax
0x180015448  jz      loc_1800155A8
0x18001544e  mov     rcx, [rbp+hWnd]; hWnd
0x180015452  lea     rdx, aNoncomponentui; "NonComponentUIWindow"
0x180015459  mov     r8d, 1; hData
0x18001545f  call    cs:__imp_SetPropW
0x180015465  test    eax, eax
0x180015467  jz      loc_1800155C2
0x18001546d  mov     rcx, [rbp+hWnd]; hWnd
0x180015471  lea     rdx, aUiaWindowpatte; "UIA_WindowPatternEnabled"
0x180015478  call    cs:__imp_RemovePropW
0x18001547e  jmp     loc_18001550E
0x180015483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015488  test    eax, eax
0x18001548a  js      short loc_18001549E
0x18001548c  mov     rcx, [rbp+hWnd]; hWnd
0x180015490  call    cs:__imp_IsWindow
0x180015496  test    eax, eax
0x180015498  jnz     loc_180015533
0x18001549e  mov     rcx, [rdi+0A8h]
0x1800154a5  lea     rdx, [rbp+var_10]
0x1800154a9  mov     rax, [rcx]
0x1800154ac  mov     rax, [rax+140h]
0x1800154b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b8  test    eax, eax
0x1800154ba  js      short loc_1800154DB
0x1800154bc  mov     rcx, [rbp+var_10]; hWnd
0x1800154c0  call    cs:__imp_IsWindow
0x1800154c6  test    eax, eax
0x1800154c8  jz      short loc_1800154DB
0x1800154ca  mov     rcx, [rbp+var_10]; hWnd
0x1800154ce  lea     rdx, aCrossprocessch; "CrossProcessChildHWND"
0x1800154d5  call    cs:__imp_RemovePropW
0x1800154db  mov     rcx, [rdi+0B0h]
0x1800154e2  mov     rax, [rcx]
0x1800154e5  mov     rax, [rax+1D8h]
0x1800154ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154f1  test    eax, eax
0x1800154f3  js      short loc_180015519
0x1800154f5  mov     eax, dword ptr [rbp+hWnd]
0x1800154f8  lea     rdx, [rbp+arg_0]
0x1800154fc  mov     [rbp+arg_0], eax
0x1800154ff  lea     rcx, [rbp+arg_10]
0x180015503  mov     eax, dword ptr [rbp+var_10]
0x180015506  mov     [rbp+arg_10], eax
0x180015509  call    ??$UnlinkingUIATrees@II@StartWindowTelemetry@@SAX$$QEAI0@Z; StartWindowTelemetry::UnlinkingUIATrees<uint,uint>(uint &&,uint &&)
0x18001550e  mov     rdi, [rsp+30h+arg_8]
0x180015513  add     rsp, 30h
0x180015517  pop     rbp
0x180015518  retn
0x180015519  mov     rcx, [rbp+8]; this
0x18001551d  lea     r8, aPcshellTwinuiX_1; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x180015524  mov     r9d, eax; char *
0x180015527  mov     edx, 769h; void *
0x18001552c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015531  jmp     short loc_1800154F5
0x180015533  mov     rcx, [rbp+hWnd]; hWnd
0x180015537  lea     rdx, aCrossprocesspa; "CrossProcessParentHWND"
0x18001553e  call    cs:__imp_RemovePropW
0x180015544  mov     rcx, [rbp+hWnd]; hWnd
0x180015548  lea     rdx, aNoncomponentui; "NonComponentUIWindow"
0x18001554f  call    cs:__imp_RemovePropW
0x180015555  mov     rcx, [rbp+hWnd]; hWnd
0x180015559  lea     rdx, aUiaWindowpatte; "UIA_WindowPatternEnabled"
0x180015560  mov     r8d, 1; hData
0x180015566  call    cs:__imp_SetPropW
0x18001556c  test    eax, eax
0x18001556e  jnz     loc_18001549E
0x180015574  mov     rcx, [rbp+8]; this
0x180015578  lea     r8, aPcshellTwinuiX_1; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x18001557f  mov     edx, 761h; void *
0x180015584  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180015589  jmp     loc_18001549E
0x18001558e  mov     rcx, [rbp+8]; this
0x180015592  lea     r8, aPcshellTwinuiX_1; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x180015599  mov     edx, 749h; void *
0x18001559e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800155a3  jmp     loc_180015431
0x1800155a8  mov     rcx, [rbp+8]; this
0x1800155ac  lea     r8, aPcshellTwinuiX_1; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x1800155b3  mov     edx, 74Ah; void *
0x1800155b8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800155bd  jmp     loc_18001544E
0x1800155c2  mov     rcx, [rbp+8]; this
0x1800155c6  lea     r8, aPcshellTwinuiX_1; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x1800155cd  mov     edx, 74Dh; void *
0x1800155d2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800155d7  jmp     loc_18001546D
```
