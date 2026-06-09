# CDataSourceProps::SecureGetValue(ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x383896160`
- end: `0x3838961bc`
- name: `?SecureGetValue@CDataSourceProps@@UEAAJKKPEAUtagVARIANT@@0@Z`
- size: `92`
- prototype: `int(CDataSourceProps *__hidden this, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x3838427d0`
- `0x383896160`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3838e0bee`
- `KERNEL32!GetLastError` at `0x3838e0bee`
- `OLEAUT32!__imp_SysFreeString` at `0x3838e0bce`
- `OLEAUT32!__imp_SysFreeString` at `0x3838e0bce`
- `OLEAUT32!__imp_VariantClear` at `0x3838e0b4a`
- `OLEAUT32!__imp_VariantClear` at `0x3838e0b4a`
- `OLEAUT32!__imp_VariantCopy` at `0x38389618e`
- `OLEAUT32!__imp_VariantCopy` at `0x38389618e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x3838e0b77`
- `OLEAUT32!__imp_SysStringByteLen` at `0x3838e0b77`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x3838e0ba1`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x3838e0ba1`

## pseudocode

```c
__int64 __fastcall CDataSourceProps::SecureGetValue(
        CDataSourceProps *this,
        int a2,
        int a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvargSrc)
{
  unsigned int v9; // ebx
  UINT *pulVal; // rsi
  UINT v12; // eax
  UINT v13; // edi
  UINT v14; // r15d
  BSTR v15; // rax
  LONGLONG v16; // r14
  DWORD LastError; // eax

  v9 = VariantCopy(a4, pvargSrc);
  if ( (v9 & 0x80000000) == 0 && pvargSrc->vt == 8 )
  {
    if ( a2 )
    {
      if ( a2 != 1 || a3 != 14 )
        return v9;
    }
    else if ( a3 != 1 && a3 != 10 )
    {
      return v9;
    }
    pulVal = a4->pulVal;
    if ( (*(_BYTE *)(*((_QWORD *)this + 72) + 280LL) & 4) != 0 )
    {
      VariantClear(a4);
      a4->llVal = 0;
    }
    else if ( pulVal )
    {
      if ( g_pfnCryptUnprotectMemory )
      {
        v12 = SysStringByteLen(a4->bstrVal);
        v13 = v12;
        if ( v12 )
        {
          if ( g_pfnCryptUnprotectMemory(pulVal, v12, 0) )
          {
            v14 = *pulVal;
            v15 = SysAllocStringByteLen(0, *pulVal);
            v16 = (LONGLONG)v15;
            if ( v15 )
            {
              memcpy(v15, pulVal + 1, v14);
              a4->llVal = v16;
              memset(pulVal, 0, v13);
              SysFreeString((BSTR)pulVal);
              return v9;
            }
          }
          else if ( (bidGblFlags & 2) != 0 && off_383B49858[0] )
          {
            LastError = GetLastError();
            bidTraceW(off_383B43328[0], 3429376, off_383B49858[0], LastError);
          }
          return (unsigned int)-2147467259;
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x383896160  mov     [rsp+arg_0], rbx
0x383896165  mov     [rsp+arg_8], rbp
0x38389616a  mov     [rsp+arg_10], rsi
0x38389616f  push    rdi
0x383896170  push    r14
0x383896172  push    r15
0x383896174  sub     rsp, 20h
0x383896178  mov     r14, [rsp+38h+pvargSrc]
0x38389617d  mov     esi, edx
0x38389617f  mov     r15, rcx
0x383896182  mov     rcx, r9; pvargDest
0x383896185  mov     rdx, r14; pvargSrc
0x383896188  mov     rbp, r9
0x38389618b  mov     edi, r8d
0x38389618e  call    cs:__imp_VariantCopy
0x383896194  mov     ebx, eax
0x383896196  test    eax, eax
0x383896198  js      short loc_3838961A1
0x38389619a  cmp     word ptr [r14], 8
0x38389619f  jz      short loc_383896137
0x3838961a1  mov     rbp, [rsp+38h+arg_8]
0x3838961a6  mov     rsi, [rsp+38h+arg_10]
0x3838961ab  mov     eax, ebx
0x3838961ad  mov     rbx, [rsp+38h+arg_0]
0x3838961b2  add     rsp, 20h
0x3838961b6  pop     r15
0x3838961b8  pop     r14
0x3838961ba  pop     rdi
0x3838961bb  retn
0x383896137  test    esi, esi
0x383896139  jz      loc_3838E0B24
0x38389613f  cmp     esi, 1
0x383896142  jnz     short loc_3838961A1
0x383896144  cmp     edi, 0Eh
0x383896147  jnz     short loc_3838961A1
0x383896149  jmp     loc_3838E0B33
0x3838e0b24  cmp     edi, 1
0x3838e0b27  jz      short loc_3838E0B33
0x3838e0b29  cmp     edi, 0Ah
0x3838e0b2c  jz      short loc_3838E0B33
0x3838e0b2e  jmp     loc_3838961A1
0x3838e0b33  mov     rax, [r15+240h]
0x3838e0b3a  mov     rsi, [rbp+8]
0x3838e0b3e  test    byte ptr [rax+118h], 4
0x3838e0b45  jz      short loc_3838E0B5D
0x3838e0b47  mov     rcx, rbp; pvarg
0x3838e0b4a  call    cs:__imp_VariantClear
0x3838e0b50  mov     qword ptr [rbp+8], 0
0x3838e0b58  jmp     loc_3838961A1
0x3838e0b5d  test    rsi, rsi
0x3838e0b60  jz      loc_3838961A1
0x3838e0b66  cmp     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, 0; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x3838e0b6e  jz      loc_3838961A1
0x3838e0b74  mov     rcx, rsi; bstr
0x3838e0b77  call    cs:__imp_SysStringByteLen
0x3838e0b7d  mov     edi, eax
0x3838e0b7f  test    eax, eax
0x3838e0b81  jz      loc_3838961A1
0x3838e0b87  xor     r8d, r8d
0x3838e0b8a  mov     edx, edi
0x3838e0b8c  mov     rcx, rsi
0x3838e0b8f  call    cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x3838e0b95  test    eax, eax
0x3838e0b97  jz      short loc_3838E0BD9
0x3838e0b99  mov     r15d, [rsi]
0x3838e0b9c  xor     ecx, ecx; psz
0x3838e0b9e  mov     edx, r15d; len
0x3838e0ba1  call    cs:__imp_SysAllocStringByteLen
0x3838e0ba7  mov     r14, rax
0x3838e0baa  test    rax, rax
0x3838e0bad  jz      short loc_3838E0C0F
0x3838e0baf  lea     rdx, [rsi+4]; Src
0x3838e0bb3  mov     r8d, r15d; Size
0x3838e0bb6  mov     rcx, rax; void *
0x3838e0bb9  call    memcpy
0x3838e0bbe  mov     ecx, edi
0x3838e0bc0  xor     eax, eax
0x3838e0bc2  mov     [rbp+8], r14
0x3838e0bc6  mov     rdi, rsi
0x3838e0bc9  rep stosb
0x3838e0bcb  mov     rcx, rsi; bstrString
0x3838e0bce  call    cs:__imp_SysFreeString
0x3838e0bd4  jmp     loc_3838961A1
0x3838e0bd9  test    byte ptr cs:_bidGblFlags, 2
0x3838e0be0  jz      short loc_3838E0C0F
0x3838e0be2  mov     rax, cs:off_383B49858; "<CDataSourceProps::SecureGetValue|ERR|S"...
0x3838e0be9  test    rax, rax
0x3838e0bec  jz      short loc_3838E0C0F
0x3838e0bee  call    cs:__imp_GetLastError
0x3838e0bf4  mov     r8, cs:off_383B49858; "<CDataSourceProps::SecureGetValue|ERR|S"...
0x3838e0bfb  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838e0c02  mov     r9d, eax
0x3838e0c05  mov     edx, 345400h
0x3838e0c0a  call    _bidTraceW
0x3838e0c0f  mov     ebx, 80004005h
0x3838e0c14  jmp     loc_3838961A1
```
