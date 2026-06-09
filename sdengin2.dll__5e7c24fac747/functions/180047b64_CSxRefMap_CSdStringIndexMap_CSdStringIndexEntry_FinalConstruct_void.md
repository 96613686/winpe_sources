# CSxRefMap<CSdStringIndexMap,CSdStringIndexEntry>::FinalConstruct(void)

- ea: `0x180047b64`
- end: `0x180047c04`
- name: `?FinalConstruct@?$CSxRefMap@VCSdStringIndexMap@@VCSdStringIndexEntry@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180047ad8`

## callees

- `0x180047b64`
- `0x18004a878`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180047bf1`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180047bf1`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180047b9d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180047b9d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180047b8a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180047b8a`
- `ole32!CoTaskMemFree` at `0x180047bab`
- `ole32!CoTaskMemFree` at `0x180047bab`
- `ole32!CoTaskMemAlloc` at `0x180047bbd`
- `ole32!CoTaskMemAlloc` at `0x180047bbd`

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
0x180047b64  mov     [rsp+arg_0], rbx
0x180047b69  push    rdi
0x180047b6a  sub     rsp, 30h
0x180047b6e  mov     rdi, rcx
0x180047b71  lock inc dword ptr [rcx+8]
0x180047b75  cmp     qword ptr [rcx], 0
0x180047b79  jz      short loc_180047BB8
0x180047b7b  lock inc dword ptr [rcx+8]
0x180047b7f  mov     rcx, [rcx]
0x180047b82  jmp     short loc_180047B9B
0x180047b84  mov     rbx, [rax]
0x180047b87  mov     rdx, rax; Buffer
0x180047b8a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180047b90  mov     rcx, rbx; this
0x180047b93  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x180047b98  mov     rcx, [rdi]; Table
0x180047b9b  mov     dl, 1; Restart
0x180047b9d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180047ba3  mov     rcx, [rdi]; pv
0x180047ba6  test    rax, rax
0x180047ba9  jnz     short loc_180047B84
0x180047bab  call    cs:__imp_CoTaskMemFree
0x180047bb1  mov     qword ptr [rdi], 0
0x180047bb8  mov     ecx, 68h ; 'h'; cb
0x180047bbd  call    cs:__imp_CoTaskMemAlloc
0x180047bc3  mov     [rdi], rax
0x180047bc6  test    rax, rax
0x180047bc9  jnz     short loc_180047BD2
0x180047bcb  mov     ebx, 8007000Eh
0x180047bd0  jmp     short loc_180047BF7
0x180047bd2  xor     ebx, ebx
0x180047bd4  mov     [rsp+38h+TableContext], rdi; TableContext
0x180047bd9  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180047be0  mov     rcx, rax; Table
0x180047be3  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180047bea  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180047bf1  call    cs:__imp_RtlInitializeGenericTableAvl
0x180047bf7  mov     eax, ebx
0x180047bf9  mov     rbx, [rsp+38h+arg_0]
0x180047bfe  add     rsp, 30h
0x180047c02  pop     rdi
0x180047c03  retn
```
