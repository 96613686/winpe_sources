# TaskDefinitionImpl::LoadFromXmlText(int)

- ea: `0x1800074d0`
- end: `0x180007e85`
- name: `?LoadFromXmlText@TaskDefinitionImpl@@AEAAJH@Z`
- size: `2485`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006618`
- `0x180006c90`

## callees

- `0x180001880`
- `0x180005bac`
- `0x180005c50`
- `0x1800074d0`
- `0x180007e90`
- `0x180008750`
- `0x180009150`
- `0x18000a06c`
- `0x18000a0ac`
- `0x18000a100`
- `0x1800193f0`
- `0x18001d5d0`
- `0x18002e624`
- `0x180032d70`
- `0x180032de0`
- `0x1800345b8`
- `0x18003977c`
- `0x18003b74c`
- `0x18003d054`
- `0x18003e88c`
- `0x18004c624`
- `0x180052380`
- `0x180052420`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `msvcrt!malloc` at `0x180007779`
- `msvcrt!malloc` at `0x18000782b`
- `msvcrt!malloc` at `0x180007779`
- `msvcrt!malloc` at `0x18000782b`
- `msvcrt!free` at `0x180007bbc`
- `msvcrt!free` at `0x180007bbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007be7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007be7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000751e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000751e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800079da`
- `OLEAUT32!__imp_SysAllocString` at `0x1800079da`

## pseudocode

```c
// Hidden C++ exception states: #wind=29 #try_helpers=1
__int64 __fastcall TaskDefinitionImpl::LoadFromXmlText(TaskDefinitionImpl *this, int a2)
{
  char *v4; // rsi
  BSTR *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rbx
  StringStream *v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rbx
  StringStream *v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // edi
  _DWORD *v20; // rax
  _DWORD *v21; // rdi
  int v22; // edx
  int v23; // r8d
  JobBucket *v24; // rax
  JobBucket *v25; // rax
  JobBucket *v26; // r12
  JobBucket *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  JobBucket *v30; // r12
  BSTR *v31; // rax
  struct IErrorInfo *v32; // rdx
  BSTR *v33; // r12
  BSTR v34; // rax
  __int64 v35; // rcx
  TaskDefinitionImpl *v36; // rax
  __int64 v37; // rcx
  PrincipalImpl *v38; // rcx
  int v39; // r15d
  BSTR *v40; // [rsp+30h] [rbp-3B8h] BYREF
  int v41; // [rsp+38h] [rbp-3B0h]
  BSTR *v42; // [rsp+40h] [rbp-3A8h] BYREF
  void *Block; // [rsp+48h] [rbp-3A0h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-398h] BYREF
  char v45; // [rsp+58h] [rbp-390h]
  __int64 *v46; // [rsp+60h] [rbp-388h]
  __int64 v47; // [rsp+68h] [rbp-380h]
  __int64 v48; // [rsp+70h] [rbp-378h]
  int v49; // [rsp+78h] [rbp-370h]
  __int64 v50; // [rsp+7Ch] [rbp-36Ch]
  void **v51; // [rsp+88h] [rbp-360h] BYREF
  char v52; // [rsp+90h] [rbp-358h]
  __int64 *v53; // [rsp+98h] [rbp-350h]
  __int64 v54; // [rsp+A0h] [rbp-348h]
  __int64 v55; // [rsp+A8h] [rbp-340h]
  int v56; // [rsp+B0h] [rbp-338h]
  __int64 v57; // [rsp+B4h] [rbp-334h]
  void **v58; // [rsp+C0h] [rbp-328h] BYREF
  char v59; // [rsp+C8h] [rbp-320h]
  __int64 *v60; // [rsp+D0h] [rbp-318h]
  __int64 v61; // [rsp+D8h] [rbp-310h]
  __int64 v62; // [rsp+E0h] [rbp-308h]
  int v63; // [rsp+E8h] [rbp-300h]
  __int64 v64; // [rsp+ECh] [rbp-2FCh]
  void **v65; // [rsp+F8h] [rbp-2F0h] BYREF
  char v66; // [rsp+100h] [rbp-2E8h]
  __int64 *v67; // [rsp+108h] [rbp-2E0h]
  __int64 v68; // [rsp+110h] [rbp-2D8h]
  __int64 v69; // [rsp+118h] [rbp-2D0h]
  int v70; // [rsp+120h] [rbp-2C8h]
  __int64 v71; // [rsp+124h] [rbp-2C4h]
  char *v72; // [rsp+130h] [rbp-2B8h]
  _DWORD *v73; // [rsp+138h] [rbp-2B0h]
  GUID v74; // [rsp+140h] [rbp-2A8h] BYREF
  _bstr_t::Data_t *v75[2]; // [rsp+150h] [rbp-298h] BYREF
  JobBucket *v76; // [rsp+160h] [rbp-288h] BYREF
  void **v77; // [rsp+170h] [rbp-278h] BYREF
  GUID v78; // [rsp+178h] [rbp-270h] BYREF
  _QWORD v79[2]; // [rsp+188h] [rbp-260h] BYREF
  JobBucket *v80; // [rsp+198h] [rbp-250h] BYREF
  int v81; // [rsp+1A0h] [rbp-248h]
  __int64 v82; // [rsp+1A8h] [rbp-240h]
  __int128 v83; // [rsp+1B0h] [rbp-238h]
  __int64 v84; // [rsp+1C0h] [rbp-228h]
  __int64 v85; // [rsp+1C8h] [rbp-220h]
  BSTR *v86; // [rsp+1D0h] [rbp-218h]
  __int16 v87; // [rsp+1D8h] [rbp-210h]
  int v88; // [rsp+1DCh] [rbp-20Ch]
  _BYTE v89[312]; // [rsp+1E0h] [rbp-208h] BYREF
  __int64 v90; // [rsp+318h] [rbp-D0h]
  int v91; // [rsp+320h] [rbp-C8h]
  __int64 v92; // [rsp+324h] [rbp-C4h]
  __int64 v93; // [rsp+330h] [rbp-B8h]
  __int64 v94; // [rsp+338h] [rbp-B0h]
  __int64 v95; // [rsp+340h] [rbp-A8h]
  __int64 v96; // [rsp+348h] [rbp-A0h]
  __int64 v97; // [rsp+350h] [rbp-98h]
  __int16 v98; // [rsp+358h] [rbp-90h]
  __int128 v99; // [rsp+360h] [rbp-88h]
  TaskDefinitionImpl *v100; // [rsp+370h] [rbp-78h]
  __int64 v101; // [rsp+378h] [rbp-70h]
  __int64 v102; // [rsp+380h] [rbp-68h] BYREF
  int v103; // [rsp+388h] [rbp-60h]
  __int64 v104; // [rsp+390h] [rbp-58h] BYREF
  _QWORD v105[2]; // [rsp+398h] [rbp-50h] BYREF
  int v106; // [rsp+3A8h] [rbp-40h]
  int v107; // [rsp+3ACh] [rbp-3Ch]

  v41 = 0;
  v4 = (char *)this + 16;
  if ( !this )
    v4 = 0;
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v72 = v4;
  v5 = 0;
  v42 = 0;
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 16);
    if ( v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(v6 + 2 * v7) );
      v8 = (StringStream *)operator new(0x28u);
      if ( v8 )
      {
        StringStream::StringStream(v8);
        *(_QWORD *)v9 = &StringReader::`vftable';
        *(_QWORD *)(v9 + 16) = -1;
        *(_DWORD *)(v9 + 24) = v7;
        *(_QWORD *)(v9 + 32) = v6;
      }
      else
      {
        v9 = 0;
      }
      if ( v9 )
      {
        v40 = 0;
        v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, BSTR **))v9)(
                v9,
                &GUID_0000000c_0000_0000_c000_000000000046,
                &v40);
        v11 = (unsigned int)v10;
        if ( v10 < 0 )
        {
          v5 = 0;
          v42 = 0;
        }
        else
        {
          v5 = v40;
          v42 = v40;
        }
      }
      else
      {
        _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator=(&v42);
        v11 = 2147500034LL;
        v5 = v42;
      }
      if ( (int)(v11 + 0x80000000) >= 0 && (_DWORD)v11 != -2147467262 )
        _com_raise_error(v11, (struct IErrorInfo *)v11);
      if ( !v5 )
      {
        v45 = 0;
        v46 = &qword_18007B2F0;
        v47 = 0;
        v48 = 0;
        v49 = 14;
        v50 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
LABEL_27:
      v18 = 0;
      goto LABEL_28;
    }
    v18 = -2147024809;
  }
  else
  {
    v12 = *((_QWORD *)this + 14);
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v12 + 2 * v13) );
      v14 = (StringStream *)operator new(0x28u);
      if ( v14 )
      {
        StringStream::StringStream(v14);
        *(_QWORD *)v15 = &StringReader::`vftable';
        *(_QWORD *)(v15 + 16) = -1;
        *(_DWORD *)(v15 + 24) = v13;
        *(_QWORD *)(v15 + 32) = v12;
      }
      else
      {
        v15 = 0;
      }
      if ( v15 )
      {
        v40 = 0;
        v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, BSTR **))v15)(
                v15,
                &GUID_0000000c_0000_0000_c000_000000000046,
                &v40);
        v17 = (unsigned int)v16;
        if ( v16 < 0 )
        {
          v5 = 0;
          v42 = 0;
        }
        else
        {
          v5 = v40;
          v42 = v40;
        }
      }
      else
      {
        _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator=(&v42);
        v17 = 2147500034LL;
        v5 = v42;
      }
      if ( (int)(v17 + 0x80000000) >= 0 && (_DWORD)v17 != -2147467262 )
        _com_raise_error(v17, (struct IErrorInfo *)v17);
      if ( !v5 )
      {
        v52 = 0;
        v53 = &qword_18007B2F0;
        v54 = 0;
        v55 = 0;
        v56 = 14;
        v57 = -1;
        v51 = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&v51;
      }
      goto LABEL_27;
    }
    v18 = -2147024809;
  }
LABEL_28:
  v41 = v18;
  if ( v18 >= 0 )
  {
    Block = 0;
    v20 = malloc(0x460u);
    v21 = v20;
    if ( !v20 )
    {
      v59 = 0;
      v60 = &qword_18007B2F0;
      v61 = 0;
      v62 = 0;
      v63 = 14;
      v64 = -1;
      v58 = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&v58;
    }
    *(_QWORD *)v20 = &wmi::RefBase::`vftable';
    v20[2] = 0;
    *(_QWORD *)v20 = &TaskXmlReader::`vftable';
    *((_QWORD *)v20 + 2) = 0;
    *((_QWORD *)v20 + 3) = 0;
    *((_QWORD *)v20 + 4) = v5;
    _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef();
    *((_BYTE *)v21 + 40) = 0;
    *((_QWORD *)v21 + 6) = &Block;
    *((_QWORD *)v21 + 7) = 0;
    *((_BYTE *)v21 + 1106) &= 0xFCu;
    v21[16] = 0;
    *((_QWORD *)v21 + 9) = 0;
    *((_WORD *)v21 + 40) = 0;
    *((_BYTE *)v21 + 1112) = 0;
    v21[279] = 65542;
    v73 = v21;
    _InterlockedIncrement(v21 + 2);
    v75[0] = 0;
    v76 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, (unsigned int)&v74, 0);
    }
    v24 = (JobBucket *)malloc(0xD8u);
    if ( !v24 )
    {
      v66 = 0;
      v67 = &qword_18007B2F0;
      v68 = 0;
      v69 = 0;
      v70 = 14;
      v71 = -1;
      v65 = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&v65;
    }
    v25 = JobBucket::JobBucket(v24);
    v26 = v25;
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)v25 + 2);
    v27 = v76;
    if ( v76 && _InterlockedExchangeAdd((volatile signed __int32 *)v76 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(JobBucket *, __int64))v27)(v27, 1);
    v76 = v26;
    _bstr_t::_Free((_bstr_t *)v75);
    *(_OWORD *)v75 = 0;
    v74 = GUID_NULL;
    *((_DWORD *)v76 + 15) = 0;
    v77 = &ValidationXmlHandler::`vftable';
    v79[0] = 0;
    v80 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, &v78, &v74);
    }
    v30 = v76;
    if ( v76 )
      _InterlockedIncrement((volatile signed __int32 *)v76 + 2);
    wmi::AutoRef<RpcFolderSnapshot>::Release(&v80);
    v80 = v30;
    if ( v75[0] )
      _InterlockedIncrement((volatile signed __int32 *)v75[0] + 4);
    _bstr_t::_Free((_bstr_t *)v79);
    v79[0] = v75[0];
    v79[1] = v75[1];
    v78 = v74;
    v81 = 7;
    v82 = 0;
    v83 = 0;
    v84 = 0;
    v85 = 0;
    v31 = (BSTR *)operator new(0x18u);
    v33 = v31;
    v40 = v31;
    if ( v31 )
    {
      v31[1] = 0;
      *((_DWORD *)v31 + 4) = 1;
      v34 = SysAllocString(L"Author");
      *v33 = v34;
      if ( !v34 )
        _com_raise_error(-2147024882, v32);
    }
    else
    {
      v33 = 0;
    }
    v86 = v33;
    if ( !v33 )
      _com_raise_error(-2147024882, v32);
    v87 = 0;
    v88 = 0;
    ValidationXmlHandler::CurrentTrigger::CurrentTrigger((ValidationXmlHandler::CurrentTrigger *)v89);
    v89[304] = 0;
    v90 = 0;
    v91 = -1;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    *(_QWORD *)&v99 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned short const * const,void *>>>::_Buyheadnode();
    v77 = &BuilderXmlHandler::`vftable';
    v100 = this;
    v101 = 0;
    v102 = 0;
    v103 = -1;
    v104 = 0;
    v105[0] = 0;
    v105[1] = 0;
    v105[0] = std::_List_alloc<0,std::_List_base_types<_bstr_t>>::_Buynode0(v35, 0, 0);
    v106 = 0;
    v107 = a2;
    if ( a2 )
    {
      v36 = v100;
      v37 = *((_QWORD *)v100 + 11);
      if ( v37 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 96LL))(v37);
        v36 = v100;
      }
      v38 = (PrincipalImpl *)*((_QWORD *)v36 + 13);
      if ( v38 )
      {
        PrincipalImpl::CleanRequiredPrivileges(v38);
        PrincipalImpl::CleanCapabilities(*((PrincipalImpl **)v100 + 13));
      }
    }
    wmi::AutoRef<RpcFolderSnapshot>::Release(&v76);
    if ( v75[0] )
    {
      _bstr_t::Data_t::Release(v75[0]);
      v75[0] = 0;
    }
    v39 = TaskXmlReader::ProcessXml((TaskXmlReader *)v21, (struct ITaskXmlHandler *)&v77);
    v41 = v39;
    if ( v39 < 0 && Block )
      SetOleErrorInfo(&GUID_f5bc8fc5_536d_4f77_b852_fbc1356fdeb6, (const struct _TASK_XML_ERROR_INFO *)Block);
    std::list<_bstr_t>::~list<_bstr_t>(v105);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v104);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v102);
    ValidationXmlHandler::~ValidationXmlHandler((ValidationXmlHandler *)&v77);
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(_DWORD *, __int64))v21)(v21, 1);
    if ( Block )
      free(Block);
    if ( v5 )
      (*((void (__fastcall **)(BSTR *))*v5 + 2))(v5);
    if ( v4 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
    return (unsigned int)v39;
  }
  else
  {
    if ( v5 )
      (*((void (__fastcall **)(BSTR *))*v5 + 2))(v5);
    if ( v4 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
    return (unsigned int)v18;
  }
}

```

## disassembly

```asm
0x1800074d0  mov     [rsp+arg_8], rbx
0x1800074d5  mov     [rsp+arg_10], rsi
0x1800074da  push    rdi
0x1800074db  push    r12
0x1800074dd  push    r13
0x1800074df  push    r14
0x1800074e1  push    r15
0x1800074e3  sub     rsp, 3C0h
0x1800074ea  mov     rax, cs:__security_cookie
0x1800074f1  xor     rax, rsp
0x1800074f4  mov     [rsp+3E8h+var_38], rax
0x1800074fc  mov     r13d, edx
0x1800074ff  mov     r15, rcx
0x180007502  xor     r12d, r12d
0x180007505  mov     [rsp+3E8h+var_3B0], r12d
0x18000750a  lea     rsi, [rcx+10h]
0x18000750e  test    rcx, rcx
0x180007511  cmovz   rsi, r12
0x180007515  test    rsi, rsi
0x180007518  jz      short loc_18000752A
0x18000751a  lea     rcx, [rsi+8]; lpCriticalSection
0x18000751e  call    cs:__imp_EnterCriticalSection
0x180007525  nop     dword ptr [rax+rax+00h]
0x18000752a  mov     [rsp+3E8h+var_2B8], rsi
0x180007532  mov     rbx, r12
0x180007535  mov     [rsp+3E8h+var_3A8], rbx
0x18000753a  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180007541  test    r13d, r13d
0x180007544  jz      loc_180007634
0x18000754a  mov     rdi, [r15+80h]
0x180007551  test    rdi, rdi
0x180007554  jz      loc_180007C7F
0x18000755a  mov     rbx, r14
0x18000755d  nop     dword ptr [rax]
0x180007560  inc     rbx
0x180007563  cmp     word ptr [rdi+rbx*2], 0
0x180007568  jnz     short loc_180007560
0x18000756a  mov     ecx, 28h ; '('; unsigned __int64
0x18000756f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007574  mov     rcx, rax; this
0x180007577  test    rax, rax
0x18000757a  jz      loc_180007739
0x180007580  call    ??0StringStream@@QEAA@XZ; StringStream::StringStream(void)
0x180007585  lea     rdx, ??_7StringReader@@6B@; const StringReader::`vftable'
0x18000758c  mov     [rcx], rdx
0x18000758f  mov     [rcx+10h], r14
0x180007593  mov     [rcx+18h], ebx
0x180007596  mov     [rcx+20h], rdi
0x18000759a  test    rcx, rcx
0x18000759d  jz      loc_180007C89
0x1800075a3  mov     [rsp+3E8h+var_3B8], r12
0x1800075a8  mov     rax, [rcx]
0x1800075ab  lea     r8, [rsp+3E8h+var_3B8]
0x1800075b0  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800075b7  mov     rax, [rax]
0x1800075ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075bf  mov     edx, eax; struct IErrorInfo *
0x1800075c1  test    eax, eax
0x1800075c3  js      loc_180007C42
0x1800075c9  mov     rbx, [rsp+3E8h+var_3B8]
0x1800075ce  mov     [rsp+3E8h+var_3A8], rbx
0x1800075d3  mov     ecx, 80000000h
0x1800075d8  lea     eax, [rdx+rcx]
0x1800075db  test    ecx, eax
0x1800075dd  jz      loc_180007741
0x1800075e3  test    rbx, rbx
0x1800075e6  jnz     loc_1800076D0
0x1800075ec  mov     [rsp+3E8h+var_390], bl
0x1800075f0  lea     rax, qword_18007B2F0
0x1800075f7  mov     [rsp+3E8h+var_388], rax
0x1800075fc  mov     [rsp+3E8h+var_380], r12
0x180007601  mov     [rsp+3E8h+var_378], r12
0x180007606  mov     [rsp+3E8h+var_370], 0Eh
0x18000760e  mov     [rsp+3E8h+var_36C], 0FFFFFFFFFFFFFFFFh
0x180007617  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000761e  mov     [rsp+3E8h+pExceptionObject], rax
0x180007623  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000762a  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x18000762f  call    _CxxThrowException_0
0x180007634  mov     rdi, [r15+70h]
0x180007638  test    rdi, rdi
0x18000763b  jz      loc_180007CA2
0x180007641  mov     rbx, r14
0x180007644  inc     rbx
0x180007647  cmp     word ptr [rdi+rbx*2], 0
0x18000764c  jnz     short loc_180007644
0x18000764e  mov     ecx, 28h ; '('; unsigned __int64
0x180007653  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007658  mov     rcx, rax; this
0x18000765b  test    rax, rax
0x18000765e  jz      loc_180007754
0x180007664  call    ??0StringStream@@QEAA@XZ; StringStream::StringStream(void)
0x180007669  lea     rdx, ??_7StringReader@@6B@; const StringReader::`vftable'
0x180007670  mov     [rcx], rdx
0x180007673  mov     [rcx+10h], r14
0x180007677  mov     [rcx+18h], ebx
0x18000767a  mov     [rcx+20h], rdi
0x18000767e  test    rcx, rcx
0x180007681  jz      loc_180007CAC
0x180007687  mov     [rsp+3E8h+var_3B8], r12
0x18000768c  mov     rax, [rcx]
0x18000768f  lea     r8, [rsp+3E8h+var_3B8]
0x180007694  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000769b  mov     rax, [rax]
0x18000769e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a3  mov     edx, eax; struct IErrorInfo *
0x1800076a5  test    eax, eax
0x1800076a7  js      loc_180007C6A
0x1800076ad  mov     rbx, [rsp+3E8h+var_3B8]
0x1800076b2  mov     [rsp+3E8h+var_3A8], rbx
0x1800076b7  mov     ecx, 80000000h
0x1800076bc  lea     eax, [rdx+rcx]
0x1800076bf  test    ecx, eax
0x1800076c1  jz      loc_18000775C
0x1800076c7  test    rbx, rbx
0x1800076ca  jz      loc_180007CC5
0x1800076d0  mov     edi, r12d
0x1800076d3  mov     [rsp+3E8h+var_3B0], edi
0x1800076d7  test    edi, edi
0x1800076d9  jns     loc_18000776F
0x1800076df  test    rbx, rbx
0x1800076e2  jz      short loc_1800076F4
0x1800076e4  mov     rax, [rbx]
0x1800076e7  mov     rcx, rbx
0x1800076ea  mov     rax, [rax+10h]
0x1800076ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f3  nop
0x1800076f4  test    rsi, rsi
0x1800076f7  jz      short loc_180007709
0x1800076f9  lea     rcx, [rsi+8]; lpCriticalSection
0x1800076fd  call    cs:__imp_LeaveCriticalSection
0x180007704  nop     dword ptr [rax+rax+00h]
0x180007709  mov     eax, edi
0x18000770b  mov     rcx, [rsp+3E8h+var_38]
0x180007713  xor     rcx, rsp; StackCookie
0x180007716  call    __security_check_cookie
0x18000771b  lea     r11, [rsp+3E8h+var_28]
0x180007723  mov     rbx, [r11+38h]
0x180007727  mov     rsi, [r11+40h]
0x18000772b  mov     rsp, r11
0x18000772e  pop     r15
0x180007730  pop     r14
0x180007732  pop     r13
0x180007734  pop     r12
0x180007736  pop     rdi
0x180007737  retn
0x180007739  mov     rcx, r12
0x18000773c  jmp     loc_18000759A
0x180007741  cmp     edx, 80004002h
0x180007747  jz      loc_1800075E3
0x18000774d  mov     ecx, edx; int
0x18000774f  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180007754  mov     rcx, r12
0x180007757  jmp     loc_18000767E
0x18000775c  cmp     edx, 80004002h
0x180007762  jz      loc_1800076C7
0x180007768  mov     ecx, edx; int
0x18000776a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000776f  mov     [rsp+3E8h+Block], r12
0x180007774  mov     ecx, 460h; Size
0x180007779  call    cs:__imp_malloc
0x180007780  nop     dword ptr [rax+rax+00h]
0x180007785  mov     rdi, rax
0x180007788  test    rax, rax
0x18000778b  jz      loc_180007D27
0x180007791  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180007798  mov     [rdi], rax
0x18000779b  mov     [rdi+8], r12d
0x18000779f  lea     rax, ??_7TaskXmlReader@@6B@; const TaskXmlReader::`vftable'
0x1800077a6  mov     [rdi], rax
0x1800077a9  mov     [rdi+10h], r12
0x1800077ad  mov     [rdi+18h], r12
0x1800077b1  lea     rcx, [rdi+20h]
0x1800077b5  mov     [rcx], rbx
0x1800077b8  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x1800077bd  mov     byte ptr [rdi+28h], 0
0x1800077c1  lea     rax, [rsp+3E8h+Block]
0x1800077c6  mov     [rdi+30h], rax
0x1800077ca  mov     [rdi+38h], r12
0x1800077ce  and     byte ptr [rdi+452h], 0FCh
0x1800077d5  mov     [rdi+40h], r12d
0x1800077d9  mov     [rdi+48h], r12
0x1800077dd  mov     [rdi+50h], r12w
0x1800077e2  mov     byte ptr [rdi+458h], 0
0x1800077e9  mov     dword ptr [rdi+45Ch], 10006h
0x1800077f3  mov     [rsp+3E8h+var_2B0], rdi
0x1800077fb  lock inc dword ptr [rdi+8]
0x1800077ff  mov     [rsp+3E8h+var_298], r12
0x180007807  mov     [rsp+3E8h+var_288], r12
0x18000780f  lea     rax, WPP_GLOBAL_Control
0x180007816  mov     rcx, cs:WPP_GLOBAL_Control
0x18000781d  cmp     rcx, rax
0x180007820  jnz     loc_180007D89
0x180007826  mov     ecx, 0D8h; Size
0x18000782b  call    cs:__imp_malloc
0x180007832  nop     dword ptr [rax+rax+00h]
0x180007837  test    rax, rax
0x18000783a  jz      loc_180007DB8
0x180007840  mov     rcx, rax; this
0x180007843  call    ??0JobBucket@@QEAA@XZ; JobBucket::JobBucket(void)
0x180007848  mov     r12, rax
0x18000784b  test    rax, rax
0x18000784e  jz      short loc_180007854
0x180007850  lock inc dword ptr [rax+8]
0x180007854  mov     rcx, [rsp+3E8h+var_288]
0x18000785c  test    rcx, rcx
0x18000785f  jz      short loc_180007872
0x180007861  mov     edx, r14d
0x180007864  lock xadd [rcx+8], edx
0x180007869  cmp     edx, 1
0x18000786c  jz      loc_180007C15
0x180007872  mov     [rsp+3E8h+var_288], r12
0x18000787a  lea     rcx, [rsp+3E8h+var_298]; this
0x180007882  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180007887  xorps   xmm0, xmm0
0x18000788a  movdqu  xmmword ptr [rsp+3E8h+var_298], xmm0
0x180007893  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18000789a  mov     [rsp+3E8h+var_2A8], rax
0x1800078a2  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800078a9  mov     [rsp+3E8h+var_2A0], rax
0x1800078b1  mov     rax, [rsp+3E8h+var_288]
0x1800078b9  xor     ecx, ecx
0x1800078bb  mov     [rax+3Ch], ecx
0x1800078be  lea     rax, ??_7ValidationXmlHandler@@6B@; const ValidationXmlHandler::`vftable'
0x1800078c5  mov     [rsp+3E8h+var_278], rax
0x1800078cd  mov     [rsp+3E8h+var_260], rcx
0x1800078d5  mov     [rsp+3E8h+var_250], rcx
0x1800078dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078e4  lea     rax, WPP_GLOBAL_Control
0x1800078eb  cmp     rcx, rax
0x1800078ee  jnz     loc_180007E1A
0x1800078f4  mov     r12, [rsp+3E8h+var_288]
0x1800078fc  test    r12, r12
0x1800078ff  jz      short loc_180007907
0x180007901  lock inc dword ptr [r12+8]
0x180007907  lea     rcx, [rsp+3E8h+var_250]
0x18000790f  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x180007914  mov     [rsp+3E8h+var_250], r12
0x18000791c  mov     rax, [rsp+3E8h+var_298]
0x180007924  test    rax, rax
0x180007927  jz      short loc_18000792D
0x180007929  lock inc dword ptr [rax+10h]
0x18000792d  lea     rcx, [rsp+3E8h+var_260]; this
0x180007935  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000793a  mov     rax, [rsp+3E8h+var_298]
0x180007942  mov     [rsp+3E8h+var_260], rax
0x18000794a  mov     rax, [rsp+3E8h+var_298+8]
0x180007952  mov     [rsp+3E8h+var_258], rax
0x18000795a  mov     rax, [rsp+3E8h+var_2A8]
0x180007962  mov     [rsp+3E8h+var_270], rax
0x18000796a  mov     rax, [rsp+3E8h+var_2A0]
0x180007972  mov     [rsp+3E8h+var_268], rax
0x18000797a  mov     [rsp+3E8h+var_248], 7
0x180007985  xor     eax, eax
0x180007987  mov     [rsp+3E8h+var_240], rax
0x18000798f  xorps   xmm0, xmm0
0x180007992  movdqa  [rsp+3E8h+var_238], xmm0
0x18000799b  mov     [rsp+3E8h+var_228], rax
0x1800079a3  mov     [rsp+3E8h+var_220], rax
0x1800079ab  mov     ecx, 18h; unsigned __int64
0x1800079b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800079b5  mov     r12, rax
0x1800079b8  mov     [rsp+3E8h+var_3B8], rax
0x1800079bd  xor     ecx, ecx
0x1800079bf  test    rax, rax
0x1800079c2  jz      loc_180007C77
0x1800079c8  mov     [rax+8], rcx
0x1800079cc  mov     dword ptr [rax+10h], 1
0x1800079d3  lea     rcx, psz; "Author"
0x1800079da  call    cs:__imp_SysAllocString
0x1800079e1  nop     dword ptr [rax+rax+00h]
0x1800079e6  mov     [r12], rax
0x1800079ea  test    rax, rax
0x1800079ed  jz      loc_180007E51
0x1800079f3  mov     [rsp+3E8h+var_218], r12
0x1800079fb  test    r12, r12
0x1800079fe  jnz     short loc_180007A0B
0x180007a00  mov     ecx, 8007000Eh; int
0x180007a05  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180007a0b  mov     [rsp+3E8h+var_210], 0
0x180007a15  xor     r12d, r12d
0x180007a18  mov     [rsp+3E8h+var_20C], r12d
0x180007a20  lea     rcx, [rsp+3E8h+var_208]; this
0x180007a28  call    ??0CurrentTrigger@ValidationXmlHandler@@QEAA@XZ; ValidationXmlHandler::CurrentTrigger::CurrentTrigger(void)
0x180007a2d  nop
0x180007a2e  mov     [rsp+3E8h+var_D8], r12b
0x180007a36  mov     [rsp+3E8h+var_D0], r12
0x180007a3e  mov     [rsp+3E8h+var_C8], 0FFFFFFFFh
0x180007a49  mov     [rsp+3E8h+var_C4], r12
0x180007a51  mov     [rsp+3E8h+var_B8], r12
0x180007a59  mov     [rsp+3E8h+var_B0], r12
0x180007a61  mov     [rsp+3E8h+var_A8], r12
0x180007a69  mov     [rsp+3E8h+var_A0], r12
0x180007a71  mov     [rsp+3E8h+var_98], r12
0x180007a79  mov     [rsp+3E8h+var_90], r12w
0x180007a82  xorps   xmm0, xmm0
0x180007a85  movdqa  [rsp+3E8h+var_88], xmm0
0x180007a8e  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEBGPEAX@std@@V?$allocator@U?$pair@QEBGPEAX@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGPEAX@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ushort const * const,void *>>>::_Buyheadnode(void)
0x180007a93  mov     qword ptr [rsp+3E8h+var_88], rax
0x180007a9b  lea     rax, ??_7BuilderXmlHandler@@6B@; const BuilderXmlHandler::`vftable'
  ... truncated ...
```
