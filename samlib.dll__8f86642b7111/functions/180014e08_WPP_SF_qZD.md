# WPP_SF_qZD

- ea: `0x180014e08`
- end: `0x180014eb0`
- name: `WPP_SF_qZD`
- size: `168`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d330`
- `0x18000d630`
- `0x18000dde0`

## callees

- `0x180014e08`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014ea5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014ea5`

## pseudocode

```c
ULONG WPP_SF_qZD(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  const wchar_t *v3; // rax
  __int64 v4; // r8
  const wchar_t *v5; // r9
  __int64 v7; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  unsigned __int16 *v9; // [rsp+A0h] [rbp+28h]
  va_list va1; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  v9 = va_arg(va1, unsigned __int16 *);
  v3 = v9;
  if ( v9 )
  {
    v4 = *v9;
    if ( *v9 )
    {
      v5 = (const wchar_t *)*((_QWORD *)v9 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !v9 )
    v3 = L"\b";
  return TraceMessage(a1, 0x2Bu, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a2, va, 8, v3, 2, v5, v4, va1, 4, 0);
}

```

## disassembly

```asm
0x180014e08  mov     [rsp+arg_18], r9
0x180014e0d  sub     rsp, 78h
0x180014e11  mov     rax, [rsp+78h+arg_20]
0x180014e19  xor     r11d, r11d
0x180014e1c  test    rax, rax
0x180014e1f  jz      short loc_180014E31
0x180014e21  movzx   r8d, word ptr [rax]
0x180014e25  cmp     [rax], r11w
0x180014e29  jz      short loc_180014E37
0x180014e2b  mov     r9, [rax+8]
0x180014e2f  jmp     short loc_180014E3E
0x180014e31  mov     r8d, 8
0x180014e37  lea     r9, aNull_0; "NULL"
0x180014e3e  mov     [rsp+78h+var_18], r11
0x180014e43  lea     r10, asc_1800209FC; "\b"
0x180014e4a  mov     [rsp+78h+var_20], 4
0x180014e53  test    rax, rax
0x180014e56  cmovz   rax, r10
0x180014e5a  lea     r10, [rsp+78h+arg_28]
0x180014e62  mov     [rsp+78h+var_28], r10
0x180014e67  mov     [rsp+78h+var_30], r8
0x180014e6c  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids; MessageGuid
0x180014e73  mov     [rsp+78h+var_38], r9
0x180014e78  mov     [rsp+78h+var_40], 2
0x180014e81  mov     [rsp+78h+var_48], rax
0x180014e86  lea     rax, [rsp+78h+arg_18]
0x180014e8e  movzx   r9d, dx; MessageNumber
0x180014e92  mov     edx, 2Bh ; '+'; MessageFlags
0x180014e97  mov     [rsp+78h+var_50], 8
0x180014ea0  mov     [rsp+78h+var_58], rax
0x180014ea5  call    cs:__imp_TraceMessage
0x180014eab  add     rsp, 78h
0x180014eaf  retn
```
