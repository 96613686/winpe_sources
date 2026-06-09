# CSyncMetadata::CreateTypeMetadata(US_OBJECTTYPE,IDBVolume *,unsigned __int64,ulong,ulong)

- ea: `0x1800b23b8`
- end: `0x1800b2814`
- name: `?CreateTypeMetadata@CSyncMetadata@@CAJW4US_OBJECTTYPE@@PEAVIDBVolume@@_KKK@Z`
- size: `1116`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b2e10`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x1800230ac`
- `0x18003e870`
- `0x180051a70`
- `0x180059828`
- `0x1800738b4`
- `0x1800b23b8`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b272f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b272f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2773`

## string_xrefs

- `0x1800b240f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncmetadata.cpp`
- `0x1800b24a9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncmetadata.cpp`
- `0x1800b2756`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncmetadata.cpp`
- `0x1800b2789`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncmetadata.cpp`
- `0x1800b27d2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncmetadata.cpp`

## pseudocode

```c
__int64 __fastcall CSyncMetadata::CreateTypeMetadata(
        __int64 a1,
        __int64 *a2,
        unsigned __int64 a3,
        int a4,
        unsigned int a5)
{
  unsigned int v7; // esi
  int TableFromObjectType; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64 *, _QWORD, _QWORD, __int64 *, _QWORD, unsigned int, __int64 *); // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *); // rbx
  unsigned int MetadataTableIdFromObjectType; // eax
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // r14d
  int i; // eax
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, _DWORD *, void **, _QWORD); // rbx
  void **v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  unsigned int *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v36; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h]
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  __int128 *v45; // [rsp+88h] [rbp-78h]
  _QWORD v46[2]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v47[4]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v48[4]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 *v49; // [rsp+C0h] [rbp-40h]
  _DWORD v50[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v51; // [rsp+D8h] [rbp-28h]
  int v52; // [rsp+E0h] [rbp-20h]
  int v53; // [rsp+F8h] [rbp-8h]
  unsigned int v54; // [rsp+100h] [rbp+0h]
  int v55; // [rsp+110h] [rbp+10h]
  unsigned int v56; // [rsp+118h] [rbp+18h]
  int v57; // [rsp+128h] [rbp+28h]
  int v58; // [rsp+130h] [rbp+30h]
  int v59; // [rsp+140h] [rbp+40h]
  unsigned int v60; // [rsp+148h] [rbp+48h]
  unsigned __int64 v61; // [rsp+1D0h] [rbp+D0h] BYREF

  v61 = a3;
  LODWORD(hMem) = -1;
  v7 = a1;
  TableFromObjectType = GetTableFromObjectType(a1, &hMem, 0);
  v9 = TableFromObjectType;
  if ( TableFromObjectType >= 0 )
  {
    v42 = 0;
    v44 = 0x2000300000000LL;
    v40 = 0;
    v43 = 4;
    v45 = &v41;
    v10 = *a2;
    LODWORD(v44) = 4;
    v41 = 0;
    v11 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 *, _QWORD, unsigned int, __int64 *))(v10 + 40);
    LODWORD(v41) = 131075;
    DWORD2(v41) = a4;
    v12 = v11(a2, (unsigned int)hMem, a5, &v43, 0, 0x80000000, &v40);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v13 = *a2;
      v38 = 0;
      v14 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *))(v13 + 32);
      MetadataTableIdFromObjectType = GetMetadataTableIdFromObjectType(v7);
      v16 = v14(a2, MetadataTableIdFromObjectType, 0, 0, &v38);
      v9 = v16;
      if ( v16 >= 0 )
      {
        v46[1] = v61;
        v61 = _byteswap_uint64(v61);
        v46[0] = 0;
        v48[1] = 0;
        v48[3] = 0;
        memset_0(v50, 0, 0x90u);
        v47[0] = 65539;
        v49 = &v61;
        v47[1] = 131075;
        v51 = v46;
        v47[2] = 235470867;
        v48[0] = -2079915967;
        v48[2] = 8;
        v50[0] = -2080178111;
        v50[2] = 16;
        v52 = -2079981549;
        v53 = -2080374765;
        v55 = 131075;
        if ( v7 != 0x20000 )
        {
          v57 = -2080243693;
          v59 = -2080309229;
          v60 = v7;
        }
        v20 = 7;
        if ( v7 == 0x20000 )
          v20 = 5;
        for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 80LL))(v40);
              ;
              i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 96LL))(v40) )
        {
          v9 = i;
          if ( i < 0 )
            break;
          v39 = 0;
          v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 112LL))(v40, &v39);
          v9 = v22;
          if ( v22 < 0 )
          {
            Log_UnistoreHREvent_0(
              (unsigned int)v22,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\syncmetadata.cpp",
              1310);
            goto LABEL_38;
          }
          v23 = v39;
          hMem = 0;
          v24 = *(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, void **, _QWORD))(*(_QWORD *)v39 + 40LL);
          v25 = tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
          v26 = v24(v23, (unsigned int)(v7 != 0x20000) + 2, v47, v25, 0);
          v9 = v26;
          if ( v26 < 0 )
          {
            v34 = 1313;
            goto LABEL_34;
          }
          v28 = (unsigned int *)hMem;
          v29 = *((unsigned __int16 *)hMem + 3);
          LOWORD(v29) = v29 & 0x100;
          if ( (_WORD)v29 )
          {
            Log_AssertionEvent_7(v27, v29, 1316);
            v28 = (unsigned int *)hMem;
          }
          v30 = v28[2];
          v54 = v28[2];
          if ( v28[8] != a4 )
          {
            Log_AssertionEvent_7(v30, v29, 1321);
            v28 = (unsigned int *)hMem;
          }
          v31 = *((unsigned __int16 *)v28 + 15);
          LOWORD(v31) = v31 & 0x100;
          if ( (_WORD)v31 )
          {
            Log_AssertionEvent_7(v30, v31, 1322);
            v28 = (unsigned int *)hMem;
          }
          v32 = v28[8];
          v56 = v28[8];
          if ( v7 == 458754 )
          {
            v58 = -2;
          }
          else if ( v7 == 458756 )
          {
            v58 = -3;
          }
          else if ( v7 != 0x20000 )
          {
            v33 = *((unsigned __int16 *)v28 + 27);
            LOWORD(v33) = v33 & 0x100;
            if ( (_WORD)v33 )
            {
              Log_AssertionEvent_7(v32, v33, 1336);
              v28 = (unsigned int *)hMem;
            }
            v58 = v28[14];
          }
          LODWORD(v36) = 0;
          v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, __int64, _QWORD))(*(_QWORD *)v38 + 40LL))(
                  v38,
                  0,
                  v20,
                  v48,
                  v36,
                  0);
          v9 = v26;
          if ( v26 < 0 )
          {
            v34 = 1340;
LABEL_34:
            Log_UnistoreHREvent_0(
              (unsigned int)v26,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\syncmetadata.cpp",
              v34);
            if ( hMem )
              LocalFree(hMem);
LABEL_38:
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v39);
            goto LABEL_43;
          }
          ATL::CComPtr<IDBFilter>::operator=(&v39, 0);
          if ( hMem )
            LocalFree(hMem);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v39);
        }
        if ( i == -2147024871 )
        {
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v40);
          return 0;
        }
        v17 = 1344;
        v18 = 0;
        v19 = (unsigned int)i;
      }
      else
      {
        v17 = 1264;
        v18 = 1;
        v19 = (unsigned int)v16;
      }
      Log_UnistoreHREvent_0(
        v19,
        v18,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\syncmetadata.cpp",
        v17);
LABEL_43:
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    }
    else
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\syncmetadata.cpp",
        1261);
    }
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v40);
  }
  else
  {
    Log_UnistoreHREvent_0(
      (unsigned int)TableFromObjectType,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\syncmetadata.cpp",
      1242);
  }
  return v9;
}

```

## disassembly

```asm
0x1800b23b8  mov     [rsp-8+arg_10], r8
0x1800b23bd  push    rbp
0x1800b23be  push    rbx
0x1800b23bf  push    rsi
0x1800b23c0  push    rdi
0x1800b23c1  push    r12
0x1800b23c3  push    r13
0x1800b23c5  push    r14
0x1800b23c7  push    r15
0x1800b23c9  lea     rbp, [rsp-78h]
0x1800b23ce  sub     rsp, 178h
0x1800b23d5  mov     rax, cs:__security_cookie
0x1800b23dc  xor     rax, rsp
0x1800b23df  mov     [rbp+0B0h+var_50], rax
0x1800b23e3  mov     rdi, rdx
0x1800b23e6  mov     dword ptr [rsp+1B0h+hMem], 0FFFFFFFFh
0x1800b23ee  lea     rdx, [rsp+1B0h+hMem]
0x1800b23f3  xor     r8d, r8d
0x1800b23f6  mov     r15d, r9d
0x1800b23f9  mov     esi, ecx
0x1800b23fb  call    ?GetTableFromObjectType@@YAJW4US_OBJECTTYPE@@PEAW4US_TABLEID@@1@Z; GetTableFromObjectType(US_OBJECTTYPE,US_TABLEID *,US_TABLEID *)
0x1800b2400  xor     r12d, r12d
0x1800b2403  mov     ebx, eax
0x1800b2405  test    eax, eax
0x1800b2407  jns     short loc_1800B2427
0x1800b2409  mov     r9d, 4DAh
0x1800b240f  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2416  lea     edx, [r12+1]
0x1800b241b  mov     ecx, eax
0x1800b241d  call    Log_UnistoreHREvent_0
0x1800b2422  jmp     loc_1800B27F2
0x1800b2427  mov     r8d, [rbp+0B0h+arg_20]
0x1800b242e  lea     r9, [rsp+1B0h+var_138]
0x1800b2433  mov     edx, dword ptr [rsp+1B0h+hMem]
0x1800b2437  xor     eax, eax
0x1800b2439  mov     [rsp+1B0h+var_140], rax
0x1800b243e  xorps   xmm0, xmm0
0x1800b2441  movups  [rbp+0B0h+var_130], xmm0
0x1800b2445  mov     r14d, 20003h
0x1800b244b  mov     [rsp+1B0h+var_158], r12
0x1800b2450  lea     ecx, [rax+4]
0x1800b2453  mov     dword ptr [rbp+0B0h+var_130+4], r14d
0x1800b2457  mov     [rsp+1B0h+var_138], rcx
0x1800b245c  lea     rax, [rsp+1B0h+var_150]
0x1800b2461  mov     qword ptr [rbp+0B0h+var_130+8], rax
0x1800b2465  mov     rax, [rdi]
0x1800b2468  mov     dword ptr [rbp+0B0h+var_130], ecx
0x1800b246b  lea     rcx, [rsp+1B0h+var_158]
0x1800b2470  mov     [rsp+1B0h+var_180], rcx
0x1800b2475  mov     rcx, rdi
0x1800b2478  movups  [rsp+1B0h+var_150], xmm0
0x1800b247d  mov     rax, [rax+28h]
0x1800b2481  mov     dword ptr [rsp+1B0h+var_188], 80000000h
0x1800b2489  mov     dword ptr [rsp+1B0h+var_150], r14d
0x1800b248e  mov     dword ptr [rsp+1B0h+var_150+8], r15d
0x1800b2493  mov     [rsp+1B0h+var_190], r12
0x1800b2498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b249d  mov     ebx, eax
0x1800b249f  test    eax, eax
0x1800b24a1  jns     short loc_1800B24C1
0x1800b24a3  mov     r9d, 4EDh
0x1800b24a9  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b24b0  mov     edx, 1
0x1800b24b5  mov     ecx, eax
0x1800b24b7  call    Log_UnistoreHREvent_0
0x1800b24bc  jmp     loc_1800B27E8
0x1800b24c1  mov     rax, [rdi]
0x1800b24c4  mov     ecx, esi
0x1800b24c6  mov     [rsp+1B0h+var_168], r12
0x1800b24cb  mov     rbx, [rax+20h]
0x1800b24cf  call    ?GetMetadataTableIdFromObjectType@@YA?AW4US_TABLEID@@W4US_OBJECTTYPE@@@Z; GetMetadataTableIdFromObjectType(US_OBJECTTYPE)
0x1800b24d4  lea     rcx, [rsp+1B0h+var_168]
0x1800b24d9  mov     edx, eax
0x1800b24db  mov     [rsp+1B0h+var_190], rcx
0x1800b24e0  xor     r9d, r9d
0x1800b24e3  mov     rcx, rdi
0x1800b24e6  xor     r8d, r8d
0x1800b24e9  mov     rax, rbx
0x1800b24ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b24f1  mov     ebx, eax
0x1800b24f3  test    eax, eax
0x1800b24f5  jns     short loc_1800B2509
0x1800b24f7  mov     r9d, 4F0h
0x1800b24fd  mov     edx, 1
0x1800b2502  mov     ecx, eax
0x1800b2504  jmp     loc_1800B27D2
0x1800b2509  mov     rax, [rbp+0B0h+arg_10]
0x1800b2510  lea     rcx, [rbp+0B0h+var_E8]; void *
0x1800b2514  mov     [rbp+0B0h+var_118], rax
0x1800b2518  xor     edx, edx; Val
0x1800b251a  bswap   rax
0x1800b251d  mov     r8d, 90h; Size
0x1800b2523  mov     [rbp+0B0h+arg_10], rax
0x1800b252a  mov     [rbp+0B0h+var_120], r12
0x1800b252e  mov     [rbp+0B0h+var_FC], r12d
0x1800b2532  mov     [rbp+0B0h+var_F4], r12d
0x1800b2536  call    memset_0
0x1800b253b  lea     rax, [rbp+0B0h+arg_10]
0x1800b2542  mov     [rbp+0B0h+var_110], 10003h
0x1800b2549  mov     [rbp+0B0h+var_F0], rax
0x1800b254d  mov     r13d, 20000h
0x1800b2553  mov     [rbp+0B0h+var_10C], r14d
0x1800b2557  lea     rax, [rbp+0B0h+var_120]
0x1800b255b  mov     [rbp+0B0h+var_D8], rax
0x1800b255f  mov     [rbp+0B0h+var_108], 0E090013h
0x1800b2566  mov     [rbp+0B0h+var_100], 84070041h
0x1800b256d  mov     [rbp+0B0h+var_F8], 8
0x1800b2574  mov     [rbp+0B0h+var_E8], 84030041h
0x1800b257b  mov     [rbp+0B0h+var_E0], 10h
0x1800b2582  mov     [rbp+0B0h+var_D0], 84060013h
0x1800b2589  mov     [rbp+0B0h+var_B8], 84000013h
0x1800b2590  mov     [rbp+0B0h+var_A0], r14d
0x1800b2594  cmp     esi, r13d
0x1800b2597  jz      short loc_1800B25AA
0x1800b2599  mov     [rbp+0B0h+var_88], 84020013h
0x1800b25a0  mov     [rbp+0B0h+var_70], 84010013h
0x1800b25a7  mov     [rbp+0B0h+var_68], esi
0x1800b25aa  mov     rcx, [rsp+1B0h+var_158]
0x1800b25af  mov     eax, 5
0x1800b25b4  lea     r14d, [rax+2]
0x1800b25b8  cmovz   r14d, eax
0x1800b25bc  mov     rax, [rcx]
0x1800b25bf  mov     rax, [rax+50h]
0x1800b25c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b25c8  mov     ebx, eax
0x1800b25ca  test    eax, eax
0x1800b25cc  js      loc_1800B27A8
0x1800b25d2  mov     rcx, [rsp+1B0h+var_158]
0x1800b25d7  lea     rdx, [rsp+1B0h+var_160]
0x1800b25dc  mov     [rsp+1B0h+var_160], r12
0x1800b25e1  mov     rax, [rcx]
0x1800b25e4  mov     rax, [rax+70h]
0x1800b25e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b25ed  mov     ebx, eax
0x1800b25ef  test    eax, eax
0x1800b25f1  js      loc_1800B2783
0x1800b25f7  mov     rdi, [rsp+1B0h+var_160]
0x1800b25fc  lea     rcx, [rsp+1B0h+hMem]
0x1800b2601  mov     [rsp+1B0h+hMem], r12
0x1800b2606  mov     rax, [rdi]
0x1800b2609  mov     rbx, [rax+28h]
0x1800b260d  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x1800b2612  mov     edx, r12d
0x1800b2615  mov     [rsp+1B0h+var_190], r12
0x1800b261a  mov     r9, rax
0x1800b261d  lea     r8, [rbp+0B0h+var_110]
0x1800b2621  cmp     esi, r13d
0x1800b2624  mov     rcx, rdi
0x1800b2627  mov     rax, rbx
0x1800b262a  setnz   dl
0x1800b262d  add     edx, 2
0x1800b2630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2635  mov     ebx, eax
0x1800b2637  test    eax, eax
0x1800b2639  js      loc_1800B277B
0x1800b263f  mov     rax, [rsp+1B0h+hMem]
0x1800b2644  mov     edi, 100h
0x1800b2649  movzx   edx, word ptr [rax+6]
0x1800b264d  and     dx, di
0x1800b2650  cmp     r12w, dx
0x1800b2654  jz      short loc_1800B2666
0x1800b2656  mov     r8d, 524h
0x1800b265c  call    Log_AssertionEvent_7
0x1800b2661  mov     rax, [rsp+1B0h+hMem]
0x1800b2666  mov     ecx, [rax+8]
0x1800b2669  mov     [rbp+0B0h+var_B0], ecx
0x1800b266c  cmp     [rax+20h], r15d
0x1800b2670  jz      short loc_1800B2682
0x1800b2672  mov     r8d, 529h
0x1800b2678  call    Log_AssertionEvent_7
0x1800b267d  mov     rax, [rsp+1B0h+hMem]
0x1800b2682  movzx   edx, word ptr [rax+1Eh]
0x1800b2686  and     dx, di
0x1800b2689  cmp     r12w, dx
0x1800b268d  jz      short loc_1800B269F
0x1800b268f  mov     r8d, 52Ah
0x1800b2695  call    Log_AssertionEvent_7
0x1800b269a  mov     rax, [rsp+1B0h+hMem]
0x1800b269f  mov     ecx, [rax+20h]
0x1800b26a2  mov     [rbp+0B0h+var_98], ecx
0x1800b26a5  cmp     esi, 70002h
0x1800b26ab  jnz     short loc_1800B26B6
0x1800b26ad  mov     [rbp+0B0h+var_80], 0FFFFFFFEh
0x1800b26b4  jmp     short loc_1800B26EF
0x1800b26b6  cmp     esi, 70004h
0x1800b26bc  jnz     short loc_1800B26C7
0x1800b26be  mov     [rbp+0B0h+var_80], 0FFFFFFFDh
0x1800b26c5  jmp     short loc_1800B26EF
0x1800b26c7  cmp     esi, r13d
0x1800b26ca  jz      short loc_1800B26EF
0x1800b26cc  movzx   edx, word ptr [rax+36h]
0x1800b26d0  and     dx, di
0x1800b26d3  cmp     r12w, dx
0x1800b26d7  jz      short loc_1800B26E9
0x1800b26d9  mov     r8d, 538h
0x1800b26df  call    Log_AssertionEvent_7
0x1800b26e4  mov     rax, [rsp+1B0h+hMem]
0x1800b26e9  mov     ecx, [rax+38h]
0x1800b26ec  mov     [rbp+0B0h+var_80], ecx
0x1800b26ef  mov     rcx, [rsp+1B0h+var_168]
0x1800b26f4  lea     r9, [rbp+0B0h+var_100]
0x1800b26f8  mov     [rsp+1B0h+var_188], r12
0x1800b26fd  mov     r8d, r14d
0x1800b2700  xor     edx, edx
0x1800b2702  mov     dword ptr [rsp+1B0h+var_190], r12d
0x1800b2707  mov     rax, [rcx]
0x1800b270a  mov     rax, [rax+28h]
0x1800b270e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2713  mov     ebx, eax
0x1800b2715  test    eax, eax
0x1800b2717  js      short loc_1800B2750
0x1800b2719  xor     edx, edx
0x1800b271b  lea     rcx, [rsp+1B0h+var_160]
0x1800b2720  call    ??4?$CComPtr@UIDBFilter@@@ATL@@QEAAPEAUIDBFilter@@PEAU2@@Z; ATL::CComPtr<IDBFilter>::operator=(IDBFilter *)
0x1800b2725  mov     rcx, [rsp+1B0h+hMem]; hMem
0x1800b272a  test    rcx, rcx
0x1800b272d  jz      short loc_1800B2735
0x1800b272f  call    cs:__imp_LocalFree
0x1800b2735  lea     rcx, [rsp+1B0h+var_160]; void *
0x1800b273a  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800b273f  mov     rcx, [rsp+1B0h+var_158]
0x1800b2744  mov     rax, [rcx]
0x1800b2747  mov     rax, [rax+60h]
0x1800b274b  jmp     loc_1800B25C3
0x1800b2750  mov     r9d, 53Ch
0x1800b2756  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b275d  mov     edx, 1
0x1800b2762  mov     ecx, eax
0x1800b2764  call    Log_UnistoreHREvent_0
0x1800b2769  mov     rcx, [rsp+1B0h+hMem]; hMem
0x1800b276e  test    rcx, rcx
0x1800b2771  jz      short loc_1800B279C
0x1800b2773  call    cs:__imp_LocalFree
0x1800b2779  jmp     short loc_1800B279C
0x1800b277b  mov     r9d, 521h
0x1800b2781  jmp     short loc_1800B2756
0x1800b2783  mov     r9d, 51Eh
0x1800b2789  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b2790  mov     edx, 1
0x1800b2795  mov     ecx, eax
0x1800b2797  call    Log_UnistoreHREvent_0
0x1800b279c  lea     rcx, [rsp+1B0h+var_160]; void *
0x1800b27a1  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800b27a6  jmp     short loc_1800B27DE
0x1800b27a8  cmp     ebx, 80070019h
0x1800b27ae  jnz     short loc_1800B27C8
0x1800b27b0  lea     rcx, [rsp+1B0h+var_168]; void *
0x1800b27b5  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800b27ba  lea     rcx, [rsp+1B0h+var_158]; void *
0x1800b27bf  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800b27c4  xor     eax, eax
0x1800b27c6  jmp     short loc_1800B27F4
0x1800b27c8  mov     r9d, 540h
0x1800b27ce  xor     edx, edx
0x1800b27d0  mov     ecx, ebx
0x1800b27d2  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b27d9  call    Log_UnistoreHREvent_0
0x1800b27de  lea     rcx, [rsp+1B0h+var_168]; void *
0x1800b27e3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800b27e8  lea     rcx, [rsp+1B0h+var_158]; void *
0x1800b27ed  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800b27f2  mov     eax, ebx
0x1800b27f4  mov     rcx, [rbp+0B0h+var_50]
0x1800b27f8  xor     rcx, rsp; StackCookie
0x1800b27fb  call    __security_check_cookie
0x1800b2800  add     rsp, 178h
0x1800b2807  pop     r15
0x1800b2809  pop     r14
0x1800b280b  pop     r13
0x1800b280d  pop     r12
0x1800b280f  pop     rdi
0x1800b2810  pop     rsi
0x1800b2811  pop     rbx
0x1800b2812  pop     rbp
0x1800b2813  retn
```
