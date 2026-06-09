# SspirDeleteSecurityContext

- ea: `0x180001470`
- end: `0x180001500`
- name: `SspirDeleteSecurityContext`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ad0`

## callees

- `0x180001470`
- `0x1800033f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirDeleteSecurityContext(__int64 a1, _QWORD *a2, __int128 *a3)
{
  __int64 (__fastcall *v3)(__int64, _QWORD *, __int128 *); // rax
  __int128 v4; // xmm0
  _QWORD v6[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v3 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(gLsapSspiExtension + 64);
  if ( !v3 )
    return 3221225659LL;
  if ( !a2 || !a3 )
    return 3221225485LL;
  v4 = *a3;
  v6[0] = *a2;
  v6[1] = a2[1];
  v7 = v4;
  return v3(a1, v6, &v7);
}

```

## disassembly

```asm
0x180001470  sub     rsp, 68h
0x180001474  mov     rax, cs:__security_cookie
0x18000147b  xor     rax, rsp
0x18000147e  mov     [rsp+68h+var_18], rax
0x180001483  mov     rax, cs:gLsapSspiExtension
0x18000148a  mov     r10, rdx
0x18000148d  test    rax, rax
0x180001490  jz      short loc_1800014E1
0x180001492  mov     rax, [rax+40h]
0x180001496  test    rax, rax
0x180001499  jz      short loc_1800014E1
0x18000149b  test    rdx, rdx
0x18000149e  jz      short loc_1800014E8
0x1800014a0  test    r8, r8
0x1800014a3  jz      short loc_1800014E8
0x1800014a5  mov     rdx, [rdx]
0x1800014a8  movups  xmm0, xmmword ptr [r8]
0x1800014ac  mov     [rsp+68h+var_38], rdx
0x1800014b1  lea     r8, [rsp+68h+var_28]
0x1800014b6  mov     rdx, [r10+8]
0x1800014ba  mov     [rsp+68h+var_30], rdx
0x1800014bf  lea     rdx, [rsp+68h+var_38]
0x1800014c4  movups  [rsp+68h+var_28], xmm0
0x1800014c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014ce  mov     rcx, [rsp+68h+var_18]
0x1800014d3  xor     rcx, rsp; StackCookie
0x1800014d6  call    __security_check_cookie
0x1800014db  add     rsp, 68h
0x1800014df  retn
0x1800014e1  mov     eax, 0C00000BBh
0x1800014e6  jmp     short loc_1800014CE
0x1800014e8  mov     eax, 0C000000Dh
0x1800014ed  mov     rcx, [rsp+68h+var_18]
0x1800014f2  xor     rcx, rsp; StackCookie
0x1800014f5  call    __security_check_cookie
0x1800014fa  add     rsp, 68h
0x1800014fe  retn
```
