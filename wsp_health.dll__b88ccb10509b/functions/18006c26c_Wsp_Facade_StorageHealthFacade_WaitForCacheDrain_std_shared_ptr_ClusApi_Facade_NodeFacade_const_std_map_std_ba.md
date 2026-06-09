# Wsp::Facade::StorageHealthFacade::WaitForCacheDrain(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18006c26c`
- end: `0x18006ca09`
- name: `?WaitForCacheDrain@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `1949`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x18006540c`

## callees

- `0x1800010f4`
- `0x1800013bc`
- `0x180001620`
- `0x180002ae0`
- `0x1800034e4`
- `0x18000b8e4`
- `0x18000bf68`
- `0x18000c934`
- `0x18000c9a8`
- `0x18000d618`
- `0x18000d69c`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000eebc`
- `0x180010ca4`
- `0x180011f44`
- `0x180013110`
- `0x180013150`
- `0x180014630`
- `0x180014a24`
- `0x18001b828`
- `0x180034360`
- `0x18003e65c`
- `0x1800424d8`
- `0x180057a0c`
- `0x180058be8`
- `0x180058c7c`
- `0x180058cf8`
- `0x18005d4cc`
- `0x18005ec50`
- `0x1800676c0`
- `0x180067eec`
- `0x18006c26c`
- `0x1800751e4`
- `0x180075210`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c43f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c490`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c43f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c490`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006c898`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006c898`

## string_xrefs

- `0x18006c2c7`: `Wsp::Facade::StorageHealthFacade::WaitForCacheDrain`
- `0x18006c971`: `Wsp::Facade::StorageHealthFacade::WaitForCacheDrain`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Wsp::Facade::StorageHealthFacade::WaitForCacheDrain(
        __int64 a1,
        __int64 a2,
        _QWORD **a3,
        Wsp::Facade::ResExtendedStatus *a4,
        const char *a5)
{
  MI_Context **v5; // r13
  __int64 v7; // rsi
  std::_Ref_count_base *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
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
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  char *v25; // rbx
  _WORD *v26; // rax
  __int16 v27; // dx
  struct cxl::TextWriter *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  char *v32; // rbx
  double v33; // xmm0_8
  __int64 v34; // rcx
  double v35; // xmm1_8
  struct cxl::TextWriter *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  char *v42; // rbx
  const MI_Char *v43; // rax
  const MI_Char *percentComplete; // r8
  const MI_Char *v45; // r9
  const char *v46; // rdx
  Wsp::Facade::ResExtendedStatus *v47; // rbx
  __int64 v48; // rax
  unsigned int v49; // ebx
  MI_Uint32 secondsRemaining; // [rsp+30h] [rbp-D8h]
  char v52; // [rsp+68h] [rbp-A0h] BYREF
  char v53; // [rsp+69h] [rbp-9Fh]
  const char *v54; // [rsp+70h] [rbp-98h] BYREF
  __int64 v55; // [rsp+78h] [rbp-90h]
  __int64 v56; // [rsp+80h] [rbp-88h] BYREF
  const char *v57; // [rsp+88h] [rbp-80h] BYREF
  Wsp::Facade::ResExtendedStatus *v58; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v59; // [rsp+98h] [rbp-70h]
  __int64 v60; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-60h]
  __int128 v62; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-48h]
  __int64 v64[3]; // [rsp+C8h] [rbp-40h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v66[32]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v67; // [rsp+118h] [rbp+10h] BYREF
  __int64 v68; // [rsp+128h] [rbp+20h]
  __int64 v69; // [rsp+130h] [rbp+28h]
  _BYTE v70[32]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v71[2]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v72[32]; // [rsp+178h] [rbp+70h] BYREF

  v5 = (MI_Context **)a4;
  v58 = a4;
  v7 = a2;
  v61 = a2;
  v57 = a5;
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v55) = 2272;
    v54 = "Wsp::Facade::StorageHealthFacade::WaitForCacheDrain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_180129D81,
      (__int64)a3,
      (__int64)a4,
      &v54);
  }
  std::vector<unsigned char>::vector<unsigned char>(v64, 1024);
  cxl::load_string(v72, qword_1801578A0, 3001);
  v62 = 0;
  v63 = 0;
  if ( a3[1] )
  {
    v12 = 1;
    v53 = 1;
    v54 = 0;
    v56 = 0;
    SblDiskState = Wsp::Facade::GetSblDiskState(v7, a3, v64);
    LODWORD(v55) = SblDiskState;
    if ( SblDiskState >= 0 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        v14 = (unsigned int *)v64[0];
        if ( *(_DWORD *)v64[0] )
        {
          v15 = 0;
          do
          {
            v16 = 28 * v15;
            *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = *(_OWORD *)&v14[28 * v15 + 3];
            std::string::string(v66, "B");
            cxl::Guid::ToString((cxl::Guid *)SystemTimeAsFileTime);
            std::string::_Tidy_deallocate(v66);
            std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(
              a3,
              &v60,
              v70);
            v17 = v60;
            if ( (_QWORD *)v60 != *a3 )
            {
              *(_DWORD *)(v60 + 228) = v14[v16 + 10];
              v52 = 0;
              v18 = v14[v16 + 10];
              if ( v18 == 3003 )
              {
                *(_BYTE *)(v17 + 226) = 1;
                ++v56;
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
                  v52 = 1;
                  ++v54;
                }
              }
              v67 = 0;
              v68 = 0;
              v69 = 7;
              LOWORD(v67) = 0;
              v21 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v66, &v67);
              SystemTimeAsFileTime[0].dwLowDateTime = v14[v16 + 10];
              cxl::TextWriter::Write<wchar_t,char [52],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,unsigned __int64,bool,cxl::DateTime>(
                v21,
                (__int64)&v14[v16 + 11],
                (__int64)&v14[v16 + 9],
                (__int64)v70,
                (__int64)&v14[v16 + 8] + 1,
                (__int64)&v14[v16 + 9],
                (__int64)SystemTimeAsFileTime,
                (__int64)&v14[v16 + 11],
                (__int64)&v14[v16 + 12],
                (__int64)v20,
                (__int64)&v52,
                v17 + 240);
              std::wstring::wstring(v66, &v67);
              if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
              {
                SystemTimeAsFileTime[0] = (struct _FILETIME)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v66);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                  v22,
                  (__int64)byte_180129CB1,
                  v23,
                  v24,
                  SystemTimeAsFileTime);
              }
              v25 = (char *)cxl::TraceManager::Instance() + 160;
              cxl::CxlTraits<std::wstring>::WriteTo(v25, v66);
              cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v25);
              std::wstring::_Tidy_deallocate(v66);
              if ( *(_QWORD *)&v14[v16 + 16]
                || *(_QWORD *)&v14[v16 + 18]
                || *(_QWORD *)&v14[v16 + 20]
                || *(_QWORD *)&v14[v16 + 22]
                || *(_QWORD *)&v14[v16 + 24]
                || *(_QWORD *)&v14[v16 + 26]
                || *(_QWORD *)v20 != *v19 )
              {
                v68 = 0;
                v26 = (_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v67);
                *v26 = v27;
                v28 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v66, &v67);
                cxl::TextWriter::Write<wchar_t,char [52],__int64,__int64,__int64,__int64,__int64,__int64,unsigned __int64>(
                  v28,
                  (__int64)&v14[v16 + 24],
                  (__int64)&v14[v16 + 22],
                  (__int64)&v14[v16 + 16],
                  (__int64)&v14[v16 + 18],
                  (__int64)&v14[v16 + 20],
                  (__int64)&v14[v16 + 22],
                  (__int64)&v14[v16 + 24],
                  (__int64)&v14[v16 + 26],
                  (__int64)v19);
                std::wstring::wstring(v66, &v67);
                if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
                {
                  SystemTimeAsFileTime[0] = (struct _FILETIME)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v66);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                    v29,
                    (__int64)byte_180129CD1,
                    v30,
                    v31,
                    SystemTimeAsFileTime);
                }
                v32 = (char *)cxl::TraceManager::Instance() + 160;
                cxl::CxlTraits<std::wstring>::WriteTo(v32, v66);
                cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v32);
                std::wstring::_Tidy_deallocate(v66);
              }
              std::wstring::_Tidy_deallocate(&v67);
              v12 = v53;
            }
            std::wstring::_Tidy_deallocate(v70);
            ++v15;
          }
          while ( v15 < *v14 );
          SblDiskState = v55;
          v7 = v61;
          v5 = (MI_Context **)v58;
        }
        if ( *v5 )
        {
          if ( v56 < 0 )
            v33 = (double)(int)(v56 & 1 | ((unsigned __int64)v56 >> 1))
                + (double)(int)(v56 & 1 | ((unsigned __int64)v56 >> 1));
          else
            v33 = (double)(int)v56;
          v34 = (__int64)a3[1];
          if ( v34 < 0 )
            v35 = (double)(int)(v34 & 1 | ((unsigned __int64)v34 >> 1))
                + (double)(int)(v34 & 1 | ((unsigned __int64)v34 >> 1));
          else
            v35 = (double)(int)v34;
          floor((v33 / v35 * 0.8 + 0.1) * 100.0);
          v71[0] = 0;
          v71[1] = si128;
          LOWORD(v71[0]) = 0;
          v36 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v70, v71);
          SystemTimeAsFileTime[0].dwLowDateTime = *((_DWORD *)a3 + 2);
          cxl::TextWriter::Write<wchar_t,char [52],unsigned __int64,unsigned long,unsigned __int64>(
            v36,
            v37,
            v38,
            (__int64)&v56,
            (__int64)SystemTimeAsFileTime,
            (__int64)&v54);
          std::wstring::wstring(v70, v71);
          if ( (unsigned int)dword_18014B6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
          {
            SystemTimeAsFileTime[0] = (struct _FILETIME)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v70);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
              v39,
              (__int64)byte_180129CF1,
              v40,
              v41,
              SystemTimeAsFileTime);
          }
          v42 = (char *)cxl::TraceManager::Instance() + 120;
          cxl::CxlTraits<std::wstring>::WriteTo(v42, v70);
          cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v42);
          std::wstring::_Tidy_deallocate(v70);
          v43 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v72);
          MI_Context_WriteProgress(*v5, v43, percentComplete, v45, (MI_Uint32)percentComplete, secondsRemaining);
          std::wstring::_Tidy_deallocate(v71);
        }
        v8 = (std::_Ref_count_base *)&v54[v56];
        if ( a3[1] <= (_QWORD *)&v54[v56] )
          break;
        v12 = 0;
        v53 = 0;
        Sleep(0x1388u);
        v54 = 0;
        v56 = 0;
        SblDiskState = Wsp::Facade::GetSblDiskState(v7, a3, v64);
        LODWORD(v55) = SblDiskState;
        if ( SblDiskState < 0 )
          goto LABEL_58;
      }
      v46 = (const char *)**a3;
      v54 = v46;
      while ( !v46[25] )
      {
        if ( !v46[226] && *((_DWORD *)v46 + 57) == 2001 )
        {
          SblDiskState = -2147023436;
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(&v62, v46 + 96);
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(&v54);
        v46 = v54;
      }
      if ( SblDiskState < 0 )
      {
        std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v58);
        std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(v57, &v58);
        v47 = v58;
        Wsp::Facade::ResExtendedStatus::SetMessageId(v58, 0x8066u);
        *((_WORD *)v47 + 76) = 1;
        v48 = std::vector<std::wstring>::vector<std::wstring>(SystemTimeAsFileTime, &v62);
        Wsp::Facade::ResExtendedStatus::SetMessageArguments(v47, v48);
        v8 = v59;
        if ( v59 )
          std::_Ref_count_base::_Decref(v59);
      }
    }
  }
  else
  {
    SblDiskState = 0;
  }
LABEL_58:
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    SystemTimeAsFileTime[0].dwLowDateTime = 2424;
    v57 = "Wsp::Facade::StorageHealthFacade::WaitForCacheDrain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      (__int64)byte_180129D11,
      v9,
      v10,
      &v57);
  }
  v49 = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)SblDiskState);
  std::vector<std::wstring>::_Tidy(&v62);
  std::wstring::_Tidy_deallocate(v72);
  std::vector<unsigned char>::_Tidy(v64);
  return v49;
}

```

## disassembly

```asm
0x18006c26c  mov     rax, rsp
0x18006c26f  mov     [rax+8], rbx
0x18006c273  push    rbp
0x18006c274  push    rsi
0x18006c275  push    rdi
0x18006c276  push    r12
0x18006c278  push    r13
0x18006c27a  push    r14
0x18006c27c  push    r15
0x18006c27e  lea     rbp, [rax-0F8h]
0x18006c285  sub     rsp, 1C0h
0x18006c28c  movaps  xmmword ptr [rax-48h], xmm6
0x18006c290  movaps  xmmword ptr [rax-58h], xmm7
0x18006c294  mov     rax, cs:__security_cookie
0x18006c29b  xor     rax, rsp
0x18006c29e  mov     [rbp+0F0h+var_60], rax
0x18006c2a5  mov     r13, r9
0x18006c2a8  mov     [rbp+0F0h+var_168], r9
0x18006c2ac  mov     r12, r8
0x18006c2af  mov     rsi, rdx
0x18006c2b2  mov     [rbp+0F0h+var_150], rdx
0x18006c2b6  mov     rax, [rbp+0F0h+arg_20]
0x18006c2bd  mov     [rbp+0F0h+var_170], rax
0x18006c2c1  mov     eax, cs:dword_18014B6A8
0x18006c2c7  lea     rdi, aWspFacadeStora_11; "Wsp::Facade::StorageHealthFacade::WaitF"...
0x18006c2ce  cmp     eax, 5
0x18006c2d1  jbe     short loc_18006C300
0x18006c2d3  mov     dword ptr [rsp+1F0h+var_180], 8E0h
0x18006c2db  mov     [rsp+1F0h+var_188], rdi
0x18006c2e0  lea     rax, [rsp+1F0h+var_180]
0x18006c2e5  mov     qword ptr [rsp+1F0h+secondsRemaining], rax
0x18006c2ea  lea     rax, [rsp+1F0h+var_188]
0x18006c2ef  mov     qword ptr [rsp+1F0h+percentComplete], rax
0x18006c2f4  lea     rdx, byte_180129D81
0x18006c2fb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006c300  mov     edx, 400h
0x18006c305  lea     rcx, [rbp+0F0h+var_130]
0x18006c309  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18006c30e  nop
0x18006c30f  mov     r8d, 0BB9h
0x18006c315  mov     rdx, cs:qword_1801578A0
0x18006c31c  lea     rcx, [rbp+0F0h+var_80]
0x18006c320  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18006c325  nop
0x18006c326  xorps   xmm0, xmm0
0x18006c329  movdqu  [rbp+0F0h+var_148], xmm0
0x18006c32e  xor     ebx, ebx
0x18006c330  mov     [rbp+0F0h+var_138], rbx
0x18006c334  cmp     [r12+8], rbx
0x18006c339  jnz     short loc_18006C343
0x18006c33b  mov     r15d, ebx
0x18006c33e  jmp     loc_18006C978
0x18006c343  mov     r14b, 1
0x18006c346  mov     byte ptr [rsp+1F0h+var_190+1], r14b
0x18006c34b  mov     [rsp+1F0h+var_188], rbx
0x18006c350  mov     [rsp+1F0h+var_178], rbx
0x18006c355  lea     r8, [rbp+0F0h+var_130]
0x18006c359  mov     rdx, r12
0x18006c35c  mov     rcx, rsi
0x18006c35f  call    ?GetSblDiskState@Facade@Wsp@@YAJAEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@4@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; Wsp::Facade::GetSblDiskState(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> const &,std::vector<uchar> &)
0x18006c364  mov     r15d, eax
0x18006c367  mov     dword ptr [rsp+1F0h+var_180], eax
0x18006c36b  test    eax, eax
0x18006c36d  js      loc_18006C978
0x18006c373  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x18006c37b  mov     rdi, [rbp+0F0h+var_130]
0x18006c37f  cmp     [rdi], ebx
0x18006c381  jbe     loc_18006C70D
0x18006c387  mov     r15, rbx
0x18006c38a  imul    rsi, r15, 70h ; 'p'
0x18006c38e  movups  xmm0, xmmword ptr [rsi+rdi+0Ch]
0x18006c393  movdqu  xmmword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18006c398  lea     rdx, aB; "B"
0x18006c39f  lea     rcx, [rbp+0F0h+var_100]
0x18006c3a3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006c3a8  nop
0x18006c3a9  lea     r8, [rbp+0F0h+var_100]
0x18006c3ad  lea     rdx, [rbp+0F0h+var_C0]
0x18006c3b1  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]
0x18006c3b5  call    ?ToString@Guid@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; cxl::Guid::ToString(std::string const &)
0x18006c3ba  nop
0x18006c3bb  lea     rcx, [rbp+0F0h+var_100]
0x18006c3bf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006c3c4  lea     r8, [rbp+0F0h+var_C0]
0x18006c3c8  lea     rdx, [rbp+0F0h+var_158]
0x18006c3cc  mov     rcx, r12
0x18006c3cf  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(std::wstring const &)
0x18006c3d4  mov     rbx, [rbp+0F0h+var_158]
0x18006c3d8  cmp     rbx, [r12]
0x18006c3dc  jnz     short loc_18006C3E3
0x18006c3de  jmp     loc_18006C6E0
0x18006c3e3  mov     eax, [rsi+rdi+28h]
0x18006c3e7  mov     [rbx+0E4h], eax
0x18006c3ed  mov     byte ptr [rsp+1F0h+var_190], 0
0x18006c3f2  mov     ecx, [rsi+rdi+28h]
0x18006c3f6  mov     edx, 0BBBh
0x18006c3fb  cmp     ecx, edx
0x18006c3fd  jnz     short loc_18006C413
0x18006c3ff  mov     eax, 1
0x18006c404  mov     [rbx+0E2h], al
0x18006c40a  add     [rsp+1F0h+var_178], rax
0x18006c40f  mov     ecx, [rsi+rdi+28h]
0x18006c413  test    r14b, r14b
0x18006c416  jnz     short loc_18006C46F
0x18006c418  lea     r14, [rbx+0E8h]
0x18006c41f  lea     r13, [rdi+38h]
0x18006c423  add     r13, rsi
0x18006c426  mov     rax, [r14]
0x18006c429  cmp     [r13+0], rax
0x18006c42d  jb      short loc_18006C46F
0x18006c42f  cmp     ecx, edx
0x18006c431  jz      short loc_18006C4A1
0x18006c433  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006c43b  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006c43f  call    cs:__imp_GetSystemTimeAsFileTime
0x18006c445  mov     rax, [rbx+0F8h]
0x18006c44c  mov     rcx, 165A0BC00h
0x18006c456  add     rax, rcx
0x18006c459  cmp     rax, qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime]
0x18006c45d  jge     short loc_18006C4A1
0x18006c45f  mov     eax, 1
0x18006c464  mov     byte ptr [rsp+1F0h+var_190], al
0x18006c468  add     [rsp+1F0h+var_188], rax
0x18006c46d  jmp     short loc_18006C4A1
0x18006c46f  lea     r13, [rdi+38h]
0x18006c473  add     r13, rsi
0x18006c476  lea     r14, [rbx+0E8h]
0x18006c47d  mov     rax, [r13+0]
0x18006c481  mov     [r14], rax
0x18006c484  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006c48c  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006c490  call    cs:__imp_GetSystemTimeAsFileTime
0x18006c496  mov     rax, qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime]
0x18006c49a  mov     [rbx+0F8h], rax
0x18006c4a1  xorps   xmm0, xmm0
0x18006c4a4  movups  [rbp+0F0h+var_E0], xmm0
0x18006c4a8  mov     [rbp+0F0h+var_D0], 0
0x18006c4b0  mov     [rbp+0F0h+var_C8], 7
0x18006c4b8  xor     eax, eax
0x18006c4ba  mov     word ptr [rbp+0F0h+var_E0], ax
0x18006c4be  lea     rdx, [rbp+0F0h+var_E0]
0x18006c4c2  lea     rcx, [rbp+0F0h+var_100]
0x18006c4c6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006c4cb  nop
0x18006c4cc  mov     ecx, [rsi+rdi+28h]
0x18006c4d0  mov     [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x18006c4d3  add     rbx, 0F0h
0x18006c4da  lea     rcx, [rdi+30h]
0x18006c4de  add     rcx, rsi
0x18006c4e1  lea     rdx, [rdi+2Ch]
0x18006c4e5  add     rdx, rsi
0x18006c4e8  lea     r8, [rdi+24h]
0x18006c4ec  add     r8, rsi
0x18006c4ef  lea     r9, [rdi+21h]
0x18006c4f3  add     r9, rsi
0x18006c4f6  mov     [rsp+1F0h+var_198], rbx; __int64
0x18006c4fb  lea     r10, [rsp+1F0h+var_190]
0x18006c500  mov     [rsp+1F0h+var_1A0], r10; __int64
0x18006c505  mov     [rsp+1F0h+var_1A8], r13; __int64
0x18006c50a  mov     [rsp+1F0h+var_1B0], rcx; __int64
0x18006c50f  mov     [rsp+1F0h+var_1B8], rdx; __int64
0x18006c514  lea     rcx, [rbp+0F0h+SystemTimeAsFileTime]
0x18006c518  mov     [rsp+1F0h+var_1C0], rcx; __int64
0x18006c51d  mov     qword ptr [rsp+1F0h+secondsRemaining], r8; __int64
0x18006c522  mov     qword ptr [rsp+1F0h+percentComplete], r9; __int64
0x18006c527  lea     r9, [rbp+0F0h+var_C0]
0x18006c52b  mov     rcx, rax; struct cxl::TextWriter *
0x18006c52e  call    ??$Write@_W$$BY0DE@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_K_NUDateTime@cxl@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBEAEBK44AEBW4S2DCacheMode@@AEB_KAEB_NAEBUDateTime@1@@Z; cxl::TextWriter::Write<wchar_t,char [52],std::wstring,uchar,ulong,ulong,ulong,S2DCacheMode,unsigned __int64,bool,cxl::DateTime>(wchar_t const *,char const (&)[52],std::wstring const &,uchar const &,ulong const &,ulong const &,ulong const &,S2DCacheMode const &,unsigned __int64 const &,bool const &,cxl::DateTime const &)
0x18006c533  nop
0x18006c534  lea     rdx, [rbp+0F0h+var_E0]
0x18006c538  lea     rcx, [rbp+0F0h+var_100]
0x18006c53c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006c541  nop
0x18006c542  mov     eax, cs:dword_18014B6A8
0x18006c548  cmp     eax, 5
0x18006c54b  jbe     short loc_18006C584
0x18006c54d  mov     edx, 4000h
0x18006c552  lea     rcx, dword_18014B6A8
0x18006c559  call    _tlgKeywordOn
0x18006c55e  test    al, al
0x18006c560  jz      short loc_18006C584
0x18006c562  lea     rcx, [rbp+0F0h+var_100]
0x18006c566  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006c56b  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18006c56f  lea     rax, [rbp+0F0h+SystemTimeAsFileTime]
0x18006c573  mov     qword ptr [rsp+1F0h+percentComplete], rax
0x18006c578  lea     rdx, byte_180129CB1
0x18006c57f  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006c584  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006c589  lea     rbx, [rax+0A0h]
0x18006c590  lea     rdx, [rbp+0F0h+var_100]
0x18006c594  mov     rcx, rbx
0x18006c597  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006c59c  mov     rcx, rbx
0x18006c59f  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006c5a4  nop
0x18006c5a5  lea     rcx, [rbp+0F0h+var_100]
0x18006c5a9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c5ae  lea     rbx, [rsi+rdi]
0x18006c5b2  xor     edx, edx
0x18006c5b4  cmp     [rbx+40h], rdx
0x18006c5b8  jnz     short loc_18006C5EA
0x18006c5ba  cmp     [rsi+rdi+48h], rdx
0x18006c5bf  jnz     short loc_18006C5EA
0x18006c5c1  cmp     [rsi+rdi+50h], rdx
0x18006c5c6  jnz     short loc_18006C5EA
0x18006c5c8  cmp     [rsi+rdi+58h], rdx
0x18006c5cd  jnz     short loc_18006C5EA
0x18006c5cf  cmp     [rsi+rdi+60h], rdx
0x18006c5d4  jnz     short loc_18006C5EA
0x18006c5d6  cmp     [rsi+rdi+68h], rdx
0x18006c5db  jnz     short loc_18006C5EA
0x18006c5dd  mov     rax, [r14]
0x18006c5e0  cmp     [r13+0], rax
0x18006c5e4  jz      loc_18006C6D1
0x18006c5ea  mov     [rbp+0F0h+var_D0], rdx
0x18006c5ee  lea     rcx, [rbp+0F0h+var_E0]
0x18006c5f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006c5f7  mov     [rax], dx
0x18006c5fa  lea     rdx, [rbp+0F0h+var_E0]
0x18006c5fe  lea     rcx, [rbp+0F0h+var_100]
0x18006c602  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006c607  nop
0x18006c608  lea     rcx, [rdi+68h]
0x18006c60c  add     rcx, rsi
0x18006c60f  lea     rdx, [rdi+60h]
0x18006c613  add     rdx, rsi
0x18006c616  lea     r8, [rdi+58h]
0x18006c61a  add     r8, rsi
0x18006c61d  lea     r10, [rdi+50h]
0x18006c621  add     r10, rsi
0x18006c624  lea     r11, [rdi+48h]
0x18006c628  add     r11, rsi
0x18006c62b  mov     [rsp+1F0h+var_1A8], r14; __int64
0x18006c630  mov     [rsp+1F0h+var_1B0], rcx; __int64
0x18006c635  mov     [rsp+1F0h+var_1B8], rdx; __int64
0x18006c63a  mov     [rsp+1F0h+var_1C0], r8; __int64
0x18006c63f  mov     qword ptr [rsp+1F0h+secondsRemaining], r10; __int64
0x18006c644  mov     qword ptr [rsp+1F0h+percentComplete], r11; __int64
0x18006c649  lea     r9, [rbx+40h]
0x18006c64d  mov     rcx, rax; struct cxl::TextWriter *
0x18006c650  call    ??$Write@_W$$BY0DE@D_J_J_J_J_J_J_K@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEB_J22222AEB_K@Z; cxl::TextWriter::Write<wchar_t,char [52],__int64,__int64,__int64,__int64,__int64,__int64,unsigned __int64>(wchar_t const *,char const (&)[52],__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &,unsigned __int64 const &)
0x18006c655  nop
0x18006c656  lea     rdx, [rbp+0F0h+var_E0]
0x18006c65a  lea     rcx, [rbp+0F0h+var_100]
0x18006c65e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006c663  nop
0x18006c664  mov     eax, cs:dword_18014B6A8
0x18006c66a  cmp     eax, 5
0x18006c66d  jbe     short loc_18006C6A6
0x18006c66f  mov     edx, 4000h
0x18006c674  lea     rcx, dword_18014B6A8
0x18006c67b  call    _tlgKeywordOn
0x18006c680  test    al, al
0x18006c682  jz      short loc_18006C6A6
0x18006c684  lea     rcx, [rbp+0F0h+var_100]
0x18006c688  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006c68d  mov     qword ptr [rbp+0F0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18006c691  lea     rax, [rbp+0F0h+SystemTimeAsFileTime]
0x18006c695  mov     qword ptr [rsp+1F0h+percentComplete], rax
0x18006c69a  lea     rdx, byte_180129CD1
0x18006c6a1  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006c6a6  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006c6ab  lea     rbx, [rax+0A0h]
0x18006c6b2  lea     rdx, [rbp+0F0h+var_100]
0x18006c6b6  mov     rcx, rbx
0x18006c6b9  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006c6be  mov     rcx, rbx
0x18006c6c1  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006c6c6  nop
0x18006c6c7  lea     rcx, [rbp+0F0h+var_100]
0x18006c6cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c6d0  nop
0x18006c6d1  lea     rcx, [rbp+0F0h+var_E0]
0x18006c6d5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c6da  nop
0x18006c6db  mov     r14b, byte ptr [rsp+1F0h+var_190+1]
0x18006c6e0  lea     rcx, [rbp+0F0h+var_C0]
0x18006c6e4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c6e9  mov     edx, 1
0x18006c6ee  add     r15, rdx
0x18006c6f1  mov     eax, [rdi]
0x18006c6f3  cmp     r15, rax
0x18006c6f6  jb      loc_18006C38A
0x18006c6fc  mov     r15d, dword ptr [rsp+1F0h+var_180]
0x18006c701  mov     rsi, [rbp+0F0h+var_150]
0x18006c705  mov     r13, [rbp+0F0h+var_168]
0x18006c709  xor     ebx, ebx
0x18006c70b  jmp     short loc_18006C712
0x18006c70d  mov     edx, 1
0x18006c712  cmp     [r13+0], rbx
0x18006c716  jz      loc_18006C87B
0x18006c71c  mov     rcx, [rsp+1F0h+var_178]
0x18006c721  xorps   xmm0, xmm0
0x18006c724  test    rcx, rcx
0x18006c727  js      short loc_18006C730
0x18006c729  cvtsi2sd xmm0, rcx
0x18006c72e  jmp     short loc_18006C745
0x18006c730  mov     rax, rcx
0x18006c733  shr     rax, 1
  ... truncated ...
```
