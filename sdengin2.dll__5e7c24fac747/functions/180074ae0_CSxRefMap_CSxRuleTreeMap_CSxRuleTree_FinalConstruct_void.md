# CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::FinalConstruct(void)

- ea: `0x180074ae0`
- end: `0x180074b80`
- name: `?FinalConstruct@?$CSxRefMap@VCSxRuleTreeMap@@VCSxRuleTree@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180072d3c`

## callees

- `0x180074ae0`
- `0x180077e20`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180074b6d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180074b6d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180074b19`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180074b19`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180074b06`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180074b06`
- `ole32!CoTaskMemFree` at `0x180074b27`
- `ole32!CoTaskMemFree` at `0x180074b27`
- `ole32!CoTaskMemAlloc` at `0x180074b39`
- `ole32!CoTaskMemAlloc` at `0x180074b39`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSxRuleTree *v3; // rbx
  CSxRuleTree **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSxRuleTree **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSxRuleTree::Release(v3);
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
      CSxRefMap<CSxStringMap,CSxStringEntry>::_CompareRoutine,
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
0x180074ae0  mov     [rsp+arg_0], rbx
0x180074ae5  push    rdi
0x180074ae6  sub     rsp, 30h
0x180074aea  mov     rdi, rcx
0x180074aed  lock inc dword ptr [rcx+8]
0x180074af1  cmp     qword ptr [rcx], 0
0x180074af5  jz      short loc_180074B34
0x180074af7  lock inc dword ptr [rcx+8]
0x180074afb  mov     rcx, [rcx]
0x180074afe  jmp     short loc_180074B17
0x180074b00  mov     rbx, [rax]
0x180074b03  mov     rdx, rax; Buffer
0x180074b06  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180074b0c  mov     rcx, rbx; this
0x180074b0f  call    ?Release@CSxRuleTree@@QEAAKXZ; CSxRuleTree::Release(void)
0x180074b14  mov     rcx, [rdi]; Table
0x180074b17  mov     dl, 1; Restart
0x180074b19  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180074b1f  mov     rcx, [rdi]; pv
0x180074b22  test    rax, rax
0x180074b25  jnz     short loc_180074B00
0x180074b27  call    cs:__imp_CoTaskMemFree
0x180074b2d  mov     qword ptr [rdi], 0
0x180074b34  mov     ecx, 68h ; 'h'; cb
0x180074b39  call    cs:__imp_CoTaskMemAlloc
0x180074b3f  mov     [rdi], rax
0x180074b42  test    rax, rax
0x180074b45  jnz     short loc_180074B4E
0x180074b47  mov     ebx, 8007000Eh
0x180074b4c  jmp     short loc_180074B73
0x180074b4e  xor     ebx, ebx
0x180074b50  mov     [rsp+38h+TableContext], rdi; TableContext
0x180074b55  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180074b5c  mov     rcx, rax; Table
0x180074b5f  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180074b66  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180074b6d  call    cs:__imp_RtlInitializeGenericTableAvl
0x180074b73  mov     eax, ebx
0x180074b75  mov     rbx, [rsp+38h+arg_0]
0x180074b7a  add     rsp, 30h
0x180074b7e  pop     rdi
0x180074b7f  retn
```
