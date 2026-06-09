# Wsp::Facade::StorageHealthFacade::WaitForCacheEnable(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18006e26c`
- end: `0x18006e9ff`
- name: `?WaitForCacheEnable@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `1939`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
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
- `0x18000cd9c`
- `0x18000da34`
- `0x18000dab8`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f34c`
- `0x18000fcec`
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
- `0x18005a4cc`
- `0x18005a54c`
- `0x18005a5d4`
- `0x18005ec5c`
- `0x180060414`
- `0x180068eec`
- `0x18006971c`
- `0x18006e26c`
- `0x180077038`
- `0x180077064`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006e32e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006e349`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006e462`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006e32e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006e349`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006e462`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006e862`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006e862`

## string_xrefs

- `0x18006e2c3`: `Wsp::Facade::StorageHealthFacade::WaitForCacheEnable`
- `0x18006e94c`: `Wsp::Facade::StorageHealthFacade::WaitForCacheEnable`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Wsp::Facade::StorageHealthFacade::WaitForCacheEnable(
        int a1,
        __int64 a2,
        __int64 **a3,
        Wsp::Facade::ResExtendedStatus *a4,
        const char *a5)
{
  __int64 v6; // r14
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
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
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  char *v27; // rdi
  _WORD *v28; // rax
  __int16 v29; // dx
  struct cxl::TextWriter *v30; // rax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  char *v34; // rdi
  MI_Context **v35; // rsi
  double v36; // xmm0_8
  __int64 v37; // rcx
  double v38; // xmm1_8
  struct cxl::TextWriter *v39; // rax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  char *v43; // rdi
  const MI_Char *v44; // rax
  const MI_Char *percentComplete; // r8
  const MI_Char *v46; // r9
  __int64 v47; // rdx
  int v48; // eax
  Wsp::Facade::ResExtendedStatus *v49; // rbx
  __int64 v50; // rax
  unsigned int v51; // ebx
  MI_Uint32 secondsRemaining; // [rsp+30h] [rbp-D8h]
  __int64 v54; // [rsp+58h] [rbp-B0h] BYREF
  MI_Uint32 v55[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+68h] [rbp-A0h]
  const char *v57; // [rsp+70h] [rbp-98h] BYREF
  Wsp::Facade::ResExtendedStatus *v58; // [rsp+78h] [rbp-90h] BYREF
  std::_Ref_count_base *v59; // [rsp+80h] [rbp-88h]
  __int64 v60; // [rsp+88h] [rbp-80h] BYREF
  __int64 v61; // [rsp+90h] [rbp-78h]
  __int128 v62; // [rsp+98h] [rbp-70h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-60h]
  __int64 v64[3]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v65[3]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v66[32]; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v67; // [rsp+100h] [rbp-8h] BYREF
  __int64 v68; // [rsp+110h] [rbp+8h]
  __int64 v69; // [rsp+118h] [rbp+10h]
  _BYTE v70[32]; // [rsp+120h] [rbp+18h] BYREF
  _OWORD v71[2]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v72[32]; // [rsp+160h] [rbp+58h] BYREF

  v58 = a4;
  v6 = a2;
  v61 = a2;
  v57 = a5;
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v65[0]) = 2435;
    *(_QWORD *)v55 = "Wsp::Facade::StorageHealthFacade::WaitForCacheEnable";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_18012BC8B,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v55,
      (__int64)v65);
  }
  std::vector<unsigned char>::vector<unsigned char>(v64, 1024);
  cxl::load_string(v72, qword_1801599A0, 3001);
  v62 = 0;
  v63 = 0;
  GetTickCount64();
  if ( a3[1] )
  {
    v11 = 10000 * GetTickCount64();
    *(_QWORD *)v55 = 0;
    v56 = 0;
    SblDiskState = Wsp::Facade::GetSblDiskState(v6, a3, v64);
    if ( SblDiskState >= 0 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        v13 = (unsigned int *)v64[0];
        v14 = 0;
        if ( *(_DWORD *)v64[0] )
        {
          do
          {
            v15 = 28 * v14;
            *(_OWORD *)v65 = *(_OWORD *)&v13[28 * v14 + 3];
            std::string::string(v66, "B");
            cxl::Guid::ToString((cxl::Guid *)v65);
            std::string::_Tidy_deallocate(v66);
            std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(
              a3,
              &v60,
              v70);
            v16 = v60;
            if ( (__int64 *)v60 != *a3 )
            {
              *(_DWORD *)(v60 + 228) = v13[v15 + 10];
              if ( v13[v15 + 10] == 3003 )
              {
                *(_BYTE *)(v16 + 226) = 1;
                v17 = ++v56;
              }
              else
              {
                v17 = v56;
              }
              LOBYTE(v54) = 0;
              v18 = v13[v15 + 10];
              if ( v18 && (v19 = v18 - 1001) != 0 && (v20 = v19 - 1) != 0 && ((v21 = v20 - 999) == 0 || v21 == 1002) )
              {
                TickCount64 = GetTickCount64();
                if ( 10000 * TickCount64 < v11 )
                {
                  std::wstring::wstring(v71, L"nowTicks >= startTicks is false");
                  cxl::Throw::AssertionFailed(v71);
                }
                if ( 10000 * TickCount64 - v11 >= 0x430E23400LL )
                {
                  LOBYTE(v54) = 1;
                  ++*(_QWORD *)v55;
                }
              }
              else
              {
                v56 = v17 + 1;
              }
              v67 = 0;
              v68 = 0;
              v69 = 7;
              LOWORD(v67) = 0;
              v23 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v66, &v67);
              LODWORD(v65[0]) = v13[v15 + 10];
              cxl::TextWriter::Write<wchar_t,char [53],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,bool>(
                v23,
                (__int64)&v13[v15 + 8] + 1,
                (__int64)&v13[v15 + 9],
                (__int64)v65,
                (__int64)&v13[v15 + 11],
                (__int64)&v13[v15 + 12],
                (__int64)&v54);
              std::wstring::wstring(v66, &v67);
              if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
              {
                v65[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v66);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                  v24,
                  (unsigned int)byte_18012BC2B,
                  v25,
                  v26,
                  (__int64)v65);
              }
              v27 = (char *)cxl::TraceManager::Instance() + 160;
              cxl::CxlTraits<std::wstring>::WriteTo(v27, v66);
              cxl::TextWriter::operator<<<cxl::ENDL>(v27);
              std::wstring::_Tidy_deallocate(v66);
              if ( *(_QWORD *)&v13[v15 + 16]
                || *(_QWORD *)&v13[v15 + 18]
                || *(_QWORD *)&v13[v15 + 20]
                || *(_QWORD *)&v13[v15 + 22]
                || *(_QWORD *)&v13[v15 + 24]
                || *(_QWORD *)&v13[v15 + 26] )
              {
                v68 = 0;
                v28 = (_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v67);
                *v28 = v29;
                v30 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v66, &v67);
                cxl::TextWriter::Write<wchar_t,char [53],__int64,__int64,__int64,__int64,__int64,__int64>(
                  v30,
                  (__int64)&v13[v15 + 18],
                  (__int64)&v13[v15 + 20],
                  (__int64)&v13[v15 + 22],
                  (__int64)&v13[v15 + 24],
                  (__int64)&v13[v15 + 26]);
                std::wstring::wstring(v66, &v67);
                if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
                {
                  v65[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v66);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                    v31,
                    (unsigned int)byte_18012BC4B,
                    v32,
                    v33,
                    (__int64)v65);
                }
                v34 = (char *)cxl::TraceManager::Instance() + 160;
                cxl::CxlTraits<std::wstring>::WriteTo(v34, v66);
                cxl::TextWriter::operator<<<cxl::ENDL>(v34);
                std::wstring::_Tidy_deallocate(v66);
              }
              std::wstring::_Tidy_deallocate(&v67);
            }
            std::wstring::_Tidy_deallocate(v70);
            ++v14;
          }
          while ( v14 < *v13 );
          v6 = v61;
        }
        v35 = (MI_Context **)v58;
        if ( *(_QWORD *)v58 )
        {
          if ( v56 < 0 )
            v36 = (double)(int)(v56 & 1 | ((unsigned __int64)v56 >> 1))
                + (double)(int)(v56 & 1 | ((unsigned __int64)v56 >> 1));
          else
            v36 = (double)(int)v56;
          v37 = (__int64)a3[1];
          if ( v37 < 0 )
            v38 = (double)(int)(v37 & 1 | ((unsigned __int64)v37 >> 1))
                + (double)(int)(v37 & 1 | ((unsigned __int64)v37 >> 1));
          else
            v38 = (double)(int)v37;
          floor((v36 / v38 * 0.8 + 0.1) * 100.0);
          v71[0] = 0;
          v71[1] = si128;
          LOWORD(v71[0]) = 0;
          v39 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v70, v71);
          LODWORD(v65[0]) = *((_DWORD *)a3 + 2);
          cxl::TextWriter::Write<wchar_t,char [53],unsigned __int64,unsigned long,unsigned __int64>(
            v39,
            (__int64)v65,
            (__int64)v55);
          std::wstring::wstring(v70, v71);
          if ( (unsigned int)dword_18014D6A8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
          {
            v65[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v70);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
              v40,
              (unsigned int)byte_18012BC6B,
              v41,
              v42,
              (__int64)v65);
          }
          v43 = (char *)cxl::TraceManager::Instance() + 120;
          cxl::CxlTraits<std::wstring>::WriteTo(v43, v70);
          cxl::TextWriter::operator<<<cxl::ENDL>(v43);
          std::wstring::_Tidy_deallocate(v70);
          v44 = (const MI_Char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v72);
          MI_Context_WriteProgress(*v35, v44, percentComplete, v46, (MI_Uint32)percentComplete, secondsRemaining);
          std::wstring::_Tidy_deallocate(v71);
        }
        v7 = v55[0] + v56;
        if ( (unsigned __int64)a3[1] <= *(_QWORD *)v55 + v56 )
          break;
        Sleep(0x1388u);
        *(_QWORD *)v55 = 0;
        v56 = 0;
        SblDiskState = Wsp::Facade::GetSblDiskState(v6, a3, v64);
        if ( SblDiskState < 0 )
          goto LABEL_61;
      }
      v47 = **a3;
      *(_QWORD *)v55 = v47;
      while ( !*(_BYTE *)(v47 + 25) )
      {
        if ( !*(_BYTE *)(v47 + 226) )
        {
          v48 = *(_DWORD *)(v47 + 228);
          if ( v48 == 2001 || v48 == 3003 )
          {
            SblDiskState = -2147023436;
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(&v62, v47 + 96);
          }
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(v55);
        v47 = *(_QWORD *)v55;
      }
      if ( SblDiskState < 0 )
      {
        std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v58);
        std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(v57, &v58);
        v49 = v58;
        Wsp::Facade::ResExtendedStatus::SetMessageId(v58, 0x8066u);
        *((_WORD *)v49 + 76) = 1;
        v50 = std::vector<std::wstring>::vector<std::wstring>(v65, &v62);
        Wsp::Facade::ResExtendedStatus::SetMessageArguments(v49, v50);
        v7 = (int)v59;
        if ( v59 )
          std::_Ref_count_base::_Decref(v59);
      }
    }
  }
  else
  {
    SblDiskState = 0;
  }
LABEL_61:
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v65[0]) = 2600;
    v57 = "Wsp::Facade::StorageHealthFacade::WaitForCacheEnable";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&word_18012BBFE,
      v8,
      v9,
      (__int64)&v57,
      (__int64)v65);
  }
  v51 = Wsp::MiSpaceAdapter::SmRCFromHResult((unsigned int)SblDiskState);
  std::vector<std::wstring>::_Tidy(&v62);
  std::wstring::_Tidy_deallocate(v72);
  std::vector<unsigned char>::_Tidy(v64);
  return v51;
}

```

## disassembly

```asm
0x18006e26c  mov     rax, rsp
0x18006e26f  mov     [rax+8], rbx
0x18006e273  push    rbp
0x18006e274  push    rsi
0x18006e275  push    rdi
0x18006e276  push    r12
0x18006e278  push    r13
0x18006e27a  push    r14
0x18006e27c  push    r15
0x18006e27e  lea     rbp, [rax-0D8h]
0x18006e285  sub     rsp, 1A0h
0x18006e28c  movaps  xmmword ptr [rax-48h], xmm6
0x18006e290  movaps  xmmword ptr [rax-58h], xmm7
0x18006e294  mov     rax, cs:__security_cookie
0x18006e29b  xor     rax, rsp
0x18006e29e  mov     [rbp+0D0h+var_58], rax
0x18006e2a2  mov     [rsp+1D0h+var_160], r9
0x18006e2a7  mov     r12, r8
0x18006e2aa  mov     r14, rdx
0x18006e2ad  mov     [rbp+0D0h+var_148], rdx
0x18006e2b1  mov     rax, [rbp+0D0h+arg_20]
0x18006e2b8  mov     [rsp+1D0h+var_168], rax
0x18006e2bd  mov     eax, cs:dword_18014D6A8
0x18006e2c3  lea     rbx, aWspFacadeStora_13; "Wsp::Facade::StorageHealthFacade::WaitF"...
0x18006e2ca  cmp     eax, 5
0x18006e2cd  jbe     short loc_18006E2FA
0x18006e2cf  mov     dword ptr [rbp+0D0h+var_110], 983h
0x18006e2d6  mov     qword ptr [rsp+1D0h+var_178], rbx
0x18006e2db  lea     rax, [rbp+0D0h+var_110]
0x18006e2df  mov     qword ptr [rsp+1D0h+secondsRemaining], rax
0x18006e2e4  lea     rax, [rsp+1D0h+var_178]
0x18006e2e9  mov     qword ptr [rsp+1D0h+percentComplete], rax
0x18006e2ee  lea     rdx, byte_18012BC8B
0x18006e2f5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006e2fa  mov     edx, 400h
0x18006e2ff  lea     rcx, [rbp+0D0h+var_128]
0x18006e303  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18006e308  nop
0x18006e309  mov     r8d, 0BB9h
0x18006e30f  mov     rdx, cs:qword_1801599A0
0x18006e316  lea     rcx, [rbp+0D0h+var_78]
0x18006e31a  call    ?load_string@cxl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; cxl::load_string(HINSTANCE__ *,uint)
0x18006e31f  nop
0x18006e320  xorps   xmm0, xmm0
0x18006e323  movdqu  [rbp+0D0h+var_140], xmm0
0x18006e328  xor     edi, edi
0x18006e32a  mov     [rbp+0D0h+var_130], rdi
0x18006e32e  call    cs:__imp_GetTickCount64
0x18006e335  nop     dword ptr [rax+rax+00h]
0x18006e33a  cmp     [r12+8], rdi
0x18006e33f  jnz     short loc_18006E349
0x18006e341  mov     r15d, edi
0x18006e344  jmp     loc_18006E953
0x18006e349  call    cs:__imp_GetTickCount64
0x18006e350  nop     dword ptr [rax+rax+00h]
0x18006e355  imul    rbx, rax, 2710h
0x18006e35c  mov     qword ptr [rsp+1D0h+var_178], rdi
0x18006e361  mov     [rsp+1D0h+var_170], rdi
0x18006e366  lea     r8, [rbp+0D0h+var_128]
0x18006e36a  mov     rdx, r12
0x18006e36d  mov     rcx, r14
0x18006e370  call    ?GetSblDiskState@Facade@Wsp@@YAJAEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@4@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; Wsp::Facade::GetSblDiskState(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> const &,std::vector<uchar> &)
0x18006e375  mov     r15d, eax
0x18006e378  test    eax, eax
0x18006e37a  js      loc_18006E94C
0x18006e380  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x18006e388  mov     edx, 1
0x18006e38d  mov     rsi, [rbp+0D0h+var_128]
0x18006e391  mov     r13, rdi
0x18006e394  cmp     [rsi], edi
0x18006e396  jbe     loc_18006E6E0
0x18006e39c  imul    r14, r13, 70h ; 'p'
0x18006e3a0  movups  xmm0, xmmword ptr [r14+rsi+0Ch]
0x18006e3a6  movdqu  xmmword ptr [rbp+0D0h+var_110], xmm0
0x18006e3ab  lea     rdx, aB; "B"
0x18006e3b2  lea     rcx, [rbp+0D0h+var_F8]
0x18006e3b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18006e3bb  nop
0x18006e3bc  lea     r8, [rbp+0D0h+var_F8]
0x18006e3c0  lea     rdx, [rbp+0D0h+var_B8]
0x18006e3c4  lea     rcx, [rbp+0D0h+var_110]
0x18006e3c8  call    ?ToString@Guid@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; cxl::Guid::ToString(std::string const &)
0x18006e3cd  nop
0x18006e3ce  lea     rcx, [rbp+0D0h+var_F8]
0x18006e3d2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006e3d7  lea     r8, [rbp+0D0h+var_B8]
0x18006e3db  lea     rdx, [rbp+0D0h+var_150]
0x18006e3df  mov     rcx, r12
0x18006e3e2  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSPACES_StoragePool@mismpstorage@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,mismpstorage::SPACES_StoragePool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,mismpstorage::SPACES_StoragePool>>,0>>::find(std::wstring const &)
0x18006e3e7  mov     rax, [rbp+0D0h+var_150]
0x18006e3eb  cmp     rax, [r12]
0x18006e3ef  jnz     short loc_18006E3F6
0x18006e3f1  jmp     loc_18006E6C0
0x18006e3f6  mov     ecx, [r14+rsi+28h]
0x18006e3fb  mov     [rax+0E4h], ecx
0x18006e401  mov     r8d, 1
0x18006e407  cmp     dword ptr [r14+rsi+28h], 0BBBh
0x18006e410  jnz     short loc_18006E428
0x18006e412  mov     [rax+0E2h], r8b
0x18006e419  mov     rdx, [rsp+1D0h+var_170]
0x18006e41e  add     rdx, r8
0x18006e421  mov     [rsp+1D0h+var_170], rdx
0x18006e426  jmp     short loc_18006E42D
0x18006e428  mov     rdx, [rsp+1D0h+var_170]
0x18006e42d  mov     byte ptr [rsp+1D0h+var_180], dil
0x18006e432  mov     ecx, [r14+rsi+28h]
0x18006e437  test    ecx, ecx
0x18006e439  jz      short loc_18006E4A0
0x18006e43b  sub     ecx, 3E9h
0x18006e441  jz      short loc_18006E4A0
0x18006e443  sub     ecx, 1
0x18006e446  jz      short loc_18006E4A0
0x18006e448  sub     ecx, 3E7h
0x18006e44e  jz      short loc_18006E462
0x18006e450  sub     ecx, 3E8h
0x18006e456  jz      short loc_18006E4A0
0x18006e458  sub     ecx, 1
0x18006e45b  jz      short loc_18006E4A0
0x18006e45d  sub     ecx, 1
0x18006e460  jnz     short loc_18006E4A0
0x18006e462  call    cs:__imp_GetTickCount64
0x18006e469  nop     dword ptr [rax+rax+00h]
0x18006e46e  imul    rcx, rax, 2710h
0x18006e475  cmp     rcx, rbx
0x18006e478  jb      loc_18006E9E4
0x18006e47e  sub     rcx, rbx
0x18006e481  mov     rax, 430E23400h
0x18006e48b  cmp     rcx, rax
0x18006e48e  jb      short loc_18006E4A8
0x18006e490  mov     eax, 1
0x18006e495  mov     byte ptr [rsp+1D0h+var_180], al
0x18006e499  add     qword ptr [rsp+1D0h+var_178], rax
0x18006e49e  jmp     short loc_18006E4A8
0x18006e4a0  add     rdx, r8
0x18006e4a3  mov     [rsp+1D0h+var_170], rdx
0x18006e4a8  xorps   xmm0, xmm0
0x18006e4ab  movups  [rbp+0D0h+var_D8], xmm0
0x18006e4af  mov     [rbp+0D0h+var_C8], rdi
0x18006e4b3  mov     [rbp+0D0h+var_C0], 7
0x18006e4bb  mov     word ptr [rbp+0D0h+var_D8], di
0x18006e4bf  lea     rdx, [rbp+0D0h+var_D8]
0x18006e4c3  lea     rcx, [rbp+0D0h+var_F8]
0x18006e4c7  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006e4cc  nop
0x18006e4cd  mov     ecx, [r14+rsi+28h]
0x18006e4d2  mov     dword ptr [rbp+0D0h+var_110], ecx
0x18006e4d5  lea     rcx, [rsi+30h]
0x18006e4d9  add     rcx, r14
0x18006e4dc  lea     rdx, [rsi+2Ch]
0x18006e4e0  add     rdx, r14
0x18006e4e3  lea     r8, [rsi+24h]
0x18006e4e7  add     r8, r14
0x18006e4ea  lea     r9, [rsi+21h]
0x18006e4ee  add     r9, r14
0x18006e4f1  lea     r10, [rsp+1D0h+var_180]
0x18006e4f6  mov     [rsp+1D0h+var_188], r10; __int64
0x18006e4fb  mov     [rsp+1D0h+var_190], rcx; __int64
0x18006e500  mov     [rsp+1D0h+var_198], rdx; __int64
0x18006e505  lea     rcx, [rbp+0D0h+var_110]
0x18006e509  mov     [rsp+1D0h+var_1A0], rcx; __int64
0x18006e50e  mov     qword ptr [rsp+1D0h+secondsRemaining], r8; __int64
0x18006e513  mov     qword ptr [rsp+1D0h+percentComplete], r9; __int64
0x18006e518  lea     r9, [rbp+0D0h+var_B8]
0x18006e51c  mov     rcx, rax; struct cxl::TextWriter *
0x18006e51f  call    ??$Write@_W$$BY0DF@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_N@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBEAEBK44AEBW4S2DCacheMode@@AEB_N@Z; cxl::TextWriter::Write<wchar_t,char [53],std::wstring,uchar,ulong,ulong,ulong,S2DCacheMode,bool>(wchar_t const *,char const (&)[53],std::wstring const &,uchar const &,ulong const &,ulong const &,ulong const &,S2DCacheMode const &,bool const &)
0x18006e524  nop
0x18006e525  lea     rdx, [rbp+0D0h+var_D8]
0x18006e529  lea     rcx, [rbp+0D0h+var_F8]
0x18006e52d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006e532  nop
0x18006e533  mov     eax, cs:dword_18014D6A8
0x18006e539  cmp     eax, 5
0x18006e53c  jbe     short loc_18006E575
0x18006e53e  mov     edx, 4000h
0x18006e543  lea     rcx, dword_18014D6A8
0x18006e54a  call    _tlgKeywordOn
0x18006e54f  test    al, al
0x18006e551  jz      short loc_18006E575
0x18006e553  lea     rcx, [rbp+0D0h+var_F8]
0x18006e557  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006e55c  mov     [rbp+0D0h+var_110], rax
0x18006e560  lea     rax, [rbp+0D0h+var_110]
0x18006e564  mov     qword ptr [rsp+1D0h+percentComplete], rax
0x18006e569  lea     rdx, byte_18012BC2B
0x18006e570  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006e575  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006e57a  lea     rdi, [rax+0A0h]
0x18006e581  lea     rdx, [rbp+0D0h+var_F8]
0x18006e585  mov     rcx, rdi
0x18006e588  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006e58d  mov     rcx, rdi
0x18006e590  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006e595  nop
0x18006e596  lea     rcx, [rbp+0D0h+var_F8]
0x18006e59a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e59f  lea     rdi, [r14+rsi]
0x18006e5a3  xor     edx, edx
0x18006e5a5  cmp     [rdi+40h], rdx
0x18006e5a9  jnz     short loc_18006E5D2
0x18006e5ab  cmp     [r14+rsi+48h], rdx
0x18006e5b0  jnz     short loc_18006E5D2
0x18006e5b2  cmp     [r14+rsi+50h], rdx
0x18006e5b7  jnz     short loc_18006E5D2
0x18006e5b9  cmp     [r14+rsi+58h], rdx
0x18006e5be  jnz     short loc_18006E5D2
0x18006e5c0  cmp     [r14+rsi+60h], rdx
0x18006e5c5  jnz     short loc_18006E5D2
0x18006e5c7  cmp     [r14+rsi+68h], rdx
0x18006e5cc  jz      loc_18006E6B4
0x18006e5d2  mov     [rbp+0D0h+var_C8], rdx
0x18006e5d6  lea     rcx, [rbp+0D0h+var_D8]
0x18006e5da  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006e5df  mov     [rax], dx
0x18006e5e2  lea     rdx, [rbp+0D0h+var_D8]
0x18006e5e6  lea     rcx, [rbp+0D0h+var_F8]
0x18006e5ea  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006e5ef  nop
0x18006e5f0  lea     rcx, [rsi+68h]
0x18006e5f4  add     rcx, r14
0x18006e5f7  lea     rdx, [rsi+60h]
0x18006e5fb  add     rdx, r14
0x18006e5fe  lea     r8, [rsi+58h]
0x18006e602  add     r8, r14
0x18006e605  lea     r10, [rsi+50h]
0x18006e609  add     r10, r14
0x18006e60c  lea     r11, [rsi+48h]
0x18006e610  add     r11, r14
0x18006e613  mov     [rsp+1D0h+var_190], rcx; __int64
0x18006e618  mov     [rsp+1D0h+var_198], rdx; __int64
0x18006e61d  mov     [rsp+1D0h+var_1A0], r8; __int64
0x18006e622  mov     qword ptr [rsp+1D0h+secondsRemaining], r10; __int64
0x18006e627  mov     qword ptr [rsp+1D0h+percentComplete], r11; __int64
0x18006e62c  lea     r9, [rdi+40h]
0x18006e630  mov     rcx, rax; struct cxl::TextWriter *
0x18006e633  call    ??$Write@_W$$BY0DF@D_J_J_J_J_J_J@TextWriter@cxl@@QEAAXPEB_WAEAY0DF@$$CBDAEB_J22222@Z; cxl::TextWriter::Write<wchar_t,char [53],__int64,__int64,__int64,__int64,__int64,__int64>(wchar_t const *,char const (&)[53],__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &,__int64 const &)
0x18006e638  nop
0x18006e639  lea     rdx, [rbp+0D0h+var_D8]
0x18006e63d  lea     rcx, [rbp+0D0h+var_F8]
0x18006e641  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006e646  nop
0x18006e647  mov     eax, cs:dword_18014D6A8
0x18006e64d  cmp     eax, 5
0x18006e650  jbe     short loc_18006E689
0x18006e652  mov     edx, 4000h
0x18006e657  lea     rcx, dword_18014D6A8
0x18006e65e  call    _tlgKeywordOn
0x18006e663  test    al, al
0x18006e665  jz      short loc_18006E689
0x18006e667  lea     rcx, [rbp+0D0h+var_F8]
0x18006e66b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006e670  mov     [rbp+0D0h+var_110], rax
0x18006e674  lea     rax, [rbp+0D0h+var_110]
0x18006e678  mov     qword ptr [rsp+1D0h+percentComplete], rax
0x18006e67d  lea     rdx, byte_18012BC4B
0x18006e684  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006e689  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006e68e  lea     rdi, [rax+0A0h]
0x18006e695  lea     rdx, [rbp+0D0h+var_F8]
0x18006e699  mov     rcx, rdi
0x18006e69c  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006e6a1  mov     rcx, rdi
0x18006e6a4  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006e6a9  nop
0x18006e6aa  lea     rcx, [rbp+0D0h+var_F8]
0x18006e6ae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e6b3  nop
0x18006e6b4  lea     rcx, [rbp+0D0h+var_D8]
0x18006e6b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e6bd  nop
0x18006e6be  xor     edi, edi
0x18006e6c0  lea     rcx, [rbp+0D0h+var_B8]
0x18006e6c4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e6c9  mov     edx, 1
0x18006e6ce  add     r13, rdx
0x18006e6d1  mov     eax, [rsi]
0x18006e6d3  cmp     r13, rax
0x18006e6d6  jb      loc_18006E39C
0x18006e6dc  mov     r14, [rbp+0D0h+var_148]
0x18006e6e0  mov     rsi, [rsp+1D0h+var_160]
0x18006e6e5  cmp     [rsi], rdi
0x18006e6e8  jz      loc_18006E84C
0x18006e6ee  mov     rcx, [rsp+1D0h+var_170]
0x18006e6f3  xorps   xmm0, xmm0
0x18006e6f6  test    rcx, rcx
0x18006e6f9  js      short loc_18006E702
0x18006e6fb  cvtsi2sd xmm0, rcx
0x18006e700  jmp     short loc_18006E717
0x18006e702  mov     rax, rcx
0x18006e705  shr     rax, 1
0x18006e708  and     rcx, rdx
0x18006e70b  or      rax, rcx
0x18006e70e  cvtsi2sd xmm0, rax
0x18006e713  addsd   xmm0, xmm0
0x18006e717  mov     rcx, [r12+8]
0x18006e71c  xorps   xmm1, xmm1
0x18006e71f  test    rcx, rcx
0x18006e722  js      short loc_18006E72B
0x18006e724  cvtsi2sd xmm1, rcx
0x18006e729  jmp     short loc_18006E740
0x18006e72b  mov     rax, rcx
  ... truncated ...
```
