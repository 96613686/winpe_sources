# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::~CTempBuffer<ushort,1024,ATL::CCRTAllocator>(void)

- ea: `0x1400021dc`
- end: `0x1400021f3`
- name: `??1?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007730`

## callees

- `0x1400021dc`
- `0x14000339c`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::~CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>(
        void **a1)
{
  if ( *a1 != a1 + 1 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(a1);
}

```

## disassembly

```asm
0x1400021dc  sub     rsp, 28h
0x1400021e0  lea     rax, [rcx+8]
0x1400021e4  cmp     [rcx], rax
0x1400021e7  jz      short loc_1400021EE
0x1400021e9  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400021ee  add     rsp, 28h
0x1400021f2  retn
```
