# CLibrarySharingCustomizeDlg::SetDefaultDeviceSettings(CDeviceSettings *)

- ea: `0x18000653c`
- end: `0x180006696`
- name: `?SetDefaultDeviceSettings@CLibrarySharingCustomizeDlg@@QEAAJPEAVCDeviceSettings@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(CLibrarySharingCustomizeDlg *__hidden this, struct CDeviceSettings *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000f430`

## callees

- `0x180003860`
- `0x180003888`
- `0x180003d5c`
- `0x180004c40`
- `0x180004f78`
- `0x18000653c`
- `0x180006bfc`
- `0x180016d00`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800065e5`
- `ole32!CoCreateInstance` at `0x1800065e5`
- `ole32!CoTaskMemFree` at `0x180006639`
- `ole32!CoTaskMemFree` at `0x180006639`

## pseudocode

```c
__int64 __fastcall CLibrarySharingCustomizeDlg::SetDefaultDeviceSettings(
        CLibrarySharingCustomizeDlg *this,
        struct CDeviceSettings *a2)
{
  _QWORD *v4; // rcx
  CDeviceSettings **v5; // rsi
  HRESULT Instance; // ebx
  CDeviceSettings *v7; // rcx
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v8; // r9
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF
  HMEHelpers *ppv; // [rsp+60h] [rbp+18h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v5 = (CDeviceSettings **)((char *)this + 72);
    Instance = 0;
    IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>((char *)this + 72);
    *((_QWORD *)this + 9) = a2;
    (*(void (__fastcall **)(struct CDeviceSettings *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( !(unsigned int)CDeviceSettings::HasDeviceSettings(*((CDeviceSettings **)this + 9)) )
    {
      ppv = 0;
      Instance = CoCreateInstance(
                   &GUID_6bf52a52_394a_11d3_b153_00c04f79faa6,
                   0,
                   1u,
                   &GUID_2712e1d1_c205_442e_8a24_b1874058fdee,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        v7 = *v5;
        pv = 0;
        Instance = CDeviceSettings::GetID(v7, (unsigned __int16 **)&pv);
        if ( Instance >= 0 )
        {
          Instance = HMEHelpers::RetrieveWMPDeviceSettings(
                       ppv,
                       (struct IWMPPlayerInternalMarshalled *)pv,
                       (unsigned __int16 *)this + 12,
                       v8);
          if ( Instance >= 0 )
            Instance = CDeviceSettings::SetWMPDeviceSettings(*v5, (CLibrarySharingCustomizeDlg *)((char *)this + 24));
          CoTaskMemFree(pv);
        }
        (*(void (__fastcall **)(HMEHelpers *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    Instance = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 121, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids, (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000653c  mov     [rsp+arg_0], rbx
0x180006541  mov     [rsp+arg_18], rbp
0x180006546  push    rsi
0x180006547  push    rdi
0x180006548  push    r14
0x18000654a  sub     rsp, 30h
0x18000654e  mov     rdi, rdx
0x180006551  mov     rbp, rcx
0x180006554  mov     rcx, cs:WPP_GLOBAL_Control
0x18000655b  lea     r14, WPP_GLOBAL_Control
0x180006562  cmp     rcx, r14
0x180006565  jz      short loc_180006589
0x180006567  test    byte ptr [rcx+1Ch], 20h
0x18000656b  jz      short loc_180006589
0x18000656d  mov     rcx, [rcx+10h]
0x180006571  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006578  mov     edx, 78h ; 'x'
0x18000657d  call    WPP_SF_
0x180006582  mov     rcx, cs:WPP_GLOBAL_Control
0x180006589  test    rdi, rdi
0x18000658c  jz      loc_180006659
0x180006592  lea     rsi, [rbp+48h]
0x180006596  xor     ebx, ebx
0x180006598  mov     rcx, rsi
0x18000659b  call    ??$IUnknown_SafeReleaseAndNullPtr@VCDeviceSettings@@@@YAXAEAPEAVCDeviceSettings@@@Z; IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(CDeviceSettings * &)
0x1800065a0  mov     [rsi], rdi
0x1800065a3  mov     rcx, rdi
0x1800065a6  mov     rax, [rdi]
0x1800065a9  mov     rax, [rax+8]
0x1800065ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065b2  mov     rcx, [rsi]; this
0x1800065b5  call    ?HasDeviceSettings@CDeviceSettings@@QEAAHXZ; CDeviceSettings::HasDeviceSettings(void)
0x1800065ba  test    eax, eax
0x1800065bc  jnz     loc_180006650
0x1800065c2  lea     rax, [rsp+48h+arg_10]
0x1800065c7  mov     [rsp+48h+arg_10], rbx
0x1800065cc  lea     r9, _GUID_2712e1d1_c205_442e_8a24_b1874058fdee; riid
0x1800065d3  mov     [rsp+48h+ppv], rax; ppv
0x1800065d8  xor     edx, edx; pUnkOuter
0x1800065da  lea     r8d, [rbx+1]; dwClsContext
0x1800065de  lea     rcx, _GUID_6bf52a52_394a_11d3_b153_00c04f79faa6; rclsid
0x1800065e5  call    cs:__imp_CoCreateInstance
0x1800065eb  mov     ebx, eax
0x1800065ed  test    eax, eax
0x1800065ef  js      short loc_180006650
0x1800065f1  mov     rcx, [rsi]; this
0x1800065f4  lea     rdx, [rsp+48h+pv]; unsigned __int16 **
0x1800065f9  mov     [rsp+48h+pv], 0
0x180006602  call    ?GetID@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetID(ushort * *)
0x180006607  mov     ebx, eax
0x180006609  test    eax, eax
0x18000660b  js      short loc_18000663F
0x18000660d  mov     rdx, [rsp+48h+pv]; struct IWMPPlayerInternalMarshalled *
0x180006612  lea     r8, [rbp+18h]; unsigned __int16 *
0x180006616  mov     rcx, [rsp+48h+arg_10]; this
0x18000661b  call    ?RetrieveWMPDeviceSettings@HMEHelpers@@YAJPEAUIWMPPlayerInternalMarshalled@@PEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::RetrieveWMPDeviceSettings(IWMPPlayerInternalMarshalled *,ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006620  mov     ebx, eax
0x180006622  test    eax, eax
0x180006624  js      short loc_180006634
0x180006626  mov     rcx, [rsi]; this
0x180006629  lea     rdx, [rbp+18h]; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x18000662d  call    ?SetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; CDeviceSettings::SetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006632  mov     ebx, eax
0x180006634  mov     rcx, [rsp+48h+pv]; pv
0x180006639  call    cs:__imp_CoTaskMemFree
0x18000663f  mov     rcx, [rsp+48h+arg_10]
0x180006644  mov     rax, [rcx]
0x180006647  mov     rax, [rax+10h]
0x18000664b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006650  mov     rcx, cs:WPP_GLOBAL_Control
0x180006657  jmp     short loc_18000665E
0x180006659  mov     ebx, 80004003h
0x18000665e  cmp     rcx, r14
0x180006661  jz      short loc_180006681
0x180006663  test    byte ptr [rcx+1Ch], 20h
0x180006667  jz      short loc_180006681
0x180006669  mov     rcx, [rcx+10h]
0x18000666d  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180006674  mov     edx, 79h ; 'y'
0x180006679  mov     r9d, ebx
0x18000667c  call    WPP_SF_d
0x180006681  mov     rbp, [rsp+48h+arg_18]
0x180006686  mov     eax, ebx
0x180006688  mov     rbx, [rsp+48h+arg_0]
0x18000668d  add     rsp, 30h
0x180006691  pop     r14
0x180006693  pop     rdi
0x180006694  pop     rsi
0x180006695  retn
```
