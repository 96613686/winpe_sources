# CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>>::~CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>>(void)

- ea: `0x1800216d0`
- end: `0x18002170d`
- name: `??1?$CCoSimpleArray@H$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@H@@@@QEAA@XZ`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030ed6`
- `0x180030f42`

## callees

- `0x1800216d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800216e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800216e5`

## pseudocode

```c
void __fastcall CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>>::~CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x1800216d0  mov     [rsp+arg_0], rbx
0x1800216d5  push    rdi
0x1800216d6  sub     rsp, 20h
0x1800216da  mov     rbx, rcx
0x1800216dd  mov     rcx, [rcx]; pv
0x1800216e0  test    rcx, rcx
0x1800216e3  jz      short loc_1800216F2
0x1800216e5  call    cs:__imp_CoTaskMemFree
0x1800216eb  mov     qword ptr [rbx], 0
0x1800216f2  mov     qword ptr [rbx+8], 0
0x1800216fa  mov     qword ptr [rbx+18h], 0
0x180021702  mov     rbx, [rsp+28h+arg_0]
0x180021707  add     rsp, 20h
0x18002170b  pop     rdi
0x18002170c  retn
```
