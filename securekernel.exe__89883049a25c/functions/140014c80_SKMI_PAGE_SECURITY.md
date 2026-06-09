# SKMI_PAGE_SECURITY

- ea: `0x140014c80`
- end: `0x140014cd0`
- name: `SKMI_PAGE_SECURITY`
- size: `80`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002a04`
- `0x140002fac`
- `0x14000ed00`
- `0x14002d168`
- `0x1400341c8`
- `0x14004853c`
- `0x14005f16c`
- `0x14006ffbc`
- `0x140071f44`
- `0x1400720b8`
- `0x140072594`
- `0x140072884`
- `0x140072b1c`
- `0x1400731c0`
- `0x140073890`
- `0x140073d1c`
- `0x140074020`
- `0x140074200`
- `0x1400747f0`
- `0x1400765fc`
- `0x1400777f0`
- `0x140079008`
- `0x14007c9b8`
- `0x14008451c`
- `0x14008793c`
- `0x1400ee634`

## callees

- `0x140014c80`
- `0x1400714d4`

## pseudocode

```c
__int64 __fastcall SKMI_PAGE_SECURITY(int a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 result; // rax
  _DWORD v5[4]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+30h] [rbp-30h]
  __int64 v7; // [rsp+38h] [rbp-28h]
  __int64 v8; // [rsp+40h] [rbp-20h]
  __int64 v9; // [rsp+48h] [rbp-18h]
  __int64 v10; // [rsp+50h] [rbp-10h]

  result = 0;
  v5[1] = 0;
  v5[3] = 0;
  v9 = 0;
  if ( SkmiFailureLog )
  {
    v5[0] = 1;
    v5[2] = a1;
    v6 = a2;
    v7 = a3;
    v10 = 0;
    if ( a4 )
      result = *a4;
    v8 = result;
    return SkmiLogFailure(v5);
  }
  return result;
}

```

## disassembly

```asm
0x140014c80  push    rbp
0x140014c82  mov     rbp, rsp
0x140014c85  sub     rsp, 60h
0x140014c89  xor     eax, eax
0x140014c8b  cmp     cs:SkmiFailureLog, rax
0x140014c92  mov     [rbp+var_3C], eax
0x140014c95  mov     [rbp+var_34], eax
0x140014c98  mov     [rbp+var_18], rax
0x140014c9c  jz      short loc_140014CC9
0x140014c9e  mov     [rbp+var_40], 1
0x140014ca5  mov     [rbp+var_38], ecx
0x140014ca8  mov     [rbp+var_30], rdx
0x140014cac  mov     [rbp+var_28], r8
0x140014cb0  mov     [rbp+var_10], rax
0x140014cb4  test    r9, r9
0x140014cb7  jz      short loc_140014CBC
0x140014cb9  mov     rax, [r9]
0x140014cbc  lea     rcx, [rbp+var_40]
0x140014cc0  mov     [rbp+var_20], rax
0x140014cc4  call    SkmiLogFailure
0x140014cc9  add     rsp, 60h
0x140014ccd  pop     rbp
0x140014cce  retn
```
