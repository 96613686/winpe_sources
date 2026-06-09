# InstantiateGlobalObjects_Sqloledb(void)

- ea: `0x3838963c0`
- end: `0x38389664e`
- name: `?InstantiateGlobalObjects_Sqloledb@@YAJXZ`
- size: `654`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x383896760`

## callees

- `0x3838435e0`
- `0x383893ff0`
- `0x383895d70`
- `0x383895dbc`
- `0x383895ec0`
- `0x3838963c0`
- `0x383896660`
- `0x38389a0c0`
- `0x38391aed0`
- `0x38391afe0`
- `0x383a9cc40`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x383896580`
- `KERNEL32!GetComputerNameW` at `0x383896580`
- `KERNEL32!InitializeSListHead` at `0x383896477`
- `KERNEL32!InitializeSListHead` at `0x383896477`
- `ole32!CoGetMalloc` at `0x383896418`
- `ole32!CoGetMalloc` at `0x383896418`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall InstantiateGlobalObjects_Sqloledb(const unsigned __int16 *a1, HINSTANCE a2, HINSTANCE *a3)
{
  unsigned int v3; // ebx
  HRESULT Malloc; // eax
  CReservedBlockManager *v6; // rax
  union _SLIST_HEADER *v7; // rax
  unsigned int v8; // edx
  void *v9; // r8
  unsigned int v10; // edx
  void *v11; // r8
  __int64 v12; // rdi
  struct IClassFactory *v13; // r14
  __int64 v14; // rax
  struct IClassFactory *v15; // rsi
  int inited; // eax
  char *v17; // rcx
  __int64 v18; // rdx
  DWORD nSize; // [rsp+70h] [rbp+8h] BYREF
  __int64 v20; // [rsp+78h] [rbp+10h]

  v3 = 0;
  if ( (g_uInitializationStatus & 0x10) != 0 )
    return v3;
  if ( !(unsigned int)InitializeSharedModules(a1, a2, a3) )
  {
    if ( (bidGblFlags & 2) == 0 )
      return (unsigned int)-2147467259;
    v17 = off_383B43250[0];
    if ( !off_383B49128[0] )
      return (unsigned int)-2147467259;
    v18 = 268329;
    goto LABEL_56;
  }
  Malloc = CoGetMalloc(1u, &g_pIMalloc);
  if ( !g_pIMalloc || Malloc < 0 || !(unsigned int)InitializeVLHeapPool() )
  {
LABEL_53:
    if ( (bidGblFlags & 2) == 0 )
      return (unsigned int)-2147467259;
    v17 = off_383B43250[0];
    if ( !off_383B49128[0] )
      return (unsigned int)-2147467259;
    v18 = 277545;
LABEL_56:
    bidTraceW(v17, v18, off_383B49128[0], 2147500037LL);
    return (unsigned int)-2147467259;
  }
  v6 = (CReservedBlockManager *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 32);
  if ( !v6 )
  {
    CReservedBlockManager::s_pInstance = 0;
    goto LABEL_52;
  }
  v7 = (union _SLIST_HEADER *)CReservedBlockManager::CReservedBlockManager(v6);
  CReservedBlockManager::s_pInstance = (struct CReservedBlockManager *)v7;
  if ( !v7 )
  {
LABEL_52:
    UninitializeVLHeapPool();
    goto LABEL_53;
  }
  InitializeSListHead(v7 + 1);
  if ( !(unsigned int)ErrCollInit((HINSTANCE)1, v8, v9) || !(unsigned int)DllMain_Sqloledb((HINSTANCE)1, v10, v11) )
    goto LABEL_53;
  v12 = 0;
  v13 = (struct IClassFactory *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 40);
  v20 = (__int64)v13;
  if ( v13 )
  {
    v13->lpVtbl = (struct IClassFactoryVtbl *)&CErrClassFactory::`vftable';
    LODWORD(v13[2].lpVtbl) = 0;
    v13[3].lpVtbl = (struct IClassFactoryVtbl *)&g_cLockInternal;
    v13[4].lpVtbl = (struct IClassFactoryVtbl *)&g_cObjInternal;
    _InterlockedIncrement(&g_cObjInternal);
  }
  else
  {
    v13 = 0;
  }
  if ( !v13 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43250[0], 294953, off_383B49128[0], 2147942414LL);
    return (unsigned int)-2147024882;
  }
  ((void (__fastcall *)(struct IClassFactory *))v13->lpVtbl->AddRef)(v13);
  v14 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 32);
  v15 = (struct IClassFactory *)v14;
  v20 = v14;
  if ( v14 )
  {
    *(_QWORD *)v14 = &CClassFactory::`vftable';
    *(_DWORD *)(v14 + 8) = 0;
    *(_QWORD *)(v14 + 16) = &g_cLockInternal;
    *(_QWORD *)(v14 + 24) = &g_cObjInternal;
    _InterlockedIncrement(&g_cObjInternal);
    *(_QWORD *)v14 = &CErrorLookupClassFactory::`vftable';
  }
  else
  {
    v15 = 0;
  }
  if ( !v15 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43250[0], 303145, off_383B49128[0], 2147942414LL);
    goto LABEL_38;
  }
  ((void (__fastcall *)(struct IClassFactory *))v15->lpVtbl->AddRef)(v15);
  if ( !g_fHaveWorkstatId )
  {
    nSize = 129;
    if ( !GetComputerNameW(&g_wszWorkstation, &nSize) )
      g_wszWorkstation = 0;
    g_fHaveWorkstatId = 1;
  }
  v12 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 208);
  v20 = v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = &CTdsParser::`vftable';
    *(_QWORD *)(v12 + 152) = 0;
    *(_DWORD *)(v12 + 160) = 0;
    *(_DWORD *)(v12 + 164) = 0;
    *(_DWORD *)(v12 + 168) = 0;
    *(_QWORD *)(v12 + 172) = 0;
    *(_QWORD *)(v12 + 180) = 0;
    *(_QWORD *)(v12 + 188) = 0;
    memset((void *)(v12 + 8), 0, 0x90u);
    *(_QWORD *)v12 = &CTdsSqloledb::`vftable';
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      bidTraceW(off_383B43250[0], 320553, off_383B49128[0], 2147942414LL);
      v3 = -2147024882;
      goto LABEL_45;
    }
LABEL_38:
    v3 = -2147024882;
    goto LABEL_45;
  }
  inited = CTdsSqloledb::initSqloledb((CTdsSqloledb *)v12);
  v3 = inited;
  if ( inited < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_47:
      ((void (__fastcall *)(struct IClassFactory *))v13->lpVtbl->Release)(v13);
      if ( v15 )
        ((void (__fastcall *)(struct IClassFactory *))v15->lpVtbl->Release)(v15);
      if ( v12 )
        (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
      return v3;
    }
    bidTraceHR(off_383B43250[0], 325641, (unsigned int)inited);
LABEL_45:
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43250[0], 339977, v3);
    goto LABEL_47;
  }
  g_pErrClassFact = v13;
  g_pErrLookupClassFact = v15;
  g_tdsp = (CTdsParser *)v12;
  g_uInitializationStatus |= 0x10u;
  return 0;
}

```

## disassembly

```asm
0x3838963c0  push    rbp
0x3838963c2  push    rsi
0x3838963c3  push    rdi
0x3838963c4  push    r14
0x3838963c6  push    r15
0x3838963c8  sub     rsp, 40h
0x3838963cc  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x3838963d5  mov     [rsp+68h+arg_10], rbx
0x3838963dd  xor     ebx, ebx
0x3838963df  mov     eax, cs:?g_uInitializationStatus@@3KC; ulong volatile g_uInitializationStatus
0x3838963e5  test    al, 10h
0x3838963e7  jz      short loc_3838963FF
0x3838963e9  mov     eax, ebx
0x3838963eb  mov     rbx, [rsp+68h+arg_10]
0x3838963f3  add     rsp, 40h
0x3838963f7  pop     r15
0x3838963f9  pop     r14
0x3838963fb  pop     rdi
0x3838963fc  pop     rsi
0x3838963fd  pop     rbp
0x3838963fe  retn
0x3838963ff  call    ?InitializeSharedModules@@YAHXZ; InitializeSharedModules(void)
0x383896404  test    eax, eax
0x383896406  jz      loc_3838D4D88
0x38389640c  lea     rdx, ?g_pIMalloc@@3PEAUIMalloc@@EA; ppMalloc
0x383896413  mov     ecx, 1; dwMemContext
0x383896418  call    cs:__imp_CoGetMalloc
0x38389641e  cmp     cs:?g_pIMalloc@@3PEAUIMalloc@@EA, rbx; IMalloc * g_pIMalloc
0x383896425  jz      loc_3838D4F23
0x38389642b  test    eax, eax
0x38389642d  js      loc_3838D4F23
0x383896433  call    ?InitializeVLHeapPool@@YAHXZ; InitializeVLHeapPool(void)
0x383896438  test    eax, eax
0x38389643a  jz      loc_3838D4F23
0x383896440  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383896447  mov     rax, [rcx]
0x38389644a  mov     edx, 20h ; ' '
0x38389644f  call    qword ptr [rax+58h]
0x383896452  test    rax, rax
0x383896455  jz      loc_3838D4F17
0x38389645b  mov     rcx, rax; this
0x38389645e  call    ??0CReservedBlockManager@@IEAA@XZ; CReservedBlockManager::CReservedBlockManager(void)
0x383896463  mov     cs:?s_pInstance@CReservedBlockManager@@1PEAV1@EA, rax; CReservedBlockManager * CReservedBlockManager::s_pInstance
0x38389646a  test    rax, rax
0x38389646d  jz      loc_3838D4F1E
0x383896473  lea     rcx, [rax+10h]; ListHead
0x383896477  call    cs:__imp_InitializeSListHead
0x38389647d  mov     ecx, 1; HINSTANCE
0x383896482  call    ?ErrCollInit@@YAHPEAUHINSTANCE__@@KPEAX@Z; ErrCollInit(HINSTANCE__ *,ulong,void *)
0x383896487  test    eax, eax
0x383896489  jz      loc_3838D4F23
0x38389648f  mov     ecx, 1; HINSTANCE
0x383896494  call    ?DllMain_Sqloledb@@YAHPEAUHINSTANCE__@@KPEAX@Z; DllMain_Sqloledb(HINSTANCE__ *,ulong,void *)
0x383896499  test    eax, eax
0x38389649b  jz      loc_3838D4F23
0x3838964a1  mov     rdi, rbx
0x3838964a4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3838964ab  mov     rax, [rcx]
0x3838964ae  mov     edx, 28h ; '('
0x3838964b3  call    qword ptr [rax+58h]
0x3838964b6  mov     r14, rax
0x3838964b9  mov     [rsp+68h+arg_8], rax
0x3838964be  lea     rbp, ?g_cLockInternal@@3JA; long g_cLockInternal
0x3838964c5  lea     r15, ?g_cObjInternal@@3JA; long g_cObjInternal
0x3838964cc  test    rax, rax
0x3838964cf  jz      loc_3838D4DBE
0x3838964d5  lea     rax, ??_7CErrClassFactory@@6B@; const CErrClassFactory::`vftable'
0x3838964dc  mov     [r14], rax
0x3838964df  mov     [r14+10h], ebx
0x3838964e3  mov     [r14+18h], rbp
0x3838964e7  mov     [r14+20h], r15
0x3838964eb  lock inc cs:?g_cObjInternal@@3JA; long g_cObjInternal
0x3838964f2  jmp     short $+2
0x3838964f4  test    r14, r14
0x3838964f7  jz      loc_3838D4DC6
0x3838964fd  mov     rax, [r14]
0x383896500  mov     rcx, r14
0x383896503  call    qword ptr [rax+8]
0x383896506  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x38389650d  mov     rax, [rcx]
0x383896510  mov     edx, 20h ; ' '
0x383896515  call    qword ptr [rax+58h]
0x383896518  mov     rsi, rax
0x38389651b  mov     [rsp+68h+arg_8], rax
0x383896520  test    rax, rax
0x383896523  jz      loc_3838D4E0B
0x383896529  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x383896530  mov     [rsi], rax
0x383896533  mov     [rsi+8], ebx
0x383896536  mov     [rsi+10h], rbp
0x38389653a  mov     [rsi+18h], r15
0x38389653e  lock inc cs:?g_cObjInternal@@3JA; long g_cObjInternal
0x383896545  lea     rax, ??_7CErrorLookupClassFactory@@6B@; const CErrorLookupClassFactory::`vftable'
0x38389654c  mov     [rsi], rax
0x38389654f  jmp     short $+2
0x383896551  test    rsi, rsi
0x383896554  jz      loc_3838D4E13
0x38389655a  mov     rax, [rsi]
0x38389655d  mov     rcx, rsi
0x383896560  call    qword ptr [rax+8]
0x383896563  cmp     cs:?g_fHaveWorkstatId@@3HA, 0; int g_fHaveWorkstatId
0x38389656a  jnz     short loc_383896598
0x38389656c  mov     [rsp+68h+nSize], 81h
0x383896574  lea     rdx, [rsp+68h+nSize]; nSize
0x383896579  lea     rcx, ?g_wszWorkstation@@3PAGA; lpBuffer
0x383896580  call    cs:__imp_GetComputerNameW
0x383896586  test    eax, eax
0x383896588  jz      loc_3838D4E55
0x38389658e  mov     cs:?g_fHaveWorkstatId@@3HA, 1; int g_fHaveWorkstatId
0x383896598  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x38389659f  mov     rax, [rcx]
0x3838965a2  mov     edx, 0D0h
0x3838965a7  call    qword ptr [rax+58h]
0x3838965aa  mov     rdi, rax
0x3838965ad  mov     [rsp+68h+arg_8], rax
0x3838965b2  test    rax, rax
0x3838965b5  jz      loc_3838D4E61
0x3838965bb  lea     rax, ??_7CTdsParser@@6B@; const CTdsParser::`vftable'
0x3838965c2  mov     [rdi], rax
0x3838965c5  mov     [rdi+98h], rbx
0x3838965cc  mov     [rdi+0A0h], ebx
0x3838965d2  mov     [rdi+0A4h], ebx
0x3838965d8  mov     [rdi+0A8h], ebx
0x3838965de  mov     [rdi+0ACh], rbx
0x3838965e5  mov     [rdi+0B4h], rbx
0x3838965ec  mov     [rdi+0BCh], rbx
0x3838965f3  lea     rcx, [rdi+8]; void *
0x3838965f7  xor     edx, edx; Val
0x3838965f9  mov     r8d, 90h; Size
0x3838965ff  call    memset
0x383896604  lea     r11, ??_7CTdsSqloledb@@6B@; const CTdsSqloledb::`vftable'
0x38389660b  mov     [rdi], r11
0x38389660e  jmp     short $+2
0x383896610  test    rdi, rdi
0x383896613  jz      loc_3838D4E69
0x383896619  mov     rcx, rdi; this
0x38389661c  call    ?initSqloledb@CTdsSqloledb@@QEAAJXZ; CTdsSqloledb::initSqloledb(void)
0x383896621  mov     ebx, eax
0x383896623  test    eax, eax
0x383896625  js      loc_3838D4EAB
0x38389662b  mov     cs:?g_pErrClassFact@@3PEAUIClassFactory@@EA, r14; IClassFactory * g_pErrClassFact
0x383896632  mov     cs:?g_pErrLookupClassFact@@3PEAUIClassFactory@@EA, rsi; IClassFactory * g_pErrLookupClassFact
0x383896639  mov     cs:?g_tdsp@@3PEAVCTdsSqloledb@@EA, rdi; CTdsSqloledb * g_tdsp
0x383896640  or      cs:?g_uInitializationStatus@@3KC, 10h; ulong volatile g_uInitializationStatus
0x383896647  xor     eax, eax
0x383896649  jmp     loc_3838963EB
0x3838d4d88  test    byte ptr cs:_bidGblFlags, 2
0x3838d4d8f  jz      loc_3838D4F5E
0x3838d4d95  mov     rcx, cs:off_383B43250; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838d4d9c  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4da3  test    rax, rax
0x3838d4da6  jz      loc_3838D4F5E
0x3838d4dac  mov     [rsp+68h+var_48], 106h
0x3838d4db4  mov     edx, 41829h
0x3838d4db9  jmp     loc_3838D4F4C
0x3838d4dbe  mov     r14, rbx
0x3838d4dc1  jmp     loc_3838964F4
0x3838d4dc6  test    byte ptr cs:_bidGblFlags, 2
0x3838d4dcd  jz      short loc_3838D4E01
0x3838d4dcf  mov     rcx, cs:off_383B43250; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838d4dd6  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4ddd  test    rax, rax
0x3838d4de0  jz      short loc_3838D4E01
0x3838d4de2  mov     [rsp+68h+var_48], 120h
0x3838d4dea  mov     r9d, 8007000Eh
0x3838d4df0  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4df7  mov     edx, 48029h
0x3838d4dfc  call    _bidTraceW
0x3838d4e01  mov     ebx, 8007000Eh
0x3838d4e06  jmp     loc_3838963E9
0x3838d4e0b  mov     rsi, rbx
0x3838d4e0e  jmp     loc_383896551
0x3838d4e13  test    byte ptr cs:_bidGblFlags, 2
0x3838d4e1a  jz      short loc_3838D4E4E
0x3838d4e1c  mov     rcx, cs:off_383B43250; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838d4e23  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4e2a  test    rax, rax
0x3838d4e2d  jz      short loc_3838D4E4E
0x3838d4e2f  mov     [rsp+68h+var_48], 128h
0x3838d4e37  mov     r9d, 8007000Eh
0x3838d4e3d  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4e44  mov     edx, 4A029h
0x3838d4e49  call    _bidTraceW
0x3838d4e4e  mov     ebx, 8007000Eh
0x3838d4e53  jmp     short loc_3838D4EC8
0x3838d4e55  mov     cs:?g_wszWorkstation@@3PAGA, bx; ushort near * g_wszWorkstation
0x3838d4e5c  jmp     loc_38389658E
0x3838d4e61  mov     rdi, rbx
0x3838d4e64  jmp     loc_383896610
0x3838d4e69  test    byte ptr cs:_bidGblFlags, 2
0x3838d4e70  jz      short loc_3838D4E4E
0x3838d4e72  mov     rcx, cs:off_383B43250; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838d4e79  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4e80  test    rax, rax
0x3838d4e83  jz      short loc_3838D4E4E
0x3838d4e85  mov     [rsp+68h+var_48], 139h
0x3838d4e8d  mov     r9d, 8007000Eh
0x3838d4e93  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4e9a  mov     edx, 4E429h
0x3838d4e9f  call    _bidTraceW
0x3838d4ea4  mov     ebx, 8007000Eh
0x3838d4ea9  jmp     short loc_3838D4EC8
0x3838d4eab  test    byte ptr cs:_bidGblFlags, 2
0x3838d4eb2  jz      short loc_3838D4EE5
0x3838d4eb4  mov     r8d, eax
0x3838d4eb7  mov     edx, 4F809h
0x3838d4ebc  mov     rcx, cs:off_383B43250; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838d4ec3  call    _bidTraceHR
0x3838d4ec8  test    byte ptr cs:_bidGblFlags, 2
0x3838d4ecf  jz      short loc_3838D4EE5
0x3838d4ed1  mov     r8d, ebx
0x3838d4ed4  mov     edx, 53009h
0x3838d4ed9  mov     rcx, cs:off_383B43250; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838d4ee0  call    _bidTraceHR
0x3838d4ee5  mov     rax, [r14]
0x3838d4ee8  mov     rcx, r14
0x3838d4eeb  call    qword ptr [rax+10h]
0x3838d4eee  test    rsi, rsi
0x3838d4ef1  jz      short loc_3838D4EFC
0x3838d4ef3  mov     rax, [rsi]
0x3838d4ef6  mov     rcx, rsi
0x3838d4ef9  call    qword ptr [rax+10h]
0x3838d4efc  test    rdi, rdi
0x3838d4eff  jz      loc_3838963E9
0x3838d4f05  mov     rax, [rdi]
0x3838d4f08  mov     edx, 1
0x3838d4f0d  mov     rcx, rdi
0x3838d4f10  call    qword ptr [rax]
0x3838d4f12  jmp     loc_3838963E9
0x3838d4f17  mov     cs:?s_pInstance@CReservedBlockManager@@1PEAV1@EA, rbx; CReservedBlockManager * CReservedBlockManager::s_pInstance
0x3838d4f1e  call    ?UninitializeVLHeapPool@@YAXXZ; UninitializeVLHeapPool(void)
0x3838d4f23  test    byte ptr cs:_bidGblFlags, 2
0x3838d4f2a  jz      short loc_3838D4F5E
0x3838d4f2c  mov     rcx, cs:off_383B43250; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838d4f33  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4f3a  test    rax, rax
0x3838d4f3d  jz      short loc_3838D4F5E
0x3838d4f3f  mov     [rsp+68h+var_48], 10Fh
0x3838d4f47  mov     edx, 43C29h
0x3838d4f4c  mov     r9d, 80004005h
0x3838d4f52  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3838d4f59  call    _bidTraceW
0x3838d4f5e  mov     ebx, 80004005h
0x3838d4f63  jmp     loc_3838963E9
```
