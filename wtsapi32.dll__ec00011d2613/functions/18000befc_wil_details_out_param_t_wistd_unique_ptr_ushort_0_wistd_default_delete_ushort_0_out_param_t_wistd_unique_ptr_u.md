# wil::details::out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>::~out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>(void)

- ea: `0x18000befc`
- end: `0x18000bf25`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@details@wil@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c0c0`
- `0x18000c270`

## callees

- `0x180006734`
- `0x18000befc`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000befc  sub     rsp, 28h
0x18000bf00  cmp     byte ptr [rcx+10h], 0
0x18000bf04  jz      short loc_18000BF20
0x18000bf06  mov     rdx, [rcx]
0x18000bf09  mov     rax, [rcx+8]
0x18000bf0d  mov     r8, [rdx]
0x18000bf10  mov     [rdx], rax
0x18000bf13  test    r8, r8
0x18000bf16  jz      short loc_18000BF20
0x18000bf18  mov     rcx, r8; Block
0x18000bf1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bf20  add     rsp, 28h
0x18000bf24  retn
```
