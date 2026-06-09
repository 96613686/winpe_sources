# CSxRefMap<CSxFileRuleMap,CSxFileRule>::FinalConstruct(void)

- ea: `0x180077a48`
- end: `0x180077b0e`
- name: `?FinalConstruct@?$CSxRefMap@VCSxFileRuleMap@@VCSxFileRule@@@@AEAAJXZ`
- size: `198`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180075a9c`

## callees

- `0x180077a48`
- `0x1800d1010`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180077af4`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180077af4`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180077a8e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180077a8e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180077a6e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180077a6e`
- `ole32!CoTaskMemFree` at `0x180077aa2`
- `ole32!CoTaskMemFree` at `0x180077aa2`
- `ole32!CoTaskMemAlloc` at `0x180077aba`
- `ole32!CoTaskMemAlloc` at `0x180077aba`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSxFileRuleMap,CSxFileRule>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  __int64 v3; // rbx
  __int64 *v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (__int64 *)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
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
      CSxRefMap<CSxDirRuleMap,CSxDirRule>::_CompareRoutine,
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
0x180077a48  mov     [rsp+arg_0], rbx
0x180077a4d  push    rdi
0x180077a4e  sub     rsp, 30h
0x180077a52  mov     rdi, rcx
0x180077a55  lock inc dword ptr [rcx+8]
0x180077a59  cmp     qword ptr [rcx], 0
0x180077a5d  jz      short loc_180077AB5
0x180077a5f  lock inc dword ptr [rcx+8]
0x180077a63  mov     rcx, [rcx]
0x180077a66  jmp     short loc_180077A8C
0x180077a68  mov     rbx, [rax]
0x180077a6b  mov     rdx, rax; Buffer
0x180077a6e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180077a75  nop     dword ptr [rax+rax+00h]
0x180077a7a  mov     rax, [rbx]
0x180077a7d  mov     rcx, rbx
0x180077a80  mov     rax, [rax+8]
0x180077a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a89  mov     rcx, [rdi]; Table
0x180077a8c  mov     dl, 1; Restart
0x180077a8e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180077a95  nop     dword ptr [rax+rax+00h]
0x180077a9a  mov     rcx, [rdi]; pv
0x180077a9d  test    rax, rax
0x180077aa0  jnz     short loc_180077A68
0x180077aa2  call    cs:__imp_CoTaskMemFree
0x180077aa9  nop     dword ptr [rax+rax+00h]
0x180077aae  mov     qword ptr [rdi], 0
0x180077ab5  mov     ecx, 68h ; 'h'; cb
0x180077aba  call    cs:__imp_CoTaskMemAlloc
0x180077ac1  nop     dword ptr [rax+rax+00h]
0x180077ac6  mov     [rdi], rax
0x180077ac9  test    rax, rax
0x180077acc  jnz     short loc_180077AD5
0x180077ace  mov     ebx, 8007000Eh
0x180077ad3  jmp     short loc_180077B00
0x180077ad5  xor     ebx, ebx
0x180077ad7  mov     [rsp+38h+TableContext], rdi; TableContext
0x180077adc  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180077ae3  mov     rcx, rax; Table
0x180077ae6  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180077aed  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180077af4  call    cs:__imp_RtlInitializeGenericTableAvl
0x180077afb  nop     dword ptr [rax+rax+00h]
0x180077b00  mov     eax, ebx
0x180077b02  mov     rbx, [rsp+38h+arg_0]
0x180077b07  add     rsp, 30h
0x180077b0b  pop     rdi
0x180077b0c  retn
```
