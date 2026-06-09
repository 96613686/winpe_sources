# UnistoreUpgrade::_UpgradeCleanupContactWithoutAggregate(IUSStoreManager *,IDBVolume *)

- ea: `0x18009c300`
- end: `0x18009c5ed`
- name: `?_UpgradeCleanupContactWithoutAggregate@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `749`
- prototype: `int(UnistoreUpgrade *__hidden this, struct IUSStoreManager *, struct IDBVolume *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180098b10`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180059828`
- `0x180066880`
- `0x18009bc2c`
- `0x18009c300`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c51d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c56d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c51d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c56d`

## string_xrefs

- `0x18009c3a4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009c4eb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009c553`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009c57a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009c5a1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::_UpgradeCleanupContactWithoutAggregate(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  __int64 v3; // rax
  unsigned int v5; // r14d
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  unsigned int (*i)(void); // rax
  int v10; // eax
  UnistoreUpgrade *v11; // rbx
  __int64 (__fastcall *v12)(UnistoreUpgrade *, __int64, _DWORD *); // rdi
  int v13; // eax
  struct IDBVolume *v14; // r9
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // eax
  struct IDBVolume *v18; // r9
  __int64 v19; // r9
  HLOCAL hMem; // [rsp+40h] [rbp-29h] BYREF
  UnistoreUpgrade *v22; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+60h] [rbp-9h] BYREF
  _DWORD v26[2]; // [rsp+68h] [rbp-1h] BYREF
  int v27; // [rsp+70h] [rbp+7h] BYREF
  __int64 v28; // [rsp+74h] [rbp+Bh]
  __int64 v29; // [rsp+80h] [rbp+17h] BYREF
  int v30; // [rsp+88h] [rbp+1Fh]

  v3 = *(_QWORD *)this;
  v24 = 0;
  v5 = (unsigned int)a2;
  v6 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD))(v3 + 136))(this, 1, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 1054;
LABEL_5:
    Log_UnistoreHREvent_0(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      v8);
    goto LABEL_33;
  }
  v29 = 0;
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64 *))(*(_QWORD *)this + 56LL))(this, &v29);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 1057;
    goto LABEL_5;
  }
  for ( i = *(unsigned int (**)(void))(*(_QWORD *)v24 + 120LL); !i(); i = *(unsigned int (**)(void))(*(_QWORD *)v24 + 96LL) )
  {
    v23 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 40LL))(v24, &v23);
    v7 = v10;
    if ( v10 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        1064);
      goto LABEL_31;
    }
    ATL::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>(
      &v22,
      v23);
    v11 = v22;
    if ( !v22 )
    {
      v7 = -2147467262;
      Log_UnistoreHREvent_0(
        2147500034LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        1067);
      goto LABEL_29;
    }
    v26[0] = 131075;
    v26[1] = 806617107;
    hMem = 0;
    v12 = *(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _DWORD *))(*(_QWORD *)v22 + 48LL);
    tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
    v13 = v12(v11, 2, v26);
    v7 = v13;
    if ( v13 < 0 )
    {
      v15 = 1076;
      goto LABEL_25;
    }
    if ( (*((_WORD *)hMem + 15) & 0x100) != 0 )
    {
      v13 = UnistoreUpgrade::_DeleteBrokenContact(v22, (struct IUSItem *)*((unsigned int *)hMem + 2), v5, v14);
      v7 = v13;
      if ( v13 < 0 )
      {
        v15 = 1081;
LABEL_25:
        Log_UnistoreHREvent_0(
          (unsigned int)v13,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v15);
        goto LABEL_26;
      }
    }
    else
    {
      v27 = v29;
      v28 = 458754;
      v25 = 0;
      v16 = *(_QWORD *)this;
      HIDWORD(v28) = *((_DWORD *)hMem + 8);
      v17 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, int *, __int64 *))(v16 + 120))(this, &v27, &v25);
      v7 = v17;
      if ( v17 == -2147023728 )
      {
        v17 = UnistoreUpgrade::_DeleteBrokenContact(v22, (struct IUSItem *)*((unsigned int *)hMem + 2), v5, v18);
        v7 = v17;
        if ( v17 < 0 )
        {
          v19 = 1095;
          goto LABEL_17;
        }
      }
      else if ( v17 < 0 )
      {
        v19 = 1099;
LABEL_17:
        Log_UnistoreHREvent_0(
          (unsigned int)v17,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v19);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v25);
LABEL_26:
        if ( hMem )
          LocalFree(hMem);
LABEL_29:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v22);
LABEL_31:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v23);
        goto LABEL_33;
      }
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v25);
    }
    if ( hMem )
      LocalFree(hMem);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v22);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v23);
  }
  v7 = 0;
LABEL_33:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
  return v7;
}

```

## disassembly

```asm
0x18009c300  mov     [rsp-8+arg_10], rbx
0x18009c305  push    rbp
0x18009c306  push    rsi
0x18009c307  push    rdi
0x18009c308  push    r12
0x18009c30a  push    r14
0x18009c30c  lea     rbp, [rsp-37h]
0x18009c311  sub     rsp, 0A0h
0x18009c318  mov     rax, cs:__security_cookie
0x18009c31f  xor     rax, rsp
0x18009c322  mov     [rbp+57h+var_30], rax
0x18009c326  mov     rax, [rcx]
0x18009c329  mov     rsi, rcx
0x18009c32c  xor     r9d, r9d
0x18009c32f  mov     [rbp+57h+var_68], 0
0x18009c337  lea     rcx, [rbp+57h+var_68]
0x18009c33b  mov     r14, rdx
0x18009c33e  mov     [rsp+0C0h+var_90], rcx
0x18009c343  xor     r8d, r8d
0x18009c346  mov     rax, [rax+88h]
0x18009c34d  mov     rcx, rsi
0x18009c350  lea     r12d, [r9+1]
0x18009c354  mov     [rsp+0C0h+var_98], 0
0x18009c35d  mov     edx, r12d
0x18009c360  mov     [rsp+0C0h+var_A0], 0
0x18009c369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c36e  mov     ebx, eax
0x18009c370  test    eax, eax
0x18009c372  jns     short loc_18009C37C
0x18009c374  mov     r9d, 41Eh
0x18009c37a  jmp     short loc_18009C3A4
0x18009c37c  xor     eax, eax
0x18009c37e  lea     rdx, [rbp+57h+var_40]
0x18009c382  mov     [rbp+57h+var_40], rax
0x18009c386  mov     rcx, rsi
0x18009c389  mov     [rbp+57h+var_38], eax
0x18009c38c  mov     rax, [rsi]
0x18009c38f  mov     rax, [rax+38h]
0x18009c393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c398  mov     ebx, eax
0x18009c39a  test    eax, eax
0x18009c39c  jns     short loc_18009C3BA
0x18009c39e  mov     r9d, 421h
0x18009c3a4  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009c3ab  mov     edx, r12d
0x18009c3ae  mov     ecx, eax
0x18009c3b0  call    Log_UnistoreHREvent_0
0x18009c3b5  jmp     loc_18009C5BF
0x18009c3ba  mov     rcx, [rbp+57h+var_68]
0x18009c3be  mov     rax, [rcx]
0x18009c3c1  mov     rax, [rax+78h]
0x18009c3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c3ca  test    eax, eax
0x18009c3cc  jnz     loc_18009C5BD
0x18009c3d2  mov     rcx, [rbp+57h+var_68]
0x18009c3d6  lea     rdx, [rbp+57h+var_70]
0x18009c3da  mov     [rbp+57h+var_70], 0
0x18009c3e2  mov     rax, [rcx]
0x18009c3e5  mov     rax, [rax+28h]
0x18009c3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c3ee  mov     ebx, eax
0x18009c3f0  test    eax, eax
0x18009c3f2  js      loc_18009C59B
0x18009c3f8  mov     rdx, [rbp+57h+var_70]
0x18009c3fc  lea     rcx, [rbp+57h+var_78]
0x18009c400  call    ??0?$CComQIPtr@UIUSItem@@$1?_GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>::CComQIPtr<IUSItem,&__s_GUID const _GUID_0b0c0eb6_4260_43f2_b6b2_321d850c0b16>(IUnknown *)
0x18009c405  mov     rbx, [rbp+57h+var_78]
0x18009c409  test    rbx, rbx
0x18009c40c  jz      loc_18009C575
0x18009c412  mov     [rbp+57h+var_58], 20003h
0x18009c419  lea     rcx, [rbp+57h+hMem]
0x18009c41d  mov     [rbp+57h+var_54], 30140013h
0x18009c424  mov     [rbp+57h+hMem], 0
0x18009c42c  mov     rax, [rbx]
0x18009c42f  mov     rdi, [rax+30h]
0x18009c433  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x18009c438  xor     r9d, r9d
0x18009c43b  mov     [rsp+0C0h+var_A0], rax
0x18009c440  lea     r8, [rbp+57h+var_58]
0x18009c444  mov     rcx, rbx
0x18009c447  mov     rax, rdi
0x18009c44a  lea     edx, [r9+2]
0x18009c44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c453  mov     ebx, eax
0x18009c455  test    eax, eax
0x18009c457  js      loc_18009C54D
0x18009c45d  mov     rax, [rbp+57h+hMem]
0x18009c461  mov     ecx, 100h
0x18009c466  test    [rax+1Eh], cx
0x18009c46a  jz      short loc_18009C490
0x18009c46c  mov     edx, [rax+8]; struct IUSItem *
0x18009c46f  mov     r8, r14; unsigned int
0x18009c472  mov     rcx, [rbp+57h+var_78]; this
0x18009c476  call    ?_DeleteBrokenContact@UnistoreUpgrade@@YAJPEAUIUSItem@@KPEAVIDBVolume@@@Z; UnistoreUpgrade::_DeleteBrokenContact(IUSItem *,ulong,IDBVolume *)
0x18009c47b  mov     ebx, eax
0x18009c47d  test    eax, eax
0x18009c47f  jns     loc_18009C514
0x18009c485  mov     r9d, 439h
0x18009c48b  jmp     loc_18009C553
0x18009c490  mov     ecx, dword ptr [rbp+57h+var_40]
0x18009c493  lea     r8, [rbp+57h+var_60]
0x18009c497  mov     [rbp+57h+var_50], ecx
0x18009c49a  lea     rdx, [rbp+57h+var_50]
0x18009c49e  mov     [rbp+57h+var_4C], 70002h
0x18009c4a6  mov     [rbp+57h+var_60], 0
0x18009c4ae  mov     ecx, [rax+20h]
0x18009c4b1  mov     rax, [rsi]
0x18009c4b4  mov     dword ptr [rbp+57h+var_4C+4], ecx
0x18009c4b7  mov     rcx, rsi
0x18009c4ba  mov     rax, [rax+78h]
0x18009c4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c4c3  mov     ebx, eax
0x18009c4c5  cmp     eax, 80070490h
0x18009c4ca  jnz     short loc_18009C507
0x18009c4cc  mov     rdx, [rbp+57h+hMem]
0x18009c4d0  mov     r8, r14; unsigned int
0x18009c4d3  mov     rcx, [rbp+57h+var_78]; this
0x18009c4d7  mov     edx, [rdx+8]; struct IUSItem *
0x18009c4da  call    ?_DeleteBrokenContact@UnistoreUpgrade@@YAJPEAUIUSItem@@KPEAVIDBVolume@@@Z; UnistoreUpgrade::_DeleteBrokenContact(IUSItem *,ulong,IDBVolume *)
0x18009c4df  mov     ebx, eax
0x18009c4e1  test    eax, eax
0x18009c4e3  jns     short loc_18009C50B
0x18009c4e5  mov     r9d, 447h
0x18009c4eb  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009c4f2  mov     edx, r12d
0x18009c4f5  mov     ecx, eax
0x18009c4f7  call    Log_UnistoreHREvent_0
0x18009c4fc  lea     rcx, [rbp+57h+var_60]; void *
0x18009c500  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009c505  jmp     short loc_18009C564
0x18009c507  test    eax, eax
0x18009c509  js      short loc_18009C545
0x18009c50b  lea     rcx, [rbp+57h+var_60]; void *
0x18009c50f  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009c514  mov     rcx, [rbp+57h+hMem]; hMem
0x18009c518  test    rcx, rcx
0x18009c51b  jz      short loc_18009C523
0x18009c51d  call    cs:__imp_LocalFree
0x18009c523  lea     rcx, [rbp+57h+var_78]; void *
0x18009c527  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009c52c  lea     rcx, [rbp+57h+var_70]; void *
0x18009c530  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009c535  mov     rcx, [rbp+57h+var_68]
0x18009c539  mov     rax, [rcx]
0x18009c53c  mov     rax, [rax+60h]
0x18009c540  jmp     loc_18009C3C5
0x18009c545  mov     r9d, 44Bh
0x18009c54b  jmp     short loc_18009C4EB
0x18009c54d  mov     r9d, 434h
0x18009c553  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009c55a  mov     edx, r12d
0x18009c55d  mov     ecx, eax
0x18009c55f  call    Log_UnistoreHREvent_0
0x18009c564  mov     rcx, [rbp+57h+hMem]; hMem
0x18009c568  test    rcx, rcx
0x18009c56b  jz      short loc_18009C590
0x18009c56d  call    cs:__imp_LocalFree
0x18009c573  jmp     short loc_18009C590
0x18009c575  mov     ebx, 80004002h
0x18009c57a  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009c581  mov     ecx, ebx
0x18009c583  mov     r9d, 42Bh
0x18009c589  xor     edx, edx
0x18009c58b  call    Log_UnistoreHREvent_0
0x18009c590  lea     rcx, [rbp+57h+var_78]; void *
0x18009c594  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009c599  jmp     short loc_18009C5B2
0x18009c59b  mov     r9d, 428h
0x18009c5a1  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009c5a8  mov     edx, r12d
0x18009c5ab  mov     ecx, eax
0x18009c5ad  call    Log_UnistoreHREvent_0
0x18009c5b2  lea     rcx, [rbp+57h+var_70]; void *
0x18009c5b6  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009c5bb  jmp     short loc_18009C5BF
0x18009c5bd  xor     ebx, ebx
0x18009c5bf  lea     rcx, [rbp+57h+var_68]; void *
0x18009c5c3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009c5c8  mov     eax, ebx
0x18009c5ca  mov     rcx, [rbp+57h+var_30]
0x18009c5ce  xor     rcx, rsp; StackCookie
0x18009c5d1  call    __security_check_cookie
0x18009c5d6  mov     rbx, [rsp+0C0h+arg_10]
0x18009c5de  add     rsp, 0A0h
0x18009c5e5  pop     r14
0x18009c5e7  pop     r12
0x18009c5e9  pop     rdi
0x18009c5ea  pop     rsi
0x18009c5eb  pop     rbp
0x18009c5ec  retn
```
