# CXmlValidator::~CXmlValidator(void)

- ea: `0x1800166b4`
- end: `0x1800166de`
- name: `??1CXmlValidator@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CXmlValidator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d21c`

## callees

- `0x1800166b4`
- `0x180019010`

## pseudocode

```c
void __fastcall CXmlValidator::~CXmlValidator(CXmlValidator *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800166b4  push    rbx
0x1800166b6  sub     rsp, 20h
0x1800166ba  mov     rbx, rcx
0x1800166bd  mov     rcx, [rcx]
0x1800166c0  test    rcx, rcx
0x1800166c3  jz      short loc_1800166D8
0x1800166c5  mov     rax, [rcx]
0x1800166c8  mov     rax, [rax+10h]
0x1800166cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166d1  mov     qword ptr [rbx], 0
0x1800166d8  add     rsp, 20h
0x1800166dc  pop     rbx
0x1800166dd  retn
```
