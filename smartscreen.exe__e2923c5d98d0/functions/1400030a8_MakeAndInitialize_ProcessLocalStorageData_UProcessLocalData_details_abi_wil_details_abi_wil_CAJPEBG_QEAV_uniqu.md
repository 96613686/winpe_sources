# ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z

- ea: `0x1400030a8`
- end: `0x14000324f`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z`
- size: `423`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140001e30`

## callees

- `0x1400029d8`
- `0x140002c8c`
- `0x1400030a8`
- `0x1400047dc`
- `0x140016ce4`
- `0x14001e730`
- `0x14002e5c0`
- `0x140062c80`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003112`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003112`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400030fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400030fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400030c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400030c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400030d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400030d9`

## string_xrefs

- `0x1400030f6`: `ntdll.dll`

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
0x1400030a8  push    rbx
0x1400030aa  push    rsi
0x1400030ab  push    rdi
0x1400030ac  push    r14
0x1400030ae  push    r15
0x1400030b0  sub     rsp, 30h
0x1400030b4  mov     r15, r8
0x1400030b7  mov     r14, rdx
0x1400030ba  mov     rsi, rcx
0x1400030bd  mov     qword ptr [r8], 0
0x1400030c4  call    cs:__imp_GetProcessHeap
0x1400030ca  mov     rdi, rax
0x1400030cd  mov     edx, 8; dwFlags
0x1400030d2  lea     r8d, [rdx+70h]; dwBytes
0x1400030d6  mov     rcx, rax; hHeap
0x1400030d9  call    cs:__imp_HeapAlloc
0x1400030df  mov     rbx, rax
0x1400030e2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400030e9  test    rax, rax
0x1400030ec  jnz     short loc_140003134
0x1400030ee  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400030f4  jnz     short loc_140003140
0x1400030f6  lea     rcx, ModuleName; "ntdll.dll"
0x1400030fd  call    cs:__imp_GetModuleHandleW
0x140003103  test    rax, rax
0x140003106  jz      short loc_140003121
0x140003108  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x14000310f  mov     rcx, rax; hModule
0x140003112  call    cs:__imp_GetProcAddress
0x140003118  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000311f  jmp     short loc_140003128
0x140003121  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003128  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000312f  test    rax, rax
0x140003132  jz      short loc_140003140
0x140003134  mov     rdx, rbx
0x140003137  mov     rcx, rdi
0x14000313a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000313f  nop
0x140003140  test    rbx, rbx
0x140003143  jnz     short loc_14000316A
0x140003145  mov     rcx, [rsp+58h]; this
0x14000314a  mov     ebx, 8007000Eh
0x14000314f  mov     r9d, ebx; char *
0x140003152  lea     r8, aWil; "wil"
0x140003159  mov     edx, 14Bh; void *
0x14000315e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003163  mov     eax, ebx
0x140003165  jmp     loc_140003243
0x14000316a  xorps   xmm0, xmm0
0x14000316d  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x140003173  test    bl, 3
0x140003176  jz      short loc_14000317E
0x140003178  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000317e  mov     r9, rbx
0x140003181  shr     r9, 2; unsigned __int64
0x140003185  mov     rdx, rsi; unsigned __int16 *
0x140003188  lea     rcx, [rsp+58h+var_38]; this
0x14000318d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003192  mov     edi, eax
0x140003194  test    eax, eax
0x140003196  jns     short loc_1400031D1
0x140003198  mov     rcx, [rsp+58h]; this
0x14000319d  mov     r9d, eax; char *
0x1400031a0  lea     r8, aWil; "wil"
0x1400031a7  mov     edx, 14Eh; void *
0x1400031ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031b1  lea     rcx, [rsp+58h+var_38+8]
0x1400031b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400031bb  lea     rcx, [rsp+58h+var_38]
0x1400031c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400031c5  mov     rcx, rbx; this
0x1400031c8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400031cd  mov     eax, edi
0x1400031cf  jmp     short loc_140003243
0x1400031d1  mov     dword ptr [rbx], 1
0x1400031d7  mov     rax, [r14]
0x1400031da  mov     [rbx+8], rax
0x1400031de  mov     qword ptr [r14], 0
0x1400031e5  mov     rax, qword ptr [rsp+58h+var_38]
0x1400031ea  mov     [rbx+10h], rax
0x1400031ee  mov     qword ptr [rsp+58h+var_38], 0
0x1400031f7  mov     rax, qword ptr [rsp+58h+var_38+8]
0x1400031fc  mov     [rbx+18h], rax
0x140003200  mov     qword ptr [rsp+58h+var_38+8], 0
0x140003209  lea     rcx, [rbx+22h]; void *
0x14000320d  xor     edx, edx; Val
0x14000320f  lea     r8d, [rdx+56h]; Size
0x140003213  call    memset
0x140003218  mov     word ptr [rbx+20h], 58h ; 'X'
0x14000321e  mov     dword ptr [rbx+24h], 1
0x140003225  lea     rcx, [rbx+28h]; void *
0x140003229  xor     edx, edx; Val
0x14000322b  lea     r8d, [rdx+50h]; Size
0x14000322f  call    memset
0x140003234  mov     [r15], rbx
0x140003237  lea     rcx, [rsp+58h+var_38]; this
0x14000323c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140003241  xor     eax, eax
0x140003243  add     rsp, 30h
0x140003247  pop     r15
0x140003249  pop     r14
0x14000324b  pop     rdi
0x14000324c  pop     rsi
0x14000324d  pop     rbx
0x14000324e  retn
```
