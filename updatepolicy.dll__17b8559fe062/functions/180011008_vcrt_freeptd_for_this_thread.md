# __vcrt_freeptd_for_this_thread

- ea: `0x180011008`
- end: `0x18001104f`
- name: `__vcrt_freeptd_for_this_thread`
- size: `71`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010cb4`

## callees

- `0x18000ec91`
- `0x180011008`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180011019`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180011019`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18001102a`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x18001102a`

## pseudocode

```c
void _vcrt_freeptd_for_this_thread()
{
  __int64 *Value; // rbx

  if ( dwFlsIndex != -1 )
  {
    Value = (__int64 *)FlsGetValue(dwFlsIndex);
    FlsSetValue(dwFlsIndex, 0);
    if ( Value )
    {
      if ( Value != qword_18001FDC0 )
        free_base(Value);
    }
  }
}

```

## disassembly

```asm
0x180011008  push    rbx
0x18001100a  sub     rsp, 20h
0x18001100e  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180011014  cmp     ecx, 0FFFFFFFFh
0x180011017  jz      short loc_180011049
0x180011019  call    cs:__imp_FlsGetValue
0x18001101f  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180011025  xor     edx, edx; lpFlsData
0x180011027  mov     rbx, rax
0x18001102a  call    cs:__imp_FlsSetValue
0x180011030  test    rbx, rbx
0x180011033  jz      short loc_180011049
0x180011035  lea     rax, qword_18001FDC0
0x18001103c  cmp     rbx, rax
0x18001103f  jz      short loc_180011049
0x180011041  mov     rcx, rbx; Block
0x180011044  call    _free_base
0x180011049  add     rsp, 20h
0x18001104d  pop     rbx
0x18001104e  retn
```
