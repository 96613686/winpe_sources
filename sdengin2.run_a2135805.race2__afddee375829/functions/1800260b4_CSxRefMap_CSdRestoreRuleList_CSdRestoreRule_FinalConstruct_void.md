# CSxRefMap<CSdRestoreRuleList,CSdRestoreRule>::FinalConstruct(void)

- ea: `0x1800260b4`
- end: `0x180026173`
- name: `?FinalConstruct@?$CSxRefMap@VCSdRestoreRuleList@@VCSdRestoreRule@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180024b70`

## callees

- `0x180009c0c`
- `0x1800260b4`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180026159`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180026159`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800260f3`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800260f3`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800260da`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800260da`
- `ole32!CoTaskMemFree` at `0x180026107`
- `ole32!CoTaskMemFree` at `0x180026107`
- `ole32!CoTaskMemAlloc` at `0x18002611f`
- `ole32!CoTaskMemAlloc` at `0x18002611f`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSdRestoreRuleList,CSdRestoreRule>::FinalConstruct(volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSdRestoreRule *v3; // rbx
  CSdRestoreRule **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSdRestoreRule **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSdRestoreRule::Release(v3);
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
      CSxRefMap<CSdRestoreRuleList,CSdRestoreRule>::_CompareRoutine,
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
0x1800260b4  mov     [rsp+arg_0], rbx
0x1800260b9  push    rdi
0x1800260ba  sub     rsp, 30h
0x1800260be  mov     rdi, rcx
0x1800260c1  lock inc dword ptr [rcx+8]
0x1800260c5  cmp     qword ptr [rcx], 0
0x1800260c9  jz      short loc_18002611A
0x1800260cb  lock inc dword ptr [rcx+8]
0x1800260cf  mov     rcx, [rcx]
0x1800260d2  jmp     short loc_1800260F1
0x1800260d4  mov     rbx, [rax]
0x1800260d7  mov     rdx, rax; Buffer
0x1800260da  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800260e1  nop     dword ptr [rax+rax+00h]
0x1800260e6  mov     rcx, rbx; this
0x1800260e9  call    ?Release@CSdRestoreRule@@QEAAKXZ; CSdRestoreRule::Release(void)
0x1800260ee  mov     rcx, [rdi]; Table
0x1800260f1  mov     dl, 1; Restart
0x1800260f3  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800260fa  nop     dword ptr [rax+rax+00h]
0x1800260ff  mov     rcx, [rdi]; pv
0x180026102  test    rax, rax
0x180026105  jnz     short loc_1800260D4
0x180026107  call    cs:__imp_CoTaskMemFree
0x18002610e  nop     dword ptr [rax+rax+00h]
0x180026113  mov     qword ptr [rdi], 0
0x18002611a  mov     ecx, 68h ; 'h'; cb
0x18002611f  call    cs:__imp_CoTaskMemAlloc
0x180026126  nop     dword ptr [rax+rax+00h]
0x18002612b  mov     [rdi], rax
0x18002612e  test    rax, rax
0x180026131  jnz     short loc_18002613A
0x180026133  mov     ebx, 8007000Eh
0x180026138  jmp     short loc_180026165
0x18002613a  xor     ebx, ebx
0x18002613c  mov     [rsp+38h+TableContext], rdi; TableContext
0x180026141  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180026148  mov     rcx, rax; Table
0x18002614b  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180026152  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSdRestoreRuleList@@VCSdRestoreRule@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180026159  call    cs:__imp_RtlInitializeGenericTableAvl
0x180026160  nop     dword ptr [rax+rax+00h]
0x180026165  mov     eax, ebx
0x180026167  mov     rbx, [rsp+38h+arg_0]
0x18002616c  add     rsp, 30h
0x180026170  pop     rdi
0x180026171  retn
```
