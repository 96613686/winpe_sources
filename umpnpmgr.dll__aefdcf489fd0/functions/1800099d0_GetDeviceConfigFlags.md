# GetDeviceConfigFlags

- ea: `0x1800099d0`
- end: `0x180009a13`
- name: `GetDeviceConfigFlags`
- size: `67`
- prototype: `__int64 __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800056d0`

## callees

- `0x1800099d0`
- `0x180009a20`

## pseudocode

```c
__int64 __fastcall GetDeviceConfigFlags(WCHAR *a1)
{
  DEVNODE v2; // [rsp+28h] [rbp-10h]
  ULONG v3; // [rsp+50h] [rbp+18h] BYREF
  int v4; // [rsp+58h] [rbp+20h]

  v3 = 4;
  v4 = 0;
  if ( (unsigned int)PnpGetDeviceRegProp(a1, &v3, v2) )
    return 0;
  else
    return 0;
}

```

## disassembly

```asm
0x1800099d0  push    rbx
0x1800099d2  sub     rsp, 30h
0x1800099d6  xor     ebx, ebx
0x1800099d8  mov     [rsp+38h+arg_10], 4
0x1800099e0  lea     rax, [rsp+38h+arg_10]
0x1800099e5  mov     [rsp+38h+arg_8], ebx
0x1800099e9  lea     r9, [rsp+38h+arg_8]
0x1800099ee  mov     [rsp+38h+arg_18], ebx
0x1800099f2  lea     r8, [rsp+38h+arg_18]
0x1800099f7  mov     [rsp+38h+var_18], rax; PULONG
0x1800099fc  call    PnpGetDeviceRegProp
0x180009a01  test    eax, eax
0x180009a03  jz      short loc_180009A0D
0x180009a05  mov     eax, ebx
0x180009a07  add     rsp, 30h
0x180009a0b  pop     rbx
0x180009a0c  retn
0x180009a0d  mov     eax, [rsp+38h+arg_8]
0x180009a11  jmp     short loc_180009A07
```
