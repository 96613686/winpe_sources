# TmPrepareCompleteExt

- ea: `0x140019f90`
- end: `0x140019ff7`
- name: `TmPrepareCompleteExt`
- size: `103`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001a000`

## pseudocode

```c
NTSTATUS __stdcall TmPrepareCompleteExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  _DWORD v3[2]; // [rsp+40h] [rbp-18h] BYREF
  __int64 (__fastcall *v4[2])(__int64); // [rsp+48h] [rbp-10h] BYREF
  int v5; // [rsp+70h] [rbp+18h] BYREF
  int v6; // [rsp+78h] [rbp+20h] BYREF

  v3[1] = 257;
  v4[0] = TmpTxActionDoPrepareComplete;
  v3[0] = 258;
  v6 = 2;
  v5 = 0;
  return TmpProcessNotificationResponse(Enlistment, (__int64)v3, (__int64)&v6, (__int64)v4, (__int64)&v5);
}

```

## disassembly

```asm
0x140019f90  mov     r11, rsp
0x140019f93  sub     rsp, 58h
0x140019f97  lea     rax, TmpTxActionDoPrepareComplete
0x140019f9e  mov     [rsp+58h+var_14], 101h
0x140019fa6  mov     [r11-10h], rax
0x140019faa  lea     r9, [r11-14h]
0x140019fae  lea     rax, [r11+18h]
0x140019fb2  mov     [rsp+58h+var_18], 102h
0x140019fba  mov     [r11-20h], rax
0x140019fbe  mov     r8d, 1
0x140019fc4  lea     rax, [r11-10h]
0x140019fc8  mov     [rsp+58h+arg_18], 2
0x140019fd0  mov     [r11-28h], rax
0x140019fd4  lea     rax, [r11+20h]
0x140019fd8  mov     [r11-30h], rax
0x140019fdc  lea     rax, [r11-18h]
0x140019fe0  mov     [r11-38h], rax
0x140019fe4  mov     [rsp+58h+arg_10], 0
0x140019fec  call    TmpProcessNotificationResponse
0x140019ff1  add     rsp, 58h
0x140019ff5  retn
```
