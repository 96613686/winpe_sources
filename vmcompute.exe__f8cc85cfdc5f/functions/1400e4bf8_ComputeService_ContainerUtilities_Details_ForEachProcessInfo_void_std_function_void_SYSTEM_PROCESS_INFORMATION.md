# ComputeService::ContainerUtilities::Details::ForEachProcessInfo(void *,std::function<void (_SYSTEM_PROCESS_INFORMATION *)>)

- ea: `0x1400e4bf8`
- end: `0x1400e4efe`
- name: `?ForEachProcessInfo@Details@ContainerUtilities@ComputeService@@YAXPEAXV?$function@$$A6AXPEAU_SYSTEM_PROCESS_INFORMATION@@@Z@std@@@Z`
- size: `774`
- prototype: `__int64 __fastcall(HANDLE hJob)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140216660`

## callees

- `0x140024030`
- `0x14004a2fc`
- `0x1400548f8`
- `0x140080180`
- `0x1400a97c8`
- `0x1400c40e0`
- `0x1400e4adc`
- `0x1400e4bf8`
- `0x1400e4f10`
- `0x1400e4f40`
- `0x1400e4f70`
- `0x1401332f0`
- `0x1402c4010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400e4ef1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400e4ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4ced`
- `ntdll!NtQueryInformationProcess` at `0x1400e4e16`
- `ntdll!NtQueryInformationProcess` at `0x1400e4e16`
- `ntdll!NtQuerySystemInformation` at `0x1400e4cb6`
- `ntdll!NtQuerySystemInformation` at `0x1400e4cb6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400e4dd7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400e4dd7`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1400e4d48`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1400e4d48`

## string_xrefs

- `0x1400e4cd7`: `onecore\vm\compute\management\shared\container\containerjobinfo.cpp`
- `0x1400e4edc`: `onecore\vm\compute\management\shared\container\containerjobinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ComputeService::ContainerUtilities::Details::ForEachProcessInfo(HANDLE hJob, __int64 a2)
{
  ULONG v4; // edi
  __int64 v5; // rax
  const char *v6; // r9
  __int64 v7; // rax
  char *v8; // rbx
  NTSTATUS v9; // eax
  DWORD v10; // edi
  __int64 i; // rdx
  const char *v12; // r9
  __int64 v13; // rax
  _DWORD *v14; // rsi
  __int64 j; // rdi
  unsigned int v16; // edi
  char *v17; // rsi
  DWORD v18; // r10d
  __int64 v19; // rax
  char *v20; // rax
  __int64 v21; // rcx
  __int64 result; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int lpReturnLength; // [rsp+20h] [rbp-59h]
  _QWORD v26[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v27; // [rsp+40h] [rbp-39h]
  __int64 v28; // [rsp+48h] [rbp-31h]
  char *v29; // [rsp+50h] [rbp-29h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp-21h] BYREF
  LPVOID lpJobObjectInformation; // [rsp+60h] [rbp-19h] BYREF
  PVOID SystemInformation; // [rsp+68h] [rbp-11h] BYREF
  __int128 v33; // [rsp+70h] [rbp-9h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v28 = a2;
  v4 = 0x80000;
  SystemInformation = 0;
  v5 = std::make_unique<unsigned char [0],0>(&lpJobObjectInformation, 0x80000);
  std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(&SystemInformation, v5);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpJobObjectInformation);
  while ( 1 )
  {
    v8 = (char *)SystemInformation;
    ReturnLength = 0;
    v9 = NtQuerySystemInformation(SystemProcessInformation, SystemInformation, v4, &ReturnLength);
    if ( v9 >= 0 )
      break;
    v6 = (const char *)(unsigned int)v9;
    if ( v9 != -1073741820 )
    {
      LODWORD(v6) = v9 | 0x10000000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerjobinfo.cpp",
        v6,
        lpReturnLength);
    }
    if ( ReturnLength <= v4 )
      v4 += 4096;
    else
      v4 = ReturnLength;
    v7 = std::make_unique<unsigned char [0],0>(&lpJobObjectInformation, v4);
    std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(&SystemInformation, v7);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpJobObjectInformation);
  }
  lpJobObjectInformation = 0;
  v10 = 1024;
  for ( i = 1024; ; i = v10 )
  {
    v13 = std::make_unique<unsigned char [0],0>(&v29, i);
    std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(
      &lpJobObjectInformation,
      v13);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v29);
    v14 = lpJobObjectInformation;
    if ( QueryInformationJobObject(hJob, JobObjectBasicProcessIdList, lpJobObjectInformation, v10, 0) )
      break;
    if ( GetLastError() != 234 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerjobinfo.cpp",
        v12);
    v10 = 8 * *v14 + 8;
  }
  v33 = 0;
  std::set<unsigned int>::set<unsigned int>(&v33);
  for ( j = 0; (unsigned int)j < v14[1]; j = (unsigned int)(j + 1) )
  {
    LODWORD(v29) = v14[2 * j + 2];
    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
      &v33,
      v26,
      &v29);
  }
  v16 = 0;
  do
  {
    v17 = &v8[v16];
    LODWORD(v29) = *((_DWORD *)v17 + 20);
    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::_Find_lower_bound<unsigned long>(
      &v33,
      v26,
      &v29);
    v19 = v27;
    if ( *(_BYTE *)(v27 + 25) || v18 < *(_DWORD *)(v27 + 28) )
      v19 = v33;
    if ( v19 != (_QWORD)v33 )
    {
      v20 = (char *)OpenProcess(0x1000u, 0, v18);
      v26[0] = v20;
      if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        memset(ProcessInformation, 0, sizeof(ProcessInformation));
        if ( NtQueryInformationProcess(v20, ProcessTimes, ProcessInformation, 0x20u, 0) >= 0
          && *(_QWORD *)&ProcessInformation[0] == *((_QWORD *)v17 + 4) )
        {
          v29 = &v8[v16];
          v21 = *(_QWORD *)(a2 + 56);
          if ( !v21 )
          {
            std::_Xbad_function_call();
            __debugbreak();
            JUMPOUT(0x1400E4EFELL);
          }
          (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v21 + 16LL))(v21, &v29);
        }
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v26);
    }
    if ( !*(_DWORD *)v17 )
      break;
    v16 += *(_DWORD *)v17;
  }
  while ( (unsigned __int64)v16 + 256 <= ReturnLength );
  std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(&v33);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpJobObjectInformation);
  result = std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&SystemInformation);
  v24 = *(_QWORD *)(a2 + 56);
  if ( v24 )
  {
    LOBYTE(v23) = v24 != a2;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 32LL))(v24, v23);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400e4bf8  mov     [rsp-8+arg_10], rbx
0x1400e4bfd  push    rbp
0x1400e4bfe  push    rsi
0x1400e4bff  push    rdi
0x1400e4c00  push    r14
0x1400e4c02  push    r15
0x1400e4c04  lea     rbp, [rsp-37h]
0x1400e4c09  sub     rsp, 0B0h
0x1400e4c10  mov     rax, cs:__security_cookie
0x1400e4c17  xor     rax, rsp
0x1400e4c1a  mov     [rbp+57h+var_30], rax
0x1400e4c1e  mov     r14, rdx
0x1400e4c21  mov     r15, rcx
0x1400e4c24  mov     [rbp+57h+var_88], rdx
0x1400e4c28  mov     edi, 80000h
0x1400e4c2d  mov     [rbp+57h+SystemInformation], 0
0x1400e4c35  mov     edx, edi
0x1400e4c37  lea     rcx, [rbp+57h+lpJobObjectInformation]
0x1400e4c3b  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1400e4c40  mov     rdx, rax
0x1400e4c43  lea     rcx, [rbp+57h+SystemInformation]
0x1400e4c47  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1400e4c4c  lea     rcx, [rbp+57h+lpJobObjectInformation]
0x1400e4c50  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400e4c55  mov     esi, 5
0x1400e4c5a  jmp     short loc_1400E4C9F
0x1400e4c5c  mov     r9d, eax
0x1400e4c5f  bts     r9d, 1Ch; char *
0x1400e4c64  mov     rcx, [rbp+5Fh]; this
0x1400e4c68  cmp     eax, 0C0000004h
0x1400e4c6d  jnz     short loc_1400E4CD7
0x1400e4c6f  cmp     [rbp+57h+ReturnLength], edi
0x1400e4c72  jbe     short loc_1400E4C79
0x1400e4c74  mov     edi, [rbp+57h+ReturnLength]
0x1400e4c77  jmp     short loc_1400E4C7F
0x1400e4c79  add     edi, 1000h
0x1400e4c7f  mov     edx, edi
0x1400e4c81  lea     rcx, [rbp+57h+lpJobObjectInformation]
0x1400e4c85  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1400e4c8a  mov     rdx, rax
0x1400e4c8d  lea     rcx, [rbp+57h+SystemInformation]
0x1400e4c91  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1400e4c96  lea     rcx, [rbp+57h+lpJobObjectInformation]
0x1400e4c9a  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400e4c9f  mov     rbx, [rbp+57h+SystemInformation]
0x1400e4ca3  mov     [rbp+57h+ReturnLength], 0
0x1400e4caa  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1400e4cae  mov     r8d, edi; SystemInformationLength
0x1400e4cb1  mov     rdx, rbx; SystemInformation
0x1400e4cb4  mov     ecx, esi; SystemInformationClass
0x1400e4cb6  call    cs:__imp_NtQuerySystemInformation
0x1400e4cbd  nop     dword ptr [rax+rax+00h]
0x1400e4cc2  test    eax, eax
0x1400e4cc4  js      short loc_1400E4C5C
0x1400e4cc6  mov     [rbp+57h+lpJobObjectInformation], 0
0x1400e4cce  mov     edi, 400h
0x1400e4cd3  mov     edx, edi
0x1400e4cd5  jmp     short loc_1400E4D0F
0x1400e4cd7  lea     r8, aOnecoreVmCompu_76; "onecore\\vm\\compute\\management\\share"...
0x1400e4cde  mov     edx, 43h ; 'C'; void *
0x1400e4ce3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e4ce9  mov     rdi, [rbp+5Fh]
0x1400e4ced  call    cs:__imp_GetLastError
0x1400e4cf4  nop     dword ptr [rax+rax+00h]
0x1400e4cf9  cmp     eax, 0EAh
0x1400e4cfe  jnz     loc_1400E4EDC
0x1400e4d04  mov     eax, [rsi]
0x1400e4d06  lea     edi, ds:8[rax*8]
0x1400e4d0d  mov     edx, edi
0x1400e4d0f  lea     rcx, [rbp+57h+var_80]
0x1400e4d13  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1400e4d18  mov     rdx, rax
0x1400e4d1b  lea     rcx, [rbp+57h+lpJobObjectInformation]
0x1400e4d1f  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1400e4d24  lea     rcx, [rbp+57h+var_80]
0x1400e4d28  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400e4d2d  mov     rsi, [rbp+57h+lpJobObjectInformation]
0x1400e4d31  mov     qword ptr [rsp+0D0h+lpReturnLength], 0; lpReturnLength
0x1400e4d3a  mov     r9d, edi; cbJobObjectInformationLength
0x1400e4d3d  mov     r8, rsi; lpJobObjectInformation
0x1400e4d40  mov     edx, 3; JobObjectInformationClass
0x1400e4d45  mov     rcx, r15; hJob
0x1400e4d48  call    cs:__imp_QueryInformationJobObject
0x1400e4d4f  nop     dword ptr [rax+rax+00h]
0x1400e4d54  test    eax, eax
0x1400e4d56  jz      short loc_1400E4CE9
0x1400e4d58  xorps   xmm0, xmm0
0x1400e4d5b  movups  [rbp+57h+var_60], xmm0
0x1400e4d5f  lea     rcx, [rbp+57h+var_60]
0x1400e4d63  call    ??0?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@QEAA@XZ; std::set<uint>::set<uint>(void)
0x1400e4d68  nop
0x1400e4d69  xor     edi, edi
0x1400e4d6b  cmp     [rsi+4], edi
0x1400e4d6e  jbe     short loc_1400E4D8F
0x1400e4d70  mov     ecx, [rsi+rdi*8+8]
0x1400e4d74  mov     dword ptr [rbp+57h+var_80], ecx
0x1400e4d77  lea     r8, [rbp+57h+var_80]
0x1400e4d7b  lea     rdx, [rbp+57h+var_A0]
0x1400e4d7f  lea     rcx, [rbp+57h+var_60]
0x1400e4d83  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@$$QEAK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<0,0>(ulong &&)
0x1400e4d88  inc     edi
0x1400e4d8a  cmp     edi, [rsi+4]
0x1400e4d8d  jb      short loc_1400E4D70
0x1400e4d8f  xor     edi, edi
0x1400e4d91  mov     esi, edi
0x1400e4d93  add     rsi, rbx
0x1400e4d96  mov     r10d, [rsi+50h]
0x1400e4d9a  mov     dword ptr [rbp+57h+var_80], r10d
0x1400e4d9e  lea     r8, [rbp+57h+var_80]
0x1400e4da2  lea     rdx, [rbp+57h+var_A0]
0x1400e4da6  lea     rcx, [rbp+57h+var_60]
0x1400e4daa  call    ??$_Find_lower_bound@K@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@KPEAX@std@@@1@AEBK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::_Find_lower_bound<ulong>(ulong const &)
0x1400e4daf  mov     rax, [rbp+57h+var_90]
0x1400e4db3  cmp     byte ptr [rax+19h], 0
0x1400e4db7  jnz     short loc_1400E4DBF
0x1400e4db9  cmp     r10d, [rax+1Ch]
0x1400e4dbd  jnb     short loc_1400E4DC3
0x1400e4dbf  mov     rax, qword ptr [rbp+57h+var_60]
0x1400e4dc3  cmp     rax, qword ptr [rbp+57h+var_60]
0x1400e4dc7  jz      loc_1400E4E5B
0x1400e4dcd  mov     r8d, r10d; dwProcessId
0x1400e4dd0  xor     edx, edx; bInheritHandle
0x1400e4dd2  mov     ecx, 1000h; dwDesiredAccess
0x1400e4dd7  call    cs:__imp_OpenProcess
0x1400e4dde  nop     dword ptr [rax+rax+00h]
0x1400e4de3  mov     [rbp+57h+var_A0], rax
0x1400e4de7  lea     rcx, [rax-1]
0x1400e4deb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400e4def  ja      short loc_1400E4E52
0x1400e4df1  xorps   xmm0, xmm0
0x1400e4df4  movups  [rbp+57h+ProcessInformation], xmm0
0x1400e4df8  movups  [rbp+57h+var_40], xmm0
0x1400e4dfc  mov     qword ptr [rsp+0D0h+lpReturnLength], 0; ReturnLength
0x1400e4e05  mov     r9d, 20h ; ' '; ProcessInformationLength
0x1400e4e0b  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x1400e4e0f  lea     edx, [r9-1Ch]; ProcessInformationClass
0x1400e4e13  mov     rcx, rax; ProcessHandle
0x1400e4e16  call    cs:__imp_NtQueryInformationProcess
0x1400e4e1d  nop     dword ptr [rax+rax+00h]
0x1400e4e22  test    eax, eax
0x1400e4e24  js      short loc_1400E4E52
0x1400e4e26  mov     rax, [rsi+20h]
0x1400e4e2a  cmp     qword ptr [rbp+57h+ProcessInformation], rax
0x1400e4e2e  jnz     short loc_1400E4E52
0x1400e4e30  mov     [rbp+57h+var_80], rsi
0x1400e4e34  mov     rcx, [r14+38h]
0x1400e4e38  test    rcx, rcx
0x1400e4e3b  jz      loc_1400E4EF1
0x1400e4e41  mov     rax, [rcx]
0x1400e4e44  lea     rdx, [rbp+57h+var_80]
0x1400e4e48  mov     rax, [rax+10h]
0x1400e4e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e4e51  nop
0x1400e4e52  lea     rcx, [rbp+57h+var_A0]; void *
0x1400e4e56  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400e4e5b  cmp     dword ptr [rsi], 0
0x1400e4e5e  jz      short loc_1400E4E77
0x1400e4e60  add     edi, [rsi]
0x1400e4e62  mov     ecx, edi
0x1400e4e64  add     rcx, 100h
0x1400e4e6b  mov     eax, [rbp+57h+ReturnLength]
0x1400e4e6e  cmp     rcx, rax
0x1400e4e71  jbe     loc_1400E4D91
0x1400e4e77  lea     rcx, [rbp+57h+var_60]
0x1400e4e7b  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x1400e4e80  nop
0x1400e4e81  lea     rcx, [rbp+57h+lpJobObjectInformation]
0x1400e4e85  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400e4e8a  nop
0x1400e4e8b  lea     rcx, [rbp+57h+SystemInformation]
0x1400e4e8f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400e4e94  nop
0x1400e4e95  mov     rcx, [r14+38h]
0x1400e4e99  test    rcx, rcx
0x1400e4e9c  jz      short loc_1400E4EB8
0x1400e4e9e  mov     rax, [rcx]
0x1400e4ea1  cmp     rcx, r14
0x1400e4ea4  setnz   dl
0x1400e4ea7  mov     rax, [rax+20h]
0x1400e4eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e4eb0  mov     qword ptr [r14+38h], 0
0x1400e4eb8  mov     rcx, [rbp+57h+var_30]
0x1400e4ebc  xor     rcx, rsp; StackCookie
0x1400e4ebf  call    __security_check_cookie
0x1400e4ec4  mov     rbx, [rsp+0D0h+arg_10]
0x1400e4ecc  add     rsp, 0B0h
0x1400e4ed3  pop     r15
0x1400e4ed5  pop     r14
0x1400e4ed7  pop     rdi
0x1400e4ed8  pop     rsi
0x1400e4ed9  pop     rbp
0x1400e4eda  retn
0x1400e4edc  lea     r8, aOnecoreVmCompu_76; "onecore\\vm\\compute\\management\\share"...
0x1400e4ee3  mov     edx, 57h ; 'W'; void *
0x1400e4ee8  mov     rcx, rdi; this
0x1400e4eeb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e4ef1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1400e4ef8  nop     dword ptr [rax+rax+00h]
0x1400e4efd  int     3; Trap to Debugger
```
