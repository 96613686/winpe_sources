# CFciPropertiesShellExt::UpdatePropertyInfoControls(HWND__ *,CFciPropertiesShellExt::PropertyInfo const *)

- ea: `0x18000fcfc`
- end: `0x18000feb4`
- name: `?UpdatePropertyInfoControls@CFciPropertiesShellExt@@CAXPEAUHWND__@@PEBUPropertyInfo@1@@Z`
- size: `440`
- prototype: `void __fastcall(HWND hDlg, const struct CFciPropertiesShellExt::PropertyInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000fa8c`

## callees

- `0x18000fcfc`

## import_xrefs

- `USER32!GetDlgItem` at `0x18000fd28`
- `USER32!GetDlgItem` at `0x18000fd3e`
- `USER32!GetDlgItem` at `0x18000fd58`
- `USER32!GetDlgItem` at `0x18000fd7b`
- `USER32!GetDlgItem` at `0x18000fd85`
- `USER32!GetDlgItem` at `0x18000fda2`
- `USER32!GetDlgItem` at `0x18000fdbc`
- `USER32!GetDlgItem` at `0x18000fdd3`
- `USER32!GetDlgItem` at `0x18000fe03`
- `USER32!GetDlgItem` at `0x18000fe1f`
- `USER32!GetDlgItem` at `0x18000fe2f`
- `USER32!GetDlgItem` at `0x18000fe48`
- `USER32!GetDlgItem` at `0x18000fe61`
- `USER32!GetDlgItem` at `0x18000fe7a`
- `USER32!GetDlgItem` at `0x18000fe93`
- `USER32!GetDlgItem` at `0x18000fd28`
- `USER32!GetDlgItem` at `0x18000fd3e`
- `USER32!GetDlgItem` at `0x18000fd58`
- `USER32!GetDlgItem` at `0x18000fd7b`
- `USER32!GetDlgItem` at `0x18000fd85`
- `USER32!GetDlgItem` at `0x18000fda2`
- `USER32!GetDlgItem` at `0x18000fdbc`
- `USER32!GetDlgItem` at `0x18000fdd3`
- `USER32!GetDlgItem` at `0x18000fe03`
- `USER32!GetDlgItem` at `0x18000fe1f`
- `USER32!GetDlgItem` at `0x18000fe2f`
- `USER32!GetDlgItem` at `0x18000fe48`
- `USER32!GetDlgItem` at `0x18000fe61`
- `USER32!GetDlgItem` at `0x18000fe7a`
- `USER32!GetDlgItem` at `0x18000fe93`
- `USER32!ShowWindow` at `0x18000fd33`
- `USER32!ShowWindow` at `0x18000fd4c`
- `USER32!ShowWindow` at `0x18000fd66`
- `USER32!ShowWindow` at `0x18000fdb0`
- `USER32!ShowWindow` at `0x18000fdc7`
- `USER32!ShowWindow` at `0x18000fdde`
- `USER32!ShowWindow` at `0x18000fe11`
- `USER32!ShowWindow` at `0x18000fe3a`
- `USER32!ShowWindow` at `0x18000fe53`
- `USER32!ShowWindow` at `0x18000fe6c`
- `USER32!ShowWindow` at `0x18000fe85`
- `USER32!ShowWindow` at `0x18000fd33`
- `USER32!ShowWindow` at `0x18000fd4c`
- `USER32!ShowWindow` at `0x18000fd66`
- `USER32!ShowWindow` at `0x18000fdb0`
- `USER32!ShowWindow` at `0x18000fdc7`
- `USER32!ShowWindow` at `0x18000fdde`
- `USER32!ShowWindow` at `0x18000fe11`
- `USER32!ShowWindow` at `0x18000fe3a`
- `USER32!ShowWindow` at `0x18000fe53`
- `USER32!ShowWindow` at `0x18000fe6c`
- `USER32!ShowWindow` at `0x18000fe85`
- `USER32!ShowWindow` at `0x18000fead`
- `USER32!SetDlgItemTextW` at `0x18000fdf7`
- `USER32!SetDlgItemTextW` at `0x18000fdf7`
- `USER32!EnableWindow` at `0x18000fd93`
- `USER32!EnableWindow` at `0x18000fd93`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::UpdatePropertyInfoControls(
        HWND hDlg,
        const struct CFciPropertiesShellExt::PropertyInfo *a2)
{
  int v4; // ebp
  HWND v5; // rax
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rax
  BOOL v9; // edx
  HWND DlgItem; // rax
  HWND v11; // rax
  HWND v12; // rax
  const WCHAR *v13; // r8
  HWND v14; // rax
  HWND v15; // rax
  int v16; // edx
  HWND v17; // rax
  HWND v18; // rax
  HWND v19; // rax
  HWND v20; // rax

  if ( a2 )
  {
    if ( *((_DWORD *)a2 + 20) )
    {
      v4 = 1002;
      DlgItem = GetDlgItem(hDlg, 1002);
      ShowWindow(DlgItem, 5);
      v11 = GetDlgItem(hDlg, 1003);
      ShowWindow(v11, 0);
      v12 = GetDlgItem(hDlg, 1006);
      ShowWindow(v12, 0);
    }
    else
    {
      v4 = 1003;
      v5 = GetDlgItem(hDlg, 1002);
      ShowWindow(v5, 0);
      v6 = GetDlgItem(hDlg, 1003);
      ShowWindow(v6, 5);
      v7 = GetDlgItem(hDlg, 1006);
      ShowWindow(v7, 5);
      if ( *((_DWORD *)a2 + 52) == 4 )
      {
        v8 = GetDlgItem(hDlg, 1006);
        v9 = 0;
      }
      else
      {
        v8 = GetDlgItem(hDlg, 1006);
        v9 = 1;
      }
      EnableWindow(v8, v9);
    }
    v13 = (const WCHAR *)((char *)a2 + 40);
    if ( *((_QWORD *)a2 + 8) >= 8u )
      v13 = *(const WCHAR **)v13;
    SetDlgItemTextW(hDlg, v4, v13);
    v14 = GetDlgItem(hDlg, -1);
    ShowWindow(v14, 5);
    v15 = GetDlgItem(hDlg, 1004);
    v16 = 5;
  }
  else
  {
    v17 = GetDlgItem(hDlg, -1);
    ShowWindow(v17, 0);
    v18 = GetDlgItem(hDlg, 1004);
    ShowWindow(v18, 0);
    v19 = GetDlgItem(hDlg, 1002);
    ShowWindow(v19, 0);
    v20 = GetDlgItem(hDlg, 1003);
    ShowWindow(v20, 0);
    v15 = GetDlgItem(hDlg, 1006);
    v16 = 0;
  }
  ShowWindow(v15, v16);
}

```

## disassembly

```asm
0x18000fcfc  mov     [rsp+arg_0], rbx
0x18000fd01  mov     [rsp+arg_8], rbp
0x18000fd06  push    rdi
0x18000fd07  sub     rsp, 20h
0x18000fd0b  mov     rdi, rdx
0x18000fd0e  mov     rbx, rcx
0x18000fd11  test    rdx, rdx
0x18000fd14  jz      loc_18000FE2C
0x18000fd1a  cmp     dword ptr [rdx+50h], 0
0x18000fd1e  jnz     short loc_18000FD9B
0x18000fd20  mov     ebp, 3EBh
0x18000fd25  lea     edx, [rbp-1]; nIDDlgItem
0x18000fd28  call    cs:__imp_GetDlgItem
0x18000fd2e  mov     rcx, rax; hWnd
0x18000fd31  xor     edx, edx; nCmdShow
0x18000fd33  call    cs:__imp_ShowWindow
0x18000fd39  mov     edx, ebp; nIDDlgItem
0x18000fd3b  mov     rcx, rbx; hDlg
0x18000fd3e  call    cs:__imp_GetDlgItem
0x18000fd44  mov     rcx, rax; hWnd
0x18000fd47  mov     edx, 5; nCmdShow
0x18000fd4c  call    cs:__imp_ShowWindow
0x18000fd52  lea     edx, [rbp+3]; nIDDlgItem
0x18000fd55  mov     rcx, rbx; hDlg
0x18000fd58  call    cs:__imp_GetDlgItem
0x18000fd5e  mov     rcx, rax; hWnd
0x18000fd61  mov     edx, 5; nCmdShow
0x18000fd66  call    cs:__imp_ShowWindow
0x18000fd6c  cmp     dword ptr [rdi+0D0h], 4
0x18000fd73  lea     edx, [rbp+3]; nIDDlgItem
0x18000fd76  mov     rcx, rbx; hDlg
0x18000fd79  jnz     short loc_18000FD85
0x18000fd7b  call    cs:__imp_GetDlgItem
0x18000fd81  xor     edx, edx
0x18000fd83  jmp     short loc_18000FD90
0x18000fd85  call    cs:__imp_GetDlgItem
0x18000fd8b  mov     edx, 1; bEnable
0x18000fd90  mov     rcx, rax; hWnd
0x18000fd93  call    cs:__imp_EnableWindow
0x18000fd99  jmp     short loc_18000FDE4
0x18000fd9b  mov     ebp, 3EAh
0x18000fda0  mov     edx, ebp; nIDDlgItem
0x18000fda2  call    cs:__imp_GetDlgItem
0x18000fda8  mov     rcx, rax; hWnd
0x18000fdab  mov     edx, 5; nCmdShow
0x18000fdb0  call    cs:__imp_ShowWindow
0x18000fdb6  lea     edx, [rbp+1]; nIDDlgItem
0x18000fdb9  mov     rcx, rbx; hDlg
0x18000fdbc  call    cs:__imp_GetDlgItem
0x18000fdc2  mov     rcx, rax; hWnd
0x18000fdc5  xor     edx, edx; nCmdShow
0x18000fdc7  call    cs:__imp_ShowWindow
0x18000fdcd  lea     edx, [rbp+4]; nIDDlgItem
0x18000fdd0  mov     rcx, rbx; hDlg
0x18000fdd3  call    cs:__imp_GetDlgItem
0x18000fdd9  mov     rcx, rax; hWnd
0x18000fddc  xor     edx, edx; nCmdShow
0x18000fdde  call    cs:__imp_ShowWindow
0x18000fde4  lea     r8, [rdi+28h]
0x18000fde8  cmp     qword ptr [r8+18h], 8
0x18000fded  jb      short loc_18000FDF2
0x18000fdef  mov     r8, [r8]; lpString
0x18000fdf2  mov     edx, ebp; nIDDlgItem
0x18000fdf4  mov     rcx, rbx; hDlg
0x18000fdf7  call    cs:__imp_SetDlgItemTextW
0x18000fdfd  or      edx, 0FFFFFFFFh; nIDDlgItem
0x18000fe00  mov     rcx, rbx; hDlg
0x18000fe03  call    cs:__imp_GetDlgItem
0x18000fe09  mov     rcx, rax; hWnd
0x18000fe0c  mov     edx, 5; nCmdShow
0x18000fe11  call    cs:__imp_ShowWindow
0x18000fe17  mov     edx, 3ECh; nIDDlgItem
0x18000fe1c  mov     rcx, rbx; hDlg
0x18000fe1f  call    cs:__imp_GetDlgItem
0x18000fe25  mov     edx, 5
0x18000fe2a  jmp     short loc_18000FE9B
0x18000fe2c  or      edx, 0FFFFFFFFh; nIDDlgItem
0x18000fe2f  call    cs:__imp_GetDlgItem
0x18000fe35  mov     rcx, rax; hWnd
0x18000fe38  xor     edx, edx; nCmdShow
0x18000fe3a  call    cs:__imp_ShowWindow
0x18000fe40  mov     edx, 3ECh; nIDDlgItem
0x18000fe45  mov     rcx, rbx; hDlg
0x18000fe48  call    cs:__imp_GetDlgItem
0x18000fe4e  mov     rcx, rax; hWnd
0x18000fe51  xor     edx, edx; nCmdShow
0x18000fe53  call    cs:__imp_ShowWindow
0x18000fe59  mov     edx, 3EAh; nIDDlgItem
0x18000fe5e  mov     rcx, rbx; hDlg
0x18000fe61  call    cs:__imp_GetDlgItem
0x18000fe67  mov     rcx, rax; hWnd
0x18000fe6a  xor     edx, edx; nCmdShow
0x18000fe6c  call    cs:__imp_ShowWindow
0x18000fe72  mov     edx, 3EBh; nIDDlgItem
0x18000fe77  mov     rcx, rbx; hDlg
0x18000fe7a  call    cs:__imp_GetDlgItem
0x18000fe80  mov     rcx, rax; hWnd
0x18000fe83  xor     edx, edx; nCmdShow
0x18000fe85  call    cs:__imp_ShowWindow
0x18000fe8b  mov     edx, 3EEh; nIDDlgItem
0x18000fe90  mov     rcx, rbx; hDlg
0x18000fe93  call    cs:__imp_GetDlgItem
0x18000fe99  xor     edx, edx
0x18000fe9b  mov     rcx, rax
0x18000fe9e  mov     rbx, [rsp+28h+arg_0]
0x18000fea3  mov     rbp, [rsp+28h+arg_8]
0x18000fea8  add     rsp, 20h
0x18000feac  pop     rdi
0x18000fead  jmp     cs:__imp_ShowWindow
```
