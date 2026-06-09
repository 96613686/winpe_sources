# Wsp::Facade::StorageHealthFacade::WaitForCacheDrain(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18006dab4`
- end: `0x18006e264`
- name: `?WaitForCacheDrain@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `1968`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x180066c34`

## callees

- `0x1800010f8`
- `0x1800013d0`
- `0x18000163c`
- `0x180002b50`
- `0x180003584`
- `0x18000bc64`
- `0x18000c2f8`
- `0x18000cce0`
- `0x18000cd54`
- `0x18000da34`
- `0x18000dab8`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f34c`
- `0x180011184`
- `0x1800124b4`
- `0x1800137cc`
- `0x180013810`
- `0x180014dd4`
- `0x1800151d0`
- `0x18001c34c`
- `0x1800354a4`
- `0x18003fc90`
- `0x180043be8`
- `0x180059104`
- `0x18005a354`
- `0x18005a3e8`
- `0x18005a468`
- `0x18005ec5c`
- `0x180060414`
- `0x180068eec`
- `0x18006971c`
- `0x18006dab4`
- `0x180077038`
- `0x180077064`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006dc87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006dcde`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006dc87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006dcde`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006e0ec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006e0ec`

## string_xrefs

- `0x18006db0f`: `Wsp::Facade::StorageHealthFacade::WaitForCacheDrain`
- `0x18006e1cb`: `Wsp::Facade::StorageHealthFacade::WaitForCacheDrain`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Wsp::Facade::StorageHealthFacade::WaitForCacheDrain(
        int a1,
        __int64 a2,
        _QWORD **a3,
        Wsp::Facade::ResExtendedStatus *a4,
        const char *a5)
{
  MI_Context **v5; // r13
  __int64 v7; // rsi
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int SblDiskState; // r15d
  char v12; // r14
  __m128i si128; // xmm7
  unsigned int *v14; // rdi
  unsigned __int64 v15; // r15
  __int64 v16; // rsi
  __int64 v17; // rbx
  unsigned int v18; // ecx
  _QWORD *v19; // r14
  unsigned int *v20; // r13
  struct cxl::TextWriter *v21; // rax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  char *v25; // rbx
  _WORD *v26; // rax
  __int16 v27; // dx
  struct cxl::TextWriter *v28; // rax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  char *v32; // rbx
  double v33; // xmm0_8
  __int64 v34; // rcx
  double v35; // xmm1_8
  struct cxl::TextWriter *v36; // rax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  char *v40; // rbx
  const MI_Char *v41; // rax
  const MI_Char *percentComplete; // r8
  const MI_Char *v43; // r9
  const char *v44; // rdx
  Wsp::Facade::ResExtendedStatus *v45; // rbx
  __int64 v46; // rax
  unsigned int v47; // ebx
  MI_Uint32 secondsRemaining; // [rsp+30h] [rbp-D8h]
  char v50; // [rsp+68h] [rbp-A0h] BYREF
  char v51; // [rsp+69h] [rbp-9Fh]
  const char *v52; // [rsp+70h] [rbp-98h] BYREF
  __int64 v53; // [rsp+78h] [rbp-90h] BYREF
  __int64 v54; // [rsp+80h] [rbp-88h]
  const char *v55; // [rsp+88h] [rbp-80h] BYREF
  Wsp::Facade::ResExtendedStatus *v56; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v57; // [rsp+98h] [rbp-70h]
  __int64 v58; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-60h]
  __int128 v60; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v61; // [rsp+C0h] [rbp-48h]
  __int64 v62[3]; // [rsp+C8h] [rbp-40h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v64[32]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v65; // [rsp+118h] [rbp+10h] BYREF
  __int64 v66; // [rsp+128h] [rbp+20h]
  __int64 v67; // [rsp+130h] [rbp+28h]
  _BYTE v68[32]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v69[2]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v70[32]; // [rsp+178h] [rbp+70h] BYREF

  v5 = (MI_Context **)a4;
  v56 = a4;
  v7 = a2;
  v59 = a2;
  v55 = a5;
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v53) = 2272;
    v52 = "Wsp::Facade::StorageHealthFacade::WaitForCacheDrain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)word_18012BDCA,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v52,
      (__int64)&v53);
  }
  std::vector<unsigned char>::vector<unsigned char>(v62, 1024);
  cxl::load_string(v70, qword_1801599A0, 3001);
  v60 = 0;
  v61 = 0;
  if ( a3[1] )
  {
    v12 = 1;
    v51 = 1;
    v52 = 0;
    v54 = 0;
    SblDiskState = Wsp::Facade::GetSblDiskState(v7, a3, v62);
    LODWORD(v53) = SblDiskState;
    if ( SblDiskState >= 0 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        v14 = (unsigned int *)v62[0];
        if ( *(_DWORD *)v62[0] )
        {
          v15 = 0;
          do
          {
            v16 = 28 * v15;
            *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = *(_OWORD *)&v14[28 * v15 + 3];
            std::string::string(v64, "B");
            cxl::Guid::ToString((cxl::Guid *)SystemTimeAsFileTime);
            std::string::_Tidy_deallocate(v64);
            std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(
              a3,
              &v58,
              v68);
            v17 = v58;
            if ( (_QWORD *)v58 != *a3 )
            {
              *(_DWORD *)(v58 + 228) = v14[v16 + 10];
              v50 = 0;
              v18 = v14[v16 + 10];
              if ( v18 == 3003 )
              {
                *(_BYTE *)(v17 + 226) = 1;
                ++v54;
                v18 = v14[v16 + 10];
              }
              if ( v12 || (v19 = (_QWORD *)(v17 + 232), v20 = &v14[v16 + 14], *(_QWORD *)v20 < *(_QWORD *)(v17 + 232)) )
              {
                v20 = &v14[v16 + 14];
                v19 = (_QWORD *)(v17 + 232);
                *(_QWORD *)(v17 + 232) = *(_QWORD *)v20;
                SystemTimeAsFileTime[0] = 0;
                GetSystemTimeAsFileTime(SystemTimeAsFileTime);
                *(struct _FILETIME *)(v17 + 248) = SystemTimeAsFileTime[0];
              }
              else if ( v18 != 3003 )
              {
                SystemTimeAsFileTime[0] = 0;
                GetSystemTimeAsFileTime(SystemTimeAsFileTime);
                if ( *(_QWORD *)(v17 + 248) + 6000000000LL < *(_QWORD *)SystemTimeAsFileTime )
                {
                  v50 = 1;
                  ++v52;
                }
              }
              v65 = 0;
              v66 = 0;
              v67 = 7;
              LOWORD(v65) = 0;
              v21 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v64, &v65);
              SystemTimeAsFileTime[0].dwLowDateTime = v14[v16 + 10];
              cxl::TextWriter::Write<wchar_t,char [52],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,unsigned __int64,bool,cxl::DateTime>(
                v21,
                (__int64)&v14[v16 + 8] + 1,
                (__int64)&v14[v16 + 9],
                (__int64)SystemTimeAsFileTime,
                (__int64)&v14[v16 + 11],
                (__int64)&v14[v16 + 12],
                (__int64)v20,
                (__int64)&v50,
                v17 + 240);
              std::wstring::wstring(v64, &v65);
              if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
              {
                SystemTimeAsFileTime[0] = (struct _FILETIME)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v64);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                  v22,
                  (unsigned int)byte_18012BCB9,
                  v23,
                  v24,
                  (__int64)SystemTimeAsFileTime);
              }
              v25 = (char *)cxl::TraceManager::Instance() + 160;
              cxl::CxlTraits<std::wstring>::WriteTo(v25, v64);
              cxl::TextWriter::operator<<<cxl::ENDL>(v25);
              std::wstring::_Tidy_deallocate(v64);
              if ( *(_QWORD *)&v14[v16 + 16]
                || *(_QWORD *)&v14[v16 + 18]
                || *(_QWORD *)&v14[v16 + 20]
                || *(_QWORD *)&v14[v16 + 22]
                || *(_QWORD *)&v14[v16 + 24]
                || *(_QWORD *)&v14[v16 + 26]
                || *(_QWORD *)v20 != *v19 )
              {
                v66 = 0;
                v26 = (_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v65);
                *v26 = v27;
                v28 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v64, &v65);
                cxl::TextWriter::Write<wchar_t,char [52],__int64,__int64,__int64,__int64,__int64,__int64,unsigned __int64>(
                  v28,
                  (__int64)&v14[v16 + 18],
                  (__int64)&v14[v16 + 20],
                  (__int64)&v14[v16 + 22],
                  (__int64)&v14[v16 + 24],
                  (__int64)&v14[v16 + 26],
                  (__int64)v19);
                std::wstring::wstring(v64, &v65);
                if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
                {
                  SystemTimeAsFileTime[0] = (struct _FILETIME)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v64);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                    v29,
                    (unsigned int)byte_18012BCD9,
                    v30,
                    v31,
                    (__int64)SystemTimeAsFileTime);
                }
                v32 = (char *)cxl::TraceManager::Instance() + 160;
                cxl::CxlTraits<std::wstring>::WriteTo(v32, v64);
                cxl::TextWriter::operator<<<cxl::ENDL>(v32);
                std::wstring::_Tidy_deallocate(v64);
              }
              std::wstring::_Tidy_deallocate(&v65);
              v12 = v51;
            }
            std::wstring::_Tidy_deallocate(v68);
            ++v15;
          }
          while ( v15 < *v14 );
          SblDiskState = v53;
          v7 = v59;
          v5 = (MI_Context **)v56;
        }
        if ( *v5 )
        {
          if ( v54 < 0 )
            v33 = (double)(int)(v54 & 1 | ((unsigned __int64)v54 >> 1))
                + (double)(int)(v54 & 1 | ((unsigned __int64)v54 >> 1));
          else
            v33 = (double)(int)v54;
          v34 = (__int64)a3[1];
          if ( v34 < 0 )
            v35 = (double)(int)(v34 & 1 | ((unsigned __int64)v34 >> 1))
                + (double)(int)(v34 & 1 | ((unsigned __int64)v34 >> 1));
          else
            v35 = (double)(int)v34;
          floor((v33 / v35 * 0.8 + 0.1) * 100.0);
          v69[0] = 0;
          v69[1] = si128;
          LOWORD(v69[0]) = 0;
          v36 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v68, v69);
          SystemTimeAsFileTime[0].dwLowDateTime = *((_DWORD *)a3 + 2);
          cxl::TextWriter::Write<wchar_t,char [52],unsigned __int64,unsigned long,unsigned __int64>(
            v36,
            (__int64)SystemTimeAsFileTime,
            (__int64)&v52);
          std::wstring::wstring(v68, v69);
          if ( (unsigned int)dword_18014D6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
          {
            SystemTimeAsFileTime[0] = (struct _FILETIME)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
              v37,
              (unsigned int)byte_18012BCF9,
              v38,
              v39,
              (__int64)SystemTimeAsFileTime);
          }
          v40 = (char *)cxl::TraceManager::Instance() + 120;
          cxl::CxlTraits<std::wstring>::WriteTo(v40, v68);
          cxl::TextWriter::operator<<<cxl::ENDL>(v40);
          std::wstring::_Tidy_deallocate(v68);
          v41 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v70);
          MI_Context_WriteProgress(*v5, v41, percentComplete, v43, (MI_Uint32)percentComplete, secondsRemaining);
          std::wstring::_Tidy_deallocate(v69);
        }
        v8 = (_DWORD)v52 + v54;
        if ( a3[1] <= (_QWORD *)&v52[v54] )
          break;
        v12 = 0;
        v51 = 0;
        Sleep(0x1388u);
        v52 = 0;
        v54 = 0;
        SblDiskState = Wsp::Facade::GetSblDiskState(v7, a3, v62);
        LODWORD(v53) = SblDiskState;
        if ( SblDiskState < 0 )
          goto LABEL_58;
      }
      v44 = (const char *)**a3;
      v52 = v44;
      while ( !v44[25] )
      {
        if ( !v44[226] && *((_DWORD *)v44 + 57) == 2001 )
        {
          SblDiskState = -2147023436;
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(&v60, v44 + 96);
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(&v52);
        v44 = v52;
      }
      if ( SblDiskState < 0 )
      {
        std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v56);
        std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(v55, &v56);
        v45 = v56;
        Wsp::Facade::ResExtendedStatus::SetMessageId(v56, 0x8066u);
        *((_WORD *)v45 + 76) = 1;
        v46 = std::vector<std::wstring>::vector<std::wstring>(SystemTimeAsFileTime, &v60);
        Wsp::Facade::ResExtendedStatus::SetMessageArguments(v45, v46);
        v8 = (int)v57;
        if ( v57 )
          std::_Ref_count_base::_Decref(v57);
      }
    }
  }
  else
  {
    SblDiskState = 0;
  }
LABEL_58:
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    SystemTimeAsFileTime[0].dwLowDateTime = 2424;
    v55 = "Wsp::Facade::StorageHealthFacade::WaitForCacheDrain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)byte_18012BD19,
      v9,
      v10,
      (__int64)&v55,
      (__int64)SystemTimeAsFileTime);
  }
  v47 = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)SblDiskState);
  std::vector<std::wstring>::_Tidy(&v60);
  std::wstring::_Tidy_deallocate(v70);
  std::vector<unsigned char>::_Tidy(v62);
  return v47;
}

```

## disassembly

```asm
0x18006dab4  mov     rax, rsp
0x18006dab7  mov     [rax+8], rbx
0x18006dabb  push    rbp
0x18006dabc  push    rsi
0x18006dabd  push    rdi
0x18006dabe  push    r12
0x18006dac0  push    r13
0x18006dac2  push    r14
0x18006dac4  push    r15
0x18006dac6  lea     rbp, [rax-0F8h]
0x18006dacd  sub     rsp, 1C0h
0x18006dad4  movaps  xmmword ptr [rax-48h], xmm6
0x18006dad8  movaps  xmmword ptr [rax-58h], xmm7
0x18006dadc  mov     rax, cs:__security_cookie
0x18006dae3  xor     rax, rsp
0x18006dae6  mov     [rbp+0F0h+var_60], rax
0x18006daed  mov     r13, r9
0x18006daf0  mov     [rbp+0F0h+var_168], r9
0x18006daf4  mov     r12, r8
0x18006daf7  mov     rsi, rdx
0x18006dafa  mov     [rbp+0F0h+var_150], rdx
0x18006dafe  mov     rax, [rbp+0F0h+arg_20]
0x18006db05  mov     [rbp+0F0h+var_170], rax
0x18006db09  mov     eax, cs:dword_18014D6A8
0x18006db0f  lea     rdi, aWspFacadeStora_11; "Wsp::Facade::StorageHealthFacade::WaitF"...
0x18006db16  cmp     eax, 5
0x18006db19  jbe     short loc_18006DB48
0x18006db1b  mov     dword ptr [rsp+1F0h+var_180], 8E0h
0x18006db23  mov     [rsp+1F0h+var_188], rdi
0x18006db28  lea     rax, [rsp+1F0h+var_180]
0x18006db2d  mov     qword ptr [rsp+1F0h+secondsRemaining], rax
0x18006db32  lea     rax, [rsp+1F0h+var_188]
0x18006db37  mov     qword ptr [rsp+1F0h+percentComplete], rax
0x18006db3c  lea     rdx, word_18012BDCA
0x18006db43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006db48  mov     edx, 400h
0x18006db4d  lea     rcx, [rbp+0F0h+var_130]
0x18006db51  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18006db56  nop
0x18006db57  mov     r8d, 0BB9h
0x18006db5d  mov     rdx, cs:qword_1801599A0
0x18006db64  lea     rcx, [rbp+0F0h+var_80]
0x18006db68  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18006db6d  nop
0x18006db6e  xorps   xmm0, xmm0
0x18006db71  movdqu  [rbp+0F0h+var_148], xmm0
0x18006db76  xor     ebx, ebx
0x18006db78  mov     [rbp+0F0h+var_138], rbx
0x18006db7c  cmp     [r12+8], rbx
0x18006db81  jnz     short loc_18006DB8B
0x18006db83  mov     r15d, ebx
0x18006db86  jmp     loc_18006E1D2
0x18006db8b  mov     r14b, 1
0x18006db8e  mov     byte ptr [rsp+1F0h+var_190+1], r14b
0x18006db93  mov     [rsp+1F0h+var_188], rbx
0x18006db98  mov     [rsp+1F0h+var_178], rbx
0x18006db9d  lea     r8, [rbp+0F0h+var_130]
0x18006dba1  mov     rdx, r12
0x18006dba4  mov     rcx, rsi
0x18006dba7  call    ?GetSblDiskState@Facade@Wsp@@YAJAEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@4@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; Wsp::Facade::GetSblDiskState(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> const &,std::vector<uchar> &)
0x18006dbac  mov     r15d, eax
0x18006dbaf  mov     dword ptr [rsp+1F0h+var_180], eax
0x18006dbb3  test    eax, eax
0x18006dbb5  js      loc_18006E1D2
0x18006dbbb  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x18006dbc3  mov     rdi, [rbp+0F0h+var_130]
0x18006dbc7  cmp     [rdi], ebx
0x18006dbc9  jbe     loc_18006DF61
0x18006dbcf  mov     r15, rbx
0x18006dbd2  imul    rsi, r15, 70h ; 'p'
0x18006dbd6  movups  xmm0, xmmword ptr [rsi+rdi+0Ch]
0x18006dbdb  movdqu  xmmword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18006dbe0  lea     rdx, aB; "B"
0x18006dbe7  lea     rcx, [rbp+0F0h+var_100]
0x18006dbeb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006dbf0  nop
0x18006dbf1  lea     r8, [rbp+0F0h+var_100]
0x18006dbf5  lea     rdx, [rbp+0F0h+var_C0]
0x18006dbf9  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]
0x18006dbfd  call    ?ToString@Guid@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; cxl::Guid::ToString(std::string const &)
0x18006dc02  nop
0x18006dc03  lea     rcx, [rbp+0F0h+var_100]
0x18006dc07  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006dc0c  lea     r8, [rbp+0F0h+var_C0]
0x18006dc10  lea     rdx, [rbp+0F0h+var_158]
0x18006dc14  mov     rcx, r12
0x18006dc17  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(std::wstring const &)
0x18006dc1c  mov     rbx, [rbp+0F0h+var_158]
0x18006dc20  cmp     rbx, [r12]
0x18006dc24  jnz     short loc_18006DC2B
0x18006dc26  jmp     loc_18006DF34
0x18006dc2b  mov     eax, [rsi+rdi+28h]
0x18006dc2f  mov     [rbx+0E4h], eax
0x18006dc35  mov     byte ptr [rsp+1F0h+var_190], 0
0x18006dc3a  mov     ecx, [rsi+rdi+28h]
0x18006dc3e  mov     edx, 0BBBh
0x18006dc43  cmp     ecx, edx
0x18006dc45  jnz     short loc_18006DC5B
0x18006dc47  mov     eax, 1
0x18006dc4c  mov     [rbx+0E2h], al
0x18006dc52  add     [rsp+1F0h+var_178], rax
0x18006dc57  mov     ecx, [rsi+rdi+28h]
0x18006dc5b  test    r14b, r14b
0x18006dc5e  jnz     short loc_18006DCBD
0x18006dc60  lea     r14, [rbx+0E8h]
0x18006dc67  lea     r13, [rdi+38h]
0x18006dc6b  add     r13, rsi
0x18006dc6e  mov     rax, [r14]
0x18006dc71  cmp     [r13+0], rax
0x18006dc75  jb      short loc_18006DCBD
0x18006dc77  cmp     ecx, edx
0x18006dc79  jz      short loc_18006DCF5
0x18006dc7b  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006dc83  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006dc87  call    cs:__imp_GetSystemTimeAsFileTime
0x18006dc8e  nop     dword ptr [rax+rax+00h]
0x18006dc93  mov     rax, [rbx+0F8h]
0x18006dc9a  mov     rcx, 165A0BC00h
0x18006dca4  add     rax, rcx
0x18006dca7  cmp     rax, qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime]
0x18006dcab  jge     short loc_18006DCF5
0x18006dcad  mov     eax, 1
0x18006dcb2  mov     byte ptr [rsp+1F0h+var_190], al
0x18006dcb6  add     [rsp+1F0h+var_188], rax
0x18006dcbb  jmp     short loc_18006DCF5
0x18006dcbd  lea     r13, [rdi+38h]
0x18006dcc1  add     r13, rsi
0x18006dcc4  lea     r14, [rbx+0E8h]
0x18006dccb  mov     rax, [r13+0]
0x18006dccf  mov     [r14], rax
0x18006dcd2  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006dcda  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006dcde  call    cs:__imp_GetSystemTimeAsFileTime
0x18006dce5  nop     dword ptr [rax+rax+00h]
0x18006dcea  mov     rax, qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime]
0x18006dcee  mov     [rbx+0F8h], rax
0x18006dcf5  xorps   xmm0, xmm0
0x18006dcf8  movups  [rbp+0F0h+var_E0], xmm0
0x18006dcfc  mov     [rbp+0F0h+var_D0], 0
0x18006dd04  mov     [rbp+0F0h+var_C8], 7
0x18006dd0c  xor     eax, eax
0x18006dd0e  mov     word ptr [rbp+0F0h+var_E0], ax
0x18006dd12  lea     rdx, [rbp+0F0h+var_E0]
0x18006dd16  lea     rcx, [rbp+0F0h+var_100]
0x18006dd1a  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006dd1f  nop
0x18006dd20  mov     ecx, [rsi+rdi+28h]
0x18006dd24  mov     [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x18006dd27  add     rbx, 0F0h
0x18006dd2e  lea     rcx, [rdi+30h]
0x18006dd32  add     rcx, rsi
0x18006dd35  lea     rdx, [rdi+2Ch]
0x18006dd39  add     rdx, rsi
0x18006dd3c  lea     r8, [rdi+24h]
0x18006dd40  add     r8, rsi
0x18006dd43  lea     r9, [rdi+21h]
0x18006dd47  add     r9, rsi
0x18006dd4a  mov     [rsp+1F0h+var_198], rbx; __int64
0x18006dd4f  lea     r10, [rsp+1F0h+var_190]
0x18006dd54  mov     [rsp+1F0h+var_1A0], r10; __int64
0x18006dd59  mov     [rsp+1F0h+var_1A8], r13; __int64
0x18006dd5e  mov     [rsp+1F0h+var_1B0], rcx; __int64
0x18006dd63  mov     [rsp+1F0h+var_1B8], rdx; __int64
0x18006dd68  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]
0x18006dd6c  mov     [rsp+1F0h+var_1C0], rcx; __int64
0x18006dd71  mov     qword ptr [rsp+1F0h+secondsRemaining], r8; __int64
0x18006dd76  mov     qword ptr [rsp+1F0h+percentComplete], r9; __int64
0x18006dd7b  lea     r9, [rbp+0F0h+var_C0]
0x18006dd7f  mov     rcx, rax; struct cxl::TextWriter *
0x18006dd82  call    ??$Write@_W$$BY0DE@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_K_NUDateTime@cxl@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBEAEBK44AEBW4S2DCacheMode@@AEB_KAEB_NAEBUDateTime@1@@Z; cxl::TextWriter::Write<wchar_t,char [52],std::wstring,uchar,ulong,ulong,ulong,S2DCacheMode,unsigned __int64,bool,cxl::DateTime>(wchar_t const *,char const (&)[52],std::wstring const &,uchar const &,ulong const &,ulong const &,ulong const &,S2DCacheMode const &,unsigned __int64 const &,bool const &,cxl::DateTime const &)
0x18006dd87  nop
0x18006dd88  lea     rdx, [rbp+0F0h+var_E0]
0x18006dd8c  lea     rcx, [rbp+0F0h+var_100]
0x18006dd90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006dd95  nop
0x18006dd96  mov     eax, cs:dword_18014D6A8
0x18006dd9c  cmp     eax, 5
0x18006dd9f  jbe     short loc_18006DDD8
0x18006dda1  mov     edx, 4000h
0x18006dda6  lea     rcx, dword_18014D6A8
0x18006ddad  call    _tlgKeywordOn
0x18006ddb2  test    al, al
0x18006ddb4  jz      short loc_18006DDD8
0x18006ddb6  lea     rcx, [rbp+0F0h+var_100]
0x18006ddba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ddbf  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18006ddc3  lea     rax, [rbp+0F0h+SystemTimeAsFileTime]
0x18006ddc7  mov     qword ptr [rsp+1F0h+percentComplete], rax
0x18006ddcc  lea     rdx, byte_18012BCB9
0x18006ddd3  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006ddd8  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006dddd  lea     rbx, [rax+0A0h]
0x18006dde4  lea     rdx, [rbp+0F0h+var_100]
0x18006dde8  mov     rcx, rbx
0x18006ddeb  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006ddf0  mov     rcx, rbx
0x18006ddf3  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006ddf8  nop
0x18006ddf9  lea     rcx, [rbp+0F0h+var_100]
0x18006ddfd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006de02  lea     rbx, [rsi+rdi]
0x18006de06  xor     edx, edx
0x18006de08  cmp     [rbx+40h], rdx
0x18006de0c  jnz     short loc_18006DE3E
0x18006de0e  cmp     [rsi+rdi+48h], rdx
0x18006de13  jnz     short loc_18006DE3E
0x18006de15  cmp     [rsi+rdi+50h], rdx
0x18006de1a  jnz     short loc_18006DE3E
0x18006de1c  cmp     [rsi+rdi+58h], rdx
0x18006de21  jnz     short loc_18006DE3E
0x18006de23  cmp     [rsi+rdi+60h], rdx
0x18006de28  jnz     short loc_18006DE3E
0x18006de2a  cmp     [rsi+rdi+68h], rdx
0x18006de2f  jnz     short loc_18006DE3E
0x18006de31  mov     rax, [r14]
0x18006de34  cmp     [r13+0], rax
0x18006de38  jz      loc_18006DF25
0x18006de3e  mov     [rbp+0F0h+var_D0], rdx
0x18006de42  lea     rcx, [rbp+0F0h+var_E0]
0x18006de46  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006de4b  mov     [rax], dx
0x18006de4e  lea     rdx, [rbp+0F0h+var_E0]
0x18006de52  lea     rcx, [rbp+0F0h+var_100]
0x18006de56  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006de5b  nop
0x18006de5c  lea     rcx, [rdi+68h]
0x18006de60  add     rcx, rsi
0x18006de63  lea     rdx, [rdi+60h]
0x18006de67  add     rdx, rsi
0x18006de6a  lea     r8, [rdi+58h]
0x18006de6e  add     r8, rsi
0x18006de71  lea     r10, [rdi+50h]
0x18006de75  add     r10, rsi
0x18006de78  lea     r11, [rdi+48h]
0x18006de7c  add     r11, rsi
0x18006de7f  mov     [rsp+1F0h+var_1A8], r14; __int64
0x18006de84  mov     [rsp+1F0h+var_1B0], rcx; __int64
0x18006de89  mov     [rsp+1F0h+var_1B8], rdx; __int64
0x18006de8e  mov     [rsp+1F0h+var_1C0], r8; __int64
0x18006de93  mov     qword ptr [rsp+1F0h+secondsRemaining], r10; __int64
0x18006de98  mov     qword ptr [rsp+1F0h+percentComplete], r11; __int64
0x18006de9d  lea     r9, [rbx+40h]
0x18006dea1  mov     rcx, rax; struct cxl::TextWriter *
0x18006dea4  call    ??$Write@_W$$BY0DE@D_J_J_J_J_J_J_K@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEB_J22222AEB_K@Z; cxl::TextWriter::Write<wchar_t,char [52],__int64,__int64,__int64,__int64,__int64,__int64,unsigned __int64>(wchar_t const *,char const (&)[52],__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &,unsigned __int64 const &)
0x18006dea9  nop
0x18006deaa  lea     rdx, [rbp+0F0h+var_E0]
0x18006deae  lea     rcx, [rbp+0F0h+var_100]
0x18006deb2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006deb7  nop
0x18006deb8  mov     eax, cs:dword_18014D6A8
0x18006debe  cmp     eax, 5
0x18006dec1  jbe     short loc_18006DEFA
0x18006dec3  mov     edx, 4000h
0x18006dec8  lea     rcx, dword_18014D6A8
0x18006decf  call    _tlgKeywordOn
0x18006ded4  test    al, al
0x18006ded6  jz      short loc_18006DEFA
0x18006ded8  lea     rcx, [rbp+0F0h+var_100]
0x18006dedc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006dee1  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18006dee5  lea     rax, [rbp+0F0h+SystemTimeAsFileTime]
0x18006dee9  mov     qword ptr [rsp+1F0h+percentComplete], rax
0x18006deee  lea     rdx, byte_18012BCD9
0x18006def5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006defa  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006deff  lea     rbx, [rax+0A0h]
0x18006df06  lea     rdx, [rbp+0F0h+var_100]
0x18006df0a  mov     rcx, rbx
0x18006df0d  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006df12  mov     rcx, rbx
0x18006df15  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006df1a  nop
0x18006df1b  lea     rcx, [rbp+0F0h+var_100]
0x18006df1f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006df24  nop
0x18006df25  lea     rcx, [rbp+0F0h+var_E0]
0x18006df29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006df2e  nop
0x18006df2f  mov     r14b, byte ptr [rsp+1F0h+var_190+1]
0x18006df34  lea     rcx, [rbp+0F0h+var_C0]
0x18006df38  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006df3d  mov     edx, 1
0x18006df42  add     r15, rdx
0x18006df45  mov     eax, [rdi]
0x18006df47  cmp     r15, rax
0x18006df4a  jb      loc_18006DBD2
0x18006df50  mov     r15d, dword ptr [rsp+1F0h+var_180]
0x18006df55  mov     rsi, [rbp+0F0h+var_150]
0x18006df59  mov     r13, [rbp+0F0h+var_168]
0x18006df5d  xor     ebx, ebx
0x18006df5f  jmp     short loc_18006DF66
0x18006df61  mov     edx, 1
0x18006df66  cmp     [r13+0], rbx
0x18006df6a  jz      loc_18006E0CF
0x18006df70  mov     rcx, [rsp+1F0h+var_178]
0x18006df75  xorps   xmm0, xmm0
0x18006df78  test    rcx, rcx
0x18006df7b  js      short loc_18006DF84
0x18006df7d  cvtsi2sd xmm0, rcx
0x18006df82  jmp     short loc_18006DF99
  ... truncated ...
```
