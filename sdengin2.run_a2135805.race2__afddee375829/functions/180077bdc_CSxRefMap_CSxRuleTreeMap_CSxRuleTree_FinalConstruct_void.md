# CSxRefMap<CSxRuleTreeMap,CSxRuleTree>::FinalConstruct(void)

- ea: `0x180077bdc`
- end: `0x180077c9b`
- name: `?FinalConstruct@?$CSxRefMap@VCSxRuleTreeMap@@VCSxRuleTree@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180075dd8`

## callees

- `0x180077bdc`
- `0x18007afc0`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180077c81`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180077c81`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180077c1b`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180077c1b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180077c02`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180077c02`
- `ole32!CoTaskMemFree` at `0x180077c2f`
- `ole32!CoTaskMemFree` at `0x180077c2f`
- `ole32!CoTaskMemAlloc` at `0x180077c47`
- `ole32!CoTaskMemAlloc` at `0x180077c47`

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
0x180077bdc  mov     [rsp+arg_0], rbx
0x180077be1  push    rdi
0x180077be2  sub     rsp, 30h
0x180077be6  mov     rdi, rcx
0x180077be9  lock inc dword ptr [rcx+8]
0x180077bed  cmp     qword ptr [rcx], 0
0x180077bf1  jz      short loc_180077C42
0x180077bf3  lock inc dword ptr [rcx+8]
0x180077bf7  mov     rcx, [rcx]
0x180077bfa  jmp     short loc_180077C19
0x180077bfc  mov     rbx, [rax]
0x180077bff  mov     rdx, rax; Buffer
0x180077c02  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180077c09  nop     dword ptr [rax+rax+00h]
0x180077c0e  mov     rcx, rbx; this
0x180077c11  call    ?Release@CSxRuleTree@@QEAAKXZ; CSxRuleTree::Release(void)
0x180077c16  mov     rcx, [rdi]; Table
0x180077c19  mov     dl, 1; Restart
0x180077c1b  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180077c22  nop     dword ptr [rax+rax+00h]
0x180077c27  mov     rcx, [rdi]; pv
0x180077c2a  test    rax, rax
0x180077c2d  jnz     short loc_180077BFC
0x180077c2f  call    cs:__imp_CoTaskMemFree
0x180077c36  nop     dword ptr [rax+rax+00h]
0x180077c3b  mov     qword ptr [rdi], 0
0x180077c42  mov     ecx, 68h ; 'h'; cb
0x180077c47  call    cs:__imp_CoTaskMemAlloc
0x180077c4e  nop     dword ptr [rax+rax+00h]
0x180077c53  mov     [rdi], rax
0x180077c56  test    rax, rax
0x180077c59  jnz     short loc_180077C62
0x180077c5b  mov     ebx, 8007000Eh
0x180077c60  jmp     short loc_180077C8D
0x180077c62  xor     ebx, ebx
0x180077c64  mov     [rsp+38h+TableContext], rdi; TableContext
0x180077c69  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180077c70  mov     rcx, rax; Table
0x180077c73  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180077c7a  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180077c81  call    cs:__imp_RtlInitializeGenericTableAvl
0x180077c88  nop     dword ptr [rax+rax+00h]
0x180077c8d  mov     eax, ebx
0x180077c8f  mov     rbx, [rsp+38h+arg_0]
0x180077c94  add     rsp, 30h
0x180077c98  pop     rdi
0x180077c99  retn
```
