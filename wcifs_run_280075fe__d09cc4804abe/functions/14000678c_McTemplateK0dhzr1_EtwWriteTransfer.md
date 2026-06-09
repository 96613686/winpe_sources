# McTemplateK0dhzr1_EtwWriteTransfer

- ea: `0x14000678c`
- end: `0x14000680d`
- name: `McTemplateK0dhzr1_EtwWriteTransfer`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140032d30`

## callees

- `0x140003f40`
- `0x140007c60`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dhzr1_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int16 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  unsigned __int16 *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+6Ch] [rbp-14h]
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v11 = 2;
  v8 = &v15;
  v10 = &a5;
  v12 = a6;
  v9 = 4;
  v13 = 2 * a5;
  v14 = 0;
  return McGenEventWrite_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)WcifsInstanceAttachFailure, a3, 4u, &v7);
}

```

## disassembly

```asm
0x14000678c  mov     [rsp-8+arg_18], r9d
0x140006791  push    rbp
0x140006792  mov     rbp, rsp
0x140006795  sub     rsp, 80h
0x14000679c  mov     rax, cs:__security_cookie
0x1400067a3  xor     rax, rsp
0x1400067a6  mov     [rbp+var_10], rax
0x1400067aa  lea     rax, [rbp+arg_18]
0x1400067ae  mov     [rbp+var_28], 2
0x1400067b6  mov     [rbp+var_40], rax
0x1400067ba  lea     rdx, WcifsInstanceAttachFailure
0x1400067c1  lea     rax, [rbp+arg_20]
0x1400067c5  mov     r9d, 4
0x1400067cb  mov     [rbp+var_30], rax
0x1400067cf  xor     ecx, ecx
0x1400067d1  mov     rax, [rbp+arg_28]
0x1400067d5  mov     [rbp+var_20], rax
0x1400067d9  movzx   eax, [rbp+arg_20]
0x1400067dd  add     eax, eax
0x1400067df  mov     [rbp+var_38], r9
0x1400067e3  mov     [rbp+var_18], eax
0x1400067e6  lea     rax, [rbp+var_50]
0x1400067ea  mov     [rsp+80h+var_60], rax
0x1400067ef  mov     [rbp+var_14], ecx
0x1400067f2  call    McGenEventWrite_EtwWriteTransfer
0x1400067f7  mov     rcx, [rbp+var_10]
0x1400067fb  xor     rcx, rsp; StackCookie
0x1400067fe  call    __security_check_cookie
0x140006803  add     rsp, 80h
0x14000680a  pop     rbp
0x14000680b  retn
```
