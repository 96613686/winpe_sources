# CSxRefMap<CWriterEntryMap,CWriterEntry>::FinalConstruct(void)

- ea: `0x18000894c`
- end: `0x1800089ec`
- name: `?FinalConstruct@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007884`

## callees

- `0x18000894c`
- `0x18000e54c`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800089d9`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800089d9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180008985`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180008985`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180008972`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180008972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089a5`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CWriterEntryMap,CWriterEntry>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CWriterEntry *v3; // rbx
  CWriterEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CWriterEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CWriterEntry::Release(v3);
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
      (PRTL_AVL_COMPARE_ROUTINE)CSxRefMap<CWriterEntryMap,CWriterEntry>::_CompareRoutine,
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
0x18000894c  mov     [rsp+arg_0], rbx
0x180008951  push    rdi
0x180008952  sub     rsp, 30h
0x180008956  mov     rdi, rcx
0x180008959  lock inc dword ptr [rcx+8]
0x18000895d  cmp     qword ptr [rcx], 0
0x180008961  jz      short loc_1800089A0
0x180008963  lock inc dword ptr [rcx+8]
0x180008967  mov     rcx, [rcx]
0x18000896a  jmp     short loc_180008983
0x18000896c  mov     rbx, [rax]
0x18000896f  mov     rdx, rax; Buffer
0x180008972  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180008978  mov     rcx, rbx; this
0x18000897b  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x180008980  mov     rcx, [rdi]; Table
0x180008983  mov     dl, 1; Restart
0x180008985  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000898b  mov     rcx, [rdi]; pv
0x18000898e  test    rax, rax
0x180008991  jnz     short loc_18000896C
0x180008993  call    cs:__imp_CoTaskMemFree
0x180008999  mov     qword ptr [rdi], 0
0x1800089a0  mov     ecx, 68h ; 'h'; cb
0x1800089a5  call    cs:__imp_CoTaskMemAlloc
0x1800089ab  mov     [rdi], rax
0x1800089ae  test    rax, rax
0x1800089b1  jnz     short loc_1800089BA
0x1800089b3  mov     ebx, 8007000Eh
0x1800089b8  jmp     short loc_1800089DF
0x1800089ba  xor     ebx, ebx
0x1800089bc  mov     [rsp+38h+TableContext], rdi; TableContext
0x1800089c1  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800089c8  mov     rcx, rax; Table
0x1800089cb  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800089d2  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800089d9  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800089df  mov     eax, ebx
0x1800089e1  mov     rbx, [rsp+38h+arg_0]
0x1800089e6  add     rsp, 30h
0x1800089ea  pop     rdi
0x1800089eb  retn
```
