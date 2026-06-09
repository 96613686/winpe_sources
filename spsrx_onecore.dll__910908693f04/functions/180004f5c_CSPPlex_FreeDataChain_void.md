# CSPPlex::FreeDataChain(void)

- ea: `0x180004f5c`
- end: `0x180004f86`
- name: `?FreeDataChain@CSPPlex@@QEAAXXZ`
- size: `42`
- prototype: `void __fastcall(CSPPlex *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cfc`
- `0x180009218`
- `0x180009344`
- `0x18000959c`
- `0x18000a614`
- `0x18000aad0`
- `0x18000b954`
- `0x18000bf40`
- `0x18000c2b8`
- `0x18000c514`
- `0x18000d040`
- `0x18000d588`

## callees

- `0x180001c50`
- `0x180004f5c`

## pseudocode

```c
void __fastcall CSPPlex::FreeDataChain(CSPPlex **this)
{
  CSPPlex *v1; // rbx

  if ( this )
  {
    do
    {
      v1 = *this;
      CWinHeap::Free(&g_heap, this);
      this = (CSPPlex **)v1;
    }
    while ( v1 );
  }
}

```

## disassembly

```asm
0x180004f5c  test    rcx, rcx
0x180004f5f  jz      short locret_180004F85
0x180004f61  push    rbx
0x180004f62  sub     rsp, 20h
0x180004f66  mov     rbx, [rcx]
0x180004f69  mov     rdx, rcx; void *
0x180004f6c  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180004f73  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180004f78  mov     rcx, rbx
0x180004f7b  test    rbx, rbx
0x180004f7e  jnz     short loc_180004F66
0x180004f80  add     rsp, 20h
0x180004f84  pop     rbx
0x180004f85  retn
```
