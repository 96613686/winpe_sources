# FilterDeRef

- ea: `0x14000443c`
- end: `0x140004484`
- name: `FilterDeRef`
- size: `72`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140003fe8`
- `0x1400041a0`
- `0x140005bf0`
- `0x140006bc0`
- `0x14000c5b0`
- `0x14000d690`

## callees

- `0x14000443c`
- `0x14000c7b0`
- `0x14000cd98`

## pseudocode

```c
void __fastcall FilterDeRef(PVOID VirtualAddress)
{
  if ( *((int *)VirtualAddress + 4) <= 0 )
    TraceAssert((int)"pFilterCtx->RefCount >0", (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.h", 367);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)VirtualAddress + 4, 0xFFFFFFFF) == 1 )
    FilterDeInit((PVOID **)VirtualAddress);
}

```

## disassembly

```asm
0x14000443c  push    rbx
0x14000443e  sub     rsp, 20h
0x140004442  cmp     dword ptr [rcx+10h], 0
0x140004446  mov     rbx, rcx
0x140004449  jle     short loc_14000445F
0x14000444b  or      eax, 0FFFFFFFFh
0x14000444e  lock xadd [rbx+10h], eax
0x140004453  cmp     eax, 1
0x140004456  jz      short loc_14000447A
0x140004458  add     rsp, 20h
0x14000445c  pop     rbx
0x14000445d  retn
0x14000445f  mov     r8d, 16Fh
0x140004465  lea     rdx, aOnecoreuapNetV; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000446c  lea     rcx, aPfilterctxRefc; "pFilterCtx->RefCount >0"
0x140004473  call    TraceAssert
0x140004478  jmp     short loc_14000444B
0x14000447a  mov     rcx, rbx; VirtualAddress
0x14000447d  call    FilterDeInit
0x140004482  jmp     short loc_140004458
```
