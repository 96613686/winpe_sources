# CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::FinalConstruct(void)

- ea: `0x1800088a4`
- end: `0x180008944`
- name: `?FinalConstruct@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007780`

## callees

- `0x1800088a4`
- `0x18000e4cc`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180008931`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180008931`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800088dd`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800088dd`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800088ca`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800088ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800088eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800088eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800088fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800088fd`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::FinalConstruct(
        volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeOnDiskPropCacheEntry *v3; // rbx
  CVolumeOnDiskPropCacheEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CVolumeOnDiskPropCacheEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CVolumeOnDiskPropCacheEntry::Release(v3);
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
      (PRTL_AVL_COMPARE_ROUTINE)CSxRefMap<CSxStringMap,CSxStringEntry>::_CompareRoutine,
      (PRTL_AVL_ALLOCATE_ROUTINE)CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::_AllocateRoutine,
      (PRTL_AVL_FREE_ROUTINE)CSxRefMap<CSppStringMap,CSppStringMapEntry>::_FreeRoutine,
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
0x1800088a4  mov     [rsp+arg_0], rbx
0x1800088a9  push    rdi
0x1800088aa  sub     rsp, 30h
0x1800088ae  mov     rdi, rcx
0x1800088b1  lock inc dword ptr [rcx+8]
0x1800088b5  cmp     qword ptr [rcx], 0
0x1800088b9  jz      short loc_1800088F8
0x1800088bb  lock inc dword ptr [rcx+8]
0x1800088bf  mov     rcx, [rcx]
0x1800088c2  jmp     short loc_1800088DB
0x1800088c4  mov     rbx, [rax]
0x1800088c7  mov     rdx, rax; Buffer
0x1800088ca  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800088d0  mov     rcx, rbx; this
0x1800088d3  call    ?Release@CVolumeOnDiskPropCacheEntry@@QEAAKXZ; CVolumeOnDiskPropCacheEntry::Release(void)
0x1800088d8  mov     rcx, [rdi]; Table
0x1800088db  mov     dl, 1; Restart
0x1800088dd  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800088e3  mov     rcx, [rdi]; pv
0x1800088e6  test    rax, rax
0x1800088e9  jnz     short loc_1800088C4
0x1800088eb  call    cs:__imp_CoTaskMemFree
0x1800088f1  mov     qword ptr [rdi], 0
0x1800088f8  mov     ecx, 68h ; 'h'; cb
0x1800088fd  call    cs:__imp_CoTaskMemAlloc
0x180008903  mov     [rdi], rax
0x180008906  test    rax, rax
0x180008909  jnz     short loc_180008912
0x18000890b  mov     ebx, 8007000Eh
0x180008910  jmp     short loc_180008937
0x180008912  xor     ebx, ebx
0x180008914  mov     [rsp+38h+TableContext], rdi; TableContext
0x180008919  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180008920  mov     rcx, rax; Table
0x180008923  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18000892a  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180008931  call    cs:__imp_RtlInitializeGenericTableAvl
0x180008937  mov     eax, ebx
0x180008939  mov     rbx, [rsp+38h+arg_0]
0x18000893e  add     rsp, 30h
0x180008942  pop     rdi
0x180008943  retn
```
