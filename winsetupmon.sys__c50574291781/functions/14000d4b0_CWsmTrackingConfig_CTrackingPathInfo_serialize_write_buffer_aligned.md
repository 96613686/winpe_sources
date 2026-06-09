# CWsmTrackingConfig::CTrackingPathInfo::serialize(write_buffer_aligned &)

- ea: `0x14000d4b0`
- end: `0x14000d526`
- name: `?serialize@CTrackingPathInfo@CWsmTrackingConfig@@UEBAJAEAVwrite_buffer_aligned@@@Z`
- size: `118`
- prototype: `int(CWsmTrackingConfig::CTrackingPathInfo *__hidden this, struct write_buffer_aligned *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140008d80`
- `0x14000d4b0`
- `0x14000f9e0`

## pseudocode

```c
unsigned __int64 __fastcall CWsmTrackingConfig::CTrackingPathInfo::serialize(
        CWsmTrackingConfig::CTrackingPathInfo *this,
        struct write_buffer_aligned *a2)
{
  unsigned __int64 result; // rax
  _DWORD *v5; // rdi
  __int64 v6; // rbx
  __int64 (__fastcall ***v7)(_QWORD, struct write_buffer_aligned *); // rcx

  result = (**((__int64 (__fastcall ***)(char *))this + 4))((char *)this + 32);
  if ( (result & 0x80000000) == 0LL )
  {
    result = write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)this + 80);
    if ( (result & 0x80000000) == 0LL )
    {
      v5 = (_DWORD *)((char *)this + 84);
      result = write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)this + 84);
      if ( (result & 0x80000000) == 0LL )
      {
        if ( *v5 )
        {
          v6 = 0;
          do
          {
            v7 = *(__int64 (__fastcall ****)(_QWORD, struct write_buffer_aligned *))(*((_QWORD *)this + 1) + 8 * v6);
            result = (**v7)(v7, a2);
            if ( (result & 0x80000000) != 0LL )
              break;
            v6 = (unsigned int)(v6 + 1);
          }
          while ( (unsigned int)v6 < *v5 );
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d4b0  push    rbx
0x14000d4b2  push    rbp
0x14000d4b3  push    rsi
0x14000d4b4  push    rdi
0x14000d4b5  sub     rsp, 28h
0x14000d4b9  mov     rbp, rcx
0x14000d4bc  mov     rsi, rdx
0x14000d4bf  add     rcx, 20h ; ' '
0x14000d4c3  mov     rax, [rcx]
0x14000d4c6  mov     rax, [rax]
0x14000d4c9  call    _guard_dispatch_icall
0x14000d4ce  test    eax, eax
0x14000d4d0  js      short loc_14000D51C
0x14000d4d2  lea     rdx, [rbp+50h]; unsigned __int8 *
0x14000d4d6  mov     rcx, rsi; this
0x14000d4d9  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d4de  test    eax, eax
0x14000d4e0  js      short loc_14000D51C
0x14000d4e2  lea     rdi, [rbp+54h]
0x14000d4e6  mov     rcx, rsi; this
0x14000d4e9  mov     rdx, rdi; unsigned __int8 *
0x14000d4ec  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d4f1  test    eax, eax
0x14000d4f3  js      short loc_14000D51C
0x14000d4f5  cmp     dword ptr [rdi], 0
0x14000d4f8  jbe     short loc_14000D51C
0x14000d4fa  xor     ebx, ebx
0x14000d4fc  mov     rax, [rbp+8]
0x14000d500  mov     rdx, rsi
0x14000d503  mov     rcx, [rax+rbx*8]
0x14000d507  mov     rax, [rcx]
0x14000d50a  mov     rax, [rax]
0x14000d50d  call    _guard_dispatch_icall
0x14000d512  test    eax, eax
0x14000d514  js      short loc_14000D51C
0x14000d516  inc     ebx
0x14000d518  cmp     ebx, [rdi]
0x14000d51a  jb      short loc_14000D4FC
0x14000d51c  add     rsp, 28h
0x14000d520  pop     rdi
0x14000d521  pop     rsi
0x14000d522  pop     rbp
0x14000d523  pop     rbx
0x14000d524  retn
```
