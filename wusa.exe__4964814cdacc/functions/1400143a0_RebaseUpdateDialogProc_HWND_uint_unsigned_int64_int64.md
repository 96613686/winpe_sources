# RebaseUpdateDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1400143a0`
- end: `0x1400144d7`
- name: `?RebaseUpdateDialogProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `311`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001a63`
- `0x1400143a0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1400144ac`
- `KERNEL32!GetFileAttributesW` at `0x1400144ac`
- `USER32!SetForegroundWindow` at `0x140014434`
- `USER32!SetForegroundWindow` at `0x140014434`
- `USER32!EndDialog` at `0x1400143d4`
- `USER32!EndDialog` at `0x1400143d4`
- `USER32!SendDlgItemMessageW` at `0x14001442b`
- `USER32!SendDlgItemMessageW` at `0x14001442b`
- `USER32!ShowWindow` at `0x140014444`
- `USER32!ShowWindow` at `0x140014444`
- `USER32!LoadIconW` at `0x14001440a`
- `USER32!LoadIconW` at `0x14001440a`
- `SHELL32!ShellExecuteExW` at `0x1400144cc`
- `SHELL32!ShellExecuteExW` at `0x1400144cc`
- `ServicingCommon!SczFree` at `0x1400143e9`
- `ServicingCommon!SczFree` at `0x1400143e9`
- `ServicingCommon!SczAllocFormatted` at `0x140014473`
- `ServicingCommon!SczAllocFormatted` at `0x140014473`

## string_xrefs

- `0x140014460`: `rebaseupdate.url`
- `0x1400144b5`: `https://go.microsoft.com/fwlink/?linkid=2263312`

## pseudocode

```c
INT_PTR __fastcall RebaseUpdateDialogProc(HWND a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  __int64 v9; // rdx
  __int64 v10; // r8
  HICON IconW; // rax
  DWORD FileAttributesW; // eax
  const WCHAR *v14; // rcx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-88h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-78h] BYREF

  v4 = 0;
  lpFileName[0] = 0;
  v6 = a2 - 16;
  if ( !v6 )
  {
LABEL_5:
    EndDialog(a1, 0);
    v4 = 1;
    goto LABEL_6;
  }
  v7 = v6 - 62;
  if ( v7 )
  {
    v8 = v7 - 194;
    if ( !v8 )
    {
      IconW = LoadIconW(0, (LPCWSTR)0x7F01);
      if ( IconW )
        SendDlgItemMessageW(a1, 107, 0x170u, (WPARAM)IconW, 0);
      SetForegroundWindow(a1);
      v4 = 1;
      ShowWindow(a1, 1);
      goto LABEL_6;
    }
    if ( v8 != 1 )
      return v4;
    goto LABEL_5;
  }
  if ( a3 != 108 || *(_DWORD *)(a4 + 16) != -2 )
    return v4;
  v4 = 1;
  if ( (int)SczAllocFormatted(lpFileName, L"%s\\%s", TargetPath, L"rebaseupdate.url") >= 0 )
  {
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.cbSize = 112;
    pExecInfo.hwnd = a1;
    pExecInfo.nShow = 1;
    FileAttributesW = GetFileAttributesW(lpFileName[0]);
    v14 = L"https://go.microsoft.com/fwlink/?linkid=2263312";
    if ( FileAttributesW != -1 )
      v14 = lpFileName[0];
    pExecInfo.lpFile = v14;
    ShellExecuteExW(&pExecInfo);
  }
LABEL_6:
  if ( lpFileName[0] )
    SczFree(lpFileName[0], v9, v10);
  return v4;
}

```

## disassembly

```asm
0x1400143a0  mov     [rsp+arg_0], rbx
0x1400143a5  push    rdi
0x1400143a6  sub     rsp, 0B0h
0x1400143ad  xor     ebx, ebx
0x1400143af  mov     rdi, rcx
0x1400143b2  mov     [rsp+0B8h+lpFileName], rbx
0x1400143b7  sub     edx, 10h
0x1400143ba  jz      short loc_1400143D2
0x1400143bc  sub     edx, 3Eh ; '>'
0x1400143bf  jz      loc_14001444C
0x1400143c5  sub     edx, 0C2h
0x1400143cb  jz      short loc_140014403
0x1400143cd  cmp     edx, 1
0x1400143d0  jnz     short loc_1400143EF
0x1400143d2  xor     edx, edx; nResult
0x1400143d4  call    cs:__imp_EndDialog
0x1400143da  mov     ebx, 1
0x1400143df  mov     rcx, [rsp+0B8h+lpFileName]
0x1400143e4  test    rcx, rcx
0x1400143e7  jz      short loc_1400143EF
0x1400143e9  call    cs:__imp_SczFree
0x1400143ef  mov     rax, rbx
0x1400143f2  mov     rbx, [rsp+0B8h+arg_0]
0x1400143fa  add     rsp, 0B0h
0x140014401  pop     rdi
0x140014402  retn
0x140014403  mov     edx, 7F01h; lpIconName
0x140014408  xor     ecx, ecx; hInstance
0x14001440a  call    cs:__imp_LoadIconW
0x140014410  test    rax, rax
0x140014413  jz      short loc_140014431
0x140014415  mov     r9, rax; wParam
0x140014418  mov     [rsp+0B8h+lParam], rbx; lParam
0x14001441d  mov     edx, 6Bh ; 'k'; nIDDlgItem
0x140014422  mov     r8d, 170h; Msg
0x140014428  mov     rcx, rdi; hDlg
0x14001442b  call    cs:__imp_SendDlgItemMessageW
0x140014431  mov     rcx, rdi; hWnd
0x140014434  call    cs:__imp_SetForegroundWindow
0x14001443a  mov     ebx, 1
0x14001443f  mov     rcx, rdi; hWnd
0x140014442  mov     edx, ebx; nCmdShow
0x140014444  call    cs:__imp_ShowWindow
0x14001444a  jmp     short loc_1400143DF
0x14001444c  cmp     r8, 6Ch ; 'l'
0x140014450  jnz     short loc_1400143EF
0x140014452  cmp     dword ptr [r9+10h], 0FFFFFFFEh
0x140014457  jnz     short loc_1400143EF
0x140014459  mov     r8, cs:TargetPath
0x140014460  lea     r9, aRebaseupdateUr; "rebaseupdate.url"
0x140014467  lea     rdx, aSS; "%s\\%s"
0x14001446e  lea     rcx, [rsp+0B8h+lpFileName]
0x140014473  call    cs:__imp_SczAllocFormatted
0x140014479  mov     ebx, 1
0x14001447e  test    eax, eax
0x140014480  js      loc_1400143DF
0x140014486  xor     edx, edx; Val
0x140014488  lea     r8d, [rbx+6Fh]; Size
0x14001448c  lea     rcx, [rsp+0B8h+pExecInfo]; void *
0x140014491  call    memset_0
0x140014496  mov     rcx, [rsp+0B8h+lpFileName]; lpFileName
0x14001449b  mov     [rsp+0B8h+pExecInfo.cbSize], 70h ; 'p'
0x1400144a3  mov     [rsp+0B8h+pExecInfo.hwnd], rdi
0x1400144a8  mov     [rsp+0B8h+pExecInfo.nShow], ebx
0x1400144ac  call    cs:__imp_GetFileAttributesW
0x1400144b2  cmp     eax, 0FFFFFFFFh
0x1400144b5  lea     rcx, aHttpsGoMicroso_0; "https://go.microsoft.com/fwlink/?linkid"...
0x1400144bc  cmovnz  rcx, [rsp+0B8h+lpFileName]
0x1400144c2  mov     [rsp+0B8h+pExecInfo.lpFile], rcx
0x1400144c7  lea     rcx, [rsp+0B8h+pExecInfo]; pExecInfo
0x1400144cc  call    cs:__imp_ShellExecuteExW
0x1400144d2  jmp     loc_1400143DF
```
