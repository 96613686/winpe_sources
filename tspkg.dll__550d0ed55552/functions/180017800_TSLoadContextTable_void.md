# TSLoadContextTable(void)

- ea: `0x180017800`
- end: `0x1800178c1`
- name: `?TSLoadContextTable@@YAJXZ`
- size: `193`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017f50`

## callees

- `0x180003e00`
- `0x180017800`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18001783d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18001783d`
- `ntdll!RtlInitializeResource` at `0x180017811`
- `ntdll!RtlInitializeResource` at `0x180017811`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180017899`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180017899`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180017857`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180017857`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180017886`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180017886`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001786a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001786a`
- `ntdll!RtlReleaseResource` at `0x1800178ae`
- `ntdll!RtlReleaseResource` at `0x1800178ae`

## pseudocode

```c
__int64 TSLoadContextTable(void)
{
  RtlInitializeResource(&Resource);
  RtlInitializeGenericTableAvl(&Table, TSContextTableCompare, TSTableAllocate, TSTableFree, 0);
  return 0;
}

```

## disassembly

```asm
0x180017800  mov     [rsp+arg_0], rsi
0x180017805  push    rdi
0x180017806  sub     rsp, 30h
0x18001780a  lea     rcx, Resource; Resource
0x180017811  call    cs:__imp_RtlInitializeResource
0x180017817  nop
0x180017818  mov     [rsp+38h+TableContext], 0; TableContext
0x180017821  lea     r9, ?TSTableFree@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180017828  lea     r8, ?TSTableAllocate@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18001782f  lea     rdx, ?TSContextTableCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180017836  lea     rcx, Table; Table
0x18001783d  call    cs:__imp_RtlInitializeGenericTableAvl
0x180017843  xor     edi, edi
0x180017845  jmp     short loc_18001784C
0x180017847  mov     edi, 0C000009Ah
0x18001784c  test    edi, edi
0x18001784e  jns     short loc_1800178B4
0x180017850  lea     rcx, Table; Table
0x180017857  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18001785d  test    eax, eax
0x18001785f  jz      short loc_1800178B4
0x180017861  mov     dl, 1; Wait
0x180017863  lea     rcx, Resource; Resource
0x18001786a  call    cs:__imp_RtlAcquireResourceExclusive
0x180017870  mov     dl, 1
0x180017872  jmp     short loc_180017892
0x180017874  mov     rcx, [rsi]; struct _TS_CONTEXT *
0x180017877  call    ?TSDereferenceContext@@YAXPEAU_TS_CONTEXT@@@Z; TSDereferenceContext(_TS_CONTEXT *)
0x18001787c  mov     rdx, rsi; Buffer
0x18001787f  lea     rcx, Table; Table
0x180017886  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001788c  test    al, al
0x18001788e  jz      short loc_1800178A7
0x180017890  xor     edx, edx; Restart
0x180017892  lea     rcx, Table; Table
0x180017899  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001789f  test    rax, rax
0x1800178a2  mov     rsi, rax
0x1800178a5  jnz     short loc_180017874
0x1800178a7  lea     rcx, Resource; Resource
0x1800178ae  call    cs:__imp_RtlReleaseResource
0x1800178b4  mov     eax, edi
0x1800178b6  mov     rsi, [rsp+38h+arg_0]
0x1800178bb  add     rsp, 30h
0x1800178bf  pop     rdi
0x1800178c0  retn
```
