# CWamAdmin::AppCreate(ushort const *,int)

- ea: `0x1800020a0`
- end: `0x1800020af`
- name: `?AppCreate@CWamAdmin@@UEAAJPEBGH@Z`
- size: `15`
- prototype: `__int64 __fastcall(CWamAdmin *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWamAdmin::AppCreate(CWamAdmin *this, const unsigned __int16 *a2)
{
  return (*(__int64 (__fastcall **)(CWamAdmin *, const unsigned __int16 *, _QWORD))(*(_QWORD *)this + 72LL))(
           this,
           a2,
           0);
}

```

## disassembly

```asm
0x1800020a0  mov     rax, [rcx]
0x1800020a3  xor     r8d, r8d
0x1800020a6  mov     rax, [rax+48h]
0x1800020aa  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
