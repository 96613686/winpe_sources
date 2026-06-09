# CSxRefMap<CSdRestoreRuleList,CSdRestoreRule>::FinalConstruct(void)

- ea: `0x18002514c`
- end: `0x1800251ec`
- name: `?FinalConstruct@?$CSxRefMap@VCSdRestoreRuleList@@VCSdRestoreRule@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023d4c`

## callees

- `0x180009998`
- `0x18002514c`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800251d9`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800251d9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180025185`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180025185`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025172`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025172`
- `ole32!CoTaskMemFree` at `0x180025193`
- `ole32!CoTaskMemFree` at `0x180025193`
- `ole32!CoTaskMemAlloc` at `0x1800251a5`
- `ole32!CoTaskMemAlloc` at `0x1800251a5`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSdRestoreRuleList,CSdRestoreRule>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSdRestoreRule *v3; // rbx
  CSdRestoreRule **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSdRestoreRule **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSdRestoreRule::Release(v3);
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
      CSxRefMap<CSdRestoreRuleList,CSdRestoreRule>::_CompareRoutine,
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
0x18002514c  mov     [rsp+arg_0], rbx
0x180025151  push    rdi
0x180025152  sub     rsp, 30h
0x180025156  mov     rdi, rcx
0x180025159  lock inc dword ptr [rcx+8]
0x18002515d  cmp     qword ptr [rcx], 0
0x180025161  jz      short loc_1800251A0
0x180025163  lock inc dword ptr [rcx+8]
0x180025167  mov     rcx, [rcx]
0x18002516a  jmp     short loc_180025183
0x18002516c  mov     rbx, [rax]
0x18002516f  mov     rdx, rax; Buffer
0x180025172  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180025178  mov     rcx, rbx; this
0x18002517b  call    ?Release@CSdRestoreRule@@QEAAKXZ; CSdRestoreRule::Release(void)
0x180025180  mov     rcx, [rdi]; Table
0x180025183  mov     dl, 1; Restart
0x180025185  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18002518b  mov     rcx, [rdi]; pv
0x18002518e  test    rax, rax
0x180025191  jnz     short loc_18002516C
0x180025193  call    cs:__imp_CoTaskMemFree
0x180025199  mov     qword ptr [rdi], 0
0x1800251a0  mov     ecx, 68h ; 'h'; cb
0x1800251a5  call    cs:__imp_CoTaskMemAlloc
0x1800251ab  mov     [rdi], rax
0x1800251ae  test    rax, rax
0x1800251b1  jnz     short loc_1800251BA
0x1800251b3  mov     ebx, 8007000Eh
0x1800251b8  jmp     short loc_1800251DF
0x1800251ba  xor     ebx, ebx
0x1800251bc  mov     [rsp+38h+TableContext], rdi; TableContext
0x1800251c1  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800251c8  mov     rcx, rax; Table
0x1800251cb  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800251d2  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSdRestoreRuleList@@VCSdRestoreRule@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800251d9  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800251df  mov     eax, ebx
0x1800251e1  mov     rbx, [rsp+38h+arg_0]
0x1800251e6  add     rsp, 30h
0x1800251ea  pop     rdi
0x1800251eb  retn
```
