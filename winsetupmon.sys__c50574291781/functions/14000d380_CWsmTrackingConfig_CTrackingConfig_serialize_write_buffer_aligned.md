# CWsmTrackingConfig::CTrackingConfig::serialize(write_buffer_aligned &)

- ea: `0x14000d380`
- end: `0x14000d438`
- name: `?serialize@CTrackingConfig@CWsmTrackingConfig@@UEBAJAEAVwrite_buffer_aligned@@@Z`
- size: `184`
- prototype: `int(CWsmTrackingConfig::CTrackingConfig *__hidden this, struct write_buffer_aligned *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140008d80`
- `0x14000d380`
- `0x14000f9e0`

## pseudocode

```c
unsigned __int64 __fastcall CWsmTrackingConfig::CTrackingConfig::serialize(
        CWsmTrackingConfig::CTrackingConfig *this,
        struct write_buffer_aligned *a2)
{
  unsigned __int64 result; // rax
  _DWORD *v5; // rsi
  __int64 v6; // rdi
  __int64 (__fastcall ***v7)(_QWORD, struct write_buffer_aligned *); // rcx
  int v8; // [rsp+50h] [rbp+18h] BYREF
  int v9; // [rsp+58h] [rbp+20h] BYREF

  v8 = 1852666743;
  result = write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)&v8);
  if ( (result & 0x80000000) == 0LL )
  {
    v9 = 6;
    result = write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)&v9);
    if ( (result & 0x80000000) == 0LL )
    {
      result = (**((__int64 (__fastcall ***)(char *, struct write_buffer_aligned *))this + 7))((char *)this + 56, a2);
      if ( (result & 0x80000000) == 0LL )
      {
        result = (**((__int64 (__fastcall ***)(char *, struct write_buffer_aligned *))this + 9))((char *)this + 72, a2);
        if ( (result & 0x80000000) == 0LL )
        {
          v5 = (_DWORD *)((char *)this + 104);
          result = write_buffer_aligned::write<unsigned long>(a2, (unsigned __int8 *)this + 104);
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
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d380  mov     [rsp+arg_0], rbx
0x14000d385  push    rbp
0x14000d386  push    rsi
0x14000d387  push    rdi
0x14000d388  sub     rsp, 20h
0x14000d38c  mov     rbx, rdx
0x14000d38f  mov     [rsp+38h+arg_10], 6E6D7377h
0x14000d397  mov     rbp, rcx
0x14000d39a  lea     rdx, [rsp+38h+arg_10]; unsigned __int8 *
0x14000d39f  mov     rcx, rbx; this
0x14000d3a2  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d3a7  test    eax, eax
0x14000d3a9  js      short loc_14000D42A
0x14000d3ab  lea     rdx, [rsp+38h+arg_18]; unsigned __int8 *
0x14000d3b0  mov     [rsp+38h+arg_18], 6
0x14000d3b8  mov     rcx, rbx; this
0x14000d3bb  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d3c0  test    eax, eax
0x14000d3c2  js      short loc_14000D42A
0x14000d3c4  lea     rcx, [rbp+38h]
0x14000d3c8  mov     rdx, rbx
0x14000d3cb  mov     rax, [rcx]
0x14000d3ce  mov     rax, [rax]
0x14000d3d1  call    _guard_dispatch_icall
0x14000d3d6  test    eax, eax
0x14000d3d8  js      short loc_14000D42A
0x14000d3da  lea     rcx, [rbp+48h]
0x14000d3de  mov     rdx, rbx
0x14000d3e1  mov     rax, [rcx]
0x14000d3e4  mov     rax, [rax]
0x14000d3e7  call    _guard_dispatch_icall
0x14000d3ec  test    eax, eax
0x14000d3ee  js      short loc_14000D42A
0x14000d3f0  lea     rsi, [rbp+68h]
0x14000d3f4  mov     rcx, rbx; this
0x14000d3f7  mov     rdx, rsi; unsigned __int8 *
0x14000d3fa  call    ??$write@K@write_buffer_aligned@@QEAAJAEBK@Z; write_buffer_aligned::write<ulong>(ulong const &)
0x14000d3ff  test    eax, eax
0x14000d401  js      short loc_14000D42A
0x14000d403  cmp     dword ptr [rsi], 0
0x14000d406  jbe     short loc_14000D42A
0x14000d408  xor     edi, edi
0x14000d40a  mov     rax, [rbp+8]
0x14000d40e  mov     rdx, rbx
0x14000d411  mov     rcx, [rax+rdi*8]
0x14000d415  mov     rax, [rcx]
0x14000d418  mov     rax, [rax]
0x14000d41b  call    _guard_dispatch_icall
0x14000d420  test    eax, eax
0x14000d422  js      short loc_14000D42A
0x14000d424  inc     edi
0x14000d426  cmp     edi, [rsi]
0x14000d428  jb      short loc_14000D40A
0x14000d42a  mov     rbx, [rsp+38h+arg_0]
0x14000d42f  add     rsp, 20h
0x14000d433  pop     rdi
0x14000d434  pop     rsi
0x14000d435  pop     rbp
0x14000d436  retn
```
