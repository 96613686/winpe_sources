# CSamPropStore::GetPropertyStorage(tagSERIALIZEDPROPSTORAGE * *,ulong *)

- ea: `0x18000e220`
- end: `0x18000e39a`
- name: `?GetPropertyStorage@CSamPropStore@@UEAAJPEAPEAUtagSERIALIZEDPROPSTORAGE@@PEAK@Z`
- size: `378`
- prototype: `__int64 __fastcall(CSamPropStore *__hidden this, struct tagSERIALIZEDPROPSTORAGE **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000c240`
- `0x18000e220`
- `0x180017010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e25f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e25f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e2fd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e2fd`

## pseudocode

```c
__int64 __fastcall CSamPropStore::GetPropertyStorage(
        CSamPropStore *this,
        struct tagSERIALIZEDPROPSTORAGE **a2,
        unsigned int *a3)
{
  HRESULT v6; // ebx
  char *v7; // rdi
  unsigned int i; // ebx
  __int64 v9; // rax
  unsigned int v11; // [rsp+20h] [rbp-50h] BYREF
  void *ppv; // [rsp+28h] [rbp-48h] BYREF
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+48h] [rbp-28h]
  __int128 v16; // [rsp+50h] [rbp-20h] BYREF
  int v17; // [rsp+60h] [rbp-10h]

  *a2 = 0;
  ppv = 0;
  v6 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v6 >= 0 )
  {
    v17 = 0;
    v7 = (char *)this - 8;
    v11 = 0;
    v16 = 0;
    if ( (*(int (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v7 + 24LL))(v7, &v11) >= 0 )
    {
      for ( i = 0; i < v11; ++i )
      {
        v15 = 0;
        v9 = *(_QWORD *)v7;
        *(_OWORD *)pvar = 0;
        if ( (*(int (__fastcall **)(char *, _QWORD, __int128 *))(v9 + 32))(v7, i, &v16) >= 0
          && (*(int (__fastcall **)(char *, __int128 *, PROPVARIANT *))(*(_QWORD *)v7 + 40LL))(v7, &v16, pvar) >= 0 )
        {
          (*(void (__fastcall **)(void *, __int128 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(ppv, &v16, pvar);
          PropVariantClear(pvar);
        }
      }
    }
    v6 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppv + 24LL))(ppv, &v11);
    if ( v6 >= 0 )
    {
      if ( v11 )
      {
        v13 = 0;
        v6 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
               &v13);
        if ( v6 >= 0 )
          v6 = (*(__int64 (__fastcall **)(__int64, struct tagSERIALIZEDPROPSTORAGE **, unsigned int *))(*(_QWORD *)v13 + 40LL))(
                 v13,
                 a2,
                 a3);
      }
      else
      {
        v6 = -2147467259;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e220  push    rbp
0x18000e222  push    rbx
0x18000e223  push    rsi
0x18000e224  push    rdi
0x18000e225  push    r14
0x18000e227  mov     rbp, rsp
0x18000e22a  sub     rsp, 70h
0x18000e22e  mov     rax, cs:__security_cookie
0x18000e235  xor     rax, rsp
0x18000e238  mov     [rbp+var_8], rax
0x18000e23c  mov     rsi, rdx
0x18000e23f  mov     qword ptr [rdx], 0
0x18000e246  mov     rdi, rcx
0x18000e249  mov     [rbp+ppv], 0
0x18000e251  lea     rdx, [rbp+ppv]; ppv
0x18000e255  mov     r14, r8
0x18000e258  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000e25f  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000e265  mov     ebx, eax
0x18000e267  test    eax, eax
0x18000e269  js      loc_18000E381
0x18000e26f  xor     eax, eax
0x18000e271  lea     rdx, [rbp+var_50]
0x18000e275  mov     [rbp+var_10], eax
0x18000e278  add     rdi, 0FFFFFFFFFFFFFFF8h
0x18000e27c  mov     [rbp+var_50], eax
0x18000e27f  xorps   xmm0, xmm0
0x18000e282  mov     rcx, rdi
0x18000e285  movups  [rbp+var_20], xmm0
0x18000e289  mov     rax, [rdi]
0x18000e28c  mov     rax, [rax+18h]
0x18000e290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e295  test    eax, eax
0x18000e297  js      short loc_18000E30A
0x18000e299  xor     ebx, ebx
0x18000e29b  cmp     [rbp+var_50], ebx
0x18000e29e  jbe     short loc_18000E30A
0x18000e2a0  xor     eax, eax
0x18000e2a2  lea     r8, [rbp+var_20]
0x18000e2a6  mov     [rbp+var_28], rax
0x18000e2aa  xorps   xmm0, xmm0
0x18000e2ad  mov     rax, [rdi]
0x18000e2b0  mov     edx, ebx
0x18000e2b2  mov     rcx, rdi
0x18000e2b5  movups  xmmword ptr [rbp+pvar], xmm0
0x18000e2b9  mov     rax, [rax+20h]
0x18000e2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2c2  test    eax, eax
0x18000e2c4  js      short loc_18000E303
0x18000e2c6  mov     rax, [rdi]
0x18000e2c9  lea     r8, [rbp+pvar]
0x18000e2cd  lea     rdx, [rbp+var_20]
0x18000e2d1  mov     rcx, rdi
0x18000e2d4  mov     rax, [rax+28h]
0x18000e2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2dd  test    eax, eax
0x18000e2df  js      short loc_18000E303
0x18000e2e1  mov     rcx, [rbp+ppv]
0x18000e2e5  lea     r8, [rbp+pvar]
0x18000e2e9  lea     rdx, [rbp+var_20]
0x18000e2ed  mov     rax, [rcx]
0x18000e2f0  mov     rax, [rax+30h]
0x18000e2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2f9  lea     rcx, [rbp+pvar]; pvar
0x18000e2fd  call    cs:__imp_PropVariantClear
0x18000e303  inc     ebx
0x18000e305  cmp     ebx, [rbp+var_50]
0x18000e308  jb      short loc_18000E2A0
0x18000e30a  mov     rcx, [rbp+ppv]
0x18000e30e  lea     rdx, [rbp+var_50]
0x18000e312  mov     rax, [rcx]
0x18000e315  mov     rax, [rax+18h]
0x18000e319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e31e  mov     ebx, eax
0x18000e320  test    eax, eax
0x18000e322  js      short loc_18000E371
0x18000e324  cmp     [rbp+var_50], 0
0x18000e328  jz      short loc_18000E36C
0x18000e32a  mov     rcx, [rbp+ppv]
0x18000e32e  lea     r8, [rbp+var_40]
0x18000e332  mov     [rbp+var_40], 0
0x18000e33a  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x18000e341  mov     rax, [rcx]
0x18000e344  mov     rax, [rax]
0x18000e347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e34c  mov     ebx, eax
0x18000e34e  test    eax, eax
0x18000e350  js      short loc_18000E371
0x18000e352  mov     rcx, [rbp+var_40]
0x18000e356  mov     r8, r14
0x18000e359  mov     rdx, rsi
0x18000e35c  mov     rax, [rcx]
0x18000e35f  mov     rax, [rax+28h]
0x18000e363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e368  mov     ebx, eax
0x18000e36a  jmp     short loc_18000E371
0x18000e36c  mov     ebx, 80004005h
0x18000e371  mov     rcx, [rbp+ppv]
0x18000e375  mov     rax, [rcx]
0x18000e378  mov     rax, [rax+10h]
0x18000e37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e381  mov     eax, ebx
0x18000e383  mov     rcx, [rbp+var_8]
0x18000e387  xor     rcx, rsp; StackCookie
0x18000e38a  call    __security_check_cookie
0x18000e38f  add     rsp, 70h
0x18000e393  pop     r14
0x18000e395  pop     rdi
0x18000e396  pop     rsi
0x18000e397  pop     rbx
0x18000e398  pop     rbp
0x18000e399  retn
```
