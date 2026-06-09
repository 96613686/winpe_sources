# CQueryWinSAT::get_XML(ushort *,ushort *,IXMLDOMNodeList * *)

- ea: `0x180001a70`
- end: `0x18000208f`
- name: `?get_XML@CQueryWinSAT@@UEAAJPEAG0PEAPEAUIXMLDOMNodeList@@@Z`
- size: `1567`
- prototype: `__int64 __fastcall(CQueryWinSAT *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMNodeList **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001a34`
- `0x180001a70`
- `0x180003230`
- `0x1800043a0`
- `0x180004a48`
- `0x180005370`
- `0x180005394`
- `0x180005570`
- `0x180006070`
- `0x180006c60`
- `0x1800071d0`
- `0x180007220`
- `0x18000e864`
- `0x18001e9c4`
- `0x18001ee18`
- `0x18002c5d4`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001b84`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001bfa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001cc0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001d64`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e29`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e32`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e58`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e61`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001ef0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001f6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001f73`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001f93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001fc5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001fce`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002026`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000202f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002055`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000205e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001b84`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001bfa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001cc0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001d64`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e29`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e32`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e58`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001e61`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001ef0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001f6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001f73`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001f93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001fc5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001fce`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002026`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000202f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002055`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000205e`

## pseudocode

```c
__int64 __fastcall CQueryWinSAT::get_XML(
        CQueryWinSAT *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNodeList **a4)
{
  int v4; // esi
  __int64 result; // rax
  __int64 *v8; // rax
  int WinSATDataStoreDir; // ebx
  CSupportErrorInfo *v10; // rcx
  bool v11; // r9
  __int64 v12; // rcx
  int AllWinSATAssessmentFileNames; // ebx
  mlib *v14; // rcx
  unsigned __int16 v15; // r9
  const unsigned __int16 *v16; // rax
  CSupportErrorInfo *v17; // rcx
  bool v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rbx
  int v21; // edi
  __int64 v22; // rcx
  int v23; // esi
  __int64 *v24; // rcx
  bool v25; // zf
  __int64 *v26; // rdi
  void *v27; // rcx
  __int64 *v28; // rdi
  void *v29; // rcx
  __int64 v30; // rbx
  mlib *v31; // rcx
  unsigned __int16 v32; // r9
  const unsigned __int16 *v33; // rax
  CSupportErrorInfo *v34; // rcx
  bool v35; // r9
  __int64 v36; // rcx
  void *v37; // rdi
  void *v38; // rcx
  __int64 *v39; // rdi
  void *v40; // rcx
  void *v41; // rbx
  void *v42; // rcx
  void *v43; // rbx
  void *v44; // rcx
  const unsigned __int16 *v45; // rdx
  HINSTANCE v46; // [rsp+20h] [rbp-98h]
  HINSTANCE v47; // [rsp+20h] [rbp-98h]
  __int128 v48; // [rsp+30h] [rbp-88h] BYREF
  __int64 v49; // [rsp+40h] [rbp-78h]
  __int64 *v50; // [rsp+48h] [rbp-70h] BYREF
  CSupportErrorInfo *v51; // [rsp+50h] [rbp-68h] BYREF
  __int64 (__fastcall ***v52)(_QWORD, GUID *, CSupportErrorInfo **); // [rsp+58h] [rbp-60h] BYREF
  _QWORD *v53; // [rsp+60h] [rbp-58h] BYREF
  __int64 *v54; // [rsp+68h] [rbp-50h] BYREF
  _QWORD v55[2]; // [rsp+70h] [rbp-48h] BYREF
  __int64 *v56[2]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v57; // [rsp+90h] [rbp-28h] BYREF
  const unsigned __int16 *v58; // [rsp+98h] [rbp-20h]
  _QWORD *v59; // [rsp+D8h] [rbp+20h] BYREF

  v56[1] = (__int64 *)-2LL;
  v4 = (int)a4;
  if ( !a4 )
    return 2147500037LL;
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v53);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v59);
    v52 = 0;
    v51 = 0;
    v8 = (__int64 *)mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v54 = v8;
    if ( v8 )
      v8 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v8,
             260);
    v50 = v8;
    WinSATDataStoreDir = DataStoreReader::GetWinSATDataStoreDir(&v50);
    if ( WinSATDataStoreDir >= 0 )
    {
      v48 = 0;
      v49 = 0;
      AllWinSATAssessmentFileNames = DataStoreReader::GetAllWinSATAssessmentFileNames(&v50, &v48);
      if ( AllWinSATAssessmentFileNames >= 0 )
      {
        if ( *((_QWORD *)&v48 + 1) == (_QWORD)v48 )
        {
          if ( (_QWORD)v48 )
          {
            std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
              v12,
              v48,
              *((_QWORD *)&v48 + 1));
            operator delete((void *)v48);
            v48 = 0;
            v49 = 0;
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v50);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v59);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v53);
          result = 2147745810LL;
        }
        else
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55);
          if ( (int)mlib::XmlDOM::LoadDocumentFromFile(v48, &v52, v55) >= 0 )
          {
            v20 = (__int64)v52;
            v21 = (**v52)(v52, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, &v51);
            if ( v21 >= 0 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v54,
                a3);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v56,
                a2);
              v23 = mlib::XmlDOM::SelectXml((_DWORD)v51, (unsigned int)v56, (unsigned int)&v54, v4, (__int64)&v59);
              v24 = v56[0];
              v25 = v56[0][2]-- == 1;
              if ( v25 )
              {
                v26 = v56[0];
                if ( v56[0] )
                {
                  v27 = (void *)v56[0][3];
                  if ( v27 )
                    operator delete(v27);
                  operator delete(v26);
                }
              }
              v25 = v54[2]-- == 1;
              if ( v25 )
              {
                v28 = v54;
                if ( v54 )
                {
                  v29 = (void *)v54[3];
                  if ( v29 )
                    operator delete(v29);
                  operator delete(v28);
                }
              }
              if ( v23 >= 0 )
              {
                v25 = (*(_QWORD *)(v55[0] + 16LL))-- == 1;
                if ( v25 )
                {
                  v37 = (void *)v55[0];
                  if ( v55[0] )
                  {
                    v38 = *(void **)(v55[0] + 24LL);
                    if ( v38 )
                      operator delete(v38);
                    operator delete(v37);
                  }
                }
                if ( (_QWORD)v48 )
                {
                  std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                    v24,
                    v48,
                    *((_QWORD *)&v48 + 1));
                  operator delete((void *)v48);
                  v48 = 0;
                  v49 = 0;
                }
                v39 = v50;
                v25 = v50[2]-- == 1;
                if ( v25 && v39 )
                {
                  v40 = (void *)v39[3];
                  if ( v40 )
                    operator delete(v40);
                  operator delete(v39);
                }
                v10 = v51;
                if ( v51 )
                  (*(void (__fastcall **)(CSupportErrorInfo *))(*(_QWORD *)v51 + 16LL))(v51);
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                v25 = v59[2]-- == 1;
                if ( v25 )
                {
                  v41 = v59;
                  if ( v59 )
                  {
                    v42 = (void *)v59[3];
                    if ( v42 )
                      operator delete(v42);
                    operator delete(v41);
                  }
                }
                v25 = v53[2]-- == 1;
                if ( v25 )
                {
                  v43 = v53;
                  if ( v53 )
                  {
                    v44 = (void *)v53[3];
                    if ( v44 )
                      operator delete(v44);
                    operator delete(v43);
                  }
                }
                result = 0;
              }
              else
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  (__int64 *)&v54,
                  1024);
                v30 = v59[3];
                v33 = mlib::MUIStr_(v31, (const char *)0x1D7, 110, v32, v47);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
                  &v54,
                  v33,
                  v30);
                CSupportErrorInfo::SetErrorInfo(
                  v34,
                  (const unsigned __int16 *)v54[3],
                  &IID_IQueryRecentWinSATAssessment,
                  v35);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v54);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v55);
                if ( (_QWORD)v48 )
                {
                  std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                    v36,
                    v48,
                    *((_QWORD *)&v48 + 1));
                  operator delete((void *)v48);
                  v48 = 0;
                  v49 = 0;
                }
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v50);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v59);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v53);
                result = 2147500037LL;
              }
            }
            else
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v55);
              if ( (_QWORD)v48 )
              {
                std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                  v22,
                  v48,
                  *((_QWORD *)&v48 + 1));
                operator delete((void *)v48);
                v48 = 0;
                v49 = 0;
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v50);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v59);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v53);
              result = (unsigned int)v21;
            }
          }
          else
          {
            v16 = mlib::MUIStr_(v14, (const char *)0x1C5, 109, v15, v46);
            CSupportErrorInfo::SetErrorInfo(v17, v16, &IID_IQueryRecentWinSATAssessment, v18);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v55);
            if ( (_QWORD)v48 )
            {
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                v19,
                v48,
                *((_QWORD *)&v48 + 1));
              operator delete((void *)v48);
              v48 = 0;
              v49 = 0;
            }
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v50);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v59);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v53);
            result = 2147549183LL;
          }
        }
      }
      else
      {
        if ( (_QWORD)v48 )
        {
          std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
            v12,
            v48,
            *((_QWORD *)&v48 + 1));
          operator delete((void *)v48);
          v48 = 0;
          v49 = 0;
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v50);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v59);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v53);
        result = (unsigned int)AllWinSATAssessmentFileNames;
      }
    }
    else
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v50);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v59);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v53);
      result = (unsigned int)WinSATDataStoreDir;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( mlib::MSError v57 )
  {
    v45 = &String2;
    if ( v58 )
      v45 = v58;
    CSupportErrorInfo::SetErrorInfo(v10, v45, &IID_IQueryAllWinSATAssessments, v11);
    mlib::MSError::~MSError((mlib::MSError *)&v57);
    return 2147500037LL;
  }
  catch ( mlib::MUIError )
  {
    CSupportErrorInfo::SetErrorInfo(v10, L"Cannot load string from resouce.", &IID_IQueryAllWinSATAssessments, v11);
    return 2147500037LL;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001a70  mov     rax, rsp
0x180001a73  push    rdi
0x180001a74  push    r14
0x180001a76  push    r15
0x180001a78  sub     rsp, 0A0h
0x180001a7f  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x180001a87  mov     [rax+8], rbx
0x180001a8b  mov     [rax+10h], rsi
0x180001a8f  mov     rsi, r9
0x180001a92  mov     r14, r8
0x180001a95  mov     r15, rdx
0x180001a98  test    r9, r9
0x180001a9b  jnz     short loc_180001AA7
0x180001a9d  mov     eax, 80004005h
0x180001aa2  jmp     loc_180002074
0x180001aa7  lea     rcx, [rsp+0B8h+var_58]
0x180001aac  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180001ab1  nop
0x180001ab2  lea     rcx, [rsp+0B8h+arg_18]
0x180001aba  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180001abf  nop
0x180001ac0  mov     [rsp+0B8h+var_60], 0
0x180001ac9  mov     [rsp+0B8h+var_68], 0
0x180001ad2  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x180001ad7  mov     [rsp+0B8h+var_50], rax
0x180001adc  test    rax, rax
0x180001adf  jz      short loc_180001AEF
0x180001ae1  mov     edx, 104h
0x180001ae6  mov     rcx, rax
0x180001ae9  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x180001aee  nop
0x180001aef  mov     [rsp+0B8h+var_70], rax
0x180001af4  lea     rcx, [rsp+0B8h+var_70]
0x180001af9  call    ?GetWinSATDataStoreDir@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; DataStoreReader::GetWinSATDataStoreDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180001afe  mov     ebx, eax
0x180001b00  test    eax, eax
0x180001b02  jns     short loc_180001B44
0x180001b04  lea     rcx, [rsp+0B8h+var_70]
0x180001b09  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001b0e  nop
0x180001b0f  lea     rcx, [rsp+0B8h+var_68]
0x180001b14  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001b19  nop
0x180001b1a  lea     rcx, [rsp+0B8h+var_60]
0x180001b1f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001b24  nop
0x180001b25  lea     rcx, [rsp+0B8h+arg_18]
0x180001b2d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001b32  nop
0x180001b33  lea     rcx, [rsp+0B8h+var_58]
0x180001b38  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001b3d  mov     eax, ebx
0x180001b3f  jmp     loc_180002074
0x180001b44  xorps   xmm0, xmm0
0x180001b47  movdqu  [rsp+0B8h+var_88], xmm0
0x180001b4d  mov     [rsp+0B8h+var_78], 0
0x180001b56  lea     rdx, [rsp+0B8h+var_88]
0x180001b5b  lea     rcx, [rsp+0B8h+var_70]
0x180001b60  call    ?GetAllWinSATAssessmentFileNames@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@W4DataStoreID@@W4AssessmentTimeTaken@@@Z; DataStoreReader::GetAllWinSATAssessmentFileNames(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,DataStoreID,AssessmentTimeTaken)
0x180001b65  mov     ebx, eax
0x180001b67  test    eax, eax
0x180001b69  jns     short loc_180001BDC
0x180001b6b  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001b70  test    rdx, rdx
0x180001b73  jz      short loc_180001B9C
0x180001b75  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001b7a  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001b7f  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001b84  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001b8a  xorps   xmm0, xmm0
0x180001b8d  movdqu  [rsp+0B8h+var_88], xmm0
0x180001b93  mov     [rsp+0B8h+var_78], 0
0x180001b9c  lea     rcx, [rsp+0B8h+var_70]
0x180001ba1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001ba6  nop
0x180001ba7  lea     rcx, [rsp+0B8h+var_68]
0x180001bac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001bb1  nop
0x180001bb2  lea     rcx, [rsp+0B8h+var_60]
0x180001bb7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001bbc  nop
0x180001bbd  lea     rcx, [rsp+0B8h+arg_18]
0x180001bc5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001bca  nop
0x180001bcb  lea     rcx, [rsp+0B8h+var_58]
0x180001bd0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001bd5  mov     eax, ebx
0x180001bd7  jmp     loc_180002074
0x180001bdc  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001be1  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001be6  cmp     r8, rdx
0x180001be9  jnz     short loc_180001C55
0x180001beb  test    rdx, rdx
0x180001bee  jz      short loc_180001C12
0x180001bf0  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001bf5  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001bfa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001c00  xorps   xmm0, xmm0
0x180001c03  movdqu  [rsp+0B8h+var_88], xmm0
0x180001c09  mov     [rsp+0B8h+var_78], 0
0x180001c12  lea     rcx, [rsp+0B8h+var_70]
0x180001c17  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001c1c  nop
0x180001c1d  lea     rcx, [rsp+0B8h+var_68]
0x180001c22  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001c27  nop
0x180001c28  lea     rcx, [rsp+0B8h+var_60]
0x180001c2d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001c32  nop
0x180001c33  lea     rcx, [rsp+0B8h+arg_18]
0x180001c3b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001c40  nop
0x180001c41  lea     rcx, [rsp+0B8h+var_58]
0x180001c46  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001c4b  mov     eax, 80040012h
0x180001c50  jmp     loc_180002074
0x180001c55  lea     rcx, [rsp+0B8h+var_48]
0x180001c5a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180001c5f  nop
0x180001c60  lea     r8, [rsp+0B8h+var_48]
0x180001c65  lea     rdx, [rsp+0B8h+var_60]
0x180001c6a  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001c6f  call    ?LoadDocumentFromFile@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMDocument2@@PEAV32@_N@Z; mlib::XmlDOM::LoadDocumentFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMDocument2 * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)
0x180001c74  test    eax, eax
0x180001c76  jns     loc_180001D1B
0x180001c7c  mov     edx, 1C5h; char *
0x180001c81  mov     r8d, 6Dh ; 'm'; int
0x180001c87  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x180001c8c  lea     r8, IID_IQueryRecentWinSATAssessment; struct _GUID *
0x180001c93  mov     rdx, rax; unsigned __int16 *
0x180001c96  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x180001c9b  nop
0x180001c9c  lea     rcx, [rsp+0B8h+var_48]
0x180001ca1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001ca6  nop
0x180001ca7  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001cac  test    rdx, rdx
0x180001caf  jz      short loc_180001CD8
0x180001cb1  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001cb6  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001cbb  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001cc0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001cc6  xorps   xmm0, xmm0
0x180001cc9  movdqu  [rsp+0B8h+var_88], xmm0
0x180001ccf  mov     [rsp+0B8h+var_78], 0
0x180001cd8  lea     rcx, [rsp+0B8h+var_70]
0x180001cdd  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001ce2  nop
0x180001ce3  lea     rcx, [rsp+0B8h+var_68]
0x180001ce8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001ced  nop
0x180001cee  lea     rcx, [rsp+0B8h+var_60]
0x180001cf3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001cf8  nop
0x180001cf9  lea     rcx, [rsp+0B8h+arg_18]
0x180001d01  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d06  nop
0x180001d07  lea     rcx, [rsp+0B8h+var_58]
0x180001d0c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d11  mov     eax, 8000FFFFh
0x180001d16  jmp     loc_180002074
0x180001d1b  mov     rbx, [rsp+0B8h+var_60]
0x180001d20  mov     rax, [rbx]
0x180001d23  lea     r8, [rsp+0B8h+var_68]
0x180001d28  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180001d2f  mov     rcx, rbx
0x180001d32  mov     rax, [rax]
0x180001d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3a  mov     edi, eax
0x180001d3c  test    eax, eax
0x180001d3e  jns     short loc_180001DBC
0x180001d40  lea     rcx, [rsp+0B8h+var_48]
0x180001d45  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d4a  nop
0x180001d4b  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001d50  test    rdx, rdx
0x180001d53  jz      short loc_180001D7C
0x180001d55  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001d5a  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001d5f  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001d64  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001d6a  xorps   xmm0, xmm0
0x180001d6d  movdqu  [rsp+0B8h+var_88], xmm0
0x180001d73  mov     [rsp+0B8h+var_78], 0
0x180001d7c  lea     rcx, [rsp+0B8h+var_70]
0x180001d81  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001d86  nop
0x180001d87  lea     rcx, [rsp+0B8h+var_68]
0x180001d8c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001d91  nop
0x180001d92  lea     rcx, [rsp+0B8h+var_60]
0x180001d97  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001d9c  nop
0x180001d9d  lea     rcx, [rsp+0B8h+arg_18]
0x180001da5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001daa  nop
0x180001dab  lea     rcx, [rsp+0B8h+var_58]
0x180001db0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001db5  mov     eax, edi
0x180001db7  jmp     loc_180002074
0x180001dbc  mov     rdx, r14
0x180001dbf  lea     rcx, [rsp+0B8h+var_50]
0x180001dc4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x180001dc9  nop
0x180001dca  mov     rdx, r15
0x180001dcd  lea     rcx, [rsp+0B8h+var_38]
0x180001dd5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x180001dda  nop
0x180001ddb  lea     rax, [rsp+0B8h+arg_18]
0x180001de3  mov     [rsp+0B8h+var_98], rax; HINSTANCE
0x180001de8  mov     r9, rsi
0x180001deb  lea     r8, [rsp+0B8h+var_50]
0x180001df0  lea     rdx, [rsp+0B8h+var_38]
0x180001df8  mov     rcx, [rsp+0B8h+var_68]
0x180001dfd  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001e02  mov     esi, eax
0x180001e04  mov     rcx, [rsp+0B8h+var_38]
0x180001e0c  sub     qword ptr [rcx+10h], 1
0x180001e11  jnz     short loc_180001E39
0x180001e13  mov     rdi, [rsp+0B8h+var_38]
0x180001e1b  test    rdi, rdi
0x180001e1e  jz      short loc_180001E39
0x180001e20  mov     rcx, [rdi+18h]
0x180001e24  test    rcx, rcx
0x180001e27  jz      short loc_180001E2F
0x180001e29  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001e2f  mov     rcx, rdi
0x180001e32  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001e38  nop
0x180001e39  mov     rax, [rsp+0B8h+var_50]
0x180001e3e  sub     qword ptr [rax+10h], 1
0x180001e43  jnz     short loc_180001E67
0x180001e45  mov     rdi, [rsp+0B8h+var_50]
0x180001e4a  test    rdi, rdi
0x180001e4d  jz      short loc_180001E67
0x180001e4f  mov     rcx, [rdi+18h]
0x180001e53  test    rcx, rcx
0x180001e56  jz      short loc_180001E5E
0x180001e58  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001e5e  mov     rcx, rdi
0x180001e61  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001e67  test    esi, esi
0x180001e69  jns     loc_180001F4B
0x180001e6f  mov     edx, 400h
0x180001e74  lea     rcx, [rsp+0B8h+var_50]
0x180001e79  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x180001e7e  nop
0x180001e7f  mov     rax, [rsp+0B8h+arg_18]
0x180001e87  mov     rbx, [rax+18h]
0x180001e8b  mov     edx, 1D7h; char *
0x180001e90  mov     r8d, 6Eh ; 'n'; int
0x180001e96  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x180001e9b  mov     r8, rbx
0x180001e9e  mov     rdx, rax
0x180001ea1  lea     rcx, [rsp+0B8h+var_50]
0x180001ea6  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x180001eab  lea     r8, IID_IQueryRecentWinSATAssessment; struct _GUID *
0x180001eb2  mov     rdx, [rsp+0B8h+var_50]
0x180001eb7  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180001ebb  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x180001ec0  nop
0x180001ec1  lea     rcx, [rsp+0B8h+var_50]
0x180001ec6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001ecb  nop
0x180001ecc  lea     rcx, [rsp+0B8h+var_48]
0x180001ed1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001ed6  nop
0x180001ed7  mov     rdx, qword ptr [rsp+0B8h+var_88]
0x180001edc  test    rdx, rdx
0x180001edf  jz      short loc_180001F08
0x180001ee1  mov     r8, qword ptr [rsp+0B8h+var_88+8]
0x180001ee6  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180001eeb  mov     rcx, qword ptr [rsp+0B8h+var_88]
0x180001ef0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001ef6  xorps   xmm0, xmm0
0x180001ef9  movdqu  [rsp+0B8h+var_88], xmm0
0x180001eff  mov     [rsp+0B8h+var_78], 0
0x180001f08  lea     rcx, [rsp+0B8h+var_70]
0x180001f0d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001f12  nop
0x180001f13  lea     rcx, [rsp+0B8h+var_68]
0x180001f18  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001f1d  nop
0x180001f1e  lea     rcx, [rsp+0B8h+var_60]
0x180001f23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001f28  nop
0x180001f29  lea     rcx, [rsp+0B8h+arg_18]
0x180001f31  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001f36  nop
0x180001f37  lea     rcx, [rsp+0B8h+var_58]
0x180001f3c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180001f41  mov     eax, 80004005h
0x180001f46  jmp     loc_180002074
0x180001f4b  mov     rax, [rsp+0B8h+var_48]
0x180001f50  sub     qword ptr [rax+10h], 1
0x180001f55  jnz     short loc_180001F7A
0x180001f57  mov     rdi, [rsp+0B8h+var_48]
0x180001f5c  test    rdi, rdi
0x180001f5f  jz      short loc_180001F7A
0x180001f61  mov     rcx, [rdi+18h]
  ... truncated ...
```
