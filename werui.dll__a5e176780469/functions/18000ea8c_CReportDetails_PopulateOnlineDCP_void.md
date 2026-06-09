# CReportDetails::PopulateOnlineDCP(void)

- ea: `0x18000ea8c`
- end: `0x18000ec84`
- name: `?PopulateOnlineDCP@CReportDetails@@AEAAJXZ`
- size: `504`
- prototype: `__int64 __fastcall(CReportDetails *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e348`

## callees

- `0x180005c80`
- `0x180008f3c`
- `0x180009580`
- `0x1800096d0`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `USER32!GetSysColor` at `0x18000eb0e`
- `USER32!GetSysColor` at `0x18000ebe9`
- `USER32!GetSysColor` at `0x18000eb0e`
- `USER32!GetSysColor` at `0x18000ebe9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eaeb`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb34`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb49`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb73`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb88`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ebb3`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec01`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec16`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec3a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec52`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eaeb`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb34`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb49`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb73`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000eb88`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ebb3`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec01`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec16`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec3a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000ec52`

## string_xrefs

- `0x18000eb93`: `https://go.microsoft.com/fwlink/?LinkId=521839`

## pseudocode

```c
__int64 __fastcall CReportDetails::PopulateOnlineDCP(HWND *this)
{
  HWND v2; // rcx
  int v3; // eax
  DWORD v4; // eax
  HWND v5; // rcx
  HWND v6; // rcx
  WPARAM wParam; // [rsp+20h] [rbp-49h] BYREF
  LPARAM v9[5]; // [rsp+28h] [rbp-41h] BYREF
  _BYTE lParam[12]; // [rsp+50h] [rbp-19h] BYREF
  DWORD SysColor; // [rsp+64h] [rbp-5h]

  memset_0(lParam, 0, 0x5Cu);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v9);
  v2 = *this;
  wParam = 0;
  SendMessageW(v2, 0x445u, 0, 0x4000000);
  *(_QWORD *)lParam = 0x400000010000005CLL;
  *(_DWORD *)&lParam[8] = 1;
  SysColor = GetSysColor(26);
  UtilLoadString(v9, 218);
  SendMessageW(*this, 0x444u, 1u, (LPARAM)lParam);
  SendMessageW(*this, 0xC2u, 0, v9[0]);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v9, L"  ");
  SendMessageW(*this, 0x444u, 1u, (LPARAM)lParam);
  SendMessageW(*this, 0xC2u, 0, v9[0]);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    v9,
    L"https://go.microsoft.com/fwlink/?LinkId=521839");
  SendMessageW(*this, 0xB0u, (WPARAM)&wParam, (LPARAM)&wParam + 4);
  v3 = wParam + ((v9[1] - v9[0]) >> 1);
  *((_DWORD *)this + 3) = wParam;
  *((_DWORD *)this + 4) = v3;
  *(_QWORD *)lParam = 0x400000250000005CLL;
  *(_DWORD *)&lParam[8] = 36;
  v4 = GetSysColor(26);
  v5 = *this;
  SysColor = v4;
  SendMessageW(v5, 0x444u, 1u, (LPARAM)lParam);
  SendMessageW(*this, 0xC2u, 0, v9[0]);
  *(_DWORD *)lParam = 92;
  v6 = *this;
  *(_QWORD *)&lParam[4] = 1073741861;
  SendMessageW(v6, 0x444u, 1u, (LPARAM)lParam);
  SendMessageW(*this, 0xC2u, 0, (LPARAM)L"\r\n\r\n");
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v9);
  return 0;
}

```

## disassembly

```asm
0x18000ea8c  mov     [rsp-8+arg_8], rbx
0x18000ea91  mov     [rsp-8+arg_10], r12
0x18000ea96  push    rbp
0x18000ea97  lea     rbp, [rsp-57h]
0x18000ea9c  sub     rsp, 0C0h
0x18000eaa3  mov     rax, cs:__security_cookie
0x18000eaaa  xor     rax, rsp
0x18000eaad  mov     [rbp+57h+var_10], rax
0x18000eab1  xor     edx, edx; Val
0x18000eab3  mov     rbx, rcx
0x18000eab6  lea     rcx, [rbp+57h+lParam]; void *
0x18000eaba  lea     r8d, [rdx+5Ch]; Size
0x18000eabe  call    memset_0
0x18000eac3  lea     rcx, [rbp+57h+var_98]; void *
0x18000eac7  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000eacc  mov     rcx, [rbx]; hWnd
0x18000eacf  mov     r9d, 4000000h; lParam
0x18000ead5  xor     r8d, r8d; wParam
0x18000ead8  mov     dword ptr [rbp+57h+wParam], 0
0x18000eadf  mov     edx, 445h; Msg
0x18000eae4  mov     dword ptr [rbp+57h+wParam+4], 0
0x18000eaeb  call    cs:__imp_SendMessageW
0x18000eaf1  mov     r12d, 1
0x18000eaf7  mov     dword ptr [rbp+57h+lParam], 5Ch ; '\'
0x18000eafe  mov     dword ptr [rbp+57h+lParam+4], 40000001h
0x18000eb05  mov     [rbp-11h], r12d
0x18000eb09  lea     ecx, [r12+19h]; nIndex
0x18000eb0e  call    cs:__imp_GetSysColor
0x18000eb14  mov     edx, 0DAh
0x18000eb19  lea     rcx, [rbp+57h+var_98]
0x18000eb1d  mov     [rbp+57h+var_5C], eax
0x18000eb20  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000eb25  mov     rcx, [rbx]; hWnd
0x18000eb28  lea     r9, [rbp+57h+lParam]; lParam
0x18000eb2c  mov     r8d, r12d; wParam
0x18000eb2f  mov     edx, 444h; Msg
0x18000eb34  call    cs:__imp_SendMessageW
0x18000eb3a  mov     r9, [rbp+57h+var_98]; lParam
0x18000eb3e  xor     r8d, r8d; wParam
0x18000eb41  mov     rcx, [rbx]; hWnd
0x18000eb44  mov     edx, 0C2h; Msg
0x18000eb49  call    cs:__imp_SendMessageW
0x18000eb4f  lea     r8d, [r12+1]
0x18000eb54  lea     rdx, asc_18001B348; "  "
0x18000eb5b  lea     rcx, [rbp+57h+var_98]
0x18000eb5f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000eb64  mov     rcx, [rbx]; hWnd
0x18000eb67  lea     r9, [rbp+57h+lParam]; lParam
0x18000eb6b  mov     r8d, r12d; wParam
0x18000eb6e  mov     edx, 444h; Msg
0x18000eb73  call    cs:__imp_SendMessageW
0x18000eb79  mov     r9, [rbp+57h+var_98]; lParam
0x18000eb7d  xor     r8d, r8d; wParam
0x18000eb80  mov     rcx, [rbx]; hWnd
0x18000eb83  mov     edx, 0C2h; Msg
0x18000eb88  call    cs:__imp_SendMessageW
0x18000eb8e  lea     r8d, [r12+2Dh]
0x18000eb93  lea     rdx, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?LinkId"...
0x18000eb9a  lea     rcx, [rbp+57h+var_98]
0x18000eb9e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000eba3  mov     rcx, [rbx]; hWnd
0x18000eba6  lea     r9, [rbp+57h+wParam+4]; lParam
0x18000ebaa  lea     r8, [rbp+57h+wParam]; wParam
0x18000ebae  mov     edx, 0B0h; Msg
0x18000ebb3  call    cs:__imp_SendMessageW
0x18000ebb9  mov     edx, dword ptr [rbp+57h+wParam]
0x18000ebbc  lea     ecx, [r12+19h]; nIndex
0x18000ebc1  mov     rax, [rbp+57h+var_90]
0x18000ebc5  sub     rax, [rbp+57h+var_98]
0x18000ebc9  sar     rax, 1
0x18000ebcc  add     eax, edx
0x18000ebce  mov     [rbx+0Ch], edx
0x18000ebd1  mov     [rbx+10h], eax
0x18000ebd4  mov     dword ptr [rbp+57h+lParam], 5Ch ; '\'
0x18000ebdb  mov     dword ptr [rbp+57h+lParam+4], 40000025h
0x18000ebe2  mov     dword ptr [rbp-11h], 24h ; '$'
0x18000ebe9  call    cs:__imp_GetSysColor
0x18000ebef  mov     rcx, [rbx]; hWnd
0x18000ebf2  lea     r9, [rbp+57h+lParam]; lParam
0x18000ebf6  mov     r8d, r12d; wParam
0x18000ebf9  mov     [rbp+57h+var_5C], eax
0x18000ebfc  mov     edx, 444h; Msg
0x18000ec01  call    cs:__imp_SendMessageW
0x18000ec07  mov     r9, [rbp+57h+var_98]; lParam
0x18000ec0b  xor     r8d, r8d; wParam
0x18000ec0e  mov     rcx, [rbx]; hWnd
0x18000ec11  mov     edx, 0C2h; Msg
0x18000ec16  call    cs:__imp_SendMessageW
0x18000ec1c  mov     dword ptr [rbp+57h+lParam], 5Ch ; '\'
0x18000ec23  mov     rcx, [rbx]; hWnd
0x18000ec26  lea     r9, [rbp+57h+lParam]; lParam
0x18000ec2a  mov     r8d, r12d; wParam
0x18000ec2d  mov     [rbp+57h+lParam+4], 40000025h
0x18000ec35  mov     edx, 444h; Msg
0x18000ec3a  call    cs:__imp_SendMessageW
0x18000ec40  mov     rcx, [rbx]; hWnd
0x18000ec43  lea     r9, asc_18001B358; "\r\n\r\n"
0x18000ec4a  xor     r8d, r8d; wParam
0x18000ec4d  mov     edx, 0C2h; Msg
0x18000ec52  call    cs:__imp_SendMessageW
0x18000ec58  lea     rcx, [rbp+57h+var_98]
0x18000ec5c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000ec61  xor     eax, eax
0x18000ec63  mov     rcx, [rbp+57h+var_10]
0x18000ec67  xor     rcx, rsp; StackCookie
0x18000ec6a  call    __security_check_cookie
0x18000ec6f  lea     r11, [rsp+0C0h+var_s0]
0x18000ec77  mov     rbx, [r11+18h]
0x18000ec7b  mov     r12, [r11+20h]
0x18000ec7f  mov     rsp, r11
0x18000ec82  pop     rbp
0x18000ec83  retn
```
