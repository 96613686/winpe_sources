# RemoveSyncPartner(IUSStoreManager *,IDBVolume *,_GUID const &)

- ea: `0x180097c04`
- end: `0x180097f3f`
- name: `?RemoveSyncPartner@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@AEBU_GUID@@@Z`
- size: `827`
- prototype: `__int64 __fastcall(struct IUSStoreManager *, struct IDBVolume *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009b310`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180059828`
- `0x180088380`
- `0x180097c04`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097da9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097e55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097da9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097e55`

## string_xrefs

- `0x180097e3c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180097e8e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180097ea6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180097ec5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180097ee3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180097f1d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall RemoveSyncPartner(struct IUSStoreManager *a1, struct IDBVolume *a2, const struct _GUID *a3)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, int *, void **); // rbx
  void **v15; // rax
  int v16; // eax
  HLOCAL v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 v21; // r9
  __int64 v23; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+48h] [rbp-28h] BYREF
  __int64 v25; // [rsp+50h] [rbp-20h] BYREF
  __int64 v26; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-10h] BYREF
  int v28; // [rsp+A0h] [rbp+30h] BYREF
  struct IDBVolume *v29; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+48h] BYREF

  v29 = a2;
  v3 = *(_QWORD *)a1;
  v28 = -2079850431;
  v26 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IUSStoreManager *, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(v3 + 72))(
         a1,
         0,
         0,
         0,
         0,
         &v26);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1132;
    v8 = 1;
    v9 = (unsigned int)v5;
LABEL_42:
    Log_UnistoreHREvent_0(
      v9,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      v7);
    goto LABEL_43;
  }
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 120LL))(v26);
LABEL_4:
  if ( v6 )
  {
    if ( v6 == -2147024871 )
    {
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
      return 0;
    }
    v7 = 1176;
    v8 = 0;
    v9 = v6;
    goto LABEL_42;
  }
  v23 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 40LL))(v26, &v23);
  v6 = v10;
  if ( v10 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      1138);
    goto LABEL_38;
  }
  ATL::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>(
    &v25,
    v23);
  if ( !v25 )
  {
    v6 = -2147467262;
    Log_UnistoreHREvent_0(
      2147500034LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      1141);
    goto LABEL_29;
  }
  v30 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 240LL))(v25, &v30);
  v6 = v11;
  if ( v11 < 0 )
  {
    v21 = 1144;
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30);
    v6 = v11;
    if ( v11 >= 0 )
    {
      while ( 1 )
      {
        v24 = 0;
        LODWORD(v29) = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, struct IDBVolume **))(*(_QWORD *)v30 + 24LL))(
                v30,
                1,
                &v24,
                &v29);
        v6 = v12;
        if ( v12 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v12,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
            1151);
          goto LABEL_27;
        }
        if ( !(_DWORD)v29 )
        {
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
          v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 96LL))(v26);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v30);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v25);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v23);
          goto LABEL_4;
        }
        v13 = v24;
        hMem = 0;
        v14 = *(__int64 (__fastcall **)(__int64, __int64, int *, void **))(*(_QWORD *)v24 + 24LL);
        v15 = tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
        v16 = v14(v13, 1, &v28, v15);
        v6 = v16;
        if ( v16 < 0 )
          break;
        v17 = hMem;
        if ( (*((_WORD *)hMem + 3) & 0x100) != 0 || *((_DWORD *)hMem + 2) != 16 )
          goto LABEL_17;
        v18 = (_QWORD *)*((_QWORD *)hMem + 2);
        v19 = *v18 - *(_QWORD *)&a3->Data1;
        if ( *v18 == *(_QWORD *)&a3->Data1 )
          v19 = v18[1] - *(_QWORD *)a3->Data4;
        if ( v19 )
          goto LABEL_17;
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 200LL))(v24);
        v6 = v16;
        if ( v16 < 0 )
        {
          v20 = 1169;
          goto LABEL_25;
        }
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30);
        v6 = v16;
        if ( v16 < 0 )
        {
          v20 = 1171;
          goto LABEL_25;
        }
        v17 = hMem;
        if ( hMem )
LABEL_17:
          LocalFree(v17);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
      }
      v20 = 1159;
LABEL_25:
      Log_UnistoreHREvent_0(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        v20);
      if ( hMem )
        LocalFree(hMem);
LABEL_27:
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
      goto LABEL_28;
    }
    v21 = 1145;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)v11,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v21);
LABEL_28:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v30);
LABEL_29:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v25);
LABEL_38:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v23);
LABEL_43:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
  return v6;
}

```

## disassembly

```asm
0x180097c04  mov     [rsp-28h+arg_8], rdx
0x180097c09  push    rbp
0x180097c0a  push    rbx
0x180097c0b  push    rsi
0x180097c0c  push    rdi
0x180097c0d  push    r14
0x180097c0f  mov     rbp, rsp
0x180097c12  sub     rsp, 70h
0x180097c16  mov     rax, [rcx]
0x180097c19  lea     rdx, [rbp+var_18]
0x180097c1d  mov     [rsp+70h+var_48], rdx
0x180097c22  mov     r14, r8
0x180097c25  xor     r9d, r9d
0x180097c28  mov     [rbp+arg_0], 84080041h
0x180097c2f  xor     r8d, r8d
0x180097c32  mov     [rbp+var_18], 0
0x180097c3a  mov     rax, [rax+48h]
0x180097c3e  xor     edx, edx
0x180097c40  mov     [rsp+70h+var_50], 0
0x180097c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097c4e  mov     ebx, eax
0x180097c50  test    eax, eax
0x180097c52  jns     short loc_180097C66
0x180097c54  mov     r9d, 46Ch
0x180097c5a  mov     edx, 1
0x180097c5f  mov     ecx, eax
0x180097c61  jmp     loc_180097F1D
0x180097c66  mov     rcx, [rbp+var_18]
0x180097c6a  mov     rax, [rcx]
0x180097c6d  mov     rax, [rax+78h]
0x180097c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097c76  mov     ebx, eax
0x180097c78  mov     esi, 1
0x180097c7d  test    ebx, ebx
0x180097c7f  jnz     loc_180097EFE
0x180097c85  mov     rcx, [rbp+var_18]
0x180097c89  lea     rdx, [rbp+var_30]
0x180097c8d  mov     [rbp+var_30], 0
0x180097c95  mov     rax, [rcx]
0x180097c98  mov     rax, [rax+28h]
0x180097c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ca1  mov     ebx, eax
0x180097ca3  test    eax, eax
0x180097ca5  js      loc_180097EDD
0x180097cab  mov     rdx, [rbp+var_30]
0x180097caf  lea     rcx, [rbp+var_20]
0x180097cb3  call    ??0?$CComQIPtr@UIUSStore@@$1?_GUID_5370942d_f237_4972_9455_b05691270bbc@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>(IUnknown *)
0x180097cb8  mov     rcx, [rbp+var_20]
0x180097cbc  test    rcx, rcx
0x180097cbf  jz      loc_180097EC0
0x180097cc5  mov     [rbp+arg_18], 0
0x180097ccd  lea     rdx, [rbp+arg_18]
0x180097cd1  mov     rax, [rcx]
0x180097cd4  mov     rax, [rax+0F0h]
0x180097cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ce0  mov     ebx, eax
0x180097ce2  test    eax, eax
0x180097ce4  js      loc_180097EB8
0x180097cea  mov     rcx, [rbp+arg_18]
0x180097cee  mov     rax, [rcx]
0x180097cf1  mov     rax, [rax+28h]
0x180097cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097cfa  mov     ebx, eax
0x180097cfc  test    eax, eax
0x180097cfe  js      loc_180097EA0
0x180097d04  mov     rcx, [rbp+arg_18]
0x180097d08  lea     r9, [rbp+arg_8]
0x180097d0c  mov     [rbp+var_28], 0
0x180097d14  lea     r8, [rbp+var_28]
0x180097d18  mov     dword ptr [rbp+arg_8], 0
0x180097d1f  mov     edx, esi
0x180097d21  mov     rax, [rcx]
0x180097d24  mov     rax, [rax+18h]
0x180097d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d2d  mov     ebx, eax
0x180097d2f  test    eax, eax
0x180097d31  js      loc_180097E88
0x180097d37  cmp     dword ptr [rbp+arg_8], 0
0x180097d3b  jz      loc_180097DFB
0x180097d41  mov     rdi, [rbp+var_28]
0x180097d45  lea     rcx, [rbp+hMem]
0x180097d49  mov     [rbp+hMem], 0
0x180097d51  mov     rax, [rdi]
0x180097d54  mov     rbx, [rax+18h]
0x180097d58  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x180097d5d  mov     r9, rax
0x180097d60  lea     r8, [rbp+arg_0]
0x180097d64  mov     rax, rbx
0x180097d67  mov     edx, esi
0x180097d69  mov     rcx, rdi
0x180097d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d71  mov     ebx, eax
0x180097d73  test    eax, eax
0x180097d75  js      loc_180097E80
0x180097d7b  mov     rcx, [rbp+hMem]; hMem
0x180097d7f  mov     eax, 100h
0x180097d84  test    [rcx+6], ax
0x180097d88  jnz     short loc_180097DA9
0x180097d8a  cmp     dword ptr [rcx+8], 10h
0x180097d8e  jnz     short loc_180097DA9
0x180097d90  mov     rdx, [rcx+10h]
0x180097d94  mov     rax, [rdx]
0x180097d97  sub     rax, [r14]
0x180097d9a  jnz     short loc_180097DA4
0x180097d9c  mov     rax, [rdx+8]
0x180097da0  sub     rax, [r14+8]
0x180097da4  test    rax, rax
0x180097da7  jz      short loc_180097DBD
0x180097da9  call    cs:__imp_LocalFree
0x180097daf  lea     rcx, [rbp+var_28]; void *
0x180097db3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097db8  jmp     loc_180097D04
0x180097dbd  mov     rcx, [rbp+var_28]
0x180097dc1  mov     rax, [rcx]
0x180097dc4  mov     rax, [rax+0C8h]
0x180097dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097dd0  mov     ebx, eax
0x180097dd2  test    eax, eax
0x180097dd4  js      loc_180097E78
0x180097dda  mov     rcx, [rbp+arg_18]
0x180097dde  mov     rax, [rcx]
0x180097de1  mov     rax, [rax+28h]
0x180097de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097dea  mov     ebx, eax
0x180097dec  test    eax, eax
0x180097dee  js      short loc_180097E36
0x180097df0  mov     rcx, [rbp+hMem]
0x180097df4  test    rcx, rcx
0x180097df7  jz      short loc_180097DAF
0x180097df9  jmp     short loc_180097DA9
0x180097dfb  lea     rcx, [rbp+var_28]; void *
0x180097dff  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097e04  mov     rcx, [rbp+var_18]
0x180097e08  mov     rax, [rcx]
0x180097e0b  mov     rax, [rax+60h]
0x180097e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e14  lea     rcx, [rbp+arg_18]; void *
0x180097e18  mov     ebx, eax
0x180097e1a  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097e1f  lea     rcx, [rbp+var_20]; void *
0x180097e23  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097e28  lea     rcx, [rbp+var_30]; void *
0x180097e2c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097e31  jmp     loc_180097C7D
0x180097e36  mov     r9d, 493h
0x180097e3c  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180097e43  mov     edx, esi
0x180097e45  mov     ecx, eax
0x180097e47  call    Log_UnistoreHREvent_0
0x180097e4c  mov     rcx, [rbp+hMem]; hMem
0x180097e50  test    rcx, rcx
0x180097e53  jz      short loc_180097E5B
0x180097e55  call    cs:__imp_LocalFree
0x180097e5b  lea     rcx, [rbp+var_28]; void *
0x180097e5f  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097e64  lea     rcx, [rbp+arg_18]; void *
0x180097e68  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097e6d  lea     rcx, [rbp+var_20]; void *
0x180097e71  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097e76  jmp     short loc_180097EF3
0x180097e78  mov     r9d, 491h
0x180097e7e  jmp     short loc_180097E3C
0x180097e80  mov     r9d, 487h
0x180097e86  jmp     short loc_180097E3C
0x180097e88  mov     r9d, 47Fh
0x180097e8e  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180097e95  mov     edx, esi
0x180097e97  mov     ecx, eax
0x180097e99  call    Log_UnistoreHREvent_0
0x180097e9e  jmp     short loc_180097E5B
0x180097ea0  mov     r9d, 479h
0x180097ea6  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180097ead  mov     edx, esi
0x180097eaf  mov     ecx, eax
0x180097eb1  call    Log_UnistoreHREvent_0
0x180097eb6  jmp     short loc_180097E64
0x180097eb8  mov     r9d, 478h
0x180097ebe  jmp     short loc_180097EA6
0x180097ec0  mov     ebx, 80004002h
0x180097ec5  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180097ecc  mov     ecx, ebx
0x180097ece  mov     r9d, 475h
0x180097ed4  xor     edx, edx
0x180097ed6  call    Log_UnistoreHREvent_0
0x180097edb  jmp     short loc_180097E6D
0x180097edd  mov     r9d, 472h
0x180097ee3  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180097eea  mov     edx, esi
0x180097eec  mov     ecx, eax
0x180097eee  call    Log_UnistoreHREvent_0
0x180097ef3  lea     rcx, [rbp+var_30]; void *
0x180097ef7  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097efc  jmp     short loc_180097F29
0x180097efe  cmp     ebx, 80070019h
0x180097f04  jnz     short loc_180097F13
0x180097f06  lea     rcx, [rbp+var_18]; void *
0x180097f0a  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097f0f  xor     eax, eax
0x180097f11  jmp     short loc_180097F34
0x180097f13  mov     r9d, 498h
0x180097f19  xor     edx, edx
0x180097f1b  mov     ecx, ebx
0x180097f1d  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180097f24  call    Log_UnistoreHREvent_0
0x180097f29  lea     rcx, [rbp+var_18]; void *
0x180097f2d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180097f32  mov     eax, ebx
0x180097f34  add     rsp, 70h
0x180097f38  pop     r14
0x180097f3a  pop     rdi
0x180097f3b  pop     rsi
0x180097f3c  pop     rbx
0x180097f3d  pop     rbp
0x180097f3e  retn
```
