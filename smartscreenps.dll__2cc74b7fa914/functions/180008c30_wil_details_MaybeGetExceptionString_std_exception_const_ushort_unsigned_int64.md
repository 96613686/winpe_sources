# wil::details::MaybeGetExceptionString(std::exception const &,ushort *,unsigned __int64)

- ea: `0x180008c30`
- end: `0x180008c71`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@std@@PEAG_K@Z`
- size: `65`
- prototype: `void(wil::details *__hidden this, const struct std::exception *, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cbf6`
- `0x18000ccc8`
- `0x18000cdd6`
- `0x18000ce21`

## callees

- `0x180008c30`
- `0x1800095ec`
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
0x180008c30  test    rdx, rdx
0x180008c33  jz      short locret_180008C70
0x180008c35  mov     [rsp+arg_0], rbx
0x180008c3a  push    rdi
0x180008c3b  sub     rsp, 20h
0x180008c3f  mov     rax, [rcx]
0x180008c42  mov     rdi, r8
0x180008c45  mov     rbx, rdx
0x180008c48  mov     rax, [rax+8]
0x180008c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c51  mov     r9, rax
0x180008c54  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x180008c5b  mov     rdx, rdi; unsigned __int64
0x180008c5e  mov     rcx, rbx; unsigned __int16 *
0x180008c61  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008c66  mov     rbx, [rsp+28h+arg_0]
0x180008c6b  add     rsp, 20h
0x180008c6f  pop     rdi
0x180008c70  retn
```
