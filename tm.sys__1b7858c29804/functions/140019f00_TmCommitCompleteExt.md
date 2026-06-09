# TmCommitCompleteExt

- ea: `0x140019f00`
- end: `0x140019f82`
- name: `TmCommitCompleteExt`
- size: `130`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012cb0`
- `0x14001c4a0`

## callees

- `0x14001a000`

## pseudocode

```c
NTSTATUS __stdcall TmCommitCompleteExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  _DWORD v3[4]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v4[2]; // [rsp+50h] [rbp-10h] BYREF
  int v5; // [rsp+80h] [rbp+20h] BYREF
  int v6; // [rsp+84h] [rbp+24h]
  int v7; // [rsp+88h] [rbp+28h] BYREF
  int v8; // [rsp+8Ch] [rbp+2Ch]

  v3[2] = 264;
  v3[0] = 260;
  v3[1] = 260;
  v3[3] = 261;
  v4[0] = TmpTxActionDoCommitComplete;
  v4[1] = TmpTxActionDoCommitComplete;
  v5 = 1;
  v6 = 1;
  v7 = 7;
  v8 = 5;
  return TmpProcessNotificationResponse(Enlistment, (__int64)v3, (__int64)&v7, (__int64)v4, (__int64)&v5);
}

```

## disassembly

```asm
0x140019f00  mov     r11, rsp
0x140019f03  push    rbp
0x140019f04  mov     rbp, rsp
0x140019f07  sub     rsp, 60h
0x140019f0b  mov     eax, 104h
0x140019f10  mov     [rbp+var_18], 108h
0x140019f17  mov     [rbp+var_20], eax
0x140019f1a  lea     r9, [rbp+var_18]
0x140019f1e  mov     [rbp+var_1C], eax
0x140019f21  mov     r8d, 2
0x140019f27  lea     rax, TmpTxActionDoCommitComplete
0x140019f2e  mov     [rbp+var_14], 105h
0x140019f35  mov     [rbp+var_10], rax
0x140019f39  mov     [rbp+var_8], rax
0x140019f3d  mov     eax, 1
0x140019f42  mov     [rbp+arg_10], eax
0x140019f45  mov     [rbp+arg_14], eax
0x140019f48  lea     rax, [rbp+arg_10]
0x140019f4c  mov     [r11-30h], rax
0x140019f50  lea     rax, [rbp+var_10]
0x140019f54  mov     [r11-38h], rax
0x140019f58  lea     rax, [rbp+arg_18]
0x140019f5c  mov     [r11-40h], rax
0x140019f60  lea     rax, [rbp+var_20]
0x140019f64  mov     [r11-48h], rax
0x140019f68  mov     [rbp+arg_18], 7
0x140019f6f  mov     [rbp+arg_1C], 5
0x140019f76  call    TmpProcessNotificationResponse
0x140019f7b  add     rsp, 60h
0x140019f7f  pop     rbp
0x140019f80  retn
```
