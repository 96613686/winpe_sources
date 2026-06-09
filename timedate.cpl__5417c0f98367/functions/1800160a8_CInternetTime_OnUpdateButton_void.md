# CInternetTime::_OnUpdateButton(void)

- ea: `0x1800160a8`
- end: `0x1800162e5`
- name: `?_OnUpdateButton@CInternetTime@@AEAAJXZ`
- size: `573`
- prototype: `__int64 __fastcall(CInternetTime *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180015ca8`

## callees

- `0x1800092c4`
- `0x180015c40`
- `0x1800160a8`
- `0x1800168c8`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016152`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001624f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016152`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001624f`
- `ntdll!WinSqmIsOptedIn` at `0x1800160ca`
- `ntdll!WinSqmIsOptedIn` at `0x1800160ca`
- `ntdll!WinSqmSetDWORD` at `0x1800160df`
- `ntdll!WinSqmSetDWORD` at `0x1800160df`
- `USER32!NotifyWinEvent` at `0x1800161dc`
- `USER32!NotifyWinEvent` at `0x1800162b3`
- `USER32!NotifyWinEvent` at `0x1800161dc`
- `USER32!NotifyWinEvent` at `0x1800162b3`
- `USER32!GetWindowTextW` at `0x180016178`
- `USER32!GetWindowTextW` at `0x180016178`
- `USER32!SetWindowTextW` at `0x1800161b8`
- `USER32!SetWindowTextW` at `0x18001628f`
- `USER32!SetWindowTextW` at `0x1800161b8`
- `USER32!SetWindowTextW` at `0x18001628f`
- `USER32!GetDlgItem` at `0x180016161`
- `USER32!GetDlgItem` at `0x1800161a7`
- `USER32!GetDlgItem` at `0x1800161c7`
- `USER32!GetDlgItem` at `0x18001627e`
- `USER32!GetDlgItem` at `0x18001629e`
- `USER32!GetDlgItem` at `0x180016161`
- `USER32!GetDlgItem` at `0x1800161a7`
- `USER32!GetDlgItem` at `0x1800161c7`
- `USER32!GetDlgItem` at `0x18001627e`
- `USER32!GetDlgItem` at `0x18001629e`
- `USER32!LoadCursorW` at `0x180016128`
- `USER32!LoadCursorW` at `0x180016128`
- `USER32!SetCursor` at `0x180016131`
- `USER32!SetCursor` at `0x180016131`

## pseudocode

```c
__int64 __fastcall CInternetTime::_OnUpdateButton(CInternetTime *this)
{
  int v2; // eax
  int v3; // edi
  HCURSOR CursorW; // rax
  HWND DlgItem; // rax
  HWND v6; // rax
  HWND v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  HWND v10; // rax
  HWND v11; // rax
  int Buffer[132]; // [rsp+20h] [rbp-848h] BYREF
  WCHAR String[264]; // [rsp+230h] [rbp-638h] BYREF
  WCHAR v15[520]; // [rsp+440h] [rbp-428h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+868h] [rbp+0h]

  if ( (unsigned int)WinSqmIsOptedIn() )
    WinSqmSetDWORD(0, 6687, 1);
  if ( *((_DWORD *)this + 10) && (v2 = CInternetTime::_ApplyChanges(this), v3 = v2, v2 < 0) )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
      (const char *)(unsigned int)v2,
      Buffer[0]);
  }
  else
  {
    if ( !*((_QWORD *)this + 3) )
    {
      CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
      *((_QWORD *)this + 3) = SetCursor(CursorW);
    }
    LoadStringW(g_hInst, 0x1F4u, (LPWSTR)Buffer, 260);
    DlgItem = GetDlgItem(*((HWND *)this + 2), 821);
    GetWindowTextW(DlgItem, String, 260);
    FormatMessageWedge(Buffer, v15, 0x208u, String);
    v6 = GetDlgItem(*((HWND *)this + 2), 825);
    SetWindowTextW(v6, v15);
    v7 = GetDlgItem(*((HWND *)this + 2), 825);
    NotifyWinEvent(0x8019u, v7, -4, 0);
    v8 = *((_QWORD *)this + 1);
    v3 = -2147467259;
    v9 = *(_QWORD *)(v8 + 488);
    if ( *(_DWORD *)(v9 + 1072) )
      v3 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v8 + 112) + 136LL))(*(_QWORD *)(v8 + 112), v9 + 4);
    if ( v3 >= 0 )
    {
      *((_DWORD *)this + 8) = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
        (const char *)(unsigned int)v3,
        Buffer[0]);
      LoadStringW(g_hInst, 0x1F9u, (LPWSTR)Buffer, 260);
      FormatMessageWedge(Buffer, v15, 0x208u, String);
      v10 = GetDlgItem(*((HWND *)this + 2), 825);
      SetWindowTextW(v10, v15);
      v11 = GetDlgItem(*((HWND *)this + 2), 825);
      NotifyWinEvent(0x8019u, v11, -4, 0);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800160a8  mov     [rsp+arg_8], rbx
0x1800160ad  push    rdi
0x1800160ae  sub     rsp, 860h
0x1800160b5  mov     rax, cs:__security_cookie
0x1800160bc  xor     rax, rsp
0x1800160bf  mov     [rsp+868h+var_18], rax
0x1800160c7  mov     rbx, rcx
0x1800160ca  call    cs:__imp_WinSqmIsOptedIn
0x1800160d0  test    eax, eax
0x1800160d2  jz      short loc_1800160E5
0x1800160d4  xor     ecx, ecx
0x1800160d6  mov     edx, 1A1Fh
0x1800160db  lea     r8d, [rcx+1]
0x1800160df  call    cs:__imp_WinSqmSetDWORD
0x1800160e5  cmp     dword ptr [rbx+28h], 0
0x1800160e9  jz      short loc_18001611A
0x1800160eb  mov     rcx, rbx; this
0x1800160ee  call    ?_ApplyChanges@CInternetTime@@AEAAJXZ; CInternetTime::_ApplyChanges(void)
0x1800160f3  mov     edi, eax
0x1800160f5  test    eax, eax
0x1800160f7  jns     short loc_18001611A
0x1800160f9  mov     rcx, [rsp+868h]; this
0x180016101  lea     r8, aShellCplsUtcIn_0; "shell\\cpls\\utc\\inettime.cpp"
0x180016108  mov     r9d, eax; char *
0x18001610b  mov     edx, 187h; void *
0x180016110  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016115  jmp     loc_1800162C2
0x18001611a  cmp     qword ptr [rbx+18h], 0
0x18001611f  jnz     short loc_18001613B
0x180016121  mov     edx, 7F02h; lpCursorName
0x180016126  xor     ecx, ecx; hInstance
0x180016128  call    cs:__imp_LoadCursorW
0x18001612e  mov     rcx, rax; hCursor
0x180016131  call    cs:__imp_SetCursor
0x180016137  mov     [rbx+18h], rax
0x18001613b  mov     rcx, cs:g_hInst; hInstance
0x180016142  lea     r8, [rsp+868h+Buffer]; lpBuffer
0x180016147  mov     r9d, 104h; cchBufferMax
0x18001614d  mov     edx, 1F4h; uID
0x180016152  call    cs:__imp_LoadStringW
0x180016158  mov     rcx, [rbx+10h]; hDlg
0x18001615c  mov     edx, 335h; nIDDlgItem
0x180016161  call    cs:__imp_GetDlgItem
0x180016167  mov     r8d, 104h; nMaxCount
0x18001616d  lea     rdx, [rsp+868h+String]; lpString
0x180016175  mov     rcx, rax; hWnd
0x180016178  call    cs:__imp_GetWindowTextW
0x18001617e  lea     r9, [rsp+868h+String]
0x180016186  mov     r8d, 208h; unsigned int
0x18001618c  lea     rdx, [rsp+868h+var_428]; unsigned __int16 *
0x180016194  lea     rcx, [rsp+868h+Buffer]; lpSource
0x180016199  call    ?FormatMessageWedge@@YAJPEBGPEAGKZZ; FormatMessageWedge(ushort const *,ushort *,ulong,...)
0x18001619e  mov     rcx, [rbx+10h]; hDlg
0x1800161a2  mov     edx, 339h; nIDDlgItem
0x1800161a7  call    cs:__imp_GetDlgItem
0x1800161ad  mov     rcx, rax; hWnd
0x1800161b0  lea     rdx, [rsp+868h+var_428]; lpString
0x1800161b8  call    cs:__imp_SetWindowTextW
0x1800161be  mov     rcx, [rbx+10h]; hDlg
0x1800161c2  mov     edx, 339h; nIDDlgItem
0x1800161c7  call    cs:__imp_GetDlgItem
0x1800161cd  xor     r9d, r9d; idChild
0x1800161d0  mov     ecx, 8019h; event
0x1800161d5  mov     rdx, rax; hwnd
0x1800161d8  lea     r8d, [r9-4]; idObject
0x1800161dc  call    cs:__imp_NotifyWinEvent
0x1800161e2  mov     rcx, [rbx+8]
0x1800161e6  mov     edi, 80004005h
0x1800161eb  mov     rdx, [rcx+1E8h]
0x1800161f2  cmp     dword ptr [rdx+430h], 0
0x1800161f9  jz      short loc_180016214
0x1800161fb  mov     rcx, [rcx+70h]
0x1800161ff  add     rdx, 4
0x180016203  mov     rax, [rcx]
0x180016206  mov     rax, [rax+88h]
0x18001620d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016212  mov     edi, eax
0x180016214  test    edi, edi
0x180016216  jns     loc_1800162BB
0x18001621c  mov     rcx, [rsp+868h]; this
0x180016224  lea     r8, aShellCplsUtcIn_0; "shell\\cpls\\utc\\inettime.cpp"
0x18001622b  mov     r9d, edi; char *
0x18001622e  mov     edx, 19Ah; void *
0x180016233  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016238  mov     rcx, cs:g_hInst; hInstance
0x18001623f  lea     r8, [rsp+868h+Buffer]; lpBuffer
0x180016244  mov     r9d, 104h; cchBufferMax
0x18001624a  mov     edx, 1F9h; uID
0x18001624f  call    cs:__imp_LoadStringW
0x180016255  lea     r9, [rsp+868h+String]
0x18001625d  mov     r8d, 208h; unsigned int
0x180016263  lea     rdx, [rsp+868h+var_428]; unsigned __int16 *
0x18001626b  lea     rcx, [rsp+868h+Buffer]; lpSource
0x180016270  call    ?FormatMessageWedge@@YAJPEBGPEAGKZZ; FormatMessageWedge(ushort const *,ushort *,ulong,...)
0x180016275  mov     rcx, [rbx+10h]; hDlg
0x180016279  mov     edx, 339h; nIDDlgItem
0x18001627e  call    cs:__imp_GetDlgItem
0x180016284  mov     rcx, rax; hWnd
0x180016287  lea     rdx, [rsp+868h+var_428]; lpString
0x18001628f  call    cs:__imp_SetWindowTextW
0x180016295  mov     rcx, [rbx+10h]; hDlg
0x180016299  mov     edx, 339h; nIDDlgItem
0x18001629e  call    cs:__imp_GetDlgItem
0x1800162a4  xor     r9d, r9d; idChild
0x1800162a7  mov     ecx, 8019h; event
0x1800162ac  mov     rdx, rax; hwnd
0x1800162af  lea     r8d, [r9-4]; idObject
0x1800162b3  call    cs:__imp_NotifyWinEvent
0x1800162b9  jmp     short loc_1800162C2
0x1800162bb  mov     dword ptr [rbx+20h], 1
0x1800162c2  mov     eax, edi
0x1800162c4  mov     rcx, [rsp+868h+var_18]
0x1800162cc  xor     rcx, rsp; StackCookie
0x1800162cf  call    __security_check_cookie
0x1800162d4  mov     rbx, [rsp+868h+arg_8]
0x1800162dc  add     rsp, 860h
0x1800162e3  pop     rdi
0x1800162e4  retn
```
