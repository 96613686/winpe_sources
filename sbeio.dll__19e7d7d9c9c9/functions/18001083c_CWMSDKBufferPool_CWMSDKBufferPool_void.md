# CWMSDKBufferPool::~CWMSDKBufferPool(void)

- ea: `0x18001083c`
- end: `0x180010867`
- name: `??1CWMSDKBufferPool@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(CWMSDKBufferPool *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011690`

## callees

- `0x180029954`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180010853`
- `KERNEL32!DeleteCriticalSection` at `0x180010853`

## pseudocode

```c
void __fastcall CWMSDKBufferPool::~CWMSDKBufferPool(CWMSDKBufferPool *this)
{
  *(_QWORD *)this = &CWMSDKBufferPool::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  CVCellPool::_Cleanup((CWMSDKBufferPool *)((char *)this + 24));
}

```

## disassembly

```asm
0x18001083c  push    rbx
0x18001083e  sub     rsp, 20h
0x180010842  lea     rax, ??_7CWMSDKBufferPool@@6B@; const CWMSDKBufferPool::`vftable'
0x180010849  mov     rbx, rcx
0x18001084c  mov     [rcx], rax
0x18001084f  add     rcx, 58h ; 'X'; lpCriticalSection
0x180010853  call    cs:__imp_DeleteCriticalSection
0x180010859  lea     rcx, [rbx+18h]; this
0x18001085d  add     rsp, 20h
0x180010861  pop     rbx
0x180010862  jmp     ?_Cleanup@CVCellPool@@AEAAXXZ; CVCellPool::_Cleanup(void)
```
