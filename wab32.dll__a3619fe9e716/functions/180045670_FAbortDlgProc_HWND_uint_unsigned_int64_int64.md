# FAbortDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180045670`
- end: `0x18004585b`
- name: `?FAbortDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `491`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180045670`
- `0x180064e84`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180045819`
- `KERNEL32!LocalFree` at `0x180045819`
- `USER32!LoadStringW` at `0x1800456fb`
- `USER32!LoadStringW` at `0x1800456fb`
- `USER32!SendMessageW` at `0x180045777`
- `USER32!SendMessageW` at `0x18004578b`
- `USER32!SendMessageW` at `0x1800457a0`
- `USER32!SendMessageW` at `0x180045777`
- `USER32!SendMessageW` at `0x18004578b`
- `USER32!SendMessageW` at `0x1800457a0`
- `USER32!GetDlgItem` at `0x1800456cb`
- `USER32!GetDlgItem` at `0x18004574e`
- `USER32!GetDlgItem` at `0x1800456cb`
- `USER32!GetDlgItem` at `0x18004574e`
- `USER32!UpdateWindow` at `0x180045757`
- `USER32!UpdateWindow` at `0x180045757`
- `USER32!SetWindowLongPtrW` at `0x1800456dd`
- `USER32!SetWindowLongPtrW` at `0x180045828`
- `USER32!SetWindowLongPtrW` at `0x1800456dd`
- `USER32!SetWindowLongPtrW` at `0x180045828`
- `USER32!GetWindowLongPtrW` at `0x1800457df`
- `USER32!GetWindowLongPtrW` at `0x1800457df`
- `USER32!SetWindowTextW` at `0x180045709`
- `USER32!SetWindowTextW` at `0x180045709`
- `USER32!SendDlgItemMessageW` at `0x180045740`
- `USER32!SendDlgItemMessageW` at `0x180045810`
- `USER32!SendDlgItemMessageW` at `0x180045740`
- `USER32!SendDlgItemMessageW` at `0x180045810`
- `USER32!LoadIconW` at `0x180045720`
- `USER32!LoadIconW` at `0x180045720`
- `USER32!EnableMenuItem` at `0x1800457bc`
- `USER32!EnableMenuItem` at `0x1800457bc`
- `USER32!GetSystemMenu` at `0x1800457ab`
- `USER32!GetSystemMenu` at `0x1800457ab`

## pseudocode

```c
__int64 __fastcall FAbortDlgProc(HWND hWnd, int a2, __int64 a3, LONG_PTR a4)
{
  HWND DlgItem; // rbp
  HICON IconW; // rax
  HWND v8; // rax
  HMENU SystemMenu; // rax
  struct _tagPerThreadGlobalData *ThreadStoragePointer; // rbp
  LONG_PTR WindowLongPtrW; // rax
  void *v13; // rsi
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( a2 == 272 )
  {
    if ( a4 )
    {
      memset_0(Buffer, 0, 0x208u);
      DlgItem = GetDlgItem(hWnd, 6008);
      SetWindowLongPtrW(hWnd, 16, a4);
      if ( *(_DWORD *)a4 )
      {
        LoadStringW(hinstMapiX, *(_DWORD *)a4, Buffer, 260);
        SetWindowTextW(hWnd, Buffer);
      }
      if ( *(_DWORD *)(a4 + 12) )
      {
        IconW = LoadIconW(hinstMapiX, (LPCWSTR)*(unsigned __int16 *)(a4 + 12));
        SendDlgItemMessageW(hWnd, 6009, 0x170u, (WPARAM)IconW, 0);
        v8 = GetDlgItem(hWnd, 6009);
        UpdateWindow(v8);
      }
      SendMessageW(DlgItem, 0x401u, 0, (unsigned __int64)(unsigned __int16)(*(_WORD *)(a4 + 4) + 1) << 16);
      SendMessageW(DlgItem, 0x404u, 1u, 0);
      SendMessageW(DlgItem, 0x402u, *(int *)(a4 + 8), 0);
    }
    SystemMenu = GetSystemMenu(hWnd, 0);
    EnableMenuItem(SystemMenu, 0xF060u, 1u);
    return 1;
  }
  if ( a2 == 273 )
  {
    ThreadStoragePointer = GetThreadStoragePointer();
    WindowLongPtrW = GetWindowLongPtrW(hWnd, 16);
    v13 = (void *)WindowLongPtrW;
    if ( WindowLongPtrW )
    {
      SendDlgItemMessageW(hWnd, 6008, 0x402u, *(int *)(WindowLongPtrW + 4) + 1LL, 0);
      LocalFree(v13);
      SetWindowLongPtrW(hWnd, 16, 0);
    }
    *((_DWORD *)ThreadStoragePointer + 613) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180045670  mov     [rsp+arg_8], rbx
0x180045675  push    rbp
0x180045676  push    rsi
0x180045677  push    rdi
0x180045678  sub     rsp, 250h
0x18004567f  mov     rax, cs:__security_cookie
0x180045686  xor     rax, rsp
0x180045689  mov     [rsp+268h+var_28], rax
0x180045691  mov     rsi, r9
0x180045694  mov     rdi, rcx
0x180045697  cmp     edx, 110h
0x18004569d  jnz     loc_1800457C7
0x1800456a3  mov     ebx, 1
0x1800456a8  test    r9, r9
0x1800456ab  jz      loc_1800457A6
0x1800456b1  xor     edx, edx; Val
0x1800456b3  lea     rcx, [rsp+268h+Buffer]; void *
0x1800456b8  mov     r8d, 208h; Size
0x1800456be  call    memset_0
0x1800456c3  mov     edx, 1778h; nIDDlgItem
0x1800456c8  mov     rcx, rdi; hDlg
0x1800456cb  call    cs:__imp_GetDlgItem
0x1800456d1  mov     r8, rsi; dwNewLong
0x1800456d4  lea     edx, [rbx+0Fh]; nIndex
0x1800456d7  mov     rcx, rdi; hWnd
0x1800456da  mov     rbp, rax
0x1800456dd  call    cs:__imp_SetWindowLongPtrW
0x1800456e3  mov     edx, [rsi]; uID
0x1800456e5  test    edx, edx
0x1800456e7  jz      short loc_18004570F
0x1800456e9  mov     rcx, cs:hinstMapiX; hInstance
0x1800456f0  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1800456f5  mov     r9d, 104h; cchBufferMax
0x1800456fb  call    cs:__imp_LoadStringW
0x180045701  lea     rdx, [rsp+268h+Buffer]; lpString
0x180045706  mov     rcx, rdi; hWnd
0x180045709  call    cs:__imp_SetWindowTextW
0x18004570f  cmp     dword ptr [rsi+0Ch], 0
0x180045713  jz      short loc_18004575D
0x180045715  movzx   edx, word ptr [rsi+0Ch]; lpIconName
0x180045719  mov     rcx, cs:hinstMapiX; hInstance
0x180045720  call    cs:__imp_LoadIconW
0x180045726  mov     edx, 1779h; nIDDlgItem
0x18004572b  mov     [rsp+268h+lParam], 0; lParam
0x180045734  mov     r9, rax; wParam
0x180045737  mov     r8d, 170h; Msg
0x18004573d  mov     rcx, rdi; hDlg
0x180045740  call    cs:__imp_SendDlgItemMessageW
0x180045746  mov     edx, 1779h; nIDDlgItem
0x18004574b  mov     rcx, rdi; hDlg
0x18004574e  call    cs:__imp_GetDlgItem
0x180045754  mov     rcx, rax; hWnd
0x180045757  call    cs:__imp_UpdateWindow
0x18004575d  movzx   eax, word ptr [rsi+4]
0x180045761  xor     r8d, r8d; wParam
0x180045764  add     ax, bx
0x180045767  mov     edx, 401h; Msg
0x18004576c  movzx   r9d, ax
0x180045770  mov     rcx, rbp; hWnd
0x180045773  shl     r9, 10h; lParam
0x180045777  call    cs:__imp_SendMessageW
0x18004577d  xor     r9d, r9d; lParam
0x180045780  mov     r8, rbx; wParam
0x180045783  mov     edx, 404h; Msg
0x180045788  mov     rcx, rbp; hWnd
0x18004578b  call    cs:__imp_SendMessageW
0x180045791  movsxd  r8, dword ptr [rsi+8]; wParam
0x180045795  xor     r9d, r9d; lParam
0x180045798  mov     edx, 402h; Msg
0x18004579d  mov     rcx, rbp; hWnd
0x1800457a0  call    cs:__imp_SendMessageW
0x1800457a6  xor     edx, edx; bRevert
0x1800457a8  mov     rcx, rdi; hWnd
0x1800457ab  call    cs:__imp_GetSystemMenu
0x1800457b1  mov     r8d, ebx; uEnable
0x1800457b4  mov     edx, 0F060h; uIDEnableItem
0x1800457b9  mov     rcx, rax; hMenu
0x1800457bc  call    cs:__imp_EnableMenuItem
0x1800457c2  mov     rax, rbx
0x1800457c5  jmp     short loc_180045838
0x1800457c7  cmp     edx, 111h
0x1800457cd  jnz     short loc_180045836
0x1800457cf  call    ?GetThreadStoragePointer@@YAPEAU_tagPerThreadGlobalData@@XZ; GetThreadStoragePointer(void)
0x1800457d4  mov     edx, 10h; nIndex
0x1800457d9  mov     rcx, rdi; hWnd
0x1800457dc  mov     rbp, rax
0x1800457df  call    cs:__imp_GetWindowLongPtrW
0x1800457e5  mov     rsi, rax
0x1800457e8  mov     ebx, 1
0x1800457ed  test    rax, rax
0x1800457f0  jz      short loc_18004582E
0x1800457f2  movsxd  r9, dword ptr [rax+4]
0x1800457f6  mov     edx, 1778h; nIDDlgItem
0x1800457fb  add     r9, rbx; wParam
0x1800457fe  mov     [rsp+268h+lParam], 0; lParam
0x180045807  mov     r8d, 402h; Msg
0x18004580d  mov     rcx, rdi; hDlg
0x180045810  call    cs:__imp_SendDlgItemMessageW
0x180045816  mov     rcx, rsi; hMem
0x180045819  call    cs:__imp_LocalFree
0x18004581f  xor     r8d, r8d; dwNewLong
0x180045822  lea     edx, [rbx+0Fh]; nIndex
0x180045825  mov     rcx, rdi; hWnd
0x180045828  call    cs:__imp_SetWindowLongPtrW
0x18004582e  mov     [rbp+994h], ebx
0x180045834  jmp     short loc_1800457C2
0x180045836  xor     eax, eax
0x180045838  mov     rcx, [rsp+268h+var_28]
0x180045840  xor     rcx, rsp; StackCookie
0x180045843  call    __security_check_cookie
0x180045848  mov     rbx, [rsp+268h+arg_8]
0x180045850  add     rsp, 250h
0x180045857  pop     rdi
0x180045858  pop     rsi
0x180045859  pop     rbp
0x18004585a  retn
```
