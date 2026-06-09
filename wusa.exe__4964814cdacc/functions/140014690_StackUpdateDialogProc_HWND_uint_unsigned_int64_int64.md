# StackUpdateDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140014690`
- end: `0x1400147c7`
- name: `?StackUpdateDialogProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `311`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001a63`
- `0x140014690`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x14001479c`
- `KERNEL32!GetFileAttributesW` at `0x14001479c`
- `USER32!SetForegroundWindow` at `0x140014724`
- `USER32!SetForegroundWindow` at `0x140014724`
- `USER32!EndDialog` at `0x1400146c4`
- `USER32!EndDialog` at `0x1400146c4`
- `USER32!SendDlgItemMessageW` at `0x14001471b`
- `USER32!SendDlgItemMessageW` at `0x14001471b`
- `USER32!ShowWindow` at `0x140014734`
- `USER32!ShowWindow` at `0x140014734`
- `USER32!LoadIconW` at `0x1400146fa`
- `USER32!LoadIconW` at `0x1400146fa`
- `SHELL32!ShellExecuteExW` at `0x1400147bc`
- `SHELL32!ShellExecuteExW` at `0x1400147bc`
- `ServicingCommon!SczFree` at `0x1400146d9`
- `ServicingCommon!SczFree` at `0x1400146d9`
- `ServicingCommon!SczAllocFormatted` at `0x140014763`
- `ServicingCommon!SczAllocFormatted` at `0x140014763`

## string_xrefs

- `0x140014750`: `stackupdate.url`
- `0x1400147a5`: `https://go.microsoft.com/fwlink/?LinkId=123986`

## pseudocode

```c
INT_PTR __fastcall StackUpdateDialogProc(HWND a1, int a2, __int64 a3, __int64 a4)
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
        SendDlgItemMessageW(a1, 104, 0x170u, (WPARAM)IconW, 0);
      SetForegroundWindow(a1);
      v4 = 1;
      ShowWindow(a1, 1);
      goto LABEL_6;
    }
    if ( v8 != 1 )
      return v4;
    goto LABEL_5;
  }
  if ( a3 != 105 || *(_DWORD *)(a4 + 16) != -2 )
    return v4;
  v4 = 1;
  if ( (int)SczAllocFormatted(lpFileName, L"%s\\%s", TargetPath, L"stackupdate.url") >= 0 )
  {
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.cbSize = 112;
    pExecInfo.hwnd = a1;
    pExecInfo.nShow = 1;
    FileAttributesW = GetFileAttributesW(lpFileName[0]);
    v14 = L"https://go.microsoft.com/fwlink/?LinkId=123986";
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
0x140014690  mov     [rsp+arg_0], rbx
0x140014695  push    rdi
0x140014696  sub     rsp, 0B0h
0x14001469d  xor     ebx, ebx
0x14001469f  mov     rdi, rcx
0x1400146a2  mov     [rsp+0B8h+lpFileName], rbx
0x1400146a7  sub     edx, 10h
0x1400146aa  jz      short loc_1400146C2
0x1400146ac  sub     edx, 3Eh ; '>'
0x1400146af  jz      loc_14001473C
0x1400146b5  sub     edx, 0C2h
0x1400146bb  jz      short loc_1400146F3
0x1400146bd  cmp     edx, 1
0x1400146c0  jnz     short loc_1400146DF
0x1400146c2  xor     edx, edx; nResult
0x1400146c4  call    cs:__imp_EndDialog
0x1400146ca  mov     ebx, 1
0x1400146cf  mov     rcx, [rsp+0B8h+lpFileName]
0x1400146d4  test    rcx, rcx
0x1400146d7  jz      short loc_1400146DF
0x1400146d9  call    cs:__imp_SczFree
0x1400146df  mov     rax, rbx
0x1400146e2  mov     rbx, [rsp+0B8h+arg_0]
0x1400146ea  add     rsp, 0B0h
0x1400146f1  pop     rdi
0x1400146f2  retn
0x1400146f3  mov     edx, 7F01h; lpIconName
0x1400146f8  xor     ecx, ecx; hInstance
0x1400146fa  call    cs:__imp_LoadIconW
0x140014700  test    rax, rax
0x140014703  jz      short loc_140014721
0x140014705  mov     r9, rax; wParam
0x140014708  mov     [rsp+0B8h+lParam], rbx; lParam
0x14001470d  mov     edx, 68h ; 'h'; nIDDlgItem
0x140014712  mov     r8d, 170h; Msg
0x140014718  mov     rcx, rdi; hDlg
0x14001471b  call    cs:__imp_SendDlgItemMessageW
0x140014721  mov     rcx, rdi; hWnd
0x140014724  call    cs:__imp_SetForegroundWindow
0x14001472a  mov     ebx, 1
0x14001472f  mov     rcx, rdi; hWnd
0x140014732  mov     edx, ebx; nCmdShow
0x140014734  call    cs:__imp_ShowWindow
0x14001473a  jmp     short loc_1400146CF
0x14001473c  cmp     r8, 69h ; 'i'
0x140014740  jnz     short loc_1400146DF
0x140014742  cmp     dword ptr [r9+10h], 0FFFFFFFEh
0x140014747  jnz     short loc_1400146DF
0x140014749  mov     r8, cs:TargetPath
0x140014750  lea     r9, aStackupdateUrl; "stackupdate.url"
0x140014757  lea     rdx, aSS; "%s\\%s"
0x14001475e  lea     rcx, [rsp+0B8h+lpFileName]
0x140014763  call    cs:__imp_SczAllocFormatted
0x140014769  mov     ebx, 1
0x14001476e  test    eax, eax
0x140014770  js      loc_1400146CF
0x140014776  xor     edx, edx; Val
0x140014778  lea     r8d, [rbx+6Fh]; Size
0x14001477c  lea     rcx, [rsp+0B8h+pExecInfo]; void *
0x140014781  call    memset_0
0x140014786  mov     rcx, [rsp+0B8h+lpFileName]; lpFileName
0x14001478b  mov     [rsp+0B8h+pExecInfo.cbSize], 70h ; 'p'
0x140014793  mov     [rsp+0B8h+pExecInfo.hwnd], rdi
0x140014798  mov     [rsp+0B8h+pExecInfo.nShow], ebx
0x14001479c  call    cs:__imp_GetFileAttributesW
0x1400147a2  cmp     eax, 0FFFFFFFFh
0x1400147a5  lea     rcx, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?LinkId"...
0x1400147ac  cmovnz  rcx, [rsp+0B8h+lpFileName]
0x1400147b2  mov     [rsp+0B8h+pExecInfo.lpFile], rcx
0x1400147b7  lea     rcx, [rsp+0B8h+pExecInfo]; pExecInfo
0x1400147bc  call    cs:__imp_ShellExecuteExW
0x1400147c2  jmp     loc_1400146CF
```
