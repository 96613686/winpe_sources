# ZoneCheckUrlExCacheW

- ea: `0x18000b050`
- end: `0x18000b1f2`
- name: `ZoneCheckUrlExCacheW`
- size: `418`
- prototype: `__int64 __fastcall(__int64, int *, int, int *, int, unsigned int, int, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b000`
- `0x180034dd0`
- `0x180034e70`
- `0x180034f20`
- `0x180034fe0`

## callees

- `0x18000b050`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b0ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b0ee`

## pseudocode

```c
__int64 __fastcall ZoneCheckUrlExCacheW(
        __int64 a1,
        int *a2,
        int a3,
        int *a4,
        int a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        _QWORD *a9)
{
  HRESULT v13; // ebx
  int v15; // eax
  int *v16; // rcx
  int *v17; // r9
  LPVOID ppv; // [rsp+50h] [rbp-28h] BYREF
  int v20; // [rsp+58h] [rbp-20h] BYREF
  int v21; // [rsp+5Ch] [rbp-1Ch] BYREF

  v13 = -2147024809;
  if ( a1 )
  {
    ppv = 0;
    if ( a9 && *a9 )
    {
      v13 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))*a9)(
              *a9,
              &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
              &ppv);
      if ( v13 < 0 )
        return (unsigned int)v13;
    }
    else
    {
      v13 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppv);
      if ( v13 < 0 )
        return (unsigned int)v13;
      if ( a9 )
        (**(void (__fastcall ***)(LPVOID, GUID *, _QWORD *))ppv)(ppv, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, a9);
    }
    v21 = 0;
    v20 = 0;
    if ( a8 )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, a8);
    v15 = 4;
    if ( !a4 )
      a5 = 4;
    v16 = &v20;
    if ( a4 )
      v16 = a4;
    if ( a2 )
      v15 = a3;
    v17 = &v21;
    if ( a2 )
      v17 = a2;
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, int *, int, int *, int, int, _DWORD))(*(_QWORD *)ppv + 56LL))(
            ppv,
            a1,
            a6,
            v17,
            v15,
            v16,
            a5,
            a7,
            0);
    if ( a8 )
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b050  push    rbp
0x18000b052  push    rbx
0x18000b053  push    rsi
0x18000b054  push    rdi
0x18000b055  push    r12
0x18000b057  push    r13
0x18000b059  push    r14
0x18000b05b  push    r15
0x18000b05d  mov     rbp, rsp
0x18000b060  sub     rsp, 78h
0x18000b064  mov     rax, cs:__security_cookie
0x18000b06b  xor     rax, rsp
0x18000b06e  mov     [rbp+var_18], rax
0x18000b072  mov     r14, [rbp+arg_38]
0x18000b079  mov     rsi, r9
0x18000b07c  mov     rdi, [rbp+arg_40]
0x18000b083  mov     r15, rdx
0x18000b086  mov     r12d, r8d
0x18000b089  mov     r13, rcx
0x18000b08c  mov     ebx, 80070057h
0x18000b091  test    rcx, rcx
0x18000b094  jz      loc_18000B1D3
0x18000b09a  mov     [rbp+var_28], 0
0x18000b0a2  test    rdi, rdi
0x18000b0a5  jz      short loc_18000B0D1
0x18000b0a7  mov     rcx, [rdi]
0x18000b0aa  test    rcx, rcx
0x18000b0ad  jz      short loc_18000B0D1
0x18000b0af  mov     rax, [rcx]
0x18000b0b2  lea     r8, [rbp+var_28]
0x18000b0b6  lea     rdx, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b
0x18000b0bd  mov     rax, [rax]
0x18000b0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0c5  mov     ebx, eax
0x18000b0c7  test    eax, eax
0x18000b0c9  js      loc_18000B1D3
0x18000b0cf  jmp     short loc_18000B11C
0x18000b0d1  xor     edx, edx; pUnkOuter
0x18000b0d3  lea     rax, [rbp+var_28]
0x18000b0d7  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18000b0de  mov     [rsp+78h+ppv], rax; ppv
0x18000b0e3  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18000b0ea  lea     r8d, [rdx+1]; dwClsContext
0x18000b0ee  call    cs:__imp_CoCreateInstance
0x18000b0f4  mov     ebx, eax
0x18000b0f6  test    eax, eax
0x18000b0f8  js      loc_18000B1D3
0x18000b0fe  test    rdi, rdi
0x18000b101  jz      short loc_18000B11C
0x18000b103  mov     rcx, [rbp+var_28]
0x18000b107  lea     rdx, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b
0x18000b10e  mov     r8, rdi
0x18000b111  mov     rax, [rcx]
0x18000b114  mov     rax, [rax]
0x18000b117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11c  mov     [rbp+var_1C], 0
0x18000b123  mov     [rbp+var_20], 0
0x18000b12a  test    r14, r14
0x18000b12d  jz      short loc_18000B142
0x18000b12f  mov     rcx, [rbp+var_28]
0x18000b133  mov     rdx, r14
0x18000b136  mov     rax, [rcx]
0x18000b139  mov     rax, [rax+18h]
0x18000b13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b142  mov     r10, [rbp+var_28]
0x18000b146  mov     edx, [rbp+arg_20]
0x18000b149  mov     rax, [r10]
0x18000b14c  mov     r11, [rax+38h]
0x18000b150  mov     eax, 4
0x18000b155  test    rsi, rsi
0x18000b158  jnz     short loc_18000B15C
0x18000b15a  mov     edx, eax
0x18000b15c  test    rsi, rsi
0x18000b15f  lea     rcx, [rbp+var_20]
0x18000b163  cmovnz  rcx, rsi
0x18000b167  test    r15, r15
0x18000b16a  jz      short loc_18000B16F
0x18000b16c  mov     rax, r12
0x18000b16f  mov     r8d, [rbp+arg_30]
0x18000b173  lea     r9, [rbp+var_1C]
0x18000b177  mov     [rsp+78h+var_38], 0
0x18000b17f  test    r15, r15
0x18000b182  mov     [rsp+78h+var_40], r8d
0x18000b187  mov     r8d, [rbp+arg_28]
0x18000b18b  cmovnz  r9, r15
0x18000b18f  mov     [rsp+78h+var_48], edx
0x18000b193  mov     rdx, r13
0x18000b196  mov     [rsp+78h+var_50], rcx
0x18000b19b  mov     rcx, r10
0x18000b19e  mov     dword ptr [rsp+78h+ppv], eax
0x18000b1a2  mov     rax, r11
0x18000b1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1aa  mov     ebx, eax
0x18000b1ac  test    r14, r14
0x18000b1af  jz      short loc_18000B1C3
0x18000b1b1  mov     rcx, [rbp+var_28]
0x18000b1b5  xor     edx, edx
0x18000b1b7  mov     rax, [rcx]
0x18000b1ba  mov     rax, [rax+18h]
0x18000b1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c3  mov     rcx, [rbp+var_28]
0x18000b1c7  mov     rax, [rcx]
0x18000b1ca  mov     rax, [rax+10h]
0x18000b1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1d3  mov     eax, ebx
0x18000b1d5  mov     rcx, [rbp+var_18]
0x18000b1d9  xor     rcx, rsp; StackCookie
0x18000b1dc  call    __security_check_cookie
0x18000b1e1  add     rsp, 78h
0x18000b1e5  pop     r15
0x18000b1e7  pop     r14
0x18000b1e9  pop     r13
0x18000b1eb  pop     r12
0x18000b1ed  pop     rdi
0x18000b1ee  pop     rsi
0x18000b1ef  pop     rbx
0x18000b1f0  pop     rbp
0x18000b1f1  retn
```
