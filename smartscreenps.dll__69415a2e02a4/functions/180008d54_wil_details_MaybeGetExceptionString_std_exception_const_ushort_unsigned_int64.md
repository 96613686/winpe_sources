# wil::details::MaybeGetExceptionString(std::exception const &,ushort *,unsigned __int64)

- ea: `0x180008d54`
- end: `0x180008d96`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@std@@PEAG_K@Z`
- size: `66`
- prototype: `void(wil::details *__hidden this, const struct std::exception *, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ced6`
- `0x18000cfa8`
- `0x18000d0b6`
- `0x18000d101`

## callees

- `0x180008d54`
- `0x180009780`
- `0x18000e010`

## pseudocode

```c
void __fastcall wil::details::MaybeGetExceptionString(
        wil::details *this,
        const struct std::exception *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // rax

  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(wil::details *))(*(_QWORD *)this + 8LL))(this);
    StringCchPrintfW((unsigned __int16 *)a2, (unsigned __int64)a3, L"std::exception: %hs", v5);
  }
}

```

## disassembly

```asm
0x180008d54  test    rdx, rdx
0x180008d57  jz      short locret_180008D94
0x180008d59  mov     [rsp+arg_0], rbx
0x180008d5e  push    rdi
0x180008d5f  sub     rsp, 20h
0x180008d63  mov     rax, [rcx]
0x180008d66  mov     rdi, r8
0x180008d69  mov     rbx, rdx
0x180008d6c  mov     rax, [rax+8]
0x180008d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d75  mov     r9, rax
0x180008d78  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x180008d7f  mov     rdx, rdi; unsigned __int64
0x180008d82  mov     rcx, rbx; unsigned __int16 *
0x180008d85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008d8a  mov     rbx, [rsp+28h+arg_0]
0x180008d8f  add     rsp, 20h
0x180008d93  pop     rdi
0x180008d94  retn
```
