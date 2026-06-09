# GetOlItemIdFromRemoteIdImpl(UdmObjectId,ushort const *,OLITEMID *)

- ea: `0x1800510dc`
- end: `0x18005177b`
- name: `?GetOlItemIdFromRemoteIdImpl@@YAJUUdmObjectId@@PEBGPEAUOLITEMID@@@Z`
- size: `1695`
- prototype: `int __high(struct UdmObjectId, const unsigned __int16 *, struct OLITEMID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ec80`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18000ae80`
- `0x1800510dc`
- `0x18005ea14`
- `0x180068780`
- `0x1800688fc`
- `0x180072ccc`
- `0x1800977ac`
- `0x1800977b8`
- `0x1800bf6b8`
- `0x1800e482c`
- `0x1800e9c60`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x180051342`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x180051342`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005117d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005117d`
- `unistore!CreateStoreManager` at `0x1800512ef`
- `unistore!CreateStoreManager` at `0x1800512ef`

## string_xrefs

- `0x180051139`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800511c1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800512b8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x180051302`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x180051355`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x1800513a0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x18005140a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x18005145a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x18005157e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`
- `0x180051649`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\other.cpp`

## pseudocode

```c
__int64 __fastcall GetOlItemIdFromRemoteIdImpl(unsigned int *a1, const unsigned __int16 *a2, __int64 a3)
{
  __int64 v4; // rdx
  bool v5; // zf
  __int64 v8; // r9
  int v9; // ebx
  void *v11; // rbx
  StorePropertyCache *v12; // rdi
  int PropertiesForStore; // eax
  int v14; // edi
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r15
  void *v18; // rdi
  void *v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // r14d
  int v23; // eax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // r9
  unsigned int v28; // ecx
  __int64 v29; // r9
  __int64 v30; // r8
  int *v31; // rdx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r9
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL fPending; // [rsp+7Ch] [rbp-84h] BYREF
  LPVOID Context; // [rsp+80h] [rbp-80h] BYREF
  union _RTL_RUN_ONCE *v48; // [rsp+88h] [rbp-78h] BYREF
  struct StorePropertySet *v49[2]; // [rsp+90h] [rbp-70h] BYREF
  int v50; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v51; // [rsp+A4h] [rbp-5Ch]
  __int128 v52; // [rsp+B4h] [rbp-4Ch]
  int v53; // [rsp+C4h] [rbp-3Ch]
  const unsigned __int16 *v54; // [rsp+C8h] [rbp-38h]
  void *Block; // [rsp+D0h] [rbp-30h] BYREF
  int v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h] BYREF
  int v58; // [rsp+E8h] [rbp-18h]
  __int64 v59; // [rsp+F0h] [rbp-10h] BYREF
  int v60; // [rsp+F8h] [rbp-8h]
  int v61; // [rsp+100h] [rbp+0h]
  _DWORD v62[2]; // [rsp+108h] [rbp+8h] BYREF
  char *v63; // [rsp+110h] [rbp+10h]
  char v64; // [rsp+118h] [rbp+18h] BYREF

  *(_QWORD *)a3 = g_ZeroOlItemId;
  v4 = 0;
  v5 = a1[1] == 36;
  *(_DWORD *)(a3 + 8) = 0;
  if ( !v5 )
  {
    v8 = 153;
    v9 = -2147024809;
LABEL_3:
    Log_HREvent(
      (unsigned int)v9,
      v4,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      v8);
    return (unsigned int)v9;
  }
  v11 = 0;
  v41[0] = 0;
  Block = 0;
  v49[0] = 0;
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, &Context);
  v12 = (StorePropertyCache *)Context;
  if ( !Context )
  {
    v48 = &stru_18015EA68;
    v12 = (StorePropertyCache *)tlx::_LazyImpl<StorePropertyCache,tlx::lazy_construct<StorePropertyCache>,tlx::static_lazy<StorePropertyCache,0,tlx::lazy_construct<StorePropertyCache>>>::_Initializer::_Construct(&v48);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v48);
  }
  PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v12, *a1, v49);
  v14 = PropertiesForStore;
  if ( PropertiesForStore < 0 )
  {
    Log_HREvent(
      (unsigned int)PropertiesForStore,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      162);
    return (unsigned int)v14;
  }
  if ( *((_QWORD *)v49[0] + 1) )
  {
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = v15 + 1;
    if ( v15 + 1 < v15 )
    {
      v8 = 166;
LABEL_14:
      v4 = 1;
      v9 = -2147024362;
      goto LABEL_3;
    }
    Block = 0;
    v17 = 2 * v16;
    if ( !is_mul_ok(v16, 2u) )
    {
      v8 = 167;
      goto LABEL_14;
    }
    if ( v17 > 0xFFFFFFFF )
    {
      v8 = 169;
      goto LABEL_14;
    }
    v18 = 0;
  }
  else
  {
    v9 = HexStringToBinary(a2, 0, v41);
    if ( v9 < 0 )
    {
      v8 = 174;
      v4 = 1;
      goto LABEL_3;
    }
    v19 = operator new[](v41[0]);
    tlx::auto_xxx<unsigned char *,void (*)(unsigned char *),&void tlx::_delete_array<unsigned char>(unsigned char *),0>::reset(
      &Block,
      v19);
    v11 = Block;
    if ( !Block )
    {
      v8 = 177;
      v4 = 0;
      v9 = -2147024882;
      goto LABEL_3;
    }
    v20 = HexStringToBinary(a2, (unsigned __int8 *)Block, v41);
    v14 = v20;
    if ( v20 < 0 )
    {
      Log_HREvent(
        (unsigned int)v20,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
        179);
LABEL_26:
      operator delete(v11);
      return (unsigned int)v14;
    }
    LODWORD(v17) = v41[0];
    a2 = (const unsigned __int16 *)v11;
    v18 = v11;
  }
  v38 = 0;
  v21 = CreateStoreManager(0, &v38);
  v22 = v21;
  if ( v21 < 0 )
  {
    Log_HREvent(
      (unsigned int)v21,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      184);
LABEL_30:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v38);
    if ( v18 )
      operator delete(v11);
    return (unsigned int)v22;
  }
  v39 = 0;
  v23 = POutlookAppManager_CreateInstance(&v39);
  v22 = v23;
  if ( v23 < 0 )
  {
    Log_HREvent(
      (unsigned int)v23,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      187);
LABEL_35:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
    goto LABEL_30;
  }
  v40 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 32LL))(v39, &v40);
  v22 = v24;
  if ( v24 < 0 )
  {
    Log_HREvent(
      (unsigned int)v24,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      190);
LABEL_38:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v40);
    goto LABEL_35;
  }
  v42 = 0;
  v25 = UdmIdToPoomId(&Block, a1);
  v59 = *(_QWORD *)v25;
  v60 = *(_DWORD *)(v25 + 8);
  v26 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v40 + 112LL))(v40, &v59, &v42);
  v22 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent(
      (unsigned int)v26,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      194);
LABEL_41:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
    goto LABEL_38;
  }
  v43 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v42 + 96LL))(v42, 10, &v43);
  if ( v22 < 0 )
  {
    v27 = 197;
LABEL_44:
    Log_HREvent(
      (unsigned int)v22,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      v27);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v43);
    goto LABEL_41;
  }
  v57 = 0;
  v58 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 24LL))(v43, &v57);
  if ( v22 < 0 )
  {
    v27 = 200;
    goto LABEL_44;
  }
  v50 = 235470867;
  v52 = 0;
  DWORD1(v52) = 17432641;
  v53 = 0;
  HIDWORD(v52) = v17;
  v51 = 0;
  DWORD1(v51) = v58;
  v54 = a2;
  memset_0(v62, 0, 0x40u);
  v62[0] = 2;
  v61 = 0;
  v63 = &v64;
  v28 = 0;
  do
  {
    v29 = v28 + 1;
    v30 = 3 * v29;
    v62[2 * v30] = 4;
    v62[2 * v30] = 4;
    v31 = &v50 + 6 * v28++;
    v62[2 * v30 + 1] = *v31;
    (&v63)[v30] = (char *)v31;
  }
  while ( (unsigned int)v29 < v62[0] );
  v44 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v38 + 136LL))(v38, 1, 0x2000000);
  v14 = v32;
  if ( v32 < 0 )
  {
    Log_HREvent(
      (unsigned int)v32,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      229);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_62:
    if ( !v11 )
      return (unsigned int)v14;
    goto LABEL_26;
  }
  v45 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 24LL))(v44, &v45);
  if ( v14 < 0 )
  {
    v35 = 232;
LABEL_66:
    Log_HREvent(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\other.cpp",
      v35);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v43);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v40);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v38);
    goto LABEL_62;
  }
  if ( v45 == 1 )
  {
    Block = 0;
    v56 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v44 + 88LL))(v44, &Block);
    if ( v14 < 0 )
    {
      v35 = 237;
      goto LABEL_66;
    }
    v36 = USOIDToOLITEMID(v49, &Block);
    v37 = *(_DWORD *)(v36 + 8);
    *(_QWORD *)a3 = *(_QWORD *)v36;
    *(_DWORD *)(a3 + 8) = v37;
  }
  else if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x200) != 0 )
  {
    McTemplateU0xq_EventWriteTransfer(v34, v33, *a1);
  }
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v43);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v40);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v38);
  if ( v11 )
    operator delete(v11);
  return 0;
}

```

## disassembly

```asm
0x1800510dc  mov     [rsp-8+arg_18], rbx
0x1800510e1  push    rbp
0x1800510e2  push    rsi
0x1800510e3  push    rdi
0x1800510e4  push    r12
0x1800510e6  push    r13
0x1800510e8  push    r14
0x1800510ea  push    r15
0x1800510ec  lea     rbp, [rsp-60h]
0x1800510f1  sub     rsp, 160h
0x1800510f8  mov     rax, cs:__security_cookie
0x1800510ff  xor     rax, rsp
0x180051102  mov     [rbp+90h+var_40], rax
0x180051106  movsd   xmm0, cs:?g_ZeroOlItemId@@3UOLITEMID@@B; OLITEMID const g_ZeroOlItemId
0x18005110e  mov     rsi, rdx
0x180051111  movsd   qword ptr [r8], xmm0
0x180051116  xor     edx, edx; dwFlags
0x180051118  cmp     dword ptr [rcx+4], 24h ; '$'
0x18005111c  mov     r13, r8
0x18005111f  mov     eax, cs:dword_18013A438
0x180051125  mov     r12, rcx
0x180051128  mov     [r8+8], eax
0x18005112c  jz      short loc_18005114E
0x18005112e  mov     r9d, 99h
0x180051134  mov     ebx, 80070057h
0x180051139  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051140  mov     ecx, ebx
0x180051142  call    Log_HREvent
0x180051147  mov     eax, ebx
0x180051149  jmp     loc_180051754
0x18005114e  xor     r14d, r14d
0x180051151  lea     r15, stru_18015EA68
0x180051158  mov     ebx, r14d
0x18005115b  mov     [rsp+190h+var_138], r14d
0x180051160  lea     r9, [rbp+90h+Context]; lpContext
0x180051164  mov     [rbp+90h+Block], rbx
0x180051168  lea     r8, [rsp+190h+fPending]; fPending
0x18005116d  mov     [rbp+90h+var_100], r14
0x180051171  mov     rcx, r15; lpInitOnce
0x180051174  mov     [rsp+190h+fPending], r14d
0x180051179  mov     [rbp+90h+Context], r14
0x18005117d  call    cs:__imp_InitOnceBeginInitialize
0x180051183  mov     rdi, [rbp+90h+Context]
0x180051187  test    rdi, rdi
0x18005118a  jnz     short loc_1800511A5
0x18005118c  lea     rcx, [rbp+90h+var_108]
0x180051190  mov     [rbp+90h+var_108], r15
0x180051194  call    ?_Construct@_Initializer@?$_LazyImpl@VStorePropertyCache@@V?$lazy_construct@VStorePropertyCache@@@tlx@@V?$static_lazy@VStorePropertyCache@@$0A@V?$lazy_construct@VStorePropertyCache@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<StorePropertyCache,tlx::lazy_construct<StorePropertyCache>,tlx::static_lazy<StorePropertyCache,0,tlx::lazy_construct<StorePropertyCache>>>::_Initializer::_Construct(void)
0x180051199  lea     rcx, [rbp+90h+var_108]
0x18005119d  mov     rdi, rax
0x1800511a0  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800511a5  mov     edx, [r12]; unsigned int
0x1800511a9  lea     r8, [rbp+90h+var_100]; struct StorePropertySet **
0x1800511ad  mov     rcx, rdi; this
0x1800511b0  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x1800511b5  mov     edi, eax
0x1800511b7  test    eax, eax
0x1800511b9  jns     short loc_1800511DB
0x1800511bb  mov     r9d, 0A2h
0x1800511c1  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800511c8  mov     edx, 1
0x1800511cd  mov     ecx, eax
0x1800511cf  call    Log_HREvent
0x1800511d4  mov     eax, edi
0x1800511d6  jmp     loc_180051754
0x1800511db  mov     rax, [rbp+90h+var_100]
0x1800511df  cmp     [rax+8], r14
0x1800511e3  jz      short loc_180051247
0x1800511e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800511e9  inc     rax
0x1800511ec  cmp     [rsi+rax*2], r14w
0x1800511f1  jnz     short loc_1800511E9
0x1800511f3  lea     rcx, [rax+1]
0x1800511f7  cmp     rcx, rax
0x1800511fa  jnb     short loc_180051211
0x1800511fc  mov     r9d, 0A6h
0x180051202  mov     edx, 1
0x180051207  mov     ebx, 80070216h
0x18005120c  jmp     loc_180051139
0x180051211  mov     eax, 2
0x180051216  mov     [rbp+90h+Block], r14
0x18005121a  mul     rcx
0x18005121d  mov     r15, rax
0x180051220  test    rdx, rdx
0x180051223  jnz     short loc_18005123F
0x180051225  mov     eax, 0FFFFFFFFh
0x18005122a  cmp     r15, rax
0x18005122d  ja      short loc_180051237
0x18005122f  mov     rdi, r14
0x180051232  jmp     loc_1800512E3
0x180051237  mov     r9d, 0A9h
0x18005123d  jmp     short loc_180051202
0x18005123f  mov     r9d, 0A7h
0x180051245  jmp     short loc_180051202
0x180051247  lea     r8, [rsp+190h+var_138]; unsigned int *
0x18005124c  xor     edx, edx; unsigned __int8 *
0x18005124e  mov     rcx, rsi; unsigned __int16 *
0x180051251  call    ?HexStringToBinary@@YAJPEBGPEAEPEAK@Z; HexStringToBinary(ushort const *,uchar *,ulong *)
0x180051256  mov     ebx, eax
0x180051258  test    eax, eax
0x18005125a  jns     short loc_18005126C
0x18005125c  mov     r9d, 0AEh
0x180051262  mov     edx, 1
0x180051267  jmp     loc_180051139
0x18005126c  mov     ecx, [rsp+190h+var_138]; unsigned __int64
0x180051270  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180051275  mov     rdx, rax
0x180051278  lea     rcx, [rbp+90h+Block]
0x18005127c  call    ?reset@?$auto_xxx@PEAEP6AXPEAE@Z$1??$_delete_array@E@tlx@@YAX0@Z$0A@@tlx@@QEAAXPEAE@Z; tlx::auto_xxx<uchar *,void (*)(uchar *),&tlx::_delete_array<uchar>(uchar *),0>::reset(uchar *)
0x180051281  mov     rbx, [rbp+90h+Block]
0x180051285  test    rbx, rbx
0x180051288  jnz     short loc_18005129C
0x18005128a  mov     r9d, 0B1h
0x180051290  xor     edx, edx
0x180051292  mov     ebx, 8007000Eh
0x180051297  jmp     loc_180051139
0x18005129c  lea     r8, [rsp+190h+var_138]; unsigned int *
0x1800512a1  mov     rdx, rbx; unsigned __int8 *
0x1800512a4  mov     rcx, rsi; unsigned __int16 *
0x1800512a7  call    ?HexStringToBinary@@YAJPEBGPEAEPEAK@Z; HexStringToBinary(ushort const *,uchar *,ulong *)
0x1800512ac  mov     edi, eax
0x1800512ae  test    eax, eax
0x1800512b0  jns     short loc_1800512D8
0x1800512b2  mov     r9d, 0B3h
0x1800512b8  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800512bf  mov     edx, 1
0x1800512c4  mov     ecx, eax
0x1800512c6  call    Log_HREvent
0x1800512cb  mov     rcx, rbx; Block
0x1800512ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800512d3  jmp     loc_1800511D4
0x1800512d8  mov     r15d, [rsp+190h+var_138]
0x1800512dd  mov     rsi, rbx
0x1800512e0  mov     rdi, rbx
0x1800512e3  lea     rdx, [rsp+190h+var_150]
0x1800512e8  mov     [rsp+190h+var_150], r14
0x1800512ed  xor     ecx, ecx
0x1800512ef  call    cs:__imp_CreateStoreManager
0x1800512f5  mov     r14d, eax
0x1800512f8  test    eax, eax
0x1800512fa  jns     short loc_180051334
0x1800512fc  mov     r9d, 0B8h
0x180051302  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051309  mov     edx, 1
0x18005130e  mov     ecx, eax
0x180051310  call    Log_HREvent
0x180051315  lea     rcx, [rsp+190h+var_150]
0x18005131a  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18005131f  test    rdi, rdi
0x180051322  jz      short loc_18005132C
0x180051324  mov     rcx, rbx; Block
0x180051327  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005132c  mov     eax, r14d
0x18005132f  jmp     loc_180051754
0x180051334  lea     rcx, [rsp+190h+var_148]
0x180051339  mov     [rsp+190h+var_148], 0
0x180051342  call    cs:__imp_POutlookAppManager_CreateInstance
0x180051348  mov     r14d, eax
0x18005134b  test    eax, eax
0x18005134d  jns     short loc_180051374
0x18005134f  mov     r9d, 0BBh
0x180051355  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005135c  mov     edx, 1
0x180051361  mov     ecx, eax
0x180051363  call    Log_HREvent
0x180051368  lea     rcx, [rsp+190h+var_148]
0x18005136d  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180051372  jmp     short loc_180051315
0x180051374  mov     rcx, [rsp+190h+var_148]
0x180051379  lea     rdx, [rsp+190h+var_140]
0x18005137e  mov     [rsp+190h+var_140], 0
0x180051387  mov     rax, [rcx]
0x18005138a  mov     rax, [rax+20h]
0x18005138e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051393  mov     r14d, eax
0x180051396  test    eax, eax
0x180051398  jns     short loc_1800513BF
0x18005139a  mov     r9d, 0BEh
0x1800513a0  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800513a7  mov     edx, 1
0x1800513ac  mov     ecx, eax
0x1800513ae  call    Log_HREvent
0x1800513b3  lea     rcx, [rsp+190h+var_140]
0x1800513b8  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800513bd  jmp     short loc_180051368
0x1800513bf  mov     rdx, r12
0x1800513c2  mov     [rsp+190h+var_130], 0
0x1800513cb  lea     rcx, [rbp+90h+Block]
0x1800513cf  call    ?UdmIdToPoomId@@YA?AUOLITEMID@@AEBUUdmObjectId@@@Z; UdmIdToPoomId(UdmObjectId const &)
0x1800513d4  mov     rcx, [rsp+190h+var_140]
0x1800513d9  lea     r8, [rsp+190h+var_130]
0x1800513de  lea     rdx, [rbp+90h+var_A0]
0x1800513e2  movsd   xmm0, qword ptr [rax]
0x1800513e6  movsd   [rbp+90h+var_A0], xmm0
0x1800513eb  mov     eax, [rax+8]
0x1800513ee  mov     [rbp+90h+var_98], eax
0x1800513f1  mov     rax, [rcx]
0x1800513f4  mov     rax, [rax+70h]
0x1800513f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513fd  mov     r14d, eax
0x180051400  test    eax, eax
0x180051402  jns     short loc_180051429
0x180051404  mov     r9d, 0C2h
0x18005140a  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051411  mov     edx, 1
0x180051416  mov     ecx, eax
0x180051418  call    Log_HREvent
0x18005141d  lea     rcx, [rsp+190h+var_130]
0x180051422  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180051427  jmp     short loc_1800513B3
0x180051429  mov     rcx, [rsp+190h+var_130]
0x18005142e  lea     r8, [rsp+190h+var_128]
0x180051433  mov     [rsp+190h+var_128], 0
0x18005143c  mov     edx, 0Ah
0x180051441  mov     rax, [rcx]
0x180051444  mov     rax, [rax+60h]
0x180051448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005144d  mov     r14d, eax
0x180051450  test    eax, eax
0x180051452  jns     short loc_18005147A
0x180051454  mov     r9d, 0C5h
0x18005145a  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051461  mov     edx, 1
0x180051466  mov     ecx, r14d
0x180051469  call    Log_HREvent
0x18005146e  lea     rcx, [rsp+190h+var_128]
0x180051473  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180051478  jmp     short loc_18005141D
0x18005147a  mov     rcx, [rsp+190h+var_128]
0x18005147f  lea     rdx, [rbp+90h+var_B0]
0x180051483  xor     eax, eax
0x180051485  mov     [rbp+90h+var_B0], rax
0x180051489  mov     [rbp+90h+var_A8], eax
0x18005148c  mov     rax, [rcx]
0x18005148f  mov     rax, [rax+18h]
0x180051493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051498  mov     r14d, eax
0x18005149b  test    eax, eax
0x18005149d  jns     short loc_1800514A7
0x18005149f  mov     r9d, 0C8h
0x1800514a5  jmp     short loc_18005145A
0x1800514a7  mov     eax, [rbp+90h+var_A8]
0x1800514aa  lea     rcx, [rbp+90h+var_88]; void *
0x1800514ae  xorps   xmm0, xmm0
0x1800514b1  mov     [rbp+90h+var_F0], 0E090013h
0x1800514b8  movups  [rbp+90h+var_DC], xmm0
0x1800514bc  xor     edx, edx; Val
0x1800514be  mov     dword ptr [rbp+90h+var_DC+4], 10A0041h
0x1800514c5  movups  [rbp+90h+var_DC+0Ch], xmm0
0x1800514c9  mov     dword ptr [rbp+90h+var_DC+0Ch], r15d
0x1800514cd  movups  [rbp+90h+var_EC], xmm0
0x1800514d1  lea     r8d, [rdx+40h]; Size
0x1800514d5  mov     dword ptr [rbp+90h+var_EC+4], eax
0x1800514d8  mov     [rbp+90h+var_C8], rsi
0x1800514dc  call    memset_0
0x1800514e1  xor     esi, esi
0x1800514e3  mov     [rbp+90h+var_88], 2
0x1800514ea  lea     rax, [rbp+90h+var_78]
0x1800514ee  mov     [rbp+90h+var_90], esi
0x1800514f1  mov     [rbp+90h+var_80], rax
0x1800514f5  mov     ecx, esi
0x1800514f7  lea     r10d, [rsi+4]
0x1800514fb  lea     r9d, [rcx+1]
0x1800514ff  mov     eax, ecx
0x180051501  lea     r8, [r9+r9*2]
0x180051505  lea     rdx, [rbp+90h+var_F0]
0x180051509  mov     [rbp+r8*8+90h+var_90], r10d
0x18005150e  mov     [rbp+r8*8+90h+var_88], r10d
0x180051513  lea     rcx, [rax+rax*2]
0x180051517  lea     rdx, [rdx+rcx*8]
0x18005151b  mov     ecx, r9d
0x18005151e  mov     eax, [rdx]
0x180051520  mov     [rbp+r8*8+90h+var_84], eax
0x180051525  mov     [rbp+r8*8+90h+var_80], rdx
0x18005152a  cmp     r9d, [rbp+90h+var_88]
0x18005152e  jb      short loc_1800514FB
0x180051530  mov     rcx, [rsp+190h+var_150]
0x180051535  lea     rdx, [rsp+190h+var_120]
0x18005153a  mov     [rsp+190h+var_160], rdx
0x18005153f  xor     r9d, r9d
0x180051542  lea     rdx, [rbp+90h+var_90]
0x180051546  mov     [rsp+190h+var_120], rsi
0x18005154b  mov     [rsp+190h+var_168], rdx
0x180051550  mov     r8d, 2000000h
0x180051556  mov     rax, [rcx]
0x180051559  lea     edx, [r9+1]
0x18005155d  mov     [rsp+190h+var_170], rsi
0x180051562  mov     rax, [rax+88h]
0x180051569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005156e  mov     edi, eax
0x180051570  test    eax, eax
0x180051572  jns     loc_180051623
0x180051578  mov     r9d, 0E5h
0x18005157e  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051585  mov     edx, 1
0x18005158a  mov     ecx, eax
0x18005158c  call    Log_HREvent
0x180051591  mov     rcx, [rsp+190h+var_120]
0x180051596  test    rcx, rcx
0x180051599  jz      short loc_1800515A7
  ... truncated ...
```
