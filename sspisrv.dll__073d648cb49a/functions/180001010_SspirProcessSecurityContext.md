# SspirProcessSecurityContext

- ea: `0x180001010`
- end: `0x18000129c`
- name: `SspirProcessSecurityContext`
- size: `652`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _OWORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002f20`

## callees

- `0x180001010`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirProcessSecurityContext(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int128 *a5,
        __int128 *a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        _OWORD *a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  __int64 result; // rax
  __int64 (__fastcall *v22)(__int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int128 *, __int64, __int64, __int64, __int64, __int64); // [rsp+C8h] [rbp-A0h]
  _QWORD v23[2]; // [rsp+D0h] [rbp-98h] BYREF
  __int128 v24; // [rsp+E0h] [rbp-88h] BYREF
  __int128 v25; // [rsp+F0h] [rbp-78h] BYREF
  __int128 v26; // [rsp+100h] [rbp-68h] BYREF

  v24 = 0;
  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64, __int64, __int128 *, __int128 *, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int128 *, __int64, __int64, __int64, __int64, __int64))(gLsapSspiExtension + 56);
  if ( !v22 )
    return 3221225659LL;
  if ( !a2 || !a3 || !a5 || !a6 || !a11 || !a12 || !a13 || !a15 || !a16 || !a17 )
    return 3221225485LL;
  v23[0] = *a2;
  v23[1] = a2[1];
  v26 = *a5;
  v25 = *a6;
  result = v22(a1, v23, a3, a4, &v26, &v25, a7, a8, a9, a10, a11, a12, a13, a14, a15, &v24, a17, a18, a19, a20, a21);
  if ( (int)result >= 0 )
  {
    *a16 = v24;
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rbp
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r12
0x180001017  push    r13
0x180001019  push    r14
0x18000101b  push    r15
0x18000101d  sub     rsp, 128h
0x180001024  mov     rax, cs:__security_cookie
0x18000102b  xor     rax, rsp
0x18000102e  mov     [rsp+168h+var_58], rax
0x180001036  mov     rax, [rsp+168h+arg_90]
0x18000103e  xorps   xmm0, xmm0
0x180001041  mov     rbx, [rsp+168h+arg_78]
0x180001049  mov     rbp, r9
0x18000104c  mov     r14, [rsp+168h+arg_40]
0x180001054  mov     rsi, rcx
0x180001057  mov     r15, [rsp+168h+arg_48]
0x18000105f  mov     r10, [rsp+168h+arg_50]
0x180001067  mov     rcx, [rsp+168h+arg_58]
0x18000106f  mov     r11, [rsp+168h+arg_60]
0x180001077  mov     r12, [rsp+168h+arg_68]
0x18000107f  mov     r9, [rsp+168h+arg_70]
0x180001087  mov     rdi, [rsp+168h+arg_80]
0x18000108f  mov     r13, [rsp+168h+arg_88]
0x180001097  mov     [rsp+168h+var_A8], rax
0x18000109f  mov     rax, [rsp+168h+arg_98]
0x1800010a7  mov     [rsp+168h+var_B0], rax
0x1800010af  mov     rax, [rsp+168h+arg_A0]
0x1800010b7  mov     [rsp+168h+var_B8], rax
0x1800010bf  mov     rax, cs:gLsapSspiExtension
0x1800010c6  movups  [rsp+168h+var_88], xmm0
0x1800010ce  test    rax, rax
0x1800010d1  jz      loc_18000128E
0x1800010d7  mov     rax, [rax+38h]
0x1800010db  mov     [rsp+168h+var_A0], rax
0x1800010e3  test    rax, rax
0x1800010e6  jz      loc_18000128E
0x1800010ec  test    rdx, rdx
0x1800010ef  jz      loc_180001295
0x1800010f5  test    r8, r8
0x1800010f8  jz      loc_180001295
0x1800010fe  cmp     [rsp+168h+arg_20], 0
0x180001107  jz      loc_180001295
0x18000110d  cmp     [rsp+168h+arg_28], 0
0x180001116  jz      loc_180001295
0x18000111c  test    r10, r10
0x18000111f  jz      loc_180001295
0x180001125  test    rcx, rcx
0x180001128  jz      loc_180001295
0x18000112e  test    r11, r11
0x180001131  jz      loc_180001295
0x180001137  test    r9, r9
0x18000113a  jz      loc_180001295
0x180001140  test    rbx, rbx
0x180001143  jz      loc_180001295
0x180001149  test    rdi, rdi
0x18000114c  jz      loc_180001295
0x180001152  mov     rax, [rdx]
0x180001155  mov     [rsp+168h+var_98], rax
0x18000115d  mov     rax, [rdx+8]
0x180001161  mov     edx, [rsp+168h+arg_38]
0x180001168  mov     [rsp+168h+var_90], rax
0x180001170  mov     rax, [rsp+168h+arg_20]
0x180001178  movups  xmm0, xmmword ptr [rax]
0x18000117b  mov     rax, [rsp+168h+arg_28]
0x180001183  movups  [rsp+168h+var_68], xmm0
0x18000118b  movups  xmm1, xmmword ptr [rax]
0x18000118e  mov     rax, [rsp+168h+var_B8]
0x180001196  mov     [rsp+168h+var_C8], rax
0x18000119e  mov     rax, [rsp+168h+var_B0]
0x1800011a6  mov     [rsp+168h+var_D0], rax
0x1800011ae  mov     rax, [rsp+168h+var_A8]
0x1800011b6  mov     [rsp+168h+var_D8], rax
0x1800011be  lea     rax, [rsp+168h+var_88]
0x1800011c6  mov     [rsp+168h+var_E0], r13
0x1800011ce  mov     [rsp+168h+var_E8], rdi
0x1800011d6  mov     [rsp+168h+var_F0], rax
0x1800011db  lea     rax, [rsp+168h+var_78]
0x1800011e3  mov     [rsp+168h+var_F8], r9
0x1800011e8  mov     r9, rbp
0x1800011eb  mov     [rsp+168h+var_100], r12
0x1800011f0  mov     [rsp+168h+var_108], r11
0x1800011f5  mov     [rsp+168h+var_110], rcx
0x1800011fa  mov     rcx, rsi
0x1800011fd  mov     [rsp+168h+var_118], r10
0x180001202  mov     [rsp+168h+var_120], r15
0x180001207  mov     [rsp+168h+var_128], r14
0x18000120c  mov     [rsp+168h+var_130], edx
0x180001210  mov     edx, [rsp+168h+arg_30]
0x180001217  mov     [rsp+168h+var_138], edx
0x18000121b  lea     rdx, [rsp+168h+var_98]
0x180001223  mov     [rsp+168h+var_140], rax
0x180001228  lea     rax, [rsp+168h+var_68]
0x180001230  mov     [rsp+168h+var_148], rax
0x180001235  mov     rax, [rsp+168h+var_A0]
0x18000123d  movups  [rsp+168h+var_78], xmm1
0x180001245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000124a  mov     ecx, eax
0x18000124c  test    eax, eax
0x18000124e  js      short loc_180001269
0x180001250  mov     rax, qword ptr [rsp+168h+var_88]
0x180001258  mov     [rbx], rax
0x18000125b  mov     rax, qword ptr [rsp+168h+var_88+8]
0x180001263  mov     [rbx+8], rax
0x180001267  mov     eax, ecx
0x180001269  mov     rcx, [rsp+168h+var_58]
0x180001271  xor     rcx, rsp; StackCookie
0x180001274  call    __security_check_cookie
0x180001279  add     rsp, 128h
0x180001280  pop     r15
0x180001282  pop     r14
0x180001284  pop     r13
0x180001286  pop     r12
0x180001288  pop     rdi
0x180001289  pop     rsi
0x18000128a  pop     rbp
0x18000128b  pop     rbx
0x18000128c  retn
0x18000128e  mov     eax, 0C00000BBh
0x180001293  jmp     short loc_180001269
0x180001295  mov     eax, 0C000000Dh
0x18000129a  jmp     short loc_180001269
```
