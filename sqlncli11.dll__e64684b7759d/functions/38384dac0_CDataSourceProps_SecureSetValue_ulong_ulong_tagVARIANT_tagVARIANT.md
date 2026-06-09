# CDataSourceProps::SecureSetValue(ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x38384dac0`
- end: `0x38384daf0`
- name: `?SecureSetValue@CDataSourceProps@@UEAAJKKPEAUtagVARIANT@@0@Z`
- size: `48`
- prototype: `int(CDataSourceProps *__hidden this, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x3838427d0`
- `0x38384dac0`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3838e0a91`
- `KERNEL32!GetLastError` at `0x3838e0a91`
- `OLEAUT32!__imp_SysFreeString` at `0x3838e0ab5`
- `OLEAUT32!__imp_SysFreeString` at `0x3838e0ab5`
- `OLEAUT32!__imp_VariantClear` at `0x3838e0adf`
- `OLEAUT32!__imp_VariantClear` at `0x3838e0adf`
- `OLEAUT32!__imp_VariantCopy` at `0x3838e0b01`
- `OLEAUT32!__imp_VariantCopy` at `0x38384dae9`
- `OLEAUT32!__imp_VariantCopy` at `0x3838e0b01`
- `OLEAUT32!__imp_SysStringByteLen` at `0x3838e0a2c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x3838e0a2c`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x3838e0a48`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x3838e0a48`

## pseudocode

```c
int __fastcall CDataSourceProps::SecureSetValue(
        CDataSourceProps *this,
        int a2,
        int a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvargSrc)
{
  int result; // eax
  OLECHAR *bstrVal; // rbp
  UINT v9; // eax
  __int64 v10; // r14
  UINT v11; // edi
  BSTR v12; // rax
  OLECHAR *v13; // rsi
  DWORD LastError; // eax
  __int64 v15; // rcx

  if ( pvargSrc->vt != 8 )
    return VariantCopy(a4, pvargSrc);
  if ( !a2 )
  {
    if ( a3 == 1 || a3 == 10 )
      goto LABEL_9;
    return VariantCopy(a4, pvargSrc);
  }
  if ( a2 != 1 || a3 != 14 )
    return VariantCopy(a4, pvargSrc);
LABEL_9:
  bstrVal = pvargSrc->bstrVal;
  if ( bstrVal && g_pfnCryptProtectMemory )
  {
    v9 = SysStringByteLen(bstrVal);
    v10 = v9;
    v11 = (v9 + 19) & 0xFFFFFFF0;
    if ( v11 < v9 )
      return -2147024882;
    v12 = SysAllocStringByteLen(0, v11);
    v13 = v12;
    if ( !v12 )
      return -2147024882;
    memcpy(v12, bstrVal - 2, v10 + 4);
    if ( !g_pfnCryptProtectMemory(v13, v11, 0) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B49860[0] )
        {
          LastError = GetLastError();
          bidTraceW(off_383B43328[0], 3337216, off_383B49860[0], LastError);
        }
      }
      SysFreeString(v13);
      return -2147467259;
    }
    result = VariantClear(a4);
    if ( result < 0 )
      return result;
    a4->llVal = (LONGLONG)v13;
    a4->vt = 8;
  }
  else
  {
    result = VariantCopy(a4, pvargSrc);
  }
  if ( result >= 0 )
  {
    v15 = *((_QWORD *)this + 72);
    if ( (*(_BYTE *)(v15 + 280) & 4) != 0 )
      *(_DWORD *)(v15 + 280) &= ~4u;
  }
  return result;
}

```

## disassembly

```asm
0x38384dac0  push    rbx
0x38384dac2  push    r15
0x38384dac4  sub     rsp, 28h
0x38384dac8  mov     eax, edx
0x38384daca  mov     rdx, [rsp+38h+pvargSrc]; pvargSrc
0x38384dacf  mov     rbx, r9
0x38384dad2  cmp     word ptr [rdx], 8
0x38384dad6  mov     r15, rcx
0x38384dad9  jz      loc_3838882D7
0x38384dadf  mov     rcx, rbx
0x38384dae2  add     rsp, 28h
0x38384dae6  pop     r15
0x38384dae8  pop     rbx
0x38384dae9  jmp     cs:__imp_VariantCopy
0x3838882d7  test    eax, eax
0x3838882d9  jnz     short loc_3838882F4
0x3838882db  cmp     r8d, 1
0x3838882df  jz      loc_3838E09FA
0x3838882e5  cmp     r8d, 0Ah
0x3838882e9  jnz     loc_38384DADF
0x3838882ef  jmp     loc_3838E09FA
0x3838882f4  cmp     eax, 1
0x3838882f7  jnz     loc_38384DADF
0x3838882fd  cmp     r8d, 0Eh
0x383888301  jnz     loc_38384DADF
0x383888307  jmp     loc_3838E09FA
0x3838e09fa  mov     [rsp+38h+arg_0], rbp
0x3838e09ff  mov     rbp, [rdx+8]
0x3838e0a03  mov     [rsp+38h+arg_8], rsi
0x3838e0a08  mov     [rsp+38h+arg_10], rdi
0x3838e0a0d  mov     [rsp+38h+var_18], r14
0x3838e0a12  test    rbp, rbp
0x3838e0a15  jz      loc_3838E0AFE
0x3838e0a1b  cmp     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, 0; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x3838e0a23  jz      loc_3838E0AFE
0x3838e0a29  mov     rcx, rbp; bstr
0x3838e0a2c  call    cs:__imp_SysStringByteLen
0x3838e0a32  mov     r14d, eax
0x3838e0a35  lea     edi, [r14+13h]
0x3838e0a39  and     edi, 0FFFFFFF0h
0x3838e0a3c  cmp     edi, eax
0x3838e0a3e  jb      loc_3838E0AF7
0x3838e0a44  mov     edx, edi; len
0x3838e0a46  xor     ecx, ecx; psz
0x3838e0a48  call    cs:__imp_SysAllocStringByteLen
0x3838e0a4e  mov     rsi, rax
0x3838e0a51  test    rax, rax
0x3838e0a54  jz      loc_3838E0AF7
0x3838e0a5a  lea     r8, [r14+4]; Size
0x3838e0a5e  lea     rdx, [rbp-4]; Src
0x3838e0a62  mov     rcx, rax; void *
0x3838e0a65  call    memcpy
0x3838e0a6a  xor     r8d, r8d
0x3838e0a6d  mov     edx, edi
0x3838e0a6f  mov     rcx, rsi
0x3838e0a72  call    cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x3838e0a78  test    eax, eax
0x3838e0a7a  jnz     short loc_3838E0ADC
0x3838e0a7c  test    byte ptr cs:_bidGblFlags, 2
0x3838e0a83  jz      short loc_3838E0AB2
0x3838e0a85  mov     rax, cs:off_383B49860; "<CDataSourceProps::SecureSetValue|ERR|S"...
0x3838e0a8c  test    rax, rax
0x3838e0a8f  jz      short loc_3838E0AB2
0x3838e0a91  call    cs:__imp_GetLastError
0x3838e0a97  mov     r8, cs:off_383B49860; "<CDataSourceProps::SecureSetValue|ERR|S"...
0x3838e0a9e  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838e0aa5  mov     r9d, eax
0x3838e0aa8  mov     edx, 32EC00h
0x3838e0aad  call    _bidTraceW
0x3838e0ab2  mov     rcx, rsi; bstrString
0x3838e0ab5  call    cs:__imp_SysFreeString
0x3838e0abb  mov     eax, 80004005h
0x3838e0ac0  mov     rdi, [rsp+38h+arg_10]
0x3838e0ac5  mov     rsi, [rsp+38h+arg_8]
0x3838e0aca  mov     rbp, [rsp+38h+arg_0]
0x3838e0acf  mov     r14, [rsp+38h+var_18]
0x3838e0ad4  add     rsp, 28h
0x3838e0ad8  pop     r15
0x3838e0ada  pop     rbx
0x3838e0adb  retn
0x3838e0adc  mov     rcx, rbx; pvarg
0x3838e0adf  call    cs:__imp_VariantClear
0x3838e0ae5  test    eax, eax
0x3838e0ae7  js      short loc_3838E0AC0
0x3838e0ae9  mov     ecx, 8
0x3838e0aee  mov     [rbx+8], rsi
0x3838e0af2  mov     [rbx], cx
0x3838e0af5  jmp     short loc_3838E0B07
0x3838e0af7  mov     eax, 8007000Eh
0x3838e0afc  jmp     short loc_3838E0AC0
0x3838e0afe  mov     rcx, rbx; pvargDest
0x3838e0b01  call    cs:__imp_VariantCopy
0x3838e0b07  test    eax, eax
0x3838e0b09  js      short loc_3838E0AC0
0x3838e0b0b  mov     rcx, [r15+240h]
0x3838e0b12  test    byte ptr [rcx+118h], 4
0x3838e0b19  jz      short loc_3838E0AC0
0x3838e0b1b  and     dword ptr [rcx+118h], 0FFFFFFFBh
0x3838e0b22  jmp     short loc_3838E0AC0
```
