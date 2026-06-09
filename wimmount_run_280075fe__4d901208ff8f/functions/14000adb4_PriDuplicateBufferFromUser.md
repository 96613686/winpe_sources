# PriDuplicateBufferFromUser

- ea: `0x14000adb4`
- end: `0x14000ae39`
- name: `PriDuplicateBufferFromUser`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b070`
- `0x14000b418`
- `0x14000b614`

## callees

- `0x140001044`
- `0x14000adb4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ade3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ade3`

## pseudocode

```c
__int64 __fastcall PriDuplicateBufferFromUser(_QWORD *a1, void *a2, unsigned int a3)
{
  unsigned int v5; // edi
  size_t v6; // r14
  PVOID PoolWithTag; // rax
  PVOID v8; // rbx

  v5 = 0;
  v6 = a3;
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, a3, 0x574D6365u);
  v8 = PoolWithTag;
  if ( PoolWithTag )
  {
    RtlCopyFromUser(PoolWithTag, a2, v6);
    *a1 = v8;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v5;
}

```

## disassembly

```asm
0x14000adb4  mov     [rsp+arg_8], rbx
0x14000adb9  mov     [rsp+arg_10], rsi
0x14000adbe  mov     [rsp+arg_0], rcx
0x14000adc3  push    rdi
0x14000adc4  push    r14
0x14000adc6  push    r15
0x14000adc8  sub     rsp, 20h
0x14000adcc  mov     r15, rdx
0x14000adcf  mov     rsi, rcx
0x14000add2  xor     edi, edi
0x14000add4  mov     r14d, r8d
0x14000add7  mov     r8d, 574D6365h; Tag
0x14000addd  mov     edx, r14d; NumberOfBytes
0x14000ade0  lea     ecx, [rdi+1]; PoolType
0x14000ade3  call    cs:__imp_ExAllocatePoolWithTag
0x14000adea  nop     dword ptr [rax+rax+00h]
0x14000adef  mov     rbx, rax
0x14000adf2  mov     [rsp+38h+arg_18], rax
0x14000adf7  test    rax, rax
0x14000adfa  jnz     short loc_14000AE03
0x14000adfc  mov     edi, 0C000009Ah
0x14000ae01  jmp     short loc_14000AE22
0x14000ae03  mov     r8, r14; Size
0x14000ae06  mov     rdx, r15; Src
0x14000ae09  mov     rcx, rax; void *
0x14000ae0c  call    RtlCopyFromUser
0x14000ae11  jmp     short loc_14000AE1F
0x14000ae13  mov     edi, eax
0x14000ae15  mov     rsi, [rsp+38h+arg_0]
0x14000ae1a  mov     rbx, [rsp+38h+arg_18]
0x14000ae1f  mov     [rsi], rbx
0x14000ae22  mov     eax, edi
0x14000ae24  mov     rbx, [rsp+38h+arg_8]
0x14000ae29  mov     rsi, [rsp+38h+arg_10]
0x14000ae2e  add     rsp, 20h
0x14000ae32  pop     r15
0x14000ae34  pop     r14
0x14000ae36  pop     rdi
0x14000ae37  retn
```
