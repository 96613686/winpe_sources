# SspirGetUserName

- ea: `0x180001400`
- end: `0x180001469`
- name: `SspirGetUserName`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c40`

## callees

- `0x180001400`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirGetUserName(__int64 a1, __int128 *a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int64 v5; // rax
  __int64 (__fastcall *v7)(__int64, __int128 *); // rax
  __int128 v8; // [rsp+30h] [rbp-18h] BYREF

  v5 = gLsapSspiExtension;
  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 120) )
    return 3221225659LL;
  if ( !a2 || !a4 || !a5 )
    return 3221225485LL;
  *a5 = 0;
  v7 = *(__int64 (__fastcall **)(__int64, __int128 *))(v5 + 120);
  v8 = *a2;
  return v7(a1, &v8);
}

```

## disassembly

```asm
0x180001400  sub     rsp, 48h
0x180001404  mov     rax, cs:gLsapSspiExtension
0x18000140b  test    rax, rax
0x18000140e  jz      short loc_180001417
0x180001410  cmp     qword ptr [rax+78h], 0
0x180001415  jnz     short loc_180001422
0x180001417  mov     eax, 0C00000BBh
0x18000141c  add     rsp, 48h
0x180001420  retn
0x180001422  test    rdx, rdx
0x180001425  jz      short loc_18000145E
0x180001427  test    r9, r9
0x18000142a  jz      short loc_18000145E
0x18000142c  mov     r10, [rsp+48h+arg_20]
0x180001431  test    r10, r10
0x180001434  jz      short loc_18000145E
0x180001436  mov     dword ptr [r10], 0
0x18000143d  movups  xmm0, xmmword ptr [rdx]
0x180001440  mov     rax, [rax+78h]
0x180001444  lea     rdx, [rsp+48h+var_18]
0x180001449  mov     [rsp+48h+var_28], r10
0x18000144e  movups  [rsp+48h+var_18], xmm0
0x180001453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001458  add     rsp, 48h
0x18000145c  retn
0x18000145e  mov     eax, 0C000000Dh
0x180001463  add     rsp, 48h
0x180001467  retn
```
