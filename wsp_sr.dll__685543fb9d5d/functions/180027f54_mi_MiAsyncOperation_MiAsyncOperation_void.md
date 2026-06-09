# mi::MiAsyncOperation::~MiAsyncOperation(void)

- ea: `0x180027f54`
- end: `0x180027f89`
- name: `??1MiAsyncOperation@mi@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(mi::MiAsyncOperation *__hidden this)`
- caller_count: `41`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a804`
- `0x18000cec8`
- `0x180013964`
- `0x180015358`
- `0x180016170`
- `0x180016424`
- `0x180019388`
- `0x18001db88`
- `0x18001dff4`
- `0x18001e200`
- `0x18001e390`
- `0x18001e5d4`
- `0x18001e790`
- `0x18001e88c`
- `0x18001ea08`
- `0x18001ebd0`
- `0x18001ed30`
- `0x18001eec0`
- `0x18001f18c`
- `0x18001f354`
- `0x18001f4e4`
- `0x18001f674`
- `0x18001f7d8`
- `0x18001fa48`
- `0x180021af0`
- `0x180021bf0`
- `0x180022788`
- `0x180022958`
- `0x180022b1c`
- `0x180022ce0`
- `0x180022ea4`
- `0x180028350`
- `0x18002ab32`
- `0x18002ae12`
- `0x18002b84b`
- `0x18002b939`
- `0x18002bd91`
- `0x18002bdd9`
- `0x18002be8d`
- `0x18002c0a0`
- `0x18002c22c`

## callees

- `0x180027eb4`
- `0x180027f54`
- `0x180028030`
- `0x180028458`

## pseudocode

```c
void __fastcall mi::MiAsyncOperation::~MiAsyncOperation(mi::MiAsyncOperation *this, enum _MI_CancellationReason a2)
{
  bool v2; // zf

  v2 = *((_QWORD *)this + 7) == 0;
  *(_QWORD *)this = &mi::MiAsyncOperation::`vftable';
  if ( !v2 )
    mi::MiOperation::Cancel(this, a2);
  std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs>((char *)this + 72);
  mi::MiOperation::~MiOperation(this);
}

```

## disassembly

```asm
0x180027f54  push    rbx
0x180027f56  sub     rsp, 20h
0x180027f5a  cmp     qword ptr [rcx+38h], 0
0x180027f5f  lea     rax, ??_7MiAsyncOperation@mi@@6B@; const mi::MiAsyncOperation::`vftable'
0x180027f66  mov     [rcx], rax
0x180027f69  mov     rbx, rcx
0x180027f6c  jz      short loc_180027F73
0x180027f6e  call    ?Cancel@MiOperation@mi@@QEAAXW4_MI_CancellationReason@@@Z; mi::MiOperation::Cancel(_MI_CancellationReason)
0x180027f73  lea     rcx, [rbx+48h]
0x180027f77  call    ??1?$unique_ptr@UMiOperationArgs@MiAsyncOperation@mi@@U?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@@std@@QEAA@XZ; std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs>(void)
0x180027f7c  mov     rcx, rbx; this
0x180027f7f  add     rsp, 20h
0x180027f83  pop     rbx
0x180027f84  jmp     ??1MiOperation@mi@@UEAA@XZ; mi::MiOperation::~MiOperation(void)
```
