# _ApplyChanges(FILEPROPINFO *)

- ea: `0x18004bee4`
- end: `0x18004c38e`
- name: `?_ApplyChanges@@YAJPEAUFILEPROPINFO@@@Z`
- size: `1194`
- prototype: `__int64 __fastcall(struct FILEPROPINFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ac30`

## callees

- `0x180014dd0`
- `0x18001d6b0`
- `0x1800285c8`
- `0x180029bac`
- `0x18002ff5c`
- `0x18004bee4`
- `0x18005d2a4`
- `0x1800628cc`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18004c282`
- `ole32!PropVariantClear` at `0x18004c30d`
- `ole32!PropVariantClear` at `0x18004c282`
- `ole32!PropVariantClear` at `0x18004c30d`
- `ole32!CoCreateInstance` at `0x18004bf81`
- `ole32!CoCreateInstance` at `0x18004c08a`
- `ole32!CoCreateInstance` at `0x18004bf81`
- `ole32!CoCreateInstance` at `0x18004c08a`
- `SHELL32!__imp_ILRemoveLastID` at `0x18004c2e8`
- `SHELL32!__imp_ILRemoveLastID` at `0x18004c2e8`
- `SHELL32!__imp_ILFree` at `0x18004c303`
- `SHELL32!__imp_ILFree` at `0x18004c303`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _ApplyChanges(struct FILEPROPINFO *a1)
{
  ITEMIDLIST *v2; // r14
  int v3; // ebx
  HRESULT Instance; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int i; // esi
  _DWORD *v8; // rcx
  int v9; // eax
  __int64 Ptr; // rax
  __int64 v11; // rdx
  unsigned int j; // edi
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v17; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h] BYREF
  PROPVARIANT pvar; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v22; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v24; // [rsp+C0h] [rbp+50h] BYREF
  struct IPortableDevicePropVariantCollection *v25; // [rsp+C8h] [rbp+58h] BYREF

  v20 = 0;
  ppv = 0;
  v17 = 0;
  v19 = 0;
  v25 = 0;
  v24 = 0;
  v22 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v2 = (ITEMIDLIST *)IDA_ILClone(*((_QWORD *)a1 + 7), 0);
  if ( v2 )
  {
    Instance = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &ppv);
    v3 = Instance;
    if ( Instance >= 0 )
    {
      v3 = 0;
      for ( i = 0; ; ++i )
      {
        v8 = (_DWORD *)*((_QWORD *)a1 + 77);
        v9 = v8 ? *v8 : 0;
        if ( i >= v9 )
          break;
        Ptr = IsolationAwareDPA_GetPtr(v8, i);
        if ( Ptr && *(_DWORD *)(Ptr + 64) )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 40LL))(ppv, Ptr, Ptr + 24);
          v3 = Instance;
          if ( Instance < 0 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v6 = 36;
              goto LABEL_7;
            }
            goto LABEL_64;
          }
          v3 = 1;
        }
      }
      _ApplyRename(v2, *((HWND *)a1 + 3), 312, (LPCWSTR)a1 + 48, 1, *((struct CContentFolder **)a1 + 2));
      if ( !v3 )
        goto LABEL_64;
      Instance = CoCreateInstance(
                   &CLSID_PortableDevicePropVariantCollection,
                   0,
                   1u,
                   &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
                   (LPVOID *)&v25);
      v3 = Instance;
      if ( Instance >= 0 )
      {
        Instance = SHBindToIDList(v2, v11, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v20);
        v3 = Instance;
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 40LL))(v20, &v17);
          v3 = Instance;
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 32LL))(v17, &v19);
            v3 = Instance;
            if ( Instance >= 0 )
            {
              Instance = CollectPersistentUniqueIDs(*((struct _IDA **)a1 + 7), v25, 0);
              v3 = Instance;
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64, struct IPortableDevicePropVariantCollection *, __int64 *))(*(_QWORD *)v17 + 72LL))(
                             v17,
                             v25,
                             &v24);
                v3 = Instance;
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v22);
                  v3 = Instance;
                  if ( Instance >= 0 )
                  {
                    for ( j = 0; j < v22; ++j )
                    {
                      v23 = 0;
                      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v24 + 32LL))(
                              v24,
                              j,
                              &pvar);
                      v3 = v13;
                      if ( v13 < 0 )
                      {
                        v14 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v15 = 44;
LABEL_61:
                          WPP_SF_d(v14[2], v15, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v13);
                        }
LABEL_62:
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
                        goto LABEL_64;
                      }
                      v13 = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER, LPVOID, __int64 *))(*(_QWORD *)v19 + 48LL))(
                              v19,
                              pvar.hVal,
                              ppv,
                              &v23);
                      v3 = v13;
                      if ( v13 < 0 )
                      {
                        v14 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v15 = 45;
                          goto LABEL_61;
                        }
                        goto LABEL_62;
                      }
                      PropVariantClear(&pvar);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
                    }
                    ILRemoveLastID(v2);
                    ChangeNotify(0x2000, 0, v2, 0);
                  }
                  else
                  {
                    v5 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v6 = 43;
                      goto LABEL_7;
                    }
                  }
                }
                else
                {
                  v5 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v6 = 42;
                    goto LABEL_7;
                  }
                }
              }
              else
              {
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v6 = 41;
                  goto LABEL_7;
                }
              }
            }
            else
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v6 = 40;
                goto LABEL_7;
              }
            }
          }
          else
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v6 = 39;
              goto LABEL_7;
            }
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v6 = 38;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v6 = 37;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v6 = 35;
LABEL_7:
        WPP_SF_d(v5[2], v6, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)Instance);
      }
    }
LABEL_64:
    ILFree(v2);
  }
  else
  {
    v3 = -2147024809;
  }
  PropVariantClear(&pvar);
  if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, (unsigned int)v3);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004bee4  push    rbp
0x18004bee6  push    rbx
0x18004bee7  push    rsi
0x18004bee8  push    rdi
0x18004bee9  push    r12
0x18004beeb  push    r13
0x18004beed  push    r14
0x18004beef  mov     rbp, rsp
0x18004bef2  sub     rsp, 70h
0x18004bef6  mov     rdi, rcx
0x18004bef9  mov     [rbp+var_28], 0
0x18004bf01  mov     [rbp+var_38], 0
0x18004bf09  mov     [rbp+var_40], 0
0x18004bf11  mov     [rbp+var_30], 0
0x18004bf19  mov     [rbp+arg_18], 0
0x18004bf21  mov     [rbp+arg_10], 0
0x18004bf29  mov     [rbp+arg_0], 0
0x18004bf30  xorps   xmm0, xmm0
0x18004bf33  xor     eax, eax
0x18004bf35  movups  xmmword ptr [rbp+pvar], xmm0
0x18004bf39  mov     qword ptr [rbp+pvar+10h], rax
0x18004bf3d  xor     edx, edx
0x18004bf3f  mov     rcx, [rcx+38h]
0x18004bf43  call    IDA_ILClone
0x18004bf48  mov     r14, rax
0x18004bf4b  lea     r13, WPP_GLOBAL_Control
0x18004bf52  mov     r12b, 2
0x18004bf55  test    rax, rax
0x18004bf58  jnz     short loc_18004BF64
0x18004bf5a  mov     ebx, 80070057h
0x18004bf5f  jmp     loc_18004C309
0x18004bf64  lea     rax, [rbp+var_38]
0x18004bf68  mov     [rsp+70h+ppv], rax; ppv
0x18004bf6d  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x18004bf74  xor     edx, edx; pUnkOuter
0x18004bf76  lea     r8d, [rdx+1]; dwClsContext
0x18004bf7a  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x18004bf81  call    cs:__imp_CoCreateInstance
0x18004bf87  mov     ebx, eax
0x18004bf89  test    eax, eax
0x18004bf8b  jns     short loc_18004BFC4
0x18004bf8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bf94  cmp     rcx, r13
0x18004bf97  jz      loc_18004C300
0x18004bf9d  test    [rcx+1Ch], r12b
0x18004bfa1  jz      loc_18004C300
0x18004bfa7  mov     edx, 23h ; '#'
0x18004bfac  mov     r9d, eax
0x18004bfaf  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004bfb6  mov     rcx, [rcx+10h]
0x18004bfba  call    WPP_SF_d
0x18004bfbf  jmp     loc_18004C300
0x18004bfc4  xor     ebx, ebx
0x18004bfc6  xor     esi, esi
0x18004bfc8  mov     rcx, [rdi+268h]
0x18004bfcf  test    rcx, rcx
0x18004bfd2  jz      short loc_18004BFD8
0x18004bfd4  mov     eax, [rcx]
0x18004bfd6  jmp     short loc_18004BFDA
0x18004bfd8  xor     eax, eax
0x18004bfda  cmp     esi, eax
0x18004bfdc  jge     short loc_18004C03E
0x18004bfde  movsxd  rdx, esi
0x18004bfe1  call    IsolationAwareDPA_GetPtr
0x18004bfe6  mov     r9, rax
0x18004bfe9  test    rax, rax
0x18004bfec  jz      short loc_18004C016
0x18004bfee  cmp     dword ptr [rax+40h], 0
0x18004bff2  jz      short loc_18004C016
0x18004bff4  mov     rcx, [rbp+var_38]
0x18004bff8  mov     rdx, [rcx]
0x18004bffb  lea     r8, [rax+18h]
0x18004bfff  mov     rax, [rdx+28h]
0x18004c003  mov     rdx, r9
0x18004c006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c00b  mov     ebx, eax
0x18004c00d  test    eax, eax
0x18004c00f  js      short loc_18004C01A
0x18004c011  mov     ebx, 1
0x18004c016  inc     esi
0x18004c018  jmp     short loc_18004BFC8
0x18004c01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c021  cmp     rcx, r13
0x18004c024  jz      loc_18004C300
0x18004c02a  test    [rcx+1Ch], r12b
0x18004c02e  jz      loc_18004C300
0x18004c034  mov     edx, 24h ; '$'
0x18004c039  jmp     loc_18004BFAC
0x18004c03e  lea     r9, [rdi+60h]; lpString
0x18004c042  mov     rax, [rdi+10h]
0x18004c046  mov     [rsp+70h+var_48], rax; struct CContentFolder *
0x18004c04b  mov     esi, 1
0x18004c050  mov     dword ptr [rsp+70h+ppv], esi; int
0x18004c054  mov     r8d, 138h; nIDDlgItem
0x18004c05a  mov     rdx, [rdi+18h]; HWND
0x18004c05e  mov     rcx, r14; struct _ITEMIDLIST *
0x18004c061  call    ?_ApplyRename@@YAHPEFAU_ITEMIDLIST@@PEAUHWND__@@HPEBGHPEAVCContentFolder@@@Z; _ApplyRename(_ITEMIDLIST *,HWND__ *,int,ushort const *,int,CContentFolder *)
0x18004c066  test    ebx, ebx
0x18004c068  jz      loc_18004C300
0x18004c06e  lea     rax, [rbp+arg_18]
0x18004c072  mov     [rsp+70h+ppv], rax; ppv
0x18004c077  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x18004c07e  mov     r8d, esi; dwClsContext
0x18004c081  xor     edx, edx; pUnkOuter
0x18004c083  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x18004c08a  call    cs:__imp_CoCreateInstance
0x18004c090  mov     ebx, eax
0x18004c092  test    eax, eax
0x18004c094  jns     short loc_18004C0BA
0x18004c096  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c09d  cmp     rcx, r13
0x18004c0a0  jz      loc_18004C300
0x18004c0a6  test    [rcx+1Ch], r12b
0x18004c0aa  jz      loc_18004C300
0x18004c0b0  mov     edx, 25h ; '%'
0x18004c0b5  jmp     loc_18004BFAC
0x18004c0ba  lea     r9, [rbp+var_28]
0x18004c0be  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x18004c0c5  mov     rcx, r14
0x18004c0c8  call    SHBindToIDList
0x18004c0cd  mov     ebx, eax
0x18004c0cf  test    eax, eax
0x18004c0d1  jns     short loc_18004C0F7
0x18004c0d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0da  cmp     rcx, r13
0x18004c0dd  jz      loc_18004C300
0x18004c0e3  test    [rcx+1Ch], r12b
0x18004c0e7  jz      loc_18004C300
0x18004c0ed  mov     edx, 26h ; '&'
0x18004c0f2  jmp     loc_18004BFAC
0x18004c0f7  mov     rcx, [rbp+var_28]
0x18004c0fb  mov     rax, [rcx]
0x18004c0fe  lea     rdx, [rbp+var_40]
0x18004c102  mov     rax, [rax+28h]
0x18004c106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c10b  mov     ebx, eax
0x18004c10d  test    eax, eax
0x18004c10f  jns     short loc_18004C135
0x18004c111  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c118  cmp     rcx, r13
0x18004c11b  jz      loc_18004C300
0x18004c121  test    [rcx+1Ch], r12b
0x18004c125  jz      loc_18004C300
0x18004c12b  mov     edx, 27h ; '''
0x18004c130  jmp     loc_18004BFAC
0x18004c135  mov     rcx, [rbp+var_40]
0x18004c139  mov     rax, [rcx]
0x18004c13c  lea     rdx, [rbp+var_30]
0x18004c140  mov     rax, [rax+20h]
0x18004c144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c149  mov     ebx, eax
0x18004c14b  test    eax, eax
0x18004c14d  jns     short loc_18004C173
0x18004c14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c156  cmp     rcx, r13
0x18004c159  jz      loc_18004C300
0x18004c15f  test    [rcx+1Ch], r12b
0x18004c163  jz      loc_18004C300
0x18004c169  mov     edx, 28h ; '('
0x18004c16e  jmp     loc_18004BFAC
0x18004c173  xor     r8d, r8d; int
0x18004c176  mov     rdx, [rbp+arg_18]; struct IPortableDevicePropVariantCollection *
0x18004c17a  mov     rcx, [rdi+38h]; struct _IDA *
0x18004c17e  call    ?CollectPersistentUniqueIDs@@YAJPEAU_IDA@@PEAUIPortableDevicePropVariantCollection@@H@Z; CollectPersistentUniqueIDs(_IDA *,IPortableDevicePropVariantCollection *,int)
0x18004c183  mov     ebx, eax
0x18004c185  test    eax, eax
0x18004c187  jns     short loc_18004C1AD
0x18004c189  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c190  cmp     rcx, r13
0x18004c193  jz      loc_18004C300
0x18004c199  test    [rcx+1Ch], r12b
0x18004c19d  jz      loc_18004C300
0x18004c1a3  mov     edx, 29h ; ')'
0x18004c1a8  jmp     loc_18004BFAC
0x18004c1ad  mov     rcx, [rbp+var_40]
0x18004c1b1  mov     rax, [rcx]
0x18004c1b4  lea     r8, [rbp+arg_10]
0x18004c1b8  mov     rdx, [rbp+arg_18]
0x18004c1bc  mov     rax, [rax+48h]
0x18004c1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1c5  mov     ebx, eax
0x18004c1c7  test    eax, eax
0x18004c1c9  jns     short loc_18004C1EF
0x18004c1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c1d2  cmp     rcx, r13
0x18004c1d5  jz      loc_18004C300
0x18004c1db  test    [rcx+1Ch], r12b
0x18004c1df  jz      loc_18004C300
0x18004c1e5  mov     edx, 2Ah ; '*'
0x18004c1ea  jmp     loc_18004BFAC
0x18004c1ef  mov     rcx, [rbp+arg_10]
0x18004c1f3  mov     rax, [rcx]
0x18004c1f6  lea     rdx, [rbp+arg_0]
0x18004c1fa  mov     rax, [rax+18h]
0x18004c1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c203  mov     ebx, eax
0x18004c205  test    eax, eax
0x18004c207  jns     short loc_18004C22D
0x18004c209  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c210  cmp     rcx, r13
0x18004c213  jz      loc_18004C300
0x18004c219  test    [rcx+1Ch], r12b
0x18004c21d  jz      loc_18004C300
0x18004c223  mov     edx, 2Bh ; '+'
0x18004c228  jmp     loc_18004BFAC
0x18004c22d  xor     edi, edi
0x18004c22f  cmp     edi, [rbp+arg_0]
0x18004c232  jnb     loc_18004C2E5
0x18004c238  mov     [rbp+arg_8], 0
0x18004c240  mov     rcx, [rbp+arg_10]
0x18004c244  mov     rax, [rcx]
0x18004c247  lea     r8, [rbp+pvar]
0x18004c24b  mov     edx, edi
0x18004c24d  mov     rax, [rax+20h]
0x18004c251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c256  mov     ebx, eax
0x18004c258  test    eax, eax
0x18004c25a  js      short loc_18004C2AF
0x18004c25c  mov     rcx, [rbp+var_30]
0x18004c260  mov     rax, [rcx]
0x18004c263  lea     r9, [rbp+arg_8]
0x18004c267  mov     r8, [rbp+var_38]
0x18004c26b  mov     rdx, qword ptr [rbp+pvar+8]
0x18004c26f  mov     rax, [rax+30h]
0x18004c273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c278  mov     ebx, eax
0x18004c27a  test    eax, eax
0x18004c27c  js      short loc_18004C296
0x18004c27e  lea     rcx, [rbp+pvar]; pvar
0x18004c282  call    cs:__imp_PropVariantClear
0x18004c288  nop
0x18004c289  lea     rcx, [rbp+arg_8]
0x18004c28d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c292  add     edi, esi
0x18004c294  jmp     short loc_18004C22F
0x18004c296  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c29d  cmp     rcx, r13
0x18004c2a0  jz      short loc_18004C2DA
0x18004c2a2  test    [rcx+1Ch], r12b
0x18004c2a6  jz      short loc_18004C2DA
0x18004c2a8  mov     edx, 2Dh ; '-'
0x18004c2ad  jmp     short loc_18004C2C6
0x18004c2af  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c2b6  cmp     rcx, r13
0x18004c2b9  jz      short loc_18004C2DA
0x18004c2bb  test    [rcx+1Ch], r12b
0x18004c2bf  jz      short loc_18004C2DA
0x18004c2c1  mov     edx, 2Ch ; ','
0x18004c2c6  mov     r9d, eax
0x18004c2c9  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004c2d0  mov     rcx, [rcx+10h]
0x18004c2d4  call    WPP_SF_d
0x18004c2d9  nop
0x18004c2da  lea     rcx, [rbp+arg_8]
0x18004c2de  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c2e3  jmp     short loc_18004C300
0x18004c2e5  mov     rcx, r14; pidl
0x18004c2e8  call    cs:__imp_ILRemoveLastID
0x18004c2ee  xor     r9d, r9d; dwItem2
0x18004c2f1  mov     r8, r14; dwItem1
0x18004c2f4  xor     edx, edx; uFlags
0x18004c2f6  mov     ecx, 2000h; wEventId
0x18004c2fb  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18004c300  mov     rcx, r14; pidl
0x18004c303  call    cs:__imp_ILFree
0x18004c309  lea     rcx, [rbp+pvar]; pvar
0x18004c30d  call    cs:__imp_PropVariantClear
0x18004c313  test    ebx, ebx
0x18004c315  jns     short loc_18004C342
0x18004c317  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c31e  cmp     rcx, r13
0x18004c321  jz      short loc_18004C342
0x18004c323  test    [rcx+1Ch], r12b
0x18004c327  jz      short loc_18004C342
0x18004c329  mov     edx, 2Eh ; '.'
0x18004c32e  mov     r9d, ebx
0x18004c331  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x18004c338  mov     rcx, [rcx+10h]
0x18004c33c  call    WPP_SF_d
0x18004c341  nop
0x18004c342  lea     rcx, [rbp+arg_10]
0x18004c346  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c34b  nop
0x18004c34c  lea     rcx, [rbp+arg_18]
0x18004c350  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c355  nop
0x18004c356  lea     rcx, [rbp+var_30]
0x18004c35a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c35f  nop
0x18004c360  lea     rcx, [rbp+var_40]
0x18004c364  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c369  nop
0x18004c36a  lea     rcx, [rbp+var_38]
0x18004c36e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c373  nop
0x18004c374  lea     rcx, [rbp+var_28]
0x18004c378  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c37d  mov     eax, ebx
0x18004c37f  add     rsp, 70h
0x18004c383  pop     r14
  ... truncated ...
```
