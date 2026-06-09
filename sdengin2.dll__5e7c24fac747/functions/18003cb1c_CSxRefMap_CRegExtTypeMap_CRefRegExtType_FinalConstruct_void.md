# CSxRefMap<CRegExtTypeMap,CRefRegExtType>::FinalConstruct(void)

- ea: `0x18003cb1c`
- end: `0x18003cbbc`
- name: `?FinalConstruct@?$CSxRefMap@VCRegExtTypeMap@@VCRefRegExtType@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c580`

## callees

- `0x180009918`
- `0x18003cb1c`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18003cba9`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003cba9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003cb55`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003cb55`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003cb42`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003cb42`
- `ole32!CoTaskMemFree` at `0x18003cb63`
- `ole32!CoTaskMemFree` at `0x18003cb63`
- `ole32!CoTaskMemAlloc` at `0x18003cb75`
- `ole32!CoTaskMemAlloc` at `0x18003cb75`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CRegExtTypeMap,CRefRegExtType>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CRefRegExtType *v3; // rbx
  CRefRegExtType **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CRefRegExtType **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CRefRegExtType::Release(v3);
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
      CSxRefMap<CRegInfoTypeMap,CRefRegInfoType>::_CompareRoutine,
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
0x18003cb1c  mov     [rsp+arg_0], rbx
0x18003cb21  push    rdi
0x18003cb22  sub     rsp, 30h
0x18003cb26  mov     rdi, rcx
0x18003cb29  lock inc dword ptr [rcx+8]
0x18003cb2d  cmp     qword ptr [rcx], 0
0x18003cb31  jz      short loc_18003CB70
0x18003cb33  lock inc dword ptr [rcx+8]
0x18003cb37  mov     rcx, [rcx]
0x18003cb3a  jmp     short loc_18003CB53
0x18003cb3c  mov     rbx, [rax]
0x18003cb3f  mov     rdx, rax; Buffer
0x18003cb42  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18003cb48  mov     rcx, rbx; this
0x18003cb4b  call    ?Release@CRefRegExtType@@QEAAKXZ; CRefRegExtType::Release(void)
0x18003cb50  mov     rcx, [rdi]; Table
0x18003cb53  mov     dl, 1; Restart
0x18003cb55  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18003cb5b  mov     rcx, [rdi]; pv
0x18003cb5e  test    rax, rax
0x18003cb61  jnz     short loc_18003CB3C
0x18003cb63  call    cs:__imp_CoTaskMemFree
0x18003cb69  mov     qword ptr [rdi], 0
0x18003cb70  mov     ecx, 68h ; 'h'; cb
0x18003cb75  call    cs:__imp_CoTaskMemAlloc
0x18003cb7b  mov     [rdi], rax
0x18003cb7e  test    rax, rax
0x18003cb81  jnz     short loc_18003CB8A
0x18003cb83  mov     ebx, 8007000Eh
0x18003cb88  jmp     short loc_18003CBAF
0x18003cb8a  xor     ebx, ebx
0x18003cb8c  mov     [rsp+38h+TableContext], rdi; TableContext
0x18003cb91  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18003cb98  mov     rcx, rax; Table
0x18003cb9b  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18003cba2  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCRegInfoTypeMap@@VCRefRegInfoType@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18003cba9  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003cbaf  mov     eax, ebx
0x18003cbb1  mov     rbx, [rsp+38h+arg_0]
0x18003cbb6  add     rsp, 30h
0x18003cbba  pop     rdi
0x18003cbbb  retn
```
