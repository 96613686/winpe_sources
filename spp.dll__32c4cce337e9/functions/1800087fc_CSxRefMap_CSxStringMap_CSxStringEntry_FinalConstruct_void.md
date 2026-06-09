# CSxRefMap<CSxStringMap,CSxStringEntry>::FinalConstruct(void)

- ea: `0x1800087fc`
- end: `0x18000889c`
- name: `?FinalConstruct@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007544`

## callees

- `0x1800087fc`
- `0x18000e308`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180008889`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180008889`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180008835`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180008835`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180008822`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180008822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008855`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSxStringMap,CSxStringEntry>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeEntry *v3; // rbx
  CVolumeEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CVolumeEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CVolumeEntry::Release(v3);
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
0x1800087fc  mov     [rsp+arg_0], rbx
0x180008801  push    rdi
0x180008802  sub     rsp, 30h
0x180008806  mov     rdi, rcx
0x180008809  lock inc dword ptr [rcx+8]
0x18000880d  cmp     qword ptr [rcx], 0
0x180008811  jz      short loc_180008850
0x180008813  lock inc dword ptr [rcx+8]
0x180008817  mov     rcx, [rcx]
0x18000881a  jmp     short loc_180008833
0x18000881c  mov     rbx, [rax]
0x18000881f  mov     rdx, rax; Buffer
0x180008822  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180008828  mov     rcx, rbx; this
0x18000882b  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180008830  mov     rcx, [rdi]; Table
0x180008833  mov     dl, 1; Restart
0x180008835  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000883b  mov     rcx, [rdi]; pv
0x18000883e  test    rax, rax
0x180008841  jnz     short loc_18000881C
0x180008843  call    cs:__imp_CoTaskMemFree
0x180008849  mov     qword ptr [rdi], 0
0x180008850  mov     ecx, 68h ; 'h'; cb
0x180008855  call    cs:__imp_CoTaskMemAlloc
0x18000885b  mov     [rdi], rax
0x18000885e  test    rax, rax
0x180008861  jnz     short loc_18000886A
0x180008863  mov     ebx, 8007000Eh
0x180008868  jmp     short loc_18000888F
0x18000886a  xor     ebx, ebx
0x18000886c  mov     [rsp+38h+TableContext], rdi; TableContext
0x180008871  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSppStringMap@@VCSppStringMapEntry@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180008878  mov     rcx, rax; Table
0x18000887b  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCVolumeIdMap@@VCVolumeIdEntry@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180008882  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180008889  call    cs:__imp_RtlInitializeGenericTableAvl
0x18000888f  mov     eax, ebx
0x180008891  mov     rbx, [rsp+38h+arg_0]
0x180008896  add     rsp, 30h
0x18000889a  pop     rdi
0x18000889b  retn
```
