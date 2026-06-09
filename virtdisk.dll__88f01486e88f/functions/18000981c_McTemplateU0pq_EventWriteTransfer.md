# McTemplateU0pq_EventWriteTransfer

- ea: `0x18000981c`
- end: `0x180009887`
- name: `McTemplateU0pq_EventWriteTransfer`
- size: `107`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003930`

## callees

- `0x180005730`
- `0x1800097bc`

## pseudocode

```c
ULONG __fastcall McTemplateU0pq_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v6; // [rsp+40h] [rbp-38h]
  __int64 v7; // [rsp+48h] [rbp-30h]
  int *v8; // [rsp+50h] [rbp-28h]
  __int64 v9; // [rsp+58h] [rbp-20h]
  __int64 v10; // [rsp+90h] [rbp+18h] BYREF
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v10 = a3;
  v7 = 8;
  v6 = &v10;
  v9 = 4;
  v8 = &v11;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)VirtdiskOpenStop, a3, 3u, &v5);
}

```

## disassembly

```asm
0x18000981c  mov     r11, rsp
0x18000981f  mov     [r11+20h], r9d
0x180009823  mov     [r11+18h], r8
0x180009827  sub     rsp, 78h
0x18000982b  mov     rax, cs:__security_cookie
0x180009832  xor     rax, rsp
0x180009835  mov     [rsp+78h+var_18], rax
0x18000983a  lea     rax, [r11+18h]
0x18000983e  mov     qword ptr [r11-30h], 8
0x180009846  mov     [r11-38h], rax
0x18000984a  lea     rdx, VirtdiskOpenStop
0x180009851  lea     rax, [r11+20h]
0x180009855  mov     qword ptr [r11-20h], 4
0x18000985d  mov     [r11-28h], rax
0x180009861  mov     r9d, 3
0x180009867  lea     rax, [r11-48h]
0x18000986b  mov     [r11-58h], rax
0x18000986f  call    McGenEventWrite_EventWriteTransfer
0x180009874  mov     rcx, [rsp+78h+var_18]
0x180009879  xor     rcx, rsp; StackCookie
0x18000987c  call    __security_check_cookie
0x180009881  add     rsp, 78h
0x180009885  retn
```
