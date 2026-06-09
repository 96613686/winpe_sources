# CSamPropStore::SetPropertyStorage(tagSERIALIZEDPROPSTORAGE const *,ulong)

- ea: `0x180015440`
- end: `0x180015568`
- name: `?SetPropertyStorage@CSamPropStore@@UEAAJPEFBUtagSERIALIZEDPROPSTORAGE@@K@Z`
- size: `296`
- prototype: `__int64 __fastcall(CSamPropStore *__hidden this, const struct tagSERIALIZEDPROPSTORAGE *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000c240`
- `0x180015440`
- `0x180017010`

## import_xrefs

- `PROPSYS!__imp_PSCreateMemoryPropertyStoreFromSerializedData` at `0x18001548b`
- `PROPSYS!__imp_PSCreateMemoryPropertyStoreFromSerializedData` at `0x18001548b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001552a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001552a`

## pseudocode

```c
__int64 __fastcall CSamPropStore::SetPropertyStorage(
        CSamPropStore *this,
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
         *((unsigned int *)this + 24),
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
0x180015440  mov     [rsp-18h+arg_18], rbx
0x180015445  push    rbp
0x180015446  push    rsi
0x180015447  push    rdi
0x180015448  mov     rbp, rsp
0x18001544b  sub     rsp, 80h
0x180015452  mov     rax, cs:__security_cookie
0x180015459  xor     rax, rsp
0x18001545c  mov     [rbp+var_10], rax
0x180015460  mov     rsi, rcx
0x180015463  mov     [rbp+var_48], 0
0x18001546b  mov     r10d, r8d
0x18001546e  lea     rcx, [rbp+var_48]
0x180015472  mov     rax, rdx
0x180015475  mov     [rsp+80h+var_60], rcx
0x18001547a  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180015481  mov     edx, r10d
0x180015484  mov     r8d, [rsi+60h]
0x180015488  mov     rcx, rax
0x18001548b  call    cs:__imp_PSCreateMemoryPropertyStoreFromSerializedData
0x180015491  mov     edi, eax
0x180015493  test    eax, eax
0x180015495  js      loc_180015547
0x18001549b  mov     rcx, [rbp+var_48]
0x18001549f  lea     rdx, [rbp+var_50]
0x1800154a3  xor     eax, eax
0x1800154a5  xorps   xmm0, xmm0
0x1800154a8  mov     [rbp+var_18], eax
0x1800154ab  mov     [rbp+var_50], eax
0x1800154ae  movups  [rbp+var_28], xmm0
0x1800154b2  mov     rax, [rcx]
0x1800154b5  mov     rax, [rax+18h]
0x1800154b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154be  mov     edi, eax
0x1800154c0  test    eax, eax
0x1800154c2  js      short loc_180015537
0x1800154c4  xor     ebx, ebx
0x1800154c6  cmp     [rbp+var_50], ebx
0x1800154c9  jbe     short loc_180015537
0x1800154cb  mov     rcx, [rbp+var_48]
0x1800154cf  lea     r8, [rbp+var_28]
0x1800154d3  xor     eax, eax
0x1800154d5  xorps   xmm0, xmm0
0x1800154d8  mov     [rbp+var_30], rax
0x1800154dc  mov     edx, ebx
0x1800154de  movups  xmmword ptr [rbp+pvar], xmm0
0x1800154e2  mov     rax, [rcx]
0x1800154e5  mov     rax, [rax+20h]
0x1800154e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ee  test    eax, eax
0x1800154f0  js      short loc_180015530
0x1800154f2  mov     rcx, [rbp+var_48]
0x1800154f6  lea     r8, [rbp+pvar]
0x1800154fa  lea     rdx, [rbp+var_28]
0x1800154fe  mov     rax, [rcx]
0x180015501  mov     rax, [rax+28h]
0x180015505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001550a  test    eax, eax
0x18001550c  js      short loc_180015530
0x18001550e  lea     rcx, [rsi-8]
0x180015512  mov     rax, [rcx]
0x180015515  lea     r8, [rbp+pvar]
0x180015519  lea     rdx, [rbp+var_28]
0x18001551d  mov     rax, [rax+30h]
0x180015521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015526  lea     rcx, [rbp+pvar]; pvar
0x18001552a  call    cs:__imp_PropVariantClear
0x180015530  inc     ebx
0x180015532  cmp     ebx, [rbp+var_50]
0x180015535  jb      short loc_1800154CB
0x180015537  mov     rcx, [rbp+var_48]
0x18001553b  mov     rax, [rcx]
0x18001553e  mov     rax, [rax+10h]
0x180015542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015547  mov     eax, edi
0x180015549  mov     rcx, [rbp+var_10]
0x18001554d  xor     rcx, rsp; StackCookie
0x180015550  call    __security_check_cookie
0x180015555  mov     rbx, [rsp+80h+arg_18]
0x18001555d  add     rsp, 80h
0x180015564  pop     rdi
0x180015565  pop     rsi
0x180015566  pop     rbp
0x180015567  retn
```
