# CWsmTrackingConfig::CTrackingOverrideInfo::serialize(write_buffer_aligned &)

- ea: `0x14000d440`
- end: `0x14000d4a7`
- name: `?serialize@CTrackingOverrideInfo@CWsmTrackingConfig@@UEBAJAEAVwrite_buffer_aligned@@@Z`
- size: `103`
- prototype: `int(CWsmTrackingConfig::CTrackingOverrideInfo *__hidden this, struct write_buffer_aligned *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140008d80`
- `0x14000d440`
- `0x14000d5e0`
- `0x14000f9e0`

## pseudocode

```c
write *__fastcall CWsmTrackingConfig::CTrackingOverrideInfo::serialize(
        CWsmTrackingConfig::CTrackingOverrideInfo *this,
        struct write_buffer_aligned *a2)
{
  write *result; // rax

  result = (write *)(**((__int64 (__fastcall ***)(char *))this + 1))((char *)this + 8);
  if ( (int)result >= 0 )
  {
    result = (write *)(**((__int64 (__fastcall ***)(char *, struct write_buffer_aligned *))this + 3))(
                        (char *)this + 24,
                        a2);
    if ( (int)result >= 0 )
    {
      result = write_buffer_uchar::write(a2, (const unsigned __int8 *const)this + 56, 1u);
      if ( (int)result >= 0 )
        return (write *)write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)this + 60);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d440  mov     [rsp+arg_0], rbx
0x14000d445  push    rdi
0x14000d446  sub     rsp, 20h
0x14000d44a  mov     rdi, rcx
0x14000d44d  mov     rbx, rdx
0x14000d450  add     rcx, 8
0x14000d454  mov     rax, [rcx]
0x14000d457  mov     rax, [rax]
0x14000d45a  call    _guard_dispatch_icall
0x14000d45f  test    eax, eax
0x14000d461  js      short loc_14000D49B
0x14000d463  lea     rcx, [rdi+18h]
0x14000d467  mov     rdx, rbx
0x14000d46a  mov     rax, [rcx]
0x14000d46d  mov     rax, [rax]
0x14000d470  call    _guard_dispatch_icall
0x14000d475  test    eax, eax
0x14000d477  js      short loc_14000D49B
0x14000d479  lea     rdx, [rdi+38h]; unsigned __int8 *
0x14000d47d  mov     r8d, 1; unsigned int
0x14000d483  mov     rcx, rbx; this
0x14000d486  call    ?write@write_buffer_uchar@@IEAAJQEBEK@Z; write_buffer_uchar::write(uchar const * const,ulong)
0x14000d48b  test    eax, eax
0x14000d48d  js      short loc_14000D49B
0x14000d48f  lea     rdx, [rdi+3Ch]; unsigned __int8 *
0x14000d493  mov     rcx, rbx; this
0x14000d496  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d49b  mov     rbx, [rsp+28h+arg_0]
0x14000d4a0  add     rsp, 20h
0x14000d4a4  pop     rdi
0x14000d4a5  retn
```
