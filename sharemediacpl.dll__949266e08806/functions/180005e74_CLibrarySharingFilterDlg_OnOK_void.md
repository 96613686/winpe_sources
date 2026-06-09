# CLibrarySharingFilterDlg::OnOK(void)

- ea: `0x180005e74`
- end: `0x1800060eb`
- name: `?OnOK@CLibrarySharingFilterDlg@@IEAA_JXZ`
- size: `631`
- prototype: `__int64 __fastcall(CLibrarySharingFilterDlg *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000586c`
- `0x180005d90`

## callees

- `0x180003860`
- `0x180004c40`
- `0x180005e74`
- `0x180006bfc`
- `0x180016da8`
- `0x180016e60`
- `0x18001e010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180006069`
- `KERNEL32!Sleep` at `0x180006069`
- `ole32!CoCreateInstance` at `0x180005fe6`
- `ole32!CoCreateInstance` at `0x180005fe6`
- `ole32!CoTaskMemFree` at `0x18000609a`
- `ole32!CoTaskMemFree` at `0x18000609a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000602c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000602c`
- `OLEAUT32!__imp_SysFreeString` at `0x180006077`
- `OLEAUT32!__imp_SysFreeString` at `0x180006077`
- `OLEAUT32!__imp_SysStringLen` at `0x180006038`
- `OLEAUT32!__imp_SysStringLen` at `0x180006038`
- `USER32!SendDlgItemMessageW` at `0x180005ed0`
- `USER32!SendDlgItemMessageW` at `0x180005ef8`
- `USER32!SendDlgItemMessageW` at `0x180005f20`
- `USER32!SendDlgItemMessageW` at `0x180005f49`
- `USER32!SendDlgItemMessageW` at `0x180005ed0`
- `USER32!SendDlgItemMessageW` at `0x180005ef8`
- `USER32!SendDlgItemMessageW` at `0x180005f20`
- `USER32!SendDlgItemMessageW` at `0x180005f49`
- `USER32!SendMessageW` at `0x180005f90`
- `USER32!SendMessageW` at `0x180005f90`
- `USER32!GetDlgItem` at `0x180005f67`
- `USER32!GetDlgItem` at `0x180005f67`

## pseudocode

```c
__int64 __fastcall CLibrarySharingFilterDlg::OnOK(CLibrarySharingFilterDlg *this)
{
  int v2; // eax
  HWND DlgItem; // rbp
  int i; // esi
  unsigned int v5; // eax
  __int64 v6; // rbx
  unsigned __int16 *v7; // rsi
  CDeviceSettings *v8; // rcx
  LPVOID v9; // r14
  OLECHAR *v10; // rbx
  int j; // edi
  int v12; // ebp
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v13; // r8
  OLECHAR *psz; // [rsp+60h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  *((_DWORD *)this + 8) = SendDlgItemMessageW(*((HWND *)this + 1), 307, 0xF0u, 0, 0) == 1;
  *((_DWORD *)this + 10) = SendDlgItemMessageW(*((HWND *)this + 1), 310, 0xF0u, 0, 0) == 1;
  *((_DWORD *)this + 11) = SendDlgItemMessageW(*((HWND *)this + 1), 311, 0xF0u, 0, 0) == 1;
  v2 = SendDlgItemMessageW(*((HWND *)this + 1), 309, 0x147u, 0, 0);
  if ( v2 != -1 )
    *((_DWORD *)this + 9) = 5 - v2;
  DlgItem = GetDlgItem(*((HWND *)this + 1), 313);
  if ( DlgItem )
  {
    for ( i = 0; i < *((_DWORD *)this + 12); *(_DWORD *)(v6 + *((_QWORD *)this + 7) + 24) = (v5 >> 12) - 1 )
    {
      v5 = SendMessageW(DlgItem, 0x102Cu, i, 61440);
      v6 = 32LL * i++;
    }
  }
  v7 = (unsigned __int16 *)((char *)this + 24);
  CDeviceSettings::SetWMPDeviceSettings(
    *((CDeviceSettings **)this + 2),
    (CLibrarySharingFilterDlg *)((char *)this + 24));
  ppv = 0;
  if ( CoCreateInstance(
         &GUID_6bf52a52_394a_11d3_b153_00c04f79faa6,
         0,
         1u,
         &GUID_2712e1d1_c205_442e_8a24_b1874058fdee,
         &ppv) >= 0 )
  {
    v8 = (CDeviceSettings *)*((_QWORD *)this + 2);
    psz = 0;
    if ( CDeviceSettings::GetID(v8, &psz) >= 0 )
    {
      v9 = ppv;
      if ( ppv )
      {
        if ( psz )
        {
          if ( this != (CLibrarySharingFilterDlg *)-24LL )
          {
            v10 = SysAllocString(psz);
            if ( SysStringLen(v10) )
            {
              for ( j = 0; j < 5; ++j )
              {
                v12 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, unsigned __int16 *))(*(_QWORD *)v9 + 40LL))(
                        v9,
                        v10,
                        v7);
                if ( v12 != -2147023659 )
                  break;
                Sleep(0x64u);
              }
              SysFreeString(v10);
              if ( v12 >= 0 )
              {
                if ( (unsigned __int8)ShouldUseIndexer2() )
                  HMEHelpers::StoreDevicePolicyToRegistry(v10, v7, v13);
              }
            }
          }
        }
      }
      CoTaskMemFree(psz);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180005e74  mov     [rsp+arg_10], rbx
0x180005e79  push    rbp
0x180005e7a  push    rsi
0x180005e7b  push    rdi
0x180005e7c  push    r12
0x180005e7e  push    r14
0x180005e80  sub     rsp, 30h
0x180005e84  mov     rdi, rcx
0x180005e87  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e8e  lea     r12, WPP_GLOBAL_Control
0x180005e95  cmp     rcx, r12
0x180005e98  jz      short loc_180005EB5
0x180005e9a  test    byte ptr [rcx+1Ch], 20h
0x180005e9e  jz      short loc_180005EB5
0x180005ea0  mov     rcx, [rcx+10h]
0x180005ea4  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005eab  mov     edx, 46h ; 'F'
0x180005eb0  call    WPP_SF_
0x180005eb5  mov     rcx, [rdi+8]; hDlg
0x180005eb9  mov     ebx, 0F0h
0x180005ebe  xor     r9d, r9d; wParam
0x180005ec1  mov     [rsp+58h+lParam], 0; lParam
0x180005eca  mov     r8d, ebx; Msg
0x180005ecd  lea     edx, [rbx+43h]; nIDDlgItem
0x180005ed0  call    cs:__imp_SendDlgItemMessageW
0x180005ed6  xor     ecx, ecx
0x180005ed8  mov     [rsp+58h+lParam], 0; lParam
0x180005ee1  cmp     rax, 1
0x180005ee5  lea     edx, [rbx+46h]; nIDDlgItem
0x180005ee8  mov     r8d, ebx; Msg
0x180005eeb  setz    cl
0x180005eee  xor     r9d, r9d; wParam
0x180005ef1  mov     [rdi+20h], ecx
0x180005ef4  mov     rcx, [rdi+8]; hDlg
0x180005ef8  call    cs:__imp_SendDlgItemMessageW
0x180005efe  xor     ecx, ecx
0x180005f00  mov     [rsp+58h+lParam], 0; lParam
0x180005f09  cmp     rax, 1
0x180005f0d  lea     edx, [rbx+47h]; nIDDlgItem
0x180005f10  mov     r8d, ebx; Msg
0x180005f13  setz    cl
0x180005f16  xor     r9d, r9d; wParam
0x180005f19  mov     [rdi+28h], ecx
0x180005f1c  mov     rcx, [rdi+8]; hDlg
0x180005f20  call    cs:__imp_SendDlgItemMessageW
0x180005f26  xor     ecx, ecx
0x180005f28  mov     [rsp+58h+lParam], 0; lParam
0x180005f31  cmp     rax, 1
0x180005f35  lea     edx, [rbx+45h]; nIDDlgItem
0x180005f38  lea     r8d, [rbx+57h]; Msg
0x180005f3c  setz    cl
0x180005f3f  xor     r9d, r9d; wParam
0x180005f42  mov     [rdi+2Ch], ecx
0x180005f45  mov     rcx, [rdi+8]; hDlg
0x180005f49  call    cs:__imp_SendDlgItemMessageW
0x180005f4f  cmp     eax, 0FFFFFFFFh
0x180005f52  jz      short loc_180005F5E
0x180005f54  mov     ecx, 5
0x180005f59  sub     ecx, eax
0x180005f5b  mov     [rdi+24h], ecx
0x180005f5e  mov     rcx, [rdi+8]; hDlg
0x180005f62  mov     edx, 139h; nIDDlgItem
0x180005f67  call    cs:__imp_GetDlgItem
0x180005f6d  mov     rbp, rax
0x180005f70  test    rax, rax
0x180005f73  jz      short loc_180005FAF
0x180005f75  xor     esi, esi
0x180005f77  cmp     [rdi+30h], esi
0x180005f7a  jle     short loc_180005FAF
0x180005f7c  movsxd  rbx, esi
0x180005f7f  mov     r9d, 0F000h; lParam
0x180005f85  mov     r8, rbx; wParam
0x180005f88  mov     edx, 102Ch; Msg
0x180005f8d  mov     rcx, rbp; hWnd
0x180005f90  call    cs:__imp_SendMessageW
0x180005f96  shl     rbx, 5
0x180005f9a  inc     esi
0x180005f9c  shr     eax, 0Ch
0x180005f9f  lea     ecx, [rax-1]
0x180005fa2  mov     rax, [rdi+38h]
0x180005fa6  mov     [rbx+rax+18h], ecx
0x180005faa  cmp     esi, [rdi+30h]
0x180005fad  jl      short loc_180005F7C
0x180005faf  mov     rcx, [rdi+10h]; this
0x180005fb3  lea     rsi, [rdi+18h]
0x180005fb7  mov     rdx, rsi; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180005fba  call    ?SetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; CDeviceSettings::SetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180005fbf  xor     edx, edx; pUnkOuter
0x180005fc1  mov     [rsp+58h+ppv], 0
0x180005fca  lea     rax, [rsp+58h+ppv]
0x180005fcf  lea     r9, _GUID_2712e1d1_c205_442e_8a24_b1874058fdee; riid
0x180005fd6  mov     [rsp+58h+lParam], rax; ppv
0x180005fdb  lea     rcx, _GUID_6bf52a52_394a_11d3_b153_00c04f79faa6; rclsid
0x180005fe2  lea     r8d, [rdx+1]; dwClsContext
0x180005fe6  call    cs:__imp_CoCreateInstance
0x180005fec  test    eax, eax
0x180005fee  js      loc_1800060B1
0x180005ff4  mov     rcx, [rdi+10h]; this
0x180005ff8  lea     rdx, [rsp+58h+psz]; unsigned __int16 **
0x180005ffd  mov     [rsp+58h+psz], 0
0x180006006  call    ?GetID@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetID(ushort * *)
0x18000600b  test    eax, eax
0x18000600d  js      loc_1800060A0
0x180006013  mov     r14, [rsp+58h+ppv]
0x180006018  test    r14, r14
0x18000601b  jz      short loc_180006095
0x18000601d  mov     rcx, [rsp+58h+psz]; psz
0x180006022  test    rcx, rcx
0x180006025  jz      short loc_180006095
0x180006027  test    rsi, rsi
0x18000602a  jz      short loc_180006095
0x18000602c  call    cs:__imp_SysAllocString
0x180006032  mov     rcx, rax; pbstr
0x180006035  mov     rbx, rax
0x180006038  call    cs:__imp_SysStringLen
0x18000603e  test    eax, eax
0x180006040  jz      short loc_180006095
0x180006042  xor     edi, edi
0x180006044  mov     rcx, [r14]
0x180006047  mov     r8, rsi
0x18000604a  mov     rdx, rbx
0x18000604d  mov     rax, [rcx+28h]
0x180006051  mov     rcx, r14
0x180006054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006059  mov     ebp, eax
0x18000605b  cmp     eax, 800704D5h
0x180006060  jnz     short loc_180006074
0x180006062  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180006067  inc     edi
0x180006069  call    cs:__imp_Sleep
0x18000606f  cmp     edi, 5
0x180006072  jl      short loc_180006044
0x180006074  mov     rcx, rbx; bstrString
0x180006077  call    cs:__imp_SysFreeString
0x18000607d  test    ebp, ebp
0x18000607f  js      short loc_180006095
0x180006081  call    ShouldUseIndexer2
0x180006086  test    al, al
0x180006088  jz      short loc_180006095
0x18000608a  mov     rdx, rsi; unsigned __int16 *
0x18000608d  mov     rcx, rbx; this
0x180006090  call    ?StoreDevicePolicyToRegistry@HMEHelpers@@YAJPEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::StoreDevicePolicyToRegistry(ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180006095  mov     rcx, [rsp+58h+psz]; pv
0x18000609a  call    cs:__imp_CoTaskMemFree
0x1800060a0  mov     rcx, [rsp+58h+ppv]
0x1800060a5  mov     rax, [rcx]
0x1800060a8  mov     rax, [rax+10h]
0x1800060ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060b8  cmp     rcx, r12
0x1800060bb  jz      short loc_1800060D8
0x1800060bd  test    byte ptr [rcx+1Ch], 20h
0x1800060c1  jz      short loc_1800060D8
0x1800060c3  mov     rcx, [rcx+10h]
0x1800060c7  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800060ce  mov     edx, 47h ; 'G'
0x1800060d3  call    WPP_SF_
0x1800060d8  mov     rbx, [rsp+58h+arg_10]
0x1800060dd  xor     eax, eax
0x1800060df  add     rsp, 30h
0x1800060e3  pop     r14
0x1800060e5  pop     r12
0x1800060e7  pop     rdi
0x1800060e8  pop     rsi
0x1800060e9  pop     rbp
0x1800060ea  retn
```
