# ProviderUnloadComponents

- ea: `0x18000c1c0`
- end: `0x18000c2e6`
- name: `ProviderUnloadComponents`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b670`
- `0x18000b680`

## callees

- `0x1800010f8`
- `0x1800011a0`
- `0x18000bc64`
- `0x18000bd2c`
- `0x18000bd58`
- `0x18000c1c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c249`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c249`

## string_xrefs

- `0x18000c1d3`: `ProviderUnloadComponents`

## pseudocode

```c
__int64 __fastcall ProviderUnloadComponents(int a1, __int64 a2, int a3, int a4)
{
  std::_Ref_count_base *v4; // rcx
  __int64 v5; // rcx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  int v10; // [rsp+50h] [rbp+10h] BYREF
  const char *v11; // [rsp+58h] [rbp+18h] BYREF
  const char *v12; // [rsp+60h] [rbp+20h] BYREF

  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v10 = 100;
    v11 = "ProviderUnloadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_18012AD4B,
      a3,
      a4,
      (__int64)&v11,
      (__int64)&v10);
  }
  v4 = qword_18015A1A8;
  g_ptrDataStore = 0;
  qword_18015A1A8 = 0;
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  std::unique_ptr<cxl::ExceptionManager>::reset(v4, 0);
  std::unique_ptr<cxl::TraceManager>::reset(v5, 0);
  v8 = (int)g_storageWMIResource;
  if ( g_storageWMIResource )
  {
    FreeLibrary(g_storageWMIResource);
    g_storageWMIResource = 0;
  }
  if ( (unsigned int)dword_18014D6A8 > 2 )
  {
    v10 = 0;
    LODWORD(v11) = 112;
    v12 = "ProviderUnloadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)word_18012AD12,
      v6,
      v7,
      (__int64)&v12,
      (__int64)&v11,
      (__int64)&v10);
  }
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v10 = 113;
    v11 = "ProviderUnloadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)byte_18012ACE5,
      v6,
      v7,
      (__int64)&v11,
      (__int64)&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c1c0  mov     [rsp-8+arg_18], rdi
0x18000c1c5  push    rbp
0x18000c1c6  mov     rbp, rsp
0x18000c1c9  sub     rsp, 40h
0x18000c1cd  mov     eax, cs:dword_18014D6A8
0x18000c1d3  lea     rdi, aProviderunload; "ProviderUnloadComponents"
0x18000c1da  cmp     eax, 5
0x18000c1dd  jbe     short loc_18000C208
0x18000c1df  lea     rax, [rbp+arg_0]
0x18000c1e3  mov     [rbp+arg_0], 64h ; 'd'
0x18000c1ea  mov     [rsp+40h+var_18], rax
0x18000c1ef  lea     rdx, byte_18012AD4B
0x18000c1f6  lea     rax, [rbp+arg_8]
0x18000c1fa  mov     [rbp+arg_8], rdi
0x18000c1fe  mov     [rsp+40h+var_20], rax
0x18000c203  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c208  mov     rcx, cs:qword_18015A1A8; this
0x18000c20f  mov     cs:?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A, 0; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000c21a  mov     cs:qword_18015A1A8, 0
0x18000c225  test    rcx, rcx
0x18000c228  jz      short loc_18000C22F
0x18000c22a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c22f  xor     edx, edx
0x18000c231  call    ?reset@?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAAXPEAVExceptionManager@cxl@@@Z; std::unique_ptr<cxl::ExceptionManager>::reset(cxl::ExceptionManager *)
0x18000c236  xor     edx, edx
0x18000c238  call    ?reset@?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAAXPEAVTraceManager@cxl@@@Z; std::unique_ptr<cxl::TraceManager>::reset(cxl::TraceManager *)
0x18000c23d  mov     rcx, cs:?g_storageWMIResource@@3PEAUHINSTANCE__@@EA; hLibModule
0x18000c244  test    rcx, rcx
0x18000c247  jz      short loc_18000C260
0x18000c249  call    cs:__imp_FreeLibrary
0x18000c250  nop     dword ptr [rax+rax+00h]
0x18000c255  mov     cs:?g_storageWMIResource@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_storageWMIResource
0x18000c260  mov     eax, cs:dword_18014D6A8
0x18000c266  cmp     eax, 2
0x18000c269  jbe     short loc_18000C2A4
0x18000c26b  lea     rax, [rbp+arg_0]
0x18000c26f  mov     [rbp+arg_0], 0
0x18000c276  mov     [rsp+40h+var_10], rax
0x18000c27b  lea     rdx, word_18012AD12
0x18000c282  lea     rax, [rbp+arg_8]
0x18000c286  mov     dword ptr [rbp+arg_8], 70h ; 'p'
0x18000c28d  mov     [rsp+40h+var_18], rax
0x18000c292  lea     rax, [rbp+arg_10]
0x18000c296  mov     [rsp+40h+var_20], rax
0x18000c29b  mov     [rbp+arg_10], rdi
0x18000c29f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c2a4  mov     eax, cs:dword_18014D6A8
0x18000c2aa  cmp     eax, 5
0x18000c2ad  jbe     short loc_18000C2D8
0x18000c2af  lea     rax, [rbp+arg_0]
0x18000c2b3  mov     [rbp+arg_0], 71h ; 'q'
0x18000c2ba  mov     [rsp+40h+var_18], rax
0x18000c2bf  lea     rdx, byte_18012ACE5
0x18000c2c6  lea     rax, [rbp+arg_8]
0x18000c2ca  mov     [rbp+arg_8], rdi
0x18000c2ce  mov     [rsp+40h+var_20], rax
0x18000c2d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c2d8  mov     rdi, [rsp+40h+arg_18]
0x18000c2dd  xor     eax, eax
0x18000c2df  add     rsp, 40h
0x18000c2e3  pop     rbp
0x18000c2e4  retn
```
