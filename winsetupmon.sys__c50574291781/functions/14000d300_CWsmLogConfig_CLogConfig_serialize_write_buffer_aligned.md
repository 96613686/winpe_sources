# CWsmLogConfig::CLogConfig::serialize(write_buffer_aligned &)

- ea: `0x14000d300`
- end: `0x14000d370`
- name: `?serialize@CLogConfig@CWsmLogConfig@@UEBAJAEAVwrite_buffer_aligned@@@Z`
- size: `112`
- prototype: `int(CWsmLogConfig::CLogConfig *__hidden this, struct write_buffer_aligned *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140008d80`
- `0x140008e70`
- `0x14000d300`
- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::CLogConfig::serialize(
        CWsmLogConfig::CLogConfig *this,
        struct write_buffer_aligned *a2)
{
  __int64 result; // rax
  int v5; // [rsp+40h] [rbp+18h] BYREF
  int v6; // [rsp+48h] [rbp+20h] BYREF

  v5 = 1852666743;
  result = write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)&v5);
  if ( (int)result >= 0 )
  {
    v6 = 2;
    result = write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)&v6);
    if ( (int)result >= 0 )
    {
      result = (**((__int64 (__fastcall ***)(char *, struct write_buffer_aligned *))this + 3))((char *)this + 24, a2);
      if ( (int)result >= 0 )
        return write_buffer_aligned::write<unsigned __int64>(a2, (unsigned __int8 *)this + 16);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d300  mov     [rsp+arg_0], rbx
0x14000d305  push    rdi
0x14000d306  sub     rsp, 20h
0x14000d30a  mov     rbx, rdx
0x14000d30d  mov     [rsp+28h+arg_10], 6E6D7377h
0x14000d315  mov     rdi, rcx
0x14000d318  lea     rdx, [rsp+28h+arg_10]; unsigned __int8 *
0x14000d31d  mov     rcx, rbx; this
0x14000d320  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d325  test    eax, eax
0x14000d327  js      short loc_14000D364
0x14000d329  lea     rdx, [rsp+28h+arg_18]; unsigned __int8 *
0x14000d32e  mov     [rsp+28h+arg_18], 2
0x14000d336  mov     rcx, rbx; this
0x14000d339  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d33e  test    eax, eax
0x14000d340  js      short loc_14000D364
0x14000d342  lea     rcx, [rdi+18h]
0x14000d346  mov     rdx, rbx
0x14000d349  mov     rax, [rcx]
0x14000d34c  mov     rax, [rax]
0x14000d34f  call    _guard_dispatch_icall
0x14000d354  test    eax, eax
0x14000d356  js      short loc_14000D364
0x14000d358  lea     rdx, [rdi+10h]; unsigned __int8 *
0x14000d35c  mov     rcx, rbx; this
0x14000d35f  call    ??$write@_K@write_buffer_aligned@@QEAAJAEB_K@Z; write_buffer_aligned::write<unsigned __int64>(unsigned __int64 const &)
0x14000d364  mov     rbx, [rsp+28h+arg_0]
0x14000d369  add     rsp, 20h
0x14000d36d  pop     rdi
0x14000d36e  retn
```
