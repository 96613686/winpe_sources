# CMulticastNamespace::`scalar deleting destructor'(uint)

- ea: `0x1800022f0`
- end: `0x180002360`
- name: `??_GCMulticastNamespace@@UEAAPEAXI@Z`
- size: `112`
- prototype: `void *__fastcall(CMulticastNamespace *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800022f0`
- `0x1800026b8`
- `0x18000b0c4`
- `0x18001a9a8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002325`
- `KERNEL32!DeleteCriticalSection` at `0x18000232f`
- `KERNEL32!DeleteCriticalSection` at `0x180002325`
- `KERNEL32!DeleteCriticalSection` at `0x18000232f`

## pseudocode

```c
CMulticastNamespace *__fastcall CMulticastNamespace::`scalar deleting destructor'(CMulticastNamespace *this, char a2)
{
  *(_QWORD *)this = &CMulticastNamespace::`vftable';
  CMulticastNamespace::Shutdown(this);
  CMcNsClients::Shutdown((LPCRITICAL_SECTION)this + 9);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &CRefCount::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800022f0  mov     [rsp+arg_0], rbx
0x1800022f5  mov     [rsp+arg_8], rsi
0x1800022fa  push    rdi
0x1800022fb  sub     rsp, 20h
0x1800022ff  lea     rax, ??_7CMulticastNamespace@@6B@; const CMulticastNamespace::`vftable'
0x180002306  mov     edi, edx
0x180002308  mov     [rcx], rax
0x18000230b  mov     rsi, rcx
0x18000230e  call    ?Shutdown@CMulticastNamespace@@QEAAKXZ; CMulticastNamespace::Shutdown(void)
0x180002313  lea     rbx, [rsi+168h]
0x18000231a  mov     rcx, rbx; lpCriticalSection
0x18000231d  call    ?Shutdown@CMcNsClients@@QEAAKXZ; CMcNsClients::Shutdown(void)
0x180002322  mov     rcx, rbx; lpCriticalSection
0x180002325  call    cs:__imp_DeleteCriticalSection
0x18000232b  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000232f  call    cs:__imp_DeleteCriticalSection
0x180002335  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x18000233c  mov     [rsi], rax
0x18000233f  test    dil, 1
0x180002343  jz      short loc_18000234D
0x180002345  mov     rcx, rsi; void *
0x180002348  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000234d  mov     rbx, [rsp+28h+arg_0]
0x180002352  mov     rax, rsi
0x180002355  mov     rsi, [rsp+28h+arg_8]
0x18000235a  add     rsp, 20h
0x18000235e  pop     rdi
0x18000235f  retn
```
