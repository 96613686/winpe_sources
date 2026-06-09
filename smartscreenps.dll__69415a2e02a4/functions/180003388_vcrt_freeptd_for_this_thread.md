# __vcrt_freeptd_for_this_thread

- ea: `0x180003388`
- end: `0x1800033cf`
- name: `__vcrt_freeptd_for_this_thread`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800031f8`

## callees

- `0x180003388`
- `0x180006956`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180003399`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180003399`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x1800033aa`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x1800033aa`

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
      if ( Value != qword_18001A330 )
        free_base_0(Value);
    }
  }
}

```

## disassembly

```asm
0x180003388  push    rbx
0x18000338a  sub     rsp, 20h
0x18000338e  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x180003394  cmp     ecx, 0FFFFFFFFh
0x180003397  jz      short loc_1800033C9
0x180003399  call    cs:__imp_FlsGetValue
0x18000339f  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x1800033a5  xor     edx, edx; lpFlsData
0x1800033a7  mov     rbx, rax
0x1800033aa  call    cs:__imp_FlsSetValue
0x1800033b0  test    rbx, rbx
0x1800033b3  jz      short loc_1800033C9
0x1800033b5  lea     rax, qword_18001A330
0x1800033bc  cmp     rbx, rax
0x1800033bf  jz      short loc_1800033C9
0x1800033c1  mov     rcx, rbx; Block
0x1800033c4  call    _free_base_0
0x1800033c9  add     rsp, 20h
0x1800033cd  pop     rbx
0x1800033ce  retn
```
