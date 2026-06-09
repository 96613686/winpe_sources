# utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>>::operator=(utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> &&)

- ea: `0x18000f800`
- end: `0x18000f82c`
- name: `??4?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180012084`

## callees

- `0x180003038`
- `0x18000f800`

## pseudocode

```c
void **__fastcall utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>>::operator=(
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
0x18000f800  push    rbx
0x18000f802  sub     rsp, 20h
0x18000f806  mov     rax, [rdx]
0x18000f809  mov     rbx, rcx
0x18000f80c  mov     qword ptr [rdx], 0
0x18000f813  mov     rcx, [rcx]; Block
0x18000f816  mov     [rbx], rax
0x18000f819  test    rcx, rcx
0x18000f81c  jz      short loc_18000F823
0x18000f81e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f823  mov     rax, rbx
0x18000f826  add     rsp, 20h
0x18000f82a  pop     rbx
0x18000f82b  retn
```
