# mi::MiAsyncOperation::~MiAsyncOperation(void)

- ea: `0x180027bbc`
- end: `0x180027bf1`
- name: `??1MiAsyncOperation@mi@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(mi::MiAsyncOperation *this, enum _MI_CancellationReason)`
- caller_count: `41`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a6a8`
- `0x18000cfa4`
- `0x180013a5c`
- `0x1800154a4`
- `0x1800162b8`
- `0x180016568`
- `0x18001935c`
- `0x18001da60`
- `0x18001decc`
- `0x18001e0d4`
- `0x18001e264`
- `0x18001e4a8`
- `0x18001e664`
- `0x18001e75c`
- `0x18001e8d8`
- `0x18001eaa0`
- `0x18001ec00`
- `0x18001ed90`
- `0x18001f058`
- `0x18001f220`
- `0x18001f3b0`
- `0x18001f540`
- `0x18001f6a0`
- `0x18001f910`
- `0x180021950`
- `0x180021a50`
- `0x1800225cc`
- `0x180022798`
- `0x18002295c`
- `0x180022b20`
- `0x180022ce4`
- `0x180027f90`
- `0x18002a665`
- `0x18002a945`
- `0x18002b36d`
- `0x18002b459`
- `0x18002b8a9`
- `0x18002b8f1`
- `0x18002b9a5`
- `0x18002bbb2`
- `0x18002bd38`

## callees

- `0x180027b38`
- `0x180027bbc`
- `0x180027c98`
- `0x180028094`

## pseudocode

```c
void __fastcall mi::MiAsyncOperation::~MiAsyncOperation(mi::MiAsyncOperation *this, enum _MI_CancellationReason a2)
{
  bool v2; // zf

  v2 = *((_QWORD *)this + 7) == 0;
  *(_QWORD *)this = &mi::MiAsyncOperation::`vftable';
  if ( !v2 )
    mi::MiOperation::Cancel(this, a2);
  std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs>((_QWORD *)this + 9);
  mi::MiOperation::~MiOperation(this);
}

```

## disassembly

```asm
0x180027bbc  push    rbx
0x180027bbe  sub     rsp, 20h
0x180027bc2  cmp     qword ptr [rcx+38h], 0
0x180027bc7  lea     rax, ??_7MiAsyncOperation@mi@@6B@; const mi::MiAsyncOperation::`vftable'
0x180027bce  mov     [rcx], rax
0x180027bd1  mov     rbx, rcx
0x180027bd4  jz      short loc_180027BDB
0x180027bd6  call    ?Cancel@MiOperation@mi@@QEAAXW4_MI_CancellationReason@@@Z; mi::MiOperation::Cancel(_MI_CancellationReason)
0x180027bdb  lea     rcx, [rbx+48h]
0x180027bdf  call    ??1?$unique_ptr@UMiOperationArgs@MiAsyncOperation@mi@@U?$default_delete@UMiOperationArgs@MiAsyncOperation@mi@@@std@@@std@@QEAA@XZ; std::unique_ptr<mi::MiAsyncOperation::MiOperationArgs>::~unique_ptr<mi::MiAsyncOperation::MiOperationArgs>(void)
0x180027be4  mov     rcx, rbx; this
0x180027be7  add     rsp, 20h
0x180027beb  pop     rbx
0x180027bec  jmp     ??1MiOperation@mi@@UEAA@XZ; mi::MiOperation::~MiOperation(void)
```
