# GetObjectByOid(USOID *,IUSObject * *)

- ea: `0x18002cc10`
- end: `0x18002d3b7`
- name: `?GetObjectByOid@@YAJPEAUUSOID@@PEAPEAUIUSObject@@@Z`
- size: `1959`
- prototype: `__int64 __fastcall(struct USOID *, struct IUSObject **)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800603c0`
- `0x180070bb0`
- `0x180070cc0`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180021e6c`
- `0x18002c9f0`
- `0x18002cc10`
- `0x180065100`
- `0x180071b08`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cec7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cec7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d164`

## string_xrefs

- `0x18002d1a9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\factory.cpp`
- `0x18002d190`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\objectimpl.h`
- `0x18002cdfe`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002ce80`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002cf56`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002cfbb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d00b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d050`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d0cf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d143`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d1cb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d255`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d32c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002d37a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`

## pseudocode

```c
__int64 __fastcall GetObjectByOid(struct USOID *a1, struct IUSObject **a2)
{
  int v4; // eax
  struct IUSFactory *v5; // rdi
  int Instance; // eax
  unsigned int v7; // ebx
  unsigned int i; // eax
  __int64 v9; // rdx
  struct IDBManager *v10; // rbx
  unsigned int v11; // r14d
  int v12; // eax
  unsigned int v13; // r15d
  int v14; // eax
  int v15; // eax
  unsigned int v16; // r14d
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r9
  struct IUSObject *v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // eax
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // r9
  struct IUSStoreManager *v28; // rbx
  int v29; // eax
  __int64 v30; // r8
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  struct IUSStoreManager *v32; // [rsp+38h] [rbp-40h] BYREF
  __int64 v33; // [rsp+40h] [rbp-38h] BYREF
  __int128 v34; // [rsp+48h] [rbp-30h] BYREF
  __int64 v35; // [rsp+58h] [rbp-20h]
  struct IDBManager *v36; // [rsp+A0h] [rbp+28h] BYREF
  struct IUSObject *v37; // [rsp+B0h] [rbp+38h] BYREF
  __int64 v38; // [rsp+B8h] [rbp+40h] BYREF

  hMem = 0;
  v36 = 0;
  v38 = 0;
  v35 = 0;
  v37 = 0;
  v34 = 0;
  if ( !a1 || !a2 )
  {
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      934);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&hMem);
    return 2147942487LL;
  }
  v4 = *((_DWORD *)a1 + 1);
  if ( v4 == 0x80000 )
  {
    if ( *(_DWORD *)a1 )
    {
      Log_UnistoreHREvent_0(
        2147942487LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
        942);
      if ( v37 )
        (*(void (__fastcall **)(struct IUSObject *))(*(_QWORD *)v37 + 16LL))(v37);
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      return 2147942487LL;
    }
  }
  else if ( v4 != 0x10000 )
  {
    v24 = CStoreManager::s_dwDeviceStoreId;
    if ( !CStoreManager::s_dwDeviceStoreId )
    {
      v32 = 0;
      v29 = CStoreManager::CreateInstance(&v32);
      v26 = v29;
      if ( v29 < 0 )
      {
        Log_UnistoreHREvent_12((unsigned int)v29, 1, v30, 190);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v32);
        v27 = 949;
        goto LABEL_79;
      }
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v32);
      v24 = CStoreManager::s_dwDeviceStoreId;
    }
    if ( *(_DWORD *)a1 < v24 )
    {
      Log_UnistoreHREvent_0(
        2147943568LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
        951);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&hMem);
      return 2147943568LL;
    }
  }
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&g_pFactory, 0, 0) )
  {
    v33 = 0;
    v32 = 0;
    v25 = CUSObjectInternal<CFactory>::CreateInstance(&v32);
    v26 = v25;
    if ( v25 >= 0 )
    {
      v28 = v32;
      if ( v32 )
        (*(void (__fastcall **)(struct IUSStoreManager *))(*(_QWORD *)v32 + 8LL))(v32);
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pFactory, (signed __int64)v28, 0) && v28 )
        (*(void (__fastcall **)(struct IUSStoreManager *))(*(_QWORD *)v28 + 16LL))(v28);
      goto LABEL_6;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v25,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\objectimpl.h",
      452);
    Log_UnistoreHREvent_0(
      v26,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\factory.cpp",
      51);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v33);
    v27 = 955;
LABEL_79:
    Log_UnistoreHREvent_0(
      v26,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      v27);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&hMem);
    return v26;
  }
LABEL_6:
  (*(void (__fastcall **)(struct IUSFactory *))(*(_QWORD *)g_pFactory + 8LL))(g_pFactory);
  v5 = g_pFactory;
  hMem = g_pFactory;
  Instance = DBManager::GetInstance(&v36);
  v7 = Instance;
  if ( Instance < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      958);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&hMem);
    return v7;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x24 )
    {
      Log_UnistoreHREvent_0(
        2147942487LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
        961);
      if ( v37 )
        (*(void (__fastcall **)(struct IUSObject *))(*(_QWORD *)v37 + 16LL))(v37);
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v36 )
        (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v36 + 16LL))(v36);
      if ( v5 )
        (*(void (__fastcall **)(struct IUSFactory *))(*(_QWORD *)v5 + 16LL))(v5);
      return 2147942487LL;
    }
    v9 = 12LL * i;
    if ( *(_DWORD *)((char *)&g_rgObjectTypeMap + v9) == *((_DWORD *)a1 + 1) )
      break;
  }
  v10 = v36;
  v11 = *(_DWORD *)((char *)&g_rgObjectTypeMap + v9 + 4);
  v12 = (*(__int64 (__fastcall **)(struct IDBManager *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v36 + 40LL))(
          v36,
          v11,
          0,
          &v38);
  v13 = v12;
  if ( v12 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v12,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      964);
    if ( v37 )
      (*(void (__fastcall **)(struct IUSObject *))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v10 )
      (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v5 )
      (*(void (__fastcall **)(struct IUSFactory *))(*(_QWORD *)v5 + 16LL))(v5);
    return v13;
  }
  if ( v11 && v11 != 53 )
    v14 = 65539;
  else
    v14 = 17170435;
  LODWORD(v34) = v14;
  DWORD2(v34) = *((_DWORD *)a1 + 2);
  v15 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v38 + 72LL))(v38, &v34, 0);
  v16 = v15;
  if ( (_WORD)v15 == 25 )
    goto LABEL_25;
  if ( v15 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      971);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&hMem);
    return v16;
  }
  v17 = (*(__int64 (__fastcall **)(struct IUSFactory *, struct USOID *, struct IUSObject **))(*(_QWORD *)v5 + 104LL))(
          v5,
          a1,
          &v37);
  v16 = v17;
  if ( v17 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v17,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      974);
LABEL_57:
    if ( v37 )
      (*(void (__fastcall **)(struct IUSObject *))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v10 )
      (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v5 )
      (*(void (__fastcall **)(struct IUSFactory *))(*(_QWORD *)v5 + 16LL))(v5);
    return v16;
  }
  v18 = *((_DWORD *)a1 + 1);
  if ( v18 == 0x10000 )
  {
    if ( *((_DWORD *)a1 + 2) != *(_DWORD *)a1 )
    {
      Log_UnistoreHREvent_0(
        2147943568LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
        978);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&hMem);
      return 2147943568LL;
    }
    goto LABEL_36;
  }
  if ( v18 == 0x80000 )
  {
LABEL_36:
    v22 = v37;
    v23 = v38;
    v37 = 0;
    *a2 = v22;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v10 )
      (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v5 )
      (*(void (__fastcall **)(struct IUSFactory *))(*(_QWORD *)v5 + 16LL))(v5);
    return 0;
  }
  LODWORD(v36) = 131075;
  hMem = 0;
  v19 = (*(__int64 (__fastcall **)(struct IUSObject *, __int64, struct IDBManager **, _QWORD, HLOCAL *))(*(_QWORD *)v37 + 48LL))(
          v37,
          1,
          &v36,
          0,
          &hMem);
  v16 = v19;
  if ( v19 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v19,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      984);
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_57;
  }
  if ( (*((_WORD *)hMem + 3) & 0x100) == 0 )
  {
    if ( *((_DWORD *)hMem + 2) != *(_DWORD *)a1 )
    {
      v20 = 986;
      goto LABEL_23;
    }
    LocalFree(hMem);
    goto LABEL_36;
  }
  v20 = 985;
LABEL_23:
  Log_UnistoreHREvent_0(
    2147943568LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
    v20);
  if ( hMem )
    LocalFree(hMem);
LABEL_25:
  if ( v37 )
    (*(void (__fastcall **)(struct IUSObject *))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v10 )
    (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v5 )
    (*(void (__fastcall **)(struct IUSFactory *))(*(_QWORD *)v5 + 16LL))(v5);
  return 2147943568LL;
}

```

## disassembly

```asm
0x18002cc10  push    rbp
0x18002cc12  push    rsi
0x18002cc13  push    r12
0x18002cc15  push    r13
0x18002cc17  mov     rbp, rsp
0x18002cc1a  sub     rsp, 78h
0x18002cc1e  xor     r13d, r13d
0x18002cc21  xor     eax, eax
0x18002cc23  mov     [rbp+hMem], r13
0x18002cc27  xorps   xmm0, xmm0
0x18002cc2a  mov     [rbp+arg_0], r13
0x18002cc2e  mov     r12, rdx
0x18002cc31  mov     [rbp+arg_18], r13
0x18002cc35  mov     rsi, rcx
0x18002cc38  mov     [rbp+var_20], rax
0x18002cc3c  mov     [rbp+arg_10], r13
0x18002cc40  movups  [rbp+var_30], xmm0
0x18002cc44  test    rcx, rcx
0x18002cc47  jz      loc_18002CE7A
0x18002cc4d  test    rdx, rdx
0x18002cc50  jz      loc_18002CE7A
0x18002cc56  mov     eax, [rcx+4]
0x18002cc59  mov     [rsp+78h+arg_8], rbx
0x18002cc61  cmp     eax, 80000h
0x18002cc66  jz      loc_18002CFFC
0x18002cc6c  cmp     eax, 10000h
0x18002cc71  jnz     loc_18002CF3A
0x18002cc77  mov     rcx, r13
0x18002cc7a  xor     eax, eax
0x18002cc7c  lock cmpxchg cs:?g_pFactory@@3PEAUIUSFactory@@EA, rcx; IUSFactory * g_pFactory
0x18002cc85  jz      loc_18002D16F
0x18002cc8b  mov     rcx, cs:?g_pFactory@@3PEAUIUSFactory@@EA; IUSFactory * g_pFactory
0x18002cc92  mov     [rsp+78h+var_8], rdi
0x18002cc97  mov     rax, [rcx]
0x18002cc9a  mov     rax, [rax+8]
0x18002cc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cca3  mov     rdi, cs:?g_pFactory@@3PEAUIUSFactory@@EA; IUSFactory * g_pFactory
0x18002ccaa  lea     rcx, [rbp+arg_0]; struct IDBManager **
0x18002ccae  mov     [rbp+hMem], rdi
0x18002ccb2  call    ?GetInstance@DBManager@@SAJPEAPEAVIDBManager@@@Z; DBManager::GetInstance(IDBManager * *)
0x18002ccb7  mov     ebx, eax
0x18002ccb9  test    eax, eax
0x18002ccbb  js      loc_18002D326
0x18002ccc1  mov     r8d, [rsi+4]
0x18002ccc5  mov     eax, r13d
0x18002ccc8  mov     [rsp+78h+var_10], r14
0x18002cccd  lea     r14, ?g_rgObjectTypeMap@@3QBUObjectTypeMapEntry@@B; ObjectTypeMapEntry const near * const g_rgObjectTypeMap
0x18002ccd4  cmp     eax, 24h ; '$'
0x18002ccd7  jnb     loc_18002D24F
0x18002ccdd  mov     ecx, eax
0x18002ccdf  lea     rdx, [rcx+rcx*2]
0x18002cce3  lea     rdx, ds:0[rdx*4]
0x18002cceb  cmp     [rdx+r14], r8d
0x18002ccef  jz      short loc_18002CCF5
0x18002ccf1  inc     eax
0x18002ccf3  jmp     short loc_18002CCD4
0x18002ccf5  mov     rbx, [rbp+arg_0]
0x18002ccf9  lea     r9, [rbp+arg_18]
0x18002ccfd  mov     r14d, [rdx+r14+4]
0x18002cd02  xor     r8d, r8d
0x18002cd05  mov     edx, r14d
0x18002cd08  mov     [rsp+78h+var_18], r15
0x18002cd0d  mov     rcx, rbx
0x18002cd10  mov     rax, [rbx]
0x18002cd13  mov     rax, [rax+28h]
0x18002cd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd1c  mov     r15d, eax
0x18002cd1f  test    eax, eax
0x18002cd21  js      loc_18002D0C9
0x18002cd27  test    r14d, r14d
0x18002cd2a  jz      short loc_18002CD36
0x18002cd2c  cmp     r14d, 35h ; '5'
0x18002cd30  jnz     loc_18002D36A
0x18002cd36  mov     eax, 1060003h
0x18002cd3b  mov     rcx, [rbp+arg_18]
0x18002cd3f  lea     rdx, [rbp+var_30]
0x18002cd43  mov     dword ptr [rbp+var_30], eax
0x18002cd46  xor     r8d, r8d
0x18002cd49  mov     eax, [rsi+8]
0x18002cd4c  mov     dword ptr [rbp+var_30+8], eax
0x18002cd4f  mov     rax, [rcx]
0x18002cd52  mov     rax, [rax+48h]
0x18002cd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd5b  mov     r14d, eax
0x18002cd5e  cmp     ax, 19h
0x18002cd62  jz      loc_18002CE1E
0x18002cd68  test    eax, eax
0x18002cd6a  js      loc_18002D374
0x18002cd70  mov     rax, [rdi]
0x18002cd73  lea     r8, [rbp+arg_10]
0x18002cd77  mov     rdx, rsi
0x18002cd7a  mov     rcx, rdi
0x18002cd7d  mov     rax, [rax+68h]
0x18002cd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd86  mov     r14d, eax
0x18002cd89  test    eax, eax
0x18002cd8b  js      loc_18002D04A
0x18002cd91  mov     eax, [rsi+4]
0x18002cd94  cmp     eax, 10000h
0x18002cd99  jz      loc_18002CFAA
0x18002cd9f  cmp     eax, 80000h
0x18002cda4  jz      loc_18002CECD
0x18002cdaa  mov     rcx, [rbp+arg_10]
0x18002cdae  lea     rdx, [rbp+hMem]
0x18002cdb2  mov     dword ptr [rbp+arg_0], 20003h
0x18002cdb9  lea     r8, [rbp+arg_0]
0x18002cdbd  mov     [rbp+hMem], r13
0x18002cdc1  xor     r9d, r9d
0x18002cdc4  mov     [rsp+78h+var_58], rdx
0x18002cdc9  mov     edx, 1
0x18002cdce  mov     rax, [rcx]
0x18002cdd1  mov     rax, [rax+30h]
0x18002cdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdda  mov     r14d, eax
0x18002cddd  test    eax, eax
0x18002cddf  js      loc_18002D13D
0x18002cde5  mov     rcx, [rbp+hMem]; hMem
0x18002cde9  mov     eax, 100h
0x18002cdee  test    [rcx+6], ax
0x18002cdf2  jz      loc_18002CF94
0x18002cdf8  mov     r9d, 3D9h
0x18002cdfe  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002ce05  xor     edx, edx
0x18002ce07  mov     ecx, 80070490h
0x18002ce0c  call    Log_UnistoreHREvent_0
0x18002ce11  mov     rcx, [rbp+hMem]; hMem
0x18002ce15  test    rcx, rcx
0x18002ce18  jnz     loc_18002D0BE
0x18002ce1e  mov     rcx, [rbp+arg_10]
0x18002ce22  test    rcx, rcx
0x18002ce25  jz      short loc_18002CE33
0x18002ce27  mov     rax, [rcx]
0x18002ce2a  mov     rax, [rax+10h]
0x18002ce2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce33  mov     rcx, [rbp+arg_18]
0x18002ce37  test    rcx, rcx
0x18002ce3a  jz      short loc_18002CE48
0x18002ce3c  mov     rax, [rcx]
0x18002ce3f  mov     rax, [rax+10h]
0x18002ce43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce48  test    rbx, rbx
0x18002ce4b  jz      short loc_18002CE5C
0x18002ce4d  mov     rax, [rbx]
0x18002ce50  mov     rcx, rbx
0x18002ce53  mov     rax, [rax+10h]
0x18002ce57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce5c  test    rdi, rdi
0x18002ce5f  jz      short loc_18002CE70
0x18002ce61  mov     rax, [rdi]
0x18002ce64  mov     rcx, rdi
0x18002ce67  mov     rax, [rax+10h]
0x18002ce6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce70  mov     eax, 80070490h
0x18002ce75  jmp     loc_18002CF18
0x18002ce7a  mov     r9d, 3A6h
0x18002ce80  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002ce87  xor     edx, edx
0x18002ce89  mov     ecx, 80070057h
0x18002ce8e  call    Log_UnistoreHREvent_0
0x18002ce93  lea     rcx, [rbp+arg_10]; void *
0x18002ce97  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002ce9c  lea     rcx, [rbp+arg_18]; void *
0x18002cea0  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cea5  lea     rcx, [rbp+arg_0]; void *
0x18002cea9  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002ceae  lea     rcx, [rbp+hMem]; void *
0x18002ceb2  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002ceb7  mov     eax, 80070057h
0x18002cebc  add     rsp, 78h
0x18002cec0  pop     r13
0x18002cec2  pop     r12
0x18002cec4  pop     rsi
0x18002cec5  pop     rbp
0x18002cec6  retn
0x18002cec7  call    cs:__imp_LocalFree
0x18002cecd  mov     rax, [rbp+arg_10]
0x18002ced1  mov     rcx, [rbp+arg_18]
0x18002ced5  mov     [rbp+arg_10], r13
0x18002ced9  mov     [r12], rax
0x18002cedd  test    rcx, rcx
0x18002cee0  jz      short loc_18002CEEE
0x18002cee2  mov     rax, [rcx]
0x18002cee5  mov     rax, [rax+10h]
0x18002cee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ceee  test    rbx, rbx
0x18002cef1  jz      short loc_18002CF02
0x18002cef3  mov     rax, [rbx]
0x18002cef6  mov     rcx, rbx
0x18002cef9  mov     rax, [rax+10h]
0x18002cefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf02  test    rdi, rdi
0x18002cf05  jz      short loc_18002CF16
0x18002cf07  mov     rax, [rdi]
0x18002cf0a  mov     rcx, rdi
0x18002cf0d  mov     rax, [rax+10h]
0x18002cf11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf16  xor     eax, eax
0x18002cf18  mov     r15, [rsp+78h+var_18]
0x18002cf1d  mov     r14, [rsp+78h+var_10]
0x18002cf22  mov     rdi, [rsp+78h+var_8]
0x18002cf27  mov     rbx, [rsp+78h+arg_8]
0x18002cf2f  add     rsp, 78h
0x18002cf33  pop     r13
0x18002cf35  pop     r12
0x18002cf37  pop     rsi
0x18002cf38  pop     rbp
0x18002cf39  retn
0x18002cf3a  mov     eax, cs:?s_dwDeviceStoreId@CStoreManager@@0KA; ulong CStoreManager::s_dwDeviceStoreId
0x18002cf40  test    eax, eax
0x18002cf42  jz      loc_18002D2D9
0x18002cf48  cmp     [rsi], eax
0x18002cf4a  jnb     loc_18002CC77
0x18002cf50  mov     r9d, 3B7h
0x18002cf56  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002cf5d  xor     edx, edx
0x18002cf5f  mov     ecx, 80070490h
0x18002cf64  call    Log_UnistoreHREvent_0
0x18002cf69  lea     rcx, [rbp+arg_10]; void *
0x18002cf6d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cf72  lea     rcx, [rbp+arg_18]; void *
0x18002cf76  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cf7b  lea     rcx, [rbp+arg_0]; void *
0x18002cf7f  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cf84  lea     rcx, [rbp+hMem]; void *
0x18002cf88  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cf8d  mov     eax, 80070490h
0x18002cf92  jmp     short loc_18002CF27
0x18002cf94  mov     eax, [rsi]
0x18002cf96  cmp     [rcx+8], eax
0x18002cf99  jz      loc_18002CEC7
0x18002cf9f  mov     r9d, 3DAh
0x18002cfa5  jmp     loc_18002CDFE
0x18002cfaa  mov     eax, [rsi]
0x18002cfac  cmp     [rsi+8], eax
0x18002cfaf  jz      loc_18002CECD
0x18002cfb5  mov     r9d, 3D2h
0x18002cfbb  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002cfc2  xor     edx, edx
0x18002cfc4  mov     ecx, 80070490h
0x18002cfc9  call    Log_UnistoreHREvent_0
0x18002cfce  lea     rcx, [rbp+arg_10]; void *
0x18002cfd2  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cfd7  lea     rcx, [rbp+arg_18]; void *
0x18002cfdb  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cfe0  lea     rcx, [rbp+arg_0]; void *
0x18002cfe4  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cfe9  lea     rcx, [rbp+hMem]; void *
0x18002cfed  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002cff2  mov     eax, 80070490h
0x18002cff7  jmp     loc_18002CF18
0x18002cffc  cmp     [rcx], r13d
0x18002cfff  jz      loc_18002CC77
0x18002d005  mov     r9d, 3AEh
0x18002d00b  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002d012  xor     edx, edx
0x18002d014  mov     ecx, 80070057h
0x18002d019  call    Log_UnistoreHREvent_0
0x18002d01e  mov     rcx, [rbp+arg_10]
0x18002d022  test    rcx, rcx
0x18002d025  jz      short loc_18002D033
0x18002d027  mov     rax, [rcx]
0x18002d02a  mov     rax, [rax+10h]
0x18002d02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d033  mov     rcx, [rbp+arg_18]
0x18002d037  test    rcx, rcx
0x18002d03a  jnz     loc_18002D2C8
0x18002d040  mov     eax, 80070057h
0x18002d045  jmp     loc_18002CF27
0x18002d04a  mov     r9d, 3CEh
0x18002d050  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002d057  mov     edx, 1
0x18002d05c  mov     ecx, r14d
0x18002d05f  call    Log_UnistoreHREvent_0
0x18002d064  mov     rcx, [rbp+arg_10]
0x18002d068  test    rcx, rcx
0x18002d06b  jz      short loc_18002D079
0x18002d06d  mov     rax, [rcx]
0x18002d070  mov     rax, [rax+10h]
0x18002d074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d079  mov     rcx, [rbp+arg_18]
0x18002d07d  test    rcx, rcx
0x18002d080  jz      short loc_18002D08E
0x18002d082  mov     rax, [rcx]
0x18002d085  mov     rax, [rax+10h]
0x18002d089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d08e  test    rbx, rbx
0x18002d091  jz      short loc_18002D0A2
0x18002d093  mov     rax, [rbx]
0x18002d096  mov     rcx, rbx
0x18002d099  mov     rax, [rax+10h]
0x18002d09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0a2  test    rdi, rdi
0x18002d0a5  jz      short loc_18002D0B6
0x18002d0a7  mov     rax, [rdi]
0x18002d0aa  mov     rcx, rdi
0x18002d0ad  mov     rax, [rax+10h]
0x18002d0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b6  mov     eax, r14d
0x18002d0b9  jmp     loc_18002CF18
0x18002d0be  call    cs:__imp_LocalFree
  ... truncated ...
```
