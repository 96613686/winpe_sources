# GetLongProfilePathNameInternal(ushort const *,ushort * *,unsigned __int64 *)

- ea: `0x18000a638`
- end: `0x18000a751`
- name: `?GetLongProfilePathNameInternal@@YAJPEBGPEAPEAGPEA_K@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bd3c`
- `0x180015800`
- `0x18001aa00`
- `0x18001b220`

## callees

- `0x1800040b0`
- `0x1800043c0`
- `0x1800068f8`
- `0x180006968`
- `0x18000a638`
- `0x18000db08`
- `0x18001ad58`

## string_xrefs

- `0x18000a65f`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000a72e`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
  __int64 v9; // r9
  unsigned __int16 *v10; // rax
  unsigned __int16 *v12; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int64 v13; // [rsp+28h] [rbp-18h]
  __int64 v14; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  *a2 = 0;
  *a3 = 0;
  if ( *a1 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    if ( (unsigned int)IsLocalFullPath(a1) )
    {
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             &v12,
             L"%s%s",
             L"\\\\?\\");
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 3146;
LABEL_9:
        v9 = (unsigned int)v7;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          (const char *)v9,
          (int)v12);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v12);
        return v5;
      }
    }
    else
    {
      if ( !(unsigned int)IsUNCPath(v6) )
      {
        v5 = -2147024809;
        v8 = 3156;
        v9 = 2147942487LL;
        goto LABEL_12;
      }
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             &v12,
             L"%s%s",
             L"\\\\?\\UNC\\");
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 3152;
        goto LABEL_9;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCount(&v12);
    v10 = v12;
    *a3 = v13;
    v12 = 0;
    v14 = 0;
    v13 = 0;
    *a2 = v10;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v12);
    return 0;
  }
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC44,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)0x80070057LL,
    (int)v12);
  return v5;
}

```

## disassembly

```asm
0x18000a638  push    rbp
0x18000a63a  push    rbx
0x18000a63b  push    rsi
0x18000a63c  push    rdi
0x18000a63d  push    r14
0x18000a63f  mov     rbp, rsp
0x18000a642  sub     rsp, 40h
0x18000a646  xor     r14d, r14d
0x18000a649  mov     rdi, r8
0x18000a64c  mov     [rdx], r14
0x18000a64f  mov     rsi, rdx
0x18000a652  mov     [r8], r14
0x18000a655  cmp     [rcx], r14w
0x18000a659  jnz     short loc_18000A67D
0x18000a65b  mov     rcx, [rbp+28h]; this
0x18000a65f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a666  mov     ebx, 80070057h
0x18000a66b  mov     edx, 0C44h; void *
0x18000a670  mov     r9d, ebx; char *
0x18000a673  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a678  jmp     loc_18000A743
0x18000a67d  mov     [rbp+var_20], r14
0x18000a681  mov     [rbp+var_18], r14
0x18000a685  mov     [rbp+var_10], r14
0x18000a689  call    ?IsLocalFullPath@@YAHPEBG@Z; IsLocalFullPath(ushort const *)
0x18000a68e  test    eax, eax
0x18000a690  jz      short loc_18000A6B9
0x18000a692  mov     r9, rcx
0x18000a695  lea     r8, asc_180020C48; "\\\\?\\"
0x18000a69c  lea     rcx, [rbp+var_20]
0x18000a6a0  lea     rdx, aSS_0; "%s%s"
0x18000a6a7  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000a6ac  mov     ebx, eax
0x18000a6ae  test    eax, eax
0x18000a6b0  jns     short loc_18000A6ED
0x18000a6b2  mov     edx, 0C4Ah
0x18000a6b7  jmp     short loc_18000A6E8
0x18000a6b9  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x18000a6be  test    eax, eax
0x18000a6c0  jz      short loc_18000A71D
0x18000a6c2  lea     r9, [rcx+4]
0x18000a6c6  lea     rcx, [rbp+var_20]
0x18000a6ca  lea     r8, aUnc; "\\\\?\\UNC\\"
0x18000a6d1  lea     rdx, aSS_0; "%s%s"
0x18000a6d8  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000a6dd  mov     ebx, eax
0x18000a6df  test    eax, eax
0x18000a6e1  jns     short loc_18000A6ED
0x18000a6e3  mov     edx, 0C50h
0x18000a6e8  mov     r9d, eax
0x18000a6eb  jmp     short loc_18000A72A
0x18000a6ed  lea     rcx, [rbp+var_20]
0x18000a6f1  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x18000a6f6  mov     rcx, [rbp+var_18]
0x18000a6fa  mov     rax, [rbp+var_20]
0x18000a6fe  mov     [rdi], rcx
0x18000a701  lea     rcx, [rbp+var_20]
0x18000a705  mov     [rbp+var_20], r14
0x18000a709  mov     [rbp+var_10], r14
0x18000a70d  mov     [rbp+var_18], r14
0x18000a711  mov     [rsi], rax
0x18000a714  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000a719  xor     eax, eax
0x18000a71b  jmp     short loc_18000A745
0x18000a71d  mov     ebx, 80070057h
0x18000a722  mov     edx, 0C54h; void *
0x18000a727  mov     r9d, ebx; char *
0x18000a72a  mov     rcx, [rbp+28h]; this
0x18000a72e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000a735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a73a  lea     rcx, [rbp+var_20]
0x18000a73e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000a743  mov     eax, ebx
0x18000a745  add     rsp, 40h
0x18000a749  pop     r14
0x18000a74b  pop     rdi
0x18000a74c  pop     rsi
0x18000a74d  pop     rbx
0x18000a74e  pop     rbp
0x18000a74f  retn
```
