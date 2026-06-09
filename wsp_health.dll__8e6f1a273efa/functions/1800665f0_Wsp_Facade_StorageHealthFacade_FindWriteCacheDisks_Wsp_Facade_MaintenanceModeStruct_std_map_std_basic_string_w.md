# Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks(Wsp::Facade::MaintenanceModeStruct &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &)

- ea: `0x1800665f0`
- end: `0x180066c2c`
- name: `?FindWriteCacheDisks@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEAUMaintenanceModeStruct@23@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@@Z`
- size: `1596`
- prototype: `__int64 __fastcall(int, __int64, const char ***, int)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x180062798`
- `0x180064604`

## callees

- `0x1800010f8`
- `0x1800013d0`
- `0x18000163c`
- `0x1800016d0`
- `0x180002b50`
- `0x18000c2f8`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000ee9c`
- `0x18000f34c`
- `0x180011184`
- `0x18001e9e0`
- `0x1800354c8`
- `0x18005bbe8`
- `0x1800600d8`
- `0x180060414`
- `0x180060868`
- `0x1800665f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800667d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800669aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800667d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800669aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006672e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006672e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066709`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180066709`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800667c3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800667c3`

## string_xrefs

- `0x18006684b`: `DeviceIoControl IOCTL_CBFLT_QUERY_PATH_INFO failed on disk {0}`
- `0x1800669cb`: `Failed to open device path {0}`
- `0x180066624`: `Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks`
- `0x180066b25`: `Cache disks not found`
- `0x180066b2c`: `Cache disk have been found.`

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
  __int64 *v28; // rdx
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

  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    OutBuffer = 1878;
    v41 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)qword_18012C260,
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
      v9 = (wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180159AA0);
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
          if ( (unsigned int)dword_18014D6A8 > 5 )
          {
            v43 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
            LODWORD(v41) = v40;
            LODWORD(v42) = 1906;
            v44 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
              v21,
              (unsigned int)&word_18012C28E,
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
          if ( (unsigned int)dword_18014D6A8 > 3 )
          {
            v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
            v28 = qword_18012C1E0;
            goto LABEL_30;
          }
        }
        else if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
          v28 = (__int64 *)byte_18012C221;
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
          if ( (unsigned int)dword_18014D6A8 > 3 )
          {
            v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
            v18 = qword_18012C160;
            goto LABEL_20;
          }
        }
        else if ( (unsigned int)dword_18014D6A8 > 2 )
        {
          v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
          v18 = (__int64 *)byte_18012C1A1;
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
  if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    v43 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v31,
      (unsigned int)byte_18012C093,
      v32,
      v33,
      (__int64)&v43);
  }
  v34 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v34, v47);
  cxl::TextWriter::operator<<<cxl::ENDL>(v34);
  std::wstring::_Tidy_deallocate(v47);
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v41) = 1939;
    v43 = "Wsp::Facade::StorageHealthFacade::FindWriteCacheDisks";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)byte_18012C0B3,
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
0x1800665f0  mov     rax, rsp
0x1800665f3  push    rbp
0x1800665f4  push    rbx
0x1800665f5  push    rsi
0x1800665f6  push    rdi
0x1800665f7  push    r12
0x1800665f9  push    r14
0x1800665fb  lea     rbp, [rax-58h]
0x1800665ff  sub     rsp, 128h
0x180066606  movaps  xmmword ptr [rax-48h], xmm6
0x18006660a  mov     rax, cs:__security_cookie
0x180066611  xor     rax, rsp
0x180066614  mov     [rbp+50h+var_50], rax
0x180066618  mov     rbx, r8
0x18006661b  mov     r14, rdx
0x18006661e  mov     eax, cs:dword_18014D6A8
0x180066624  lea     r12, aWspFacadeStora_16; "Wsp::Facade::StorageHealthFacade::FindW"...
0x18006662b  cmp     eax, 5
0x18006662e  jbe     short loc_18006665D
0x180066630  mov     [rsp+150h+OutBuffer], 756h
0x180066638  mov     [rsp+150h+var_108], r12
0x18006663d  lea     rax, [rsp+150h+OutBuffer]
0x180066642  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x180066647  lea     rax, [rsp+150h+var_108]
0x18006664c  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180066651  lea     rdx, qword_18012C260
0x180066658  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006665d  xor     edi, edi
0x18006665f  xorps   xmm0, xmm0
0x180066662  movups  xmmword ptr [rbp+50h+var_C0], xmm0
0x180066666  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18006666e  movdqu  [rbp+50h+var_B0], xmm6
0x180066673  xor     eax, eax
0x180066675  mov     word ptr [rbp+50h+var_C0], ax
0x180066679  mov     rbx, [rbx]
0x18006667c  mov     rbx, [rbx]
0x18006667f  mov     [rsp+150h+var_108], rbx
0x180066684  cmp     byte ptr [rbx+19h], 0
0x180066688  jnz     loc_180066B25
0x18006668e  cmp     qword ptr [rbx+50h], 0
0x180066693  jz      loc_180066824
0x180066699  xorps   xmm0, xmm0
0x18006669c  movups  [rbp+50h+var_A0], xmm0
0x1800666a0  movdqu  [rbp+50h+var_90], xmm6
0x1800666a5  xor     eax, eax
0x1800666a7  mov     word ptr [rbp+50h+var_A0], ax
0x1800666ab  lea     rdx, [rbp+50h+var_A0]
0x1800666af  lea     rcx, [rsp+70h]
0x1800666b4  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800666b9  mov     r10, rax
0x1800666bc  lea     rcx, qword_180159AA0
0x1800666c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800666c8  mov     rdx, rax; wchar_t *
0x1800666cb  lea     r8, [rbx+40h]
0x1800666cf  mov     rcx, r10; struct cxl::TextWriter *
0x1800666d2  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x1800666d7  nop
0x1800666d8  lea     rcx, [rbp+50h+var_A0]
0x1800666dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800666e1  mov     rcx, rax; lpFileName
0x1800666e4  mov     [rsp+150h+hTemplateFile], 0; hTemplateFile
0x1800666ed  mov     [rsp+150h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800666f5  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x1800666fd  xor     r9d, r9d; lpSecurityAttributes
0x180066700  mov     edx, 0C0100000h; dwDesiredAccess
0x180066705  lea     r8d, [r9+3]; dwShareMode
0x180066709  call    cs:__imp_CreateFileW
0x180066710  nop     dword ptr [rax+rax+00h]
0x180066715  mov     rdi, rax
0x180066718  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006671c  jz      loc_1800669AA
0x180066722  call    cs:__imp_GetCurrentProcess
0x180066729  nop     dword ptr [rax+rax+00h]
0x18006672e  call    cs:__imp_GetCurrentProcess
0x180066735  nop     dword ptr [rax+rax+00h]
0x18006673a  lea     rax, ??_7KernelObject@cxl@@6B@; const cxl::KernelObject::`vftable'
0x180066741  mov     [rbp+50h+var_80], rax
0x180066745  mov     [rbp+50h+hDevice], 0
0x18006674d  xor     edx, edx; void *
0x18006674f  lea     rcx, [rbp+50h+var_80]; this
0x180066753  call    ?Attach@KernelObject@cxl@@QEAAXPEAX@Z; cxl::KernelObject::Attach(void *)
0x180066758  lea     rax, ??_7FileObject@cxl@@6B@; const cxl::FileObject::`vftable'
0x18006675f  mov     [rbp+50h+var_80], rax
0x180066763  xorps   xmm0, xmm0
0x180066766  movups  [rbp+50h+var_70], xmm0
0x18006676a  movdqu  [rbp+50h+var_60], xmm6
0x18006676f  xor     eax, eax
0x180066771  mov     word ptr [rbp+50h+var_70], ax
0x180066775  mov     rdx, rdi; void *
0x180066778  lea     rcx, [rbp+50h+var_80]; this
0x18006677c  call    ?Attach@KernelObject@cxl@@QEAAXPEAX@Z; cxl::KernelObject::Attach(void *)
0x180066781  mov     [rsp+150h+BytesReturned], 0
0x180066789  mov     [rsp+150h+OutBuffer], 0
0x180066791  xor     edi, edi
0x180066793  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x180066798  lea     rax, [rsp+150h+BytesReturned]
0x18006679d  mov     [rsp+150h+hTemplateFile], rax; lpBytesReturned
0x1800667a2  mov     [rsp+150h+dwFlagsAndAttributes], 4; nOutBufferSize
0x1800667aa  lea     rax, [rsp+150h+OutBuffer]
0x1800667af  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; lpOutBuffer
0x1800667b4  xor     r9d, r9d; nInBufferSize
0x1800667b7  xor     r8d, r8d; lpInBuffer
0x1800667ba  mov     edx, 7914050h; dwIoControlCode
0x1800667bf  mov     rcx, [rbp+50h+hDevice]; hDevice
0x1800667c3  call    cs:__imp_DeviceIoControl
0x1800667ca  nop     dword ptr [rax+rax+00h]
0x1800667cf  test    eax, eax
0x1800667d1  jnz     short loc_1800667E1
0x1800667d3  call    cs:__imp_GetLastError
0x1800667da  nop     dword ptr [rax+rax+00h]
0x1800667df  mov     edi, eax
0x1800667e1  test    edi, edi
0x1800667e3  jnz     short loc_180066838
0x1800667e5  test    [rsp+150h+OutBuffer], 1000h
0x1800667ed  setnz   al
0x1800667f0  mov     [rbx+0E0h], al
0x1800667f6  test    [rsp+150h+OutBuffer], 1000h
0x1800667fe  jz      short loc_180066811
0x180066800  cmp     [r14+9Ah], dil
0x180066807  jnz     short loc_180066811
0x180066809  mov     byte ptr [r14+9Ah], 1
0x180066811  lea     rcx, [rbp+50h+var_80]; this
0x180066815  call    ??1FileObject@cxl@@UEAA@XZ; cxl::FileObject::~FileObject(void)
0x18006681a  nop
0x18006681b  lea     rcx, [rbp+50h+var_A0]
0x18006681f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066824  lea     rcx, [rsp+150h+var_108]
0x180066829  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(void)
0x18006682e  mov     rbx, [rsp+150h+var_108]
0x180066833  jmp     loc_180066684
0x180066838  lea     rdx, [rbp+50h+var_C0]
0x18006683c  lea     rcx, [rsp+70h]
0x180066841  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180066846  nop
0x180066847  lea     r8, [rbx+40h]
0x18006684b  lea     rdx, aDeviceiocontro; "DeviceIoControl IOCTL_CBFLT_QUERY_PATH_"...
0x180066852  mov     rcx, rax
0x180066855  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18006685a  nop
0x18006685b  mov     dword ptr [rsp+150h+var_110], edi
0x18006685f  lea     rdx, [rbp+50h+var_C0]
0x180066863  lea     rcx, [rsp+70h]
0x180066868  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006686d  nop
0x18006686e  mov     eax, dword ptr [rsp+150h+var_110]
0x180066872  test    eax, eax
0x180066874  jnz     short loc_1800668E2
0x180066876  mov     eax, cs:dword_18014D6A8
0x18006687c  cmp     eax, 5
0x18006687f  jbe     loc_180066991
0x180066885  lea     rcx, [rsp+70h]
0x18006688a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006688f  mov     qword ptr [rsp+150h+var_F0], rax
0x180066894  mov     eax, dword ptr [rsp+150h+var_110]
0x180066898  mov     dword ptr [rsp+150h+var_100], eax
0x18006689c  mov     dword ptr [rsp+150h+var_108], 785h
0x1800668a4  mov     [rsp+150h+var_F8], r12
0x1800668a9  lea     rax, [rsp+150h+var_F0]
0x1800668ae  mov     [rsp+150h+lpOverlapped], rax
0x1800668b3  lea     rax, [rsp+150h+var_100]
0x1800668b8  mov     [rsp+150h+hTemplateFile], rax
0x1800668bd  lea     rax, [rsp+150h+var_108]
0x1800668c2  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x1800668c7  lea     rax, [rsp+150h+var_F8]
0x1800668cc  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x1800668d1  lea     rdx, byte_18012C11F
0x1800668d8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800668dd  jmp     loc_180066991
0x1800668e2  cmp     eax, 7Ah ; 'z'
0x1800668e5  mov     eax, cs:dword_18014D6A8
0x1800668eb  jnz     short loc_180066905
0x1800668ed  cmp     eax, 3
0x1800668f0  jbe     short loc_180066962
0x1800668f2  lea     rcx, [rsp+70h]
0x1800668f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800668fc  lea     rdx, qword_18012C160
0x180066903  jmp     short loc_18006691B
0x180066905  cmp     eax, 2
0x180066908  jbe     short loc_180066962
0x18006690a  lea     rcx, [rsp+70h]
0x18006690f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180066914  lea     rdx, byte_18012C1A1
0x18006691b  mov     [rsp+150h+var_F8], rax
0x180066920  mov     eax, dword ptr [rsp+150h+var_110]
0x180066924  mov     dword ptr [rsp+150h+var_108], eax
0x180066928  lea     rax, [rsp+150h+var_F8]
0x18006692d  mov     [rsp+150h+lpOverlapped], rax
0x180066932  lea     rax, [rsp+150h+var_108]
0x180066937  mov     [rsp+150h+hTemplateFile], rax
0x18006693c  lea     rax, [rsp+150h+var_100]
0x180066941  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x180066946  lea     rax, [rsp+150h+var_F0]
0x18006694b  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180066950  mov     dword ptr [rsp+150h+var_100], 785h
0x180066958  mov     qword ptr [rsp+150h+var_F0], r12
0x18006695d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180066962  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180066967  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006696b  lea     rax, [rbp+50h+var_C0]
0x18006696f  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax; __int64
0x180066974  lea     rax, [rsp+150h+var_110]
0x180066979  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; __int64
0x18006697e  mov     dword ptr [rsp+150h+var_108], 785h
0x180066986  lea     r9, [rsp+150h+var_108]
0x18006698b  call    ??$WriteLine@_W$$BY0DG@DHKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DG@$$CBDAEBHAEBKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,char [54],int,ulong,std::wstring>(wchar_t const *,char const (&)[54],int const &,ulong const &,std::wstring const &)
0x180066990  nop
0x180066991  lea     rcx, [rsp+70h]
0x180066996  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006699b  nop
0x18006699c  lea     rcx, [rbp+50h+var_80]; this
0x1800669a0  call    ??1FileObject@cxl@@UEAA@XZ; cxl::FileObject::~FileObject(void)
0x1800669a5  jmp     loc_180066B1C
0x1800669aa  call    cs:__imp_GetLastError
0x1800669b1  nop     dword ptr [rax+rax+00h]
0x1800669b6  mov     edi, eax
0x1800669b8  lea     rdx, [rbp+50h+var_C0]
0x1800669bc  lea     rcx, [rsp+70h]
0x1800669c1  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800669c6  nop
0x1800669c7  lea     r8, [rbp+50h+var_A0]
0x1800669cb  lea     rdx, aFailedToOpenDe; "Failed to open device path {0}"
0x1800669d2  mov     rcx, rax; struct cxl::TextWriter *
0x1800669d5  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x1800669da  nop
0x1800669db  mov     dword ptr [rsp+150h+var_110], edi
0x1800669df  lea     rdx, [rbp+50h+var_C0]
0x1800669e3  lea     rcx, [rsp+70h]
0x1800669e8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800669ed  nop
0x1800669ee  mov     eax, dword ptr [rsp+150h+var_110]
0x1800669f2  test    eax, eax
0x1800669f4  jnz     short loc_180066A62
0x1800669f6  mov     eax, cs:dword_18014D6A8
0x1800669fc  cmp     eax, 5
0x1800669ff  jbe     loc_180066B11
0x180066a05  lea     rcx, [rsp+70h]
0x180066a0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180066a0f  mov     [rsp+150h+var_F8], rax
0x180066a14  mov     eax, dword ptr [rsp+150h+var_110]
0x180066a18  mov     dword ptr [rsp+150h+var_108], eax
0x180066a1c  mov     dword ptr [rsp+150h+var_100], 772h
0x180066a24  mov     qword ptr [rsp+150h+var_F0], r12
0x180066a29  lea     rax, [rsp+150h+var_F8]
0x180066a2e  mov     [rsp+150h+lpOverlapped], rax
0x180066a33  lea     rax, [rsp+150h+var_108]
0x180066a38  mov     [rsp+150h+hTemplateFile], rax
0x180066a3d  lea     rax, [rsp+150h+var_100]
0x180066a42  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x180066a47  lea     rax, [rsp+150h+var_F0]
0x180066a4c  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180066a51  lea     rdx, word_18012C28E
0x180066a58  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180066a5d  jmp     loc_180066B11
0x180066a62  cmp     eax, 7Ah ; 'z'
0x180066a65  mov     eax, cs:dword_18014D6A8
0x180066a6b  jnz     short loc_180066A85
0x180066a6d  cmp     eax, 3
0x180066a70  jbe     short loc_180066AE2
0x180066a72  lea     rcx, [rsp+70h]
0x180066a77  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180066a7c  lea     rdx, qword_18012C1E0
0x180066a83  jmp     short loc_180066A9B
0x180066a85  cmp     eax, 2
0x180066a88  jbe     short loc_180066AE2
0x180066a8a  lea     rcx, [rsp+70h]
0x180066a8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180066a94  lea     rdx, byte_18012C221
0x180066a9b  mov     [rsp+150h+var_F8], rax
0x180066aa0  mov     eax, dword ptr [rsp+150h+var_110]
0x180066aa4  mov     dword ptr [rsp+150h+var_108], eax
0x180066aa8  lea     rax, [rsp+150h+var_F8]
0x180066aad  mov     [rsp+150h+lpOverlapped], rax
0x180066ab2  lea     rax, [rsp+150h+var_108]
0x180066ab7  mov     [rsp+150h+hTemplateFile], rax
0x180066abc  lea     rax, [rsp+150h+var_100]
0x180066ac1  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x180066ac6  lea     rax, [rsp+150h+var_F0]
0x180066acb  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x180066ad0  mov     dword ptr [rsp+150h+var_100], 772h
0x180066ad8  mov     qword ptr [rsp+150h+var_F0], r12
0x180066add  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180066ae2  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180066ae7  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180066aeb  lea     rax, [rbp+50h+var_C0]
0x180066aef  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax; __int64
0x180066af4  lea     rax, [rsp+150h+var_110]
0x180066af9  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; __int64
0x180066afe  mov     dword ptr [rsp+150h+var_108], 772h
0x180066b06  lea     r9, [rsp+150h+var_108]
0x180066b0b  call    ??$WriteLine@_W$$BY0DG@DHKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DG@$$CBDAEBHAEBKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,char [54],int,ulong,std::wstring>(wchar_t const *,char const (&)[54],int const &,ulong const &,std::wstring const &)
0x180066b10  nop
0x180066b11  lea     rcx, [rsp+70h]
0x180066b16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066b1b  nop
0x180066b1c  lea     rcx, [rbp+50h+var_A0]
0x180066b20  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066b25  lea     rax, aCacheDisksNotF; "Cache disks not found"
0x180066b2c  lea     rdx, aCacheDiskHaveB; "Cache disk have been found."
0x180066b33  cmp     byte ptr [r14+9Ah], 0
0x180066b3b  cmovz   rdx, rax
  ... truncated ...
```
