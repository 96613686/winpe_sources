# PolicyHelpers::ReadPolicyRegistry(wchar_t const *,wchar_t const *,wchar_t const *,tagPolicyStore,tagEnterprisePolicyValue_V1 *)

- ea: `0x18001f880`
- end: `0x18001f947`
- name: `?ReadPolicyRegistry@PolicyHelpers@@SAJPEB_W00W4tagPolicyStore@@PEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, const OLECHAR *, int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180010c1c`
- `0x180011cf8`

## callees

- `0x18001f328`
- `0x18001f880`
- `0x18003002c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001f8d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f8fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f8d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f8fe`

## pseudocode

```c
__int64 __fastcall PolicyHelpers::ReadPolicyRegistry(
        const WCHAR *a1,
        const WCHAR *a2,
        const OLECHAR *a3,
        int a4,
        __int64 a5)
{
  unsigned int v7; // edi
  int v8; // eax
  OLECHAR *v9; // rsi
  BSTR v10; // rax
  __int64 v11; // rax
  OLECHAR *psz; // [rsp+20h] [rbp-28h] BYREF

  psz = 0;
  if ( !a5 )
    return (unsigned int)-2147467261;
  *(_QWORD *)(a5 + 4) = 0;
  *(_WORD *)(a5 + 16) = 8;
  v8 = PolicyHelpers::ReadPolicyString(a1, a2, &psz);
  v9 = psz;
  v7 = v8;
  if ( v8 < 0 )
  {
    v10 = SysAllocString(a3);
    v7 = 0;
LABEL_12:
    *(_QWORD *)(a5 + 24) = v10;
    goto LABEL_13;
  }
  if ( !psz )
    goto LABEL_9;
  v11 = -1;
  do
    ++v11;
  while ( psz[v11] );
  if ( v11 )
  {
LABEL_9:
    v10 = SysAllocString(psz);
    if ( !v10 )
    {
      v7 = -2147024882;
      goto LABEL_13;
    }
    *(_DWORD *)(a5 + 4) = 1;
    *(_DWORD *)(a5 + 8) = a4;
    goto LABEL_12;
  }
LABEL_13:
  if ( v9 )
    operator delete(v9);
  return v7;
}

```

## disassembly

```asm
0x18001f880  mov     rax, rsp
0x18001f883  mov     [rax+8], rbx
0x18001f887  mov     [rax+10h], rbp
0x18001f88b  mov     [rax+18h], rsi
0x18001f88f  push    rdi
0x18001f890  push    r14
0x18001f892  push    r15
0x18001f894  sub     rsp, 30h
0x18001f898  mov     rbx, [rsp+48h+arg_20]
0x18001f89d  xor     r15d, r15d
0x18001f8a0  mov     [rax-28h], r15
0x18001f8a4  mov     r14d, r9d
0x18001f8a7  mov     rbp, r8
0x18001f8aa  test    rbx, rbx
0x18001f8ad  jnz     short loc_18001F8B6
0x18001f8af  mov     edi, 80004003h
0x18001f8b4  jmp     short loc_18001F92C
0x18001f8b6  lea     r8, [rsp+48h+psz]; wchar_t **
0x18001f8bb  mov     [rbx+4], r15
0x18001f8bf  mov     word ptr [rbx+10h], 8
0x18001f8c5  call    ?ReadPolicyString@PolicyHelpers@@SAJPEB_W0PEAPEA_W@Z; PolicyHelpers::ReadPolicyString(wchar_t const *,wchar_t const *,wchar_t * *)
0x18001f8ca  mov     rsi, [rsp+48h+psz]
0x18001f8cf  mov     edi, eax
0x18001f8d1  test    eax, eax
0x18001f8d3  jns     short loc_18001F8E3
0x18001f8d5  mov     rcx, rbp; psz
0x18001f8d8  call    cs:__imp_SysAllocString
0x18001f8de  mov     edi, r15d
0x18001f8e1  jmp     short loc_18001F91B
0x18001f8e3  test    rsi, rsi
0x18001f8e6  jz      short loc_18001F8FB
0x18001f8e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f8ec  inc     rax
0x18001f8ef  cmp     [rsi+rax*2], r15w
0x18001f8f4  jnz     short loc_18001F8EC
0x18001f8f6  test    rax, rax
0x18001f8f9  jz      short loc_18001F91F
0x18001f8fb  mov     rcx, rsi; psz
0x18001f8fe  call    cs:__imp_SysAllocString
0x18001f904  test    rax, rax
0x18001f907  jnz     short loc_18001F910
0x18001f909  mov     edi, 8007000Eh
0x18001f90e  jmp     short loc_18001F91F
0x18001f910  mov     dword ptr [rbx+4], 1
0x18001f917  mov     [rbx+8], r14d
0x18001f91b  mov     [rbx+18h], rax
0x18001f91f  test    rsi, rsi
0x18001f922  jz      short loc_18001F92C
0x18001f924  mov     rcx, rsi; Block
0x18001f927  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f92c  mov     rbx, [rsp+48h+arg_0]
0x18001f931  mov     eax, edi
0x18001f933  mov     rbp, [rsp+48h+arg_8]
0x18001f938  mov     rsi, [rsp+48h+arg_10]
0x18001f93d  add     rsp, 30h
0x18001f941  pop     r15
0x18001f943  pop     r14
0x18001f945  pop     rdi
0x18001f946  retn
```
