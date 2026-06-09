# ConvertToUnicode(ulong *,uint,uchar const *,uint *,wchar_t *,uint *)

- ea: `0x1004015c0`
- end: `0x100401693`
- name: `?ConvertToUnicode@@YAJPEAKIPEBEPEAIPEA_W2@Z`
- size: `211`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, const unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10041bb10`
- `0x100420d00`

## callees

- `0x1004015c0`
- `0x100439df0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x10040160e`
- `ole32!CoCreateInstance` at `0x10040160e`

## pseudocode

```c
HRESULT __fastcall ConvertToUnicode(
        unsigned int *a1,
        unsigned int a2,
        const unsigned __int8 *a3,
        unsigned int *a4,
        wchar_t *a5,
        unsigned int *a6)
{
  struct IMultiLanguage2 *v8; // rcx
  HRESULT result; // eax
  bool v12; // zf
  LPVOID ppv; // [rsp+40h] [rbp-18h] BYREF

  v8 = s_pMultiLanguage2;
  if ( s_pMultiLanguage2 )
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, unsigned int *, _QWORD, const unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))v8->lpVtbl->ConvertStringToUnicode)(
             v8,
             a1,
             a2,
             a3,
             a4,
             a5,
             a6);
  ppv = 0;
  result = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &ppv);
  v12 = result == 0;
  if ( result >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&s_pMultiLanguage2, (signed __int64)ppv, 0) )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    result = 0;
    v12 = 1;
  }
  if ( v12 )
  {
    v8 = s_pMultiLanguage2;
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, unsigned int *, _QWORD, const unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))v8->lpVtbl->ConvertStringToUnicode)(
             v8,
             a1,
             a2,
             a3,
             a4,
             a5,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x1004015c0  mov     [rsp+arg_0], rbx
0x1004015c5  mov     [rsp+arg_8], rbp
0x1004015ca  mov     [rsp+arg_10], rsi
0x1004015cf  push    rdi
0x1004015d0  sub     rsp, 50h
0x1004015d4  mov     rbp, rcx
0x1004015d7  mov     rbx, r9
0x1004015da  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x1004015e1  mov     rdi, r8
0x1004015e4  mov     esi, edx
0x1004015e6  test    rcx, rcx
0x1004015e9  jnz     short loc_100401649
0x1004015eb  mov     [rsp+58h+var_18], rcx
0x1004015f0  lea     rax, [rsp+58h+var_18]
0x1004015f5  lea     r8d, [rcx+1]; dwClsContext
0x1004015f9  mov     [rsp+58h+ppv], rax; ppv
0x1004015fe  lea     rcx, CLSID_CMultiLanguage; rclsid
0x100401605  xor     edx, edx; pUnkOuter
0x100401607  lea     r9, IID_IMultiLanguage2; riid
0x10040160e  call    cs:__imp_CoCreateInstance
0x100401614  test    eax, eax
0x100401616  js      short loc_100401640
0x100401618  mov     rcx, [rsp+58h+var_18]
0x10040161d  xor     eax, eax
0x10040161f  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x100401628  jz      short loc_10040163C
0x10040162a  mov     rcx, [rsp+58h+var_18]
0x10040162f  mov     rax, [rcx]
0x100401632  mov     rax, [rax+10h]
0x100401636  call    cs:__guard_dispatch_icall_fptr
0x10040163c  xor     eax, eax
0x10040163e  test    eax, eax
0x100401640  jnz     short loc_10040167E
0x100401642  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100401649  mov     rdx, [rsp+58h+arg_28]
0x100401651  mov     r9, rdi
0x100401654  mov     rax, [rcx]
0x100401657  mov     r8d, esi
0x10040165a  mov     [rsp+58h+var_28], rdx
0x10040165f  mov     rdx, [rsp+58h+arg_20]
0x100401667  mov     [rsp+58h+var_30], rdx
0x10040166c  mov     rdx, rbp
0x10040166f  mov     rax, [rax+50h]
0x100401673  mov     [rsp+58h+ppv], rbx
0x100401678  call    cs:__guard_dispatch_icall_fptr
0x10040167e  mov     rbx, [rsp+58h+arg_0]
0x100401683  mov     rbp, [rsp+58h+arg_8]
0x100401688  mov     rsi, [rsp+58h+arg_10]
0x10040168d  add     rsp, 50h
0x100401691  pop     rdi
0x100401692  retn
```
