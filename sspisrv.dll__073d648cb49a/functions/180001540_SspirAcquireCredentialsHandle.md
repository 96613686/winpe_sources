# SspirAcquireCredentialsHandle

- ea: `0x180001540`
- end: `0x1800016c8`
- name: `SspirAcquireCredentialsHandle`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002950`

## callees

- `0x180001540`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirAcquireCredentialsHandle(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        _OWORD *a11,
        __int64 a12)
{
  __int64 (__fastcall *v12)(__int64, _QWORD *); // r12
  __int64 result; // rax
  _QWORD v14[2]; // [rsp+80h] [rbp-68h] BYREF
  __int128 v15; // [rsp+90h] [rbp-58h]

  v15 = 0;
  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD *))(gLsapSspiExtension + 40);
  if ( !v12 )
    return 3221225659LL;
  if ( !a2 || !a7 || !a11 || !a12 )
    return 3221225485LL;
  v14[0] = *a2;
  v14[1] = a2[1];
  result = v12(a1, v14);
  if ( (int)result >= 0 )
  {
    *a11 = v15;
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x180001540  mov     r11, rsp
0x180001543  push    rbx
0x180001544  push    rbp
0x180001545  push    rsi
0x180001546  push    rdi
0x180001547  push    r12
0x180001549  push    r14
0x18000154b  push    r15
0x18000154d  sub     rsp, 0B0h
0x180001554  mov     rax, cs:__security_cookie
0x18000155b  xor     rax, rsp
0x18000155e  mov     [rsp+0E8h+var_48], rax
0x180001566  mov     rax, cs:gLsapSspiExtension
0x18000156d  xorps   xmm0, xmm0
0x180001570  mov     rbx, [rsp+0E8h+arg_50]
0x180001578  mov     rsi, rcx
0x18000157b  mov     rdi, [rsp+0E8h+arg_30]
0x180001583  mov     rbp, [rsp+0E8h+arg_28]
0x18000158b  mov     rcx, [rsp+0E8h+arg_58]
0x180001593  mov     r14, [rsp+0E8h+arg_60]
0x18000159b  mov     r15, [rsp+0E8h+arg_68]
0x1800015a3  movups  xmmword ptr [r11-58h], xmm0
0x1800015a8  test    rax, rax
0x1800015ab  jz      loc_1800016BA
0x1800015b1  mov     r12, [rax+28h]
0x1800015b5  test    r12, r12
0x1800015b8  jz      loc_1800016BA
0x1800015be  test    rdx, rdx
0x1800015c1  jz      loc_1800016C1
0x1800015c7  test    rdi, rdi
0x1800015ca  jz      loc_1800016C1
0x1800015d0  test    rbx, rbx
0x1800015d3  jz      loc_1800016C1
0x1800015d9  test    rcx, rcx
0x1800015dc  jz      loc_1800016C1
0x1800015e2  mov     rax, [rdx]
0x1800015e5  mov     r10d, 8
0x1800015eb  mov     [rsp+0E8h+var_78], r15
0x1800015f0  mov     [rsp+0E8h+var_80], r14
0x1800015f5  mov     [rsp+0E8h+var_88], rcx
0x1800015fa  mov     rcx, rsi
0x1800015fd  mov     [r11-68h], rax
0x180001601  mov     rax, [rdx+8]
0x180001605  mov     rdx, [rsp+0E8h+arg_40]
0x18000160d  mov     [r11-60h], rax
0x180001611  mov     eax, 10h
0x180001616  mov     r11d, [rdi]
0x180001619  test    r11d, r11d
0x18000161c  cmovnz  r10d, eax
0x180001620  lea     rax, [rsp+0E8h+var_58]
0x180001628  mov     [rsp+0E8h+var_90], rax
0x18000162d  mov     eax, [rsp+0E8h+arg_48]
0x180001634  mov     [rsp+0E8h+var_98], eax
0x180001638  mov     rax, r12
0x18000163b  mov     [rsp+0E8h+var_A0], rdx
0x180001640  mov     rdx, [rsp+0E8h+arg_38]
0x180001648  mov     [rsp+0E8h+var_A8], rdx
0x18000164d  mov     rdx, [r10+rdi]
0x180001651  mov     [rsp+0E8h+var_B0], r11d
0x180001656  mov     [rsp+0E8h+var_B8], rdx
0x18000165b  mov     edx, [rsp+0E8h+arg_20]
0x180001662  mov     [rsp+0E8h+var_C0], rbp
0x180001667  mov     [rsp+0E8h+var_C8], edx
0x18000166b  lea     rdx, [rsp+0E8h+var_68]
0x180001673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001678  mov     ecx, eax
0x18000167a  test    eax, eax
0x18000167c  js      short loc_180001697
0x18000167e  mov     rax, [rsp+0E8h+var_58]
0x180001686  mov     [rbx], rax
0x180001689  mov     rax, [rsp+0E8h+var_50]
0x180001691  mov     [rbx+8], rax
0x180001695  mov     eax, ecx
0x180001697  mov     rcx, [rsp+0E8h+var_48]
0x18000169f  xor     rcx, rsp; StackCookie
0x1800016a2  call    __security_check_cookie
0x1800016a7  add     rsp, 0B0h
0x1800016ae  pop     r15
0x1800016b0  pop     r14
0x1800016b2  pop     r12
0x1800016b4  pop     rdi
0x1800016b5  pop     rsi
0x1800016b6  pop     rbp
0x1800016b7  pop     rbx
0x1800016b8  retn
0x1800016ba  mov     eax, 0C00000BBh
0x1800016bf  jmp     short loc_180001697
0x1800016c1  mov     eax, 0C000000Dh
0x1800016c6  jmp     short loc_180001697
```
