# CSxRefMap<CSdMediaMapFinder,CSdMedia>::FinalConstruct(void)

- ea: `0x180025fec`
- end: `0x1800260ab`
- name: `?FinalConstruct@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800248f0`

## callees

- `0x180025fec`
- `0x180027700`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180026091`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180026091`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002602b`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002602b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180026012`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180026012`
- `ole32!CoTaskMemFree` at `0x18002603f`
- `ole32!CoTaskMemFree` at `0x18002603f`
- `ole32!CoTaskMemAlloc` at `0x180026057`
- `ole32!CoTaskMemAlloc` at `0x180026057`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSdMediaMapFinder,CSdMedia>::FinalConstruct(volatile signed __int32 *TableContext)
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
      CSxRefMap<CSdMediaMapFinder,CSdMedia>::_CompareRoutine,
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
0x180025fec  mov     [rsp+arg_0], rbx
0x180025ff1  push    rdi
0x180025ff2  sub     rsp, 30h
0x180025ff6  mov     rdi, rcx
0x180025ff9  lock inc dword ptr [rcx+8]
0x180025ffd  cmp     qword ptr [rcx], 0
0x180026001  jz      short loc_180026052
0x180026003  lock inc dword ptr [rcx+8]
0x180026007  mov     rcx, [rcx]
0x18002600a  jmp     short loc_180026029
0x18002600c  mov     rbx, [rax]
0x18002600f  mov     rdx, rax; Buffer
0x180026012  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180026019  nop     dword ptr [rax+rax+00h]
0x18002601e  mov     rcx, rbx; this
0x180026021  call    ?Release@CSdMedia@@QEAAKXZ; CSdMedia::Release(void)
0x180026026  mov     rcx, [rdi]; Table
0x180026029  mov     dl, 1; Restart
0x18002602b  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180026032  nop     dword ptr [rax+rax+00h]
0x180026037  mov     rcx, [rdi]; pv
0x18002603a  test    rax, rax
0x18002603d  jnz     short loc_18002600C
0x18002603f  call    cs:__imp_CoTaskMemFree
0x180026046  nop     dword ptr [rax+rax+00h]
0x18002604b  mov     qword ptr [rdi], 0
0x180026052  mov     ecx, 68h ; 'h'; cb
0x180026057  call    cs:__imp_CoTaskMemAlloc
0x18002605e  nop     dword ptr [rax+rax+00h]
0x180026063  mov     [rdi], rax
0x180026066  test    rax, rax
0x180026069  jnz     short loc_180026072
0x18002606b  mov     ebx, 8007000Eh
0x180026070  jmp     short loc_18002609D
0x180026072  xor     ebx, ebx
0x180026074  mov     [rsp+38h+TableContext], rdi; TableContext
0x180026079  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180026080  mov     rcx, rax; Table
0x180026083  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18002608a  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180026091  call    cs:__imp_RtlInitializeGenericTableAvl
0x180026098  nop     dword ptr [rax+rax+00h]
0x18002609d  mov     eax, ebx
0x18002609f  mov     rbx, [rsp+38h+arg_0]
0x1800260a4  add     rsp, 30h
0x1800260a8  pop     rdi
0x1800260a9  retn
```
