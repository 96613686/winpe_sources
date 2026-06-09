# CLogConfigurableFilter::ParseDateString(ushort const *,double *)

- ea: `0x180025bdc`
- end: `0x180025ce0`
- name: `?ParseDateString@CLogConfigurableFilter@@IEAAHPEBGPEAN@Z`
- size: `260`
- prototype: `int(CLogConfigurableFilter *__hidden this, const unsigned __int16 *, double *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800264cc`

## callees

- `0x180025bdc`
- `0x180027510`

## import_xrefs

- `msvcrt!swscanf_s` at `0x180025c3b`
- `msvcrt!swscanf_s` at `0x180025c67`
- `msvcrt!swscanf_s` at `0x180025c3b`
- `msvcrt!swscanf_s` at `0x180025c67`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180025ca8`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180025ca8`

## pseudocode

```c
__int64 __fastcall CLogConfigurableFilter::ParseDateString(
        CLogConfigurableFilter *this,
        const unsigned __int16 *a2,
        double *a3)
{
  unsigned int v5; // ecx
  int v7; // [rsp+30h] [rbp-30h] BYREF
  int v8; // [rsp+34h] [rbp-2Ch] BYREF
  int v9; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-20h] BYREF

  if ( !a2 )
    return 0;
  v8 = 0;
  v9 = 0;
  v7 = 0;
  if ( swscanf_s(a2, L"%u/%u/%u", &v7, &v8, &v9) != 3 && swscanf_s(a2, L"%u-%u-%u", &v7, &v8, &v9) != 3 )
    return 0;
  v5 = 1;
  SystemTime = 0;
  SystemTime.wYear = v7;
  SystemTime.wMonth = v8;
  SystemTime.wDay = v9;
  if ( a3 )
    return SystemTimeToVariantTime(&SystemTime, a3) != 0;
  return v5;
}

```

## disassembly

```asm
0x180025bdc  mov     [rsp-8+arg_0], rbx
0x180025be1  mov     [rsp-8+arg_18], rdi
0x180025be6  push    rbp
0x180025be7  mov     rbp, rsp
0x180025bea  sub     rsp, 60h
0x180025bee  mov     rax, cs:__security_cookie
0x180025bf5  xor     rax, rsp
0x180025bf8  mov     [rbp+var_10], rax
0x180025bfc  mov     rdi, r8
0x180025bff  mov     rbx, rdx
0x180025c02  test    rdx, rdx
0x180025c05  jz      loc_180025CBF
0x180025c0b  lea     rax, [rbp+var_28]
0x180025c0f  mov     [rbp+var_2C], 0
0x180025c16  lea     r9, [rbp+var_2C]
0x180025c1a  mov     [rsp+60h+var_40], rax
0x180025c1f  lea     r8, [rbp+var_30]
0x180025c23  mov     [rbp+var_28], 0
0x180025c2a  lea     rdx, aUUU_0; "%u/%u/%u"
0x180025c31  mov     [rbp+var_30], 0
0x180025c38  mov     rcx, rbx; Buffer
0x180025c3b  call    cs:__imp_swscanf_s
0x180025c42  nop     dword ptr [rax+rax+00h]
0x180025c47  cmp     eax, 3
0x180025c4a  jz      short loc_180025C78
0x180025c4c  lea     rax, [rbp+var_28]
0x180025c50  mov     rcx, rbx; Buffer
0x180025c53  lea     r9, [rbp+var_2C]
0x180025c57  mov     [rsp+60h+var_40], rax
0x180025c5c  lea     r8, [rbp+var_30]
0x180025c60  lea     rdx, aUUU; "%u-%u-%u"
0x180025c67  call    cs:__imp_swscanf_s
0x180025c6e  nop     dword ptr [rax+rax+00h]
0x180025c73  cmp     eax, 3
0x180025c76  jnz     short loc_180025CBF
0x180025c78  movzx   eax, word ptr [rbp+var_30]
0x180025c7c  xorps   xmm0, xmm0
0x180025c7f  mov     ecx, 1
0x180025c84  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180025c88  mov     [rbp+SystemTime.wYear], ax
0x180025c8c  movzx   eax, word ptr [rbp+var_2C]
0x180025c90  mov     [rbp+SystemTime.wMonth], ax
0x180025c94  movzx   eax, word ptr [rbp+var_28]
0x180025c98  mov     [rbp+SystemTime.wDay], ax
0x180025c9c  test    rdi, rdi
0x180025c9f  jz      short loc_180025CBB
0x180025ca1  mov     rdx, rdi; pvtime
0x180025ca4  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180025ca8  call    cs:__imp_SystemTimeToVariantTime
0x180025caf  nop     dword ptr [rax+rax+00h]
0x180025cb4  xor     ecx, ecx
0x180025cb6  test    eax, eax
0x180025cb8  setnz   cl
0x180025cbb  mov     eax, ecx
0x180025cbd  jmp     short loc_180025CC1
0x180025cbf  xor     eax, eax
0x180025cc1  mov     rcx, [rbp+var_10]
0x180025cc5  xor     rcx, rsp; StackCookie
0x180025cc8  call    __security_check_cookie
0x180025ccd  lea     r11, [rsp+60h+var_s0]
0x180025cd2  mov     rbx, [r11+10h]
0x180025cd6  mov     rdi, [r11+28h]
0x180025cda  mov     rsp, r11
0x180025cdd  pop     rbp
0x180025cde  retn
```
