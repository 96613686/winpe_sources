# Microsoft::Diagnostics::GetProcessDumpActionDef::DumpProcess(ulong,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &)

- ea: `0x1800e7680`
- end: `0x1800e7b17`
- name: `?DumpProcess@GetProcessDumpActionDef@Diagnostics@Microsoft@@AEBAJKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@@Z`
- size: `1175`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ec8ec`
- `0x180302c1c`

## callees

- `0x18001d5ac`
- `0x18001e638`
- `0x180020c1c`
- `0x180020fbc`
- `0x180024ee0`
- `0x180026ecc`
- `0x180029954`
- `0x180034d94`
- `0x1800566b0`
- `0x1800568e4`
- `0x18008674c`
- `0x18008b6b8`
- `0x1800d0d9c`
- `0x1800db3c8`
- `0x1800e7680`
- `0x1800fbba4`
- `0x180108668`
- `0x18022c00c`
- `0x18022c084`
- `0x180275a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7a52`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e76a9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e7722`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e76a9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e7722`

## string_xrefs

- `0x1800e7833`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800e78d5`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800e796b`: `onecore\base\telemetry\utc\service\scenarios\actions\getprocessdumpaction.cpp`
- `0x1800e7a68`: `Failed to open process (PplQuery): 0x`
- `0x1800e7751`: `Failed to open process (Non-Ppl): 0x`
- `0x1800e79d0`: `commandline`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::GetProcessDumpActionDef::DumpProcess(
        __int64 a1,
        DWORD a2,
        __int128 *a3,
        _QWORD *a4)
{
  char *v8; // rax
  bool IsProcessPpl; // al
  void *v10; // rcx
  __int64 v11; // rax
  void *v12; // rax
  DWORD v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v17; // r9
  __int64 result; // rax
  int v19; // eax
  unsigned int v20; // r15d
  __int64 v21; // rax
  void *v22; // rax
  int v23; // eax
  unsigned int v24; // esi
  int CommandLineForPids; // eax
  __int64 v26; // rbx
  int v27; // r8d
  DWORD LastError; // r14d
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // [rsp+20h] [rbp-C8h]
  __int128 v33; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-A8h] BYREF
  char *v35; // [rsp+50h] [rbp-98h] BYREF
  _QWORD v36[2]; // [rsp+58h] [rbp-90h] BYREF
  __int128 v37; // [rsp+68h] [rbp-80h] BYREF
  __int64 v38; // [rsp+78h] [rbp-70h]
  _QWORD v39[3]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v40[80]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v8 = (char *)OpenProcess(0x1000u, 0, a2);
  try
  {
    v35 = v8;
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v29 = Microsoft::Diagnostics::WideStringStream::operator<<(a4 + 21);
      WORD1(v34[0]) = 0;
      LOBYTE(v33) = 1;
      *(_WORD *)((char *)&v33 + 1) = BYTE1(v34[0]);
      BYTE3(v33) = 0;
      DWORD1(v33) = 2097153;
      *((_QWORD *)&v33 + 1) = 0;
      v30 = Microsoft::Diagnostics::WideStringStream::operator<<(v29, &v33);
      v31 = Microsoft::Diagnostics::WideStringStream::operator<<(v30, LastError);
      WORD1(v34[0]) = 0;
      LOBYTE(v33) = 1;
      *(_WORD *)((char *)&v33 + 1) = BYTE1(v34[0]);
      BYTE3(v33) = 0;
      DWORD1(v33) = 0x200000;
      *((_QWORD *)&v33 + 1) = 0;
      Microsoft::Diagnostics::WideStringStream::operator<<(v31, &v33);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
      result = 1;
    }
    else
    {
      IsProcessPpl = Microsoft::Diagnostics::Utils::Os::IsProcessPpl(v8);
      v10 = a4 + 21;
      if ( IsProcessPpl )
      {
        v21 = Microsoft::Diagnostics::WideStringStream::operator<<(v10);
        v22 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v21, a2);
        Microsoft::Diagnostics::WideStringStream::operator<<(v22);
        v33 = *a3;
        v23 = Microsoft::Diagnostics::Utils::Os::DumpPplProcess(a2, &v35, *(_DWORD *)(a1 + 200), &v33, a4[1]);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v23,
            v32);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
          return v24;
        }
      }
      else
      {
        v11 = Microsoft::Diagnostics::WideStringStream::operator<<(v10);
        v12 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v11, a2);
        Microsoft::Diagnostics::WideStringStream::operator<<(v12);
        v36[0] = OpenProcess(16 * (*(_DWORD *)(a1 + 200) & 4 | 0x41u), 1, a2);
        if ( ((v36[0] + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v13 = GetLastError();
          v14 = Microsoft::Diagnostics::WideStringStream::operator<<(a4 + 21);
          WORD1(v34[0]) = 0;
          LOBYTE(v33) = 1;
          *(_WORD *)((char *)&v33 + 1) = BYTE1(v34[0]);
          BYTE3(v33) = 0;
          DWORD1(v33) = 2097153;
          *((_QWORD *)&v33 + 1) = 0;
          v15 = Microsoft::Diagnostics::WideStringStream::operator<<(v14, &v33);
          v16 = Microsoft::Diagnostics::WideStringStream::operator<<(v15, v13);
          WORD1(v34[0]) = 0;
          LOBYTE(v33) = 1;
          *(_WORD *)((char *)&v33 + 1) = BYTE1(v34[0]);
          BYTE3(v33) = 0;
          DWORD1(v33) = 0x200000;
          *((_QWORD *)&v33 + 1) = 0;
          Microsoft::Diagnostics::WideStringStream::operator<<(v16, &v33);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v36);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
          return 1;
        }
        v33 = *a3;
        v19 = Microsoft::Diagnostics::Utils::Os::DumpProcess(a2, v36, *(_DWORD *)(a1 + 200), &v33, a4[1]);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
            (const char *)(unsigned int)v19,
            v32);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v36);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
          return v20;
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v36);
      }
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(v39);
      LODWORD(v36[0]) = a2;
      v37 = 0;
      v38 = 0;
      v34[0] = (char *)v36 + 4;
      *(_QWORD *)&v33 = v36;
      std::vector<unsigned long>::_Construct_n<unsigned long const *,unsigned long const *>(&v37, 1, &v33, v34);
      CommandLineForPids = Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids((DWORD **)&v37, (__int64)v39);
      if ( CommandLineForPids < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
          (const char *)(unsigned int)CommandLineForPids,
          v32);
      std::vector<enum _TDH_IN_TYPE>::~vector<enum _TDH_IN_TYPE>(&v37);
      if ( v39[0] != v39[1] )
      {
        v26 = a4[8];
        Microsoft::Diagnostics::EscalationWorkItemState::AddNewActionInfoToBuilder(a4, v36);
        v33 = *(_OWORD *)std::wstring::operator std::wstring_view(v39[0], v40);
        v34[0] = L"commandline";
        v34[1] = 11;
        JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(
          (unsigned int)&v37,
          v26,
          v27,
          (unsigned int)v36,
          (__int64)v34,
          (__int64)&v33);
        Microsoft::Diagnostics::EscalationWorkItemState::AddDynamicInfoForCurrentActionToBuilder((Microsoft::Diagnostics::EscalationWorkItemState *)a4);
      }
      v33 = *a3;
      Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(a4, &v33);
      std::vector<Microsoft::Diagnostics::XboxUser>::_Tidy(v39);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x190,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getprocessdumpaction.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800e7680  push    rbx
0x1800e7682  push    rsi
0x1800e7683  push    rdi
0x1800e7684  push    r12
0x1800e7686  push    r13
0x1800e7688  push    r14
0x1800e768a  push    r15
0x1800e768c  sub     rsp, 0B0h
0x1800e7693  mov     rdi, r9
0x1800e7696  mov     r12, r8
0x1800e7699  mov     r14d, edx
0x1800e769c  mov     r13, rcx
0x1800e769f  mov     r8d, edx; dwProcessId
0x1800e76a2  xor     edx, edx; bInheritHandle
0x1800e76a4  mov     ecx, 1000h; dwDesiredAccess
0x1800e76a9  call    cs:__imp_OpenProcess
0x1800e76b0  nop     dword ptr [rax+rax+00h]
0x1800e76b5  mov     [rsp+0E8h+var_98], rax
0x1800e76ba  lea     rcx, [rax-1]
0x1800e76be  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800e76c2  ja      loc_1800E7A52
0x1800e76c8  lea     r15, [rdi+0A8h]
0x1800e76cf  mov     rcx, rax; void *
0x1800e76d2  call    ?IsProcessPpl@Os@Utils@Diagnostics@Microsoft@@SA_NPEAX@Z; Microsoft::Diagnostics::Utils::Os::IsProcessPpl(void *)
0x1800e76d7  xor     ebx, ebx
0x1800e76d9  mov     rcx, r15; Src
0x1800e76dc  test    al, al
0x1800e76de  jnz     loc_1800E7871
0x1800e76e4  lea     rdx, aDumpingNonPplP; "Dumping non-PPL process: "
0x1800e76eb  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800e76f0  mov     edx, r14d
0x1800e76f3  mov     rcx, rax
0x1800e76f6  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1800e76fb  lea     rdx, asc_1803721B4; "\r\n"
0x1800e7702  mov     rcx, rax; Src
0x1800e7705  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800e770a  mov     ecx, [r13+0C8h]
0x1800e7711  and     ecx, 4
0x1800e7714  or      ecx, 41h
0x1800e7717  shl     ecx, 4; dwDesiredAccess
0x1800e771a  mov     r8d, r14d; dwProcessId
0x1800e771d  lea     esi, [rbx+1]
0x1800e7720  mov     edx, esi; bInheritHandle
0x1800e7722  call    cs:__imp_OpenProcess
0x1800e7729  nop     dword ptr [rax+rax+00h]
0x1800e772e  mov     [rsp+0E8h+var_90], rax
0x1800e7733  inc     rax
0x1800e7736  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e773c  jnz     loc_1800E77F4
0x1800e7742  call    cs:__imp_GetLastError
0x1800e7749  nop     dword ptr [rax+rax+00h]
0x1800e774e  mov     r14d, eax
0x1800e7751  lea     rdx, aFailedToOpenPr; "Failed to open process (Non-Ppl): 0x"
0x1800e7758  mov     rcx, r15; Src
0x1800e775b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800e7760  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1800e7765  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1800e776a  movzx   ecx, word ptr [rsp+41h]
0x1800e776f  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1800e7774  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1800e7778  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1800e777c  mov     dword ptr [rsp+0E8h+var_B8+4], 200001h
0x1800e7784  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1800e7789  lea     rdx, [rsp+0E8h+var_B8]
0x1800e778e  mov     rcx, rax
0x1800e7791  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1800e7796  mov     edx, r14d
0x1800e7799  mov     rcx, rax
0x1800e779c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1800e77a1  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1800e77a6  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1800e77ab  movzx   ecx, word ptr [rsp+41h]
0x1800e77b0  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1800e77b5  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1800e77b9  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1800e77bd  mov     dword ptr [rsp+0E8h+var_B8+4], 200000h
0x1800e77c5  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1800e77ca  lea     rdx, [rsp+0E8h+var_B8]
0x1800e77cf  mov     rcx, rax
0x1800e77d2  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1800e77d7  nop
0x1800e77d8  lea     rcx, [rsp+0E8h+var_90]
0x1800e77dd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e77e2  nop
0x1800e77e3  lea     rcx, [rsp+0E8h+var_98]
0x1800e77e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e77ed  mov     eax, esi
0x1800e77ef  jmp     loc_1800E7B03
0x1800e77f4  movaps  xmm0, xmmword ptr [r12]
0x1800e77f9  movdqa  [rsp+0E8h+var_B8], xmm0
0x1800e77ff  mov     rax, [rdi+8]
0x1800e7803  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800e7808  lea     r9, [rsp+0E8h+var_B8]
0x1800e780d  mov     r8d, [r13+0C8h]
0x1800e7814  lea     rdx, [rsp+0E8h+var_90]
0x1800e7819  mov     ecx, r14d
0x1800e781c  call    ?DumpProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z; Microsoft::Diagnostics::Utils::Os::DumpProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::wstring_view,unsigned __int64)
0x1800e7821  mov     r15d, eax
0x1800e7824  test    eax, eax
0x1800e7826  jns     short loc_1800E7862
0x1800e7828  mov     rcx, [rsp+0E8h]; this
0x1800e7830  mov     r9d, eax; char *
0x1800e7833  lea     r8, aOnecoreBaseTel_163; "onecore\\base\\telemetry\\utc\\service"...
0x1800e783a  mov     edx, 176h; void *
0x1800e783f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7844  nop
0x1800e7845  lea     rcx, [rsp+0E8h+var_90]
0x1800e784a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e784f  nop
0x1800e7850  lea     rcx, [rsp+0E8h+var_98]
0x1800e7855  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e785a  mov     eax, r15d
0x1800e785d  jmp     loc_1800E7B03
0x1800e7862  lea     rcx, [rsp+0E8h+var_90]
0x1800e7867  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e786c  jmp     loc_1800E78FD
0x1800e7871  lea     rdx, aDumpingPplProc; "Dumping PPL process: "
0x1800e7878  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800e787d  mov     edx, r14d
0x1800e7880  mov     rcx, rax
0x1800e7883  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1800e7888  lea     rdx, asc_1803721B4; "\r\n"
0x1800e788f  mov     rcx, rax; Src
0x1800e7892  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800e7897  movaps  xmm0, xmmword ptr [r12]
0x1800e789c  movdqa  [rsp+0E8h+var_B8], xmm0
0x1800e78a2  mov     rax, [rdi+8]
0x1800e78a6  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800e78ab  lea     r9, [rsp+0E8h+var_B8]
0x1800e78b0  mov     r8d, [r13+0C8h]
0x1800e78b7  lea     rdx, [rsp+0E8h+var_98]
0x1800e78bc  mov     ecx, r14d
0x1800e78bf  call    ?DumpPplProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z; Microsoft::Diagnostics::Utils::Os::DumpPplProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::wstring_view,unsigned __int64)
0x1800e78c4  mov     esi, eax
0x1800e78c6  test    eax, eax
0x1800e78c8  jns     short loc_1800E78F8
0x1800e78ca  mov     rcx, [rsp+0E8h]; this
0x1800e78d2  mov     r9d, eax; char *
0x1800e78d5  lea     r8, aOnecoreBaseTel_163; "onecore\\base\\telemetry\\utc\\service"...
0x1800e78dc  mov     edx, 17Ch; void *
0x1800e78e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e78e6  nop
0x1800e78e7  lea     rcx, [rsp+0E8h+var_98]
0x1800e78ec  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e78f1  mov     eax, esi
0x1800e78f3  jmp     loc_1800E7B03
0x1800e78f8  mov     esi, 1
0x1800e78fd  lea     rcx, [rsp+0E8h+var_68]; void *
0x1800e7905  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1800e790a  nop
0x1800e790b  mov     dword ptr [rsp+0E8h+var_90], r14d
0x1800e7910  xorps   xmm0, xmm0
0x1800e7913  movdqu  [rsp+0E8h+var_80], xmm0
0x1800e7919  mov     [rsp+0E8h+var_70], rbx
0x1800e791e  lea     rax, [rsp+0E8h+var_90+4]
0x1800e7923  mov     [rsp+40h], rax
0x1800e7928  lea     rax, [rsp+0E8h+var_90]
0x1800e792d  mov     qword ptr [rsp+0E8h+var_B8], rax
0x1800e7932  lea     r9, [rsp+0E8h+var_A8]
0x1800e7937  lea     r8, [rsp+0E8h+var_B8]
0x1800e793c  mov     rdx, rsi
0x1800e793f  lea     rcx, [rsp+0E8h+var_80]
0x1800e7944  call    ??$_Construct_n@PEBKPEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAX_K$$QEAPEBK1@Z; std::vector<ulong>::_Construct_n<ulong const *,ulong const *>(unsigned __int64,ulong const * &&,ulong const * &&)
0x1800e7949  nop
0x1800e794a  lea     rdx, [rsp+0E8h+var_68]
0x1800e7952  lea     rcx, [rsp+0E8h+var_80]
0x1800e7957  call    ?GetCommandLineForPids@Os@Utils@Diagnostics@Microsoft@@SAJAEBV?$vector@KV?$allocator@K@std@@@std@@AEAV?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@6@@Z; Microsoft::Diagnostics::Utils::Os::GetCommandLineForPids(std::vector<ulong> const &,std::vector<std::pair<std::wstring,ulong>> &)
0x1800e795c  mov     rcx, [rsp+0E8h]; this
0x1800e7964  test    eax, eax
0x1800e7966  jns     short loc_1800E797D
0x1800e7968  mov     r9d, eax; char *
0x1800e796b  lea     r8, aOnecoreBaseTel_163; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7972  mov     edx, 181h; void *
0x1800e7977  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e797c  nop
0x1800e797d  lea     rcx, [rsp+0E8h+var_80]
0x1800e7982  call    ??1?$vector@W4_TDH_IN_TYPE@@V?$allocator@W4_TDH_IN_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_TDH_IN_TYPE>::~vector<_TDH_IN_TYPE>(void)
0x1800e7987  mov     rax, [rsp+0E8h+var_60]
0x1800e798f  cmp     [rsp+0E8h+var_68], rax
0x1800e7997  jz      short loc_1800E7A13
0x1800e7999  mov     rbx, [rdi+40h]
0x1800e799d  lea     rdx, [rsp+0E8h+var_90]
0x1800e79a2  mov     rcx, rdi
0x1800e79a5  call    ?AddNewActionInfoToBuilder@EscalationWorkItemState@Diagnostics@Microsoft@@QEAA?AVJsonIterator@@XZ; Microsoft::Diagnostics::EscalationWorkItemState::AddNewActionInfoToBuilder(void)
0x1800e79aa  lea     rdx, [rsp+0E8h+var_50]
0x1800e79b2  mov     rcx, [rsp+0E8h+var_68]
0x1800e79ba  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800e79bf  mov     rcx, [rax]
0x1800e79c2  mov     qword ptr [rsp+0E8h+var_B8], rcx
0x1800e79c7  mov     rax, [rax+8]
0x1800e79cb  mov     qword ptr [rsp+0E8h+var_B8+8], rax
0x1800e79d0  lea     rax, aCommandline_2; "commandline"
0x1800e79d7  mov     [rsp+0E8h+var_A8], rax
0x1800e79dc  mov     [rsp+0E8h+var_A0], 0Bh
0x1800e79e5  lea     rax, [rsp+0E8h+var_B8]
0x1800e79ea  mov     [rsp+0E8h+var_C0], rax
0x1800e79ef  lea     rax, [rsp+0E8h+var_A8]
0x1800e79f4  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1800e79f9  lea     r9, [rsp+0E8h+var_90]
0x1800e79fe  mov     rdx, rbx
0x1800e7a01  lea     rcx, [rsp+0E8h+var_80]
0x1800e7a06  call    ?AddValue@?$JsonImplementType@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@SA?AVJsonIterator@@AEAVJsonBuilder@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@3@Z; JsonImplementType<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::AddValue(JsonBuilder &,bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800e7a0b  mov     rcx, rdi; this
0x1800e7a0e  call    ?AddDynamicInfoForCurrentActionToBuilder@EscalationWorkItemState@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::EscalationWorkItemState::AddDynamicInfoForCurrentActionToBuilder(void)
0x1800e7a13  mov     r8d, 3
0x1800e7a19  movaps  xmm0, xmmword ptr [r12]
0x1800e7a1e  movdqa  [rsp+0E8h+var_B8], xmm0
0x1800e7a24  lea     rdx, [rsp+0E8h+var_B8]
0x1800e7a29  mov     rcx, rdi
0x1800e7a2c  call    ?AddCollectedFileToBuilder@EscalationWorkItemState@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@VCollectedFileType@EnumDetails@23@@Z; Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(std::wstring_view,Microsoft::Diagnostics::EnumDetails::CollectedFileType)
0x1800e7a31  nop
0x1800e7a32  lea     rcx, [rsp+0E8h+var_68]
0x1800e7a3a  call    ?_Tidy@?$vector@UXboxUser@Diagnostics@Microsoft@@V?$allocator@UXboxUser@Diagnostics@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Diagnostics::XboxUser>::_Tidy(void)
0x1800e7a3f  nop
0x1800e7a40  lea     rcx, [rsp+0E8h+var_98]
0x1800e7a45  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7a4a  nop
0x1800e7a4b  xor     eax, eax
0x1800e7a4d  jmp     loc_1800E7B03
0x1800e7a52  call    cs:__imp_GetLastError
0x1800e7a59  nop     dword ptr [rax+rax+00h]
0x1800e7a5e  mov     r14d, eax
0x1800e7a61  lea     rcx, [rdi+0A8h]; Src
0x1800e7a68  lea     rdx, aFailedToOpenPr_0; "Failed to open process (PplQuery): 0x"
0x1800e7a6f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800e7a74  xor     ebx, ebx
0x1800e7a76  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1800e7a7b  lea     esi, [rbx+1]
0x1800e7a7e  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1800e7a83  movzx   ecx, word ptr [rsp+0E8h+var_A8+1]
0x1800e7a88  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1800e7a8d  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1800e7a91  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1800e7a95  mov     dword ptr [rsp+0E8h+var_B8+4], 200001h
0x1800e7a9d  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1800e7aa2  lea     rdx, [rsp+0E8h+var_B8]
0x1800e7aa7  mov     rcx, rax
0x1800e7aaa  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1800e7aaf  mov     edx, r14d
0x1800e7ab2  mov     rcx, rax
0x1800e7ab5  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1800e7aba  mov     word ptr [rsp+0E8h+var_A8+2], bx
0x1800e7abf  mov     byte ptr [rsp+0E8h+var_B8], sil
0x1800e7ac4  movzx   ecx, word ptr [rsp+0E8h+var_A8+1]
0x1800e7ac9  mov     word ptr [rsp+0E8h+var_B8+1], cx
0x1800e7ace  mov     cl, byte ptr [rsp+0E8h+var_A8+3]
0x1800e7ad2  mov     byte ptr [rsp+0E8h+var_B8+3], cl
0x1800e7ad6  mov     dword ptr [rsp+0E8h+var_B8+4], 200000h
0x1800e7ade  mov     qword ptr [rsp+0E8h+var_B8+8], rbx
0x1800e7ae3  lea     rdx, [rsp+0E8h+var_B8]
0x1800e7ae8  mov     rcx, rax
0x1800e7aeb  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1800e7af0  nop
0x1800e7af1  lea     rcx, [rsp+0E8h+var_98]
0x1800e7af6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7afb  mov     eax, esi
0x1800e7afd  jmp     short loc_1800E7B03
0x1800e7aff  mov     eax, dword ptr [rsp+0E8h+var_90]
0x1800e7b03  add     rsp, 0B0h
0x1800e7b0a  pop     r15
0x1800e7b0c  pop     r14
0x1800e7b0e  pop     r13
0x1800e7b10  pop     r12
0x1800e7b12  pop     rdi
0x1800e7b13  pop     rsi
0x1800e7b14  pop     rbx
0x1800e7b15  retn
```
