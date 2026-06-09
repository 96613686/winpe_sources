# CustomizedContactGroupPropMapping_UnistoreToUdm(UnistoreOperationContext *,ulong,Udm::Vector<_USPROPVAL> const &,UdmPropertyValue *)

- ea: `0x1800c08c0`
- end: `0x1800c0be3`
- name: `?CustomizedContactGroupPropMapping_UnistoreToUdm@@YAJPEAVUnistoreOperationContext@@KAEBV?$Vector@U_USPROPVAL@@@Udm@@PEAUUdmPropertyValue@@@Z`
- size: `803`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800054c0`
- `0x18000ae80`
- `0x180027220`
- `0x18004aff0`
- `0x180072ccc`
- `0x1800c08c0`
- `0x1800c0bec`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c0a3e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c0b53`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c0a3e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800c0b53`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c09f3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c0b08`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c09f3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800c0b08`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c0a15`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c0b2a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c0a15`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800c0b2a`
- `UserDataTypeHelperUtil!DupString` at `0x1800c0a8e`
- `UserDataTypeHelperUtil!DupString` at `0x1800c0a8e`

## pseudocode

```c
__int64 __fastcall CustomizedContactGroupPropMapping_UnistoreToUdm(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  const struct _USPROPVAL *v9; // rdi
  const struct _USPROPVAL *v10; // rdx
  unsigned __int64 v11; // rcx
  const struct _USPROPVAL *v12; // rax
  struct UdmPropertyValue *v13; // rdx
  const struct _USPROPVAL *v14; // rax
  const struct _USPROPVAL *v15; // rsi
  StorePropertyCache *v16; // rdi
  int PropertiesForStore; // eax
  const struct _USPROPVAL *PropByUnistorePropId; // rax
  const struct _USPROPVAL *v19; // rsi
  StorePropertyCache *v20; // rdi
  __int64 v21; // xmm2_8
  WINBOOL fPending; // [rsp+30h] [rbp-40h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-38h] BYREF
  struct StorePropertySet *v25; // [rsp+40h] [rbp-30h] BYREF
  __int64 v26; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v27[24]; // [rsp+50h] [rbp-20h] BYREF

  *(_DWORD *)&v27[4] = a2;
  *(_DWORD *)v27 = 256;
  *(_OWORD *)&v27[8] = 0;
  switch ( a2 )
  {
    case 470155271:
      PropByUnistorePropId = FindPropByUnistorePropId(*(_QWORD *)a3, *(const struct _USPROPVAL **)(a3 + 8), 0x20003u);
      v19 = PropByUnistorePropId;
      if ( PropByUnistorePropId && (*((_WORD *)PropByUnistorePropId + 3) & 0x300) == 0 )
      {
        *(_DWORD *)v27 = 0;
        Context = 0;
        fPending = 0;
        v25 = 0;
        InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, (LPVOID *)&v25);
        v20 = v25;
        if ( !v25 )
        {
          qword_18015EA70 = 0;
          InitializeCriticalSectionEx(&stru_18015EA78, 0, 0);
          utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(qword_18015EAA0);
          v26 = 0;
          v20 = (StorePropertyCache *)&qword_18015EA70;
          InitOnceComplete(&stru_18015EA68, 0, &qword_18015EA70);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v26);
        }
        PropertiesForStore = StorePropertyCache::GetPropertiesForStore(
                               v20,
                               *((_DWORD *)v19 + 2),
                               (const struct StorePropertySet **)&Context);
        v5 = PropertiesForStore;
        if ( PropertiesForStore < 0 )
        {
          v8 = 85;
          goto LABEL_16;
        }
        *(_QWORD *)&v27[8] = 0x2900000000LL;
        *(_DWORD *)&v27[16] = *(_DWORD *)Context;
      }
      goto LABEL_29;
    case 470548485:
      v14 = FindPropByUnistorePropId(*(_QWORD *)a3, *(const struct _USPROPVAL **)(a3 + 8), 0x20003u);
      v15 = v14;
      if ( v14 && (*((_WORD *)v14 + 3) & 0x300) == 0 )
      {
        v25 = 0;
        fPending = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, &Context);
        v16 = (StorePropertyCache *)Context;
        if ( !Context )
        {
          qword_18015EA70 = 0;
          InitializeCriticalSectionEx(&stru_18015EA78, 0, 0);
          utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(qword_18015EAA0);
          v26 = 0;
          v16 = (StorePropertyCache *)&qword_18015EA70;
          InitOnceComplete(&stru_18015EA68, 0, &qword_18015EA70);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v26);
        }
        PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v16, *((_DWORD *)v15 + 2), &v25);
        v5 = PropertiesForStore;
        if ( PropertiesForStore < 0 )
        {
          v8 = 100;
LABEL_16:
          v6 = 1;
          v7 = (unsigned int)PropertiesForStore;
          goto LABEL_17;
        }
        v13 = (struct UdmPropertyValue *)*((_QWORD *)v25 + 1);
        if ( v13 )
        {
          PropertiesForStore = DupString(&v27[8], v13);
          v5 = PropertiesForStore;
          if ( PropertiesForStore < 0 )
          {
            v8 = 104;
            goto LABEL_16;
          }
          *(_DWORD *)v27 &= ~0x100u;
        }
      }
LABEL_29:
      v21 = *(_QWORD *)&v27[16];
      *(_OWORD *)a4 = *(_OWORD *)v27;
      v5 = 0;
      *(_QWORD *)&v27[16] = 0;
      *(_QWORD *)(a4 + 16) = v21;
      *(_OWORD *)v27 = 0;
      goto LABEL_30;
    case 478216199:
      v9 = FindPropByUnistorePropId(*(_QWORD *)a3, *(const struct _USPROPVAL **)(a3 + 8), 0xE090013u);
      v12 = FindPropByUnistorePropId(v11, v10, 0x20003u);
      if ( v9 && (*((_WORD *)v9 + 3) & 0x300) == 0 && v12 && (*((_WORD *)v12 + 3) & 0x300) == 0 )
      {
        *(_DWORD *)v27 = 0;
        *(_DWORD *)&v27[8] = *((_DWORD *)v12 + 2);
        *(_DWORD *)&v27[12] = 38;
        *(_DWORD *)&v27[16] = *((_DWORD *)v9 + 2);
      }
      goto LABEL_29;
  }
  v5 = -2147024809;
  v6 = 0;
  v7 = 2147942487LL;
  v8 = 130;
LABEL_17:
  Log_HREvent_60(v7, v6, a3, v8);
LABEL_30:
  Udm::FreeUdmPropVal((Udm *)v27, v13);
  return v5;
}

```

## disassembly

```asm
0x1800c08c0  mov     [rsp-18h+arg_0], rsi
0x1800c08c5  push    rbp
0x1800c08c6  push    rdi
0x1800c08c7  push    r14
0x1800c08c9  mov     rbp, rsp
0x1800c08cc  sub     rsp, 70h
0x1800c08d0  mov     rax, cs:__security_cookie
0x1800c08d7  xor     rax, rsp
0x1800c08da  mov     [rbp+var_8], rax
0x1800c08de  xorps   xmm0, xmm0
0x1800c08e1  xor     eax, eax
0x1800c08e3  mov     [rbp+var_10], rax
0x1800c08e7  mov     r14, r9
0x1800c08ea  mov     r11, r8
0x1800c08ed  movups  [rbp+var_20], xmm0
0x1800c08f1  mov     dword ptr [rbp+var_20+4], edx
0x1800c08f4  mov     dword ptr [rbp+var_20], 100h
0x1800c08fb  movdqu  [rbp+var_20+8], xmm0
0x1800c0900  cmp     edx, 1C060007h
0x1800c0906  jz      loc_1800C0AAC
0x1800c090c  cmp     edx, 1C0C0005h
0x1800c0912  jz      loc_1800C099E
0x1800c0918  cmp     edx, 1C810007h
0x1800c091e  jz      short loc_1800C0934
0x1800c0920  mov     edi, 80070057h
0x1800c0925  xor     edx, edx
0x1800c0927  mov     ecx, edi
0x1800c0929  mov     r9d, 82h
0x1800c092f  jmp     loc_1800C0A6F
0x1800c0934  mov     rdx, [r8+8]; struct _USPROPVAL *
0x1800c0938  mov     r8d, 0E090013h; unsigned int
0x1800c093e  mov     rcx, [r11]; unsigned __int64
0x1800c0941  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x1800c0946  mov     r8d, 20003h; unsigned int
0x1800c094c  mov     rdi, rax
0x1800c094f  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x1800c0954  test    rdi, rdi
0x1800c0957  jz      loc_1800C0B99
0x1800c095d  mov     ecx, 300h
0x1800c0962  test    [rdi+6], cx
0x1800c0966  jnz     loc_1800C0B99
0x1800c096c  test    rax, rax
0x1800c096f  jz      loc_1800C0B99
0x1800c0975  test    [rax+6], cx
0x1800c0979  jnz     loc_1800C0B99
0x1800c097f  mov     dword ptr [rbp+var_20], 0
0x1800c0986  mov     eax, [rax+8]
0x1800c0989  mov     dword ptr [rbp+var_20+8], eax
0x1800c098c  mov     dword ptr [rbp+var_20+0Ch], 26h ; '&'
0x1800c0993  mov     eax, [rdi+8]
0x1800c0996  mov     dword ptr [rbp+var_10], eax
0x1800c0999  jmp     loc_1800C0B99
0x1800c099e  mov     rdx, [r11+8]; struct _USPROPVAL *
0x1800c09a2  mov     r8d, 20003h; unsigned int
0x1800c09a8  mov     rcx, [r11]; unsigned __int64
0x1800c09ab  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x1800c09b0  mov     rsi, rax
0x1800c09b3  test    rax, rax
0x1800c09b6  jz      loc_1800C0B99
0x1800c09bc  mov     ecx, 300h
0x1800c09c1  test    [rax+6], cx
0x1800c09c5  jnz     loc_1800C0B99
0x1800c09cb  lea     r9, [rbp+Context]; lpContext
0x1800c09cf  mov     [rbp+var_30], 0
0x1800c09d7  lea     r8, [rbp+fPending]; fPending
0x1800c09db  mov     [rbp+fPending], 0
0x1800c09e2  xor     edx, edx; dwFlags
0x1800c09e4  mov     [rbp+Context], 0
0x1800c09ec  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c09f3  call    cs:__imp_InitOnceBeginInitialize
0x1800c09f9  mov     rdi, [rbp+Context]
0x1800c09fd  test    rdi, rdi
0x1800c0a00  jnz     short loc_1800C0A4D
0x1800c0a02  xor     r8d, r8d; Flags
0x1800c0a05  mov     cs:qword_18015EA70, rdi
0x1800c0a0c  xor     edx, edx; dwSpinCount
0x1800c0a0e  lea     rcx, stru_18015EA78; lpCriticalSection
0x1800c0a15  call    cs:__imp_InitializeCriticalSectionEx
0x1800c0a1b  lea     rcx, qword_18015EAA0
0x1800c0a22  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800c0a27  mov     [rbp+var_28], rdi
0x1800c0a2b  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c0a32  lea     rdi, qword_18015EA70
0x1800c0a39  xor     edx, edx; dwFlags
0x1800c0a3b  mov     r8, rdi; lpContext
0x1800c0a3e  call    cs:__imp_InitOnceComplete
0x1800c0a44  lea     rcx, [rbp+var_28]
0x1800c0a48  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800c0a4d  mov     edx, [rsi+8]; unsigned int
0x1800c0a50  lea     r8, [rbp+var_30]; struct StorePropertySet **
0x1800c0a54  mov     rcx, rdi; this
0x1800c0a57  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x1800c0a5c  mov     edi, eax
0x1800c0a5e  test    eax, eax
0x1800c0a60  jns     short loc_1800C0A79
0x1800c0a62  mov     r9d, 64h ; 'd'
0x1800c0a68  mov     edx, 1
0x1800c0a6d  mov     ecx, eax
0x1800c0a6f  call    Log_HREvent_60
0x1800c0a74  jmp     loc_1800C0BBB
0x1800c0a79  mov     rax, [rbp+var_30]
0x1800c0a7d  mov     rdx, [rax+8]
0x1800c0a81  test    rdx, rdx
0x1800c0a84  jz      loc_1800C0B99
0x1800c0a8a  lea     rcx, [rbp+var_20+8]
0x1800c0a8e  call    cs:__imp_DupString
0x1800c0a94  mov     edi, eax
0x1800c0a96  test    eax, eax
0x1800c0a98  jns     short loc_1800C0AA2
0x1800c0a9a  mov     r9d, 68h ; 'h'
0x1800c0aa0  jmp     short loc_1800C0A68
0x1800c0aa2  btr     dword ptr [rbp+var_20], 8
0x1800c0aa7  jmp     loc_1800C0B99
0x1800c0aac  mov     rdx, [r11+8]; struct _USPROPVAL *
0x1800c0ab0  mov     r8d, 20003h; unsigned int
0x1800c0ab6  mov     rcx, [r11]; unsigned __int64
0x1800c0ab9  call    ?FindPropByUnistorePropId@@YAPEBU_USPROPVAL@@_KPEBU1@K@Z; FindPropByUnistorePropId(unsigned __int64,_USPROPVAL const *,ulong)
0x1800c0abe  mov     rsi, rax
0x1800c0ac1  test    rax, rax
0x1800c0ac4  jz      loc_1800C0B99
0x1800c0aca  mov     ecx, 300h
0x1800c0acf  test    [rax+6], cx
0x1800c0ad3  jnz     loc_1800C0B99
0x1800c0ad9  lea     r9, [rbp+var_30]; lpContext
0x1800c0add  mov     dword ptr [rbp+var_20], 0
0x1800c0ae4  lea     r8, [rbp+fPending]; fPending
0x1800c0ae8  mov     [rbp+Context], 0
0x1800c0af0  xor     edx, edx; dwFlags
0x1800c0af2  mov     [rbp+fPending], 0
0x1800c0af9  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c0b00  mov     [rbp+var_30], 0
0x1800c0b08  call    cs:__imp_InitOnceBeginInitialize
0x1800c0b0e  mov     rdi, [rbp+var_30]
0x1800c0b12  test    rdi, rdi
0x1800c0b15  jnz     short loc_1800C0B62
0x1800c0b17  xor     r8d, r8d; Flags
0x1800c0b1a  mov     cs:qword_18015EA70, rdi
0x1800c0b21  xor     edx, edx; dwSpinCount
0x1800c0b23  lea     rcx, stru_18015EA78; lpCriticalSection
0x1800c0b2a  call    cs:__imp_InitializeCriticalSectionEx
0x1800c0b30  lea     rcx, qword_18015EAA0
0x1800c0b37  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800c0b3c  mov     [rbp+var_28], rdi
0x1800c0b40  lea     rcx, stru_18015EA68; lpInitOnce
0x1800c0b47  lea     rdi, qword_18015EA70
0x1800c0b4e  xor     edx, edx; dwFlags
0x1800c0b50  mov     r8, rdi; lpContext
0x1800c0b53  call    cs:__imp_InitOnceComplete
0x1800c0b59  lea     rcx, [rbp+var_28]
0x1800c0b5d  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800c0b62  mov     edx, [rsi+8]; unsigned int
0x1800c0b65  lea     r8, [rbp+Context]; struct StorePropertySet **
0x1800c0b69  mov     rcx, rdi; this
0x1800c0b6c  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x1800c0b71  mov     edi, eax
0x1800c0b73  test    eax, eax
0x1800c0b75  jns     short loc_1800C0B82
0x1800c0b77  mov     r9d, 55h ; 'U'
0x1800c0b7d  jmp     loc_1800C0A68
0x1800c0b82  mov     rax, [rbp+Context]
0x1800c0b86  mov     dword ptr [rbp+var_20+8], 0
0x1800c0b8d  mov     dword ptr [rbp+var_20+0Ch], 29h ; ')'
0x1800c0b94  mov     ecx, [rax]
0x1800c0b96  mov     dword ptr [rbp+var_10], ecx
0x1800c0b99  movups  xmm1, [rbp+var_20]
0x1800c0b9d  xor     eax, eax
0x1800c0b9f  movsd   xmm2, [rbp+var_10]
0x1800c0ba4  xorps   xmm0, xmm0
0x1800c0ba7  movups  xmmword ptr [r14], xmm1
0x1800c0bab  xor     edi, edi
0x1800c0bad  mov     [rbp+var_10], rax
0x1800c0bb1  movsd   qword ptr [r14+10h], xmm2
0x1800c0bb7  movups  [rbp+var_20], xmm0
0x1800c0bbb  lea     rcx, [rbp+var_20]; this
0x1800c0bbf  call    ?FreeUdmPropVal@Udm@@YAXPEAUUdmPropertyValue@@@Z; Udm::FreeUdmPropVal(UdmPropertyValue *)
0x1800c0bc4  mov     eax, edi
0x1800c0bc6  mov     rcx, [rbp+var_8]
0x1800c0bca  xor     rcx, rsp; StackCookie
0x1800c0bcd  call    __security_check_cookie
0x1800c0bd2  mov     rsi, [rsp+70h+arg_0]
0x1800c0bda  add     rsp, 70h
0x1800c0bde  pop     r14
0x1800c0be0  pop     rdi
0x1800c0be1  pop     rbp
0x1800c0be2  retn
```
