# CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::FinalConstruct(void)

- ea: `0x180090254`
- end: `0x1800902f4`
- name: `?FinalConstruct@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800901a4`

## callees

- `0x180090254`
- `0x1800905bc`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800902e1`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800902e1`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009028d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009028d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18009027a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18009027a`
- `ole32!CoTaskMemFree` at `0x18009029b`
- `ole32!CoTaskMemFree` at `0x18009029b`
- `ole32!CoTaskMemAlloc` at `0x1800902ad`
- `ole32!CoTaskMemAlloc` at `0x1800902ad`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeIdEntry *v3; // rbx
  CVolumeIdEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CVolumeIdEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CVolumeIdEntry::Release(v3);
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
      CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::_CompareRoutine,
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
0x180090254  mov     [rsp+arg_0], rbx
0x180090259  push    rdi
0x18009025a  sub     rsp, 30h
0x18009025e  mov     rdi, rcx
0x180090261  lock inc dword ptr [rcx+8]
0x180090265  cmp     qword ptr [rcx], 0
0x180090269  jz      short loc_1800902A8
0x18009026b  lock inc dword ptr [rcx+8]
0x18009026f  mov     rcx, [rcx]
0x180090272  jmp     short loc_18009028B
0x180090274  mov     rbx, [rax]
0x180090277  mov     rdx, rax; Buffer
0x18009027a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180090280  mov     rcx, rbx; this
0x180090283  call    ?Release@CVolumeIdEntry@@QEAAKXZ; CVolumeIdEntry::Release(void)
0x180090288  mov     rcx, [rdi]; Table
0x18009028b  mov     dl, 1; Restart
0x18009028d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180090293  mov     rcx, [rdi]; pv
0x180090296  test    rax, rax
0x180090299  jnz     short loc_180090274
0x18009029b  call    cs:__imp_CoTaskMemFree
0x1800902a1  mov     qword ptr [rdi], 0
0x1800902a8  mov     ecx, 68h ; 'h'; cb
0x1800902ad  call    cs:__imp_CoTaskMemAlloc
0x1800902b3  mov     [rdi], rax
0x1800902b6  test    rax, rax
0x1800902b9  jnz     short loc_1800902C2
0x1800902bb  mov     ebx, 8007000Eh
0x1800902c0  jmp     short loc_1800902E7
0x1800902c2  xor     ebx, ebx
0x1800902c4  mov     [rsp+38h+TableContext], rdi; TableContext
0x1800902c9  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800902d0  mov     rcx, rax; Table
0x1800902d3  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800902da  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800902e1  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800902e7  mov     eax, ebx
0x1800902e9  mov     rbx, [rsp+38h+arg_0]
0x1800902ee  add     rsp, 30h
0x1800902f2  pop     rdi
0x1800902f3  retn
```
