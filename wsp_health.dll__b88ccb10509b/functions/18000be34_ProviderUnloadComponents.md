# ProviderUnloadComponents

- ea: `0x18000be34`
- end: `0x18000bf53`
- name: `ProviderUnloadComponents`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b2f0`
- `0x18000b300`

## callees

- `0x1800010f4`
- `0x18000119c`
- `0x18000b8e4`
- `0x18000b9ac`
- `0x18000b9d8`
- `0x18000be34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bebd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bebd`

## string_xrefs

- `0x18000be47`: `ProviderUnloadComponents`

## pseudocode

```c
__int64 __fastcall ProviderUnloadComponents(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  std::_Ref_count_base *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  HMODULE v8; // rcx
  const char *v10; // [rsp+58h] [rbp+18h] BYREF
  const char *v11; // [rsp+60h] [rbp+20h] BYREF

  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v10 = "ProviderUnloadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_180128D43,
      a3,
      a4,
      &v10);
  }
  v4 = qword_1801581B0;
  g_ptrDataStore = 0;
  qword_1801581B0 = 0;
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  std::unique_ptr<cxl::ExceptionManager>::reset(v4, 0);
  std::unique_ptr<cxl::TraceManager>::reset(v5, 0);
  v8 = g_storageWMIResource;
  if ( g_storageWMIResource )
  {
    FreeLibrary(g_storageWMIResource);
    g_storageWMIResource = 0;
  }
  if ( (unsigned int)dword_18014B6A8 > 2 )
  {
    LODWORD(v10) = 112;
    v11 = "ProviderUnloadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      (__int64)word_180128D0A,
      v6,
      v7,
      &v11);
  }
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v10 = "ProviderUnloadComponents";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      (__int64)byte_180128CDD,
      v6,
      v7,
      &v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000be34  mov     [rsp-8+arg_18], rdi
0x18000be39  push    rbp
0x18000be3a  mov     rbp, rsp
0x18000be3d  sub     rsp, 40h
0x18000be41  mov     eax, cs:dword_18014B6A8
0x18000be47  lea     rdi, aProviderunload; "ProviderUnloadComponents"
0x18000be4e  cmp     eax, 5
0x18000be51  jbe     short loc_18000BE7C
0x18000be53  lea     rax, [rbp+arg_0]
0x18000be57  mov     [rbp+arg_0], 64h ; 'd'
0x18000be5e  mov     [rsp+40h+var_18], rax
0x18000be63  lea     rdx, byte_180128D43
0x18000be6a  lea     rax, [rbp+arg_8]
0x18000be6e  mov     [rbp+arg_8], rdi
0x18000be72  mov     [rsp+40h+var_20], rax
0x18000be77  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000be7c  mov     rcx, cs:qword_1801581B0; this
0x18000be83  mov     cs:?g_ptrDataStore@@3V?$shared_ptr@VDataStore@ClusWmi@@@std@@A, 0; std::shared_ptr<ClusWmi::DataStore> g_ptrDataStore
0x18000be8e  mov     cs:qword_1801581B0, 0
0x18000be99  test    rcx, rcx
0x18000be9c  jz      short loc_18000BEA3
0x18000be9e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bea3  xor     edx, edx
0x18000bea5  call    ?reset@?$unique_ptr@VExceptionManager@cxl@@U?$default_delete@VExceptionManager@cxl@@@std@@@std@@QEAAXPEAVExceptionManager@cxl@@@Z; std::unique_ptr<cxl::ExceptionManager>::reset(cxl::ExceptionManager *)
0x18000beaa  xor     edx, edx
0x18000beac  call    ?reset@?$unique_ptr@VTraceManager@cxl@@U?$default_delete@VTraceManager@cxl@@@std@@@std@@QEAAXPEAVTraceManager@cxl@@@Z; std::unique_ptr<cxl::TraceManager>::reset(cxl::TraceManager *)
0x18000beb1  mov     rcx, cs:?g_storageWMIResource@@3PEAUHINSTANCE__@@EA; hLibModule
0x18000beb8  test    rcx, rcx
0x18000bebb  jz      short loc_18000BECE
0x18000bebd  call    cs:__imp_FreeLibrary
0x18000bec3  mov     cs:?g_storageWMIResource@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_storageWMIResource
0x18000bece  mov     eax, cs:dword_18014B6A8
0x18000bed4  cmp     eax, 2
0x18000bed7  jbe     short loc_18000BF12
0x18000bed9  lea     rax, [rbp+arg_0]
0x18000bedd  mov     [rbp+arg_0], 0
0x18000bee4  mov     [rsp+40h+var_10], rax
0x18000bee9  lea     rdx, word_180128D0A
0x18000bef0  lea     rax, [rbp+arg_8]
0x18000bef4  mov     dword ptr [rbp+arg_8], 70h ; 'p'
0x18000befb  mov     [rsp+40h+var_18], rax
0x18000bf00  lea     rax, [rbp+arg_10]
0x18000bf04  mov     [rsp+40h+var_20], rax
0x18000bf09  mov     [rbp+arg_10], rdi
0x18000bf0d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000bf12  mov     eax, cs:dword_18014B6A8
0x18000bf18  cmp     eax, 5
0x18000bf1b  jbe     short loc_18000BF46
0x18000bf1d  lea     rax, [rbp+arg_0]
0x18000bf21  mov     [rbp+arg_0], 71h ; 'q'
0x18000bf28  mov     [rsp+40h+var_18], rax
0x18000bf2d  lea     rdx, byte_180128CDD
0x18000bf34  lea     rax, [rbp+arg_8]
0x18000bf38  mov     [rbp+arg_8], rdi
0x18000bf3c  mov     [rsp+40h+var_20], rax
0x18000bf41  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000bf46  mov     rdi, [rsp+40h+arg_18]
0x18000bf4b  xor     eax, eax
0x18000bf4d  add     rsp, 40h
0x18000bf51  pop     rbp
0x18000bf52  retn
```
