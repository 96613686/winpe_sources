# GetLongProfilePathNameInternal(ushort const *,ushort * *,unsigned __int64 *)

- ea: `0x180009cb8`
- end: `0x180009dd0`
- name: `?GetLongProfilePathNameInternal@@YAJPEBGPEAPEAGPEA_K@Z`
- size: `280`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b2d0`
- `0x180014650`
- `0x180018ff4`
- `0x180019748`

## callees

- `0x180003f60`
- `0x180003fe0`
- `0x180006308`
- `0x180006378`
- `0x180009cb8`
- `0x18000cea0`
- `0x180019290`

## string_xrefs

- `0x180009cdf`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180009dae`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall GetLongProfilePathNameInternal(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int64 *a3)
{
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  unsigned __int16 *v11; // rax
  unsigned __int16 *v13; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-18h]
  __int64 v15; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  *a2 = 0;
  *a3 = 0;
  if ( *a1 )
  {
    v13 = 0;
    v14 = 0;
    v15 = 0;
    if ( (unsigned int)IsLocalFullPath(a1) )
    {
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             &v13,
             L"%s%s",
             L"\\\\?\\",
             v6);
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 3142;
LABEL_9:
        v10 = (unsigned int)v7;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          (const char *)v10,
          (int)v13);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v13);
        return v5;
      }
    }
    else
    {
      if ( !(unsigned int)IsUNCPath(v6) )
      {
        v5 = -2147024809;
        v8 = 3152;
        v10 = 2147942487LL;
        goto LABEL_12;
      }
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             &v13,
             L"%s%s",
             L"\\\\?\\UNC\\",
             v9 + 4);
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 3148;
        goto LABEL_9;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCount(&v13);
    v11 = v13;
    *a3 = v14;
    v13 = 0;
    v15 = 0;
    v14 = 0;
    *a2 = v11;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v13);
    return 0;
  }
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC40,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)0x80070057LL,
    (int)v13);
  return v5;
}

```

## disassembly

```asm
0x180009cb8  push    rbp
0x180009cba  push    rbx
0x180009cbb  push    rsi
0x180009cbc  push    rdi
0x180009cbd  push    r14
0x180009cbf  mov     rbp, rsp
0x180009cc2  sub     rsp, 40h
0x180009cc6  xor     r14d, r14d
0x180009cc9  mov     rdi, r8
0x180009ccc  mov     [rdx], r14
0x180009ccf  mov     rsi, rdx
0x180009cd2  mov     [r8], r14
0x180009cd5  cmp     [rcx], r14w
0x180009cd9  jnz     short loc_180009CFD
0x180009cdb  mov     rcx, [rbp+28h]; this
0x180009cdf  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180009ce6  mov     ebx, 80070057h
0x180009ceb  mov     edx, 0C40h; void *
0x180009cf0  mov     r9d, ebx; char *
0x180009cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cf8  jmp     loc_180009DC3
0x180009cfd  mov     [rbp+var_20], r14
0x180009d01  mov     [rbp+var_18], r14
0x180009d05  mov     [rbp+var_10], r14
0x180009d09  call    ?IsLocalFullPath@@YAHPEBG@Z; IsLocalFullPath(ushort const *)
0x180009d0e  test    eax, eax
0x180009d10  jz      short loc_180009D39
0x180009d12  mov     r9, rcx
0x180009d15  lea     r8, asc_18001FC38; "\\\\?\\"
0x180009d1c  lea     rcx, [rbp+var_20]
0x180009d20  lea     rdx, aSS_0; "%s%s"
0x180009d27  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180009d2c  mov     ebx, eax
0x180009d2e  test    eax, eax
0x180009d30  jns     short loc_180009D6D
0x180009d32  mov     edx, 0C46h
0x180009d37  jmp     short loc_180009D68
0x180009d39  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x180009d3e  test    eax, eax
0x180009d40  jz      short loc_180009D9D
0x180009d42  lea     r9, [rcx+4]
0x180009d46  lea     rcx, [rbp+var_20]
0x180009d4a  lea     r8, aUnc; "\\\\?\\UNC\\"
0x180009d51  lea     rdx, aSS_0; "%s%s"
0x180009d58  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180009d5d  mov     ebx, eax
0x180009d5f  test    eax, eax
0x180009d61  jns     short loc_180009D6D
0x180009d63  mov     edx, 0C4Ch
0x180009d68  mov     r9d, eax
0x180009d6b  jmp     short loc_180009DAA
0x180009d6d  lea     rcx, [rbp+var_20]
0x180009d71  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x180009d76  mov     rcx, [rbp+var_18]
0x180009d7a  mov     rax, [rbp+var_20]
0x180009d7e  mov     [rdi], rcx
0x180009d81  lea     rcx, [rbp+var_20]
0x180009d85  mov     [rbp+var_20], r14
0x180009d89  mov     [rbp+var_10], r14
0x180009d8d  mov     [rbp+var_18], r14
0x180009d91  mov     [rsi], rax
0x180009d94  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009d99  xor     eax, eax
0x180009d9b  jmp     short loc_180009DC5
0x180009d9d  mov     ebx, 80070057h
0x180009da2  mov     edx, 0C50h; void *
0x180009da7  mov     r9d, ebx; char *
0x180009daa  mov     rcx, [rbp+28h]; this
0x180009dae  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180009db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dba  lea     rcx, [rbp+var_20]
0x180009dbe  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009dc3  mov     eax, ebx
0x180009dc5  add     rsp, 40h
0x180009dc9  pop     r14
0x180009dcb  pop     rdi
0x180009dcc  pop     rsi
0x180009dcd  pop     rbx
0x180009dce  pop     rbp
0x180009dcf  retn
```
