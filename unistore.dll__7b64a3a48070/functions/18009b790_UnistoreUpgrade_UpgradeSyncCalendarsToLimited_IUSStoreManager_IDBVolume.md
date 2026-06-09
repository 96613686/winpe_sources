# UnistoreUpgrade::UpgradeSyncCalendarsToLimited(IUSStoreManager *,IDBVolume *)

- ea: `0x18009b790`
- end: `0x18009bc26`
- name: `?UpgradeSyncCalendarsToLimited@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `1174`
- prototype: `__int64 __fastcall(UnistoreUpgrade *__hidden this, struct IUSStoreManager *, struct IDBVolume *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18001e2f4`
- `0x180034664`
- `0x180035d40`
- `0x1800576c0`
- `0x180072e68`
- `0x180088380`
- `0x18009b790`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bae9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bbee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bae9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bbee`

## string_xrefs

- `0x18009b7f3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009bb0a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009bb48`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009bb64`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009bb8b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009bbac`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009bbd5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeSyncCalendarsToLimited(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, int *, _QWORD, __int64); // rbx
  __int64 v10; // rax
  int v11; // eax
  int started; // eax
  int v13; // eax
  int v14; // eax
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, int *, _QWORD, __int64); // rbx
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  HLOCAL hMem; // [rsp+40h] [rbp-79h] BYREF
  __int64 v27; // [rsp+48h] [rbp-71h] BYREF
  __int64 v28; // [rsp+50h] [rbp-69h] BYREF
  __int64 v29; // [rsp+58h] [rbp-61h] BYREF
  int v30; // [rsp+60h] [rbp-59h] BYREF
  __int64 v31; // [rsp+68h] [rbp-51h] BYREF
  __int64 v32; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v33[8]; // [rsp+78h] [rbp-41h] BYREF
  int v34; // [rsp+80h] [rbp-39h]
  int v35; // [rsp+88h] [rbp-31h] BYREF
  __int128 v36; // [rsp+90h] [rbp-29h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-19h]
  __int128 v38; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-1h]
  __int64 v40; // [rsp+C0h] [rbp+7h] BYREF
  int v41; // [rsp+C8h] [rbp+Fh]
  int v42; // [rsp+CCh] [rbp+13h]
  __int128 *v43; // [rsp+D0h] [rbp+17h]
  __int64 v44; // [rsp+D8h] [rbp+1Fh] BYREF
  int v45; // [rsp+E0h] [rbp+27h]

  v3 = *(_QWORD *)this;
  v32 = 0;
  v5 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(v3 + 72))(
         this,
         0,
         0,
         0,
         0,
         &v32);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 120LL))(v32);
    while ( 1 )
    {
      if ( v7 )
      {
        v6 = 0;
        goto LABEL_47;
      }
      v8 = v32;
      hMem = 0;
      v30 = 873922625;
      v9 = *(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD, __int64))(*(_QWORD *)v32 + 48LL);
      v10 = tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>((__int64)&hMem);
      v11 = v9(v8, 1, &v30, 0, v10);
      v6 = v11;
      if ( v11 < 0 )
      {
        v24 = 1471;
        goto LABEL_43;
      }
      if ( (*((_WORD *)hMem + 3) & 0x300) == 0 )
        break;
LABEL_23:
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 96LL))(v32);
      if ( hMem )
        LocalFree(hMem);
    }
    v44 = 0;
    v45 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 88LL))(v32, &v44);
    v6 = v11;
    if ( v11 >= 0 )
    {
      ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v33, a2);
      v34 = 0;
      started = DBAutoTopLevelTransact::StartTransaction(
                  (DBAutoTopLevelTransact *)v33,
                  3u,
                  1u,
                  (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)&v44);
      v6 = started;
      if ( started < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)started,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          1483);
      }
      else
      {
        v40 = 4;
        v37 = 0;
        v36 = 0;
        DWORD2(v36) = 3;
        v41 = 4;
        LODWORD(v36) = 906231827;
        v43 = &v36;
        v42 = 906231827;
        v28 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 40LL))(v32, &v28);
        v6 = v13;
        if ( v13 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v13,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
            1497);
        }
        else
        {
          ATL::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>(
            &v29,
            v28);
          if ( v29 )
          {
            v27 = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v29 + 288LL))(
                    v29,
                    0x2000000,
                    0,
                    0,
                    &v40,
                    &v27);
            v6 = v14;
            if ( v14 < 0 )
            {
              v21 = 1503;
            }
            else
            {
              v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 120LL))(v27);
              while ( !v15 )
              {
                v31 = 0;
                v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 40LL))(v27, &v31);
                v6 = v16;
                if ( v16 < 0 )
                {
                  v20 = 1509;
                  goto LABEL_28;
                }
                v17 = v31;
                v30 = 1159200787;
                v18 = *(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD, __int64))(*(_QWORD *)v31 + 48LL);
                v19 = tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>((__int64)&hMem);
                v16 = v18(v17, 1, &v30, 0, v19);
                v6 = v16;
                if ( v16 < 0 )
                {
                  v20 = 1512;
                  goto LABEL_28;
                }
                if ( (*((_WORD *)hMem + 3) & 0x300) == 0 && *((_DWORD *)hMem + 2) == 3 )
                {
                  v38 = 0;
                  v39 = 0;
                  LODWORD(v38) = 1159200787;
                  DWORD2(v38) = 2;
                  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v31 + 80LL))(
                          v31,
                          1,
                          &v38,
                          0);
                  v6 = v16;
                  if ( v16 < 0 )
                  {
                    v20 = 1522;
LABEL_28:
                    Log_UnistoreHREvent_0(
                      (unsigned int)v16,
                      1,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
                      v20);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
                    goto LABEL_34;
                  }
                }
                v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 96LL))(v27);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
              }
              v35 = 0;
              v14 = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v33, 1, &v35);
              v6 = v14;
              if ( v14 >= 0 )
              {
                if ( v35 )
                {
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v27);
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v29);
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
                  DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v33);
                  goto LABEL_23;
                }
                v6 = -2147418113;
                v21 = 1529;
                v22 = 2147549183LL;
                v23 = 0;
                goto LABEL_33;
              }
              v21 = 1528;
            }
            v23 = 1;
            v22 = (unsigned int)v14;
LABEL_33:
            Log_UnistoreHREvent_0(
              v22,
              v23,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
              v21);
LABEL_34:
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v27);
          }
          else
          {
            v6 = -2147467262;
            Log_UnistoreHREvent_0(
              2147500034LL,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
              1500);
          }
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v29);
        }
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
      }
      DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v33);
      goto LABEL_44;
    }
    v24 = 1477;
LABEL_43:
    Log_UnistoreHREvent_0(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      v24);
LABEL_44:
    if ( hMem )
      LocalFree(hMem);
  }
  else
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      1464);
  }
LABEL_47:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v32);
  return v6;
}

```

## disassembly

```asm
0x18009b790  mov     [rsp-8+arg_10], rbx
0x18009b795  push    rbp
0x18009b796  push    rsi
0x18009b797  push    rdi
0x18009b798  push    r13
0x18009b79a  push    r14
0x18009b79c  lea     rbp, [rsp-37h]
0x18009b7a1  sub     rsp, 0F0h
0x18009b7a8  mov     rax, cs:__security_cookie
0x18009b7af  xor     rax, rsp
0x18009b7b2  mov     [rbp+57h+var_28], rax
0x18009b7b6  mov     rax, [rcx]
0x18009b7b9  mov     r14, rdx
0x18009b7bc  lea     rdx, [rbp+57h+var_A0]
0x18009b7c0  mov     [rbp+57h+var_A0], 0
0x18009b7c8  mov     [rsp+110h+var_E8], rdx
0x18009b7cd  xor     r9d, r9d
0x18009b7d0  xor     r8d, r8d
0x18009b7d3  mov     [rsp+110h+var_F0], 0
0x18009b7dc  mov     rax, [rax+48h]
0x18009b7e0  xor     edx, edx
0x18009b7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b7e7  mov     ebx, eax
0x18009b7e9  test    eax, eax
0x18009b7eb  jns     short loc_18009B80B
0x18009b7ed  mov     r9d, 5B8h
0x18009b7f3  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009b7fa  mov     edx, 1
0x18009b7ff  mov     ecx, eax
0x18009b801  call    Log_UnistoreHREvent_0
0x18009b806  jmp     loc_18009BBF8
0x18009b80b  mov     rcx, [rbp+57h+var_A0]
0x18009b80f  mov     rax, [rcx]
0x18009b812  mov     rax, [rax+78h]
0x18009b816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b81b  mov     ebx, eax
0x18009b81d  mov     esi, 1
0x18009b822  mov     r13d, 300h
0x18009b828  test    ebx, ebx
0x18009b82a  jnz     loc_18009BBF6
0x18009b830  mov     rdi, [rbp+57h+var_A0]
0x18009b834  lea     rcx, [rbp+57h+hMem]
0x18009b838  mov     [rbp+57h+hMem], 0
0x18009b840  mov     [rbp+57h+var_B0], 34170041h
0x18009b847  mov     rax, [rdi]
0x18009b84a  mov     rbx, [rax+30h]
0x18009b84e  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_array_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_array_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x18009b853  mov     [rsp+110h+var_F0], rax
0x18009b858  lea     r8, [rbp+57h+var_B0]
0x18009b85c  mov     rax, rbx
0x18009b85f  xor     r9d, r9d
0x18009b862  mov     edx, esi
0x18009b864  mov     rcx, rdi
0x18009b867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b86c  mov     ebx, eax
0x18009b86e  test    eax, eax
0x18009b870  js      loc_18009BBCF
0x18009b876  mov     rax, [rbp+57h+hMem]
0x18009b87a  test    [rax+6], r13w
0x18009b87f  jnz     loc_18009BACA
0x18009b885  mov     rcx, [rbp+57h+var_A0]
0x18009b889  lea     rdx, [rbp+57h+var_38]
0x18009b88d  xor     eax, eax
0x18009b88f  mov     [rbp+57h+var_38], rax
0x18009b893  mov     [rbp+57h+var_30], eax
0x18009b896  mov     rax, [rcx]
0x18009b899  mov     rax, [rax+58h]
0x18009b89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b8a2  mov     ebx, eax
0x18009b8a4  test    eax, eax
0x18009b8a6  js      loc_18009BBC7
0x18009b8ac  mov     rdx, r14
0x18009b8af  lea     rcx, [rbp+57h+var_98]
0x18009b8b3  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x18009b8b8  lea     r9, [rbp+57h+var_38]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x18009b8bc  mov     [rbp+57h+var_90], 0
0x18009b8c3  mov     r8d, esi; unsigned int
0x18009b8c6  lea     rcx, [rbp+57h+var_98]; this
0x18009b8ca  mov     edx, 3; unsigned int
0x18009b8cf  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x18009b8d4  mov     ebx, eax
0x18009b8d6  test    eax, eax
0x18009b8d8  js      loc_18009BBA6
0x18009b8de  mov     rcx, [rbp+57h+var_A0]
0x18009b8e2  lea     rdx, [rbp+57h+var_C0]
0x18009b8e6  xor     eax, eax
0x18009b8e8  mov     [rbp+57h+var_50], 4
0x18009b8f0  mov     [rbp+57h+var_70], rax
0x18009b8f4  xorps   xmm0, xmm0
0x18009b8f7  movups  [rbp+57h+var_80], xmm0
0x18009b8fb  mov     eax, 4
0x18009b900  mov     dword ptr [rbp+57h+var_80+8], 3
0x18009b907  mov     [rbp+57h+var_48], eax
0x18009b90a  mov     edi, 36040013h
0x18009b90f  lea     rax, [rbp+57h+var_80]
0x18009b913  mov     dword ptr [rbp+57h+var_80], edi
0x18009b916  mov     [rbp+57h+var_40], rax
0x18009b91a  mov     [rbp+57h+var_44], edi
0x18009b91d  mov     [rbp+57h+var_C0], 0
0x18009b925  mov     rax, [rcx]
0x18009b928  mov     rax, [rax+28h]
0x18009b92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b931  mov     ebx, eax
0x18009b933  test    eax, eax
0x18009b935  js      loc_18009BB85
0x18009b93b  mov     rdx, [rbp+57h+var_C0]
0x18009b93f  lea     rcx, [rbp+57h+var_B8]
0x18009b943  call    ??0?$CComQIPtr@UIUSStore@@$1?_GUID_5370942d_f237_4972_9455_b05691270bbc@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>(IUnknown *)
0x18009b948  mov     rcx, [rbp+57h+var_B8]
0x18009b94c  test    rcx, rcx
0x18009b94f  jz      loc_18009BB5F
0x18009b955  mov     [rbp+57h+var_C8], 0
0x18009b95d  lea     rdx, [rbp+57h+var_C8]
0x18009b961  mov     rax, [rcx]
0x18009b964  xor     r9d, r9d
0x18009b967  mov     [rsp+110h+var_E8], rdx
0x18009b96c  xor     r8d, r8d
0x18009b96f  lea     rdx, [rbp+57h+var_50]
0x18009b973  mov     [rsp+110h+var_F0], rdx
0x18009b978  mov     edx, 2000000h
0x18009b97d  mov     rax, [rax+120h]
0x18009b984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b989  mov     ebx, eax
0x18009b98b  test    eax, eax
0x18009b98d  js      loc_18009BB3E
0x18009b993  mov     rcx, [rbp+57h+var_C8]
0x18009b997  mov     rax, [rcx]
0x18009b99a  mov     rax, [rax+78h]
0x18009b99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b9a3  mov     ebx, eax
0x18009b9a5  test    ebx, ebx
0x18009b9a7  jnz     loc_18009BA80
0x18009b9ad  mov     rcx, [rbp+57h+var_C8]
0x18009b9b1  lea     rdx, [rbp+57h+var_A8]
0x18009b9b5  mov     [rbp+57h+var_A8], 0
0x18009b9bd  mov     rax, [rcx]
0x18009b9c0  mov     rax, [rax+28h]
0x18009b9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b9c9  mov     ebx, eax
0x18009b9cb  test    eax, eax
0x18009b9cd  js      loc_18009BB04
0x18009b9d3  mov     rdi, [rbp+57h+var_A8]
0x18009b9d7  lea     rcx, [rbp+57h+hMem]
0x18009b9db  mov     [rbp+57h+var_B0], 45180013h
0x18009b9e2  mov     rax, [rdi]
0x18009b9e5  mov     rbx, [rax+30h]
0x18009b9e9  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_array_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_array_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x18009b9ee  mov     [rsp+110h+var_F0], rax
0x18009b9f3  lea     r8, [rbp+57h+var_B0]
0x18009b9f7  mov     rax, rbx
0x18009b9fa  xor     r9d, r9d
0x18009b9fd  mov     edx, esi
0x18009b9ff  mov     rcx, rdi
0x18009ba02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba07  mov     ebx, eax
0x18009ba09  test    eax, eax
0x18009ba0b  js      loc_18009BAFC
0x18009ba11  mov     rax, [rbp+57h+hMem]
0x18009ba15  test    [rax+6], r13w
0x18009ba1a  jnz     short loc_18009BA60
0x18009ba1c  cmp     dword ptr [rax+8], 3
0x18009ba20  jnz     short loc_18009BA60
0x18009ba22  mov     rcx, [rbp+57h+var_A8]
0x18009ba26  lea     r8, [rbp+57h+var_68]
0x18009ba2a  xor     eax, eax
0x18009ba2c  xorps   xmm0, xmm0
0x18009ba2f  movups  [rbp+57h+var_68], xmm0
0x18009ba33  mov     [rbp+57h+var_58], rax
0x18009ba37  xor     r9d, r9d
0x18009ba3a  mov     dword ptr [rbp+57h+var_68], 45180013h
0x18009ba41  mov     edx, esi
0x18009ba43  mov     dword ptr [rbp+57h+var_68+8], 2
0x18009ba4a  mov     rax, [rcx]
0x18009ba4d  mov     rax, [rax+50h]
0x18009ba51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba56  mov     ebx, eax
0x18009ba58  test    eax, eax
0x18009ba5a  js      loc_18009BAF4
0x18009ba60  mov     rcx, [rbp+57h+var_C8]
0x18009ba64  mov     rax, [rcx]
0x18009ba67  mov     rax, [rax+60h]
0x18009ba6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba70  lea     rcx, [rbp+57h+var_A8]; void *
0x18009ba74  mov     ebx, eax
0x18009ba76  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009ba7b  jmp     loc_18009B9A5
0x18009ba80  lea     r8, [rbp+57h+var_88]; int *
0x18009ba84  mov     [rbp+57h+var_88], 0
0x18009ba8b  mov     edx, esi; int
0x18009ba8d  lea     rcx, [rbp+57h+var_98]; this
0x18009ba91  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x18009ba96  mov     ebx, eax
0x18009ba98  test    eax, eax
0x18009ba9a  js      loc_18009BB36
0x18009baa0  cmp     [rbp+57h+var_88], 0
0x18009baa4  jz      short loc_18009BB25
0x18009baa6  lea     rcx, [rbp+57h+var_C8]; void *
0x18009baaa  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009baaf  lea     rcx, [rbp+57h+var_B8]; void *
0x18009bab3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009bab8  lea     rcx, [rbp+57h+var_C0]; void *
0x18009babc  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009bac1  lea     rcx, [rbp+57h+var_98]; this
0x18009bac5  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009baca  mov     rcx, [rbp+57h+var_A0]
0x18009bace  mov     rax, [rcx]
0x18009bad1  mov     rax, [rax+60h]
0x18009bad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bada  mov     rcx, [rbp+57h+hMem]; hMem
0x18009bade  mov     ebx, eax
0x18009bae0  test    rcx, rcx
0x18009bae3  jz      loc_18009B828
0x18009bae9  call    cs:__imp_LocalFree
0x18009baef  jmp     loc_18009B828
0x18009baf4  mov     r9d, 5F2h
0x18009bafa  jmp     short loc_18009BB0A
0x18009bafc  mov     r9d, 5E8h
0x18009bb02  jmp     short loc_18009BB0A
0x18009bb04  mov     r9d, 5E5h
0x18009bb0a  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009bb11  mov     edx, esi
0x18009bb13  mov     ecx, eax
0x18009bb15  call    Log_UnistoreHREvent_0
0x18009bb1a  lea     rcx, [rbp+57h+var_A8]; void *
0x18009bb1e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009bb23  jmp     short loc_18009BB54
0x18009bb25  mov     ebx, 8000FFFFh
0x18009bb2a  mov     r9d, 5F9h
0x18009bb30  mov     ecx, ebx
0x18009bb32  xor     edx, edx
0x18009bb34  jmp     short loc_18009BB48
0x18009bb36  mov     r9d, 5F8h
0x18009bb3c  jmp     short loc_18009BB44
0x18009bb3e  mov     r9d, 5DFh
0x18009bb44  mov     edx, esi
0x18009bb46  mov     ecx, eax
0x18009bb48  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009bb4f  call    Log_UnistoreHREvent_0
0x18009bb54  lea     rcx, [rbp+57h+var_C8]; void *
0x18009bb58  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009bb5d  jmp     short loc_18009BB7A
0x18009bb5f  mov     ebx, 80004002h
0x18009bb64  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009bb6b  mov     ecx, ebx
0x18009bb6d  mov     r9d, 5DCh
0x18009bb73  xor     edx, edx
0x18009bb75  call    Log_UnistoreHREvent_0
0x18009bb7a  lea     rcx, [rbp+57h+var_B8]; void *
0x18009bb7e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009bb83  jmp     short loc_18009BB9B
0x18009bb85  mov     r9d, 5D9h
0x18009bb8b  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009bb92  mov     edx, esi
0x18009bb94  mov     ecx, eax
0x18009bb96  call    Log_UnistoreHREvent_0
0x18009bb9b  lea     rcx, [rbp+57h+var_C0]; void *
0x18009bb9f  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009bba4  jmp     short loc_18009BBBC
0x18009bba6  mov     r9d, 5CBh
0x18009bbac  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009bbb3  mov     edx, esi
0x18009bbb5  mov     ecx, eax
0x18009bbb7  call    Log_UnistoreHREvent_0
0x18009bbbc  lea     rcx, [rbp+57h+var_98]; this
0x18009bbc0  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009bbc5  jmp     short loc_18009BBE5
0x18009bbc7  mov     r9d, 5C5h
0x18009bbcd  jmp     short loc_18009BBD5
0x18009bbcf  mov     r9d, 5BFh
0x18009bbd5  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009bbdc  mov     edx, esi
0x18009bbde  mov     ecx, eax
0x18009bbe0  call    Log_UnistoreHREvent_0
0x18009bbe5  mov     rcx, [rbp+57h+hMem]; hMem
0x18009bbe9  test    rcx, rcx
0x18009bbec  jz      short loc_18009BBF8
0x18009bbee  call    cs:__imp_LocalFree
0x18009bbf4  jmp     short loc_18009BBF8
0x18009bbf6  xor     ebx, ebx
0x18009bbf8  lea     rcx, [rbp+57h+var_A0]; void *
0x18009bbfc  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009bc01  mov     eax, ebx
0x18009bc03  mov     rcx, [rbp+57h+var_28]
0x18009bc07  xor     rcx, rsp; StackCookie
0x18009bc0a  call    __security_check_cookie
0x18009bc0f  mov     rbx, [rsp+110h+arg_10]
0x18009bc17  add     rsp, 0F0h
0x18009bc1e  pop     r14
0x18009bc20  pop     r13
0x18009bc22  pop     rdi
0x18009bc23  pop     rsi
0x18009bc24  pop     rbp
0x18009bc25  retn
```
