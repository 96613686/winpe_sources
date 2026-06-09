# CreateFunctionDiscoveryQueryForWcn(ulong,IFunctionDiscoveryNotification *,IFunctionInstanceCollectionQuery * *)

- ea: `0x18001de30`
- end: `0x18001e23b`
- name: `?CreateFunctionDiscoveryQueryForWcn@@YAJKPEAUIFunctionDiscoveryNotification@@PEAPEAUIFunctionInstanceCollectionQuery@@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(unsigned int, struct IFunctionDiscoveryNotification *, struct IFunctionInstanceCollectionQuery **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019ab0`
- `0x18001be2c`

## callees

- `0x180003abc`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001de30`
- `0x18001e568`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df05`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df05`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateFunctionDiscoveryQueryForWcn(
        int a1,
        struct IFunctionDiscoveryNotification *a2,
        struct IFunctionInstanceCollectionQuery **a3)
{
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  int v9; // ebx
  HRESULT v10; // eax
  _BYTE *v11; // r10
  __int64 v12; // rdx
  unsigned __int64 i; // rdi
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // eax
  __int64 v18; // r10
  __int128 v20; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]
  __int64 v22; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+48h] BYREF

  ppv = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 19, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_s(v6[2], 20, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids, "ppQueryOut");
    v9 = -2147467261;
    goto LABEL_54;
  }
  v10 = CoCreateInstance(&CLSID_FunctionDiscovery, 0, 0x401u, &GUID_4df99b70_e148_4432_b004_4c9eeb535a5e, &ppv);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_54;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_50;
    v12 = 21;
    goto LABEL_48;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD, struct IFunctionDiscoveryNotification *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(
          ppv,
          L"Provider\\Microsoft.Networking.WCN",
          0,
          0,
          a2,
          0,
          &v22);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_54;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_50;
    v12 = 22;
    goto LABEL_48;
  }
  for ( i = 0; i < 5; ++i )
  {
    if ( (a1 & qword_1800347B0[2 * i]) != 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v22 + 24LL))(
              v22,
              qword_1800347B0[2 * i + 1],
              L"TRUE");
      v9 = v14;
      if ( v14 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_54;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, qword_1800347B0[2 * i + 1], v14);
          goto LABEL_49;
        }
        goto LABEL_50;
      }
    }
  }
  if ( (a1 & 0x100) != 0 )
  {
    LOWORD(v20) = 18;
    DWORD2(v20) = 2;
    v10 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *, _QWORD))(*(_QWORD *)v22 + 32LL))(
            v22,
            &PKEY_WCN_ConfigState,
            &v20,
            0);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_54;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 24;
        goto LABEL_48;
      }
      goto LABEL_50;
    }
  }
  if ( (a1 & 0x200) != 0 )
  {
    LOWORD(v20) = 18;
    DWORD2(v20) = 1;
    v10 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *, _QWORD))(*(_QWORD *)v22 + 32LL))(
            v22,
            &PKEY_WCN_ConfigState,
            &v20,
            0);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_54;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 25;
        goto LABEL_48;
      }
LABEL_50:
      if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v9 < 0 || v11[25] >= 6u) )
      {
        v17 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v18 + 16), 29, (unsigned int)WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids, v17, v9);
      }
      goto LABEL_54;
    }
  }
  if ( (a1 & 0x800) != 0 )
  {
    LOWORD(v20) = 23;
    DWORD2(v20) = 6;
    v10 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *, _QWORD))(*(_QWORD *)v22 + 32LL))(
            v22,
            &PKEY_WCN_DeviceType_Category,
            &v20,
            0);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_54;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 26;
        goto LABEL_48;
      }
      goto LABEL_50;
    }
  }
  if ( (a1 & 0x400) != 0 )
  {
    LOWORD(v20) = 23;
    DWORD2(v20) = 6;
    v10 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *, __int64))(*(_QWORD *)v22 + 32LL))(
            v22,
            &PKEY_WCN_DeviceType_Category,
            &v20,
            1);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_54;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 27;
        goto LABEL_48;
      }
      goto LABEL_50;
    }
  }
  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IFunctionInstanceCollectionQuery **))v22)(
          v22,
          &GUID_57cc6fd2_c09a_4289_bb72_25f04142058e,
          a3);
  v9 = v10;
  if ( v10 >= 0 )
    goto LABEL_49;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_50;
    v12 = 28;
LABEL_48:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids, (unsigned int)v10);
LABEL_49:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_50;
  }
LABEL_54:
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&v22);
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001de30  mov     [rsp-28h+arg_0], rbx
0x18001de35  mov     [rsp-28h+arg_8], rsi
0x18001de3a  push    rbp
0x18001de3b  push    rdi
0x18001de3c  push    r12
0x18001de3e  push    r14
0x18001de40  push    r15
0x18001de42  mov     rbp, rsp
0x18001de45  sub     rsp, 60h
0x18001de49  mov     r15, r8
0x18001de4c  mov     rdi, rdx
0x18001de4f  mov     r14d, ecx
0x18001de52  mov     [rbp+arg_18], 0
0x18001de5a  mov     [rbp+arg_10], 0
0x18001de62  xorps   xmm0, xmm0
0x18001de65  xor     eax, eax
0x18001de67  movups  [rbp+var_20], xmm0
0x18001de6b  mov     [rbp+var_10], rax
0x18001de6f  lea     r12, WPP_GLOBAL_Control
0x18001de76  mov     r10, cs:WPP_GLOBAL_Control
0x18001de7d  cmp     r10, r12
0x18001de80  jz      short loc_18001DEB0
0x18001de82  cmp     byte ptr [r10+19h], 6
0x18001de87  jb      short loc_18001DEB0
0x18001de89  lea     ecx, [rax+1]; int
0x18001de8c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001de91  mov     edx, 13h
0x18001de96  mov     r9, rax
0x18001de99  lea     r8, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids
0x18001dea0  mov     rcx, [r10+10h]
0x18001dea4  call    WPP_SF_s
0x18001dea9  mov     r10, cs:WPP_GLOBAL_Control
0x18001deb0  test    r15, r15
0x18001deb3  jnz     short loc_18001DEE6
0x18001deb5  cmp     r10, r12
0x18001deb8  jz      short loc_18001DEDC
0x18001deba  cmp     byte ptr [r10+19h], 2
0x18001debf  jb      short loc_18001DEDC
0x18001dec1  lea     edx, [r15+14h]
0x18001dec5  lea     r9, aPpqueryout; "ppQueryOut"
0x18001decc  lea     r8, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids
0x18001ded3  mov     rcx, [r10+10h]
0x18001ded7  call    WPP_SF_s
0x18001dedc  mov     ebx, 80004003h
0x18001dee1  jmp     loc_18001E20D
0x18001dee6  lea     rax, [rbp+arg_18]
0x18001deea  mov     [rsp+60h+ppv], rax; ppv
0x18001deef  lea     r9, _GUID_4df99b70_e148_4432_b004_4c9eeb535a5e; riid
0x18001def6  xor     edx, edx; pUnkOuter
0x18001def8  mov     r8d, 401h; dwClsContext
0x18001defe  lea     rcx, CLSID_FunctionDiscovery; rclsid
0x18001df05  call    cs:__imp_CoCreateInstance
0x18001df0b  mov     ebx, eax
0x18001df0d  test    eax, eax
0x18001df0f  jns     short loc_18001DF36
0x18001df11  mov     r10, cs:WPP_GLOBAL_Control
0x18001df18  cmp     r10, r12
0x18001df1b  jz      loc_18001E20D
0x18001df21  cmp     byte ptr [r10+19h], 2
0x18001df26  jb      loc_18001E1D8
0x18001df2c  mov     edx, 15h
0x18001df31  jmp     loc_18001E1BE
0x18001df36  mov     rcx, [rbp+arg_18]
0x18001df3a  mov     rax, [rcx]
0x18001df3d  lea     rdx, [rbp+arg_10]
0x18001df41  mov     [rsp+60h+var_30], rdx
0x18001df46  mov     [rsp+60h+var_38], 0
0x18001df4f  mov     [rsp+60h+ppv], rdi
0x18001df54  xor     r9d, r9d
0x18001df57  xor     r8d, r8d
0x18001df5a  lea     rdx, aProviderMicros_0; "Provider\\Microsoft.Networking.WCN"
0x18001df61  mov     rax, [rax+28h]
0x18001df65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df6a  mov     ebx, eax
0x18001df6c  test    eax, eax
0x18001df6e  jns     short loc_18001DF95
0x18001df70  mov     r10, cs:WPP_GLOBAL_Control
0x18001df77  cmp     r10, r12
0x18001df7a  jz      loc_18001E20D
0x18001df80  cmp     byte ptr [r10+19h], 2
0x18001df85  jb      loc_18001E1D8
0x18001df8b  mov     edx, 16h
0x18001df90  jmp     loc_18001E1BE
0x18001df95  xor     edi, edi
0x18001df97  lea     rdx, qword_1800347B0
0x18001df9e  mov     rsi, rdi
0x18001dfa1  add     rsi, rsi
0x18001dfa4  test    [rdx+rsi*8], r14d
0x18001dfa8  jz      short loc_18001DFD3
0x18001dfaa  mov     rcx, [rbp+arg_10]
0x18001dfae  mov     rax, [rcx]
0x18001dfb1  lea     r8, aTrue; "TRUE"
0x18001dfb8  mov     rdx, [rdx+rsi*8+8]
0x18001dfbd  mov     rax, [rax+18h]
0x18001dfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfc6  mov     ebx, eax
0x18001dfc8  test    eax, eax
0x18001dfca  js      short loc_18001E03E
0x18001dfcc  lea     rdx, qword_1800347B0
0x18001dfd3  inc     rdi
0x18001dfd6  cmp     rdi, 5
0x18001dfda  jb      short loc_18001DF9E
0x18001dfdc  mov     edi, 12h
0x18001dfe1  bt      r14d, 8
0x18001dfe6  jnb     loc_18001E077
0x18001dfec  mov     word ptr [rbp+var_20], di
0x18001dff0  mov     dword ptr [rbp+var_20+8], 2
0x18001dff7  mov     rcx, [rbp+arg_10]
0x18001dffb  mov     rax, [rcx]
0x18001dffe  xor     r9d, r9d
0x18001e001  lea     r8, [rbp+var_20]
0x18001e005  lea     rdx, PKEY_WCN_ConfigState
0x18001e00c  mov     rax, [rax+20h]
0x18001e010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e015  mov     ebx, eax
0x18001e017  test    eax, eax
0x18001e019  jns     short loc_18001E077
0x18001e01b  mov     r10, cs:WPP_GLOBAL_Control
0x18001e022  cmp     r10, r12
0x18001e025  jz      loc_18001E20D
0x18001e02b  cmp     byte ptr [r10+19h], 2
0x18001e030  jb      loc_18001E1D8
0x18001e036  lea     edx, [rdi+6]
0x18001e039  jmp     loc_18001E1BE
0x18001e03e  mov     r10, cs:WPP_GLOBAL_Control
0x18001e045  cmp     r10, r12
0x18001e048  jz      loc_18001E20D
0x18001e04e  cmp     byte ptr [r10+19h], 2
0x18001e053  jb      loc_18001E1D8
0x18001e059  mov     dword ptr [rsp+60h+ppv], eax
0x18001e05d  lea     r9, qword_1800347B0
0x18001e064  mov     r9, [r9+rsi*8+8]
0x18001e069  mov     rcx, [r10+10h]
0x18001e06d  call    WPP_SF_Sd
0x18001e072  jmp     loc_18001E1D1
0x18001e077  bt      r14d, 9
0x18001e07c  jnb     short loc_18001E0D2
0x18001e07e  mov     word ptr [rbp+var_20], di
0x18001e082  mov     dword ptr [rbp+var_20+8], 1
0x18001e089  mov     rcx, [rbp+arg_10]
0x18001e08d  mov     rax, [rcx]
0x18001e090  xor     r9d, r9d
0x18001e093  lea     r8, [rbp+var_20]
0x18001e097  lea     rdx, PKEY_WCN_ConfigState
0x18001e09e  mov     rax, [rax+20h]
0x18001e0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0a7  mov     ebx, eax
0x18001e0a9  test    eax, eax
0x18001e0ab  jns     short loc_18001E0D2
0x18001e0ad  mov     r10, cs:WPP_GLOBAL_Control
0x18001e0b4  cmp     r10, r12
0x18001e0b7  jz      loc_18001E20D
0x18001e0bd  cmp     byte ptr [r10+19h], 2
0x18001e0c2  jb      loc_18001E1D8
0x18001e0c8  mov     edx, 19h
0x18001e0cd  jmp     loc_18001E1BE
0x18001e0d2  mov     edi, 17h
0x18001e0d7  bt      r14d, 0Bh
0x18001e0dc  jnb     short loc_18001E130
0x18001e0de  mov     word ptr [rbp+var_20], di
0x18001e0e2  mov     dword ptr [rbp+var_20+8], 6
0x18001e0e9  mov     rcx, [rbp+arg_10]
0x18001e0ed  mov     rax, [rcx]
0x18001e0f0  xor     r9d, r9d
0x18001e0f3  lea     r8, [rbp+var_20]
0x18001e0f7  lea     rdx, PKEY_WCN_DeviceType_Category
0x18001e0fe  mov     rax, [rax+20h]
0x18001e102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e107  mov     ebx, eax
0x18001e109  test    eax, eax
0x18001e10b  jns     short loc_18001E130
0x18001e10d  mov     r10, cs:WPP_GLOBAL_Control
0x18001e114  cmp     r10, r12
0x18001e117  jz      loc_18001E20D
0x18001e11d  cmp     byte ptr [r10+19h], 2
0x18001e122  jb      loc_18001E1D8
0x18001e128  lea     edx, [rdi+3]
0x18001e12b  jmp     loc_18001E1BE
0x18001e130  bt      r14d, 0Ah
0x18001e135  jnb     short loc_18001E187
0x18001e137  mov     word ptr [rbp+var_20], di
0x18001e13b  mov     dword ptr [rbp+var_20+8], 6
0x18001e142  mov     rcx, [rbp+arg_10]
0x18001e146  mov     rax, [rcx]
0x18001e149  mov     r9d, 1
0x18001e14f  lea     r8, [rbp+var_20]
0x18001e153  lea     rdx, PKEY_WCN_DeviceType_Category
0x18001e15a  mov     rax, [rax+20h]
0x18001e15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e163  mov     ebx, eax
0x18001e165  test    eax, eax
0x18001e167  jns     short loc_18001E187
0x18001e169  mov     r10, cs:WPP_GLOBAL_Control
0x18001e170  cmp     r10, r12
0x18001e173  jz      loc_18001E20D
0x18001e179  cmp     byte ptr [r10+19h], 2
0x18001e17e  jb      short loc_18001E1D8
0x18001e180  mov     edx, 1Bh
0x18001e185  jmp     short loc_18001E1BE
0x18001e187  mov     rcx, [rbp+arg_10]
0x18001e18b  mov     rax, [rcx]
0x18001e18e  mov     r8, r15
0x18001e191  lea     rdx, _GUID_57cc6fd2_c09a_4289_bb72_25f04142058e
0x18001e198  mov     rax, [rax]
0x18001e19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a0  mov     ebx, eax
0x18001e1a2  test    eax, eax
0x18001e1a4  jns     short loc_18001E1D1
0x18001e1a6  mov     r10, cs:WPP_GLOBAL_Control
0x18001e1ad  cmp     r10, r12
0x18001e1b0  jz      short loc_18001E20D
0x18001e1b2  cmp     byte ptr [r10+19h], 2
0x18001e1b7  jb      short loc_18001E1D8
0x18001e1b9  mov     edx, 1Ch
0x18001e1be  mov     r9d, eax
0x18001e1c1  lea     r8, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids
0x18001e1c8  mov     rcx, [r10+10h]
0x18001e1cc  call    WPP_SF_d
0x18001e1d1  mov     r10, cs:WPP_GLOBAL_Control
0x18001e1d8  cmp     r10, r12
0x18001e1db  jz      short loc_18001E20D
0x18001e1dd  test    ebx, ebx
0x18001e1df  js      short loc_18001E1E8
0x18001e1e1  cmp     byte ptr [r10+19h], 6
0x18001e1e6  jb      short loc_18001E20D
0x18001e1e8  or      ecx, 0FFFFFFFFh; int
0x18001e1eb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001e1f0  mov     edx, 1Dh
0x18001e1f5  mov     dword ptr [rsp+60h+ppv], ebx
0x18001e1f9  mov     r9, rax
0x18001e1fc  lea     r8, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids
0x18001e203  mov     rcx, [r10+10h]
0x18001e207  call    WPP_SF_sd
0x18001e20c  nop
0x18001e20d  lea     rcx, [rbp+arg_10]
0x18001e211  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x18001e216  nop
0x18001e217  lea     rcx, [rbp+arg_18]
0x18001e21b  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x18001e220  mov     eax, ebx
0x18001e222  lea     r11, [rsp+60h+var_s0]
0x18001e227  mov     rbx, [r11+30h]
0x18001e22b  mov     rsi, [r11+38h]
0x18001e22f  mov     rsp, r11
0x18001e232  pop     r15
0x18001e234  pop     r14
0x18001e236  pop     r12
0x18001e238  pop     rdi
0x18001e239  pop     rbp
0x18001e23a  retn
```
