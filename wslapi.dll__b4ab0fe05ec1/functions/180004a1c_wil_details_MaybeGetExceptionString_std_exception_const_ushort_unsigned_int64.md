# wil::details::MaybeGetExceptionString(std::exception const &,ushort *,unsigned __int64)

- ea: `0x180004a1c`
- end: `0x180004a5d`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@std@@PEAG_K@Z`
- size: `65`
- prototype: `void __fastcall(wil::details *this, const struct std::exception *, unsigned __int16 *)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bc57`
- `0x18000bd29`
- `0x18000be37`
- `0x18000be82`
- `0x18000c3ea`
- `0x18000c426`
- `0x18000c462`
- `0x18000c591`
- `0x18000c5cd`
- `0x18000c609`
- `0x18000c645`

## callees

- `0x180004a1c`
- `0x18000552c`
- `0x18000d010`

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
0x180004a1c  test    rdx, rdx
0x180004a1f  jz      short locret_180004A5C
0x180004a21  mov     [rsp+arg_0], rbx
0x180004a26  push    rdi
0x180004a27  sub     rsp, 20h
0x180004a2b  mov     rax, [rcx]
0x180004a2e  mov     rdi, r8
0x180004a31  mov     rbx, rdx
0x180004a34  mov     rax, [rax+8]
0x180004a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a3d  mov     r9, rax
0x180004a40  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x180004a47  mov     rdx, rdi; unsigned __int64
0x180004a4a  mov     rcx, rbx; unsigned __int16 *
0x180004a4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004a52  mov     rbx, [rsp+28h+arg_0]
0x180004a57  add     rsp, 20h
0x180004a5b  pop     rdi
0x180004a5c  retn
```
