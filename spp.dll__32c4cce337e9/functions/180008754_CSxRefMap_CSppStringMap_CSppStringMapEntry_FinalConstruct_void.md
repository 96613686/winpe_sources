# CSxRefMap<CSppStringMap,CSppStringMapEntry>::FinalConstruct(void)

- ea: `0x180008754`
- end: `0x1800087f4`
- name: `?FinalConstruct@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800073a0`

## callees

- `0x180008754`
- `0x18000e208`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800087e1`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800087e1`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000878d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000878d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000877a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000877a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000879b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000879b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800087ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800087ad`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSppStringMap,CSppStringMapEntry>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSppStringMapEntry *v3; // rbx
  CSppStringMapEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSppStringMapEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSppStringMapEntry::Release(v3);
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
      (PRTL_AVL_COMPARE_ROUTINE)CSxRefMap<CSxStringMap,CSxStringEntry>::_CompareRoutine,
      (PRTL_AVL_ALLOCATE_ROUTINE)CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::_AllocateRoutine,
      (PRTL_AVL_FREE_ROUTINE)CSxRefMap<CSppStringMap,CSppStringMapEntry>::_FreeRoutine,
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
0x180008754  mov     [rsp+arg_0], rbx
0x180008759  push    rdi
0x18000875a  sub     rsp, 30h
0x18000875e  mov     rdi, rcx
0x180008761  lock inc dword ptr [rcx+8]
0x180008765  cmp     qword ptr [rcx], 0
0x180008769  jz      short loc_1800087A8
0x18000876b  lock inc dword ptr [rcx+8]
0x18000876f  mov     rcx, [rcx]
0x180008772  jmp     short loc_18000878B
0x180008774  mov     rbx, [rax]
0x180008777  mov     rdx, rax; Buffer
0x18000877a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180008780  mov     rcx, rbx; this
0x180008783  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x180008788  mov     rcx, [rdi]; Table
0x18000878b  mov     dl, 1; Restart
0x18000878d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180008793  mov     rcx, [rdi]; pv
0x180008796  test    rax, rax
0x180008799  jnz     short loc_180008774
0x18000879b  call    cs:__imp_CoTaskMemFree
0x1800087a1  mov     qword ptr [rdi], 0
0x1800087a8  mov     ecx, 68h ; 'h'; cb
0x1800087ad  call    cs:__imp_CoTaskMemAlloc
0x1800087b3  mov     [rdi], rax
0x1800087b6  test    rax, rax
0x1800087b9  jnz     short loc_1800087C2
0x1800087bb  mov     ebx, 8007000Eh
0x1800087c0  jmp     short loc_1800087E7
0x1800087c2  xor     ebx, ebx
0x1800087c4  mov     [rsp+38h+TableContext], rdi; TableContext
0x1800087c9  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800087d0  mov     rcx, rax; Table
0x1800087d3  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800087da  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800087e1  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800087e7  mov     eax, ebx
0x1800087e9  mov     rbx, [rsp+38h+arg_0]
0x1800087ee  add     rsp, 30h
0x1800087f2  pop     rdi
0x1800087f3  retn
```
