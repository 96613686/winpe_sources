# CWatcherFactory::UnregisterLocalChangeWatcher(ushort const *,_GUID const &,ushort const *,bool)

- ea: `0x180030140`
- end: `0x18003053a`
- name: `?UnregisterLocalChangeWatcher@CWatcherFactory@@UEAAXPEBGAEBU_GUID@@0_N@Z`
- size: `1018`
- prototype: `void __fastcall(CWatcherFactory *__hidden this, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180009158`
- `0x180011314`
- `0x18001133c`
- `0x180028d00`
- `0x18002e848`
- `0x18002e908`
- `0x18002ea68`
- `0x18002fe24`
- `0x180030140`
- `0x1800644c4`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800301ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003035e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800301ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003035e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CWatcherFactory::UnregisterLocalChangeWatcher(
        CWatcherFactory *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned __int16 *a4,
        bool a5)
{
  _BYTE *v6; // rax
  char v7; // al
  HRESULT v8; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // eax
  HRESULT v12; // eax
  int v13; // eax
  CWatcherFactory *v14; // rcx
  int v15; // edi
  int v16; // r14d
  int v17; // eax
  int v18; // [rsp+30h] [rbp-118h] BYREF
  int v19; // [rsp+34h] [rbp-114h]
  char v20; // [rsp+38h] [rbp-110h]
  const char *v21; // [rsp+40h] [rbp-108h]
  __int64 v22; // [rsp+48h] [rbp-100h]
  _BYTE *v23; // [rsp+50h] [rbp-F8h] BYREF
  _BYTE *v24; // [rsp+58h] [rbp-F0h]
  LPVOID ppv; // [rsp+60h] [rbp-E8h] BYREF
  HRESULT pExceptionObject; // [rsp+68h] [rbp-E0h] BYREF
  HRESULT v27; // [rsp+6Ch] [rbp-DCh] BYREF
  int v28; // [rsp+70h] [rbp-D8h] BYREF
  int v29; // [rsp+74h] [rbp-D4h] BYREF
  int v30; // [rsp+78h] [rbp-D0h] BYREF
  int v31; // [rsp+7Ch] [rbp-CCh] BYREF
  LPVOID v32; // [rsp+80h] [rbp-C8h] BYREF
  int v33; // [rsp+88h] [rbp-C0h] BYREF
  int v34; // [rsp+8Ch] [rbp-BCh] BYREF
  int v35; // [rsp+90h] [rbp-B8h] BYREF
  unsigned __int16 *v36; // [rsp+98h] [rbp-B0h]
  const ATL::CAtlException *v37; // [rsp+A0h] [rbp-A8h] BYREF
  const ATL::CAtlException *v38; // [rsp+A8h] [rbp-A0h] BYREF
  const ATL::CAtlException *v39; // [rsp+B0h] [rbp-98h] BYREF
  _BYTE v40[64]; // [rsp+B8h] [rbp-90h] BYREF
  _BYTE v41[8]; // [rsp+F8h] [rbp-50h] BYREF
  __int128 v42; // [rsp+100h] [rbp-48h]

  v36 = a4;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v7 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 8) == 0 || v6[65] < 6u )
    goto LABEL_8;
  v7 = 1;
LABEL_9:
  v18 = 0;
  v19 = 192;
  v20 = v7;
  v21 = "CWatcherFactory::UnregisterLocalChangeWatcher";
  v22 = 0;
  try
  {
    ppv = 0;
    v8 = CoCreateInstance(
           &GUID_69f31c37_09e1_433b_aecb_ebc83e4065d9,
           0,
           1u,
           &GUID_5c4c1c61_6779_4c4b_9c8a_da2653ce628d,
           &ppv);
    v18 = v8;
    if ( v8 < 0 )
    {
      HIWORD(v19) = 208;
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v19) = 208;
    v23 = v40;
    ATL::CComPtr<IStorageConfiguration>::CComPtr<IStorageConfiguration>(v41, &ppv);
    v42 = (__int128)*a3;
    v9 = std::function_long___cdecl_void__::function_long___cdecl_void____lambda_a81f4081553fc48b4c1d9ca8acca4500__0_(
           v40,
           v41);
    CChangeTrackerHelper::CallChangeTrackerWithRetry(v9);
    lambda_a81f4081553fc48b4c1d9ca8acca4500_::__lambda_a81f4081553fc48b4c1d9ca8acca4500_(v41);
    v24 = v40;
    ATL::CComPtr<IStorageConfiguration>::CComPtr<IStorageConfiguration>(&v23, &ppv);
    v10 = std::function_long___cdecl_void__::function_long___cdecl_void____lambda_0e8b3c5e4f412a327ea5074593eec10f__0_(
            v40,
            &v23);
    CChangeTrackerHelper::CallChangeTrackerWithRetry(v10);
    lambda_a81f4081553fc48b4c1d9ca8acca4500_::__lambda_a81f4081553fc48b4c1d9ca8acca4500_(&v23);
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&ppv);
  }
  catch ( long v33 )
  {
    v18 = v33;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v19) = 223;
    v18 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v19) = 223;
    v18 = -2147418113;
  }
  catch ( const ATL::CAtlException *v37 )
  {
    HIWORD(v19) = 223;
    v18 = *(_DWORD *)v37;
  }
  LODWORD(v23) = 0;
  v11 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids);
      v11 = v18;
    }
    LODWORD(v23) = v11;
    v18 = 0;
  }
  try
  {
    v32 = 0;
    v12 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v32);
    v18 = v12;
    if ( v12 < 0 )
    {
      HIWORD(v19) = 237;
      v27 = v12;
      throw (long *)&v27;
    }
    LOWORD(v19) = 237;
    v13 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v32 + 160LL))(v32, L"WorkFolders");
    v18 = v13;
    if ( v13 < 0 )
    {
      HIWORD(v19) = 239;
      v28 = v13;
      throw (long *)&v28;
    }
    LOWORD(v19) = 239;
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v32);
  }
  catch ( long v34 )
  {
    v18 = v34;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v19) = 241;
    v18 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v19) = 241;
    v18 = -2147418113;
  }
  catch ( const ATL::CAtlException *v38 )
  {
    HIWORD(v19) = 241;
    v14 = (CWatcherFactory *)*(unsigned int *)v38;
    v18 = *(_DWORD *)v38;
  }
  v15 = 0;
  LODWORD(v24) = 0;
  v16 = 0;
  v17 = v18;
  if ( v18 < 0 )
  {
    v14 = (CWatcherFactory *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids);
      v17 = v18;
    }
    v15 = v17;
    LODWORD(v24) = v17;
    v18 = 0;
  }
  if ( a5 )
  {
    try
    {
      CWatcherFactory::RemoveSearchIndexOnExpandedLocalPath(v14, v36);
    }
    catch ( long v35 )
    {
      v18 = v35;
      v15 = (int)v24;
    }
    catch ( std::bad_alloc )
    {
      HIWORD(v19) = 257;
      v18 = -2147024882;
      v15 = (int)v24;
    }
    catch ( std::exception )
    {
      HIWORD(v19) = 257;
      v18 = -2147418113;
      v15 = (int)v24;
    }
    catch ( const ATL::CAtlException *v39 )
    {
      HIWORD(v19) = 257;
      v18 = *(_DWORD *)v39;
      v15 = (int)v24;
    }
    v16 = v18;
  }
  v18 = (int)v23;
  if ( (int)v23 < 0 )
  {
    HIWORD(v19) = 264;
    v29 = (int)v23;
    throw (long *)&v29;
  }
  LOWORD(v19) = 264;
  v18 = v15;
  if ( v15 < 0 )
  {
    HIWORD(v19) = 265;
    v30 = v15;
    throw (long *)&v30;
  }
  LOWORD(v19) = 265;
  v18 = v16;
  if ( v16 < 0 )
  {
    HIWORD(v19) = 266;
    v31 = v16;
    throw (long *)&v31;
  }
  LOWORD(v19) = 266;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v18);
}

```

## disassembly

```asm
0x180030140  push    rbx
0x180030142  push    rsi
0x180030143  push    rdi
0x180030144  push    r14
0x180030146  sub     rsp, 128h
0x18003014d  mov     rax, cs:__security_cookie
0x180030154  xor     rax, rsp
0x180030157  mov     [rsp+148h+var_38], rax
0x18003015f  mov     rdi, r8
0x180030162  mov     [rsp+148h+var_B0], r9
0x18003016a  lea     rsi, WPP_GLOBAL_Control
0x180030171  mov     rax, cs:WPP_GLOBAL_Control
0x180030178  cmp     rax, rsi
0x18003017b  jz      short loc_1800301A5
0x18003017d  test    byte ptr [rax+44h], 8
0x180030181  jz      short loc_1800301B7
0x180030183  cmp     byte ptr [rax+41h], 6
0x180030187  jb      short loc_1800301A5
0x180030189  mov     edx, 0Fh
0x18003018e  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x180030195  mov     rcx, [rax+38h]
0x180030199  call    WPP_SF_
0x18003019e  mov     rax, cs:WPP_GLOBAL_Control
0x1800301a5  test    byte ptr [rax+44h], 8
0x1800301a9  jz      short loc_1800301B7
0x1800301ab  cmp     byte ptr [rax+41h], 6
0x1800301af  jb      short loc_1800301B7
0x1800301b1  mov     al, 1
0x1800301b3  xor     ebx, ebx
0x1800301b5  jmp     short loc_1800301BB
0x1800301b7  xor     ebx, ebx
0x1800301b9  mov     al, bl
0x1800301bb  mov     [rsp+148h+var_118], ebx
0x1800301bf  mov     [rsp+148h+var_114], 0C0h
0x1800301c7  mov     [rsp+148h+var_110], al
0x1800301cb  lea     rax, aCwatcherfactor_1; "CWatcherFactory::UnregisterLocalChangeW"...
0x1800301d2  mov     [rsp+148h+var_108], rax
0x1800301d7  mov     [rsp+148h+var_100], rbx
0x1800301dc  mov     [rsp+148h+var_E8], rbx
0x1800301e1  lea     rax, [rsp+148h+var_E8]
0x1800301e6  mov     [rsp+148h+ppv], rax; ppv
0x1800301eb  lea     r9, _GUID_5c4c1c61_6779_4c4b_9c8a_da2653ce628d; riid
0x1800301f2  xor     edx, edx; pUnkOuter
0x1800301f4  lea     r8d, [rdx+1]; dwClsContext
0x1800301f8  lea     rcx, _GUID_69f31c37_09e1_433b_aecb_ebc83e4065d9; rclsid
0x1800301ff  call    cs:__imp_CoCreateInstance
0x180030205  mov     [rsp+148h+var_118], eax
0x180030209  mov     [rsp+148h+var_118], eax
0x18003020d  mov     ecx, 0D0h
0x180030212  test    eax, eax
0x180030214  jns     short loc_180030230
0x180030216  mov     word ptr [rsp+148h+var_114+2], cx
0x18003021b  mov     [rsp+148h+pExceptionObject], eax
0x18003021f  lea     rdx, _TI1J; pThrowInfo
0x180030226  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18003022b  call    _CxxThrowException_0
0x180030230  mov     word ptr [rsp+148h+var_114], cx
0x180030235  lea     rax, [rsp+148h+var_90]
0x18003023d  mov     [rsp+148h+var_F8], rax
0x180030242  lea     rdx, [rsp+148h+var_E8]
0x180030247  lea     rcx, [rsp+148h+var_50]
0x18003024f  call    ??0?$CComPtr@UIStorageConfiguration@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IStorageConfiguration>::CComPtr<IStorageConfiguration>(ATL::CComPtr<IStorageConfiguration> const &)
0x180030254  nop
0x180030255  movups  xmm0, xmmword ptr [rdi]
0x180030258  movdqu  [rsp+148h+var_48], xmm0
0x180030261  lea     rdx, [rsp+148h+var_50]
0x180030269  lea     rcx, [rsp+148h+var_90]
0x180030271  call    std__function_long___cdecl_void____function_long___cdecl_void____lambda_a81f4081553fc48b4c1d9ca8acca4500__0_
0x180030276  nop
0x180030277  mov     rcx, rax
0x18003027a  call    ?CallChangeTrackerWithRetry@CChangeTrackerHelper@@SAXV?$function@$$A6AJXZ@std@@@Z; CChangeTrackerHelper::CallChangeTrackerWithRetry(std::function<long (void)>)
0x18003027f  nop
0x180030280  lea     rcx, [rsp+148h+var_50]
0x180030288  call    _lambda_a81f4081553fc48b4c1d9ca8acca4500_____lambda_a81f4081553fc48b4c1d9ca8acca4500_
0x18003028d  lea     rax, [rsp+148h+var_90]
0x180030295  mov     [rsp+148h+var_F0], rax
0x18003029a  lea     rdx, [rsp+148h+var_E8]
0x18003029f  lea     rcx, [rsp+148h+var_F8]
0x1800302a4  call    ??0?$CComPtr@UIStorageConfiguration@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IStorageConfiguration>::CComPtr<IStorageConfiguration>(ATL::CComPtr<IStorageConfiguration> const &)
0x1800302a9  nop
0x1800302aa  lea     rdx, [rsp+148h+var_F8]
0x1800302af  lea     rcx, [rsp+148h+var_90]
0x1800302b7  call    std__function_long___cdecl_void____function_long___cdecl_void____lambda_0e8b3c5e4f412a327ea5074593eec10f__0_
0x1800302bc  nop
0x1800302bd  mov     rcx, rax
0x1800302c0  call    ?CallChangeTrackerWithRetry@CChangeTrackerHelper@@SAXV?$function@$$A6AJXZ@std@@@Z; CChangeTrackerHelper::CallChangeTrackerWithRetry(std::function<long (void)>)
0x1800302c5  nop
0x1800302c6  lea     rcx, [rsp+148h+var_F8]
0x1800302cb  call    _lambda_a81f4081553fc48b4c1d9ca8acca4500_____lambda_a81f4081553fc48b4c1d9ca8acca4500_
0x1800302d0  nop
0x1800302d1  lea     rcx, [rsp+148h+var_E8]
0x1800302d6  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x1800302db  nop
0x1800302dc  jmp     short loc_1800302ED
0x1800302de  jmp     short loc_1800302E4
0x1800302e0  jmp     short loc_1800302E4
0x1800302e2  jmp     short $+2
0x1800302e4  xor     ebx, ebx
0x1800302e6  lea     rsi, WPP_GLOBAL_Control
0x1800302ed  mov     dword ptr [rsp+148h+var_F8], ebx
0x1800302f1  mov     eax, [rsp+148h+var_118]
0x1800302f5  test    eax, eax
0x1800302f7  jns     short loc_180030335
0x1800302f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030300  cmp     rcx, rsi
0x180030303  jz      short loc_18003032D
0x180030305  test    byte ptr [rcx+44h], 8
0x180030309  jz      short loc_18003032D
0x18003030b  cmp     byte ptr [rcx+41h], 2
0x18003030f  jb      short loc_18003032D
0x180030311  mov     edx, 10h
0x180030316  mov     r9d, eax
0x180030319  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x180030320  mov     rcx, [rcx+38h]
0x180030324  call    WPP_SF_d
0x180030329  mov     eax, [rsp+148h+var_118]
0x18003032d  mov     dword ptr [rsp+148h+var_F8], eax
0x180030331  mov     [rsp+148h+var_118], ebx
0x180030335  mov     [rsp+148h+var_C8], rbx
0x18003033d  lea     rax, [rsp+148h+var_C8]
0x180030345  mov     [rsp+148h+ppv], rax; ppv
0x18003034a  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180030351  xor     edx, edx; pUnkOuter
0x180030353  lea     r8d, [rdx+1]; dwClsContext
0x180030357  lea     rcx, CLSID_SyncRootManager; rclsid
0x18003035e  call    cs:__imp_CoCreateInstance
0x180030364  mov     [rsp+148h+var_118], eax
0x180030368  mov     [rsp+148h+var_118], eax
0x18003036c  mov     ecx, 0EDh
0x180030371  test    eax, eax
0x180030373  jns     short loc_18003038F
0x180030375  mov     word ptr [rsp+148h+var_114+2], cx
0x18003037a  mov     [rsp+148h+var_DC], eax
0x18003037e  lea     rdx, _TI1J; pThrowInfo
0x180030385  lea     rcx, [rsp+148h+var_DC]; pExceptionObject
0x18003038a  call    _CxxThrowException_0
0x18003038f  mov     word ptr [rsp+148h+var_114], cx
0x180030394  mov     rcx, [rsp+148h+var_C8]
0x18003039c  mov     rax, [rcx]
0x18003039f  lea     rdx, aWorkfolders; "WorkFolders"
0x1800303a6  mov     rax, [rax+0A0h]
0x1800303ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303b2  mov     [rsp+148h+var_118], eax
0x1800303b6  mov     [rsp+148h+var_118], eax
0x1800303ba  mov     ecx, 0EFh
0x1800303bf  test    eax, eax
0x1800303c1  jns     short loc_1800303DD
0x1800303c3  mov     word ptr [rsp+148h+var_114+2], cx
0x1800303c8  mov     [rsp+148h+var_D8], eax
0x1800303cc  lea     rdx, _TI1J; pThrowInfo
0x1800303d3  lea     rcx, [rsp+148h+var_D8]; pExceptionObject
0x1800303d8  call    _CxxThrowException_0
0x1800303dd  mov     word ptr [rsp+148h+var_114], cx
0x1800303e2  lea     rcx, [rsp+148h+var_C8]
0x1800303ea  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x1800303ef  nop
0x1800303f0  jmp     short loc_180030401
0x1800303f2  jmp     short loc_1800303F8
0x1800303f4  jmp     short loc_1800303F8
0x1800303f6  jmp     short $+2
0x1800303f8  xor     ebx, ebx
0x1800303fa  lea     rsi, WPP_GLOBAL_Control
0x180030401  mov     edi, ebx
0x180030403  mov     dword ptr [rsp+148h+var_F0], ebx
0x180030407  mov     r14d, ebx
0x18003040a  mov     eax, [rsp+148h+var_118]
0x18003040e  test    eax, eax
0x180030410  jns     short loc_180030450
0x180030412  mov     rcx, cs:WPP_GLOBAL_Control
0x180030419  cmp     rcx, rsi
0x18003041c  jz      short loc_180030446
0x18003041e  test    byte ptr [rcx+44h], 8
0x180030422  jz      short loc_180030446
0x180030424  cmp     byte ptr [rcx+41h], 2
0x180030428  jb      short loc_180030446
0x18003042a  mov     edx, 11h
0x18003042f  mov     r9d, eax
0x180030432  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x180030439  mov     rcx, [rcx+38h]
0x18003043d  call    WPP_SF_d
0x180030442  mov     eax, [rsp+148h+var_118]
0x180030446  mov     edi, eax
0x180030448  mov     dword ptr [rsp+148h+var_F0], eax
0x18003044c  mov     [rsp+148h+var_118], ebx
0x180030450  cmp     [rsp+148h+arg_20], bl
0x180030457  jz      short loc_180030478
0x180030459  mov     rdx, [rsp+148h+var_B0]; unsigned __int16 *
0x180030461  call    ?RemoveSearchIndexOnExpandedLocalPath@CWatcherFactory@@AEAAXPEBG@Z; CWatcherFactory::RemoveSearchIndexOnExpandedLocalPath(ushort const *)
0x180030466  nop
0x180030467  jmp     short loc_180030473
0x180030469  jmp     short loc_18003046F
0x18003046b  jmp     short loc_18003046F
0x18003046d  jmp     short $+2
0x18003046f  mov     edi, dword ptr [rsp+148h+var_F0]
0x180030473  mov     r14d, [rsp+148h+var_118]
0x180030478  mov     eax, dword ptr [rsp+148h+var_F8]
0x18003047c  mov     [rsp+148h+var_118], eax
0x180030480  mov     [rsp+148h+var_118], eax
0x180030484  mov     ecx, 108h
0x180030489  test    eax, eax
0x18003048b  jns     short loc_1800304A8
0x18003048d  mov     word ptr [rsp+148h+var_114+2], cx
0x180030492  mov     [rsp+148h+var_D4], eax
0x180030496  lea     rdx, _TI1J; pThrowInfo
0x18003049d  lea     rcx, [rsp+148h+var_D4]; pExceptionObject
0x1800304a2  call    _CxxThrowException_0
0x1800304a8  mov     word ptr [rsp+148h+var_114], cx
0x1800304ad  mov     [rsp+148h+var_118], edi
0x1800304b1  mov     [rsp+148h+var_118], edi
0x1800304b5  mov     eax, 109h
0x1800304ba  test    edi, edi
0x1800304bc  jns     short loc_1800304D9
0x1800304be  mov     word ptr [rsp+148h+var_114+2], ax
0x1800304c3  mov     [rsp+148h+var_D0], edi
0x1800304c7  lea     rdx, _TI1J; pThrowInfo
0x1800304ce  lea     rcx, [rsp+148h+var_D0]; pExceptionObject
0x1800304d3  call    _CxxThrowException_0
0x1800304d9  mov     word ptr [rsp+148h+var_114], ax
0x1800304de  mov     [rsp+148h+var_118], r14d
0x1800304e3  mov     [rsp+148h+var_118], r14d
0x1800304e8  mov     eax, 10Ah
0x1800304ed  test    r14d, r14d
0x1800304f0  jns     short loc_18003050E
0x1800304f2  mov     word ptr [rsp+148h+var_114+2], ax
0x1800304f7  mov     [rsp+148h+var_CC], r14d
0x1800304fc  lea     rdx, _TI1J; pThrowInfo
0x180030503  lea     rcx, [rsp+148h+var_CC]; pExceptionObject
0x180030508  call    _CxxThrowException_0
0x18003050e  mov     word ptr [rsp+148h+var_114], ax
0x180030513  lea     rcx, [rsp+148h+var_118]; this
0x180030518  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003051d  mov     rcx, [rsp+148h+var_38]
0x180030525  xor     rcx, rsp; StackCookie
0x180030528  call    __security_check_cookie
0x18003052d  add     rsp, 128h
0x180030534  pop     r14
0x180030536  pop     rdi
0x180030537  pop     rsi
0x180030538  pop     rbx
0x180030539  retn
```
