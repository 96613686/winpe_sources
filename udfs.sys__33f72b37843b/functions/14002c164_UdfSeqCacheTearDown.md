# UdfSeqCacheTearDown

- ea: `0x14002c164`
- end: `0x14002c247`
- name: `UdfSeqCacheTearDown`
- size: `227`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003148`
- `0x14002c008`
- `0x140049f80`

## callees

- `0x140004340`
- `0x140019f5c`
- `0x14002c164`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002c1e6`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c1e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c1d3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c1d3`
- `ntoskrnl!KeSetEvent` at `0x14002c1a7`
- `ntoskrnl!KeSetEvent` at `0x14002c1a7`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheTearDown(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  char v5; // si
  int v6; // edx
  void *v7; // rcx
  __int64 result; // rax
  __int64 i; // rdi

  if ( (*(_DWORD *)(a2 + 48) & 0x200000) != 0 )
  {
    v4 = *(_QWORD *)(a2 + 104);
    v5 = 0;
    v6 = *(_DWORD *)(v4 + 4);
    if ( (v6 & 8) != 0 )
    {
      *(_DWORD *)(v4 + 4) = v6 | 4;
      KeSetEvent((PRKEVENT)(v4 + 592), 1, 0);
      v7 = *(void **)(v4 + 616);
      if ( v7 )
      {
        v5 = 1;
        KeWaitForSingleObject(v7, Executive, 0, 0, 0);
        ObfDereferenceObject(*(PVOID *)(v4 + 616));
        *(_DWORD *)(v4 + 4) &= ~8u;
      }
    }
    result = UdfSeqCacheDeallocate(a1, a2, v4, v5);
    if ( (*(_DWORD *)(a2 + 48) & 0x20000000) != 0 )
    {
      for ( i = 1; i != 3; ++i )
        UdfSeqCacheDeallocate(a1, a2, *(_QWORD *)(a2 + 8 * i + 104), v5);
      return UdfFreePool(a2 + 128);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002c164  mov     [rsp+arg_10], r8b
0x14002c169  push    rbx
0x14002c16a  push    rbp
0x14002c16b  push    rsi
0x14002c16c  push    rdi
0x14002c16d  sub     rsp, 38h
0x14002c171  test    dword ptr [rdx+30h], 200000h
0x14002c178  mov     rbx, rdx
0x14002c17b  mov     rbp, rcx
0x14002c17e  jz      loc_14002C23D
0x14002c184  mov     rdi, [rdx+68h]
0x14002c188  xor     sil, sil
0x14002c18b  mov     edx, [rdi+4]
0x14002c18e  test    dl, 8
0x14002c191  jz      short loc_14002C1F6
0x14002c193  or      edx, 4
0x14002c196  lea     rcx, [rdi+250h]; Event
0x14002c19d  xor     r8d, r8d; Wait
0x14002c1a0  mov     [rdi+4], edx
0x14002c1a3  lea     edx, [r8+1]; Increment
0x14002c1a7  call    cs:__imp_KeSetEvent
0x14002c1ae  nop     dword ptr [rax+rax+00h]
0x14002c1b3  mov     rcx, [rdi+268h]; Object
0x14002c1ba  test    rcx, rcx
0x14002c1bd  jz      short loc_14002C1F6
0x14002c1bf  xor     r9d, r9d; Alertable
0x14002c1c2  mov     [rsp+58h+Timeout], 0; Timeout
0x14002c1cb  xor     r8d, r8d; WaitMode
0x14002c1ce  xor     edx, edx; WaitReason
0x14002c1d0  mov     sil, 1
0x14002c1d3  call    cs:__imp_KeWaitForSingleObject
0x14002c1da  nop     dword ptr [rax+rax+00h]
0x14002c1df  mov     rcx, [rdi+268h]; Object
0x14002c1e6  call    cs:__imp_ObfDereferenceObject
0x14002c1ed  nop     dword ptr [rax+rax+00h]
0x14002c1f2  and     dword ptr [rdi+4], 0FFFFFFF7h
0x14002c1f6  mov     r9b, sil
0x14002c1f9  mov     r8, rdi
0x14002c1fc  mov     rdx, rbx
0x14002c1ff  mov     rcx, rbp
0x14002c202  call    UdfSeqCacheDeallocate
0x14002c207  test    dword ptr [rbx+30h], 20000000h
0x14002c20e  jz      short loc_14002C23D
0x14002c210  mov     edi, 1
0x14002c215  mov     r8, [rbx+rdi*8+68h]
0x14002c21a  mov     r9b, sil
0x14002c21d  mov     rdx, rbx
0x14002c220  mov     rcx, rbp
0x14002c223  call    UdfSeqCacheDeallocate
0x14002c228  inc     rdi
0x14002c22b  cmp     rdi, 3
0x14002c22f  jnz     short loc_14002C215
0x14002c231  lea     rcx, [rbx+80h]
0x14002c238  call    UdfFreePool
0x14002c23d  add     rsp, 38h
0x14002c241  pop     rdi
0x14002c242  pop     rsi
0x14002c243  pop     rbp
0x14002c244  pop     rbx
0x14002c245  retn
```
