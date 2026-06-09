# UnistoreUpgrade::UpgradeMeetingTimezones(IUSStoreManager *,IDBVolume *)

- ea: `0x18009ae10`
- end: `0x18009b2ff`
- name: `?UpgradeMeetingTimezones@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `1263`
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
- `0x18009ae10`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ae65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ae65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b1d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b22c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b1d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b22c`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18009ae5a`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18009ae5a`
- `UserDataTimeUtil!StdTimeZoneInfoFromRen` at `0x18009b15e`
- `UserDataTimeUtil!StdTimeZoneInfoFromRen` at `0x18009b15e`
- `UserDataTimeUtil!ConvertSchedPlusToRenTz` at `0x18009b0be`
- `UserDataTimeUtil!ConvertSchedPlusToRenTz` at `0x18009b0be`

## string_xrefs

- `0x18009ae82`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009b216`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009b261`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009b282`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009b2bf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeMeetingTimezones(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int i; // eax
  int v15; // eax
  int started; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, __int64 *, _QWORD, void **); // rbx
  void **v19; // rax
  int v20; // eax
  HLOCAL v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[8]; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+70h] [rbp-90h]
  int v35; // [rsp+78h] [rbp-88h] BYREF
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  _QWORD v38[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v40; // [rsp+B8h] [rbp-48h]
  __int128 v41; // [rsp+C8h] [rbp-38h]
  __int64 v42; // [rsp+D8h] [rbp-28h] BYREF
  int v43; // [rsp+E0h] [rbp-20h]
  int v44; // [rsp+E4h] [rbp-1Ch]
  __int128 *v45; // [rsp+E8h] [rbp-18h]
  __int64 v46; // [rsp+F0h] [rbp-10h] BYREF
  int v47; // [rsp+F8h] [rbp-8h]
  _OWORD v48[3]; // [rsp+100h] [rbp+0h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v50[9]; // [rsp+1E0h] [rbp+E0h] BYREF
  _OWORD v51[2]; // [rsp+270h] [rbp+170h]

  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  if ( GetTimeZoneInformation(&TimeZoneInformation) == -1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = 350;
    v8 = 0;
    goto LABEL_5;
  }
  v29 = 0;
  v38[0] = L"PR_SPLUS_TIME_ZONE";
  v38[1] = L"Meeting:Timezone";
  v6 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD *, __int64, __int64 *))(*(_QWORD *)this + 208LL))(
         this,
         2,
         v38,
         0x10000,
         &v29);
  if ( (v6 & 0x80000000) != 0 )
  {
    v7 = 363;
    v8 = 1;
LABEL_5:
    Log_UnistoreHREvent_0(
      v6,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      v7);
    return v6;
  }
  v29 |= 0x4100000013uLL;
  v44 = v29;
  v37 = 0;
  v31 = 0;
  v36 = 0;
  LODWORD(v36) = v29;
  DWORD2(v36) = 0;
  v45 = &v36;
  v9 = *(_QWORD *)this;
  v42 = 4;
  v43 = 3;
  v10 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD, _QWORD, _QWORD, __int64 *, __int64 *))(v9 + 184))(
          this,
          196610,
          0,
          0,
          0,
          &v42,
          &v31);
  v6 = v10;
  if ( v10 >= 0 )
  {
    for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 120LL))(v31);
          ;
          i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 96LL))(v31) )
    {
      v6 = i;
      if ( i )
        break;
      v28 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 40LL))(v31, &v28);
      v6 = v15;
      if ( v15 < 0 )
      {
        v26 = 386;
        goto LABEL_37;
      }
      v46 = 0;
      v47 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 24LL))(v28, &v46);
      v6 = v15;
      if ( v15 < 0 )
      {
        v26 = 389;
LABEL_37:
        Log_UnistoreHREvent_0(
          (unsigned int)v15,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v26);
        goto LABEL_38;
      }
      v35 = v46;
      ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v33, a2);
      v34 = 0;
      started = DBAutoTopLevelTransact::StartTransaction(
                  (DBAutoTopLevelTransact *)v33,
                  3u,
                  1u,
                  (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)&v35);
      v6 = started;
      if ( started < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)started,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          400);
        goto LABEL_28;
      }
      v17 = v28;
      hMem = 0;
      v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD, void **))(*(_QWORD *)v28 + 48LL);
      v19 = tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
      v20 = v18(v17, 1, &v29, 0, v19);
      v6 = v20;
      if ( v20 < 0 )
      {
        v24 = 403;
        goto LABEL_30;
      }
      v21 = hMem;
      if ( (*((_WORD *)hMem + 3) & 0x300) != 0 )
        goto LABEL_23;
      v39 = 0;
      LODWORD(v39) = v29;
      WORD3(v39) = 512;
      v40 = 0;
      v41 = 0;
      memset(v48, 0, 44);
      v22 = ConvertSchedPlusToRenTz(*((unsigned int *)hMem + 2), v48);
      v50[0] = *(_OWORD *)&TimeZoneInformation.Bias;
      v50[2] = *(_OWORD *)&TimeZoneInformation.StandardName[14];
      v50[1] = *(_OWORD *)&TimeZoneInformation.StandardName[6];
      v50[4] = *(_OWORD *)&TimeZoneInformation.StandardName[30];
      v50[3] = *(_OWORD *)&TimeZoneInformation.StandardName[22];
      v50[6] = *(_OWORD *)&TimeZoneInformation.DaylightName[4];
      v50[5] = *(_OWORD *)&TimeZoneInformation.StandardDate.wSecond;
      v50[8] = *(_OWORD *)&TimeZoneInformation.DaylightName[20];
      v50[7] = *(_OWORD *)&TimeZoneInformation.DaylightName[12];
      v51[0] = *(_OWORD *)&TimeZoneInformation.DaylightName[28];
      *(_OWORD *)((char *)v51 + 12) = *(_OWORD *)&TimeZoneInformation.DaylightDate.wDayOfWeek;
      if ( v22 >= 0 )
        StdTimeZoneInfoFromRen(v50, v48);
      DWORD2(v40) = HIDWORD(v29);
      *((_QWORD *)&v41 + 1) = v50;
      LODWORD(v41) = 172;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v28 + 80LL))(v28, 2, &v39);
      v6 = v20;
      v23 = 1;
      if ( v20 < 0 )
      {
        v24 = 428;
LABEL_31:
        v25 = (unsigned int)v20;
LABEL_26:
        Log_UnistoreHREvent_0(
          v25,
          v23,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v24);
        if ( hMem )
          LocalFree(hMem);
LABEL_28:
        DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v33);
LABEL_38:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
        goto LABEL_43;
      }
      v32 = 0;
      v20 = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v33, 1, &v32);
      v6 = v20;
      if ( v20 < 0 )
      {
        v24 = 431;
LABEL_30:
        v23 = 1;
        goto LABEL_31;
      }
      if ( !v32 )
      {
        v6 = -2147418113;
        v24 = 432;
        v25 = 2147549183LL;
        v23 = 0;
        goto LABEL_26;
      }
      v21 = hMem;
      if ( hMem )
LABEL_23:
        LocalFree(v21);
      DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v33);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
    }
    if ( i == -2147024871 )
    {
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
      return 0;
    }
    v11 = 434;
    v12 = 0;
    v13 = i;
  }
  else
  {
    v11 = 380;
    v12 = 1;
    v13 = (unsigned int)v10;
  }
  Log_UnistoreHREvent_0(
    v13,
    v12,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v11);
LABEL_43:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
  return v6;
}

```

## disassembly

```asm
0x18009ae10  mov     [rsp-8+arg_10], rbx
0x18009ae15  mov     [rsp-8+arg_18], rdi
0x18009ae1a  push    rbp
0x18009ae1b  push    r14
0x18009ae1d  push    r15
0x18009ae1f  lea     rbp, [rsp-1A0h]
0x18009ae27  sub     rsp, 2A0h
0x18009ae2e  mov     rax, cs:__security_cookie
0x18009ae35  xor     rax, rsp
0x18009ae38  mov     [rbp+1B0h+var_20], rax
0x18009ae3f  mov     r15, rdx
0x18009ae42  mov     rdi, rcx
0x18009ae45  xor     edx, edx; Val
0x18009ae47  lea     rcx, [rbp+1B0h+TimeZoneInformation]; void *
0x18009ae4b  mov     r8d, 0ACh; Size
0x18009ae51  call    memset_0
0x18009ae56  lea     rcx, [rbp+1B0h+TimeZoneInformation]; lpTimeZoneInformation
0x18009ae5a  call    cs:__imp_GetTimeZoneInformation
0x18009ae60  cmp     eax, 0FFFFFFFFh
0x18009ae63  jnz     short loc_18009AE95
0x18009ae65  call    cs:__imp_GetLastError
0x18009ae6b  mov     ebx, eax
0x18009ae6d  test    eax, eax
0x18009ae6f  jle     short loc_18009AE7A
0x18009ae71  movzx   ebx, ax
0x18009ae74  or      ebx, 80070000h
0x18009ae7a  mov     r9d, 15Eh
0x18009ae80  xor     edx, edx
0x18009ae82  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009ae89  mov     ecx, ebx
0x18009ae8b  call    Log_UnistoreHREvent_0
0x18009ae90  jmp     loc_18009B2D5
0x18009ae95  lea     rax, aPrSplusTimeZon; "PR_SPLUS_TIME_ZONE"
0x18009ae9c  mov     [rsp+2B0h+var_268], 0
0x18009aea5  mov     [rbp+1B0h+var_218], rax
0x18009aea9  lea     rcx, [rsp+2B0h+var_268]
0x18009aeae  lea     rax, aMeetingTimezon; "Meeting:Timezone"
0x18009aeb5  mov     [rsp+2B0h+var_290], rcx
0x18009aeba  mov     [rbp+1B0h+var_210], rax
0x18009aebe  lea     r8, [rbp+1B0h+var_218]
0x18009aec2  mov     rax, [rdi]
0x18009aec5  mov     r9d, 10000h
0x18009aecb  mov     edx, 2
0x18009aed0  mov     rcx, rdi
0x18009aed3  mov     rax, [rax+0D0h]
0x18009aeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aedf  mov     ebx, eax
0x18009aee1  test    eax, eax
0x18009aee3  jns     short loc_18009AEF2
0x18009aee5  mov     r9d, 16Bh
0x18009aeeb  mov     edx, 1
0x18009aef0  jmp     short loc_18009AE82
0x18009aef2  mov     eax, dword ptr [rsp+2B0h+var_268]
0x18009aef6  xor     ecx, ecx
0x18009aef8  or      dword ptr [rsp+2B0h+var_268+4], 41h
0x18009aefd  or      eax, 13h
0x18009af00  mov     dword ptr [rsp+2B0h+var_268], eax
0x18009af04  xorps   xmm0, xmm0
0x18009af07  mov     [rbp+1B0h+var_1CC], eax
0x18009af0a  xor     r9d, r9d
0x18009af0d  mov     [rbp+1B0h+var_220], rcx
0x18009af11  xor     r8d, r8d
0x18009af14  mov     [rsp+2B0h+var_258], rcx
0x18009af19  mov     edx, 30002h
0x18009af1e  movups  [rbp+1B0h+var_230], xmm0
0x18009af22  mov     dword ptr [rbp+1B0h+var_230], eax
0x18009af25  lea     rax, [rbp+1B0h+var_230]
0x18009af29  mov     dword ptr [rbp+1B0h+var_230+8], ecx
0x18009af2c  lea     rcx, [rsp+2B0h+var_258]
0x18009af31  mov     [rsp+2B0h+var_280], rcx
0x18009af36  lea     rcx, [rbp+1B0h+var_1D8]
0x18009af3a  mov     [rbp+1B0h+var_1C8], rax
0x18009af3e  mov     rax, [rdi]
0x18009af41  mov     [rsp+2B0h+var_288], rcx
0x18009af46  mov     rcx, rdi
0x18009af49  mov     [rbp+1B0h+var_1D8], 4
0x18009af51  mov     [rbp+1B0h+var_1D0], 3
0x18009af58  mov     rax, [rax+0B8h]
0x18009af5f  mov     [rsp+2B0h+var_290], 0
0x18009af68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af6d  mov     ebx, eax
0x18009af6f  test    eax, eax
0x18009af71  jns     short loc_18009AF85
0x18009af73  mov     r9d, 17Ch
0x18009af79  mov     edx, 1
0x18009af7e  mov     ecx, eax
0x18009af80  jmp     loc_18009B2BF
0x18009af85  mov     rcx, [rsp+2B0h+var_258]
0x18009af8a  mov     rax, [rcx]
0x18009af8d  mov     rax, [rax+78h]
0x18009af91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af96  mov     r14d, 1
0x18009af9c  mov     ebx, eax
0x18009af9e  test    eax, eax
0x18009afa0  jnz     loc_18009B29F
0x18009afa6  mov     rcx, [rsp+2B0h+var_258]
0x18009afab  lea     rdx, [rsp+2B0h+var_270]
0x18009afb0  mov     [rsp+2B0h+var_270], 0
0x18009afb9  mov     rax, [rcx]
0x18009afbc  mov     rax, [rax+28h]
0x18009afc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009afc5  mov     ebx, eax
0x18009afc7  test    eax, eax
0x18009afc9  js      loc_18009B27C
0x18009afcf  mov     rcx, [rsp+2B0h+var_270]
0x18009afd4  lea     rdx, [rbp+1B0h+var_1C0]
0x18009afd8  xor     eax, eax
0x18009afda  mov     [rbp+1B0h+var_1C0], rax
0x18009afde  mov     [rbp+1B0h+var_1B8], eax
0x18009afe1  mov     rax, [rcx]
0x18009afe4  mov     rax, [rax+18h]
0x18009afe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009afed  mov     ebx, eax
0x18009afef  test    eax, eax
0x18009aff1  js      loc_18009B274
0x18009aff7  mov     eax, dword ptr [rbp+1B0h+var_1C0]
0x18009affa  lea     rcx, [rsp+2B0h+var_248]
0x18009afff  mov     rdx, r15
0x18009b002  mov     [rsp+2B0h+var_238], eax
0x18009b006  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x18009b00b  lea     r9, [rsp+2B0h+var_238]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x18009b010  mov     [rsp+2B0h+var_240], 0
0x18009b018  mov     r8d, r14d; unsigned int
0x18009b01b  lea     rcx, [rsp+2B0h+var_248]; this
0x18009b020  mov     edx, 3; unsigned int
0x18009b025  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x18009b02a  mov     ebx, eax
0x18009b02c  test    eax, eax
0x18009b02e  js      loc_18009B25B
0x18009b034  mov     rdi, [rsp+2B0h+var_270]
0x18009b039  lea     rcx, [rsp+2B0h+hMem]
0x18009b03e  mov     [rsp+2B0h+hMem], 0
0x18009b047  mov     rax, [rdi]
0x18009b04a  mov     rbx, [rax+30h]
0x18009b04e  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x18009b053  mov     [rsp+2B0h+var_290], rax
0x18009b058  lea     r8, [rsp+2B0h+var_268]
0x18009b05d  mov     rax, rbx
0x18009b060  xor     r9d, r9d
0x18009b063  mov     edx, r14d
0x18009b066  mov     rcx, rdi
0x18009b069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b06e  mov     ebx, eax
0x18009b070  test    eax, eax
0x18009b072  js      loc_18009B253
0x18009b078  mov     rcx, [rsp+2B0h+hMem]
0x18009b07d  mov     eax, 300h
0x18009b082  test    [rcx+6], ax
0x18009b086  jnz     loc_18009B1D4
0x18009b08c  mov     eax, dword ptr [rsp+2B0h+var_268]
0x18009b090  lea     rdx, [rbp+1B0h+var_1B0]
0x18009b094  xorps   xmm0, xmm0
0x18009b097  movups  [rbp+1B0h+var_208], xmm0
0x18009b09b  mov     dword ptr [rbp+1B0h+var_208], eax
0x18009b09e  mov     eax, 200h
0x18009b0a3  movups  xmmword ptr [rbp+1B0h+var_1A0], xmm0
0x18009b0a7  mov     word ptr [rbp+1B0h+var_208+6], ax
0x18009b0ab  movups  [rbp+1B0h+var_1F8], xmm0
0x18009b0af  movups  [rbp+1B0h+var_1E8], xmm0
0x18009b0b3  movups  [rbp+1B0h+var_1B0], xmm0
0x18009b0b7  movups  xmmword ptr [rbp+1B0h+var_1A0+0Ch], xmm0
0x18009b0bb  mov     ecx, [rcx+8]
0x18009b0be  call    cs:__imp_ConvertSchedPlusToRenTz
0x18009b0c4  movaps  xmm0, xmmword ptr [rbp+1B0h+TimeZoneInformation.Bias]
0x18009b0c8  movaps  xmm1, xmmword ptr [rbp+1B0h+TimeZoneInformation.StandardName+0Ch]
0x18009b0cc  movups  [rbp+1B0h+var_D0], xmm0
0x18009b0d3  movaps  xmm0, xmmword ptr [rbp+1B0h+TimeZoneInformation.StandardName+1Ch]
0x18009b0d7  movups  [rbp+1B0h+var_B0], xmm0
0x18009b0de  movaps  xmm0, xmmword ptr [rbp+1B0h+TimeZoneInformation.StandardName+3Ch]
0x18009b0e2  movups  [rbp+1B0h+var_C0], xmm1
0x18009b0e9  movaps  xmm1, xmmword ptr [rbp+1B0h+TimeZoneInformation.StandardName+2Ch]
0x18009b0ed  movups  [rbp+1B0h+var_90], xmm0
0x18009b0f4  movaps  xmm0, xmmword ptr [rbp+1B0h+TimeZoneInformation.DaylightName+8]
0x18009b0fb  movups  [rbp+1B0h+var_A0], xmm1
0x18009b102  movaps  xmm1, xmmword ptr [rbp+1B0h+TimeZoneInformation.StandardDate.wSecond]
0x18009b109  movups  [rbp+1B0h+var_70], xmm0
0x18009b110  movaps  xmm0, xmmword ptr [rbp+1B0h+TimeZoneInformation.DaylightName+28h]
0x18009b117  movups  [rbp+1B0h+var_80], xmm1
0x18009b11e  movaps  xmm1, xmmword ptr [rbp+1B0h+TimeZoneInformation.DaylightName+18h]
0x18009b125  movups  [rbp+1B0h+var_50], xmm0
0x18009b12c  movups  xmm0, xmmword ptr [rbp+1B0h+TimeZoneInformation.DaylightDate.wDayOfWeek]
0x18009b133  movups  [rbp+1B0h+var_60], xmm1
0x18009b13a  movaps  xmm1, xmmword ptr [rbp+0C0h]
0x18009b141  movups  xmmword ptr [rbp+1B0h+var_40], xmm1
0x18009b148  movups  xmmword ptr [rbp+1B0h+var_40+0Ch], xmm0
0x18009b14f  test    eax, eax
0x18009b151  js      short loc_18009B164
0x18009b153  lea     rdx, [rbp+1B0h+var_1B0]
0x18009b157  lea     rcx, [rbp+1B0h+var_D0]
0x18009b15e  call    cs:__imp_StdTimeZoneInfoFromRen
0x18009b164  mov     eax, dword ptr [rsp+2B0h+var_268+4]
0x18009b168  lea     r8, [rbp+1B0h+var_208]
0x18009b16c  mov     rcx, [rsp+2B0h+var_270]
0x18009b171  xor     r9d, r9d
0x18009b174  mov     dword ptr [rbp+1B0h+var_1F8+8], eax
0x18009b177  lea     rax, [rbp+1B0h+var_D0]
0x18009b17e  mov     qword ptr [rbp+1B0h+var_1E8+8], rax
0x18009b182  mov     dword ptr [rbp+1B0h+var_1E8], 0ACh
0x18009b189  mov     rax, [rcx]
0x18009b18c  lea     edx, [r9+2]
0x18009b190  mov     rax, [rax+50h]
0x18009b194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b199  mov     ebx, eax
0x18009b19b  mov     edx, r14d; int
0x18009b19e  test    eax, eax
0x18009b1a0  js      loc_18009B24B
0x18009b1a6  lea     r8, [rsp+2B0h+var_250]; int *
0x18009b1ab  mov     [rsp+2B0h+var_250], 0
0x18009b1b3  lea     rcx, [rsp+2B0h+var_248]; this
0x18009b1b8  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x18009b1bd  mov     ebx, eax
0x18009b1bf  test    eax, eax
0x18009b1c1  js      short loc_18009B23E
0x18009b1c3  cmp     [rsp+2B0h+var_250], 0
0x18009b1c8  jz      short loc_18009B207
0x18009b1ca  mov     rcx, [rsp+2B0h+hMem]; hMem
0x18009b1cf  test    rcx, rcx
0x18009b1d2  jz      short loc_18009B1DA
0x18009b1d4  call    cs:__imp_LocalFree
0x18009b1da  lea     rcx, [rsp+2B0h+var_248]; this
0x18009b1df  lea     rbx, [rsp+2B0h+var_270]
0x18009b1e4  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009b1e9  mov     rcx, rbx; void *
0x18009b1ec  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009b1f1  mov     rcx, [rsp+2B0h+var_258]
0x18009b1f6  mov     rax, [rcx]
0x18009b1f9  mov     rax, [rax+60h]
0x18009b1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b202  jmp     loc_18009AF9C
0x18009b207  mov     ebx, 8000FFFFh
0x18009b20c  mov     r9d, 1B0h
0x18009b212  mov     ecx, ebx
0x18009b214  xor     edx, edx
0x18009b216  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009b21d  call    Log_UnistoreHREvent_0
0x18009b222  mov     rcx, [rsp+2B0h+hMem]; hMem
0x18009b227  test    rcx, rcx
0x18009b22a  jz      short loc_18009B232
0x18009b22c  call    cs:__imp_LocalFree
0x18009b232  lea     rcx, [rsp+2B0h+var_248]; this
0x18009b237  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009b23c  jmp     short loc_18009B293
0x18009b23e  mov     r9d, 1AFh
0x18009b244  mov     edx, r14d
0x18009b247  mov     ecx, eax
0x18009b249  jmp     short loc_18009B216
0x18009b24b  mov     r9d, 1ACh
0x18009b251  jmp     short loc_18009B247
0x18009b253  mov     r9d, 193h
0x18009b259  jmp     short loc_18009B244
0x18009b25b  mov     r9d, 190h
0x18009b261  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009b268  mov     edx, r14d
0x18009b26b  mov     ecx, eax
0x18009b26d  call    Log_UnistoreHREvent_0
0x18009b272  jmp     short loc_18009B232
0x18009b274  mov     r9d, 185h
0x18009b27a  jmp     short loc_18009B282
0x18009b27c  mov     r9d, 182h
0x18009b282  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009b289  mov     edx, r14d
0x18009b28c  mov     ecx, eax
0x18009b28e  call    Log_UnistoreHREvent_0
0x18009b293  lea     rcx, [rsp+2B0h+var_270]; void *
0x18009b298  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009b29d  jmp     short loc_18009B2CB
0x18009b29f  cmp     ebx, 80070019h
0x18009b2a5  jnz     short loc_18009B2B5
0x18009b2a7  lea     rcx, [rsp+2B0h+var_258]; void *
0x18009b2ac  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009b2b1  xor     eax, eax
0x18009b2b3  jmp     short loc_18009B2D7
0x18009b2b5  mov     r9d, 1B2h
0x18009b2bb  xor     edx, edx
0x18009b2bd  mov     ecx, ebx
0x18009b2bf  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009b2c6  call    Log_UnistoreHREvent_0
0x18009b2cb  lea     rcx, [rsp+2B0h+var_258]; void *
0x18009b2d0  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009b2d5  mov     eax, ebx
0x18009b2d7  mov     rcx, [rbp+1B0h+var_20]
0x18009b2de  xor     rcx, rsp; StackCookie
0x18009b2e1  call    __security_check_cookie
0x18009b2e6  lea     r11, [rsp+2B0h+var_10]
0x18009b2ee  mov     rbx, [r11+30h]
0x18009b2f2  mov     rdi, [r11+38h]
0x18009b2f6  mov     rsp, r11
0x18009b2f9  pop     r15
0x18009b2fb  pop     r14
0x18009b2fd  pop     rbp
0x18009b2fe  retn
```
