# SspirNegQueryContextAttributes

- ea: `0x180002e10`
- end: `0x180002f10`
- name: `SspirNegQueryContextAttributes`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800013d0`
- `0x180001510`
- `0x180002e10`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirNegQueryContextAttributes(__int64 a1, _QWORD *a2, __int128 *a3, unsigned int a4, _QWORD *a5)
{
  void *v7; // rax
  void *v8; // rbx
  int v10; // edi
  _QWORD v11[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-38h] BYREF

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 80) )
    return 3221225659LL;
  if ( !a2 )
    return 3221225485LL;
  if ( !a3 )
    return 3221225485LL;
  if ( !a5 )
    return 3221225485LL;
  v11[0] = *a2;
  v11[1] = a2[1];
  v12 = *a3;
  if ( a4 )
  {
    if ( a4 != 12 )
      return 3221225485LL;
  }
  v7 = MIDL_user_allocate(0x10u);
  v8 = v7;
  if ( !v7 )
    return 3221225626LL;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, _QWORD, void *))(gLsapSspiExtension + 80))(
          a1,
          v11,
          &v12,
          a4,
          v7);
  if ( v10 < 0 )
    MIDL_user_free(v8);
  else
    *a5 = v8;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180002e10  mov     [rsp+arg_10], rbx
0x180002e15  push    rbp
0x180002e16  push    rsi
0x180002e17  push    rdi
0x180002e18  sub     rsp, 60h
0x180002e1c  mov     rax, cs:__security_cookie
0x180002e23  xor     rax, rsp
0x180002e26  mov     [rsp+78h+var_28], rax
0x180002e2b  mov     rax, cs:gLsapSspiExtension
0x180002e32  mov     edi, r9d
0x180002e35  mov     rsi, [rsp+78h+arg_20]
0x180002e3d  mov     rbp, rcx
0x180002e40  test    rax, rax
0x180002e43  jz      loc_180002EED
0x180002e49  cmp     qword ptr [rax+50h], 0
0x180002e4e  jz      loc_180002EED
0x180002e54  test    rdx, rdx
0x180002e57  jz      loc_180002EE6
0x180002e5d  test    r8, r8
0x180002e60  jz      loc_180002EE6
0x180002e66  test    rsi, rsi
0x180002e69  jz      short loc_180002EE6
0x180002e6b  mov     rax, [rdx]
0x180002e6e  mov     [rsp+78h+var_48], rax
0x180002e73  mov     rax, [rdx+8]
0x180002e77  mov     [rsp+78h+var_40], rax
0x180002e7c  movups  xmm0, xmmword ptr [r8]
0x180002e80  movdqu  [rsp+78h+var_38], xmm0
0x180002e86  test    r9d, r9d
0x180002e89  jz      short loc_180002E91
0x180002e8b  cmp     r9d, 0Ch
0x180002e8f  jnz     short loc_180002EE6
0x180002e91  mov     ecx, 10h; size
0x180002e96  call    MIDL_user_allocate
0x180002e9b  mov     rbx, rax
0x180002e9e  test    rax, rax
0x180002ea1  jnz     short loc_180002EAA
0x180002ea3  mov     eax, 0C000009Ah
0x180002ea8  jmp     short loc_180002EF2
0x180002eaa  mov     rax, cs:gLsapSspiExtension
0x180002eb1  lea     r8, [rsp+78h+var_38]
0x180002eb6  mov     r9d, edi
0x180002eb9  mov     [rsp+78h+var_58], rbx
0x180002ebe  lea     rdx, [rsp+78h+var_48]
0x180002ec3  mov     rcx, rbp
0x180002ec6  mov     rax, [rax+50h]
0x180002eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ecf  mov     edi, eax
0x180002ed1  test    eax, eax
0x180002ed3  js      short loc_180002EDA
0x180002ed5  mov     [rsi], rbx
0x180002ed8  jmp     short loc_180002EE2
0x180002eda  mov     rcx, rbx; void *
0x180002edd  call    MIDL_user_free
0x180002ee2  mov     eax, edi
0x180002ee4  jmp     short loc_180002EF2
0x180002ee6  mov     eax, 0C000000Dh
0x180002eeb  jmp     short loc_180002EF2
0x180002eed  mov     eax, 0C00000BBh
0x180002ef2  mov     rcx, [rsp+78h+var_28]
0x180002ef7  xor     rcx, rsp; StackCookie
0x180002efa  call    __security_check_cookie
0x180002eff  mov     rbx, [rsp+78h+arg_10]
0x180002f07  add     rsp, 60h
0x180002f0b  pop     rdi
0x180002f0c  pop     rsi
0x180002f0d  pop     rbp
0x180002f0e  retn
```
