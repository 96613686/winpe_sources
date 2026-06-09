# CLibrarySharingCustomizeDlg::OnInitDialog(void)

- ea: `0x1800059a8`
- end: `0x180005bb3`
- name: `?OnInitDialog@CLibrarySharingCustomizeDlg@@QEAA_JXZ`
- size: `523`
- prototype: `__int64 __fastcall(CLibrarySharingCustomizeDlg *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180007270`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x18000449c`
- `0x1800049c0`
- `0x180004ff0`
- `0x1800059a8`
- `0x180005ce8`
- `0x18000638c`
- `0x180006ca8`
- `0x180006d34`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005aa0`
- `ole32!CoTaskMemFree` at `0x180005aa0`
- `GDI32!DeleteObject` at `0x180005b60`
- `GDI32!DeleteObject` at `0x180005b60`
- `USER32!SetDlgItemTextW` at `0x180005a95`
- `USER32!SetDlgItemTextW` at `0x180005a95`
- `USER32!SendDlgItemMessageW` at `0x180005acf`
- `USER32!SendDlgItemMessageW` at `0x180005b52`
- `USER32!SendDlgItemMessageW` at `0x180005acf`
- `USER32!SendDlgItemMessageW` at `0x180005b52`
- `USER32!LoadStringW` at `0x180005a4c`
- `USER32!LoadStringW` at `0x180005a4c`

## pseudocode

```c
__int64 __fastcall CLibrarySharingCustomizeDlg::OnInitDialog(CLibrarySharingCustomizeDlg *this)
{
  CDeviceSettings *v2; // rcx
  const WCHAR **v3; // rcx
  __int64 v4; // rdx
  int v5; // r8d
  void *v6; // rax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPARAM lParam; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[304]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String[304]; // [rsp+2A0h] [rbp+1A0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  v2 = (CDeviceSettings *)*((_QWORD *)this + 2);
  pv = 0;
  if ( CDeviceSettings::GetDeviceName(v2, (unsigned __int16 **)&pv) >= 0 )
  {
    memset_0(Buffer, 0, 0x258u);
    LoadStringW(g_hinst, 0x1Eu, Buffer, 300);
    memset_0(String, 0, 0x258u);
    if ( (int)StringCchPrintfW(String, 0x12Cu, Buffer, pv) >= 0 )
      SetDlgItemTextW(*((HWND *)this + 1), 320, String);
    CoTaskMemFree(pv);
  }
  CLibrarySharingFilterDlg::OnInitDialog(this);
  SendDlgItemMessageW(*((HWND *)this + 1), 315, 0xF1u, *((_DWORD *)this + 6) != 0, 0);
  CLibrarySharingFilterDlg::SetCheckboxesByDevice(
    this,
    *(struct CDeviceSettings **)((char *)this + (*((_DWORD *)this + 6) != 0 ? 0x38 : 0) + 16));
  CLibrarySharingFilterDlg::InitParentalRatingListByDevice(
    this,
    *(struct CDeviceSettings **)((char *)this + (*((_DWORD *)this + 6) != 0 ? 0x38 : 0) + 16));
  CLibrarySharingFilterDlg::UpdateStateOfDialogItemsByDevice(
    this,
    *(struct CDeviceSettings **)((char *)this + (*((_DWORD *)this + 6) != 0 ? 0x38 : 0) + 16));
  v3 = (const WCHAR **)*((_QWORD *)this + 2);
  lParam = 0;
  if ( (int)CDeviceSettings::GetDeviceIcon(v3, v4, v5, (HBITMAP *)&lParam) >= 0 )
  {
    v6 = (void *)SendDlgItemMessageW(*((HWND *)this + 1), 301, 0x172u, 0, lParam);
    if ( v6 )
      DeleteObject(v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800059a8  mov     [rsp-8+arg_8], rbx
0x1800059ad  mov     [rsp-8+arg_10], r15
0x1800059b2  push    rbp
0x1800059b3  lea     rbp, [rsp-410h]
0x1800059bb  sub     rsp, 510h
0x1800059c2  mov     rax, cs:__security_cookie
0x1800059c9  xor     rax, rsp
0x1800059cc  mov     [rbp+410h+var_10], rax
0x1800059d3  mov     rbx, rcx
0x1800059d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059dd  lea     r15, WPP_GLOBAL_Control
0x1800059e4  cmp     rcx, r15
0x1800059e7  jz      short loc_180005A04
0x1800059e9  test    byte ptr [rcx+1Ch], 20h
0x1800059ed  jz      short loc_180005A04
0x1800059ef  mov     rcx, [rcx+10h]
0x1800059f3  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800059fa  mov     edx, 6Eh ; 'n'
0x1800059ff  call    WPP_SF_
0x180005a04  mov     rcx, [rbx+10h]; this
0x180005a08  lea     rdx, [rsp+510h+pv]; unsigned __int16 **
0x180005a0d  mov     [rsp+510h+pv], 0
0x180005a16  call    ?GetDeviceName@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetDeviceName(ushort * *)
0x180005a1b  test    eax, eax
0x180005a1d  js      loc_180005AA6
0x180005a23  xor     edx, edx; Val
0x180005a25  lea     rcx, [rsp+510h+Buffer]; void *
0x180005a2a  mov     r8d, 258h; Size
0x180005a30  call    memset_0
0x180005a35  mov     rcx, cs:g_hinst; hInstance
0x180005a3c  lea     r8, [rsp+510h+Buffer]; lpBuffer
0x180005a41  mov     r9d, 12Ch; cchBufferMax
0x180005a47  mov     edx, 1Eh; uID
0x180005a4c  call    cs:__imp_LoadStringW
0x180005a52  xor     edx, edx; Val
0x180005a54  lea     rcx, [rbp+410h+String]; void *
0x180005a5b  mov     r8d, 258h; Size
0x180005a61  call    memset_0
0x180005a66  mov     r9, [rsp+510h+pv]
0x180005a6b  lea     r8, [rsp+510h+Buffer]; unsigned __int16 *
0x180005a70  mov     edx, 12Ch; unsigned __int64
0x180005a75  lea     rcx, [rbp+410h+String]; unsigned __int16 *
0x180005a7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a81  test    eax, eax
0x180005a83  js      short loc_180005A9B
0x180005a85  mov     rcx, [rbx+8]; hDlg
0x180005a89  lea     r8, [rbp+410h+String]; lpString
0x180005a90  mov     edx, 140h; nIDDlgItem
0x180005a95  call    cs:__imp_SetDlgItemTextW
0x180005a9b  mov     rcx, [rsp+510h+pv]; pv
0x180005aa0  call    cs:__imp_CoTaskMemFree
0x180005aa6  mov     rcx, rbx; this
0x180005aa9  call    ?OnInitDialog@CLibrarySharingFilterDlg@@IEAA_JXZ; CLibrarySharingFilterDlg::OnInitDialog(void)
0x180005aae  mov     rcx, [rbx+8]; hDlg
0x180005ab2  xor     r9d, r9d
0x180005ab5  cmp     [rbx+18h], r9d
0x180005ab9  mov     edx, 13Bh; nIDDlgItem
0x180005abe  mov     [rsp+510h+lParam], 0; lParam
0x180005ac7  setnz   r9b; wParam
0x180005acb  lea     r8d, [rdx-4Ah]; Msg
0x180005acf  call    cs:__imp_SendDlgItemMessageW
0x180005ad5  mov     eax, [rbx+18h]
0x180005ad8  mov     rcx, rbx; this
0x180005adb  neg     eax
0x180005add  sbb     rdx, rdx
0x180005ae0  and     edx, 38h
0x180005ae3  mov     rdx, [rdx+rbx+10h]; struct CDeviceSettings *
0x180005ae8  call    ?SetCheckboxesByDevice@CLibrarySharingFilterDlg@@IEAAJPEAVCDeviceSettings@@@Z; CLibrarySharingFilterDlg::SetCheckboxesByDevice(CDeviceSettings *)
0x180005aed  mov     eax, [rbx+18h]
0x180005af0  mov     rcx, rbx; this
0x180005af3  neg     eax
0x180005af5  sbb     rdx, rdx
0x180005af8  and     edx, 38h
0x180005afb  mov     rdx, [rdx+rbx+10h]; struct CDeviceSettings *
0x180005b00  call    ?InitParentalRatingListByDevice@CLibrarySharingFilterDlg@@IEAAJPEAVCDeviceSettings@@@Z; CLibrarySharingFilterDlg::InitParentalRatingListByDevice(CDeviceSettings *)
0x180005b05  mov     eax, [rbx+18h]
0x180005b08  mov     rcx, rbx; this
0x180005b0b  neg     eax
0x180005b0d  sbb     rdx, rdx
0x180005b10  and     edx, 38h
0x180005b13  mov     rdx, [rdx+rbx+10h]; struct CDeviceSettings *
0x180005b18  call    ?UpdateStateOfDialogItemsByDevice@CLibrarySharingFilterDlg@@IEAAJPEAVCDeviceSettings@@@Z; CLibrarySharingFilterDlg::UpdateStateOfDialogItemsByDevice(CDeviceSettings *)
0x180005b1d  mov     rcx, [rbx+10h]; this
0x180005b21  lea     r9, [rsp+510h+var_4D8]; HBITMAP *
0x180005b26  mov     [rsp+510h+var_4D8], 0
0x180005b2f  call    ?GetDeviceIcon@CDeviceSettings@@QEAAJHHPEAPEAUHBITMAP__@@@Z; CDeviceSettings::GetDeviceIcon(int,int,HBITMAP__ * *)
0x180005b34  test    eax, eax
0x180005b36  js      short loc_180005B66
0x180005b38  mov     rax, [rsp+510h+var_4D8]
0x180005b3d  mov     edx, 12Dh; nIDDlgItem
0x180005b42  mov     rcx, [rbx+8]; hDlg
0x180005b46  xor     r9d, r9d; wParam
0x180005b49  mov     [rsp+510h+lParam], rax; lParam
0x180005b4e  lea     r8d, [rdx+45h]; Msg
0x180005b52  call    cs:__imp_SendDlgItemMessageW
0x180005b58  test    rax, rax
0x180005b5b  jz      short loc_180005B66
0x180005b5d  mov     rcx, rax; ho
0x180005b60  call    cs:__imp_DeleteObject
0x180005b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b6d  cmp     rcx, r15
0x180005b70  jz      short loc_180005B8D
0x180005b72  test    byte ptr [rcx+1Ch], 20h
0x180005b76  jz      short loc_180005B8D
0x180005b78  mov     rcx, [rcx+10h]
0x180005b7c  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005b83  mov     edx, 6Fh ; 'o'
0x180005b88  call    WPP_SF_
0x180005b8d  xor     eax, eax
0x180005b8f  mov     rcx, [rbp+410h+var_10]
0x180005b96  xor     rcx, rsp; StackCookie
0x180005b99  call    __security_check_cookie
0x180005b9e  lea     r11, [rsp+510h+var_s0]
0x180005ba6  mov     rbx, [r11+18h]
0x180005baa  mov     r15, [r11+20h]
0x180005bae  mov     rsp, r11
0x180005bb1  pop     rbp
0x180005bb2  retn
```
