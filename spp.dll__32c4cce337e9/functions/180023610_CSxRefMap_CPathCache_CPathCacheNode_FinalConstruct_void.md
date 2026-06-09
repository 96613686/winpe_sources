# CSxRefMap<CPathCache,CPathCacheNode>::FinalConstruct(void)

- ea: `0x180023610`
- end: `0x1800236b0`
- name: `?FinalConstruct@?$CSxRefMap@VCPathCache@@VCPathCacheNode@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800233d8`

## callees

- `0x18000e104`
- `0x180023610`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18002369d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18002369d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180023649`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180023649`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023636`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023669`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CPathCache,CPathCacheNode>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CFileDescriptorEntry *v3; // rbx
  CFileDescriptorEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CFileDescriptorEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CFileDescriptorEntry::Release(v3);
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
0x180023610  mov     [rsp+arg_0], rbx
0x180023615  push    rdi
0x180023616  sub     rsp, 30h
0x18002361a  mov     rdi, rcx
0x18002361d  lock inc dword ptr [rcx+8]
0x180023621  cmp     qword ptr [rcx], 0
0x180023625  jz      short loc_180023664
0x180023627  lock inc dword ptr [rcx+8]
0x18002362b  mov     rcx, [rcx]
0x18002362e  jmp     short loc_180023647
0x180023630  mov     rbx, [rax]
0x180023633  mov     rdx, rax; Buffer
0x180023636  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002363c  mov     rcx, rbx; this
0x18002363f  call    ?Release@CFileDescriptorEntry@@QEAAKXZ; CFileDescriptorEntry::Release(void)
0x180023644  mov     rcx, [rdi]; Table
0x180023647  mov     dl, 1; Restart
0x180023649  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18002364f  mov     rcx, [rdi]; pv
0x180023652  test    rax, rax
0x180023655  jnz     short loc_180023630
0x180023657  call    cs:__imp_CoTaskMemFree
0x18002365d  mov     qword ptr [rdi], 0
0x180023664  mov     ecx, 68h ; 'h'; cb
0x180023669  call    cs:__imp_CoTaskMemAlloc
0x18002366f  mov     [rdi], rax
0x180023672  test    rax, rax
0x180023675  jnz     short loc_18002367E
0x180023677  mov     ebx, 8007000Eh
0x18002367c  jmp     short loc_1800236A3
0x18002367e  xor     ebx, ebx
0x180023680  mov     [rsp+38h+TableContext], rdi; TableContext
0x180023685  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18002368c  mov     rcx, rax; Table
0x18002368f  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180023696  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18002369d  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800236a3  mov     eax, ebx
0x1800236a5  mov     rbx, [rsp+38h+arg_0]
0x1800236aa  add     rsp, 30h
0x1800236ae  pop     rdi
0x1800236af  retn
```
