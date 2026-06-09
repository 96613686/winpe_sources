# WMNewOpenResizerBasic

- ea: `0x180012dd0`
- end: `0x180012e23`
- name: `WMNewOpenResizerBasic`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180012e30`

## pseudocode

```c
__int64 __fastcall WMNewOpenResizerBasic(__int64 a1, __int64 *a2, int a3, int a4, int a5, int a6)
{
  return WMNewOpenResizerWithFullCropping(
           a1,
           a2,
           a3,
           a4,
           0,
           0,
           *(_DWORD *)(a1 + 4),
           *(_DWORD *)(a1 + 8),
           0,
           0,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180012dd0  sub     rsp, 78h
0x180012dd4  mov     eax, [rsp+78h+arg_28]
0x180012ddb  xor     r10d, r10d
0x180012dde  mov     [rsp+78h+var_10], eax
0x180012de2  mov     eax, [rsp+78h+arg_20]
0x180012de9  mov     [rsp+78h+var_18], eax
0x180012ded  mov     eax, [rcx+8]
0x180012df0  mov     [rsp+78h+var_20], r9d
0x180012df5  mov     [rsp+78h+var_28], r8d
0x180012dfa  mov     [rsp+78h+var_30], r10d
0x180012dff  mov     [rsp+78h+var_38], r10d
0x180012e04  mov     [rsp+78h+var_40], eax
0x180012e08  mov     eax, [rcx+4]
0x180012e0b  mov     [rsp+78h+var_48], eax
0x180012e0f  mov     [rsp+78h+var_50], r10d
0x180012e14  mov     [rsp+78h+var_58], r10d
0x180012e19  call    WMNewOpenResizerWithFullCropping
0x180012e1e  add     rsp, 78h
0x180012e22  retn
```
