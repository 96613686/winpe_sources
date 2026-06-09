# SKMI_IMAGE_SECURITY

- ea: `0x140014d64`
- end: `0x140014dc7`
- name: `SKMI_IMAGE_SECURITY`
- size: `99`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008500`
- `0x140014dd0`
- `0x14002a97c`
- `0x14002b1e0`
- `0x14003a10c`
- `0x14005f16c`
- `0x14005f838`
- `0x14005f8b8`
- `0x14006032c`
- `0x140060370`
- `0x140061b08`
- `0x140061d60`
- `0x1400631cc`
- `0x140063824`
- `0x140063a80`
- `0x140063ca8`
- `0x1400720b8`
- `0x140072b1c`
- `0x140074200`
- `0x14007c9b8`
- `0x14007d2b0`

## callees

- `0x140014d64`
- `0x1400714d4`

## pseudocode

```c
__int64 __fastcall SKMI_IMAGE_SECURITY(int a1, int a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 result; // rax
  _DWORD v6[4]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v7; // [rsp+30h] [rbp-30h]
  __int64 v8; // [rsp+38h] [rbp-28h]
  __int64 v9; // [rsp+40h] [rbp-20h]
  __int64 v10; // [rsp+48h] [rbp-18h]
  __int64 v11; // [rsp+50h] [rbp-10h]

  v6[1] = 0;
  v10 = 0;
  if ( SkmiFailureLog )
  {
    v7 = *(_QWORD *)(a3 + 240);
    v6[0] = 2;
    v6[2] = a1;
    v6[3] = a2;
    v8 = a4;
    v11 = 0;
    if ( a5 )
      v9 = *a5;
    else
      v9 = 0;
    return SkmiLogFailure(v6);
  }
  return result;
}

```

## disassembly

```asm
0x140014d64  push    rbp
0x140014d66  mov     rbp, rsp
0x140014d69  sub     rsp, 60h
0x140014d6d  xor     r10d, r10d
0x140014d70  cmp     cs:SkmiFailureLog, r10
0x140014d77  mov     [rbp+var_3C], r10d
0x140014d7b  mov     [rbp+var_18], r10
0x140014d7f  jz      short loc_140014DC0
0x140014d81  mov     rax, [r8+0F0h]
0x140014d88  mov     [rbp+var_30], rax
0x140014d8c  mov     rax, [rbp+arg_20]
0x140014d90  mov     [rbp+var_40], 2
0x140014d97  mov     [rbp+var_38], ecx
0x140014d9a  mov     [rbp+var_34], edx
0x140014d9d  mov     [rbp+var_28], r9
0x140014da1  mov     [rbp+var_10], r10
0x140014da5  test    rax, rax
0x140014da8  jz      short loc_140014DB3
0x140014daa  mov     rax, [rax]
0x140014dad  mov     [rbp+var_20], rax
0x140014db1  jmp     short loc_140014DB7
0x140014db3  mov     [rbp+var_20], r10
0x140014db7  lea     rcx, [rbp+var_40]
0x140014dbb  call    SkmiLogFailure
0x140014dc0  add     rsp, 60h
0x140014dc4  pop     rbp
0x140014dc5  retn
```
