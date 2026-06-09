# CSxRefMap<CSdMediaMapFinder,CSdMedia>::FinalConstruct(void)

- ea: `0x1800250a4`
- end: `0x180025144`
- name: `?FinalConstruct@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023acc`

## callees

- `0x1800250a4`
- `0x180026700`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180025131`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180025131`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800250dd`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800250dd`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800250ca`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800250ca`
- `ole32!CoTaskMemFree` at `0x1800250eb`
- `ole32!CoTaskMemFree` at `0x1800250eb`
- `ole32!CoTaskMemAlloc` at `0x1800250fd`
- `ole32!CoTaskMemAlloc` at `0x1800250fd`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSdMediaMapFinder,CSdMedia>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSdMedia *v3; // rbx
  CSdMedia **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSdMedia **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSdMedia::Release(v3);
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
      CSxRefMap<CSdMediaMapFinder,CSdMedia>::_CompareRoutine,
      (PRTL_AVL_ALLOCATE_ROUTINE)CSxRefMap<CSxDirRuleMap,CSxDirRule>::_AllocateRoutine,
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
0x1800250a4  mov     [rsp+arg_0], rbx
0x1800250a9  push    rdi
0x1800250aa  sub     rsp, 30h
0x1800250ae  mov     rdi, rcx
0x1800250b1  lock inc dword ptr [rcx+8]
0x1800250b5  cmp     qword ptr [rcx], 0
0x1800250b9  jz      short loc_1800250F8
0x1800250bb  lock inc dword ptr [rcx+8]
0x1800250bf  mov     rcx, [rcx]
0x1800250c2  jmp     short loc_1800250DB
0x1800250c4  mov     rbx, [rax]
0x1800250c7  mov     rdx, rax; Buffer
0x1800250ca  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800250d0  mov     rcx, rbx; this
0x1800250d3  call    ?Release@CSdMedia@@QEAAKXZ; CSdMedia::Release(void)
0x1800250d8  mov     rcx, [rdi]; Table
0x1800250db  mov     dl, 1; Restart
0x1800250dd  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800250e3  mov     rcx, [rdi]; pv
0x1800250e6  test    rax, rax
0x1800250e9  jnz     short loc_1800250C4
0x1800250eb  call    cs:__imp_CoTaskMemFree
0x1800250f1  mov     qword ptr [rdi], 0
0x1800250f8  mov     ecx, 68h ; 'h'; cb
0x1800250fd  call    cs:__imp_CoTaskMemAlloc
0x180025103  mov     [rdi], rax
0x180025106  test    rax, rax
0x180025109  jnz     short loc_180025112
0x18002510b  mov     ebx, 8007000Eh
0x180025110  jmp     short loc_180025137
0x180025112  xor     ebx, ebx
0x180025114  mov     [rsp+38h+TableContext], rdi; TableContext
0x180025119  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180025120  mov     rcx, rax; Table
0x180025123  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18002512a  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180025131  call    cs:__imp_RtlInitializeGenericTableAvl
0x180025137  mov     eax, ebx
0x180025139  mov     rbx, [rsp+38h+arg_0]
0x18002513e  add     rsp, 30h
0x180025142  pop     rdi
0x180025143  retn
```
