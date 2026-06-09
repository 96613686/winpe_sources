# EnterprisePolicyReader::ReadLusPolicy(wchar_t const *,wchar_t const *,tagEnterprisePolicyValue_V1 *)

- ea: `0x180011e8c`
- end: `0x180011f79`
- name: `?ReadLusPolicy@EnterprisePolicyReader@@CAJPEB_W0PEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180010c1c`

## callees

- `0x180011e8c`
- `0x180011f80`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011f28`
- `OLEAUT32!__imp_SysAllocString` at `0x180011f28`
- `OLEAUT32!__imp_VariantInit` at `0x180011eba`
- `OLEAUT32!__imp_VariantInit` at `0x180011ed4`
- `OLEAUT32!__imp_VariantInit` at `0x180011eba`
- `OLEAUT32!__imp_VariantInit` at `0x180011ed4`
- `OLEAUT32!__imp_VariantClear` at `0x180011f57`
- `OLEAUT32!__imp_VariantClear` at `0x180011f57`
- `OLEAUT32!__imp_VariantCopy` at `0x180011f17`
- `OLEAUT32!__imp_VariantCopy` at `0x180011f17`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadLusPolicy(
        const wchar_t *a1,
        const wchar_t *a2,
        struct tagEnterprisePolicyValue_V1 *a3)
{
  HRESULT v5; // ebx
  unsigned int v7; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-40h] BYREF

  v7 = 0;
  VariantInit(&pvarg);
  if ( a3 && a1 )
  {
    VariantInit(&pvarg);
    v5 = EnterprisePolicyReader::ReadLusPolicy(a1, 8u, &pvarg, &v7);
    if ( v5 >= 0 && v7 == 1 )
    {
      *((_DWORD *)a3 + 1) = 1;
      if ( pvarg.vt == 8 )
        v5 = VariantCopy((VARIANTARG *)((char *)a3 + 16), &pvarg);
      else
        *((_QWORD *)a3 + 3) = SysAllocString(&psz);
      if ( *((_QWORD *)a3 + 3) )
      {
        *((_WORD *)a3 + 8) = 8;
        *((_DWORD *)a3 + 2) = 5;
      }
      else
      {
        v5 = -2147024882;
      }
    }
  }
  else
  {
    v5 = -2147467261;
  }
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011e8c  mov     [rsp+arg_8], rbx
0x180011e91  push    rbp
0x180011e92  push    rsi
0x180011e93  push    rdi
0x180011e94  sub     rsp, 50h
0x180011e98  mov     rax, cs:__security_cookie
0x180011e9f  xor     rax, rsp
0x180011ea2  mov     [rsp+68h+var_28], rax
0x180011ea7  mov     rdi, r8
0x180011eaa  mov     rbx, rcx
0x180011ead  mov     [rsp+68h+var_48], 0
0x180011eb5  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180011eba  call    cs:__imp_VariantInit
0x180011ec0  nop
0x180011ec1  test    rdi, rdi
0x180011ec4  jz      loc_180011F4D
0x180011eca  test    rbx, rbx
0x180011ecd  jz      short loc_180011F4D
0x180011ecf  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180011ed4  call    cs:__imp_VariantInit
0x180011eda  mov     ebp, 8
0x180011edf  mov     edx, ebp; unsigned __int16
0x180011ee1  lea     r9, [rsp+68h+var_48]; unsigned int *
0x180011ee6  lea     r8, [rsp+68h+pvarg]; struct tagVARIANT *
0x180011eeb  mov     rcx, rbx; wchar_t *
0x180011eee  call    ?ReadLusPolicy@EnterprisePolicyReader@@CAJPEB_WGPEAUtagVARIANT@@PEAK@Z; EnterprisePolicyReader::ReadLusPolicy(wchar_t const *,ushort,tagVARIANT *,ulong *)
0x180011ef3  mov     ebx, eax
0x180011ef5  test    eax, eax
0x180011ef7  js      short loc_180011F52
0x180011ef9  cmp     [rsp+68h+var_48], 1
0x180011efe  jnz     short loc_180011F52
0x180011f00  mov     dword ptr [rdi+4], 1
0x180011f07  cmp     word ptr [rsp+68h+pvarg], bp
0x180011f0c  jnz     short loc_180011F21
0x180011f0e  lea     rdx, [rsp+68h+pvarg]; pvargSrc
0x180011f13  lea     rcx, [rdi+10h]; pvargDest
0x180011f17  call    cs:__imp_VariantCopy
0x180011f1d  mov     ebx, eax
0x180011f1f  jmp     short loc_180011F32
0x180011f21  lea     rcx, psz; psz
0x180011f28  call    cs:__imp_SysAllocString
0x180011f2e  mov     [rdi+18h], rax
0x180011f32  cmp     qword ptr [rdi+18h], 0
0x180011f37  jnz     short loc_180011F40
0x180011f39  mov     ebx, 8007000Eh
0x180011f3e  jmp     short loc_180011F52
0x180011f40  mov     [rdi+10h], bp
0x180011f44  mov     dword ptr [rdi+8], 5
0x180011f4b  jmp     short loc_180011F52
0x180011f4d  mov     ebx, 80004003h
0x180011f52  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180011f57  call    cs:__imp_VariantClear
0x180011f5d  mov     eax, ebx
0x180011f5f  mov     rcx, [rsp+68h+var_28]
0x180011f64  xor     rcx, rsp; StackCookie
0x180011f67  call    __security_check_cookie
0x180011f6c  mov     rbx, [rsp+68h+arg_8]
0x180011f71  add     rsp, 50h
0x180011f75  pop     rdi
0x180011f76  pop     rsi
0x180011f77  pop     rbp
0x180011f78  retn
```
