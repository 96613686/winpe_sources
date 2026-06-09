# QueryPolicyString

- ea: `0x1800421dc`
- end: `0x18004234f`
- name: `QueryPolicyString`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040d58`

## callees

- `0x180027a70`
- `0x18002c090`
- `0x18002c34c`
- `0x1800421dc`
- `0x180042718`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042309`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042309`

## string_xrefs

- `0x180042261`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18004229a`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18004231e`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
int __fastcall QueryPolicyString(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v9; // eax
  unsigned int v10; // r8d
  int v12; // edi
  HLOCAL v13; // rbx
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // [rsp+20h] [rbp-38h]
  int v17; // [rsp+20h] [rbp-38h]
  int v18; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-14h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  v18 = 3;
  v19 = 0;
  v9 = SIPolicyQueryOneSecurityPolicy(a1, a2, a3, a4, &v18, 0, &v19);
  if ( v9 != -1073741275 )
  {
    if ( v9 < 0 )
      return wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x6ED, v10, (const char *)(unsigned int)v9, v16);
    if ( v18 == 3 )
    {
      wil::make_unique_hlocal_nothrow<unsigned char [0]>(hMem, v19);
      v13 = hMem[0];
      if ( !hMem[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F2,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
          (const char *)0x8007000ELL,
          v16);
        return -2147024882;
      }
      v14 = SIPolicyQueryOneSecurityPolicy(a1, a2, a3, a4, &v18, 0, &v19);
      if ( v14 >= 0 )
      {
        if ( v18 == 3 )
        {
          *a5 = v13;
          return 0;
        }
        v12 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6FC,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
          (const char *)0x8000FFFFLL,
          v17);
      }
      else
      {
        v12 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x6FB, v15, (const char *)(unsigned int)v14, v17);
      }
      if ( v13 )
        LocalFree(v13);
    }
    else
    {
      v12 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6EE,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
        (const char *)0x8000FFFFLL,
        v16);
    }
    return v12;
  }
  *a5 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800421dc  push    rbp
0x1800421de  push    rbx
0x1800421df  push    rsi
0x1800421e0  push    rdi
0x1800421e1  push    r14
0x1800421e3  push    r15
0x1800421e5  mov     rbp, rsp
0x1800421e8  sub     rsp, 58h
0x1800421ec  lea     rax, [rbp+var_14]
0x1800421f0  mov     [rbp+var_18], 3
0x1800421f7  mov     [rsp+58h+var_28], rax
0x1800421fc  mov     rdi, r9
0x1800421ff  lea     rax, [rbp+var_18]
0x180042203  mov     [rsp+58h+var_30], 0
0x18004220c  mov     qword ptr [rsp+58h+var_38], rax; int
0x180042211  mov     rsi, r8
0x180042214  mov     r14, rdx
0x180042217  mov     [rbp+var_14], 0
0x18004221e  mov     r15, rcx
0x180042221  call    SIPolicyQueryOneSecurityPolicy
0x180042226  cmp     eax, 0C0000225h
0x18004222b  jnz     short loc_18004223D
0x18004222d  mov     rax, [rbp+arg_20]
0x180042231  mov     qword ptr [rax], 0
0x180042238  jmp     loc_180042340
0x18004223d  test    eax, eax
0x18004223f  jns     short loc_180042257
0x180042241  mov     rcx, [rbp+30h]; this
0x180042245  mov     r9d, eax; char *
0x180042248  mov     edx, 6EDh; void *
0x18004224d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180042252  jmp     loc_180042342
0x180042257  cmp     [rbp+var_18], 3
0x18004225b  jz      short loc_180042281
0x18004225d  mov     rcx, [rbp+30h]; this
0x180042261  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180042268  mov     edi, 8000FFFFh
0x18004226d  mov     edx, 6EEh; void *
0x180042272  mov     r9d, edi; char *
0x180042275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004227a  mov     eax, edi
0x18004227c  jmp     loc_180042342
0x180042281  mov     edx, [rbp+var_14]
0x180042284  lea     rcx, [rbp+hMem]
0x180042288  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18004228d  mov     rbx, [rbp+hMem]
0x180042291  test    rbx, rbx
0x180042294  jnz     short loc_1800422BA
0x180042296  mov     rcx, [rbp+30h]; this
0x18004229a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x1800422a1  mov     ebx, 8007000Eh
0x1800422a6  mov     edx, 6F2h; void *
0x1800422ab  mov     r9d, ebx; char *
0x1800422ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800422b3  mov     eax, ebx
0x1800422b5  jmp     loc_180042342
0x1800422ba  lea     rax, [rbp+var_14]
0x1800422be  mov     r9, rdi
0x1800422c1  mov     [rsp+58h+var_28], rax
0x1800422c6  mov     r8, rsi
0x1800422c9  lea     rax, [rbp+var_18]
0x1800422cd  mov     [rsp+58h+var_30], 0
0x1800422d6  mov     rdx, r14
0x1800422d9  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800422de  mov     rcx, r15
0x1800422e1  call    SIPolicyQueryOneSecurityPolicy
0x1800422e6  test    eax, eax
0x1800422e8  jns     short loc_180042314
0x1800422ea  mov     rcx, [rbp+30h]; this
0x1800422ee  mov     r9d, eax; char *
0x1800422f1  mov     edx, 6FBh; void *
0x1800422f6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800422fb  mov     edi, eax
0x1800422fd  test    rbx, rbx
0x180042300  jz      loc_18004227A
0x180042306  mov     rcx, rbx; hMem
0x180042309  call    cs:__imp_LocalFree
0x18004230f  jmp     loc_18004227A
0x180042314  cmp     [rbp+var_18], 3
0x180042318  jz      short loc_180042339
0x18004231a  mov     rcx, [rbp+30h]; this
0x18004231e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180042325  mov     edi, 8000FFFFh
0x18004232a  mov     edx, 6FCh; void *
0x18004232f  mov     r9d, edi; char *
0x180042332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042337  jmp     short loc_1800422FD
0x180042339  mov     rax, [rbp+arg_20]
0x18004233d  mov     [rax], rbx
0x180042340  xor     eax, eax
0x180042342  add     rsp, 58h
0x180042346  pop     r15
0x180042348  pop     r14
0x18004234a  pop     rdi
0x18004234b  pop     rsi
0x18004234c  pop     rbx
0x18004234d  pop     rbp
0x18004234e  retn
```
