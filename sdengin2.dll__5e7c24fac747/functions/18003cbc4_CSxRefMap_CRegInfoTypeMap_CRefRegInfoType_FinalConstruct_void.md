# CSxRefMap<CRegInfoTypeMap,CRefRegInfoType>::FinalConstruct(void)

- ea: `0x18003cbc4`
- end: `0x18003cc64`
- name: `?FinalConstruct@?$CSxRefMap@VCRegInfoTypeMap@@VCRefRegInfoType@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c60c`

## callees

- `0x180009958`
- `0x18003cbc4`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18003cc51`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003cc51`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003cbfd`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003cbfd`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003cbea`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003cbea`
- `ole32!CoTaskMemFree` at `0x18003cc0b`
- `ole32!CoTaskMemFree` at `0x18003cc0b`
- `ole32!CoTaskMemAlloc` at `0x18003cc1d`
- `ole32!CoTaskMemAlloc` at `0x18003cc1d`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CRegInfoTypeMap,CRefRegInfoType>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CRefRegInfoType *v3; // rbx
  CRefRegInfoType **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CRefRegInfoType **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CRefRegInfoType::Release(v3);
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
0x18003cbc4  mov     [rsp+arg_0], rbx
0x18003cbc9  push    rdi
0x18003cbca  sub     rsp, 30h
0x18003cbce  mov     rdi, rcx
0x18003cbd1  lock inc dword ptr [rcx+8]
0x18003cbd5  cmp     qword ptr [rcx], 0
0x18003cbd9  jz      short loc_18003CC18
0x18003cbdb  lock inc dword ptr [rcx+8]
0x18003cbdf  mov     rcx, [rcx]
0x18003cbe2  jmp     short loc_18003CBFB
0x18003cbe4  mov     rbx, [rax]
0x18003cbe7  mov     rdx, rax; Buffer
0x18003cbea  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18003cbf0  mov     rcx, rbx; this
0x18003cbf3  call    ?Release@CRefRegInfoType@@QEAAKXZ; CRefRegInfoType::Release(void)
0x18003cbf8  mov     rcx, [rdi]; Table
0x18003cbfb  mov     dl, 1; Restart
0x18003cbfd  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18003cc03  mov     rcx, [rdi]; pv
0x18003cc06  test    rax, rax
0x18003cc09  jnz     short loc_18003CBE4
0x18003cc0b  call    cs:__imp_CoTaskMemFree
0x18003cc11  mov     qword ptr [rdi], 0
0x18003cc18  mov     ecx, 68h ; 'h'; cb
0x18003cc1d  call    cs:__imp_CoTaskMemAlloc
0x18003cc23  mov     [rdi], rax
0x18003cc26  test    rax, rax
0x18003cc29  jnz     short loc_18003CC32
0x18003cc2b  mov     ebx, 8007000Eh
0x18003cc30  jmp     short loc_18003CC57
0x18003cc32  xor     ebx, ebx
0x18003cc34  mov     [rsp+38h+TableContext], rdi; TableContext
0x18003cc39  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18003cc40  mov     rcx, rax; Table
0x18003cc43  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18003cc4a  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCRegInfoTypeMap@@VCRefRegInfoType@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18003cc51  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003cc57  mov     eax, ebx
0x18003cc59  mov     rbx, [rsp+38h+arg_0]
0x18003cc5e  add     rsp, 30h
0x18003cc62  pop     rdi
0x18003cc63  retn
```
