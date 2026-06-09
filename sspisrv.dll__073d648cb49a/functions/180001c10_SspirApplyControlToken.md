# SspirApplyControlToken

- ea: `0x180001c10`
- end: `0x180001c94`
- name: `SspirApplyControlToken`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002a20`

## callees

- `0x180001c10`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirApplyControlToken(__int64 a1, _QWORD *a2, __int128 *a3, __int64 a4)
{
  __int64 (__fastcall *v4)(__int64, _QWORD *, __int128 *); // rax
  __int128 v5; // xmm0
  _QWORD v7[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(gLsapSspiExtension + 96);
  if ( !v4 )
    return 3221225659LL;
  if ( !a2 || !a3 || !a4 )
    return 3221225485LL;
  v5 = *a3;
  v7[0] = *a2;
  v7[1] = a2[1];
  v8 = v5;
  return v4(a1, v7, &v8);
}

```

## disassembly

```asm
0x180001c10  sub     rsp, 68h
0x180001c14  mov     rax, cs:__security_cookie
0x180001c1b  xor     rax, rsp
0x180001c1e  mov     [rsp+68h+var_18], rax
0x180001c23  mov     rax, cs:gLsapSspiExtension
0x180001c2a  mov     r10, rdx
0x180001c2d  test    rax, rax
0x180001c30  jz      short loc_180001C86
0x180001c32  mov     rax, [rax+60h]
0x180001c36  test    rax, rax
0x180001c39  jz      short loc_180001C86
0x180001c3b  test    rdx, rdx
0x180001c3e  jz      short loc_180001C8D
0x180001c40  test    r8, r8
0x180001c43  jz      short loc_180001C8D
0x180001c45  test    r9, r9
0x180001c48  jz      short loc_180001C8D
0x180001c4a  mov     rdx, [rdx]
0x180001c4d  movups  xmm0, xmmword ptr [r8]
0x180001c51  mov     [rsp+68h+var_38], rdx
0x180001c56  lea     r8, [rsp+68h+var_28]
0x180001c5b  mov     rdx, [r10+8]
0x180001c5f  mov     [rsp+68h+var_30], rdx
0x180001c64  lea     rdx, [rsp+68h+var_38]
0x180001c69  movups  [rsp+68h+var_28], xmm0
0x180001c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c73  mov     rcx, [rsp+68h+var_18]
0x180001c78  xor     rcx, rsp; StackCookie
0x180001c7b  call    __security_check_cookie
0x180001c80  add     rsp, 68h
0x180001c84  retn
0x180001c86  mov     eax, 0C00000BBh
0x180001c8b  jmp     short loc_180001C73
0x180001c8d  mov     eax, 0C000000Dh
0x180001c92  jmp     short loc_180001C73
```
