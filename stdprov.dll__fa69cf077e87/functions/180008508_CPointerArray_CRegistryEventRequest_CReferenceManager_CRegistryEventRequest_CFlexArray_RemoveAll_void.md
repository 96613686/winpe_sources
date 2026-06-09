# CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::RemoveAll(void)

- ea: `0x180008508`
- end: `0x180008568`
- name: `?RemoveAll@?$CPointerArray@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@VCFlexArray@@@@QEAAXXZ`
- size: `96`
- prototype: `void __fastcall(CFlexArray *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008370`
- `0x18000ba40`

## callees

- `0x180008508`
- `0x18000a2e0`

## import_xrefs

- `wbemcomn!?SetAt@CFlexArray@@QEAAXHPEAX@Z` at `0x180008536`
- `wbemcomn!?SetAt@CFlexArray@@QEAAXHPEAX@Z` at `0x180008536`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x180008561`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008525`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008525`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::RemoveAll(
        CFlexArray *a1)
{
  int i; // ebx
  CRegistryEventRequest *v3; // rsi

  for ( i = 0; i < *(_DWORD *)a1; ++i )
  {
    v3 = (CRegistryEventRequest *)CFlexArray::GetAt(a1, i);
    CFlexArray::SetAt(a1, i, 0);
    if ( v3 )
      CRegistryEventRequest::Release(v3);
  }
  CFlexArray::Empty(a1);
}

```

## disassembly

```asm
0x180008508  mov     [rsp+arg_0], rbx
0x18000850d  mov     [rsp+arg_8], rsi
0x180008512  push    rdi
0x180008513  sub     rsp, 20h
0x180008517  xor     ebx, ebx
0x180008519  mov     rdi, rcx
0x18000851c  cmp     [rcx], ebx
0x18000851e  jle     short loc_18000854F
0x180008520  mov     edx, ebx
0x180008522  mov     rcx, rdi
0x180008525  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000852b  xor     r8d, r8d
0x18000852e  mov     edx, ebx
0x180008530  mov     rcx, rdi
0x180008533  mov     rsi, rax
0x180008536  call    cs:__imp_?SetAt@CFlexArray@@QEAAXHPEAX@Z; CFlexArray::SetAt(int,void *)
0x18000853c  test    rsi, rsi
0x18000853f  jz      short loc_180008549
0x180008541  mov     rcx, rsi; this
0x180008544  call    ?Release@CRegistryEventRequest@@QEAAJXZ; CRegistryEventRequest::Release(void)
0x180008549  inc     ebx
0x18000854b  cmp     ebx, [rdi]
0x18000854d  jl      short loc_180008520
0x18000854f  mov     rcx, rdi
0x180008552  mov     rbx, [rsp+28h+arg_0]
0x180008557  mov     rsi, [rsp+28h+arg_8]
0x18000855c  add     rsp, 20h
0x180008560  pop     rdi
0x180008561  jmp     cs:__imp_?Empty@CFlexArray@@QEAAXXZ; CFlexArray::Empty(void)
```
