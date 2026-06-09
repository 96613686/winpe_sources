# EasEngineUninitialize

- ea: `0x180069b08`
- end: `0x180069be7`
- name: `EasEngineUninitialize`
- size: `223`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011988`
- `0x180011d20`
- `0x18006eb70`
- `0x18006ecf0`

## callees

- `0x180069b08`
- `0x18006a608`
- `0x180078010`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180069b9b`
- `ntdll!RtlDeleteResource` at `0x180069b9b`
- `ntdll!RtlReleaseResource` at `0x180069bd9`
- `ntdll!RtlReleaseResource` at `0x180069bd9`
- `ntdll!RtlAcquireResourceExclusive` at `0x180069b17`
- `ntdll!RtlAcquireResourceExclusive` at `0x180069b17`

## string_xrefs

- `0x180069b3a`: `onecore\ds\security\eas\policyengine\initialize.cpp`

## pseudocode

```c
__int64 EasEngineUninitialize()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx

  RtlAcquireResourceExclusive(&g_lockObject, 1u);
  v0 = g_dwRefCount;
  v1 = 0;
  if ( g_dwRefCount )
  {
    --g_dwRefCount;
    if ( v0 == 1 )
    {
      g_bInitialized = 0;
      if ( g_Uninitialize )
      {
        g_Uninitialize();
        g_Uninitialize = 0;
      }
      RtlDeleteResource(&g_EvalLock);
      if ( qword_1800A2330 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800A2330 + 80LL))(qword_1800A2330, 1);
        qword_1800A2330 = 0;
      }
      g_bProvInitialized = 0;
      g_pFnLog = 0;
    }
  }
  else
  {
    v1 = -2147483611;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      2147483685LL,
      L"onecore\\ds\\security\\eas\\policyengine\\initialize.cpp",
      116,
      L"Extra EasEngineUninitialize call",
      &Class);
  }
  RtlReleaseResource(&g_lockObject);
  return v1;
}

```

## disassembly

```asm
0x180069b08  push    rbx
0x180069b0a  sub     rsp, 40h
0x180069b0e  mov     dl, 1; Wait
0x180069b10  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x180069b17  call    cs:__imp_RtlAcquireResourceExclusive
0x180069b1d  mov     eax, cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180069b23  xor     ebx, ebx
0x180069b25  test    eax, eax
0x180069b27  jnz     short loc_180069B6B
0x180069b29  lea     rax, Class
0x180069b30  mov     ebx, 80000025h
0x180069b35  mov     [rsp+48h+var_18], rax
0x180069b3a  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x180069b41  lea     rax, aExtraEasengine; "Extra EasEngineUninitialize call"
0x180069b48  mov     r8d, ebx
0x180069b4b  mov     [rsp+48h+var_20], rax
0x180069b50  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180069b57  mov     ecx, 1; unsigned int
0x180069b5c  mov     [rsp+48h+var_28], 74h ; 't'
0x180069b64  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180069b69  jmp     short loc_180069BD2
0x180069b6b  add     eax, 0FFFFFFFFh
0x180069b6e  mov     cs:?g_dwRefCount@@3KA, eax; ulong g_dwRefCount
0x180069b74  jnz     short loc_180069BD2
0x180069b76  mov     rax, cs:?g_Uninitialize@@3P6AXXZEA; void (*g_Uninitialize)(void)
0x180069b7d  mov     cs:?g_bInitialized@@3HA, ebx; int g_bInitialized
0x180069b83  test    rax, rax
0x180069b86  jz      short loc_180069B94
0x180069b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b8d  mov     cs:?g_Uninitialize@@3P6AXXZEA, rbx; void (*g_Uninitialize)(void)
0x180069b94  lea     rcx, ?g_EvalLock@@3U_RTL_RESOURCE@@A; Resource
0x180069b9b  call    cs:__imp_RtlDeleteResource
0x180069ba1  mov     rcx, cs:qword_1800A2330
0x180069ba8  test    rcx, rcx
0x180069bab  jz      short loc_180069BC5
0x180069bad  mov     rax, [rcx]
0x180069bb0  mov     edx, 1
0x180069bb5  mov     rax, [rax+50h]
0x180069bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bbe  mov     cs:qword_1800A2330, rbx
0x180069bc5  mov     cs:?g_bProvInitialized@@3HA, ebx; int g_bProvInitialized
0x180069bcb  mov     cs:?g_pFnLog@@3P6AXKPEAG@ZEA, rbx; void (*g_pFnLog)(ulong,ushort *)
0x180069bd2  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x180069bd9  call    cs:__imp_RtlReleaseResource
0x180069bdf  mov     eax, ebx
0x180069be1  add     rsp, 40h
0x180069be5  pop     rbx
0x180069be6  retn
```
