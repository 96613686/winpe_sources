# McTemplateU0idq_EventWriteTransfer

- ea: `0x180003558`
- end: `0x1800035cc`
- name: `McTemplateU0idq_EventWriteTransfer`
- size: `116`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, int, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002270`

## callees

- `0x180004084`
- `0x18000fa00`

## pseudocode

```c
ULONG __fastcall McTemplateU0idq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  char *v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  __int64 v13; // [rsp+A0h] [rbp+20h] BYREF
  int v14; // [rsp+A8h] [rbp+28h] BYREF

  v14 = a4;
  v13 = a3;
  v8 = 8;
  v10 = 4;
  v7 = &v13;
  v9 = &v14;
  v11 = &a5;
  v12 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 4u, &v6);
}

```

## disassembly

```asm
0x180003558  mov     [rsp-8+arg_18], r9d
0x18000355d  mov     [rsp-8+arg_10], r8
0x180003562  push    rbp
0x180003563  mov     rbp, rsp
0x180003566  sub     rsp, 80h
0x18000356d  mov     rax, cs:__security_cookie
0x180003574  xor     rax, rsp
0x180003577  mov     [rbp+var_10], rax
0x18000357b  mov     r9d, 4
0x180003581  mov     [rbp+var_38], 8
0x180003589  lea     rax, [rbp+arg_10]
0x18000358d  mov     [rbp+var_28], r9
0x180003591  mov     [rbp+var_40], rax
0x180003595  lea     rax, [rbp+arg_18]
0x180003599  mov     [rbp+var_30], rax
0x18000359d  lea     rax, [rbp+arg_20]
0x1800035a1  mov     [rbp+var_20], rax
0x1800035a5  lea     rax, [rbp+var_50]
0x1800035a9  mov     [rsp+80h+var_60], rax
0x1800035ae  mov     [rbp+var_18], r9
0x1800035b2  call    McGenEventWrite_EventWriteTransfer
0x1800035b7  mov     rcx, [rbp+var_10]
0x1800035bb  xor     rcx, rsp; StackCookie
0x1800035be  call    __security_check_cookie
0x1800035c3  add     rsp, 80h
0x1800035ca  pop     rbp
0x1800035cb  retn
```
