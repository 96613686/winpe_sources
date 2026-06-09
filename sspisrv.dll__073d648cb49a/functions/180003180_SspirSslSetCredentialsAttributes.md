# SspirSslSetCredentialsAttributes

- ea: `0x180003180`
- end: `0x18000320e`
- name: `SspirSslSetCredentialsAttributes`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003180`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirSslSetCredentialsAttributes(__int64 a1, _QWORD *a2, __int128 *a3, __int64 a4)
{
  __int64 (__fastcall *v4)(__int64, _QWORD *, __int128 *, __int64, __int64); // rax
  __int128 v5; // xmm0
  _QWORD v7[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, __int64, __int64))(gLsapSspiExtension + 88);
  if ( !v4 )
    return 3221225659LL;
  if ( !a2 || !a3 || !a4 )
    return 3221225485LL;
  v5 = *a3;
  v7[0] = *a2;
  v7[1] = a2[1];
  v8 = v5;
  return v4(a1, v7, &v8, 96, a4);
}

```

## disassembly

```asm
0x180003180  mov     r11, rsp
0x180003183  sub     rsp, 68h
0x180003187  mov     rax, cs:__security_cookie
0x18000318e  xor     rax, rsp
0x180003191  mov     [rsp+68h+var_18], rax
0x180003196  mov     rax, cs:gLsapSspiExtension
0x18000319d  mov     r10, rdx
0x1800031a0  test    rax, rax
0x1800031a3  jz      short loc_1800031F6
0x1800031a5  mov     rax, [rax+58h]
0x1800031a9  test    rax, rax
0x1800031ac  jz      short loc_1800031F6
0x1800031ae  test    rdx, rdx
0x1800031b1  jz      short loc_1800031EF
0x1800031b3  test    r8, r8
0x1800031b6  jz      short loc_1800031EF
0x1800031b8  test    r9, r9
0x1800031bb  jz      short loc_1800031EF
0x1800031bd  mov     rdx, [rdx]
0x1800031c0  movups  xmm0, xmmword ptr [r8]
0x1800031c4  mov     [r11-38h], rdx
0x1800031c8  lea     r8, [r11-28h]
0x1800031cc  mov     rdx, [r10+8]
0x1800031d0  mov     [r11-30h], rdx
0x1800031d4  lea     rdx, [r11-38h]
0x1800031d8  mov     [r11-48h], r9
0x1800031dc  mov     r9d, 60h ; '`'
0x1800031e2  movdqu  [rsp+68h+var_28], xmm0
0x1800031e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ed  jmp     short loc_1800031FB
0x1800031ef  mov     eax, 0C000000Dh
0x1800031f4  jmp     short loc_1800031FB
0x1800031f6  mov     eax, 0C00000BBh
0x1800031fb  mov     rcx, [rsp+68h+var_18]
0x180003200  xor     rcx, rsp; StackCookie
0x180003203  call    __security_check_cookie
0x180003208  add     rsp, 68h
0x18000320c  retn
```
