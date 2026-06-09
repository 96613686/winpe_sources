# ConvertFromUnicode(ulong *,uint,wchar_t const *,uint *,uchar *,uint *)

- ea: `0x1004016a0`
- end: `0x100401773`
- name: `?ConvertFromUnicode@@YAJPEAKIPEB_WPEAIPEAE2@Z`
- size: `211`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, const wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100421170`

## callees

- `0x1004016a0`
- `0x100439df0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1004016ee`
- `ole32!CoCreateInstance` at `0x1004016ee`

## pseudocode

```c
HRESULT __fastcall ConvertFromUnicode(
        unsigned int *a1,
        unsigned int a2,
        const wchar_t *a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  struct IMultiLanguage2 *v8; // rcx
  HRESULT result; // eax
  bool v12; // zf
  LPVOID ppv; // [rsp+40h] [rbp-18h] BYREF

  v8 = s_pMultiLanguage2;
  if ( s_pMultiLanguage2 )
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, unsigned int *, _QWORD, const wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))v8->lpVtbl->ConvertStringFromUnicode)(
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
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, unsigned int *, _QWORD, const wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))v8->lpVtbl->ConvertStringFromUnicode)(
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
0x1004016a0  mov     [rsp+arg_0], rbx
0x1004016a5  mov     [rsp+arg_8], rbp
0x1004016aa  mov     [rsp+arg_10], rsi
0x1004016af  push    rdi
0x1004016b0  sub     rsp, 50h
0x1004016b4  mov     rbp, rcx
0x1004016b7  mov     rbx, r9
0x1004016ba  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x1004016c1  mov     rdi, r8
0x1004016c4  mov     esi, edx
0x1004016c6  test    rcx, rcx
0x1004016c9  jnz     short loc_100401729
0x1004016cb  mov     [rsp+58h+var_18], rcx
0x1004016d0  lea     rax, [rsp+58h+var_18]
0x1004016d5  lea     r8d, [rcx+1]; dwClsContext
0x1004016d9  mov     [rsp+58h+ppv], rax; ppv
0x1004016de  lea     rcx, CLSID_CMultiLanguage; rclsid
0x1004016e5  xor     edx, edx; pUnkOuter
0x1004016e7  lea     r9, IID_IMultiLanguage2; riid
0x1004016ee  call    cs:__imp_CoCreateInstance
0x1004016f4  test    eax, eax
0x1004016f6  js      short loc_100401720
0x1004016f8  mov     rcx, [rsp+58h+var_18]
0x1004016fd  xor     eax, eax
0x1004016ff  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x100401708  jz      short loc_10040171C
0x10040170a  mov     rcx, [rsp+58h+var_18]
0x10040170f  mov     rax, [rcx]
0x100401712  mov     rax, [rax+10h]
0x100401716  call    cs:__guard_dispatch_icall_fptr
0x10040171c  xor     eax, eax
0x10040171e  test    eax, eax
0x100401720  jnz     short loc_10040175E
0x100401722  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100401729  mov     rdx, [rsp+58h+arg_28]
0x100401731  mov     r9, rdi
0x100401734  mov     rax, [rcx]
0x100401737  mov     r8d, esi
0x10040173a  mov     [rsp+58h+var_28], rdx
0x10040173f  mov     rdx, [rsp+58h+arg_20]
0x100401747  mov     [rsp+58h+var_30], rdx
0x10040174c  mov     rdx, rbp
0x10040174f  mov     rax, [rax+58h]
0x100401753  mov     [rsp+58h+ppv], rbx
0x100401758  call    cs:__guard_dispatch_icall_fptr
0x10040175e  mov     rbx, [rsp+58h+arg_0]
0x100401763  mov     rbp, [rsp+58h+arg_8]
0x100401768  mov     rsi, [rsp+58h+arg_10]
0x10040176d  add     rsp, 50h
0x100401771  pop     rdi
0x100401772  retn
```
