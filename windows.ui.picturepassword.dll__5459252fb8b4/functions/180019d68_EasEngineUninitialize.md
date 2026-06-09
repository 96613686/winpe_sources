# EasEngineUninitialize

- ea: `0x180019d68`
- end: `0x180019e35`
- name: `EasEngineUninitialize`
- size: `205`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016740`

## callees

- `0x180019d68`
- `0x18001a154`
- `0x18001a204`
- `0x18001f010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180019e27`
- `ntdll!RtlReleaseResource` at `0x180019e27`
- `ntdll!RtlDeleteResource` at `0x180019dfb`
- `ntdll!RtlDeleteResource` at `0x180019dfb`
- `ntdll!RtlAcquireResourceExclusive` at `0x180019d77`
- `ntdll!RtlAcquireResourceExclusive` at `0x180019d77`

## string_xrefs

- `0x180019d9a`: `onecore\ds\security\eas\policyengine\initialize.cpp`

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
      if ( qword_18002D630 )
      {
        EncryptHandle::DestroyEncryptHandle(qword_18002D630);
        qword_18002D630 = 0;
      }
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
      &pszPassword);
  }
  RtlReleaseResource(&g_lockObject);
  return v1;
}

```

## disassembly

```asm
0x180019d68  push    rbx
0x180019d6a  sub     rsp, 40h
0x180019d6e  mov     dl, 1; Wait
0x180019d70  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x180019d77  call    cs:__imp_RtlAcquireResourceExclusive
0x180019d7d  mov     eax, cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180019d83  xor     ebx, ebx
0x180019d85  test    eax, eax
0x180019d87  jnz     short loc_180019DCB
0x180019d89  lea     rax, pszPassword
0x180019d90  mov     ebx, 80000025h
0x180019d95  mov     [rsp+48h+var_18], rax
0x180019d9a  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180019da1  lea     rax, aExtraEasengine; "Extra EasEngineUninitialize call"
0x180019da8  mov     r8d, ebx
0x180019dab  mov     [rsp+48h+var_20], rax
0x180019db0  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180019db7  mov     ecx, 1; unsigned int
0x180019dbc  mov     [rsp+48h+var_28], 74h ; 't'
0x180019dc4  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180019dc9  jmp     short loc_180019E20
0x180019dcb  add     eax, 0FFFFFFFFh
0x180019dce  mov     cs:?g_dwRefCount@@3KA, eax; ulong g_dwRefCount
0x180019dd4  jnz     short loc_180019E20
0x180019dd6  mov     rax, cs:?g_Uninitialize@@3P6AXXZEA; void (*g_Uninitialize)(void)
0x180019ddd  mov     cs:?g_bInitialized@@3HA, ebx; int g_bInitialized
0x180019de3  test    rax, rax
0x180019de6  jz      short loc_180019DF4
0x180019de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ded  mov     cs:?g_Uninitialize@@3P6AXXZEA, rbx; void (*g_Uninitialize)(void)
0x180019df4  lea     rcx, ?g_EvalLock@@3U_RTL_RESOURCE@@A; Resource
0x180019dfb  call    cs:__imp_RtlDeleteResource
0x180019e01  mov     rcx, cs:qword_18002D630; struct EncryptHandle *
0x180019e08  test    rcx, rcx
0x180019e0b  jz      short loc_180019E19
0x180019e0d  call    ?DestroyEncryptHandle@EncryptHandle@@SAXPEAV1@@Z; EncryptHandle::DestroyEncryptHandle(EncryptHandle *)
0x180019e12  mov     cs:qword_18002D630, rbx
0x180019e19  mov     cs:?g_pFnLog@@3P6AXKPEAG@ZEA, rbx; void (*g_pFnLog)(ulong,ushort *)
0x180019e20  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; Resource
0x180019e27  call    cs:__imp_RtlReleaseResource
0x180019e2d  mov     eax, ebx
0x180019e2f  add     rsp, 40h
0x180019e33  pop     rbx
0x180019e34  retn
```
