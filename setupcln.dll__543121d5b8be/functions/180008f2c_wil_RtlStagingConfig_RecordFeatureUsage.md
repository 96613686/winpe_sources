# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180008f2c`
- end: `0x180008f5c`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `48`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180011a90`

## callees

- `0x180008f2c`

## import_xrefs

- `ntdll!RtlNotifyFeatureUsage` at `0x180008f51`
- `ntdll!RtlNotifyFeatureUsage` at `0x180008f51`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, __int16 a2, int a3)
{
  int v4; // [rsp+48h] [rbp+20h] BYREF
  __int16 v5; // [rsp+4Ch] [rbp+24h]
  __int16 v6; // [rsp+4Eh] [rbp+26h]

  v6 = 0;
  v4 = a1;
  v5 = a2;
  if ( a3 )
    v6 |= 1u;
  return RtlNotifyFeatureUsage(&v4);
}

```

## disassembly

```asm
0x180008f2c  mov     rax, rsp
0x180008f2f  sub     rsp, 28h
0x180008f33  mov     qword ptr [rax+20h], 0
0x180008f3b  mov     [rax+20h], ecx
0x180008f3e  mov     [rax+24h], dx
0x180008f42  test    r8d, r8d
0x180008f45  jz      short loc_180008F4C
0x180008f47  or      word ptr [rax+26h], 1
0x180008f4c  lea     rcx, [rsp+28h+arg_18]
0x180008f51  call    cs:__imp_RtlNotifyFeatureUsage
0x180008f57  add     rsp, 28h
0x180008f5b  retn
```
