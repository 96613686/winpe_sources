# UnBCL::StreamCounter::~StreamCounter(void)

- ea: `0x1800045c0`
- end: `0x1800045dd`
- name: `??1StreamCounter@UnBCL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(UnBCL::StreamCounter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800045d1`
- `KERNEL32!DeleteCriticalSection` at `0x1800045d1`

## pseudocode

```c
void __fastcall UnBCL::StreamCounter::~StreamCounter(UnBCL::StreamCounter *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800045c0  sub     rsp, 38h
0x1800045c4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800045cd  add     rcx, 8; lpCriticalSection
0x1800045d1  call    cs:__imp_DeleteCriticalSection
0x1800045d7  nop
0x1800045d8  add     rsp, 38h
0x1800045dc  retn
```
