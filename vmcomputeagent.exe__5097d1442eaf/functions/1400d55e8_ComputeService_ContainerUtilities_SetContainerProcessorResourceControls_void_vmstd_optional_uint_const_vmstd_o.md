# ComputeService::ContainerUtilities::SetContainerProcessorResourceControls(void *,vmstd::optional<uint> const &,vmstd::optional<__int64> const &,vmstd::optional<__int64> const &)

- ea: `0x1400d55e8`
- end: `0x1400d581f`
- name: `?SetContainerProcessorResourceControls@ContainerUtilities@ComputeService@@YAXPEAXAEBU?$optional@I@vmstd@@AEBU?$optional@_J@4@2@Z`
- size: `567`
- prototype: `__int64 __fastcall(HANDLE hJob)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140087d00`
- `0x14008b7f0`

## callees

- `0x140005360`
- `0x1400083bc`
- `0x14000ddac`
- `0x140030048`
- `0x140030060`
- `0x14003fc00`
- `0x1400d1c4c`
- `0x1400d55e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1400d5632`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1400d5632`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1400d5709`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x1400d5709`

## string_xrefs

- `0x1400d5774`: `onecore\vm\common\vml\VmPhysicalProcessorInfo.h`
- `0x1400d573c`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d5794`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d57d5`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d580d`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`

## pseudocode

```c
void __fastcall ComputeService::ContainerUtilities::SetContainerProcessorResourceControls(
        HANDLE hJob,
        unsigned int *a2,
        __int64 a3,
        __int64 a4)
{
  bool v4; // zf
  __int64 v9; // rdx
  const char *v10; // r9
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  const char *v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // [rsp+20h] [rbp-20h] BYREF
  __int64 JobObjectInformation; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v4 = *((_BYTE *)a2 + 4) == 0;
  JobObjectInformation = 0;
  if ( v4 )
  {
    if ( *(_BYTE *)(a3 + 8) )
    {
      if ( *(_QWORD *)a3 > 0x2710u )
      {
        v16 = wil::verify_hresult<long>(2147942487LL, a2);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x38C,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
          (const char *)v16,
          v17);
        v17 = *(_QWORD *)vmstd::optional<__int64>::operator*(a3);
        ComputeService::Reporting::LogAndThrowComputeError<__int64>(
          v17,
          MSVCOMP_INVALID_CONTAINER_PROCESSOR_WEIGHT,
          &v17);
      }
      v12 = 8LL * *(_QWORD *)a3;
      LODWORD(JobObjectInformation) = 3;
      HIDWORD(JobObjectInformation) = (int)v12 / 10000 + 1;
      goto LABEL_16;
    }
    if ( !*(_BYTE *)(a4 + 8) )
      return;
    if ( (unsigned __int64)(*(_QWORD *)a4 - 1LL) > 0x270F )
    {
      v14 = wil::verify_hresult<long>(2147942487LL, a2);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x39C,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)v14,
        v17);
      v17 = *(_QWORD *)vmstd::optional<__int64>::operator*(a4);
      ComputeService::Reporting::LogAndThrowComputeError<__int64>(v17, MSVCOMP_INVALID_CONTAINER_PROCESSOR_LIMIT, &v17);
    }
    LODWORD(v11) = *(_DWORD *)a4;
    LODWORD(JobObjectInformation) = 5;
  }
  else
  {
    if ( !InitOnceExecuteOnce(
            &Vml::gm_PhysicalProcessorInfoInit,
            _lambda_416112f8a69568f1ffa65c20bf1b41eb_::_lambda_invoker_cdecl_,
            0,
            0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x167,
        (unsigned int)"onecore\\vm\\common\\vml\\VmPhysicalProcessorInfo.h",
        v10);
    if ( !*((_BYTE *)a2 + 4) )
      __fastfail(5u);
    if ( !*a2 || (v9 = (unsigned int)dword_14016137C, *a2 > dword_14016137C) )
    {
      v15 = wil::verify_hresult<long>(2147942487LL, v9);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)v15,
        v17);
      v17 = *(unsigned int *)vmstd::optional<unsigned int>::operator*(a2);
      ComputeService::Reporting::LogAndThrowComputeError<__int64>(v17, MSVCOMP_INVALID_CONTAINER_PROCESSOR_COUNT, &v17);
    }
    LODWORD(JobObjectInformation) = 5;
    v11 = 10000 * (unsigned __int64)*a2 / (unsigned int)dword_14016137C;
    if ( !v11 )
      LODWORD(v11) = 1;
  }
  HIDWORD(JobObjectInformation) = v11;
LABEL_16:
  if ( !SetInformationJobObject(hJob, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &JobObjectInformation, 8u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3B0,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      v13);
}

```

## disassembly

```asm
0x1400d55e8  push    rbp
0x1400d55ea  push    rbx
0x1400d55eb  push    rsi
0x1400d55ec  push    rdi
0x1400d55ed  push    r14
0x1400d55ef  mov     rbp, rsp
0x1400d55f2  sub     rsp, 40h
0x1400d55f6  mov     rax, cs:__security_cookie
0x1400d55fd  xor     rax, rsp
0x1400d5600  mov     [rbp+var_10], rax
0x1400d5604  cmp     byte ptr [rdx+4], 0
0x1400d5608  mov     rbx, r9
0x1400d560b  mov     rdi, r8
0x1400d560e  mov     [rbp+JobObjectInformation], 0
0x1400d5616  mov     rsi, rdx
0x1400d5619  mov     r14, rcx
0x1400d561c  jz      short loc_1400D5691
0x1400d561e  xor     r9d, r9d; Context
0x1400d5621  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_416112f8a69568f1ffa65c20bf1b41eb_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1400d5628  xor     r8d, r8d; Parameter
0x1400d562b  lea     rcx, ?gm_PhysicalProcessorInfoInit@Vml@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1400d5632  call    cs:__imp_InitOnceExecuteOnce
0x1400d5638  test    eax, eax
0x1400d563a  jz      loc_1400D5770
0x1400d5640  mov     al, [rsi+4]
0x1400d5643  mov     ecx, 5
0x1400d5648  test    al, al
0x1400d564a  jnz     short loc_1400D564E
0x1400d564c  int     29h; Win8: RtlFailFast(ecx)
0x1400d564e  cmp     dword ptr [rsi], 0
0x1400d5651  jbe     loc_1400D5786
0x1400d5657  mov     edx, cs:dword_14016137C
0x1400d565d  test    al, al
0x1400d565f  jnz     short loc_1400D5663
0x1400d5661  int     29h; Win8: RtlFailFast(ecx)
0x1400d5663  cmp     [rsi], edx
0x1400d5665  ja      loc_1400D5786
0x1400d566b  mov     dword ptr [rbp+JobObjectInformation], ecx
0x1400d566e  test    al, al
0x1400d5670  jnz     short loc_1400D5674
0x1400d5672  int     29h; Win8: RtlFailFast(ecx)
0x1400d5674  mov     eax, [rsi]
0x1400d5676  mov     rcx, rdx
0x1400d5679  imul    rax, 2710h
0x1400d5680  xor     edx, edx
0x1400d5682  div     rcx
0x1400d5685  test    rax, rax
0x1400d5688  jnz     short loc_1400D56F5
0x1400d568a  mov     eax, 1
0x1400d568f  jmp     short loc_1400D56F5
0x1400d5691  cmp     byte ptr [r8+8], 0
0x1400d5696  jz      short loc_1400D56D5
0x1400d5698  mov     rcx, [r8]
0x1400d569b  cmp     rcx, 2710h
0x1400d56a2  ja      loc_1400D57C7
0x1400d56a8  shl     rcx, 3
0x1400d56ac  mov     rax, 346DC5D63886594Bh
0x1400d56b6  imul    rcx
0x1400d56b9  mov     dword ptr [rbp+JobObjectInformation], 3
0x1400d56c0  sar     rdx, 0Bh
0x1400d56c4  mov     rax, rdx
0x1400d56c7  shr     rax, 3Fh
0x1400d56cb  add     rdx, rax
0x1400d56ce  inc     edx
0x1400d56d0  mov     dword ptr [rbp+JobObjectInformation+4], edx
0x1400d56d3  jmp     short loc_1400D56F8
0x1400d56d5  cmp     byte ptr [r9+8], 0
0x1400d56da  jz      short loc_1400D5717
0x1400d56dc  mov     rax, [r9]
0x1400d56df  dec     rax
0x1400d56e2  cmp     rax, 270Fh
0x1400d56e8  ja      short loc_1400D572E
0x1400d56ea  mov     eax, [r9]
0x1400d56ed  mov     ecx, 5
0x1400d56f2  mov     dword ptr [rbp+JobObjectInformation], ecx
0x1400d56f5  mov     dword ptr [rbp+JobObjectInformation+4], eax
0x1400d56f8  mov     r9d, 8; cbJobObjectInformationLength
0x1400d56fe  lea     r8, [rbp+JobObjectInformation]; lpJobObjectInformation
0x1400d5702  mov     rcx, r14; hJob
0x1400d5705  lea     edx, [r9+7]; JobObjectInformationClass
0x1400d5709  call    cs:__imp_SetInformationJobObject
0x1400d570f  test    eax, eax
0x1400d5711  jz      loc_1400D5809
0x1400d5717  mov     rcx, [rbp+var_10]
0x1400d571b  xor     rcx, rsp; StackCookie
0x1400d571e  call    __security_check_cookie
0x1400d5723  add     rsp, 40h
0x1400d5727  pop     r14
0x1400d5729  pop     rdi
0x1400d572a  pop     rsi
0x1400d572b  pop     rbx
0x1400d572c  pop     rbp
0x1400d572d  retn
0x1400d572e  mov     ecx, 80070057h
0x1400d5733  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400d5738  mov     rcx, [rbp+28h]; this
0x1400d573c  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d5743  mov     r9d, eax; char *
0x1400d5746  mov     edx, 39Ch; void *
0x1400d574b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400d5750  mov     rcx, rbx
0x1400d5753  call    ??D?$optional@_J@vmstd@@QEBAAEB_JXZ; vmstd::optional<__int64>::operator*(void)
0x1400d5758  lea     r8, [rbp+var_20]
0x1400d575c  lea     rdx, MSVCOMP_INVALID_CONTAINER_PROCESSOR_LIMIT
0x1400d5763  mov     rcx, [rax]
0x1400d5766  mov     [rbp+var_20], rcx
0x1400d576a  call    ??$LogAndThrowComputeError@_J@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEA_J@Z; ComputeService::Reporting::LogAndThrowComputeError<__int64>(long,_EVENT_DESCRIPTOR const *,__int64 &&)
0x1400d5770  mov     rcx, [rbp+28h]; this
0x1400d5774  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmPhysicalPro"...
0x1400d577b  mov     edx, 167h; void *
0x1400d5780  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400d5786  mov     ecx, 80070057h
0x1400d578b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400d5790  mov     rcx, [rbp+28h]; this
0x1400d5794  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d579b  mov     r9d, eax; char *
0x1400d579e  mov     edx, 382h; void *
0x1400d57a3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400d57a8  mov     rcx, rsi
0x1400d57ab  call    ??D?$optional@I@vmstd@@QEBAAEBIXZ; vmstd::optional<uint>::operator*(void)
0x1400d57b0  lea     r8, [rbp+var_20]
0x1400d57b4  lea     rdx, MSVCOMP_INVALID_CONTAINER_PROCESSOR_COUNT
0x1400d57bb  mov     ecx, [rax]
0x1400d57bd  mov     [rbp+var_20], rcx
0x1400d57c1  call    ??$LogAndThrowComputeError@_J@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEA_J@Z; ComputeService::Reporting::LogAndThrowComputeError<__int64>(long,_EVENT_DESCRIPTOR const *,__int64 &&)
0x1400d57c7  mov     ecx, 80070057h
0x1400d57cc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400d57d1  mov     rcx, [rbp+28h]; this
0x1400d57d5  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d57dc  mov     r9d, eax; char *
0x1400d57df  mov     edx, 38Ch; void *
0x1400d57e4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400d57e9  mov     rcx, rdi
0x1400d57ec  call    ??D?$optional@_J@vmstd@@QEBAAEB_JXZ; vmstd::optional<__int64>::operator*(void)
0x1400d57f1  lea     r8, [rbp+var_20]
0x1400d57f5  lea     rdx, MSVCOMP_INVALID_CONTAINER_PROCESSOR_WEIGHT
0x1400d57fc  mov     rcx, [rax]
0x1400d57ff  mov     [rbp+var_20], rcx
0x1400d5803  call    ??$LogAndThrowComputeError@_J@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEA_J@Z; ComputeService::Reporting::LogAndThrowComputeError<__int64>(long,_EVENT_DESCRIPTOR const *,__int64 &&)
0x1400d5809  mov     rcx, [rbp+28h]; this
0x1400d580d  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d5814  mov     edx, 3B0h; void *
0x1400d5819  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
