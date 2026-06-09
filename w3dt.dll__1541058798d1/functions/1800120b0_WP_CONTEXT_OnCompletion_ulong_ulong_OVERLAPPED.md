# WP_CONTEXT::OnCompletion(ulong,ulong,_OVERLAPPED *)

- ea: `0x1800120b0`
- end: `0x1800120ef`
- name: `?OnCompletion@WP_CONTEXT@@SAXKKPEAU_OVERLAPPED@@@Z`
- size: `63`
- prototype: `void __fastcall(unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800120b0`
- `0x180017010`

## import_xrefs

- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x1800120bf`
- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x1800120bf`

## pseudocode

```c
void __fastcall WP_CONTEXT::OnCompletion(unsigned int a1, unsigned int a2, struct _OVERLAPPED *a3)
{
  unsigned int v5; // edx

  v5 = ThreadPoolMapErrorCodeIfNecessary(a1);
  if ( a3 )
    (*(void (__fastcall **)(HANDLE *, _QWORD, _QWORD, struct _OVERLAPPED *))a3[-1].hEvent)(&a3[-1].hEvent, a2, v5, a3);
}

```

## disassembly

```asm
0x1800120b0  mov     [rsp+arg_0], rbx
0x1800120b5  push    rdi
0x1800120b6  sub     rsp, 30h
0x1800120ba  mov     rbx, r8
0x1800120bd  mov     edi, edx
0x1800120bf  call    cs:__imp_?ThreadPoolMapErrorCodeIfNecessary@@YAKK@Z; ThreadPoolMapErrorCodeIfNecessary(ulong)
0x1800120c5  mov     edx, eax
0x1800120c7  test    rbx, rbx
0x1800120ca  jz      short loc_1800120E4
0x1800120cc  mov     r8, [rbx-8]
0x1800120d0  lea     rcx, [rbx-8]
0x1800120d4  mov     r9, rbx
0x1800120d7  mov     rax, [r8]
0x1800120da  mov     r8d, edx
0x1800120dd  mov     edx, edi
0x1800120df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e4  mov     rbx, [rsp+38h+arg_0]
0x1800120e9  add     rsp, 30h
0x1800120ed  pop     rdi
0x1800120ee  retn
```
