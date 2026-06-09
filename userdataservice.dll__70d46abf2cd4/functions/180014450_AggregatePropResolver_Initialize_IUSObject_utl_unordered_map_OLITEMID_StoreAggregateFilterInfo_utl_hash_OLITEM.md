# AggregatePropResolver::Initialize(IUSObject *,utl::unordered_map<OLITEMID,StoreAggregateFilterInfo,utl::hash<OLITEMID>,utl::equal_to<OLITEMID>,utl::allocator<utl::pair<OLITEMID const,StoreAggregateFilterInfo>>> *,utl::vector<ulong,utl::allocator<ulong>> const &)

- ea: `0x180014450`
- end: `0x180014970`
- name: `?Initialize@AggregatePropResolver@@AEAAJPEAUIUSObject@@PEAV?$unordered_map@UOLITEMID@@UStoreAggregateFilterInfo@@U?$hash@UOLITEMID@@@utl@@U?$equal_to@UOLITEMID@@@4@V?$allocator@U?$pair@$$CBUOLITEMID@@UStoreAggregateFilterInfo@@@utl@@@4@@utl@@AEBV?$vector@KV?$allocator@K@utl@@@4@@Z`
- size: `1312`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180013594`
- `0x180014374`
- `0x180039a88`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180011838`
- `0x180014450`
- `0x180024cf8`
- `0x18012c752`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800144e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800144e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800146a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001474e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001476b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001479e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001481a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014829`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001485b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001491a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800146a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001474e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001476b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001479e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001481a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014829`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001485b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001491a`
- `unistore!CreateStoreManager` at `0x18001459f`
- `unistore!CreateStoreManager` at `0x18001459f`

## string_xrefs

- `0x1800144fb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`
- `0x180014514`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`
- `0x1800147e9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`
- `0x18001483f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`
- `0x18001486e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`
- `0x1800148d0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`
- `0x180014931`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`
- `0x18001494f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\aggregatepropresolver.cpp`

## pseudocode

```c
__int64 __fastcall AggregatePropResolver::Initialize(__int128 *a1, __int64 *a2, __int128 *a3, __int64 a4)
{
  __int64 v4; // rax
  int v9; // eax
  unsigned int v10; // ebx
  const void *v11; // r12
  __int64 v12; // r14
  _OWORD *v13; // rax
  void *v14; // rbx
  int v16; // eax
  unsigned int v17; // esi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HLOCAL v21; // rsi
  HLOCAL v22; // r14
  HLOCAL v23; // rcx
  HLOCAL v24; // rcx
  _QWORD *v25; // rcx
  _QWORD *v26; // rcx
  __int128 v27; // xmm1
  __int64 v28; // rcx
  __int64 v29; // rcx
  HLOCAL v30; // rdi
  void (*v31)(void); // rax
  unsigned int v32; // esi
  HLOCAL hMem; // [rsp+40h] [rbp-69h] BYREF
  HLOCAL v34; // [rsp+48h] [rbp-61h] BYREF
  __int64 v35; // [rsp+50h] [rbp-59h] BYREF
  __int64 v36; // [rsp+58h] [rbp-51h] BYREF
  __int128 v37; // [rsp+60h] [rbp-49h] BYREF
  __int64 v38; // [rsp+70h] [rbp-39h]
  __int64 v39; // [rsp+78h] [rbp-31h] BYREF
  int v40; // [rsp+80h] [rbp-29h]
  int v41; // [rsp+84h] [rbp-25h]
  __int128 *v42; // [rsp+88h] [rbp-21h]
  __int64 v43; // [rsp+90h] [rbp-19h] BYREF
  int v44; // [rsp+98h] [rbp-11h]
  _QWORD v45[3]; // [rsp+A0h] [rbp-9h] BYREF

  v4 = *a2;
  hMem = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, _QWORD, HLOCAL *))(v4 + 48))(
         a2,
         2,
         &qword_18013A4B8,
         0,
         &hMem);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = *(const void **)a4;
    v12 = (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 2;
    v13 = LocalAlloc(0, 4LL * (unsigned __int16)(v12 + 8));
    v14 = v13;
    if ( !v13 )
    {
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
        109);
      Log_HREvent(
        2147942414LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
        45);
      if ( hMem )
        LocalFree(hMem);
      return 2147942414LL;
    }
    *v13 = xmmword_18013A498;
    v13[1] = xmmword_18013A4A8;
    memcpy_0(v13 + 2, v11, 4LL * (unsigned __int16)v12);
    v43 = 0;
    v44 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a2 + 24))(a2, &v43);
    v17 = v16;
    if ( v16 < 0 )
    {
      Log_HREvent(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
        48);
    }
    else
    {
      v35 = 0;
      v18 = CreateStoreManager(0, &v35);
      v17 = v18;
      if ( v18 >= 0 )
      {
        v38 = 0;
        v37 = 0;
        DWORD2(v37) = v44;
        v42 = &v37;
        v39 = 4;
        LODWORD(v37) = 806617107;
        v41 = 806617107;
        v40 = 4;
        v45[0] = 17498131;
        v45[1] = 17563659;
        v45[2] = 131075;
        v36 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v35 + 136LL))(
                v35,
                1,
                0x2000000,
                3,
                v45,
                &v39,
                &v36);
        v17 = v19;
        if ( v19 < 0 )
        {
          Log_HREvent(
            (unsigned int)v19,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
            78);
          if ( !v36 )
            goto LABEL_38;
          v31 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
        }
        else
        {
          v34 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, void *, HLOCAL *))(*(_QWORD *)v36 + 160LL))(
                  v36,
                  0xFFFFFFFFLL,
                  (unsigned __int16)(v12 + 8),
                  v14,
                  &v34);
          v17 = v20;
          if ( v20 >= 0 )
          {
            v21 = v34;
            if ( *(_DWORD *)v34 )
            {
              v22 = hMem;
              v23 = (HLOCAL)*((_QWORD *)a1 + 5);
              hMem = 0;
              if ( v22 != v23 )
              {
                if ( v23 )
                {
                  LocalFree(v23);
                  v21 = v34;
                }
                *((_QWORD *)a1 + 5) = v22;
              }
              v24 = (HLOCAL)*((_QWORD *)a1 + 6);
              v34 = 0;
              if ( v21 != v24 )
              {
                if ( v24 )
                  FreeUSPROPVALBATCH(v24);
                *((_QWORD *)a1 + 6) = v21;
              }
              v25 = (_QWORD *)*((_QWORD *)a1 + 1);
              *(_QWORD *)(*(_QWORD *)a1 + 8LL) = a3;
              *v25 = a3;
              v26 = (_QWORD *)*((_QWORD *)a3 + 1);
              *(_QWORD *)(*(_QWORD *)a3 + 8LL) = a1;
              *v26 = a1;
              v27 = *a3;
              *a3 = *a1;
              *a1 = v27;
              v28 = *((_QWORD *)a3 + 2);
              *((_QWORD *)a3 + 2) = *((_QWORD *)a1 + 2);
              *((_QWORD *)a1 + 2) = v28;
              v29 = *((_QWORD *)a3 + 3);
              *((_QWORD *)a3 + 3) = *((_QWORD *)a1 + 3);
              *((_QWORD *)a1 + 3) = v29;
              LOBYTE(v29) = *((_BYTE *)a3 + 32);
              *((_BYTE *)a3 + 32) = *((_BYTE *)a1 + 32);
              *((_BYTE *)a1 + 32) = v29;
              LOBYTE(v29) = *((_BYTE *)a3 + 33);
              *((_BYTE *)a3 + 33) = *((_BYTE *)a1 + 33);
              *((_BYTE *)a1 + 33) = v29;
              v30 = v34;
              if ( v34 )
              {
                if ( *((_QWORD *)v34 + 3) )
                {
                  v32 = 0;
                  if ( *(_DWORD *)v34 )
                  {
                    do
                      LocalFree(*(HLOCAL *)(*((_QWORD *)v30 + 3) + 8LL * v32++));
                    while ( v32 < *(_DWORD *)v30 );
                  }
                }
                LocalFree(*((HLOCAL *)v30 + 1));
                LocalFree(*((HLOCAL *)v30 + 2));
                LocalFree(*((HLOCAL *)v30 + 3));
                LocalFree(v30);
              }
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( v35 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              LocalFree(v14);
              if ( hMem )
                LocalFree(hMem);
              return 0;
            }
            else
            {
              Log_HREvent(
                2147943568LL,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
                88);
              tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v34);
              ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
              ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
              LocalFree(v14);
              if ( hMem )
                LocalFree(hMem);
              return 2147943568LL;
            }
          }
          Log_HREvent(
            (unsigned int)v20,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
            85);
          tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v34);
          if ( !v36 )
            goto LABEL_38;
          v31 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
        }
        v31();
LABEL_38:
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        goto LABEL_40;
      }
      Log_HREvent(
        (unsigned int)v18,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
        51);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
    }
LABEL_40:
    LocalFree(v14);
    if ( hMem )
      LocalFree(hMem);
    return v17;
  }
  Log_HREvent(
    (unsigned int)v9,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\aggregatepropresolver.cpp",
    35);
  if ( hMem )
    LocalFree(hMem);
  return v10;
}

```

## disassembly

```asm
0x180014450  push    rbp
0x180014452  push    rbx
0x180014453  push    rsi
0x180014454  push    rdi
0x180014455  push    r14
0x180014457  push    r15
0x180014459  lea     rbp, [rsp-2Fh]
0x18001445e  sub     rsp, 0D8h
0x180014465  mov     rax, cs:__security_cookie
0x18001446c  xor     rax, rsp
0x18001446f  mov     [rbp+57h+var_48], rax
0x180014473  mov     rax, [rdx]
0x180014476  mov     rdi, rcx
0x180014479  mov     rsi, rdx
0x18001447c  mov     [rbp+57h+hMem], 0
0x180014484  lea     rcx, [rbp+57h+hMem]
0x180014488  mov     r14, r9
0x18001448b  mov     r15, r8
0x18001448e  mov     [rsp+100h+var_E0], rcx
0x180014493  mov     rax, [rax+30h]
0x180014497  lea     r8, qword_18013A4B8
0x18001449e  xor     r9d, r9d
0x1800144a1  mov     edx, 2
0x1800144a6  mov     rcx, rsi
0x1800144a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144ae  mov     ebx, eax
0x1800144b0  test    eax, eax
0x1800144b2  js      loc_180014839
0x1800144b8  mov     [rsp+100h+var_30], r12
0x1800144c0  xor     ecx, ecx; uFlags
0x1800144c2  mov     r12, [r14]
0x1800144c5  mov     r14, [r14+8]
0x1800144c9  sub     r14, r12
0x1800144cc  mov     [rsp+100h+var_38], r13
0x1800144d4  sar     r14, 2
0x1800144d8  lea     eax, [r14+8]
0x1800144dc  movzx   r13d, ax
0x1800144e0  mov     edx, r13d
0x1800144e3  shl     rdx, 2; uBytes
0x1800144e7  call    cs:__imp_LocalAlloc
0x1800144ed  mov     rbx, rax
0x1800144f0  test    rax, rax
0x1800144f3  jnz     short loc_180014543
0x1800144f5  mov     r9d, 6Dh ; 'm'
0x1800144fb  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014502  xor     edx, edx
0x180014504  mov     ecx, 8007000Eh
0x180014509  call    Log_HREvent
0x18001450e  mov     r9d, 2Dh ; '-'
0x180014514  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001451b  mov     edx, 1
0x180014520  mov     ecx, 8007000Eh
0x180014525  call    Log_HREvent
0x18001452a  mov     rcx, [rbp+57h+hMem]; hMem
0x18001452e  test    rcx, rcx
0x180014531  jz      short loc_180014539
0x180014533  call    cs:__imp_LocalFree
0x180014539  mov     eax, 8007000Eh
0x18001453e  jmp     loc_1800147AF
0x180014543  movups  xmm0, cs:xmmword_18013A498
0x18001454a  movzx   r8d, r14w
0x18001454e  lea     rcx, [rax+20h]; void *
0x180014552  shl     r8, 2; Size
0x180014556  mov     rdx, r12; Src
0x180014559  movups  xmmword ptr [rax], xmm0
0x18001455c  movups  xmm1, cs:xmmword_18013A4A8
0x180014563  movups  xmmword ptr [rax+10h], xmm1
0x180014567  call    memcpy_0
0x18001456c  xor     eax, eax
0x18001456e  lea     rdx, [rbp+57h+var_70]
0x180014572  mov     [rbp+57h+var_70], rax
0x180014576  mov     rcx, rsi
0x180014579  mov     [rbp+57h+var_68], eax
0x18001457c  mov     rax, [rsi]
0x18001457f  mov     rax, [rax+18h]
0x180014583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014588  mov     esi, eax
0x18001458a  test    eax, eax
0x18001458c  js      loc_18001492B
0x180014592  xor     r12d, r12d
0x180014595  lea     rdx, [rbp+57h+var_B0]
0x180014599  xor     ecx, ecx
0x18001459b  mov     [rbp+57h+var_B0], r12
0x18001459f  call    cs:__imp_CreateStoreManager
0x1800145a5  mov     esi, eax
0x1800145a7  test    eax, eax
0x1800145a9  js      loc_180014949
0x1800145af  mov     rcx, [rbp+57h+var_B0]
0x1800145b3  lea     rdx, [rbp+57h+var_A8]
0x1800145b7  xor     eax, eax
0x1800145b9  mov     [rsp+100h+var_D0], rdx
0x1800145be  mov     [rbp+57h+var_90], rax
0x1800145c2  lea     rdx, [rbp+57h+var_88]
0x1800145c6  mov     eax, [rbp+57h+var_68]
0x1800145c9  xorps   xmm0, xmm0
0x1800145cc  movups  [rbp+57h+var_A0], xmm0
0x1800145d0  mov     dword ptr [rbp+57h+var_A0+8], eax
0x1800145d3  mov     r9d, 3
0x1800145d9  mov     [rsp+100h+var_D8], rdx
0x1800145de  lea     rax, [rbp+57h+var_A0]
0x1800145e2  mov     [rbp+57h+var_78], rax
0x1800145e6  lea     rdx, [rbp+57h+var_60]
0x1800145ea  mov     [rbp+57h+var_88], 4
0x1800145f2  mov     r8d, 2000000h
0x1800145f8  mov     dword ptr [rbp+57h+var_A0], 30140013h
0x1800145ff  mov     [rbp+57h+var_7C], 30140013h
0x180014606  mov     [rbp+57h+var_80], 4
0x18001460d  mov     [rbp+57h+var_60], 10B0013h
0x180014615  mov     [rbp+57h+var_58], 10C000Bh
0x18001461d  mov     [rbp+57h+var_50], 20003h
0x180014625  mov     [rbp+57h+var_A8], r12
0x180014629  mov     rax, [rcx]
0x18001462c  mov     [rsp+100h+var_E0], rdx
0x180014631  mov     edx, 1
0x180014636  mov     rax, [rax+88h]
0x18001463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014642  mov     esi, eax
0x180014644  test    eax, eax
0x180014646  js      loc_180014868
0x18001464c  mov     rcx, [rbp+57h+var_A8]
0x180014650  lea     rdx, [rbp+57h+var_B8]
0x180014654  mov     [rbp+57h+var_B8], r12
0x180014658  mov     r8d, r13d
0x18001465b  mov     [rsp+100h+var_E0], rdx
0x180014660  mov     r9, rbx
0x180014663  mov     edx, 0FFFFFFFFh
0x180014668  mov     rax, [rcx]
0x18001466b  mov     rax, [rax+0A0h]
0x180014672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014677  mov     esi, eax
0x180014679  test    eax, eax
0x18001467b  js      loc_1800148CA
0x180014681  mov     rsi, [rbp+57h+var_B8]
0x180014685  cmp     [rsi], r12d
0x180014688  jbe     loc_1800147E3
0x18001468e  mov     r14, [rbp+57h+hMem]
0x180014692  mov     rcx, [rdi+28h]; hMem
0x180014696  mov     [rbp+57h+hMem], r12
0x18001469a  cmp     r14, rcx
0x18001469d  jz      short loc_1800146B2
0x18001469f  test    rcx, rcx
0x1800146a2  jz      short loc_1800146AE
0x1800146a4  call    cs:__imp_LocalFree
0x1800146aa  mov     rsi, [rbp+57h+var_B8]
0x1800146ae  mov     [rdi+28h], r14
0x1800146b2  mov     rcx, [rdi+30h]; hMem
0x1800146b6  mov     [rbp+57h+var_B8], r12
0x1800146ba  cmp     rsi, rcx
0x1800146bd  jz      short loc_1800146CD
0x1800146bf  test    rcx, rcx
0x1800146c2  jz      short loc_1800146C9
0x1800146c4  call    ?FreeUSPROPVALBATCH@@YAXPEAU_USPROPVALBATCH@@@Z; FreeUSPROPVALBATCH(_USPROPVALBATCH *)
0x1800146c9  mov     [rdi+30h], rsi
0x1800146cd  mov     rax, [rdi]
0x1800146d0  mov     rcx, [rdi+8]
0x1800146d4  mov     [rax+8], r15
0x1800146d8  mov     [rcx], r15
0x1800146db  mov     rax, [r15]
0x1800146de  mov     rcx, [r15+8]
0x1800146e2  mov     [rax+8], rdi
0x1800146e6  mov     [rcx], rdi
0x1800146e9  movups  xmm0, xmmword ptr [rdi]
0x1800146ec  movups  xmm1, xmmword ptr [r15]
0x1800146f0  movups  xmmword ptr [r15], xmm0
0x1800146f4  movups  xmmword ptr [rdi], xmm1
0x1800146f7  mov     rax, [rdi+10h]
0x1800146fb  mov     rcx, [r15+10h]
0x1800146ff  mov     [r15+10h], rax
0x180014703  mov     [rdi+10h], rcx
0x180014707  mov     rax, [rdi+18h]
0x18001470b  mov     rcx, [r15+18h]
0x18001470f  mov     [r15+18h], rax
0x180014713  mov     [rdi+18h], rcx
0x180014717  movzx   eax, byte ptr [rdi+20h]
0x18001471b  movzx   ecx, byte ptr [r15+20h]
0x180014720  mov     [r15+20h], al
0x180014724  mov     [rdi+20h], cl
0x180014727  movzx   eax, byte ptr [rdi+21h]
0x18001472b  movzx   ecx, byte ptr [r15+21h]
0x180014730  mov     [r15+21h], al
0x180014734  mov     [rdi+21h], cl
0x180014737  mov     rdi, [rbp+57h+var_B8]
0x18001473b  test    rdi, rdi
0x18001473e  jz      short loc_180014771
0x180014740  cmp     [rdi+18h], r12
0x180014744  jnz     loc_1800148FE
0x18001474a  mov     rcx, [rdi+8]; hMem
0x18001474e  call    cs:__imp_LocalFree
0x180014754  mov     rcx, [rdi+10h]; hMem
0x180014758  call    cs:__imp_LocalFree
0x18001475e  mov     rcx, [rdi+18h]; hMem
0x180014762  call    cs:__imp_LocalFree
0x180014768  mov     rcx, rdi; hMem
0x18001476b  call    cs:__imp_LocalFree
0x180014771  mov     rcx, [rbp+57h+var_A8]
0x180014775  test    rcx, rcx
0x180014778  jz      short loc_180014786
0x18001477a  mov     rax, [rcx]
0x18001477d  mov     rax, [rax+10h]
0x180014781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014786  mov     rcx, [rbp+57h+var_B0]
0x18001478a  test    rcx, rcx
0x18001478d  jz      short loc_18001479B
0x18001478f  mov     rax, [rcx]
0x180014792  mov     rax, [rax+10h]
0x180014796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001479b  mov     rcx, rbx; hMem
0x18001479e  call    cs:__imp_LocalFree
0x1800147a4  mov     rcx, [rbp+57h+hMem]; hMem
0x1800147a8  test    rcx, rcx
0x1800147ab  jnz     short loc_1800147DB
0x1800147ad  xor     eax, eax
0x1800147af  mov     r12, [rsp+100h+var_30]
0x1800147b7  mov     r13, [rsp+100h+var_38]
0x1800147bf  mov     rcx, [rbp+57h+var_48]
0x1800147c3  xor     rcx, rsp; StackCookie
0x1800147c6  call    __security_check_cookie
0x1800147cb  add     rsp, 0D8h
0x1800147d2  pop     r15
0x1800147d4  pop     r14
0x1800147d6  pop     rdi
0x1800147d7  pop     rsi
0x1800147d8  pop     rbx
0x1800147d9  pop     rbp
0x1800147da  retn
0x1800147db  call    cs:__imp_LocalFree
0x1800147e1  jmp     short loc_1800147AD
0x1800147e3  mov     r9d, 58h ; 'X'
0x1800147e9  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800147f0  xor     edx, edx
0x1800147f2  mov     ecx, 80070490h
0x1800147f7  call    Log_HREvent
0x1800147fc  lea     rcx, [rbp+57h+var_B8]
0x180014800  call    ??1?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(void)
0x180014805  lea     rcx, [rbp+57h+var_A8]
0x180014809  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18001480e  lea     rcx, [rbp+57h+var_B0]
0x180014812  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180014817  mov     rcx, rbx; hMem
0x18001481a  call    cs:__imp_LocalFree
0x180014820  mov     rcx, [rbp+57h+hMem]; hMem
0x180014824  test    rcx, rcx
0x180014827  jz      short loc_18001482F
0x180014829  call    cs:__imp_LocalFree
0x18001482f  mov     eax, 80070490h
0x180014834  jmp     loc_1800147AF
0x180014839  mov     r9d, 23h ; '#'
0x18001483f  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014846  mov     edx, 1
0x18001484b  mov     ecx, ebx
0x18001484d  call    Log_HREvent
0x180014852  mov     rcx, [rbp+57h+hMem]; hMem
0x180014856  test    rcx, rcx
0x180014859  jz      short loc_180014861
0x18001485b  call    cs:__imp_LocalFree
0x180014861  mov     eax, ebx
0x180014863  jmp     loc_1800147BF
0x180014868  mov     r9d, 4Eh ; 'N'
0x18001486e  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180014875  mov     edx, 1
0x18001487a  mov     ecx, esi
0x18001487c  call    Log_HREvent
0x180014881  mov     rcx, [rbp+57h+var_A8]
0x180014885  test    rcx, rcx
0x180014888  jz      short loc_180014896
0x18001488a  mov     rdx, [rcx]
0x18001488d  mov     rax, [rdx+10h]
0x180014891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014896  mov     rcx, [rbp+57h+var_B0]
0x18001489a  test    rcx, rcx
0x18001489d  jz      short loc_1800148AB
0x18001489f  mov     rax, [rcx]
0x1800148a2  mov     rax, [rax+10h]
0x1800148a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148ab  mov     rcx, rbx; hMem
0x1800148ae  call    cs:__imp_LocalFree
0x1800148b4  mov     rcx, [rbp+57h+hMem]; hMem
0x1800148b8  test    rcx, rcx
0x1800148bb  jz      short loc_1800148C3
0x1800148bd  call    cs:__imp_LocalFree
0x1800148c3  mov     eax, esi
0x1800148c5  jmp     loc_1800147AF
0x1800148ca  mov     r9d, 55h ; 'U'
0x1800148d0  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800148d7  mov     edx, 1
0x1800148dc  mov     ecx, esi
0x1800148de  call    Log_HREvent
0x1800148e3  lea     rcx, [rbp+57h+var_B8]
0x1800148e7  call    ??1?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(void)
0x1800148ec  mov     rcx, [rbp+57h+var_A8]
0x1800148f0  test    rcx, rcx
0x1800148f3  jz      short loc_180014896
0x1800148f5  mov     rax, [rcx]
0x1800148f8  mov     rax, [rax+10h]
0x1800148fc  jmp     short loc_180014891
0x1800148fe  mov     esi, r12d
0x180014901  cmp     [rdi], r12d
0x180014904  jbe     loc_18001474A
0x18001490a  nop     word ptr [rax+rax+00h]
0x180014910  mov     rcx, [rdi+18h]
  ... truncated ...
```
