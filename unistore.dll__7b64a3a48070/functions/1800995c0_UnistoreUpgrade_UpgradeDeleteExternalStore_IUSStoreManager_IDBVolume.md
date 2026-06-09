# UnistoreUpgrade::UpgradeDeleteExternalStore(IUSStoreManager *,IDBVolume *)

- ea: `0x1800995c0`
- end: `0x180099e4f`
- name: `?UpgradeDeleteExternalStore@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `2191`
- prototype: `__int64 __fastcall(UnistoreUpgrade *__hidden this, struct IUSStoreManager *, struct IDBVolume *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180004440`
- `0x180004464`
- `0x1800068f0`
- `0x18001abf4`
- `0x18001e2f4`
- `0x180034664`
- `0x180035d40`
- `0x18003c174`
- `0x18004bbc0`
- `0x1800576c0`
- `0x180059828`
- `0x1800995c0`
- `0x18009c5f4`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099786`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800997d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099aba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099b42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099786`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800997d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099aba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099b42`

## string_xrefs

- `0x1800997bf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800997e3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099816`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009986d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099b0a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099b27`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099b58`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099bd9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099d2a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099d4f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099dc2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeDeleteExternalStore(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // eax
  _QWORD *v14; // rdi
  int v15; // eax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, __int64, int *, _QWORD, void **); // rbx
  void **v18; // rax
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64, _DWORD *); // rbx
  int v31; // eax
  int v32; // eax
  __int64 v33; // r9
  int v34; // r11d
  char v35; // bl
  __int64 v36; // rsi
  _DWORD *j; // rax
  unsigned __int64 v38; // r10
  int v39; // r9d
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r9
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // rcx
  int v48; // eax
  int started; // eax
  __int64 v50; // rdx
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // r9
  _QWORD *i; // rbx
  int v55; // eax
  unsigned int v56; // esi
  __int64 v58; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v61; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A0h] BYREF
  int v63; // [rsp+68h] [rbp-98h] BYREF
  __int64 v64; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+88h] [rbp-78h]
  int v68; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+98h] [rbp-68h] BYREF
  int v70; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v71[2]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v72[2]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v73[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v74; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v75; // [rsp+C8h] [rbp-38h]
  _QWORD *v76; // [rsp+D0h] [rbp-30h]
  __int64 v77; // [rsp+D8h] [rbp-28h] BYREF
  int v78; // [rsp+E0h] [rbp-20h]
  int v79; // [rsp+E4h] [rbp-1Ch]
  __int64 v80; // [rsp+E8h] [rbp-18h]
  __int128 v81; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v82; // [rsp+100h] [rbp+0h]
  _QWORD v83[3]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v84; // [rsp+120h] [rbp+20h] BYREF
  int v85; // [rsp+128h] [rbp+28h]
  int v86; // [rsp+12Ch] [rbp+2Ch]
  __int128 *v87; // [rsp+130h] [rbp+30h]
  __int64 v88; // [rsp+138h] [rbp+38h] BYREF
  int v89; // [rsp+140h] [rbp+40h]
  __int64 v90; // [rsp+148h] [rbp+48h] BYREF
  int v91; // [rsp+150h] [rbp+50h]

  v84 = 4;
  v82 = 0;
  v85 = 4;
  v86 = 927137803;
  v81 = 0;
  LODWORD(v81) = 927137803;
  DWORD2(v81) = 1;
  v87 = &v81;
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &v74,
    a2,
    a3);
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    v83,
    v5,
    v6);
  v7 = *(_QWORD *)this;
  v69 = 0;
  v8 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, _QWORD, _QWORD, _QWORD, __int64 *, __int64 *))(v7 + 72))(
         this,
         0,
         0,
         0,
         &v84,
         &v69);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1334;
    v11 = 1;
    v12 = (unsigned int)v8;
LABEL_26:
    Log_UnistoreHREvent_0(
      v12,
      v11,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      v10);
    goto LABEL_108;
  }
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 120LL))(v69);
  v14 = v75;
  v9 = v13;
  while ( 1 )
  {
    if ( v9 )
    {
      if ( v9 != -2147024871 )
      {
        v10 = 1354;
        v11 = 0;
        v12 = v9;
        goto LABEL_26;
      }
      v23 = *(_QWORD *)this;
      v58 = 0;
      v24 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD))(v23 + 176))(this, 2, 0);
      v9 = v24;
      if ( v24 < 0 )
      {
        v25 = 1358;
        v26 = 1;
        v27 = (unsigned int)v24;
        goto LABEL_29;
      }
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v58 + 120LL))(v58);
LABEL_32:
      if ( v9 )
      {
        if ( v9 == -2147024871 )
        {
          v43 = *(_QWORD *)this;
          v60 = 0;
          v44 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD, _QWORD, _QWORD, __int64 *, __int64 *))(v43 + 136))(
                  this,
                  1,
                  0,
                  0,
                  0,
                  &v84,
                  &v60);
          v9 = v44;
          if ( v44 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 120LL))(v60);
            while ( !v9 )
            {
              v62 = 0;
              v48 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 40LL))(v60, &v62);
              v9 = v48;
              if ( v48 < 0 )
              {
                v53 = 1427;
                goto LABEL_98;
              }
              v88 = 0;
              v89 = 0;
              v48 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 24LL))(v62, &v88);
              v9 = v48;
              if ( v48 < 0 )
              {
                v53 = 1430;
LABEL_98:
                Log_UnistoreHREvent_0(
                  (unsigned int)v48,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
                  v53);
                goto LABEL_99;
              }
              v73[0] = v88;
              v73[1] = 2147483643;
              ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(&v66, a2);
              v67 = 0;
              started = DBAutoTopLevelTransact::StartTransaction(
                          (DBAutoTopLevelTransact *)&v66,
                          3u,
                          2u,
                          (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)v73);
              v9 = started;
              if ( started < 0 )
              {
                v51 = 1440;
LABEL_93:
                v50 = 1;
LABEL_94:
                v52 = (unsigned int)started;
LABEL_95:
                Log_UnistoreHREvent_0(
                  v52,
                  v50,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
                  v51);
                DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)&v66);
LABEL_99:
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v62);
                goto LABEL_79;
              }
              started = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 40LL))(v62);
              v9 = started;
              v50 = 1;
              if ( started < 0 )
              {
                v51 = 1442;
                goto LABEL_94;
              }
              v63 = 0;
              started = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)&v66, 1, &v63);
              v9 = started;
              if ( started < 0 )
              {
                v51 = 1445;
                goto LABEL_93;
              }
              if ( !v63 )
              {
                v9 = -2147418113;
                v51 = 1446;
                v52 = 2147549183LL;
                v50 = 0;
                goto LABEL_95;
              }
              v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 96LL))(v60);
              DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)&v66);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v62);
            }
            if ( v9 == -2147024871 )
            {
              for ( i = v74; i != v14; ++i )
              {
                ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(&v66, *i);
                v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 40LL))(v66);
                v56 = v55;
                if ( v55 < 0 )
                {
                  Log_UnistoreHREvent_0(
                    (unsigned int)v55,
                    1,
                    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
                    1455);
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v66);
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v58);
                  v9 = v56;
                  goto LABEL_108;
                }
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v66);
              }
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v58);
              v9 = 0;
              goto LABEL_108;
            }
            v45 = 1450;
            v46 = 0;
            v47 = v9;
          }
          else
          {
            v45 = 1421;
            v46 = 1;
            v47 = (unsigned int)v44;
          }
          Log_UnistoreHREvent_0(
            v47,
            v46,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
            v45);
LABEL_79:
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
        }
        else
        {
          v25 = 1417;
          v26 = 0;
          v27 = v9;
LABEL_29:
          Log_UnistoreHREvent_0(
            v27,
            v26,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
            v25);
        }
LABEL_30:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v58);
        goto LABEL_108;
      }
      v59 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 40LL))(v58, &v59);
      v9 = v28;
      if ( v28 < 0 )
      {
        v42 = 1364;
        goto LABEL_72;
      }
      v90 = 0;
      v91 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 24LL))(v59, &v90);
      v9 = v28;
      if ( v28 < 0 )
      {
        v42 = 1367;
LABEL_72:
        Log_UnistoreHREvent_0(
          (unsigned int)v28,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v42);
        goto LABEL_73;
      }
      v29 = v59;
      v71[0] = 927137803;
      v71[1] = 29687873;
      v61 = 0;
      v30 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v59 + 48LL);
      tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&v61);
      v31 = v30(v29, 2, v71);
      v9 = v31;
      if ( v31 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v31,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          1371);
        goto LABEL_68;
      }
      v72[0] = v90;
      v72[1] = 2147483643;
      ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(&v88, a2);
      v89 = 0;
      v32 = DBAutoTopLevelTransact::StartTransaction(
              (DBAutoTopLevelTransact *)&v88,
              3u,
              2u,
              (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)v72);
      v9 = v32;
      if ( v32 < 0 )
      {
        v33 = 1381;
        goto LABEL_64;
      }
      if ( (*((_WORD *)v61 + 3) & 0x300) == 0 && *((_DWORD *)v61 + 2) || (*((_WORD *)v61 + 15) & 0x300) != 0 )
      {
        v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 40LL))(v59);
        v9 = v32;
        if ( v32 >= 0 )
          goto LABEL_54;
        v33 = 1385;
        goto LABEL_64;
      }
      v34 = *((_DWORD *)v61 + 8);
      v35 = 0;
      v36 = *((_QWORD *)v61 + 5);
      for ( j = (_DWORD *)v83[0]; ; ++j )
      {
        if ( j == (_DWORD *)v83[1] )
        {
          if ( v35 )
          {
            v77 = 29687873;
            v79 = 0;
            v78 = v34;
            v80 = v36;
            v32 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v59 + 80LL))(
                    v59,
                    1,
                    &v77,
                    0);
            v9 = v32;
            if ( v32 < 0 )
            {
              v33 = 1407;
LABEL_64:
              v40 = (unsigned int)v32;
LABEL_65:
              v41 = 1;
LABEL_66:
              Log_UnistoreHREvent_0(
                v40,
                v41,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
                v33);
              DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)&v88);
LABEL_68:
              if ( v61 )
                LocalFree(v61);
LABEL_73:
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v59);
              goto LABEL_30;
            }
          }
LABEL_54:
          v68 = 0;
          v32 = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)&v88, 1, &v68);
          v9 = v32;
          if ( v32 < 0 )
          {
            v33 = 1412;
            goto LABEL_64;
          }
          if ( !v68 )
          {
            v9 = -2147418113;
            v33 = 1413;
            v40 = 2147549183LL;
            v41 = 0;
            goto LABEL_66;
          }
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v58 + 96LL))(v58);
          DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)&v88);
          if ( v61 )
            LocalFree(v61);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v59);
          goto LABEL_32;
        }
        if ( v34 )
        {
          if ( (unsigned int)(8 * v34) < *j )
            continue;
          v38 = (unsigned int)*j;
          v39 = *j & 7;
          if ( (*(_BYTE *)((v38 >> 3) + v36) & (unsigned __int8)(1 << (*(_BYTE *)j & 7))) == 0 )
            continue;
        }
        else
        {
          v38 = (unsigned int)*j;
          v39 = *j & 7;
        }
        if ( (unsigned int)(8 * v34) <= *j )
        {
          v9 = -2147024809;
          v33 = 1396;
          v40 = 2147942487LL;
          goto LABEL_65;
        }
        v35 = 1;
        *(_BYTE *)((v38 >> 3) + v36) &= ~(1 << v39);
      }
    }
    v64 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 40LL))(v69, &v64);
    v9 = v15;
    if ( v15 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v15,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        1340);
      goto LABEL_23;
    }
    v16 = v64;
    v70 = 327698;
    hMem = 0;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD, void **))(*(_QWORD *)v64 + 48LL);
    v18 = tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
    v19 = v17(v16, 1, &v70, 0, v18);
    v9 = v19;
    if ( v19 < 0 )
    {
      v20 = 1344;
      v21 = 1;
      v22 = (unsigned int)v19;
      goto LABEL_20;
    }
    if ( (*((_WORD *)hMem + 3) & 0x300) == 0 )
      break;
LABEL_13:
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 96LL))(v69);
    if ( hMem )
      LocalFree(hMem);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v64);
  }
  if ( v14 != v76 )
  {
    ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v14++, v64);
    v75 = v14;
    goto LABEL_12;
  }
  if ( utl::vector<ATL::CComPtr<IUSObject>,utl::allocator<ATL::CComPtr<IUSObject>>>::_PushBackOne2<ATL::CComPtr<IUSObject> const &>(
         (__int64 *)&v74,
         &v64) )
  {
    v14 = v75;
LABEL_12:
    v63 = *((unsigned __int16 *)hMem + 4);
    if ( !(unsigned __int8)utl::vector<unsigned int,utl::allocator<unsigned int>>::push_back(v83, &v63) )
    {
      v20 = 1349;
      goto LABEL_18;
    }
    goto LABEL_13;
  }
  v20 = 1348;
LABEL_18:
  v9 = -2147024882;
  v21 = 0;
  v22 = 2147942414LL;
LABEL_20:
  Log_UnistoreHREvent_0(
    v22,
    v21,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v20);
  if ( hMem )
    LocalFree(hMem);
LABEL_23:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v64);
LABEL_108:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v69);
  utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(v83);
  utl::vector<ATL::CComPtr<IUSObject>,utl::allocator<ATL::CComPtr<IUSObject>>>::_Uninit(&v74);
  return v9;
}

```

## disassembly

```asm
0x1800995c0  mov     [rsp-8+arg_10], rbx
0x1800995c5  push    rbp
0x1800995c6  push    rsi
0x1800995c7  push    rdi
0x1800995c8  push    r12
0x1800995ca  push    r13
0x1800995cc  push    r14
0x1800995ce  push    r15
0x1800995d0  lea     rbp, [rsp-60h]
0x1800995d5  sub     rsp, 160h
0x1800995dc  mov     rax, cs:__security_cookie
0x1800995e3  xor     rax, rsp
0x1800995e6  mov     [rbp+90h+var_38], rax
0x1800995ea  xor     eax, eax
0x1800995ec  mov     [rbp+90h+var_70], 4
0x1800995f4  mov     [rbp+90h+var_90], rax
0x1800995f8  xor     r12d, r12d
0x1800995fb  mov     eax, 3743000Bh
0x180099600  mov     [rbp+90h+var_68], 4
0x180099607  mov     [rbp+90h+var_64], eax
0x18009960a  xorps   xmm0, xmm0
0x18009960d  movups  [rbp+90h+var_A0], xmm0
0x180099611  mov     dword ptr [rbp+90h+var_A0], eax
0x180099614  lea     r13d, [r12+1]
0x180099619  lea     rax, [rbp+90h+var_A0]
0x18009961d  mov     dword ptr [rbp+90h+var_A0+8], r13d
0x180099621  mov     r14, rcx
0x180099624  mov     [rbp+90h+var_60], rax
0x180099628  lea     rcx, [rbp+90h+var_D0]
0x18009962c  mov     r15, rdx
0x18009962f  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x180099634  lea     rcx, [rbp+90h+var_88]
0x180099638  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x18009963d  mov     rax, [r14]
0x180099640  lea     rcx, [rbp+90h+var_F8]
0x180099644  mov     [rsp+190h+var_168], rcx
0x180099649  xor     r9d, r9d
0x18009964c  lea     rcx, [rbp+90h+var_70]
0x180099650  mov     [rbp+90h+var_F8], r12
0x180099654  mov     [rsp+190h+var_170], rcx
0x180099659  xor     r8d, r8d
0x18009965c  mov     rax, [rax+48h]
0x180099660  mov     rcx, r14
0x180099663  xor     edx, edx
0x180099665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009966a  mov     ebx, eax
0x18009966c  test    eax, eax
0x18009966e  jns     short loc_180099680
0x180099670  mov     r9d, 536h
0x180099676  mov     edx, r13d
0x180099679  mov     ecx, eax
0x18009967b  jmp     loc_180099816
0x180099680  mov     rcx, [rbp+90h+var_F8]
0x180099684  mov     rax, [rcx]
0x180099687  mov     rax, [rax+78h]
0x18009968b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099690  mov     rdi, [rbp+90h+var_C8]
0x180099694  mov     ebx, eax
0x180099696  test    ebx, ebx
0x180099698  jnz     loc_180099803
0x18009969e  mov     rcx, [rbp+90h+var_F8]
0x1800996a2  lea     rdx, [rsp+190h+var_120]
0x1800996a7  mov     [rsp+190h+var_120], r12
0x1800996ac  mov     rax, [rcx]
0x1800996af  mov     rax, [rax+28h]
0x1800996b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996b8  mov     ebx, eax
0x1800996ba  test    eax, eax
0x1800996bc  js      loc_1800997DD
0x1800996c2  mov     rsi, [rsp+190h+var_120]
0x1800996c7  lea     rcx, [rsp+190h+hMem]
0x1800996cc  mov     [rbp+90h+var_F0], 50012h
0x1800996d3  mov     [rsp+190h+hMem], r12
0x1800996d8  mov     rax, [rsi]
0x1800996db  mov     rbx, [rax+30h]
0x1800996df  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x1800996e4  mov     [rsp+190h+var_170], rax
0x1800996e9  lea     r8, [rbp+90h+var_F0]
0x1800996ed  mov     rax, rbx
0x1800996f0  xor     r9d, r9d
0x1800996f3  mov     edx, r13d
0x1800996f6  mov     rcx, rsi
0x1800996f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996fe  mov     ebx, eax
0x180099700  test    eax, eax
0x180099702  js      loc_1800997B4
0x180099708  mov     rax, [rsp+190h+hMem]
0x18009970d  mov     ecx, 300h
0x180099712  test    [rax+6], cx
0x180099716  jnz     short loc_18009976A
0x180099718  cmp     rdi, [rbp+90h+var_C0]
0x18009971c  jz      short loc_180099735
0x18009971e  mov     rdx, [rsp+190h+var_120]
0x180099723  mov     rcx, rdi
0x180099726  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x18009972b  add     rdi, 8
0x18009972f  mov     [rbp+90h+var_C8], rdi
0x180099733  jmp     short loc_18009974B
0x180099735  lea     rdx, [rsp+190h+var_120]
0x18009973a  lea     rcx, [rbp+90h+var_D0]
0x18009973e  call    ??$_PushBackOne2@AEBV?$CComPtr@UIUSObject@@@ATL@@@?$vector@V?$CComPtr@UIUSObject@@@ATL@@V?$allocator@V?$CComPtr@UIUSObject@@@ATL@@@utl@@@utl@@AEAA_NAEBV?$CComPtr@UIUSObject@@@ATL@@@Z; utl::vector<ATL::CComPtr<IUSObject>,utl::allocator<ATL::CComPtr<IUSObject>>>::_PushBackOne2<ATL::CComPtr<IUSObject> const &>(ATL::CComPtr<IUSObject> const &)
0x180099743  test    al, al
0x180099745  jz      short loc_1800997A3
0x180099747  mov     rdi, [rbp+90h+var_C8]
0x18009974b  mov     rax, [rsp+190h+hMem]
0x180099750  lea     rdx, [rsp+190h+var_128]
0x180099755  movzx   ecx, word ptr [rax+8]
0x180099759  mov     [rsp+190h+var_128], ecx
0x18009975d  lea     rcx, [rbp+90h+var_88]
0x180099761  call    ?push_back@?$vector@IV?$allocator@I@utl@@@utl@@QEAA_N$$QEAI@Z; utl::vector<uint,utl::allocator<uint>>::push_back(uint &&)
0x180099766  test    al, al
0x180099768  jz      short loc_18009979B
0x18009976a  mov     rcx, [rbp+90h+var_F8]
0x18009976e  mov     rax, [rcx]
0x180099771  mov     rax, [rax+60h]
0x180099775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009977a  mov     rcx, [rsp+190h+hMem]; hMem
0x18009977f  mov     ebx, eax
0x180099781  test    rcx, rcx
0x180099784  jz      short loc_18009978C
0x180099786  call    cs:__imp_LocalFree
0x18009978c  lea     rcx, [rsp+190h+var_120]; void *
0x180099791  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180099796  jmp     loc_180099696
0x18009979b  mov     r9d, 545h
0x1800997a1  jmp     short loc_1800997A9
0x1800997a3  mov     r9d, 544h
0x1800997a9  mov     ebx, 8007000Eh
0x1800997ae  xor     edx, edx
0x1800997b0  mov     ecx, ebx
0x1800997b2  jmp     short loc_1800997BF
0x1800997b4  mov     r9d, 540h
0x1800997ba  mov     edx, r13d
0x1800997bd  mov     ecx, eax
0x1800997bf  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800997c6  call    Log_UnistoreHREvent_0
0x1800997cb  mov     rcx, [rsp+190h+hMem]; hMem
0x1800997d0  test    rcx, rcx
0x1800997d3  jz      short loc_1800997F4
0x1800997d5  call    cs:__imp_LocalFree
0x1800997db  jmp     short loc_1800997F4
0x1800997dd  mov     r9d, 53Ch
0x1800997e3  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800997ea  mov     edx, r13d
0x1800997ed  mov     ecx, eax
0x1800997ef  call    Log_UnistoreHREvent_0
0x1800997f4  lea     rcx, [rsp+190h+var_120]; void *
0x1800997f9  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800997fe  jmp     loc_180099E0B
0x180099803  mov     esi, 80070019h
0x180099808  cmp     ebx, esi
0x18009980a  jz      short loc_180099827
0x18009980c  mov     r9d, 54Ah
0x180099812  xor     edx, edx
0x180099814  mov     ecx, ebx
0x180099816  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009981d  call    Log_UnistoreHREvent_0
0x180099822  jmp     loc_180099E0B
0x180099827  mov     rax, [r14]
0x18009982a  lea     rcx, [rsp+190h+var_150]
0x18009982f  mov     [rsp+190h+var_160], rcx
0x180099834  xor     r9d, r9d
0x180099837  mov     [rsp+190h+var_168], r12
0x18009983c  xor     r8d, r8d
0x18009983f  mov     rcx, r14
0x180099842  mov     [rsp+190h+var_150], r12
0x180099847  mov     rax, [rax+0B0h]
0x18009984e  lea     edx, [r9+2]
0x180099852  mov     [rsp+190h+var_170], r12
0x180099857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009985c  mov     ebx, eax
0x18009985e  test    eax, eax
0x180099860  jns     short loc_180099888
0x180099862  mov     r9d, 54Eh
0x180099868  mov     edx, r13d
0x18009986b  mov     ecx, eax
0x18009986d  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180099874  call    Log_UnistoreHREvent_0
0x180099879  lea     rcx, [rsp+190h+var_150]; void *
0x18009987e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180099883  jmp     loc_180099E0B
0x180099888  mov     rcx, [rsp+190h+var_150]
0x18009988d  mov     rax, [rcx]
0x180099890  mov     rax, [rax+78h]
0x180099894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099899  mov     ebx, eax
0x18009989b  test    ebx, ebx
0x18009989d  jnz     loc_180099B78
0x1800998a3  mov     rcx, [rsp+190h+var_150]
0x1800998a8  lea     rdx, [rsp+190h+var_148]
0x1800998ad  mov     [rsp+190h+var_148], r12
0x1800998b2  mov     rax, [rcx]
0x1800998b5  mov     rax, [rax+28h]
0x1800998b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800998be  mov     ebx, eax
0x1800998c0  test    eax, eax
0x1800998c2  js      loc_180099B52
0x1800998c8  mov     rcx, [rsp+190h+var_148]
0x1800998cd  lea     rdx, [rbp+90h+var_48]
0x1800998d1  xor     eax, eax
0x1800998d3  mov     [rbp+90h+var_48], rax
0x1800998d7  mov     [rbp+90h+var_40], eax
0x1800998da  mov     rax, [rcx]
0x1800998dd  mov     rax, [rax+18h]
0x1800998e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800998e6  mov     ebx, eax
0x1800998e8  test    eax, eax
0x1800998ea  js      loc_180099B4A
0x1800998f0  mov     rsi, [rsp+190h+var_148]
0x1800998f5  lea     rcx, [rsp+190h+var_138]
0x1800998fa  mov     [rbp+90h+var_E8], 3743000Bh
0x180099901  mov     [rbp+90h+var_E4], 1C50041h
0x180099908  mov     [rsp+190h+var_138], r12
0x18009990d  mov     rax, [rsi]
0x180099910  mov     rbx, [rax+30h]
0x180099914  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x180099919  xor     r9d, r9d
0x18009991c  mov     [rsp+190h+var_170], rax
0x180099921  lea     r8, [rbp+90h+var_E8]
0x180099925  mov     rcx, rsi
0x180099928  mov     rax, rbx
0x18009992b  lea     edx, [r9+2]
0x18009992f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099934  mov     ebx, eax
0x180099936  test    eax, eax
0x180099938  js      loc_180099B21
0x18009993e  mov     eax, dword ptr [rbp+90h+var_48]
0x180099941  lea     rcx, [rbp+90h+var_58]
0x180099945  mov     rdx, r15
0x180099948  mov     [rbp+90h+var_E0], eax
0x18009994b  mov     [rbp+90h+var_DC], 7FFFFFFBh
0x180099952  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x180099957  mov     edx, 3; unsigned int
0x18009995c  mov     [rbp+90h+var_50], r12d
0x180099960  lea     r9, [rbp+90h+var_E0]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x180099964  lea     rcx, [rbp+90h+var_58]; this
0x180099968  lea     r8d, [rdx-1]; unsigned int
0x18009996c  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x180099971  mov     ebx, eax
0x180099973  test    eax, eax
0x180099975  js      loc_180099AFF
0x18009997b  mov     rax, [rsp+190h+var_138]
0x180099980  mov     ecx, 300h
0x180099985  test    [rax+6], cx
0x180099989  jnz     short loc_180099991
0x18009998b  cmp     [rax+8], r12d
0x18009998f  jnz     short loc_180099997
0x180099991  test    [rax+1Eh], cx
0x180099995  jz      short loc_1800999BD
0x180099997  mov     rcx, [rsp+190h+var_148]
0x18009999c  mov     rax, [rcx]
0x18009999f  mov     rax, [rax+28h]
0x1800999a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800999a8  mov     ebx, eax
0x1800999aa  test    eax, eax
0x1800999ac  jns     loc_180099A74
0x1800999b2  mov     r9d, 569h
0x1800999b8  jmp     loc_180099B05
0x1800999bd  mov     r11d, [rax+20h]
0x1800999c1  mov     bl, r12b
0x1800999c4  mov     rsi, [rax+28h]
0x1800999c8  mov     rax, [rbp+90h+var_88]
0x1800999cc  cmp     rax, [rbp+90h+var_80]
0x1800999d0  jz      short loc_180099A3B
0x1800999d2  test    r11d, r11d
0x1800999d5  jz      short loc_180099A07
0x1800999d7  lea     ecx, ds:0[r11*8]
0x1800999df  cmp     ecx, [rax]
0x1800999e1  jb      short loc_180099A35
0x1800999e3  mov     r10d, [rax]
0x1800999e6  mov     edx, r13d
0x1800999e9  mov     r9d, [rax]
0x1800999ec  mov     ecx, r10d
0x1800999ef  shr     rcx, 3
0x1800999f3  and     r9d, 7
0x1800999f7  mov     r8b, [rcx+rsi]
0x1800999fb  mov     ecx, r9d
0x1800999fe  shl     edx, cl
0x180099a00  test    dl, r8b
0x180099a03  jz      short loc_180099A35
0x180099a05  jmp     short loc_180099A11
0x180099a07  mov     r9d, [rax]
0x180099a0a  mov     r10d, [rax]
0x180099a0d  and     r9d, 7
0x180099a11  lea     ecx, ds:0[r11*8]
0x180099a19  cmp     ecx, [rax]
0x180099a1b  jbe     loc_180099ACF
0x180099a21  shr     r10, 3
0x180099a25  mov     bl, r13b
0x180099a28  movzx   ecx, byte ptr [r10+rsi]
0x180099a2d  btr     ecx, r9d
0x180099a31  mov     [r10+rsi], cl
0x180099a35  add     rax, 4
0x180099a39  jmp     short loc_1800999CC
0x180099a3b  test    bl, bl
0x180099a3d  jz      short loc_180099A74
0x180099a3f  mov     rcx, [rsp+190h+var_148]
0x180099a44  lea     r8, [rbp+90h+var_B8]
0x180099a48  mov     [rbp+90h+var_B8], 1C50041h
0x180099a50  xor     r9d, r9d
  ... truncated ...
```
