# CShareWithList::Notify(EventReason,ushort *,tagVARIANT *)

- ea: `0x18000b380`
- end: `0x18000b5da`
- name: `?Notify@CShareWithList@@UEAAJW4EventReason@@PEAGPEAUtagVARIANT@@@Z`
- size: `602`
- prototype: `int __high(enum EventReason, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000b380`
- `0x180012d4c`
- `0x1800166a0`
- `0x180016d00`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000b470`
- `ole32!CoCreateInstance` at `0x18000b50c`
- `ole32!CoCreateInstance` at `0x18000b470`
- `ole32!CoCreateInstance` at `0x18000b50c`
- `ole32!CoUninitialize` at `0x18000b594`
- `ole32!CoUninitialize` at `0x18000b594`
- `ole32!CoInitializeEx` at `0x18000b436`
- `ole32!CoInitializeEx` at `0x18000b436`

## pseudocode

```c
__int64 __fastcall CShareWithList::Notify(__int64 a1, int a2, struct IWMPPlayerInternalMarshalled *a3)
{
  _QWORD *v6; // rcx
  int v7; // ebx
  int v8; // ebx
  HRESULT v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // rdx
  int WMPDeviceSettings; // esi
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v13; // r9
  unsigned __int16 *v14; // r9
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v15; // rdx
  HMEHelpers *v17; // [rsp+30h] [rbp-48h] BYREF
  __int64 v18; // [rsp+38h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 v20[4]; // [rsp+48h] [rbp-30h] BYREF
  int v21; // [rsp+50h] [rbp-28h]
  int v22; // [rsp+54h] [rbp-24h]
  int v23; // [rsp+58h] [rbp-20h]
  int v24; // [rsp+5Ch] [rbp-1Ch]
  __int64 v25; // [rsp+60h] [rbp-18h]
  __int64 v26; // [rsp+68h] [rbp-10h]

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = a2 - 1001;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( (unsigned int)(v8 - 1) >= 2 )
      {
        v9 = -2147024809;
        goto LABEL_31;
      }
      v10 = 3;
    }
    else
    {
      v10 = 4;
    }
  }
  else
  {
    v10 = 2;
  }
  v9 = 0;
  if ( !*(_DWORD *)(a1 + 116) )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_LS(v6[2], (unsigned int)&WPP_GLOBAL_Control, (_DWORD)a3, v10, (__int64)a3);
    v9 = CoInitializeEx(0, 2u);
    if ( v9 >= 0 )
    {
      ppv = 0;
      v9 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
      if ( v9 >= 0 )
      {
        v11 = *(unsigned int *)(a1 + 64);
        v18 = 0;
        v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64 *))(*(_QWORD *)ppv + 40LL))(
               ppv,
               v11,
               &GUID_595d6e65_732c_4736_853f_db64f5aa1eec,
               &v18);
        if ( v9 >= 0 && !*(_DWORD *)(a1 + 116) )
        {
          v25 = 0;
          WMPDeviceSettings = -2147467259;
          *(_QWORD *)v20 = 1;
          v26 = 0;
          v24 = 1;
          v21 = 1;
          v23 = 1;
          v22 = 1;
          if ( v10 == 2 )
          {
            v17 = 0;
            if ( CoCreateInstance(
                   &GUID_6bf52a52_394a_11d3_b153_00c04f79faa6,
                   0,
                   1u,
                   &GUID_2712e1d1_c205_442e_8a24_b1874058fdee,
                   (LPVOID *)&v17) >= 0 )
            {
              WMPDeviceSettings = HMEHelpers::RetrieveWMPDeviceSettings(v17, a3, v20, v13);
              (*(void (__fastcall **)(HMEHelpers *))(*(_QWORD *)v17 + 16LL))(v17);
            }
          }
          if ( WMPDeviceSettings >= 0 && v10 == 2 )
            v14 = v20;
          else
            v14 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWMPPlayerInternalMarshalled *, unsigned __int16 *))(*(_QWORD *)v18 + 24LL))(
                 v18,
                 v10,
                 a3,
                 v14);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          if ( WMPDeviceSettings >= 0 )
            HMEHelpers::CleanupWMPDeviceSettings((HMEHelpers *)v20, v15);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      CoUninitialize();
    }
    v6 = WPP_GLOBAL_Control;
  }
LABEL_31:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_d(v6[2], 158, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b380  push    rbp
0x18000b382  push    rbx
0x18000b383  push    rsi
0x18000b384  push    rdi
0x18000b385  push    r12
0x18000b387  push    r14
0x18000b389  mov     rbp, rsp
0x18000b38c  sub     rsp, 78h
0x18000b390  mov     r14, r8
0x18000b393  mov     ebx, edx
0x18000b395  mov     rsi, rcx
0x18000b398  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b39f  lea     rdx, WPP_GLOBAL_Control
0x18000b3a6  cmp     rcx, rdx
0x18000b3a9  jz      short loc_18000B3D4
0x18000b3ab  test    byte ptr [rcx+1Ch], 20h
0x18000b3af  jz      short loc_18000B3D4
0x18000b3b1  mov     rcx, [rcx+10h]
0x18000b3b5  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b3bc  mov     edx, 9Ch
0x18000b3c1  call    WPP_SF_
0x18000b3c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3cd  lea     rdx, WPP_GLOBAL_Control
0x18000b3d4  sub     ebx, 3E9h
0x18000b3da  jz      short loc_18000B403
0x18000b3dc  sub     ebx, 1
0x18000b3df  jz      short loc_18000B3FC
0x18000b3e1  sub     ebx, 1
0x18000b3e4  jz      short loc_18000B3F5
0x18000b3e6  cmp     ebx, 1
0x18000b3e9  jz      short loc_18000B3F5
0x18000b3eb  mov     ebx, 80070057h
0x18000b3f0  jmp     loc_18000B5A1
0x18000b3f5  mov     edi, 3
0x18000b3fa  jmp     short loc_18000B408
0x18000b3fc  mov     edi, 4
0x18000b401  jmp     short loc_18000B408
0x18000b403  mov     edi, 2
0x18000b408  xor     ebx, ebx
0x18000b40a  cmp     [rsi+74h], ebx
0x18000b40d  jnz     loc_18000B5A1
0x18000b413  cmp     rcx, rdx
0x18000b416  jz      short loc_18000B42F
0x18000b418  test    byte ptr [rcx+1Ch], 8
0x18000b41c  jz      short loc_18000B42F
0x18000b41e  mov     rcx, [rcx+10h]
0x18000b422  mov     r9d, edi
0x18000b425  mov     [rsp+78h+ppv], r14
0x18000b42a  call    WPP_SF_LS
0x18000b42f  mov     edx, 2; dwCoInit
0x18000b434  xor     ecx, ecx; pvReserved
0x18000b436  call    cs:__imp_CoInitializeEx
0x18000b43c  mov     ebx, eax
0x18000b43e  test    eax, eax
0x18000b440  js      loc_18000B59A
0x18000b446  lea     rax, [rbp+var_38]
0x18000b44a  mov     [rbp+var_38], 0
0x18000b452  mov     r12d, 1
0x18000b458  mov     [rsp+78h+ppv], rax; ppv
0x18000b45d  mov     r8d, r12d; dwClsContext
0x18000b460  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000b467  xor     edx, edx; pUnkOuter
0x18000b469  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000b470  call    cs:__imp_CoCreateInstance
0x18000b476  mov     ebx, eax
0x18000b478  test    eax, eax
0x18000b47a  js      loc_18000B594
0x18000b480  mov     rcx, [rbp+var_38]
0x18000b484  lea     r9, [rbp+var_40]
0x18000b488  mov     edx, [rsi+40h]
0x18000b48b  lea     r8, _GUID_595d6e65_732c_4736_853f_db64f5aa1eec
0x18000b492  mov     [rbp+var_40], 0
0x18000b49a  mov     rax, [rcx]
0x18000b49d  mov     rax, [rax+28h]
0x18000b4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4a6  mov     ebx, eax
0x18000b4a8  test    eax, eax
0x18000b4aa  js      loc_18000B584
0x18000b4b0  cmp     dword ptr [rsi+74h], 0
0x18000b4b4  jnz     loc_18000B584
0x18000b4ba  mov     [rbp+var_18], 0
0x18000b4c2  mov     esi, 80004005h
0x18000b4c7  mov     qword ptr [rbp+var_30], r12
0x18000b4cb  mov     [rbp+var_10], 0
0x18000b4d3  mov     [rbp+var_1C], r12d
0x18000b4d7  mov     [rbp+var_28], r12d
0x18000b4db  mov     [rbp+var_20], r12d
0x18000b4df  mov     [rbp+var_24], r12d
0x18000b4e3  cmp     edi, 2
0x18000b4e6  jnz     short loc_18000B538
0x18000b4e8  lea     rax, [rbp+var_48]
0x18000b4ec  mov     [rbp+var_48], 0
0x18000b4f4  lea     r9, _GUID_2712e1d1_c205_442e_8a24_b1874058fdee; riid
0x18000b4fb  mov     [rsp+78h+ppv], rax; ppv
0x18000b500  mov     r8d, r12d; dwClsContext
0x18000b503  lea     rcx, _GUID_6bf52a52_394a_11d3_b153_00c04f79faa6; rclsid
0x18000b50a  xor     edx, edx; pUnkOuter
0x18000b50c  call    cs:__imp_CoCreateInstance
0x18000b512  test    eax, eax
0x18000b514  js      short loc_18000B538
0x18000b516  mov     rcx, [rbp+var_48]; this
0x18000b51a  lea     r8, [rbp+var_30]; unsigned __int16 *
0x18000b51e  mov     rdx, r14; struct IWMPPlayerInternalMarshalled *
0x18000b521  call    ?RetrieveWMPDeviceSettings@HMEHelpers@@YAJPEAUIWMPPlayerInternalMarshalled@@PEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::RetrieveWMPDeviceSettings(IWMPPlayerInternalMarshalled *,ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x18000b526  mov     rcx, [rbp+var_48]
0x18000b52a  mov     esi, eax
0x18000b52c  mov     rdx, [rcx]
0x18000b52f  mov     rax, [rdx+10h]
0x18000b533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b538  mov     rax, [rbp+var_40]
0x18000b53c  mov     rcx, [rax]
0x18000b53f  mov     r10, [rcx+18h]
0x18000b543  test    esi, esi
0x18000b545  js      short loc_18000B552
0x18000b547  cmp     edi, 2
0x18000b54a  jnz     short loc_18000B552
0x18000b54c  lea     r9, [rbp+var_30]
0x18000b550  jmp     short loc_18000B555
0x18000b552  xor     r9d, r9d
0x18000b555  mov     rcx, rax
0x18000b558  mov     r8, r14
0x18000b55b  mov     rax, r10
0x18000b55e  mov     edx, edi
0x18000b560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b565  mov     rcx, [rbp+var_40]
0x18000b569  mov     ebx, eax
0x18000b56b  mov     rax, [rcx]
0x18000b56e  mov     rax, [rax+10h]
0x18000b572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b577  test    esi, esi
0x18000b579  js      short loc_18000B584
0x18000b57b  lea     rcx, [rbp+var_30]; this
0x18000b57f  call    ?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x18000b584  mov     rcx, [rbp+var_38]
0x18000b588  mov     rax, [rcx]
0x18000b58b  mov     rax, [rax+10h]
0x18000b58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b594  call    cs:__imp_CoUninitialize
0x18000b59a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5a1  lea     rax, WPP_GLOBAL_Control
0x18000b5a8  cmp     rcx, rax
0x18000b5ab  jz      short loc_18000B5CB
0x18000b5ad  test    byte ptr [rcx+1Ch], 20h
0x18000b5b1  jz      short loc_18000B5CB
0x18000b5b3  mov     rcx, [rcx+10h]
0x18000b5b7  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000b5be  mov     edx, 9Eh
0x18000b5c3  mov     r9d, ebx
0x18000b5c6  call    WPP_SF_d
0x18000b5cb  mov     eax, ebx
0x18000b5cd  add     rsp, 78h
0x18000b5d1  pop     r14
0x18000b5d3  pop     r12
0x18000b5d5  pop     rdi
0x18000b5d6  pop     rsi
0x18000b5d7  pop     rbx
0x18000b5d8  pop     rbp
0x18000b5d9  retn
```
