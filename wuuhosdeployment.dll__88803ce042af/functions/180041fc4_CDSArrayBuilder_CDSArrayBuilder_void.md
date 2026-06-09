# CDSArrayBuilder::~CDSArrayBuilder(void)

- ea: `0x180041fc4`
- end: `0x180041fe8`
- name: `??1CDSArrayBuilder@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CDSArrayBuilder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800392ec`
- `0x180039b40`
- `0x18004b0af`

## callees

- `0x180041fc4`
- `0x180041ff0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041fdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041fdb`

## pseudocode

```c
void __fastcall CDSArrayBuilder::~CDSArrayBuilder(CDSArrayBuilder *this, int a2)
{
  void *v3; // rcx

  CDSArrayBuilder::Cleanup(this, a2);
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
    CoTaskMemFree(v3);
}

```

## disassembly

```asm
0x180041fc4  push    rbx
0x180041fc6  sub     rsp, 20h
0x180041fca  mov     rbx, rcx
0x180041fcd  call    ?Cleanup@CDSArrayBuilder@@IEAAXH@Z; CDSArrayBuilder::Cleanup(int)
0x180041fd2  mov     rcx, [rbx+8]; pv
0x180041fd6  test    rcx, rcx
0x180041fd9  jz      short loc_180041FE2
0x180041fdb  call    cs:__imp_CoTaskMemFree
0x180041fe1  nop
0x180041fe2  add     rsp, 20h
0x180041fe6  pop     rbx
0x180041fe7  retn
```
