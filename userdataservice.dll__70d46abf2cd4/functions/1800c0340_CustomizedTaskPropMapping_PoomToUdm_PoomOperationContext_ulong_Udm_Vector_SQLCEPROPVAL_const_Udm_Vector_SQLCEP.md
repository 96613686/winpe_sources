# CustomizedTaskPropMapping_PoomToUdm(PoomOperationContext *,ulong,Udm::Vector<_SQLCEPROPVAL> const &,Udm::Vector<_SQLCEPROPVAL> const &,UdmObjectId const &,UdmPropertyValue *)

- ea: `0x1800c0340`
- end: `0x1800c05db`
- name: `?CustomizedTaskPropMapping_PoomToUdm@@YAJPEAVPoomOperationContext@@KAEBV?$Vector@U_SQLCEPROPVAL@@@Udm@@1AEBUUdmObjectId@@PEAUUdmPropertyValue@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPVOID Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800054c0`
- `0x18000ae80`
- `0x18004aff0`
- `0x180072ccc`
- `0x1800c0340`
- `0x1800c06c8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c0474`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c057d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c0474`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c057d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c0429`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c0532`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c0429`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c0532`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c044b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c0554`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c044b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c0554`
- `UserDataTypeHelperUtil!DupString` at `0x1800c04b9`
- `UserDataTypeHelperUtil!DupString` at `0x1800c04b9`

## pseudocode

```c
__int64 __fastcall CustomizedTaskPropMapping_PoomToUdm(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _DWORD *Context)
{
  _DWORD *v6; // rdi
  const struct _USPROPVAL *v8; // rax
  const struct _USPROPVAL *v9; // rax
  const struct _USPROPVAL *v10; // r14
  StorePropertyCache *v11; // rsi
  int PropertiesForStore; // esi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  const struct _USPROPVAL *PropByUnistorePropId; // rax
  const struct _USPROPVAL *v17; // r14
  StorePropertyCache *v18; // rsi
  struct StorePropertySet *v19; // rax
  struct StorePropertySet *v20; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v21[2]; // [rsp+38h] [rbp-10h] BYREF
  WINBOOL fPending; // [rsp+78h] [rbp+30h] BYREF

  v6 = Context;
  Context[1] = a2;
  switch ( a2 )
  {
    case 453050375:
      PropByUnistorePropId = FindPropByUnistorePropId(*(_QWORD *)a3, *(const struct _USPROPVAL **)(a3 + 8), 0x20003u);
      v17 = PropByUnistorePropId;
      if ( PropByUnistorePropId && (*((_WORD *)PropByUnistorePropId + 3) & 0x300) == 0 )
      {
        *v6 &= ~0x100u;
        v20 = 0;
        fPending = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, (LPVOID *)&Context);
        v18 = (StorePropertyCache *)Context;
        if ( !Context )
        {
          qword_18015EA70 = 0;
          InitializeCriticalSectionEx(&stru_18015EA78, 0, 0);
          utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(qword_18015EAA0);
          v21[0] = 0;
          v18 = (StorePropertyCache *)&qword_18015EA70;
          InitOnceComplete(&stru_18015EA68, 0, &qword_18015EA70);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(v21);
        }
        PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v18, *((_DWORD *)v17 + 2), &v20);
        if ( PropertiesForStore < 0 )
        {
          v14 = 63;
          goto LABEL_24;
        }
        v19 = v20;
        v6[2] = 0;
        v6[3] = 41;
        v6[4] = *(_DWORD *)v19;
      }
      break;
    case 453378053:
      v9 = FindPropByUnistorePropId(*(_QWORD *)a3, *(const struct _USPROPVAL **)(a3 + 8), 0x20003u);
      v10 = v9;
      if ( v9 && (*((_WORD *)v9 + 3) & 0x300) == 0 )
      {
        v20 = 0;
        fPending = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, (LPVOID *)&Context);
        v11 = (StorePropertyCache *)Context;
        if ( !Context )
        {
          qword_18015EA70 = 0;
          InitializeCriticalSectionEx(&stru_18015EA78, 0, 0);
          utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(qword_18015EAA0);
          v21[0] = 0;
          v11 = (StorePropertyCache *)&qword_18015EA70;
          InitOnceComplete(&stru_18015EA68, 0, &qword_18015EA70);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(v21);
        }
        PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v11, *((_DWORD *)v10 + 2), &v20);
        if ( PropertiesForStore < 0 )
        {
          v14 = 78;
LABEL_24:
          Log_HREvent_59((unsigned int)PropertiesForStore, 1, v13, v14);
          return (unsigned int)PropertiesForStore;
        }
        v15 = *((_QWORD *)v20 + 1);
        if ( v15 )
        {
          PropertiesForStore = DupString(v6 + 2, v15);
          if ( PropertiesForStore < 0 )
          {
            v14 = 82;
            goto LABEL_24;
          }
          *v6 &= ~0x100u;
        }
      }
      break;
    case 458293255:
      v8 = FindPropByUnistorePropId(*(_QWORD *)a3, *(const struct _USPROPVAL **)(a3 + 8), 0xE090013u);
      if ( v8 )
      {
        if ( (*((_WORD *)v8 + 3) & 0x300) == 0 )
        {
          *v6 &= ~0x100u;
          v6[2] = 0;
          v6[3] = 50;
          v6[4] = *((_DWORD *)v8 + 2);
        }
      }
      return 0;
    default:
      Log_HREvent_59(2147942487LL, 0, a3, 105);
      return 2147942487LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800c0340  push    rbp
0x1800c0342  push    rsi
0x1800c0343  push    rdi
0x1800c0344  push    r14
0x1800c0346  mov     rbp, rsp
0x1800c0349  sub     rsp, 48h
0x1800c034d  mov     rdi, [rbp+Context]
0x1800c0351  mov     rax, r8
0x1800c0354  mov     [rdi+4], edx
0x1800c0357  cmp     edx, 1B010007h
0x1800c035d  jz      loc_1800C04D9
0x1800c0363  cmp     edx, 1B060005h
0x1800c0369  jz      short loc_1800C03D4
0x1800c036b  cmp     edx, 1B510007h
0x1800c0371  jz      short loc_1800C038D
0x1800c0373  xor     edx, edx
0x1800c0375  mov     ecx, 80070057h
0x1800c037a  lea     r9d, [rdx+69h]
0x1800c037e  call    Log_HREvent_59
0x1800c0383  mov     eax, 80070057h
0x1800c0388  jmp     loc_1800C05D1
0x1800c038d  mov     rdx, [rax+8]; struct _USPROPVAL *
0x1800c0391  mov     r8d, 0E090013h; unsigned int
0x1800c0397  mov     rcx, [rax]; unsigned __int64
0x1800c039a  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x1800c039f  test    rax, rax
0x1800c03a2  jz      loc_1800C05CF
0x1800c03a8  mov     ecx, 300h
0x1800c03ad  test    [rax+6], cx
0x1800c03b1  jnz     loc_1800C05CF
0x1800c03b7  btr     dword ptr [rdi], 8
0x1800c03bb  mov     dword ptr [rdi+8], 0
0x1800c03c2  mov     dword ptr [rdi+0Ch], 32h ; '2'
0x1800c03c9  mov     eax, [rax+8]
0x1800c03cc  mov     [rdi+10h], eax
0x1800c03cf  jmp     loc_1800C05CF
0x1800c03d4  mov     rdx, [rax+8]; struct _USPROPVAL *
0x1800c03d8  mov     r8d, 20003h; unsigned int
0x1800c03de  mov     rcx, [rax]; unsigned __int64
0x1800c03e1  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x1800c03e6  mov     r14, rax
0x1800c03e9  test    rax, rax
0x1800c03ec  jz      loc_1800C05CF
0x1800c03f2  mov     ecx, 300h
0x1800c03f7  test    [rax+6], cx
0x1800c03fb  jnz     loc_1800C05CF
0x1800c0401  lea     r9, [rbp+Context]; lpContext
0x1800c0405  mov     [rbp+var_18], 0
0x1800c040d  lea     r8, [rbp+fPending]; fPending
0x1800c0411  mov     [rbp+fPending], 0
0x1800c0418  xor     edx, edx; dwFlags
0x1800c041a  mov     [rbp+Context], 0
0x1800c0422  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c0429  call    cs:__imp_InitOnceBeginInitialize
0x1800c042f  mov     rsi, [rbp+Context]
0x1800c0433  test    rsi, rsi
0x1800c0436  jnz     short loc_1800C0483
0x1800c0438  xor     r8d, r8d; Flags
0x1800c043b  mov     cs:qword_18015EA70, rsi
0x1800c0442  xor     edx, edx; dwSpinCount
0x1800c0444  lea     rcx, stru_18015EA78; lpCriticalSection
0x1800c044b  call    cs:__imp_InitializeCriticalSectionEx
0x1800c0451  lea     rcx, qword_18015EAA0
0x1800c0458  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800c045d  mov     [rbp+var_10], rsi
0x1800c0461  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c0468  lea     rsi, qword_18015EA70
0x1800c046f  xor     edx, edx; dwFlags
0x1800c0471  mov     r8, rsi; lpContext
0x1800c0474  call    cs:__imp_InitOnceComplete
0x1800c047a  lea     rcx, [rbp+var_10]
0x1800c047e  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800c0483  mov     edx, [r14+8]; unsigned int
0x1800c0487  lea     r8, [rbp+var_18]; struct StorePropertySet **
0x1800c048b  mov     rcx, rsi; this
0x1800c048e  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x1800c0493  mov     esi, eax
0x1800c0495  test    eax, eax
0x1800c0497  jns     short loc_1800C04A4
0x1800c0499  mov     r9d, 4Eh ; 'N'
0x1800c049f  jmp     loc_1800C05A8
0x1800c04a4  mov     rax, [rbp+var_18]
0x1800c04a8  mov     rdx, [rax+8]
0x1800c04ac  test    rdx, rdx
0x1800c04af  jz      loc_1800C05CF
0x1800c04b5  lea     rcx, [rdi+8]
0x1800c04b9  call    cs:__imp_DupString
0x1800c04bf  mov     esi, eax
0x1800c04c1  test    eax, eax
0x1800c04c3  jns     short loc_1800C04D0
0x1800c04c5  mov     r9d, 52h ; 'R'
0x1800c04cb  jmp     loc_1800C05A8
0x1800c04d0  btr     dword ptr [rdi], 8
0x1800c04d4  jmp     loc_1800C05CF
0x1800c04d9  mov     rdx, [rax+8]; struct _USPROPVAL *
0x1800c04dd  mov     r8d, 20003h; unsigned int
0x1800c04e3  mov     rcx, [rax]; unsigned __int64
0x1800c04e6  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x1800c04eb  mov     r14, rax
0x1800c04ee  test    rax, rax
0x1800c04f1  jz      loc_1800C05CF
0x1800c04f7  mov     ecx, 300h
0x1800c04fc  test    [rax+6], cx
0x1800c0500  jnz     loc_1800C05CF
0x1800c0506  btr     dword ptr [rdi], 8
0x1800c050a  lea     r9, [rbp+Context]; lpContext
0x1800c050e  lea     r8, [rbp+fPending]; fPending
0x1800c0512  mov     [rbp+var_18], 0
0x1800c051a  xor     edx, edx; dwFlags
0x1800c051c  mov     [rbp+fPending], 0
0x1800c0523  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c052a  mov     [rbp+Context], 0
0x1800c0532  call    cs:__imp_InitOnceBeginInitialize
0x1800c0538  mov     rsi, [rbp+Context]
0x1800c053c  test    rsi, rsi
0x1800c053f  jnz     short loc_1800C058C
0x1800c0541  xor     r8d, r8d; Flags
0x1800c0544  mov     cs:qword_18015EA70, rsi
0x1800c054b  xor     edx, edx; dwSpinCount
0x1800c054d  lea     rcx, stru_18015EA78; lpCriticalSection
0x1800c0554  call    cs:__imp_InitializeCriticalSectionEx
0x1800c055a  lea     rcx, qword_18015EAA0
0x1800c0561  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800c0566  mov     [rbp+var_10], rsi
0x1800c056a  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c0571  lea     rsi, qword_18015EA70
0x1800c0578  xor     edx, edx; dwFlags
0x1800c057a  mov     r8, rsi; lpContext
0x1800c057d  call    cs:__imp_InitOnceComplete
0x1800c0583  lea     rcx, [rbp+var_10]
0x1800c0587  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800c058c  mov     edx, [r14+8]; unsigned int
0x1800c0590  lea     r8, [rbp+var_18]; struct StorePropertySet **
0x1800c0594  mov     rcx, rsi; this
0x1800c0597  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x1800c059c  mov     esi, eax
0x1800c059e  test    eax, eax
0x1800c05a0  jns     short loc_1800C05B8
0x1800c05a2  mov     r9d, 3Fh ; '?'
0x1800c05a8  mov     edx, 1
0x1800c05ad  mov     ecx, esi
0x1800c05af  call    Log_HREvent_59
0x1800c05b4  mov     eax, esi
0x1800c05b6  jmp     short loc_1800C05D1
0x1800c05b8  mov     rax, [rbp+var_18]
0x1800c05bc  mov     dword ptr [rdi+8], 0
0x1800c05c3  mov     dword ptr [rdi+0Ch], 29h ; ')'
0x1800c05ca  mov     ecx, [rax]
0x1800c05cc  mov     [rdi+10h], ecx
0x1800c05cf  xor     eax, eax
0x1800c05d1  add     rsp, 48h
0x1800c05d5  pop     r14
0x1800c05d7  pop     rdi
0x1800c05d8  pop     rsi
0x1800c05d9  pop     rbp
0x1800c05da  retn
```
