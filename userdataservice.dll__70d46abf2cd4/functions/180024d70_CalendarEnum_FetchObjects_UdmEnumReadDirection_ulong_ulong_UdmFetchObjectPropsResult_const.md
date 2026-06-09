# CalendarEnum::FetchObjects(UdmEnumReadDirection,ulong,ulong *,UdmFetchObjectPropsResult * const)

- ea: `0x180024d70`
- end: `0x18002533d`
- name: `?FetchObjects@CalendarEnum@@MEAAJW4UdmEnumReadDirection@@KPEAKQEAUUdmFetchObjectPropsResult@@@Z`
- size: `1485`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18000d828`
- `0x180012988`
- `0x180024d70`
- `0x180026070`
- `0x18007f200`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800250ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800250fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800250ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800250fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025204`
- `UserDataTypeHelperUtil!UsOidToCalendarUdmId` at `0x180024eeb`
- `UserDataTypeHelperUtil!UsOidToCalendarUdmId` at `0x180024eeb`

## string_xrefs

- `0x180025126`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x1800251b4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x1800251cf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x180025225`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x180025265`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x180025282`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x1800252a5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x1800252ce`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`
- `0x180025305`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\calendarenum.cpp`

## pseudocode

```c
__int64 __fastcall CalendarEnum::FetchObjects(__int64 *a1, int a2, int a3, unsigned int *a4, void *a5)
{
  int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r14
  unsigned __int64 i; // rsi
  __int64 v16; // rax
  void (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  int v18; // eax
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, __int64, __int64, HLOCAL *, int *, HANDLE); // r13
  HANDLE ProcessHeap; // r12
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  __int64 v28; // rax
  HLOCAL v29; // rcx
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64, __int64, __int64, HLOCAL *, int *, HANDLE); // r13
  HANDLE v33; // r12
  __int64 v34; // rdx
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  __int64 v41; // rax
  __int64 v42; // r8
  int v43; // eax
  unsigned int v44; // [rsp+50h] [rbp-91h] BYREF
  __int64 v45; // [rsp+58h] [rbp-89h] BYREF
  HLOCAL v46; // [rsp+60h] [rbp-81h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-79h] BYREF
  int v48; // [rsp+70h] [rbp-71h] BYREF
  __int64 v49; // [rsp+78h] [rbp-69h] BYREF
  __int64 v50; // [rsp+80h] [rbp-61h] BYREF
  __int64 v51; // [rsp+88h] [rbp-59h]
  unsigned int *v52; // [rsp+90h] [rbp-51h]
  __int64 v53; // [rsp+98h] [rbp-49h] BYREF
  int v54; // [rsp+A0h] [rbp-41h]
  unsigned int *v55; // [rsp+A8h] [rbp-39h] BYREF
  void *v56; // [rsp+B0h] [rbp-31h]
  _QWORD v57[2]; // [rsp+B8h] [rbp-29h] BYREF
  _QWORD v58[2]; // [rsp+C8h] [rbp-19h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-9h] BYREF
  int v60; // [rsp+E0h] [rbp-1h]
  __int64 v61; // [rsp+E8h] [rbp+7h] BYREF
  int v62; // [rsp+F0h] [rbp+Fh]

  v52 = a4;
  if ( a2 )
  {
    Log_HREvent(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
      344);
    return 2147942487LL;
  }
  if ( !*((_DWORD *)a1 + 26) )
  {
    v8 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 112))(a1);
    v10 = v8;
    if ( v8 < 0 )
    {
      Log_HREvent_11((unsigned int)v8, 1, v9, 9);
      Log_HREvent(
        v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
        346);
      return v10;
    }
    *((_DWORD *)a1 + 26) = 1;
  }
  if ( !a3 )
  {
    *a4 = 0;
    return 0;
  }
  v11 = a1[2];
  v55 = &v44;
  v12 = a1[3];
  v44 = 0;
  v56 = a5;
  v50 = 0;
  v51 = 0;
  if ( v11 != v12 )
  {
    v51 = v11;
    v50 = (v12 - v11) >> 2;
  }
  v13 = *((unsigned int *)a1 + 28);
  v14 = (unsigned int)(a3 + v13);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((a1[24] - a1[23]) >> 3) < v14 )
    v14 = 0xAAAAAAAAAAAAAAABuLL * ((a1[24] - a1[23]) >> 3);
  if ( v13 < v14 )
    memset_0(a5, 0, 24 * (v14 - v13));
  for ( i = *((unsigned int *)a1 + 28); ; ++i )
  {
    if ( i >= v14 )
    {
      v41 = *a1;
      v42 = v44;
      *((_DWORD *)a1 + 28) += v44;
      v43 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, void *))(v41 + 160))(a1, 0, v42, a5);
      v10 = v43;
      if ( v43 >= 0 )
      {
        v10 = 0;
        v56 = 0;
        *v52 = v44;
      }
      else
      {
        Log_HREvent(
          (unsigned int)v43,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
          435);
      }
      goto LABEL_42;
    }
    v16 = a1[23];
    v45 = 0;
    v17 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(v16 + 24 * i);
    if ( !v17 || ((**v17)(v17, &GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df, &v45), !v45) )
    {
      v10 = -2147467262;
      Log_HREvent(
        2147500034LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
        376);
      goto LABEL_40;
    }
    v59 = 0;
    v60 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 24LL))(v45, &v59);
    v10 = v18;
    if ( v18 < 0 )
    {
      Log_HREvent(
        (unsigned int)v18,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
        379);
      goto LABEL_61;
    }
    v61 = v59;
    v62 = v60;
    UsOidToCalendarUdmId(&v53, &v61);
    v19 = v54;
    v20 = 3LL * v44;
    *((_QWORD *)a5 + v20) = v53;
    *((_DWORD *)a5 + 2 * v20 + 2) = v19;
    v21 = a1[6];
    hMem = 0;
    v48 = 0;
    if ( v21 != a1[5] )
    {
      v22 = v45;
      v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, HLOCAL *, int *, HANDLE))(*(_QWORD *)v45 + 32LL);
      ProcessHeap = GetProcessHeap();
      if ( hMem )
        LocalFree(hMem);
      v25 = a1[5];
      v26 = (a1[6] - v25) >> 2;
      hMem = 0;
      v27 = v23(v22, v25, 1, v26, &hMem, &v48, ProcessHeap);
      v10 = v27;
      if ( v27 < 0 )
      {
        Log_HREvent(
          (unsigned int)v27,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
          394);
        goto LABEL_49;
      }
    }
    v28 = a1[9];
    v29 = 0;
    v46 = 0;
    if ( v28 != a1[8] )
      break;
LABEL_29:
    v37 = (a1[6] - a1[5]) >> 2;
    if ( v37 || a1[9] != a1[8] )
    {
      v58[1] = hMem;
      v38 = (a1[9] - a1[8]) >> 2;
      v57[1] = v29;
      v57[0] = v38;
      v58[0] = v37;
      v39 = PoomPropsToUdmProps(
              (unsigned int)&v50,
              (int)a1 + 88,
              (unsigned int)v58,
              (unsigned int)v57,
              0,
              (__int64)(a1 + 16),
              (__int64)a5 + 24 * v44,
              (__int64)a5 + 24 * v44 + 12,
              (__int64)a5 + 24 * v44 + 16);
      v10 = v39;
      if ( v39 < 0 )
      {
        Log_HREvent(
          (unsigned int)v39,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
          427);
        goto LABEL_47;
      }
      v29 = v46;
    }
    ++v44;
    if ( v29 )
      LocalFree(v29);
    if ( hMem )
      LocalFree(hMem);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v49 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 120LL))(v45, &v49);
  v10 = v30;
  if ( v30 >= 0 )
  {
    v31 = v49;
    v48 = 0;
    v32 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, HLOCAL *, int *, HANDLE))(*(_QWORD *)v49 + 80LL);
    v33 = GetProcessHeap();
    if ( v46 )
      LocalFree(v46);
    v34 = a1[8];
    v35 = (__int64)(unsigned int)(*((_DWORD *)a1 + 12) - *((_DWORD *)a1 + 10)) >> 2;
    v46 = 0;
    v36 = v32(v31, v34, 1, v35, &v46, &v48, v33);
    v10 = v36;
    if ( v36 < 0 )
    {
      Log_HREvent(
        (unsigned int)v36,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
        410);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v49);
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v46);
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&hMem);
LABEL_61:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
      goto LABEL_42;
    }
    if ( v49 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v29 = v46;
    goto LABEL_29;
  }
  Log_HREvent(
    (unsigned int)v30,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\calendarenum.cpp",
    401);
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
LABEL_47:
  if ( v46 )
    LocalFree(v46);
LABEL_49:
  if ( hMem )
    LocalFree(hMem);
LABEL_40:
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
LABEL_42:
  ResultCleaner::~ResultCleaner((ResultCleaner *)&v55);
  return v10;
}

```

## disassembly

```asm
0x180024d70  mov     [rsp-8+arg_8], rbx
0x180024d75  push    rbp
0x180024d76  push    rsi
0x180024d77  push    rdi
0x180024d78  push    r12
0x180024d7a  push    r13
0x180024d7c  push    r14
0x180024d7e  push    r15
0x180024d80  lea     rbp, [rsp-1Fh]
0x180024d85  sub     rsp, 100h
0x180024d8c  mov     rax, cs:__security_cookie
0x180024d93  xor     rax, rsp
0x180024d96  mov     [rbp+4Fh+var_38], rax
0x180024d9a  mov     r15, [rbp+4Fh+arg_20]
0x180024d9e  xor     r13d, r13d
0x180024da1  mov     [rbp+4Fh+var_A0], r9
0x180024da5  mov     r12, r9
0x180024da8  mov     esi, r8d
0x180024dab  mov     rbx, rcx
0x180024dae  test    edx, edx
0x180024db0  jnz     loc_18002527D
0x180024db6  cmp     [rcx+68h], r13d
0x180024dba  jnz     short loc_180024DD9
0x180024dbc  mov     rax, [rcx]
0x180024dbf  mov     rax, [rax+70h]
0x180024dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dc8  mov     edi, eax
0x180024dca  test    eax, eax
0x180024dcc  js      loc_18002524F
0x180024dd2  mov     dword ptr [rbx+68h], 1
0x180024dd9  test    esi, esi
0x180024ddb  jz      loc_1800252BD
0x180024de1  mov     rcx, [rbx+10h]
0x180024de5  lea     rax, [rsp+130h+var_E0]
0x180024dea  mov     [rbp+4Fh+var_88], rax
0x180024dee  mov     rax, [rbx+18h]
0x180024df2  mov     [rsp+130h+var_E0], r13d
0x180024df7  mov     [rbp+4Fh+var_80], r15
0x180024dfb  mov     [rbp+4Fh+var_B0], r13
0x180024dff  mov     [rbp+4Fh+var_A8], r13
0x180024e03  cmp     rcx, rax
0x180024e06  jz      short loc_180024E17
0x180024e08  sub     rax, rcx
0x180024e0b  mov     [rbp+4Fh+var_A8], rcx
0x180024e0f  sar     rax, 2
0x180024e13  mov     [rbp+4Fh+var_B0], rax
0x180024e17  mov     edx, [rbx+70h]
0x180024e1a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180024e24  mov     rcx, [rbx+0C0h]
0x180024e2b  sub     rcx, [rbx+0B8h]
0x180024e32  sar     rcx, 3
0x180024e36  imul    rcx, rax
0x180024e3a  lea     r14d, [rsi+rdx]
0x180024e3e  cmp     rcx, r14
0x180024e41  cmovb   r14, rcx
0x180024e45  cmp     rdx, r14
0x180024e48  jnb     short loc_180024E62
0x180024e4a  mov     rax, r14
0x180024e4d  mov     rcx, r15; void *
0x180024e50  sub     rax, rdx
0x180024e53  xor     edx, edx; Val
0x180024e55  lea     r8, [rax+rax*2]
0x180024e59  shl     r8, 3; Size
0x180024e5d  call    memset_0
0x180024e62  mov     esi, [rbx+70h]
0x180024e65  cmp     rsi, r14
0x180024e68  jnb     loc_180025184
0x180024e6e  mov     rax, [rbx+0B8h]
0x180024e75  lea     rcx, [rsi+rsi*2]
0x180024e79  mov     [rsp+130h+var_D8], r13
0x180024e7e  mov     rcx, [rax+rcx*8]
0x180024e82  test    rcx, rcx
0x180024e85  jz      loc_180025121
0x180024e8b  mov     rax, [rcx]
0x180024e8e  lea     r8, [rsp+130h+var_D8]
0x180024e93  lea     rdx, _GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df
0x180024e9a  mov     rax, [rax]
0x180024e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ea2  mov     rcx, [rsp+130h+var_D8]
0x180024ea7  test    rcx, rcx
0x180024eaa  jz      loc_180025121
0x180024eb0  xor     eax, eax
0x180024eb2  lea     rdx, [rbp+4Fh+var_58]
0x180024eb6  mov     [rbp+4Fh+var_58], rax
0x180024eba  mov     [rbp+4Fh+var_50], eax
0x180024ebd  mov     rax, [rcx]
0x180024ec0  mov     rax, [rax+18h]
0x180024ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ec9  mov     edi, eax
0x180024ecb  test    eax, eax
0x180024ecd  js      loc_1800252FF
0x180024ed3  movsd   xmm0, [rbp+4Fh+var_58]
0x180024ed8  lea     rdx, [rbp+4Fh+var_48]
0x180024edc  mov     eax, [rbp+4Fh+var_50]
0x180024edf  lea     rcx, [rbp+4Fh+var_98]
0x180024ee3  movsd   [rbp+4Fh+var_48], xmm0
0x180024ee8  mov     [rbp+4Fh+var_40], eax
0x180024eeb  call    cs:__imp_UsOidToCalendarUdmId
0x180024ef1  mov     eax, [rsp+130h+var_E0]
0x180024ef5  movsd   xmm0, [rbp+4Fh+var_98]
0x180024efa  mov     edx, [rbp+4Fh+var_90]
0x180024efd  lea     rcx, [rax+rax*2]
0x180024f01  movsd   qword ptr [r15+rcx*8], xmm0
0x180024f07  mov     [r15+rcx*8+8], edx
0x180024f0c  mov     rax, [rbx+30h]
0x180024f10  mov     [rbp+4Fh+hMem], r13
0x180024f14  mov     [rbp+4Fh+var_C0], r13d
0x180024f18  cmp     rax, [rbx+28h]
0x180024f1c  jz      short loc_180024F8E
0x180024f1e  mov     rdi, [rsp+130h+var_D8]
0x180024f23  mov     rax, [rdi]
0x180024f26  mov     r13, [rax+20h]
0x180024f2a  call    cs:__imp_GetProcessHeap
0x180024f30  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180024f34  mov     r12, rax
0x180024f37  test    rcx, rcx
0x180024f3a  jz      short loc_180024F42
0x180024f3c  call    cs:__imp_LocalFree
0x180024f42  mov     rdx, [rbx+28h]
0x180024f46  lea     rax, [rbp+4Fh+var_C0]
0x180024f4a  mov     r9, [rbx+30h]
0x180024f4e  mov     r8d, 1
0x180024f54  mov     [rsp+130h+var_100], r12
0x180024f59  sub     r9, rdx
0x180024f5c  mov     [rsp+130h+var_108], rax
0x180024f61  mov     rcx, rdi
0x180024f64  lea     rax, [rbp+4Fh+hMem]
0x180024f68  sar     r9, 2
0x180024f6c  mov     [rsp+130h+var_110], rax
0x180024f71  mov     rax, r13
0x180024f74  mov     [rbp+4Fh+hMem], 0
0x180024f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f81  xor     r13d, r13d
0x180024f84  mov     edi, eax
0x180024f86  test    eax, eax
0x180024f88  js      loc_18002529F
0x180024f8e  mov     rax, [rbx+48h]
0x180024f92  mov     rcx, r13
0x180024f95  mov     [rsp+130h+var_D0], rcx
0x180024f9a  cmp     rax, [rbx+40h]
0x180024f9e  jz      loc_180025058
0x180024fa4  mov     rcx, [rsp+130h+var_D8]
0x180024fa9  lea     rdx, [rbp+4Fh+var_B8]
0x180024fad  mov     [rbp+4Fh+var_B8], r13
0x180024fb1  mov     rax, [rcx]
0x180024fb4  mov     rax, [rax+78h]
0x180024fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fbd  mov     edi, eax
0x180024fbf  test    eax, eax
0x180024fc1  js      loc_18002521F
0x180024fc7  mov     rdi, [rbp+4Fh+var_B8]
0x180024fcb  mov     [rbp+4Fh+var_C0], r13d
0x180024fcf  mov     rax, [rdi]
0x180024fd2  mov     r13, [rax+50h]
0x180024fd6  call    cs:__imp_GetProcessHeap
0x180024fdc  mov     rcx, [rsp+130h+var_D0]; hMem
0x180024fe1  mov     r12, rax
0x180024fe4  test    rcx, rcx
0x180024fe7  jz      short loc_180024FEF
0x180024fe9  call    cs:__imp_LocalFree
0x180024fef  mov     r9d, [rbx+30h]
0x180024ff3  lea     rax, [rbp+4Fh+var_C0]
0x180024ff7  sub     r9d, [rbx+28h]
0x180024ffb  mov     r8d, 1
0x180025001  mov     rdx, [rbx+40h]
0x180025005  mov     rcx, rdi
0x180025008  mov     [rsp+130h+var_100], r12
0x18002500d  mov     [rsp+130h+var_108], rax
0x180025012  lea     rax, [rsp+130h+var_D0]
0x180025017  mov     [rsp+130h+var_110], rax
0x18002501c  mov     rax, r13
0x18002501f  sar     r9, 2
0x180025023  mov     [rsp+130h+var_D0], 0
0x18002502c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025031  xor     r13d, r13d
0x180025034  mov     edi, eax
0x180025036  test    eax, eax
0x180025038  js      loc_1800252C8
0x18002503e  mov     rcx, [rbp+4Fh+var_B8]
0x180025042  test    rcx, rcx
0x180025045  jz      short loc_180025053
0x180025047  mov     rax, [rcx]
0x18002504a  mov     rax, [rax+10h]
0x18002504e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025053  mov     rcx, [rsp+130h+var_D0]
0x180025058  mov     rdx, [rbx+30h]
0x18002505c  sub     rdx, [rbx+28h]
0x180025060  sar     rdx, 2
0x180025064  test    rdx, rdx
0x180025067  jz      loc_18002520C
0x18002506d  mov     rax, [rbp+4Fh+hMem]
0x180025071  lea     r8, [rbx+80h]
0x180025078  mov     [rbp+4Fh+var_60], rax
0x18002507c  mov     rax, [rbx+48h]
0x180025080  sub     rax, [rbx+40h]
0x180025084  sar     rax, 2
0x180025088  mov     [rbp+4Fh+var_70], rcx
0x18002508c  mov     [rbp+4Fh+var_78], rax
0x180025090  mov     eax, [rsp+130h+var_E0]
0x180025094  mov     [rbp+4Fh+var_68], rdx
0x180025098  lea     rdx, [rbx+58h]
0x18002509c  lea     rcx, [rax+rax*2]
0x1800250a0  lea     r9, [r15+rcx*8]
0x1800250a4  lea     rcx, [r9+0Ch]
0x1800250a8  lea     rax, [r9+10h]
0x1800250ac  mov     [rsp+130h+var_F0], rax
0x1800250b1  mov     [rsp+130h+var_F8], rcx
0x1800250b6  lea     rcx, [rbp+4Fh+var_B0]
0x1800250ba  mov     [rsp+130h+var_100], r9
0x1800250bf  lea     r9, [rbp+4Fh+var_78]
0x1800250c3  mov     [rsp+130h+var_108], r8
0x1800250c8  lea     r8, [rbp+4Fh+var_68]
0x1800250cc  mov     [rsp+130h+var_110], r13
0x1800250d1  call    ?PoomPropsToUdmProps@@YAJAEBV?$Vector@K@Udm@@AEBV?$Vector@$$CBUUdmPoomPropIdMap@@@2@AEBV?$Vector@U_SQLCEPROPVAL@@@2@2PEAV?$Vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@2@PEAVPoomOperationContext@@AEBUUdmObjectId@@PEAKPEAPEAUUdmPropertyValue@@@Z; PoomPropsToUdmProps(Udm::Vector<ulong> const &,Udm::Vector<UdmPoomPropIdMap const> const &,Udm::Vector<_SQLCEPROPVAL> const &,Udm::Vector<_SQLCEPROPVAL> const &,Udm::Vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>> *,PoomOperationContext *,UdmObjectId const &,ulong *,UdmPropertyValue * *)
0x1800250d6  mov     edi, eax
0x1800250d8  test    eax, eax
0x1800250da  js      loc_1800251C9
0x1800250e0  mov     rcx, [rsp+130h+var_D0]; hMem
0x1800250e5  inc     [rsp+130h+var_E0]
0x1800250e9  test    rcx, rcx
0x1800250ec  jz      short loc_1800250F4
0x1800250ee  call    cs:__imp_LocalFree
0x1800250f4  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800250f8  test    rcx, rcx
0x1800250fb  jz      short loc_180025103
0x1800250fd  call    cs:__imp_LocalFree
0x180025103  mov     rcx, [rsp+130h+var_D8]
0x180025108  test    rcx, rcx
0x18002510b  jz      short loc_180025119
0x18002510d  mov     rax, [rcx]
0x180025110  mov     rax, [rax+10h]
0x180025114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025119  inc     rsi
0x18002511c  jmp     loc_180024E65
0x180025121  mov     edi, 80004002h
0x180025126  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002512d  mov     ecx, edi
0x18002512f  mov     r9d, 178h
0x180025135  xor     edx, edx
0x180025137  call    Log_HREvent
0x18002513c  mov     rcx, [rsp+130h+var_D8]
0x180025141  test    rcx, rcx
0x180025144  jz      short loc_180025152
0x180025146  mov     rax, [rcx]
0x180025149  mov     rax, [rax+10h]
0x18002514d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025152  lea     rcx, [rbp+4Fh+var_88]; this
0x180025156  call    ??1ResultCleaner@@QEAA@XZ; ResultCleaner::~ResultCleaner(void)
0x18002515b  mov     eax, edi
0x18002515d  mov     rcx, [rbp+4Fh+var_38]
0x180025161  xor     rcx, rsp; StackCookie
0x180025164  call    __security_check_cookie
0x180025169  mov     rbx, [rsp+130h+arg_8]
0x180025171  add     rsp, 100h
0x180025178  pop     r15
0x18002517a  pop     r14
0x18002517c  pop     r13
0x18002517e  pop     r12
0x180025180  pop     rdi
0x180025181  pop     rsi
0x180025182  pop     rbp
0x180025183  retn
0x180025184  mov     rax, [rbx]
0x180025187  mov     r9, r15
0x18002518a  mov     r8d, [rsp+130h+var_E0]
0x18002518f  xor     edx, edx
0x180025191  add     [rbx+70h], r8d
0x180025195  mov     rcx, rbx
0x180025198  mov     rax, [rax+0A0h]
0x18002519f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251a4  mov     edi, eax
0x1800251a6  test    eax, eax
0x1800251a8  jns     loc_180025327
0x1800251ae  mov     r9d, 1B3h
0x1800251b4  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800251bb  mov     edx, 1
0x1800251c0  mov     ecx, eax
0x1800251c2  call    Log_HREvent
0x1800251c7  jmp     short loc_180025152
0x1800251c9  mov     r9d, 1ABh
0x1800251cf  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800251d6  mov     edx, 1
0x1800251db  mov     ecx, eax
0x1800251dd  call    Log_HREvent
0x1800251e2  mov     rcx, [rsp+130h+var_D0]; hMem
0x1800251e7  test    rcx, rcx
0x1800251ea  jnz     short loc_180025204
0x1800251ec  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800251f0  test    rcx, rcx
0x1800251f3  jz      loc_18002513C
0x1800251f9  call    cs:__imp_LocalFree
0x1800251ff  jmp     loc_18002513C
0x180025204  call    cs:__imp_LocalFree
0x18002520a  jmp     short loc_1800251EC
0x18002520c  mov     rax, [rbx+48h]
0x180025210  cmp     rax, [rbx+40h]
0x180025214  jnz     loc_18002506D
0x18002521a  jmp     loc_1800250E5
0x18002521f  mov     r9d, 191h
0x180025225  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
  ... truncated ...
```
