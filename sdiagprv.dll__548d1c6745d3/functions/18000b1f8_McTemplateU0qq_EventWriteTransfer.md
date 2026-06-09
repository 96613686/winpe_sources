# McTemplateU0qq_EventWriteTransfer

- ea: `0x18000b1f8`
- end: `0x18000b262`
- name: `McTemplateU0qq_EventWriteTransfer`
- size: `106`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e60`

## callees

- `0x18000247c`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qq_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  int *v6; // [rsp+40h] [rbp-38h]
  __int64 v7; // [rsp+48h] [rbp-30h]
  int *v8; // [rsp+50h] [rbp-28h]
  __int64 v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+90h] [rbp+18h] BYREF
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v10 = a3;
  v7 = 4;
  v6 = &v10;
  v9 = 4;
  v8 = &v11;
  return McGenEventWrite_EventWriteTransfer(
           a1,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_SEND_POST_REQUEST_END,
           a3,
           3u,
           &v5);
}

```

## disassembly

```asm
0x18000b1f8  mov     r11, rsp
0x18000b1fb  mov     [r11+20h], r9d
0x18000b1ff  mov     [r11+18h], r8d
0x18000b203  sub     rsp, 78h
0x18000b207  mov     rax, cs:__security_cookie
0x18000b20e  xor     rax, rsp
0x18000b211  mov     [rsp+78h+var_18], rax
0x18000b216  lea     rax, [r11+18h]
0x18000b21a  mov     qword ptr [r11-30h], 4
0x18000b222  mov     [r11-38h], rax
0x18000b226  lea     rdx, SDIAGPRV_EVENT_PERF_DIAGNOSTIC_PROVIDER_SEND_POST_REQUEST_END
0x18000b22d  lea     rax, [r11+20h]
0x18000b231  mov     qword ptr [r11-20h], 4
0x18000b239  mov     [r11-28h], rax
0x18000b23d  mov     r9d, 3
0x18000b243  lea     rax, [r11-48h]
0x18000b247  mov     [r11-58h], rax
0x18000b24b  call    McGenEventWrite_EventWriteTransfer
0x18000b250  mov     rcx, [rsp+78h+var_18]
0x18000b255  xor     rcx, rsp; StackCookie
0x18000b258  call    __security_check_cookie
0x18000b25d  add     rsp, 78h
0x18000b261  retn
```
