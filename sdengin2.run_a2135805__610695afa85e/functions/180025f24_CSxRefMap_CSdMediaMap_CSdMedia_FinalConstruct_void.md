# CSxRefMap<CSdMediaMap,CSdMedia>::FinalConstruct(void)

- ea: `0x180025f24`
- end: `0x180025fe3`
- name: `?FinalConstruct@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180024864`

## callees

- `0x180025f24`
- `0x180027700`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180025fc9`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180025fc9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180025f63`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180025f63`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025f4a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025f4a`
- `ole32!CoTaskMemFree` at `0x180025f77`
- `ole32!CoTaskMemFree` at `0x180025f77`
- `ole32!CoTaskMemAlloc` at `0x180025f8f`
- `ole32!CoTaskMemAlloc` at `0x180025f8f`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSdMediaMap,CSdMedia>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSdMedia *v3; // rbx
  CSdMedia **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSdMedia **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSdMedia::Release(v3);
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
      CSxRefMap<CSdMediaMap,CSdMedia>::_CompareRoutine,
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
0x180025f24  mov     [rsp+arg_0], rbx
0x180025f29  push    rdi
0x180025f2a  sub     rsp, 30h
0x180025f2e  mov     rdi, rcx
0x180025f31  lock inc dword ptr [rcx+8]
0x180025f35  cmp     qword ptr [rcx], 0
0x180025f39  jz      short loc_180025F8A
0x180025f3b  lock inc dword ptr [rcx+8]
0x180025f3f  mov     rcx, [rcx]
0x180025f42  jmp     short loc_180025F61
0x180025f44  mov     rbx, [rax]
0x180025f47  mov     rdx, rax; Buffer
0x180025f4a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180025f51  nop     dword ptr [rax+rax+00h]
0x180025f56  mov     rcx, rbx; this
0x180025f59  call    ?Release@CSdMedia@@QEAAKXZ; CSdMedia::Release(void)
0x180025f5e  mov     rcx, [rdi]; Table
0x180025f61  mov     dl, 1; Restart
0x180025f63  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180025f6a  nop     dword ptr [rax+rax+00h]
0x180025f6f  mov     rcx, [rdi]; pv
0x180025f72  test    rax, rax
0x180025f75  jnz     short loc_180025F44
0x180025f77  call    cs:__imp_CoTaskMemFree
0x180025f7e  nop     dword ptr [rax+rax+00h]
0x180025f83  mov     qword ptr [rdi], 0
0x180025f8a  mov     ecx, 68h ; 'h'; cb
0x180025f8f  call    cs:__imp_CoTaskMemAlloc
0x180025f96  nop     dword ptr [rax+rax+00h]
0x180025f9b  mov     [rdi], rax
0x180025f9e  test    rax, rax
0x180025fa1  jnz     short loc_180025FAA
0x180025fa3  mov     ebx, 8007000Eh
0x180025fa8  jmp     short loc_180025FD5
0x180025faa  xor     ebx, ebx
0x180025fac  mov     [rsp+38h+TableContext], rdi; TableContext
0x180025fb1  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180025fb8  mov     rcx, rax; Table
0x180025fbb  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180025fc2  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180025fc9  call    cs:__imp_RtlInitializeGenericTableAvl
0x180025fd0  nop     dword ptr [rax+rax+00h]
0x180025fd5  mov     eax, ebx
0x180025fd7  mov     rbx, [rsp+38h+arg_0]
0x180025fdc  add     rsp, 30h
0x180025fe0  pop     rdi
0x180025fe1  retn
```
