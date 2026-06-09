# utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)

- ea: `0x14000d0a8`
- end: `0x14000d16b`
- name: `?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z`
- size: `195`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14000960c`
- `0x140009b70`
- `0x14000a0fc`
- `0x14000ab4c`
- `0x14000adb8`
- `0x14000b77c`
- `0x14000c6f0`
- `0x14000cad0`

## callees

- `0x14000bfb8`
- `0x14000d0a8`

## pseudocode

```c
char __fastcall utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rsi
  char v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // rax

  v4 = *a1;
  v5 = 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - v4) >> 3);
  if ( a2 > v5 )
  {
    if ( a2 <= 0xAAAAAAAAAAAAAAABuLL * ((a1[2] - v4) >> 3)
      || (unsigned __int8)utl::vector<_WSM_TRACKING_OVERRIDE_INFO,utl::allocator<_WSM_TRACKING_OVERRIDE_INFO>>::_GrowMinimum(
                            a1,
                            a2) )
    {
      v7 = a1[1];
      v8 = 0;
      v6 = 1;
      if ( a2 != v5 )
      {
        do
        {
          v9 = 3 * v8++;
          *(_OWORD *)(v7 + 8 * v9) = 0;
          *(_QWORD *)(v7 + 8 * v9 + 16) = 0;
        }
        while ( v8 != a2 - v5 );
      }
      a1[1] = *a1 + 24 * a2;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v6 = 1;
    a1[1] = v4 + 24 * a2;
  }
  return v6;
}

```

## disassembly

```asm
0x14000d0a8  mov     [rsp+arg_0], rbx
0x14000d0ad  mov     [rsp+arg_8], rsi
0x14000d0b2  push    rdi
0x14000d0b3  sub     rsp, 20h
0x14000d0b7  mov     rdi, rcx
0x14000d0ba  mov     rbx, rdx
0x14000d0bd  mov     rcx, [rcx]
0x14000d0c0  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14000d0ca  mov     rsi, [rdi+8]
0x14000d0ce  sub     rsi, rcx
0x14000d0d1  sar     rsi, 3
0x14000d0d5  imul    rsi, rdx
0x14000d0d9  cmp     rbx, rsi
0x14000d0dc  ja      short loc_14000D0F2
0x14000d0de  lea     rax, [rbx+rbx*2]
0x14000d0e2  mov     r8d, 1
0x14000d0e8  lea     rcx, [rcx+rax*8]
0x14000d0ec  mov     [rdi+8], rcx
0x14000d0f0  jmp     short loc_14000D157
0x14000d0f2  mov     rax, [rdi+10h]
0x14000d0f6  sub     rax, rcx
0x14000d0f9  sar     rax, 3
0x14000d0fd  imul    rax, rdx
0x14000d101  cmp     rbx, rax
0x14000d104  jbe     short loc_14000D11A
0x14000d106  mov     rdx, rbx
0x14000d109  mov     rcx, rdi
0x14000d10c  call    ?_GrowMinimum@?$vector@U_WSM_TRACKING_OVERRIDE_INFO@@V?$allocator@U_WSM_TRACKING_OVERRIDE_INFO@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<_WSM_TRACKING_OVERRIDE_INFO,utl::allocator<_WSM_TRACKING_OVERRIDE_INFO>>::_GrowMinimum(unsigned __int64)
0x14000d111  test    al, al
0x14000d113  jnz     short loc_14000D11A
0x14000d115  xor     r8b, r8b
0x14000d118  jmp     short loc_14000D157
0x14000d11a  mov     r9, [rdi+8]
0x14000d11e  xor     ecx, ecx
0x14000d120  mov     rdx, rbx
0x14000d123  lea     r8d, [rcx+1]
0x14000d127  sub     rdx, rsi
0x14000d12a  jz      short loc_14000D148
0x14000d12c  lea     rax, [rcx+rcx*2]
0x14000d130  xor     r10d, r10d
0x14000d133  add     rcx, r8
0x14000d136  xorps   xmm0, xmm0
0x14000d139  movups  xmmword ptr [r9+rax*8], xmm0
0x14000d13e  mov     [r9+rax*8+10h], r10
0x14000d143  cmp     rcx, rdx
0x14000d146  jnz     short loc_14000D12C
0x14000d148  mov     rcx, [rdi]
0x14000d14b  lea     rdx, [rbx+rbx*2]
0x14000d14f  lea     rdx, [rcx+rdx*8]
0x14000d153  mov     [rdi+8], rdx
0x14000d157  mov     rbx, [rsp+28h+arg_0]
0x14000d15c  mov     al, r8b
0x14000d15f  mov     rsi, [rsp+28h+arg_8]
0x14000d164  add     rsp, 20h
0x14000d168  pop     rdi
0x14000d169  retn
```
