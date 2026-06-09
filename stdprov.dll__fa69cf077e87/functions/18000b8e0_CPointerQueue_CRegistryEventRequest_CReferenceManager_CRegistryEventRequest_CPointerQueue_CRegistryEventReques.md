# CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>(void)

- ea: `0x18000b8e0`
- end: `0x18000b914`
- name: `??1?$CPointerQueue@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CFlexQueue *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000840c`
- `0x18000b8c8`
- `0x1800161ec`
- `0x180016442`
- `0x1800165b1`

## callees

- `0x18000a2e0`
- `0x18000b8e0`

## import_xrefs

- `wbemcomn!??1CFlexQueue@@QEAA@XZ` at `0x18000b90d`
- `wbemcomn!?Dequeue@CFlexQueue@@QEAAPEAXXZ` at `0x18000b8fa`
- `wbemcomn!?Dequeue@CFlexQueue@@QEAAPEAXXZ` at `0x18000b8fa`

## pseudocode

```c
void __fastcall CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>(
        CFlexQueue *a1)
{
  CFlexQueue *i; // rbx
  CRegistryEventRequest *v2; // rax

  for ( i = a1; ; a1 = i )
  {
    v2 = (CRegistryEventRequest *)CFlexQueue::Dequeue(a1);
    if ( !v2 )
      break;
    CRegistryEventRequest::Release(v2);
  }
  CFlexQueue::~CFlexQueue(i);
}

```

## disassembly

```asm
0x18000b8e0  mov     [rsp+arg_0], rcx
0x18000b8e5  push    rbx
0x18000b8e6  sub     rsp, 20h
0x18000b8ea  mov     rbx, rcx
0x18000b8ed  jmp     short loc_18000B8FA
0x18000b8ef  mov     rcx, rax; this
0x18000b8f2  call    ?Release@CRegistryEventRequest@@QEAAJXZ; CRegistryEventRequest::Release(void)
0x18000b8f7  mov     rcx, rbx
0x18000b8fa  call    cs:__imp_?Dequeue@CFlexQueue@@QEAAPEAXXZ; CFlexQueue::Dequeue(void)
0x18000b900  test    rax, rax
0x18000b903  jnz     short loc_18000B8EF
0x18000b905  mov     rcx, rbx
0x18000b908  add     rsp, 20h
0x18000b90c  pop     rbx
0x18000b90d  jmp     cs:__imp_??1CFlexQueue@@QEAA@XZ; CFlexQueue::~CFlexQueue(void)
```
