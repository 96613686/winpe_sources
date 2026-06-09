# WPP_SF_D

- ea: `0x18000f32c`
- end: `0x18000f36a`
- name: `WPP_SF_D`
- size: `62`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, __int64, int)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e360`
- `0x18000e640`
- `0x18000e928`
- `0x18000ec18`
- `0x18000edec`
- `0x18000efd4`
- `0x18000f180`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f35f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f35f`

## pseudocode

```c
ULONG __fastcall WPP_SF_D(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, &WPP_f14b85ebde3837b9d33c63fdcbae6fb0_Traceguids, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000f32c  mov     r11, rsp
0x18000f32f  mov     [r11+20h], r9d
0x18000f333  sub     rsp, 48h
0x18000f337  mov     qword ptr [r11-18h], 0
0x18000f33f  lea     rax, [r11+20h]
0x18000f343  movzx   r9d, dx; MessageNumber
0x18000f347  lea     r8, WPP_f14b85ebde3837b9d33c63fdcbae6fb0_Traceguids; MessageGuid
0x18000f34e  mov     qword ptr [r11-20h], 4
0x18000f356  mov     edx, 2Bh ; '+'; MessageFlags
0x18000f35b  mov     [r11-28h], rax
0x18000f35f  call    cs:__imp_TraceMessage
0x18000f365  add     rsp, 48h
0x18000f369  retn
```
