# HcsClient::GetWorkerProcessJob(_GUID const &,HCS_SYSTEM__ *,ulong,ulong)

- ea: `0x180050c5c`
- end: `0x180051183`
- name: `?GetWorkerProcessJob@HcsClient@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEAUHCS_SYSTEM__@@KK@Z`
- size: `1319`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037a40`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d0ec`
- `0x18000d108`
- `0x18000e648`
- `0x18000ebb0`
- `0x180018bd4`
- `0x1800391e8`
- `0x18003eb10`
- `0x18004694c`
- `0x18004704c`
- `0x180048534`
- `0x180050390`
- `0x180050c5c`
- `0x180051ca8`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180050d97`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180050d97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050e99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050daf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050f9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050f9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180050e25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180050e6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180050e25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180050e6f`
- `ntdll!RtlInitUnicodeString` at `0x180050fd4`
- `ntdll!RtlInitUnicodeString` at `0x180050fd4`
- `ntdll!NtOpenJobObject` at `0x180051033`
- `ntdll!NtOpenJobObject` at `0x180051033`

## string_xrefs

- `0x1800510e3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800510fc`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005105a`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x180051114`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x18005112f`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x180051141`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x180051153`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x18005116e`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x18005104b`: `Failed to open job object '%ls'`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall HcsClient::GetWorkerProcessJob(_QWORD *a1, __int64 a2, __int64 *a3, ACCESS_MASK a4, unsigned int a5)
{
  ACCESS_MASK v5; // r15d
  __int64 v8; // rax
  __int64 v9; // rbx
  volatile signed __int32 *v10; // rsi
  char v11; // cl
  HANDLE Event; // rdi
  const char *v13; // r9
  _QWORD *v14; // r8
  const struct _GUID *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // r14
  volatile signed __int32 *v18; // rdi
  ULONGLONG TickCount64; // r13
  DWORD v20; // eax
  HcsClient *v22; // rcx
  struct HCS_SYSTEM__ *v23; // r8
  const char *v24; // r9
  const WCHAR *v25; // rdx
  PCWSTR *v26; // rbx
  void **v27; // rax
  unsigned int v28; // eax
  int v30; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v33; // [rsp+40h] [rbp-C0h]
  __int128 v34; // [rsp+50h] [rbp-B0h]
  _QWORD *v35; // [rsp+60h] [rbp-A0h]
  const struct _GUID *v36; // [rsp+68h] [rbp-98h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR SourceString[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  HANDLE hHandle; // [rsp+C0h] [rbp-40h] BYREF
  char *v41; // [rsp+C8h] [rbp-38h]
  __int128 v42; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v46[29]; // [rsp+100h] [rbp+0h] BYREF
  int v47; // [rsp+1E8h] [rbp+E8h]
  char v48; // [rsp+458h] [rbp+358h]
  _BYTE v49[16]; // [rsp+460h] [rbp+360h] BYREF
  __int64 v50; // [rsp+470h] [rbp+370h]
  __int64 v51; // [rsp+480h] [rbp+380h]
  _BYTE v52[864]; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v53[16]; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v54; // [rsp+8C0h] [rbp+7C0h]
  char v55; // [rsp+8D0h] [rbp+7D0h]
  wil::details::in1diag3 *retaddr; // [rsp+9F8h] [rbp+8F8h]

  v5 = a4;
  v35 = a1;
  v33 = 0;
  v8 = a3[1];
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
  v9 = *a3;
  *(_QWORD *)&v33 = v9;
  v10 = (volatile signed __int32 *)a3[1];
  *((_QWORD *)&v33 + 1) = v10;
  *(_OWORD *)SourceString = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(SourceString[0]) = 0;
  v32 = a2;
  lambda_80fb9797dfb51f618d68e1d22ff94370_::operator()(&v32, v46, v9);
  if ( !(_BYTE)v51 || (v11 = 0, !v48) )
    v11 = 1;
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
      (const char *)0x80070057LL,
      v30);
  if ( !(_BYTE)v51 )
    __fastfail(5u);
  if ( v50 )
  {
    std::wstring::operator=(SourceString, v49);
  }
  else
  {
    if ( v47 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
        (const char *)0x8000FFFFLL,
        v30);
    hHandle = 0;
    LODWORD(v41) = -2147418113;
    v42 = 0;
    v43 = 0;
    v44 = 7;
    LOWORD(v42) = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CC8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        v13);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &hHandle,
      Event);
    v14 = v46;
    if ( v46[3] > 7u )
      v14 = (_QWORD *)v46[0];
    v15 = (const struct _GUID *)HcsClient::OpenComputeSystem(a2, v9 + 24, v14);
    v36 = v15;
    v34 = 0;
    v16 = *(_QWORD *)v15->Data4;
    if ( v16 )
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
    v17 = *(_QWORD *)&v15->Data1;
    *(_QWORD *)&v34 = v17;
    v18 = *(volatile signed __int32 **)v15->Data4;
    *((_QWORD *)&v34 + 1) = v18;
    HcsClient::OperationTracker::SetClientCallback(
      *(HcsClient::OperationTracker **)(v17 + 112),
      HcsEventOptionNone,
      &hHandle,
      lambda_a2d8e03cc03dc09e021f93ab7c667289_::_lambda_invoker_cdecl_);
    TickCount64 = GetTickCount64();
    while ( 1 )
    {
      lambda_80fb9797dfb51f618d68e1d22ff94370_::operator()(&v32, v52, v17);
      if ( !v55 )
        __fastfail(5u);
      if ( v54 )
        break;
      if ( GetTickCount64() - TickCount64 > a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
          (const char *)0x80070102LL,
          v30);
      v20 = WaitForSingleObject(hHandle, 0xFAu);
      if ( v20 && v20 != 258 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x16D,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
          (const char *)retaddr);
      if ( !v20 )
      {
        if ( (int)v41 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x173,
            (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
            (const char *)(unsigned int)v41,
            v30);
        if ( v43 )
        {
          std::wstring::operator=(SourceString, &v42);
          Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v52);
          goto LABEL_33;
        }
      }
      Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v52);
    }
    std::wstring::operator=(SourceString, v53);
    Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v52);
LABEL_33:
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    HcsClient::CloseComputeSystem(v22, v15, v23);
    std::wstring::~wstring(&v42);
    if ( hHandle && !CloseHandle(hHandle) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    v5 = a4;
  }
  DestinationString = 0;
  v25 = (const WCHAR *)SourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v25 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v25);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *a1 = 0;
  v26 = SourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v26 = (PCWSTR *)SourceString[0];
  v27 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(a1);
  v28 = NtOpenJobObject(v27, v5, &ObjectAttributes);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x187,
    (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
    (const char *)v28,
    (int)"Failed to open job object '%ls'",
    (const char *)v26);
  Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v46);
  std::wstring::~wstring(SourceString);
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180050c5c  push    rbp
0x180050c5e  push    rbx
0x180050c5f  push    rsi
0x180050c60  push    rdi
0x180050c61  push    r12
0x180050c63  push    r13
0x180050c65  push    r14
0x180050c67  push    r15
0x180050c69  lea     rbp, [rsp-8B8h]
0x180050c71  sub     rsp, 9B8h
0x180050c78  mov     rax, cs:__security_cookie
0x180050c7f  xor     rax, rsp
0x180050c82  mov     [rbp+8F0h+var_50], rax
0x180050c89  mov     r15d, r9d
0x180050c8c  mov     [rsp+9F0h+var_9C0], r9d
0x180050c91  mov     r14, rdx
0x180050c94  mov     r12, rcx
0x180050c97  mov     [rsp+9F0h+var_990], rcx
0x180050c9c  xor     r13d, r13d
0x180050c9f  mov     [rsp+9F0h+var_9BC], r13d
0x180050ca4  xorps   xmm0, xmm0
0x180050ca7  movups  [rsp+9F0h+var_9B0], xmm0
0x180050cac  mov     rax, [r8+8]
0x180050cb0  test    rax, rax
0x180050cb3  jz      short loc_180050CB9
0x180050cb5  lock inc dword ptr [rax+8]
0x180050cb9  mov     rbx, [r8]
0x180050cbc  mov     qword ptr [rsp+9F0h+var_9B0], rbx
0x180050cc1  mov     rsi, [r8+8]
0x180050cc5  mov     qword ptr [rsp+9F0h+var_9B0+8], rsi
0x180050cca  movups  xmmword ptr [rbp+8F0h+SourceString], xmm0
0x180050cce  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180050cd6  movdqu  [rbp+8F0h+var_940], xmm1
0x180050cdb  mov     word ptr [rbp+8F0h+SourceString], r13w
0x180050ce0  mov     [rsp+9F0h+var_9B8], r14
0x180050ce5  mov     r8, rbx
0x180050ce8  lea     rdx, [rbp+8F0h+var_8F0]
0x180050cec  lea     rcx, [rsp+9F0h+var_9B8]
0x180050cf1  call    _lambda_80fb9797dfb51f618d68e1d22ff94370___operator__
0x180050cf6  nop
0x180050cf7  mov     rax, [rbp+8F0h+var_570]
0x180050cfe  test    al, al
0x180050d00  jz      short loc_180050D0E
0x180050d02  cmp     [rbp+8F0h+var_598], r13b
0x180050d09  mov     cl, r13b
0x180050d0c  jnz     short loc_180050D10
0x180050d0e  mov     cl, 1
0x180050d10  mov     r10, [rbp+8F8h]
0x180050d17  test    cl, cl
0x180050d19  jnz     loc_18005110E
0x180050d1f  mov     ecx, 5
0x180050d24  test    al, al
0x180050d26  jnz     short loc_180050D2A
0x180050d28  int     29h; Win8: RtlFailFast(ecx)
0x180050d2a  cmp     [rbp+8F0h+var_580], r13
0x180050d31  jz      short loc_180050D4E
0x180050d33  test    al, al
0x180050d35  jnz     short loc_180050D39
0x180050d37  int     29h; Win8: RtlFailFast(ecx)
0x180050d39  lea     rdx, [rbp+8F0h+var_590]
0x180050d40  lea     rcx, [rbp+8F0h+SourceString]
0x180050d44  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050d49  jmp     loc_180050FBB
0x180050d4e  cmp     [rbp+8F0h+var_808], r13d
0x180050d55  setnz   al
0x180050d58  mov     rcx, [rbp+8F8h]; this
0x180050d5f  test    al, al
0x180050d61  jnz     loc_180051129
0x180050d67  mov     [rbp+8F0h+hHandle], r13
0x180050d6b  mov     dword ptr [rbp+8F0h+var_928], 8000FFFFh
0x180050d72  xorps   xmm0, xmm0
0x180050d75  movups  [rbp+8F0h+var_920], xmm0
0x180050d79  mov     [rbp+8F0h+var_910], r13
0x180050d7d  mov     [rbp+8F0h+var_908], 7
0x180050d85  mov     word ptr [rbp+8F0h+var_920], r13w
0x180050d8a  mov     r9d, 1F0003h; dwDesiredAccess
0x180050d90  xor     r8d, r8d; dwFlags
0x180050d93  xor     edx, edx; lpName
0x180050d95  xor     ecx, ecx; lpEventAttributes
0x180050d97  call    cs:__imp_CreateEventExW
0x180050d9e  nop     dword ptr [rax+rax+00h]
0x180050da3  mov     rdi, rax
0x180050da6  test    rax, rax
0x180050da9  jz      loc_1800510F5
0x180050daf  call    cs:__imp_GetLastError
0x180050db6  nop     dword ptr [rax+rax+00h]
0x180050dbb  mov     rdx, rdi
0x180050dbe  lea     rcx, [rbp+8F0h+hHandle]
0x180050dc2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180050dc7  lea     r8, [rbp+8F0h+var_8F0]
0x180050dcb  cmp     [rbp+8F0h+var_8D8], 7
0x180050dd0  cmova   r8, [rbp+8F0h+var_8F0]
0x180050dd5  lea     rdx, [rbx+18h]
0x180050dd9  mov     rcx, r14
0x180050ddc  call    ?OpenComputeSystem@HcsClient@@YAPEAUHCS_SYSTEM__@@AEBU_GUID@@AEBV?$shared_ptr@VHcsServer@@@std@@PEBGK@Z; HcsClient::OpenComputeSystem(_GUID const &,std::shared_ptr<HcsServer> const &,ushort const *,ulong)
0x180050de1  mov     rbx, rax
0x180050de4  mov     [rsp+9F0h+var_988], rax
0x180050de9  xorps   xmm0, xmm0
0x180050dec  movups  [rsp+9F0h+var_9A0], xmm0
0x180050df1  mov     rax, [rax+8]
0x180050df5  test    rax, rax
0x180050df8  jz      short loc_180050DFE
0x180050dfa  lock inc dword ptr [rax+8]
0x180050dfe  mov     r14, [rbx]
0x180050e01  mov     qword ptr [rsp+9F0h+var_9A0], r14
0x180050e06  mov     rdi, [rbx+8]
0x180050e0a  mov     qword ptr [rsp+9F0h+var_9A0+8], rdi
0x180050e0f  lea     r9, _lambda_a2d8e03cc03dc09e021f93ab7c667289____lambda_invoker_cdecl_; void (*)(struct HCS_EVENT *, void *)
0x180050e16  lea     r8, [rbp+8F0h+hHandle]; void *
0x180050e1a  xor     edx, edx; enum HCS_EVENT_OPTIONS
0x180050e1c  mov     rcx, [r14+70h]; this
0x180050e20  call    ?SetClientCallback@OperationTracker@HcsClient@@QEAAXW4HCS_EVENT_OPTIONS@@PEBXP6AXPEAUHCS_EVENT@@PEAX@Z@Z; HcsClient::OperationTracker::SetClientCallback(HCS_EVENT_OPTIONS,void const *,void (*)(HCS_EVENT *,void *))
0x180050e25  call    cs:__imp_GetTickCount64
0x180050e2c  nop     dword ptr [rax+rax+00h]
0x180050e31  mov     r13, rax
0x180050e34  mov     r8, r14
0x180050e37  lea     rdx, [rbp+8F0h+var_4A0]
0x180050e3e  lea     rcx, [rsp+9F0h+var_9B8]
0x180050e43  call    _lambda_80fb9797dfb51f618d68e1d22ff94370___operator__
0x180050e48  nop
0x180050e49  mov     al, [rbp+8F0h+var_120]
0x180050e4f  test    al, al
0x180050e51  jnz     short loc_180050E5A
0x180050e53  mov     ecx, 5
0x180050e58  int     29h; Win8: RtlFailFast(ecx)
0x180050e5a  cmp     [rbp+8F0h+var_130], 0
0x180050e62  jnz     loc_180050F14
0x180050e68  mov     r15, [rbp+8F8h]
0x180050e6f  call    cs:__imp_GetTickCount64
0x180050e76  nop     dword ptr [rax+rax+00h]
0x180050e7b  mov     rcx, rax
0x180050e7e  sub     rcx, r13
0x180050e81  mov     eax, [rbp+8F0h+arg_20]
0x180050e87  cmp     rcx, rax
0x180050e8a  ja      loc_180051168
0x180050e90  mov     edx, 0FAh; dwMilliseconds
0x180050e95  mov     rcx, [rbp+8F0h+hHandle]; hHandle
0x180050e99  call    cs:__imp_WaitForSingleObject
0x180050ea0  nop     dword ptr [rax+rax+00h]
0x180050ea5  test    eax, eax
0x180050ea7  jz      short loc_180050EB4
0x180050ea9  cmp     eax, 102h
0x180050eae  jz      short loc_180050EB4
0x180050eb0  mov     cl, 1
0x180050eb2  jmp     short loc_180050EB6
0x180050eb4  xor     cl, cl
0x180050eb6  mov     r9, [rbp+8F8h]; char *
0x180050ebd  test    cl, cl
0x180050ebf  jnz     loc_180051153
0x180050ec5  test    eax, eax
0x180050ec7  jnz     short loc_180050EE4
0x180050ec9  mov     r9d, dword ptr [rbp+8F0h+var_928]; char *
0x180050ecd  mov     rcx, [rbp+8F8h]; this
0x180050ed4  test    r9d, r9d
0x180050ed7  js      loc_180051141
0x180050edd  cmp     [rbp+8F0h+var_910], 0
0x180050ee2  jnz     short loc_180050EF5
0x180050ee4  lea     rcx, [rbp+8F0h+var_4A0]; this
0x180050eeb  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180050ef0  jmp     loc_180050E34
0x180050ef5  lea     rdx, [rbp+8F0h+var_920]
0x180050ef9  lea     rcx, [rbp+8F0h+SourceString]
0x180050efd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050f02  nop
0x180050f03  lea     rcx, [rbp+8F0h+var_4A0]; this
0x180050f0a  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180050f0f  xor     r13d, r13d
0x180050f12  jmp     short loc_180050F3F
0x180050f14  xor     r13d, r13d
0x180050f17  test    al, al
0x180050f19  jnz     short loc_180050F21
0x180050f1b  lea     ecx, [r13+5]
0x180050f1f  int     29h; Win8: RtlFailFast(ecx)
0x180050f21  lea     rdx, [rbp+8F0h+var_140]
0x180050f28  lea     rcx, [rbp+8F0h+SourceString]
0x180050f2c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050f31  nop
0x180050f32  lea     rcx, [rbp+8F0h+var_4A0]; this
0x180050f39  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180050f3e  nop
0x180050f3f  test    rdi, rdi
0x180050f42  jz      short loc_180050F80
0x180050f44  or      r14d, 0FFFFFFFFh
0x180050f48  mov     eax, r14d
0x180050f4b  lock xadd [rdi+8], eax
0x180050f50  add     eax, r14d
0x180050f53  jnz     short loc_180050F80
0x180050f55  mov     rax, [rdi]
0x180050f58  mov     rcx, rdi
0x180050f5b  mov     rax, [rax]
0x180050f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f63  mov     eax, r14d
0x180050f66  lock xadd [rdi+0Ch], eax
0x180050f6b  add     eax, r14d
0x180050f6e  jnz     short loc_180050F80
0x180050f70  mov     rax, [rdi]
0x180050f73  mov     rcx, rdi
0x180050f76  mov     rax, [rax+8]
0x180050f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f7f  nop
0x180050f80  mov     rdx, rbx; struct _GUID *
0x180050f83  call    ?CloseComputeSystem@HcsClient@@YAXAEBU_GUID@@PEAUHCS_SYSTEM__@@@Z; HcsClient::CloseComputeSystem(_GUID const &,HCS_SYSTEM__ *)
0x180050f88  nop
0x180050f89  lea     rcx, [rbp+8F0h+var_920]
0x180050f8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050f92  mov     rcx, [rbp+8F0h+hHandle]; hObject
0x180050f96  test    rcx, rcx
0x180050f99  jz      short loc_180050FB6
0x180050f9b  call    cs:__imp_CloseHandle
0x180050fa2  nop     dword ptr [rax+rax+00h]
0x180050fa7  mov     rcx, [rbp+8F8h]; this
0x180050fae  test    eax, eax
0x180050fb0  jz      loc_1800510E3
0x180050fb6  mov     r15d, [rsp+9F0h+var_9C0]
0x180050fbb  xorps   xmm0, xmm0
0x180050fbe  movups  xmmword ptr [rbp+8F0h+DestinationString.Length], xmm0
0x180050fc2  lea     rdx, [rbp+8F0h+SourceString]
0x180050fc6  cmp     qword ptr [rbp+8F0h+var_940+8], 7
0x180050fcb  cmova   rdx, [rbp+8F0h+SourceString]; SourceString
0x180050fd0  lea     rcx, [rbp+8F0h+DestinationString]; DestinationString
0x180050fd4  call    cs:__imp_RtlInitUnicodeString
0x180050fdb  nop     dword ptr [rax+rax+00h]
0x180050fe0  mov     qword ptr [rsp+9F0h+ObjectAttributes.Length], 30h ; '0'
0x180050fe9  mov     qword ptr [rbp+8F0h+ObjectAttributes.Attributes], 0
0x180050ff1  mov     [rsp+9F0h+ObjectAttributes.RootDirectory], r13
0x180050ff6  lea     rax, [rbp+8F0h+DestinationString]
0x180050ffa  mov     [rbp+8F0h+ObjectAttributes.ObjectName], rax
0x180050ffe  xorps   xmm0, xmm0
0x180051001  movdqu  xmmword ptr [rbp+8F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051006  mov     [r12], r13
0x18005100a  mov     [rsp+9F0h+var_9BC], 1
0x180051012  lea     rbx, [rbp+8F0h+SourceString]
0x180051016  cmp     qword ptr [rbp+8F0h+var_940+8], 7
0x18005101b  cmova   rbx, [rbp+8F0h+SourceString]
0x180051020  mov     rcx, r12
0x180051023  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180051028  mov     rcx, rax; JobHandle
0x18005102b  lea     r8, [rsp+9F0h+ObjectAttributes]; ObjectAttributes
0x180051030  mov     edx, r15d; DesiredAccess
0x180051033  call    cs:__imp_NtOpenJobObject
0x18005103a  nop     dword ptr [rax+rax+00h]
0x18005103f  mov     rcx, [rbp+8F8h]; this
0x180051046  mov     [rsp+9F0h+var_9C8], rbx; char *
0x18005104b  lea     rdx, aFailedToOpenJo; "Failed to open job object '%ls'"
0x180051052  mov     qword ptr [rsp+9F0h+var_9D0], rdx; int
0x180051057  mov     r9d, eax; char *
0x18005105a  lea     r8, aOnecoreVmCompu_29; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x180051061  mov     edx, 187h; void *
0x180051066  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005106b  nop
0x18005106c  lea     rcx, [rbp+8F0h+var_8F0]; this
0x180051070  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180051075  nop
0x180051076  lea     rcx, [rbp+8F0h+SourceString]
0x18005107a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005107f  nop
0x180051080  test    rsi, rsi
0x180051083  jz      short loc_1800510BC
0x180051085  or      eax, 0FFFFFFFFh
0x180051088  lock xadd [rsi+8], eax
0x18005108d  cmp     eax, 1
0x180051090  jnz     short loc_1800510BC
0x180051092  mov     rax, [rsi]
0x180051095  mov     rcx, rsi
0x180051098  mov     rax, [rax]
0x18005109b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510a0  or      edx, 0FFFFFFFFh
0x1800510a3  lock xadd [rsi+0Ch], edx
0x1800510a8  cmp     edx, 1
0x1800510ab  jnz     short loc_1800510BC
0x1800510ad  mov     rdx, [rsi]
0x1800510b0  mov     rcx, rsi
0x1800510b3  mov     rax, [rdx+8]
0x1800510b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510bc  mov     rax, r12
0x1800510bf  mov     rcx, [rbp+8F0h+var_50]
0x1800510c6  xor     rcx, rsp; StackCookie
0x1800510c9  call    __security_check_cookie
0x1800510ce  add     rsp, 9B8h
0x1800510d5  pop     r15
0x1800510d7  pop     r14
0x1800510d9  pop     r13
0x1800510db  pop     r12
0x1800510dd  pop     rdi
0x1800510de  pop     rsi
0x1800510df  pop     rbx
0x1800510e0  pop     rbp
0x1800510e1  retn
0x1800510e3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800510ea  mov     edx, 0A0Bh; void *
0x1800510ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800510f5  mov     rcx, [rbp+8F8h]; this
0x1800510fc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180051103  mov     edx, 1CC8h; void *
0x180051108  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005110e  mov     r9d, 80070057h; char *
0x180051114  lea     r8, aOnecoreVmCompu_29; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x18005111b  mov     edx, 118h; void *
0x180051120  mov     rcx, r10; this
0x180051123  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
