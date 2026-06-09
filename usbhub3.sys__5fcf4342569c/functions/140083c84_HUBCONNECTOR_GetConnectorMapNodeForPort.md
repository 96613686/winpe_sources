# HUBCONNECTOR_GetConnectorMapNodeForPort

- ea: `0x140083c84`
- end: `0x140083da2`
- name: `HUBCONNECTOR_GetConnectorMapNodeForPort`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001f3e0`

## callees

- `0x140045570`
- `0x140083c84`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140083d28`
- `ntoskrnl!RtlCompareMemory` at `0x140083d28`

## pseudocode

```c
_QWORD *__fastcall HUBCONNECTOR_GetConnectorMapNodeForPort(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 v3; // rax
  _QWORD *v4; // rsi
  _QWORD *i; // rax
  __int64 v6; // rax

  v1 = 0;
  if ( (*(_DWORD *)(a1 + 204) & 0x20) != 0 )
  {
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           WdfDriverGlobals->Driver,
           off_14006B2C0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 56),
      0);
    v4 = (_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      WdfDriverGlobals->Driver,
                      off_14006B2C0)
                  + 40);
    for ( i = (_QWORD *)*v4; ; i = (_QWORD *)v1[10] )
    {
      v1 = i - 10;
      if ( v4 == i )
        break;
      if ( RtlCompareMemory(i - 10, (const void *)(a1 + 1368), 0x38u) == 56 )
        goto LABEL_7;
    }
    v1 = 0;
LABEL_7:
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           WdfDriverGlobals->Driver,
           off_14006B2C0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
      WdfDriverGlobals,
      *(_QWORD *)(v6 + 56));
  }
  return v1;
}

```

## disassembly

```asm
0x140083c84  mov     [rsp+arg_0], rbx
0x140083c89  mov     [rsp+arg_8], rsi
0x140083c8e  push    rdi
0x140083c8f  sub     rsp, 20h
0x140083c93  mov     eax, [rcx+0CCh]
0x140083c99  xor     ebx, ebx
0x140083c9b  mov     rdi, rcx
0x140083c9e  test    al, 20h
0x140083ca0  jz      loc_140083D8E
0x140083ca6  mov     rax, cs:WdfFunctions_01015
0x140083cad  mov     rcx, cs:WdfDriverGlobals
0x140083cb4  mov     r8, cs:off_14006B2C0
0x140083cbb  mov     rax, [rax+650h]
0x140083cc2  mov     rdx, [rcx]
0x140083cc5  call    _guard_dispatch_icall
0x140083cca  mov     rcx, cs:WdfDriverGlobals
0x140083cd1  xor     r8d, r8d
0x140083cd4  mov     rdx, [rax+38h]
0x140083cd8  mov     rax, cs:WdfFunctions_01015
0x140083cdf  mov     rax, [rax+9C8h]
0x140083ce6  call    _guard_dispatch_icall
0x140083ceb  mov     rax, cs:WdfFunctions_01015
0x140083cf2  mov     rcx, cs:WdfDriverGlobals
0x140083cf9  mov     r8, cs:off_14006B2C0
0x140083d00  mov     rax, [rax+650h]
0x140083d07  mov     rdx, [rcx]
0x140083d0a  call    _guard_dispatch_icall
0x140083d0f  lea     rsi, [rax+28h]
0x140083d13  mov     rax, [rsi]
0x140083d16  jmp     short loc_140083D3E
0x140083d18  mov     r8d, 38h ; '8'; Length
0x140083d1e  lea     rdx, [rdi+558h]; Source2
0x140083d25  mov     rcx, rbx; Source1
0x140083d28  call    cs:__imp_RtlCompareMemory
0x140083d2f  nop     dword ptr [rax+rax+00h]
0x140083d34  cmp     rax, 38h ; '8'
0x140083d38  jz      short loc_140083D49
0x140083d3a  mov     rax, [rbx+50h]
0x140083d3e  lea     rbx, [rax-50h]
0x140083d42  cmp     rsi, rax
0x140083d45  jnz     short loc_140083D18
0x140083d47  xor     ebx, ebx
0x140083d49  mov     rax, cs:WdfFunctions_01015
0x140083d50  mov     rcx, cs:WdfDriverGlobals
0x140083d57  mov     r8, cs:off_14006B2C0
0x140083d5e  mov     rax, [rax+650h]
0x140083d65  mov     rdx, [rcx]
0x140083d68  call    _guard_dispatch_icall
0x140083d6d  mov     rcx, cs:WdfFunctions_01015
0x140083d74  mov     rdx, [rax+38h]
0x140083d78  mov     r8, [rcx+9D0h]
0x140083d7f  mov     rcx, cs:WdfDriverGlobals
0x140083d86  mov     rax, r8
0x140083d89  call    _guard_dispatch_icall
0x140083d8e  mov     rsi, [rsp+28h+arg_8]
0x140083d93  mov     rax, rbx
0x140083d96  mov     rbx, [rsp+28h+arg_0]
0x140083d9b  add     rsp, 20h
0x140083d9f  pop     rdi
0x140083da0  retn
```
