# CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::FinalConstruct(void)

- ea: `0x1800278b0`
- end: `0x180027950`
- name: `?FinalConstruct@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800277ac`

## callees

- `0x1800278b0`
- `0x180027cdc`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18002793d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18002793d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800278e9`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800278e9`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800278d6`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800278d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800278f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800278f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027909`

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
      (PRTL_AVL_COMPARE_ROUTINE)CSxRefMap<CVolumeIdMap,CVolumeIdEntry>::_CompareRoutine,
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
0x1800278b0  mov     [rsp+arg_0], rbx
0x1800278b5  push    rdi
0x1800278b6  sub     rsp, 30h
0x1800278ba  mov     rdi, rcx
0x1800278bd  lock inc dword ptr [rcx+8]
0x1800278c1  cmp     qword ptr [rcx], 0
0x1800278c5  jz      short loc_180027904
0x1800278c7  lock inc dword ptr [rcx+8]
0x1800278cb  mov     rcx, [rcx]
0x1800278ce  jmp     short loc_1800278E7
0x1800278d0  mov     rbx, [rax]
0x1800278d3  mov     rdx, rax; Buffer
0x1800278d6  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800278dc  mov     rcx, rbx; this
0x1800278df  call    ?Release@CVolumeIdEntry@@QEAAKXZ; CVolumeIdEntry::Release(void)
0x1800278e4  mov     rcx, [rdi]; Table
0x1800278e7  mov     dl, 1; Restart
0x1800278e9  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800278ef  mov     rcx, [rdi]; pv
0x1800278f2  test    rax, rax
0x1800278f5  jnz     short loc_1800278D0
0x1800278f7  call    cs:__imp_CoTaskMemFree
0x1800278fd  mov     qword ptr [rdi], 0
0x180027904  mov     ecx, 68h ; 'h'; cb
0x180027909  call    cs:__imp_CoTaskMemAlloc
0x18002790f  mov     [rdi], rax
0x180027912  test    rax, rax
0x180027915  jnz     short loc_18002791E
0x180027917  mov     ebx, 8007000Eh
0x18002791c  jmp     short loc_180027943
0x18002791e  xor     ebx, ebx
0x180027920  mov     [rsp+38h+TableContext], rdi; TableContext
0x180027925  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18002792c  mov     rcx, rax; Table
0x18002792f  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180027936  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18002793d  call    cs:__imp_RtlInitializeGenericTableAvl
0x180027943  mov     eax, ebx
0x180027945  mov     rbx, [rsp+38h+arg_0]
0x18002794a  add     rsp, 30h
0x18002794e  pop     rdi
0x18002794f  retn
```
