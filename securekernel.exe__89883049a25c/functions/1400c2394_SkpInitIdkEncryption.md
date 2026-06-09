# SkpInitIdkEncryption

- ea: `0x1400c2394`
- end: `0x1400c24fb`
- name: `SkpInitIdkEncryption`
- size: `359`
- prototype: `__int64 __fastcall(__int64, BCRYPT_ALG_HANDLE *, BCRYPT_KEY_HANDLE *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140034988`
- `0x1400b5d60`
- `0x1400b5ef4`
- `0x1400b63ac`
- `0x1400c3b48`
- `0x1400c4228`

## callees

- `0x14000f0f0`
- `0x14001d804`
- `0x140037e68`
- `0x1400c2394`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400c242c`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c242c`
- `cng!BCryptImportKeyPair` at `0x1400c246b`
- `cng!BCryptImportKeyPair` at `0x1400c246b`
- `cng!BCryptDestroyKey` at `0x1400c24b6`
- `cng!BCryptDestroyKey` at `0x1400c24b6`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c24cc`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c24cc`

## pseudocode

```c
__int64 __fastcall SkpInitIdkEncryption(__int64 a1, BCRYPT_ALG_HANDLE *a2, BCRYPT_KEY_HANDLE *a3)
{
  __int64 Pool; // rax
  __int64 v7; // rdi
  NTSTATUS v8; // ebx
  char v9; // si
  bool v10; // r12
  int v11; // eax
  __int64 v12; // rbp
  __int64 v13; // rdx
  _BYTE *v14; // rax
  unsigned int v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = 1024;
  if ( a2 && a3 )
  {
    Pool = SkAllocatePool(512, 0x400u);
    v7 = Pool;
    if ( Pool )
    {
      v9 = 0;
      v10 = 0;
      v11 = SkKSGetKey(a1, Pool, &v16);
      v12 = v16;
      v8 = v11;
      if ( v11 >= 0 )
      {
        if ( v16 < 0x29 || v16 < *(_DWORD *)v7 )
        {
          v8 = -1073741595;
        }
        else
        {
          v8 = BCryptOpenAlgorithmProvider(a2, L"RSA", 0, 1u);
          if ( v8 >= 0 )
          {
            v9 = 1;
            v8 = BCryptImportKeyPair(*a2, 0, L"RSAPRIVATEBLOB", a3, (PUCHAR)(v7 + 16), *(_DWORD *)(v7 + 8) - 8, 0);
            v10 = v8 >= 0;
          }
        }
      }
      v13 = v12;
      v14 = (_BYTE *)v7;
      if ( (_DWORD)v12 )
      {
        do
        {
          *v14++ = 0;
          --v13;
        }
        while ( v13 );
      }
      SkFreePool(512, v7);
      if ( v8 < 0 )
      {
        if ( v10 )
          BCryptDestroyKey(*a3);
        if ( v9 )
          BCryptCloseAlgorithmProvider(*a2, 0);
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400c2394  mov     [rsp+arg_0], rbx
0x1400c2399  mov     [rsp+arg_10], rbp
0x1400c239e  push    rsi
0x1400c239f  push    rdi
0x1400c23a0  push    r12
0x1400c23a2  push    r14
0x1400c23a4  push    r15
0x1400c23a6  sub     rsp, 40h
0x1400c23aa  mov     r14, rdx
0x1400c23ad  mov     r15, r8
0x1400c23b0  mov     edx, 400h
0x1400c23b5  mov     rbx, rcx
0x1400c23b8  mov     [rsp+68h+arg_8], edx
0x1400c23bc  test    r14, r14
0x1400c23bf  jz      loc_1400C24DA
0x1400c23c5  test    r8, r8
0x1400c23c8  jz      loc_1400C24DA
0x1400c23ce  mov     ecx, 200h
0x1400c23d3  mov     r8d, 57474E43h
0x1400c23d9  call    SkAllocatePool
0x1400c23de  mov     rdi, rax
0x1400c23e1  test    rax, rax
0x1400c23e4  jnz     short loc_1400C23F0
0x1400c23e6  mov     ebx, 0C000009Ah
0x1400c23eb  jmp     loc_1400C24DF
0x1400c23f0  lea     r8, [rsp+68h+arg_8]
0x1400c23f5  mov     rdx, rdi
0x1400c23f8  mov     rcx, rbx
0x1400c23fb  xor     sil, sil
0x1400c23fe  xor     r12b, r12b
0x1400c2401  call    SkKSGetKey
0x1400c2406  mov     ebp, [rsp+68h+arg_8]
0x1400c240a  mov     ebx, eax
0x1400c240c  test    eax, eax
0x1400c240e  js      short loc_1400C2487
0x1400c2410  cmp     ebp, 29h ; ')'
0x1400c2413  jb      short loc_1400C2482
0x1400c2415  cmp     ebp, [rdi]
0x1400c2417  jb      short loc_1400C2482
0x1400c2419  mov     r9d, 1; dwFlags
0x1400c241f  lea     rdx, aRsa; "RSA"
0x1400c2426  xor     r8d, r8d; pszImplementation
0x1400c2429  mov     rcx, r14; phAlgorithm
0x1400c242c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400c2433  nop     dword ptr [rax+rax+00h]
0x1400c2438  mov     ebx, eax
0x1400c243a  test    eax, eax
0x1400c243c  js      short loc_1400C2487
0x1400c243e  mov     ecx, [rdi+8]
0x1400c2441  lea     rax, [rdi+10h]
0x1400c2445  sub     ecx, 8
0x1400c2448  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1400c2450  mov     [rsp+68h+cbInput], ecx; cbInput
0x1400c2454  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x1400c245b  mov     rcx, [r14]; hAlgorithm
0x1400c245e  mov     r9, r15; phKey
0x1400c2461  xor     edx, edx; hImportKey
0x1400c2463  mov     [rsp+68h+pbInput], rax; pbInput
0x1400c2468  mov     sil, 1
0x1400c246b  call    cs:__imp_BCryptImportKeyPair
0x1400c2472  nop     dword ptr [rax+rax+00h]
0x1400c2477  mov     ebx, eax
0x1400c2479  test    eax, eax
0x1400c247b  js      short loc_1400C2487
0x1400c247d  mov     r12b, sil
0x1400c2480  jmp     short loc_1400C2487
0x1400c2482  mov     ebx, 0C00000E5h
0x1400c2487  mov     rdx, rbp
0x1400c248a  mov     rax, rdi
0x1400c248d  test    ebp, ebp
0x1400c248f  jz      short loc_1400C249D
0x1400c2491  mov     byte ptr [rax], 0
0x1400c2494  inc     rax
0x1400c2497  sub     rdx, 1
0x1400c249b  jnz     short loc_1400C2491
0x1400c249d  mov     rdx, rdi
0x1400c24a0  mov     ecx, 200h
0x1400c24a5  call    SkFreePool
0x1400c24aa  test    ebx, ebx
0x1400c24ac  jns     short loc_1400C24DF
0x1400c24ae  test    r12b, r12b
0x1400c24b1  jz      short loc_1400C24C2
0x1400c24b3  mov     rcx, [r15]; hKey
0x1400c24b6  call    cs:__imp_BCryptDestroyKey
0x1400c24bd  nop     dword ptr [rax+rax+00h]
0x1400c24c2  test    sil, sil
0x1400c24c5  jz      short loc_1400C24DF
0x1400c24c7  mov     rcx, [r14]; hAlgorithm
0x1400c24ca  xor     edx, edx; dwFlags
0x1400c24cc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c24d3  nop     dword ptr [rax+rax+00h]
0x1400c24d8  jmp     short loc_1400C24DF
0x1400c24da  mov     ebx, 0C000000Dh
0x1400c24df  lea     r11, [rsp+68h+var_28]
0x1400c24e4  mov     eax, ebx
0x1400c24e6  mov     rbx, [r11+30h]
0x1400c24ea  mov     rbp, [r11+40h]
0x1400c24ee  mov     rsp, r11
0x1400c24f1  pop     r15
0x1400c24f3  pop     r14
0x1400c24f5  pop     r12
0x1400c24f7  pop     rdi
0x1400c24f8  pop     rsi
0x1400c24f9  retn
```
