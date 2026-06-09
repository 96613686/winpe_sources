# CConsumerModuleInproc::ProcessBatch(_FsrmPipelinePhase,ulong,_FSRM_PROPERTYBAG_FIELDS * *,_FSRM_PROPERTYBAG_ARRAYS * *,_FSRM_PROPERTY_CACHE * *,_FSRM_IN_FILE_SECURE_PROPERTIES * *,IFsrmBatchedPipelineModuleCallback *,_FSRM_PROPERTYBAG_FIELDS_DELTA * *)

- ea: `0x180041f60`
- end: `0x18004272a`
- name: `?ProcessBatch@CConsumerModuleInproc@@UEAAJW4_FsrmPipelinePhase@@KPEAPEAU_FSRM_PROPERTYBAG_FIELDS@@PEAPEAU_FSRM_PROPERTYBAG_ARRAYS@@PEAPEAU_FSRM_PROPERTY_CACHE@@PEAPEAU_FSRM_IN_FILE_SECURE_PROPERTIES@@PEAUIFsrmBatchedPipelineModuleCallback@@PEAPEAU_FSRM_PROPERTYBAG_FIELDS_DELTA@@@Z`
- size: `1994`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000cd60`
- `0x18003f74c`
- `0x180040528`
- `0x180041f60`
- `0x180042bd8`
- `0x18004513c`
- `0x18004e864`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073d04`
- `0x180073f54`
- `0x180084bc4`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180042304`
- `msvcrt!_wcsicmp` at `0x180042373`
- `msvcrt!_wcsicmp` at `0x180042304`
- `msvcrt!_wcsicmp` at `0x180042373`
- `ole32!CoTaskMemAlloc` at `0x180042085`
- `ole32!CoTaskMemAlloc` at `0x180042085`

## string_xrefs

- `0x180041fe2`: `base\fs\fsrm\service\modulewrp\consumermodule.cpp`
- `0x180042673`: `base\fs\fsrm\service\modulewrp\consumermodule.cpp`
- `0x180042688`: `CoTaskMemRealloc(FSRM_PROPERTYBAG_FIELDS_DELTA)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CConsumerModuleInproc::ProcessBatch(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  __int64 v9; // r12
  __int64 v10; // rsi
  __int64 v11; // r15
  unsigned int v12; // r13d
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rbx
  unsigned int v17; // r14d
  __int64 v18; // rdi
  __int64 v19; // rdx
  void **v20; // rax
  int v21; // eax
  __int64 v22; // r10
  __int64 v23; // rax
  __int64 v24; // rdx
  unsigned __int64 v25; // r12
  unsigned __int64 v26; // r15
  __int64 v27; // rsi
  _QWORD *v28; // rax
  const wchar_t **v29; // r14
  __int64 *v30; // rbx
  __int64 *v31; // rdi
  const wchar_t *v32; // rcx
  const wchar_t *v33; // rdx
  __int64 v34; // rdi
  const wchar_t *v35; // rdx
  const wchar_t *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  unsigned int v39; // ebx
  __int64 v41; // rax
  int Hr; // eax
  char v43; // al
  int v44; // eax
  char v45; // al
  __int64 v46; // [rsp+20h] [rbp-318h]
  __int64 v47; // [rsp+28h] [rbp-310h]
  unsigned int v48; // [rsp+60h] [rbp-2D8h]
  __int64 v49; // [rsp+68h] [rbp-2D0h] BYREF
  __int64 v50; // [rsp+70h] [rbp-2C8h] BYREF
  unsigned int v51; // [rsp+78h] [rbp-2C0h]
  unsigned int v52; // [rsp+7Ch] [rbp-2BCh]
  __int64 v53; // [rsp+80h] [rbp-2B8h] BYREF
  __int64 v54; // [rsp+88h] [rbp-2B0h]
  __int64 *v55; // [rsp+90h] [rbp-2A8h]
  _QWORD *v56; // [rsp+98h] [rbp-2A0h]
  _QWORD *v57; // [rsp+A0h] [rbp-298h]
  int v58; // [rsp+A8h] [rbp-290h] BYREF
  _QWORD *v59; // [rsp+B0h] [rbp-288h]
  __int64 *v60; // [rsp+B8h] [rbp-280h]
  __int64 *v61; // [rsp+C0h] [rbp-278h] BYREF
  __int64 *v62; // [rsp+C8h] [rbp-270h]
  __int64 v63; // [rsp+D0h] [rbp-268h]
  __int64 v64; // [rsp+D8h] [rbp-260h]
  unsigned __int64 v65; // [rsp+E0h] [rbp-258h]
  __int64 v66; // [rsp+E8h] [rbp-250h]
  int v67; // [rsp+F0h] [rbp-248h] BYREF
  __int64 v68; // [rsp+F8h] [rbp-240h]
  __int64 v69; // [rsp+100h] [rbp-238h]
  __int64 v70; // [rsp+108h] [rbp-230h]
  __int64 *v71; // [rsp+110h] [rbp-228h]
  __int64 *v72; // [rsp+118h] [rbp-220h]
  __int64 *v73; // [rsp+120h] [rbp-218h]
  __int64 *v74; // [rsp+128h] [rbp-210h]
  __int64 *v75; // [rsp+130h] [rbp-208h]
  __int64 *v76; // [rsp+138h] [rbp-200h]
  _com_error *v77; // [rsp+140h] [rbp-1F8h] BYREF
  const exception *v78; // [rsp+148h] [rbp-1F0h] BYREF
  __int64 *v79; // [rsp+150h] [rbp-1E8h]
  _QWORD v80[3]; // [rsp+158h] [rbp-1E0h] BYREF
  int v81; // [rsp+170h] [rbp-1C8h]
  int v82; // [rsp+174h] [rbp-1C4h]
  int v83; // [rsp+178h] [rbp-1C0h]
  _DWORD v84[26]; // [rsp+180h] [rbp-1B8h] BYREF
  void *v85[2]; // [rsp+1E8h] [rbp-150h] BYREF
  __int64 v86; // [rsp+1F8h] [rbp-140h]
  unsigned __int64 v87; // [rsp+200h] [rbp-138h]
  void *Block[3]; // [rsp+210h] [rbp-128h] BYREF
  unsigned __int64 v89; // [rsp+228h] [rbp-110h]
  __int64 v90; // [rsp+238h] [rbp-100h] BYREF
  void **v91; // [rsp+240h] [rbp-F8h] BYREF
  int v92; // [rsp+248h] [rbp-F0h]
  unsigned int v93; // [rsp+26Ch] [rbp-CCh]

  v9 = a4;
  v68 = a4;
  v10 = a3;
  v51 = a3;
  v11 = a1;
  v54 = a1;
  v70 = a5;
  v69 = a8;
  v57 = a9;
  v56 = v80;
  v80[0] = L"base\\fs\\fsrm\\service\\modulewrp\\consumermodule.cpp";
  v80[1] = L"CConsumerModuleInproc::ProcessBatch";
  v80[2] = L"CNSMMODC";
  v81 = 274;
  v82 = 22;
  v83 = 255;
  v12 = 0;
  v84[24] = 0x1000000;
  memset_0(v84, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v91, v80, 0);
  *a9 = 0;
  try
  {
    v58 = 0;
    v59 = 0;
    v13 = CoTaskMemAlloc(40 * v10);
    v14 = v13;
    v56 = v13;
    if ( !v13 )
    {
      v57 = v80;
      v41 = CSrmDebugInfo::CSrmDebugInfo(
              v80,
              L"base\\fs\\fsrm\\service\\modulewrp\\consumermodule.cpp",
              L"CNSMMODC",
              L"CConsumerModuleInproc::ProcessBatch",
              304,
              24);
      CSrmFunctionTracer::Throw(&v91, v41, 2147942414LL, L"CoTaskMemRealloc(FSRM_PROPERTYBAG_FIELDS_DELTA)");
    }
    memset_0(v13, 0, 40 * v10);
    v58 = v10;
    v59 = v14;
    while ( 1 )
    {
      v52 = v12;
      if ( v12 >= (unsigned int)v10 )
        break;
      v15 = *(_QWORD *)(v9 + 8LL * v12);
      if ( v15 )
      {
        v50 = 0;
        v87 = 7;
        v86 = 0;
        LOWORD(v85[0]) = 0;
        v16 = *(unsigned int *)(v15 + 48);
        v17 = *(_DWORD *)(v15 + 52);
        v48 = v17;
        CPropertyBagProxy::CreateInstance(
          v12,
          v15,
          *(_QWORD *)(v70 + 8LL * v12),
          0,
          0,
          0,
          v69,
          (__int64)&v14[5 * v12],
          (__int64)&CPropertyBagProxy::s_ftNeverModified,
          0,
          &v50);
        v18 = v50;
        LOBYTE(v19) = 1;
        CPropertyBagFieldsBase::BuildFullPath(v50 + 88, v19, 0, v85);
        v20 = v85;
        if ( v87 >= 8 )
          v20 = (void **)v85[0];
        CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v91, 0x8Cu, 0x164u, L"Consuming filename: %s", v20);
        v53 = 0;
        v21 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
                v18,
                &GUID_774589d1_d300_4f7a_9a24_f7b766800250,
                &v53);
        v92 = v21;
        if ( v21 < 0 )
        {
          Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v91);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v91, Hr);
          v43 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v91);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v91, 0x167u, v43, 0);
        }
        v92 = v21;
        v22 = *(_QWORD *)(v11 + 184) + 56 * v16;
        v64 = v22;
        while ( v17 != -1 )
        {
          v23 = 88LL * v17;
          v66 = v23;
          v24 = *(_QWORD *)(v22 + 16);
          v63 = v24;
          v25 = 0x8F5C28F5C28F5C29uLL * ((__int64)(*(_QWORD *)(v23 + v24 + 64) - *(_QWORD *)(v23 + v24 + 56)) >> 3);
          v26 = 0;
          v65 = 0;
          while ( v26 < v25 )
          {
            v27 = *(_QWORD *)(v23 + v24 + 56) + 200 * v26;
            if ( *(_BYTE *)(v27 + 48) )
            {
              v28 = (_QWORD *)(v27 + 56);
              if ( *(_QWORD *)(v27 + 80) >= 8u )
                v28 = (_QWORD *)*v28;
              LODWORD(v47) = 0;
              LODWORD(v46) = 6;
              CPropertyBagFieldsContextual::SetContext(v18 + 88, v22, v17, v26, v46, v47, v28, *(_QWORD *)(v27 + 40), 0);
              v29 = (const wchar_t **)(v27 + 152);
              v30 = *(__int64 **)(v54 + 104);
              v31 = (__int64 *)v30[1];
              v55 = v31;
              v60 = v30;
              while ( !*((_BYTE *)v31 + 73) )
              {
                v32 = (const wchar_t *)(v31 + 3);
                if ( *(_QWORD *)(v27 + 176) < 8u )
                  v33 = (const wchar_t *)(v27 + 152);
                else
                  v33 = *v29;
                if ( (unsigned __int64)v31[6] >= 8 )
                  v32 = *(const wchar_t **)v32;
                if ( _wcsicmp(v32, v33) >= 0 )
                {
                  v30 = v31;
                  v60 = v31;
                  v31 = (__int64 *)*v31;
                }
                else
                {
                  v31 = (__int64 *)v31[2];
                }
                v55 = v31;
              }
              v34 = v54;
              v62 = v30;
              v79 = *(__int64 **)(v54 + 104);
              if ( v30 == v79 )
                goto LABEL_34;
              v35 = (const wchar_t *)(v30 + 3);
              if ( (unsigned __int64)v30[6] >= 8 )
                v35 = *(const wchar_t **)v35;
              v36 = *(_QWORD *)(v27 + 176) < 8u ? (const wchar_t *)(v27 + 152) : *v29;
              if ( _wcsicmp(v36, v35) < 0 )
              {
LABEL_34:
                v71 = &v49;
                v49 = 0;
                std::wstring::wstring(Block, v29);
                v72 = &v90;
                v73 = &v90;
                v90 = v49;
                if ( v49 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
                v37 = std::_Tree_val<std::_Tmap_traits<std::wstring,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineConsumer>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineConsumer>>>>,0>>::_Buynode<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineConsumer>>>>(
                        v34 + 96,
                        Block);
                std::_Tree<std::_Tmap_traits<std::wstring,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineModuleDefinition>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineModuleDefinition>>>>,0>>::_Insert(
                  v34 + 96,
                  &v61,
                  v30,
                  v37);
                v30 = v61;
                v62 = v61;
                v74 = &v90;
                v75 = &v90;
                if ( v90 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                if ( v89 >= 8 )
                  operator delete(Block[0]);
                v89 = 7;
                Block[2] = 0;
                LOWORD(Block[0]) = 0;
                v76 = &v49;
                if ( v49 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              }
              v38 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30[8] + 96LL))(v30[8], v53);
              v92 = v38;
              v18 = v50;
              if ( v38 == -2147200134 )
              {
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v50 + 88) + 56LL))(v50 + 88, 0x4000);
                v38 = 0;
                v92 = 0;
              }
              v92 = v38;
              if ( v38 < 0 )
              {
                v44 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v91);
                CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v91, v44);
                v45 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v91);
                CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v91, 0x194u, v45, 0);
              }
              v92 = v38;
              v24 = v63;
              v22 = v64;
              v17 = v48;
            }
            v65 = ++v26;
            v23 = v66;
          }
          v17 = *(_DWORD *)(v23 + v24);
          v48 = v17;
        }
        if ( v53 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v87 >= 8 )
          operator delete(v85[0]);
        v87 = 7;
        v86 = 0;
        LOWORD(v85[0]) = 0;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v14 = v56;
        LODWORD(v10) = v51;
        v11 = v54;
        v9 = v68;
      }
      ++v12;
    }
    v59 = 0;
    *v57 = v14;
    CPropertyBagFieldsDeltaBatch::~CPropertyBagFieldsDeltaBatch((CPropertyBagFieldsDeltaBatch *)&v58);
  }
  catch ( long v67 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v91,
      v67,
      L"base\\fs\\fsrm\\service\\modulewrp\\consumermodule.cpp",
      L"CNSMMODC",
      L"CConsumerModuleInproc::ProcessBatch",
      0x1A1u,
      v93);
  }
  catch ( _com_error *v77 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v91,
      v77,
      L"base\\fs\\fsrm\\service\\modulewrp\\consumermodule.cpp",
      L"CNSMMODC",
      L"CConsumerModuleInproc::ProcessBatch",
      0x1A1u,
      v93);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v91,
      L"base\\fs\\fsrm\\service\\modulewrp\\consumermodule.cpp",
      L"CNSMMODC",
      L"CConsumerModuleInproc::ProcessBatch",
      0x1A1u,
      v93);
  }
  catch ( const exception *v78 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v91,
      v78,
      L"base\\fs\\fsrm\\service\\modulewrp\\consumermodule.cpp",
      L"CNSMMODC",
      L"CConsumerModuleInproc::ProcessBatch",
      0x1A1u,
      v93);
  }
  v58 = 0;
  v59 = 0;
  v13 = CoTaskMemAlloc(40 * v10);
  v14 = v13;
}

```

## disassembly

```asm
0x180041f60  mov     r11, rsp
0x180041f63  push    rbx
0x180041f64  push    rsi
0x180041f65  push    rdi
0x180041f66  push    r12
0x180041f68  push    r13
0x180041f6a  push    r14
0x180041f6c  push    r15
0x180041f6e  sub     rsp, 300h
0x180041f75  mov     rax, cs:__security_cookie
0x180041f7c  xor     rax, rsp
0x180041f7f  mov     [rsp+338h+var_48], rax
0x180041f87  mov     r12, r9
0x180041f8a  mov     [rsp+338h+var_240], r9
0x180041f92  mov     esi, r8d
0x180041f95  mov     [rsp+338h+var_2C0], esi
0x180041f99  mov     r15, rcx
0x180041f9c  mov     [rsp+338h+var_2B0], rcx
0x180041fa4  mov     rax, [rsp+338h+arg_20]
0x180041fac  mov     [rsp+338h+var_230], rax
0x180041fb4  mov     rax, [rsp+338h+arg_38]
0x180041fbc  mov     [rsp+338h+var_238], rax
0x180041fc4  mov     r14, [rsp+338h+arg_40]
0x180041fcc  mov     [rsp+338h+var_298], r14
0x180041fd4  lea     rax, [r11-1E0h]
0x180041fdb  mov     [r11-2A0h], rax
0x180041fe2  lea     rax, aBaseFsFsrmServ_22; "base\\fs\\fsrm\\service\\modulewrp\\con"...
0x180041fe9  mov     [r11-1E0h], rax
0x180041ff0  lea     rax, aCconsumermodul; "CConsumerModuleInproc::ProcessBatch"
0x180041ff7  mov     [r11-1D8h], rax
0x180041ffe  lea     rax, aCnsmmodc; "CNSMMODC"
0x180042005  mov     [r11-1D0h], rax
0x18004200c  mov     [rsp+338h+var_1C8], 112h
0x180042017  mov     [rsp+338h+var_1C4], 16h
0x180042022  mov     [rsp+338h+var_1C0], 0FFh
0x18004202d  xor     r13d, r13d
0x180042030  mov     [rsp+338h+var_158], 1000000h
0x18004203b  xor     edx, edx; Val
0x18004203d  lea     r8d, [r13+60h]; Size
0x180042041  lea     rcx, [r11-1B8h]; void *
0x180042048  call    memset_0
0x18004204d  nop
0x18004204e  xor     r8d, r8d
0x180042051  lea     rdx, [rsp+338h+var_1E0]
0x180042059  lea     rcx, [rsp+338h+var_F8]
0x180042061  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180042066  nop
0x180042067  mov     [r14], r13
0x18004206a  mov     [rsp+338h+var_290], r13d
0x180042072  mov     [rsp+338h+var_288], r13
0x18004207a  lea     rbx, [rsi+rsi*4]
0x18004207e  shl     rbx, 3
0x180042082  mov     rcx, rbx; cb
0x180042085  call    cs:__imp_CoTaskMemAlloc
0x18004208b  mov     rdi, rax
0x18004208e  mov     [rsp+338h+var_2A0], rax
0x180042096  test    rax, rax
0x180042099  jz      loc_180042645
0x18004209f  mov     r8, rbx; Size
0x1800420a2  xor     edx, edx; Val
0x1800420a4  mov     rcx, rdi; void *
0x1800420a7  call    memset_0
0x1800420ac  mov     [rsp+338h+var_290], esi
0x1800420b3  mov     [rsp+338h+var_288], rdi
0x1800420bb  mov     [rsp+338h+var_2BC], r13d
0x1800420c0  cmp     r13d, esi
0x1800420c3  jnb     loc_1800425D2
0x1800420c9  mov     r8d, r13d
0x1800420cc  mov     rdx, [r12+r8*8]
0x1800420d0  test    rdx, rdx
0x1800420d3  jnz     short loc_1800420DA
0x1800420d5  jmp     loc_1800425CA
0x1800420da  xor     esi, esi
0x1800420dc  mov     [rsp+338h+var_2C8], rsi
0x1800420e1  mov     [rsp+338h+var_138], 7
0x1800420ed  mov     [rsp+338h+var_140], rsi
0x1800420f5  mov     word ptr [rsp+338h+var_150], si
0x1800420fd  mov     ebx, [rdx+30h]
0x180042100  mov     r14d, [rdx+34h]
0x180042104  mov     [rsp+338h+var_2D8], r14d
0x180042109  lea     rax, [r8+r8*4]
0x18004210d  lea     rcx, [rdi+rax*8]
0x180042111  lea     rax, [rsp+338h+var_2C8]
0x180042116  mov     [rsp+338h+var_2E8], rax
0x18004211b  mov     [rsp+338h+var_2F0], rsi
0x180042120  lea     rax, ?s_ftNeverModified@CPropertyBagProxy@@2VCSrmFileTime@@B; CSrmFileTime const CPropertyBagProxy::s_ftNeverModified
0x180042127  mov     [rsp+338h+var_2F8], rax
0x18004212c  mov     [rsp+338h+var_300], rcx
0x180042131  mov     rax, [rsp+338h+var_238]
0x180042139  mov     [rsp+338h+var_308], rax
0x18004213e  mov     [rsp+338h+var_310], rsi
0x180042143  mov     byte ptr [rsp+338h+var_318], sil
0x180042148  xor     r9d, r9d
0x18004214b  mov     rax, [rsp+338h+var_230]
0x180042153  mov     r8, [rax+r8*8]
0x180042157  mov     ecx, r13d
0x18004215a  call    ?CreateInstance@CPropertyBagProxy@@SAXKPEBU_FSRM_PROPERTYBAG_FIELDS@@PEBU_FSRM_PROPERTYBAG_ARRAYS@@PEBU_FSRM_PROPERTY_CACHE@@_NPEBU_FSRM_IN_FILE_SECURE_PROPERTIES@@PEAUIFsrmBatchedPipelineModuleCallback@@PEAU_FSRM_PROPERTYBAG_FIELDS_DELTA@@PEBVCSrmFileTime@@PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@@std@@@2@@std@@PEAPEAV?$CComObject@VCPropertyBagProxy@@@ATL@@@Z; CPropertyBagProxy::CreateInstance(ulong,_FSRM_PROPERTYBAG_FIELDS const *,_FSRM_PROPERTYBAG_ARRAYS const *,_FSRM_PROPERTY_CACHE const *,bool,_FSRM_IN_FILE_SECURE_PROPERTIES const *,IFsrmBatchedPipelineModuleCallback *,_FSRM_PROPERTYBAG_FIELDS_DELTA *,CSrmFileTime const *,std::map<std::wstring,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>>>> *,ATL::CComObject<CPropertyBagProxy> * *)
0x18004215f  mov     rdi, [rsp+338h+var_2C8]
0x180042164  lea     rcx, [rdi+58h]
0x180042168  lea     r9, [rsp+338h+var_150]
0x180042170  xor     r8d, r8d
0x180042173  mov     dl, 1
0x180042175  call    ?BuildFullPath@CPropertyBagFieldsBase@@QEBAX_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CPropertyBagFieldsBase::BuildFullPath(bool,ushort const *,std::wstring &)
0x18004217a  lea     rax, [rsp+338h+var_150]
0x180042182  cmp     [rsp+338h+var_138], 8
0x18004218b  cmovnb  rax, [rsp+338h+var_150]
0x180042194  mov     [rsp+338h+var_318], rax
0x180042199  lea     r9, aConsumingFilen; "Consuming filename: %s"
0x1800421a0  mov     edx, 8Ch; unsigned int
0x1800421a5  mov     r8d, 164h; unsigned int
0x1800421ab  lea     rcx, [rsp+338h+var_F8]; this
0x1800421b3  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800421b8  mov     [rsp+338h+var_2B8], rsi
0x1800421c0  mov     rax, [rdi]
0x1800421c3  lea     r8, [rsp+338h+var_2B8]
0x1800421cb  lea     rdx, _GUID_774589d1_d300_4f7a_9a24_f7b766800250
0x1800421d2  mov     rcx, rdi
0x1800421d5  mov     rax, [rax]
0x1800421d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421dd  mov     [rsp+338h+var_F0], eax
0x1800421e4  test    eax, eax
0x1800421e6  js      loc_1800426A6
0x1800421ec  mov     [rsp+338h+var_F0], eax
0x1800421f3  imul    r10, rbx, 38h ; '8'
0x1800421f7  add     r10, [r15+0B8h]
0x1800421fe  mov     [rsp+338h+var_260], r10
0x180042206  cmp     r14d, 0FFFFFFFFh
0x18004220a  jz      loc_18004254C
0x180042210  mov     eax, r14d
0x180042213  imul    rax, 58h ; 'X'
0x180042217  mov     [rsp+338h+var_250], rax
0x18004221f  mov     rdx, [r10+10h]
0x180042223  mov     [rsp+338h+var_268], rdx
0x18004222b  mov     r12, [rax+rdx+40h]
0x180042230  sub     r12, [rax+rdx+38h]
0x180042235  sar     r12, 3
0x180042239  mov     rcx, 8F5C28F5C28F5C29h
0x180042243  imul    r12, rcx
0x180042247  mov     r15, rsi
0x18004224a  mov     [rsp+338h+var_258], rsi
0x180042252  cmp     r15, r12
0x180042255  jnb     loc_18004253E
0x18004225b  imul    rsi, r15, 0C8h
0x180042262  add     rsi, [rax+rdx+38h]
0x180042267  xor     r8d, r8d
0x18004226a  cmp     [rsi+30h], r8b
0x18004226e  jnz     short loc_180042277
0x180042270  xor     esi, esi
0x180042272  jmp     loc_180042526
0x180042277  mov     rdx, [rsi+28h]
0x18004227b  lea     rax, [rsi+38h]
0x18004227f  cmp     qword ptr [rax+18h], 8
0x180042284  jb      short loc_180042289
0x180042286  mov     rax, [rax]
0x180042289  lea     rcx, [rdi+58h]
0x18004228d  mov     dword ptr [rsp+338h+var_2F8], r8d
0x180042292  mov     [rsp+338h+var_300], rdx
0x180042297  mov     [rsp+338h+var_308], rax
0x18004229c  mov     dword ptr [rsp+338h+var_310], r8d
0x1800422a1  mov     dword ptr [rsp+338h+var_318], 6
0x1800422a9  mov     r9, r15
0x1800422ac  mov     r8d, r14d
0x1800422af  mov     rdx, r10
0x1800422b2  call    ?SetContext@CPropertyBagFieldsContextual@@QEAAXPEBVCVolumeStructure@@K_KW4_FsrmPipelinePhase@@W4_FsrmStorageModuleTypeInternal@@PEBG4K@Z; CPropertyBagFieldsContextual::SetContext(CVolumeStructure const *,ulong,unsigned __int64,_FsrmPipelinePhase,_FsrmStorageModuleTypeInternal,ushort const *,ushort const *,ulong)
0x1800422b7  lea     r14, [rsi+98h]
0x1800422be  mov     rax, [rsp+338h+var_2B0]
0x1800422c6  mov     rbx, [rax+68h]
0x1800422ca  mov     rdi, [rbx+8]
0x1800422ce  mov     [rsp+338h+var_2A8], rdi
0x1800422d6  mov     [rsp+338h+var_280], rbx
0x1800422de  cmp     byte ptr [rdi+49h], 0
0x1800422e2  jnz     short loc_18004232C
0x1800422e4  lea     rcx, [rdi+18h]
0x1800422e8  cmp     qword ptr [rsi+0B0h], 8
0x1800422f0  jb      short loc_1800422F7
0x1800422f2  mov     rdx, [r14]
0x1800422f5  jmp     short loc_1800422FA
0x1800422f7  mov     rdx, r14; String2
0x1800422fa  cmp     qword ptr [rcx+18h], 8
0x1800422ff  jb      short loc_180042304
0x180042301  mov     rcx, [rcx]; String1
0x180042304  call    cs:__imp__wcsicmp
0x18004230a  test    eax, eax
0x18004230c  jns     short loc_180042314
0x18004230e  mov     rdi, [rdi+10h]
0x180042312  jmp     short loc_180042322
0x180042314  mov     rbx, rdi
0x180042317  mov     [rsp+338h+var_280], rbx
0x18004231f  mov     rdi, [rdi]
0x180042322  mov     [rsp+338h+var_2A8], rdi
0x18004232a  jmp     short loc_1800422DE
0x18004232c  mov     rdi, [rsp+338h+var_2B0]
0x180042334  mov     [rsp+338h+var_270], rbx
0x18004233c  mov     rax, [rdi+68h]
0x180042340  mov     [rsp+338h+var_1E8], rax
0x180042348  cmp     rbx, rax
0x18004234b  jz      short loc_180042385
0x18004234d  lea     rdx, [rbx+18h]
0x180042351  mov     eax, 18h
0x180042356  cmp     qword ptr [rdx+18h], 8
0x18004235b  jb      short loc_180042360
0x18004235d  mov     rdx, [rdx]; String2
0x180042360  cmp     qword ptr [rax+rsi+98h], 8
0x180042369  jb      short loc_180042370
0x18004236b  mov     rcx, [r14]
0x18004236e  jmp     short loc_180042373
0x180042370  mov     rcx, r14; String1
0x180042373  call    cs:__imp__wcsicmp
0x180042379  xor     esi, esi
0x18004237b  test    eax, eax
0x18004237d  jns     loc_1800424B2
0x180042383  jmp     short loc_180042387
0x180042385  xor     esi, esi
0x180042387  lea     rax, [rsp+338h+var_2D0]
0x18004238c  mov     [rsp+338h+var_228], rax
0x180042394  mov     [rsp+338h+var_2D0], rsi
0x180042399  mov     rdx, r14
0x18004239c  lea     rcx, [rsp+338h+Block]
0x1800423a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800423a9  nop
0x1800423aa  lea     rax, [rsp+338h+var_100]
0x1800423b2  mov     [rsp+338h+var_220], rax
0x1800423ba  lea     rax, [rsp+338h+var_100]
0x1800423c2  mov     [rsp+338h+var_218], rax
0x1800423ca  mov     rcx, [rsp+338h+var_2D0]
0x1800423cf  mov     [rsp+338h+var_100], rcx
0x1800423d7  test    rcx, rcx
0x1800423da  jz      short loc_1800423E9
0x1800423dc  mov     rax, [rcx]
0x1800423df  mov     rax, [rax+8]
0x1800423e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423e8  nop
0x1800423e9  lea     rdx, [rsp+338h+Block]
0x1800423f1  lea     rcx, [rdi+60h]
0x1800423f5  call    ??$_Buynode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineConsumer@@@ATL@@@ATL@@@std@@@?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineConsumer@@@ATL@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineConsumer@@@ATL@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineConsumer@@@ATL@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineConsumer@@@ATL@@@ATL@@@std@@@2@$0A@@std@@@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineConsumer@@@ATL@@@ATL@@@1@@Z; std::_Tree_val<std::_Tmap_traits<std::wstring,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineConsumer>>,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineConsumer>>>>,0>>::_Buynode<std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineConsumer>>>>(std::pair<std::wstring const,ATL::CAdapt<ATL::CComPtr<IFsrmPipelineConsumer>>> &&)
0x1800423fa  mov     r9, rax
0x1800423fd  mov     r8, rbx
0x180042400  lea     rdx, [rsp+338h+var_278]
0x180042408  lea     rcx, [rdi+60h]
0x18004240c  call    ?_Insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@@std@@@2@$0A@@std@@@std@@@2@PEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CComPtr@UIFsrmPipelineModuleDefinition@@@ATL@@@ATL@@@std@@@2@$0A@@std@@@2@@Z
0x180042411  mov     rbx, [rsp+338h+var_278]
0x180042419  mov     [rsp+338h+var_270], rbx
0x180042421  lea     rax, [rsp+338h+var_100]
0x180042429  mov     [rsp+338h+var_210], rax
0x180042431  lea     rax, [rsp+338h+var_100]
0x180042439  mov     [rsp+338h+var_208], rax
0x180042441  mov     rcx, [rsp+338h+var_100]
0x180042449  test    rcx, rcx
0x18004244c  jz      short loc_18004245B
0x18004244e  mov     rax, [rcx]
0x180042451  mov     rax, [rax+10h]
0x180042455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004245a  nop
0x18004245b  cmp     [rsp+338h+var_110], 8
0x180042464  jb      short loc_180042473
0x180042466  mov     rcx, [rsp+338h+Block]; Block
0x18004246e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180042473  mov     [rsp+338h+var_110], 7
0x18004247f  mov     [rsp+338h+var_118], rsi
0x180042487  mov     word ptr [rsp+338h+Block], si
0x18004248f  lea     rax, [rsp+338h+var_2D0]
0x180042494  mov     [rsp+338h+var_200], rax
0x18004249c  mov     rcx, [rsp+338h+var_2D0]
0x1800424a1  test    rcx, rcx
0x1800424a4  jz      short loc_1800424B2
0x1800424a6  mov     rax, [rcx]
0x1800424a9  mov     rax, [rax+10h]
0x1800424ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424b2  mov     rcx, [rbx+40h]
0x1800424b6  mov     rax, [rcx]
0x1800424b9  mov     rdx, [rsp+338h+var_2B8]
0x1800424c1  mov     rax, [rax+60h]
0x1800424c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424ca  mov     [rsp+338h+var_F0], eax
0x1800424d1  mov     rdi, [rsp+338h+var_2C8]
0x1800424d6  cmp     eax, 8004537Ah
0x1800424db  jnz     short loc_1800424FB
0x1800424dd  lea     rcx, [rdi+58h]
0x1800424e1  mov     rax, [rcx]
0x1800424e4  mov     edx, 4000h
0x1800424e9  mov     rax, [rax+38h]
0x1800424ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424f2  mov     eax, esi
0x1800424f4  mov     [rsp+338h+var_F0], eax
0x1800424fb  mov     [rsp+338h+var_F0], eax
0x180042502  test    eax, eax
0x180042504  js      loc_1800426E7
0x18004250a  mov     [rsp+338h+var_F0], eax
0x180042511  mov     rdx, [rsp+338h+var_268]
0x180042519  mov     r10, [rsp+338h+var_260]
0x180042521  mov     r14d, [rsp+338h+var_2D8]
0x180042526  inc     r15
0x180042529  mov     [rsp+338h+var_258], r15
0x180042531  mov     rax, [rsp+338h+var_250]
0x180042539  jmp     loc_180042252
0x18004253e  mov     r14d, [rax+rdx]
0x180042542  mov     [rsp+338h+var_2D8], r14d
0x180042547  jmp     loc_180042206
0x18004254c  mov     rcx, [rsp+338h+var_2B8]
0x180042554  test    rcx, rcx
  ... truncated ...
```
