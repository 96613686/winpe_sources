# CACSecurityPage::OnDestroy(uint,unsigned __int64,__int64,int &)

- ea: `0x18000a194`
- end: `0x18000a296`
- name: `?OnDestroy@CACSecurityPage@@QEAA_JI_K_JAEAH@Z`
- size: `258`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x1800060a0`
- `0x180007570`
- `0x18000a194`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a1cc`
- `KERNEL32!GetProcessHeap` at `0x18000a22e`
- `KERNEL32!GetProcessHeap` at `0x18000a1cc`
- `KERNEL32!GetProcessHeap` at `0x18000a22e`
- `KERNEL32!HeapFree` at `0x18000a1da`
- `KERNEL32!HeapFree` at `0x18000a23c`
- `KERNEL32!HeapFree` at `0x18000a1da`
- `KERNEL32!HeapFree` at `0x18000a23c`
- `USER32!GetDlgItem` at `0x18000a1ef`
- `USER32!GetDlgItem` at `0x18000a21b`
- `USER32!GetDlgItem` at `0x18000a1ef`
- `USER32!GetDlgItem` at `0x18000a21b`
- `USER32!SendMessageW` at `0x18000a1af`
- `USER32!SendMessageW` at `0x18000a203`
- `USER32!SendMessageW` at `0x18000a263`
- `USER32!SendMessageW` at `0x18000a1af`
- `USER32!SendMessageW` at `0x18000a203`
- `USER32!SendMessageW` at `0x18000a263`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnDestroy(HWND *this)
{
  int v2; // esi
  int v3; // ebp
  void *ItemDataPtr; // rbx
  HANDLE ProcessHeap; // rax
  HWND DlgItem; // rax
  int v7; // esi
  int v8; // ebp
  HWND v9; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HWND v12; // rdi
  int v13; // ebx
  int v14; // esi
  struct _AUI_EAP_METHOD_INFO *v15; // rax
  EapControls *v16; // rcx

  v2 = 0;
  v3 = SendMessageW(this[8], 0x146u, 0, 0);
  if ( v3 > 0 )
  {
    do
    {
      ItemDataPtr = ComboBox_GetItemDataPtr(this[8], v2);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, ItemDataPtr);
      ++v2;
    }
    while ( v2 < v3 );
  }
  DlgItem = GetDlgItem(this[1], 1112);
  v7 = 0;
  v8 = SendMessageW(DlgItem, 0x146u, 0, 0);
  if ( v8 > 0 )
  {
    do
    {
      v9 = GetDlgItem(this[1], 1112);
      v10 = ComboBox_GetItemDataPtr(v9, v7);
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      ++v7;
    }
    while ( v7 < v8 );
  }
  v12 = this[167];
  if ( v12 )
  {
    v13 = 0;
    v14 = SendMessageW(*((HWND *)v12 + 4), 0x146u, 0, 0);
    if ( v14 > 0 )
    {
      do
      {
        v15 = (struct _AUI_EAP_METHOD_INFO *)ComboBox_GetItemDataPtr(*((HWND *)v12 + 4), v13);
        EapControls::DestroyAuiEapInfo(v16, v15);
        ++v13;
      }
      while ( v13 < v14 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a194  push    rbx
0x18000a196  push    rbp
0x18000a197  push    rsi
0x18000a198  push    rdi
0x18000a199  sub     rsp, 28h
0x18000a19d  mov     rdi, rcx
0x18000a1a0  xor     r9d, r9d; lParam
0x18000a1a3  mov     rcx, [rcx+40h]; hWnd
0x18000a1a7  xor     r8d, r8d; wParam
0x18000a1aa  mov     edx, 146h; Msg
0x18000a1af  call    cs:__imp_SendMessageW
0x18000a1b5  xor     esi, esi
0x18000a1b7  mov     rbp, rax
0x18000a1ba  test    eax, eax
0x18000a1bc  jle     short loc_18000A1E6
0x18000a1be  mov     rcx, [rdi+40h]; HWND
0x18000a1c2  mov     edx, esi; int
0x18000a1c4  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000a1c9  mov     rbx, rax
0x18000a1cc  call    cs:__imp_GetProcessHeap
0x18000a1d2  mov     r8, rbx; lpMem
0x18000a1d5  xor     edx, edx; dwFlags
0x18000a1d7  mov     rcx, rax; hHeap
0x18000a1da  call    cs:__imp_HeapFree
0x18000a1e0  inc     esi
0x18000a1e2  cmp     esi, ebp
0x18000a1e4  jl      short loc_18000A1BE
0x18000a1e6  mov     rcx, [rdi+8]; hDlg
0x18000a1ea  mov     edx, 458h; nIDDlgItem
0x18000a1ef  call    cs:__imp_GetDlgItem
0x18000a1f5  xor     r9d, r9d; lParam
0x18000a1f8  xor     r8d, r8d; wParam
0x18000a1fb  mov     rcx, rax; hWnd
0x18000a1fe  mov     edx, 146h; Msg
0x18000a203  call    cs:__imp_SendMessageW
0x18000a209  xor     esi, esi
0x18000a20b  mov     rbp, rax
0x18000a20e  test    eax, eax
0x18000a210  jle     short loc_18000A248
0x18000a212  mov     rcx, [rdi+8]; hDlg
0x18000a216  mov     edx, 458h; nIDDlgItem
0x18000a21b  call    cs:__imp_GetDlgItem
0x18000a221  mov     rcx, rax; HWND
0x18000a224  mov     edx, esi; int
0x18000a226  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000a22b  mov     rbx, rax
0x18000a22e  call    cs:__imp_GetProcessHeap
0x18000a234  mov     r8, rbx; lpMem
0x18000a237  xor     edx, edx; dwFlags
0x18000a239  mov     rcx, rax; hHeap
0x18000a23c  call    cs:__imp_HeapFree
0x18000a242  inc     esi
0x18000a244  cmp     esi, ebp
0x18000a246  jl      short loc_18000A212
0x18000a248  mov     rdi, [rdi+538h]
0x18000a24f  test    rdi, rdi
0x18000a252  jz      short loc_18000A28B
0x18000a254  mov     rcx, [rdi+20h]; hWnd
0x18000a258  xor     r9d, r9d; lParam
0x18000a25b  xor     r8d, r8d; wParam
0x18000a25e  mov     edx, 146h; Msg
0x18000a263  call    cs:__imp_SendMessageW
0x18000a269  xor     ebx, ebx
0x18000a26b  mov     rsi, rax
0x18000a26e  test    eax, eax
0x18000a270  jle     short loc_18000A28B
0x18000a272  mov     rcx, [rdi+20h]; HWND
0x18000a276  mov     edx, ebx; int
0x18000a278  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000a27d  mov     rdx, rax; struct _AUI_EAP_METHOD_INFO *
0x18000a280  call    ?DestroyAuiEapInfo@EapControls@@QEAAXPEAU_AUI_EAP_METHOD_INFO@@@Z; EapControls::DestroyAuiEapInfo(_AUI_EAP_METHOD_INFO *)
0x18000a285  inc     ebx
0x18000a287  cmp     ebx, esi
0x18000a289  jl      short loc_18000A272
0x18000a28b  xor     eax, eax
0x18000a28d  add     rsp, 28h
0x18000a291  pop     rdi
0x18000a292  pop     rsi
0x18000a293  pop     rbp
0x18000a294  pop     rbx
0x18000a295  retn
```
