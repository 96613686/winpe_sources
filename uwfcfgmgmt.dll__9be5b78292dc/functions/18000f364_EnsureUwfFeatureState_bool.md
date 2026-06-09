# EnsureUwfFeatureState(bool)

- ea: `0x18000f364`
- end: `0x18000f523`
- name: `?EnsureUwfFeatureState@@YAJ_N@Z`
- size: `447`
- prototype: `__int64 __fastcall()`
- caller_count: `53`
- callee_count: `5`
- tags: ``

## callers

- `0x180017d50`
- `0x180017df0`
- `0x180017e90`
- `0x180017fa0`
- `0x180018080`
- `0x1800181a0`
- `0x180018240`
- `0x1800182e0`
- `0x180018390`
- `0x180018430`
- `0x1800184b0`
- `0x180018540`
- `0x1800185f0`
- `0x180018720`
- `0x1800187b0`
- `0x180018830`
- `0x1800188d0`
- `0x180018950`
- `0x180018bf0`
- `0x180018c70`
- `0x180018cf0`
- `0x180018d90`
- `0x180018e40`
- `0x180018f50`
- `0x180018fe0`
- `0x180019070`
- `0x180019110`
- `0x1800191a0`
- `0x180019260`
- `0x180019310`
- `0x1800193c0`
- `0x180019600`
- `0x180019690`
- `0x180019730`
- `0x1800197d0`
- `0x1800198d0`
- `0x180019940`
- `0x1800199b0`
- `0x180019a30`
- `0x180019d70`
- `0x180019df0`
- `0x180019e70`
- `0x180019fa0`
- `0x18001a010`
- `0x18001a080`
- `0x18001a110`
- `0x18001a1a0`
- `0x18001a240`
- `0x18001a2d0`
- `0x18001a4e0`

## callees

- `0x18000e5f0`
- `0x18000f364`
- `0x180010898`
- `0x180010d10`
- `0x18001c010`

## string_xrefs

- `0x18000f42d`: `Client-UnifiedWriteFilter`
- `0x18000f45d`: `Client-UnifiedWriteFilter`
- `0x18000f4ab`: `Client-UnifiedWriteFilter`

## pseudocode

```c
__int64 __fastcall EnsureUwfFeatureState()
{
  int DismLibrary; // ebx
  char v1; // di
  char v2; // si
  __int64 v3; // rcx
  __int64 v5; // [rsp+60h] [rbp-19h] BYREF
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD); // [rsp+68h] [rbp-11h]
  __int64 (__fastcall *v7)(const wchar_t *, _QWORD, _QWORD, unsigned int *); // [rsp+70h] [rbp-9h]
  __int64 (__fastcall *v8)(_QWORD, const wchar_t *, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, int, _QWORD, _QWORD, _QWORD); // [rsp+78h] [rbp-1h]
  __int64 v9; // [rsp+80h] [rbp+7h]
  __int64 (__fastcall *v10)(_QWORD, const wchar_t *, _QWORD, _QWORD, __int64 *); // [rsp+88h] [rbp+Fh]
  void (*v11)(void); // [rsp+90h] [rbp+17h]
  void (__fastcall *v12)(_QWORD); // [rsp+98h] [rbp+1Fh]
  void (*v13)(void); // [rsp+A0h] [rbp+27h]
  bool v14; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v15; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v16; // [rsp+F0h] [rbp+77h] BYREF

  v15 = 0;
  v16 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( (int)QuickCheckUwfFeatureState(&v14) >= 0 && v14 )
  {
    DismLibrary = 0;
  }
  else
  {
    v1 = 0;
    v2 = 0;
    DismLibrary = CDismHelper::LoadDismLibrary((CDismHelper *)&v5);
    if ( DismLibrary < 0
      || (DismLibrary = v6(0, 0, 0), DismLibrary < 0)
      || (v1 = 1, DismLibrary = v7(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v15), DismLibrary < 0)
      || (v2 = 1, DismLibrary = v10(v15, L"Client-UnifiedWriteFilter", 0, 0, &v16), DismLibrary < 0)
      || *(_DWORD *)(v16 + 8) == 2
      && (DismLibrary = v8(v15, L"Client-UnifiedWriteFilter", 0, 0, 0, 0, 0, 1, 0, 0, 0), DismLibrary < 0)
      || (DismLibrary = v10(v15, L"Client-UnifiedWriteFilter", 0, 0, &v16), DismLibrary < 0) )
    {
      v3 = v16;
    }
    else
    {
      v3 = v16;
      if ( *(_DWORD *)(v16 + 8) != 4 )
        DismLibrary = -2147418113;
    }
    if ( v3 )
      v11();
    if ( v2 )
      v12(v15);
    if ( v1 )
      v13();
  }
  CDismHelper::~CDismHelper((CDismHelper *)&v5);
  return (unsigned int)DismLibrary;
}

```

## disassembly

```asm
0x18000f364  mov     [rsp-8+arg_0], cl
0x18000f368  push    rbp
0x18000f369  push    rbx
0x18000f36a  push    rsi
0x18000f36b  push    rdi
0x18000f36c  push    r14
0x18000f36e  lea     rbp, [rsp-37h]
0x18000f373  sub     rsp, 0B0h
0x18000f37a  xor     r14d, r14d
0x18000f37d  lea     rcx, [rbp+57h+arg_0]; bool *
0x18000f381  mov     [rbp+57h+arg_8], r14d
0x18000f385  mov     [rbp+57h+arg_10], r14
0x18000f389  mov     [rbp+57h+var_70], r14
0x18000f38d  mov     [rbp+57h+var_68], r14
0x18000f391  mov     [rbp+57h+var_60], r14
0x18000f395  mov     [rbp+57h+var_58], r14
0x18000f399  mov     [rbp+57h+var_50], r14
0x18000f39d  mov     [rbp+57h+var_48], r14
0x18000f3a1  mov     [rbp+57h+var_40], r14
0x18000f3a5  mov     [rbp+57h+var_38], r14
0x18000f3a9  mov     [rbp+57h+var_30], r14
0x18000f3ad  mov     [rbp+57h+arg_0], r14b
0x18000f3b1  call    ?QuickCheckUwfFeatureState@@YAJPEA_N@Z; QuickCheckUwfFeatureState(bool *)
0x18000f3b6  test    eax, eax
0x18000f3b8  js      short loc_18000F3C8
0x18000f3ba  cmp     [rbp+57h+arg_0], 1
0x18000f3be  jnz     short loc_18000F3C8
0x18000f3c0  mov     ebx, r14d
0x18000f3c3  jmp     loc_18000F50A
0x18000f3c8  lea     rcx, [rbp+57h+var_70]; this
0x18000f3cc  mov     dil, r14b
0x18000f3cf  mov     sil, r14b
0x18000f3d2  call    ?LoadDismLibrary@CDismHelper@@QEAAJXZ; CDismHelper::LoadDismLibrary(void)
0x18000f3d7  mov     ebx, eax
0x18000f3d9  test    eax, eax
0x18000f3db  js      loc_18000F4D9
0x18000f3e1  mov     rax, [rbp+57h+var_68]
0x18000f3e5  xor     r8d, r8d
0x18000f3e8  xor     edx, edx
0x18000f3ea  xor     ecx, ecx
0x18000f3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3f1  mov     ebx, eax
0x18000f3f3  test    eax, eax
0x18000f3f5  js      loc_18000F4D9
0x18000f3fb  mov     rax, [rbp+57h+var_60]
0x18000f3ff  lea     r9, [rbp+57h+arg_8]
0x18000f403  xor     r8d, r8d
0x18000f406  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x18000f40d  xor     edx, edx
0x18000f40f  mov     dil, 1
0x18000f412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f417  mov     ebx, eax
0x18000f419  test    eax, eax
0x18000f41b  js      loc_18000F4D9
0x18000f421  mov     ecx, [rbp+57h+arg_8]
0x18000f424  lea     rax, [rbp+57h+arg_10]
0x18000f428  mov     [rsp+0D0h+var_B0], rax
0x18000f42d  lea     rdx, aClientUnifiedw; "Client-UnifiedWriteFilter"
0x18000f434  mov     rax, [rbp+57h+var_48]
0x18000f438  xor     r9d, r9d
0x18000f43b  xor     r8d, r8d
0x18000f43e  mov     sil, dil
0x18000f441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f446  mov     ebx, eax
0x18000f448  test    eax, eax
0x18000f44a  js      loc_18000F4D9
0x18000f450  mov     rax, [rbp+57h+arg_10]
0x18000f454  cmp     dword ptr [rax+8], 2
0x18000f458  jnz     short loc_18000F49F
0x18000f45a  mov     ecx, [rbp+57h+arg_8]
0x18000f45d  lea     rdx, aClientUnifiedw; "Client-UnifiedWriteFilter"
0x18000f464  mov     rax, [rbp+57h+var_58]
0x18000f468  xor     r9d, r9d
0x18000f46b  mov     [rsp+0D0h+var_80], r14
0x18000f470  xor     r8d, r8d
0x18000f473  mov     [rsp+0D0h+var_88], r14
0x18000f478  mov     [rsp+0D0h+var_90], r14
0x18000f47d  mov     [rsp+0D0h+var_98], 1
0x18000f485  mov     [rsp+0D0h+var_A0], r14d
0x18000f48a  mov     [rsp+0D0h+var_A8], r14
0x18000f48f  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x18000f494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f499  mov     ebx, eax
0x18000f49b  test    eax, eax
0x18000f49d  js      short loc_18000F4D9
0x18000f49f  mov     ecx, [rbp+57h+arg_8]
0x18000f4a2  lea     rax, [rbp+57h+arg_10]
0x18000f4a6  mov     [rsp+0D0h+var_B0], rax
0x18000f4ab  lea     rdx, aClientUnifiedw; "Client-UnifiedWriteFilter"
0x18000f4b2  mov     rax, [rbp+57h+var_48]
0x18000f4b6  xor     r9d, r9d
0x18000f4b9  xor     r8d, r8d
0x18000f4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4c1  mov     ebx, eax
0x18000f4c3  test    eax, eax
0x18000f4c5  js      short loc_18000F4D9
0x18000f4c7  mov     rcx, [rbp+57h+arg_10]
0x18000f4cb  mov     eax, 8000FFFFh
0x18000f4d0  cmp     dword ptr [rcx+8], 4
0x18000f4d4  cmovnz  ebx, eax
0x18000f4d7  jmp     short loc_18000F4DD
0x18000f4d9  mov     rcx, [rbp+57h+arg_10]
0x18000f4dd  test    rcx, rcx
0x18000f4e0  jz      short loc_18000F4EB
0x18000f4e2  mov     rax, [rbp+57h+var_40]
0x18000f4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4eb  test    sil, sil
0x18000f4ee  jz      short loc_18000F4FC
0x18000f4f0  mov     ecx, [rbp+57h+arg_8]
0x18000f4f3  mov     rax, [rbp+57h+var_38]
0x18000f4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4fc  test    dil, dil
0x18000f4ff  jz      short loc_18000F50A
0x18000f501  mov     rax, [rbp+57h+var_30]
0x18000f505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f50a  lea     rcx, [rbp+57h+var_70]; this
0x18000f50e  call    ??1CDismHelper@@QEAA@XZ; CDismHelper::~CDismHelper(void)
0x18000f513  mov     eax, ebx
0x18000f515  add     rsp, 0B0h
0x18000f51c  pop     r14
0x18000f51e  pop     rdi
0x18000f51f  pop     rsi
0x18000f520  pop     rbx
0x18000f521  pop     rbp
0x18000f522  retn
```
