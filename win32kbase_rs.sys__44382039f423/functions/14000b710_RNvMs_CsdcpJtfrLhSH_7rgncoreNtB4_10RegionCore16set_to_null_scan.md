# _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan

- ea: `0x14000b710`
- end: `0x14000b853`
- name: `_RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004e40`
- `0x1400050b0`
- `0x14000acb0`
- `0x14000b240`
- `0x14000b860`
- `0x14000c640`
- `0x14000ca10`
- `0x14000cc10`
- `0x14000e9d0`
- `0x14000f3a0`
- `0x1400101f0`

## callees

- `0x14000b710`
- `0x140017a10`
- `0x140017f00`
- `0x140018470`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan(unsigned __int64 *a1)
{
  unsigned __int64 v1; // rdi
  _OWORD *v2; // r14
  unsigned __int64 v3; // rsi
  __int64 v4; // rdx
  unsigned __int64 *v5; // rbx
  unsigned __int64 result; // rax
  _BYTE v7[32]; // [rsp+0h] [rbp-78h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v9; // [rsp+50h] [rbp-28h]

  *(_OWORD *)((char *)a1 + 28) = 0;
  v1 = a1[2];
  if ( v1 < 5 )
  {
    if ( v1 == 4 )
    {
      v2 = (_OWORD *)a1[1];
    }
    else
    {
      v3 = 4;
      v4 = *a1;
      if ( 4 - v1 > *a1 - v1 )
      {
        if ( (unsigned __int64)(2 * v4) >= 5 )
          v3 = 2 * v4;
        v5 = a1;
        RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
          (__int64 *)v8,
          v4,
          (const void *)a1[1],
          v3,
          4u,
          4u);
        if ( v8[0] )
        {
LABEL_14:
          *(_OWORD *)v8 = *(_OWORD *)&v8[8];
          RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
            (__int64)"called `Result::unwrap()` on an `Err` valuergncore\\src\\scan.rs",
            43,
            (__int64)v8,
            (__int64)&qword_14001B430,
            (__int64)&off_14001B450);
        }
        v2 = *(_OWORD **)&v8[8];
        v5[1] = *(_QWORD *)&v8[8];
        *v5 = v3;
      }
      else
      {
        v5 = a1;
        v2 = (_OWORD *)a1[1];
      }
      memset((char *)v2 + 4 * v1, 0, 16 - 4 * v1);
      a1 = v5;
      v5[2] = 4;
    }
  }
  else
  {
    v2 = (_OWORD *)a1[1];
    a1[2] = 4;
  }
  *v2 = _xmm;
  *((_DWORD *)a1 + 6) = 1;
  result = (unsigned __int64)v7 ^ v9;
  if ( _security_cookie != ((unsigned __int64)v7 ^ v9) )
    goto LABEL_14;
  return result;
}

```

## disassembly

```asm
0x14000b710  push    r14
0x14000b712  push    rsi
0x14000b713  push    rdi
0x14000b714  push    rbx
0x14000b715  sub     rsp, 58h
0x14000b719  mov     rax, cs:__security_cookie
0x14000b720  xor     rax, rsp
0x14000b723  mov     [rsp+78h+var_28], rax
0x14000b728  xorps   xmm0, xmm0
0x14000b72b  movups  xmmword ptr [rcx+1Ch], xmm0
0x14000b72f  mov     rdi, [rcx+10h]
0x14000b733  cmp     rdi, 5
0x14000b737  jb      short loc_14000B747
0x14000b739  mov     r14, [rcx+8]
0x14000b73d  mov     qword ptr [rcx+10h], 4
0x14000b745  jmp     short loc_14000B798
0x14000b747  cmp     rdi, 4
0x14000b74b  jnz     short loc_14000B753
0x14000b74d  mov     r14, [rcx+8]
0x14000b751  jmp     short loc_14000B798
0x14000b753  mov     esi, 4
0x14000b758  mov     eax, 4
0x14000b75d  sub     rax, rdi
0x14000b760  mov     rdx, [rcx]
0x14000b763  mov     r8, rdx
0x14000b766  sub     r8, rdi
0x14000b769  cmp     rax, r8
0x14000b76c  ja      short loc_14000B7C8
0x14000b76e  mov     rbx, rcx
0x14000b771  mov     r14, [rcx+8]
0x14000b775  lea     rcx, [r14+rdi*4]; void *
0x14000b779  shl     rdi, 2
0x14000b77d  mov     r8d, 10h
0x14000b783  sub     r8, rdi; Size
0x14000b786  xor     edx, edx; Val
0x14000b788  call    memset
0x14000b78d  mov     rcx, rbx
0x14000b790  mov     qword ptr [rbx+10h], 4
0x14000b798  movaps  xmm0, cs:__xmm@000000007fffffff8000000000000000
0x14000b79f  movups  xmmword ptr [r14], xmm0
0x14000b7a3  mov     dword ptr [rcx+18h], 1
0x14000b7aa  mov     rax, [rsp+78h+var_28]
0x14000b7af  xor     rax, rsp
0x14000b7b2  mov     rcx, cs:__security_cookie
0x14000b7b9  cmp     rcx, rax
0x14000b7bc  jnz     short loc_14000B812
0x14000b7be  add     rsp, 58h
0x14000b7c2  pop     rbx
0x14000b7c3  pop     rdi
0x14000b7c4  pop     rsi
0x14000b7c5  pop     r14
0x14000b7c7  retn
0x14000b7c8  lea     rax, [rdx+rdx]
0x14000b7cc  cmp     rax, 5
0x14000b7d0  cmovnb  rsi, rax
0x14000b7d4  mov     rbx, rcx
0x14000b7d7  mov     r8, [rcx+8]
0x14000b7db  mov     [rsp+78h+var_50], 4
0x14000b7e4  mov     [rsp+78h+var_58], 4
0x14000b7ed  lea     rcx, [rsp+78h+var_40]
0x14000b7f2  mov     r9, rsi
0x14000b7f5  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x14000b7fa  cmp     [rsp+78h+var_40], 0
0x14000b7ff  jnz     short loc_14000B81F
0x14000b801  mov     r14, qword ptr [rsp+78h+var_40+8]
0x14000b806  mov     [rbx+8], r14
0x14000b80a  mov     [rbx], rsi
0x14000b80d  jmp     loc_14000B775
0x14000b812  mov     rcx, [rsp+78h+var_28]
0x14000b817  xor     rcx, rsp; StackCookie
0x14000b81a  call    __security_check_cookie
0x14000b81f  movups  xmm0, xmmword ptr [rsp+78h+var_40+8]
0x14000b824  movups  xmmword ptr [rsp+78h+var_40], xmm0
0x14000b829  lea     rax, off_14001B450; "rgncore\\src\\lib.rs"
0x14000b830  mov     [rsp+78h+var_58], rax
0x14000b835  lea     rcx, aCalledResultUn; "called `Result::unwrap()` on an `Err` v"...
0x14000b83c  lea     r9, qword_14001B430
0x14000b843  lea     r8, [rsp+78h+var_40]
0x14000b848  mov     edx, 2Bh ; '+'
0x14000b84d  call    _RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed
```
