# Microsoft::Diagnostics::CensusTaskData::QueryCensusTaskEnabled(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1802dfdb8`
- end: `0x1802e02cd`
- name: `?QueryCensusTaskEnabled@CensusTaskData@Diagnostics@Microsoft@@IEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z`
- size: `1301`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1802e02d4`

## callees

- `0x180026ecc`
- `0x180053a84`
- `0x1800807c8`
- `0x1800b2ccc`
- `0x1801cd790`
- `0x180271a20`
- `0x1802dfdb8`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802dfe02`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802dfe02`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1802dfef1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1802dff28`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1802dfef1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1802dff28`

## string_xrefs

- `0x1802dfe1f`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x1802dfec8`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x1802dff0d`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x1802dff41`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x1802dff89`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x1802e0000`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x1802e0081`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::Diagnostics::CensusTaskData::QueryCensusTaskEnabled(_DWORD *a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  int v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  BSTR v12; // rax
  const char *v13; // r9
  BSTR v14; // rbx
  BSTR v15; // rax
  const char *v16; // r9
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  int i; // esi
  __int64 v27; // rax
  __int64 v28; // rdi
  int (__fastcall *v29)(__int64, __int64 *); // rbx
  __int64 v30; // rax
  int ppv; // [rsp+20h] [rbp-F8h]
  LPVOID v32; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v33; // [rsp+38h] [rbp-E0h] BYREF
  __int64 *v34; // [rsp+40h] [rbp-D8h] BYREF
  __int64 *v35; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-C8h] BYREF
  BSTR v37; // [rsp+58h] [rbp-C0h] BYREF
  _QWORD v38[2]; // [rsp+60h] [rbp-B8h] BYREF
  int v39[4]; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+80h] [rbp-98h]
  __int128 v41; // [rsp+90h] [rbp-88h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-78h]
  __int128 v43; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-58h]
  __int128 v45; // [rsp+D0h] [rbp-48h]
  __int64 v46; // [rsp+E0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  int v48; // [rsp+120h] [rbp+8h] BYREF
  int v49; // [rsp+138h] [rbp+20h] BYREF

  *a1 = -1;
  v32 = 0;
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v32);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *(_OWORD *)v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v45 = 0;
    v46 = 0;
    v43 = 0;
    v44 = 0;
    try
    {
      v9 = (*(__int64 (**)(void))(*(_QWORD *)v32 + 80LL))();
      v10 = v9;
      if ( v9 >= 0 )
      {
        v12 = SysAllocStringLen(*(const OLECHAR **)a2, *(_DWORD *)(a2 + 8));
        v14 = v12;
        if ( !v12 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x38,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
            v13);
        v38[0] = v12;
        v15 = SysAllocStringLen(*(const OLECHAR **)a3, *(_DWORD *)(a3 + 8));
        if ( !v15 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x39,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
            v16);
        v37 = v15;
        v35 = 0;
        v17 = *(_QWORD *)v32;
        v35 = 0;
        v18 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 **))(v17 + 56))(v32, v14, &v35);
        v19 = v18;
        if ( v18 >= 0 )
        {
          v34 = 0;
          v20 = *v35;
          v34 = 0;
          v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v20 + 112))(v35, 0, &v34);
          v22 = v21;
          if ( v21 >= 0 )
          {
            v49 = 0;
            v23 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v34 + 56))(v34, &v49);
            v24 = v23;
            if ( v23 >= 0 )
            {
              v25 = v49;
              if ( v49 )
              {
                for ( i = 1; i <= v25; ++i )
                {
                  v33 = 0;
                  *(_OWORD *)v39 = 0;
                  LOWORD(v39[0]) = 3;
                  v39[2] = i;
                  v27 = *v34;
                  v33 = 0;
                  v43 = *(_OWORD *)v39;
                  v44 = 0;
                  if ( (*(int (__fastcall **)(__int64 *, __int128 *, __int64 *))(v27 + 64))(v34, &v43, &v33) >= 0 )
                  {
                    v36 = 0;
                    v28 = v33;
                    v29 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 56LL);
                    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
                      &v36,
                      0);
                    if ( v29(v28, &v36) >= 0 )
                    {
                      v30 = -1;
                      do
                        ++v30;
                      while ( *(_WORD *)(v36 + 2 * v30) );
                      *(_QWORD *)&v41 = v36;
                      *((_QWORD *)&v41 + 1) = v30;
                      *(_OWORD *)v39 = *(_OWORD *)a3;
                      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v39, &v41) )
                      {
                        LOWORD(v48) = 0;
                        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 80LL))(v33, &v48) >= 0 )
                        {
                          *a1 = (_WORD)v48 != 0;
                          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v36);
                          wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v33);
                          break;
                        }
                      }
                    }
                    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v36);
                  }
                  wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v33);
                  v25 = v49;
                }
              }
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v34);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v35);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v37);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v38);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v32);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x42,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
                (const char *)(unsigned int)v23,
                (int)v39);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v34);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v35);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v37);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v38);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v32);
              result = v24;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
              (const char *)(unsigned int)v21,
              (int)v39);
            wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v34);
            wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v35);
            wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v37);
            wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v38);
            wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v32);
            result = v22;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
            (const char *)(unsigned int)v18,
            (int)v39);
          wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v37);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v38);
          wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v32);
          result = v19;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
          (const char *)(unsigned int)v9,
          (int)v39);
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v32);
        result = v10;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x66,
                             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
                             v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v32);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1802dfdb8  mov     [rsp+arg_8], rbx
0x1802dfdbd  push    rsi
0x1802dfdbe  push    rdi
0x1802dfdbf  push    r12
0x1802dfdc1  push    r14
0x1802dfdc3  push    r15
0x1802dfdc5  sub     rsp, 0F0h
0x1802dfdcc  mov     r14, r8
0x1802dfdcf  mov     rdi, rdx
0x1802dfdd2  mov     r15, rcx
0x1802dfdd5  mov     dword ptr [rcx], 0FFFFFFFFh
0x1802dfddb  xor     r12d, r12d
0x1802dfdde  mov     [rsp+118h+var_E8], r12
0x1802dfde3  lea     rax, [rsp+118h+var_E8]
0x1802dfde8  mov     qword ptr [rsp+118h+ppv], rax; int
0x1802dfded  lea     r9, IID_ITaskService; riid
0x1802dfdf4  xor     edx, edx; pUnkOuter
0x1802dfdf6  lea     r8d, [r12+1]; dwClsContext
0x1802dfdfb  lea     rcx, CLSID_TaskScheduler; rclsid
0x1802dfe02  call    cs:__imp_CoCreateInstance
0x1802dfe09  nop     dword ptr [rax+rax+00h]
0x1802dfe0e  mov     ebx, eax
0x1802dfe10  test    eax, eax
0x1802dfe12  jns     short loc_1802DFE42
0x1802dfe14  mov     rcx, [rsp+118h]; this
0x1802dfe1c  mov     r9d, eax; char *
0x1802dfe1f  lea     r8, aOnecoreBaseTel_138; "onecore\\base\\telemetry\\utc\\service"...
0x1802dfe26  lea     edx, [r12+32h]; void *
0x1802dfe2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802dfe30  nop
0x1802dfe31  lea     rcx, [rsp+118h+var_E8]
0x1802dfe36  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802dfe3b  mov     eax, ebx
0x1802dfe3d  jmp     loc_1802E028F
0x1802dfe42  xorps   xmm1, xmm1
0x1802dfe45  xor     eax, eax
0x1802dfe47  mov     rcx, [rsp+118h+var_E8]
0x1802dfe4c  movaps  xmmword ptr [rsp+118h+var_A8], xmm1
0x1802dfe51  mov     [rsp+118h+var_98], rax
0x1802dfe59  movaps  [rsp+118h+var_88], xmm1
0x1802dfe61  mov     [rsp+118h+var_78], rax
0x1802dfe69  movaps  [rsp+118h+var_48], xmm1
0x1802dfe71  mov     [rsp+118h+var_38], rax
0x1802dfe79  movaps  [rsp+118h+var_68], xmm1
0x1802dfe81  mov     [rsp+118h+var_58], rax
0x1802dfe89  mov     rax, [rcx]
0x1802dfe8c  lea     rdx, [rsp+118h+var_A8]
0x1802dfe91  mov     qword ptr [rsp+118h+ppv], rdx; int
0x1802dfe96  lea     r9, [rsp+118h+var_88]
0x1802dfe9e  lea     r8, [rsp+118h+var_48]
0x1802dfea6  lea     rdx, [rsp+118h+var_68]
0x1802dfeae  mov     rax, [rax+50h]
0x1802dfeb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802dfeb7  mov     ebx, eax
0x1802dfeb9  test    eax, eax
0x1802dfebb  jns     short loc_1802DFEEB
0x1802dfebd  mov     rcx, [rsp+118h]; this
0x1802dfec5  mov     r9d, eax; char *
0x1802dfec8  lea     r8, aOnecoreBaseTel_138; "onecore\\base\\telemetry\\utc\\service"...
0x1802dfecf  mov     edx, 36h ; '6'; void *
0x1802dfed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802dfed9  nop
0x1802dfeda  lea     rcx, [rsp+118h+var_E8]
0x1802dfedf  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802dfee4  mov     eax, ebx
0x1802dfee6  jmp     loc_1802E028F
0x1802dfeeb  mov     edx, [rdi+8]; ui
0x1802dfeee  mov     rcx, [rdi]; strIn
0x1802dfef1  call    cs:__imp_SysAllocStringLen
0x1802dfef8  nop     dword ptr [rax+rax+00h]
0x1802dfefd  mov     rbx, rax
0x1802dff00  mov     rcx, [rsp+118h]; this
0x1802dff08  test    rax, rax
0x1802dff0b  jnz     short loc_1802DFF1C
0x1802dff0d  lea     r8, aOnecoreBaseTel_138; "onecore\\base\\telemetry\\utc\\service"...
0x1802dff14  lea     edx, [rax+38h]; void *
0x1802dff17  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1802dff1c  mov     [rsp+118h+var_B8], rbx
0x1802dff21  mov     edx, [r14+8]; ui
0x1802dff25  mov     rcx, [r14]; strIn
0x1802dff28  call    cs:__imp_SysAllocStringLen
0x1802dff2f  nop     dword ptr [rax+rax+00h]
0x1802dff34  mov     rcx, [rsp+118h]; this
0x1802dff3c  test    rax, rax
0x1802dff3f  jnz     short loc_1802DFF50
0x1802dff41  lea     r8, aOnecoreBaseTel_138; "onecore\\base\\telemetry\\utc\\service"...
0x1802dff48  lea     edx, [rax+39h]; void *
0x1802dff4b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1802dff50  mov     [rsp+118h+var_C0], rax
0x1802dff55  mov     [rsp+118h+var_D0], r12
0x1802dff5a  mov     rcx, [rsp+118h+var_E8]
0x1802dff5f  mov     rax, [rcx]
0x1802dff62  mov     [rsp+118h+var_D0], r12
0x1802dff67  lea     r8, [rsp+118h+var_D0]
0x1802dff6c  mov     rdx, rbx
0x1802dff6f  mov     rax, [rax+38h]
0x1802dff73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802dff78  mov     ebx, eax
0x1802dff7a  test    eax, eax
0x1802dff7c  jns     short loc_1802DFFCD
0x1802dff7e  mov     rcx, [rsp+118h]; this
0x1802dff86  mov     r9d, eax; char *
0x1802dff89  lea     r8, aOnecoreBaseTel_138; "onecore\\base\\telemetry\\utc\\service"...
0x1802dff90  mov     edx, 3Ch ; '<'; void *
0x1802dff95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802dff9a  nop
0x1802dff9b  lea     rcx, [rsp+118h+var_D0]
0x1802dffa0  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802dffa5  nop
0x1802dffa6  lea     rcx, [rsp+118h+var_C0]
0x1802dffab  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802dffb0  nop
0x1802dffb1  lea     rcx, [rsp+118h+var_B8]
0x1802dffb6  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802dffbb  nop
0x1802dffbc  lea     rcx, [rsp+118h+var_E8]
0x1802dffc1  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802dffc6  mov     eax, ebx
0x1802dffc8  jmp     loc_1802E028F
0x1802dffcd  mov     [rsp+118h+var_D8], r12
0x1802dffd2  mov     rcx, [rsp+118h+var_D0]
0x1802dffd7  mov     rax, [rcx]
0x1802dffda  mov     [rsp+118h+var_D8], r12
0x1802dffdf  lea     r8, [rsp+118h+var_D8]
0x1802dffe4  xor     edx, edx
0x1802dffe6  mov     rax, [rax+70h]
0x1802dffea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802dffef  mov     ebx, eax
0x1802dfff1  test    eax, eax
0x1802dfff3  jns     short loc_1802E004F
0x1802dfff5  mov     rcx, [rsp+118h]; this
0x1802dfffd  mov     r9d, eax; char *
0x1802e0000  lea     r8, aOnecoreBaseTel_138; "onecore\\base\\telemetry\\utc\\service"...
0x1802e0007  mov     edx, 3Fh ; '?'; void *
0x1802e000c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802e0011  nop
0x1802e0012  lea     rcx, [rsp+118h+var_D8]
0x1802e0017  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e001c  nop
0x1802e001d  lea     rcx, [rsp+118h+var_D0]
0x1802e0022  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e0027  nop
0x1802e0028  lea     rcx, [rsp+118h+var_C0]
0x1802e002d  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e0032  nop
0x1802e0033  lea     rcx, [rsp+118h+var_B8]
0x1802e0038  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e003d  nop
0x1802e003e  lea     rcx, [rsp+118h+var_E8]
0x1802e0043  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e0048  mov     eax, ebx
0x1802e004a  jmp     loc_1802E028F
0x1802e004f  mov     [rsp+118h+arg_18], r12d
0x1802e0057  mov     rcx, [rsp+118h+var_D8]
0x1802e005c  mov     rax, [rcx]
0x1802e005f  lea     rdx, [rsp+118h+arg_18]
0x1802e0067  mov     rax, [rax+38h]
0x1802e006b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e0070  mov     ebx, eax
0x1802e0072  test    eax, eax
0x1802e0074  jns     short loc_1802E00D0
0x1802e0076  mov     rcx, [rsp+118h]; this
0x1802e007e  mov     r9d, eax; char *
0x1802e0081  lea     r8, aOnecoreBaseTel_138; "onecore\\base\\telemetry\\utc\\service"...
0x1802e0088  mov     edx, 42h ; 'B'; void *
0x1802e008d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802e0092  nop
0x1802e0093  lea     rcx, [rsp+118h+var_D8]
0x1802e0098  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e009d  nop
0x1802e009e  lea     rcx, [rsp+118h+var_D0]
0x1802e00a3  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e00a8  nop
0x1802e00a9  lea     rcx, [rsp+118h+var_C0]
0x1802e00ae  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e00b3  nop
0x1802e00b4  lea     rcx, [rsp+118h+var_B8]
0x1802e00b9  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e00be  nop
0x1802e00bf  lea     rcx, [rsp+118h+var_E8]
0x1802e00c4  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e00c9  mov     eax, ebx
0x1802e00cb  jmp     loc_1802E028F
0x1802e00d0  mov     eax, [rsp+118h+arg_18]
0x1802e00d7  test    eax, eax
0x1802e00d9  jnz     short loc_1802E0118
0x1802e00db  lea     rcx, [rsp+118h+var_D8]
0x1802e00e0  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e00e5  nop
0x1802e00e6  lea     rcx, [rsp+118h+var_D0]
0x1802e00eb  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e00f0  nop
0x1802e00f1  lea     rcx, [rsp+118h+var_C0]
0x1802e00f6  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e00fb  nop
0x1802e00fc  lea     rcx, [rsp+118h+var_B8]
0x1802e0101  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e0106  nop
0x1802e0107  lea     rcx, [rsp+118h+var_E8]
0x1802e010c  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e0111  xor     eax, eax
0x1802e0113  jmp     loc_1802E028F
0x1802e0118  mov     esi, 1
0x1802e011d  cmp     esi, eax
0x1802e011f  jg      loc_1802E024E
0x1802e0125  mov     [rsp+118h+var_E0], r12
0x1802e012a  xorps   xmm0, xmm0
0x1802e012d  xor     edx, edx
0x1802e012f  movups  xmmword ptr [rsp+118h+var_A8], xmm0
0x1802e0134  lea     eax, [rdx+3]
0x1802e0137  mov     word ptr [rsp+118h+var_A8], ax
0x1802e013c  mov     [rsp+118h+var_A8+8], esi
0x1802e0140  mov     rcx, [rsp+118h+var_D8]
0x1802e0145  mov     rax, [rcx]
0x1802e0148  mov     [rsp+118h+var_E0], r12
0x1802e014d  movups  xmm0, xmmword ptr [rsp+118h+var_A8]
0x1802e0152  movaps  [rsp+118h+var_68], xmm0
0x1802e015a  mov     [rsp+118h+var_58], rdx
0x1802e0162  lea     r8, [rsp+118h+var_E0]
0x1802e0167  lea     rdx, [rsp+118h+var_68]
0x1802e016f  mov     rax, [rax+40h]
0x1802e0173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e0178  test    eax, eax
0x1802e017a  js      loc_1802E02B3
0x1802e0180  mov     [rsp+118h+var_C8], r12
0x1802e0185  mov     rdi, [rsp+118h+var_E0]
0x1802e018a  mov     rax, [rdi]
0x1802e018d  mov     rbx, [rax+38h]
0x1802e0191  xor     edx, edx
0x1802e0193  lea     rcx, [rsp+118h+var_C8]
0x1802e0198  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1802e019d  lea     rdx, [rsp+118h+var_C8]
0x1802e01a2  mov     rcx, rdi
0x1802e01a5  mov     rax, rbx
0x1802e01a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e01ad  test    eax, eax
0x1802e01af  js      loc_1802E02A8
0x1802e01b5  mov     rcx, [rsp+118h+var_C8]
0x1802e01ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802e01be  inc     rax
0x1802e01c1  cmp     [rcx+rax*2], r12w
0x1802e01c6  jnz     short loc_1802E01BE
0x1802e01c8  mov     qword ptr [rsp+118h+var_88], rcx
0x1802e01d0  mov     qword ptr [rsp+118h+var_88+8], rax
0x1802e01d8  movaps  xmm0, xmmword ptr [r14]
0x1802e01dc  movdqa  xmmword ptr [rsp+118h+var_A8], xmm0
0x1802e01e2  lea     rdx, [rsp+118h+var_88]
0x1802e01ea  lea     rcx, [rsp+118h+var_A8]
0x1802e01ef  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802e01f4  test    eax, eax
0x1802e01f6  jnz     loc_1802E02A8
0x1802e01fc  mov     word ptr [rsp+118h+arg_0], r12w
0x1802e0205  mov     rcx, [rsp+118h+var_E0]
0x1802e020a  mov     rax, [rcx]
0x1802e020d  lea     rdx, [rsp+118h+arg_0]
0x1802e0215  mov     rax, [rax+50h]
0x1802e0219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e021e  test    eax, eax
0x1802e0220  js      loc_1802E02A8
0x1802e0226  mov     eax, r12d
0x1802e0229  cmp     word ptr [rsp+118h+arg_0], r12w
0x1802e0232  setnz   al
0x1802e0235  mov     [r15], eax
0x1802e0238  lea     rcx, [rsp+118h+var_C8]
0x1802e023d  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e0242  nop
0x1802e0243  lea     rcx, [rsp+118h+var_E0]
0x1802e0248  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e024d  nop
0x1802e024e  lea     rcx, [rsp+118h+var_D8]
0x1802e0253  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e0258  nop
0x1802e0259  lea     rcx, [rsp+118h+var_D0]
0x1802e025e  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e0263  nop
0x1802e0264  lea     rcx, [rsp+118h+var_C0]
0x1802e0269  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e026e  nop
0x1802e026f  lea     rcx, [rsp+118h+var_B8]
0x1802e0274  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e0279  nop
0x1802e027a  lea     rcx, [rsp+118h+var_E8]
0x1802e027f  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e0284  xor     eax, eax
0x1802e0286  jmp     short loc_1802E028F
0x1802e0288  mov     eax, [rsp+118h+arg_0]
0x1802e028f  mov     rbx, [rsp+118h+arg_8]
0x1802e0297  add     rsp, 0F0h
0x1802e029e  pop     r15
0x1802e02a0  pop     r14
0x1802e02a2  pop     r12
0x1802e02a4  pop     rdi
0x1802e02a5  pop     rsi
0x1802e02a6  retn
0x1802e02a8  lea     rcx, [rsp+118h+var_C8]
0x1802e02ad  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e02b2  nop
0x1802e02b3  lea     rcx, [rsp+118h+var_E0]
0x1802e02b8  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802e02bd  inc     esi
  ... truncated ...
```
