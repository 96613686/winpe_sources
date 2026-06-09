# FilterAddRef

- ea: `0x140006960`
- end: `0x140006995`
- name: `FilterAddRef`
- size: `53`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400027d0`
- `0x140006790`
- `0x140006bc0`
- `0x14000c5b0`
- `0x14000cd04`
- `0x14000d690`

## callees

- `0x140006960`
- `0x14000cd98`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall FilterAddRef(__int64 a1)
{
  PDEVICE_OBJECT *result; // rax

  if ( *(int *)(a1 + 16) < 0 )
    result = TraceAssert((int)"pFilterCtx->RefCount >=0", (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.h", 359);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x140006960  push    rbx
0x140006962  sub     rsp, 20h
0x140006966  cmp     dword ptr [rcx+10h], 0
0x14000696a  mov     rbx, rcx
0x14000696d  jl      short loc_14000697A
0x14000696f  lock inc dword ptr [rbx+10h]
0x140006973  add     rsp, 20h
0x140006977  pop     rbx
0x140006978  retn
0x14000697a  mov     r8d, 167h
0x140006980  lea     rdx, aOnecoreuapNetV; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140006987  lea     rcx, aPfilterctxRefc_0; "pFilterCtx->RefCount >=0"
0x14000698e  call    TraceAssert
0x140006993  jmp     short loc_14000696F
```
