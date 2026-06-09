# CSxRefMap<CSdMediaMap,CSdMedia>::FinalConstruct(void)

- ea: `0x180024ffc`
- end: `0x18002509c`
- name: `?FinalConstruct@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023a40`

## callees

- `0x180024ffc`
- `0x180026700`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180025089`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180025089`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180025035`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180025035`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025022`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025022`
- `ole32!CoTaskMemFree` at `0x180025043`
- `ole32!CoTaskMemFree` at `0x180025043`
- `ole32!CoTaskMemAlloc` at `0x180025055`
- `ole32!CoTaskMemAlloc` at `0x180025055`

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
0x180024ffc  mov     [rsp+arg_0], rbx
0x180025001  push    rdi
0x180025002  sub     rsp, 30h
0x180025006  mov     rdi, rcx
0x180025009  lock inc dword ptr [rcx+8]
0x18002500d  cmp     qword ptr [rcx], 0
0x180025011  jz      short loc_180025050
0x180025013  lock inc dword ptr [rcx+8]
0x180025017  mov     rcx, [rcx]
0x18002501a  jmp     short loc_180025033
0x18002501c  mov     rbx, [rax]
0x18002501f  mov     rdx, rax; Buffer
0x180025022  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180025028  mov     rcx, rbx; this
0x18002502b  call    ?Release@CSdMedia@@QEAAKXZ; CSdMedia::Release(void)
0x180025030  mov     rcx, [rdi]; Table
0x180025033  mov     dl, 1; Restart
0x180025035  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18002503b  mov     rcx, [rdi]; pv
0x18002503e  test    rax, rax
0x180025041  jnz     short loc_18002501C
0x180025043  call    cs:__imp_CoTaskMemFree
0x180025049  mov     qword ptr [rdi], 0
0x180025050  mov     ecx, 68h ; 'h'; cb
0x180025055  call    cs:__imp_CoTaskMemAlloc
0x18002505b  mov     [rdi], rax
0x18002505e  test    rax, rax
0x180025061  jnz     short loc_18002506A
0x180025063  mov     ebx, 8007000Eh
0x180025068  jmp     short loc_18002508F
0x18002506a  xor     ebx, ebx
0x18002506c  mov     [rsp+38h+TableContext], rdi; TableContext
0x180025071  lea     r9, ?_FreeRoutine@?$CSxRefMap@VCSdMediaMapFinder@@VCSdMedia@@@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180025078  mov     rcx, rax; Table
0x18002507b  lea     r8, ?_AllocateRoutine@?$CSxRefMap@VCSxDirRuleMap@@VCSxDirRule@@@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180025082  lea     rdx, ?_CompareRoutine@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180025089  call    cs:__imp_RtlInitializeGenericTableAvl
0x18002508f  mov     eax, ebx
0x180025091  mov     rbx, [rsp+38h+arg_0]
0x180025096  add     rsp, 30h
0x18002509a  pop     rdi
0x18002509b  retn
```
