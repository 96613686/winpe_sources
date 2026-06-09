# _OnSaveReferences(FILEPROPINFO *)

- ea: `0x180050058`
- end: `0x180050597`
- name: `?_OnSaveReferences@@YAXPEAUFILEPROPINFO@@@Z`
- size: `1343`
- prototype: `void __fastcall(struct FILEPROPINFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004af50`

## callees

- `0x180014dd0`
- `0x1800285c8`
- `0x18002ff5c`
- `0x18004fa54`
- `0x180050058`
- `0x1800628cc`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1800503e8`
- `ole32!PropVariantClear` at `0x18005051b`
- `ole32!PropVariantClear` at `0x1800503e8`
- `ole32!PropVariantClear` at `0x18005051b`
- `ole32!CoCreateInstance` at `0x1800500be`
- `ole32!CoCreateInstance` at `0x180050120`
- `ole32!CoCreateInstance` at `0x180050171`
- `ole32!CoCreateInstance` at `0x1800500be`
- `ole32!CoCreateInstance` at `0x180050120`
- `ole32!CoCreateInstance` at `0x180050171`
- `SHELL32!__imp_ILFindLastID` at `0x18005029f`
- `SHELL32!__imp_ILFindLastID` at `0x18005029f`
- `SHELL32!__imp_ILFree` at `0x180050529`
- `SHELL32!__imp_ILFree` at `0x180050529`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall _OnSaveReferences(struct FILEPROPINFO *a1)
{
  ITEMIDLIST *v2; // rsi
  HRESULT v3; // eax
  __int64 v4; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HRESULT v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, LPITEMIDLIST, __int64 *, _QWORD); // rbx
  LPITEMIDLIST ID; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // r8
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int ArrayItemsIntoReferenceCollection; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // [rsp+30h] [rbp-50h] BYREF
  struct IPortableDevicePropVariantCollection *v29; // [rsp+38h] [rbp-48h] BYREF
  __int64 v30; // [rsp+40h] [rbp-40h] BYREF
  __int64 v31; // [rsp+48h] [rbp-38h] BYREF
  __int64 v32; // [rsp+50h] [rbp-30h] BYREF
  __int64 v33; // [rsp+58h] [rbp-28h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-20h] BYREF
  LPVOID v35; // [rsp+B8h] [rbp+38h] BYREF
  LPVOID v36; // [rsp+C0h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+48h] BYREF

  v2 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v32 = 0;
  v28 = 0;
  v31 = 0;
  v30 = 0;
  ppv = 0;
  v33 = 0;
  v29 = 0;
  v36 = 0;
  v35 = 0;
  v3 = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &ppv);
  v4 = (unsigned int)v3;
  if ( v3 >= 0 )
  {
    v7 = CoCreateInstance(
           &CLSID_PortableDevicePropVariantCollection,
           0,
           1u,
           &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
           &v36);
    v4 = (unsigned int)v7;
    if ( v7 >= 0 )
    {
      v8 = CoCreateInstance(
             &CLSID_PortableDevicePropVariantCollection,
             0,
             1u,
             &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
             &v35);
      v4 = (unsigned int)v8;
      if ( v8 >= 0 )
      {
        v9 = IDA_ILClone(*((_QWORD *)a1 + 7), 0);
        v2 = (ITEMIDLIST *)v9;
        if ( v9 )
        {
          v11 = SHBindToIDList(v9, v10, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v32);
          v4 = (unsigned int)v11;
          if ( v11 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD))(*(_QWORD *)v32 + 40LL))(
                    v32,
                    &v28,
                    v12,
                    (unsigned int)v11);
            v4 = (unsigned int)v13;
            if ( v13 >= 0 )
            {
              v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD))(*(_QWORD *)v28 + 32LL))(
                      v28,
                      &v31,
                      v14,
                      (unsigned int)v13);
              v4 = (unsigned int)v15;
              if ( v15 >= 0 )
              {
                v16 = *((_QWORD *)a1 + 1);
                v17 = *(__int64 (__fastcall **)(__int64, LPITEMIDLIST, __int64 *, _QWORD))(*(_QWORD *)v16 + 32LL);
                ID = ILFindLastID(v2);
                v19 = v17(v16, ID, &v30, 0);
                v4 = (unsigned int)v19;
                if ( v19 >= 0 )
                {
                  v20 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *, _QWORD))(*(_QWORD *)v30 + 40LL))(
                          v30,
                          &WPD_OBJECT_PERSISTENT_UNIQUE_ID,
                          &pvar,
                          (unsigned int)v19);
                  v4 = (unsigned int)v20;
                  if ( v20 >= 0 )
                  {
                    if ( pvar.vt != 10 && pvar.vt )
                    {
                      v22 = (*(__int64 (__fastcall **)(LPVOID, PROPVARIANT *, __int64, _QWORD))(*(_QWORD *)v36 + 40LL))(
                              v36,
                              &pvar,
                              v21,
                              (unsigned int)v20);
                      v4 = (unsigned int)v22;
                      if ( v22 >= 0 )
                      {
                        v23 = (*(__int64 (__fastcall **)(__int64, LPVOID, LPVOID *, _QWORD))(*(_QWORD *)v28 + 72LL))(
                                v28,
                                v36,
                                &v35,
                                (unsigned int)v22);
                        v4 = (unsigned int)v23;
                        if ( v23 >= 0 )
                        {
                          PropVariantClear(&pvar);
                          v24 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, PROPVARIANT *))(*(_QWORD *)v35 + 32LL))(
                                  v35,
                                  0,
                                  &pvar);
                          v4 = (unsigned int)v24;
                          if ( v24 >= 0 )
                          {
                            ArrayItemsIntoReferenceCollection = _MakeArrayItemsIntoReferenceCollection(a1, &v29);
                            v4 = (unsigned int)ArrayItemsIntoReferenceCollection;
                            if ( ArrayItemsIntoReferenceCollection >= 0 )
                            {
                              v26 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, struct IPortableDevicePropVariantCollection *, _QWORD))(*(_QWORD *)ppv + 264LL))(
                                      ppv,
                                      &WPD_OBJECT_REFERENCES,
                                      v29,
                                      (unsigned int)ArrayItemsIntoReferenceCollection);
                              v4 = (unsigned int)v26;
                              if ( v26 >= 0 )
                              {
                                v27 = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER, LPVOID, __int64 *))(*(_QWORD *)v31 + 48LL))(
                                        v31,
                                        pvar.hVal,
                                        ppv,
                                        &v33);
                                v4 = (unsigned int)v27;
                                if ( v27 >= 0 )
                                {
                                  ChangeNotify(0x2000, 0x3000u, v2, 0);
                                }
                                else
                                {
                                  v5 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                                  {
                                    v6 = 105;
                                    goto LABEL_5;
                                  }
                                }
                              }
                              else
                              {
                                v5 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                                {
                                  v6 = 104;
                                  goto LABEL_5;
                                }
                              }
                            }
                            else
                            {
                              v5 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                              {
                                v6 = 103;
                                goto LABEL_5;
                              }
                            }
                          }
                          else
                          {
                            v5 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                            {
                              v6 = 102;
                              goto LABEL_5;
                            }
                          }
                        }
                        else
                        {
                          v5 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          {
                            v6 = 101;
                            goto LABEL_5;
                          }
                        }
                      }
                      else
                      {
                        v5 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v6 = 100;
                          goto LABEL_5;
                        }
                      }
                    }
                  }
                  else
                  {
                    v5 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v6 = 99;
                      goto LABEL_5;
                    }
                  }
                }
                else
                {
                  v5 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v6 = 98;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v6 = 97;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v6 = 96;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v6 = 95;
              goto LABEL_5;
            }
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v6 = 94;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v6 = 93;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 92;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids, v4);
    }
  }
  PropVariantClear(&pvar);
  if ( v2 )
    ILFree(v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
}

```

## disassembly

```asm
0x180050058  push    rbp
0x18005005a  push    rbx
0x18005005b  push    rsi
0x18005005c  push    rdi
0x18005005d  push    r14
0x18005005f  mov     rbp, rsp
0x180050062  sub     rsp, 80h
0x180050069  mov     r14, rcx
0x18005006c  xor     esi, esi
0x18005006e  xorps   xmm0, xmm0
0x180050071  xor     eax, eax
0x180050073  movups  xmmword ptr [rbp+pvar], xmm0
0x180050077  mov     qword ptr [rbp+pvar+10h], rax
0x18005007b  mov     [rbp+var_30], rax
0x18005007f  mov     [rbp+var_50], rax
0x180050083  mov     [rbp+var_38], rax
0x180050087  mov     [rbp+var_40], rax
0x18005008b  mov     [rbp+arg_18], rax
0x18005008f  mov     [rbp+var_28], rax
0x180050093  mov     [rbp+var_48], rax
0x180050097  mov     [rbp+arg_10], rax
0x18005009b  mov     [rbp+arg_8], rax
0x18005009f  lea     rax, [rbp+arg_18]
0x1800500a3  mov     [rsp+80h+ppv], rax; ppv
0x1800500a8  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x1800500af  lea     ebx, [rsi+1]
0x1800500b2  mov     r8d, ebx; dwClsContext
0x1800500b5  xor     edx, edx; pUnkOuter
0x1800500b7  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x1800500be  call    cs:__imp_CoCreateInstance
0x1800500c4  mov     r9d, eax
0x1800500c7  test    eax, eax
0x1800500c9  jns     short loc_180050104
0x1800500cb  lea     rax, WPP_GLOBAL_Control
0x1800500d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800500d9  cmp     rcx, rax
0x1800500dc  jz      loc_180050517
0x1800500e2  test    byte ptr [rcx+1Ch], 2
0x1800500e6  jz      loc_180050517
0x1800500ec  lea     edx, [rsi+5Ch]
0x1800500ef  lea     r8, WPP_10acedde41323f2668e6dc1b1f75dfed_Traceguids
0x1800500f6  mov     rcx, [rcx+10h]
0x1800500fa  call    WPP_SF_d
0x1800500ff  jmp     loc_180050517
0x180050104  lea     rax, [rbp+arg_10]
0x180050108  mov     [rsp+80h+ppv], rax; ppv
0x18005010d  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x180050114  mov     r8d, ebx; dwClsContext
0x180050117  xor     edx, edx; pUnkOuter
0x180050119  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x180050120  call    cs:__imp_CoCreateInstance
0x180050126  mov     r9d, eax
0x180050129  test    eax, eax
0x18005012b  jns     short loc_180050155
0x18005012d  lea     rax, WPP_GLOBAL_Control
0x180050134  mov     rcx, cs:WPP_GLOBAL_Control
0x18005013b  cmp     rcx, rax
0x18005013e  jz      loc_180050517
0x180050144  test    byte ptr [rcx+1Ch], 2
0x180050148  jz      loc_180050517
0x18005014e  mov     edx, 5Dh ; ']'
0x180050153  jmp     short loc_1800500EF
0x180050155  lea     rax, [rbp+arg_8]
0x180050159  mov     [rsp+80h+ppv], rax; ppv
0x18005015e  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x180050165  mov     r8d, ebx; dwClsContext
0x180050168  xor     edx, edx; pUnkOuter
0x18005016a  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x180050171  call    cs:__imp_CoCreateInstance
0x180050177  mov     r9d, eax
0x18005017a  test    eax, eax
0x18005017c  jns     short loc_1800501A9
0x18005017e  lea     rax, WPP_GLOBAL_Control
0x180050185  mov     rcx, cs:WPP_GLOBAL_Control
0x18005018c  cmp     rcx, rax
0x18005018f  jz      loc_180050517
0x180050195  test    byte ptr [rcx+1Ch], 2
0x180050199  jz      loc_180050517
0x18005019f  mov     edx, 5Eh ; '^'
0x1800501a4  jmp     loc_1800500EF
0x1800501a9  xor     edx, edx
0x1800501ab  mov     rcx, [r14+38h]
0x1800501af  call    IDA_ILClone
0x1800501b4  mov     rsi, rax
0x1800501b7  test    rax, rax
0x1800501ba  jz      loc_180050517
0x1800501c0  lea     r9, [rbp+var_30]
0x1800501c4  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x1800501cb  mov     rcx, rax
0x1800501ce  call    SHBindToIDList
0x1800501d3  mov     r9d, eax
0x1800501d6  test    eax, eax
0x1800501d8  jns     short loc_180050205
0x1800501da  lea     rax, WPP_GLOBAL_Control
0x1800501e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800501e8  cmp     rcx, rax
0x1800501eb  jz      loc_180050517
0x1800501f1  test    byte ptr [rcx+1Ch], 2
0x1800501f5  jz      loc_180050517
0x1800501fb  mov     edx, 5Fh ; '_'
0x180050200  jmp     loc_1800500EF
0x180050205  mov     rcx, [rbp+var_30]
0x180050209  mov     rax, [rcx]
0x18005020c  lea     rdx, [rbp+var_50]
0x180050210  mov     rax, [rax+28h]
0x180050214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050219  mov     r9d, eax
0x18005021c  test    eax, eax
0x18005021e  jns     short loc_18005024B
0x180050220  lea     rax, WPP_GLOBAL_Control
0x180050227  mov     rcx, cs:WPP_GLOBAL_Control
0x18005022e  cmp     rcx, rax
0x180050231  jz      loc_180050517
0x180050237  test    byte ptr [rcx+1Ch], 2
0x18005023b  jz      loc_180050517
0x180050241  mov     edx, 60h ; '`'
0x180050246  jmp     loc_1800500EF
0x18005024b  mov     rcx, [rbp+var_50]
0x18005024f  mov     rax, [rcx]
0x180050252  lea     rdx, [rbp+var_38]
0x180050256  mov     rax, [rax+20h]
0x18005025a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005025f  mov     r9d, eax
0x180050262  test    eax, eax
0x180050264  jns     short loc_180050291
0x180050266  lea     rax, WPP_GLOBAL_Control
0x18005026d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050274  cmp     rcx, rax
0x180050277  jz      loc_180050517
0x18005027d  test    byte ptr [rcx+1Ch], 2
0x180050281  jz      loc_180050517
0x180050287  mov     edx, 61h ; 'a'
0x18005028c  jmp     loc_1800500EF
0x180050291  mov     rdi, [r14+8]
0x180050295  mov     rax, [rdi]
0x180050298  mov     rbx, [rax+20h]
0x18005029c  mov     rcx, rsi; pidl
0x18005029f  call    cs:__imp_ILFindLastID
0x1800502a5  xor     r9d, r9d
0x1800502a8  lea     r8, [rbp+var_40]
0x1800502ac  mov     rdx, rax
0x1800502af  mov     rcx, rdi
0x1800502b2  mov     rax, rbx
0x1800502b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502ba  mov     r9d, eax
0x1800502bd  test    eax, eax
0x1800502bf  jns     short loc_1800502EC
0x1800502c1  lea     rax, WPP_GLOBAL_Control
0x1800502c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800502cf  cmp     rcx, rax
0x1800502d2  jz      loc_180050517
0x1800502d8  test    byte ptr [rcx+1Ch], 2
0x1800502dc  jz      loc_180050517
0x1800502e2  mov     edx, 62h ; 'b'
0x1800502e7  jmp     loc_1800500EF
0x1800502ec  mov     rcx, [rbp+var_40]
0x1800502f0  mov     rax, [rcx]
0x1800502f3  lea     r8, [rbp+pvar]
0x1800502f7  lea     rdx, WPD_OBJECT_PERSISTENT_UNIQUE_ID
0x1800502fe  mov     rax, [rax+28h]
0x180050302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050307  mov     r9d, eax
0x18005030a  test    eax, eax
0x18005030c  jns     short loc_180050339
0x18005030e  lea     rax, WPP_GLOBAL_Control
0x180050315  mov     rcx, cs:WPP_GLOBAL_Control
0x18005031c  cmp     rcx, rax
0x18005031f  jz      loc_180050517
0x180050325  test    byte ptr [rcx+1Ch], 2
0x180050329  jz      loc_180050517
0x18005032f  mov     edx, 63h ; 'c'
0x180050334  jmp     loc_1800500EF
0x180050339  mov     eax, 0Ah
0x18005033e  cmp     ax, word ptr [rbp+pvar]
0x180050342  jz      loc_180050517
0x180050348  xor     eax, eax
0x18005034a  cmp     ax, word ptr [rbp+pvar]
0x18005034e  jz      loc_180050517
0x180050354  mov     rcx, [rbp+arg_10]
0x180050358  mov     rax, [rcx]
0x18005035b  lea     rdx, [rbp+pvar]
0x18005035f  mov     rax, [rax+28h]
0x180050363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050368  mov     r9d, eax
0x18005036b  test    eax, eax
0x18005036d  jns     short loc_18005039A
0x18005036f  lea     rax, WPP_GLOBAL_Control
0x180050376  mov     rcx, cs:WPP_GLOBAL_Control
0x18005037d  cmp     rcx, rax
0x180050380  jz      loc_180050517
0x180050386  test    byte ptr [rcx+1Ch], 2
0x18005038a  jz      loc_180050517
0x180050390  mov     edx, 64h ; 'd'
0x180050395  jmp     loc_1800500EF
0x18005039a  mov     rcx, [rbp+var_50]
0x18005039e  mov     rax, [rcx]
0x1800503a1  lea     r8, [rbp+arg_8]
0x1800503a5  mov     rdx, [rbp+arg_10]
0x1800503a9  mov     rax, [rax+48h]
0x1800503ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503b2  mov     r9d, eax
0x1800503b5  test    eax, eax
0x1800503b7  jns     short loc_1800503E4
0x1800503b9  lea     rax, WPP_GLOBAL_Control
0x1800503c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503c7  cmp     rcx, rax
0x1800503ca  jz      loc_180050517
0x1800503d0  test    byte ptr [rcx+1Ch], 2
0x1800503d4  jz      loc_180050517
0x1800503da  mov     edx, 65h ; 'e'
0x1800503df  jmp     loc_1800500EF
0x1800503e4  lea     rcx, [rbp+pvar]; pvar
0x1800503e8  call    cs:__imp_PropVariantClear
0x1800503ee  mov     rcx, [rbp+arg_8]
0x1800503f2  mov     rax, [rcx]
0x1800503f5  lea     r8, [rbp+pvar]
0x1800503f9  xor     edx, edx
0x1800503fb  mov     rax, [rax+20h]
0x1800503ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050404  mov     r9d, eax
0x180050407  test    eax, eax
0x180050409  jns     short loc_180050436
0x18005040b  lea     rax, WPP_GLOBAL_Control
0x180050412  mov     rcx, cs:WPP_GLOBAL_Control
0x180050419  cmp     rcx, rax
0x18005041c  jz      loc_180050517
0x180050422  test    byte ptr [rcx+1Ch], 2
0x180050426  jz      loc_180050517
0x18005042c  mov     edx, 66h ; 'f'
0x180050431  jmp     loc_1800500EF
0x180050436  lea     rdx, [rbp+var_48]; struct IPortableDevicePropVariantCollection **
0x18005043a  mov     rcx, r14; struct FILEPROPINFO *
0x18005043d  call    ?_MakeArrayItemsIntoReferenceCollection@@YAJPEAUFILEPROPINFO@@PEAPEAUIPortableDevicePropVariantCollection@@@Z; _MakeArrayItemsIntoReferenceCollection(FILEPROPINFO *,IPortableDevicePropVariantCollection * *)
0x180050442  mov     r9d, eax
0x180050445  test    eax, eax
0x180050447  jns     short loc_180050474
0x180050449  lea     rax, WPP_GLOBAL_Control
0x180050450  mov     rcx, cs:WPP_GLOBAL_Control
0x180050457  cmp     rcx, rax
0x18005045a  jz      loc_180050517
0x180050460  test    byte ptr [rcx+1Ch], 2
0x180050464  jz      loc_180050517
0x18005046a  mov     edx, 67h ; 'g'
0x18005046f  jmp     loc_1800500EF
0x180050474  mov     rcx, [rbp+arg_18]
0x180050478  mov     rax, [rcx]
0x18005047b  mov     r8, [rbp+var_48]
0x18005047f  lea     rdx, WPD_OBJECT_REFERENCES
0x180050486  mov     rax, [rax+108h]
0x18005048d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050492  mov     r9d, eax
0x180050495  test    eax, eax
0x180050497  jns     short loc_1800504BC
0x180050499  lea     rax, WPP_GLOBAL_Control
0x1800504a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504a7  cmp     rcx, rax
0x1800504aa  jz      short loc_180050517
0x1800504ac  test    byte ptr [rcx+1Ch], 2
0x1800504b0  jz      short loc_180050517
0x1800504b2  mov     edx, 68h ; 'h'
0x1800504b7  jmp     loc_1800500EF
0x1800504bc  mov     rcx, [rbp+var_38]
0x1800504c0  mov     rax, [rcx]
0x1800504c3  lea     r9, [rbp+var_28]
0x1800504c7  mov     r8, [rbp+arg_18]
0x1800504cb  mov     rdx, qword ptr [rbp+pvar+8]
0x1800504cf  mov     rax, [rax+30h]
0x1800504d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504d8  mov     r9d, eax
0x1800504db  test    eax, eax
0x1800504dd  jns     short loc_180050502
0x1800504df  lea     rax, WPP_GLOBAL_Control
0x1800504e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504ed  cmp     rcx, rax
0x1800504f0  jz      short loc_180050517
0x1800504f2  test    byte ptr [rcx+1Ch], 2
0x1800504f6  jz      short loc_180050517
0x1800504f8  mov     edx, 69h ; 'i'
0x1800504fd  jmp     loc_1800500EF
0x180050502  xor     r9d, r9d; dwItem2
0x180050505  mov     r8, rsi; dwItem1
0x180050508  mov     edx, 3000h; uFlags
0x18005050d  mov     ecx, 2000h; wEventId
0x180050512  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x180050517  lea     rcx, [rbp+pvar]; pvar
0x18005051b  call    cs:__imp_PropVariantClear
0x180050521  test    rsi, rsi
0x180050524  jz      short loc_180050530
0x180050526  mov     rcx, rsi; pidl
0x180050529  call    cs:__imp_ILFree
0x18005052f  nop
0x180050530  lea     rcx, [rbp+arg_8]
0x180050534  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180050539  nop
0x18005053a  lea     rcx, [rbp+arg_10]
0x18005053e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180050543  nop
0x180050544  lea     rcx, [rbp+var_48]
0x180050548  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005054d  nop
  ... truncated ...
```
