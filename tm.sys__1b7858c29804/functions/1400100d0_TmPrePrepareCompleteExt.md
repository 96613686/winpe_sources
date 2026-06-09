# TmPrePrepareCompleteExt

- ea: `0x1400100d0`
- end: `0x140010137`
- name: `TmPrePrepareCompleteExt`
- size: `103`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001a000`

## pseudocode

```c
NTSTATUS __stdcall TmPrePrepareCompleteExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  _DWORD v3[2]; // [rsp+40h] [rbp-18h] BYREF
  __int64 (__fastcall *v4[2])(__int64); // [rsp+48h] [rbp-10h] BYREF
  int v5; // [rsp+70h] [rbp+18h] BYREF
  int v6; // [rsp+78h] [rbp+20h] BYREF

  v3[1] = 266;
  v4[0] = TmpTxActionDoPrePrepareComplete;
  v3[0] = 273;
  v6 = 8;
  v5 = 2;
  return TmpProcessNotificationResponse(Enlistment, (__int64)v3, (__int64)&v6, (__int64)v4, (__int64)&v5);
}

```

## disassembly

```asm
0x1400100d0  mov     r11, rsp
0x1400100d3  sub     rsp, 58h
0x1400100d7  lea     rax, TmpTxActionDoPrePrepareComplete
0x1400100de  mov     [rsp+58h+var_14], 10Ah
0x1400100e6  mov     [r11-10h], rax
0x1400100ea  lea     r9, [r11-14h]
0x1400100ee  lea     rax, [r11+18h]
0x1400100f2  mov     [rsp+58h+var_18], 111h
0x1400100fa  mov     [r11-20h], rax
0x1400100fe  mov     r8d, 1
0x140010104  lea     rax, [r11-10h]
0x140010108  mov     [rsp+58h+arg_18], 8
0x140010110  mov     [r11-28h], rax
0x140010114  lea     rax, [r11+20h]
0x140010118  mov     [r11-30h], rax
0x14001011c  lea     rax, [r11-18h]
0x140010120  mov     [r11-38h], rax
0x140010124  mov     [rsp+58h+arg_10], 2
0x14001012c  call    TmpProcessNotificationResponse
0x140010131  add     rsp, 58h
0x140010135  retn
```
