# CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::RemoveAll(void)

- ea: `0x1800728e4`
- end: `0x180072921`
- name: `?RemoveAll@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006a510`
- `0x18006ad9c`

## callees

- `0x1800728e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800728f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800728f9`

## pseudocode

```c
void __fastcall CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::RemoveAll(
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
0x1800728e4  mov     [rsp+arg_0], rbx
0x1800728e9  push    rdi
0x1800728ea  sub     rsp, 20h
0x1800728ee  mov     rbx, rcx
0x1800728f1  mov     rcx, [rcx]; pv
0x1800728f4  test    rcx, rcx
0x1800728f7  jz      short loc_180072906
0x1800728f9  call    cs:__imp_CoTaskMemFree
0x1800728ff  mov     qword ptr [rbx], 0
0x180072906  mov     qword ptr [rbx+8], 0
0x18007290e  mov     qword ptr [rbx+18h], 0
0x180072916  mov     rbx, [rsp+28h+arg_0]
0x18007291b  add     rsp, 20h
0x18007291f  pop     rdi
0x180072920  retn
```
