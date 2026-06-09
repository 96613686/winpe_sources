# Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks(Wsp::Facade::MaintenanceModeStruct &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &)

- ea: `0x180064dec`
- end: `0x180065403`
- name: `?FindWriteCacheDisks@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEAUMaintenanceModeStruct@23@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@@Z`
- size: `1559`
- prototype: `__int64 __fastcall(int, __int64, const char ***, int)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x180060f98`
- `0x180062e00`

## callees

- `0x1800010f4`
- `0x1800013bc`
- `0x180001620`
- `0x1800016b0`
- `0x180002ae0`
- `0x18000bf68`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000ea0c`
- `0x18000eebc`
- `0x180010ca4`
- `0x18001de28`
- `0x180034384`
- `0x18005a470`
- `0x18005e914`
- `0x18005ec50`
- `0x18005f098`
- `0x180064dec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065188`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064f18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064f1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064f18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064f1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064f05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064f05`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180064fad`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180064fad`

## string_xrefs

- `0x180065029`: `DeviceIoControl IOCTL_CBFLT_QUERY_PATH_INFO failed on disk {0}`
- `0x1800651a3`: `Failed to open device path {0}`
- `0x180064e20`: `Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks`
- `0x1800652fd`: `Cache disks not found`
- `0x180065304`: `Cache disk have been found.`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks(int a1, __int64 a2, const char ***a3, int a4)
{
  DWORD LastError; // edi
  __m128i si128; // xmm6
  const char *v8; // rbx
  wchar_t *v9; // rax
  struct cxl::TextWriter *v10; // r10
  const WCHAR *v11; // rax
  HANDLE FileW; // rdi
  struct cxl::TextWriter *v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 *v18; // rdx
  struct cxl::TraceManager *v19; // rax
  struct cxl::TextWriter *v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int16 *v28; // rdx
  struct cxl::TraceManager *v29; // rax
  const wchar_t *v30; // rdx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  char *v34; // rbx
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  unsigned int v38; // ebx
  __int64 v40; // [rsp+48h] [rbp-C0h] BYREF
  const char *v41; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+58h] [rbp-B0h] BYREF
  const char *v43; // [rsp+60h] [rbp-A8h] BYREF
  const char *v44; // [rsp+68h] [rbp-A0h] BYREF
  int OutBuffer; // [rsp+70h] [rbp-98h] BYREF
  DWORD BytesReturned; // [rsp+74h] [rbp-94h] BYREF
  _BYTE v47[32]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v48[2]; // [rsp+98h] [rbp-70h] BYREF
  __m128i v49; // [rsp+A8h] [rbp-60h]
  _OWORD v50[2]; // [rsp+B8h] [rbp-50h] BYREF
  void **v51; // [rsp+D8h] [rbp-30h] BYREF
  HANDLE hDevice; // [rsp+E0h] [rbp-28h]
  __int128 v53; // [rsp+E8h] [rbp-20h]
  __m128i v54; // [rsp+F8h] [rbp-10h]

  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    OutBuffer = 1878;
    v41 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)&byte_18012A217,
      (_DWORD)a3,
      a4,
      (__int64)&v41,
      (__int64)&OutBuffer);
  }
  LastError = 0;
  *(_OWORD *)v48 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v49 = si128;
  LOWORD(v48[0]) = 0;
  v8 = **a3;
  v41 = v8;
  while ( !v8[25] )
  {
    if ( *((_QWORD *)v8 + 10) )
    {
      v50[0] = 0;
      v50[1] = si128;
      LOWORD(v50[0]) = 0;
      cxl::StringWriter::StringWriter(v47, v50);
      v9 = (wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_1801579A0);
      cxl::TextWriter::Write<wchar_t,std::wstring,>(v10, v9);
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v50);
      FileW = CreateFileW(v11, 0xC0100000, 3u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v20 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v47, v48);
        cxl::TextWriter::Write<wchar_t,std::wstring,>(v20, (wchar_t *)L"Failed to open device path {0}");
        LODWORD(v40) = LastError;
        std::wstring::wstring(v47, v48);
        if ( !LastError )
        {
          if ( (unsigned int)dword_18014B6A8 > 5 )
          {
            v43 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
            LODWORD(v41) = v40;
            LODWORD(v42) = 1906;
            v44 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
              v21,
              (unsigned int)byte_18012A245,
              v22,
              v23,
              (__int64)&v44,
              (__int64)&v42,
              (__int64)&v41,
              (__int64)&v43);
          }
          goto LABEL_32;
        }
        if ( LastError == 122 )
        {
          if ( (unsigned int)dword_18014B6A8 > 3 )
          {
            v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
            v28 = &word_18012A286;
            goto LABEL_30;
          }
        }
        else if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
          v28 = (__int16 *)qword_18012A1D8;
LABEL_30:
          v43 = (const char *)v24;
          LODWORD(v41) = v40;
          LODWORD(v42) = 1906;
          v44 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v25,
            (_DWORD)v28,
            v26,
            v27,
            (__int64)&v44,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v43);
        }
        v29 = cxl::TraceManager::Instance();
        LODWORD(v41) = 1906;
        cxl::TextWriter::WriteLine<wchar_t,char [54],int,unsigned long,std::wstring>(
          (struct cxl::TraceManager *)((char *)v29 + 40),
          (__int64)&v40,
          (__int64)v48);
LABEL_32:
        std::wstring::_Tidy_deallocate(v47);
        goto LABEL_33;
      }
      GetCurrentProcess();
      GetCurrentProcess();
      v51 = &cxl::KernelObject::`vftable';
      hDevice = 0;
      cxl::KernelObject::Attach((cxl::KernelObject *)&v51, 0);
      v51 = &cxl::FileObject::`vftable';
      v53 = 0;
      v54 = si128;
      LOWORD(v53) = 0;
      cxl::KernelObject::Attach((cxl::KernelObject *)&v51, FileW);
      BytesReturned = 0;
      OutBuffer = 0;
      LastError = 0;
      if ( !DeviceIoControl(hDevice, 0x7914050u, 0, 0, &OutBuffer, 4u, &BytesReturned, 0) )
        LastError = GetLastError();
      if ( LastError )
      {
        v13 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v47, v48);
        cxl::TextWriter::Write<char,std::wstring,>(
          v13,
          "DeviceIoControl IOCTL_CBFLT_QUERY_PATH_INFO failed on disk {0}");
        LODWORD(v40) = LastError;
        std::wstring::wstring(v47, v48);
        if ( LastError == 122 )
        {
          if ( (unsigned int)dword_18014B6A8 > 3 )
          {
            v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
            v18 = qword_18012A158;
            goto LABEL_20;
          }
        }
        else if ( (unsigned int)dword_18014B6A8 > 2 )
        {
          v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
          v18 = (__int64 *)byte_18012A199;
LABEL_20:
          v43 = (const char *)v14;
          LODWORD(v41) = v40;
          LODWORD(v42) = 1925;
          v44 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            v15,
            (_DWORD)v18,
            v16,
            v17,
            (__int64)&v44,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v43);
        }
        v19 = cxl::TraceManager::Instance();
        LODWORD(v41) = 1925;
        cxl::TextWriter::WriteLine<wchar_t,char [54],int,unsigned long,std::wstring>(
          (struct cxl::TraceManager *)((char *)v19 + 40),
          (__int64)&v40,
          (__int64)v48);
        std::wstring::_Tidy_deallocate(v47);
        cxl::FileObject::~FileObject((cxl::FileObject *)&v51);
LABEL_33:
        std::wstring::_Tidy_deallocate(v50);
        break;
      }
      *((_BYTE *)v8 + 224) = (OutBuffer & 0x1000) != 0;
      if ( (OutBuffer & 0x1000) != 0 && !*(_BYTE *)(a2 + 154) )
        *(_BYTE *)(a2 + 154) = 1;
      cxl::FileObject::~FileObject((cxl::FileObject *)&v51);
      std::wstring::_Tidy_deallocate(v50);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(&v41);
    v8 = v41;
  }
  v30 = L"Cache disk have been found.";
  if ( !*(_BYTE *)(a2 + 154) )
    v30 = L"Cache disks not found";
  std::wstring::wstring(v47, v30);
  if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    v43 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v31,
      (unsigned int)byte_18012A08B,
      v32,
      v33,
      (__int64)&v43);
  }
  v34 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v34, v47);
  cxl::TextWriter::operator<<<cxl::ENDL>(v34);
  std::wstring::_Tidy_deallocate(v47);
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v41) = 1939;
    v43 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)byte_18012A0AB,
      v36,
      v37,
      (__int64)&v43,
      (__int64)&v41);
  }
  v38 = Wsp::MiSpaceAdapter::SmRCFromWinError(LastError);
  std::wstring::_Tidy_deallocate(v48);
  return v38;
}

```

## disassembly

```asm
0x180064dec  mov     rax, rsp
0x180064def  push    rbp
0x180064df0  push    rbx
0x180064df1  push    rsi
0x180064df2  push    rdi
0x180064df3  push    r12
0x180064df5  push    r14
0x180064df7  lea     rbp, [rax-58h]
0x180064dfb  sub     rsp, 128h
0x180064e02  movaps  xmmword ptr [rax-48h], xmm6
0x180064e06  mov     rax, cs:__security_cookie
0x180064e0d  xor     rax, rsp
0x180064e10  mov     [rbp+50h+var_50], rax
0x180064e14  mov     rbx, r8
0x180064e17  mov     r14, rdx
0x180064e1a  mov     eax, cs:dword_18014B6A8
0x180064e20  lea     r12, aWspFacadeStora_16; "Wsp::Facade::StorageHealthFacade::FindW"...
0x180064e27  cmp     eax, 5
0x180064e2a  jbe     short loc_180064E59
0x180064e2c  mov     [rsp+150h+OutBuffer], 756h
0x180064e34  mov     [rsp+150h+var_108], r12
0x180064e39  lea     rax, [rsp+150h+OutBuffer]
0x180064e3e  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x180064e43  lea     rax, [rsp+150h+var_108]
0x180064e48  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180064e4d  lea     rdx, byte_18012A217
0x180064e54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180064e59  xor     edi, edi
0x180064e5b  xorps   xmm0, xmm0
0x180064e5e  movups  xmmword ptr [rbp+50h+var_C0], xmm0
0x180064e62  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180064e6a  movdqu  [rbp+50h+var_B0], xmm6
0x180064e6f  xor     eax, eax
0x180064e71  mov     word ptr [rbp+50h+var_C0], ax
0x180064e75  mov     rbx, [rbx]
0x180064e78  mov     rbx, [rbx]
0x180064e7b  mov     [rsp+150h+var_108], rbx
0x180064e80  cmp     byte ptr [rbx+19h], 0
0x180064e84  jnz     loc_1800652FD
0x180064e8a  cmp     qword ptr [rbx+50h], 0
0x180064e8f  jz      loc_180065002
0x180064e95  xorps   xmm0, xmm0
0x180064e98  movups  [rbp+50h+var_A0], xmm0
0x180064e9c  movdqu  [rbp+50h+var_90], xmm6
0x180064ea1  xor     eax, eax
0x180064ea3  mov     word ptr [rbp+50h+var_A0], ax
0x180064ea7  lea     rdx, [rbp+50h+var_A0]
0x180064eab  lea     rcx, [rsp+70h]
0x180064eb0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180064eb5  mov     r10, rax
0x180064eb8  lea     rcx, qword_1801579A0
0x180064ebf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180064ec4  mov     rdx, rax; wchar_t *
0x180064ec7  lea     r8, [rbx+40h]
0x180064ecb  mov     rcx, r10; struct cxl::TextWriter *
0x180064ece  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x180064ed3  nop
0x180064ed4  lea     rcx, [rbp+50h+var_A0]
0x180064ed8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180064edd  mov     rcx, rax; lpFileName
0x180064ee0  mov     [rsp+150h+hTemplateFile], 0; hTemplateFile
0x180064ee9  mov     [rsp+150h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180064ef1  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x180064ef9  xor     r9d, r9d; lpSecurityAttributes
0x180064efc  mov     edx, 0C0100000h; dwDesiredAccess
0x180064f01  lea     r8d, [r9+3]; dwShareMode
0x180064f05  call    cs:__imp_CreateFileW
0x180064f0b  mov     rdi, rax
0x180064f0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064f12  jz      loc_180065188
0x180064f18  call    cs:__imp_GetCurrentProcess
0x180064f1e  call    cs:__imp_GetCurrentProcess
0x180064f24  lea     rax, ??_7KernelObject@cxl@@6B@; const cxl::KernelObject::`vftable'
0x180064f2b  mov     [rbp+50h+var_80], rax
0x180064f2f  mov     [rbp+50h+hDevice], 0
0x180064f37  xor     edx, edx; void *
0x180064f39  lea     rcx, [rbp+50h+var_80]; this
0x180064f3d  call    ?Attach@KernelObject@cxl@@QEAAXPEAX@Z; cxl::KernelObject::Attach(void *)
0x180064f42  lea     rax, ??_7FileObject@cxl@@6B@; const cxl::FileObject::`vftable'
0x180064f49  mov     [rbp+50h+var_80], rax
0x180064f4d  xorps   xmm0, xmm0
0x180064f50  movups  [rbp+50h+var_70], xmm0
0x180064f54  movdqu  [rbp+50h+var_60], xmm6
0x180064f59  xor     eax, eax
0x180064f5b  mov     word ptr [rbp+50h+var_70], ax
0x180064f5f  mov     rdx, rdi; void *
0x180064f62  lea     rcx, [rbp+50h+var_80]; this
0x180064f66  call    ?Attach@KernelObject@cxl@@QEAAXPEAX@Z; cxl::KernelObject::Attach(void *)
0x180064f6b  mov     [rsp+150h+BytesReturned], 0
0x180064f73  mov     [rsp+150h+OutBuffer], 0
0x180064f7b  xor     edi, edi
0x180064f7d  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x180064f82  lea     rax, [rsp+150h+BytesReturned]
0x180064f87  mov     [rsp+150h+hTemplateFile], rax; lpBytesReturned
0x180064f8c  mov     [rsp+150h+dwFlagsAndAttributes], 4; nOutBufferSize
0x180064f94  lea     rax, [rsp+150h+OutBuffer]
0x180064f99  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; lpOutBuffer
0x180064f9e  xor     r9d, r9d; nInBufferSize
0x180064fa1  xor     r8d, r8d; lpInBuffer
0x180064fa4  mov     edx, 7914050h; dwIoControlCode
0x180064fa9  mov     rcx, [rbp+50h+hDevice]; hDevice
0x180064fad  call    cs:__imp_DeviceIoControl
0x180064fb3  test    eax, eax
0x180064fb5  jnz     short loc_180064FBF
0x180064fb7  call    cs:__imp_GetLastError
0x180064fbd  mov     edi, eax
0x180064fbf  test    edi, edi
0x180064fc1  jnz     short loc_180065016
0x180064fc3  test    [rsp+150h+OutBuffer], 1000h
0x180064fcb  setnz   al
0x180064fce  mov     [rbx+0E0h], al
0x180064fd4  test    [rsp+150h+OutBuffer], 1000h
0x180064fdc  jz      short loc_180064FEF
0x180064fde  cmp     [r14+9Ah], dil
0x180064fe5  jnz     short loc_180064FEF
0x180064fe7  mov     byte ptr [r14+9Ah], 1
0x180064fef  lea     rcx, [rbp+50h+var_80]; this
0x180064ff3  call    ??1FileObject@cxl@@UEAA@XZ; cxl::FileObject::~FileObject(void)
0x180064ff8  nop
0x180064ff9  lea     rcx, [rbp+50h+var_A0]
0x180064ffd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065002  lea     rcx, [rsp+150h+var_108]
0x180065007  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(void)
0x18006500c  mov     rbx, [rsp+150h+var_108]
0x180065011  jmp     loc_180064E80
0x180065016  lea     rdx, [rbp+50h+var_C0]
0x18006501a  lea     rcx, [rsp+70h]
0x18006501f  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180065024  nop
0x180065025  lea     r8, [rbx+40h]
0x180065029  lea     rdx, aDeviceiocontro; "DeviceIoControl IOCTL_CBFLT_QUERY_PATH_"...
0x180065030  mov     rcx, rax
0x180065033  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x180065038  nop
0x180065039  mov     dword ptr [rsp+150h+var_110], edi
0x18006503d  lea     rdx, [rbp+50h+var_C0]
0x180065041  lea     rcx, [rsp+70h]
0x180065046  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006504b  nop
0x18006504c  mov     eax, dword ptr [rsp+150h+var_110]
0x180065050  test    eax, eax
0x180065052  jnz     short loc_1800650C0
0x180065054  mov     eax, cs:dword_18014B6A8
0x18006505a  cmp     eax, 5
0x18006505d  jbe     loc_18006516F
0x180065063  lea     rcx, [rsp+70h]
0x180065068  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006506d  mov     qword ptr [rsp+150h+var_F0], rax
0x180065072  mov     eax, dword ptr [rsp+150h+var_110]
0x180065076  mov     dword ptr [rsp+150h+var_100], eax
0x18006507a  mov     dword ptr [rsp+150h+var_108], 785h
0x180065082  mov     [rsp+150h+var_F8], r12
0x180065087  lea     rax, [rsp+150h+var_F0]
0x18006508c  mov     [rsp+150h+lpOverlapped], rax
0x180065091  lea     rax, [rsp+150h+var_100]
0x180065096  mov     [rsp+150h+hTemplateFile], rax
0x18006509b  lea     rax, [rsp+150h+var_108]
0x1800650a0  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x1800650a5  lea     rax, [rsp+150h+var_F8]
0x1800650aa  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x1800650af  lea     rdx, byte_18012A117
0x1800650b6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800650bb  jmp     loc_18006516F
0x1800650c0  cmp     eax, 7Ah ; 'z'
0x1800650c3  mov     eax, cs:dword_18014B6A8
0x1800650c9  jnz     short loc_1800650E3
0x1800650cb  cmp     eax, 3
0x1800650ce  jbe     short loc_180065140
0x1800650d0  lea     rcx, [rsp+70h]
0x1800650d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800650da  lea     rdx, qword_18012A158
0x1800650e1  jmp     short loc_1800650F9
0x1800650e3  cmp     eax, 2
0x1800650e6  jbe     short loc_180065140
0x1800650e8  lea     rcx, [rsp+70h]
0x1800650ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800650f2  lea     rdx, byte_18012A199
0x1800650f9  mov     [rsp+150h+var_F8], rax
0x1800650fe  mov     eax, dword ptr [rsp+150h+var_110]
0x180065102  mov     dword ptr [rsp+150h+var_108], eax
0x180065106  lea     rax, [rsp+150h+var_F8]
0x18006510b  mov     [rsp+150h+lpOverlapped], rax
0x180065110  lea     rax, [rsp+150h+var_108]
0x180065115  mov     [rsp+150h+hTemplateFile], rax
0x18006511a  lea     rax, [rsp+150h+var_100]
0x18006511f  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x180065124  lea     rax, [rsp+150h+var_F0]
0x180065129  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x18006512e  mov     dword ptr [rsp+150h+var_100], 785h
0x180065136  mov     qword ptr [rsp+150h+var_F0], r12
0x18006513b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180065140  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180065145  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180065149  lea     rax, [rbp+50h+var_C0]
0x18006514d  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax; __int64
0x180065152  lea     rax, [rsp+150h+var_110]
0x180065157  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; __int64
0x18006515c  mov     dword ptr [rsp+150h+var_108], 785h
0x180065164  lea     r9, [rsp+150h+var_108]
0x180065169  call    ??$WriteLine@_W$$BY0DG@DHKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DG@$$CBDAEBHAEBKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,char [54],int,ulong,std::wstring>(wchar_t const *,char const (&)[54],int const &,ulong const &,std::wstring const &)
0x18006516e  nop
0x18006516f  lea     rcx, [rsp+70h]
0x180065174  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065179  nop
0x18006517a  lea     rcx, [rbp+50h+var_80]; this
0x18006517e  call    ??1FileObject@cxl@@UEAA@XZ; cxl::FileObject::~FileObject(void)
0x180065183  jmp     loc_1800652F4
0x180065188  call    cs:__imp_GetLastError
0x18006518e  mov     edi, eax
0x180065190  lea     rdx, [rbp+50h+var_C0]
0x180065194  lea     rcx, [rsp+70h]
0x180065199  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006519e  nop
0x18006519f  lea     r8, [rbp+50h+var_A0]
0x1800651a3  lea     rdx, aFailedToOpenDe; "Failed to open device path {0}"
0x1800651aa  mov     rcx, rax; struct cxl::TextWriter *
0x1800651ad  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x1800651b2  nop
0x1800651b3  mov     dword ptr [rsp+150h+var_110], edi
0x1800651b7  lea     rdx, [rbp+50h+var_C0]
0x1800651bb  lea     rcx, [rsp+70h]
0x1800651c0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800651c5  nop
0x1800651c6  mov     eax, dword ptr [rsp+150h+var_110]
0x1800651ca  test    eax, eax
0x1800651cc  jnz     short loc_18006523A
0x1800651ce  mov     eax, cs:dword_18014B6A8
0x1800651d4  cmp     eax, 5
0x1800651d7  jbe     loc_1800652E9
0x1800651dd  lea     rcx, [rsp+70h]
0x1800651e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800651e7  mov     [rsp+150h+var_F8], rax
0x1800651ec  mov     eax, dword ptr [rsp+150h+var_110]
0x1800651f0  mov     dword ptr [rsp+150h+var_108], eax
0x1800651f4  mov     dword ptr [rsp+150h+var_100], 772h
0x1800651fc  mov     qword ptr [rsp+150h+var_F0], r12
0x180065201  lea     rax, [rsp+150h+var_F8]
0x180065206  mov     [rsp+150h+lpOverlapped], rax
0x18006520b  lea     rax, [rsp+150h+var_108]
0x180065210  mov     [rsp+150h+hTemplateFile], rax
0x180065215  lea     rax, [rsp+150h+var_100]
0x18006521a  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x18006521f  lea     rax, [rsp+150h+var_F0]
0x180065224  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180065229  lea     rdx, byte_18012A245
0x180065230  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180065235  jmp     loc_1800652E9
0x18006523a  cmp     eax, 7Ah ; 'z'
0x18006523d  mov     eax, cs:dword_18014B6A8
0x180065243  jnz     short loc_18006525D
0x180065245  cmp     eax, 3
0x180065248  jbe     short loc_1800652BA
0x18006524a  lea     rcx, [rsp+70h]
0x18006524f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180065254  lea     rdx, word_18012A286
0x18006525b  jmp     short loc_180065273
0x18006525d  cmp     eax, 2
0x180065260  jbe     short loc_1800652BA
0x180065262  lea     rcx, [rsp+70h]
0x180065267  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006526c  lea     rdx, qword_18012A1D8
0x180065273  mov     [rsp+150h+var_F8], rax
0x180065278  mov     eax, dword ptr [rsp+150h+var_110]
0x18006527c  mov     dword ptr [rsp+150h+var_108], eax
0x180065280  lea     rax, [rsp+150h+var_F8]
0x180065285  mov     [rsp+150h+lpOverlapped], rax
0x18006528a  lea     rax, [rsp+150h+var_108]
0x18006528f  mov     [rsp+150h+hTemplateFile], rax
0x180065294  lea     rax, [rsp+150h+var_100]
0x180065299  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x18006529e  lea     rax, [rsp+150h+var_F0]
0x1800652a3  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x1800652a8  mov     dword ptr [rsp+150h+var_100], 772h
0x1800652b0  mov     qword ptr [rsp+150h+var_F0], r12
0x1800652b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800652ba  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800652bf  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x1800652c3  lea     rax, [rbp+50h+var_C0]
0x1800652c7  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax; __int64
0x1800652cc  lea     rax, [rsp+150h+var_110]
0x1800652d1  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; __int64
0x1800652d6  mov     dword ptr [rsp+150h+var_108], 772h
0x1800652de  lea     r9, [rsp+150h+var_108]
0x1800652e3  call    ??$WriteLine@_W$$BY0DG@DHKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DG@$$CBDAEBHAEBKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,char [54],int,ulong,std::wstring>(wchar_t const *,char const (&)[54],int const &,ulong const &,std::wstring const &)
0x1800652e8  nop
0x1800652e9  lea     rcx, [rsp+70h]
0x1800652ee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800652f3  nop
0x1800652f4  lea     rcx, [rbp+50h+var_A0]
0x1800652f8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800652fd  lea     rax, aCacheDisksNotF; "Cache disks not found"
0x180065304  lea     rdx, aCacheDiskHaveB; "Cache disk have been found."
0x18006530b  cmp     byte ptr [r14+9Ah], 0
0x180065313  cmovz   rdx, rax
0x180065317  lea     rcx, [rsp+70h]
0x18006531c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180065321  nop
0x180065322  mov     eax, cs:dword_18014B6A8
0x180065328  cmp     eax, 5
0x18006532b  jbe     short loc_180065367
  ... truncated ...
```
