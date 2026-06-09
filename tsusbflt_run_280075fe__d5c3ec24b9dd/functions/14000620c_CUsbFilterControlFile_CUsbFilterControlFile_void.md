# CUsbFilterControlFile::~CUsbFilterControlFile(void)

- ea: `0x14000620c`
- end: `0x140006237`
- name: `??1CUsbFilterControlFile@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(CUsbFilterControlFile *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006efc`
- `0x1400094a0`

## callees

- `0x14000620c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000621d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000621d`

## pseudocode

```c
void __fastcall CUsbFilterControlFile::~CUsbFilterControlFile(void **this)
{
  void *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    ObfDereferenceObject(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x14000620c  push    rbx
0x14000620e  sub     rsp, 20h
0x140006212  mov     rbx, rcx
0x140006215  mov     rcx, [rcx]; Object
0x140006218  test    rcx, rcx
0x14000621b  jz      short loc_140006230
0x14000621d  call    cs:__imp_ObfDereferenceObject
0x140006224  nop     dword ptr [rax+rax+00h]
0x140006229  mov     qword ptr [rbx], 0
0x140006230  add     rsp, 20h
0x140006234  pop     rbx
0x140006235  retn
```
