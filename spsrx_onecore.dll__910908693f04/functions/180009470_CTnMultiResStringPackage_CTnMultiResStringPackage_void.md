# CTnMultiResStringPackage::~CTnMultiResStringPackage(void)

- ea: `0x180009470`
- end: `0x1800094b2`
- name: `??1CTnMultiResStringPackage@@QEAA@XZ`
- size: `66`
- prototype: `void __fastcall(CTnMultiResStringPackage *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cd70`
- `0x18000cef7`
- `0x18000cf10`
- `0x18000d01f`
- `0x18000d040`
- `0x18000d1a7`

## callees

- `0x180004cfc`
- `0x180009470`
- `0x18000973c`

## pseudocode

```c
void __fastcall CTnMultiResStringPackage::~CTnMultiResStringPackage(CTnMultiResStringPackage *this, unsigned int a2)
{
  _QWORD *v2; // rbx
  CTnMultiResStringPackage::SStrCost *v4; // rcx

  v2 = *(_QWORD **)this;
  while ( v2 )
  {
    v4 = (CTnMultiResStringPackage::SStrCost *)v2[2];
    v2 = (_QWORD *)*v2;
    if ( v4 )
      CTnMultiResStringPackage::SStrCost::`scalar deleting destructor'(v4, a2);
  }
  CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll((__int64)this);
  CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll((__int64)this);
}

```

## disassembly

```asm
0x180009470  mov     [rsp+arg_0], rbx
0x180009475  push    rdi
0x180009476  sub     rsp, 20h
0x18000947a  mov     rbx, [rcx]
0x18000947d  mov     rdi, rcx
0x180009480  jmp     short loc_180009493
0x180009482  mov     rcx, [rbx+10h]; this
0x180009486  mov     rbx, [rbx]
0x180009489  test    rcx, rcx
0x18000948c  jz      short loc_180009493
0x18000948e  call    ??_GSStrCost@CTnMultiResStringPackage@@QEAAPEAXI@Z; CTnMultiResStringPackage::SStrCost::`scalar deleting destructor'(uint)
0x180009493  test    rbx, rbx
0x180009496  jnz     short loc_180009482
0x180009498  mov     rcx, rdi
0x18000949b  call    ?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ; CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)
0x1800094a0  mov     rcx, rdi
0x1800094a3  mov     rbx, [rsp+28h+arg_0]
0x1800094a8  add     rsp, 20h
0x1800094ac  pop     rdi
0x1800094ad  jmp     ?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ; CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)
```
