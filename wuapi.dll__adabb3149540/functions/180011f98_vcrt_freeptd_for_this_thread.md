# __vcrt_freeptd_for_this_thread

- ea: `0x180011f98`
- end: `0x180011fdf`
- name: `__vcrt_freeptd_for_this_thread`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011c44`

## callees

- `0x18000fc2a`
- `0x180011f98`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180011fba`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180011fba`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180011fa9`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180011fa9`

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
      if ( Value != qword_180021DD0 )
        free_base(Value);
    }
  }
}

```

## disassembly

```asm
0x180011f98  push    rbx
0x180011f9a  sub     rsp, 20h
0x180011f9e  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180011fa4  cmp     ecx, 0FFFFFFFFh
0x180011fa7  jz      short loc_180011FD9
0x180011fa9  call    cs:__imp_FlsGetValue
0x180011faf  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180011fb5  xor     edx, edx; lpFlsData
0x180011fb7  mov     rbx, rax
0x180011fba  call    cs:__imp_FlsSetValue
0x180011fc0  test    rbx, rbx
0x180011fc3  jz      short loc_180011FD9
0x180011fc5  lea     rax, qword_180021DD0
0x180011fcc  cmp     rbx, rax
0x180011fcf  jz      short loc_180011FD9
0x180011fd1  mov     rcx, rbx; Block
0x180011fd4  call    _free_base
0x180011fd9  add     rsp, 20h
0x180011fdd  pop     rbx
0x180011fde  retn
```
