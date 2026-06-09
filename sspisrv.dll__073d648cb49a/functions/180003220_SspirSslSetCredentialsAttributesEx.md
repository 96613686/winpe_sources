# SspirSslSetCredentialsAttributesEx

- ea: `0x180003220`
- end: `0x1800032b2`
- name: `SspirSslSetCredentialsAttributesEx`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003220`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirSslSetCredentialsAttributesEx(__int64 a1, _QWORD *a2, __int128 *a3, __int64 a4, __int64 a5)
{
  __int64 (__fastcall *v5)(__int64, _QWORD *, __int128 *); // rax
  __int128 v6; // xmm0
  _QWORD v8[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(gLsapSspiExtension + 88);
  if ( !v5 )
    return 3221225659LL;
  if ( !a2 || !a3 || !a5 )
    return 3221225485LL;
  v6 = *a3;
  v8[0] = *a2;
  v8[1] = a2[1];
  v9 = v6;
  return v5(a1, v8, &v9);
}

```

## disassembly

```asm
0x180003220  sub     rsp, 68h
0x180003224  mov     rax, cs:__security_cookie
0x18000322b  xor     rax, rsp
0x18000322e  mov     [rsp+68h+var_18], rax
0x180003233  mov     rax, cs:gLsapSspiExtension
0x18000323a  mov     r10, rdx
0x18000323d  mov     r11, [rsp+68h+arg_20]
0x180003245  test    rax, rax
0x180003248  jz      short loc_18000329A
0x18000324a  mov     rax, [rax+58h]
0x18000324e  test    rax, rax
0x180003251  jz      short loc_18000329A
0x180003253  test    rdx, rdx
0x180003256  jz      short loc_180003293
0x180003258  test    r8, r8
0x18000325b  jz      short loc_180003293
0x18000325d  test    r11, r11
0x180003260  jz      short loc_180003293
0x180003262  mov     rdx, [rdx]
0x180003265  movups  xmm0, xmmword ptr [r8]
0x180003269  mov     [rsp+68h+var_38], rdx
0x18000326e  lea     r8, [rsp+68h+var_28]
0x180003273  mov     rdx, [r10+8]
0x180003277  mov     [rsp+68h+var_30], rdx
0x18000327c  lea     rdx, [rsp+68h+var_38]
0x180003281  movdqu  [rsp+68h+var_28], xmm0
0x180003287  mov     [rsp+68h+var_48], r11
0x18000328c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003291  jmp     short loc_18000329F
0x180003293  mov     eax, 0C000000Dh
0x180003298  jmp     short loc_18000329F
0x18000329a  mov     eax, 0C00000BBh
0x18000329f  mov     rcx, [rsp+68h+var_18]
0x1800032a4  xor     rcx, rsp; StackCookie
0x1800032a7  call    __security_check_cookie
0x1800032ac  add     rsp, 68h
0x1800032b0  retn
```
