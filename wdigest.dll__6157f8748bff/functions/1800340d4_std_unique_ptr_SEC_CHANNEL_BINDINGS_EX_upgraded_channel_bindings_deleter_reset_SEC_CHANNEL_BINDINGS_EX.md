# std::unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>::reset(_SEC_CHANNEL_BINDINGS_EX *)

- ea: `0x1800340d4`
- end: `0x1800340fc`
- name: `?reset@?$unique_ptr@U_SEC_CHANNEL_BINDINGS_EX@@Uupgraded_channel_bindings_deleter@@@std@@QEAAXPEAU_SEC_CHANNEL_BINDINGS_EX@@@Z`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180033bb0`
- `0x180033f78`

## callees

- `0x180012c50`
- `0x1800340d4`

## pseudocode

```c
void __fastcall std::unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>::reset(
        __int64 a1,
        __int64 a2)
{
  void *v2; // rax

  v2 = *(void **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = a2;
  if ( v2 )
  {
    if ( *(_BYTE *)a1 )
      operator delete(v2);
  }
}

```

## disassembly

```asm
0x1800340d4  sub     rsp, 28h
0x1800340d8  mov     rax, [rcx+8]
0x1800340dc  mov     [rcx+8], rdx
0x1800340e0  test    rax, rax
0x1800340e3  jz      short loc_1800340F7
0x1800340e5  cmp     byte ptr [rcx], 0
0x1800340e8  jz      short loc_1800340F7
0x1800340ea  mov     edx, 30h ; '0'; unsigned __int64
0x1800340ef  mov     rcx, rax; void *
0x1800340f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800340f7  add     rsp, 28h
0x1800340fb  retn
```
