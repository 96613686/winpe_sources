# UnistoreUpgrade::UpgradeChangeTrackingData(IUSStoreManager *,IDBVolume *)

- ea: `0x18006d010`
- end: `0x18006d4a5`
- name: `?UpgradeChangeTrackingData@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `1173`
- prototype: `__int64 __fastcall(UnistoreUpgrade *__hidden this, struct IUSStoreManager *, struct IDBVolume *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18001af78`
- `0x18001e2f4`
- `0x18001ecc4`
- `0x180034664`
- `0x180035d40`
- `0x1800576c0`
- `0x180059828`
- `0x18006d010`
- `0x18006dfa4`
- `0x18007aef0`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d32c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d37a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d3af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d32c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d37a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d3af`

## string_xrefs

- `0x18006d364`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18006d395`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18006d404`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18006d427`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18006d463`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeChangeTrackingData(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(UnistoreUpgrade *, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *); // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // r12
  int v12; // eax
  int started; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, _DWORD *); // rbx
  int v16; // eax
  _DWORD *v17; // rax
  int v18; // eax
  __int64 v19; // r8
  struct AppRevisionStoredBlob *v20; // r8
  unsigned int i; // edx
  __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned int v24; // r14d
  int IsValid; // eax
  unsigned int v26; // edi
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r9
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  struct AppRevisionStoredBlob *v37; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[8]; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h]
  _DWORD v43[6]; // [rsp+88h] [rbp-78h] BYREF
  int v44; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v45[2]; // [rsp+A4h] [rbp-5Ch] BYREF
  __int16 v46; // [rsp+A6h] [rbp-5Ah]
  __int128 v47; // [rsp+A8h] [rbp-58h]
  int v48; // [rsp+B8h] [rbp-48h]
  __int16 v49; // [rsp+BEh] [rbp-42h]
  int v50; // [rsp+D0h] [rbp-30h]
  __int16 v51; // [rsp+D6h] [rbp-2Ah]
  int v52; // [rsp+E8h] [rbp-18h]
  __int16 v53; // [rsp+EEh] [rbp-12h]
  int v54; // [rsp+100h] [rbp+0h]
  __int128 v55; // [rsp+108h] [rbp+8h]

  v3 = *(_QWORD *)this;
  v43[0] = 928514113;
  v43[1] = 929562689;
  v5 = *(__int64 (__fastcall **)(UnistoreUpgrade *, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(v3 + 72);
  v43[2] = 929693761;
  v43[3] = 929824833;
  v43[4] = 930086977;
  v43[5] = 930152513;
  v36 = 0;
  v6 = v5(this, 0, 0, 0, 0, &v36);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v11 = GetAndBumpLongRevision();
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 120LL))(v36);
    while ( !v7 )
    {
      v34 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 40LL))(v36, &v34);
      v7 = v12;
      if ( v12 < 0 )
      {
        v32 = 705;
        goto LABEL_44;
      }
      v41 = 0;
      v42 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 24LL))(v34, &v41);
      v7 = v12;
      if ( v12 < 0 )
      {
        v32 = 708;
LABEL_44:
        Log_UnistoreHREvent_0(
          (unsigned int)v12,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v32);
        goto LABEL_45;
      }
      ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v39, a2);
      v40 = 0;
      started = DBAutoTopLevelTransact::StartTransaction(
                  (DBAutoTopLevelTransact *)v39,
                  3u,
                  1u,
                  (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)&v41);
      v7 = started;
      if ( started < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)started,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          714);
        goto LABEL_31;
      }
      hMem = 0;
      v14 = v34;
      v15 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v34 + 48LL);
      tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
      v16 = v15(v14, 6, v43);
      v7 = v16;
      if ( v16 < 0 )
      {
        v30 = 717;
LABEL_37:
        v29 = 1;
LABEL_38:
        v31 = (unsigned int)v16;
LABEL_29:
        Log_UnistoreHREvent_0(
          v31,
          v29,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v30);
        if ( hMem )
          LocalFree(hMem);
LABEL_31:
        DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v39);
LABEL_45:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v34);
        goto LABEL_50;
      }
      memset_0(v45, 0, 0xD4u);
      v17 = hMem;
      v44 = 929890404;
      v46 = 512;
      v48 = 929955905;
      v49 = 512;
      v50 = 928448612;
      v51 = 512;
      if ( (*((_WORD *)hMem + 3) & 0x300) != 0 )
      {
        v24 = 3;
        v23 = 1;
        goto LABEL_15;
      }
      v52 = 928514113;
      v53 = 512;
      v37 = 0;
      v18 = SafeConvertAppRevisionStoredBlob((const struct _USBLOB *)((char *)hMem + 8), &v37);
      v7 = v18;
      if ( v18 < 0 )
      {
        Log_UnistoreHREvent_2((unsigned int)v18, 1, v19, 1268);
        v30 = 745;
        v29 = 1;
LABEL_28:
        v31 = v7;
        goto LABEL_29;
      }
      v20 = v37;
      for ( i = 0; i < *(_DWORD *)v20; *((_QWORD *)v20 + 3 * v22 + 1) = -1 )
        v22 = i++;
      v17 = hMem;
      v23 = 2;
      v54 = 929562689;
      v24 = 5;
      v55 = *(_OWORD *)((char *)hMem + 8);
LABEL_15:
      while ( v23 < 6 )
      {
        if ( (v17[6 * v23 + 1] & 0x1000000) == 0 )
        {
          LODWORD(v37) = 0;
          IsValid = EnsureAppRevisionBlobIsValid((struct _USBLOB *)&v17[6 * v23 + 2], v11, (int *)&v37);
          v26 = IsValid;
          if ( IsValid < 0 )
          {
            Log_UnistoreHREvent_0(
              (unsigned int)IsValid,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
              765);
            if ( hMem )
              LocalFree(hMem);
            DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v39);
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v34);
            v7 = v26;
            goto LABEL_50;
          }
          v17 = hMem;
          if ( (_DWORD)v37 )
          {
            v27 = v24++;
            v28 = 3 * v27;
            *(__int128 *)((char *)&v47 + 8 * v28) = *(_OWORD *)((char *)hMem + 24 * v23 + 8);
            *(_DWORD *)&v45[8 * v28 - 4] = v17[6 * v23];
          }
        }
        ++v23;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, _QWORD))(*(_QWORD *)v34 + 80LL))(v34, v24, &v44, 0);
      v7 = v16;
      v29 = 1;
      if ( v16 < 0 )
      {
        v30 = 775;
        goto LABEL_38;
      }
      v38 = 0;
      v16 = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v39, 1, &v38);
      v7 = v16;
      if ( v16 < 0 )
      {
        v30 = 778;
        goto LABEL_37;
      }
      if ( !v38 )
      {
        v30 = 779;
        v29 = 0;
        v7 = -2147418113;
        goto LABEL_28;
      }
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 96LL))(v36);
      if ( hMem )
        LocalFree(hMem);
      DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v39);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v34);
    }
    if ( v7 == -2147024871 )
    {
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
      return 0;
    }
    v8 = 783;
    v9 = 0;
    v10 = v7;
  }
  else
  {
    v8 = 697;
    v9 = 1;
    v10 = (unsigned int)v6;
  }
  Log_UnistoreHREvent_0(
    v10,
    v9,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v8);
LABEL_50:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
  return v7;
}

```

## disassembly

```asm
0x18006d010  mov     [rsp-8+arg_10], rbx
0x18006d015  push    rbp
0x18006d016  push    rsi
0x18006d017  push    rdi
0x18006d018  push    r12
0x18006d01a  push    r13
0x18006d01c  push    r14
0x18006d01e  push    r15
0x18006d020  lea     rbp, [rsp-90h]
0x18006d028  sub     rsp, 190h
0x18006d02f  mov     rax, cs:__security_cookie
0x18006d036  xor     rax, rsp
0x18006d039  mov     [rbp+0C0h+var_40], rax
0x18006d040  mov     rax, [rcx]
0x18006d043  mov     r13, rdx
0x18006d046  lea     rdx, [rsp+1C0h+var_170]
0x18006d04b  mov     [rbp+0C0h+var_138], 37580041h
0x18006d052  mov     [rsp+1C0h+var_198], rdx
0x18006d057  xor     edi, edi
0x18006d059  xor     r9d, r9d
0x18006d05c  mov     [rbp+0C0h+var_134], 37680041h
0x18006d063  mov     rax, [rax+48h]
0x18006d067  xor     r8d, r8d
0x18006d06a  xor     edx, edx
0x18006d06c  mov     [rbp+0C0h+var_130], 376A0041h
0x18006d073  mov     [rbp+0C0h+var_12C], 376C0041h
0x18006d07a  mov     [rbp+0C0h+var_128], 37700041h
0x18006d081  mov     [rbp+0C0h+var_124], 37710041h
0x18006d088  mov     [rsp+1C0h+var_170], rdi
0x18006d08d  mov     [rsp+1C0h+var_1A0], rdi
0x18006d092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d097  mov     ebx, eax
0x18006d099  test    eax, eax
0x18006d09b  jns     short loc_18006D0AD
0x18006d09d  mov     r9d, 2B9h
0x18006d0a3  lea     edx, [rdi+1]
0x18006d0a6  mov     ecx, eax
0x18006d0a8  jmp     loc_18006D463
0x18006d0ad  call    ?GetAndBumpLongRevision@@YA_KXZ; GetAndBumpLongRevision(void)
0x18006d0b2  mov     rcx, [rsp+1C0h+var_170]
0x18006d0b7  mov     r12, rax
0x18006d0ba  mov     rdx, [rcx]
0x18006d0bd  mov     rax, [rdx+78h]
0x18006d0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0c6  mov     ebx, eax
0x18006d0c8  mov     esi, 1
0x18006d0cd  mov     r14d, 200h
0x18006d0d3  test    ebx, ebx
0x18006d0d5  jnz     loc_18006D443
0x18006d0db  mov     rcx, [rsp+1C0h+var_170]
0x18006d0e0  lea     rdx, [rsp+1C0h+var_180]
0x18006d0e5  mov     [rsp+1C0h+var_180], rdi
0x18006d0ea  mov     rax, [rcx]
0x18006d0ed  mov     rax, [rax+28h]
0x18006d0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0f6  mov     ebx, eax
0x18006d0f8  test    eax, eax
0x18006d0fa  js      loc_18006D421
0x18006d100  mov     rcx, [rsp+1C0h+var_180]
0x18006d105  lea     rdx, [rsp+1C0h+var_148]
0x18006d10a  xor     eax, eax
0x18006d10c  mov     [rsp+1C0h+var_148], rax
0x18006d111  mov     [rbp+0C0h+var_140], eax
0x18006d114  mov     rax, [rcx]
0x18006d117  mov     rax, [rax+18h]
0x18006d11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d120  mov     ebx, eax
0x18006d122  test    eax, eax
0x18006d124  js      loc_18006D419
0x18006d12a  mov     rdx, r13
0x18006d12d  lea     rcx, [rsp+1C0h+var_158]
0x18006d132  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x18006d137  lea     r9, [rsp+1C0h+var_148]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x18006d13c  mov     [rsp+1C0h+var_150], edi
0x18006d140  mov     r8d, esi; unsigned int
0x18006d143  lea     rcx, [rsp+1C0h+var_158]; this
0x18006d148  mov     edx, 3; unsigned int
0x18006d14d  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x18006d152  mov     ebx, eax
0x18006d154  test    eax, eax
0x18006d156  js      loc_18006D3FE
0x18006d15c  mov     [rsp+1C0h+hMem], rdi
0x18006d161  lea     rcx, [rsp+1C0h+hMem]
0x18006d166  mov     rdi, [rsp+1C0h+var_180]
0x18006d16b  mov     rax, [rdi]
0x18006d16e  mov     rbx, [rax+30h]
0x18006d172  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x18006d177  xor     r9d, r9d
0x18006d17a  mov     [rsp+1C0h+var_1A0], rax
0x18006d17f  lea     r8, [rbp+0C0h+var_138]
0x18006d183  mov     rcx, rdi
0x18006d186  mov     rax, rbx
0x18006d189  lea     edx, [r9+6]
0x18006d18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d192  xor     edi, edi
0x18006d194  mov     ebx, eax
0x18006d196  test    eax, eax
0x18006d198  js      loc_18006D3F6
0x18006d19e  xor     edx, edx; Val
0x18006d1a0  lea     rcx, [rbp+0C0h+var_11C]; void *
0x18006d1a4  mov     r8d, 0D4h; Size
0x18006d1aa  call    memset_0
0x18006d1af  mov     rax, [rsp+1C0h+hMem]
0x18006d1b4  mov     ecx, 300h
0x18006d1b9  mov     [rbp+0C0h+var_120], 376D0064h
0x18006d1c0  mov     [rbp+0C0h+var_11A], r14w
0x18006d1c5  mov     [rbp+0C0h+var_108], 376E0041h
0x18006d1cc  mov     [rbp+0C0h+var_102], r14w
0x18006d1d1  mov     [rbp+0C0h+var_F0], 37570064h
0x18006d1d8  mov     [rbp+0C0h+var_EA], r14w
0x18006d1dd  test    [rax+6], cx
0x18006d1e1  jnz     short loc_18006D24E
0x18006d1e3  lea     rcx, [rax+8]; struct _USBLOB *
0x18006d1e7  mov     [rbp+0C0h+var_D8], 37580041h
0x18006d1ee  lea     rdx, [rsp+1C0h+var_168]; struct AppRevisionStoredBlob **
0x18006d1f3  mov     [rbp+0C0h+var_D2], r14w
0x18006d1f8  mov     [rsp+1C0h+var_168], rdi
0x18006d1fd  call    ?SafeConvertAppRevisionStoredBlob@@YAJPEBU_USBLOB@@PEAPEAUAppRevisionStoredBlob@@@Z; SafeConvertAppRevisionStoredBlob(_USBLOB const *,AppRevisionStoredBlob * *)
0x18006d202  mov     ebx, eax
0x18006d204  test    eax, eax
0x18006d206  js      loc_18006D34B
0x18006d20c  mov     r8, [rsp+1C0h+var_168]
0x18006d211  mov     edx, edi
0x18006d213  cmp     [r8], edi
0x18006d216  jbe     short loc_18006D22E
0x18006d218  mov     eax, edx
0x18006d21a  add     edx, esi
0x18006d21c  lea     rcx, [rax+rax*2]
0x18006d220  mov     qword ptr [r8+rcx*8+8], 0FFFFFFFFFFFFFFFFh
0x18006d229  cmp     edx, [r8]
0x18006d22c  jb      short loc_18006D218
0x18006d22e  mov     rax, [rsp+1C0h+hMem]
0x18006d233  mov     ebx, 2
0x18006d238  mov     [rbp+0C0h+var_C0], 37680041h
0x18006d23f  movups  xmm0, xmmword ptr [rax+8]
0x18006d243  lea     r14d, [rbx+3]
0x18006d247  movdqu  [rbp+0C0h+var_B8], xmm0
0x18006d24c  jmp     short loc_18006D257
0x18006d24e  mov     r14d, 3
0x18006d254  mov     rbx, rsi
0x18006d257  cmp     rbx, 6
0x18006d25b  jnb     short loc_18006D2C1
0x18006d25d  lea     r15, [rbx+rbx*2]
0x18006d261  mov     ecx, 100h
0x18006d266  test    [rax+r15*8+6], cx
0x18006d26c  jnz     short loc_18006D2BC
0x18006d26e  lea     rcx, [rax+8]
0x18006d272  mov     dword ptr [rsp+1C0h+var_168], edi
0x18006d276  lea     rcx, [rcx+r15*8]; struct _USBLOB *
0x18006d27a  mov     rdx, r12; unsigned __int64
0x18006d27d  lea     r8, [rsp+1C0h+var_168]; int *
0x18006d282  call    ?EnsureAppRevisionBlobIsValid@@YAJPEAU_USBLOB@@_KPEAH@Z; EnsureAppRevisionBlobIsValid(_USBLOB *,unsigned __int64,int *)
0x18006d287  mov     edi, eax
0x18006d289  test    eax, eax
0x18006d28b  js      loc_18006D38F
0x18006d291  mov     rax, [rsp+1C0h+hMem]
0x18006d296  xor     edi, edi
0x18006d298  cmp     dword ptr [rsp+1C0h+var_168], edi
0x18006d29c  jz      short loc_18006D2BC
0x18006d29e  movups  xmm0, xmmword ptr [rax+r15*8+8]
0x18006d2a4  mov     ecx, r14d
0x18006d2a7  add     r14d, esi
0x18006d2aa  lea     rdx, [rcx+rcx*2]
0x18006d2ae  movdqu  [rbp+rdx*8+0C0h+var_118], xmm0
0x18006d2b4  mov     ecx, [rax+r15*8]
0x18006d2b8  mov     [rbp+rdx*8+0C0h+var_120], ecx
0x18006d2bc  add     rbx, rsi
0x18006d2bf  jmp     short loc_18006D257
0x18006d2c1  mov     rcx, [rsp+1C0h+var_180]
0x18006d2c6  lea     r8, [rbp+0C0h+var_120]
0x18006d2ca  xor     r9d, r9d
0x18006d2cd  mov     edx, r14d
0x18006d2d0  mov     rax, [rcx]
0x18006d2d3  mov     rax, [rax+50h]
0x18006d2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2dc  mov     ebx, eax
0x18006d2de  mov     edx, esi; int
0x18006d2e0  test    eax, eax
0x18006d2e2  js      loc_18006D3EE
0x18006d2e8  lea     r8, [rsp+1C0h+var_160]; int *
0x18006d2ed  mov     [rsp+1C0h+var_160], edi
0x18006d2f1  lea     rcx, [rsp+1C0h+var_158]; this
0x18006d2f6  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x18006d2fb  mov     ebx, eax
0x18006d2fd  test    eax, eax
0x18006d2ff  js      loc_18006D3DF
0x18006d305  cmp     [rsp+1C0h+var_160], edi
0x18006d309  jz      loc_18006D3D0
0x18006d30f  mov     rcx, [rsp+1C0h+var_170]
0x18006d314  mov     rax, [rcx]
0x18006d317  mov     rax, [rax+60h]
0x18006d31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d320  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18006d325  mov     ebx, eax
0x18006d327  test    rcx, rcx
0x18006d32a  jz      short loc_18006D332
0x18006d32c  call    cs:__imp_LocalFree
0x18006d332  lea     rcx, [rsp+1C0h+var_158]; this
0x18006d337  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18006d33c  lea     rcx, [rsp+1C0h+var_180]; void *
0x18006d341  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18006d346  jmp     loc_18006D0CD
0x18006d34b  mov     r9d, 4F4h
0x18006d351  mov     edx, esi
0x18006d353  mov     ecx, ebx
0x18006d355  call    Log_UnistoreHREvent_2
0x18006d35a  mov     r9d, 2E9h
0x18006d360  mov     edx, esi
0x18006d362  mov     ecx, ebx
0x18006d364  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006d36b  call    Log_UnistoreHREvent_0
0x18006d370  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18006d375  test    rcx, rcx
0x18006d378  jz      short loc_18006D380
0x18006d37a  call    cs:__imp_LocalFree
0x18006d380  lea     rcx, [rsp+1C0h+var_158]; this
0x18006d385  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18006d38a  jmp     loc_18006D437
0x18006d38f  mov     r9d, 2FDh
0x18006d395  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006d39c  mov     edx, esi
0x18006d39e  mov     ecx, edi
0x18006d3a0  call    Log_UnistoreHREvent_0
0x18006d3a5  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18006d3aa  test    rcx, rcx
0x18006d3ad  jz      short loc_18006D3B5
0x18006d3af  call    cs:__imp_LocalFree
0x18006d3b5  lea     rcx, [rsp+1C0h+var_158]; this
0x18006d3ba  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18006d3bf  lea     rcx, [rsp+1C0h+var_180]; void *
0x18006d3c4  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18006d3c9  mov     ebx, edi
0x18006d3cb  jmp     loc_18006D46F
0x18006d3d0  mov     r9d, 30Bh
0x18006d3d6  xor     edx, edx
0x18006d3d8  mov     ebx, 8000FFFFh
0x18006d3dd  jmp     short loc_18006D362
0x18006d3df  mov     r9d, 30Ah
0x18006d3e5  mov     edx, esi
0x18006d3e7  mov     ecx, eax
0x18006d3e9  jmp     loc_18006D364
0x18006d3ee  mov     r9d, 307h
0x18006d3f4  jmp     short loc_18006D3E7
0x18006d3f6  mov     r9d, 2CDh
0x18006d3fc  jmp     short loc_18006D3E5
0x18006d3fe  mov     r9d, 2CAh
0x18006d404  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006d40b  mov     edx, esi
0x18006d40d  mov     ecx, eax
0x18006d40f  call    Log_UnistoreHREvent_0
0x18006d414  jmp     loc_18006D380
0x18006d419  mov     r9d, 2C4h
0x18006d41f  jmp     short loc_18006D427
0x18006d421  mov     r9d, 2C1h
0x18006d427  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006d42e  mov     edx, esi
0x18006d430  mov     ecx, eax
0x18006d432  call    Log_UnistoreHREvent_0
0x18006d437  lea     rcx, [rsp+1C0h+var_180]; void *
0x18006d43c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18006d441  jmp     short loc_18006D46F
0x18006d443  cmp     ebx, 80070019h
0x18006d449  jnz     short loc_18006D459
0x18006d44b  lea     rcx, [rsp+1C0h+var_170]; void *
0x18006d450  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18006d455  xor     eax, eax
0x18006d457  jmp     short loc_18006D47B
0x18006d459  mov     r9d, 30Fh
0x18006d45f  xor     edx, edx
0x18006d461  mov     ecx, ebx
0x18006d463  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006d46a  call    Log_UnistoreHREvent_0
0x18006d46f  lea     rcx, [rsp+1C0h+var_170]; void *
0x18006d474  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18006d479  mov     eax, ebx
0x18006d47b  mov     rcx, [rbp+0C0h+var_40]
0x18006d482  xor     rcx, rsp; StackCookie
0x18006d485  call    __security_check_cookie
0x18006d48a  mov     rbx, [rsp+1C0h+arg_10]
0x18006d492  add     rsp, 190h
0x18006d499  pop     r15
0x18006d49b  pop     r14
0x18006d49d  pop     r13
0x18006d49f  pop     r12
0x18006d4a1  pop     rdi
0x18006d4a2  pop     rsi
0x18006d4a3  pop     rbp
0x18006d4a4  retn
```
