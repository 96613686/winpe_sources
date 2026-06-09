# PolicyTransforms::GetPauseUpdatesStartTime(tagEnterprisePolicyValue_V1 *,bool)

- ea: `0x180017804`
- end: `0x1800178f2`
- name: `?GetPauseUpdatesStartTime@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@_N@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *, unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180017900`
- `0x180017950`

## callees

- `0x180017804`
- `0x18001f09c`
- `0x18002c898`
- `0x18002cdfc`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800178af`
- `OLEAUT32!__imp_SysAllocString` at `0x1800178af`
- `OLEAUT32!__imp_VariantClear` at `0x18001786f`
- `OLEAUT32!__imp_VariantClear` at `0x1800178ca`
- `OLEAUT32!__imp_VariantClear` at `0x18001786f`
- `OLEAUT32!__imp_VariantClear` at `0x1800178ca`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::GetPauseUpdatesStartTime(
        struct tagEnterprisePolicyValue_V1 *a1,
        unsigned __int8 a2)
{
  unsigned int v2; // edi
  HRESULT v4; // edi
  bool v5; // zf
  BSTR v6; // rax
  __int64 v8; // [rsp+20h] [rbp-58h] BYREF
  OLECHAR psz[8]; // [rsp+28h] [rbp-50h] BYREF
  __int128 v10; // [rsp+38h] [rbp-40h]
  __int64 v11; // [rsp+48h] [rbp-30h]
  __int16 v12; // [rsp+50h] [rbp-28h]

  v2 = a2;
  v8 = 0;
  v11 = 0;
  v12 = 0;
  *(_OWORD *)psz = 0;
  v10 = 0;
  if ( !a1
    || (unsigned int)PolicyHelpers::IsPolicyConfiguredAndEnabled(a1)
    && (int)StringToFileTime(*((_QWORD *)a1 + 3), &v8, v2) < 0
    || (v4 = VariantClear((VARIANTARG *)((char *)a1 + 16)), v4 < 0)
    || ((v5 = (_DWORD)v8 == 0, *((_WORD *)a1 + 8) = 8, !v5) || HIDWORD(v8)) && (v4 = FileTimeToString(psz), v4 < 0)
    || (v6 = SysAllocString(psz), (*((_QWORD *)a1 + 3) = v6) == 0) )
  {
    *(_QWORD *)((char *)a1 + 4) = 0;
    return (unsigned int)VariantClear((VARIANTARG *)((char *)a1 + 16));
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017804  mov     [rsp+arg_10], rbx
0x180017809  push    rsi
0x18001780a  push    rdi
0x18001780b  push    r14
0x18001780d  sub     rsp, 60h
0x180017811  mov     rax, cs:__security_cookie
0x180017818  xor     rax, rsp
0x18001781b  mov     [rsp+78h+var_20], rax
0x180017820  xor     eax, eax
0x180017822  movzx   edi, dl
0x180017825  mov     [rsp+78h+var_58], 0
0x18001782e  xorps   xmm0, xmm0
0x180017831  mov     [rsp+78h+var_30], rax
0x180017836  mov     rbx, rcx
0x180017839  mov     [rsp+78h+var_28], ax
0x18001783e  movups  xmmword ptr [rsp+78h+psz], xmm0
0x180017843  movups  [rsp+78h+var_40], xmm0
0x180017848  test    rcx, rcx
0x18001784b  jz      short loc_1800178BE
0x18001784d  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x180017852  test    eax, eax
0x180017854  jz      short loc_18001786B
0x180017856  mov     rcx, [rbx+18h]
0x18001785a  lea     rdx, [rsp+78h+var_58]
0x18001785f  mov     r8d, edi
0x180017862  call    StringToFileTime
0x180017867  test    eax, eax
0x180017869  js      short loc_1800178BE
0x18001786b  lea     rcx, [rbx+10h]; pvarg
0x18001786f  call    cs:__imp_VariantClear
0x180017875  mov     edi, eax
0x180017877  test    eax, eax
0x180017879  js      short loc_1800178BE
0x18001787b  cmp     dword ptr [rsp+78h+var_58], 0
0x180017880  mov     word ptr [rbx+10h], 8
0x180017886  jnz     short loc_18001788F
0x180017888  cmp     dword ptr [rsp+78h+var_58+4], 0
0x18001788d  jz      short loc_1800178AA
0x18001788f  mov     r9d, 6
0x180017895  lea     r8, [rsp+78h+var_58]
0x18001789a  lea     rcx, [rsp+78h+psz]; Buffer
0x18001789f  call    FileTimeToString
0x1800178a4  mov     edi, eax
0x1800178a6  test    eax, eax
0x1800178a8  js      short loc_1800178BE
0x1800178aa  lea     rcx, [rsp+78h+psz]; psz
0x1800178af  call    cs:__imp_SysAllocString
0x1800178b5  mov     [rbx+18h], rax
0x1800178b9  test    rax, rax
0x1800178bc  jnz     short loc_1800178D2
0x1800178be  mov     qword ptr [rbx+4], 0
0x1800178c6  lea     rcx, [rbx+10h]; pvarg
0x1800178ca  call    cs:__imp_VariantClear
0x1800178d0  mov     edi, eax
0x1800178d2  mov     eax, edi
0x1800178d4  mov     rcx, [rsp+78h+var_20]
0x1800178d9  xor     rcx, rsp; StackCookie
0x1800178dc  call    __security_check_cookie
0x1800178e1  mov     rbx, [rsp+78h+arg_10]
0x1800178e9  add     rsp, 60h
0x1800178ed  pop     r14
0x1800178ef  pop     rdi
0x1800178f0  pop     rsi
0x1800178f1  retn
```
