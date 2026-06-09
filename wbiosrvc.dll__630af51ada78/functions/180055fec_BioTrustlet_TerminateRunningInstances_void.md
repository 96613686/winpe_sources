# BioTrustlet::TerminateRunningInstances(void)

- ea: `0x180055fec`
- end: `0x180056351`
- name: `?TerminateRunningInstances@BioTrustlet@@AEAAJXZ`
- size: `869`
- prototype: `__int64 __fastcall(BioTrustlet *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056378`

## callees

- `0x180011d90`
- `0x180014894`
- `0x180052f44`
- `0x1800538b0`
- `0x1800549a0`
- `0x180055fec`
- `0x180056358`
- `0x180068f60`
- `0x180069cc8`
- `0x1800b4c64`
- `0x1800b4e1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056233`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056233`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056292`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056292`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180056249`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180056249`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800561d0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800561d0`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180056068`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180056068`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180056214`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180056214`

## string_xrefs

- `0x18005607a`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x18005612a`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x18005625b`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x1800562a7`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x180056302`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BioTrustlet::TerminateRunningInstances(BioTrustlet *this)
{
  unsigned __int64 v2; // rbx
  const char *v3; // r9
  unsigned int LastError; // ebx
  const char *v5; // r9
  __int64 result; // rax
  unsigned __int64 v7; // rdi
  DWORD *v8; // rsi
  unsigned __int64 v9; // rcx
  DWORD *v10; // rax
  size_t v11; // rbx
  unsigned int v12; // ebx
  DWORD *v13; // rdi
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  size_t v16; // rbx
  DWORD *i; // rsi
  char *v18; // rbx
  __int64 v19; // rax
  const char *v20; // r9
  unsigned int v21; // ebx
  DWORD v22; // eax
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  DWORD cbNeeded; // [rsp+20h] [rbp-268h] BYREF
  DWORD *lpidProcess[2]; // [rsp+28h] [rbp-260h] BYREF
  __int64 v27; // [rsp+38h] [rbp-250h]
  _QWORD v28[2]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR ExeName[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  try
  {
    LODWORD(v7) = 500;
    *(_OWORD *)lpidProcess = 0;
    v27 = 0;
    std::vector<unsigned long>::_Construct_n<>(lpidProcess, 500);
    while ( 1 )
    {
      v2 = 4LL * (unsigned int)v7;
      if ( v2 > 0xFFFFFFFF )
      {
        v24 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x3BC,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                (const char *)0xC0000095LL,
                cbNeeded);
        std::vector<unsigned int>::_Tidy(lpidProcess);
        return v24;
      }
      cbNeeded = 0;
      if ( !K32EnumProcesses(lpidProcess[0], v2, &cbNeeded) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3C3,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                      v3);
        std::vector<unsigned int>::_Tidy(lpidProcess);
        return LastError;
      }
      if ( cbNeeded < (unsigned int)v2 )
        break;
      v7 = 2LL * (unsigned int)v7;
      if ( v7 > 0xFFFFFFFF )
      {
        v12 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x3CC,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                (const char *)0xC0000095LL,
                cbNeeded);
        std::vector<unsigned int>::_Tidy(lpidProcess);
        return v12;
      }
      v8 = lpidProcess[1];
      v9 = lpidProcess[1] - lpidProcess[0];
      if ( (unsigned int)v7 < v9 )
      {
        v10 = &lpidProcess[0][(unsigned int)v7];
        goto LABEL_13;
      }
      if ( (unsigned int)v7 > v9 )
      {
        if ( (unsigned int)v7 <= (unsigned __int64)((signed __int64)(v27 - (unsigned __int64)lpidProcess[0]) >> 2) )
        {
          v11 = (unsigned int)v7 - v9;
          memset_0(lpidProcess[1], 0, v11 * 4);
          v10 = &v8[v11];
LABEL_13:
          lpidProcess[1] = v10;
        }
        else
        {
          std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(lpidProcess, (unsigned int)v7);
        }
      }
    }
    v13 = lpidProcess[1];
    v14 = lpidProcess[1] - lpidProcess[0];
    v15 = (unsigned __int64)cbNeeded >> 2;
    if ( v15 < v14 )
    {
      v13 = &lpidProcess[0][v15];
      goto LABEL_21;
    }
    if ( v15 > v14 )
    {
      if ( v15 <= (signed __int64)(v27 - (unsigned __int64)lpidProcess[0]) >> 2 )
      {
        v16 = 4 * (v15 - v14);
        memset_0(lpidProcess[1], 0, v16);
        v13 = (DWORD *)((char *)v13 + v16);
LABEL_21:
        lpidProcess[1] = v13;
      }
      else
      {
        std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(
          lpidProcess,
          (unsigned __int64)cbNeeded >> 2);
        v13 = lpidProcess[1];
      }
    }
    for ( i = lpidProcess[0]; i != v13; ++i )
    {
      v18 = (char *)OpenProcess(0x101001u, 0, *i);
      v28[0] = v18;
      if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        memset_0(ExeName, 0, 0x208u);
        cbNeeded = 260;
        if ( QueryFullProcessImageNameW(v18, 0, ExeName, &cbNeeded) )
        {
          v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8);
          if ( !(unsigned int)_o__wcsicmp(v19, ExeName) )
          {
            if ( !TerminateProcess(v18, 0xC0000001) )
            {
              v21 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3FA,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                      v20);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v28);
              std::vector<unsigned int>::_Tidy(lpidProcess);
              return v21;
            }
            v22 = WaitForSingleObject(v18, 0x3E8u);
            if ( v22 )
            {
              v23 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x3FF,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                      (const char *)v22,
                      cbNeeded);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v28);
              std::vector<unsigned int>::_Tidy(lpidProcess);
              return v23;
            }
          }
        }
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v28);
    }
    std::vector<unsigned int>::_Tidy(lpidProcess);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x404,
                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180055fec  mov     [rsp+arg_8], rbx
0x180055ff1  mov     [rsp+arg_10], rsi
0x180055ff6  push    rdi
0x180055ff7  push    r14
0x180055ff9  push    r15
0x180055ffb  sub     rsp, 270h
0x180056002  mov     rax, cs:__security_cookie
0x180056009  xor     rax, rsp
0x18005600c  mov     [rsp+288h+var_28], rax
0x180056014  mov     r14, rcx
0x180056017  mov     edi, 1F4h
0x18005601c  xorps   xmm0, xmm0
0x18005601f  movdqu  xmmword ptr [rsp+288h+lpidProcess], xmm0
0x180056025  mov     [rsp+288h+var_250], 0
0x18005602e  mov     edx, edi
0x180056030  lea     rcx, [rsp+288h+lpidProcess]
0x180056035  call    ??$_Construct_n@$$V@?$vector@KV?$allocator@K@std@@@std@@AEAAX_K@Z; std::vector<ulong>::_Construct_n<>(unsigned __int64)
0x18005603a  nop
0x18005603b  mov     r15d, 0FFFFFFFFh
0x180056041  mov     edi, edi
0x180056043  lea     rbx, ds:0[rdi*4]
0x18005604b  cmp     rbx, r15
0x18005604e  ja      loc_1800562F4
0x180056054  mov     [rsp+288h+cbNeeded], 0; int
0x18005605c  lea     r8, [rsp+288h+cbNeeded]; lpcbNeeded
0x180056061  mov     edx, ebx; cb
0x180056063  mov     rcx, [rsp+288h+lpidProcess]; lpidProcess
0x180056068  call    cs:__imp_K32EnumProcesses
0x18005606e  test    eax, eax
0x180056070  jnz     short loc_18005609E
0x180056072  mov     rcx, [rsp+288h]; this
0x18005607a  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180056081  mov     edx, 3C3h; void *
0x180056086  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005608b  mov     ebx, eax
0x18005608d  lea     rcx, [rsp+288h+lpidProcess]
0x180056092  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180056097  mov     eax, ebx
0x180056099  jmp     loc_180056327
0x18005609e  cmp     [rsp+288h+cbNeeded], ebx
0x1800560a2  jb      loc_18005614E
0x1800560a8  add     rdi, rdi
0x1800560ab  cmp     rdi, r15
0x1800560ae  ja      short loc_18005611C
0x1800560b0  mov     rdx, [rsp+288h+lpidProcess]
0x1800560b5  mov     rsi, [rsp+288h+lpidProcess+8]
0x1800560ba  mov     rcx, rsi
0x1800560bd  sub     rcx, rdx
0x1800560c0  sar     rcx, 2
0x1800560c4  mov     ebx, edi
0x1800560c6  cmp     rbx, rcx
0x1800560c9  jnb     short loc_1800560D1
0x1800560cb  lea     rax, [rdx+rbx*4]
0x1800560cf  jmp     short loc_180056112
0x1800560d1  jbe     loc_180056041
0x1800560d7  mov     rax, [rsp+288h+var_250]
0x1800560dc  sub     rax, rdx
0x1800560df  sar     rax, 2
0x1800560e3  cmp     rbx, rax
0x1800560e6  jbe     short loc_1800560FA
0x1800560e8  mov     rdx, rbx
0x1800560eb  lea     rcx, [rsp+288h+lpidProcess]
0x1800560f0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800560f5  jmp     loc_180056041
0x1800560fa  sub     rbx, rcx
0x1800560fd  shl     rbx, 2
0x180056101  mov     r8, rbx; Size
0x180056104  xor     edx, edx; Val
0x180056106  mov     rcx, rsi; void *
0x180056109  call    memset_0
0x18005610e  lea     rax, [rbx+rsi]
0x180056112  mov     [rsp+288h+lpidProcess+8], rax
0x180056117  jmp     loc_180056041
0x18005611c  mov     rcx, [rsp+288h]; this
0x180056124  mov     r9d, 0C0000095h; char *
0x18005612a  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180056131  mov     edx, 3CCh; void *
0x180056136  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005613b  mov     ebx, eax
0x18005613d  lea     rcx, [rsp+288h+lpidProcess]
0x180056142  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180056147  mov     eax, ebx
0x180056149  jmp     loc_180056327
0x18005614e  mov     rdx, [rsp+288h+lpidProcess]
0x180056153  mov     rdi, [rsp+288h+lpidProcess+8]
0x180056158  mov     rcx, rdi
0x18005615b  sub     rcx, rdx
0x18005615e  sar     rcx, 2
0x180056162  mov     ebx, [rsp+288h+cbNeeded]
0x180056166  shr     rbx, 2
0x18005616a  cmp     rbx, rcx
0x18005616d  jnb     short loc_180056175
0x18005616f  lea     rdi, [rdx+rbx*4]
0x180056173  jmp     short loc_1800561B3
0x180056175  jbe     short loc_1800561B8
0x180056177  mov     rax, [rsp+288h+var_250]
0x18005617c  sub     rax, rdx
0x18005617f  sar     rax, 2
0x180056183  cmp     rbx, rax
0x180056186  jbe     short loc_18005619C
0x180056188  mov     rdx, rbx
0x18005618b  lea     rcx, [rsp+288h+lpidProcess]
0x180056190  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180056195  mov     rdi, [rsp+288h+lpidProcess+8]
0x18005619a  jmp     short loc_1800561B8
0x18005619c  sub     rbx, rcx
0x18005619f  shl     rbx, 2
0x1800561a3  mov     r8, rbx; Size
0x1800561a6  xor     edx, edx; Val
0x1800561a8  mov     rcx, rdi; void *
0x1800561ab  call    memset_0
0x1800561b0  add     rdi, rbx
0x1800561b3  mov     [rsp+288h+lpidProcess+8], rdi
0x1800561b8  mov     rsi, [rsp+288h+lpidProcess]
0x1800561bd  cmp     rsi, rdi
0x1800561c0  jz      loc_1800562E6
0x1800561c6  mov     r8d, [rsi]; dwProcessId
0x1800561c9  xor     edx, edx; bInheritHandle
0x1800561cb  mov     ecx, 101001h; dwDesiredAccess
0x1800561d0  call    cs:__imp_OpenProcess
0x1800561d6  mov     rbx, rax
0x1800561d9  mov     [rsp+288h+var_248], rax
0x1800561de  dec     rax
0x1800561e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800561e5  ja      loc_1800562D3
0x1800561eb  xor     edx, edx; Val
0x1800561ed  mov     r8d, 208h; Size
0x1800561f3  lea     rcx, [rsp+288h+ExeName]; void *
0x1800561f8  call    memset_0
0x1800561fd  mov     [rsp+288h+cbNeeded], 104h; unsigned int
0x180056205  lea     r9, [rsp+288h+cbNeeded]; lpdwSize
0x18005620a  lea     r8, [rsp+288h+ExeName]; lpExeName
0x18005620f  xor     edx, edx; dwFlags
0x180056211  mov     rcx, rbx; hProcess
0x180056214  call    cs:__imp_QueryFullProcessImageNameW
0x18005621a  test    eax, eax
0x18005621c  jz      loc_1800562D3
0x180056222  lea     rcx, [r14+8]
0x180056226  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005622b  lea     rdx, [rsp+288h+ExeName]
0x180056230  mov     rcx, rax
0x180056233  call    cs:__imp__o__wcsicmp
0x180056239  test    eax, eax
0x18005623b  jnz     loc_1800562D3
0x180056241  mov     edx, 0C0000001h; uExitCode
0x180056246  mov     rcx, rbx; hProcess
0x180056249  call    cs:__imp_TerminateProcess
0x18005624f  test    eax, eax
0x180056251  jnz     short loc_18005628A
0x180056253  mov     rcx, [rsp+288h]; this
0x18005625b  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180056262  mov     edx, 3FAh; void *
0x180056267  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005626c  mov     ebx, eax
0x18005626e  lea     rcx, [rsp+288h+var_248]
0x180056273  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180056278  nop
0x180056279  lea     rcx, [rsp+288h+lpidProcess]
0x18005627e  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180056283  mov     eax, ebx
0x180056285  jmp     loc_180056327
0x18005628a  mov     edx, 3E8h; dwMilliseconds
0x18005628f  mov     rcx, rbx; hHandle
0x180056292  call    cs:__imp_WaitForSingleObject
0x180056298  test    eax, eax
0x18005629a  jz      short loc_1800562D3
0x18005629c  mov     rcx, [rsp+288h]; this
0x1800562a4  mov     r9d, eax; char *
0x1800562a7  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x1800562ae  mov     edx, 3FFh; void *
0x1800562b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800562b8  mov     ebx, eax
0x1800562ba  lea     rcx, [rsp+288h+var_248]
0x1800562bf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800562c4  nop
0x1800562c5  lea     rcx, [rsp+288h+lpidProcess]
0x1800562ca  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x1800562cf  mov     eax, ebx
0x1800562d1  jmp     short loc_180056327
0x1800562d3  lea     rcx, [rsp+288h+var_248]
0x1800562d8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800562dd  add     rsi, 4
0x1800562e1  jmp     loc_1800561BD
0x1800562e6  lea     rcx, [rsp+288h+lpidProcess]
0x1800562eb  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x1800562f0  xor     eax, eax
0x1800562f2  jmp     short loc_180056327
0x1800562f4  mov     rcx, [rsp+288h]; this
0x1800562fc  mov     r9d, 0C0000095h; char *
0x180056302  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180056309  mov     edx, 3BCh; void *
0x18005630e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180056313  mov     ebx, eax
0x180056315  lea     rcx, [rsp+288h+lpidProcess]
0x18005631a  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005631f  mov     eax, ebx
0x180056321  jmp     short loc_180056327
0x180056323  mov     eax, [rsp+288h+cbNeeded]
0x180056327  mov     rcx, [rsp+288h+var_28]
0x18005632f  xor     rcx, rsp; StackCookie
0x180056332  call    __security_check_cookie
0x180056337  lea     r11, [rsp+288h+var_18]
0x18005633f  mov     rbx, [r11+28h]
0x180056343  mov     rsi, [r11+30h]
0x180056347  mov     rsp, r11
0x18005634a  pop     r15
0x18005634c  pop     r14
0x18005634e  pop     rdi
0x18005634f  retn
```
