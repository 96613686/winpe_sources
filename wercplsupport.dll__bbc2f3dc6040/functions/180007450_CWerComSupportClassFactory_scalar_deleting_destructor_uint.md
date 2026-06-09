# CWerComSupportClassFactory::`scalar deleting destructor'(uint)

- ea: `0x180007450`
- end: `0x180007490`
- name: `??_GCWerComSupportClassFactory@@UEAAPEAXI@Z`
- size: `64`
- prototype: `void *__fastcall(CWerComSupportClassFactory *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x180007450`
- `0x180007624`

## pseudocode

```c
CWerComSupportClassFactory *__fastcall CWerComSupportClassFactory::`scalar deleting destructor'(
        CWerComSupportClassFactory *this,
        char a2)
{
  *(_QWORD *)this = &CManagedObj::`vftable';
  CObjectManager::UnLockServer((CObjectManager *)&CObjectManager::ms_instance);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007450  mov     [rsp+arg_0], rbx
0x180007455  push    rdi
0x180007456  sub     rsp, 20h
0x18000745a  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x180007461  mov     rdi, rcx
0x180007464  mov     [rcx], rax
0x180007467  mov     ebx, edx
0x180007469  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x180007470  call    ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
0x180007475  test    bl, 1
0x180007478  jz      short loc_180007482
0x18000747a  mov     rcx, rdi; Block
0x18000747d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007482  mov     rbx, [rsp+28h+arg_0]
0x180007487  mov     rax, rdi
0x18000748a  add     rsp, 20h
0x18000748e  pop     rdi
0x18000748f  retn
```
