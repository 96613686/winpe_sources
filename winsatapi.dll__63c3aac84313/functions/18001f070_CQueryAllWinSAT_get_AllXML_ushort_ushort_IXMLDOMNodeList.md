# CQueryAllWinSAT::get_AllXML(ushort *,ushort *,IXMLDOMNodeList * *)

- ea: `0x18001f070`
- end: `0x18001f473`
- name: `?get_AllXML@CQueryAllWinSAT@@UEAAJPEAG0PEAPEAUIXMLDOMNodeList@@@Z`
- size: `1027`
- prototype: `__int64 __fastcall(CQueryAllWinSAT *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMNodeList **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001a34`
- `0x1800043a0`
- `0x180004a48`
- `0x180005394`
- `0x180006070`
- `0x180006c60`
- `0x1800071d0`
- `0x180007220`
- `0x18000e864`
- `0x18001e9c4`
- `0x18001ee18`
- `0x18001f070`
- `0x18002c5d4`
- `0x18002d0c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001f15b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f1c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f289`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f3a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f40e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f15b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f1c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f289`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f3a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f40e`

## pseudocode

```c
__int64 __fastcall CQueryAllWinSAT::get_AllXML(
        CQueryAllWinSAT *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNodeList **a4)
{
  int v4; // esi
  __int64 result; // rax
  int WinSATDataStoreDir; // ebx
  CSupportErrorInfo *v9; // rcx
  bool v10; // r9
  __int64 v11; // rcx
  int AllWinSATAssessmentFileNames; // ebx
  char v13; // bl
  mlib *v14; // rcx
  unsigned __int16 v15; // r9
  const unsigned __int16 *v16; // rax
  CSupportErrorInfo *v17; // rcx
  bool v18; // r9
  __int64 v19; // rcx
  int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rbx
  mlib *v23; // rcx
  unsigned __int16 v24; // r9
  const unsigned __int16 *v25; // rax
  CSupportErrorInfo *v26; // rcx
  bool v27; // r9
  __int64 v28; // rcx
  const unsigned __int16 *v29; // rdx
  HINSTANCE v30; // [rsp+20h] [rbp-98h]
  HINSTANCE v31; // [rsp+20h] [rbp-98h]
  __int64 *v32; // [rsp+30h] [rbp-88h] BYREF
  __int128 v33; // [rsp+38h] [rbp-80h] BYREF
  __int64 v34; // [rsp+48h] [rbp-70h]
  __int64 v35; // [rsp+50h] [rbp-68h] BYREF
  struct HINSTANCE__ v36[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v37; // [rsp+60h] [rbp-58h] BYREF
  __int64 *v38[2]; // [rsp+68h] [rbp-50h] BYREF
  __int64 v39; // [rsp+78h] [rbp-40h] BYREF
  const unsigned __int16 *v40; // [rsp+80h] [rbp-38h]
  __int64 v41; // [rsp+D8h] [rbp+20h] BYREF

  v38[1] = (__int64 *)-2LL;
  v4 = (int)a4;
  if ( !a4 )
    return 2147500037LL;
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v37);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v36);
    v35 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v41,
      260);
    WinSATDataStoreDir = DataStoreReader::GetWinSATDataStoreDir(&v41);
    if ( WinSATDataStoreDir >= 0 )
    {
      v33 = 0;
      v34 = 0;
      AllWinSATAssessmentFileNames = DataStoreReader::GetAllWinSATAssessmentFileNames(&v41, &v33);
      if ( AllWinSATAssessmentFileNames >= 0 )
      {
        if ( *((_QWORD *)&v33 + 1) == (_QWORD)v33 )
        {
          if ( (_QWORD)v33 )
          {
            std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
              v11,
              v33,
              *((_QWORD *)&v33 + 1));
            operator delete((void *)v33);
            v33 = 0;
            v34 = 0;
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v41);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v36);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v37);
          result = 2147745810LL;
        }
        else
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v32,
            L"WinsatAssessments");
          v13 = mlib::XmlDOM::LoadManyFilesIntoOneDocument(&v32, &v33, &v35);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v32);
          if ( v13 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v38,
              a3);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v32,
              a2);
            v20 = mlib::XmlDOM::SelectXml(v35, (unsigned int)&v32, (unsigned int)v38, v4, (__int64)v36);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v32);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v38);
            if ( v20 >= 0 )
            {
              if ( (_QWORD)v33 )
              {
                std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                  v21,
                  v33,
                  *((_QWORD *)&v33 + 1));
                operator delete((void *)v33);
                v33 = 0;
                v34 = 0;
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v41);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v36);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v37);
              result = 0;
            }
            else
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                (__int64 *)&v32,
                1024);
              v22 = *(_QWORD *)(*(_QWORD *)&v36[0].unused + 24LL);
              v25 = mlib::MUIStr_(v23, (const char *)0x238, 110, v24, v31);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
                &v32,
                v25,
                v22);
              CSupportErrorInfo::SetErrorInfo(
                v26,
                (const unsigned __int16 *)v32[3],
                &IID_IQueryAllWinSATAssessments,
                v27);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v32);
              if ( (_QWORD)v33 )
              {
                std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                  v28,
                  v33,
                  *((_QWORD *)&v33 + 1));
                operator delete((void *)v33);
                v33 = 0;
                v34 = 0;
              }
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v41);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v36);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v37);
              result = 2147500037LL;
            }
          }
          else
          {
            v16 = mlib::MUIStr_(v14, (const char *)0x22C, 109, v15, v30);
            CSupportErrorInfo::SetErrorInfo(v17, v16, &IID_IQueryAllWinSATAssessments, v18);
            if ( (_QWORD)v33 )
            {
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
                v19,
                v33,
                *((_QWORD *)&v33 + 1));
              operator delete((void *)v33);
              v33 = 0;
              v34 = 0;
            }
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v41);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v36);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v37);
            result = 2147549183LL;
          }
        }
      }
      else
      {
        if ( (_QWORD)v33 )
        {
          std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
            v11,
            v33,
            *((_QWORD *)&v33 + 1));
          operator delete((void *)v33);
          v33 = 0;
          v34 = 0;
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v41);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v36);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v37);
        result = (unsigned int)AllWinSATAssessmentFileNames;
      }
    }
    else
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v41);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v36);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v37);
      result = (unsigned int)WinSATDataStoreDir;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( mlib::MSError v39 )
  {
    v29 = &String2;
    if ( v40 )
      v29 = v40;
    CSupportErrorInfo::SetErrorInfo(v9, v29, &IID_IQueryAllWinSATAssessments, v10);
    mlib::MSError::~MSError((mlib::MSError *)&v39);
    return 2147500037LL;
  }
  catch ( mlib::MUIError )
  {
    CSupportErrorInfo::SetErrorInfo(v9, L"Cannot load string from resouce.", &IID_IQueryAllWinSATAssessments, v10);
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
0x18001f070  push    rbx
0x18001f072  push    rsi
0x18001f073  push    rdi
0x18001f074  push    r14
0x18001f076  sub     rsp, 98h
0x18001f07d  mov     [rsp+0B8h+var_48], 0FFFFFFFFFFFFFFFEh
0x18001f086  mov     rsi, r9
0x18001f089  mov     rdi, r8
0x18001f08c  mov     r14, rdx
0x18001f08f  test    r9, r9
0x18001f092  jnz     short loc_18001F09E
0x18001f094  mov     eax, 80004005h
0x18001f099  jmp     loc_18001F464
0x18001f09e  lea     rcx, [rsp+0B8h+var_58]
0x18001f0a3  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18001f0a8  nop
0x18001f0a9  lea     rcx, [rsp+0B8h+var_60]
0x18001f0ae  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18001f0b3  nop
0x18001f0b4  mov     [rsp+0B8h+var_68], 0
0x18001f0bd  mov     edx, 104h
0x18001f0c2  lea     rcx, [rsp+0B8h+arg_18]
0x18001f0ca  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001f0cf  nop
0x18001f0d0  lea     rcx, [rsp+0B8h+arg_18]
0x18001f0d8  call    ?GetWinSATDataStoreDir@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; DataStoreReader::GetWinSATDataStoreDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x18001f0dd  mov     ebx, eax
0x18001f0df  test    eax, eax
0x18001f0e1  jns     short loc_18001F118
0x18001f0e3  lea     rcx, [rsp+0B8h+arg_18]
0x18001f0eb  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f0f0  nop
0x18001f0f1  lea     rcx, [rsp+0B8h+var_68]
0x18001f0f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f0fb  nop
0x18001f0fc  lea     rcx, [rsp+0B8h+var_60]
0x18001f101  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f106  nop
0x18001f107  lea     rcx, [rsp+0B8h+var_58]
0x18001f10c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f111  mov     eax, ebx
0x18001f113  jmp     loc_18001F464
0x18001f118  xorps   xmm0, xmm0
0x18001f11b  movdqu  [rsp+0B8h+var_80], xmm0
0x18001f121  mov     [rsp+0B8h+var_70], 0
0x18001f12a  lea     rdx, [rsp+0B8h+var_80]
0x18001f12f  lea     rcx, [rsp+0B8h+arg_18]
0x18001f137  call    ?GetAllWinSATAssessmentFileNames@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@W4DataStoreID@@W4AssessmentTimeTaken@@@Z; DataStoreReader::GetAllWinSATAssessmentFileNames(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,DataStoreID,AssessmentTimeTaken)
0x18001f13c  mov     ebx, eax
0x18001f13e  test    eax, eax
0x18001f140  jns     short loc_18001F1A8
0x18001f142  mov     rdx, qword ptr [rsp+0B8h+var_80]
0x18001f147  test    rdx, rdx
0x18001f14a  jz      short loc_18001F173
0x18001f14c  mov     r8, qword ptr [rsp+0B8h+var_80+8]
0x18001f151  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f156  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x18001f15b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f161  xorps   xmm0, xmm0
0x18001f164  movdqu  [rsp+0B8h+var_80], xmm0
0x18001f16a  mov     [rsp+0B8h+var_70], 0
0x18001f173  lea     rcx, [rsp+0B8h+arg_18]
0x18001f17b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f180  nop
0x18001f181  lea     rcx, [rsp+0B8h+var_68]
0x18001f186  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f18b  nop
0x18001f18c  lea     rcx, [rsp+0B8h+var_60]
0x18001f191  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f196  nop
0x18001f197  lea     rcx, [rsp+0B8h+var_58]
0x18001f19c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f1a1  mov     eax, ebx
0x18001f1a3  jmp     loc_18001F464
0x18001f1a8  mov     r8, qword ptr [rsp+0B8h+var_80+8]
0x18001f1ad  mov     rdx, qword ptr [rsp+0B8h+var_80]
0x18001f1b2  cmp     r8, rdx
0x18001f1b5  jnz     short loc_18001F216
0x18001f1b7  test    rdx, rdx
0x18001f1ba  jz      short loc_18001F1DE
0x18001f1bc  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f1c1  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x18001f1c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f1cc  xorps   xmm0, xmm0
0x18001f1cf  movdqu  [rsp+0B8h+var_80], xmm0
0x18001f1d5  mov     [rsp+0B8h+var_70], 0
0x18001f1de  lea     rcx, [rsp+0B8h+arg_18]
0x18001f1e6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f1eb  nop
0x18001f1ec  lea     rcx, [rsp+0B8h+var_68]
0x18001f1f1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f1f6  nop
0x18001f1f7  lea     rcx, [rsp+0B8h+var_60]
0x18001f1fc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f201  nop
0x18001f202  lea     rcx, [rsp+0B8h+var_58]
0x18001f207  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f20c  mov     eax, 80040012h
0x18001f211  jmp     loc_18001F464
0x18001f216  lea     rdx, aWinsatassessme; "WinsatAssessments"
0x18001f21d  lea     rcx, [rsp+0B8h+var_88]
0x18001f222  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18001f227  nop
0x18001f228  lea     r8, [rsp+0B8h+var_68]
0x18001f22d  lea     rdx, [rsp+0B8h+var_80]
0x18001f232  lea     rcx, [rsp+0B8h+var_88]
0x18001f237  call    ?LoadManyFilesIntoOneDocument@XmlDOM@mlib@@SA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAPEAUIXMLDOMNode@@@Z; mlib::XmlDOM::LoadManyFilesIntoOneDocument(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> const &,IXMLDOMNode * *)
0x18001f23c  mov     bl, al
0x18001f23e  lea     rcx, [rsp+0B8h+var_88]
0x18001f243  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f248  test    bl, bl
0x18001f24a  jnz     loc_18001F2D9
0x18001f250  mov     edx, 22Ch; char *
0x18001f255  mov     r8d, 6Dh ; 'm'; int
0x18001f25b  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x18001f260  lea     r8, IID_IQueryAllWinSATAssessments; struct _GUID *
0x18001f267  mov     rdx, rax; unsigned __int16 *
0x18001f26a  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x18001f26f  nop
0x18001f270  mov     rdx, qword ptr [rsp+0B8h+var_80]
0x18001f275  test    rdx, rdx
0x18001f278  jz      short loc_18001F2A1
0x18001f27a  mov     r8, qword ptr [rsp+0B8h+var_80+8]
0x18001f27f  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f284  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x18001f289  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f28f  xorps   xmm0, xmm0
0x18001f292  movdqu  [rsp+0B8h+var_80], xmm0
0x18001f298  mov     [rsp+0B8h+var_70], 0
0x18001f2a1  lea     rcx, [rsp+0B8h+arg_18]
0x18001f2a9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f2ae  nop
0x18001f2af  lea     rcx, [rsp+0B8h+var_68]
0x18001f2b4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f2b9  nop
0x18001f2ba  lea     rcx, [rsp+0B8h+var_60]
0x18001f2bf  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f2c4  nop
0x18001f2c5  lea     rcx, [rsp+0B8h+var_58]
0x18001f2ca  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f2cf  mov     eax, 8000FFFFh
0x18001f2d4  jmp     loc_18001F464
0x18001f2d9  mov     rdx, rdi
0x18001f2dc  lea     rcx, [rsp+0B8h+var_50]
0x18001f2e1  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18001f2e6  nop
0x18001f2e7  mov     rdx, r14
0x18001f2ea  lea     rcx, [rsp+0B8h+var_88]
0x18001f2ef  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18001f2f4  nop
0x18001f2f5  lea     rax, [rsp+0B8h+var_60]
0x18001f2fa  mov     [rsp+0B8h+var_98], rax; HINSTANCE
0x18001f2ff  mov     r9, rsi
0x18001f302  lea     r8, [rsp+0B8h+var_50]
0x18001f307  lea     rdx, [rsp+0B8h+var_88]
0x18001f30c  mov     rcx, [rsp+0B8h+var_68]
0x18001f311  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f316  mov     ebx, eax
0x18001f318  lea     rcx, [rsp+0B8h+var_88]
0x18001f31d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f322  nop
0x18001f323  lea     rcx, [rsp+0B8h+var_50]
0x18001f328  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f32d  test    ebx, ebx
0x18001f32f  jns     loc_18001F3F5
0x18001f335  mov     edx, 400h
0x18001f33a  lea     rcx, [rsp+0B8h+var_88]
0x18001f33f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001f344  nop
0x18001f345  mov     rax, qword ptr [rsp+0B8h+var_60.unused]
0x18001f34a  mov     rbx, [rax+18h]
0x18001f34e  mov     edx, 238h; char *
0x18001f353  mov     r8d, 6Eh ; 'n'; int
0x18001f359  call    ?MUIStr_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@@Z; mlib::MUIStr_(char const *,int,ushort,HINSTANCE__ *)
0x18001f35e  mov     r8, rbx
0x18001f361  mov     rdx, rax
0x18001f364  lea     rcx, [rsp+0B8h+var_88]
0x18001f369  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x18001f36e  lea     r8, IID_IQueryAllWinSATAssessments; struct _GUID *
0x18001f375  mov     rdx, [rsp+0B8h+var_88]
0x18001f37a  mov     rdx, [rdx+18h]; unsigned __int16 *
0x18001f37e  call    ?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z; CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)
0x18001f383  nop
0x18001f384  lea     rcx, [rsp+0B8h+var_88]
0x18001f389  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f38e  nop
0x18001f38f  mov     rdx, qword ptr [rsp+0B8h+var_80]
0x18001f394  test    rdx, rdx
0x18001f397  jz      short loc_18001F3C0
0x18001f399  mov     r8, qword ptr [rsp+0B8h+var_80+8]
0x18001f39e  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f3a3  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x18001f3a8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f3ae  xorps   xmm0, xmm0
0x18001f3b1  movdqu  [rsp+0B8h+var_80], xmm0
0x18001f3b7  mov     [rsp+0B8h+var_70], 0
0x18001f3c0  lea     rcx, [rsp+0B8h+arg_18]
0x18001f3c8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f3cd  nop
0x18001f3ce  lea     rcx, [rsp+0B8h+var_68]
0x18001f3d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f3d8  nop
0x18001f3d9  lea     rcx, [rsp+0B8h+var_60]
0x18001f3de  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f3e3  nop
0x18001f3e4  lea     rcx, [rsp+0B8h+var_58]
0x18001f3e9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f3ee  mov     eax, 80004005h
0x18001f3f3  jmp     short loc_18001F464
0x18001f3f5  mov     rdx, qword ptr [rsp+0B8h+var_80]
0x18001f3fa  test    rdx, rdx
0x18001f3fd  jz      short loc_18001F426
0x18001f3ff  mov     r8, qword ptr [rsp+0B8h+var_80+8]
0x18001f404  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001f409  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x18001f40e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f414  xorps   xmm0, xmm0
0x18001f417  movdqu  [rsp+0B8h+var_80], xmm0
0x18001f41d  mov     [rsp+0B8h+var_70], 0
0x18001f426  lea     rcx, [rsp+0B8h+arg_18]
0x18001f42e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f433  nop
0x18001f434  lea     rcx, [rsp+0B8h+var_68]
0x18001f439  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f43e  nop
0x18001f43f  lea     rcx, [rsp+0B8h+var_60]
0x18001f444  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f449  nop
0x18001f44a  lea     rcx, [rsp+0B8h+var_58]
0x18001f44f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001f454  xor     eax, eax
0x18001f456  jmp     short loc_18001F464
0x18001f458  mov     eax, 8007000Eh
0x18001f45d  jmp     short loc_18001F464
0x18001f45f  mov     eax, 80004005h
0x18001f464  add     rsp, 98h
0x18001f46b  pop     r14
0x18001f46d  pop     rdi
0x18001f46e  pop     rsi
0x18001f46f  pop     rbx
0x18001f470  retn
0x18001f471  jmp     short loc_18001F45F
```
