# CSxRefMap<CSxExtensionMap,CSxExtension>::FinalConstruct(void)

- ea: `0x180074a38`
- end: `0x180074ad8`
- name: `?FinalConstruct@?$CSxRefMap@VCSxExtensionMap@@VCSxExtension@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180072bd8`

## callees

- `0x180074a38`
- `0x180077d40`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180074ac5`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180074ac5`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180074a71`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180074a71`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180074a5e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180074a5e`
- `ole32!CoTaskMemFree` at `0x180074a7f`
- `ole32!CoTaskMemFree` at `0x180074a7f`
- `ole32!CoTaskMemAlloc` at `0x180074a91`
- `ole32!CoTaskMemAlloc` at `0x180074a91`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSxExtensionMap,CSxExtension>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSxExtension *v3; // rbx
  CSxExtension **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSxExtension **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSxExtension::Release(v3);
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
      CSxRefMap<CSxExtensionMap,CSxExtension>::_CompareRoutine,
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
0x180074a38  mov     [rsp+arg_0], rbx
0x180074a3d  push    rdi
0x180074a3e  sub     rsp, 30h
0x180074a42  mov     rdi, rcx
0x180074a45  lock inc dword ptr [rcx+8]
0x180074a49  cmp     qword ptr [rcx], 0
0x180074a4d  jz      short loc_180074A8C
0x180074a4f  lock inc dword ptr [rcx+8]
0x180074a53  mov     rcx, [rcx]
0x180074a56  jmp     short loc_180074A6F
0x180074a58  mov     rbx, [rax]
0x180074a5b  mov     rdx, rax; Buffer
0x180074a5e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180074a64  mov     rcx, rbx; this
0x180074a67  call    ?Release@CSxExtension@@QEAAKXZ; CSxExtension::Release(void)
0x180074a6c  mov     rcx, [rdi]; Table
0x180074a6f  mov     dl, 1; Restart
0x180074a71  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180074a77  mov     rcx, [rdi]; pv
0x180074a7a  test    rax, rax
0x180074a7d  jnz     short loc_180074A58
0x180074a7f  call    cs:__imp_CoTaskMemFree
0x180074a85  mov     qword ptr [rdi], 0
0x180074a8c  mov     ecx, 68h ; 'h'; cb
0x180074a91  call    cs:__imp_CoTaskMemAlloc
0x180074a97  mov     [rdi], rax
0x180074a9a  test    rax, rax
0x180074a9d  jnz     short loc_180074AA6
0x180074a9f  mov     ebx, 8007000Eh
0x180074aa4  jmp     short loc_180074ACB
0x180074aa6  xor     ebx, ebx
0x180074aa8  mov     [rsp+38h+TableContext], rdi; TableContext
0x180074aad  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180074ab4  mov     rcx, rax; Table
0x180074ab7  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180074abe  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxExtensionMap@@VCSxExtension@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180074ac5  call    cs:__imp_RtlInitializeGenericTableAvl
0x180074acb  mov     eax, ebx
0x180074acd  mov     rbx, [rsp+38h+arg_0]
0x180074ad2  add     rsp, 30h
0x180074ad6  pop     rdi
0x180074ad7  retn
```
