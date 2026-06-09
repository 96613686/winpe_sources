# __vcrt_freeptd_for_this_thread

- ea: `0x180011f48`
- end: `0x180011f8f`
- name: `__vcrt_freeptd_for_this_thread`
- size: `71`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011ca4`

## callees

- `0x1800101a4`
- `0x180011f48`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180011f59`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180011f59`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180011f6a`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180011f6a`

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
      if ( Value != qword_18001FE30 )
        free_base(Value);
    }
  }
}

```

## disassembly

```asm
0x180011f48  push    rbx
0x180011f4a  sub     rsp, 20h
0x180011f4e  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180011f54  cmp     ecx, 0FFFFFFFFh
0x180011f57  jz      short loc_180011F89
0x180011f59  call    cs:__imp_FlsGetValue
0x180011f5f  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180011f65  xor     edx, edx; lpFlsData
0x180011f67  mov     rbx, rax
0x180011f6a  call    cs:__imp_FlsSetValue
0x180011f70  test    rbx, rbx
0x180011f73  jz      short loc_180011F89
0x180011f75  lea     rax, qword_18001FE30
0x180011f7c  cmp     rbx, rax
0x180011f7f  jz      short loc_180011F89
0x180011f81  mov     rcx, rbx; Block
0x180011f84  call    _free_base
0x180011f89  add     rsp, 20h
0x180011f8d  pop     rbx
0x180011f8e  retn
```
