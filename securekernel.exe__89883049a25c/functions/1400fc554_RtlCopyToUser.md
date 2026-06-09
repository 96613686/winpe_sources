# RtlCopyToUser

- ea: `0x1400fc554`
- end: `0x1400fc5b1`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `31`
- callee_count: `3`
- tags: ``

## callers

- `0x140021428`
- `0x140040250`
- `0x140041234`
- `0x14004244c`
- `0x1400425ac`
- `0x140042760`
- `0x1400427c4`
- `0x140042824`
- `0x140042afc`
- `0x140042c40`
- `0x140043038`
- `0x1400440b4`
- `0x14004439c`
- `0x140066b20`
- `0x1400671bc`
- `0x140067ecc`
- `0x1400883a4`
- `0x1400961bc`
- `0x1400adaf8`
- `0x1400addd0`
- `0x1400aeeec`
- `0x1400af528`
- `0x1400af910`
- `0x1400b0bc0`
- `0x1400b17a4`
- `0x1400b4c40`
- `0x1400bc3a0`
- `0x1400c2b18`
- `0x1400c3614`
- `0x1400fc1a8`
- `0x140107020`

## callees

- `0x1400442ac`
- `0x1400f38f0`
- `0x1400fc554`

## pseudocode

```c
void *__fastcall RtlCopyToUser(void *a1, void *Src, size_t Size)
{
  void *result; // rax

  result = 0;
  if ( Size )
  {
    ProbeForRead(a1, Size, 1u);
    return RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x1400fc554  mov     [rsp+arg_0], rbx
0x1400fc559  mov     [rsp+arg_8], rsi
0x1400fc55e  push    rdi
0x1400fc55f  sub     rsp, 20h
0x1400fc563  mov     rax, cs:qword_14010C3E0
0x1400fc56a  mov     rbx, r8
0x1400fc56d  mov     rsi, rdx
0x1400fc570  mov     rdi, rcx
0x1400fc573  test    rax, rax
0x1400fc576  jz      short loc_1400FC57F
0x1400fc578  call    rax ; qword_14010C3E0
0x1400fc57a  nop     dword ptr [rax]
0x1400fc57d  jmp     short loc_1400FC5A0
0x1400fc57f  test    rbx, rbx
0x1400fc582  jz      short loc_1400FC5A0
0x1400fc584  mov     r8d, 1; Alignment
0x1400fc58a  mov     rdx, rbx; Length
0x1400fc58d  call    ProbeForRead
0x1400fc592  mov     r8, rbx; Size
0x1400fc595  mov     rdx, rsi; Src
0x1400fc598  mov     rcx, rdi; void *
0x1400fc59b  call    RtlCopyVolatileMemory
0x1400fc5a0  mov     rbx, [rsp+28h+arg_0]
0x1400fc5a5  mov     rsi, [rsp+28h+arg_8]
0x1400fc5aa  add     rsp, 20h
0x1400fc5ae  pop     rdi
0x1400fc5af  retn
```
