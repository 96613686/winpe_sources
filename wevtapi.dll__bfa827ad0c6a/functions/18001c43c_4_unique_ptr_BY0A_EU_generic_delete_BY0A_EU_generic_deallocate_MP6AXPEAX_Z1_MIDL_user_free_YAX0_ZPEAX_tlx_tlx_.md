# ??4?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z

- ea: `0x18001c43c`
- end: `0x18001c468`
- name: `??4?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001b3d4`
- `0x18001bda4`
- `0x18001c130`
- `0x18001c280`
- `0x18001c470`
- `0x180020a5c`
- `0x180020d74`
- `0x1800237bc`

## callees

- `0x18000a100`
- `0x18001c43c`

## pseudocode

```c
void **__fastcall __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
        void **a1,
        void **a2)
{
  void *v2; // rax
  void *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    operator delete(v4);
  return a1;
}

```

## disassembly

```asm
0x18001c43c  push    rbx
0x18001c43e  sub     rsp, 20h
0x18001c442  mov     rax, [rdx]
0x18001c445  mov     rbx, rcx
0x18001c448  mov     qword ptr [rdx], 0
0x18001c44f  mov     rcx, [rcx]; void *
0x18001c452  mov     [rbx], rax
0x18001c455  test    rcx, rcx
0x18001c458  jz      short loc_18001C45F
0x18001c45a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c45f  mov     rax, rbx
0x18001c462  add     rsp, 20h
0x18001c466  pop     rbx
0x18001c467  retn
```
