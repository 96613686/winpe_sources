# CAgreementElement::`scalar deleting destructor'(uint)

- ea: `0x18000959c`
- end: `0x1800095f0`
- name: `??_GCAgreementElement@@QEAAPEAXI@Z`
- size: `84`
- prototype: `void *__fastcall(CAgreementElement *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800092d0`
- `0x180009344`
- `0x18000a614`
- `0x18000b208`

## callees

- `0x180002594`
- `0x180004f5c`
- `0x18000959c`

## pseudocode

```c
CAgreementElement *__fastcall CAgreementElement::`scalar deleting destructor'(CAgreementElement *this)
{
  CSPPlex **v2; // rcx

  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = 0;
  v2 = (CSPPlex **)*((_QWORD *)this + 5);
  if ( v2 )
  {
    CSPPlex::FreeDataChain(v2);
    *((_QWORD *)this + 5) = 0;
  }
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000959c  push    rbx
0x18000959e  sub     rsp, 20h
0x1800095a2  mov     rbx, rcx
0x1800095a5  mov     dword ptr [rcx+18h], 0
0x1800095ac  mov     qword ptr [rcx+20h], 0
0x1800095b4  mov     qword ptr [rcx+10h], 0
0x1800095bc  mov     qword ptr [rcx+8], 0
0x1800095c4  mov     rcx, [rcx+28h]; this
0x1800095c8  test    rcx, rcx
0x1800095cb  jz      short loc_1800095DA
0x1800095cd  call    ?FreeDataChain@CSPPlex@@QEAAXXZ; CSPPlex::FreeDataChain(void)
0x1800095d2  mov     qword ptr [rbx+28h], 0
0x1800095da  mov     edx, 38h ; '8'; unsigned __int64
0x1800095df  mov     rcx, rbx; void *
0x1800095e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800095e7  mov     rax, rbx
0x1800095ea  add     rsp, 20h
0x1800095ee  pop     rbx
0x1800095ef  retn
```
