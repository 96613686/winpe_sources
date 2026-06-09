# CDetectISAPIConfigModuleFactory::Terminate(void)

- ea: `0x180002f90`
- end: `0x180002fcb`
- name: `?Terminate@CDetectISAPIConfigModuleFactory@@UEAAXXZ`
- size: `59`
- prototype: `void __fastcall(CDetectISAPIConfigModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180001820`
- `0x180002f90`
- `0x180004010`

## pseudocode

```c
void __fastcall CDetectISAPIConfigModuleFactory::Terminate(CDetectISAPIConfigModuleFactory *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 240LL))(v2, 1);
    *((_QWORD *)this + 1) = 0;
  }
  operator delete(this);
}

```

## disassembly

```asm
0x180002f90  push    rbx
0x180002f92  sub     rsp, 20h
0x180002f96  mov     rbx, rcx
0x180002f99  mov     rcx, [rcx+8]
0x180002f9d  test    rcx, rcx
0x180002fa0  jz      short loc_180002FBE
0x180002fa2  mov     rax, [rcx]
0x180002fa5  mov     edx, 1
0x180002faa  mov     rax, [rax+0F0h]
0x180002fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb6  mov     qword ptr [rbx+8], 0
0x180002fbe  mov     rcx, rbx; Block
0x180002fc1  add     rsp, 20h
0x180002fc5  pop     rbx
0x180002fc6  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
