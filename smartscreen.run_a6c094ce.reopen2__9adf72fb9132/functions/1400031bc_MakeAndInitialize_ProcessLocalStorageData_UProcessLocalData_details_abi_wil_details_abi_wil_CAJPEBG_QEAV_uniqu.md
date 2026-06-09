# ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z

- ea: `0x1400031bc`
- end: `0x14000337c`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z`
- size: `448`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140001ef0`

## callees

- `0x140002af4`
- `0x140002d8c`
- `0x1400031bc`
- `0x140004a30`
- `0x1400184f0`
- `0x14001f804`
- `0x14002f7fc`
- `0x140064940`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003238`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003238`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000321d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000321d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400031d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400031d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400031f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400031f3`

## string_xrefs

- `0x140003216`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
        unsigned __int16 *a1,
        _QWORD *a2,
        unsigned __int64 *a3)
{
  HANDLE ProcessHeap; // rdi
  wil::details::in1diag3 *v7; // rcx
  unsigned __int64 v8; // rbx
  __int64 v9; // r8
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // eax
  unsigned int v14; // edi
  void *v15; // rdx
  int v16[4]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (unsigned __int64)HeapAlloc(ProcessHeap, 8u, 0x78u);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, unsigned __int64))ProcAddress)(ProcessHeap, v8);
  }
  if ( v8 )
  {
    *(_OWORD *)v16 = 0;
    if ( (v8 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v7);
    v13 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v16,
            a1,
            v9,
            v8 >> 2);
    v14 = v13;
    if ( v13 >= 0 )
    {
      *(_DWORD *)v8 = 1;
      *(_QWORD *)(v8 + 8) = *a2;
      *a2 = 0;
      *(_QWORD *)(v8 + 16) = *(_QWORD *)v16;
      *(_QWORD *)v16 = 0;
      *(_QWORD *)(v8 + 24) = *(_QWORD *)&v16[2];
      *(_QWORD *)&v16[2] = 0;
      memset((void *)(v8 + 34), 0, 0x56u);
      *(_WORD *)(v8 + 32) = 88;
      *(_DWORD *)(v8 + 36) = 1;
      memset((void *)(v8 + 40), 0, 0x50u);
      *a3 = v8;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v16);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16[0]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v16[2]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
      wil::details::FreeProcessHeap((wil::details *)v8, v15);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, v16[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1400031bc  push    rbx
0x1400031be  push    rsi
0x1400031bf  push    rdi
0x1400031c0  push    r14
0x1400031c2  push    r15
0x1400031c4  sub     rsp, 30h
0x1400031c8  mov     r15, r8
0x1400031cb  mov     r14, rdx
0x1400031ce  mov     rsi, rcx
0x1400031d1  mov     qword ptr [r8], 0
0x1400031d8  call    cs:__imp_GetProcessHeap
0x1400031df  nop     dword ptr [rax+rax+00h]
0x1400031e4  mov     rdi, rax
0x1400031e7  mov     edx, 8; dwFlags
0x1400031ec  lea     r8d, [rdx+70h]; dwBytes
0x1400031f0  mov     rcx, rax; hHeap
0x1400031f3  call    cs:__imp_HeapAlloc
0x1400031fa  nop     dword ptr [rax+rax+00h]
0x1400031ff  mov     rbx, rax
0x140003202  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003209  test    rax, rax
0x14000320c  jnz     short loc_140003260
0x14000320e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140003214  jnz     short loc_14000326C
0x140003216  lea     rcx, ModuleName; "ntdll.dll"
0x14000321d  call    cs:__imp_GetModuleHandleW
0x140003224  nop     dword ptr [rax+rax+00h]
0x140003229  test    rax, rax
0x14000322c  jz      short loc_14000324D
0x14000322e  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140003235  mov     rcx, rax; hModule
0x140003238  call    cs:__imp_GetProcAddress
0x14000323f  nop     dword ptr [rax+rax+00h]
0x140003244  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000324b  jmp     short loc_140003254
0x14000324d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003254  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000325b  test    rax, rax
0x14000325e  jz      short loc_14000326C
0x140003260  mov     rdx, rbx
0x140003263  mov     rcx, rdi
0x140003266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000326b  nop
0x14000326c  test    rbx, rbx
0x14000326f  jnz     short loc_140003296
0x140003271  mov     rcx, [rsp+58h]; this
0x140003276  mov     ebx, 8007000Eh
0x14000327b  mov     r9d, ebx; char *
0x14000327e  lea     r8, aWil; "wil"
0x140003285  mov     edx, 14Bh; void *
0x14000328a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000328f  mov     eax, ebx
0x140003291  jmp     loc_14000336F
0x140003296  xorps   xmm0, xmm0
0x140003299  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x14000329f  test    bl, 3
0x1400032a2  jz      short loc_1400032AA
0x1400032a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400032aa  mov     r9, rbx
0x1400032ad  shr     r9, 2; unsigned __int64
0x1400032b1  mov     rdx, rsi; unsigned __int16 *
0x1400032b4  lea     rcx, [rsp+58h+var_38]; this
0x1400032b9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400032be  mov     edi, eax
0x1400032c0  test    eax, eax
0x1400032c2  jns     short loc_1400032FD
0x1400032c4  mov     rcx, [rsp+58h]; this
0x1400032c9  mov     r9d, eax; char *
0x1400032cc  lea     r8, aWil; "wil"
0x1400032d3  mov     edx, 14Eh; void *
0x1400032d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400032dd  lea     rcx, [rsp+58h+var_38+8]
0x1400032e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400032e7  lea     rcx, [rsp+58h+var_38]
0x1400032ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400032f1  mov     rcx, rbx; this
0x1400032f4  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400032f9  mov     eax, edi
0x1400032fb  jmp     short loc_14000336F
0x1400032fd  mov     dword ptr [rbx], 1
0x140003303  mov     rax, [r14]
0x140003306  mov     [rbx+8], rax
0x14000330a  mov     qword ptr [r14], 0
0x140003311  mov     rax, qword ptr [rsp+58h+var_38]
0x140003316  mov     [rbx+10h], rax
0x14000331a  mov     qword ptr [rsp+58h+var_38], 0
0x140003323  mov     rax, qword ptr [rsp+58h+var_38+8]
0x140003328  mov     [rbx+18h], rax
0x14000332c  mov     qword ptr [rsp+58h+var_38+8], 0
0x140003335  lea     rcx, [rbx+22h]; void *
0x140003339  xor     edx, edx; Val
0x14000333b  lea     r8d, [rdx+56h]; Size
0x14000333f  call    memset
0x140003344  mov     word ptr [rbx+20h], 58h ; 'X'
0x14000334a  mov     dword ptr [rbx+24h], 1
0x140003351  lea     rcx, [rbx+28h]; void *
0x140003355  xor     edx, edx; Val
0x140003357  lea     r8d, [rdx+50h]; Size
0x14000335b  call    memset
0x140003360  mov     [r15], rbx
0x140003363  lea     rcx, [rsp+58h+var_38]; this
0x140003368  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14000336d  xor     eax, eax
0x14000336f  add     rsp, 30h
0x140003373  pop     r15
0x140003375  pop     r14
0x140003377  pop     rdi
0x140003378  pop     rsi
0x140003379  pop     rbx
0x14000337a  retn
```
