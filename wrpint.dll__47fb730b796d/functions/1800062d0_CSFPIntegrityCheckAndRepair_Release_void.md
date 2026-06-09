# CSFPIntegrityCheckAndRepair::Release(void)

- ea: `0x1800062d0`
- end: `0x180006300`
- name: `?Release@CSFPIntegrityCheckAndRepair@@UEAAKXZ`
- size: `48`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800012f4`
- `0x180002694`
- `0x1800062d0`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::Release(CSFPIntegrityCheckAndRepair *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 3);
  if ( !(_DWORD)result )
  {
    if ( this )
    {
      CSFPIntegrityCheckAndRepair::~CSFPIntegrityCheckAndRepair(this);
      operator delete(this);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800062d0  push    rbx
0x1800062d2  sub     rsp, 20h
0x1800062d6  mov     rbx, rcx
0x1800062d9  or      eax, 0FFFFFFFFh
0x1800062dc  lock xadd [rcx+0Ch], eax
0x1800062e1  sub     eax, 1
0x1800062e4  jnz     short loc_1800062FA
0x1800062e6  test    rcx, rcx
0x1800062e9  jz      short loc_1800062F8
0x1800062eb  call    ??1CSFPIntegrityCheckAndRepair@@QEAA@XZ; CSFPIntegrityCheckAndRepair::~CSFPIntegrityCheckAndRepair(void)
0x1800062f0  mov     rcx, rbx; Block
0x1800062f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062f8  xor     eax, eax
0x1800062fa  add     rsp, 20h
0x1800062fe  pop     rbx
0x1800062ff  retn
```
