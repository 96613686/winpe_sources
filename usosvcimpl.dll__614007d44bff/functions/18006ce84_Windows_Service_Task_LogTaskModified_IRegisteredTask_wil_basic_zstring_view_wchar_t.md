# Windows::Service::Task::LogTaskModified(IRegisteredTask *,wil::basic_zstring_view<wchar_t>)

- ea: `0x18006ce84`
- end: `0x18006d752`
- name: `?LogTaskModified@Task@Service@Windows@@AEAAXPEAUIRegisteredTask@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `2254`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180069948`

## callees

- `0x1800112d0`
- `0x18002dedc`
- `0x180063000`
- `0x18006ce84`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d381`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d356`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d394`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d356`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d394`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d32d`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d36b`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d32d`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d36b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d2a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d2f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d34e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d38c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d5f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d60c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d654`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d2a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d2f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d34e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d38c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d5f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d60c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d654`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006cf50`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006cffa`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006cf50`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006cffa`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18006cf73`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18006d01d`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18006cf73`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18006d01d`

## string_xrefs

- `0x18006cf81`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006d693`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006d6a8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006d6bc`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall Windows::Service::Task::LogTaskModified(__int64 a1, __int64 *a2, __int128 *a3)
{
  int v5; // eax
  int v6; // eax
  const char *v7; // r9
  int v8; // eax
  const char *v9; // r9
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  int (__fastcall *v20)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rbx
  int (__fastcall *v24)(__int64, BSTR *); // r15
  OLECHAR *v25; // r14
  DWORD LastError; // edi
  __int64 v27; // rbx
  int (__fastcall *v28)(__int64, BSTR *); // r15
  OLECHAR *v29; // r14
  DWORD v30; // edi
  OLECHAR *v31; // r14
  OLECHAR *v32; // rdi
  DWORD v33; // ebx
  OLECHAR *v34; // r14
  OLECHAR *v35; // rdi
  DWORD v36; // ebx
  int v37; // eax
  __int64 *System; // rax
  __int64 v39; // rax
  __int64 v40; // r11
  void (__fastcall *v41)(__int64, _QWORD *, _BYTE *, _BYTE *, int, int, int, bool, bool, __int128 *, _QWORD *, _QWORD *); // rsi
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // r10
  const char *v45; // r9
  volatile signed __int32 *v46; // rbx
  volatile signed __int32 *v47; // rbx
  int v48; // [rsp+20h] [rbp-1A8h]
  _QWORD v49[2]; // [rsp+70h] [rbp-158h] BYREF
  _QWORD v50[2]; // [rsp+80h] [rbp-148h] BYREF
  _QWORD v51[2]; // [rsp+90h] [rbp-138h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-128h] BYREF
  _BYTE v53[8]; // [rsp+B0h] [rbp-118h] BYREF
  volatile signed __int32 *v54; // [rsp+B8h] [rbp-110h]
  __int64 v55; // [rsp+C0h] [rbp-108h] BYREF
  volatile signed __int32 *v56; // [rsp+C8h] [rbp-100h]
  _WORD v57[2]; // [rsp+D0h] [rbp-F8h] BYREF
  __int16 v58; // [rsp+D4h] [rbp-F4h] BYREF
  BSTR v59; // [rsp+D8h] [rbp-F0h] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp-E8h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-E0h] BYREF
  int v62; // [rsp+F0h] [rbp-D8h] BYREF
  int v63; // [rsp+F4h] [rbp-D4h] BYREF
  int v64; // [rsp+F8h] [rbp-D0h] BYREF
  _QWORD *v65; // [rsp+100h] [rbp-C8h] BYREF
  __int64 v66; // [rsp+108h] [rbp-C0h] BYREF
  __int64 v67; // [rsp+110h] [rbp-B8h] BYREF
  __int64 *v68; // [rsp+118h] [rbp-B0h] BYREF
  BSTR v69; // [rsp+120h] [rbp-A8h] BYREF
  DOUBLE vtime; // [rsp+128h] [rbp-A0h] BYREF
  DOUBLE v71; // [rsp+130h] [rbp-98h] BYREF
  _BYTE v72[8]; // [rsp+138h] [rbp-90h] BYREF
  _BYTE v73[8]; // [rsp+140h] [rbp-88h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+148h] [rbp-80h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+158h] [rbp-70h] BYREF
  SYSTEMTIME LocalTime; // [rsp+168h] [rbp-60h] BYREF
  struct _SYSTEMTIME v77; // [rsp+178h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)0x80070057LL,
        v48);
    v69 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*a2 + 56))(a2, &v69);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v5,
        v48);
    vtime = 0.0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, DOUBLE *))(*a2 + 144))(a2, &vtime);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x361,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v6,
        v48);
    SystemTime = 0;
    VariantTimeToSystemTime(vtime, &SystemTime);
    UniversalTime = 0;
    if ( !TzSpecificLocalTimeToSystemTime(0, &SystemTime, &UniversalTime) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x367,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        v7);
    Windows::Time::from_systemtime(v73, &UniversalTime);
    v71 = 0.0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, DOUBLE *))(*a2 + 120))(a2, &v71);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v8,
        v48);
    LocalTime = 0;
    VariantTimeToSystemTime(v71, &LocalTime);
    v77 = 0;
    if ( !TzSpecificLocalTimeToSystemTime(0, &LocalTime, &v77) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x372,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        v9);
    Windows::Time::from_systemtime(v72, &v77);
    v64 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a2 + 128))(a2, &v64);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v10,
        v48);
    v63 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a2 + 72))(a2, &v63);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v11,
        v48);
    v62 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a2 + 136))(a2, &v62);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v12,
        v48);
    v13 = *a2;
    v68 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v13 + 152))(a2, &v68);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x380,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v14,
        v48);
    v66 = 0;
    v15 = *v68;
    v66 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 88))(v68, &v66);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x383,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v16,
        v48);
    v58 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v66 + 344LL))(v66, &v58);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x386,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v17,
        v48);
    bstrString = 0;
    v59 = 0;
    v67 = 0;
    v65 = 0;
    v61 = 0;
    v18 = *v68;
    v67 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *))(v18 + 136))(v68, &v67) < 0 )
      goto LABEL_29;
    v19 = v67;
    v20 = *(int (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v67 + 64LL);
    v21 = v65;
    v65 = 0;
    if ( v21 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v21 + 16LL))(v21, *v21);
    if ( v20(v19, 1, &v65) < 0 )
      goto LABEL_29;
    v22 = v61;
    v61 = 0;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( (*(int (__fastcall **)(_QWORD *, GUID *, __int64 *))*v65)(
           v65,
           &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
           &v61) < 0 )
      goto LABEL_29;
    v23 = v61;
    v24 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v61 + 80LL);
    v25 = bstrString;
    if ( bstrString )
    {
      LastError = GetLastError();
      SysFreeString(v25);
      SetLastError(LastError);
    }
    bstrString = 0;
    if ( v24(v23, &bstrString) < 0 )
      goto LABEL_29;
    v27 = v61;
    v28 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v61 + 96LL);
    v29 = v59;
    if ( v59 )
    {
      v30 = GetLastError();
      SysFreeString(v29);
      SetLastError(v30);
    }
    v59 = 0;
    if ( v28(v27, &v59) < 0 )
    {
LABEL_29:
      v31 = SysAllocString(&S1);
      v32 = bstrString;
      if ( bstrString )
      {
        v33 = GetLastError();
        SysFreeString(v32);
        SetLastError(v33);
      }
      bstrString = v31;
      v34 = SysAllocString(&S1);
      v35 = v59;
      if ( v59 )
      {
        v36 = GetLastError();
        SysFreeString(v35);
        SetLastError(v36);
      }
      v59 = v34;
    }
    v57[0] = 0;
    v37 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v66 + 136LL))(v66, v57);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v37,
        v48);
    System = SystemInterface::Service::GetSystem(&v55);
    v39 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*System + 104LL))(*System, v53);
    v40 = *(_QWORD *)v39;
    v41 = *(void (__fastcall **)(__int64, _QWORD *, _BYTE *, _BYTE *, int, int, int, bool, bool, __int128 *, _QWORD *, _QWORD *))(**(_QWORD **)v39 + 216LL);
    v42 = -1;
    do
      ++v42;
    while ( v59[v42] );
    v43 = -1;
    do
      ++v43;
    while ( bstrString[v43] );
    v44 = -1;
    do
      ++v44;
    while ( v69[v44] );
    v49[0] = v59;
    v49[1] = v42;
    v50[0] = bstrString;
    v50[1] = v43;
    v52 = *a3;
    v51[0] = v69;
    v51[1] = v44;
    v41(v40, v51, v73, v72, v64, v63, v62, v58 == -1, v57[0] == 0xFFFF, &v52, v50, v49);
    v46 = v54;
    if ( v54 )
    {
      if ( !_InterlockedDecrement(v54 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
        if ( !_InterlockedDecrement(v46 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
      }
    }
    v47 = v56;
    if ( v56 )
    {
      if ( !_InterlockedDecrement(v56 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
        if ( !_InterlockedDecrement(v47 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
      }
    }
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    if ( v65 )
      (*(void (__fastcall **)(_QWORD *))(*v65 + 16LL))(v65);
    if ( v67 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    if ( v59 )
      SysFreeString(v59);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    if ( v68 )
      (*(void (__fastcall **)(__int64 *))(*v68 + 16))(v68);
    if ( v69 )
      SysFreeString(v69);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3A9,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      v45);
  }
}

```

## disassembly

```asm
0x18006ce84  mov     rax, rsp
0x18006ce87  mov     [rax+8], rbx
0x18006ce8b  mov     [rax+20h], rsi
0x18006ce8f  push    rdi
0x18006ce90  push    r12
0x18006ce92  push    r13
0x18006ce94  push    r14
0x18006ce96  push    r15
0x18006ce98  sub     rsp, 1A0h
0x18006ce9f  movaps  xmmword ptr [rax-38h], xmm6
0x18006cea3  mov     rax, cs:__security_cookie
0x18006ceaa  xor     rax, rsp
0x18006cead  mov     [rsp+1C8h+var_40], rax
0x18006ceb5  mov     r12, r8
0x18006ceb8  mov     rbx, rdx
0x18006cebb  mov     rcx, [rsp+1C8h]; this
0x18006cec3  xor     r13d, r13d
0x18006cec6  test    rdx, rdx
0x18006cec9  jz      loc_18006D68D
0x18006cecf  mov     [rsp+1C8h+var_A8], r13
0x18006ced7  mov     rax, [rdx]
0x18006ceda  lea     rdx, [rsp+1C8h+var_A8]
0x18006cee2  mov     rcx, rbx
0x18006cee5  mov     rax, [rax+38h]
0x18006cee9  call    _guard_dispatch_icall
0x18006ceee  mov     rcx, [rsp+1C8h]; this
0x18006cef6  test    eax, eax
0x18006cef8  js      loc_18006D6A5
0x18006cefe  xorps   xmm6, xmm6
0x18006cf01  movsd   [rsp+1C8h+vtime], xmm6
0x18006cf0a  mov     rax, [rbx]
0x18006cf0d  lea     rdx, [rsp+1C8h+vtime]
0x18006cf15  mov     rcx, rbx
0x18006cf18  mov     rax, [rax+90h]
0x18006cf1f  call    _guard_dispatch_icall
0x18006cf24  mov     rcx, [rsp+1C8h]; this
0x18006cf2c  test    eax, eax
0x18006cf2e  js      loc_18006D6B9
0x18006cf34  xorps   xmm0, xmm0
0x18006cf37  movups  xmmword ptr [rsp+1C8h+SystemTime.wYear], xmm0
0x18006cf3f  lea     rdx, [rsp+1C8h+SystemTime]; lpSystemTime
0x18006cf47  movsd   xmm0, [rsp+1C8h+vtime]; vtime
0x18006cf50  call    cs:__imp_VariantTimeToSystemTime
0x18006cf56  xorps   xmm0, xmm0
0x18006cf59  movups  xmmword ptr [rsp+1C8h+UniversalTime.wYear], xmm0
0x18006cf61  lea     r8, [rsp+1C8h+UniversalTime]; lpUniversalTime
0x18006cf69  lea     rdx, [rsp+1C8h+SystemTime]; lpLocalTime
0x18006cf71  xor     ecx, ecx; lpTimeZoneInformation
0x18006cf73  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18006cf79  mov     rcx, [rsp+1C8h]; this
0x18006cf81  lea     rsi, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006cf88  test    eax, eax
0x18006cf8a  jnz     short loc_18006CF99
0x18006cf8c  mov     r8, rsi; unsigned int
0x18006cf8f  mov     edx, 367h; void *
0x18006cf94  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006cf99  lea     rdx, [rsp+1C8h+UniversalTime]
0x18006cfa1  lea     rcx, [rsp+1C8h+var_88]
0x18006cfa9  call    ?from_systemtime@Time@Windows@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBU_SYSTEMTIME@@@Z; Windows::Time::from_systemtime(_SYSTEMTIME const &)
0x18006cfae  movsd   [rsp+1C8h+var_98], xmm6
0x18006cfb7  mov     rax, [rbx]
0x18006cfba  lea     rdx, [rsp+1C8h+var_98]
0x18006cfc2  mov     rcx, rbx
0x18006cfc5  mov     rax, [rax+78h]
0x18006cfc9  call    _guard_dispatch_icall
0x18006cfce  mov     rcx, [rsp+1C8h]; this
0x18006cfd6  test    eax, eax
0x18006cfd8  js      loc_18006D6CD
0x18006cfde  xorps   xmm0, xmm0
0x18006cfe1  movups  xmmword ptr [rsp+1C8h+LocalTime.wYear], xmm0
0x18006cfe9  lea     rdx, [rsp+1C8h+LocalTime]; lpSystemTime
0x18006cff1  movsd   xmm0, [rsp+1C8h+var_98]; vtime
0x18006cffa  call    cs:__imp_VariantTimeToSystemTime
0x18006d000  xorps   xmm0, xmm0
0x18006d003  movups  xmmword ptr [rsp+1C8h+var_50.wYear], xmm0
0x18006d00b  lea     r8, [rsp+1C8h+var_50]; lpUniversalTime
0x18006d013  lea     rdx, [rsp+1C8h+LocalTime]; lpLocalTime
0x18006d01b  xor     ecx, ecx; lpTimeZoneInformation
0x18006d01d  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18006d023  mov     rcx, [rsp+1C8h]; this
0x18006d02b  test    eax, eax
0x18006d02d  jnz     short loc_18006D03C
0x18006d02f  mov     r8, rsi; unsigned int
0x18006d032  mov     edx, 372h; void *
0x18006d037  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006d03c  lea     rdx, [rsp+1C8h+var_50]
0x18006d044  lea     rcx, [rsp+1C8h+var_90]
0x18006d04c  call    ?from_systemtime@Time@Windows@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBU_SYSTEMTIME@@@Z; Windows::Time::from_systemtime(_SYSTEMTIME const &)
0x18006d051  mov     [rsp+1C8h+var_D0], r13d
0x18006d059  mov     rax, [rbx]
0x18006d05c  lea     rdx, [rsp+1C8h+var_D0]
0x18006d064  mov     rcx, rbx
0x18006d067  mov     rax, [rax+80h]
0x18006d06e  call    _guard_dispatch_icall
0x18006d073  mov     rcx, [rsp+1C8h]; this
0x18006d07b  test    eax, eax
0x18006d07d  js      loc_18006D6DD
0x18006d083  mov     [rsp+1C8h+var_D4], r13d
0x18006d08b  mov     rax, [rbx]
0x18006d08e  lea     rdx, [rsp+1C8h+var_D4]
0x18006d096  mov     rcx, rbx
0x18006d099  mov     rax, [rax+48h]
0x18006d09d  call    _guard_dispatch_icall
0x18006d0a2  mov     rcx, [rsp+1C8h]; this
0x18006d0aa  test    eax, eax
0x18006d0ac  js      loc_18006D6ED
0x18006d0b2  mov     [rsp+1C8h+var_D8], r13d
0x18006d0ba  mov     rax, [rbx]
0x18006d0bd  lea     rdx, [rsp+1C8h+var_D8]
0x18006d0c5  mov     rcx, rbx
0x18006d0c8  mov     rax, [rax+88h]
0x18006d0cf  call    _guard_dispatch_icall
0x18006d0d4  mov     rcx, [rsp+1C8h]; this
0x18006d0dc  test    eax, eax
0x18006d0de  js      loc_18006D6FD
0x18006d0e4  mov     rax, [rbx]
0x18006d0e7  mov     [rsp+1C8h+var_B0], r13
0x18006d0ef  lea     rdx, [rsp+1C8h+var_B0]
0x18006d0f7  mov     rcx, rbx
0x18006d0fa  mov     rax, [rax+98h]
0x18006d101  call    _guard_dispatch_icall
0x18006d106  mov     rcx, [rsp+1C8h]; this
0x18006d10e  test    eax, eax
0x18006d110  js      loc_18006D70E
0x18006d116  mov     [rsp+1C8h+var_C0], r13
0x18006d11e  mov     rcx, [rsp+1C8h+var_B0]
0x18006d126  mov     rax, [rcx]
0x18006d129  mov     [rsp+1C8h+var_C0], r13
0x18006d131  lea     rdx, [rsp+1C8h+var_C0]
0x18006d139  mov     rax, [rax+58h]
0x18006d13d  call    _guard_dispatch_icall
0x18006d142  mov     rcx, [rsp+1C8h]; this
0x18006d14a  test    eax, eax
0x18006d14c  js      loc_18006D71F
0x18006d152  mov     [rsp+1C8h+var_F4], r13w
0x18006d15b  mov     rcx, [rsp+1C8h+var_C0]
0x18006d163  mov     rax, [rcx]
0x18006d166  lea     rdx, [rsp+1C8h+var_F4]
0x18006d16e  mov     rax, [rax+158h]
0x18006d175  call    _guard_dispatch_icall
0x18006d17a  mov     rcx, [rsp+1C8h]; this
0x18006d182  test    eax, eax
0x18006d184  js      loc_18006D72F
0x18006d18a  mov     [rsp+1C8h+bstrString], r13
0x18006d192  mov     [rsp+1C8h+var_F0], r13
0x18006d19a  mov     [rsp+1C8h+var_B8], r13
0x18006d1a2  mov     [rsp+1C8h+var_C8], r13
0x18006d1aa  mov     [rsp+1C8h+var_E0], r13
0x18006d1b2  mov     rcx, [rsp+1C8h+var_B0]
0x18006d1ba  mov     rax, [rcx]
0x18006d1bd  mov     [rsp+1C8h+var_B8], r13
0x18006d1c5  lea     rdx, [rsp+1C8h+var_B8]
0x18006d1cd  mov     rax, [rax+88h]
0x18006d1d4  call    _guard_dispatch_icall
0x18006d1d9  test    eax, eax
0x18006d1db  js      loc_18006D326
0x18006d1e1  mov     rbx, [rsp+1C8h+var_B8]
0x18006d1e9  mov     rax, [rbx]
0x18006d1ec  mov     rdi, [rax+40h]
0x18006d1f0  mov     rcx, [rsp+1C8h+var_C8]
0x18006d1f8  mov     [rsp+1C8h+var_C8], r13
0x18006d200  test    rcx, rcx
0x18006d203  jz      short loc_18006D212
0x18006d205  mov     rdx, [rcx]
0x18006d208  mov     rax, [rdx+10h]
0x18006d20c  call    _guard_dispatch_icall
0x18006d211  nop
0x18006d212  lea     r8, [rsp+1C8h+var_C8]
0x18006d21a  mov     edx, 1
0x18006d21f  mov     rcx, rbx
0x18006d222  mov     rax, rdi
0x18006d225  call    _guard_dispatch_icall
0x18006d22a  test    eax, eax
0x18006d22c  js      loc_18006D326
0x18006d232  mov     rcx, [rsp+1C8h+var_E0]
0x18006d23a  mov     [rsp+1C8h+var_E0], r13
0x18006d242  test    rcx, rcx
0x18006d245  jz      short loc_18006D254
0x18006d247  mov     rax, [rcx]
0x18006d24a  mov     rax, [rax+10h]
0x18006d24e  call    _guard_dispatch_icall
0x18006d253  nop
0x18006d254  mov     rcx, [rsp+1C8h+var_C8]
0x18006d25c  mov     rax, [rcx]
0x18006d25f  lea     r8, [rsp+1C8h+var_E0]
0x18006d267  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x18006d26e  mov     rax, [rax]
0x18006d271  call    _guard_dispatch_icall
0x18006d276  test    eax, eax
0x18006d278  js      loc_18006D326
0x18006d27e  mov     rbx, [rsp+1C8h+var_E0]
0x18006d286  mov     rax, [rbx]
0x18006d289  mov     r15, [rax+50h]
0x18006d28d  mov     r14, [rsp+1C8h+bstrString]
0x18006d295  test    r14, r14
0x18006d298  jz      short loc_18006D2B3
0x18006d29a  call    cs:__imp_GetLastError
0x18006d2a0  mov     edi, eax
0x18006d2a2  mov     rcx, r14; bstrString
0x18006d2a5  call    cs:__imp_SysFreeString
0x18006d2ab  mov     ecx, edi; dwErrCode
0x18006d2ad  call    cs:__imp_SetLastError
0x18006d2b3  mov     [rsp+1C8h+bstrString], r13
0x18006d2bb  lea     rdx, [rsp+1C8h+bstrString]
0x18006d2c3  mov     rcx, rbx
0x18006d2c6  mov     rax, r15
0x18006d2c9  call    _guard_dispatch_icall
0x18006d2ce  test    eax, eax
0x18006d2d0  js      short loc_18006D326
0x18006d2d2  mov     rbx, [rsp+1C8h+var_E0]
0x18006d2da  mov     rax, [rbx]
0x18006d2dd  mov     r15, [rax+60h]
0x18006d2e1  mov     r14, [rsp+1C8h+var_F0]
0x18006d2e9  test    r14, r14
0x18006d2ec  jz      short loc_18006D307
0x18006d2ee  call    cs:__imp_GetLastError
0x18006d2f4  mov     edi, eax
0x18006d2f6  mov     rcx, r14; bstrString
0x18006d2f9  call    cs:__imp_SysFreeString
0x18006d2ff  mov     ecx, edi; dwErrCode
0x18006d301  call    cs:__imp_SetLastError
0x18006d307  mov     [rsp+1C8h+var_F0], r13
0x18006d30f  lea     rdx, [rsp+1C8h+var_F0]
0x18006d317  mov     rcx, rbx
0x18006d31a  mov     rax, r15
0x18006d31d  call    _guard_dispatch_icall
0x18006d322  test    eax, eax
0x18006d324  jns     short loc_18006D3A2
0x18006d326  lea     rcx, S1; psz
0x18006d32d  call    cs:__imp_SysAllocString
0x18006d333  mov     r14, rax
0x18006d336  mov     rdi, [rsp+1C8h+bstrString]
0x18006d33e  test    rdi, rdi
0x18006d341  jz      short loc_18006D35C
0x18006d343  call    cs:__imp_GetLastError
0x18006d349  mov     ebx, eax
0x18006d34b  mov     rcx, rdi; bstrString
0x18006d34e  call    cs:__imp_SysFreeString
0x18006d354  mov     ecx, ebx; dwErrCode
0x18006d356  call    cs:__imp_SetLastError
0x18006d35c  mov     [rsp+1C8h+bstrString], r14
0x18006d364  lea     rcx, S1; psz
0x18006d36b  call    cs:__imp_SysAllocString
0x18006d371  mov     r14, rax
0x18006d374  mov     rdi, [rsp+1C8h+var_F0]
0x18006d37c  test    rdi, rdi
0x18006d37f  jz      short loc_18006D39A
0x18006d381  call    cs:__imp_GetLastError
0x18006d387  mov     ebx, eax
0x18006d389  mov     rcx, rdi; bstrString
0x18006d38c  call    cs:__imp_SysFreeString
0x18006d392  mov     ecx, ebx; dwErrCode
0x18006d394  call    cs:__imp_SetLastError
0x18006d39a  mov     [rsp+1C8h+var_F0], r14
0x18006d3a2  mov     [rsp+1C8h+var_F8], r13w
0x18006d3ab  mov     rcx, [rsp+1C8h+var_C0]
0x18006d3b3  mov     rax, [rcx]
0x18006d3b6  lea     rdx, [rsp+1C8h+var_F8]
0x18006d3be  mov     rax, [rax+88h]
0x18006d3c5  call    _guard_dispatch_icall
0x18006d3ca  mov     rcx, [rsp+1C8h]; this
0x18006d3d2  test    eax, eax
0x18006d3d4  js      loc_18006D740
0x18006d3da  lea     rcx, [rsp+1C8h+var_108]
0x18006d3e2  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18006d3e7  nop
0x18006d3e8  mov     rcx, [rax]
0x18006d3eb  mov     rax, [rcx]
0x18006d3ee  lea     rdx, [rsp+1C8h+var_118]
0x18006d3f6  mov     rax, [rax+68h]
0x18006d3fa  call    _guard_dispatch_icall
0x18006d3ff  nop
0x18006d400  mov     r11, [rax]
0x18006d403  mov     rax, [r11]
0x18006d406  mov     rsi, [rax+0D8h]
0x18006d40d  mov     rcx, [rsp+1C8h+var_F0]
0x18006d415  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006d419  mov     r8, r14
0x18006d41c  inc     r8
0x18006d41f  cmp     [rcx+r8*2], r13w
0x18006d424  jnz     short loc_18006D41C
0x18006d426  mov     rax, [rsp+1C8h+bstrString]
0x18006d42e  mov     r9, r14
0x18006d431  inc     r9
0x18006d434  cmp     [rax+r9*2], r13w
0x18006d439  jnz     short loc_18006D431
0x18006d43b  cmp     [rsp+1C8h+var_F8], r14w
0x18006d444  setz    bl
0x18006d447  cmp     [rsp+1C8h+var_F4], r14w
0x18006d450  setz    dil
0x18006d454  mov     rdx, [rsp+1C8h+var_A8]
0x18006d45c  mov     r10, r14
0x18006d45f  inc     r10
0x18006d462  cmp     [rdx+r10*2], r13w
0x18006d467  jnz     short loc_18006D45F
0x18006d469  mov     [rsp+1C8h+var_158], rcx
0x18006d46e  mov     [rsp+1C8h+var_150], r8
0x18006d473  mov     [rsp+1C8h+var_148], rax
0x18006d47b  mov     [rsp+1C8h+var_140], r9
0x18006d483  movaps  xmm0, xmmword ptr [r12]
  ... truncated ...
```
