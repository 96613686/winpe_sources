# ConfirmDeleteDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001ba70`
- end: `0x18001bbd2`
- name: `?ConfirmDeleteDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `354`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180003950`
- `0x18001ba70`
- `0x18001d0c0`
- `0x18001de94`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `USER32!GetDlgItem` at `0x18001baea`
- `USER32!GetDlgItem` at `0x18001bb07`
- `USER32!GetDlgItem` at `0x18001bb71`
- `USER32!GetDlgItem` at `0x18001baea`
- `USER32!GetDlgItem` at `0x18001bb07`
- `USER32!GetDlgItem` at `0x18001bb71`
- `USER32!EndDialog` at `0x18001bad6`
- `USER32!EndDialog` at `0x18001bad6`
- `USER32!SendMessageW` at `0x18001bb87`
- `USER32!SendMessageW` at `0x18001bb87`

## pseudocode

```c
__int64 __fastcall ConfirmDeleteDlgProc(HWND a1, int a2, INT_PTR a3, __int64 a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // r8d
  HWND v10; // rax
  HWND v11; // rax
  HWND DlgItem; // rax
  LPARAM lParam[4]; // [rsp+20h] [rbp-10D8h] BYREF
  int v15; // [rsp+40h] [rbp-10B8h]
  unsigned __int16 v16[2088]; // [rsp+80h] [rbp-1078h] BYREF

  v7 = a2 - 78;
  if ( !v7 )
  {
    if ( (_WORD)a3 != 2085 )
      return 0;
    if ( *(_DWORD *)(a4 + 16) != -158 )
      return 0;
    memset_0(lParam, 0, 0x58u);
    LODWORD(lParam[0]) = 1;
    lParam[3] = (LPARAM)v16;
    v15 = 2084;
    DlgItem = GetDlgItem(a1, 2085);
    if ( !(unsigned int)SendMessageW(DlgItem, 0x104Bu, 0, (LPARAM)lParam) )
      return 0;
    StringCchCopyW(*(unsigned __int16 **)(a4 + 32), *(int *)(a4 + 40), v16);
    return 1;
  }
  v8 = v7 - 194;
  if ( !v8 )
  {
    v10 = GetDlgItem(a1, 2091);
    SetListViewToString(v10);
    v11 = GetDlgItem(a1, 2085);
    SetListViewToString(v11);
    LoadIconMUI(a1);
    return 1;
  }
  if ( v8 == 1 )
  {
    v9 = (unsigned __int16)a3 - 2;
    if ( (unsigned __int16)a3 == 2 || (unsigned int)(v9 - 4) <= 1 )
      EndDialog(a1, a3);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ba70  mov     [rsp+arg_8], rbx
0x18001ba75  push    rbp
0x18001ba76  push    rsi
0x18001ba77  push    rdi
0x18001ba78  mov     eax, 10E0h
0x18001ba7d  call    _alloca_probe
0x18001ba82  sub     rsp, rax
0x18001ba85  mov     rax, cs:__security_cookie
0x18001ba8c  xor     rax, rsp
0x18001ba8f  mov     [rsp+10F8h+var_28], rax
0x18001ba97  mov     rdi, r9
0x18001ba9a  mov     r9, r8
0x18001ba9d  mov     rbp, rcx
0x18001baa0  sub     edx, 4Eh ; 'N'
0x18001baa3  jz      loc_18001BB2B
0x18001baa9  sub     edx, 0C2h
0x18001baaf  jz      short loc_18001BAE1
0x18001bab1  cmp     edx, 1
0x18001bab4  jnz     loc_18001BBAD
0x18001baba  movzx   r8d, r9w
0x18001babe  sub     r8d, 2
0x18001bac2  jz      short loc_18001BAD3
0x18001bac4  sub     r8d, 4
0x18001bac8  jz      short loc_18001BAD3
0x18001baca  cmp     r8d, edx
0x18001bacd  jnz     loc_18001BBA6
0x18001bad3  mov     rdx, r9; nResult
0x18001bad6  call    cs:__imp_EndDialog
0x18001badc  jmp     loc_18001BBA6
0x18001bae1  mov     rbx, [rdi+8]
0x18001bae5  mov     edx, 82Bh; nIDDlgItem
0x18001baea  call    cs:__imp_GetDlgItem
0x18001baf0  mov     rcx, rax; hWnd
0x18001baf3  mov     rdx, rbx
0x18001baf6  call    SetListViewToString
0x18001bafb  mov     rbx, [rdi+10h]
0x18001baff  mov     edx, 825h; nIDDlgItem
0x18001bb04  mov     rcx, rbp; hDlg
0x18001bb07  call    cs:__imp_GetDlgItem
0x18001bb0d  mov     rcx, rax; hWnd
0x18001bb10  mov     rdx, rbx
0x18001bb13  call    SetListViewToString
0x18001bb18  mov     r8d, 192h
0x18001bb1e  mov     rcx, rbp; hDlg
0x18001bb21  mov     edx, r8d
0x18001bb24  call    LoadIconMUI
0x18001bb29  jmp     short loc_18001BBA6
0x18001bb2b  mov     esi, 825h
0x18001bb30  cmp     r9w, si
0x18001bb34  jnz     short loc_18001BBAD
0x18001bb36  cmp     dword ptr [rdi+10h], 0FFFFFF62h
0x18001bb3d  jnz     short loc_18001BBAD
0x18001bb3f  xor     edx, edx; Val
0x18001bb41  lea     rcx, [rsp+10F8h+lParam]; void *
0x18001bb46  lea     r8d, [rdx+58h]; Size
0x18001bb4a  call    memset_0
0x18001bb4f  lea     rax, [rsp+10F8h+var_1078]
0x18001bb57  mov     dword ptr [rsp+10F8h+lParam], 1
0x18001bb5f  mov     edx, esi; nIDDlgItem
0x18001bb61  mov     [rsp+10F8h+var_10C0], rax
0x18001bb66  mov     rcx, rbp; hDlg
0x18001bb69  mov     [rsp+10F8h+var_10B8], 824h
0x18001bb71  call    cs:__imp_GetDlgItem
0x18001bb77  lea     r9, [rsp+10F8h+lParam]; lParam
0x18001bb7c  xor     r8d, r8d; wParam
0x18001bb7f  mov     rcx, rax; hWnd
0x18001bb82  mov     edx, 104Bh; Msg
0x18001bb87  call    cs:__imp_SendMessageW
0x18001bb8d  test    eax, eax
0x18001bb8f  jz      short loc_18001BBAD
0x18001bb91  movsxd  rdx, dword ptr [rdi+28h]; unsigned __int64
0x18001bb95  lea     r8, [rsp+10F8h+var_1078]; unsigned __int16 *
0x18001bb9d  mov     rcx, [rdi+20h]; unsigned __int16 *
0x18001bba1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001bba6  mov     eax, 1
0x18001bbab  jmp     short loc_18001BBAF
0x18001bbad  xor     eax, eax
0x18001bbaf  mov     rcx, [rsp+10F8h+var_28]
0x18001bbb7  xor     rcx, rsp; StackCookie
0x18001bbba  call    __security_check_cookie
0x18001bbbf  mov     rbx, [rsp+10F8h+arg_8]
0x18001bbc7  add     rsp, 10E0h
0x18001bbce  pop     rdi
0x18001bbcf  pop     rsi
0x18001bbd0  pop     rbp
0x18001bbd1  retn
```
