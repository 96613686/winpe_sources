# SetPrintDialogMsg(int,int,ushort *)

- ea: `0x18004590c`
- end: `0x180045aeb`
- name: `?SetPrintDialogMsg@@YAXHHPEAG@Z`
- size: `479`
- prototype: `void(int, int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180076400`
- `0x180077c74`
- `0x180078938`

## callees

- `0x1800045e4`
- `0x180033ae0`
- `0x18004590c`
- `0x1800637cc`
- `0x180064e84`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800459d9`
- `KERNEL32!FormatMessageW` at `0x1800459d9`
- `USER32!LoadStringW` at `0x180045990`
- `USER32!LoadStringW` at `0x180045990`
- `USER32!GetDlgItem` at `0x180045a46`
- `USER32!GetDlgItem` at `0x180045a46`
- `USER32!UpdateWindow` at `0x180045a37`
- `USER32!UpdateWindow` at `0x180045a4f`
- `USER32!UpdateWindow` at `0x180045a37`
- `USER32!UpdateWindow` at `0x180045a4f`
- `USER32!GetWindowLongPtrW` at `0x180045a86`
- `USER32!GetWindowLongPtrW` at `0x180045a86`
- `USER32!SendDlgItemMessageW` at `0x180045a71`
- `USER32!SendDlgItemMessageW` at `0x180045aad`
- `USER32!SendDlgItemMessageW` at `0x180045a71`
- `USER32!SendDlgItemMessageW` at `0x180045aad`
- `USER32!SetDlgItemTextW` at `0x180045a2a`
- `USER32!SetDlgItemTextW` at `0x180045a2a`

## pseudocode

```c
void __fastcall SetPrintDialogMsg(__int64 a1, UINT a2, unsigned __int16 *a3)
{
  struct _tagPerThreadGlobalData *ThreadStoragePointer; // rbx
  const unsigned __int16 *v6; // r8
  __int64 v7; // rax
  HWND DlgItem; // rax
  int v9; // edi
  LONG_PTR WindowLongPtrW; // rax
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  va_list Arguments; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v13[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[200]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  ThreadStoragePointer = GetThreadStoragePointer();
  *(_QWORD *)lpBuffer = 0;
  if ( a2 )
  {
    memset_0(v13, 0, sizeof(v13));
    LoadStringW(hinstMapiX, a2, Buffer, 200);
    CopyTruncate(v13, a3, 32);
    Arguments = (va_list)v13;
    FormatMessageW(0x2500u, Buffer, 0, 0, lpBuffer, 0, &Arguments);
    v6 = *(const unsigned __int16 **)lpBuffer;
    if ( *(_QWORD *)lpBuffer )
      goto LABEL_6;
  }
  else if ( a3 )
  {
    v6 = a3;
LABEL_6:
    StringCchCopyW(Buffer, 0xC8u, v6);
  }
  v7 = -1;
  do
    ++v7;
  while ( Buffer[v7] );
  if ( v7 )
    SetDlgItemTextW(*((HWND *)ThreadStoragePointer + 307), 66, Buffer);
  UpdateWindow(*((HWND *)ThreadStoragePointer + 307));
  DlgItem = GetDlgItem(*((HWND *)ThreadStoragePointer + 307), 66);
  UpdateWindow(DlgItem);
  v9 = SendDlgItemMessageW(*((HWND *)ThreadStoragePointer + 307), 6008, 0x408u, 0, 0);
  WindowLongPtrW = GetWindowLongPtrW(*((HWND *)ThreadStoragePointer + 307), 16);
  if ( WindowLongPtrW && v9 < *(_DWORD *)(WindowLongPtrW + 4) )
    SendDlgItemMessageW(*((HWND *)ThreadStoragePointer + 307), 6008, 0x405u, 0, 0);
  if ( *(_QWORD *)lpBuffer )
    LocalFreeAndNull((void **)lpBuffer);
}

```

## disassembly

```asm
0x18004590c  mov     [rsp-8+arg_0], rbx
0x180045911  mov     [rsp-8+arg_18], rsi
0x180045916  push    rbp
0x180045917  push    rdi
0x180045918  push    r14
0x18004591a  lea     rbp, [rsp-130h]
0x180045922  sub     rsp, 230h
0x180045929  mov     rax, cs:__security_cookie
0x180045930  xor     rax, rsp
0x180045933  mov     [rbp+140h+var_20], rax
0x18004593a  mov     rdi, r8
0x18004593d  lea     rcx, [rbp+140h+Buffer]; void *
0x180045941  mov     esi, edx
0x180045943  mov     r8d, 190h; Size
0x180045949  xor     edx, edx; Val
0x18004594b  call    memset_0
0x180045950  call    ?GetThreadStoragePointer@@YAPEAU_tagPerThreadGlobalData@@XZ; GetThreadStoragePointer(void)
0x180045955  xor     r14d, r14d
0x180045958  mov     rbx, rax
0x18004595b  mov     qword ptr [rsp+240h+var_200], r14
0x180045960  test    esi, esi
0x180045962  jz      loc_1800459EB
0x180045968  xor     edx, edx; Val
0x18004596a  lea     r8d, [r14+40h]; Size
0x18004596e  lea     rcx, [rsp+240h+var_1F0]; void *
0x180045973  call    memset_0
0x180045978  mov     rcx, cs:hinstMapiX; hInstance
0x18004597f  lea     r8, [rbp+140h+Buffer]; lpBuffer
0x180045983  mov     r9d, 0C8h; cchBufferMax
0x180045989  mov     [rsp+240h+var_1F8], r14
0x18004598e  mov     edx, esi; uID
0x180045990  call    cs:__imp_LoadStringW
0x180045996  lea     r8d, [r14+20h]; int
0x18004599a  mov     rdx, rdi; unsigned __int16 *
0x18004599d  lea     rcx, [rsp+240h+var_1F0]; unsigned __int16 *
0x1800459a2  call    ?CopyTruncate@@YAXPEAG0H@Z; CopyTruncate(ushort *,ushort *,int)
0x1800459a7  lea     rax, [rsp+240h+var_1F0]
0x1800459ac  xor     r9d, r9d; dwLanguageId
0x1800459af  mov     [rsp+240h+var_1F8], rax
0x1800459b4  lea     rdx, [rbp+140h+Buffer]; lpSource
0x1800459b8  lea     rax, [rsp+240h+var_1F8]
0x1800459bd  xor     r8d, r8d; dwMessageId
0x1800459c0  mov     [rsp+240h+Arguments], rax; Arguments
0x1800459c5  mov     ecx, 2500h; dwFlags
0x1800459ca  lea     rax, [rsp+240h+var_200]
0x1800459cf  mov     [rsp+240h+nSize], r14d; nSize
0x1800459d4  mov     [rsp+240h+lpBuffer], rax; lpBuffer
0x1800459d9  call    cs:__imp_FormatMessageW
0x1800459df  mov     r8, qword ptr [rsp+240h+var_200]
0x1800459e4  test    r8, r8
0x1800459e7  jz      short loc_180045A01
0x1800459e9  jmp     short loc_1800459F3
0x1800459eb  test    rdi, rdi
0x1800459ee  jz      short loc_180045A01
0x1800459f0  mov     r8, rdi; unsigned __int16 *
0x1800459f3  mov     edx, 0C8h; unsigned __int64
0x1800459f8  lea     rcx, [rbp+140h+Buffer]; unsigned __int16 *
0x1800459fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045a01  lea     rcx, [rbp+140h+Buffer]
0x180045a05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045a09  inc     rax
0x180045a0c  cmp     [rcx+rax*2], r14w
0x180045a11  jnz     short loc_180045A09
0x180045a13  mov     edi, 42h ; 'B'
0x180045a18  test    rax, rax
0x180045a1b  jz      short loc_180045A30
0x180045a1d  mov     rcx, [rbx+998h]; hDlg
0x180045a24  lea     r8, [rbp+140h+Buffer]; lpString
0x180045a28  mov     edx, edi; nIDDlgItem
0x180045a2a  call    cs:__imp_SetDlgItemTextW
0x180045a30  mov     rcx, [rbx+998h]; hWnd
0x180045a37  call    cs:__imp_UpdateWindow
0x180045a3d  mov     rcx, [rbx+998h]; hDlg
0x180045a44  mov     edx, edi; nIDDlgItem
0x180045a46  call    cs:__imp_GetDlgItem
0x180045a4c  mov     rcx, rax; hWnd
0x180045a4f  call    cs:__imp_UpdateWindow
0x180045a55  mov     rcx, [rbx+998h]; hDlg
0x180045a5c  mov     esi, 1778h
0x180045a61  mov     edx, esi; nIDDlgItem
0x180045a63  mov     [rsp+240h+lpBuffer], r14; lParam
0x180045a68  xor     r9d, r9d; wParam
0x180045a6b  mov     r8d, 408h; Msg
0x180045a71  call    cs:__imp_SendDlgItemMessageW
0x180045a77  mov     rcx, [rbx+998h]; hWnd
0x180045a7e  mov     edx, 10h; nIndex
0x180045a83  mov     rdi, rax
0x180045a86  call    cs:__imp_GetWindowLongPtrW
0x180045a8c  test    rax, rax
0x180045a8f  jz      short loc_180045AB3
0x180045a91  cmp     edi, [rax+4]
0x180045a94  jge     short loc_180045AB3
0x180045a96  mov     rcx, [rbx+998h]; hDlg
0x180045a9d  xor     r9d, r9d; wParam
0x180045aa0  mov     r8d, 405h; Msg
0x180045aa6  mov     [rsp+240h+lpBuffer], r14; lParam
0x180045aab  mov     edx, esi; nIDDlgItem
0x180045aad  call    cs:__imp_SendDlgItemMessageW
0x180045ab3  cmp     qword ptr [rsp+240h+var_200], r14
0x180045ab8  jz      short loc_180045AC4
0x180045aba  lea     rcx, [rsp+240h+var_200]; void **
0x180045abf  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180045ac4  mov     rcx, [rbp+140h+var_20]
0x180045acb  xor     rcx, rsp; StackCookie
0x180045ace  call    __security_check_cookie
0x180045ad3  lea     r11, [rsp+240h+var_10]
0x180045adb  mov     rbx, [r11+20h]
0x180045adf  mov     rsi, [r11+38h]
0x180045ae3  mov     rsp, r11
0x180045ae6  pop     r14
0x180045ae8  pop     rdi
0x180045ae9  pop     rbp
0x180045aea  retn
```
