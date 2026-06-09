# CSxRefMap<CRegInfoTypeMap,CRefRegInfoType>::FinalConstruct(void)

- ea: `0x18003e248`
- end: `0x18003e307`
- name: `?FinalConstruct@?$CSxRefMap@VCRegInfoTypeMap@@VCRefRegInfoType@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003dc64`

## callees

- `0x180009bcc`
- `0x18003e248`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18003e2ed`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003e2ed`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003e287`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003e287`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003e26e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003e26e`
- `ole32!CoTaskMemFree` at `0x18003e29b`
- `ole32!CoTaskMemFree` at `0x18003e29b`
- `ole32!CoTaskMemAlloc` at `0x18003e2b3`
- `ole32!CoTaskMemAlloc` at `0x18003e2b3`

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
0x18003e248  mov     [rsp+arg_0], rbx
0x18003e24d  push    rdi
0x18003e24e  sub     rsp, 30h
0x18003e252  mov     rdi, rcx
0x18003e255  lock inc dword ptr [rcx+8]
0x18003e259  cmp     qword ptr [rcx], 0
0x18003e25d  jz      short loc_18003E2AE
0x18003e25f  lock inc dword ptr [rcx+8]
0x18003e263  mov     rcx, [rcx]
0x18003e266  jmp     short loc_18003E285
0x18003e268  mov     rbx, [rax]
0x18003e26b  mov     rdx, rax; Buffer
0x18003e26e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18003e275  nop     dword ptr [rax+rax+00h]
0x18003e27a  mov     rcx, rbx; this
0x18003e27d  call    ?Release@CRefRegInfoType@@QEAAKXZ; CRefRegInfoType::Release(void)
0x18003e282  mov     rcx, [rdi]; Table
0x18003e285  mov     dl, 1; Restart
0x18003e287  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18003e28e  nop     dword ptr [rax+rax+00h]
0x18003e293  mov     rcx, [rdi]; pv
0x18003e296  test    rax, rax
0x18003e299  jnz     short loc_18003E268
0x18003e29b  call    cs:__imp_CoTaskMemFree
0x18003e2a2  nop     dword ptr [rax+rax+00h]
0x18003e2a7  mov     qword ptr [rdi], 0
0x18003e2ae  mov     ecx, 68h ; 'h'; cb
0x18003e2b3  call    cs:__imp_CoTaskMemAlloc
0x18003e2ba  nop     dword ptr [rax+rax+00h]
0x18003e2bf  mov     [rdi], rax
0x18003e2c2  test    rax, rax
0x18003e2c5  jnz     short loc_18003E2CE
0x18003e2c7  mov     ebx, 8007000Eh
0x18003e2cc  jmp     short loc_18003E2F9
0x18003e2ce  xor     ebx, ebx
0x18003e2d0  mov     [rsp+38h+TableContext], rdi; TableContext
0x18003e2d5  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18003e2dc  mov     rcx, rax; Table
0x18003e2df  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18003e2e6  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCRegInfoTypeMap@@VCRefRegInfoType@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18003e2ed  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003e2f4  nop     dword ptr [rax+rax+00h]
0x18003e2f9  mov     eax, ebx
0x18003e2fb  mov     rbx, [rsp+38h+arg_0]
0x18003e300  add     rsp, 30h
0x18003e304  pop     rdi
0x18003e305  retn
```
