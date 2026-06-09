# CLoggedOnPropStore::SetPropertyStorage(tagSERIALIZEDPROPSTORAGE const *,ulong)

- ea: `0x180013cb0`
- end: `0x180013dd8`
- name: `?SetPropertyStorage@CLoggedOnPropStore@@UEAAJPEFBUtagSERIALIZEDPROPSTORAGE@@K@Z`
- size: `296`
- prototype: `__int64 __fastcall(CLoggedOnPropStore *__hidden this, const struct tagSERIALIZEDPROPSTORAGE *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000c240`
- `0x180013cb0`
- `0x180017010`

## import_xrefs

- `PROPSYS!__imp_PSCreateMemoryPropertyStoreFromSerializedData` at `0x180013cfb`
- `PROPSYS!__imp_PSCreateMemoryPropertyStoreFromSerializedData` at `0x180013cfb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013d9a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013d9a`

## pseudocode

```c
__int64 __fastcall CLoggedOnPropStore::SetPropertyStorage(
        CLoggedOnPropStore *this,
        const struct tagSERIALIZEDPROPSTORAGE *a2,
        unsigned int a3)
{
  int v4; // edi
  unsigned int i; // ebx
  unsigned int v7; // [rsp+30h] [rbp-50h] BYREF
  __int64 v8; // [rsp+38h] [rbp-48h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+50h] [rbp-30h]
  __int128 v11; // [rsp+58h] [rbp-28h] BYREF
  int v12; // [rsp+68h] [rbp-18h]

  v8 = 0;
  v4 = PSCreateMemoryPropertyStoreFromSerializedData(
         a2,
         a3,
         *((unsigned int *)this + 13),
         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
         &v8);
  if ( v4 >= 0 )
  {
    v12 = 0;
    v7 = 0;
    v11 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 24LL))(v8, &v7);
    if ( v4 >= 0 )
    {
      for ( i = 0; i < v7; ++i )
      {
        v10 = 0;
        *(_OWORD *)pvar = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v8 + 32LL))(v8, i, &v11) >= 0
          && (*(int (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v8 + 40LL))(v8, &v11, pvar) >= 0 )
        {
          (*(void (__fastcall **)(char *, __int128 *, PROPVARIANT *))(*((_QWORD *)this - 1) + 48LL))(
            (char *)this - 8,
            &v11,
            pvar);
          PropVariantClear(pvar);
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013cb0  mov     [rsp-18h+arg_18], rbx
0x180013cb5  push    rbp
0x180013cb6  push    rsi
0x180013cb7  push    rdi
0x180013cb8  mov     rbp, rsp
0x180013cbb  sub     rsp, 80h
0x180013cc2  mov     rax, cs:__security_cookie
0x180013cc9  xor     rax, rsp
0x180013ccc  mov     [rbp+var_10], rax
0x180013cd0  mov     rsi, rcx
0x180013cd3  mov     [rbp+var_48], 0
0x180013cdb  mov     r10d, r8d
0x180013cde  lea     rcx, [rbp+var_48]
0x180013ce2  mov     rax, rdx
0x180013ce5  mov     [rsp+80h+var_60], rcx
0x180013cea  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180013cf1  mov     edx, r10d
0x180013cf4  mov     r8d, [rsi+34h]
0x180013cf8  mov     rcx, rax
0x180013cfb  call    cs:__imp_PSCreateMemoryPropertyStoreFromSerializedData
0x180013d01  mov     edi, eax
0x180013d03  test    eax, eax
0x180013d05  js      loc_180013DB7
0x180013d0b  mov     rcx, [rbp+var_48]
0x180013d0f  lea     rdx, [rbp+var_50]
0x180013d13  xor     eax, eax
0x180013d15  xorps   xmm0, xmm0
0x180013d18  mov     [rbp+var_18], eax
0x180013d1b  mov     [rbp+var_50], eax
0x180013d1e  movups  [rbp+var_28], xmm0
0x180013d22  mov     rax, [rcx]
0x180013d25  mov     rax, [rax+18h]
0x180013d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d2e  mov     edi, eax
0x180013d30  test    eax, eax
0x180013d32  js      short loc_180013DA7
0x180013d34  xor     ebx, ebx
0x180013d36  cmp     [rbp+var_50], ebx
0x180013d39  jbe     short loc_180013DA7
0x180013d3b  mov     rcx, [rbp+var_48]
0x180013d3f  lea     r8, [rbp+var_28]
0x180013d43  xor     eax, eax
0x180013d45  xorps   xmm0, xmm0
0x180013d48  mov     [rbp+var_30], rax
0x180013d4c  mov     edx, ebx
0x180013d4e  movups  xmmword ptr [rbp+pvar], xmm0
0x180013d52  mov     rax, [rcx]
0x180013d55  mov     rax, [rax+20h]
0x180013d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d5e  test    eax, eax
0x180013d60  js      short loc_180013DA0
0x180013d62  mov     rcx, [rbp+var_48]
0x180013d66  lea     r8, [rbp+pvar]
0x180013d6a  lea     rdx, [rbp+var_28]
0x180013d6e  mov     rax, [rcx]
0x180013d71  mov     rax, [rax+28h]
0x180013d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d7a  test    eax, eax
0x180013d7c  js      short loc_180013DA0
0x180013d7e  lea     rcx, [rsi-8]
0x180013d82  mov     rax, [rcx]
0x180013d85  lea     r8, [rbp+pvar]
0x180013d89  lea     rdx, [rbp+var_28]
0x180013d8d  mov     rax, [rax+30h]
0x180013d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d96  lea     rcx, [rbp+pvar]; pvar
0x180013d9a  call    cs:__imp_PropVariantClear
0x180013da0  inc     ebx
0x180013da2  cmp     ebx, [rbp+var_50]
0x180013da5  jb      short loc_180013D3B
0x180013da7  mov     rcx, [rbp+var_48]
0x180013dab  mov     rax, [rcx]
0x180013dae  mov     rax, [rax+10h]
0x180013db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db7  mov     eax, edi
0x180013db9  mov     rcx, [rbp+var_10]
0x180013dbd  xor     rcx, rsp; StackCookie
0x180013dc0  call    __security_check_cookie
0x180013dc5  mov     rbx, [rsp+80h+arg_18]
0x180013dcd  add     rsp, 80h
0x180013dd4  pop     rdi
0x180013dd5  pop     rsi
0x180013dd6  pop     rbp
0x180013dd7  retn
```
