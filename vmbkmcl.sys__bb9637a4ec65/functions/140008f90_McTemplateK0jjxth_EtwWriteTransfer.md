# McTemplateK0jjxth_EtwWriteTransfer

- ea: `0x140008f90`
- end: `0x140009022`
- name: `McTemplateK0jjxth_EtwWriteTransfer`
- size: `146`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026f0`
- `0x1400037e0`
- `0x140003f40`
- `0x140004cc0`
- `0x140005300`
- `0x140005750`

## callees

- `0x140008e18`
- `0x140011e90`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jjxth_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        char a7,
        char a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+40h] [rbp-29h]
  __int64 v11; // [rsp+48h] [rbp-21h]
  __int64 v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  char *v14; // [rsp+60h] [rbp-9h]
  __int64 v15; // [rsp+68h] [rbp-1h]
  char *v16; // [rsp+70h] [rbp+7h]
  __int64 v17; // [rsp+78h] [rbp+Fh]
  char *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  v12 = a5;
  v14 = &a6;
  v16 = &a7;
  v18 = &a8;
  v10 = a4;
  v11 = 16;
  v13 = 16;
  v15 = 8;
  v17 = 4;
  v19 = 2;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 6u, &v9);
}

```

## disassembly

```asm
0x140008f90  push    rbp
0x140008f92  lea     rbp, [rsp-37h]
0x140008f97  sub     rsp, 0A0h
0x140008f9e  mov     rax, cs:__security_cookie
0x140008fa5  xor     rax, rsp
0x140008fa8  mov     [rbp+37h+var_10], rax
0x140008fac  mov     rax, [rbp+37h+arg_20]
0x140008fb0  mov     [rbp+37h+var_50], rax
0x140008fb4  lea     rax, [rbp+37h+arg_28]
0x140008fb8  mov     [rbp+37h+var_40], rax
0x140008fbc  lea     rax, [rbp+37h+arg_30]
0x140008fc0  mov     [rbp+37h+var_30], rax
0x140008fc4  lea     rax, [rbp+37h+arg_38]
0x140008fc8  mov     [rbp+37h+var_20], rax
0x140008fcc  lea     rax, [rbp+37h+var_70]
0x140008fd0  mov     [rbp+37h+var_60], r9
0x140008fd4  mov     r9d, 6
0x140008fda  mov     [rsp+0A0h+var_80], rax
0x140008fdf  mov     [rbp+37h+var_58], 10h
0x140008fe7  mov     [rbp+37h+var_48], 10h
0x140008fef  mov     [rbp+37h+var_38], 8
0x140008ff7  mov     [rbp+37h+var_28], 4
0x140008fff  mov     [rbp+37h+var_18], 2
0x140009007  call    McGenEventWrite_EtwWriteTransfer
0x14000900c  mov     rcx, [rbp+37h+var_10]
0x140009010  xor     rcx, rsp; StackCookie
0x140009013  call    __security_check_cookie
0x140009018  add     rsp, 0A0h
0x14000901f  pop     rbp
0x140009020  retn
```
