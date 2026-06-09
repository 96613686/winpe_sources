# CSxRefMap<CSdStringIndexMap,CSdStringIndexEntry>::FinalConstruct(void)

- ea: `0x180049728`
- end: `0x1800497e7`
- name: `?FinalConstruct@?$CSxRefMap@VCSdStringIndexMap@@VCSdStringIndexEntry@@@@AEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004969c`

## callees

- `0x180049728`
- `0x18004c528`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800497cd`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800497cd`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180049767`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180049767`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004974e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004974e`
- `ole32!CoTaskMemFree` at `0x18004977b`
- `ole32!CoTaskMemFree` at `0x18004977b`
- `ole32!CoTaskMemAlloc` at `0x180049793`
- `ole32!CoTaskMemAlloc` at `0x180049793`

## pseudocode

```c
__int64 __fastcall CSxRefMap<CSdStringIndexMap,CSdStringIndexEntry>::FinalConstruct(
        volatile signed __int32 *TableContext)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSdStringIndexEntry *v3; // rbx
  CSdStringIndexEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  struct _RTL_AVL_TABLE *v6; // rax
  unsigned int v7; // ebx

  _InterlockedIncrement(TableContext + 2);
  if ( *(_QWORD *)TableContext )
  {
    _InterlockedIncrement(TableContext + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)TableContext; ; i = *(struct _RTL_AVL_TABLE **)TableContext )
    {
      v4 = (CSdStringIndexEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)TableContext;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSdStringIndexEntry::Release(v3);
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
      CSxRefMap<CSxStringMap,CSxStringEntry>::_CompareRoutine,
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
0x180049728  mov     [rsp+arg_0], rbx
0x18004972d  push    rdi
0x18004972e  sub     rsp, 30h
0x180049732  mov     rdi, rcx
0x180049735  lock inc dword ptr [rcx+8]
0x180049739  cmp     qword ptr [rcx], 0
0x18004973d  jz      short loc_18004978E
0x18004973f  lock inc dword ptr [rcx+8]
0x180049743  mov     rcx, [rcx]
0x180049746  jmp     short loc_180049765
0x180049748  mov     rbx, [rax]
0x18004974b  mov     rdx, rax; Buffer
0x18004974e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180049755  nop     dword ptr [rax+rax+00h]
0x18004975a  mov     rcx, rbx; this
0x18004975d  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x180049762  mov     rcx, [rdi]; Table
0x180049765  mov     dl, 1; Restart
0x180049767  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18004976e  nop     dword ptr [rax+rax+00h]
0x180049773  mov     rcx, [rdi]; pv
0x180049776  test    rax, rax
0x180049779  jnz     short loc_180049748
0x18004977b  call    cs:__imp_CoTaskMemFree
0x180049782  nop     dword ptr [rax+rax+00h]
0x180049787  mov     qword ptr [rdi], 0
0x18004978e  mov     ecx, 68h ; 'h'; cb
0x180049793  call    cs:__imp_CoTaskMemAlloc
0x18004979a  nop     dword ptr [rax+rax+00h]
0x18004979f  mov     [rdi], rax
0x1800497a2  test    rax, rax
0x1800497a5  jnz     short loc_1800497AE
0x1800497a7  mov     ebx, 8007000Eh
0x1800497ac  jmp     short loc_1800497D9
0x1800497ae  xor     ebx, ebx
0x1800497b0  mov     [rsp+38h+TableContext], rdi; TableContext
0x1800497b5  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800497bc  mov     rcx, rax; Table
0x1800497bf  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800497c6  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800497cd  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800497d4  nop     dword ptr [rax+rax+00h]
0x1800497d9  mov     eax, ebx
0x1800497db  mov     rbx, [rsp+38h+arg_0]
0x1800497e0  add     rsp, 30h
0x1800497e4  pop     rdi
0x1800497e5  retn
```
