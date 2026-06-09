# CSxRefMap<CRegExtTypeMap,CRefRegExtType>::FinalConstruct(void)

- ea: `0x18003e180`
- end: `0x18003e23f`
- name: `?FinalConstruct@?$CSxRefMap@VCRegExtTypeMap@@VCRefRegExtType@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003dbd8`

## callees

- `0x180009b8c`
- `0x18003e180`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18003e225`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003e225`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003e1bf`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18003e1bf`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003e1a6`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18003e1a6`
- `ole32!CoTaskMemFree` at `0x18003e1d3`
- `ole32!CoTaskMemFree` at `0x18003e1d3`
- `ole32!CoTaskMemAlloc` at `0x18003e1eb`
- `ole32!CoTaskMemAlloc` at `0x18003e1eb`

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
0x18003e180  mov     [rsp+arg_0], rbx
0x18003e185  push    rdi
0x18003e186  sub     rsp, 30h
0x18003e18a  mov     rdi, rcx
0x18003e18d  lock inc dword ptr [rcx+8]
0x18003e191  cmp     qword ptr [rcx], 0
0x18003e195  jz      short loc_18003E1E6
0x18003e197  lock inc dword ptr [rcx+8]
0x18003e19b  mov     rcx, [rcx]
0x18003e19e  jmp     short loc_18003E1BD
0x18003e1a0  mov     rbx, [rax]
0x18003e1a3  mov     rdx, rax; Buffer
0x18003e1a6  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18003e1ad  nop     dword ptr [rax+rax+00h]
0x18003e1b2  mov     rcx, rbx; this
0x18003e1b5  call    ?Release@CRefRegExtType@@QEAAKXZ; CRefRegExtType::Release(void)
0x18003e1ba  mov     rcx, [rdi]; Table
0x18003e1bd  mov     dl, 1; Restart
0x18003e1bf  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18003e1c6  nop     dword ptr [rax+rax+00h]
0x18003e1cb  mov     rcx, [rdi]; pv
0x18003e1ce  test    rax, rax
0x18003e1d1  jnz     short loc_18003E1A0
0x18003e1d3  call    cs:__imp_CoTaskMemFree
0x18003e1da  nop     dword ptr [rax+rax+00h]
0x18003e1df  mov     qword ptr [rdi], 0
0x18003e1e6  mov     ecx, 68h ; 'h'; cb
0x18003e1eb  call    cs:__imp_CoTaskMemAlloc
0x18003e1f2  nop     dword ptr [rax+rax+00h]
0x18003e1f7  mov     [rdi], rax
0x18003e1fa  test    rax, rax
0x18003e1fd  jnz     short loc_18003E206
0x18003e1ff  mov     ebx, 8007000Eh
0x18003e204  jmp     short loc_18003E231
0x18003e206  xor     ebx, ebx
0x18003e208  mov     [rsp+38h+TableContext], rdi; TableContext
0x18003e20d  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18003e214  mov     rcx, rax; Table
0x18003e217  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18003e21e  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCRegInfoTypeMap@@VCRefRegInfoType@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18003e225  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003e22c  nop     dword ptr [rax+rax+00h]
0x18003e231  mov     eax, ebx
0x18003e233  mov     rbx, [rsp+38h+arg_0]
0x18003e238  add     rsp, 30h
0x18003e23c  pop     rdi
0x18003e23d  retn
```
