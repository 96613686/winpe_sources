# UnistoreUpgrade::UpgradeCalendarWriteAccess(IUSStoreManager *,IDBVolume *)

- ea: `0x180098630`
- end: `0x180098b04`
- name: `?UpgradeCalendarWriteAccess@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `1236`
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
- `0x180059828`
- `0x180088380`
- `0x180098630`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800989b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800989b3`

## string_xrefs

- `0x18009899a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800989f4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098a15`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098a45`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098a64`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098a8c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098ac8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeCalendarWriteAccess(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int started; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, _DWORD *); // rbx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v35[2]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v36[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int128 v39; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v40; // [rsp+C0h] [rbp-40h]
  __int128 v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+E0h] [rbp-20h] BYREF
  int v43; // [rsp+E8h] [rbp-18h]
  int v44; // [rsp+ECh] [rbp-14h]
  __int128 *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h] BYREF
  int v47; // [rsp+100h] [rbp+0h]

  v3 = *(_QWORD *)this;
  v30 = 0;
  v5 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(v3 + 72))(
         this,
         0,
         0,
         0,
         0,
         &v30);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 795;
    v8 = 1;
    v9 = (unsigned int)v5;
LABEL_48:
    Log_UnistoreHREvent_0(
      v9,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      v7);
    goto LABEL_49;
  }
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 120LL))(v30);
  while ( 2 )
  {
    if ( v6 )
    {
      if ( v6 == -2147024871 )
      {
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v30);
        return 0;
      }
      v7 = 870;
      v8 = 0;
      v9 = v6;
      goto LABEL_48;
    }
    v26 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 40LL))(v30, &v26);
    v6 = v10;
    if ( v10 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        802);
      goto LABEL_44;
    }
    ATL::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>(
      &v27,
      v26);
    if ( !v27 )
    {
      v6 = -2147467262;
      v22 = 805;
      v24 = 2147500034LL;
      v23 = 0;
      goto LABEL_41;
    }
    v46 = 0;
    v47 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 24LL))(v27, &v46);
    v6 = v11;
    if ( v11 < 0 )
    {
      v22 = 808;
      v23 = 1;
      v24 = (unsigned int)v11;
LABEL_41:
      Log_UnistoreHREvent_0(
        v24,
        v23,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        v22);
      goto LABEL_29;
    }
    v35[1] = v46;
    v35[0] = 2147483644;
    ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v31, a2);
    v32 = 0;
    started = DBAutoTopLevelTransact::StartTransaction(
                (DBAutoTopLevelTransact *)v31,
                3u,
                2u,
                (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)v35);
    v6 = started;
    if ( started >= 0 )
    {
      v38 = 0;
      v42 = 4;
      v37 = 0;
      LODWORD(v37) = 906231827;
      v45 = &v37;
      DWORD2(v37) = 3;
      v44 = 906231827;
      v43 = 4;
      v28 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v27 + 288LL))(
              v27,
              0,
              0,
              0,
              &v42,
              &v28);
      v6 = v13;
      if ( v13 < 0 )
      {
        v19 = 834;
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 120LL))(v28);
        while ( !v6 )
        {
          v29 = 0;
          v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 40LL))(v28, &v29);
          v6 = v14;
          if ( v14 < 0 )
          {
            Log_UnistoreHREvent_0(
              (unsigned int)v14,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
              840);
            goto LABEL_26;
          }
          v15 = v29;
          v36[0] = 285474827;
          v36[1] = 1159200787;
          hMem = 0;
          v16 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v29 + 48LL);
          tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
          v17 = v16(v15, 2, v36);
          v6 = v17;
          if ( v17 < 0 )
          {
            v18 = 845;
            goto LABEL_24;
          }
          if ( (*((_WORD *)hMem + 3) & 0x300) == 0 )
          {
            v39 = 0;
            LODWORD(v39) = 285474827;
            WORD3(v39) = 512;
            v40 = 0;
            DWORD2(v40) = 1159200787;
            v41 = 0;
            LODWORD(v41) = *((_DWORD *)hMem + 2) != 0 ? 1 : 3;
            v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v29 + 80LL))(v29, 2, &v39);
            v6 = v17;
            if ( v17 < 0 )
            {
              v18 = 857;
LABEL_24:
              Log_UnistoreHREvent_0(
                (unsigned int)v17,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
                v18);
              if ( hMem )
                LocalFree(hMem);
LABEL_26:
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v29);
              goto LABEL_27;
            }
          }
          v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 96LL))(v28);
          if ( hMem )
            LocalFree(hMem);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v29);
        }
        if ( v6 != -2147024871 )
        {
          v19 = 862;
LABEL_33:
          v20 = 0;
          v21 = v6;
          goto LABEL_34;
        }
        v33 = 0;
        v13 = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v31, 1, &v33);
        v6 = v13;
        if ( v13 >= 0 )
        {
          if ( v33 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30);
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
            DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v31);
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v27);
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
            continue;
          }
          v19 = 866;
          v6 = -2147418113;
          goto LABEL_33;
        }
        v19 = 865;
      }
      v20 = 1;
      v21 = (unsigned int)v13;
LABEL_34:
      Log_UnistoreHREvent_0(
        v21,
        v20,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        v19);
LABEL_27:
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
      goto LABEL_28;
    }
    break;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)started,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    820);
LABEL_28:
  DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v31);
LABEL_29:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v27);
LABEL_44:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
LABEL_49:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v30);
  return v6;
}

```

## disassembly

```asm
0x180098630  mov     [rsp-8+arg_10], rbx
0x180098635  mov     [rsp-8+arg_18], rsi
0x18009863a  push    rbp
0x18009863b  push    rdi
0x18009863c  push    r14
0x18009863e  lea     rbp, [rsp-10h]
0x180098643  sub     rsp, 110h
0x18009864a  mov     rax, cs:__security_cookie
0x180098651  xor     rax, rsp
0x180098654  mov     [rbp+20h+var_18], rax
0x180098658  mov     rax, [rcx]
0x18009865b  mov     r14, rdx
0x18009865e  lea     rdx, [rsp+120h+var_C0]
0x180098663  mov     [rsp+120h+var_C0], 0
0x18009866c  mov     [rsp+120h+var_F8], rdx
0x180098671  xor     r9d, r9d
0x180098674  xor     r8d, r8d
0x180098677  mov     [rsp+120h+var_100], 0
0x180098680  mov     rax, [rax+48h]
0x180098684  xor     edx, edx
0x180098686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009868b  mov     ebx, eax
0x18009868d  test    eax, eax
0x18009868f  jns     short loc_1800986A3
0x180098691  mov     r9d, 31Bh
0x180098697  mov     edx, 1
0x18009869c  mov     ecx, eax
0x18009869e  jmp     loc_180098AC8
0x1800986a3  mov     rcx, [rsp+120h+var_C0]
0x1800986a8  mov     rax, [rcx]
0x1800986ab  mov     rax, [rax+78h]
0x1800986af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800986b4  mov     ebx, eax
0x1800986b6  mov     esi, 1
0x1800986bb  test    ebx, ebx
0x1800986bd  jnz     loc_180098AA8
0x1800986c3  mov     rcx, [rsp+120h+var_C0]
0x1800986c8  lea     rdx, [rsp+120h+var_E0]
0x1800986cd  mov     [rsp+120h+var_E0], 0
0x1800986d6  mov     rax, [rcx]
0x1800986d9  mov     rax, [rax+28h]
0x1800986dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800986e2  mov     ebx, eax
0x1800986e4  test    eax, eax
0x1800986e6  js      loc_180098A86
0x1800986ec  mov     rdx, [rsp+120h+var_E0]
0x1800986f1  lea     rcx, [rsp+120h+var_D8]
0x1800986f6  call    ??0?$CComQIPtr@UIUSStore@@$1?_GUID_5370942d_f237_4972_9455_b05691270bbc@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>::CComQIPtr<IUSStore,&__s_GUID const _GUID_5370942d_f237_4972_9455_b05691270bbc>(IUnknown *)
0x1800986fb  mov     rcx, [rsp+120h+var_D8]
0x180098700  test    rcx, rcx
0x180098703  jz      loc_180098A75
0x180098709  xor     eax, eax
0x18009870b  lea     rdx, [rbp+20h+var_28]
0x18009870f  mov     [rbp+20h+var_28], rax
0x180098713  mov     [rbp+20h+var_20], eax
0x180098716  mov     rax, [rcx]
0x180098719  mov     rax, [rax+18h]
0x18009871d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098722  mov     ebx, eax
0x180098724  test    eax, eax
0x180098726  js      loc_180098A5A
0x18009872c  mov     eax, dword ptr [rbp+20h+var_28]
0x18009872f  lea     rcx, [rsp+120h+var_B8]
0x180098734  mov     rdx, r14
0x180098737  mov     [rbp+20h+var_94], eax
0x18009873a  mov     [rbp+20h+var_98], 7FFFFFFCh
0x180098741  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x180098746  mov     edx, 3; unsigned int
0x18009874b  mov     [rsp+120h+var_B0], 0
0x180098753  lea     r9, [rbp+20h+var_98]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x180098757  lea     rcx, [rsp+120h+var_B8]; this
0x18009875c  lea     r8d, [rdx-1]; unsigned int
0x180098760  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x180098765  mov     ebx, eax
0x180098767  test    eax, eax
0x180098769  js      loc_180098A3F
0x18009876f  mov     rcx, [rsp+120h+var_D8]
0x180098774  lea     rdx, [rsp+120h+var_D0]
0x180098779  xor     eax, eax
0x18009877b  mov     [rsp+120h+var_F8], rdx
0x180098780  mov     [rbp+20h+var_78], rax
0x180098784  lea     rdx, [rbp+20h+var_40]
0x180098788  xorps   xmm0, xmm0
0x18009878b  mov     [rbp+20h+var_40], 4
0x180098793  movups  [rbp+20h+var_88], xmm0
0x180098797  lea     rax, [rbp+20h+var_88]
0x18009879b  mov     dword ptr [rbp+20h+var_88], 36040013h
0x1800987a2  mov     [rbp+20h+var_30], rax
0x1800987a6  xor     r9d, r9d
0x1800987a9  mov     dword ptr [rbp+20h+var_88+8], 3
0x1800987b0  xor     r8d, r8d
0x1800987b3  mov     [rbp+20h+var_34], 36040013h
0x1800987ba  mov     [rbp+20h+var_38], 4
0x1800987c1  mov     [rsp+120h+var_D0], 0
0x1800987ca  mov     rax, [rcx]
0x1800987cd  mov     [rsp+120h+var_100], rdx
0x1800987d2  xor     edx, edx
0x1800987d4  mov     rax, [rax+120h]
0x1800987db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800987e0  mov     ebx, eax
0x1800987e2  test    eax, eax
0x1800987e4  js      loc_180098A37
0x1800987ea  mov     rcx, [rsp+120h+var_D0]
0x1800987ef  mov     rax, [rcx]
0x1800987f2  mov     rax, [rax+78h]
0x1800987f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800987fb  mov     ebx, eax
0x1800987fd  test    ebx, ebx
0x1800987ff  jnz     loc_18009891A
0x180098805  mov     rcx, [rsp+120h+var_D0]
0x18009880a  lea     rdx, [rsp+120h+var_C8]
0x18009880f  mov     [rsp+120h+var_C8], 0
0x180098818  mov     rax, [rcx]
0x18009881b  mov     rax, [rax+28h]
0x18009881f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098824  mov     ebx, eax
0x180098826  test    eax, eax
0x180098828  js      loc_1800989EE
0x18009882e  mov     rdi, [rsp+120h+var_C8]
0x180098833  lea     rcx, [rbp+20h+hMem]
0x180098837  mov     [rbp+20h+var_90], 1104000Bh
0x18009883e  mov     [rbp+20h+var_8C], 45180013h
0x180098845  mov     [rbp+20h+hMem], 0
0x18009884d  mov     rax, [rdi]
0x180098850  mov     rbx, [rax+30h]
0x180098854  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x180098859  xor     r9d, r9d
0x18009885c  mov     [rsp+120h+var_100], rax
0x180098861  lea     r8, [rbp+20h+var_90]
0x180098865  mov     rcx, rdi
0x180098868  mov     rax, rbx
0x18009886b  lea     edx, [r9+2]
0x18009886f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098874  mov     ebx, eax
0x180098876  test    eax, eax
0x180098878  js      loc_1800989E6
0x18009887e  mov     rax, [rbp+20h+hMem]
0x180098882  mov     ecx, 300h
0x180098887  test    [rax+6], cx
0x18009888b  jnz     short loc_1800988E9
0x18009888d  xorps   xmm0, xmm0
0x180098890  lea     r8, [rbp+20h+var_70]
0x180098894  movups  [rbp+20h+var_70], xmm0
0x180098898  mov     ecx, 200h
0x18009889d  mov     dword ptr [rbp+20h+var_70], 1104000Bh
0x1800988a4  mov     word ptr [rbp+20h+var_70+6], cx
0x1800988a8  movups  [rbp+20h+var_60], xmm0
0x1800988ac  mov     dword ptr [rbp+20h+var_60+8], 45180013h
0x1800988b3  movups  [rbp+20h+var_50], xmm0
0x1800988b7  mov     ecx, [rax+8]
0x1800988ba  neg     ecx
0x1800988bc  mov     rcx, [rsp+120h+var_C8]
0x1800988c1  sbb     eax, eax
0x1800988c3  xor     r9d, r9d
0x1800988c6  and     eax, 0FFFFFFFEh
0x1800988c9  add     eax, 3
0x1800988cc  mov     dword ptr [rbp+20h+var_50], eax
0x1800988cf  mov     rax, [rcx]
0x1800988d2  lea     edx, [r9+2]
0x1800988d6  mov     rax, [rax+50h]
0x1800988da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988df  mov     ebx, eax
0x1800988e1  test    eax, eax
0x1800988e3  js      loc_180098994
0x1800988e9  mov     rcx, [rsp+120h+var_D0]
0x1800988ee  mov     rax, [rcx]
0x1800988f1  mov     rax, [rax+60h]
0x1800988f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988fa  mov     rcx, [rbp+20h+hMem]; hMem
0x1800988fe  mov     ebx, eax
0x180098900  test    rcx, rcx
0x180098903  jz      short loc_18009890B
0x180098905  call    cs:__imp_LocalFree
0x18009890b  lea     rcx, [rsp+120h+var_C8]; void *
0x180098910  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098915  jmp     loc_1800987FD
0x18009891a  cmp     ebx, 80070019h
0x180098920  jnz     loc_180098A2F
0x180098926  lea     r8, [rsp+120h+var_A8]; int *
0x18009892b  mov     [rsp+120h+var_A8], 0
0x180098933  mov     edx, esi; int
0x180098935  lea     rcx, [rsp+120h+var_B8]; this
0x18009893a  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x18009893f  mov     ebx, eax
0x180098941  test    eax, eax
0x180098943  js      loc_180098A23
0x180098949  cmp     [rsp+120h+var_A8], 0
0x18009894e  jz      loc_180098A06
0x180098954  mov     rcx, [rsp+120h+var_C0]
0x180098959  mov     rax, [rcx]
0x18009895c  mov     rax, [rax+60h]
0x180098960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098965  lea     rcx, [rsp+120h+var_D0]; void *
0x18009896a  mov     ebx, eax
0x18009896c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098971  lea     rcx, [rsp+120h+var_B8]; this
0x180098976  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009897b  lea     rcx, [rsp+120h+var_D8]; void *
0x180098980  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098985  lea     rcx, [rsp+120h+var_E0]; void *
0x18009898a  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009898f  jmp     loc_1800986BB
0x180098994  mov     r9d, 359h
0x18009899a  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800989a1  mov     edx, esi
0x1800989a3  mov     ecx, eax
0x1800989a5  call    Log_UnistoreHREvent_0
0x1800989aa  mov     rcx, [rbp+20h+hMem]; hMem
0x1800989ae  test    rcx, rcx
0x1800989b1  jz      short loc_1800989B9
0x1800989b3  call    cs:__imp_LocalFree
0x1800989b9  lea     rcx, [rsp+120h+var_C8]; void *
0x1800989be  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800989c3  lea     rcx, [rsp+120h+var_D0]; void *
0x1800989c8  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800989cd  lea     rcx, [rsp+120h+var_B8]; this
0x1800989d2  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x1800989d7  lea     rcx, [rsp+120h+var_D8]; void *
0x1800989dc  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800989e1  jmp     loc_180098A9C
0x1800989e6  mov     r9d, 34Dh
0x1800989ec  jmp     short loc_18009899A
0x1800989ee  mov     r9d, 348h
0x1800989f4  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800989fb  mov     edx, esi
0x1800989fd  mov     ecx, eax
0x1800989ff  call    Log_UnistoreHREvent_0
0x180098a04  jmp     short loc_1800989B9
0x180098a06  mov     r9d, 362h
0x180098a0c  mov     ebx, 8000FFFFh
0x180098a11  xor     edx, edx
0x180098a13  mov     ecx, ebx
0x180098a15  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098a1c  call    Log_UnistoreHREvent_0
0x180098a21  jmp     short loc_1800989C3
0x180098a23  mov     r9d, 361h
0x180098a29  mov     edx, esi
0x180098a2b  mov     ecx, eax
0x180098a2d  jmp     short loc_180098A15
0x180098a2f  mov     r9d, 35Eh
0x180098a35  jmp     short loc_180098A11
0x180098a37  mov     r9d, 342h
0x180098a3d  jmp     short loc_180098A29
0x180098a3f  mov     r9d, 334h
0x180098a45  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098a4c  mov     edx, esi
0x180098a4e  mov     ecx, eax
0x180098a50  call    Log_UnistoreHREvent_0
0x180098a55  jmp     loc_1800989CD
0x180098a5a  mov     r9d, 328h
0x180098a60  mov     edx, esi
0x180098a62  mov     ecx, eax
0x180098a64  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098a6b  call    Log_UnistoreHREvent_0
0x180098a70  jmp     loc_1800989D7
0x180098a75  mov     ebx, 80004002h
0x180098a7a  mov     r9d, 325h
0x180098a80  mov     ecx, ebx
0x180098a82  xor     edx, edx
0x180098a84  jmp     short loc_180098A64
0x180098a86  mov     r9d, 322h
0x180098a8c  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098a93  mov     edx, esi
0x180098a95  mov     ecx, eax
0x180098a97  call    Log_UnistoreHREvent_0
0x180098a9c  lea     rcx, [rsp+120h+var_E0]; void *
0x180098aa1  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098aa6  jmp     short loc_180098AD4
0x180098aa8  cmp     ebx, 80070019h
0x180098aae  jnz     short loc_180098ABE
0x180098ab0  lea     rcx, [rsp+120h+var_C0]; void *
0x180098ab5  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098aba  xor     eax, eax
0x180098abc  jmp     short loc_180098AE0
0x180098abe  mov     r9d, 366h
0x180098ac4  xor     edx, edx
0x180098ac6  mov     ecx, ebx
0x180098ac8  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098acf  call    Log_UnistoreHREvent_0
0x180098ad4  lea     rcx, [rsp+120h+var_C0]; void *
0x180098ad9  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098ade  mov     eax, ebx
0x180098ae0  mov     rcx, [rbp+20h+var_18]
0x180098ae4  xor     rcx, rsp; StackCookie
0x180098ae7  call    __security_check_cookie
0x180098aec  lea     r11, [rsp+120h+var_10]
0x180098af4  mov     rbx, [r11+30h]
0x180098af8  mov     rsi, [r11+38h]
0x180098afc  mov     rsp, r11
0x180098aff  pop     r14
0x180098b01  pop     rdi
0x180098b02  pop     rbp
0x180098b03  retn
```
