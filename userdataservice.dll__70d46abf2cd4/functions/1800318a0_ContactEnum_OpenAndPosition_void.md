# ContactEnum::OpenAndPosition(void)

- ea: `0x1800318a0`
- end: `0x180031e1b`
- name: `?OpenAndPosition@ContactEnum@@MEAAJXZ`
- size: `1403`
- prototype: `__int64 __fastcall(ContactEnum *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18000ae80`
- `0x18000b22c`
- `0x1800303cc`
- `0x1800318a0`
- `0x180031e24`
- `0x180032228`
- `0x180032c14`
- `0x180035c40`
- `0x18003ac30`
- `0x18003ed7c`
- `0x180056bb0`
- `0x180059de0`
- `0x180072ccc`
- `0x180079824`
- `0x180087d04`
- `0x1800e482c`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!GetSortBy` at `0x180031d48`
- `PIMSTORE!GetSortBy` at `0x180031d48`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800319f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800319f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031b06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b30`
- `UserDataLanguageUtil!GetConvertedTextForMatching` at `0x180031c70`
- `UserDataLanguageUtil!GetConvertedTextForMatching` at `0x180031c70`
- `OLEAUT32!__imp_SysAllocString` at `0x180031d75`
- `OLEAUT32!__imp_SysAllocString` at `0x180031d75`

## string_xrefs

- `0x180031950`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180031ad6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180031b4b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180031be0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180031cbd`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180031d20`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180031dd1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`

## pseudocode

```c
__int64 __fastcall ContactEnum::OpenAndPosition(ContactEnum *this)
{
  __int64 *v1; // r14
  __int64 v3; // rcx
  unsigned int *v4; // r15
  int v5; // eax
  int PropertiesForStore; // esi
  __int64 v7; // r9
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 *v12; // r12
  StorePropertyCache *v13; // rsi
  __int64 v14; // rcx
  int v15; // eax
  int SortBy; // edi
  __int64 v17; // r9
  HANDLE *v18; // r15
  HANDLE EventW; // rsi
  signed int LastError; // eax
  unsigned int v21; // ebx
  int v22; // eax
  __int64 v23; // rcx
  int EmailPhoneSearchResults; // eax
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  const unsigned __int16 *v28; // rcx
  const unsigned __int16 *v29; // r11
  __int64 v30; // r9
  const OLECHAR *v31; // rcx
  BSTR v32; // rax
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // eax
  LPVOID Context; // [rsp+30h] [rbp-D0h] BYREF
  WINBOOL fPending; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v40; // [rsp+3Ch] [rbp-C4h] BYREF
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  struct StorePropertySet *v42[2]; // [rsp+48h] [rbp-B8h] BYREF
  union _RTL_RUN_ONCE *v43; // [rsp+58h] [rbp-A8h] BYREF
  struct StorePropertySet *v44; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+68h] [rbp-98h]
  unsigned __int16 v46[256]; // [rsp+70h] [rbp-90h] BYREF

  v1 = (__int64 *)((char *)this + 352);
  v3 = *((_QWORD *)this + 44);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *v1 = 0;
  }
  v41 = 0;
  v4 = (unsigned int *)((char *)this + 184);
  v5 = (*(__int64 (__fastcall **)(char *, char *, int *, _QWORD))(*((_QWORD *)this + 16) + 24LL))(
         (char *)this + 128,
         (char *)this + 184,
         &v41,
         0);
  if ( (unsigned int)IsItemNotFoundError(v5) )
  {
    *((_DWORD *)this + 27) = 1;
    return 0;
  }
  PropertiesForStore = ContactQueryEnumBase::PopulateAnnotationOperationFilterResults(this, 196609);
  if ( PropertiesForStore < 0 )
  {
    v7 = 763;
    goto LABEL_7;
  }
  *((_DWORD *)this + 99) = v41 == 1;
  v9 = *((unsigned int *)this + 47);
  LODWORD(v42[0]) = *v4;
  v10 = UdmTypeToUnistoreType(v9);
  v11 = *((_QWORD *)this + 22);
  v12 = (__int64 *)((char *)this + 360);
  HIDWORD(v42[0]) = v10;
  v45 = *((_DWORD *)this + 48);
  v44 = v42[0];
  PropertiesForStore = (*(__int64 (__fastcall **)(__int64, struct StorePropertySet **, char *))(*(_QWORD *)v11 + 112LL))(
                         v11,
                         &v44,
                         (char *)this + 360);
  if ( PropertiesForStore < 0 )
  {
    v7 = 771;
    goto LABEL_7;
  }
  v42[0] = 0;
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, &Context);
  v13 = (StorePropertyCache *)Context;
  if ( !Context )
  {
    v43 = &stru_18015EA68;
    v13 = (StorePropertyCache *)tlx::_LazyImpl<StorePropertyCache,tlx::lazy_construct<StorePropertyCache>,tlx::static_lazy<StorePropertyCache,0,tlx::lazy_construct<StorePropertyCache>>>::_Initializer::_Construct(&v43);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v43);
  }
  PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v13, *v4, v42);
  if ( PropertiesForStore < 0 )
  {
    v7 = 775;
    goto LABEL_7;
  }
  if ( !*((_DWORD *)this + 63) )
  {
    v23 = *v12;
    Context = 0;
    EmailPhoneSearchResults = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v23 + 96LL))(
                                v23,
                                10,
                                &Context);
    PropertiesForStore = EmailPhoneSearchResults;
    if ( EmailPhoneSearchResults >= 0 )
    {
      EmailPhoneSearchResults = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)Context + 40LL))(
                                  Context,
                                  32,
                                  v1);
      PropertiesForStore = EmailPhoneSearchResults;
      if ( EmailPhoneSearchResults >= 0 )
      {
        EmailPhoneSearchResults = ContactEnum::GetEmailPhoneSearchResults(this, (char *)this + 256);
        PropertiesForStore = EmailPhoneSearchResults;
        if ( EmailPhoneSearchResults >= 0 )
        {
          if ( (*((_BYTE *)this + 240) & 1) != 0 )
          {
            memset_0(v46, 0, 0x1F6u);
            v28 = (const unsigned __int16 *)*((_QWORD *)this + 29);
            v42[0] = 0;
            EmailPhoneSearchResults = StringCchLengthW(v28, 0xFAu, (unsigned __int64 *)v42);
            PropertiesForStore = EmailPhoneSearchResults;
            if ( EmailPhoneSearchResults < 0 )
            {
              v25 = 812;
              goto LABEL_41;
            }
            EmailPhoneSearchResults = GetConvertedTextForMatching(0, v29, (unsigned __int64)v42[0], v46, 0xFBu);
            PropertiesForStore = EmailPhoneSearchResults;
            if ( EmailPhoneSearchResults < 0 )
            {
              v25 = 819;
              goto LABEL_41;
            }
            if ( !v46[0] )
            {
              PropertiesForStore = -2147024809;
              v25 = 820;
              v27 = 2147942487LL;
              v26 = 0;
              goto LABEL_42;
            }
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     (char *)this + 320,
                                     v46) )
            {
              Log_HREvent(
                2147942414LL,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
                822);
              PropertiesForStore = -2147024882;
              goto LABEL_54;
            }
          }
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&Context);
          goto LABEL_56;
        }
        v25 = 804;
      }
      else
      {
        v25 = 803;
      }
    }
    else
    {
      v25 = 801;
    }
LABEL_41:
    v26 = 1;
    v27 = (unsigned int)EmailPhoneSearchResults;
LABEL_42:
    Log_HREvent(
      v27,
      v26,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      v25);
LABEL_54:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&Context);
    return (unsigned int)PropertiesForStore;
  }
  if ( *((_QWORD *)v42[0] + 1) )
  {
    PropertiesForStore = ContactEnum::_CreateUniqueServerSearchFolder(this);
    if ( PropertiesForStore < 0 )
    {
      v7 = 782;
      goto LABEL_7;
    }
    v14 = *v12;
    Context = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, char *, LPVOID *))(*(_QWORD *)v14 + 136LL))(
            v14,
            (char *)this + 400,
            &Context);
    SortBy = v15;
    if ( v15 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)Context + 40LL))(Context, 32, v1);
      SortBy = v15;
      if ( v15 >= 0 )
      {
        SortBy = 0;
        goto LABEL_25;
      }
      v17 = 787;
    }
    else
    {
      v17 = 786;
    }
    Log_HREvent(
      (unsigned int)v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      v17);
LABEL_25:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&Context);
    return (unsigned int)SortBy;
  }
  v18 = (HANDLE *)((char *)this + 368);
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW == *((HANDLE *)this + 46) )
  {
    EventW = *v18;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 368);
    *v18 = EventW;
  }
  if ( EventW )
  {
    v22 = ContactEnum::SubmitServerSearch(this);
    PropertiesForStore = v22;
    if ( v22 < 0 )
    {
      if ( v22 == -2147467260 )
        return (unsigned int)PropertiesForStore;
      v7 = 796;
LABEL_7:
      Log_HREvent(
        (unsigned int)PropertiesForStore,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
        v7);
      return (unsigned int)PropertiesForStore;
    }
LABEL_56:
    if ( (*(unsigned __int8 (__fastcall **)(ContactEnum *))(*(_QWORD *)this + 160LL))(this) )
    {
      if ( !*v1 )
        return 0;
      fPending = 0;
      SortBy = GetSortBy(&fPending);
      if ( SortBy >= 0 )
      {
        v31 = L"[Sort2]";
        Context = 0;
        if ( fPending != 1 )
          v31 = L"[Sort1]";
        v32 = SysAllocString(v31);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::reset(
          &Context,
          v32);
        if ( Context )
        {
          v36 = *v1;
          v40 = 0;
          v37 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, __int16 *))(*(_QWORD *)v36 + 104LL))(
                  v36,
                  1,
                  &Context,
                  &v40);
          SortBy = v37;
          if ( v37 >= 0 )
          {
            tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&Context);
            return 0;
          }
          v33 = 843;
          v35 = 1;
          v34 = (unsigned int)v37;
        }
        else
        {
          SortBy = -2147024882;
          v33 = 840;
          v34 = 2147942414LL;
          v35 = 0;
        }
        Log_HREvent(
          v34,
          v35,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
          v33);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&Context);
        return (unsigned int)SortBy;
      }
      v30 = 836;
    }
    else
    {
      *((_DWORD *)this + 28) = 0;
      SortBy = ContactQueryEnumBase::PrefetchAndSortResults(this);
      if ( SortBy >= 0 )
        return 0;
      v30 = 831;
    }
    Log_HREvent(
      (unsigned int)SortBy,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      v30);
    return (unsigned int)SortBy;
  }
  LastError = GetLastError();
  v21 = LastError;
  if ( LastError > 0 )
    v21 = (unsigned __int16)LastError | 0x80070000;
  Log_HREvent(
    v21,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
    794);
  return v21;
}

```

## disassembly

```asm
0x1800318a0  push    rbp
0x1800318a2  push    rbx
0x1800318a3  push    rsi
0x1800318a4  push    rdi
0x1800318a5  push    r12
0x1800318a7  push    r13
0x1800318a9  push    r14
0x1800318ab  push    r15
0x1800318ad  lea     rbp, [rsp-188h]
0x1800318b5  sub     rsp, 288h
0x1800318bc  mov     rax, cs:__security_cookie
0x1800318c3  xor     rax, rsp
0x1800318c6  mov     [rbp+1C0h+var_50], rax
0x1800318cd  lea     r14, [rcx+160h]
0x1800318d4  mov     rdi, rcx
0x1800318d7  mov     rcx, [r14]
0x1800318da  xor     r13d, r13d
0x1800318dd  test    rcx, rcx
0x1800318e0  jz      short loc_1800318F1
0x1800318e2  mov     rax, [rcx]
0x1800318e5  mov     rax, [rax+10h]
0x1800318e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318ee  mov     [r14], r13
0x1800318f1  lea     rcx, [rdi+80h]
0x1800318f8  mov     [rsp+2C0h+var_280], r13d
0x1800318fd  mov     rax, [rcx]
0x180031900  lea     r15, [rdi+0B8h]
0x180031907  xor     r9d, r9d
0x18003190a  lea     r8, [rsp+2C0h+var_280]
0x18003190f  mov     rdx, r15
0x180031912  mov     rax, [rax+18h]
0x180031916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003191b  mov     ecx, eax; int
0x18003191d  call    ?IsItemNotFoundError@@YAHJ@Z; IsItemNotFoundError(long)
0x180031922  test    eax, eax
0x180031924  jz      short loc_180031932
0x180031926  mov     dword ptr [rdi+6Ch], 1
0x18003192d  jmp     loc_180031DF6
0x180031932  mov     edx, 30001h
0x180031937  mov     rcx, rdi
0x18003193a  call    ?PopulateAnnotationOperationFilterResults@ContactQueryEnumBase@@IEAAJW4US_OBJECTTYPE@@@Z; ContactQueryEnumBase::PopulateAnnotationOperationFilterResults(US_OBJECTTYPE)
0x18003193f  mov     esi, eax
0x180031941  test    eax, eax
0x180031943  jns     short loc_180031965
0x180031945  mov     r9d, 2FBh
0x18003194b  mov     edx, 1
0x180031950  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031957  mov     ecx, esi
0x180031959  call    Log_HREvent
0x18003195e  mov     eax, esi
0x180031960  jmp     loc_180031DF8
0x180031965  mov     eax, r13d
0x180031968  mov     ebx, 1
0x18003196d  cmp     [rsp+2C0h+var_280], ebx
0x180031971  setz    al
0x180031974  mov     [rdi+18Ch], eax
0x18003197a  mov     eax, [r15]
0x18003197d  mov     ecx, [r15+4]
0x180031981  mov     dword ptr [rsp+2C0h+var_278], eax
0x180031985  call    ?UdmTypeToUnistoreType@@YA?AW4US_OBJECTTYPE@@W4UdmItemType@@@Z; UdmTypeToUnistoreType(UdmItemType)
0x18003198a  mov     rcx, [rdi+0B0h]
0x180031991  lea     r12, [rdi+168h]
0x180031998  mov     dword ptr [rsp+2C0h+var_278+4], eax
0x18003199c  lea     rdx, [rsp+2C0h+var_260]
0x1800319a1  mov     eax, [r15+8]
0x1800319a5  mov     r8, r12
0x1800319a8  movsd   xmm0, [rsp+2C0h+var_278]
0x1800319ae  mov     [rsp+2C0h+var_258], eax
0x1800319b2  movsd   [rsp+2C0h+var_260], xmm0
0x1800319b8  mov     rax, [rcx]
0x1800319bb  mov     rax, [rax+70h]
0x1800319bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319c4  mov     esi, eax
0x1800319c6  test    eax, eax
0x1800319c8  jns     short loc_1800319D7
0x1800319ca  mov     r9d, 303h
0x1800319d0  mov     edx, ebx
0x1800319d2  jmp     loc_180031950
0x1800319d7  lea     r9, [rsp+2C0h+Context]; lpContext
0x1800319dc  mov     [rsp+2C0h+var_278], r13
0x1800319e1  lea     r8, [rsp+2C0h+fPending]; fPending
0x1800319e6  mov     [rsp+2C0h+fPending], r13d
0x1800319eb  xor     edx, edx; dwFlags
0x1800319ed  mov     [rsp+2C0h+Context], r13
0x1800319f2  lea     rcx, stru_18015EA68; lpInitOnce
0x1800319f9  call    cs:__imp_InitOnceBeginInitialize
0x1800319ff  mov     rsi, [rsp+2C0h+Context]
0x180031a04  test    rsi, rsi
0x180031a07  jnz     short loc_180031A2C
0x180031a09  lea     rax, stru_18015EA68
0x180031a10  lea     rcx, [rsp+2C0h+var_268]
0x180031a15  mov     [rsp+2C0h+var_268], rax
0x180031a1a  call    ?_Construct@_Initializer@?$_LazyImpl@VStorePropertyCache@@V?$lazy_construct@VStorePropertyCache@@@tlx@@V?$static_lazy@VStorePropertyCache@@$0A@V?$lazy_construct@VStorePropertyCache@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<StorePropertyCache,tlx::lazy_construct<StorePropertyCache>,tlx::static_lazy<StorePropertyCache,0,tlx::lazy_construct<StorePropertyCache>>>::_Initializer::_Construct(void)
0x180031a1f  lea     rcx, [rsp+2C0h+var_268]
0x180031a24  mov     rsi, rax
0x180031a27  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x180031a2c  mov     edx, [r15]; unsigned int
0x180031a2f  lea     r8, [rsp+2C0h+var_278]; struct StorePropertySet **
0x180031a34  mov     rcx, rsi; this
0x180031a37  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x180031a3c  mov     esi, eax
0x180031a3e  test    eax, eax
0x180031a40  jns     short loc_180031A4A
0x180031a42  mov     r9d, 307h
0x180031a48  jmp     short loc_1800319D0
0x180031a4a  cmp     [rdi+0FCh], r13d
0x180031a51  jz      loc_180031B8A
0x180031a57  mov     rax, [rsp+2C0h+var_278]
0x180031a5c  cmp     [rax+8], r13
0x180031a60  jz      loc_180031AFC
0x180031a66  mov     rcx, rdi; this
0x180031a69  call    ?_CreateUniqueServerSearchFolder@ContactEnum@@AEAAJXZ; ContactEnum::_CreateUniqueServerSearchFolder(void)
0x180031a6e  mov     esi, eax
0x180031a70  test    eax, eax
0x180031a72  jns     short loc_180031A7F
0x180031a74  mov     r9d, 30Eh
0x180031a7a  jmp     loc_1800319D0
0x180031a7f  mov     rcx, [r12]
0x180031a83  lea     rdx, [rdi+190h]
0x180031a8a  mov     [rsp+2C0h+Context], r13
0x180031a8f  lea     r8, [rsp+2C0h+Context]
0x180031a94  mov     rax, [rcx]
0x180031a97  mov     rax, [rax+88h]
0x180031a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aa3  mov     edi, eax
0x180031aa5  test    eax, eax
0x180031aa7  jns     short loc_180031AB1
0x180031aa9  mov     r9d, 312h
0x180031aaf  jmp     short loc_180031AD6
0x180031ab1  mov     rcx, [rsp+2C0h+Context]
0x180031ab6  mov     r8, r14
0x180031ab9  mov     edx, 20h ; ' '
0x180031abe  mov     rax, [rcx]
0x180031ac1  mov     rax, [rax+28h]
0x180031ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aca  mov     edi, eax
0x180031acc  test    eax, eax
0x180031ace  jns     short loc_180031AE8
0x180031ad0  mov     r9d, 313h
0x180031ad6  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031add  mov     edx, ebx
0x180031adf  mov     ecx, eax
0x180031ae1  call    Log_HREvent
0x180031ae6  jmp     short loc_180031AEB
0x180031ae8  mov     edi, r13d
0x180031aeb  lea     rcx, [rsp+2C0h+Context]
0x180031af0  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180031af5  mov     eax, edi
0x180031af7  jmp     loc_180031DF8
0x180031afc  xor     r9d, r9d; lpName
0x180031aff  xor     r8d, r8d; bInitialState
0x180031b02  mov     edx, ebx; bManualReset
0x180031b04  xor     ecx, ecx; lpEventAttributes
0x180031b06  call    cs:__imp_CreateEventW
0x180031b0c  lea     r15, [rdi+170h]
0x180031b13  mov     rsi, rax
0x180031b16  cmp     rax, [r15]
0x180031b19  jz      short loc_180031B28
0x180031b1b  mov     rcx, r15
0x180031b1e  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180031b23  mov     [r15], rsi
0x180031b26  jmp     short loc_180031B2B
0x180031b28  mov     rsi, [r15]
0x180031b2b  test    rsi, rsi
0x180031b2e  jnz     short loc_180031B62
0x180031b30  call    cs:__imp_GetLastError
0x180031b36  mov     ebx, eax
0x180031b38  test    eax, eax
0x180031b3a  jle     short loc_180031B45
0x180031b3c  movzx   ebx, ax
0x180031b3f  or      ebx, 80070000h
0x180031b45  mov     r9d, 31Ah
0x180031b4b  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031b52  xor     edx, edx
0x180031b54  mov     ecx, ebx
0x180031b56  call    Log_HREvent
0x180031b5b  mov     eax, ebx
0x180031b5d  jmp     loc_180031DF8
0x180031b62  mov     rcx, rdi; this
0x180031b65  call    ?SubmitServerSearch@ContactEnum@@IEAAJXZ; ContactEnum::SubmitServerSearch(void)
0x180031b6a  mov     esi, eax
0x180031b6c  test    eax, eax
0x180031b6e  jns     loc_180031CEE
0x180031b74  cmp     eax, 80004004h
0x180031b79  jz      loc_18003195E
0x180031b7f  mov     r9d, 31Ch
0x180031b85  jmp     loc_1800319D0
0x180031b8a  mov     rcx, [r12]
0x180031b8e  lea     r8, [rsp+2C0h+Context]
0x180031b93  mov     [rsp+2C0h+Context], r13
0x180031b98  mov     edx, 0Ah
0x180031b9d  mov     rax, [rcx]
0x180031ba0  mov     rax, [rax+60h]
0x180031ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ba9  mov     esi, eax
0x180031bab  test    eax, eax
0x180031bad  jns     short loc_180031BB7
0x180031baf  mov     r9d, 321h
0x180031bb5  jmp     short loc_180031BDC
0x180031bb7  mov     rcx, [rsp+2C0h+Context]
0x180031bbc  mov     r8, r14
0x180031bbf  mov     edx, 20h ; ' '
0x180031bc4  mov     rax, [rcx]
0x180031bc7  mov     rax, [rax+28h]
0x180031bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bd0  mov     esi, eax
0x180031bd2  test    eax, eax
0x180031bd4  jns     short loc_180031BF1
0x180031bd6  mov     r9d, 323h
0x180031bdc  mov     edx, ebx
0x180031bde  mov     ecx, eax
0x180031be0  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031be7  call    Log_HREvent
0x180031bec  jmp     loc_180031CD5
0x180031bf1  lea     rdx, [rdi+100h]
0x180031bf8  mov     rcx, rdi
0x180031bfb  call    ?GetEmailPhoneSearchResults@ContactEnum@@IEAAJPEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; ContactEnum::GetEmailPhoneSearchResults(utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)
0x180031c00  mov     esi, eax
0x180031c02  test    eax, eax
0x180031c04  jns     short loc_180031C0E
0x180031c06  mov     r9d, 324h
0x180031c0c  jmp     short loc_180031BDC
0x180031c0e  test    [rdi+0F0h], bl
0x180031c14  jz      loc_180031CE4
0x180031c1a  xor     edx, edx; Val
0x180031c1c  lea     rcx, [rsp+2C0h+var_250]; void *
0x180031c21  mov     r8d, 1F6h; Size
0x180031c27  call    memset_0
0x180031c2c  mov     r11, [rdi+0E8h]
0x180031c33  lea     r8, [rsp+2C0h+var_278]; unsigned __int64 *
0x180031c38  mov     rcx, r11; unsigned __int16 *
0x180031c3b  mov     [rsp+2C0h+var_278], r13
0x180031c40  mov     edx, 0FAh; unsigned __int64
0x180031c45  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031c4a  mov     esi, eax
0x180031c4c  test    eax, eax
0x180031c4e  jns     short loc_180031C58
0x180031c50  mov     r9d, 32Ch
0x180031c56  jmp     short loc_180031BDC
0x180031c58  mov     r8, [rsp+2C0h+var_278]
0x180031c5d  lea     r9, [rsp+2C0h+var_250]
0x180031c62  mov     rdx, r11
0x180031c65  mov     [rsp+2C0h+var_2A0], 0FBh
0x180031c6e  xor     ecx, ecx
0x180031c70  call    cs:__imp_?GetConvertedTextForMatching@@YAJKPEBG_KPEAG1@Z; GetConvertedTextForMatching(ulong,ushort const *,unsigned __int64,ushort *,unsigned __int64)
0x180031c76  mov     esi, eax
0x180031c78  test    eax, eax
0x180031c7a  jns     short loc_180031C87
0x180031c7c  mov     r9d, 333h
0x180031c82  jmp     loc_180031BDC
0x180031c87  cmp     [rsp+2C0h+var_250], r13w
0x180031c8d  jnz     short loc_180031CA3
0x180031c8f  mov     esi, 80070057h
0x180031c94  mov     r9d, 334h
0x180031c9a  mov     ecx, esi
0x180031c9c  xor     edx, edx
0x180031c9e  jmp     loc_180031BE0
0x180031ca3  lea     rcx, [rdi+140h]
0x180031caa  lea     rdx, [rsp+2C0h+var_250]
0x180031caf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180031cb4  test    al, al
0x180031cb6  jnz     short loc_180031CE4
0x180031cb8  mov     edi, 8007000Eh
0x180031cbd  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031cc4  mov     ecx, edi
0x180031cc6  mov     r9d, 336h
0x180031ccc  xor     edx, edx
0x180031cce  call    Log_HREvent
0x180031cd3  mov     esi, edi
0x180031cd5  lea     rcx, [rsp+2C0h+Context]
0x180031cda  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180031cdf  jmp     loc_18003195E
0x180031ce4  lea     rcx, [rsp+2C0h+Context]
0x180031ce9  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180031cee  mov     rax, [rdi]
0x180031cf1  mov     rcx, rdi
0x180031cf4  mov     rax, [rax+0A0h]
0x180031cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d00  test    al, al
0x180031d02  jnz     short loc_180031D35
0x180031d04  mov     rcx, rdi; this
0x180031d07  mov     [rdi+70h], r13d
0x180031d0b  call    ?PrefetchAndSortResults@ContactQueryEnumBase@@IEAAJXZ; ContactQueryEnumBase::PrefetchAndSortResults(void)
0x180031d10  mov     edi, eax
0x180031d12  test    eax, eax
0x180031d14  jns     loc_180031DF6
0x180031d1a  mov     r9d, 33Fh
0x180031d20  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180031d27  mov     edx, ebx
0x180031d29  mov     ecx, edi
0x180031d2b  call    Log_HREvent
0x180031d30  jmp     loc_180031AF5
0x180031d35  cmp     [r14], r13
0x180031d38  jz      loc_180031DF6
0x180031d3e  lea     rcx, [rsp+2C0h+fPending]
0x180031d43  mov     [rsp+2C0h+fPending], r13d
0x180031d48  call    cs:__imp_GetSortBy
0x180031d4e  mov     edi, eax
0x180031d50  test    eax, eax
0x180031d52  jns     short loc_180031D5C
  ... truncated ...
```
