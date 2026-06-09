# CTSimpleArray<int,4294967294,CTPolicyCoTaskMem<int>,CSimpleArrayStandardCompareHelper<int>,CSimpleArrayStandardMergeHelper<int>>::Sort(void)

- ea: `0x1800231f0`
- end: `0x180023281`
- name: `?Sort@?$CTSimpleArray@H$0PPPPPPPO@V?$CTPolicyCoTaskMem@H@@V?$CSimpleArrayStandardCompareHelper@H@@V?$CSimpleArrayStandardMergeHelper@H@@@@QEAAJXZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022698`

## callees

- `0x18000e8d8`
- `0x18000eb30`
- `0x18002150c`
- `0x1800231f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023262`

## pseudocode

```c
__int64 __fastcall CTSimpleArray<int,4294967294,CTPolicyCoTaskMem<int>,CSimpleArrayStandardCompareHelper<int>,CSimpleArrayStandardMergeHelper<int>>::Sort(
        __int64 a1)
{
  unsigned __int64 v2; // rcx
  int v3; // ebx
  LPVOID *v4; // rsi
  unsigned int v5; // edx
  void *v6; // rcx
  char v8; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  v2 = *(_QWORD *)(a1 + 8);
  v3 = 0;
  if ( v2 > 1 )
  {
    v4 = (LPVOID *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = 0;
    v9 = 0;
    v3 = ULongLongMult(v2 >> 1, 4u, &v9);
    if ( v3 >= 0 )
      v3 = CTCoAllocPolicy::Realloc(v6, v5, 0, v9, (void **)(a1 + 16));
    if ( v3 >= 0 )
    {
      CTSimpleArray<int,4294967294,CTPolicyCoTaskMem<int>,CSimpleArrayStandardCompareHelper<int>,CSimpleArrayStandardMergeHelper<int>>::_MergeSort<CSimpleArrayStandardCompareHelper<int>>(
        a1,
        (__int64)&v8,
        0,
        *(_QWORD *)(a1 + 8));
      CoTaskMemFree(*v4);
      *v4 = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800231f0  mov     rax, rsp
0x1800231f3  mov     [rax+18h], rbx
0x1800231f7  mov     [rax+20h], rsi
0x1800231fb  push    rdi
0x1800231fc  sub     rsp, 30h
0x180023200  mov     rdi, rcx
0x180023203  mov     byte ptr [rax+8], 0
0x180023207  mov     rcx, [rcx+8]
0x18002320b  xor     ebx, ebx
0x18002320d  cmp     rcx, 1
0x180023211  jbe     short loc_18002326F
0x180023213  lea     rsi, [rdi+10h]
0x180023217  shr     rcx, 1; unsigned __int64
0x18002321a  lea     r8, [rax+10h]; unsigned __int64 *
0x18002321e  mov     [rsi], rbx
0x180023221  lea     edx, [rbx+4]; unsigned __int64
0x180023224  mov     [rax+10h], rbx
0x180023228  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002322d  mov     ebx, eax
0x18002322f  test    eax, eax
0x180023231  js      short loc_180023247
0x180023233  mov     r9, [rsp+38h+arg_8]; unsigned __int64
0x180023238  xor     r8d, r8d; void *
0x18002323b  mov     [rsp+38h+var_18], rsi; void **
0x180023240  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x180023245  mov     ebx, eax
0x180023247  test    ebx, ebx
0x180023249  js      short loc_18002326F
0x18002324b  mov     r9, [rdi+8]
0x18002324f  lea     rdx, [rsp+38h+arg_0]
0x180023254  xor     r8d, r8d
0x180023257  mov     rcx, rdi
0x18002325a  call    ??$_MergeSort@V?$CSimpleArrayStandardCompareHelper@H@@@?$CTSimpleArray@H$0PPPPPPPO@V?$CTPolicyCoTaskMem@H@@V?$CSimpleArrayStandardCompareHelper@H@@V?$CSimpleArrayStandardMergeHelper@H@@@@QEAAXAEBV?$CSimpleArrayStandardCompareHelper@H@@_K1@Z; CTSimpleArray<int,4294967294,CTPolicyCoTaskMem<int>,CSimpleArrayStandardCompareHelper<int>,CSimpleArrayStandardMergeHelper<int>>::_MergeSort<CSimpleArrayStandardCompareHelper<int>>(CSimpleArrayStandardCompareHelper<int> const &,unsigned __int64,unsigned __int64)
0x18002325f  mov     rcx, [rsi]; pv
0x180023262  call    cs:__imp_CoTaskMemFree
0x180023268  mov     qword ptr [rsi], 0
0x18002326f  mov     rsi, [rsp+38h+arg_18]
0x180023274  mov     eax, ebx
0x180023276  mov     rbx, [rsp+38h+arg_10]
0x18002327b  add     rsp, 30h
0x18002327f  pop     rdi
0x180023280  retn
```
