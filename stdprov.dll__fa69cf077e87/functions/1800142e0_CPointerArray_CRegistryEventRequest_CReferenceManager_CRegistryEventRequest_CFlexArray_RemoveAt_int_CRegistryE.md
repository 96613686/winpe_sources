# CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::RemoveAt(int,CRegistryEventRequest * *)

- ea: `0x1800142e0`
- end: `0x18001432f`
- name: `?RemoveAt@?$CPointerArray@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@VCFlexArray@@@@QEAA_NHPEAPEAVCRegistryEventRequest@@@Z`
- size: `79`
- prototype: `char __fastcall(CFlexArray *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008030`

## callees

- `0x18000a2e0`
- `0x1800142e0`

## import_xrefs

- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180014302`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180014302`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800142f4`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800142f4`

## pseudocode

```c
char __fastcall CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::RemoveAt(
        CFlexArray *a1,
        int a2)
{
  CRegistryEventRequest *v4; // rsi

  v4 = (CRegistryEventRequest *)CFlexArray::GetAt(a1, a2);
  if ( CFlexArray::RemoveAt(a1, a2) )
    return 0;
  if ( v4 )
    CRegistryEventRequest::Release(v4);
  return 1;
}

```

## disassembly

```asm
0x1800142e0  mov     [rsp+arg_0], rbx
0x1800142e5  mov     [rsp+arg_8], rsi
0x1800142ea  push    rdi
0x1800142eb  sub     rsp, 20h
0x1800142ef  mov     ebx, edx
0x1800142f1  mov     rdi, rcx
0x1800142f4  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800142fa  mov     edx, ebx
0x1800142fc  mov     rcx, rdi
0x1800142ff  mov     rsi, rax
0x180014302  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180014308  test    eax, eax
0x18001430a  jz      short loc_180014310
0x18001430c  xor     al, al
0x18001430e  jmp     short loc_18001431F
0x180014310  test    rsi, rsi
0x180014313  jz      short loc_18001431D
0x180014315  mov     rcx, rsi; this
0x180014318  call    ?Release@CRegistryEventRequest@@QEAAJXZ; CRegistryEventRequest::Release(void)
0x18001431d  mov     al, 1
0x18001431f  mov     rbx, [rsp+28h+arg_0]
0x180014324  mov     rsi, [rsp+28h+arg_8]
0x180014329  add     rsp, 20h
0x18001432d  pop     rdi
0x18001432e  retn
```
