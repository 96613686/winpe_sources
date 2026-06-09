# UnBCL::HeapMemoryManager::~HeapMemoryManager(void)

- ea: `0x18003edd0`
- end: `0x18003ee0b`
- name: `??1HeapMemoryManager@UnBCL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(UnBCL::HeapMemoryManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005df0`

## callees

- `0x18003f090`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18003edf7`
- `KERNEL32!DeleteCriticalSection` at `0x18003edf7`

## pseudocode

```c
void __fastcall UnBCL::HeapMemoryManager::~HeapMemoryManager(UnBCL::HeapMemoryManager *this)
{
  *(_QWORD *)this = &UnBCL::HeapMemoryManager::`vftable';
  UnBCL::HeapMemoryManager::InternalValidate(this, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x18003edd0  push    rbx
0x18003edd2  sub     rsp, 30h
0x18003edd6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18003eddf  mov     rbx, rcx
0x18003ede2  lea     rax, ??_7HeapMemoryManager@UnBCL@@6B@; const UnBCL::HeapMemoryManager::`vftable'
0x18003ede9  mov     [rcx], rax
0x18003edec  xor     edx, edx; void *
0x18003edee  call    ?InternalValidate@HeapMemoryManager@UnBCL@@AEAAXPEAX@Z; UnBCL::HeapMemoryManager::InternalValidate(void *)
0x18003edf3  lea     rcx, [rbx+8]; lpCriticalSection
0x18003edf7  call    cs:__imp_DeleteCriticalSection
0x18003edfd  mov     qword ptr [rbx+40h], 0
0x18003ee05  add     rsp, 30h
0x18003ee09  pop     rbx
0x18003ee0a  retn
```
