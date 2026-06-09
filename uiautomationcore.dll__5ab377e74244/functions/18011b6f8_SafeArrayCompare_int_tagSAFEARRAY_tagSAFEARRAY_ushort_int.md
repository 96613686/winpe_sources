# SafeArrayCompare<int>(tagSAFEARRAY *,tagSAFEARRAY *,ushort,int *)

- ea: `0x18011b6f8`
- end: `0x18011b7df`
- name: `??$SafeArrayCompare@H@@YAJPEAUtagSAFEARRAY@@0GPEAH@Z`
- size: `231`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016a80`
- `0x18004a618`
- `0x1800b725c`
- `0x18011b350`
- `0x180138e1c`
- `0x18016a568`
- `0x180273f78`

## callees

- `0x18011b6f8`
- `0x18011b7e8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b746`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b757`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b799`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b7aa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b7be`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b7cf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b746`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b757`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b799`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b7aa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b7be`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011b7cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SafeArrayCompare<int>(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rdx
  SAFEARRAY *psa; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h]
  __int64 v11; // [rsp+30h] [rbp-28h]
  SAFEARRAY *v12; // [rsp+38h] [rbp-20h]
  __int64 v13; // [rsp+40h] [rbp-18h]
  const char *v14; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a4 = 0;
  try
  {
    ((void (*)(void))SafeArrayAccessor<int>::SafeArrayAccessor<int>)();
    SafeArrayAccessor<int>::SafeArrayAccessor<int>(&psa, a2);
    if ( (_DWORD)v13 == v10 )
    {
      v8 = 0;
      v6 = v14;
      while ( (unsigned int)v8 < (unsigned int)v13 )
      {
        if ( *(_DWORD *)&v14[4 * v8] != *(_DWORD *)(v11 + 4 * v8) )
        {
          if ( psa )
            SafeArrayUnaccessData(psa);
          if ( v12 )
            SafeArrayUnaccessData(v12);
          return 0;
        }
        v8 = (unsigned int)(v8 + 1);
      }
      *a4 = 1;
      if ( psa )
        SafeArrayUnaccessData(psa);
      if ( v12 )
        SafeArrayUnaccessData(v12);
      result = 0;
    }
    else
    {
      if ( psa )
        SafeArrayUnaccessData(psa);
      if ( v12 )
        SafeArrayUnaccessData(v12);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x15C,
                           (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18011b6f8  mov     [rsp+arg_0], rbx
0x18011b6fd  mov     word ptr [rsp+arg_10], r8w
0x18011b703  push    rdi
0x18011b704  sub     rsp, 50h
0x18011b708  mov     rbx, r9
0x18011b70b  mov     rdi, rdx
0x18011b70e  mov     dword ptr [r9], 0
0x18011b715  mov     rdx, rcx
0x18011b718  lea     rcx, [rsp+58h+var_20]
0x18011b71d  call    ??0?$SafeArrayAccessor@H@@QEAA@PEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<int>::SafeArrayAccessor<int>(tagSAFEARRAY *,ushort)
0x18011b722  nop
0x18011b723  mov     rdx, rdi
0x18011b726  lea     rcx, [rsp+58h+psa]
0x18011b72b  call    ??0?$SafeArrayAccessor@H@@QEAA@PEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<int>::SafeArrayAccessor<int>(tagSAFEARRAY *,ushort)
0x18011b730  mov     r8, [rsp+58h+var_18]
0x18011b735  cmp     r8d, [rsp+58h+var_30]
0x18011b73a  jz      short loc_18011B76A
0x18011b73c  mov     rcx, [rsp+58h+psa]; psa
0x18011b741  test    rcx, rcx
0x18011b744  jz      short loc_18011B74D
0x18011b746  call    cs:__imp_SafeArrayUnaccessData
0x18011b74c  nop
0x18011b74d  mov     rcx, [rsp+58h+var_20]; psa
0x18011b752  test    rcx, rcx
0x18011b755  jz      short loc_18011B75D
0x18011b757  call    cs:__imp_SafeArrayUnaccessData
0x18011b75d  xor     eax, eax
0x18011b75f  mov     rbx, [rsp+58h+arg_0]
0x18011b764  add     rsp, 50h
0x18011b768  pop     rdi
0x18011b769  retn
0x18011b76a  xor     edx, edx
0x18011b76c  mov     r9, [rsp+58h+var_10]
0x18011b771  mov     r10, [rsp+58h+var_28]
0x18011b776  cmp     edx, r8d
0x18011b779  jnb     short loc_18011B789
0x18011b77b  mov     eax, [r10+rdx*4]
0x18011b77f  cmp     [r9+rdx*4], eax
0x18011b783  jnz     short loc_18011B7B4
0x18011b785  inc     edx
0x18011b787  jmp     short loc_18011B776
0x18011b789  mov     dword ptr [rbx], 1
0x18011b78f  mov     rcx, [rsp+58h+psa]; psa
0x18011b794  test    rcx, rcx
0x18011b797  jz      short loc_18011B7A0
0x18011b799  call    cs:__imp_SafeArrayUnaccessData
0x18011b79f  nop
0x18011b7a0  mov     rcx, [rsp+58h+var_20]; psa
0x18011b7a5  test    rcx, rcx
0x18011b7a8  jz      short loc_18011B7B0
0x18011b7aa  call    cs:__imp_SafeArrayUnaccessData
0x18011b7b0  xor     eax, eax
0x18011b7b2  jmp     short loc_18011B75F
0x18011b7b4  mov     rcx, [rsp+58h+psa]; psa
0x18011b7b9  test    rcx, rcx
0x18011b7bc  jz      short loc_18011B7C5
0x18011b7be  call    cs:__imp_SafeArrayUnaccessData
0x18011b7c4  nop
0x18011b7c5  mov     rcx, [rsp+58h+var_20]; psa
0x18011b7ca  test    rcx, rcx
0x18011b7cd  jz      short loc_18011B7D5
0x18011b7cf  call    cs:__imp_SafeArrayUnaccessData
0x18011b7d5  xor     eax, eax
0x18011b7d7  jmp     short loc_18011B75F
0x18011b7d9  mov     eax, [rsp+58h+arg_10]
0x18011b7dd  jmp     short loc_18011B75F
```
