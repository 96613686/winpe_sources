# CLogManager::RemoveGlobalFilter(void *)

- ea: `0x18001fd10`
- end: `0x18001fd8c`
- name: `?RemoveGlobalFilter@CLogManager@@UEAAHPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(CLogManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001fd10`
- `0x180020704`
- `0x180022f4c`
- `0x180023474`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CLogManager::RemoveGlobalFilter(CLogManager *this, void *a2)
{
  CMutualExclusionObject *v3; // rdi
  struct ILogProvider **v4; // rsi
  __int64 v5; // rcx

  v3 = (CLogManager *)((char *)this + 40);
  CMutualExclusionObject::Acquiry((CLogManager *)((char *)this + 40));
  v4 = (struct ILogProvider **)((char *)this + 104);
  v5 = *((_QWORD *)this + 13);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64, unsigned __int64, __int64))(*(_QWORD *)v5 + 40LL))(
      v5,
      ((unsigned __int64)this + 8) & -(__int64)(this != 0),
      1);
    LogiDestroyProvider(*v4);
    *v4 = 0;
  }
  CMutualExclusionObject::Release(v3);
  return 1;
}

```

## disassembly

```asm
0x18001fd10  mov     [rsp+arg_8], rbx
0x18001fd15  mov     [rsp+arg_10], rsi
0x18001fd1a  mov     [rsp+arg_0], rcx
0x18001fd1f  push    rdi
0x18001fd20  sub     rsp, 20h
0x18001fd24  mov     rbx, rcx
0x18001fd27  lea     rdi, [rcx+28h]
0x18001fd2b  mov     rcx, rdi; this
0x18001fd2e  call    ?Acquiry@CMutualExclusionObject@@QEAAXXZ; CMutualExclusionObject::Acquiry(void)
0x18001fd33  nop
0x18001fd34  lea     rsi, [rbx+68h]
0x18001fd38  mov     rcx, [rsi]
0x18001fd3b  test    rcx, rcx
0x18001fd3e  jz      short loc_18001FD6E
0x18001fd40  mov     r8, [rcx]
0x18001fd43  lea     rax, [rbx+8]
0x18001fd47  neg     rbx
0x18001fd4a  sbb     rdx, rdx
0x18001fd4d  and     rdx, rax
0x18001fd50  mov     rax, [r8+28h]
0x18001fd54  mov     r8d, 1
0x18001fd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd5f  mov     rcx, [rsi]; struct ILogProvider *
0x18001fd62  call    ?LogiDestroyProvider@@YAHPEAVILogProvider@@@Z; LogiDestroyProvider(ILogProvider *)
0x18001fd67  mov     qword ptr [rsi], 0
0x18001fd6e  mov     rcx, rdi; this
0x18001fd71  call    ?Release@CMutualExclusionObject@@QEAAXXZ; CMutualExclusionObject::Release(void)
0x18001fd76  mov     eax, 1
0x18001fd7b  mov     rbx, [rsp+28h+arg_8]
0x18001fd80  mov     rsi, [rsp+28h+arg_10]
0x18001fd85  add     rsp, 20h
0x18001fd89  pop     rdi
0x18001fd8a  retn
0x180029323  push    rbp
0x180029325  sub     rsp, 20h
0x180029329  mov     rbp, rdx
0x18002932c  mov     rcx, [rbp+30h]
0x180029330  add     rcx, 28h ; '('; this
0x180029334  add     rsp, 20h
0x180029338  pop     rbp
0x180029339  jmp     ?Release@CMutualExclusionObject@@QEAAXXZ; CMutualExclusionObject::Release(void)
```
