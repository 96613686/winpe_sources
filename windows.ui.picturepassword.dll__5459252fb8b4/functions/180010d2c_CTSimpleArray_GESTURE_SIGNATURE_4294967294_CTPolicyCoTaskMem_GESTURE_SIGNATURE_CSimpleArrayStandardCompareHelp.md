# CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::RemoveAll(void)

- ea: `0x180010d2c`
- end: `0x180010d69`
- name: `?RemoveAll@?$CTSimpleArray@UGESTURE_SIGNATURE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardCompareHelper@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardMergeHelper@UGESTURE_SIGNATURE@@@@@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d0f0`
- `0x180012d7c`
- `0x180013f60`
- `0x180014938`
- `0x1800149e4`

## callees

- `0x180010d2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010d41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010d41`

## pseudocode

```c
void __fastcall CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::RemoveAll(
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
0x180010d2c  mov     [rsp+arg_0], rbx
0x180010d31  push    rdi
0x180010d32  sub     rsp, 20h
0x180010d36  mov     rbx, rcx
0x180010d39  mov     rcx, [rcx]; pv
0x180010d3c  test    rcx, rcx
0x180010d3f  jz      short loc_180010D4E
0x180010d41  call    cs:__imp_CoTaskMemFree
0x180010d47  mov     qword ptr [rbx], 0
0x180010d4e  mov     qword ptr [rbx+8], 0
0x180010d56  mov     qword ptr [rbx+18h], 0
0x180010d5e  mov     rbx, [rsp+28h+arg_0]
0x180010d63  add     rsp, 20h
0x180010d67  pop     rdi
0x180010d68  retn
```
