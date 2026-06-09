# CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayStandardCompareHelper<ushort *>>::~CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayStandardCompareHelper<ushort *>>(void)

- ea: `0x18006a510`
- end: `0x18006a555`
- name: `??1?$CSimplePointerArray@GV?$CTPolicyCoTaskMem@G@@V?$CSimpleArrayStandardCompareHelper@PEAG@@@@QEAA@XZ`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006a55c`
- `0x18006ad9c`
- `0x1800860f0`

## callees

- `0x18006a510`
- `0x1800728e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a52c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a52c`

## pseudocode

```c
__int64 __fastcall CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayStandardCompareHelper<unsigned short *>>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayStandardCompareHelper<unsigned short *>>(
        _QWORD *a1)
{
  unsigned __int64 i; // rdi

  for ( i = 0; i < a1[1]; ++i )
    CoTaskMemFree(*(LPVOID *)(*a1 + 8 * i));
  CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::RemoveAll(a1);
  return CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::RemoveAll(a1);
}

```

## disassembly

```asm
0x18006a510  mov     [rsp+arg_0], rbx
0x18006a515  push    rdi
0x18006a516  sub     rsp, 20h
0x18006a51a  xor     edi, edi
0x18006a51c  mov     rbx, rcx
0x18006a51f  cmp     [rcx+8], rdi
0x18006a523  jbe     short loc_18006A53B
0x18006a525  mov     rcx, [rbx]
0x18006a528  mov     rcx, [rcx+rdi*8]; pv
0x18006a52c  call    cs:__imp_CoTaskMemFree
0x18006a532  inc     rdi
0x18006a535  cmp     rdi, [rbx+8]
0x18006a539  jb      short loc_18006A525
0x18006a53b  mov     rcx, rbx
0x18006a53e  call    ?RemoveAll@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXXZ; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::RemoveAll(void)
0x18006a543  mov     rcx, rbx
0x18006a546  mov     rbx, [rsp+28h+arg_0]
0x18006a54b  add     rsp, 20h
0x18006a54f  pop     rdi
0x18006a550  jmp     ?RemoveAll@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXXZ; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::RemoveAll(void)
```
