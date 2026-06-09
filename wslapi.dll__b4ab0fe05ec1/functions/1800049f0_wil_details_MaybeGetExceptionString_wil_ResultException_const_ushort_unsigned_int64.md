# wil::details::MaybeGetExceptionString(wil::ResultException const &,ushort *,unsigned __int64)

- ea: `0x1800049f0`
- end: `0x180004a13`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVResultException@2@PEAG_K@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *this, const struct wil::ResultException *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bcc0`
- `0x18000bdce`
- `0x18000c344`
- `0x18000c4eb`

## callees

- `0x180003bd4`
- `0x1800049f0`

## pseudocode

```c
void __fastcall wil::details::MaybeGetExceptionString(
        wil::details *this,
        const struct wil::ResultException *a2,
        unsigned __int16 *a3)
{
  if ( a2 )
    wil::GetFailureLogString(a2, a3, (__int64)this + 24, (const struct wil::FailureInfo *)a3);
}

```

## disassembly

```asm
0x1800049f0  sub     rsp, 28h
0x1800049f4  mov     r9, r8; struct wil::FailureInfo *
0x1800049f7  mov     rax, rdx
0x1800049fa  test    rdx, rdx
0x1800049fd  jz      short loc_180004A0E
0x1800049ff  lea     r8, [rcx+18h]; unsigned __int64
0x180004a03  mov     rdx, r9; unsigned __int16 *
0x180004a06  mov     rcx, rax; this
0x180004a09  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004a0e  add     rsp, 28h
0x180004a12  retn
```
