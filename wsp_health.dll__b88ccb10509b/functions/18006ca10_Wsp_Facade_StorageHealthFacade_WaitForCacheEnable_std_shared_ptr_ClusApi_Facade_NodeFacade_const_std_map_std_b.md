# Wsp::Facade::StorageHealthFacade::WaitForCacheEnable(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18006ca10`
- end: `0x18006d18a`
- name: `?WaitForCacheEnable@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `1914`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
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
- `0x18000c9f0`
- `0x18000d618`
- `0x18000d69c`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000eebc`
- `0x18000f828`
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
- `0x180058d5c`
- `0x180058dd8`
- `0x180058e60`
- `0x18005d4cc`
- `0x18005ec50`
- `0x1800676c0`
- `0x180067eec`
- `0x18006ca10`
- `0x1800751e4`
- `0x180075210`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006cad2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006cae7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006cbfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006cad2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006cae7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006cbfa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006cff4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006cff4`

## string_xrefs

- `0x18006ca67`: `Wsp::Facade::StorageHealthFacade::WaitForCacheEnable`
- `0x18006d0d8`: `Wsp::Facade::StorageHealthFacade::WaitForCacheEnable`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Wsp::Facade::StorageHealthFacade::WaitForCacheEnable(
        __int64 a1,
        __int64 a2,
        __int64 **a3,
        Wsp::Facade::ResExtendedStatus *a4,
        const char *a5)
{
  __int64 v6; // r14
  std::_Ref_count_base *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int SblDiskState; // r15d
  ULONGLONG v11; // rbx
  __m128i si128; // xmm7
  unsigned int *v13; // rsi
  unsigned __int64 v14; // r13
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  ULONGLONG TickCount64; // rax
  struct cxl::TextWriter *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  char *v27; // rdi
  _WORD *v28; // rax
  __int16 v29; // dx
  struct cxl::TextWriter *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  char *v34; // rdi
  MI_Context **v35; // rsi
  double v36; // xmm0_8
  __int64 v37; // rcx
  double v38; // xmm1_8
  struct cxl::TextWriter *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  char *v45; // rdi
  const MI_Char *v46; // rax
  const MI_Char *percentComplete; // r8
  const MI_Char *v48; // r9
  __int64 v49; // rdx
  int v50; // eax
  Wsp::Facade::ResExtendedStatus *v51; // rbx
  __int64 v52; // rax
  unsigned int v53; // ebx
  MI_Uint32 secondsRemaining; // [rsp+30h] [rbp-D8h]
  __int64 v56; // [rsp+58h] [rbp-B0h] BYREF
  MI_Uint32 v57[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+68h] [rbp-A0h] BYREF
  const char *v59; // [rsp+70h] [rbp-98h] BYREF
  Wsp::Facade::ResExtendedStatus *v60; // [rsp+78h] [rbp-90h] BYREF
  std::_Ref_count_base *v61; // [rsp+80h] [rbp-88h]
  __int64 v62; // [rsp+88h] [rbp-80h] BYREF
  __int64 v63; // [rsp+90h] [rbp-78h]
  __int128 v64; // [rsp+98h] [rbp-70h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-60h]
  __int64 v66[3]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v67[3]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v68[32]; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v69; // [rsp+100h] [rbp-8h] BYREF
  __int64 v70; // [rsp+110h] [rbp+8h]
  __int64 v71; // [rsp+118h] [rbp+10h]
  _BYTE v72[32]; // [rsp+120h] [rbp+18h] BYREF
  _OWORD v73[2]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v74[32]; // [rsp+160h] [rbp+58h] BYREF

  v60 = a4;
  v6 = a2;
  v63 = a2;
  v59 = a5;
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v67[0]) = 2435;
    *(_QWORD *)v57 = "Wsp::Facade::StorageHealthFacade::WaitForCacheEnable";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_180129C83,
      (__int64)a3,
      (__int64)a4,
      v57);
  }
  std::vector<unsigned char>::vector<unsigned char>(v66, 1024);
  cxl::load_string(v74, qword_1801578A0, 3001);
  v64 = 0;
  v65 = 0;
  GetTickCount64();
  if ( a3[1] )
  {
    v11 = 10000 * GetTickCount64();
    *(_QWORD *)v57 = 0;
    v58 = 0;
    SblDiskState = Wsp::Facade::GetSblDiskState(v6, a3, v66);
    if ( SblDiskState >= 0 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        v13 = (unsigned int *)v66[0];
        v14 = 0;
        if ( *(_DWORD *)v66[0] )
        {
          do
          {
            v15 = 28 * v14;
            *(_OWORD *)v67 = *(_OWORD *)&v13[28 * v14 + 3];
            std::string::string(v68, "B");
            cxl::Guid::ToString((cxl::Guid *)v67);
            std::string::_Tidy_deallocate(v68);
            std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(
              a3,
              &v62,
              v72);
            v16 = v62;
            if ( (__int64 *)v62 != *a3 )
            {
              *(_DWORD *)(v62 + 228) = v13[v15 + 10];
              if ( v13[v15 + 10] == 3003 )
              {
                *(_BYTE *)(v16 + 226) = 1;
                v17 = ++v58;
              }
              else
              {
                v17 = v58;
              }
              LOBYTE(v56) = 0;
              v18 = v13[v15 + 10];
              if ( v18 && (v19 = v18 - 1001) != 0 && (v20 = v19 - 1) != 0 && ((v21 = v20 - 999) == 0 || v21 == 1002) )
              {
                TickCount64 = GetTickCount64();
                if ( 10000 * TickCount64 < v11 )
                {
                  std::wstring::wstring(v73, L"nowTicks >= startTicks is false");
                  cxl::Throw::AssertionFailed(v73);
                }
                if ( 10000 * TickCount64 - v11 >= 0x430E23400LL )
                {
                  LOBYTE(v56) = 1;
                  ++*(_QWORD *)v57;
                }
              }
              else
              {
                v58 = v17 + 1;
              }
              v69 = 0;
              v70 = 0;
              v71 = 7;
              LOWORD(v69) = 0;
              v23 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v68, &v69);
              LODWORD(v67[0]) = v13[v15 + 10];
              cxl::TextWriter::Write<wchar_t,char [53],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,bool>(
                v23,
                (__int64)&v13[v15 + 11],
                (__int64)&v13[v15 + 9],
                (__int64)v72,
                (__int64)&v13[v15 + 8] + 1,
                (__int64)&v13[v15 + 9],
                (__int64)v67,
                (__int64)&v13[v15 + 11],
                (__int64)&v13[v15 + 12],
                (__int64)&v56);
              std::wstring::wstring(v68, &v69);
              if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
              {
                v67[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                  v24,
                  (__int64)&word_180129BF6,
                  v25,
                  v26,
                  v67);
              }
              v27 = (char *)cxl::TraceManager::Instance() + 160;
              cxl::CxlTraits<std::wstring>::WriteTo(v27, v68);
              cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v27);
              std::wstring::_Tidy_deallocate(v68);
              if ( *(_QWORD *)&v13[v15 + 16]
                || *(_QWORD *)&v13[v15 + 18]
                || *(_QWORD *)&v13[v15 + 20]
                || *(_QWORD *)&v13[v15 + 22]
                || *(_QWORD *)&v13[v15 + 24]
                || *(_QWORD *)&v13[v15 + 26] )
              {
                v70 = 0;
                v28 = (_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v69);
                *v28 = v29;
                v30 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v68, &v69);
                cxl::TextWriter::Write<wchar_t,char [53],__int64,__int64,__int64,__int64,__int64,__int64>(
                  v30,
                  (__int64)&v13[v15 + 24],
                  (__int64)&v13[v15 + 22],
                  (__int64)&v13[v15 + 16],
                  (__int64)&v13[v15 + 18],
                  (__int64)&v13[v15 + 20],
                  (__int64)&v13[v15 + 22],
                  (__int64)&v13[v15 + 24],
                  (__int64)&v13[v15 + 26]);
                std::wstring::wstring(v68, &v69);
                if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
                {
                  v67[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                    v31,
                    (__int64)&word_180129C16,
                    v32,
                    v33,
                    v67);
                }
                v34 = (char *)cxl::TraceManager::Instance() + 160;
                cxl::CxlTraits<std::wstring>::WriteTo(v34, v68);
                cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v34);
                std::wstring::_Tidy_deallocate(v68);
              }
              std::wstring::_Tidy_deallocate(&v69);
            }
            std::wstring::_Tidy_deallocate(v72);
            ++v14;
          }
          while ( v14 < *v13 );
          v6 = v63;
        }
        v35 = (MI_Context **)v60;
        if ( *(_QWORD *)v60 )
        {
          if ( v58 < 0 )
            v36 = (double)(int)(v58 & 1 | ((unsigned __int64)v58 >> 1))
                + (double)(int)(v58 & 1 | ((unsigned __int64)v58 >> 1));
          else
            v36 = (double)(int)v58;
          v37 = (__int64)a3[1];
          if ( v37 < 0 )
            v38 = (double)(int)(v37 & 1 | ((unsigned __int64)v37 >> 1))
                + (double)(int)(v37 & 1 | ((unsigned __int64)v37 >> 1));
          else
            v38 = (double)(int)v37;
          floor((v36 / v38 * 0.8 + 0.1) * 100.0);
          v73[0] = 0;
          v73[1] = si128;
          LOWORD(v73[0]) = 0;
          v39 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v72, v73);
          LODWORD(v67[0]) = *((_DWORD *)a3 + 2);
          cxl::TextWriter::Write<wchar_t,char [53],unsigned __int64,unsigned long,unsigned __int64>(
            v39,
            v40,
            v41,
            (__int64)&v58,
            (__int64)v67,
            (__int64)v57);
          std::wstring::wstring(v72, v73);
          if ( (unsigned int)dword_18014B6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
          {
            v67[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v72);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
              v42,
              (__int64)&word_180129C36,
              v43,
              v44,
              v67);
          }
          v45 = (char *)cxl::TraceManager::Instance() + 120;
          cxl::CxlTraits<std::wstring>::WriteTo(v45, v72);
          cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v45);
          std::wstring::_Tidy_deallocate(v72);
          v46 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v74);
          MI_Context_WriteProgress(*v35, v46, percentComplete, v48, (MI_Uint32)percentComplete, secondsRemaining);
          std::wstring::_Tidy_deallocate(v73);
        }
        v7 = (std::_Ref_count_base *)(*(_QWORD *)v57 + v58);
        if ( (unsigned __int64)a3[1] <= *(_QWORD *)v57 + v58 )
          break;
        Sleep(0x1388u);
        *(_QWORD *)v57 = 0;
        v58 = 0;
        SblDiskState = Wsp::Facade::GetSblDiskState(v6, a3, v66);
        if ( SblDiskState < 0 )
          goto LABEL_61;
      }
      v49 = **a3;
      *(_QWORD *)v57 = v49;
      while ( !*(_BYTE *)(v49 + 25) )
      {
        if ( !*(_BYTE *)(v49 + 226) )
        {
          v50 = *(_DWORD *)(v49 + 228);
          if ( v50 == 2001 || v50 == 3003 )
          {
            SblDiskState = -2147023436;
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(&v64, v49 + 96);
          }
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(v57);
        v49 = *(_QWORD *)v57;
      }
      if ( SblDiskState < 0 )
      {
        std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v60);
        std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(v59, &v60);
        v51 = v60;
        Wsp::Facade::ResExtendedStatus::SetMessageId(v60, 0x8066u);
        *((_WORD *)v51 + 76) = 1;
        v52 = std::vector<std::wstring>::vector<std::wstring>(v67, &v64);
        Wsp::Facade::ResExtendedStatus::SetMessageArguments(v51, v52);
        v7 = v61;
        if ( v61 )
          std::_Ref_count_base::_Decref(v61);
      }
    }
  }
  else
  {
    SblDiskState = 0;
  }
LABEL_61:
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v67[0]) = 2600;
    v59 = "Wsp::Facade::StorageHealthFacade::WaitForCacheEnable";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v7,
      (__int64)&word_180129C56,
      v8,
      v9,
      &v59);
  }
  v53 = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)SblDiskState);
  std::vector<std::wstring>::_Tidy(&v64);
  std::wstring::_Tidy_deallocate(v74);
  std::vector<unsigned char>::_Tidy(v66);
  return v53;
}

```

## disassembly

```asm
0x18006ca10  mov     rax, rsp
0x18006ca13  mov     [rax+8], rbx
0x18006ca17  push    rbp
0x18006ca18  push    rsi
0x18006ca19  push    rdi
0x18006ca1a  push    r12
0x18006ca1c  push    r13
0x18006ca1e  push    r14
0x18006ca20  push    r15
0x18006ca22  lea     rbp, [rax-0D8h]
0x18006ca29  sub     rsp, 1A0h
0x18006ca30  movaps  xmmword ptr [rax-48h], xmm6
0x18006ca34  movaps  xmmword ptr [rax-58h], xmm7
0x18006ca38  mov     rax, cs:__security_cookie
0x18006ca3f  xor     rax, rsp
0x18006ca42  mov     [rbp+0D0h+var_58], rax
0x18006ca46  mov     [rsp+1D0h+var_160], r9
0x18006ca4b  mov     r12, r8
0x18006ca4e  mov     r14, rdx
0x18006ca51  mov     [rbp+0D0h+var_148], rdx
0x18006ca55  mov     rax, [rbp+0D0h+arg_20]
0x18006ca5c  mov     [rsp+1D0h+var_168], rax
0x18006ca61  mov     eax, cs:dword_18014B6A8
0x18006ca67  lea     rbx, aWspFacadeStora_13; "Wsp::Facade::StorageHealthFacade::WaitF"...
0x18006ca6e  cmp     eax, 5
0x18006ca71  jbe     short loc_18006CA9E
0x18006ca73  mov     dword ptr [rbp+0D0h+var_110], 983h
0x18006ca7a  mov     qword ptr [rsp+1D0h+var_178], rbx
0x18006ca7f  lea     rax, [rbp+0D0h+var_110]
0x18006ca83  mov     qword ptr [rsp+1D0h+secondsRemaining], rax
0x18006ca88  lea     rax, [rsp+1D0h+var_178]
0x18006ca8d  mov     qword ptr [rsp+1D0h+percentComplete], rax
0x18006ca92  lea     rdx, byte_180129C83
0x18006ca99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006ca9e  mov     edx, 400h
0x18006caa3  lea     rcx, [rbp+0D0h+var_128]
0x18006caa7  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18006caac  nop
0x18006caad  mov     r8d, 0BB9h
0x18006cab3  mov     rdx, cs:qword_1801578A0
0x18006caba  lea     rcx, [rbp+0D0h+var_78]
0x18006cabe  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18006cac3  nop
0x18006cac4  xorps   xmm0, xmm0
0x18006cac7  movdqu  [rbp+0D0h+var_140], xmm0
0x18006cacc  xor     edi, edi
0x18006cace  mov     [rbp+0D0h+var_130], rdi
0x18006cad2  call    cs:__imp_GetTickCount64
0x18006cad8  cmp     [r12+8], rdi
0x18006cadd  jnz     short loc_18006CAE7
0x18006cadf  mov     r15d, edi
0x18006cae2  jmp     loc_18006D0DF
0x18006cae7  call    cs:__imp_GetTickCount64
0x18006caed  imul    rbx, rax, 2710h
0x18006caf4  mov     qword ptr [rsp+1D0h+var_178], rdi
0x18006caf9  mov     [rsp+1D0h+var_170], rdi
0x18006cafe  lea     r8, [rbp+0D0h+var_128]
0x18006cb02  mov     rdx, r12
0x18006cb05  mov     rcx, r14
0x18006cb08  call    ?GetSblDiskState@Facade@Wsp@@YAJAEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@4@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; Wsp::Facade::GetSblDiskState(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> const &,std::vector<uchar> &)
0x18006cb0d  mov     r15d, eax
0x18006cb10  test    eax, eax
0x18006cb12  js      loc_18006D0D8
0x18006cb18  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x18006cb20  mov     edx, 1
0x18006cb25  mov     rsi, [rbp+0D0h+var_128]
0x18006cb29  mov     r13, rdi
0x18006cb2c  cmp     [rsi], edi
0x18006cb2e  jbe     loc_18006CE72
0x18006cb34  imul    r14, r13, 70h ; 'p'
0x18006cb38  movups  xmm0, xmmword ptr [r14+rsi+0Ch]
0x18006cb3e  movdqu  xmmword ptr [rbp+0D0h+var_110], xmm0
0x18006cb43  lea     rdx, aB; "B"
0x18006cb4a  lea     rcx, [rbp+0D0h+var_F8]
0x18006cb4e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006cb53  nop
0x18006cb54  lea     r8, [rbp+0D0h+var_F8]
0x18006cb58  lea     rdx, [rbp+0D0h+var_B8]
0x18006cb5c  lea     rcx, [rbp+0D0h+var_110]
0x18006cb60  call    ?ToString@Guid@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; cxl::Guid::ToString(std::string const &)
0x18006cb65  nop
0x18006cb66  lea     rcx, [rbp+0D0h+var_F8]
0x18006cb6a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006cb6f  lea     r8, [rbp+0D0h+var_B8]
0x18006cb73  lea     rdx, [rbp+0D0h+var_150]
0x18006cb77  mov     rcx, r12
0x18006cb7a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(std::wstring const &)
0x18006cb7f  mov     rax, [rbp+0D0h+var_150]
0x18006cb83  cmp     rax, [r12]
0x18006cb87  jnz     short loc_18006CB8E
0x18006cb89  jmp     loc_18006CE52
0x18006cb8e  mov     ecx, [r14+rsi+28h]
0x18006cb93  mov     [rax+0E4h], ecx
0x18006cb99  mov     r8d, 1
0x18006cb9f  cmp     dword ptr [r14+rsi+28h], 0BBBh
0x18006cba8  jnz     short loc_18006CBC0
0x18006cbaa  mov     [rax+0E2h], r8b
0x18006cbb1  mov     rdx, [rsp+1D0h+var_170]
0x18006cbb6  add     rdx, r8
0x18006cbb9  mov     [rsp+1D0h+var_170], rdx
0x18006cbbe  jmp     short loc_18006CBC5
0x18006cbc0  mov     rdx, [rsp+1D0h+var_170]
0x18006cbc5  mov     byte ptr [rsp+1D0h+var_180], dil
0x18006cbca  mov     ecx, [r14+rsi+28h]
0x18006cbcf  test    ecx, ecx
0x18006cbd1  jz      short loc_18006CC32
0x18006cbd3  sub     ecx, 3E9h
0x18006cbd9  jz      short loc_18006CC32
0x18006cbdb  sub     ecx, 1
0x18006cbde  jz      short loc_18006CC32
0x18006cbe0  sub     ecx, 3E7h
0x18006cbe6  jz      short loc_18006CBFA
0x18006cbe8  sub     ecx, 3E8h
0x18006cbee  jz      short loc_18006CC32
0x18006cbf0  sub     ecx, 1
0x18006cbf3  jz      short loc_18006CC32
0x18006cbf5  sub     ecx, 1
0x18006cbf8  jnz     short loc_18006CC32
0x18006cbfa  call    cs:__imp_GetTickCount64
0x18006cc00  imul    rcx, rax, 2710h
0x18006cc07  cmp     rcx, rbx
0x18006cc0a  jb      loc_18006D16F
0x18006cc10  sub     rcx, rbx
0x18006cc13  mov     rax, 430E23400h
0x18006cc1d  cmp     rcx, rax
0x18006cc20  jb      short loc_18006CC3A
0x18006cc22  mov     eax, 1
0x18006cc27  mov     byte ptr [rsp+1D0h+var_180], al
0x18006cc2b  add     qword ptr [rsp+1D0h+var_178], rax
0x18006cc30  jmp     short loc_18006CC3A
0x18006cc32  add     rdx, r8
0x18006cc35  mov     [rsp+1D0h+var_170], rdx
0x18006cc3a  xorps   xmm0, xmm0
0x18006cc3d  movups  [rbp+0D0h+var_D8], xmm0
0x18006cc41  mov     [rbp+0D0h+var_C8], rdi
0x18006cc45  mov     [rbp+0D0h+var_C0], 7
0x18006cc4d  mov     word ptr [rbp+0D0h+var_D8], di
0x18006cc51  lea     rdx, [rbp+0D0h+var_D8]
0x18006cc55  lea     rcx, [rbp+0D0h+var_F8]
0x18006cc59  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006cc5e  nop
0x18006cc5f  mov     ecx, [r14+rsi+28h]
0x18006cc64  mov     dword ptr [rbp+0D0h+var_110], ecx
0x18006cc67  lea     rcx, [rsi+30h]
0x18006cc6b  add     rcx, r14
0x18006cc6e  lea     rdx, [rsi+2Ch]
0x18006cc72  add     rdx, r14
0x18006cc75  lea     r8, [rsi+24h]
0x18006cc79  add     r8, r14
0x18006cc7c  lea     r9, [rsi+21h]
0x18006cc80  add     r9, r14
0x18006cc83  lea     r10, [rsp+1D0h+var_180]
0x18006cc88  mov     [rsp+1D0h+var_188], r10; __int64
0x18006cc8d  mov     [rsp+1D0h+var_190], rcx; __int64
0x18006cc92  mov     [rsp+1D0h+var_198], rdx; __int64
0x18006cc97  lea     rcx, [rbp+0D0h+var_110]
0x18006cc9b  mov     [rsp+1D0h+var_1A0], rcx; __int64
0x18006cca0  mov     qword ptr [rsp+1D0h+secondsRemaining], r8; __int64
0x18006cca5  mov     qword ptr [rsp+1D0h+percentComplete], r9; __int64
0x18006ccaa  lea     r9, [rbp+0D0h+var_B8]
0x18006ccae  mov     rcx, rax; struct cxl::TextWriter *
0x18006ccb1  call    ??$Write@_W$$BY0DF@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_N@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBEAEBK44AEBW4S2DCacheMode@@AEB_N@Z; cxl::TextWriter::Write<wchar_t,char [53],std::wstring,uchar,ulong,ulong,ulong,S2DCacheMode,bool>(wchar_t const *,char const (&)[53],std::wstring const &,uchar const &,ulong const &,ulong const &,ulong const &,S2DCacheMode const &,bool const &)
0x18006ccb6  nop
0x18006ccb7  lea     rdx, [rbp+0D0h+var_D8]
0x18006ccbb  lea     rcx, [rbp+0D0h+var_F8]
0x18006ccbf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006ccc4  nop
0x18006ccc5  mov     eax, cs:dword_18014B6A8
0x18006cccb  cmp     eax, 5
0x18006ccce  jbe     short loc_18006CD07
0x18006ccd0  mov     edx, 4000h
0x18006ccd5  lea     rcx, dword_18014B6A8
0x18006ccdc  call    _tlgKeywordOn
0x18006cce1  test    al, al
0x18006cce3  jz      short loc_18006CD07
0x18006cce5  lea     rcx, [rbp+0D0h+var_F8]
0x18006cce9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ccee  mov     [rbp+0D0h+var_110], rax
0x18006ccf2  lea     rax, [rbp+0D0h+var_110]
0x18006ccf6  mov     qword ptr [rsp+1D0h+percentComplete], rax
0x18006ccfb  lea     rdx, word_180129BF6
0x18006cd02  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006cd07  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006cd0c  lea     rdi, [rax+0A0h]
0x18006cd13  lea     rdx, [rbp+0D0h+var_F8]
0x18006cd17  mov     rcx, rdi
0x18006cd1a  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006cd1f  mov     rcx, rdi
0x18006cd22  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006cd27  nop
0x18006cd28  lea     rcx, [rbp+0D0h+var_F8]
0x18006cd2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006cd31  lea     rdi, [r14+rsi]
0x18006cd35  xor     edx, edx
0x18006cd37  cmp     [rdi+40h], rdx
0x18006cd3b  jnz     short loc_18006CD64
0x18006cd3d  cmp     [r14+rsi+48h], rdx
0x18006cd42  jnz     short loc_18006CD64
0x18006cd44  cmp     [r14+rsi+50h], rdx
0x18006cd49  jnz     short loc_18006CD64
0x18006cd4b  cmp     [r14+rsi+58h], rdx
0x18006cd50  jnz     short loc_18006CD64
0x18006cd52  cmp     [r14+rsi+60h], rdx
0x18006cd57  jnz     short loc_18006CD64
0x18006cd59  cmp     [r14+rsi+68h], rdx
0x18006cd5e  jz      loc_18006CE46
0x18006cd64  mov     [rbp+0D0h+var_C8], rdx
0x18006cd68  lea     rcx, [rbp+0D0h+var_D8]
0x18006cd6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006cd71  mov     [rax], dx
0x18006cd74  lea     rdx, [rbp+0D0h+var_D8]
0x18006cd78  lea     rcx, [rbp+0D0h+var_F8]
0x18006cd7c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006cd81  nop
0x18006cd82  lea     rcx, [rsi+68h]
0x18006cd86  add     rcx, r14
0x18006cd89  lea     rdx, [rsi+60h]
0x18006cd8d  add     rdx, r14
0x18006cd90  lea     r8, [rsi+58h]
0x18006cd94  add     r8, r14
0x18006cd97  lea     r10, [rsi+50h]
0x18006cd9b  add     r10, r14
0x18006cd9e  lea     r11, [rsi+48h]
0x18006cda2  add     r11, r14
0x18006cda5  mov     [rsp+1D0h+var_190], rcx; __int64
0x18006cdaa  mov     [rsp+1D0h+var_198], rdx; __int64
0x18006cdaf  mov     [rsp+1D0h+var_1A0], r8; __int64
0x18006cdb4  mov     qword ptr [rsp+1D0h+secondsRemaining], r10; __int64
0x18006cdb9  mov     qword ptr [rsp+1D0h+percentComplete], r11; __int64
0x18006cdbe  lea     r9, [rdi+40h]
0x18006cdc2  mov     rcx, rax; struct cxl::TextWriter *
0x18006cdc5  call    ??$Write@_W$$BY0DF@D_J_J_J_J_J_J@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEB_J22222@Z; cxl::TextWriter::Write<wchar_t,char [53],__int64,__int64,__int64,__int64,__int64,__int64>(wchar_t const *,char const (&)[53],__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &)
0x18006cdca  nop
0x18006cdcb  lea     rdx, [rbp+0D0h+var_D8]
0x18006cdcf  lea     rcx, [rbp+0D0h+var_F8]
0x18006cdd3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006cdd8  nop
0x18006cdd9  mov     eax, cs:dword_18014B6A8
0x18006cddf  cmp     eax, 5
0x18006cde2  jbe     short loc_18006CE1B
0x18006cde4  mov     edx, 4000h
0x18006cde9  lea     rcx, dword_18014B6A8
0x18006cdf0  call    _tlgKeywordOn
0x18006cdf5  test    al, al
0x18006cdf7  jz      short loc_18006CE1B
0x18006cdf9  lea     rcx, [rbp+0D0h+var_F8]
0x18006cdfd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ce02  mov     [rbp+0D0h+var_110], rax
0x18006ce06  lea     rax, [rbp+0D0h+var_110]
0x18006ce0a  mov     qword ptr [rsp+1D0h+percentComplete], rax
0x18006ce0f  lea     rdx, word_180129C16
0x18006ce16  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006ce1b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006ce20  lea     rdi, [rax+0A0h]
0x18006ce27  lea     rdx, [rbp+0D0h+var_F8]
0x18006ce2b  mov     rcx, rdi
0x18006ce2e  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006ce33  mov     rcx, rdi
0x18006ce36  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006ce3b  nop
0x18006ce3c  lea     rcx, [rbp+0D0h+var_F8]
0x18006ce40  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ce45  nop
0x18006ce46  lea     rcx, [rbp+0D0h+var_D8]
0x18006ce4a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ce4f  nop
0x18006ce50  xor     edi, edi
0x18006ce52  lea     rcx, [rbp+0D0h+var_B8]
0x18006ce56  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ce5b  mov     edx, 1
0x18006ce60  add     r13, rdx
0x18006ce63  mov     eax, [rsi]
0x18006ce65  cmp     r13, rax
0x18006ce68  jb      loc_18006CB34
0x18006ce6e  mov     r14, [rbp+0D0h+var_148]
0x18006ce72  mov     rsi, [rsp+1D0h+var_160]
0x18006ce77  cmp     [rsi], rdi
0x18006ce7a  jz      loc_18006CFDE
0x18006ce80  mov     rcx, [rsp+1D0h+var_170]
0x18006ce85  xorps   xmm0, xmm0
0x18006ce88  test    rcx, rcx
0x18006ce8b  js      short loc_18006CE94
0x18006ce8d  cvtsi2sd xmm0, rcx
0x18006ce92  jmp     short loc_18006CEA9
0x18006ce94  mov     rax, rcx
0x18006ce97  shr     rax, 1
0x18006ce9a  and     rcx, rdx
0x18006ce9d  or      rax, rcx
0x18006cea0  cvtsi2sd xmm0, rax
0x18006cea5  addsd   xmm0, xmm0
0x18006cea9  mov     rcx, [r12+8]
0x18006ceae  xorps   xmm1, xmm1
0x18006ceb1  test    rcx, rcx
0x18006ceb4  js      short loc_18006CEBD
0x18006ceb6  cvtsi2sd xmm1, rcx
0x18006cebb  jmp     short loc_18006CED2
0x18006cebd  mov     rax, rcx
0x18006cec0  shr     rax, 1
0x18006cec3  and     rcx, rdx
0x18006cec6  or      rax, rcx
  ... truncated ...
```
