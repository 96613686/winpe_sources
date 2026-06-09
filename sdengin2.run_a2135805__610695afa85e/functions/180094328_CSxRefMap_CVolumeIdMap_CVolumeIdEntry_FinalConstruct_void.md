# CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::FinalConstruct(void)

- ea: `0x180094328`
- end: `0x1800943e7`
- name: `?FinalConstruct@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180094274`

## callees

- `0x180094328`
- `0x1800946b0`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800943cd`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800943cd`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180094367`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180094367`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18009434e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18009434e`
- `ole32!CoTaskMemFree` at `0x18009437b`
- `ole32!CoTaskMemFree` at `0x18009437b`
- `ole32!CoTaskMemAlloc` at `0x180094393`
- `ole32!CoTaskMemAlloc` at `0x180094393`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeIdEntry *v3; // rbx
  CVolumeIdEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CVolumeIdEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CVolumeIdEntry::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)TableContext = 0;
  }
  v6 = (struct _RTL_AVL_TABLE *)CoTaskMemAlloc(0x68u);
  *(_QWORD *)TableContext = v6;
  if ( v6 )
  {
    v7 = 0;
    RtlInitializeGenericTableAvl(
      v6,
      CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::_CompareRoutine,
      CSxRefMap<CSxDirRuleMap,CSxDirRule>::_AllocateRoutine,
      CSxRefMap<CSdMediaMapFinder,CSdMedia>::_FreeRoutine,
      (PVOID)TableContext);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180094328  mov     [rsp+arg_0], rbx
0x18009432d  push    rdi
0x18009432e  sub     rsp, 30h
0x180094332  mov     rdi, rcx
0x180094335  lock inc dword ptr [rcx+8]
0x180094339  cmp     qword ptr [rcx], 0
0x18009433d  jz      short loc_18009438E
0x18009433f  lock inc dword ptr [rcx+8]
0x180094343  mov     rcx, [rcx]
0x180094346  jmp     short loc_180094365
0x180094348  mov     rbx, [rax]
0x18009434b  mov     rdx, rax; Buffer
0x18009434e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180094355  nop     dword ptr [rax+rax+00h]
0x18009435a  mov     rcx, rbx; this
0x18009435d  call    ?Release@CVolumeIdEntry@@QEAAKXZ; CVolumeIdEntry::Release(void)
0x180094362  mov     rcx, [rdi]; Table
0x180094365  mov     dl, 1; Restart
0x180094367  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18009436e  nop     dword ptr [rax+rax+00h]
0x180094373  mov     rcx, [rdi]; pv
0x180094376  test    rax, rax
0x180094379  jnz     short loc_180094348
0x18009437b  call    cs:__imp_CoTaskMemFree
0x180094382  nop     dword ptr [rax+rax+00h]
0x180094387  mov     qword ptr [rdi], 0
0x18009438e  mov     ecx, 68h ; 'h'; cb
0x180094393  call    cs:__imp_CoTaskMemAlloc
0x18009439a  nop     dword ptr [rax+rax+00h]
0x18009439f  mov     [rdi], rax
0x1800943a2  test    rax, rax
0x1800943a5  jnz     short loc_1800943AE
0x1800943a7  mov     ebx, 8007000Eh
0x1800943ac  jmp     short loc_1800943D9
0x1800943ae  xor     ebx, ebx
0x1800943b0  mov     [rsp+38h+TableContext], rdi; TableContext
0x1800943b5  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800943bc  mov     rcx, rax; Table
0x1800943bf  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800943c6  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800943cd  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800943d4  nop     dword ptr [rax+rax+00h]
0x1800943d9  mov     eax, ebx
0x1800943db  mov     rbx, [rsp+38h+arg_0]
0x1800943e0  add     rsp, 30h
0x1800943e4  pop     rdi
0x1800943e5  retn
```
