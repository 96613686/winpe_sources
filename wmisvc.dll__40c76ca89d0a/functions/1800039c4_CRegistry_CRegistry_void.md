# CRegistry::~CRegistry(void)

- ea: `0x1800039c4`
- end: `0x1800039ed`
- name: `??1CRegistry@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002ea4`
- `0x1800174ec`
- `0x18001d744`
- `0x18001ec3c`

## callees

- `0x180003958`
- `0x1800039c4`
- `0x180004194`

## pseudocode

```c
void __fastcall CRegistry::~CRegistry(CRegistry *this)
{
  CRegistry *v1; // rbx

  try
  {
    v1 = this;
    CRegistry::Close(this);
  }
  catch ( CHeap_Exception )
  {
    v1 = this;
  }
  v1 = this;
}

```

## disassembly

```asm
0x1800039c4  mov     [rsp+arg_0], rcx
0x1800039c9  push    rbx
0x1800039ca  sub     rsp, 20h
0x1800039ce  mov     rbx, rcx
0x1800039d1  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x1800039d6  nop
0x1800039d7  lea     rcx, [rbx+18h]; this
0x1800039db  add     rsp, 20h
0x1800039df  pop     rbx
0x1800039e0  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800039e5  mov     rbx, [rsp+28h+arg_0]
0x1800039ea  jmp     short loc_1800039D7
```
