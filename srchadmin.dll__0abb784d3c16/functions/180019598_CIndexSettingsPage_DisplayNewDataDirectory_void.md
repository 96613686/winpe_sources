# CIndexSettingsPage::_DisplayNewDataDirectory(void)

- ea: `0x180019598`
- end: `0x1800196a7`
- name: `?_DisplayNewDataDirectory@CIndexSettingsPage@@AEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(CIndexSettingsPage *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800198d4`
- `0x180019dcc`

## callees

- `0x180005cc0`
- `0x18000957c`
- `0x180010c18`
- `0x18001924c`
- `0x180019598`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019615`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019615`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18001967a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18001967a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180019661`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180019661`
- `USER32!GetDlgItem` at `0x18001964c`
- `USER32!GetDlgItem` at `0x18001966c`
- `USER32!GetDlgItem` at `0x18001964c`
- `USER32!GetDlgItem` at `0x18001966c`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_DisplayNewDataDirectory(CIndexSettingsPage *this)
{
  const unsigned __int16 *v1; // rdi
  int v3; // ebx
  CIndexSettingsPage *v4; // rcx
  HWND DlgItem; // rax
  HWND v6; // rax
  int cchCount1[2]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 lParam[264]; // [rsp+40h] [rbp-228h] BYREF

  v1 = (const unsigned __int16 *)((char *)this + 600);
  *(_QWORD *)cchCount1 = 0;
  v3 = StringCchLengthW((const unsigned __int16 *)this + 300, 0x104u, (unsigned __int64 *)cchCount1);
  if ( v3 >= 0 )
  {
    if ( *(_QWORD *)cchCount1 )
    {
      if ( CompareStringW(0x7Fu, 1u, v1, cchCount1[0], (PCNZWCH)this + 40, -1) != 2 )
      {
        StringCchCopyW(lParam, 0x104u, v1);
        v3 = CIndexSettingsPage::_DataDirectoryStripSuffx(v4, lParam);
        if ( v3 >= 0 )
        {
          DlgItem = GetDlgItem(*(HWND *)this, 907);
          SendMessageW(DlgItem, 0xCu, 0, (LPARAM)lParam);
          v6 = GetDlgItem(*(HWND *)this, 907);
          EnableWindow(v6, 1);
        }
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180019598  mov     [rsp+arg_8], rbx
0x18001959d  mov     [rsp+arg_10], rsi
0x1800195a2  push    rdi
0x1800195a3  sub     rsp, 260h
0x1800195aa  mov     rax, cs:__security_cookie
0x1800195b1  xor     rax, rsp
0x1800195b4  mov     [rsp+268h+var_18], rax
0x1800195bc  lea     rdi, [rcx+258h]
0x1800195c3  mov     qword ptr [rsp+268h+cchCount1], 0
0x1800195cc  mov     rsi, rcx
0x1800195cf  lea     r8, [rsp+268h+cchCount1]; unsigned __int64 *
0x1800195d4  mov     rcx, rdi; unsigned __int16 *
0x1800195d7  mov     edx, 104h; unsigned __int64
0x1800195dc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800195e1  mov     ebx, eax
0x1800195e3  test    eax, eax
0x1800195e5  js      loc_180019680
0x1800195eb  mov     r9, qword ptr [rsp+268h+cchCount1]; cchCount1
0x1800195f0  test    r9, r9
0x1800195f3  jz      loc_180019680
0x1800195f9  lea     rcx, [rsi+50h]
0x1800195fd  mov     [rsp+268h+cchCount2], 0FFFFFFFFh; cchCount2
0x180019605  mov     edx, 1; dwCmpFlags
0x18001960a  mov     [rsp+268h+lpString2], rcx; lpString2
0x18001960f  mov     r8, rdi; lpString1
0x180019612  lea     ecx, [rdx+7Eh]; Locale
0x180019615  call    cs:__imp_CompareStringW
0x18001961b  cmp     eax, 2
0x18001961e  jz      short loc_180019680
0x180019620  mov     r8, rdi; unsigned __int16 *
0x180019623  lea     rcx, [rsp+268h+lParam]; unsigned __int16 *
0x180019628  mov     edx, 104h; unsigned __int64
0x18001962d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019632  lea     rdx, [rsp+268h+lParam]; unsigned __int16 *
0x180019637  call    ?_DataDirectoryStripSuffx@CIndexSettingsPage@@AEAAJPEAG@Z; CIndexSettingsPage::_DataDirectoryStripSuffx(ushort *)
0x18001963c  mov     ebx, eax
0x18001963e  test    eax, eax
0x180019640  js      short loc_180019680
0x180019642  mov     rcx, [rsi]; hDlg
0x180019645  mov     edi, 38Bh
0x18001964a  mov     edx, edi; nIDDlgItem
0x18001964c  call    cs:__imp_GetDlgItem
0x180019652  xor     r8d, r8d; wParam
0x180019655  lea     r9, [rsp+268h+lParam]; lParam
0x18001965a  mov     rcx, rax; hWnd
0x18001965d  lea     edx, [r8+0Ch]; Msg
0x180019661  call    cs:__imp_SendMessageW
0x180019667  mov     rcx, [rsi]; hDlg
0x18001966a  mov     edx, edi; nIDDlgItem
0x18001966c  call    cs:__imp_GetDlgItem
0x180019672  mov     rcx, rax; hWnd
0x180019675  mov     edx, 1; bEnable
0x18001967a  call    cs:__imp_EnableWindow
0x180019680  mov     eax, ebx
0x180019682  mov     rcx, [rsp+268h+var_18]
0x18001968a  xor     rcx, rsp; StackCookie
0x18001968d  call    __security_check_cookie
0x180019692  lea     r11, [rsp+268h+var_8]
0x18001969a  mov     rbx, [r11+18h]
0x18001969e  mov     rsi, [r11+20h]
0x1800196a2  mov     rsp, r11
0x1800196a5  pop     rdi
0x1800196a6  retn
```
