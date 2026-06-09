# std::unique_ptr<HrtfPersonalizationParams,std::default_delete<HrtfPersonalizationParams>>::~unique_ptr<HrtfPersonalizationParams,std::default_delete<HrtfPersonalizationParams>>(void)

- ea: `0x180004910`
- end: `0x180004935`
- name: `??1?$unique_ptr@UHrtfPersonalizationParams@@U?$default_delete@UHrtfPersonalizationParams@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f0ab`
- `0x18000f12d`
- `0x18000f1ba`

## callees

- `0x180004910`
- `0x180004c60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004929`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004929`

## pseudocode

```c
void __fastcall std::unique_ptr<HrtfPersonalizationParams>::~unique_ptr<HrtfPersonalizationParams>(
        HrtfPersonalizationParams **a1)
{
  HrtfPersonalizationParams *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    HrtfPersonalizationParams::~HrtfPersonalizationParams(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180004910  push    rbx
0x180004912  sub     rsp, 20h
0x180004916  mov     rbx, [rcx]
0x180004919  test    rbx, rbx
0x18000491c  jz      short loc_18000492F
0x18000491e  mov     rcx, rbx; this
0x180004921  call    ??1HrtfPersonalizationParams@@QEAA@XZ; HrtfPersonalizationParams::~HrtfPersonalizationParams(void)
0x180004926  mov     rcx, rbx
0x180004929  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000492f  add     rsp, 20h
0x180004933  pop     rbx
0x180004934  retn
```
