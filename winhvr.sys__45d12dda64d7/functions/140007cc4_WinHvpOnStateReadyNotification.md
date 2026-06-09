# WinHvpOnStateReadyNotification

- ea: `0x140007cc4`
- end: `0x140007d06`
- name: `WinHvpOnStateReadyNotification`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400011c0`

## callees

- `0x1400024d0`
- `0x140002bf0`
- `0x140007cc4`
- `0x140009c90`

## pseudocode

```c
__int64 __fastcall WinHvpOnStateReadyNotification(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rbx

  result = WinHvpReferencePartition(*(_QWORD *)(a1 + 8));
  v3 = result;
  if ( result )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(result + 24))(*(_QWORD *)(result + 32), a1);
    return WinHvpDereferencePartition(v3);
  }
  return result;
}

```

## disassembly

```asm
0x140007cc4  mov     [rsp+arg_0], rbx
0x140007cc9  push    rdi
0x140007cca  sub     rsp, 20h
0x140007cce  mov     rdi, rcx
0x140007cd1  mov     rcx, [rcx+8]
0x140007cd5  call    WinHvpReferencePartition
0x140007cda  mov     rbx, rax
0x140007cdd  test    rax, rax
0x140007ce0  jz      short loc_140007CFA
0x140007ce2  mov     rax, [rax+18h]
0x140007ce6  mov     rdx, rdi
0x140007ce9  mov     rcx, [rbx+20h]
0x140007ced  call    _guard_dispatch_icall
0x140007cf2  mov     rcx, rbx
0x140007cf5  call    WinHvpDereferencePartition
0x140007cfa  mov     rbx, [rsp+28h+arg_0]
0x140007cff  add     rsp, 20h
0x140007d03  pop     rdi
0x140007d04  retn
```
