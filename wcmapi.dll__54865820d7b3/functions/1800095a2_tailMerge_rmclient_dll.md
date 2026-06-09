# __tailMerge_rmclient_dll

- ea: `0x1800095a2`
- end: `0x18000961b`
- name: `__tailMerge_rmclient_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009621`

## callees

- `0x180005980`
- `0x1800095a2`

## pseudocode

```c
__int64 __fastcall _tailMerge_rmclient_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rmclient_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800095a2  mov     [rsp+arg_0], rcx
0x1800095a7  mov     [rsp+arg_8], rdx
0x1800095ac  mov     [rsp+arg_10], r8
0x1800095b1  mov     [rsp+arg_18], r9
0x1800095b6  sub     rsp, 68h
0x1800095ba  movdqa  [rsp+68h+var_48], xmm0
0x1800095c0  movdqa  [rsp+68h+var_38], xmm1
0x1800095c6  movdqa  [rsp+68h+var_28], xmm2
0x1800095cc  movdqa  [rsp+68h+var_18], xmm3
0x1800095d2  mov     rdx, rax
0x1800095d5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rmclient_dll
0x1800095dc  call    __delayLoadHelper2
0x1800095e1  movdqa  xmm0, [rsp+68h+var_48]
0x1800095e7  movdqa  xmm1, [rsp+68h+var_38]
0x1800095ed  movdqa  xmm2, [rsp+68h+var_28]
0x1800095f3  movdqa  xmm3, [rsp+68h+var_18]
0x1800095f9  mov     rcx, [rsp+68h+arg_0]
0x1800095fe  mov     rdx, [rsp+68h+arg_8]
0x180009603  mov     r8, [rsp+68h+arg_10]
0x18000960b  mov     r9, [rsp+68h+arg_18]
0x180009613  add     rsp, 68h
0x180009617  jmp     short $+2
0x180009619  jmp     rax
```
