# CLibrarySharingDefaultsDlg::OnInitDialog(void)

- ea: `0x180005bbc`
- end: `0x180005cdf`
- name: `?OnInitDialog@CLibrarySharingDefaultsDlg@@QEAA_JXZ`
- size: `291`
- prototype: `__int64 __fastcall(CLibrarySharingDefaultsDlg *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18000735c`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004da4`
- `0x180004ff0`
- `0x18000553c`
- `0x180005bbc`
- `0x180005ce8`
- `0x18000638c`
- `0x180006d34`

## import_xrefs

- `GDI32!DeleteObject` at `0x180005c9a`
- `GDI32!DeleteObject` at `0x180005c9a`
- `USER32!SendDlgItemMessageW` at `0x180005c8c`
- `USER32!SendDlgItemMessageW` at `0x180005c8c`

## pseudocode

```c
__int64 __fastcall CLibrarySharingDefaultsDlg::OnInitDialog(CLibrarySharingDefaultsDlg *this)
{
  unsigned __int16 *v2; // rcx
  int v3; // edi
  void *v4; // rax
  HICON v6; // [rsp+40h] [rbp+8h] BYREF
  LPARAM lParam; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  CLibrarySharingFilterDlg::OnInitDialog(this);
  CLibrarySharingFilterDlg::SetCheckboxesByDevice(this, *((struct CDeviceSettings **)this + 2));
  CLibrarySharingFilterDlg::InitParentalRatingListByDevice(this, *((struct CDeviceSettings **)this + 2));
  CLibrarySharingFilterDlg::UpdateStateOfDialogItemsByDevice(this, *((struct CDeviceSettings **)this + 2));
  v6 = 0;
  v3 = LoadIconFromModule(v2, 0x7277u, 32, 32, &v6);
  if ( v3 >= 0 )
  {
    lParam = 0;
    v3 = HBITMAPFromHICON(v6, (HBITMAP *)&lParam);
    if ( v3 >= 0 )
    {
      v4 = (void *)SendDlgItemMessageW(*((HWND *)this + 1), 301, 0x172u, 0, lParam);
      if ( v4 )
        DeleteObject(v4);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, (unsigned int)v3);
  return 1;
}

```

## disassembly

```asm
0x180005bbc  mov     [rsp+arg_10], rbx
0x180005bc1  mov     [rsp+arg_18], rbp
0x180005bc6  push    rdi
0x180005bc7  sub     rsp, 30h
0x180005bcb  mov     rbx, rcx
0x180005bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bd5  lea     rbp, WPP_GLOBAL_Control
0x180005bdc  cmp     rcx, rbp
0x180005bdf  jz      short loc_180005BFC
0x180005be1  test    byte ptr [rcx+1Ch], 20h
0x180005be5  jz      short loc_180005BFC
0x180005be7  mov     rcx, [rcx+10h]
0x180005beb  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005bf2  mov     edx, 60h ; '`'
0x180005bf7  call    WPP_SF_
0x180005bfc  mov     rcx, rbx; this
0x180005bff  call    ?OnInitDialog@CLibrarySharingFilterDlg@@IEAA_JXZ; CLibrarySharingFilterDlg::OnInitDialog(void)
0x180005c04  mov     rdx, [rbx+10h]; struct CDeviceSettings *
0x180005c08  mov     rcx, rbx; this
0x180005c0b  call    ?SetCheckboxesByDevice@CLibrarySharingFilterDlg@@IEAAJPEAVCDeviceSettings@@@Z; CLibrarySharingFilterDlg::SetCheckboxesByDevice(CDeviceSettings *)
0x180005c10  mov     rdx, [rbx+10h]; struct CDeviceSettings *
0x180005c14  mov     rcx, rbx; this
0x180005c17  call    ?InitParentalRatingListByDevice@CLibrarySharingFilterDlg@@IEAAJPEAVCDeviceSettings@@@Z; CLibrarySharingFilterDlg::InitParentalRatingListByDevice(CDeviceSettings *)
0x180005c1c  mov     rdx, [rbx+10h]; struct CDeviceSettings *
0x180005c20  mov     rcx, rbx; this
0x180005c23  call    ?UpdateStateOfDialogItemsByDevice@CLibrarySharingFilterDlg@@IEAAJPEAVCDeviceSettings@@@Z; CLibrarySharingFilterDlg::UpdateStateOfDialogItemsByDevice(CDeviceSettings *)
0x180005c28  mov     r9d, 20h ; ' '; int
0x180005c2e  mov     [rsp+38h+arg_0], 0
0x180005c37  lea     rax, [rsp+38h+arg_0]
0x180005c3c  mov     r8d, r9d; int
0x180005c3f  mov     edx, 7277h; unsigned int
0x180005c44  mov     [rsp+38h+lParam], rax; HICON *
0x180005c49  call    ?LoadIconFromModule@@YAJPEAGKHHPEAPEAUHICON__@@@Z; LoadIconFromModule(ushort *,ulong,int,int,HICON__ * *)
0x180005c4e  mov     edi, eax
0x180005c50  test    eax, eax
0x180005c52  js      short loc_180005CA0
0x180005c54  mov     rcx, [rsp+38h+arg_0]; HICON
0x180005c59  lea     rdx, [rsp+38h+arg_8]; HBITMAP *
0x180005c5e  mov     [rsp+38h+arg_8], 0
0x180005c67  call    ?HBITMAPFromHICON@@YAJPEAUHICON__@@PEAPEAUHBITMAP__@@@Z; HBITMAPFromHICON(HICON__ *,HBITMAP__ * *)
0x180005c6c  mov     edi, eax
0x180005c6e  test    eax, eax
0x180005c70  js      short loc_180005CA0
0x180005c72  mov     rax, [rsp+38h+arg_8]
0x180005c77  mov     edx, 12Dh; nIDDlgItem
0x180005c7c  mov     rcx, [rbx+8]; hDlg
0x180005c80  xor     r9d, r9d; wParam
0x180005c83  mov     [rsp+38h+lParam], rax; lParam
0x180005c88  lea     r8d, [rdx+45h]; Msg
0x180005c8c  call    cs:__imp_SendDlgItemMessageW
0x180005c92  test    rax, rax
0x180005c95  jz      short loc_180005CA0
0x180005c97  mov     rcx, rax; ho
0x180005c9a  call    cs:__imp_DeleteObject
0x180005ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ca7  cmp     rcx, rbp
0x180005caa  jz      short loc_180005CCA
0x180005cac  test    byte ptr [rcx+1Ch], 20h
0x180005cb0  jz      short loc_180005CCA
0x180005cb2  mov     rcx, [rcx+10h]
0x180005cb6  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005cbd  mov     edx, 61h ; 'a'
0x180005cc2  mov     r9d, edi
0x180005cc5  call    WPP_SF_d
0x180005cca  mov     rbx, [rsp+38h+arg_10]
0x180005ccf  mov     eax, 1
0x180005cd4  mov     rbp, [rsp+38h+arg_18]
0x180005cd9  add     rsp, 30h
0x180005cdd  pop     rdi
0x180005cde  retn
```
