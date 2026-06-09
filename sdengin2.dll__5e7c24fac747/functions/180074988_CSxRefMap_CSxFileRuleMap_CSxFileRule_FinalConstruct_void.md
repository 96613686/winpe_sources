# CSxRefMap<CSxFileRuleMap,CSxFileRule>::FinalConstruct(void)

- ea: `0x180074988`
- end: `0x180074a2f`
- name: `?FinalConstruct@?$CSxRefMap@VCSxFileRuleMap@@VCSxFileRule@@@@AEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180072a04`

## callees

- `0x180074988`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180074a1c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180074a1c`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800749c8`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800749c8`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800749ae`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800749ae`
- `ole32!CoTaskMemFree` at `0x1800749d6`
- `ole32!CoTaskMemFree` at `0x1800749d6`
- `ole32!CoTaskMemAlloc` at `0x1800749e8`
- `ole32!CoTaskMemAlloc` at `0x1800749e8`

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
0x180074988  mov     [rsp+arg_0], rbx
0x18007498d  push    rdi
0x18007498e  sub     rsp, 30h
0x180074992  mov     rdi, rcx
0x180074995  lock inc dword ptr [rcx+8]
0x180074999  cmp     qword ptr [rcx], 0
0x18007499d  jz      short loc_1800749E3
0x18007499f  lock inc dword ptr [rcx+8]
0x1800749a3  mov     rcx, [rcx]
0x1800749a6  jmp     short loc_1800749C6
0x1800749a8  mov     rbx, [rax]
0x1800749ab  mov     rdx, rax; Buffer
0x1800749ae  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800749b4  mov     rax, [rbx]
0x1800749b7  mov     rcx, rbx
0x1800749ba  mov     rax, [rax+8]
0x1800749be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749c3  mov     rcx, [rdi]; Table
0x1800749c6  mov     dl, 1; Restart
0x1800749c8  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800749ce  mov     rcx, [rdi]; pv
0x1800749d1  test    rax, rax
0x1800749d4  jnz     short loc_1800749A8
0x1800749d6  call    cs:__imp_CoTaskMemFree
0x1800749dc  mov     qword ptr [rdi], 0
0x1800749e3  mov     ecx, 68h ; 'h'; cb
0x1800749e8  call    cs:__imp_CoTaskMemAlloc
0x1800749ee  mov     [rdi], rax
0x1800749f1  test    rax, rax
0x1800749f4  jnz     short loc_1800749FD
0x1800749f6  mov     ebx, 8007000Eh
0x1800749fb  jmp     short loc_180074A22
0x1800749fd  xor     ebx, ebx
0x1800749ff  mov     [rsp+38h+TableContext], rdi; TableContext
0x180074a04  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180074a0b  mov     rcx, rax; Table
0x180074a0e  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180074a15  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180074a1c  call    cs:__imp_RtlInitializeGenericTableAvl
0x180074a22  mov     eax, ebx
0x180074a24  mov     rbx, [rsp+38h+arg_0]
0x180074a29  add     rsp, 30h
0x180074a2d  pop     rdi
0x180074a2e  retn
```
