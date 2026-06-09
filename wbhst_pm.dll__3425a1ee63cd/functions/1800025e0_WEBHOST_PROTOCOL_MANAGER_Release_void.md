# WEBHOST_PROTOCOL_MANAGER::Release(void)

- ea: `0x1800025e0`
- end: `0x180002619`
- name: `?Release@WEBHOST_PROTOCOL_MANAGER@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002620`
- `0x180002630`
- `0x180002640`
- `0x180002650`
- `0x180002660`

## callees

- `0x180001048`
- `0x180001958`
- `0x1800025e0`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::Release(WEBHOST_PROTOCOL_MANAGER *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 13);
  if ( !v2 && this )
  {
    WEBHOST_PROTOCOL_MANAGER::~WEBHOST_PROTOCOL_MANAGER(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1800025e0  mov     [rsp+arg_0], rbx
0x1800025e5  push    rdi
0x1800025e6  sub     rsp, 20h
0x1800025ea  mov     rbx, rcx
0x1800025ed  or      edi, 0FFFFFFFFh
0x1800025f0  lock xadd [rcx+34h], edi
0x1800025f5  sub     edi, 1
0x1800025f8  jnz     short loc_18000260C
0x1800025fa  test    rcx, rcx
0x1800025fd  jz      short loc_18000260C
0x1800025ff  call    ??1WEBHOST_PROTOCOL_MANAGER@@QEAA@XZ; WEBHOST_PROTOCOL_MANAGER::~WEBHOST_PROTOCOL_MANAGER(void)
0x180002604  mov     rcx, rbx; Block
0x180002607  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000260c  mov     rbx, [rsp+28h+arg_0]
0x180002611  mov     eax, edi
0x180002613  add     rsp, 20h
0x180002617  pop     rdi
0x180002618  retn
```
