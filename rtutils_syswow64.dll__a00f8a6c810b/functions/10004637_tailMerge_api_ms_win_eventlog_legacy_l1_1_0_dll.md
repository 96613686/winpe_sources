# __tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll

- ea: `0x10004637`
- end: `0x10004648`
- name: `__tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll`
- size: `17`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1000462d`
- `0x1000464e`
- `0x1000465e`
- `0x1000466e`
- `0x1000467e`

## callees

- `0x1000a6a1`

## pseudocode

```c
int __usercall _tailMerge_api_ms_win_eventlog_legacy_l1_1_0_dll@<eax>(int a1@<eax>, int a2@<edx>, int a3@<ecx>)
{
  int (__fastcall *Helper2)(int, int); // eax

  Helper2 = (int (__fastcall *)(int, int))__delayLoadHelper2(
                                            &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventlog_legacy_l1_1_0_dll,
                                            a1);
  return Helper2(a3, a2);
}

```

## disassembly

```asm
0x10004637  push    ecx
0x10004638  push    edx
0x10004639  push    eax
0x1000463a  push    offset __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventlog_legacy_l1_1_0_dll
0x1000463f  call    ___delayLoadHelper2@8; __delayLoadHelper2(x,x)
0x10004644  pop     edx
0x10004645  pop     ecx
0x10004646  jmp     eax
```
