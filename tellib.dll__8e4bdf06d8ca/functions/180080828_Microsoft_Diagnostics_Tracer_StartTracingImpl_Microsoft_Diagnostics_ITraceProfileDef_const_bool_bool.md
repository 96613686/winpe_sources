# Microsoft::Diagnostics::Tracer::StartTracingImpl(Microsoft::Diagnostics::ITraceProfileDef const &,bool,bool &)

- ea: `0x180080828`
- end: `0x180080d8e`
- name: `?StartTracingImpl@Tracer@Diagnostics@Microsoft@@AEAAJAEBVITraceProfileDef@23@_NAEA_N@Z`
- size: `1382`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::Tracer *__hidden this, const struct Microsoft::Diagnostics::ITraceProfileDef *, bool, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802714bc`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180031e2c`
- `0x1800807c8`
- `0x180080828`
- `0x180080d94`
- `0x180080df0`
- `0x1800b2ccc`
- `0x1800effa4`
- `0x18012de40`
- `0x180262cf4`
- `0x18026f320`
- `0x18027061c`
- `0x180271a90`
- `0x180346010`

## import_xrefs

- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x1800808d6`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x1800809a3`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x1800808d6`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x1800809a3`

## string_xrefs

- `0x1800808fd`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x1800809ca`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080a5e`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080ab7`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080b0d`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080b70`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080bdc`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080c48`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080c9c`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080cfb`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180080d49`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Diagnostics::Tracer::StartTracingImpl(
        Microsoft::Diagnostics::Tracer *this,
        const struct Microsoft::Diagnostics::ITraceProfileDef *a2,
        char a3,
        bool *a4)
{
  int CurrentTraceProfileCollection; // eax
  const char *v8; // r9
  unsigned int v9; // edi
  _QWORD *v10; // r14
  char *v11; // rdi
  char *v12; // rdx
  _QWORD *bstr; // rax
  int v14; // esi
  __int64 v15; // rdx
  __int64 result; // rax
  _QWORD *v17; // rsi
  _QWORD *v18; // rax
  int v19; // edi
  __int64 v20; // rdx
  _QWORD *v21; // rax
  int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // edi
  __int64 v31; // rdx
  int v32; // eax
  unsigned int v33; // edi
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  unsigned int v39; // edi
  __int64 v40; // rdx
  int v41; // eax
  unsigned int v42; // edi
  __int64 v43; // rdx
  int v44; // eax
  unsigned int v45; // edi
  __int64 v46; // rdx
  __int64 v47; // rdx
  int v48; // [rsp+20h] [rbp-A8h]
  _QWORD v49[2]; // [rsp+30h] [rbp-98h] BYREF
  __int128 v50; // [rsp+40h] [rbp-88h] BYREF
  Microsoft::Diagnostics::Tracer *v51; // [rsp+50h] [rbp-78h]
  char v52; // [rsp+58h] [rbp-70h]
  _BYTE v53[16]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v54[32]; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  try
  {
    v51 = this;
    v52 = 1;
    *(_BYTE *)this = a3;
    *a4 = 0;
    *((_BYTE *)this + 176) = 0;
    CurrentTraceProfileCollection = Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(this, 1);
    v9 = CurrentTraceProfileCollection;
    if ( CurrentTraceProfileCollection == -984076288 )
    {
      v10 = (_QWORD *)((char *)this + 200);
      wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset((char *)this + 200);
      wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset((char *)this + 200);
      v11 = (char *)this + 96;
      if ( *((_QWORD *)this + 15) <= 7u )
        v12 = (char *)this + 96;
      else
        v12 = *(char **)v11;
      bstr = (_QWORD *)wil::make_bstr(&v50, v12);
      v14 = WPRCCreateInstanceUnderInstanceName(*bstr, &GUID_b98b53f3_83ba_4837_8946_e886be8d4003, 0, 1);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v50);
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x228,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v14,
          (int)&GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a);
        LOBYTE(v15) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v15);
        return (unsigned int)v14;
      }
      v17 = (_QWORD *)((char *)this + 208);
      if ( *((_QWORD *)this + 26) )
      {
        wil::com_ptr_t<IProfile,wil::err_exception_policy>::query<WindowsPerformanceRecorder::IProfileElement>(
          (char *)this + 208,
          &v50);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v50 + 32LL))(v50);
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v50);
      }
      wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset((char *)this + 208);
      wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset((char *)this + 208);
      if ( *((_QWORD *)this + 15) > 7u )
        v11 = *(char **)v11;
      v18 = (_QWORD *)wil::make_bstr(&v50, v11);
      v19 = WPRCCreateInstanceUnderInstanceName(*v18, &GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4, 0, 1);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v50);
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x238,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v19,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        LOBYTE(v20) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v20);
        return (unsigned int)v19;
      }
      v50 = *(_OWORD *)Microsoft::Diagnostics::ITraceProfileDef::GetProfile(a2, v53);
      v21 = (_QWORD *)Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(v54, &v50);
      if ( v21[3] > 7u )
        v21 = (_QWORD *)*v21;
      wil::make_bstr(v49, v21);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
      v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v17 + 208LL))(*v17, v49[0]);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v22,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
        LOBYTE(v24) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v24);
        return v23;
      }
      v25 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v17 + 152LL))(*v17, (char *)this + 160);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v25,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
        LOBYTE(v27) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v27);
        return v26;
      }
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v10 + 56LL))(*v10, *v17, 0xFFFFFFFFLL);
      v30 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v28,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
        LOBYTE(v31) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v31);
        return v30;
      }
      if ( !*((_BYTE *)this + 1) )
      {
        v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 72LL))(
                *((_QWORD *)this + 23),
                *v10);
        v33 = v32;
        if ( v32 < 0 && v32 != -984076287 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x243,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
            (const char *)(unsigned int)v32,
            (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
          LOBYTE(v34) = 0;
          Microsoft::Diagnostics::Tracer::CancelTracing(this, v34);
          return v33;
        }
      }
      if ( *(_BYTE *)this || *((_BYTE *)this + 1) )
      {
        *(_QWORD *)&v50 = 0;
        if ( !(unsigned __int8)wil::com_ptr_t<IControlManager,wil::err_exception_policy>::try_query_to(
                                 (char *)this + 184,
                                 v29,
                                 &v50) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x250,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
            (const char *)0x80004005LL,
            (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
          wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v50);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
          LOBYTE(v35) = 0;
          Microsoft::Diagnostics::Tracer::CancelTracing(this, v35);
          return 2147500037LL;
        }
        v36 = *((_QWORD *)this + 25);
        v37 = *(_QWORD *)v50;
        if ( *(_BYTE *)this )
        {
          v38 = (*(__int64 (__fastcall **)(_QWORD, __int64))(v37 + 56))(v50, v36);
          v39 = v38;
          if ( v38 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x253,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
              (const char *)(unsigned int)v38,
              (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
            wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v50);
            wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
            LOBYTE(v40) = 0;
            Microsoft::Diagnostics::Tracer::CancelTracing(this, v40);
            return v39;
          }
        }
        else
        {
          v41 = (*(__int64 (__fastcall **)(_QWORD, __int64))(v37 + 72))(v50, v36);
          v42 = v41;
          if ( v41 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x257,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
              (const char *)(unsigned int)v41,
              (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
            wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v50);
            wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
            LOBYTE(v43) = 0;
            Microsoft::Diagnostics::Tracer::CancelTracing(this, v43);
            return v42;
          }
        }
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v50);
      }
      v44 = Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(this, 1);
      v45 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x25C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v44,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
        LOBYTE(v46) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v46);
        return v45;
      }
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v49);
      return 0;
    }
    if ( CurrentTraceProfileCollection >= 0 )
    {
      *a4 = 1;
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
      (const char *)(unsigned int)CurrentTraceProfileCollection,
      v48);
    LOBYTE(v47) = 0;
    Microsoft::Diagnostics::Tracer::CancelTracing(this, v47);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x26B,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180080828  push    rbx
0x18008082a  push    rsi
0x18008082b  push    rdi
0x18008082c  push    r14
0x18008082e  push    r15
0x180080830  sub     rsp, 0A0h
0x180080837  mov     rax, cs:__security_cookie
0x18008083e  xor     rax, rsp
0x180080841  mov     [rsp+0C8h+var_38], rax
0x180080849  mov     rsi, r9
0x18008084c  mov     r15, rdx
0x18008084f  mov     rbx, rcx
0x180080852  mov     [rsp+0C8h+var_78], rcx
0x180080857  mov     [rsp+0C8h+var_70], 1
0x18008085c  mov     [rcx], r8b
0x18008085f  mov     byte ptr [r9], 0
0x180080863  mov     byte ptr [rcx+0B0h], 0
0x18008086a  mov     dl, 1; bool
0x18008086c  call    ?QueryCurrentTraceProfileCollection@Tracer@Diagnostics@Microsoft@@AEAAJ_N@Z; Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(bool)
0x180080871  mov     edi, eax
0x180080873  cmp     eax, 0C5583000h
0x180080878  jnz     loc_180080D33
0x18008087e  lea     r14, [rbx+0C8h]
0x180080885  mov     rcx, r14
0x180080888  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x18008088d  mov     rcx, r14
0x180080890  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x180080895  lea     rdi, [rbx+60h]
0x180080899  cmp     qword ptr [rdi+18h], 7
0x18008089e  jbe     short loc_1800808A5
0x1800808a0  mov     rdx, [rdi]
0x1800808a3  jmp     short loc_1800808A8
0x1800808a5  mov     rdx, rdi
0x1800808a8  lea     rcx, [rsp+0C8h+var_88]
0x1800808ad  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800808b2  mov     [rsp+0C8h+var_A0], r14
0x1800808b7  lea     rcx, _GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a
0x1800808be  mov     qword ptr [rsp+0C8h+var_A8], rcx; int
0x1800808c3  mov     r9d, 1
0x1800808c9  xor     r8d, r8d
0x1800808cc  lea     rdx, _GUID_b98b53f3_83ba_4837_8946_e886be8d4003
0x1800808d3  mov     rcx, [rax]
0x1800808d6  call    cs:__imp_WPRCCreateInstanceUnderInstanceName
0x1800808dd  nop     dword ptr [rax+rax+00h]
0x1800808e2  mov     esi, eax
0x1800808e4  lea     rcx, [rsp+0C8h+var_88]
0x1800808e9  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800808ee  test    esi, esi
0x1800808f0  jns     short loc_180080921
0x1800808f2  mov     rcx, [rsp+0C8h]; this
0x1800808fa  mov     r9d, esi; char *
0x1800808fd  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080904  mov     edx, 228h; void *
0x180080909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008090e  nop
0x18008090f  xor     dl, dl
0x180080911  mov     rcx, rbx
0x180080914  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180080919  nop
0x18008091a  mov     eax, esi
0x18008091c  jmp     loc_180080D6E
0x180080921  lea     rsi, [rbx+0D0h]
0x180080928  cmp     qword ptr [rsi], 0
0x18008092c  jz      short loc_180080958
0x18008092e  lea     rdx, [rsp+0C8h+var_88]
0x180080933  mov     rcx, rsi
0x180080936  call    ??$query@UIProfileElement@WindowsPerformanceRecorder@@@?$com_ptr_t@UIProfile@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIProfileElement@WindowsPerformanceRecorder@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IProfile,wil::err_exception_policy>::query<WindowsPerformanceRecorder::IProfileElement>(void)
0x18008093b  nop
0x18008093c  mov     rcx, qword ptr [rsp+0C8h+var_88]
0x180080941  mov     rax, [rcx]
0x180080944  mov     rax, [rax+20h]
0x180080948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008094d  nop
0x18008094e  lea     rcx, [rsp+0C8h+var_88]
0x180080953  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180080958  mov     rcx, rsi
0x18008095b  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x180080960  mov     rcx, rsi
0x180080963  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x180080968  cmp     qword ptr [rdi+18h], 7
0x18008096d  jbe     short loc_180080972
0x18008096f  mov     rdi, [rdi]
0x180080972  mov     rdx, rdi
0x180080975  lea     rcx, [rsp+0C8h+var_88]
0x18008097a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x18008097f  mov     [rsp+0C8h+var_A0], rsi
0x180080984  lea     rcx, _GUID_c732a38e_0699_4acc_9070_a0a43f568e34
0x18008098b  mov     qword ptr [rsp+0C8h+var_A8], rcx; int
0x180080990  mov     r9d, 1
0x180080996  xor     r8d, r8d
0x180080999  lea     rdx, _GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4
0x1800809a0  mov     rcx, [rax]
0x1800809a3  call    cs:__imp_WPRCCreateInstanceUnderInstanceName
0x1800809aa  nop     dword ptr [rax+rax+00h]
0x1800809af  mov     edi, eax
0x1800809b1  lea     rcx, [rsp+0C8h+var_88]
0x1800809b6  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800809bb  test    edi, edi
0x1800809bd  jns     short loc_1800809EE
0x1800809bf  mov     rcx, [rsp+0C8h]; this
0x1800809c7  mov     r9d, edi; char *
0x1800809ca  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x1800809d1  mov     edx, 238h; void *
0x1800809d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800809db  nop
0x1800809dc  xor     dl, dl
0x1800809de  mov     rcx, rbx
0x1800809e1  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x1800809e6  nop
0x1800809e7  mov     eax, edi
0x1800809e9  jmp     loc_180080D6E
0x1800809ee  lea     rdx, [rsp+0C8h+var_68]
0x1800809f3  mov     rcx, r15
0x1800809f6  call    ?GetProfile@ITraceProfileDef@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@XZ; Microsoft::Diagnostics::ITraceProfileDef::GetProfile(void)
0x1800809fb  movups  xmm0, xmmword ptr [rax]
0x1800809fe  movdqu  [rsp+0C8h+var_88], xmm0
0x180080a04  lea     rdx, [rsp+0C8h+var_88]
0x180080a09  lea     rcx, [rsp+0C8h+var_58]
0x180080a0e  call    ?MultiByteStringToWideString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(std::string_view,ulong)
0x180080a13  nop
0x180080a14  cmp     qword ptr [rax+18h], 7
0x180080a19  jbe     short loc_180080A1E
0x180080a1b  mov     rax, [rax]
0x180080a1e  mov     rdx, rax
0x180080a21  lea     rcx, [rsp+0C8h+var_98]
0x180080a26  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180080a2b  nop
0x180080a2c  lea     rcx, [rsp+0C8h+var_58]; this
0x180080a31  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180080a36  mov     rcx, [rsi]
0x180080a39  mov     rax, [rcx]
0x180080a3c  mov     rdx, [rsp+0C8h+var_98]
0x180080a41  mov     rax, [rax+0D0h]
0x180080a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080a4d  mov     edi, eax
0x180080a4f  test    eax, eax
0x180080a51  jns     short loc_180080A8D
0x180080a53  mov     rcx, [rsp+0C8h]; this
0x180080a5b  mov     r9d, eax; char *
0x180080a5e  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080a65  mov     edx, 23Bh; void *
0x180080a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080a6f  nop
0x180080a70  lea     rcx, [rsp+0C8h+var_98]
0x180080a75  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180080a7a  nop
0x180080a7b  xor     dl, dl
0x180080a7d  mov     rcx, rbx
0x180080a80  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180080a85  nop
0x180080a86  mov     eax, edi
0x180080a88  jmp     loc_180080D6E
0x180080a8d  mov     rcx, [rsi]
0x180080a90  mov     rax, [rcx]
0x180080a93  lea     rdx, [rbx+0A0h]
0x180080a9a  mov     rax, [rax+98h]
0x180080aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080aa6  mov     edi, eax
0x180080aa8  test    eax, eax
0x180080aaa  jns     short loc_180080AE6
0x180080aac  mov     rcx, [rsp+0C8h]; this
0x180080ab4  mov     r9d, eax; char *
0x180080ab7  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080abe  mov     edx, 23Ch; void *
0x180080ac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080ac8  nop
0x180080ac9  lea     rcx, [rsp+0C8h+var_98]
0x180080ace  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180080ad3  nop
0x180080ad4  xor     dl, dl
0x180080ad6  mov     rcx, rbx
0x180080ad9  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180080ade  nop
0x180080adf  mov     eax, edi
0x180080ae1  jmp     loc_180080D6E
0x180080ae6  mov     rcx, [r14]
0x180080ae9  mov     rax, [rcx]
0x180080aec  or      r8d, 0FFFFFFFFh
0x180080af0  mov     rdx, [rsi]
0x180080af3  mov     rax, [rax+38h]
0x180080af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080afc  mov     edi, eax
0x180080afe  test    eax, eax
0x180080b00  jns     short loc_180080B3C
0x180080b02  mov     rcx, [rsp+0C8h]; this
0x180080b0a  mov     r9d, eax; char *
0x180080b0d  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080b14  mov     edx, 23Dh; void *
0x180080b19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080b1e  nop
0x180080b1f  lea     rcx, [rsp+0C8h+var_98]
0x180080b24  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180080b29  nop
0x180080b2a  xor     dl, dl
0x180080b2c  mov     rcx, rbx
0x180080b2f  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180080b34  nop
0x180080b35  mov     eax, edi
0x180080b37  jmp     loc_180080D6E
0x180080b3c  cmp     byte ptr [rbx+1], 0
0x180080b40  jnz     short loc_180080B9F
0x180080b42  mov     rcx, [rbx+0B8h]
0x180080b49  mov     rax, [rcx]
0x180080b4c  mov     rdx, [r14]
0x180080b4f  mov     rax, [rax+48h]
0x180080b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b58  mov     edi, eax
0x180080b5a  test    eax, eax
0x180080b5c  jns     short loc_180080B9F
0x180080b5e  cmp     eax, 0C5583001h
0x180080b63  jz      short loc_180080B9F
0x180080b65  mov     rcx, [rsp+0C8h]; this
0x180080b6d  mov     r9d, eax; char *
0x180080b70  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080b77  mov     edx, 243h; void *
0x180080b7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080b81  nop
0x180080b82  lea     rcx, [rsp+0C8h+var_98]
0x180080b87  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180080b8c  nop
0x180080b8d  xor     dl, dl
0x180080b8f  mov     rcx, rbx
0x180080b92  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180080b97  nop
0x180080b98  mov     eax, edi
0x180080b9a  jmp     loc_180080D6E
0x180080b9f  cmp     byte ptr [rbx], 0
0x180080ba2  jnz     short loc_180080BAE
0x180080ba4  cmp     byte ptr [rbx+1], 0
0x180080ba8  jz      loc_180080CE0
0x180080bae  mov     qword ptr [rsp+0C8h+var_88], 0
0x180080bb7  lea     rcx, [rbx+0B8h]
0x180080bbe  lea     r8, [rsp+0C8h+var_88]
0x180080bc3  call    ?try_query_to@?$com_ptr_t@UIControlManager@@Uerr_exception_policy@wil@@@wil@@QEBA_NAEBU_GUID@@PEAPEAX@Z; wil::com_ptr_t<IControlManager,wil::err_exception_policy>::try_query_to(_GUID const &,void * *)
0x180080bc8  test    al, al
0x180080bca  jnz     short loc_180080C16
0x180080bcc  mov     rcx, [rsp+0C8h]; this
0x180080bd4  mov     edi, 80004005h
0x180080bd9  mov     r9d, edi; char *
0x180080bdc  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080be3  mov     edx, 250h; void *
0x180080be8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080bed  nop
0x180080bee  lea     rcx, [rsp+0C8h+var_88]
0x180080bf3  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180080bf8  nop
0x180080bf9  lea     rcx, [rsp+0C8h+var_98]
0x180080bfe  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180080c03  nop
0x180080c04  xor     dl, dl
0x180080c06  mov     rcx, rbx
0x180080c09  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180080c0e  nop
0x180080c0f  mov     eax, edi
0x180080c11  jmp     loc_180080D6E
0x180080c16  mov     rcx, qword ptr [rsp+0C8h+var_88]
0x180080c1b  mov     rdx, [rbx+0C8h]
0x180080c22  mov     rax, [rcx]
0x180080c25  cmp     byte ptr [rbx], 0
0x180080c28  jz      short loc_180080C82
0x180080c2a  mov     rax, [rax+38h]
0x180080c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080c33  mov     edi, eax
0x180080c35  test    eax, eax
0x180080c37  jns     loc_180080CD6
0x180080c3d  mov     rcx, [rsp+0C8h]; this
0x180080c45  mov     r9d, eax; char *
0x180080c48  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080c4f  mov     edx, 253h; void *
0x180080c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080c59  nop
0x180080c5a  lea     rcx, [rsp+0C8h+var_88]
0x180080c5f  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180080c64  nop
0x180080c65  lea     rcx, [rsp+0C8h+var_98]
0x180080c6a  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180080c6f  nop
0x180080c70  xor     dl, dl
0x180080c72  mov     rcx, rbx
0x180080c75  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180080c7a  nop
0x180080c7b  mov     eax, edi
0x180080c7d  jmp     loc_180080D6E
0x180080c82  mov     rax, [rax+48h]
0x180080c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080c8b  mov     edi, eax
0x180080c8d  test    eax, eax
0x180080c8f  jns     short loc_180080CD6
0x180080c91  mov     rcx, [rsp+0C8h]; this
0x180080c99  mov     r9d, eax; char *
0x180080c9c  lea     r8, aOnecoreBaseTel_133; "onecore\\base\\telemetry\\utc\\service"...
0x180080ca3  mov     edx, 257h; void *
0x180080ca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080cad  nop
0x180080cae  lea     rcx, [rsp+0C8h+var_88]
0x180080cb3  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180080cb8  nop
0x180080cb9  lea     rcx, [rsp+0C8h+var_98]
0x180080cbe  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180080cc3  nop
  ... truncated ...
```
