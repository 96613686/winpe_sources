# SaveFindWindowPos(HWND__ *,AddressBook *)

- ea: `0x18005f994`
- end: `0x18005fadb`
- name: `?SaveFindWindowPos@@YAXPEAUHWND__@@PEAVAddressBook@@@Z`
- size: `327`
- prototype: `void __fastcall(HWND hDlg, struct AddressBook *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060850`

## callees

- `0x18005e6d8`
- `0x18005f994`
- `0x18006b0b8`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `ADVAPI32!RegSetValueW` at `0x18005faad`
- `ADVAPI32!RegSetValueW` at `0x18005faad`
- `KERNEL32!LocalFree` at `0x18005fab6`
- `KERNEL32!LocalFree` at `0x18005fab6`
- `USER32!SendMessageW` at `0x18005fa38`
- `USER32!SendMessageW` at `0x18005fa38`
- `USER32!GetDlgItem` at `0x18005fa24`
- `USER32!GetDlgItem` at `0x18005fa59`
- `USER32!GetDlgItem` at `0x18005fa24`
- `USER32!GetDlgItem` at `0x18005fa59`
- `USER32!GetWindowRect` at `0x18005f9fa`
- `USER32!GetWindowRect` at `0x18005f9fa`
- `USER32!GetWindowPlacement` at `0x18005f9ed`
- `USER32!GetWindowPlacement` at `0x18005f9ed`

## pseudocode

```c
void __fastcall SaveFindWindowPos(HWND hDlg, struct AddressBook *a2)
{
  HWND DlgItem; // rax
  const unsigned __int16 *v5; // r8
  HWND v6; // rax
  WCHAR *v7; // rdi
  __int64 v8; // rcx
  __int64 cbData; // rax
  LPCWSTR lpData; // [rsp+30h] [rbp-59h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+38h] [rbp-51h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-19h] BYREF
  int v13; // [rsp+B4h] [rbp+2Bh]

  Rect.left = 0;
  memset_0(&Rect.top, 0, 0x48u);
  memset(&wndpl, 0, sizeof(wndpl));
  wndpl.length = 44;
  GetWindowPlacement(hDlg, &wndpl);
  GetWindowRect(hDlg, &Rect);
  if ( wndpl.showCmd != 1 )
    Rect = wndpl.rcNormalPosition;
  DlgItem = GetDlgItem(hDlg, 100);
  v13 = SendMessageW(DlgItem, 0x130Bu, 0, 0);
  WriteRegistryPositionInfo(a2, (const BYTE *)&Rect, v5);
  lpData = 0;
  v6 = GetDlgItem(hDlg, 99);
  GetSelectedText(v6, (unsigned __int16 **)&lpData);
  v7 = (WCHAR *)lpData;
  if ( lpData )
  {
    if ( !a2 || (v8 = *((_QWORD *)a2 + 132)) == 0 )
      v8 = -2147483647;
    cbData = -1;
    do
      ++cbData;
    while ( lpData[cbData] );
    RegSetValueW((HKEY)v8, L"Software\\Microsoft\\WAB\\WAB4\\LastFind", 1u, lpData, cbData);
    LocalFree(v7);
  }
}

```

## disassembly

```asm
0x18005f994  mov     [rsp-8+arg_10], rbx
0x18005f999  push    rbp
0x18005f99a  push    rsi
0x18005f99b  push    rdi
0x18005f99c  lea     rbp, [rsp-47h]
0x18005f9a1  sub     rsp, 0D0h
0x18005f9a8  mov     rax, cs:__security_cookie
0x18005f9af  xor     rax, rsp
0x18005f9b2  mov     [rbp+57h+var_20], rax
0x18005f9b6  xor     esi, esi
0x18005f9b8  mov     rbx, rdx
0x18005f9bb  mov     rdi, rcx
0x18005f9be  mov     [rbp+57h+Rect.left], esi
0x18005f9c1  xor     edx, edx; Val
0x18005f9c3  lea     rcx, [rbp+57h+Rect.top]; void *
0x18005f9c7  lea     r8d, [rsi+48h]; Size
0x18005f9cb  call    memset_0
0x18005f9d0  xorps   xmm0, xmm0
0x18005f9d3  lea     rdx, [rbp+57h+wndpl]; lpwndpl
0x18005f9d7  movups  xmmword ptr [rbp+57h+wndpl.length], xmm0
0x18005f9db  mov     rcx, rdi; hWnd
0x18005f9de  mov     [rbp+57h+wndpl.length], 2Ch ; ','
0x18005f9e5  movups  xmmword ptr [rbp+57h+wndpl.ptMinPosition.y], xmm0
0x18005f9e9  movups  xmmword ptr [rbp+57h+wndpl.rcNormalPosition.left], xmm0
0x18005f9ed  call    cs:__imp_GetWindowPlacement
0x18005f9f3  lea     rdx, [rbp+57h+Rect]; lpRect
0x18005f9f7  mov     rcx, rdi; hWnd
0x18005f9fa  call    cs:__imp_GetWindowRect
0x18005fa00  cmp     [rbp+57h+wndpl.showCmd], 1
0x18005fa04  jz      short loc_18005FA1C
0x18005fa06  mov     eax, [rbp+57h+wndpl.rcNormalPosition.left]
0x18005fa09  movsd   xmm0, qword ptr [rbp+57h+wndpl.rcNormalPosition.top]
0x18005fa0e  mov     [rbp+57h+Rect.left], eax
0x18005fa11  mov     eax, [rbp+57h+wndpl.rcNormalPosition.bottom]
0x18005fa14  mov     [rbp+57h+Rect.bottom], eax
0x18005fa17  movsd   qword ptr [rbp+57h+Rect.top], xmm0
0x18005fa1c  mov     edx, 64h ; 'd'; nIDDlgItem
0x18005fa21  mov     rcx, rdi; hDlg
0x18005fa24  call    cs:__imp_GetDlgItem
0x18005fa2a  xor     r9d, r9d; lParam
0x18005fa2d  xor     r8d, r8d; wParam
0x18005fa30  mov     rcx, rax; hWnd
0x18005fa33  mov     edx, 130Bh; Msg
0x18005fa38  call    cs:__imp_SendMessageW
0x18005fa3e  lea     rdx, [rbp+57h+Rect]; struct _AddressBookPosColSize *
0x18005fa42  mov     rcx, rbx; struct AddressBook *
0x18005fa45  mov     [rbp+57h+var_2C], eax
0x18005fa48  call    ?WriteRegistryPositionInfo@@YAHPEAVAddressBook@@PEAU_AddressBookPosColSize@@PEBG@Z; WriteRegistryPositionInfo(AddressBook *,_AddressBookPosColSize *,ushort const *)
0x18005fa4d  mov     edx, 63h ; 'c'; nIDDlgItem
0x18005fa52  mov     [rbp+57h+lpData], rsi
0x18005fa56  mov     rcx, rdi; hDlg
0x18005fa59  call    cs:__imp_GetDlgItem
0x18005fa5f  mov     rcx, rax; hWnd
0x18005fa62  lea     rdx, [rbp+57h+lpData]; unsigned __int16 **
0x18005fa66  call    ?GetSelectedText@@YAXPEAUHWND__@@PEAPEAG@Z; GetSelectedText(HWND__ *,ushort * *)
0x18005fa6b  mov     rdi, [rbp+57h+lpData]
0x18005fa6f  test    rdi, rdi
0x18005fa72  jz      short loc_18005FABC
0x18005fa74  test    rbx, rbx
0x18005fa77  jz      short loc_18005FA85
0x18005fa79  mov     rcx, [rbx+420h]
0x18005fa80  test    rcx, rcx
0x18005fa83  jnz     short loc_18005FA8C
0x18005fa85  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005fa8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005fa90  inc     rax
0x18005fa93  cmp     [rdi+rax*2], si
0x18005fa97  jnz     short loc_18005FA90
0x18005fa99  mov     r9, rdi; lpData
0x18005fa9c  mov     [rsp+0E0h+cbData], eax; cbData
0x18005faa0  mov     r8d, 1; dwType
0x18005faa6  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\WAB\\WAB4\\LastFin"...
0x18005faad  call    cs:__imp_RegSetValueW
0x18005fab3  mov     rcx, rdi; hMem
0x18005fab6  call    cs:__imp_LocalFree
0x18005fabc  mov     rcx, [rbp+57h+var_20]
0x18005fac0  xor     rcx, rsp; StackCookie
0x18005fac3  call    __security_check_cookie
0x18005fac8  mov     rbx, [rsp+0E0h+arg_10]
0x18005fad0  add     rsp, 0D0h
0x18005fad7  pop     rdi
0x18005fad8  pop     rsi
0x18005fad9  pop     rbp
0x18005fada  retn
```
