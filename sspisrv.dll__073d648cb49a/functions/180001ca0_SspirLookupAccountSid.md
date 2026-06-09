# SspirLookupAccountSid

- ea: `0x180001ca0`
- end: `0x180001d98`
- name: `SspirLookupAccountSid`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001ca0`
- `0x180004010`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180001d19`
- `ntdll!RtlValidSid` at `0x180001d19`

## pseudocode

```c
__int64 __fastcall SspirLookupAccountSid(__int64 a1, __int128 *a2, void *a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int128 v11; // [rsp+40h] [rbp-28h] BYREF

  v11 = 0;
  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 104) )
    return 3221225659LL;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
    return 3221225485LL;
  if ( !RtlValidSid(a3) )
    return 3221225592LL;
  v11 = *a2;
  return (*(__int64 (__fastcall **)(__int64, __int128 *, void *, __int64, __int64, __int64))(gLsapSspiExtension + 104))(
           a1,
           &v11,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180001ca0  mov     [rsp+arg_10], rbx
0x180001ca5  push    rbp
0x180001ca6  push    rsi
0x180001ca7  push    rdi
0x180001ca8  sub     rsp, 50h
0x180001cac  mov     rax, cs:gLsapSspiExtension
0x180001cb3  xorps   xmm0, xmm0
0x180001cb6  mov     rdi, r9
0x180001cb9  mov     rbx, r8
0x180001cbc  mov     rsi, rdx
0x180001cbf  mov     rbp, rcx
0x180001cc2  movups  [rsp+68h+var_28], xmm0
0x180001cc7  test    rax, rax
0x180001cca  jz      loc_180001D82
0x180001cd0  cmp     qword ptr [rax+68h], 0
0x180001cd5  jz      loc_180001D82
0x180001cdb  mov     [rsp+68h+arg_0], r14
0x180001ce0  mov     [rsp+68h+arg_8], r15
0x180001ce5  test    rdx, rdx
0x180001ce8  jz      loc_180001D7B
0x180001cee  test    rbx, rbx
0x180001cf1  jz      loc_180001D7B
0x180001cf7  test    r9, r9
0x180001cfa  jz      short loc_180001D7B
0x180001cfc  mov     r14, [rsp+68h+arg_20]
0x180001d04  test    r14, r14
0x180001d07  jz      short loc_180001D7B
0x180001d09  mov     r15, [rsp+68h+arg_28]
0x180001d11  test    r15, r15
0x180001d14  jz      short loc_180001D7B
0x180001d16  mov     rcx, rbx; Sid
0x180001d19  call    cs:__imp_RtlValidSid
0x180001d20  nop     dword ptr [rax+rax+00h]
0x180001d25  test    al, al
0x180001d27  jnz     short loc_180001D49
0x180001d29  mov     eax, 0C0000078h
0x180001d2e  mov     r14, [rsp+68h+arg_0]
0x180001d33  mov     r15, [rsp+68h+arg_8]
0x180001d38  mov     rbx, [rsp+68h+arg_10]
0x180001d40  add     rsp, 50h
0x180001d44  pop     rdi
0x180001d45  pop     rsi
0x180001d46  pop     rbp
0x180001d47  retn
0x180001d49  movups  xmm0, xmmword ptr [rsi]
0x180001d4c  mov     rax, cs:gLsapSspiExtension
0x180001d53  lea     rdx, [rsp+68h+var_28]
0x180001d58  mov     [rsp+68h+var_40], r15
0x180001d5d  mov     r9, rdi
0x180001d60  movups  [rsp+68h+var_28], xmm0
0x180001d65  mov     r8, rbx
0x180001d68  mov     [rsp+68h+var_48], r14
0x180001d6d  mov     rax, [rax+68h]
0x180001d71  mov     rcx, rbp
0x180001d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d79  jmp     short loc_180001D2E
0x180001d7b  mov     eax, 0C000000Dh
0x180001d80  jmp     short loc_180001D2E
0x180001d82  mov     rbx, [rsp+68h+arg_10]
0x180001d8a  mov     eax, 0C00000BBh
0x180001d8f  add     rsp, 50h
0x180001d93  pop     rdi
0x180001d94  pop     rsi
0x180001d95  pop     rbp
0x180001d96  retn
```
