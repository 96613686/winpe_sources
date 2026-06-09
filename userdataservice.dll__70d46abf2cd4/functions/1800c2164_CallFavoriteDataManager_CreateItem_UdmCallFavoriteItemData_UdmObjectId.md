# CallFavoriteDataManager::CreateItem(UdmCallFavoriteItemData,UdmObjectId *)

- ea: `0x1800c2164`
- end: `0x1800c247b`
- name: `?CreateItem@CallFavoriteDataManager@@QEAAJUUdmCallFavoriteItemData@@PEAUUdmObjectId@@@Z`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800c1fd4`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18001e940`
- `0x18006a880`
- `0x180087990`
- `0x1800977c4`
- `0x1800c1900`
- `0x1800c2164`
- `0x1800c2a08`
- `0x1800c2a9c`
- `0x1800c5a90`
- `0x1800c5eb4`
- `0x1800c5f4c`
- `0x18012c76a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c22cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c22cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c224e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c2256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c244f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c2458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c224e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c2256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c244f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c2458`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c221e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c221e`

## string_xrefs

- `0x1800c2230`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c2377`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c23d1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c242f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`

## pseudocode

```c
__int64 __fastcall CallFavoriteDataManager::CreateItem(__int64 a1, __int128 *a2, _DWORD *a3)
{
  int v6; // r13d
  void *v7; // r15
  void *v8; // r12
  void *v9; // r8
  HRESULT v10; // eax
  unsigned int v11; // edi
  __int64 v13; // xmm0_8
  int ContactProps; // edi
  struct UdmCallFavoriteItemDataWithId *v15; // rax
  struct UdmCallFavoriteItemDataWithId *v16; // rdi
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm1
  NewIdManager *v21; // rax
  int NextId; // eax
  unsigned int v23; // ebx
  __int64 v24; // r9
  struct UdmCallFavoriteItemDataWithId *v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // eax
  struct UdmCallFavoriteItemDataWithId *v30; // rcx
  __int64 v31; // [rsp+40h] [rbp-79h] BYREF
  int v32; // [rsp+48h] [rbp-71h]
  int v33; // [rsp+50h] [rbp-69h] BYREF
  void *v34; // [rsp+58h] [rbp-61h]
  int v35; // [rsp+60h] [rbp-59h] BYREF
  void *v36; // [rsp+68h] [rbp-51h]
  unsigned int v37; // [rsp+70h] [rbp-49h] BYREF
  __int128 v38; // [rsp+78h] [rbp-41h]
  __int128 v39; // [rsp+88h] [rbp-31h]
  __int128 v40; // [rsp+98h] [rbp-21h]
  __int128 v41; // [rsp+A8h] [rbp-11h]
  __int128 v42; // [rsp+B8h] [rbp-1h]
  __int128 v43; // [rsp+C8h] [rbp+Fh]
  __int64 v44; // [rsp+D8h] [rbp+1Fh]
  LPVOID ppv; // [rsp+128h] [rbp+6Fh] BYREF
  struct UdmCallFavoriteItemDataWithId *Block; // [rsp+138h] [rbp+7Fh] BYREF

  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v6 = 0;
  LODWORD(ppv) = 0;
  v7 = 0;
  v31 = g_ZeroOlItemId;
  v8 = 0;
  v32 = 0;
  if ( !(unsigned __int8)operator==(a2 + 1, &v31)
    && *((_DWORD *)a2 + 8) == (_DWORD)v9
    && *((void **)a2 + 5) == v9
    && *((_DWORD *)a2 + 12) == (_DWORD)v9
    && *((void **)a2 + 7) == v9 )
  {
    ppv = v9;
    v10 = CoCreateInstance(&CLSID_Application, 0, 0x17u, &GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d, &ppv);
    v11 = v10;
    if ( v10 < 0 )
    {
      Log_HREvent(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
        530);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
      LocalFree(0);
      LocalFree(0);
      return v11;
    }
    v13 = *((_QWORD *)a2 + 2);
    v32 = *((_DWORD *)a2 + 6);
    v31 = v13;
    ContactProps = GetContactProps((_DWORD)ppv, (unsigned int)&v31, 9830431, 0, 0, (__int64)&v33, (__int64)&v35, 0);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
    v7 = v34;
    v6 = v33;
    v8 = v36;
    LODWORD(ppv) = ContactProps >= 0;
  }
  v31 = a1 + 8;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  v15 = (struct UdmCallFavoriteItemDataWithId *)operator new(0x70u);
  v16 = v15;
  if ( !v15 )
  {
    v23 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
      551);
    goto LABEL_28;
  }
  memset_0(v15, 0, 0x70u);
  Block = v16;
  memset_0(&v37, 0, 0x70u);
  v17 = a2[1];
  v38 = *a2;
  v40 = a2[2];
  v18 = a2[4];
  v39 = v17;
  v19 = a2[3];
  v42 = v18;
  *(_QWORD *)&v18 = *((_QWORD *)a2 + 12);
  v41 = v19;
  v20 = a2[5];
  v44 = v18;
  v43 = v20;
  if ( (_DWORD)ppv )
  {
    LODWORD(v41) = v35;
    LODWORD(v40) = v6;
    *((_QWORD *)&v40 + 1) = v7;
    *((_QWORD *)&v41 + 1) = v8;
  }
  v21 = (NewIdManager *)tlx::_LazyImpl<NewIdManager,tlx::lazy_construct<NewIdManager>,tlx::static_lazy<NewIdManager,0,tlx::lazy_construct<NewIdManager>>>::get();
  NextId = NewIdManager::GetNextId(v21, &v37);
  v23 = NextId;
  if ( NextId < 0 )
  {
    v24 = 565;
LABEL_14:
    Log_HREvent(
      (unsigned int)NextId,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
      v24);
    v25 = v16;
LABEL_15:
    FreeUdmCallFavoriteItemDataWithId(v25);
    goto LABEL_28;
  }
  NextId = CloneCallFavoriteItemData((const struct UdmCallFavoriteItemDataWithId *)&v37, v16);
  v23 = NextId;
  if ( NextId < 0 )
  {
    v24 = 567;
    goto LABEL_14;
  }
  if ( (unsigned __int8)utl::list<tlx::auto_xxx<UdmCallFavoriteItemDataWithId *,void (*)(UdmCallFavoriteItemDataWithId *),&void FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *),0>,utl::allocator<tlx::auto_xxx<UdmCallFavoriteItemDataWithId *,void (*)(UdmCallFavoriteItemDataWithId *),&void FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *),0>>>::push_back(
                          a1 + 48,
                          &Block) )
  {
    v29 = CallFavoriteDataManager::_SaveDataToFile((LPCWSTR *)a1);
    v23 = v29;
    if ( v29 >= 0 )
    {
      v30 = Block;
      a3[2] = v37;
      a3[1] = 3;
      *a3 = 0;
      if ( v30 )
        FreeUdmCallFavoriteItemDataWithId(v30);
      v23 = 0;
      goto LABEL_28;
    }
    v26 = 571;
    v28 = 1;
    v27 = (unsigned int)v29;
  }
  else
  {
    v23 = -2147024882;
    v26 = 569;
    v27 = 2147942414LL;
    v28 = 0;
  }
  Log_HREvent(
    v27,
    v28,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
    v26);
  v25 = Block;
  if ( Block )
    goto LABEL_15;
LABEL_28:
  auto_SRWLockBase<_RTL_SRWLOCK,&void AcquireSRWLockExclusive(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>::~auto_SRWLockBase<_RTL_SRWLOCK,&void AcquireSRWLockExclusive(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>(&v31);
  LocalFree(v8);
  LocalFree(v7);
  return v23;
}

```

## disassembly

```asm
0x1800c2164  mov     [rsp-8+arg_0], rbx
0x1800c2169  push    rbp
0x1800c216a  push    rsi
0x1800c216b  push    rdi
0x1800c216c  push    r12
0x1800c216e  push    r13
0x1800c2170  push    r14
0x1800c2172  push    r15
0x1800c2174  lea     rbp, [rsp-27h]
0x1800c2179  sub     rsp, 0E0h
0x1800c2180  mov     eax, cs:dword_18013A438
0x1800c2186  mov     rsi, r8
0x1800c2189  movsd   xmm0, cs:?g_ZeroOlItemId@@3UOLITEMID@@B; OLITEMID const g_ZeroOlItemId
0x1800c2191  xor     r8d, r8d
0x1800c2194  mov     r14, rcx
0x1800c2197  mov     [rbp+57h+var_C0], r8d
0x1800c219b  lea     rcx, [rdx+10h]
0x1800c219f  mov     [rbp+57h+var_B8], r8
0x1800c21a3  mov     rbx, rdx
0x1800c21a6  mov     [rbp+57h+var_B0], r8d
0x1800c21aa  lea     rdx, [rbp+57h+var_D0]
0x1800c21ae  mov     [rbp+57h+var_A8], r8
0x1800c21b2  mov     r13d, r8d
0x1800c21b5  mov     dword ptr [rbp+57h+arg_8], r8d
0x1800c21b9  mov     r15d, r8d
0x1800c21bc  movsd   [rbp+57h+var_D0], xmm0
0x1800c21c1  mov     r12d, r8d
0x1800c21c4  mov     [rbp+57h+var_C8], eax
0x1800c21c7  call    ??8@YA_NAEBUOLITEMID@@0@Z; operator==(OLITEMID const &,OLITEMID const &)
0x1800c21cc  test    al, al
0x1800c21ce  jnz     loc_1800C22C4
0x1800c21d4  cmp     [rbx+20h], r8d
0x1800c21d8  jnz     loc_1800C22C4
0x1800c21de  cmp     [rbx+28h], r8
0x1800c21e2  jnz     loc_1800C22C4
0x1800c21e8  cmp     [rbx+30h], r8d
0x1800c21ec  jnz     loc_1800C22C4
0x1800c21f2  cmp     [rbx+38h], r8
0x1800c21f6  jnz     loc_1800C22C4
0x1800c21fc  mov     [rbp+57h+arg_8], r8
0x1800c2200  lea     rax, [rbp+57h+arg_8]
0x1800c2204  lea     r8d, [r12+17h]; dwClsContext
0x1800c2209  mov     [rsp+110h+ppv], rax; ppv
0x1800c220e  lea     r9, _GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d; riid
0x1800c2215  xor     edx, edx; pUnkOuter
0x1800c2217  lea     rcx, CLSID_Application; rclsid
0x1800c221e  call    cs:__imp_CoCreateInstance
0x1800c2224  mov     edi, eax
0x1800c2226  test    eax, eax
0x1800c2228  jns     short loc_1800C2263
0x1800c222a  mov     r9d, 212h
0x1800c2230  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c2237  lea     edx, [r12+1]
0x1800c223c  mov     ecx, eax
0x1800c223e  call    Log_HREvent
0x1800c2243  lea     rcx, [rbp+57h+arg_8]
0x1800c2247  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800c224c  xor     ecx, ecx; hMem
0x1800c224e  call    cs:__imp_LocalFree
0x1800c2254  xor     ecx, ecx; hMem
0x1800c2256  call    cs:__imp_LocalFree
0x1800c225c  mov     eax, edi
0x1800c225e  jmp     loc_1800C2460
0x1800c2263  mov     eax, [rbx+18h]
0x1800c2266  lea     rdx, [rbp+57h+var_D0]
0x1800c226a  movsd   xmm0, qword ptr [rbx+10h]
0x1800c226f  xor     r9d, r9d
0x1800c2272  mov     rcx, [rbp+57h+arg_8]
0x1800c2276  mov     r8d, 96001Fh
0x1800c227c  mov     [rbp+57h+var_C8], eax
0x1800c227f  lea     rax, [rbp+57h+var_B0]
0x1800c2283  mov     [rsp+110h+var_D8], r12
0x1800c2288  mov     [rsp+110h+var_E0], rax
0x1800c228d  lea     rax, [rbp+57h+var_C0]
0x1800c2291  mov     [rsp+110h+var_E8], rax
0x1800c2296  mov     [rsp+110h+ppv], r12
0x1800c229b  movsd   [rbp+57h+var_D0], xmm0
0x1800c22a0  call    ?GetContactProps@@YAJPEAUIPOutlookApp3@@UOLITEMID@@KPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAVCAutoBlob@@43@Z; GetContactProps(IPOutlookApp3 *,OLITEMID,ulong,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,CAutoBlob &,CAutoBlob &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800c22a5  lea     rcx, [rbp+57h+arg_8]
0x1800c22a9  mov     edi, eax
0x1800c22ab  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800c22b0  mov     r15, [rbp+57h+var_B8]
0x1800c22b4  not     edi
0x1800c22b6  mov     r13d, [rbp+57h+var_C0]
0x1800c22ba  mov     r12, [rbp+57h+var_A8]
0x1800c22be  shr     edi, 1Fh
0x1800c22c1  mov     dword ptr [rbp+57h+arg_8], edi
0x1800c22c4  lea     rcx, [r14+8]; SRWLock
0x1800c22c8  mov     [rbp+57h+var_D0], rcx
0x1800c22cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800c22d2  mov     ecx, 70h ; 'p'; Size
0x1800c22d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c22dc  xor     edx, edx; Val
0x1800c22de  mov     rdi, rax
0x1800c22e1  test    rax, rax
0x1800c22e4  jz      loc_1800C242A
0x1800c22ea  lea     r8d, [rdx+70h]; Size
0x1800c22ee  mov     rcx, rax; void *
0x1800c22f1  call    memset_0
0x1800c22f6  xor     edx, edx; Val
0x1800c22f8  mov     [rbp+57h+Block], rdi
0x1800c22fc  lea     rcx, [rbp+57h+var_A0]; void *
0x1800c2300  lea     r8d, [rdx+70h]; Size
0x1800c2304  call    memset_0
0x1800c2309  cmp     dword ptr [rbp+57h+arg_8], 0
0x1800c230d  movaps  xmm0, xmmword ptr [rbx]
0x1800c2310  movaps  xmm1, xmmword ptr [rbx+10h]
0x1800c2314  movups  [rbp+57h+var_98], xmm0
0x1800c2318  movaps  xmm0, xmmword ptr [rbx+20h]
0x1800c231c  movups  [rbp+57h+var_78], xmm0
0x1800c2320  movaps  xmm0, xmmword ptr [rbx+40h]
0x1800c2324  movups  [rbp+57h+var_88], xmm1
0x1800c2328  movaps  xmm1, xmmword ptr [rbx+30h]
0x1800c232c  movups  [rbp+57h+var_58], xmm0
0x1800c2330  movsd   xmm0, qword ptr [rbx+60h]
0x1800c2335  movups  [rbp+57h+var_68], xmm1
0x1800c2339  movaps  xmm1, xmmword ptr [rbx+50h]
0x1800c233d  movsd   [rbp+57h+var_38], xmm0
0x1800c2342  movups  [rbp+57h+var_48], xmm1
0x1800c2346  jz      short loc_1800C235A
0x1800c2348  mov     eax, [rbp+57h+var_B0]
0x1800c234b  mov     dword ptr [rbp+57h+var_68], eax
0x1800c234e  mov     dword ptr [rbp+57h+var_78], r13d
0x1800c2352  mov     qword ptr [rbp+57h+var_78+8], r15
0x1800c2356  mov     qword ptr [rbp+57h+var_68+8], r12
0x1800c235a  call    ?get@?$_LazyImpl@VNewIdManager@@V?$lazy_construct@VNewIdManager@@@tlx@@V?$static_lazy@VNewIdManager@@$0A@V?$lazy_construct@VNewIdManager@@@tlx@@@3@@tlx@@QEAAAEAVNewIdManager@@XZ; tlx::_LazyImpl<NewIdManager,tlx::lazy_construct<NewIdManager>,tlx::static_lazy<NewIdManager,0,tlx::lazy_construct<NewIdManager>>>::get(void)
0x1800c235f  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x1800c2363  mov     rcx, rax; this
0x1800c2366  call    ?GetNextId@NewIdManager@@QEAAJPEAK@Z; NewIdManager::GetNextId(ulong *)
0x1800c236b  mov     ebx, eax
0x1800c236d  test    eax, eax
0x1800c236f  jns     short loc_1800C2397
0x1800c2371  mov     r9d, 235h
0x1800c2377  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c237e  mov     edx, 1
0x1800c2383  mov     ecx, eax
0x1800c2385  call    Log_HREvent
0x1800c238a  mov     rcx, rdi; Block
0x1800c238d  call    ?FreeUdmCallFavoriteItemDataWithId@@YAXPEAUUdmCallFavoriteItemDataWithId@@@Z; FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *)
0x1800c2392  jmp     loc_1800C2443
0x1800c2397  mov     rdx, rdi; struct UdmCallFavoriteItemDataWithId *
0x1800c239a  lea     rcx, [rbp+57h+var_A0]; struct UdmCallFavoriteItemDataWithId *
0x1800c239e  call    ?CloneCallFavoriteItemData@@YAJAEBUUdmCallFavoriteItemDataWithId@@PEAU1@@Z; CloneCallFavoriteItemData(UdmCallFavoriteItemDataWithId const &,UdmCallFavoriteItemDataWithId *)
0x1800c23a3  mov     ebx, eax
0x1800c23a5  test    eax, eax
0x1800c23a7  jns     short loc_1800C23B1
0x1800c23a9  mov     r9d, 237h
0x1800c23af  jmp     short loc_1800C2377
0x1800c23b1  lea     rcx, [r14+30h]
0x1800c23b5  lea     rdx, [rbp+57h+Block]
0x1800c23b9  call    ?push_back@?$list@V?$auto_xxx@PEAUUdmCallFavoriteItemDataWithId@@P6AXPEAU1@@Z$1?FreeUdmCallFavoriteItemDataWithId@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAUUdmCallFavoriteItemDataWithId@@P6AXPEAU1@@Z$1?FreeUdmCallFavoriteItemDataWithId@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA_N$$QEAV?$auto_xxx@PEAUUdmCallFavoriteItemDataWithId@@P6AXPEAU1@@Z$1?FreeUdmCallFavoriteItemDataWithId@@YAX0@Z$0A@@tlx@@@Z; utl::list<tlx::auto_xxx<UdmCallFavoriteItemDataWithId *,void (*)(UdmCallFavoriteItemDataWithId *),&FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *),0>,utl::allocator<tlx::auto_xxx<UdmCallFavoriteItemDataWithId *,void (*)(UdmCallFavoriteItemDataWithId *),&FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *),0>>>::push_back(tlx::auto_xxx<UdmCallFavoriteItemDataWithId *,void (*)(UdmCallFavoriteItemDataWithId *),&FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *),0> &&)
0x1800c23be  test    al, al
0x1800c23c0  jnz     short loc_1800C23E8
0x1800c23c2  mov     ebx, 8007000Eh
0x1800c23c7  mov     r9d, 239h
0x1800c23cd  mov     ecx, ebx
0x1800c23cf  xor     edx, edx
0x1800c23d1  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c23d8  call    Log_HREvent
0x1800c23dd  mov     rcx, [rbp+57h+Block]
0x1800c23e1  test    rcx, rcx
0x1800c23e4  jz      short loc_1800C2443
0x1800c23e6  jmp     short loc_1800C238D
0x1800c23e8  mov     rcx, r14; this
0x1800c23eb  call    ?_SaveDataToFile@CallFavoriteDataManager@@AEAAJXZ; CallFavoriteDataManager::_SaveDataToFile(void)
0x1800c23f0  mov     ebx, eax
0x1800c23f2  test    eax, eax
0x1800c23f4  jns     short loc_1800C2405
0x1800c23f6  mov     r9d, 23Bh
0x1800c23fc  mov     edx, 1
0x1800c2401  mov     ecx, eax
0x1800c2403  jmp     short loc_1800C23D1
0x1800c2405  mov     rcx, [rbp+57h+Block]; Block
0x1800c2409  mov     eax, [rbp+57h+var_A0]
0x1800c240c  mov     [rsi+8], eax
0x1800c240f  mov     dword ptr [rsi+4], 3
0x1800c2416  mov     dword ptr [rsi], 0
0x1800c241c  test    rcx, rcx
0x1800c241f  jz      short loc_1800C2426
0x1800c2421  call    ?FreeUdmCallFavoriteItemDataWithId@@YAXPEAUUdmCallFavoriteItemDataWithId@@@Z; FreeUdmCallFavoriteItemDataWithId(UdmCallFavoriteItemDataWithId *)
0x1800c2426  xor     ebx, ebx
0x1800c2428  jmp     short loc_1800C2443
0x1800c242a  mov     ebx, 8007000Eh
0x1800c242f  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c2436  mov     ecx, ebx
0x1800c2438  mov     r9d, 227h
0x1800c243e  call    Log_HREvent
0x1800c2443  lea     rcx, [rbp+57h+var_D0]
0x1800c2447  call    ??1?$auto_SRWLockBase@U_RTL_SRWLOCK@@$1?AcquireSRWLockExclusive@@YAXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@Z@@QEAA@XZ; auto_SRWLockBase<_RTL_SRWLOCK,&AcquireSRWLockExclusive(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>::~auto_SRWLockBase<_RTL_SRWLOCK,&AcquireSRWLockExclusive(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>(void)
0x1800c244c  mov     rcx, r12; hMem
0x1800c244f  call    cs:__imp_LocalFree
0x1800c2455  mov     rcx, r15; hMem
0x1800c2458  call    cs:__imp_LocalFree
0x1800c245e  mov     eax, ebx
0x1800c2460  mov     rbx, [rsp+110h+arg_0]
0x1800c2468  add     rsp, 0E0h
0x1800c246f  pop     r15
0x1800c2471  pop     r14
0x1800c2473  pop     r13
0x1800c2475  pop     r12
0x1800c2477  pop     rdi
0x1800c2478  pop     rsi
0x1800c2479  pop     rbp
0x1800c247a  retn
```
