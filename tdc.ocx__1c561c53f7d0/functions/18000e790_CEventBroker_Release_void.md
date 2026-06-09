# CEventBroker::Release(void)

- ea: `0x18000e790`
- end: `0x18000e7c7`
- name: `?Release@CEventBroker@@UEAAKXZ`
- size: `55`
- prototype: `unsigned int __fastcall(CEventBroker *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001194`
- `0x18000e700`
- `0x18000e790`

## pseudocode

```c
__int64 __fastcall CEventBroker::Release(CEventBroker *this)
{
  bool v1; // zf
  unsigned int v3; // edi

  v1 = (*((_DWORD *)this + 4))-- == 1;
  v3 = *((_DWORD *)this + 4);
  if ( v1 )
  {
    *((_DWORD *)this + 4) = 0xFFFF;
    CEventBroker::~CEventBroker(this);
    operator delete(this);
  }
  return v3;
}

```

## disassembly

```asm
0x18000e790  mov     [rsp+arg_0], rbx
0x18000e795  push    rdi
0x18000e796  sub     rsp, 20h
0x18000e79a  add     dword ptr [rcx+10h], 0FFFFFFFFh
0x18000e79e  mov     rbx, rcx
0x18000e7a1  mov     edi, [rcx+10h]
0x18000e7a4  jnz     short loc_18000E7BA
0x18000e7a6  mov     dword ptr [rcx+10h], 0FFFFh
0x18000e7ad  call    ??1CEventBroker@@QEAA@XZ; CEventBroker::~CEventBroker(void)
0x18000e7b2  mov     rcx, rbx; Block
0x18000e7b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e7ba  mov     rbx, [rsp+28h+arg_0]
0x18000e7bf  mov     eax, edi
0x18000e7c1  add     rsp, 20h
0x18000e7c5  pop     rdi
0x18000e7c6  retn
```
