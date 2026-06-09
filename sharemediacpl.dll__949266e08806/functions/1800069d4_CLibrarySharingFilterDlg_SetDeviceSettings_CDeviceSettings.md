# CLibrarySharingFilterDlg::SetDeviceSettings(CDeviceSettings *)

- ea: `0x1800069d4`
- end: `0x180006b33`
- name: `?SetDeviceSettings@CLibrarySharingFilterDlg@@QEAAJPEAVCDeviceSettings@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(CLibrarySharingFilterDlg *__hidden this, struct CDeviceSettings *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18000f430`
- `0x18000f660`

## callees

- `0x180003860`
- `0x180003888`
- `0x180003d5c`
- `0x180004c40`
- `0x180004ce8`
- `0x180004f78`
- `0x1800069d4`
- `0x180006bfc`
- `0x180016d00`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180006a7f`
- `ole32!CoCreateInstance` at `0x180006a7f`
- `ole32!CoTaskMemFree` at `0x180006ad3`
- `ole32!CoTaskMemFree` at `0x180006ad3`

## pseudocode

```c
__int64 __fastcall CLibrarySharingFilterDlg::SetDeviceSettings(
        CLibrarySharingFilterDlg *this,
        struct CDeviceSettings *a2)
{
  _QWORD *v4; // rcx
  HRESULT WMPDeviceSettings; // ebx
  CDeviceSettings **v6; // rdi
  CDeviceSettings *v7; // rcx
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v8; // r9
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF
  HMEHelpers *ppv; // [rsp+60h] [rbp+18h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v6 = (CDeviceSettings **)((char *)this + 16);
    IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>((char *)this + 16);
    *((_QWORD *)this + 2) = a2;
    (*(void (__fastcall **)(struct CDeviceSettings *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( (unsigned int)CDeviceSettings::HasDeviceSettings(*((CDeviceSettings **)this + 2)) )
    {
      WMPDeviceSettings = CDeviceSettings::GetWMPDeviceSettings(*v6, (CLibrarySharingFilterDlg *)((char *)this + 24));
    }
    else
    {
      ppv = 0;
      WMPDeviceSettings = CoCreateInstance(
                            &GUID_6bf52a52_394a_11d3_b153_00c04f79faa6,
                            0,
                            1u,
                            &GUID_2712e1d1_c205_442e_8a24_b1874058fdee,
                            (LPVOID *)&ppv);
      if ( WMPDeviceSettings >= 0 )
      {
        v7 = *v6;
        pv = 0;
        WMPDeviceSettings = CDeviceSettings::GetID(v7, (unsigned __int16 **)&pv);
        if ( WMPDeviceSettings >= 0 )
        {
          WMPDeviceSettings = HMEHelpers::RetrieveWMPDeviceSettings(
                                ppv,
                                (struct IWMPPlayerInternalMarshalled *)pv,
                                (unsigned __int16 *)this + 12,
                                v8);
          if ( WMPDeviceSettings >= 0 )
            WMPDeviceSettings = CDeviceSettings::SetWMPDeviceSettings(
                                  *v6,
                                  (CLibrarySharingFilterDlg *)((char *)this + 24));
          CoTaskMemFree(pv);
        }
        (*(void (__fastcall **)(HMEHelpers *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    WMPDeviceSettings = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 89, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, (unsigned int)WMPDeviceSettings);
  return (unsigned int)WMPDeviceSettings;
}

```

## disassembly

```asm
0x1800069d4  mov     [rsp+arg_0], rbx
0x1800069d9  push    rbp
0x1800069da  push    rsi
0x1800069db  push    rdi
0x1800069dc  sub     rsp, 30h
0x1800069e0  mov     rbx, rdx
0x1800069e3  mov     rsi, rcx
0x1800069e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069ed  lea     rbp, WPP_GLOBAL_Control
0x1800069f4  cmp     rcx, rbp
0x1800069f7  jz      short loc_180006A1B
0x1800069f9  test    byte ptr [rcx+1Ch], 20h
0x1800069fd  jz      short loc_180006A1B
0x1800069ff  mov     rcx, [rcx+10h]
0x180006a03  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006a0a  mov     edx, 58h ; 'X'
0x180006a0f  call    WPP_SF_
0x180006a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a1b  test    rbx, rbx
0x180006a1e  jnz     short loc_180006A2A
0x180006a20  mov     ebx, 80004003h
0x180006a25  jmp     loc_180006B01
0x180006a2a  lea     rdi, [rsi+10h]
0x180006a2e  mov     rcx, rdi
0x180006a31  call    ??$IUnknown_SafeReleaseAndNullPtr@VCDeviceSettings@@@@YAXAEAPEAVCDeviceSettings@@@Z; IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(CDeviceSettings * &)
0x180006a36  mov     [rdi], rbx
0x180006a39  mov     rcx, rbx
0x180006a3c  mov     rax, [rbx]
0x180006a3f  mov     rax, [rax+8]
0x180006a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a48  mov     rcx, [rdi]; this
0x180006a4b  call    ?HasDeviceSettings@CDeviceSettings@@QEAAHXZ; CDeviceSettings::HasDeviceSettings(void)
0x180006a50  test    eax, eax
0x180006a52  jnz     loc_180006AEC
0x180006a58  xor     edx, edx; pUnkOuter
0x180006a5a  mov     [rsp+48h+arg_10], 0
0x180006a63  lea     rax, [rsp+48h+arg_10]
0x180006a68  lea     r9, _GUID_2712e1d1_c205_442e_8a24_b1874058fdee; riid
0x180006a6f  mov     [rsp+48h+ppv], rax; ppv
0x180006a74  lea     rcx, _GUID_6bf52a52_394a_11d3_b153_00c04f79faa6; rclsid
0x180006a7b  lea     r8d, [rdx+1]; dwClsContext
0x180006a7f  call    cs:__imp_CoCreateInstance
0x180006a85  mov     ebx, eax
0x180006a87  test    eax, eax
0x180006a89  js      short loc_180006AFA
0x180006a8b  mov     rcx, [rdi]; this
0x180006a8e  lea     rdx, [rsp+48h+pv]; unsigned __int16 **
0x180006a93  mov     [rsp+48h+pv], 0
0x180006a9c  call    ?GetID@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetID(ushort * *)
0x180006aa1  mov     ebx, eax
0x180006aa3  test    eax, eax
0x180006aa5  js      short loc_180006AD9
0x180006aa7  mov     rdx, [rsp+48h+pv]; struct IWMPPlayerInternalMarshalled *
0x180006aac  lea     r8, [rsi+18h]; unsigned __int16 *
0x180006ab0  mov     rcx, [rsp+48h+arg_10]; this
0x180006ab5  call    ?RetrieveWMPDeviceSettings@HMEHelpers@@YAJPEAUIWMPPlayerInternalMarshalled@@PEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::RetrieveWMPDeviceSettings(IWMPPlayerInternalMarshalled *,ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006aba  mov     ebx, eax
0x180006abc  test    eax, eax
0x180006abe  js      short loc_180006ACE
0x180006ac0  mov     rcx, [rdi]; this
0x180006ac3  lea     rdx, [rsi+18h]; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180006ac7  call    ?SetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; CDeviceSettings::SetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006acc  mov     ebx, eax
0x180006ace  mov     rcx, [rsp+48h+pv]; pv
0x180006ad3  call    cs:__imp_CoTaskMemFree
0x180006ad9  mov     rcx, [rsp+48h+arg_10]
0x180006ade  mov     rax, [rcx]
0x180006ae1  mov     rax, [rax+10h]
0x180006ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aea  jmp     short loc_180006AFA
0x180006aec  mov     rcx, [rdi]; this
0x180006aef  lea     rdx, [rsi+18h]; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180006af3  call    ?GetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; CDeviceSettings::GetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006af8  mov     ebx, eax
0x180006afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b01  cmp     rcx, rbp
0x180006b04  jz      short loc_180006B24
0x180006b06  test    byte ptr [rcx+1Ch], 20h
0x180006b0a  jz      short loc_180006B24
0x180006b0c  mov     rcx, [rcx+10h]
0x180006b10  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006b17  mov     edx, 59h ; 'Y'
0x180006b1c  mov     r9d, ebx
0x180006b1f  call    WPP_SF_d
0x180006b24  mov     eax, ebx
0x180006b26  mov     rbx, [rsp+48h+arg_0]
0x180006b2b  add     rsp, 30h
0x180006b2f  pop     rdi
0x180006b30  pop     rsi
0x180006b31  pop     rbp
0x180006b32  retn
```
