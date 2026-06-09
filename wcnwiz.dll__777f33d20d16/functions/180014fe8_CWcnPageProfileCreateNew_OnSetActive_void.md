# CWcnPageProfileCreateNew::OnSetActive(void)

- ea: `0x180014fe8`
- end: `0x180015156`
- name: `?OnSetActive@CWcnPageProfileCreateNew@@QEAA_NXZ`
- size: `366`
- prototype: `bool __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009be4`

## callees

- `0x180001820`
- `0x180010758`
- `0x180014fe8`
- `0x1800158d8`
- `0x18002b8dc`
- `0x180031010`

## import_xrefs

- `USER32!EnableWindow` at `0x1800150ce`
- `USER32!EnableWindow` at `0x180015108`
- `USER32!EnableWindow` at `0x1800150ce`
- `USER32!EnableWindow` at `0x180015108`
- `USER32!ShowWindow` at `0x1800150dc`
- `USER32!ShowWindow` at `0x180015113`
- `USER32!ShowWindow` at `0x18001511e`
- `USER32!ShowWindow` at `0x1800150dc`
- `USER32!ShowWindow` at `0x180015113`
- `USER32!ShowWindow` at `0x18001511e`
- `USER32!SendMessageW` at `0x180015036`
- `USER32!SendMessageW` at `0x180015064`
- `USER32!SendMessageW` at `0x1800150f9`
- `USER32!SendMessageW` at `0x180015036`
- `USER32!SendMessageW` at `0x180015064`
- `USER32!SendMessageW` at `0x1800150f9`
- `USER32!GetDlgItem` at `0x180015020`
- `USER32!GetDlgItem` at `0x180015053`
- `USER32!GetDlgItem` at `0x180015076`
- `USER32!GetDlgItem` at `0x18001508b`
- `USER32!GetDlgItem` at `0x180015020`
- `USER32!GetDlgItem` at `0x180015053`
- `USER32!GetDlgItem` at `0x180015076`
- `USER32!GetDlgItem` at `0x18001508b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CWcnPageProfileCreateNew::OnSetActive(CWcnPageProfileCreateNew *this)
{
  WPARAM v2; // rbx
  HWND DlgItem; // rax
  WPARAM v4; // rbx
  HWND v5; // rax
  HWND v6; // rbx
  HWND v7; // rdi
  WPARAM v8; // r8
  int v9; // edx
  _QWORD v11[5]; // [rsp+20h] [rbp-38h] BYREF

  v2 = *((_BYTE *)this + 360) != 0;
  DlgItem = GetDlgItem(*((HWND *)this + 21), 2918);
  SendMessageW(DlgItem, 0xF1u, v2, 0);
  v4 = *((_BYTE *)this + 361) != 0;
  v5 = GetDlgItem(*((HWND *)this + 21), 2304);
  SendMessageW(v5, 0xF1u, v4, 0);
  v6 = GetDlgItem(*((HWND *)this + 21), 2012);
  v7 = GetDlgItem(*((HWND *)this + 21), 2915);
  CWcnNetworkProfileLoaderElevated::CWcnNetworkProfileLoaderElevated((CWcnNetworkProfileLoaderElevated *)v11);
  (*(void (__fastcall **)(_QWORD *, __int64, _QWORD))(v11[0] + 8LL))(v11, 196611, 0);
  if ( v11[2] == v11[3] )
  {
    EnableWindow(v6, 0);
    ShowWindow(v6, 0);
    v9 = 0;
    goto LABEL_5;
  }
  EnableWindow(v6, 1);
  ShowWindow(v6, 5);
  v8 = *((_QWORD *)this + 82);
  if ( v8 )
  {
    SendMessageW(v7, 0x170u, v8, 0);
    v9 = 5;
LABEL_5:
    ShowWindow(v7, v9);
  }
  CWcnPageProfileCreateNew::ResizeTheDetailsText((HWND *)this);
  CWcnNetworkProfileLoader::~CWcnNetworkProfileLoader((CWcnNetworkProfileLoader *)v11);
  return 1;
}

```

## disassembly

```asm
0x180014fe8  mov     [rsp+arg_8], rbx
0x180014fed  mov     [rsp+arg_10], rsi
0x180014ff2  push    rdi
0x180014ff3  sub     rsp, 50h
0x180014ff7  mov     rax, cs:__security_cookie
0x180014ffe  xor     rax, rsp
0x180015001  mov     [rsp+58h+var_10], rax
0x180015006  mov     rsi, rcx
0x180015009  xor     ebx, ebx
0x18001500b  cmp     [rcx+168h], bl
0x180015011  setnz   bl
0x180015014  mov     edx, 0B66h; nIDDlgItem
0x180015019  mov     rcx, [rcx+0A8h]; hDlg
0x180015020  call    cs:__imp_GetDlgItem
0x180015026  xor     r9d, r9d; lParam
0x180015029  mov     r8, rbx; wParam
0x18001502c  mov     edi, 0F1h
0x180015031  mov     edx, edi; Msg
0x180015033  mov     rcx, rax; hWnd
0x180015036  call    cs:__imp_SendMessageW
0x18001503c  xor     ebx, ebx
0x18001503e  cmp     [rsi+169h], bl
0x180015044  setnz   bl
0x180015047  mov     edx, 900h; nIDDlgItem
0x18001504c  mov     rcx, [rsi+0A8h]; hDlg
0x180015053  call    cs:__imp_GetDlgItem
0x180015059  xor     r9d, r9d; lParam
0x18001505c  mov     r8, rbx; wParam
0x18001505f  mov     edx, edi; Msg
0x180015061  mov     rcx, rax; hWnd
0x180015064  call    cs:__imp_SendMessageW
0x18001506a  mov     edx, 7DCh; nIDDlgItem
0x18001506f  mov     rcx, [rsi+0A8h]; hDlg
0x180015076  call    cs:__imp_GetDlgItem
0x18001507c  mov     rbx, rax
0x18001507f  mov     edx, 0B63h; nIDDlgItem
0x180015084  mov     rcx, [rsi+0A8h]; hDlg
0x18001508b  call    cs:__imp_GetDlgItem
0x180015091  mov     rdi, rax
0x180015094  lea     rcx, [rsp+58h+var_38]; this
0x180015099  call    ??0CWcnNetworkProfileLoaderElevated@@QEAA@XZ; CWcnNetworkProfileLoaderElevated::CWcnNetworkProfileLoaderElevated(void)
0x18001509e  nop
0x18001509f  mov     rcx, [rsp+58h+var_38]
0x1800150a4  mov     rax, [rcx+8]
0x1800150a8  xor     r8d, r8d
0x1800150ab  mov     edx, 30003h
0x1800150b0  lea     rcx, [rsp+58h+var_38]
0x1800150b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150ba  mov     rcx, [rsp+58h+var_20]
0x1800150bf  cmp     [rsp+58h+var_28], rcx
0x1800150c4  mov     rcx, rbx; hWnd
0x1800150c7  jz      short loc_180015106
0x1800150c9  mov     edx, 1; bEnable
0x1800150ce  call    cs:__imp_EnableWindow
0x1800150d4  mov     edx, 5; nCmdShow
0x1800150d9  mov     rcx, rbx; hWnd
0x1800150dc  call    cs:__imp_ShowWindow
0x1800150e2  mov     r8, [rsi+290h]; wParam
0x1800150e9  test    r8, r8
0x1800150ec  jz      short loc_180015124
0x1800150ee  xor     r9d, r9d; lParam
0x1800150f1  mov     edx, 170h; Msg
0x1800150f6  mov     rcx, rdi; hWnd
0x1800150f9  call    cs:__imp_SendMessageW
0x1800150ff  mov     edx, 5
0x180015104  jmp     short loc_18001511B
0x180015106  xor     edx, edx; bEnable
0x180015108  call    cs:__imp_EnableWindow
0x18001510e  xor     edx, edx; nCmdShow
0x180015110  mov     rcx, rbx; hWnd
0x180015113  call    cs:__imp_ShowWindow
0x180015119  xor     edx, edx; nCmdShow
0x18001511b  mov     rcx, rdi; hWnd
0x18001511e  call    cs:__imp_ShowWindow
0x180015124  mov     rcx, rsi; this
0x180015127  call    ?ResizeTheDetailsText@CWcnPageProfileCreateNew@@AEAAXXZ; CWcnPageProfileCreateNew::ResizeTheDetailsText(void)
0x18001512c  nop
0x18001512d  lea     rcx, [rsp+58h+var_38]; this
0x180015132  call    ??1CWcnNetworkProfileLoader@@UEAA@XZ; CWcnNetworkProfileLoader::~CWcnNetworkProfileLoader(void)
0x180015137  mov     al, 1
0x180015139  mov     rcx, [rsp+58h+var_10]
0x18001513e  xor     rcx, rsp; StackCookie
0x180015141  call    __security_check_cookie
0x180015146  mov     rbx, [rsp+58h+arg_8]
0x18001514b  mov     rsi, [rsp+58h+arg_10]
0x180015150  add     rsp, 50h
0x180015154  pop     rdi
0x180015155  retn
```
