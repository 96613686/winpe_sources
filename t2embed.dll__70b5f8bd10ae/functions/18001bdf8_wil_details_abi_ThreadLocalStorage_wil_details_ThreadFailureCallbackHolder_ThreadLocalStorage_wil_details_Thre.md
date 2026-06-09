# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18001bdf8`
- end: `0x18001be47`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a9a0`

## callees

- `0x18001bdf8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001be27`
- `KERNEL32!HeapFree` at `0x18001be27`
- `KERNEL32!GetProcessHeap` at `0x18001be19`
- `KERNEL32!GetProcessHeap` at `0x18001be19`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18001bdf8  push    rbx
0x18001bdfa  push    rbp
0x18001bdfb  push    rsi
0x18001bdfc  push    rdi
0x18001bdfd  sub     rsp, 28h
0x18001be01  lea     rbp, [rcx+50h]
0x18001be05  mov     rdi, rcx
0x18001be08  cmp     rcx, rbp
0x18001be0b  jz      short loc_18001BE3E
0x18001be0d  mov     rsi, [rdi]
0x18001be10  jmp     short loc_18001BE2D
0x18001be12  mov     rbx, rsi
0x18001be15  mov     rsi, [rsi+8]
0x18001be19  call    cs:__imp_GetProcessHeap
0x18001be1f  mov     r8, rbx; lpMem
0x18001be22  xor     edx, edx; dwFlags
0x18001be24  mov     rcx, rax; hHeap
0x18001be27  call    cs:__imp_HeapFree
0x18001be2d  test    rsi, rsi
0x18001be30  jnz     short loc_18001BE12
0x18001be32  mov     [rdi], rsi
0x18001be35  add     rdi, 8
0x18001be39  cmp     rdi, rbp
0x18001be3c  jnz     short loc_18001BE0D
0x18001be3e  add     rsp, 28h
0x18001be42  pop     rdi
0x18001be43  pop     rsi
0x18001be44  pop     rbp
0x18001be45  pop     rbx
0x18001be46  retn
```
