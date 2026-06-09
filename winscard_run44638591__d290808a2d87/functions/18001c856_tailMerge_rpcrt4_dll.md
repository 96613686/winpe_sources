# __tailMerge_rpcrt4_dll

- ea: `0x18001c856`
- end: `0x18001c8cf`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c8d5`
- `0x18001c8e7`
- `0x18001c8f9`
- `0x18001c90b`
- `0x18001c91d`
- `0x18001c92f`
- `0x18001c941`
- `0x18001c953`
- `0x18001c965`
- `0x18001c977`
- `0x18001c989`
- `0x18001c99b`
- `0x18001c9ad`
- `0x18001c9bf`

## callees

- `0x180017530`
- `0x18001c856`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001c856  mov     [rsp+arg_0], rcx
0x18001c85b  mov     [rsp+arg_8], rdx
0x18001c860  mov     [rsp+arg_10], r8
0x18001c865  mov     [rsp+arg_18], r9
0x18001c86a  sub     rsp, 68h
0x18001c86e  movdqa  [rsp+68h+var_48], xmm0
0x18001c874  movdqa  [rsp+68h+var_38], xmm1
0x18001c87a  movdqa  [rsp+68h+var_28], xmm2
0x18001c880  movdqa  [rsp+68h+var_18], xmm3
0x18001c886  mov     rdx, rax
0x18001c889  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18001c890  call    __delayLoadHelper2
0x18001c895  movdqa  xmm0, [rsp+68h+var_48]
0x18001c89b  movdqa  xmm1, [rsp+68h+var_38]
0x18001c8a1  movdqa  xmm2, [rsp+68h+var_28]
0x18001c8a7  movdqa  xmm3, [rsp+68h+var_18]
0x18001c8ad  mov     rcx, [rsp+68h+arg_0]
0x18001c8b2  mov     rdx, [rsp+68h+arg_8]
0x18001c8b7  mov     r8, [rsp+68h+arg_10]
0x18001c8bf  mov     r9, [rsp+68h+arg_18]
0x18001c8c7  add     rsp, 68h
0x18001c8cb  jmp     short $+2
0x18001c8cd  jmp     rax
```
