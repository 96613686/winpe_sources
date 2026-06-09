# TmRollbackCompleteExt

- ea: `0x140019da0`
- end: `0x140019e40`
- name: `TmRollbackCompleteExt`
- size: `160`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013ab0`
- `0x14001c4a0`

## callees

- `0x14001a000`

## pseudocode

```c
NTSTATUS __stdcall TmRollbackCompleteExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  __int64 v3; // [rsp+48h] [rbp-9h] BYREF
  int v4; // [rsp+50h] [rbp-1h]
  _DWORD v5[4]; // [rsp+58h] [rbp+7h] BYREF
  __int64 v6; // [rsp+68h] [rbp+17h] BYREF
  int v7; // [rsp+70h] [rbp+1Fh]
  int v8; // [rsp+78h] [rbp+27h]
  int v9; // [rsp+7Ch] [rbp+2Bh]
  int v10; // [rsp+80h] [rbp+2Fh]
  _QWORD v11[4]; // [rsp+88h] [rbp+37h] BYREF

  v8 = 264;
  v9 = 269;
  v10 = 269;
  v5[0] = 7;
  v6 = 0x10700000107LL;
  v7 = 263;
  v11[0] = TmpTxActionDoRollbackComplete;
  v11[1] = TmpTxActionDoRollbackComplete;
  v11[2] = TmpTxActionDoRollbackComplete;
  v5[1] = 6;
  v5[2] = 9;
  v3 = 1;
  v4 = 0;
  return TmpProcessNotificationResponse(Enlistment, (__int64)&v6, (__int64)v5, (__int64)v11, (__int64)&v3);
}

```

## disassembly

```asm
0x140019da0  mov     r11, rsp
0x140019da3  push    rbp
0x140019da4  lea     rbp, [r11-5Fh]
0x140019da8  sub     rsp, 0A0h
0x140019daf  mov     eax, 10Dh
0x140019db4  mov     [rbp+57h+var_30], 108h
0x140019dbb  mov     [rbp+57h+var_2C], eax
0x140019dbe  lea     r9, [rbp+57h+var_30]
0x140019dc2  mov     [rbp+57h+var_28], eax
0x140019dc5  mov     r8d, 3
0x140019dcb  mov     eax, 107h
0x140019dd0  mov     [rbp+57h+var_50], 7
0x140019dd7  mov     dword ptr [rbp+57h+var_40], eax
0x140019dda  mov     dword ptr [rbp+57h+var_40+4], eax
0x140019ddd  mov     [rbp+57h+var_38], eax
0x140019de0  lea     rax, TmpTxActionDoRollbackComplete
0x140019de7  mov     [rbp+57h+var_20], rax
0x140019deb  mov     [rbp+57h+var_18], rax
0x140019def  mov     [rbp+57h+var_10], rax
0x140019df3  lea     rax, [rbp+57h+var_60]
0x140019df7  mov     [r11-70h], rax
0x140019dfb  lea     rax, [rbp+57h+var_20]
0x140019dff  mov     [r11-78h], rax
0x140019e03  lea     rax, [rbp+57h+var_50]
0x140019e07  mov     [r11-80h], rax
0x140019e0b  lea     rax, [rbp+57h+var_40]
0x140019e0f  mov     [rsp+20h], rax; __int64
0x140019e14  mov     [rbp+57h+var_4C], 6
0x140019e1b  mov     [rbp+57h+var_48], 9
0x140019e22  mov     [rbp+57h+var_60], 1
0x140019e2a  mov     [rbp+57h+var_58], 0
0x140019e31  call    TmpProcessNotificationResponse
0x140019e36  add     rsp, 0A0h
0x140019e3d  pop     rbp
0x140019e3e  retn
```
