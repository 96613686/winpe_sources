# McTemplateK0qq_EtwWriteTransfer

- ea: `0x14001567c`
- end: `0x1400156dc`
- name: `McTemplateK0qq_EtwWriteTransfer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c618`

## callees

- `0x1400095bc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qq_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  int *v7; // [rsp+40h] [rbp-38h]
  __int64 v8; // [rsp+48h] [rbp-30h]
  __int64 *v9; // [rsp+50h] [rbp-28h]
  __int64 v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v8 = 4;
  v7 = &v11;
  v10 = 4;
  v9 = &a5;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 3u, &v6);
}

```

## disassembly

```asm
0x14001567c  mov     r11, rsp
0x14001567f  mov     [r11+20h], r9d
0x140015683  sub     rsp, 78h
0x140015687  mov     rax, cs:__security_cookie
0x14001568e  xor     rax, rsp
0x140015691  mov     [rsp+78h+var_18], rax
0x140015696  lea     rax, [r11+20h]
0x14001569a  mov     qword ptr [r11-30h], 4
0x1400156a2  mov     [r11-38h], rax
0x1400156a6  mov     r9d, 3
0x1400156ac  lea     rax, [r11+28h]
0x1400156b0  mov     qword ptr [r11-20h], 4
0x1400156b8  mov     [r11-28h], rax
0x1400156bc  lea     rax, [r11-48h]
0x1400156c0  mov     [r11-58h], rax
0x1400156c4  call    McGenEventWrite_EtwWriteTransfer
0x1400156c9  mov     rcx, [rsp+78h+var_18]
0x1400156ce  xor     rcx, rsp; StackCookie
0x1400156d1  call    __security_check_cookie
0x1400156d6  add     rsp, 78h
0x1400156da  retn
```
